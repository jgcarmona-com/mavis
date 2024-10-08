# MAVIS (Multi-camera Azure Video Image Sync)

MAVIS is a scalable system for monitoring and uploading images from multiple webcams to Azure Blob Storage. It features smart synchronization and storage management, with the potential to generate continuous recordings and time-lapse videos.

## Features
- **Multi-camera Support**: Automatically detects new cameras and starts monitoring them.
- **Azure Integration**: Uploads images to Azure Blob Storage, including maintaining the latest snapshot.
- **Time-lapse Ready**: Stores all images with timestamps for future time-lapse or video generation.
- **Scalable and Flexible**: Designed to easily add and manage multiple cameras in an environment.

## How It Works
MAVIS continuously monitors a root folder for subdirectories, each representing a webcam. When a new image is detected, it is:
1. Uploaded to Azure Blob Storage with a unique timestamp.
2. The current image is also uploaded as `latest.jpg` to provide an easy link to the most recent snapshot.

This setup allows real-time updates while also creating a history of images that can be used for further analysis or fun compilations like time-lapse videos.

## Installation
1. **Clone the Repository**
   ```sh
   git clone https://github.com/yourusername/MAVIS.git
   cd MAVIS
   ```

2. **Configuration**
   - Update the `config/appsettings.json` file with the necessary Azure connection string and root folder path.

3. **Run the Application**
   - MAVIS is a console application. You can run it using:
     ```sh
     dotnet run --project src/MAVIS.csproj
     ```

## Requirements
- **.NET Core 6.0** or higher
- **Azure Blob Storage Account** for storing images
- **Access to Cameras** that can save images to a local folder

## Usage
- **Real-time Monitoring**: MAVIS runs as a console application, monitoring specified folders for new images.
- **Flexible Configuration**: Adjust settings such as monitoring interval, Azure connection string, and folder paths in `appsettings.json`.

## Future Plans
- **Time-lapse Generation**: Automatically generate time-lapse videos from stored images.
- **Web Dashboard**: A simple dashboard to view the status of connected cameras and browse uploaded images.
- **Alerts**: Integrate alerts if a camera stops providing new images for a certain period.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to help improve MAVIS.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For any questions or suggestions, please contact [your email].