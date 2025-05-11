## Setup Guide (Linux)

Ensure that your system has the correct permissions and dependencies before running the application.

---

### 🔧 Requirements
- A Linux-based operating system
- Python 3.x installed
- `pip` (Python package installer)
- Access to hardware ports (e.g., serial ports)

---

### 🔐 Step 1: Check Serial Port Permissions
To use serial ports, your user account must belong to the `dialout` group.

1. Open a terminal and run:
    ```bash
    groups
    ```
2. If `dialout` is **not** listed in the output, add your user to the group:
    ```bash
    sudo usermod -a -G dialout $USER
    ```

---

### 🔁 Step 2: Restart Your Computer
After modifying group memberships, a system restart is required to apply the changes.

---

### 📦 Step 3: Install Project Dependencies
Navigate to your project directory and install the required Python packages:
```bash
pip install -r requirements.txt
```
This will install all dependencies listed in `requirements.txt`.

---

### 🚀 Step 4: Run the Application
Once everything is set up, execute your Python script:
```bash
python car_entry.py
```
---

### ✅ You're Ready!
Your environment should now be properly configured to run the application.

---

### 💳 Payment System

The parking management system uses RFID cards for payment processing.

#### Payment Details
- **Rate**: 200 RWF per hour (minimum 1 hour)
- **Payment Method**: RFID cards linked to license plates
- **Balance Storage**: Each RFID card stores both the license plate number and available balance

#### Topping Up RFID Cards
To add funds to an RFID card:
```bash
# Navigate to the topup directory
cd payment/topup

# Upload the topup.ino sketch to your Arduino
# Then run the serial monitor to interact with the system
```
The topup system will:
1. Prompt you to place an RFID card
2. Ask for a license plate number (7 characters max)
3. Request the balance amount to add to the card

#### Processing Payments
When a vehicle exits the parking:
```bash
# Navigate to the payment directory
cd payment

# Run the payment processing script
python process_payment.py
```
The payment process:
1. Reads the RFID card associated with the vehicle
2. Calculates parking duration and amount due
3. Verifies sufficient balance on the card
4. Deducts the payment and updates the card balance
5. Updates payment status in the system database

---
