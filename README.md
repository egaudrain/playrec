*This is a fork of the [original Playrec](https://www.playrec.co.uk/) making it sort of up-to-date for 2023, at least on Mac...*

Playrec is a Matlab and Octave utility (MEX file) that provides simple yet 
versatile access to soundcards using PortAudio, a free, open-source audio 
I/O library. It can be used on different platforms (Windows, Macintosh, 
Unix) and access the soundcard via different host API including ASIO, WMME 
and DirectSound under Windows.

Note that current versions of Matlab support bidirectional sound objects without
requiring that you compile your own PortAudio. This is only for historical
reasons.

### Difference from the original

The Playrec version this repository is based on is [7c15bf6](https://github.com/PlayrecForMatlab/playrec/tree/7c15bf6ecba48a1cb54620d066b30281168212d1).

Meanwhile PortAudio merged its MacOSX OS specific integration into the general Unix branch. The version shown here compiles with
[PortAudio v190700](https://files.portaudio.com/archives/pa_stable_v190700_20210406.tgz). Check [here](https://files.portaudio.com/download.html) for the latest
version.

It also looks like Matlab's Mex is not dealing with MacOS's frameworks automatically in the linker. To get Playrec to compile, some LDFLAGS have to be added.
This was done by modifying `m_file/compile_playrec_func.m` and adding the framework definition as extra flags.
