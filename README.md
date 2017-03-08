# imageCompressor
image compresser most like image compression in wechat



公司最近要做一款图片共享的软件，研究了一下朋友圈上传图片时对图片的压缩操作，并写了一个比较接近朋友圈图片压缩的image分类。

用了11张图做了对比，比对参数如下：

|     1      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 1600 * 1200 | 176 K |
|     微信     | 1280 * 960  | 205 K |
| compressor | 1280 * 960  | 205 K |

|     2      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 4032 * 3024 |  2 M  |
|     微信     | 1280 * 960  | 213 K |
| compressor | 1280 * 960  | 209 K |

|     3      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 3024 * 4032 | 2.2 M |
|     微信     | 960 * 1280  | 246 K |
| compressor | 960 * 1280  | 242 K |

|     4      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 2818 * 2817 | 2.3 M |
|     微信     | 1280 * 1280 | 520 K |
| compressor | 1280 * 1280 | 504 K |

|     5      |    像素尺寸    | 存储体积  |
| :--------: | :--------: | :---: |
|     原图     | 1334 * 750 | 2.3 M |
|     微信     | 1280 * 719 | 229 K |
| compressor | 1280 * 719 | 224 K |

|     6      |   像素尺寸    | 存储体积  |
| :--------: | :-------: | :---: |
|     原图     | 800 * 800 | 905 K |
|     微信     | 800 * 800 | 168 K |
| compressor | 800 * 800 | 168 K |

|     7      |    像素尺寸    | 存储体积  |
| :--------: | :--------: | :---: |
|     原图     | 1920 *1080 | 262 K |
|     微信     | 1280 * 720 | 61 K  |
| compressor | 1280 * 720 | 61 K  |

|     8      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 2560 * 1600 | 676 K |
|     微信     | 1280 * 800  | 225 K |
| compressor | 1280 * 800  | 225 K |

|     9      |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 3264 * 2448 | 2.9 M |
|     微信     | 1280 * 960  | 307 K |
| compressor | 1280 * 960  | 303 K |

|     10     |    像素尺寸     | 存储体积  |
| :--------: | :---------: | :---: |
|     原图     | 8323 * 5793 | 6.6 M |
|     微信     | 1280 * 890  | 492 K |
| compressor | 1280 * 890  | 528 K |

|     11     |     像素尺寸     | 存储体积  |
| :--------: | :----------: | :---: |
|     原图     | 1968 * 12728 | 4.6 M |
|     微信     | 1280 * 8278  | 913 K |
| compressor |  198 * 1280  | 59 K  |



对于常规图片1-10，压缩后的图片与微信压缩后的图片肉眼几乎无法区分压缩效果。

对于长图11，暂未找到微信的裁剪规则，并没有做出较好的压缩。



测试步骤如下：

1.手机通过 `AirDrop`将图片传到 mac 上，在mac 上右键-显示简介查看原图尺寸和大小

2.手机用原图发朋友圈，将朋友圈中的图片保存至图库，重复1，查看朋友圈处理过的图片的尺寸和大小

3.将mac 中的原图拖到xcode工程中，运行程序，程序会主动将处理过的图片保存到手机中，重复1，查看compressor 处理过得图片的尺寸和大小



如果发现问题欢迎issue!