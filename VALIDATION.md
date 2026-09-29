# 검증 결과

2026-09-29, 별도 Ubuntu 24.04 Docker 컨테이너에서 검증했습니다. 실제 호스트의 사용자 계정이나 로그인 셸에는 적용하지 않았습니다.

- Ansible 문법 검사: 통과 (ansible-core 2.19.13)
- YAML, Starship TOML, zsh 구문 검사: 통과
- Ubuntu 패키지의 Ansible로 실제 설치: 통과
- root 및 일반 사용자별 설정·파일 소유권: 통과
- 기존 `.zshrc` 백업: 통과
- UID 1500인 `nologin` 서비스 계정 제외: 통과
- git 별칭, 자동 제안, 문법 강조, fzf 키 설정, Starship 함수 로드: 통과
- `useradd -m` 및 `adduser`로 생성한 신규 사용자의 설정·기본 셸: 통과
- 신규 사용자 생성 후 재실행: `ok=58 changed=0 unreachable=0 failed=0`

Ubuntu 최소 컨테이너의 문서 제외 설정은 테스트 전에 해제했습니다. 그렇지 않으면 fzf 패키지의 `/usr/share/doc/fzf/examples/` 파일이 설치되지 않습니다. ARM64 및 다른 Ubuntu 버전, 원격 SSH 연결은 이번에 실행 검증하지 않았습니다.
