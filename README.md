git code trials
fcfs
package org.cloudbus.cloudsim.examples;

import java.text.ParseException;

class FCFS {

    static void findWaitingTime(int processes[], int n, int bt[], int wt[]) {
        wt[0] = 0;
        for (int i = 1; i < n; i++) {
            wt[i] = bt[i - 1] + wt[i - 1];
        }
    }

    static void findTurnAroundTime(int processes[], int n, int bt[], int wt[], int tat[]) {
        for (int i = 0; i < n; i++) {
            tat[i] = bt[i] + wt[i];
        }
    }

    static void findAvgTime(int processes[], int n, int bt[]) {
        int wt[] = new int[n], tat[] = new int[n];
        int total_wt = 0, total_tat = 0;

        findWaitingTime(processes, n, bt, wt);
        findTurnAroundTime(processes, n, bt, wt, tat);

        System.out.println("Processes  Burst Time  Waiting Time  Turnaround Time");

        for (int i = 0; i < n; i++) {
            total_wt += wt[i];
            total_tat += tat[i];
            System.out.println("  " + (i + 1) + "\t\t" + bt[i] + "\t    " + wt[i] + "\t\t " + tat[i]);
        }

        float avg_wt = (float) total_wt / (float) n;
        float avg_tat = (float) total_tat / (float) n;

        System.out.println("\nAverage Waiting Time = " + avg_wt);
        System.out.println("Average Turnaround Time = " + avg_tat);
    }

    public static void main(String args[]) throws ParseException {
        int processes[] = {1, 2, 3};
        int n = processes.length;
        int burst_time[] = {7, 5, 8};

        findAvgTime(processes, n, burst_time);
    }
}






fibonacci
#include<stdio.h>

int main() {
    int i, n;
    int t1 = 0, t2 = 1;
    int nextint;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("The number of elements can't be zero or negative.\n");
    } else if (n == 1) {
        printf("Fibonacci series: %d\n", t1);
    } else {
        printf("Fibonacci series: %d, %d", t1, t2);

        for (i = 3; i <= n; i++) {
            nextint = t1 + t2;
            printf(", %d", nextint);
            t1 = t2;
            t2 = nextint;
        }

        printf("\n");
    }

    return 0;
}




factorial

#include<stdio.h>

int main() {
    unsigned long long fact = 1;
    int n, i;

    printf("Enter n: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Factorial is not defined for negative numbers.\n");
    } else {
        for (i = 1; i <= n; i++) {
            fact *= i;
        }
        printf("The factorial of %d is %llu\n", n, fact);
    }

    return 0;
}


largest of 3
#include <stdio.h>

int main() {
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b && a >= c) {
        printf("Largest number is %d\n", a);
    } else if (b >= a && b >= c) {
        printf("Largest number is %d\n", b);
    } else {
        printf("Largest number is %d\n", c);
    }

    return 0;
}
