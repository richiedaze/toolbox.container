# toolbx.container
### A collection of Quadlet container templates for toolbx

## Base toolbx
- **Default image:** Current Version of registry.fedoraproject.org/fedora-toolbox
- **Default container name:** (instance name)-toolbx
- **Default template chart**

  |Template|Description|
  -|-
  **[toolbx<span>@</span>.container](toolbx@.container)** | The base instruction set to build a default toolbx container.
  **toolbx<span>@</span>.container.d** | The drop-in directory contaning the override instruction set to build a toolbx container. 
  **[toolbx<span>@</span>.container.d/debug.conf](toolbx@.container.d/debug.conf)** | Allow sending debugging messages to journal from this service.
  **[toolbx<span>@</span>.container.d/homedir.conf](toolbx@.container.d/homedir.conf)** | Allow temporary or container allocated home directory alternatives.

## toolbx@fedora
- **Modified image:** Not modified
- **Modified container name:** fedora-toolbox-\$\{VERSION\}.
- **Modified Template chart**

  |Template|Description|
  -|-
  **toolbx<span>@</span>fedora.container.d** | The drop-in directory contaning the override instruction set to build a fedora toolbx container. This directory's content is only read if toolbx<span>@</span>fedora.container exist.
  **toolbx<span>@</span>fedora.container** | Should be a link to toolbx<span>@</span>.container. but renamed after it's instance. Customization's should be made in the directory above.

## Installation

1. Download or clone this repository.
  1. Create a Quadlet user configuration directory, if one does not exist.

      ```sh
      mkdir --parents ~/config/containers/systemd
      ```
      Place Quadlet configuration files in the above directory.
      
  2. Reload systemd user manager configuration

      ```sh
		systemctl --user daemon-reload
      ```
## Debugging quadlet files
1. View the generated files and/or error messages with:

	```sh
    /usr/libexec/podman/quadlet -user -dryrun
	```

2. Read and verify every modification you intended is correct.
      
## Usage
  1. Create a toolbx container with the following command:

      ```sh
      systemctl --user start toolbx@fedora
      ```
  2. Enter the toolbx
	  ```sh
	  toolbox enter
	  ```

---

|Notes|
-|
|- All system modifications to the container will be lost once it's terminated. Persistent modifications are highly encouraged on the image of the container, then by overriding the configuration of the image location.

