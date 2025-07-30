`# CryptoSteg - Advanced Steganography Tool

**Covert Message Delivery System for Intelligence Operations**

CryptoSteg is a sophisticated web-based steganography application that combines advanced cryptographic techniques with image-based message hiding for secure covert communication.

## 🔐 Features

### Core Functionality
- **PKI Infrastructure**: 2048-bit RSA key generation and management
- **Advanced Encryption**: AES-256-CBC with RSA key exchange
- **Digital Signatures**: SHA-256 based message authentication
- **LSB Steganography**: Randomized pixel embedding with integrity checking
- **QR Code Integration**: Dynamic URL generation for message delivery
- **Certificate Revocation**: CRL management for compromised users
- **Real-time Monitoring**: WebSocket-based admin panel

### Security Features
- Session token authentication
- Seed-based randomization for steganography
- SHA-256 checksum validation
- Transparent background PKI operations
- Secure key storage and validation

### User Interface
- Modern responsive design with Bootstrap
- Drag-and-drop file upload
- Real-time status updates
- Professional admin monitoring panel
- Mobile-friendly QR code scanning

## 🚀 Quick Start

### Prerequisites
```bash
pip install -r requirements.txt
```

### Installation
1. Clone or download the CryptoSteg application
2. Install dependencies:
   ```bash
   pip install flask pillow cryptography qrcode[pil] flask-socketio python-socketio
   ```

### Running the Application

#### Option 1: Use the launcher script
```bash
python run_cryptosteg.py
```

#### Option 2: Run manually
```bash
# Terminal 1 - Main Application
python app.py

# Terminal 2 - Admin Panel
python admin.py
```

### Access Points
- **Main Application**: http://localhost:5000
- **Admin Panel**: http://localhost:5001/admin

## 📋 Usage Guide

### 1. Agent Registration
1. Enter a unique codename in the registration panel
2. Click "Generate Credentials" to create RSA key pair and session token
3. Your credentials are automatically populated in the interface

### 2. Sending Covert Messages
1. Enter your codename and secret message
2. Upload a cover image (PNG, JPG, JPEG, BMP)
3. Click "Encrypt & Embed Message"
4. Download the generated QR code for message delivery

### 3. Message Extraction
1. Scan the QR code to access the stego image
2. Download the stego image to your device
3. Upload the stego image in the extraction panel
4. Enter your codename and session token
5. Click "Extract & Decrypt Message" to reveal the hidden content

### 4. Admin Monitoring
- Access the admin panel at http://localhost:5001/admin
- Monitor real-time statistics and system status
- View active agents and revoke access if needed
- Track security alerts and system processes

## 🏗️ Architecture

### File Structure
```
cryptosteg/
├── app.py              # Main Flask application
├── admin.py            # Admin panel with WebSocket
├── crypto.py           # PKI and cryptographic operations
├── stego.py            # Steganography engine
├── run_cryptosteg.py   # Application launcher
├── requirements.txt    # Python dependencies
├── templates/
│   ├── index.html      # Main user interface
│   └── admin.html      # Admin panel interface
├── static/
│   └── stego_images/   # Generated stego images
├── uploads/            # Temporary file storage
└── pki_data/           # PKI database and keys
```

### Technical Components

#### Cryptographic Operations (crypto.py)
- **RSA Key Generation**: 2048-bit keys with PKCS8 serialization
- **AES Encryption**: 256-bit CBC mode with PKCS7 padding
- **Digital Signatures**: PSS padding with SHA-256
- **Session Management**: Token-based authentication
- **CRL Management**: Certificate revocation list

#### Steganography Engine (stego.py)
- **LSB Embedding**: Least Significant Bit modification
- **Randomization**: Username-derived seed for pixel selection
- **Integrity Checking**: SHA-256 checksum validation
- **Multi-channel**: RGB channel utilization
- **Capacity Calculation**: Dynamic message size limits

#### Web Interface (app.py)
- **RESTful API**: JSON-based communication
- **File Handling**: Secure upload and processing
- **QR Generation**: Dynamic URL encoding
- **Error Handling**: Comprehensive validation

#### Admin Panel (admin.py)
- **Real-time Monitoring**: WebSocket updates
- **System Statistics**: Live PKI metrics
- **User Management**: Agent status and revocation
- **Security Alerts**: Automated threat detection

## 🔧 Configuration

### Environment Variables
The application uses default configurations but can be customized:

```python
# Flask Configuration
SECRET_KEY = 'cryptosteg_secret_key_2023'
UPLOAD_FOLDER = 'uploads'
STEGO_FOLDER = 'static/stego_images'

# Admin Configuration
ADMIN_SECRET_KEY = 'cryptosteg_admin_secret_2023'
```

### Security Settings
- RSA key size: 2048 bits
- AES key size: 256 bits
- Session token length: 32 bytes
- Checksum algorithm: SHA-256

## 🧪 Testing

### Test Scenarios
1. **Registration**: Create multiple agents with unique codenames
2. **Message Embedding**: Test various image formats and message sizes
3. **QR Code Generation**: Verify dynamic URL creation and token inclusion
4. **Message Extraction**: Validate decryption and signature verification
5. **Admin Functions**: Test user revocation and monitoring features

### Security Testing
- Attempt extraction without proper credentials
- Test with revoked user accounts
- Verify signature validation on tampered messages
- Check CRL enforcement during authentication

## 📊 Performance Metrics

### Capacity Limits
- **Image Size**: Minimum 100x100 pixels recommended
- **Message Length**: Depends on image dimensions (calculated automatically)
- **File Formats**: PNG (best), JPG, JPEG, BMP supported
- **Processing Time**: < 2 seconds for typical operations

### System Requirements
- **Python**: 3.7 or higher
- **Memory**: 512MB minimum
- **Storage**: 100MB for application and temporary files
- **Network**: Local network access for multi-user scenarios

## 🔒 Security Considerations

### Cryptographic Strength
- RSA-2048 provides ~112-bit security level
- AES-256 provides 256-bit security level
- SHA-256 provides 128-bit collision resistance
- PSS padding prevents signature forgery

### Operational Security
- Session tokens expire on server restart
- Private keys stored in memory only
- Temporary files automatically cleaned
- CRL prevents compromised user access

### Limitations
- Images may show slight quality degradation
- Large messages require larger cover images
- Session tokens not persistent across restarts
- Single-server deployment (no clustering)

## 📚 Academic Context

This application was developed for the **ST6051CEM Practical Cryptography** course at **Softwarica College**. It demonstrates:

- Advanced cryptographic protocol implementation
- Secure software development practices
- Real-world steganography applications
- PKI infrastructure design
- Web security principles

### Learning Objectives Achieved
1. **Cryptographic Implementation**: RSA, AES, SHA-256
2. **Steganography Techniques**: LSB with randomization
3. **Security Protocols**: Authentication, authorization, integrity
4. **System Architecture**: Modular design with separation of concerns
5. **User Experience**: Professional interface design

## 🤝 Contributing

This is an academic project, but suggestions for improvements are welcome:

1. Enhanced error handling and logging
2. Database persistence for PKI data
3. Multi-server deployment support
4. Additional steganography algorithms
5. Mobile application development

## 📄 License

This project is developed for educational purposes as part of the ST6051CEM coursework at Softwarica College.

## 🙏 Acknowledgments

- **Softwarica College** for the academic framework
- **Python Cryptography Library** for robust cryptographic primitives
- **Flask Framework** for web application development
- **Bootstrap** for responsive UI components

---

**CryptoSteg** - Where cryptography meets steganography for ultimate covert communication.``

