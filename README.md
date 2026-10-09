# GuardianJoin

GuardianJoin sends the Guardian Curse effect to a player when they join an Axolotl-PM server. It does not change player health, permissions or world data.

[![Build](https://github.com/NhanAZ-Plugins/GuardianJoin/actions/workflows/build.yml/badge.svg)](https://github.com/NhanAZ-Plugins/GuardianJoin/actions/workflows/build.yml)
[![License](https://img.shields.io/github/license/NhanAZ-Plugins/GuardianJoin)](LICENSE)

## Requirements and compatibility

- Axolotl-PM with plugin API `5.0.0`.
- PHP 8.1 or newer in the Axolotl-PM 5 toolchain.

The [build workflow](.github/workflows/build.yml) pins the Axolotl-PM source used for PHPStan at maximum level. Runtime evidence for a particular server release belongs to the corresponding verified build or release. Compatibility with every Axolotl-PM 5.x release has not been established.

## Installation

Download `GuardianJoin.phar` from a verified [GitHub release](https://github.com/NhanAZ-Plugins/GuardianJoin/releases). Place it in the server's `plugins/` directory and restart the server. The plugin has no configuration, commands, permissions or external plugin dependencies.

## Behavior and testing

On `PlayerJoinEvent`, GuardianJoin sends the joining player a `LevelEventPacket` with the Guardian Curse event at the player's position. The effect is visual and is sent to that player's network session.

![Guardian Curse effect shown in a Bedrock client](https://user-images.githubusercontent.com/60387689/179580439-a64344a2-63fa-483a-8b8e-f7851060573f.png)

The [build workflow](.github/workflows/build.yml) runs PHPStan at maximum level, builds and inspects the PHAR with [DevTools](https://github.com/NhanAZ/DevTools), and uploads the verified artifact. A clean server startup confirms that the plugin loads. Seeing the effect requires a Bedrock client, so a startup test alone does not verify its appearance.

## License and support

GuardianJoin is licensed under [GPL-3.0](LICENSE). For help, use [NhanAZ Discord](https://discord.gg/j2X83ujT6c).
