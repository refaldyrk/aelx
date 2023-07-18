# AELX

AELX는 `.aelx` 구성 파일을 읽고 처리할 수 있는 명령 줄 도구입니다. 이 도구는 구성 파일에서 키-값 쌍을 추출하고 JSON 형식이나 환경 변수로 데이터를 출력하는 옵션을 지원합니다.

## 설치

AELX를 설치하려면 다음 단계를 따르세요:

1. AELX 저장소를 복제합니다:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. 프로젝트 디렉토리로 이동합니다:

   ```shell
   cd aelx
   ```

3. AELX를 실행합니다:

   ```shell
   aelx --f=something.aelx -k=key
   ```

## 사용법

다음 옵션과 함께 `aelx` 명령을 실행합니다:

- `-k`: 구성 파일에서 값을 가져올 키 이름입니다.
- `--f`: 읽을 `.aelx` 파일 이름입니다.
- `-j`: 선택적으로 JSON 형식으로 데이터를 출력합니다. 기본값: `false`.
- `--o`: 선택적으로 JSON 형식으로 출력 파일 이름을 지정합니다. 기본값: `aelx.json`.
- `-e`: 선택적으로 데이터를 환경 변수로 출력합니다. 기본값: `false`.

### 사용 예시

1. 구성 파일에서 특정 키의 값을 가져오는 경우:

   ```shell
   aelx -k <키 이름> --f <파일 이름.aelx>
   ```

   예시:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. JSON 형식으로 데이터를 출력하는 경우:

   ```shell
   aelx -k <키 이름> --f <파일 이름.aelx> -j true
   ```

   예시:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. 사용자 정의 파일 이름으로 JSON 형식으로 데이터를 출력하는 경우:

   ```shell
   aelx -k <키 이름> --f <파일 이름.aelx> -j true --o <출력.json>
   ```

   예시:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. 환경 변수로 데이터를 출력하는 경우:

   ```shell
   aelx -k <키 이름> --f <파일 이름.aelx> -e true
   ```

   예시:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## `.aelx` 파일 형식

`.aelx` 파일은 특정 형식을 사용합니다. 다음은 지원되는 `.aelx` 파일 형식의 예시입니다:

```
project: start|
[키-1] 값-1|
[키-2] 값-2|
[키-3] 값-3|
project: end|
```

데이터 추출의 정확성을 보장하기 위해 `.aelx` 파일이 이 형식을 따르도록 하십시오.

## `.aelx` 구성 파일 예시

다음은 `.aelx` 구성 파일 내용의 예시입니다:

```
project: start|
hello[world]|
lorem[ipsum]|
project: end|
```

이 예시에서는 두 개의 키-값 쌍이 있습니다:

- 키: `hello`, 값: `world`
- 키: `lorem`, 값: `ipsum`

이러한 키의 값을 가져오거나 필요에 따라 데이터 추출을 수행하기 위해 `aelx` 명령을 사용할 수 있습니다.