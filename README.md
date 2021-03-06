# movie-finder电影管理器

> Manage the local movies

#### Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:9080
npm run dev

# build electron application for production
npm run build
```

P.S. The node module `pinyin` requires VS 2015 or MSBuild 14.0 to build up (on Windows).

If it says `MSBUILD : error MSB3428 Could not load the Visual C++ component "VCBuild.exe"`, use the following command to fix:

`npm install --global --production windows-build-tools`

P.S. The node module `drivelist` may need rebuild (`electron-builder install-app-deps` or `npm run postinstall`) after install.

如果出现无法build的情况请为npm设置代理服务器。

#### Config.JSON Structure

``` json
{
    "theme": "light",
    "VF": [0, 2, 4],
    "ffmpeg": "path/to/ffmpeg/executable/file",
    "volumes": [
        {
            "isPortable": false,
            "volume": "D:\\",
            "directories": [
                {
                    "path": "path/to/your/directory",
                    "recursive": false,
                    "files": [
                        {
                            "fileName": "something中文.ext",
                            "nameSlice": [
                                ["something"],
                                ["中", "zhong"],
                                ["文", "wen"]
                            ],
                            "hasViewed": true,
                            "md5": "some md5 hex"
                        }
                    ]
                }
            ]
        },
        {
            "isPortable": true,
            "description": "WD Elements 10B8 USB Device",
            "mountIndex": 0,
            "partitions": 1,
            "size": 2000365289472,
            "directories": [
                {
                    "path": "path/to/your/directory",
                    "recursive":true,
                    "directories": [
                        {
                            "path": "subdirectory",
                            "recursive": false,
                            "files": []
                        }
                    ],
                    "files": []
                }
            ]
        }
    ]
}
```

Due to binding to USB device dynamically, change the number of usb partition will cause corresponding data loss.

#### Todo List

- [ ] Test Available Video Formats
- [ ] Theme
- [ ] Recursive Directory Index
- [ ] Customize Sort
- [ ] Efficient Thumbnail
- [ ] Rebind USB + Thumbnail Rename
- [ ] Clear Thumbnail
- [ ] i18n
- [ ] Performance

---

This project was generated with [electron-vue](https://github.com/SimulatedGREG/electron-vue)@[1c165f7](https://github.com/SimulatedGREG/electron-vue/tree/1c165f7c5e56edaf48be0fbb70838a1af26bb015) using [vue-cli](https://github.com/vuejs/vue-cli). Documentation about the original structure can be found [here](https://simulatedgreg.gitbooks.io/electron-vue/content/index.html).