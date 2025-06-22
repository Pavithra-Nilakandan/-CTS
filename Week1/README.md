# Week 1 Assignment 
This folder contains the code and output screenshot for week 1 assignment.
# SINGLETON PATTERN:

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


# IMPLEMENTING THE FACTORY METHOD PATTERN:

interface Notification {
    void notifyUser();
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

class NotificationFactory {
    public Notification createNotification(String type) {
        if (type == null || type.isEmpty()) return null;
        switch (type) {
            case "SMS":
                return new SMSNotification();
            case "Email":
                return new EmailNotification();
            case "Push":
                return new PushNotification();
            default:
                return null;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        NotificationFactory factory = new NotificationFactory();
        Notification sms = factory.createNotification("SMS");
        sms.notifyUser();
        Notification email = factory.createNotification("Email");
        email.notifyUser();
        Notification push = factory.createNotification("Push");
        push.notifyUser();
        }
}
OUTPUT:
Sending SMS Notification
Sending Email Notification
Sending Push Notification

![Screenshot 2025-06-22 230139](https://github.com/user-attachments/assets/5b7b4147-cc2f-4475-971c-391379a8ffd5)

# E-COMMERCE PLATFORM SEARCH FUNCTION:

import java.util.*;
class Product {
    String name;
    double price;
    Product(String name, double price) {
        this.name = name;
        this.price = price;
    }
}
public class Main {
    public static void main(String[] args) {
        List<Product> productList = new ArrayList<>();
        productList.add(new Product("Laptop", 55000.00));
        productList.add(new Product("Smartphone", 20000.00));
        productList.add(new Product("Headphones", 1500.00));
        productList.add(new Product("Keyboard", 700.00));
        productList.add(new Product("Mouse", 500.00));
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter product name to search: ");
        String query = sc.nextLine();
        boolean found = false;
        for (Product p : productList) {
            if (p.name.equalsIgnoreCase(query)) {
                System.out.println("Product found: " + p.name + " | Price: ₹" + p.price);
                found = true;
                break;
            }
        }
        if (!found) {
            System.out.println("Product not found.");
        }
        }
    }

OUTPUT:
Enter product name to search: Tablet
Product not found.
    
 ![Screenshot 2025-06-22 230831](https://github.com/user-attachments/assets/379f9364-5e3b-412e-ae74-c5beb8797904)

# FINANCIAL FORECASTING:

 import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of months: ");
        int n = sc.nextInt();
        double[] sales = new double[n];
        System.out.println("Enter sales for each month:");
        for (int i = 0; i < n; i++) {
            System.out.print("Month " + (i + 1) + ": ");
            sales[i] = sc.nextDouble();
        }
        System.out.print("Enter the window size for moving average: ");
        int window = sc.nextInt();
        if (window > n) {
            System.out.println("Window size cannot be greater than number of months.");
            return;
        }
        double sum = 0;
        for (int i = n - window; i < n; i++) {
            sum += sales[i];
        }
        double forecast = sum / window;
        System.out.println("Forecasted sales for next month: ₹" + forecast);
    }
}

OUTPUT:
Enter number of months: 6
Enter sales for each month:
Month 1: 12000
Month 2: 13500
Month 3: 15000
Month 4: 17000
Month 5: 16000
Month 6: 18000
Enter the window size for moving average: 3
Forecasted sales for next month: ₹17000.0
![Screenshot 2025-06-22 231410](https://github.com/user-attachments/assets/c3c39a46-f8c3-434e-be8f-1246962e1da6)





