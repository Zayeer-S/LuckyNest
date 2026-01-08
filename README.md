# LuckyNest
LuckyNest is a guest and property management system that was made to streamline administrative tasks for Ms. Lucky. The system provides guest and property management functionalities for the owner/admins and provides meal plan and laundry slot purchases and notifications for guests.

## Stack:
PHP, MySQL, JS, HTML and CSS.

## Key Features:
1. **Complete property management** (including advanced DatePickers) 
2. **Complete guest management** (including advanced DatePickers)
3. **Meal plan and laundry management**
4. **Stripe payments**
5. **Invoice PDF generation**
6. **Email notifications**
7. **SMS notifications**
8. **Two-Factor Authentication using Authenticator Apps**
9. **Various analytics/reports pages** (e.g. financial reports)

## My Development Contributions (approximately 50% of the project):
1. **Team Leader and Team Secretary**
2. **Implemented DatePickers that change colours (green/red) to signal availability**
3. **Implemented Payments using Stripe API**
4. **Implemented Deposit Refund Handling**
5. **Implemented Invoice PDF generation**
6. **All analytics/reports pages**
7. **Stored confidential information (e.g. API keys) in environment variables (.env) file**

## My Leadership Contributions
1. Led a mixed-experience team by adapting development process (Agile-style iterations) to continuous feedback from a non-technical stakeholder, ensuring requirements were correctly interpreted and delivered
2. Made a deliberate architectural decision to avoid frameworks, prioritising team accessibility and onboarding speed over tooling complexity to maximise collective contribution
3. Identified and mitigated a potential security risk through code reviews by enforcing environment-based secret management (.env), preventing API key exposure in version control
4. Prevented potential API key exposure by guiding a teammate to apply secure environment configuration via .env
5. Introduced anonymous peer assessment to ensure fair contribution evaluation and improve accountability
6. Unblocked a teammate struggling with the Trello API by breaking the integration into smaller, testable steps and walking through the request/response flow, enabling on-time feature delivery


## Setup:
### FIRSTLY CREATE YOUR OWN ".env" FILE IN THE WEBROOT
e.g. "C:\xampp\htdocs\LuckyNest\.env" here .env is my .env file

### How to setup payments_page.php:
     1. Copy paste the following and replace the 'rk_test_...' part with your own Stripe API keys:
          stripe_first_key = rk_test_...
          stripe_second_key = rk_test_...
          stripe_third_key = rk_test_...
          stripe_fourth_key = rk_test_...
          stripe_fallback_key = rk_test_...



### How to setup phpmailer:
     1. Create an app password in your Google Account https://myaccount.google.com/apppasswords
     2. Configue SMTP settings in your .env file:
          SMTP_HOST=smtp.gmail.com
          SMTP_PORT=587
          SMTP_USERNAME=your@gmail.com
          SMTP_PASSWORD=your-app-password


### How to setup the automated notifications:
     1. Open up Windows Task Scheduler by searching for "Task Scheduler" in the start menu
     2. Click "Create a Basic Task" on the right
     3. Choose when you want to run it and click next
     4. Then choose what frequency you want to run it and click Next
     5. Select start a program and click next
     6. In the program/script section add: C:\xampp\php\php.exe (you may have to adjust the path to the file)
     7. In add arguments enter: C:\xampp\htdocs\LuckyNest\notification_scheduler.php (you may have to adjust the path to the file)
     8. Click Next, then finish
     9. Create a notification_logs.php file in the logs folder (although not necessary as the scripts should automatically create it)

     Note: you can manually run it via "C:\xampp\php\php.exe C:\xampp\htdocs\LuckyNest\notification_scheduler.php" (you may have to adjust the path to the file)


### Two Factor Authentication (2FA):
Technical Note: While the Sonata Google Authenticator Library that is used in this project has been officially deprecated, we made deliberate engineering decision
to continue using Sonata for LuckyNest 2FA. The library remains functional and meets our extra requirement to add 2FA, while at the same time providing a much simpler
implementation. While newer alternatives exist, we believe that the Sonata implementation has satisfied the project's extra requirement and has resulted in a seamless
production quality version of 2FA for the users of LuckyNest.

## Technologies Used:
1. **Core Stack:** PHP, MySQL, JavaScript, HTML and CSS
2. **Payment Processing:** Stripe API
3. **Notifications:** Twilio API, PHPMailer
4. **UI Components:** FlatPickr
5. **PDF Generation:** FPDF

## Lessons Learnt:
1. **Always establish a well-thought out file structure before development begins**
2. **Do small commits often instead of large commits rarely**
3. **Always minimise user data in the database and hash it to protect user data**
4. **Modularise files instead of making large, difficult to maintain files**
5. **Use DAOs and Service layers instead of mixing concerns**
6. **Implement CI/CD to standardise code quality**
