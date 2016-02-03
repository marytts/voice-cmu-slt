# voice-cmu-slt

A female US English unit selection voice for [MaryTTS](http://mary.dfki.de/) built from [recordings provided by CMU](http://festvox.org/cmu_arctic/)

## Prerequisites

You will need to have [Java](https://www.java.com/), [Praat](http://praat.org/), and the [Edinburgh Speech Tools](http://www.cstr.ed.ac.uk/projects/speech_tools/) installed.
On OSX with [Homebrew](http://brew.sh/), do
```
$ brew cask install java praat
$ brew install speech-tools
```
as needed.

On Debian-based Linux (including Ubuntu), do
```
$ sudo apt-get install default-jdk praat speech-tools
```
accordingly.

This repository uses [Git submodules](https://git-scm.com/docs/git-submodule).
If you did not clone it recursively, you need to do
```
$ git submodule update --init
```

## Initialize

Do
```
$ ./gradlew legacyInit
```

### Running the voice

To build the voice and run it in a MaryTTS server, do
```
$ ./gradlew run
```
Then, go to [http://localhost:59125](http://localhost:59125/).

### Packaging the voice

To package the voice for another MaryTTS installation, do
```
$ ./gradlew assemble
```
The packaged files will be placed under `build/distributions`.
Copy the zip file and xml descriptor into your MaryTTS installation's `download` directory, then run the `marytts-component-installer` to install the voice.
