# Lucky-draw-
A project on Lucky Draw Winner Selection. It is prepared by 1. Amrina Rahman (242-35-589) 2.Al Jubair Badhon (242-35-428) 3. Milton (242-35--589) 
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>

#define MAX_PARTICIPANTS 50

int main() {
    char participants[MAX_PARTICIPANTS][50];
    int num, i ,draw;
    //input number of participants
    printf("welcome to Lucky Draw Winner Selector!\nEnter the number of participants: ");
    scanf("%d", &num);
    if (num > MAX_PARTICIPANTS || num <1)
    {
        printf("Invalid number of participants.");
    }
    //input names of participants
        for ( i = 0; i < num; i++)
    {
        printf("Enter the name of participant %d: ", i + 1);
        scanf("%s", participants[i]);
    }
    //randomly select a winner
    srand(time(0));
    draw = rand() % num;
    printf("The winner is %s!!", participants[draw]);
    
    return 0;
}
