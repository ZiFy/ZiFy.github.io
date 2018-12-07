---
title: Jenkens CI iOS Project
---
# Jenkens CI iOS Project
test package
## AppStore

1. loginkeychains配置

```
${KEYCHAIN_PATH} ${KEYCHAIN_PASSWORD} ${CODE_SIGNING_IDENTITY}
```

loginkeychains.png

2. 编译准备

```
cd YUNDADA
sh ../scripts/AsignBuildNumber.sh line ${BUILD_NUM}
pod install --verbose

if [ -f "${WORKSPACE}/scripts/copyFiles.sh" ];then
   sh ${WORKSPACE}/scripts/copyFiles.sh
else
   echo "文件不存在"
fi
```
3. xcode配置
xcode_1
xcode_2
xcode_3
xcode_4

4.上传到appstore

```
python upload.py SHIPPER REL 1.1.0 1 ./build/YUNDADA-Shipper.ipa

python upload.py EXPRESS REL 1.1.0 1 ./build/YUNDADA-Line.ipa

```

## 上传appStore

```
IPA_PATH="${WORKSPACE}/build/YUNDADA-Line.ipa"
altoolPath="/Applications/Xcode.app/Contents/Applications/Application Loader.app/Contents/Frameworks/ITunesSoftwareService.framework/Versions/A/Support/altool"
"${altoolPath}" --validate-app -f "${IPA_PATH}" -u transda56@aliyun.com -p ofnc-vnyh-gdig-izka -t ios --output-format xml
"${altoolPath}" --upload-app -f "${IPA_PATH}" -u transda56@aliyun.com -p ofnc-vnyh-gdig-izka -t ios --output-format xml

```

5.通知到钉钉
dingding.png
