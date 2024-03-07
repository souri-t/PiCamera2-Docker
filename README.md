# Raspberry Pi 5 Docker Container for PiCamera2

This Dockerfile allows you to create a Docker container on a Raspberry Pi 5(Bookworm) that can run a Python script utilizing the PiCamera2 module.
Feel free to customize the Dockerfile according to your specific use case and project requirements.

## PiCamera2 and Libcamera
### PiCamera2

[PiCamera2](https://github.com/raspberrypi/picamera2) is a new Python library used to control the Raspberry Pi Camera Module. It provides a simple and intuitive API for capturing images or video from the Raspberry Pi's camera in your Python scripts. This Docker container is set up to run Python scripts that utilize the PiCamera2 library, allowing you to easily capture and process images from the camera module.

### Libcamera

Libcamera is a new library designed to handle camera devices on Linux. It provides a modern, easy-to-use interface for applications to use with camera devices. PiCamera2, the module used in this Docker container, utilizes libcamera for its operations. This allows for more advanced control and functionality when capturing images or video from the Raspberry Pi's camera module.


## Prerequisites

- Raspberry Pi 5
- Docker and docker-compose installed on the Raspberry Pi

## Run Docker Container

Run the Docker container using the following command:

```bash
docker-compose up -d
```

## Camera Script

The Docker container executes a Python script named camera.py located in the /code directory. You can replace this script with your own PiCamera2 script.

```bash
docker-compose exec picamera2 bash
python3.11 camera.py
```

or 

```bash
docker-compose exec picamera2 python3.11 camera.py
```

## Important Notes

Ensure that your Raspberry Pi has the camera module connected and enabled.
The Docker container needs privileged access to interact with the camera hardware.
Adjust the Dockerfile and script according to your specific requirements.


If you do need to alter the [configuration](https://www.raspberrypi.com/documentation/computers/camera_software.html), need to bind the camera configuration file `/boot/firmware/config.txt`
