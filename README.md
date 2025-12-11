This is a personal salary tracking and management tool designed to run in a web browser. It uses a modern, colorful, and responsive design based on the Poppins font.
​🎨 Design and Styling Highlights
​Vibrant Color Palette: Uses bright greens (--primary-color), sky blues (--secondary-color), and bright yellows (--accent-color) with dynamic CSS gradients for the background (--bg-gradient-start, --bg-gradient-mid, --bg-gradient-end).
​Full-Screen Layout: The main content container takes up the full width and minimizes shadows for a flat, modern appearance.
​Intuitive Controls: Inputs and buttons are large, well-padded, and highly rounded (border-radius: 12px). Buttons use a subtle gradient and a pronounced translateY and scale effect on hover for high-quality feedback.
​Custom Select Box: The <select> elements are customized with a standard background-image arrow to look consistent across browsers.
​Information Cards: Data summaries are presented in distinct, color-coded boxes with clear borders and shadows (.highlight-box, .dashboard-info-card).
​⚙️ Application Pages and Functionality
​The application consists of three main pages managed by the showPage and goToPage JavaScript functions.

Welcome Page (#welcomePage)
​Purpose: Collects the user's name.
​Input: Text field for Your Name.
​Transition: Saves the name and navigates to the Salary Details Page.
​2. Salary Details Page (#salaryDetailsPage)
​Purpose: Collects the user's base pay rates and currency settings.
​Key Inputs:
​Currency Symbol: Select dropdown with an option for a custom symbol.
​Country: Select dropdown.
​Per hour salary (regular work).
​Per day salary (regular work).
​Extra Shift: Per hour salary.
​Calculation: Dynamically calculates and displays the Estimated monthly base salary based on the entered daily rate or (hourly rate * 8) * 22 days.
​Transition: calculateAndGoToPage processes the inputs, saves the settings, and navigates to the Main Dashboard

Salary Details Page (#salaryDetailsPage)
​Purpose: Collects the user's base pay rates and currency settings.
​Key Inputs:
​Currency Symbol: Select dropdown with an option for a custom symbol.
​Country: Select dropdown.
​Per hour salary (regular work).
​Per day salary (regular work).
​Extra Shift: Per hour salary.
​Calculation: Dynamically calculates and displays the Estimated monthly base salary based on the entered daily rate or (hourly rate * 8) * 22 days.
​Transition: calculateAndGoToPage processes the inputs, saves the settings, and navigates to the Main Dashboard


Main Dashboard Page (#mainDashboardPage)
​This is the core of the application, featuring multiple interactive components for tracking earnings.


Data Management (JavaScript)
​Global appData Object: Stores all user settings and data maps.
​localStorage: Used to persist all application data across sessions:
​saveAppData(): Writes all data to browser's local storage.
​loadAppData(): Reads data and reconstructs the appData maps (workedDaysMap, extraShiftHoursMap, otherAddonsMap).
​getMonthlySummary(monthDate): This is the critical calculation function that aggregates data from all three maps (main days, extra hours, and add-ons) to compute the total earnings for a specific month.
​updateDashboard(): The master function that re-renders all dashboard elements, calendars, and summaries, and calls saveAppData() to persist the new state.

