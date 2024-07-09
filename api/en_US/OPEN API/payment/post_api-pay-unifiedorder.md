---
title: "Create Payment"
slug: "post_api-pay-unifiedorder"
excerpt: "WayCode | Payment Method\n------- | -------\nCHANNEL_CASHIER | Channel WEB cashier\nWEB_CASHIER | WEB Cashier\nQR_CASHIER | Aggregated code scanning (user scans merchants)\nAUTO_BAR | Aggregated barcode (merchant scans user)\nALI_BAR | Alipay barcode\nALI_JSAPI | Alipay Life Account\nALI_APP | Alipay APP\nALI_WAP | Alipay WAP\nALI_PC | Alipay PC website\nALI_QR | Alipay QR code\nWX_BAR | WeChat barcode\nWX_JSAPI | WeChat public account\nWX_LITE | WeChat Mini Program\nWX_APP | WeChat APP\nWX_H5 | WeChat H5\nWX_NATIVE | WeChat scan code\nYSF_BAR | Cloud QuickPass barcode\nYSF_JSAPI | Cloud QuickPass jsapi\nAUTO_POS | Smart POS\nDCEP_BAR | Digital RMB barcode\nDCEP_QR | Digital RMB QR code\n\n> channelExtra parameter description\n\nWhen `wayCode=AUTO_BAR` or `wayCode=ALI_BAR` or `wayCode=WX_BAR` or `wayCode=YSF_BAR`, channelExtra must pass auth_code, which is the user's payment code value. ChannelExtra sample data is as follows:\n```json\n{\"authCode\": \"13920933111042\"}\n```\nWhen `wayCode=ALI_JSAPI`, channelExtra must pass buyerUserId, which is the Alipay user ID. The example data of channelExtra is as follows:\n```json\n{\"buyerUserId\": \"2088702585070844\"}\n```\n\n\nWhen `wayCode=WX_JSAPI` or `wayCode=WX_LITE`, channelExtra must pass openid, which is WeChat OpenId. The channelExtra sample data is as follows:\n```json\n{\"openid\": \"o6BcIwvSiRpfS8e_UyfQNrYuk2LI\"}\n```\nNote: If you are currently a special merchant and the merchant uses its own official account or the openId obtained by the mini program:\nneed: \n1. The merchant’s own official account or the AppId of the mini program needs to be associated with the service provider. Please contact the operating platform for configuration;\n2. Add the subAppId parameter to the `channelExtra` parameter. This parameter is the merchant's official account or the AppId of the mini program. Example:\n\n```json\n{ \"openid\": \"o6BcIwvSiRpfS8e_UyfQNrYuk2LI\", \"subAppId\": \"wx08b5a41f7a27abf1\" }\n```\n\nWhen `wayCode=ALI_QR` or `wayCode=WX_NATIVE`, channelExtra can pass the payDataType setting to return the payment data payment type. At this time, payDataType can be: codeUrl - QR code address, codeImgUrl - QR code image address. If payDataType is not passed, the codeUrl type will be returned by default. ChannelExtra sample data is as follows:\n```json\n{\"payDataType\": \"codeImgUrl\"}\n```\nWhen `wayCode=QR_CASHIER`, channelExtra can pass payDataType and entryPageType.\nentryPageType specifies that the H5 or mini program page will be entered when scanning the aggregation code. The default is the H5 page. h5-h5 page, lite-mini program page.\nThe payDataType setting returns the payment data payment type. At this time, payDataType can be: codeUrl - QR code address, codeImgUrl - QR code image address. If payDataType is not passed, the codeUrl type will be returned by default. ChannelExtra sample data is such as:\n```json\n{\"payDataType\": \"codeImgUrl\"}\n```\n\nWhen `wayCode=ALI_WAP`, channelExtra can pass the payDataType setting to return the payment data payment type. At this time, the payDataType can be: form-returns the automatic jump payment form, codeImgUrl-returns a QR code image URL, payUrl-returns the payment link. If payDataType is not passed, the payUrl type is returned by default. ChannelExtra sample data is such as:\n```json\n{\"payDataType\": \"form\"}\n```\n\nWhen `wayCode=ALI_PC`, channelExtra can pass the payDataType setting to return the payment data payment type. At this time, payDataType can be: form-returns the payment form that automatically jumps, payUrl-returns the payment link, if payDataType is not passed, the payUrl type is returned by default, channelExtra sample data is such as:\n```json\n{\"payDataType\": \"form\"}\n```"
hidden: true
createdAt: "Sun Mar 10 2024 07:17:40 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Thu Mar 14 2024 01:13:47 GMT+0000 (Coordinated Universal Time)"
---