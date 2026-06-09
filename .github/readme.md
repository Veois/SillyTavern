<a name="readme-top"></a>

![][cover]

<div align="center">

English

[![GitHub Stars](https://img.shields.io/github/stars/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/forks)
[![GitHub Issues](https://img.shields.io/github/issues/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/pulls)

</div>

---

### Discord server

| [![][discord-shield-badge]][discord-link] | [Join our Discord community!](https://discord.gg/sillytavern) Get support, share favorite characters and prompts. |
| :---------------------------------------- | :----------------------------------------------------------------------------------------------------------------- |

Or get in touch with the developers directly:

* Discord: cohee, rossascends, wolfsblvt
* Reddit: [/u/RossAscends](https://www.reddit.com/user/RossAscends/), [/u/sillylossy](https://www.reddit.com/user/sillylossy/), [u/Wolfsblvt](https://www.reddit.com/user/Wolfsblvt/)
* [Post a GitHub issue](https://github.com/SillyTavern/SillyTavern/issues)

# What does this fork do?

On page load, the frontend calls getCharacters(), which fetches all character data from the server via /api/characters/all.
Backend Returns All Characters:
The backend endpoint /api/characters/all reads every character .png file, parses the embedded JSON, and returns an array of character objects (either full or "shallow" depending on config).
Potential for Large Data:
If you have many characters, this means a lot of files are read, parsed, and sent to the browser before the UI is usable.

# In short, the more characters you have, the longer the interface takes to load. This fork is designed to fix this.

## To enable indexing, go to the "config.yalm" file and change lazyLoadCharacters: false to lazyLoadCharacters: true.

# What was changed in the fork:

- Bulk Import Tags
- imagen button for image generation in settings. (Adds a button of the same name in the Image Generation settings in order to conveniently and quickly send only what is in the < imagen > < /imagen > box as a prompt, instead of sending the entire text of the LLM.)

### - A character index system was added:
A characters-index.json file is now created and updated in each user's character directory.
This index contains only minimal info: id, name, avatar, tags, etc.
The index is updated automatically when ST start up, characters are added, removed, etc.
### Returns the lightweight character index for fast frontend loading.

# I am an unqualified programmer, the code is written using AI.

# Its work?

Yes, it was checked personally. I have 3500 cards and before these changes I had to wait about 3-4 minutes to be let into the interface, after these changes the wait is a few seconds.

<!-- LINK GROUP -->
[cover]: https://github.com/user-attachments/assets/01a6ae9a-16aa-45f2-8bff-32b5dc587e44
[discord-link]: https://discord.gg/sillytavern
[discord-shield-badge]: https://img.shields.io/discord/1100685673633153084?color=5865F2&label=discord&labelColor=black&logo=discord&logoColor=white&style=for-the-badge
