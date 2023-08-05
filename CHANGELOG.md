### [6.0.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v6.0.1) (2023-08-05)
- update canvas lib to be compatible with Node 18

### [6.0.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v6.0.0) (2022-08-07)
- update dependencies
- changed the build process, to be able to use the newest versions of dependencies. This is why it is a major version

### [5.4.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.4.0) (2022-05-22)
- `nft-art-maker updateImageCID`possibility to update the CID when you don't want to use the `nft-art-maker pack` and `nft-art-maker upload` commands. It is an additional way of doing the same operations. Remember to provide the CID in the configuration file using the `overwriteImageCID` key.
- the `edition` field is now optional
- thanks to @dohomi for your awesome contribution

### [5.3.2](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.3.2) (2022-05-21)
- Improvements for upload functionality: It sometimes hangs with massive files, a couple of GB. These improvements should fix it, but we should monitor that further because it depends on the network and IPFS responsiveness at the moment of sending.
- Added a simple progress indicator.

### [5.3.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.3.1) (2022-05-10)
- possibility to configure the metadata files extension, by default `.json`, it can also be set to empty string, so no extension. Thanks to @dohomi.

### [5.3.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.3.0) (2022-05-10)
- nft.storage ipfs car upload using your API key
- progress logging
- some basic tests
- thanks to @dohomi for your awesome contribution

### [5.2.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.2.0) (2022-05-08)
- posibility to define the metadata structure

### [5.1.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.1.1) (2022-04-06)
- npm audit fix

### [5.1.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.1.0) (2022-02-20)
- more fixes regarding how it works
- Additional command: `check` will show how many unique assets are generated. Sometimes the names of files can be misleading when there are not enough layers to achieve the required amount of assets. This probably needs some rewrites in the future.
- better output messages which contain the actual number of generated assets

### [5.0.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.0.1) (2022-02-20)
- fix the bug when there are no rarity values in the file names

### [5.0.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v5.0.0) (2022-01-05)
- Changes in the metadata file structure, the attributes field is now in the root level
- `shuffleLayerConfigurations` is now enabled by default - in most cases, it is desirable, but you can still disable it in the config file
- it should also now work with Node 17 too

### [4.0.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v4.0.0) (2021-12-26)
- The previous assumption about unique CIDs for every file is not well suited for a proper smart contract with a randomized minting process. It would be hard to keep tracking all the CIDs there. It is much simpler and cheaper to have file numbers for all of them and base CID for the directory. `nft-art-maker pack` will now create two .car files with images and metadata json files. The base CID for images will be replaced in all metadata files after packing them into .car. Then the metadata json files CID will be saved into the main big metadata.json file. You can then use both when minting. (Unique CIDs will still work with version 3.0.0, so feel free to use it if needed.)
- added new fields for the image in the metadata output

### [3.0.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v3.0.0) (2021-11-16)
- schema for metadata.json file changes - it is now more standardized
- possibility to pack files using ipfs-car and generate metadata JSON file for each of them with updated CIDs to files. Metadata files will also be packed, and there will be output with the CIDs list. It could be useful when minting
- ~~removed the option to replace the base file URI. It was ok, but a different URI for each file with a different CID is a better solution, and this is now possible using the `nft-art-maker pack` command~~ --> Invalidated in v4.0.0 (for more details see description for v4)
- these are breaking changes, so the major version is now 3. You can still use the older versions.
- minimum version of Node is now **14.14.0**

### [2.2.2](https://github.com/juliancwirko/nft-art-maker/releases/tag/v2.2.2) (2021-11-08)
- bugfix: version command, now it is possible to check the version without configuration

### [2.2.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v2.2.1) (2021-11-04)
- bugfix: there was a problem with `shuffleLayerConfigurations` which randomized the entries in the metadata.json file but not the actual order of images. From now the order in the metadata.json is by edition, but then the images are correctly randomly ordered

### [2.2.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v2.2.0) (2021-10-29)
- possibility to update the image path base in metadata.json - useful when you need to update your paths after uploading, for example, when uploading a CAR file using IPFS, but it can be anything.

### [2.1.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v2.1.0) (2021-10-28)
- bring back `shuffleLayerConfigurations` it has a valid use case even if we want only basic functionality
- fix for preview generation

### [2.0.0](https://github.com/juliancwirko/nft-art-maker/releases/tag/v2.0.0) (2021-10-23)
- changes in the output JSON file
- replace sha1 with sha256, which is now also used for provenance hash
- there will be a possibility to download the image (PNG or SVG) and validate the sha256 hash. You can save this hash on a blockchain with other info like block number and timestamp etc.
- there will also be a possibility to validate provenance hash (hash of hashes)
- it can still get breaking changes in the future. In such a case, there will always be a major version

### [1.0.1](https://github.com/juliancwirko/nft-art-maker/releases/tag/v1.0.1) (2021-10-17)
- initial code
