# Table of Contents
1. [Introduction](#introduction)
2. [CPU](#cpu)
3. [RAM](#ram)
4. [GPU](#gpu)
5. [Motherboard](#motherboard)
6. [Storage](#storage)
===ENDTOC===

# Introduction

In this documentation we will review some computer components terminologies to better understand them and help you choose your components for your computer.

# CPU

## Cores

The cores are what determines how many tasks the CPU can handle at the same time. The higher the number of cores the more tasks the CPU can handle at the same time.

## Threads

The threads are like virtual cores. Each CPU core can be "split" in multiple virtual threads that can each handle on task. With that, each core can handle multiple tasks instead of one. However, threads share the same core ressources so they've less performances.

## Frequency / Clock speed

The clock is what determines how many cycles can be executed per second by the CPU. The higher the speed the more operations the CPU can make per second.

The clock speed is measured in GHz (1 GHz = 1B cycles per second)

# RAM

## Capacity

RAM (Random-Access Memory) is a temporary storage used to store software programs and data that are currently used. These programs and data are stored in the RAM during execution because it's a lot faster to access. The more RAM capacity you have, the more fast-access data you can store in it.

## Frequency

The RAM frequency is the speed at which data is transferred between the RAM and the other components (CPU, GPU, Storage, ...). The higher the speed the more data the RAM can transfer per second.

## CAS Latency

CAS Latency (Column Address Strobe Latency) is the number of clock cycles between the one when the data is read and the one when the data is available. It is the latency between the moment the CPU try to read data and the moment the RAM gives it. The lower the CAS Latency the faster the access to data will be.

## Frequency / CAS Latency

If you want to find the best compromise between Frequency and CAS Latency you can use this formula to calculate the real-world latency :

Real-world latency = (CAS Latency * 2000) / Frequency

Example with a RAM with a frequency of 2666 MHz and a CAS Latency of 16 clock ticks:

Real-world latency = (16 clock ticks * 2000) / 2666 MHz = ~12 nano seconds

# GPU

## VRAM

VRAM (Video Random Access Memory) is a memory used by GPU to store image data, textures, ... that can then be quickly accessed by the GPU for faster rendering. The more VRAM the more data can be stored and so you can have better quality and faster rendering.

## Memory Frequency

The VRAM frequency follows the same principle as the [RAM Frequency](#frequency)

## L1/L2/... Cache

Cache is a smaller (usually a few MB) but faster memory than VRAM. It has the same use as VRAM with the difference that it is used to store data that is more important or more often needed.

## DLSS

DLSS (Deep Learning Super Sampling) is an image rendering technology used to create better quality images from lower quality ones using artificial intelligence

# Motherboard

In a performance perspective, motherboard doesn't really affect the performances of the computer as long as it is compatible with you other components.

## CPU

For the CPU you must ensure that the CPU socket and the motherboard chipset are compatibles.

## RAM

For the RAM you must ensure that the memory type (DDR4, DDR5, ...) and frequency are compatibles as well as the number of slots and the maximum ram supported.

## GPU

For the GPU you must ensure that you have enough compatibles PCI ports.

# Storage

## Capacity

The capacity determines how much content the drive can hold. The more capacity you have the better it is.

However, faster disks (like SSD and NVMe) can often hold less data that slower ones (HDD). That's why HDD are good for storing Documents, Images, Videos, ... that doesn't need to be accessed very fast. While SSD and NVMe are good for storing OS, Applications, Games, ... that needs a faster access

## Speed

Storage have 2 types of speed, the reading speed and the writing speed. The reading speed is often the one that matters the most as it's the one you will use when you start an application for example. The writing speed, on the other hand, is only used when you create new files, when downloading apps for example.