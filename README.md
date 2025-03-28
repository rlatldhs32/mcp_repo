# Model Context Protocol (MCP)

## 개요
Model Context Protocol(MCP)는 AI 모델과 외부 도구 및 서비스 간의 통신을 위한 표준 프로토콜입니다. 이 프로토콜을 통해 AI 모델은 파일 시스템, 웹 서비스, 데이터베이스 등 다양한 외부 리소스에 접근할 수 있습니다.

## 주요 기능
- **범용 인터페이스**: 다양한 외부 도구와 서비스에 일관된 방식으로 접근
- **확장성**: 새로운.맩바아서 쉽게 추가 가능
- **보안**: 접근 권한 및 리소스 사용에 대한 세밀한 제어

## 구성요소

### MCP 서버
- `text-memory`: 텍스트 데이터를 저장하고 검색하는 서비스
- `find-files`: 로컬 파일 시스템에서 파일을 검색하는 서비스
- `github`: GitHub 저장소와 상호작용하는 서비스

### 설정
시스템은 `claude_desktop_config.json` 파일을 통해 설정됩니다. 이 파일에는 각 MCP 서버의 설정 정보가 포함되어 있습니다.

## 사용 방법
1. 필요한 MCP 서버 설정을 `claude_desktop_config.json`에 추가
2. 관련 패키지 설치 (`npm install` 또는 `npx -y [package-name]`)
3. AI 모델에서 MCP 함수 호출

## 예제
```javascript
// GitHub 저장소 생성 예제
mcpClient.invoke("github", "createRepository", {
  name: "test-repo",
  private: false,
  autoInit: true
});
```

## 보안 참고 사항
토큰과 같은 민감한 정보는 환경 변수를 통해 안전하게 관리해야 합니다.
