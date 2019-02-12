
# @RestControllerAdvice == {@ControllerAdvice + @ResponseBody} #

# @ResponseStatus #

사용자에게 원하는 response code와 reason을 리턴

예외처리 함수 앞에 사용

```java
@ResponseStatus(value = HttpStatus.NOT_FOUND, reason = "URL changed..") 
```

# @SessionAttributes #

세션에 데이터를 할당

```java
@SessionAttributes("name") // Model의 key값이 "name"으로 있는 값이 자동으로 세션에 저장

```

# @EnableEurekaServer #

# @EnableDiscoveryClient #

# @Transactional #

데이터베이스 트랜잭션을 설정하고 싶은 메서드에 애노테이션을 적용하면 메서드 내부에서 일어나는 데이터베이스 로직이 전부 성공하게되거나 데이터베이스 접근중 하나라도 실패하면 다시 롤백할 수 있게 해주는 애노테이션

```java
@Transaction(readOnly=true, rollbackFor=Exception.class) // readOnly는 읽기전용 rollbackFor는 해당 Exception이 생기면 롤백

@Transaction(noRollbackFor=Exception.class) // 해당 Exception이 나타나도 롤백하지 말라는 뜻

@Transaction(timeout = 10) // 10초안에 해당 로직을 수행하지 못하면 롤백
```

# @Cacheable #

메서드 앞에 지정하면 해당 메서드를 최초에 호출하면 캐시에 적재하고 다음부터는 동일한 메서드 호출이 있을 때 캐시에서 결과를 가져와서 리턴

```java
@Cacheable(value="cacheKey"), @Cacheable(key="cacheKey")
```

# @CachePut #

캐시를 업데이트하기 위해서 메서드를 항상 실행하게 강제함

# @CacheEvict #

# @CacheConfig #

클래스 레벨에서 공통의 캐시설정을 공유하는 기능

# @Scheduled #

# @EnableAutoConfiguration #

# @PostConstruct #

# @PreConstruct #

# @InitBinder #

# @RequestAttribute #

# @RequestPart #

# @ControllerAdvice #

# @ExceptionHandler(ExceptionClassName.class) #

# @PostMapping #

@RequestMapping(Method=RequestMethod.POST)과 같음

# @GetMapping #

@RequestMapping(Method=RequestMethod.GET)과 같음

# @ModelAttribute #

View에서 전달해주는 파라미터를 클래스(VO/DTO)의 멤버변수로 binding

# @PreDestroy #

# @PropertySource #

# @ConfigurationProperties #

# @CrossOrigin #

# @Lazy #

# @Value #

# @CookieValue #

# @SpringBootApplication == {@Configuration, @EnableAutoConfiguration, @ComponentScan} #

# @Email #

# @Length(min=,max=) #

# @NotEmpty #

# @Range(min=,max=) #

# @URL #

# @AssertFalse #

# @AssertTrue #

# @DecimalMax #

# @DecimalMin #

# @Digits(integer=,fraction=) #

# @Future #

# @Max #

# @Min #

# @Pattern(regex=,flag=) #

# @Size(min=,max=) #

# @Past #

# @NotNull #

# @Null #

# @ObjectId #

# @Retention #

# @Target #

# @Bean #

# @Configuration #

# @Valid #

```ミ●﹏☉ミ```

#### 유효성 검사 계단식의 속성, 메서드 매개 변수 또는 메서드 반환 형식을 표시.

```@Valid : 해당 클래스에 존재하는 유효성 검증 어노테이션으로 값을 검증한다```

```java
public String classVORequest(@Valid ClassVO classVO) // 유효성 검증이 필요한 객체임을 지정
```

# @PathVariable #

```ヽ༼ ಠ益ಠ ༽ﾉ```

#### 메소드 파라미터가 URI 템플릿 변수에 바인드되어야한다는 것을 나타내는 주석.

```@PathVariable : RequestMapping의 URL 파라미터의 값을 할당시킨다```

```java
	@RequestMapping(value="/parameter/{vars:.+}")
	public String membermodify(@PathVariable String vars){
  }
```

# @ResponseBody #

# @RequestHeader("header") #

# @RequestParam("parameter") #

```t(-_-t)```

#### 메서드 매개 변수가 웹 요청 매개 변수에 바인딩되어야 함을 나타내는 주석.

```@RequestParam("parameter") : 매서드 매개변수를 파라미터에 할당시킨다```

```java
public String modify(@RequestParam("parameter") int parameter) {
}
```

# @Controller #

```(° ͜ʖ͡°)╭∩╮```

#### 일반적으로 org.springframework.web.bind.annotation.RequestMapping 주석을 기반으로하는 주석 처리기 메소드와 함께 사용

```@Controller : 해당 클래스를 HTTP 요청을 처리하는 컨트롤러로 위임한다.```

```java
클래스 상위에 기입
@Controller
public class Controller(){}
```


# @RequestMapping #

``import org.springframework.web.bind.annotation.RequestMapping;``

```(╬ ಠ益ಠ)```

#### 요청 처리 클래스의 메소드에 웹 요청을 매핑하는 주석. Spring MVC와 Spring WebFlux는 RequestMappingHandlerMapping과 RequestMappingHandlerAdapter를 통해 각각의 모듈과 패키지 구조에서 이 주석을 지원한다. 

```@RequestMapping("/parameter") : URL을 매핑시킨다.```

```@RequestMapping("/") : 전역매핑.```

```java
클래스 상위에 기입
@Controller
public class Controller(){}
```


# @Autowired (Auto Wiring by type) - Dependency Injection #

``import org.springframework.beans.factory.annotation.Autowired;``

```(╯°□°）╯︵```

#### Spring의 의존성 삽입 기능에 의해 자동 생성되도록 생성자, 필드, 설정 메소드 또는 구성 메소드를 표시한다.

필드, 생성자, 입력파라미터가 여러개인 메소드

@Autowired : 자동으로 의존성 주입 개체를 찾아준다. (Getter Setter)
private ClassName ClassVariable;



# @Qualifier("Object") #

``import org.springframework.beans.factory.annotation.Qualifier;``

#### 이 주석은 autowiring 할 때 후보 빈에 대한 규정 자로 필드 또는 매개 변수에 사용될 수 있다. 또한 다른 사용자 정의 주석에 주석을 달고 한정자로 사용할 수 있다.

@Qualifier("Object") : 

# @Resource (Auto Wiring by Name) * Spring Framework 2.5.*  #

# @Required #

# @Scope #

# @PostConstruct #

# @PreDestory #

# @Inject #

# @Service #

# @Repository #
