# AI Program


<h2>Summary:</h2>

The provided Java code implements an AI Survey Program that surveys users on various political and social issues to guess their potential political affiliation. The code utilizes functions for updating counters and guessing the political party to enhance modularity.
The guessing mechanism is simplistic and may be improved with more sophisticated algorithms as additional information is collected.
Overall, the program provides a basic demonstration of how user responses to survey questions can be used to make a simple guess about their political affiliation. Here is a summary of the key components:

1. Survey Questions and Answers:
* The program lists a set of questions and corresponding answer options stored in arrays. Answer options are presented with labels A, B, C, and D.

2. Political Party Counters:
* The program initializes counters for four political parties: Democratic, Socialist, Libertarian, and Republican.
* Users' responses are used to increment the respective party counters based on their choices (A, B, C, or D).

3. Survey Loop:
* The program conducts a survey by presenting each question along with answer options to the user.
* Users input their choices, and the counters are updated accordingly.

4. Guessing Political Affiliation:
* After the survey, the program employs a simple rule-based approach to guess the user's political affiliation.
* The party with the highest counter is chosen as the guess.

5. Output:
 * The program outputs the guessed political party based on the user's responses.


      import java.util.Scanner;


       public class StateCapitalQuiz {
       public static void main(String[] args) {
       // State capitals are combined in an array 1 = state 2 =capital
       String[][] stateCapitals = {
               {""Alabama", "Montgomery"},{"Alaska", "Juneau"},{"Arkansas", "Little Rock"},{"California", "Sacramento"},{"Colorado", "Denver"},{"Connecticut", "Hartford"},{"Delaware", "Dover"},{"Florida", "Tallahassee"},{"Georgia", "Atlanta"},{"Hawaii", "Honolulu"},{"Idaho", "Boise"},{"Illinois", "Springfield"},{"Indiana", "Indianapolis"},{"Iowa", "Des Moines"},{"Kansas", "Topeka"},{"Kentucky", "Frankfort"},{"Louisiana", "Baton Rouge"},{"Maine", "Augusta"},{"Maryland", "Annapolis"},{"Massachusetts", "Boston"},{"Michigan", "Lansing"},{"Minnesota", "Saint Paul"},{"Mississippi", "Jackson"},{"Missouri", "Jefferson City"},{"Montana", "Helena"},{"Nebraska", "Lincoln"},{"Nevada", "Carson City"},{"New Hampshire", "Concord"},{"New Jersey", "Trenton"},{"New Mexico", "Santa Fe"}, {"New York", "Albany"},{"North Carolina", "Raleigh"},{"North Dakota", "Bismarck"},{"Ohio", "Columbus"},{"Oklahoma", "Oklahoma City"},{"Oregon", "Salem"},{"Pennsylvania", "Harrisburg"},{"Rhode Island", "Providence"},{"South Carolina", "Columbia"},{"South Dakota",  "Pierre"},{"Tennessee",  "Nashville"},{"Texas",  "Austin"},{"Utah", "Salt Lake City"},{"Vermont", "Montpelier"},{ "Virginia", "Richmond"},{"Washington", "Olympia"},{"West Virginia", "Charleston"},{"Wisconsin", "Madison"},{"Wyoming", "Cheyenne"},
       };


       // Display the current contents of the array turn on so you can use it to test the connection
       //System.out.println("Current Contents of the Array:");
       for (String[] pair : stateCapitals) {
           //System.out.println(pair[0] + " - " + pair[1]);
       }


       // Sort the array by capital using Bubble Sort
       bubbleSortByCapital(stateCapitals);


       // Initialize Scanner to read user input
       Scanner scanner = new Scanner(System.in);


       // Initialize a variable to count correct answers
       int correctCount = 0;


       // Prompt the user to enter answers for all the state capitals
       for (String[] pair : stateCapitals) {
           System.out.print("Enter the capital of " + pair[0] + ": ");
           String userAnswer = scanner.nextLine();


           if (userAnswer.equalsIgnoreCase(pair[1])) {
               System.out.println("Correct!");
               correctCount++;
           } else {
               System.out.println("Incorrect. The correct answer is " + pair[1]);
           }
       }


       // Display the total correct count
       System.out.println("Total Correct Answers: " + correctCount);


       // Close the scanner to end game.
       scanner.close();
       }


       // Bubble Sort function to sort the array by capital
       private static void bubbleSortByCapital(String[][] arr) {
       int n = arr.length;
       boolean swapped;
       do {
           swapped = false;
           for (int i = 0; i < n - 1; i++) {
               if (arr[i][1].compareToIgnoreCase(arr[i + 1][1]) > 0) {
                   // Swap the elements if they are out of order
                   String[] temp = arr[i];
                   arr[i] = arr[i + 1];
                   arr[i + 1] = temp;
                   swapped = true;
               }
           }
       } while (swapped);


        }
        }


        import java.util.*;


        public class StateCapitalQuiz {


       public static void main(String[] args) {
       // Create a HashMap to store the state-capital pairs
       Map<String, String> stateCapitalMap = new HashMap<>();


       // Populate the HashMap with state-capital pairs
       stateCapitalMap.put("Alabama", "Montgomery");
       stateCapitalMap.put("Alaska", "Juneau");
       stateCapitalMap.put("Arkansas", "Little Rock");
       stateCapitalMap.put("Arizona", "Phoenix");
       stateCapitalMap.put("California", "Sacramento");
       stateCapitalMap.put("Colorado", "Denver");
       stateCapitalMap.put("Connecticut", "Hartford");
       stateCapitalMap.put("Florida", "Tallahassee");
       stateCapitalMap.put("Delaware", "Dover");
       stateCapitalMap.put("Georgia", "Atlanta");
       stateCapitalMap.put("Hawaii", "Honolulu");
       stateCapitalMap.put("Idaho", "Boise");
       stateCapitalMap.put("Illinois", "Springfield");
       stateCapitalMap.put("Indiana", "Indianapolis");
       stateCapitalMap.put("Iowa",  "Des Moines");
       stateCapitalMap.put("Kansas", "Topeka");
       stateCapitalMap.put("Kentucky", "Frankfort");
       stateCapitalMap.put("Louisiana", "Baton Rouge");
       stateCapitalMap.put("Maine", "Augusta");
       stateCapitalMap.put("Maryland", "Annapolis");
       stateCapitalMap.put("Massachusetts", "Boston");
       stateCapitalMap.put("Michigan", "Lansing");
       stateCapitalMap.put("Minnesota", "Saint Paul");
       stateCapitalMap.put("Mississippi", "Jackson");
       stateCapitalMap.put("Missouri", "Jefferson City");
       stateCapitalMap.put("Montana", "Helena");
       stateCapitalMap.put("Nebraska", "Lincoln");
       stateCapitalMap.put("Nevada", "Carson City");
       stateCapitalMap.put("New Hampshire", "Concord");
       stateCapitalMap.put("New Jersey", "Trenton");
       stateCapitalMap.put("New Mexico", "Santa Fe");
       stateCapitalMap.put("New York", "Albany");
       stateCapitalMap.put("North Carolina", "Raleigh");
       stateCapitalMap.put("North Dakota", "Bismarck");
       stateCapitalMap.put("Ohio", "Columbus");
       stateCapitalMap.put("Oklahoma", "Oklahoma City");
       stateCapitalMap.put("Oregon", "Salem");
       stateCapitalMap.put("Pennsylvania", "Harrisburg");
       stateCapitalMap.put("Rhode Island", "Providence");
       stateCapitalMap.put("South Carolina", "Columbia");
       stateCapitalMap.put("South Dakota",  "Pierre");
       stateCapitalMap.put("Tennessee",  "Nashville");
       stateCapitalMap.put("Texas",  "Austin");
       stateCapitalMap.put("Utah", "Salt Lake City");
       stateCapitalMap.put("Vermont", "Montpelier");
       stateCapitalMap.put("Virginia", "Richmond");
       stateCapitalMap.put("Washington", "Olympia");
       stateCapitalMap.put("West Virginia", "Charleston");
       stateCapitalMap.put("Wisconsin", "Madison");
       stateCapitalMap.put("Wyoming", "Cheyenne");


       // Add entries for all 50 states and capitals here...


       // Display the content of the HashMap
       System.out.println("State-Capital Pairs:");
       for (String state : stateCapitalMap.keySet()) {
           String capital = stateCapitalMap.get(state);
           System.out.println("The capital of "+ state + " is " + capital);
       }


       // Create a TreeMap to sort the map
       TreeMap<String, String> sortedMap = new TreeMap<>(stateCapitalMap);


       // Prompt the user to enter a state
       Scanner scanner = new Scanner(System.in);
       System.out.print("Enter a state: ");
       String userState = scanner.nextLine();


       // Check if the user's input exists in the map
       if (sortedMap.containsKey(userState)) {
           String capital = sortedMap.get(userState);
           System.out.println("The capital of " + userState + " is " + capital);
       } else {
