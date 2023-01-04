---
title: gbd调试
date: 2023-01-04 11:11:00
author: zhangyuanes
categories: Record
tags:
  - Record
  - URL_Encoding
  - 编码
---

## 背景

## 编码与解码

```cpp
class URLFormat {

public:

    static unsigned char toHex(unsigned char x) {
        return  x > 9 ? x + 55 : x + 48;
    }

    static unsigned char fromHex(unsigned char x) {
        unsigned char y = 0;
        if (x >= 'A' && x <= 'Z') y = x - 'A' + 10;
        else if (x >= 'a' && x <= 'z') y = x - 'a' + 10;
        else if (x >= '0' && x <= '9') y = x - '0';
        //else assert(0);
        return y;
    };

    static std::string urlEncode(const std::string& str) {
        std::string strTemp = "";
        size_t length = str.length();
        for (size_t i = 0; i < length; i++) {
            if (isalnum((unsigned char)str[i]) ||
                (str[i] == '-') ||
                (str[i] == '_') ||
                (str[i] == '.') ||
                (str[i] == '~'))
                strTemp += str[i];
            else if (str[i] == ' ')
                strTemp += "+";
            else {
                strTemp += '%';
                strTemp += toHex((unsigned char)str[i] >> 4);
                strTemp += toHex((unsigned char)str[i] % 16);
            }
        }
        return strTemp;
    };

    static std::string urlDecode(const std::string& str) {
        std::string strTemp = "";
        size_t length = str.length();
        for (size_t i = 0; i < length; i++) {
            if (str[i] == '+') {
                strTemp += ' ';
            }
            else if (str[i] == '%') {
                //assert(i + 2 < length);
                if (i + 2 >= length) continue;
                unsigned char high = fromHex((unsigned char)str[++i]);
                unsigned char low = fromHex((unsigned char)str[++i]);
                strTemp += high*16 + low;
            }
            else strTemp += str[i];
        }
        return strTemp;
    };
};
```