<p align="center"><a href="https://github.com/MEiDIK/Cipher.so" target="_blank"><img width="200"src="logo.png"></a></p>
<h1 align="center">Cipher.so</h1>
<p align="center">Providing a simple way to keep your secure info safe for android app development.</p>
<p align="center">
  <a href='https://bintray.com/idik-net/Cipher.so/cipher.so/_latestVersion'><img src='https://api.bintray.com/packages/idik-net/Cipher.so/cipher.so/images/download.svg'></a>
  <a href="https://github.com/MEiDIK/Cipher.so/blob/master/LICENSE"><img src="https://img.shields.io/github/license/MEiDIK/Cipher.so.svg" alt="GitHub license"></a>
  <a href="http://androidweekly.net/issues/issue-288"><img src="https://img.shields.io/badge/Android%20Weekly-%23288-green.svg" alt="Android Weekly"></a>
  <a href="#"><img src="https://img.shields.io/badge/Recommend-%E2%AD%90%EF%B8%8F%E2%AD%90%EF%B8%8F%E2%AD%90%EF%B8%8F%E2%AD%90%EF%B8%8F%E2%AD%90%EF%B8%8F-green.svg" alt="Recommend"></a>
</p>

## About

### How it works?

All the key-values will be auto package into a native library during the compile time. Then your can obtain them from the Java interface generated by Cipher.so.

### Features

* Encrypt secure info in a native library via easy configs
* Reflection free

---
## Usages

#### Installation
##### Step 1. in the root build.gradle:  
Add `jcenter()` resposity and `classpath 'net.idik.lib.security:cipher.so:0.0.3'` dependency into the buildscript as fllow:

```groovy
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.0.1'
        classpath 'net.idik.lib.security:cipher.so:0.0.3'
    }
}
```

##### Step 2. in the app module build.gradle:
Add `apply plugin:'cipher.so'` **before**(*VERY IMPORTANT*) `apply plugin: 'com.android.application'`

```groovy
apply plugin: 'cipher.so'
apply plugin: 'com.android.application'
```

That's all, Cipher.so is ready to GO.

#### Configuration

In your app module build.gradle, add the follow-like configs to save key-values.

```groovy
cipher.so {
    keys {
        hello {
            value = 'Hello From Cipher.so😊'
        }
        httpsKey {
            value = 'htkdjfkj@https2017now'
        }
        数据库密码 {
            value = '今天天气不错😂😂'
        }
        ...
    }
}
```

Then Rebuild to generate the Java Interface.

#### 3. Call In Java/Kotlin

```Java
String hello = CipherClient.hello();
String httpsKey = CipherClient.httpsKey();
String dbKey = CipherClient.数据库密码();
```


> Sample: [HelloCipherSo](https://github.com/MEiDIK/HelloCipherSo)




## Contribute?

I am very glad for your contributes. Let's make this job more awnsome.

Here is the contribute workflow from github: [Contribute Guide](https://github.com/openframeworks/openFrameworks/wiki/Code-Contribution-Workflow#workflow)


## Todos
* Encypte data in .so-lib
* Prevent dynamic attacks
    * ~~Check Signature~~
    * More
* Support different Application varients

-----
## References

* [Add C and C++ Code to Your Project](https://developer.android.com/studio/projects/add-native-code.html)
* [Gradle User Guide](https://docs.gradle.org/4.4/userguide/userguide.html)

## Great Thanks to

* [android-api-SecureKeys](https://github.com/saantiaguilera/android-api-SecureKeys) by [Santi Aguilera](https://github.com/saantiaguilera)
* [gradle-android-ribbonizer-plugin](https://github.com/maskarade/gradle-android-ribbonizer-plugin) by [maskarade](https://github.com/maskarade)


## License

    Copyright 2017 认真的帅斌

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
