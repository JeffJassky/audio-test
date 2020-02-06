$ arecord -l
**** List of CAPTURE Hardware Devices ****
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 0: ADMAIF1 CIF ADMAIF1-0 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 1: ADMAIF2 CIF ADMAIF2-1 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 2: ADMAIF3 CIF ADMAIF3-2 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 3: ADMAIF4 CIF ADMAIF4-3 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 4: ADMAIF5 CIF ADMAIF5-4 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 5: ADMAIF6 CIF ADMAIF6-5 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 6: ADMAIF7 CIF ADMAIF7-6 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 7: ADMAIF8 CIF ADMAIF8-7 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 8: ADMAIF9 CIF ADMAIF9-8 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: tegrasndt210ref [tegra-snd-t210ref-mobile-rt565x], device 9: ADMAIF10 CIF ADMAIF10-9 []
  Subdevices: 1/1
  Subdevice #0: subdevice #0


arecord -D hw:tegrasndt210ref,0 -f s24_le -c 2 -r 48000 -d 10 /tmp/i2s4_test.wav

sudo grep "Name:\|J:\|BB:" /sys/kernel/debug/tegra_gpio

Name:Bank:Port CNF OE OUT IN INT_STA INT_ENB INT_LVL
 J: 2:1 00 00 00 00 00 00 000000
BB: 6:3 00 00 00 00 00 00 000000

arecord -D hw:tegrasndt210ref,0 -f s24_le -c 2 -r 48000 -d 10 /tmp/i2s4_test.wav



 arecord -D hw:tegrasndt210ref,0 -r 48000 -f S16_LE -c 1 -d 10 test.wav



Card #0
	Name: alsa_card.platform-70030000.hda
	Driver: module-alsa-card.c
	Owner Module: 7
	Properties:
		alsa.card = "0"
		alsa.card_name = "tegra-hda"
		alsa.long_card_name = "tegra-hda at 0x70038000 irq 83"
		device.bus_path = "platform-70030000.hda"
		sysfs.path = "/devices/70030000.hda/sound/card0"
		device.form_factor = "internal"
		device.string = "0"
		device.description = "Built-in Audio"
		module-udev-detect.discovered = "1"
		device.icon_name = "audio-card"
	Profiles:
		output:hdmi-stereo: Digital Stereo (HDMI) Output (sinks: 1, sources: 0, priority: 5400, available: yes)
		off: Off (sinks: 0, sources: 0, priority: 0, available: yes)
	Active Profile: output:hdmi-stereo
	Ports:
		hdmi-output-0: HDMI / DisplayPort (priority: 5900, latency offset: 0 usec, available)
			Properties:
				device.icon_name = "video-display"
			Part of profile(s): output:hdmi-stereo

Card #1
	Name: alsa_card.platform-sound
	Driver: module-alsa-card.c
	Owner Module: 8
	Properties:
		alsa.card = "1"
		alsa.card_name = "tegra-snd-t210ref-mobile-rt565x"
		alsa.long_card_name = "tegra-snd-t210ref-mobile-rt565x"
		device.bus_path = "platform-sound"
		sysfs.path = "/devices/sound/sound/card1"
		device.form_factor = "internal"
		device.string = "1"
		device.description = "Built-in Audio"
		module-udev-detect.discovered = "1"
		device.icon_name = "audio-card"
	Profiles:
		input:analog-mono: Analog Mono Input (sinks: 0, sources: 1, priority: 2, available: yes)
		input:analog-stereo: Analog Stereo Input (sinks: 0, sources: 1, priority: 60, available: yes)
		output:analog-mono: Analog Mono Output (sinks: 1, sources: 0, priority: 200, available: yes)
		output:analog-mono+input:analog-mono: Analog Mono Duplex (sinks: 1, sources: 1, priority: 202, available: yes)
		output:analog-mono+input:analog-stereo: Analog Mono Output + Analog Stereo Input (sinks: 1, sources: 1, priority: 260, available: yes)
		output:analog-stereo: Analog Stereo Output (sinks: 1, sources: 0, priority: 6000, available: yes)
		output:analog-stereo+input:analog-mono: Analog Stereo Output + Analog Mono Input (sinks: 1, sources: 1, priority: 6002, available: yes)
		output:analog-stereo+input:analog-stereo: Analog Stereo Duplex (sinks: 1, sources: 1, priority: 6060, available: yes)
		off: Off (sinks: 0, sources: 0, priority: 0, available: yes)
	Active Profile: output:analog-stereo+input:analog-stereo
	Ports:
		analog-input: Analog Input (priority: 10000, latency offset: 0 usec)
			Part of profile(s): input:analog-mono, input:analog-stereo, output:analog-mono+input:analog-mono, output:analog-mono+input:analog-stereo, output:analog-stereo+input:analog-mono, output:analog-stereo+input:analog-stereo
		analog-output: Analog Output (priority: 9900, latency offset: 0 usec)
			Part of profile(s): output:analog-mono, output:analog-mono+input:analog-mono, output:analog-mono+input:analog-stereo, output:analog-stereo, output:analog-stereo+input:analog-mono, output:analog-stereo+input:analog-stereo
