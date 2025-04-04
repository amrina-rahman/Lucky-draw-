# Lucky-draw-
A project on Lucky Draw Winner Selection. It is prepared by 1. Amrina Rahman (242-35-589) 2.Al Jubair Badhon (242-35-428) 3. Milton (242-35--589) .
This project is a simple lucky draw selector that randomly picks winners from a list of contestants. Users can input multiple names, and the program will use a random selection method to determine the lucky winners. This is useful for giveaways, raffles, or any event where a fair and unbiased selection is needed.
 The code is designed to be user-friendly, providing clear prompts and feedback throughout the process.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>
#define MAX_PARTICIPANTS 50
struct Participant {
    char name[50];
};
int main() {
    struct Participant participants[MAX_PARTICIPANTS];
    int num, numWinners, i, draw;
    // Input number of participants
    printf("Welcome to Lucky Draw Winner Selector!\nEnter the number of participants: ");
    scanf("%d", &num);
    // Check if the number of participants is valid
    if (num > MAX_PARTICIPANTS || num < 1) {
        printf("Invalid number of participants. Please enter a number between 1 and %d.\n", MAX_PARTICIPANTS);
        return 1;
    }
    // Input names of participants
    for (i = 0; i < num; i++) {
        printf("Enter the name of participant %d: ", i + 1);
        scanf("%s", participants[i].name);
    }
    // Input number of winners
    printf("Enter the number of winners (1 to %d): ", num);
    scanf("%d", &numWinners);
    // Check if the number of winners is valid
    if (numWinners < 1 || numWinners > num) {
        printf("Invalid number of winners. Please enter a number between 1 and %d.\n", num);
        return 1;
    }
    srand(time(0));
    // Draw multiple winners
    printf("\nThe winners are:\n");
    for (i = 0; i < numWinners; i++) {
        draw = rand() % num;  // Randomly select a winner
        printf("Winner %d: %s\n", i + 1, participants[draw].name);
    }
    return 0;
}
