FROM --platform=linux/arm64/v8 alexnerd/java:17
LABEL maintainer="Aleksey Popov, alexnerd.com" description="Jakarta EE 9 Full & Web Distribution"
ENV PAYARA_ARCHIVE payaramicro5
ENV INSTALL_DIR /opt
RUN curl -o ${INSTALL_DIR}/${PAYARA_ARCHIVE}.jar -L "https://info.payara.fish/cs/c/?cta_guid=3462e195-f07d-44a2-8815-23bdbf456583&signature=AAH58kGD_os4I2zcU7pqlhanR6hD3gsH9w&placement_guid=908761da-2736-4afd-b6e5-023e5a101b91&click=7cdfd79a-347e-4863-8cb6-fe2504059b12&hsutk=252b962526bee9fff1a44435ef6c03c6&canon=https%3A%2F%2Fwww.payara.fish%2Fdownloads%2Fpayara-platform-community-edition%2F&portal_id=334594&redirect_url=APefjpEXX8zeBtlGoJlrFoJR31nUmK5BYXKuwAn1HhcjGWvcixcb3nWkhextds4-fFDNdKAfJtfAw48LJQ7UQ4dfeJvVgCaz2Oz1N2gtpg2JYIuFJQRjF_o_JTc-uvTlYeLDRJZV9nJlsByLwWt2aKaZ7WFiQvSVBlIpwkuq7nNA3yH5K7WZdXSYPNupiTS9WxXzvqzMqXf45Y8gzhLyqB8uKX4_-C6PVg&__hstc=229474563.252b962526bee9fff1a44435ef6c03c6.1666034658694.1666034658694.1666034658694.1&__hssc=229474563.1.1666034658694&__hsfp=807035548"
ENV PAYARA_HOME ${INSTALL_DIR}
ENV DEPLOYMENT_DIR ${PAYARA_HOME}
ENTRYPOINT java -jar ${PAYARA_ARCHIVE}.jar --deploy ${ARCHIVE_NAME}
WORKDIR ${INSTALL_DIR}
EXPOSE 8080 5900