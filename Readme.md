https://www.thomasvitale.com/https-spring-boot-ssl-certificate/

1. Generate self signed certificate
`keytool -genkeypair -alias springboot -keyalg RSA -keysize 4096 -storetype PKCS12 -keystore springboot.p12 -validity 3650 -storepass password`
2. check certificate in the keystore 
`keytool -list -keystore springboot.p12`
3. Export certificate from the keystore
`keytool -export -keystore springboot.p12 -alias springboot -file myCertificate.crt`
4. Import certificate into java trusted keystore
   `keytool -importcert -file myCertificate.crt -alias springboot -keystore C:\jdk-11.0.2\lib\security\cacerts`
5. Delete certificate from java trusted keystore
`keytool -delete -alias springboot -keystore C:\jdk-11.0.2\lib\security\cacerts`   
6. `