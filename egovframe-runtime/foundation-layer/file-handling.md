# File Handling

## 개요

[File Handling Service](https://www.egovframe.go.kr/wiki/doku.php?id=egovframework:rte2:fdl:file_handling) 를 적용해서 Excel 다운로드 하기 위한 Excel 정보를 설정한다.

[Excel](https://www.egovframe.go.kr/wiki/doku.php?id=egovframework:rte2:fdl:excel) Service에 적용되어 있다.

## 설명

### Source

```java
FileObject writtenFile = manager.resolveFile(baseDir, this.propertyPath);
FileContent writtenContents = writtenFile.getContent();
InputStream is = writtenContents.getInputStream();
 
BufferedReader reader = new BufferedReader(new InputStreamReader(is));
StringBuffer sb = new StringBuffer();
 
for (String line = ""; (line = reader.readLine()) != null; sb.append(line));
is.close();
```