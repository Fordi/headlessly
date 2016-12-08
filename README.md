# headlessly
Simple script to run a GUI application in Linux headlessly, with optional VNC service and recording.

	headlessly <flags> -- command [args...]
	-s|--serve-vnc          Also make a VNC server (requires Xvnc)
	-r|--record FILENAME    Record the session to a video
	-d|--display            Force use of a display (e.g., :99)
	                        Note: will usually just use whatever's free
	-g|--geometry WxH       Set geometry (default: 1440x900)
	-w|--window-manager CMD Set window manager (default: ratpoison)
	-h|--help               This helpful message
	-v|--verbose            Output more messages; stack for more
	-q|--quiet              Output fewer messages; stack for less
	--                      No further processing of flags by this script

### Basic usage

The purpose here was to be able to run automated tests without the need for a 
full X server, e.g., 

	headlessly -- ./gradlew -Dbrowser=chrome test

Basic requirements for headlessly are:

	* Xvfb
	* ratpoison (or another lightweight WM, but you'll need to specify it)

Optional requirements:

	* Xvnc (for -s)
	* ffmpeg (for -r {filename})
