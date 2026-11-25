# Test Cases: Sauce Demo Store

### ID: TC-001
- **Module:**: Login
- **Title:** Login with valid credentials
- **Preconditions:** Registered account exists
- **Steps:** 1. Open login page</br> 
             2. Enter valid email and password 
             3. Click "Sign in"
- **Expected result:** User is logged in and redirected to the account page
- **Actual result:** successfully logged in and redirected to account page
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-002
- **Module:**: Login
- **Title:** Login with wrong password
- **Preconditions:** Registered account exists
- **Steps:** 1. Open login page 
             2. Enter valid email and wrong password 
             3. Click "Sign in"
- **Expected result:** An error message is shown and the user is not logged in
- **Actual result:** error msg displayed "Incorrect email or password".
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-003
- **Module:**: Cart
- **Title:** Add a product to the cart
- **Preconditions:** Store is open
- **Steps:** 1. Open a product page 
             2. Click "Add to cart"
- **Expected result:** The product appears in the cart with the right price
- **Actual result:** the product is added to cart with correct price but is not displayed until page refresh or module change.
- **Status:** Fail
- **Linked Bug:** BUG-007

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-004
- **Module:**: Checkout
- **Title:** Checkout a product
- **Preconditions:** product inside cart
- **Steps:** 1. Open a cart 
             2. Click "checkout" on cart 
             3. click "checkout" on checkout page 
             4. Insert delivery address and payment method 
             5. click "Pay now" 
- **Expected result:** the checkout page confirms checkout
- **Actual result:** Your order is confirmed
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-005
- **Module:**: Search
- **Title:** Search functionality
- **Preconditions:** logged in
- **Steps:** 1. navigate to search module 
             2. insert "jacket" on search field 
             3.click "magnifying glass icon" or "press enter" on the keyboard 
- **Expected result:** items filtered by jacket family item
- **Actual result:** items correctly filtered by jacket family item
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-006
- **Module:**: About us
- **Title:** module navigation About us
- **Preconditions:** logged in
- **Steps:** 1. click on the "About us" module 
- **Expected result:** display of "About us" information module
- **Actual result:** "About us" module information successfully displayed
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-007
- **Module:** Blog
- **Title:** module navigation Blog
- **Preconditions:** logged in
- **Steps:** 1. click on the "Blog" module 
- **Expected result:** display of "Blog" information module
- **Actual result:** "Blog" module information successfully displayed
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------

### ID: TC-008
- **Module:**: Logout
- **Title:** Logout validation
- **Preconditions:** logged in
- **Steps:** 1. click on the "Logout" button 
- **Expected result:** display of home page logged out
- **Actual result:** successfully logged out and redirected to home page.
- **Status:** Pass
- **Linked Bug:** None

-----------------------------------------------------------------------------------------------------------------------------------------