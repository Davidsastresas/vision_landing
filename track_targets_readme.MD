// output hdmi. Very sharp

./track_targets -v -d TAG16h5 /dev/video0 calibration/raspicamv2-calibration-640x480.yml --sizemapping=11:0.506,16:0.238,19:0.122,23:0.056 0.506 -o window -f 50

// output udp h264 hardware encoded. very very sharp also. Mind the fps, if set to high latency gets accumulated.

./track_targets -v -d TAG16h5 /dev/video0 calibration/raspicamv2-calibration-640x480.yml --sizemapping=11:0.506,16:0.238,19:0.122,23:0.056 0.506 -o 'appsrc ! videoconvert ! omxh264enc ! h264parse ! rtph264pay ! udpsink host=10.42.0.1 port=5000 sync=false' -f 30
