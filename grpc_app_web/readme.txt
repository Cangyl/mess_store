 split -b 50m grpc-app-web-v1.zip grpc-app-web-v1.zip.part
cat grpc-app-web-v1.zip.part* > grpc-app-web-v1.zip
验证是否正确
md5sum grpc-app-web-v1.zip


