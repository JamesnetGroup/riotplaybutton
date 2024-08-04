# RiotPlayButton [![English](https://img.shields.io/badge/Language-English-blue.svg)](README.md) [![中文](https://img.shields.io/badge/Language-中文-red.svg)](README.zh-CN.md) [![한국어](https://img.shields.io/badge/Language-한국어-red.svg)](README.ko.md)

리그 오브 레전드의 PLAY 버튼에서 영감을 받은 사용자 정의 WPF ToggleButton 기반 컨트롤

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download)
[![Stars](https://img.shields.io/github/stars/vickyqu115/riotplaybutton.svg)](https://github.com/vickyqu115/riotplaybutton/stargazers)
[![Issues](https://img.shields.io/github/issues/vickyqu115/riotplaybutton.svg)](https://github.com/vickyqu115/riotplaybutton/issues)

## 프로젝트 개요

RiotPlayButton은 리그 오브 레전드 게임 클라이언트의 PLAY 버튼을 재현한 사용자 정의 WPF 컨트롤입니다. 사용자 정의 형태 생성, 그라데이션 브러시, 애니메이션, 효율적인 XAML 디자인 등 고급 WPF 기술을 보여줍니다.

<img src="https://github.com/user-attachments/assets/cc980d89-4479-4c4d-8d6a-d97593e12b3b" width="49%"/>
<img src="https://github.com/user-attachments/assets/033e7a46-c0d2-4f3c-9566-69ec0028f442" width="49%"/>
<img src="https://github.com/user-attachments/assets/218fe98c-dfa8-4eb0-9038-c8f4199f107b" width="49%"/>
<img src="https://github.com/user-attachments/assets/ea15edee-6efd-43c5-b796-226ccb78e89a" width="49%"/>
<img src="https://github.com/user-attachments/assets/4beb7730-cfd5-46fb-9a5e-31075ae0db2d" width="49%"/>
<img src="https://github.com/user-attachments/assets/7d0f803c-c8f7-40e0-a324-7ecc4b75126a" width="49%"/>

## 주요 기능 및 구현 사항
#### 1. 사용자 정의 WPF 컨트롤 개발
- [x] 특수 기능을 위한 WPF ToggleButton 확장
- [x] 순수 XAML을 사용한 복잡한 UI 요소 구현

#### 2. 고급 XAML 기술
- [x] Path와 Geometry를 사용한 불규칙한 형태 생성
- [x] 정교한 색상 효과를 위한 LinearGradientBrush 활용

#### 3. 복잡한 형태 생성
- [x] 다중 포인트 형태 생성을 위한 Polygon 사용
- [x] 부드럽고 복잡한 곡선을 위한 Cubic Bezier 곡선 구현
- [x] 간단한 곡선 형태를 위한 Quadratic Bezier 곡선 적용

#### 4. 애니메이션 및 상호작용
- [x] Jamesnet.WPF Nuget 패키지를 사용한 부드러운 애니메이션
- [x] 마우스 오버 및 체크 상태에 대한 상호작용 효과

#### 5. 성능 최적화
- [x] 클리핑 기술을 사용한 효율적인 렌더링
- [x] 성능 향상을 위한 최적화된 XAML 구조

#### 6. 충실한 재현
- [x] 리그 오브 레전드 PLAY 버튼의 픽셀 퍼펙트 재현
- [x] 디자인과 기능성에 대한 세심한 주의

<img src="https://github.com/user-attachments/assets/0abeddcb-8f4e-4273-82d8-e7c42849ec4e" width="49%"/>
<img src="https://github.com/user-attachments/assets/4feb4e87-dbc2-435a-b5fb-cff1640004f8" width="49%"/>
<img src="https://github.com/user-attachments/assets/f7f97dca-9918-45bc-aa49-5920059728ae" width="49%"/>
<img src="https://github.com/user-attachments/assets/7181da5b-0218-40a7-b1a6-e9ac05b334bf" width="49%"/>
<img src="https://github.com/user-attachments/assets/a3a52292-c9ac-441f-bf5c-9f3dd40823e5" width="49%"/>
<img src="https://github.com/user-attachments/assets/c777c08a-9680-4b6c-97e8-1a1edc5d6fb5" width="49%"/>

[이미지 섹션은 동일하게 유지]

## 기술 스택
- WPF (Windows Presentation Foundation)
- .NET 8.0
- C#
- Jamesnet.WPF Nuget 패키지

## 시작하기
### 필요 조건
- Visual Studio 2022 이상
- .NET 8.0 SDK

### 설치 및 실행
#### 1. 리포지토리 복제:

```
git clone https://github.com/vickyqu115/riotplaybutton.git
```

#### 2. 솔루션 열기
- [x] Visual Studio
- [x] Visual Studio Code
- [x] JetBrains Rider

<img src="https://github.com/user-attachments/assets/af70f422-7057-4e77-a54d-042ee8358d2a" width="32%"/>
<img src="https://github.com/user-attachments/assets/e4feaa10-a107-4b58-8d13-1d8be620ec62" width="32%"/>
<img src="https://github.com/user-attachments/assets/5ff487f6-55e4-43e1-9abf-f8d419ee6943" width="32%"/>

#### 3. 빌드 및 실행
- [x] 시작 프로젝트 설정
- [x] F5를 누르거나 실행 버튼 클릭
- [x] Windows 11 권장

## 학습 자료
- [구현에 대한 상세 아티클](https://jamesnet.dev/article/51)
- [YouTube 튜토리얼](https://bit.ly/40YoVIo)
- [BiliBili 튜토리얼](https://bit.ly/49L6dXu)

## 기여하기
RiotPlayButton에 대한 기여를 환영합니다! 이슈를 제출하거나, 풀 리퀘스트를 생성하거나, 개선 사항을 제안해 주세요.

## 라이선스
이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 연락처
- 웹사이트: https://jamesnet.dev
- 이메일: vickyqu115@hotmail.com, james@jamesnet.dev

고급 형태 생성 기술을 갖춘 이 매력적인 리그 오브 레전드 스타일의 PLAY 버튼으로 WPF 애플리케이션을 향상시켜 보세요!
