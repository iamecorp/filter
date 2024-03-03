import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

class PersonalData {
    private String surname;
    private String firstName;
    private String patronymic;
    private String birthDate;
    private long phoneNumber;
    private char gender;

    // Constructor
    public PersonalData(String surname, String firstName, String patronymic, String birthDate, long phoneNumber, char gender) {
        this.surname = surname;
        this.firstName = firstName;
        this.patronymic = patronymic;
        this.birthDate = birthDate;
        this.phoneNumber = phoneNumber;
        this.gender = gender;
    }

    // Getter methods
    public String getSurname() {
        return surname;
    }

    public String getFirstName() {
        return firstName;
    }

    public String getPatronymic() {
        return patronymic;
    }

    public String getBirthDate() {
        return birthDate;
    }

    public long getPhoneNumber() {
        return phoneNumber;
    }

    public char getGender() {
        return gender;
    }

    // toString method to format data for writing to file
    @Override
    public String toString() {
        return String.format("%s %s %s %s %d %c", surname, firstName, patronymic, birthDate, phoneNumber, gender);
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter data (Surname Name Patronymic BirthDate PhoneNumber Gender):");

        try {
            String input = scanner.nextLine();
            String[] data = input.split(" ");

            // Check if input data length is correct
            if (data.length != 6) {
                throw new IllegalArgumentException("Incorrect number of data entries. Please enter data in format: Surname Name Patronymic BirthDate PhoneNumber Gender");
            }

            // Parse input data
            String surname = data[0];
            String firstName = data[1];
            String patronymic = data[2];
            String birthDate = data[3];
            long phoneNumber = Long.parseLong(data[4]);
            char gender = data[5].charAt(0);

            // Create PersonalData object
            PersonalData personalData = new PersonalData(surname, firstName, patronymic, birthDate, phoneNumber, gender);

            // Write data to file
            writeToFile(personalData);
        } catch (IllegalArgumentException | IOException e) {
            System.err.println(e.getMessage());
        } finally {
            scanner.close();
        }
    }

    private static void writeToFile(PersonalData personalData) throws IOException {
        String filename = personalData.getSurname() + ".txt";
        BufferedWriter writer = new BufferedWriter(new FileWriter(filename, true));

        try {
            // Write data to file
            writer.write(personalData.toString());
            writer.newLine();
            System.out.println("Data has been successfully written to file: " + filename);
        } finally {
            // Close the file
            writer.close();
        }
    }
}
