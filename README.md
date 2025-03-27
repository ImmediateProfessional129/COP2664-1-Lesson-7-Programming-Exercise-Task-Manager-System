# COP2664-1-Lesson-7-Programming-Exercise-Task-Manager-System
This repository is a submission link for COP2664-1: Lesson 7 Programming Exercise Task Manager System

// This program is designed to construct a task manager system that can be used to preside over tasks and their dependencies.

enum TaskState {
    case pending, inProgress, completed
} // This enum is used to represent the state of a task.

struct TaskDetails {
    var priority: String
    var dueDate: String
} // This struct is used to store the priority and due date of a task.

class Task {
    var title: String
    var state: TaskState
    var description: String
    var details: TaskDetails
// This class is used to represent a task. It has properties for the title, state, description, and details.
    init(title: String, state: TaskState, description: String, details: TaskDetails) {
        self.title = title
        self.state = state
        self.description = description
        self.details = details
    } // This is the initializer for the Task class.

    func markInProgress() {
        if state == .pending {
            state = .inProgress
        } // This function is used to mark a task as in progress.
    } 

    func markCompleted() {
        if state == .inProgress {
            state = .completed
        } // This function is used to mark a task as completed.
    }

    func displayTaskDetails() {
        print("Task: \(title)")
        print("State: \(state)")
        print("Description: \(description)")
        print("Priority: \(details.priority)")
        print("Due Date: \(details.dueDate)\n")
    } // This function is used to display the details of a task.
}

let task1 = Task(title: "House Chores", state: .pending, description: "Dust all the furniture around the house.", details: TaskDetails(priority: "Low", dueDate: "2021-10-7"))
let task2 = Task(title: "Dinner", state: .pending, description: "Prepare dinner for the guests that are coming tomorrow.", details: TaskDetails(priority: "High", dueDate: "2022-7-4"))
let task3 = Task(title: "Haircut Appointment", state: .pending, description: "Call the barbershop and set up the day and time for your haircut.", details: TaskDetails(priority: "Medium", dueDate: "2023-5-23")) // These are the three tasks that are created.

task1.markCompleted()
task2.markInProgress()
task3.markInProgress()
task1.displayTaskDetails()
task2.displayTaskDetails()
task3.displayTaskDetails()
// These are the functions that are used to mark tasks as completed and in progress, and then display their details.
