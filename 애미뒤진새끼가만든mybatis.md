# 기본 쿼리 #

```xml
<$queryType id="$queryID">
    	${Query}
</$queryType>

$queryType = {UPDATE, SELECT, DELETE...}
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
