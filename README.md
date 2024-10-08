﻿# Project2


#### 1. **Main and Initial Loading Page** (`main.dart`):
- The app starts with a **Loading Page** that displays a centered logo (`Logomark.png`) with a background color drawn from the light theme.
- After a 2-second delay, the app smoothly transitions to the **Welcome Screen** using a custom sliding animation.
- The project uses `MaterialApp` to define the navigation routes for the app, including:
  - **Intro Page**: `WelcomeScreen()`
  - **Login/Register Page**: `LoginRegister()`
  - **Registration Page**: `Registration()`
  - **Address Details Page**: `AddressDetails()`
  - **Map Integration Page**: `IntegrateMap()`

#### 2. **Custom Route Transition**:
- The `LoadingPage` includes a custom route transition using `PageRouteBuilder`. The screen slides in from the bottom with a smooth animation defined by `Curves.easeInOut`, lasting 1.5 seconds.

#### 3. **Theming**:
- The app utilizes a **light theme** defined in `AppThemes` to apply a consistent look and feel across all pages.

#### 4. **Navigation**:
- The `Navigator.pushReplacement()` function is used to replace the loading screen with the next screen after the delay. 
- The app features predefined routes, enabling easy navigation between key screens like the **Welcome**, **Login**, and **Map** pages.

#### 5. **Loading Page Structure**:
- The **LoadingPage** is built using a `Scaffold` with a background color set to the app's primary color.
- A centered image is displayed using `BoxFit.fill` to ensure it occupies the available space.


### Welcome Screen Overview

The **WelcomeScreen** is the entry point where users are introduced to the app. This screen displays a background pattern, icons, text, and two buttons for login options. It utilizes various widgets and custom elements to create a visually appealing interface.

#### Key Components:

1. **Background and Layout**:
   - The screen uses a `Stack` to layer the **BackgroundPatternWidget** (which displays a background animation) behind the core content of the page.
   - A **Column** is used to vertically arrange the content, ensuring space is evenly distributed using `mainAxisAlignment.spaceAround`.

2. **Icon and Text Section**:
   - A **Row** widget contains a **Column** with vertically stacked icons on one side and a rotated text widget on the other:
     - The icons (e.g., logomark, hotdog, burger, etc.) are clickable, but currently have no actions assigned (`onPressed` is empty).
     - The **VerticalTextWidget** displays "KoouL." in a large, bold font rotated 90 degrees for a unique visual effect.

3. **Login Buttons**:
   - Two **CustomButton** widgets are provided:
     - The first button is labeled **"دخول برقم الهاتف"** (Login with phone number) and navigates to the **LoginRegister** screen (`"login"` route).
     - The second button is labeled **"Google دخول بحساب"** (Login with Google) and also navigates to the **LoginRegister** screen.

4. **Styling and Themes**:
   - The app uses the **AppThemes** light theme to apply consistent styling across the screen.
   - Buttons have rounded corners (40.0 radius) and custom background colors.

### `LoginRegister` Page Description:

The **LoginRegister** screen is designed to provide a smooth login and registration experience, supporting both Left-to-Right (LTR) and Right-to-Left (RTL) languages like Arabic. Below is a breakdown of the components and functionalities used:

- **RTL Layout Support**:  
  The page uses `RTLPage` to dynamically adjust the layout direction based on the selected language, either Arabic (RTL) or English (LTR). This ensures an intuitive user interface for both languages.

- **State Management**:  
  The app tracks the current language (`isArabic`).  
  If the password field should be obscured (`_obscureText`).

- **Input Fields & Validation**:  
  There are two text fields: one for phone number input (`_phoneController`) and one for password input (`_passwordController`). Both fields include validation:
  - Phone number: must be 10 digits.
  - Password: must be at least 6 characters.

- **Language Toggle Button**:  
  A button allows users to switch between Arabic and English. When the language changes, the entire layout mirrors (RTL/LTR).

- **Login Function**:  
  The login button triggers validation of the phone number and password. If valid, login logic can be implemented (e.g., API call). Otherwise, errors are displayed.

- **Password Visibility Toggle**:  
  A suffix icon (eye icon) allows users to toggle between showing and hiding their password.

- **"Forgot Password" Link**:  
  Clicking the "Forgot Password" link displays a dialog, informing users they will be redirected to reset their password.

- **UI Elements**:  
  - `HeaderWidget` displays a title and subtitle for the page.
  - `CustomTextField` handles both phone number and password input, with a toggle to obscure the password.
  - `CustomButton` allows navigation to the registration screen or triggers login.

# Registration Page

The Registration Page is a user-friendly interface built with Flutter that allows users to register by entering their personal information, including phone number, email, full name, and password. This page is designed to support both Arabic and English languages, ensuring a seamless experience for users from diverse backgrounds.

## Features

- **Language Support**: Users can toggle between Arabic and English, with the UI adjusting to accommodate Right-to-Left (RTL) layout for Arabic text.
  
- **Input Validation**: The page includes validation for phone numbers (10-digit format) and passwords (minimum 6 characters), providing immediate feedback for incorrect entries.
  
- **Secure Password Entry**: Users can toggle password visibility for improved usability.

- **Responsive Design**: The layout is structured to adapt to different screen sizes, providing an optimal experience on various devices.

## Key Components

- **Custom Widgets**: The page utilizes custom widgets for buttons, text fields, and icons, ensuring consistency in design and functionality.
  
- **State Management**: The registration state is managed using a `StatefulWidget`, allowing dynamic updates to the UI based on user interactions.

- **Navigation**: After successful registration, users are directed to the address details page.

### AddressDetails Class Overview

The `AddressDetails` class is a Flutter widget designed to facilitate users in entering their address details in a user-friendly manner. It utilizes a variety of custom widgets and follows the design principles of responsive UI for both Right-to-Left (RTL) and Left-to-Right (LTR) languages. Here’s a breakdown of its components:

#### Key Components:

1. **RTL Support**:
   - The `RTLPage` class is used to ensure that the layout dynamically adjusts for RTL languages, such as Arabic. This allows for a better user experience for Arabic-speaking users.

2. **Scaffold Structure**:
   - The main structure of the widget is built using a `Scaffold`, which provides the basic material design visual layout structure.

3. **Padding**:
   - The entire content is wrapped in a `Padding` widget, ensuring a consistent space of 15 pixels around all edges, improving readability and aesthetics.

4. **Column Layout**:
   - A `Column` widget is employed to arrange all the child widgets vertically. It uses `MainAxisAlignment.spaceAround` to evenly distribute the space between the widgets and `CrossAxisAlignment.start` to align them to the left.

5. **Header Row**:
   - A `Row` widget displays a back button and the page title ("تفاصيل العنوان"). The back button uses an `IconButton` to allow users to navigate back to the previous page.

6. **Location Section**:
   - Another `Row` widget presents a location icon and the current city and neighborhood. 
   - The location icon is placed within a circular container, enhancing visual appeal.
   - A `HeaderWidget` is used to display the city name ("Casablanca") and the neighborhood ("Grand Casablanca").

7. **Modify Button**:
   - An `ElevatedButton` is provided to allow users to change their address details. It contains an icon and a text label, styled for consistency.

8. **Input Fields**:
   - Three `CustomTextField` widgets are included for users to input:
     - Door number
     - Architecture number
     - Additional details
   - Each input field has a label and an icon, ensuring clarity.

9. **Spacer**:
   - A `SizedBox` is used to add a vertical space of 100 pixels, separating the input fields from the entry button, enhancing the layout.

10. **Entry Button**:
    - A `CustomButton` labeled "دخول" is provided for users to submit their address details. It utilizes the primary color from the app's light theme for visual consistency.

