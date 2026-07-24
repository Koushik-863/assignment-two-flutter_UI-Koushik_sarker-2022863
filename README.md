# assignment-two-flutter_UI-Koushik_sarker-2022863

## Student Information
- **Student Name:** Koushik sarker
- **Student ID:** 2022863
- **Student Email:** 2022863@iub.edu.bd
- **Institution:** Independent University, Bangladesh (IUB)

---

## 📌 Project Overview
This repository contains a complete Flutter mobile application created for **Assignment 2: Flutter UI**. It accurately reproduces the 4-page Figma design specification with bottom navigation, pixel-perfect card layouts, transaction records, monthly spending reports, credit card UI, and personal student profile management.

---

## 📱 Implemented Pages & Features

### 1. Page 1 – Home Screen (Mandatory)
- **Top Header**: User avatar with initial "K", personalized welcome text (`Welcome back, KOUSHIK SARKER`), and notification bell with indicator dot.
- **Total Balance Card**: Gradient purple-to-blue background, balance `$8,945.32`, savings total `$5,500`, and last 30 days change badge (`+$300 ->`).
- **Quick Action Buttons**: `Transfer`, `Pay Bills`, and `Invest` circular icon buttons with subtle shadow cards.
- **Recent Transactions List**: Itemized list featuring:
  - Netflix Subscription (`-$19.99`)
  - Coffee Shop (`-$4.50`)
  - Salary Deposit (`+$3500.00`)
  - Grocery Store (`-$55.80`)
  - Amazon Purchase (`-$120.45`)

### 2. Page 2 – Monthly Spending Report
- **Header**: Synchronized user header.
- **Total Expenses Summary**: Card displaying `-$1270.00` total expenses with `↑ Up 12% from last month` indicator.
- **Spending Breakdown**: Category progress indicators with amounts and percentages:
  - Food & Drink: `$450.00 (35%)`
  - Shopping: `$320.00 (25%)`
  - Housing: `$280.00 (22%)`
  - Transport: `$150.00 (12%)`
  - Other: `$70.00 (6%)`

### 3. Page 3 – My Cards
- **Header**: Synchronized user header.
- **Metallic Credit Card Widget**:
  - Gold metallic chip simulation & `BANK` logo.
  - Card number: `4567 **** **** 1234`.
  - Cardholder Name: `KOUSHIK SARKER` & Expiry date `12/28`.
- **Card Action Buttons**: `Block`, `Details`, `Limit` buttons with interactive SnackBar callbacks.
- **Linked Accounts**: `Shared Savings` card (`$5,500.00`).

### 4. Page 4 – User Profile (Mandatory)
- **Header**: "User Profile" title with an edit action button.
- **Enlarged Avatar Circle**: Initials `KS` in white on indigo circle.
- **Information Card Fields**:
  - **Name**: `Koushik sarker`
  - **Student ID**: `2022863`
  - **Email**: `2022863@iub.edu.bd`
  - **Bio / Story**: Full short personal story/bio text box.
- **Interactive Editing**: Includes an interactive modal so you can modify and test profile details live.

---

## ⚡ Navigation Implementation
Navigation between all 4 screens is implemented strictly following the Figma design recommendation using **`PageView`** and **`PageController`**:

```dart
class _MainScreenState extends State<MainScreen> {
  int _currentIndex = 0;
  final PageController _pageController = PageController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: PageView(
        controller: _pageController,
        physics: const NeverScrollableScrollPhysics(),
        children: const [
          HomeScreen(),
          ReportsScreen(),
          CardsScreen(),
          ProfileScreen(),
        ],
      ),
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: _currentIndex,
        onTap: (i) {
          setState(() => _currentIndex = i);
          _pageController.jumpToPage(i);
        },
        items: const [ ... ],
      ),
    );
  }
}
```

---

## 🚀 How to Run the App

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/assignment-two-flutter_UI-Koushik_sarker-2022863.git
   cd assignment-two-flutter_UI-Koushik_sarker-2022863
   ```
2. **Get Dependencies**:
   ```bash
   flutter pub get
   ```
3. **Run the App**:
   ```bash
   flutter run
   ```

---

## 📽️ Demo Video Instructions (For Google Classroom Submission)
1. Use your mobile screen recorder (or Android Emulator screen recording).
2. Open the app and show:
   - Page 1 (Home Dashboard & Transactions)
   - Bottom navigation tab tap to Page 2 (Monthly Spending Report)
   - Bottom navigation tab tap to Page 3 (My Cards)
   - Bottom navigation tab tap to Page 4 (User Profile showing Koushik sarker, ID 2022863, Email, and Bio)
3. Attach the video file directly in your **Google Classroom Submission**.
