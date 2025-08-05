# BloomFilterEmails

A Java implementation demonstrating the use of Bloom Filters and Trie data structures for efficient email processing and filtering.

## Overview

This project implements two complementary data structures to handle email address storage and lookup operations:

- **Bloom Filter**: A space-efficient probabilistic data structure for testing set membership with no false negatives
- **Trie**: A tree-like data structure for efficient prefix-based searching and exact string matching

## Project Structure

```
BloomFilterEmails/
├── BloomFilter.class      # Bloom filter implementation for probabilistic email filtering
├── CLInterface.class      # Command-line interface for user interaction
├── LoadData.class         # Utility class for loading email data from files
├── emails.txt             # Sample dataset containing email addresses
└── Trie/
    ├── Node.class         # Trie node implementation
    └── Trie.class         # Trie data structure implementation
```

## Features

### Bloom Filter
- **Fast Membership Testing**: Quickly check if an email might exist in the dataset
- **Space Efficient**: Uses minimal memory compared to storing all emails
- **No False Negatives**: If the filter says an email doesn't exist, it definitely doesn't
- **Controlled False Positives**: Small chance of false positives for memory efficiency

### Trie Data Structure
- **Prefix Matching**: Find all emails starting with a given prefix
- **Exact Lookups**: Precise email address verification
- **Autocomplete Support**: Enable email suggestion features
- **Sorted Traversal**: Retrieve emails in lexicographical order

## Dataset

The project includes a sample dataset (`emails.txt`) containing over 2,000 synthetic email addresses from a Kaggle community dataset. The dataset spans various domains:
- `example.com`
- `example.org`  
- `example.net`

Email formats include various common patterns like:
- `firstname.lastname@domain.com`
- `username123@domain.org`
- `firstnamelastname@domain.net`

*Note: If you are the original creator of this dataset, please contact me to claim proper attribution credit.*

## Getting Started

### Prerequisites
- Java Development Kit (JDK) 8 or higher
- Command-line interface (Terminal/PowerShell)

### Running the Application

1. **Navigate to the project directory:**
   ```bash
   cd BloomFilterEmails
   ```

2. **Run the command-line interface:**
   ```bash
   java CLInterface
   ```

3. **Load email data:**
   The application uses `LoadData` class to read emails from `emails.txt`

## Use Cases

### Email Validation Systems
- **Primary Check**: Use Bloom filter for fast initial screening
- **Verification**: Use Trie for exact match confirmation
- **Performance**: Reduce database queries by filtering obvious non-matches

### Email Autocomplete
- **Prefix Search**: Trie enables real-time email suggestions
- **User Experience**: Fast response times for typing assistance
- **Memory Efficient**: Bloom filter pre-filters unlikely candidates

### Spam Detection
- **Allowlist Checking**: Quickly verify if sender is in approved list
- **Blocklist Filtering**: Efficient checking against known spam addresses
- **Performance**: Handle large volumes without significant delays

## Performance Characteristics

### Bloom Filter
- **Time Complexity**: O(k) for both insertion and lookup (k = number of hash functions)
- **Space Complexity**: O(m) where m is the size of the bit array
- **False Positive Rate**: Configurable based on filter size and hash functions

### Trie
- **Time Complexity**: O(L) for insertion, deletion, and search (L = string length)
- **Space Complexity**: O(ALPHABET_SIZE × N × L) in worst case
- **Advantages**: No false positives, supports prefix operations

## Technical Implementation

### Data Flow
1. **Data Loading**: `LoadData` reads email addresses from `emails.txt`
2. **Bloom Filter Population**: Each email is hashed and added to the filter
3. **Trie Construction**: Emails are inserted character by character
4. **Query Processing**: `CLInterface` handles user requests using both structures

### Memory Optimization
- **Bloom Filter**: Trades accuracy for space efficiency
- **Trie**: Shares common prefixes to reduce memory usage
- **Combined Approach**: Leverages strengths of both data structures

## Educational Value

This project demonstrates:
- **Probabilistic Data Structures**: Understanding trade-offs in space vs. accuracy
- **Tree Data Structures**: Practical application of prefix trees
- **Algorithm Analysis**: Comparing different approaches for the same problem
- **Java Implementation**: Object-oriented design patterns
- **Data Processing**: File I/O and string manipulation

## Future Enhancements

### Potential Improvements
- **Dynamic Bloom Filter**: Support for resizing based on load
- **Compressed Trie**: Implement Patricia tree for space optimization
- **Persistence**: Save/load data structures to/from disk
- **GUI Interface**: Add graphical user interface
- **Performance Metrics**: Built-in benchmarking and statistics
- **Unicode Support**: Handle international email addresses

### Advanced Features
- **Distributed Processing**: Scale across multiple machines
- **Real-time Updates**: Support for live data modifications
- **Custom Hash Functions**: Pluggable hashing strategies
- **Configurable Parameters**: Runtime tuning of filter parameters

## Contributing

Contributions are welcome! Areas for contribution include:
- Performance optimizations
- Additional data structures
- Enhanced user interface
- Documentation improvements
- Test case additions

## Educational Context

This project is ideal for:
- **Computer Science Students**: Learning data structures and algorithms
- **Software Engineers**: Understanding practical applications of theoretical concepts
- **System Designers**: Exploring trade-offs in data structure selection
- **Interview Preparation**: Common topics in technical interviews

## License

This project is created for educational purposes. Feel free to use and modify for learning and teaching.

## Acknowledgments

- Developed as part of computer science coursework
- Demonstrates practical applications of theoretical data structures
- Sample data generated for educational use only

---

*Note: This implementation uses compiled Java classes. For source code access or modifications, decompilation may be necessary or the original source files should be obtained.*
