package com.abc;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.boot.builder.SpringApplicationBuilder;
import org.springframework.boot.web.servlet.MultipartConfigFactory;
import org.springframework.boot.web.servlet.support.SpringBootServletInitializer;
import org.springframework.context.annotation.Bean;
import org.springframework.util.unit.DataSize;

import javax.servlet.MultipartConfigElement;

// 解决jmx重复注册bean的问题
//@EnableMBeanExport(registration = RegistrationPolicy.IGNORE_EXISTING)
@SpringBootApplication(/*exclude= {DataSourceAutoConfiguration.class}*/)
public class SpringbootApplication extends SpringBootServletInitializer {
    private static Logger logger = LoggerFactory.getLogger(SpringbootApplication.class);

    @Override
    protected SpringApplicationBuilder configure(SpringApplicationBuilder builder) {
        return super.configure(builder);
    }

    @Bean
    public MultipartConfigElement multipartConfigElement() {
        MultipartConfigFactory factory = new MultipartConfigFactory();
        //Max size of one file
        factory.setMaxFileSize(DataSize.ofMegabytes(1000000000)); //KB,MB
        /// Max Size of All files
        factory.setMaxRequestSize(DataSize.ofMegabytes(1000000000));
        return factory.createMultipartConfig();
    }

    public static void main(String[] args) {
        SpringApplication.run(SpringbootApplication.class, args);
        logger.info("------------------启动成功----------------");

    }

}
