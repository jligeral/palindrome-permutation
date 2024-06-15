# Palindrom Permutation

The hints provided by the text specify that all permutations of the provided string do not need to be generated. Instead we can focus out attention on the definition of a palindrome - We can observe that a palindrome will have an even number of almost all characters, with only exactly one character having an odd amount. With this in mind, we build our strategy: Count the frequency of each character in the string and make sure that at most only exactly one of the characters has an odd number of occurences. To do this we employ a *frequency table*.

## Frequency Table

```public static int[] buildCharFrequencyTable(String str) {
        int[] table = new int[Character.getNumericValue('z') - Character.getNumericValue('a') + 1];
        for (char c : str.toCharArray()) {
            int x = getCharNumber(c);
            if (x != -1) {
                table[x]++;
            }
        }
        return table;
    }
```
In the solution, this method takes the numeric values of the letters 'z' and 'a' to create an array of 26 indices (90-65+1). The second part uses an *enhanced for loop* to obtain the numeric value of each character in the given string and increment its count or frequency in the table by one each time it appears.

Once we've completed the frequency table, we can then check to see how many counts are odd to determine if the string contains a palindrome. The for loop takes up the most time in this algorithm since we check each character in the provided string so the asymptotic time or big O is O(N).
