#include <stdio.h>
#include <string.h>

void respondToCommand(char *command) {
    if (strcmp(command, "hello") == 0) {
        printf("Hello! How can I assist you today?\n");
    } else if (strcmp(command, "who are you") == 0) {
        printf("I am your AI assistant!\n");
    } else if (strcmp(command, "thank you") == 0) {
        printf("You're welcome!\n");
    } else if (strcmp(command, "exit") == 0) {
        printf("Goodbye!\n");
    } else {
        printf("I'm sorry, I don't understand that command.\n");
    }
}

int main() {
    char command[100];

    printf("Welcome! I am your AI assistant.\n");
    printf("Commands: hello, who are you, thank you, exit\n");

    while (1) {
        printf("\nEnter a command: ");
        fgets(command, sizeof(command), stdin);
        command[strcspn(command, "\n")] = 0;  // Remove newline character

        if (strcmp(command, "exit") == 0) {
            break;
        }

        respondToCommand(command);
    }

    return 0;
}
