<h3 align="center">Pywr-schema</h3>

<p align="center">
<a href="https://github.com/pywr/pywr">Pywr</a>용 스키마 및 JSON 검증기.
<br />
<br />
<a href="https://github.com/pywr/pywr-schema/issues">버그 신고</a>
·
<a href="https://github.com/pywr/pywr-schema/issues">기능 요청</a>
</p>

(영문 원본: `README.md`)

## 목차

- [프로젝트 소개](#프로젝트-소개)
- [시작하기](#시작하기)
- [로드맵](#로드맵)
- [기여하기](#기여하기)
- [라이선스](#라이선스)
- [연락처](#연락처)

## 프로젝트 소개

[Pywr](https://github.com/pywr/pywr)는 수자원 모델링 라이브러리입니다. 모델 정의에 JSON 파일 형식을 사용합니다.
아쉽게도 이 형식에는 강력한 스키마 정의가 없으며 독자적인 역직렬화 방식을 사용합니다. 이 때문에 다른 도구에서 모델
정의를 파싱하기가 어렵습니다.

Pywr 자체에 스키마 정의를 추가하고 강화하려는 시도가 여러 차례 있었지만, 하위 호환성 문제로 구현이 어려워졌습니다.
그래서 이 프로젝트는 Pywr JSON 스키마의 별도 정의로 만들어졌습니다. Rust로 `serde`와 `serde_json`을 사용해 구현되어
있습니다. 최신 버전의 Pywr와 스키마 호환성을 달성하는 동시에 사용자 정의 노드와 파라미터도 지원하는 것을 목표로
합니다.

패키지는 라이브러리 `pywr_schema`와 검증기 `pywr_validator`로 나뉩니다. 다른 도구는 Pywr JSON을 파싱하는 데 이
라이브러리를 사용할 수 있습니다.

> 참고: 현재 이 저장소의 워크스페이스에서 실제 크레이트 이름은 `pywr-v1-schema`, `pywr-v1-schema-macros`,
> `pywr-v1-validator`입니다.

## 시작하기

Pywr-schema는 Rust로 빌드되며 정상적으로 [설치](https://www.rust-lang.org/tools/install)된 Rust가 필요합니다.
Pywr JSON 파일을 검증하려면 다음과 같이 검증기를 실행하세요.

   ```sh
   git clone https://github.com/pywr/pywr-schema.git
   cd pywr-schema
   cargo run --bin pywr-v1-validator -- --path /path/to/my-model.json
   ```

## 로드맵

- [x] 노드 초기 지원
- [x] 파라미터 초기 지원
- [ ] 레코더 초기 지원
- [ ] 모든 노드의 스키마 정의
- [ ] 모든 파라미터의 스키마 정의
- [ ] 모든 레코더의 스키마 정의
- [ ] Python 지원

제안된 기능(및 알려진 문제)의 전체 목록은 [열린 이슈](https://github.com/pywr/pywr-schema/issues)를 참고하세요.

## 기여하기

기여는 오픈 소스 커뮤니티를 배우고, 영감을 얻고, 창작하는 놀라운 공간으로 만드는 원동력입니다. 어떤 기여든 **매우
감사히** 받겠습니다.

개선 제안이 있다면 저장소를 포크하고 pull request를 만들어 주세요. "enhancement" 태그로 이슈를 열어도 됩니다.
프로젝트에 스타를 남기는 것도 잊지 마세요! 감사합니다!

1. 프로젝트를 포크합니다
2. 기능 브랜치를 만듭니다 (`git checkout -b feature/AmazingFeature`)
3. 변경 사항을 커밋합니다 (`git commit -m 'Add some AmazingFeature'`)
4. 브랜치에 푸시합니다 (`git push origin feature/AmazingFeature`)
5. Pull Request를 엽니다

## 라이선스

Apache-2 라이선스로 배포됩니다. 자세한 내용은 `LICENSE.txt`를 참고하세요.

## 연락처

프로젝트 링크: [https://github.com/pywr/pywr-schema](https://github.com/pywr/pywr-schema)
