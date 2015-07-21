# Proposal: Beeping Paddles #

<pre>
Jack Hall, Reuben Smith<br>
ECE 287 C, Miami University<br>
Fall Semester, 2011<br>
</pre>

## Description ##
Pong, published by Atari and one of the first video games created and commercially successful, is a traditional first step in learning the game development process. The project, a clone of the Pong system, will require developing a video adapter, audio synthesizer, memory controller, input handler, and the logic necessary for the game itself.

Video output relies on a framebuffer stored in memory that will be drawn to a television or monitor via signals generated by the ADV7123 DAC on the DE2 board and output over VGA. Audio signals will be generated on-the-fly using the DE2’s onboard WM8731 codec. Given the interactive nature of Pong, input is taken from Super Nintendo Entertainment System (SNES) controllers that are wired into the GPIO headers on the DE2. Framebuffer and state storage will be implemented using the DE2’s 512KiB SRAM module rather than the more complicated, but more spacious, 8MiB SDRAM module.

## Tasks ##
Given the interdependence of some components, the completion of certain subtasks will be dependent on the completion of some functionality in another component. This dependence will be noted on each subtask in brackets. Desirable but unnecessary features will be listed in italics. Modules created by a third party will be considered, and where chosen the tasks around those systems will represent learning to use their module and integrating it with in-house modules.

  * Video
    * Research VGA protocol and DE2’s DAC
    * Implement video adapter with static output
    * Implement video adapter with framebuffer (Memory)
    * _Implement video adapter with double buffering_
  * Audio
    * Research sound generation and DE2’s WM8731 codec
    * Implement synthesizer with simple tone generation
    * Implement synthesizer with streamed output (Memory)
    * Implement multi-channel sound output
  * Input
    * Research SNES controller protocol and DE2’s GPIO headers
    * Implement single-controller input recognizing a single button press
    * Implement single-controller input recognizing simultaneous signals
    * Implement dual-controller input
  * Memory
    * Research SRAM and memory timing
    * Implement reading from a single address with preloaded data
    * Implement reading from any address
    * Implement writing to a single address with constant data
    * Implement writing to any address with data sent to the module
    * _Implement run-length encoding for video data_
  * Game
    * Create a finite-state machine controlling game progress
    * Generate field (static objects) (Memory)
    * Generate players (paddles) (Memory)
    * Render game (Video, Memory)
    * Handle input controlling players (Input)
    * Handle physics for ball (Memory)
    * Track score (Memory)
    * _Generate a variable field (randomize static object positions) (Memory)_
    * _Add fun, new features (score multipliers, speed-up, etc)_

## Goals ##
  * Increased proficiency with Verilog
  * Better understanding of sequential logic, finite-state machines, timing, and the relevant components of the DE2
  * Experience in the development life cycle of a complex, interdependent system