# **New Auth System with React Redux & React Router**

## **Overview**
This project updates the authentication and registration logic, allowing users to browse the site without logging in while restricting access to specific sections like "My Store" and "My Wallet." The implementation is based on **React Redux**, **React Router**, and **Redux Persist** for state management and authentication.

## **Features**
- Public access to general pages without registration.
- Authentication required only for certain sections.
- User data and authentication token stored in **Redux**.
- **Redux Persist** ensures token persistence after page reloads.
- Secure private routes using **React Router Guards**.
- **Axios** integration for handling authentication headers.

## **Technologies Used**
- **React** (Frontend framework)
- **Redux Toolkit** (State management)
- **Redux Persist** (State persistence)
- **React Router** (Routing and navigation)
- **Axios** (API requests and token handling)

## **Installation & Setup**
### **1. Clone the Repository**
```sh
git clone https://github.com/BalakaMd/new_auth.git
cd new_auth

2. Install Dependencies

npm install

3. Start the Development Server

npm start

The app will run on http://localhost:3000.

Implementation Details

Authentication Flow
	1.	User logs in → Data and token are stored in Redux.
	2.	Redux Persist ensures the authentication state remains after a page refresh.
	3.	Axios Configuration:

const removeToken = () => {
    delete axios.defaults.headers.common['Authorization'];
};


	4.	Private Route Protection:

const PrivateRoute = ({ component: Component, redirectTo = '/login' }) => {
    const isLoggedIn = useSelector(selectLoggedIn);
    return isLoggedIn ? Component : <Navigate to={redirectTo} />;
};



Routing Structure
	•	Public Routes: Homepage, product listings, descriptions.
	•	Private Routes: User dashboard, store management, wallet.

Live Demo & Testing
	•	Live Version: https://new-auth-red.vercel.app
	•	Source Code: https://github.com/BalakaMd/new_auth

Future Improvements
	•	Implement role-based access control.
	•	Enhance security using JWT token expiration handling.
	•	Add multi-factor authentication for better security.

Contributing

Feel free to submit issues or pull requests. Contributions are welcome!

License

This project is licensed under the MIT License.

This README provides clear instructions, technical details, and useful references. Let me know if you want any modifications! 🚀