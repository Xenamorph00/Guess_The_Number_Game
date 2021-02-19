// Guess_The_Number_Game

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {

int userNum = 0, attemps = 5 ;

//Current time.
time_t rawtime;
struct tm * timeinfo;

time ( &rawtime );
timeinfo = localtime ( &rawtime );

srand(time(NULL));   // Initialization, should only be called once.
int radNum = rand() % 21; // random int between 0 and 20.

//Structuring attempt functionality.


//Rules of the game and local time.
printf ("\t\t\t\t\t\t\t\tCurrent local time and date: %s", asctime (timeinfo));

puts("\t\t\t\aWelcome to Guess the Number !"
    "\n\nRULES:"
    "\n\n---------------------------------------------------------------------\n"
    "*You have 5 attempts to guess the number correctly\n"
    "*You should only enter numbers from 0 to 20 ; both 0 and 20 included\n"
    "\t\t\t\tGOOD LUCK!"
    "\n---------------------------------------------------------------------\n") ;

while(userNum != radNum){
//User enters a number.
    printf("\nEnter a number: ") ;
    scanf("%d", &userNum) ;

//Conditions
    if(userNum == radNum && attemps == 5) {
        printf("\nCONGRATS you got it on the first try!\n") ;
        break ;
    }
    else if(userNum == radNum) {
        printf("\nCONGRATS you got it!\n") ;
        break ;
    }
    else if(attemps == 0) {
        printf("\nYou've run out of attemps.") ;
        break ;
    }



    else if(userNum != radNum) {
        if(userNum == (radNum - 1)) {
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're close...") ;
            attemps -= attemps ;
            }
        else if(userNum == (radNum - 2)){
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're close...") ;
            }
        else if(userNum <= (radNum - 3)){
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're not even close...") ;
            }
        else if(userNum == (radNum + 1)){
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're close...") ;
            }
        else if(userNum == (radNum + 2)){
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're close...") ;
            }
        else if(userNum >= (radNum + 3)){+
            printf("\nYou have %d attemps left.\n", attemps) ;
            printf("\nYou're not even close...") ;
            }

    }


}

return 0;
}
