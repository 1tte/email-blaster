# PHPMailer Composer Integration 🚀  

This repository provides a simple and efficient way to send emails using **PHPMailer** with **Composer** in PHP. PHPMailer is a powerful and flexible email-sending library that supports **SMTP authentication, HTML emails, attachments, and more**.  

---

## 📌 Features  
- ✅ Send Emails via SMTP (Gmail, Outlook, etc.)  
- ✅ Supports HTML & Plain Text Emails  
- ✅ Add Attachments & Inline Images  
- ✅ Authentication with Username & Password  
- ✅ Custom Headers & Reply-To Options  
- ✅ Secure TLS/SSL Encryption  

---

## 📥 Installation  
Install PHPMailer using Composer:  
```bash
composer require phpmailer/phpmailer
```

---

## 🚀 Usage Example  
```php
<?php
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\Exception;

require 'vendor/autoload.php';

$mail = new PHPMailer(true);

try {
    // Server settings
    $mail->isSMTP();
    $mail->Host       = 'smtp.gmail.com';
    $mail->SMTPAuth   = true;
    $mail->Username   = 'your-email@gmail.com';
    $mail->Password   = 'your-password';
    $mail->SMTPSecure = PHPMailer::ENCRYPTION_STARTTLS;
    $mail->Port       = 587;

    // Recipients
    $mail->setFrom('your-email@gmail.com', 'Your Name');
    $mail->addAddress('recipient@example.com', 'Recipient Name');

    // Content
    $mail->isHTML(true);
    $mail->Subject = 'Test Email';
    $mail->Body    = '<b>Hello, this is a test email!</b>';

    $mail->send();
    echo 'Email sent successfully!';
} catch (Exception $e) {
    echo "Email could not be sent. Error: {$mail->ErrorInfo}";
}
?>
```

---

## 🔹 Configuration  
- Replace **your-email@gmail.com** and **password** with your credentials.  
- Enable **"Less Secure Apps"** in your email provider or use an **App Password** for security.  

---

## 📜 License  
This project is open-source and available under the **MIT License**.  
