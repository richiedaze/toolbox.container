# toolbox.container
A collection of Quadlet container templates for toolbox 
  |Template|Description|
  -|- 
  **toolbox.pod** | **Parent pod for toolbox containers to attach to.**
  | | Not yet available on current podman version. Currently set in toolbox<span>@</span>.container until next release.
  |||
  **toolbox.image** | **Default image set by the Quadlet default configuration.**
  |||
  **toolbox<span>@</span>.container** | **Default Quadlet toolbox container configuration.**
  toolbox<span>@</span>fedora.container | Should be Default Instance to toolbox<span>@</span>.container but doesn't work. We can use the fedora-toolbox.container for now.
  | | 
  **toolbox<span>@</span>ubuntu.container.d** | Override configuration for a ubuntu instance.
  | | Not yet available on current podman version.
  |||
  **fedora-toolbox.container** | toolbox<span>@</span>.container modified for fedora instance.
  |||

## Installation
  1. Create a Quadlet user configuration directory.

      ```sh
      mkdir --parents \
        ~/config/containers/systemd
      ```
      Place Quadlet configuration files in the above directory.
      
  2. View the generated files and/or error messages with:

      ```sh
      /usr/lib/systemd/system-generators/podman-system-generator --user --dryrun
      ```
      
  3. Start a toolbox container

      ```sh
      systemctl --user start toolbox@fedora
      ```
  4. Edit toolbox container

     ```sh
     systemctl --user edit toolbox@fedora
     ```
