#include <stdio.h>

int main() {
    int n, i, tq;
    int burst[10], rem[10];
    int wait[10], tat[10];
    int time = 0;
    int completed;

    printf("Enter number of processes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter burst time of P%d: ", i + 1);
        scanf("%d", &burst[i]);
        rem[i] = burst[i];
        wait[i] = 0;
    }

    printf("Enter time quantum: ");
    scanf("%d", &tq);

    do {
        completed = 1;

        for (i = 0; i < n; i++) {
            if (rem[i] > 0) {
                completed = 0;

                if (rem[i] > tq) {
                    time += tq;
                    rem[i] -= tq;
                } else {
                    time += rem[i];
                    wait[i] = time - burst[i];
                    rem[i] = 0;
                }
            }
        }
    } while (!completed);

    for (i = 0; i < n; i++) {
        tat[i] = burst[i] + wait[i];
    }

    printf("\nProcess\tBurst Time\tWaiting Time\tTurnaround Time\n");
    for (i = 0; i < n; i++) {
        printf("P%d\t%d\t\t%d\t\t%d\n", i + 1, burst[i], wait[i], tat[i]);
    }

    return 0;
}
