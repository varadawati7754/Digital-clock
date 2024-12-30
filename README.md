#include <stdio.h>
#include <time.h>
#include <unistd.h> // For sleep function

int main() {
    while (1) {
        // Get the current time
        time_t current_time;
        struct tm *time_info;

        time(&current_time);         // Get the time in seconds since epoch
        time_info = localtime(&current_time); // Convert to local time

        // Clear the screen
        system("clear");

        // Display the current time in HH:MM:SS format
        printf("====================================\n");
        printf("           Digital Clock\n");
        printf("====================================\n");
        printf("           %02d:%02d:%02d\n",
               time_info->tm_hour,
               time_info->tm_min,
               time_info->tm_sec);
        printf("====================================\n");

        // Wait for 1 second before updating the time
        sleep(1);
    }

    return 0;
}
