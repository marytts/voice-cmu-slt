# voice-cmu-slt

A female US English unit selection voice for [MaryTTS](http://mary.dfki.de/) built from [recordings provided by CMU](http://festvox.org/cmu_arctic/)

## Prerequisites

You will need to have [Java](https://www.java.com/), [SoX](http://sox.sourceforge.net/), and the [Edinburgh Speech Tools](http://www.cstr.ed.ac.uk/projects/speech_tools/) installed.
On OSX with [Homebrew](http://brew.sh/), do
```
$ brew cask install java
$ brew install sox speech-tools
```
as needed.

On Debian-based Linux (including Ubuntu), do
```
$ sudo apt-get install default-jdk sox speech-tools
```
accordingly.

### Initializing the build

Do
```
$ ./gradlew legacyInit
```

### Building the voice

To assemble, test, and package the voice for another MaryTTS installation, do
```
$ ./gradlew build
```
The packaged files will be placed under `build/distributions`.
Copy the zip file and xml descriptor into your MaryTTS installation's `download` directory, then run the `marytts-component-installer` to install the voice.

### Running the voice

To build the voice and run it in an ad-hoc MaryTTS server, do
```
$ ./gradlew run
```
Then, go to <http://localhost:59125>.
