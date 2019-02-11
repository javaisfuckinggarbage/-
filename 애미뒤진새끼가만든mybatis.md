# 기본 쿼리 #

```xml
<$queryType id="$queryID" resultType="$resultType" parameterType="$parameterType">
    	${Query}
</$queryType>

$queryType = {UPDATE, SELECT, DELETE...}

$resultType = int

$parameterType
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
