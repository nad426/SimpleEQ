# SimpleEQ

## Overview
SimpleEQ is a fully-featured audio equalizer plugin built with the JUCE framework. This plugin provides precise control over your audio's frequency spectrum with low-cut, high-cut, and parametric peak filters, making it suitable for a variety of audio production tasks.

## Features
- **Three-Band EQ System**:
  - Low-cut filter with adjustable frequency and slope
  - High-cut filter with adjustable frequency and slope
  - Parametric peak filter with adjustable frequency, gain, and Q

- **Filter Controls**:
  - Low-cut and high-cut frequency range: 20Hz - 20kHz
  - Peak filter frequency range: 20Hz - 20kHz
  - Peak gain range: -24dB to +24dB
  - Peak quality (Q) range: 0.1 - 10.0
  - Slope options for cut filters: 12, 24, 36, or 48 dB/octave

- **Real-time Spectrum Analysis**:
  - FFT-based frequency spectrum visualization
  - See the effects of your EQ adjustments in real time

## Getting Started

### Prerequisites
- C++ compiler compatible with C++17 standard
- JUCE framework (version 6.0.0 or higher)
- An audio plugin host (DAW) that supports VST3, AU, or standalone applications

### Building the Project
1. Clone this repository to your local machine
2. Open the SimpleEQ.jucer file in Projucer
3. Configure your exporter settings for your platform (Windows, macOS, Linux)
4. Generate the project files for your preferred IDE
5. Build the project in your IDE

### Installation
After building the plugin, install it in your system's VST3 or AU plugin directory:

#### Windows
- Copy the VST3 file to: `C:\Program Files\Common Files\VST3`

#### macOS
- Copy the VST3 file to: `/Library/Audio/Plug-Ins/VST3`
- Copy the AU file to: `/Library/Audio/Plug-Ins/Components`

#### Linux
- Copy the VST3 file to: `~/.vst3`

## Usage
1. Load SimpleEQ in your preferred DAW's plugin chain
2. Adjust the low-cut frequency to remove unwanted low-end rumble
3. Use the peak filter to boost or cut specific frequency ranges
4. Set the high-cut filter to roll off harsh high frequencies
5. Adjust the slope settings for the low-cut and high-cut filters to control how aggressively the filters attenuate frequencies

## Project Structure
- `Source/PluginProcessor.h/cpp`: Core DSP processing logic
- `Source/PluginEditor.h/cpp`: User interface implementation
- The code uses JUCE's DSP module for efficient filter processing
- Real-time spectrum analysis is implemented using FFT

## Technical Details
- Built with JUCE's AudioProcessor framework
- Uses JUCE's dsp module for high-quality digital filters
- Implements sample-accurate parameter automation
- Uses lock-free FIFO for thread-safe communication between audio and UI threads
- FFT analysis with windowing function for accurate spectrum visualization