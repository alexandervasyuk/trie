#Tries — javascript simple implementation
##What is a trie?
A trie is a tree. It’s an n-ary tree, designed for efficient retrieval. How efficient is efficient? A trie allows us to search for a string in O(m), where m is the number of characters in that string. Do other data structures perform bette? Perhaps, here is an argument in favor of Hashtables:
http://loup-vaillant.fr/projects/string-interning/benchmark

Anyhow — tries. In a trie one can retrieve anything one can prefix and the most common example is to retrieve strings. One can treat individual characters as prefixes to a string. If we are to imagine a tree like structure with nodes having characters for keys, we will see that a path from the root to a leaf constitutes a string. We will also see that if two string were to share first character, their paths will share that one node and branch off into different directions afterwards. If one was so inclined, she could have a value at every leaf, which is admissible, however most of the nodes will just have a key, as they serve as prefixes.

Note the root is an empty string denotes as “.” and \0 or null signals that the node completes a string.

Operations
What can a trie do and what can one for on a trie? Three simple operations are as follows:

add
search
remove

The add method has two while loops. The first looks for an appropriate place to insert an element and the second iterates through the remaining characters of the string, filling out the trie.

The search method returns the depth of the given key or -1 if it does not find any.

If the string in question is present in the trie, the remove method recurses down to the node that represents the last character of the string and removes nodes associated with the characters in the string only if they have no sub nodes dependent on them.