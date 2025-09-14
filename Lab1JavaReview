import java.util.Scanner;

    public class Lab1JavaReview {

        static String[] bookTitles = new String[5];
        static String[] bookStatus = new String[5];
        static int bookCount = 0;

        public static void main(String[] args) {
            Scanner ii = new Scanner(System.in);
            int choice;

            do {
                displayMenu();
                System.out.print("Please enter your choice: ");
                while (!ii.hasNextInt()) {
                    System.out.println("Invalid input. Please enter a number.");
                    ii.next(); 
                }
                choice = ii.nextInt();
                ii.nextLine();

                switch (choice) {
                    case 1:
                        addBook(ii);
                        break;
                    case 2:
                        updateBookStatus(ii);
                        break;
                    case 3:
                        showBooks();
                        break;
                    case 4:
                        generateReport();
                        break;
                    case 5:
                        System.out.println("Exiting the Library Management System. Goodbye!");
                        break;
                    default:
                        System.out.println("Invalid choice. Please select a valid option.");
                }
                System.out.println();
            } while (choice != 5);

            ii.close();
        }

        //  Display Menu
        public static void displayMenu() {
            System.out.println("");
            System.out.println("========= Library Book Management System =========");
            System.out.println("[1] Add Book");
            System.out.println("[2] Update Book Status");
            System.out.println("[3] Show All Books");
            System.out.println("[4] Generate Report");
            System.out.println("[5] Exit");
            System.out.println("");
        }

        // 1. Add Book
        public static void addBook(Scanner scanner) {
            if (bookCount >= 5) {
                System.out.println("");
                System.out.println("Book limit reached! Cannot add more books.");
                return;
            }

            System.out.print("Enter book title: ");
            String title = scanner.nextLine();

            bookTitles[bookCount] = title;
            bookStatus[bookCount] = "Available";
            bookCount++;

            System.out.println("");
            System.out.println("Book added successfully.");
        }

        // 2. Update Book Status
        public static void updateBookStatus(Scanner scanner) {
            if (bookCount == 0) {
                System.out.println("");
                System.out.println("No books available to update.");
                return;
            }

            showBooks();
            System.out.println("");
            System.out.print("Enter the book number to update status: ");
            int bookNumber;

            while (!scanner.hasNextInt()) {
                
                System.out.println("Invalid input. Please enter a valid book number.");
                scanner.next();
            }
            bookNumber = scanner.nextInt();
            scanner.nextLine(); 

            if (bookNumber < 1 || bookNumber > bookCount) {
                System.out.println("Invalid book number.");
                return;
            }

            int index = bookNumber - 1;
            // Toggle the status
            if (bookStatus[index].equals("Available")) {
                bookStatus[index] = "Borrowed";
            } else {
                bookStatus[index] = "Available";
            }

            System.out.println("");
            System.out.println("Book status updated successfully.");
        }

        // 3. Show All Books
        public static void showBooks() {
            if (bookCount == 0) {
                System.out.println("");
                System.out.println("No books registered yet.");
                return;
            }

            System.out.println("===== List of Books =====");
            for (int i = 0; i < bookCount; i++) {
                System.out.println((i + 1) + ". Title: " + bookTitles[i] + " | Status: " + bookStatus[i]);
            }
        }

        // 4. Generate Report
        public static void generateReport() {
            int availableCount = 0;
            int borrowedCount = 0;

            for (int i = 0; i < bookCount; i++) {
                if (bookStatus[i].equals("Available")) {
                    availableCount++;
                } else if (bookStatus[i].equals("Borrowed")) {
                    borrowedCount++;
                }
            }
            System.out.println("");
            System.out.println("===== Book Report =====");
            System.out.println("Total Books: " + bookCount);
            System.out.println("Available Book/s: " + availableCount);
            System.out.println("Borrowed Book/s: " + borrowedCount);
        }
    }
