# Introduction
Today we are  discussing how we can integrate Razorpay payment gateway with our website. Its very easy and quick to start with razaorpay payment gateway.

# Initialization
```
use Razorpay\Api\Api;
$api = new Api($api_key, $api_secret);
```
# Generate API Key

1. Log into your Dashboard with appropriate credentials.
2. Select the mode (Test or Live) for which you want to generate the API key.
Note:
You have to generate separate API Keys for the test and live modes. No real money is used in test mode.
 3. Navigate to Settings → API Keys → Generate Key to generate key for the selected mode.
The Key Id and Key Secret appear in a pop-out window as shown below:


Note:
After generating the keys from the Dashboard, download and save them securely. If you do not remember your API Keys, you need to re-generate it from the Dashboard and replace it wherever required

Warning:
Do not share your API Key secret with anyone or on any public platforms. This can pose security threats for your Razorpay account.

Sample Application
Note: Ensure that you are using the latest version of the SDK. You can download the latest version of the SDK from GitHub.

# Get Started
1. Download Razorpay PHP Sample App.
2. Open the index.html file on your browser to see a demo of the php-test app
3. Follow the below steps to set up the config.php file:
a. Copy the contents of config.php.sample to config.php.
b. Enter your <key_id> and <key_secret> in the config.php file. Refer to the Generate API Key section to learn how to generate keys.
c. If you want to collect payments in a currency other than INR, change the displayCurrency parameter to the currency of your choice. Razorpay supports these currencies.
4. Watch the demo to test out automatic or manual checkout.
An easy way to test this is to run php -S localhost:8000 in the root directory and open http://localhost:8000 in your browser.

# Standard Checkout Integration

The Standard or Automatic Checkout method provides a default Pay with Razorpay button that invokes the checkout form. The checkout form options are passed as data attributes inside a <script> tag. You can add any additional, hidden or visible, fields to the form. These fields will be submitted along with the form.

Follow the below steps to integrate the automatic checkout:

1. Create a checkout form using Razorpay Standard Checkout Integration.
2. Accept razorpay_payment_id parameter in the form submission.
3. Run the capture code to capture the payment.
Note:
If you want to re-use this as your final code, follow the below steps:

Edit the key_id inside automatic-checkout/index.html. Use the live keys when using the application to accept live payments.
Edit the <key_id> and the <key_secret> in automatic-checkout/charge.php.

# Custom Checkout Integration

In the Custom or the Manual Checkout method, the Checkout form is invoked by the custom button on your site and the form options are passed as variables in a key-value pair format within a <script> tag. Once the payment is successfully authorized, a handler function is called automatically. This function returns a response object containing razorpay_payment_id. This handler function must be called back to your server-side to capture the payment.

Follow the below steps to integrate the manual checkout:

1. Create an order using Razorpay Orders API.
2. Accept razorpay_payment_id parameter and razorpay_signature in the form submission.
3. Store the razorpay_order_id as a sessions variable.
4. Verify the signature emitted from Razorpay server based on the algorithm.

# Are you want to get implementation help, or modify or enhance the functionality of this script?
https://www.custdeal.com/contact
