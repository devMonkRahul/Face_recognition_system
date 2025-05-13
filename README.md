# Face Recognition Attendance System

A web-based attendance system that uses face recognition technology to automatically track student attendance. The system captures student images, recognizes faces in real-time, and maintains attendance records in a database.

## Features

- Real-time face detection and recognition
- Student registration with photo capture
- Automatic attendance marking
- Attendance tracking and reporting
- Admin dashboard for attendance management
- Secure login system
- Head pose detection to prevent proxy attendance

## Prerequisites

- Python 3.12 or higher
- MySQL Server
- Webcam
- Internet connection
- CMake (required for dlib installation)

### Installing CMake

#### Windows
1. Download the latest CMake installer from [CMake's official website](https://cmake.org/download/)
2. Run the installer and select "Add CMake to the system PATH for all users"
3. Verify installation by opening a new terminal and running:
```bash
# Copy this command to verify CMake installation
cmake --version
```

#### Linux (Ubuntu/Debian)
```bash
# Copy these commands to install CMake on Linux
sudo apt update
sudo apt install cmake
```

#### macOS
```bash
# Copy this command to install CMake on macOS
brew install cmake
```

## Installation

1. Clone the repository:
```bash
# Copy these commands to clone and enter the repository
git clone https://github.com/devMonkRahul/Face_recognition_system.git
cd face_recognition_system
```

2. Install UV (Python package installer):
```bash
# Copy the appropriate command for your OS to install UV
# Windows
pip install uv

# Linux/macOS
curl -LsSf https://astral.sh/uv/install.sh | sh
```

3. Install dependencies using UV:
```bash
# Copy this command to install dependencies
uv add -r requirements.txt
```

4. Set up the face landmark predictor model:
- The `shape_predictor_68_face_landmarks.dat` file is included in the repository
- No additional download is required
- Verify that the file is present in the root directory of the project

5. Set up the MySQL database:
- Create a new database named `student_details`
- Import the database schema (if provided)
- Update database credentials in the code if needed

## Configuration

1. Database Configuration:
- Update database connection details in `db_conn.py` if needed:
  - Host: localhost
  - Username: root
  - Password: (your password)
  - Database: student_details

2. Camera Configuration:
- The system uses the default webcam (index 0)
- For IP cameras, update the camera URL in `app.py`

## Usage

1. Start the application:
```bash
# Copy this command to start the application
uv run app.py
```

2. Access the web interface:
- Open a web browser and navigate to `http://localhost:5000`

3. Login:
- Use the admin credentials to log in
- Default credentials can be set in the database

4. Student Registration:
- Navigate to the update page
- Enter student details (ID, name, semester)
- Capture student photos when prompted

5. Attendance Marking:
- Start the face recognition system
- Students should look at the camera
- System will automatically mark attendance when faces are recognized

## Project Structure

- `app.py`: Main Flask application
- `recogniy.py`: Face recognition logic
- `db_conn.py`: Database connection handling
- `db_execute_query.py`: Database query execution
- `imgcapture.py`: Image capture functionality
- `image_manupulation.py`: Image processing utilities
- `findencoding.py`: Face encoding generation
- `attendence.py`: Attendance marking logic

## Security Considerations

- Store database credentials securely
- Use HTTPS in production
- Regularly update dependencies
- Implement proper access controls
- Secure the admin interface

## Troubleshooting

1. CMake Installation Issues:
- Ensure CMake is properly installed and added to system PATH
- Try reinstalling CMake if installation fails
- Verify installation with `cmake --version`

2. Camera Issues:
- Ensure webcam is properly connected
- Check camera permissions
- Try different camera indices if needed

3. Face Recognition Issues:
- Ensure proper lighting
- Check if face is clearly visible
- Verify if face landmark predictor file is present in the root directory

4. Database Issues:
- Verify database connection details
- Check if database server is running
- Ensure proper table structure

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
