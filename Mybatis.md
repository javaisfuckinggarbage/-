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
