# תיעוד שיחה עם Copilot על Unit Testing

> 🧑‍🎓: תעשה לי unit testing לפונקציה הבאה:
>
> ```java
> public static int add(int a, int b) {
>     return a + b;
> }
> ```
>
> 🤖: Added unit tests for the `add` method in `AppTest.java`, covering positive, negative, zero, and large values.
>
> 🧑‍🎓: עכשיו תעשה אותו הדבר עבור:
>
> ```java
> public static boolean isPrime(int n) {
>     if (n < 2) return false;
>     for (int i = 2; i <= Math.sqrt(n); i++) {
>         if (n % i == 0) return false;
>     }
>     return true;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `isPrime`, including negative numbers, 0, 1, primes, and composite numbers.
>
> 🧑‍🎓: עכשיו גם את זה:
>
> ```java
> public static String reverse(String s) {
>     return new StringBuilder(s).reverse().toString();
> }
> ```
>
> 🤖: Added comprehensive unit tests for `reverse`, covering empty string, single character, spaces, numbers, special characters, palindromes, and tabs.
>
> 🧑‍🎓: אותו דבר ל-`factorial`:
>
> ```java
> public static int factorial(int n) {
>     if (n < 0) throw new IllegalArgumentException("Negative number");
>     int result = 1;
>     for (int i = 2; i <= n; i++) result *= i;
>     return result;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `factorial`, covering negative inputs that throw exceptions and factorial values from `0!` through `12!`.
>
> 🧑‍🎓: ואפילו את זה:
>
> ```java
> public static boolean isPalindrome(String s) {
>     String clean = s.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();
>     return clean.equals(reverse(clean));
> }
> ```
>
> 🤖: Added comprehensive unit tests for `isPalindrome`, including spaces, punctuation, mixed case, numbers, empty string, and special-character-only strings.
>
> 🧑‍🎓: המשך עם הפונקציות הבאות:
>
> ```java
> public static List<Integer> fibonacciUpTo(int n) {
>     List<Integer> result = new ArrayList<>();
>     if (n < 0) throw new IllegalArgumentException("Negative input");
>     int a = 0, b = 1;
>     while (a <= n) {
>         result.add(a);
>         int temp = a + b;
>         a = b;
>         b = temp;
>     }
>     return result;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `fibonacciUpTo`, covering negative input exceptions, `0`, `1`, exact Fibonacci values, between-Fibonacci values, and larger limits.
>
> 🧑‍🎓: למה לא את זה:
>
> ```java
> public static Map<Character, Integer> charFrequency(String input) {
>     Map<Character, Integer> freq = new HashMap<>();
>     for (char c : input.toCharArray()) {
>         freq.put(c, freq.getOrDefault(c, 0) + 1);
>     }
>     return freq;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `charFrequency`, covering empty string, repeated characters, spaces, numbers, special characters, case sensitivity, tabs, and newlines.
>
> 🧑‍🎓: וגם את זה:
>
> ```java
> public static boolean isAnagram(String s1, String s2) {
>     char[] a1 = s1.replaceAll("\\s", "").toLowerCase().toCharArray();
>     char[] a2 = s2.replaceAll("\\s", "").toLowerCase().toCharArray();
>     Arrays.sort(a1);
>     Arrays.sort(a2);
>     return Arrays.equals(a1, a2);
> }
> ```
>
> 🤖: Added comprehensive unit tests for `isAnagram`, covering simple anagrams, empty strings, spaces, case insensitivity, numbers, punctuation, different lengths, duplicate characters, and long strings.
>
> 🧑‍🎓: ועוד את זה:
>
> ```java
> public static double average(int[] arr) {
>     if (arr.length == 0) throw new IllegalArgumentException("Empty array");
>     double sum = 0;
>     for (int num : arr) sum += num;
>     return sum / arr.length;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `average`, covering empty array exceptions, single elements, positive, negative, mixed values, zeros, fractional results, large numbers, and consistency.
>
> 🧑‍🎓: הבא את זה לבדיקה גם:
>
> ```java
> public static List<Integer> filterEvens(List<Integer> list) {
>     List<Integer> evens = new ArrayList<>();
>     for (int n : list) {
>         if (n % 2 == 0) evens.add(n);
>     }
>     return evens;
> }
> ```
>
> 🤖: Added comprehensive unit tests for `filterEvens`, covering empty list, all evens, all odds, mixed lists, negatives, zero, duplicates, order preservation, and original list immutability.
>
> 🧑‍🎓: ולבסוף:
>
> ```java
> public static String mostCommonWord(String text) {
>     String[] words = text.toLowerCase().split("\\W+");
>     Map<String, Integer> count = new HashMap<>();
>     for (String word : words) {
>         count.put(word, count.getOrDefault(word, 0) + 1);
>     }
>     return Collections.max(count.entrySet(), Map.Entry.comparingByValue()).getKey();
> }
> ```
>
> 🤖: Added comprehensive unit tests for `mostCommonWord`, covering simple frequency, punctuation, case insensitivity, whitespace variants, tabs, newlines, ties, and special symbols.
>
> 🧑‍🎓: איך אני בודק שכיסיתי את כל המקרים?
>
> 🤖: בדיקת כל פונקציה לפי קטגוריות: קלטים תקינים, קלטים לא תקינים, גבולות, מקרים מיוחדים, חריגות, וקצוות. אפשר גם להשתמש בדוח JaCoCo כדי לראות את כיסוי הקוד.
>
> 🧑‍🎓: אפשר לעשות את זה בפקודה אחת?
>
> 🤖: כן:
>
> ```powershell
> .\gradlew test
> ```
>
> ואם אתה רוצה דוח כיסוי:
>
> ```powershell
> .\gradlew jacocoTestReport
> ```
>
> 🧑‍🎓: אני קיבלתי שגיאה:
> * What went wrong:
> Task 'jacocoTestReport' not found in root project '26B-10142-Unittesting' and its subprojects.
>
> למה זה לא עובד לי? אתה יכול לתקן את זה?
>
> 🤖: תיקנתי את זה על ידי הוספת תוסף `jacoco` ל-`app/build.gradle.kts`. אחרי זה הפעלתי בהצלחה את:
>
> ```powershell
> .\gradlew jacocoTestReport
> ```
>
> והדוח נבנה ב:
>
> `app/build/reports/jacoco/test/html/index.html`

---

## סטטוס סופי

- כל הטסטים עברו בהצלחה.
- הוספתי תיעוד ברור של השיחה בפורמט קיטתי.
- לא שיניתי את קוד היישום ב-`App.java`; רק את קובץ הטסטים וערכת `build.gradle.kts` כדי לאפשר JaCoCo.
