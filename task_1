# task_1
#include <iostream>
#include <vector>
#include <string>
#include <ctime>
#include <cstdlib>

const int MAX_LIVES = 6;
const std::vector<std::string> WORDS = {"programming", "hangman", "computer", "software", "engineer"};

void displayWord(const std::string& word, const std::vector<bool>& guessed) {
    for (size_t i = 0; i < word.length(); ++i) {
        if (guessed[i]) {
            std::cout << word[i] << ' ';
        } else {
            std::cout << "_ ";
        }
    }
    std::cout << std::endl;
}

bool isWordGuessed(const std::vector<bool>& guessed) {
    for (bool letterGuessed : guessed) {
        if (!letterGuessed) {
            return false;
        }
    }
    return true;
}

int main() {
    std::srand(std::time(0));
    std::string word = WORDS[std::rand() % WORDS.size()];
    std::vector<bool> guessed(word.length(), false);
    int lives = MAX_LIVES;
    char guess;

    std::cout << "Добро пожаловать в игру «Виселица»!" << std::endl;

    while (lives > 0 && !isWordGuessed(guessed)) {
        std::cout << "Загаданное слово: ";
        displayWord(word, guessed);
        std::cout << "Осталось жизней: " << lives << std::endl;
        std::cout << "Введите букву: ";
        std::cin >> guess;

        bool correctGuess = false;
        for (size_t i = 0; i < word.length(); ++i) {
            if (word[i] == guess) {
                guessed[i] = true;
                correctGuess = true;
            }
        }

        if (!correctGuess) {
            --lives;
        }
    }

    if (isWordGuessed(guessed)) {
        std::cout << "Поздравляем! Вы угадали слово: " << word << std::endl;
    } else {
        std::cout << "Вы проиграли. Загаданное слово было: " << word << std::endl;
    }

    return 0;
}
