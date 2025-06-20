# Week 1 Assignment - Singleton Pattern
This folder contains the code and output screenshot for week 1 assignment.

[Week1_SingletonPattern_CTS.docx](https://github.com/user-attachments/files/20838824/Week1_SingletonPattern_CTS.docx)
![Screenshot 2025-06-20 201404](https://github.com/user-attachments/assets/1083c928-06f8-4f29-8ddd-7b414adbdfde)

class Logger {
    private static Logger instance = new Logger();
    private Logger() {
        System.out.println("Logger instance created");
    }
    public static Logger getInstance() {
        return instance;
    }
    public void log(String message) {
        System.out.println("Log: " + message);
    }
}

public class Main {
    public static void main(String[] args) {
        Logger logger1 = Logger.getInstance();
        Logger logger2 = Logger.getInstance();
        logger1.log("First log message");
        logger2.log("Second log message");
        if (logger1 == logger2) {
            System.out.println("Same instance used");
        } else {
            System.out.println("Different instances");
        }
    }
}
OUTPUT:
Logger instance created
Log: First log message
Log: Second log message
Same instance used
