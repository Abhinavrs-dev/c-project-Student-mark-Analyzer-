#include <iostream>
using namespace std;


int findTotal(int marks[], int n) {
    int total = 0;

    for (int i = 0; i < n; i++) {
        total += marks[i];
    }

    return total;
}


double totalAverage(int total, int n) {
    double average = (double)total / n;

    return average;
}


int highestMarks(int marks[], int n) {
    int highest = marks[0];

    for (int i = 1; i < n; i++) {
        if (marks[i] > highest) {
            highest = marks[i];
        }
    }

    return highest;
}

int lowestMark(int marks[], int n) {
    int lowest = marks[0];

    for (int i = 1; i < n; i++) {
        if (marks[i] < lowest) {
            lowest = marks[i];
        }
    }

    return lowest;
}


int countPassed(int marks[], int n) {
    int passed = 0;

    for (int i = 0; i < n; i++) {
        if (marks[i] >= 40) {
            passed++;
        }
    }

    return passed;
}


int countFailed(int marks[], int n) {
    int failed = 0;

    for (int i = 0; i < n; i++) {
        if (marks[i] < 40) {
            failed++;
        }
    }

    return failed;
}


int main() {

    char choice;

    do {

        int marks[100];
        int n;


        cout << "Enter Student Number: ";
        cin >> n;

        while (n < 1 || n > 100) {
            cout << "Invalid Count! Enter between 1 and 100." << endl;
            cout << "Enter Student Number: ";
            cin >> n;
        }


        for (int i = 0; i < n; i++) {
            cout << "Enter Marks for Student " << i + 1 << ": ";
            cin >> marks[i];
        }


        cout << "========== STUDENT MARKS ==========" << endl;

        for (int i = 0; i < n; i++) {
            cout << "Student " << i + 1 << ": "
                 << marks[i] << endl;
        }

        int total = findTotal(marks, n);
        double average = totalAverage(total, n);
        int highest = highestMarks(marks, n);
        int lowest = lowestMark(marks, n);
        int passed = countPassed(marks, n);
        int failed = countFailed(marks, n);

cout << "=*=*=*=*=*=* STUDENT REPORT =*=*=*=*=*=*=" << endl;

        cout << "Total Marks       : " << total << endl;
        cout << "Average Marks     : " << average << endl;
        cout << "Highest Marks     : " << highest << endl;
        cout << "Lowest Marks      : " << lowest << endl;
        cout << "Passed Students   : " << passed << endl;
        cout << "Failed Students   : " << failed << endl;


        cout << "Analyse another group? (q/w): ";
        cin >> choice;

    } while (choice == 'q' || choice == 'Q');

    cout << "Analyzer Exit!!" << endl;

    return 0;
}
