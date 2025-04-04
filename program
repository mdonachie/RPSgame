#include <iostream>
#include <string>
#include <cstdlib>
using namespace std;

class RPS {
public:
    //game states
    enum GameResult {
        USER_WIN = 1,
        DRAW = 2,
        COMPUTER_WIN = 3
    };

    void preamble();
    void userTurn();
    int checkUserInput();
    void computerTurn(int x);
    void decideWinner();
    void end();

private:
    string stateChoices[3] = {"Rock", "Paper", "Scissors"};
    string userInput;
    string computerInput;
    GameResult gameState;  
};

int main() {
    srand(time(0)); //seed rand
    RPS rps; //class object
    int x; // necessary for computerTurn

    rps.preamble();
    rps.userTurn();
    rps.checkUserInput();
    rps.computerTurn(x);
    rps.decideWinner();
    rps.end();

    return 0;
}

void RPS::preamble() {
    cout << "Welcome to Rock Paper Scissors. Today you will play vs the computer. Let's begin!" << endl;
}

void RPS::userTurn() {
    cout << "Rock, Paper, or Scissors? " << endl;
    cin >> userInput;
}

int RPS::checkUserInput() {
    if (userInput != "Rock" && userInput != "Paper" && userInput != "Scissors" &&
        userInput != "rock" && userInput != "paper" && userInput != "scissors") {
        cout << "Invalid input, please run the program again." << endl;
        exit(0); //force end program
    }
    return 1; 
}

void RPS::computerTurn(int x) {
    x = rand() % 3; //rand computer choice
    computerInput = stateChoices[x];
    cout << "The computer has chosen... " << computerInput << endl;
}

void RPS::decideWinner() {
    // rock
    if (userInput == "Rock" || userInput == "rock") {
        if (computerInput == "Scissors")
            gameState = USER_WIN;
        else if (computerInput == "Rock")
            gameState = DRAW;
        else if (computerInput == "Paper")
            gameState = COMPUTER_WIN;
    }
    // paper
    else if (userInput == "Paper" || userInput == "paper") {
        if (computerInput == "Rock")
            gameState = USER_WIN;
        else if (computerInput == "Paper")
            gameState = DRAW;
        else if (computerInput == "Scissors")
            gameState = COMPUTER_WIN;
    }
    // scissors
    else if (userInput == "Scissors" || userInput == "scissors") {
        if (computerInput == "Paper")
            gameState = USER_WIN;
        else if (computerInput == "Scissors")
            gameState = DRAW;
        else if (computerInput == "Rock")
            gameState = COMPUTER_WIN;
    }
}

void RPS::end() {
    switch(gameState) {
        case USER_WIN:
            cout << "User has won!" << endl;
            break;
        case DRAW:
            cout << "Match has ended in a draw." << endl;
            break;
        case COMPUTER_WIN:
            cout << "Computer has won!" << endl;
            break;
        default:
            cout << "Invalid game state." << endl;
            break;
    }
}
