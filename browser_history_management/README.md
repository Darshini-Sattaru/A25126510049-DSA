# 🌐 Browser History Management Using Two Stacks in C

## 📌 Overview

Browser History Management Using Two Stacks is a menu-driven C application that simulates browser navigation using two stacks implemented with linked lists.

Users can visit new pages, navigate backward and forward, view their browsing history, and clear all history.

This project demonstrates the practical application of stack data structures, linked lists, and dynamic memory management.

## ✨ Features

- **Visit New Page:** Opens a new page and updates browsing history.
- **Back Navigation:** Returns to the previously visited page.
- **Forward Navigation:** Moves to the next page in forward history.
- **Show Current Page:** Displays the currently open page.
- **Show Full History:** Displays the back stack, current page, and forward stack.
- **Clear History:** Clears both stacks and resets the current page.
- **Input Validation:** Handles invalid menu choices, empty URLs, and excessively long URLs.
- **Memory Management:** Uses dynamic memory allocation and frees allocated memory.

## 🧠 Data Structures and Concepts

- **Stack (LIFO):** Manages backward and forward navigation.
- **Linked Lists:** Implements both stacks dynamically.
- **Structures and Pointers:** Organizes browser data and stack nodes.
- **Dynamic Memory Allocation:** Uses `malloc()` and `free()`.
- **Input Validation:** Handles invalid inputs and edge cases.

## ⚙️ How It Works

The application maintains three components:

- **Back Stack:** Stores previously visited pages.
- **Forward Stack:** Stores pages available for forward navigation.
- **Current Page:** Stores the page currently being viewed.

### Navigation Operations

- **Visit:** Pushes the current page onto the back stack, opens the new page, and clears forward history.
- **Back:** Pushes the current page onto the forward stack and restores the previous page.
- **Forward:** Pushes the current page onto the back stack and restores the next page.
- **Show Current Page:** Displays the currently open page.
- **Show Full History:** Displays both stacks and the current page.
- **Clear History:** Clears both stacks and resets the current page.

**Important behavior:** Visiting a new page after navigating backward clears the forward history.

## 🛠️ Technologies Used

- **Programming Language:** C
- **Data Structures:** Stacks and linked lists
- **Libraries:** `stdio.h`, `stdlib.h`, `string.h`
- **Compiler:** GCC

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
```

Replace `<your-repository-url>` with your actual GitHub repository URL.

### 2. Navigate to the Project Folder

```bash
cd Browser-History-Management
```

### 3. Compile the Program

```bash
gcc browser_history.c -o browser_history
```

### 4. Run the Program

**Linux/macOS:**

```bash
./browser_history
```

**Windows:**

```bash
browser_history.exe
```

## 🖥️ Menu Options

The program provides the following menu:

```text
===== Browser History Manager =====
1. Visit new page
2. Back
3. Forward
4. Show current page
5. Show full history
6. Clear history
0. Exit
```

Enter the corresponding number to perform an operation.

## 🧪 Test Cases

- **Empty Back Stack:** Displays a message when no previous page exists.
- **Empty Forward Stack:** Displays a message when no forward page is available.
- **Multiple Page Visits:** Updates the current page and back stack correctly.
- **Back and Forward Navigation:** Restores the appropriate pages.
- **New Visit After Back:** Clears the forward history.
- **Display History:** Shows the back stack, current page, and forward stack.
- **Invalid Menu Choice:** Displays an error message.
- **Non-Numeric Input:** Requests valid numeric input.
- **Empty URL:** Rejects empty URLs.
- **Excessively Long URL:** Rejects URLs that exceed the allowed length.
- **Clear History:** Resets the browser history.
- **Exit:** Releases the remaining dynamically allocated stack nodes.

## ⏱️ Time and Space Complexity

Let `n` represent the total number of pages stored in both stacks.

- **Push:** O(1)
- **Pop:** O(1)
- **Back Navigation:** O(1)
- **Forward Navigation:** O(1)
- **Show Current Page:** O(1)
- **Display Full History:** O(n)
- **Clear History:** O(n)

**Space Complexity:** O(n)

## 📚 Key Takeaways

- Applied stack operations to a practical browser navigation problem.
- Implemented stacks using linked lists.
- Practiced pointers, structures, and dynamic memory management.
- Implemented input validation and error handling.
- Understood how data structures can solve real-world problems.

## 🔮 Future Enhancements

- Add a graphical user interface.
- Save browsing history to a file.
- Implement bookmarks for frequently visited pages.
- Add timestamps to visited pages.
- Implement a search feature for browsing history.

## 👩‍💻 Author

**Darshini Sattaru**

Computer Science Student | Data Structures & Algorithms

---

⭐ If you find this project interesting, feel free to explore the code!
