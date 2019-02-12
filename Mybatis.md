Maven : https://mvnrepository.com/artifact/org.mybatis

# Config #

# typeAliases #

```매퍼의 resultType, parameterType에서 참조할 오브젝트를 정의한다```

> ```xml
<typeAlias alias="$alias" type="$classPackage" />
````

```xml
<typeAlias alias="sampleVO" type="com.java.app.board.vo.BoardVO" />
```

# Mappers #

# 기본 쿼리 #

```xml
<$queryType id="$queryID" resultType="$resultType" parameterType="$parameterType">
    	${Query}
</$queryType>

$queryType = {UPDATE, SELECT, DELETE...}

$resultType = 반환타입 = {int, DTO}

$parameterType = 매개 변수 타입 = {유효성 검증 어노테이션 클래스 VO}
```

```xml
<select id="selectCount" resultType="int">
    select count(*) from bbs
</select>
```

# Choose #

```xml
<choose>
    <when test="option == 'TC'.toString()">
      ${Query}
    </when>
    <otherwise>
       ${Query}
    </otherwise>
</choose>
```
