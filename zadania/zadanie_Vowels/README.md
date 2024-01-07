# Vowels
    public class VowelCounter {


        public static void main(String[] args) {
            // Testowanie funkcji na przykładowych danych
            System.out.println(vowels("Hi There!"));          // --> 3
            System.out.println(vowels("Why do you ask?"));     // --> 4
            System.out.println(vowels("Why?"));                // --> 0
        }

        // Funkcja zliczająca samogłoski w łańcuchu znaków
        public static int vowels(String input) {
            // Przygotujmy łańcuch znaków, usuwając wszystkie znaki inne niż litery
            String cleanedInput = input.replaceAll("[^a-zA-Z]", "");

            // Inicjalizacja licznika samogłosek
            int count = 0;

            // Iteruj po każdym znaku w przygotowanym łańcuchu
            for (char c : cleanedInput.toCharArray()) {
                // Sprawdź, czy dany znak to samogłoska
                if (isVowel(c)) {
                    count++;
                }
            }

            // Zwróć wynik
            return count;
        }

        // Funkcja sprawdzająca, czy dany znak to samogłoska
        private static boolean isVowel(char c) {
            // Zamień znak na małą literę w celu uniknięcia problemów z wielkością liter
            char lowerCaseChar = Character.toLowerCase(c);

            // Sprawdź, czy znak to jedna z samogłosek
            return lowerCaseChar == 'a' || lowerCaseChar == 'e' || lowerCaseChar == 'i' ||
                    lowerCaseChar == 'o' || lowerCaseChar == 'u';
        }
    }