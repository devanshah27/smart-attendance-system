# Smart Attendance System

A modern web-based attendance system with face recognition capabilities, featuring a beautiful HTML/CSS frontend and Python Flask backend. Uses your existing `attendance_system.py` file with enhanced web interface.

## Features

- 🔐 **Secure Admin Login** - Password-protected access
- 📹 **Laptop Camera Integration** - Uses your laptop's built-in camera
- 👤 **Face Recognition** - Recognizes faces from `face_test/known` folder
- 👁️ **Blink Detection** - Liveness check to prevent spoofing (requires 3 blinks)
- 📊 **Real-time Dashboard** - Live attendance tracking and statistics
- 💾 **CSV Data Storage** - All attendance records saved to CSV files
- 📱 **Responsive Design** - Works on desktop and mobile devices
- 🔄 **Dual Mode** - Console mode and Web mode support

## Default Login Credentials

- **Username:** `admin`
- **Password:** `admin123`

## Setup Instructions

### Prerequisites

- Python 3.7 or higher
- Laptop with built-in camera
- Modern web browser

### Installation

1. **Install Python Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Prepare Face Database:**
   - Add known face images to the `face_test/known/` folder
   - Supported formats: `.jpg`, `.jpeg`, `.png`
   - Name files with the person's name (e.g., `john.jpg`, `mary.png`)

3. **Run the Web Interface:**
   ```bash
   python attendance_system.py --web
   ```

4. **Access the System:**
   - Open your web browser
   - Navigate to `http://localhost:5000`
   - Login with admin credentials
   - Click "Start Camera" to begin face recognition

### Alternative: Console Mode

To run the original console-based version:
```bash
python attendance_system.py
```

## File Structure

```
smart-attendance-system/
├── attendance_system.py    # Main application (enhanced with web interface)
├── requirements.txt         # Python dependencies
├── templates/             # HTML templates
│   ├── index.html         # Login page
│   └── dashboard.html    # Main dashboard
├── static/               # CSS and JavaScript files
│   ├── styles.css        # Styling
│   ├── script.js         # Login functionality
│   └── dashboard.js      # Dashboard functionality
├── face_test/known/      # Known face images (your existing folder)
├── users.csv             # User credentials
├── attendance.csv        # Attendance records (your existing file)
└── README.md            # This file
```

## How It Works

1. **Login:** Admin logs in with username and password
2. **Camera Access:** System requests laptop camera permission
3. **Face Detection:** Live video feed detects faces using your existing face recognition
4. **Recognition:** Compares detected faces with known faces from `face_test/known`
5. **Liveness Check:** Requires 3 blinks to verify it's a real person
6. **Attendance Marking:** Automatically marks attendance in your existing CSV
7. **Dashboard Updates:** Real-time statistics and records display

## Configuration

### Face Recognition Settings

You can modify these settings in `attendance_system.py`:

- `FACE_DISTANCE_THRESHOLD = 0.5` - Face matching sensitivity
- `BLINK_THRESHOLD = 0.25` - Blink detection sensitivity  
- `REQUIRED_BLINKS = 3` - Number of blinks required for verification
- `FRAME_SCALE = 0.5` - Frame resize for faster processing

### Adding New Users

1. Add face images to `face_test/known/` folder
2. Restart the application
3. The system will automatically load new faces

## Troubleshooting

### Camera Issues
- Ensure laptop camera permissions are granted
- Check if camera is being used by another application
- Try refreshing the page

### Face Recognition Issues
- Ensure face images in `face_test/known/` are clear and well-lit
- Check that faces are looking directly at the camera
- Verify image files are in supported formats (.jpg, .jpeg, .png)

### Performance Issues
- Close other applications using the camera
- Ensure good lighting conditions
- Check system resources

## Security Features

- Password hashing using SHA-256
- Session-based authentication
- Blink-based liveness detection
- Face distance thresholding
- Uses your existing security implementations

## Browser Compatibility

- Chrome (recommended)
- Firefox
- Safari
- Edge

## Integration with Existing System

This web interface seamlessly integrates with your existing `attendance_system.py`:
- Uses the same face recognition algorithms
- Maintains the same CSV file structure
- Preserves all security features
- Uses the same `face_test/known` folder
- Compatible with your existing attendance data

## License

This project is open source and available under the MIT License.

## Support

For issues or questions, please check the troubleshooting section or create an issue in the project repository.
