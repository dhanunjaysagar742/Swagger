# Swagger



1.Add below dependency in POM.XML	
	
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-boot-starter -->
<dependency>
<groupId>io.springfox</groupId>
<artifactId>springfox-boot-starter</artifactId>
<version>3.0.0</version>
</dependency>

2. Add @EnableWebMVC annotation in security Class
	And below public URLS.
PUBLIC_URLS = {
"/v3/api-docs", 
"/v2/api-docs",
"/swagger-resources/**", 
"/swagger-ui/**"
};



3. IT IS OPTIONAL 
	@Configuration
public class SwagggerConfig {
@Bean
public Docket api() {
return new Docket(DocumentationType.SWAGGER_2).apiInfo(getInfo()).select().apis(RequestHandlerSelectors.any())
.paths(PathSelectors.any()).build();
}
private ApiInfo getInfo() {
return new ApiInfo("Application :Swagger TEST ",
"This project is developed by Dj", "1.0", "Terms of Service",
new Contact("Dj", "https://DJ.com", "DJ@gmail.com"),
"License of APIS", "API license URL", Collections.emptyList());
};
}


