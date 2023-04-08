

# Video and Audio Streaming Project

This project provides a solution to stream live video and audio from a server to a client using sockets, threading, and OpenCV library. The project consists of two python files; `server.py` and `client.py`.

The `server.py` script reads a video file and prepares frames to be sent over the network. The script also listens to incoming requests from a client and sends frames to the client.

The `client.py` script connects to the server and displays the video stream in a window. The script also receives and plays the audio stream from the server.

## Setup and Usage

### Setup

- Install the required libraries: OpenCV, pyaudio, and imutils

```bash
pip install opencv-python pyaudio imutils
```

- Run the `server.py` script:

```bash
python server.py <path_to_video_file>
```

- Run the `client.py` script:

```bash
python client.py
```

### Usage

- After running the server, it will display the IP address and port that the client should use to connect.
- Run the client and connect to the server using the IP address and port number shown on the server.
- The client will display the video stream, and the audio stream will start playing automatically.

## Project Architecture

The project is designed to use a UDP socket for video streaming and a TCP socket for audio streaming.

The video frames are captured from the video file using OpenCV and resized before being sent to the client. The frames are then encoded using base64 and sent over the network to the client.

The audio stream is captured using pyaudio and encoded using pickle. The encoded audio is then sent over the network to the client.

Both the server and client use threading to handle the video and audio streams concurrently.

## Future Improvements

- Add encryption to the video and audio streams for security reasons.
- Implement a web-based interface to enable easy access to the streaming service.
- Add support for multiple clients to access the streaming service simultaneously.

## Credits

This project is inspired by and adapted from several existing projects, including:

- OpenCV video streaming project by Adrian Rosebrock: https://www.pyimagesearch.com/2019/09/02/opencv-stream-video-to-web-browser-html-page/
- Socket programming with Python by Tech with Tim: https://www.youtube.com/watch?v=3QiPPX-KeSc
- Python Audio Streaming project by Sudhanshu Shekhar: https://github.com/sudhanshu456/Python-Audio-Streaming-using-Socket

## License

This project is licensed under the MIT License. See the LICENSE file for details.
