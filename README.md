# PROJECT-4
Student study time mismanagement
#include <iostream>
#include <vector>
using namespace std;

struct Task {
    string name;
    bool completed;
};

vector<Task> tasks;

void addTask() {
    Task t;
    cout << "Enter task: ";
    cin.ignore();
    getline(cin, t.name);
    t.completed = false;
    tasks.push_back(t);
    cout << "Task added!\n";
}

void viewTasks() {
    for(int i = 0; i < tasks.size(); i++) {
        cout << i+1 << ". " << tasks[i].name;
        if(tasks[i].completed)
            cout << " [Done]";
        cout << endl;
    }
}

void markComplete() {
    int n;
    cout << "Enter task number: ";
    cin >> n;
    if(n > 0 && n <= tasks.size()) {
        tasks[n-1].completed = true;
        cout << "Marked as completed!\n";
    } else {
        cout << "Invalid task!\n";
    }
}

int main() {
    int choice;
    while(true) {
        cout << "\n1. Add Task\n2. View Tasks\n3. Mark Complete\n4. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch(choice) {
            case 1: addTask(); break;
            case 2: viewTasks(); break;
            case 3: markComplete(); break;
            case 4: return 0;
            default: cout << "Invalid choice\n";
        }
    }
}
