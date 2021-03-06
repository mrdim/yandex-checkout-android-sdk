# Migration guide

### Table of Contents
[4.0.1 -> 4.1.0](##4---4)
- [Обновить версию `ui-lib-1.19.5.aar`](###Обновить-версию-`ui-lib-1.19.5.aar`)<br>

[3.\*.\* -> 4.0.0](##3---4)
- [Подключить ru.yoo.sdk.auth](###Подключить-`ru.yoo.sdk.auth`)
- [Подключить ThreatMetrix Android SDK 5.4-73.aar](###Подключить-ThreatMetrix-Android-SDK-`5.4-73.aar`)
- [Подключить ui-lib-1.19.4.aar](###Подключить-`ui-lib-1.19.4.aar`)


## 4.0.1 -> 4.1.0

### **Обновить версию `ui-lib-1.19.5.aar`**

> Если вы не использовали платежный метод “Яндекс.Деньги”, и не подключали `ru.yoo.sdk.auth`, то этот блок можно пропустить.

Попросить у менеджера по подключению новую библиотеку `ui-lib-1.19.5.aar` и положить её в папку `libs`. Старую версию `ui-lib-1.19.4.aar` нужно удалить.

## 3.\*.\* -> 4.0.0

### Подключить `ru.yoo.sdk.auth`

> Если вы не использовали платежный метод “Яндекс.Деньги”, и не подключали YandexLoginSDK, то этот блок можно пропустить.

Попросить менеджера по подключению зарегистрировать для вас приложение в центре авторизации.

Прописать в `build.gradle`

```groovy
repositories {
    maven { url 'https://dl.bintray.com/yoomoney/maven' }
}
dependencies {
    implementation "ru.yoo.sdk.auth:auth:$yoo_sdk_auth_version"
}
```

### **Подключить `ThreatMetrix Android SDK 5.4-73.aar`**

> Если вы не использовали платежный метод “Яндекс.Деньги”, и не подключали YandexLoginSDK, то этот блок можно пропустить.

Попросите у менеджера по подключению библиотеку `ThreatMetrix Android SDK 5.4-73.aar`. Создайте папку libs в модуле где подключаете sdk и добавьте туда файл `ThreatMetrix Android SDK 5.4-73.aar`. В build.gradle того же модуля в dependencies добавьте:

```
dependencies {
    implementation fileTree(dir: "libs", include: ["*.aar"])
}

```

### **Подключить `ui-lib-1.19.4.aar`**

> Если вы не использовали платежный метод “Яндекс.Деньги”, и не подключали YandexLoginSDK, то этот блок можно пропустить.

Создайте папку `libs` в модуле где подключаете sdk и положите туда файл `ui-lib-1.19.5.aar`. В `build.gradle` того же модуля в dependencies добавьте:

```
dependencies {
    implementation fileTree(dir: "libs", include: ["*.aar"])
}
```