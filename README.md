# BaseEnvironment

Studio Biside 프로젝트의 공유 코딩 스타일 정의 및 개발 표준을 포함하는 저장소입니다.

## 목적

- **코딩 스타일**: StyleCop ruleset과 .editorconfig를 통한 일관된 코드 포맷팅
- **개발 표준**: 공유 설정 파일 및 모범 사례
- **프로젝트 간 일관성**: 여러 프로젝트에서 균일한 코드 스타일 보장

## 포함 내용

- `CodingStyle.ruleset`: StyleCop analyzer 규칙 설정
- `.editorconfig`: 에디터 포맷팅 규칙
- 기타 공유 개발 설정

## 사용 방법

이 저장소는 다른 프로젝트에서 git submodule로 사용하도록 설계되었습니다.

### 서브모듈로 추가하기

프로젝트에 BaseEnvironment를 추가하려면:

```bash
# 프로젝트 루트에 서브모듈 추가
git submodule add git@github.com:StudioBside/BaseEnvironment.git BaseEnvironment

# 서브모듈 추가 사항 커밋
git add .gitmodules BaseEnvironment
git commit -m "Add BaseEnvironment submodule"
```

### BaseEnvironment가 포함된 프로젝트 클론하기

BaseEnvironment를 사용하는 프로젝트를 클론할 때:

```bash
# 서브모듈을 포함하여 클론
git clone --recursive <repository-url>

# 또는 이미 클론한 경우, 서브모듈 초기화
git submodule update --init --recursive
```

### 서브모듈 업데이트하기

BaseEnvironment를 최신 버전으로 업데이트하려면:

```bash
# 서브모듈 디렉토리로 이동
cd BaseEnvironment

# 최신 변경 사항 가져오기
git pull origin main

# 프로젝트 루트로 돌아가서 업데이트 커밋
cd ..
git add BaseEnvironment
git commit -m "Update BaseEnvironment submodule"
```

## 프로젝트에서 참조하기

`.csproj` 파일에서 ruleset을 참조하세요:

```xml
<PropertyGroup>
  <CodeAnalysisRuleSet>BaseEnvironment\CodingStyle.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

또는 프로젝트 구조에 따라 경로를 조정하세요:

```xml
<PropertyGroup>
  <CodeAnalysisRuleSet>..\..\BaseEnvironment\CodingStyle.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```
