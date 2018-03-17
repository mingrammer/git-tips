# Git Tips
> [git tips](https://github.com/git-tips/tips)의 한국어 버전 문서입니다.

[English](http://git.io/git-tips) | [中文](https://github.com/521xueweihan/git-tips) | [Русский](https://github.com/Imangazaliev/git-tips) | [Tiếng Việt](https://github.com/hprobotic/git-tips)

## 팁 툴

* [git-tip](https://www.npmjs.com/package/git-tip) - 아래에 나열된 팁들을 사용할 수 있는 CLI 툴 ([도커 컨테이너](https://github.com/djoudi5/docker-git-tip))

## 목차

> 참고로 모든 명령어는 다음 버전에서 테스트 되었습니다: `git version 2.7.4 (Apple Git-66)`.

* [20개 내외의 명령어로 Git 사용하기](#20개-내외의-명령어로-git-사용하기)
* [Git과 함께 제공되는 유용한 가이드라인 보기](#git과-함께-제공되는-유용한-가이드라인-보기)
* [내용으로 변경사항 검색](#내용으로-변경사항-검색)
* [원격지 동기화 및 로컬 변경사항 덮어쓰기](#원격지-동기화-및-로컬-변경사항-덮어쓰기)
* [특정 커밋까지의 모든 파일 나열하기](#특정-커밋까지의-모든-파일-나열하기)
* [첫 번째 커밋 초기화](#첫-번째-커밋-초기화)
* [충돌된 모든 파일 나열하기](#충돌된-모든-파일-나열하기)
* [특정 커밋에서 변경된 모든 파일 나열하기](#특정-커밋에서-변경된-모든-파일-나열하기)
* [마지막 커밋 이후로 스테이징되지 않은 변경사항 보기](#마지막-커밋-이후로-스테이징되지-않은-변경사항-보기)
* [커밋을 하기 위해 스테이징된 변경사항 보기](#커밋을-하기-위해-스테이징된-변경사항-보기)
* [스테이징된 변경사항과 스테이징되지 않은 변경사항 모두 보기](#스테이징된-변경사항과-스테이징되지-않은-변경사항-모두-보기)
* [이미 마스터 브랜치에 머지된 모든 브랜치 나열하기](#이미-마스터-브랜치에-머지된-모든-브랜치-나열하기)
* [이전 브랜치로 전환하기](#이전-브랜치로-전환하기)
* [이미 마스터 브랜치에 머지된 모든 브랜치들 삭제하기](#이미-마스터-브랜치에-머지된-모든-브랜치들-삭제하기)
* [모든 브랜치들 및 그 브랜치들의 업스트림과 마지막 커밋 나열하기](#모든-브랜치들-및-그-브랜치들의-업스트림과-마지막-커밋-나열하기)
* [업스트림 브랜치 설정 (트래킹)](#업스트림-브랜치-설정-트래킹)
* [로컬 브랜치 삭제](#로컬-브랜치-삭제)
* [원격 브랜치 삭제](#원격-브랜치-삭제)
* [로컬 태그 삭제](#로컬-태그-삭제)
* [원격 태그 삭제](#원격-태그-삭제)
* [로컬 변경사항을 헤드의 마지막 내용으로 되돌리기](#로컬-변경사항을-헤드의-마지막-내용으로-되돌리기)
* [Revert: 새로운 커밋을 생성하면서 커밋 되돌리기](#revert-새로운-커밋을-생성하면서-커밋-되돌리기)
* [Reset: 커밋 제거 (프라이빗 브랜치에서만 사용하길 권고)](#reset-커밋-제거-프라이빗-브랜치에서만-사용하길-권고)
* [이전 커밋 메시지 변경](#이전-커밋-메시지-변경)
* [브랜치의 커밋중 업스트림에 머지되지 않은 커밋 히스토리 보기](#브랜치의-커밋중-업스트림에-머지되지-않은-커밋-히스토리-보기)
* [Author 수정하기](#author-수정하기)
* [글로벌 설정에서 변경된 author로 author 재설정하기](#글로벌-설정에서-변경된-author로-author-재설정하기)
* [원격지 URL 변경하기](#원격지-url-변경하기)
* [모든 원격지 레퍼런스 리스트 나열하기](#모든-원격지-레퍼런스-리스트-나열하기)
* [모든 로컬 및 원격지 브랜치 나열하기](#모든-로컬-및-원격지-브랜치-나열하기)
* [원격지 브랜치만 나열하기](#원격지-브랜치만-나열하기)
* [파일 변경사항의 전체가 아닌 일부만 스테이징하기](#파일-변경사항의-전체가-아닌-일부만-스테이징하기)
* [git 배시 자동완성 사용하기](#git-배시-자동완성-사용하기)
* [2주 전부터 현재까지의 변경사항 보기](#2주-전부터-현재까지의-변경사항-보기)
* [마스터로부터 포크한 이후에 생성된 모든 커밋 보기](#마스터로부터-포크한-이후에-생성된-모든-커밋-보기)
* [cherry-pick을 사용해 브랜치간 커밋 가져오기](#cherry-pick을-사용해-브랜치간-커밋-가져오기)
* [해당 커밋 해시를 가지고 있는 브랜치들 검색하기](#해당-커밋-해시를-가지고-있는-브랜치들-검색하기)
* [Git 명령어 별칭 지정](#git-명령어-별칭-지정)
* [커밋하지 않은 트래킹된 파일들의 상태 저장하기](#커밋하지-않은-트래킹된-파일들의-상태-저장하기)
* [스테이징되지 않은 변경사항들의 현재 상태를 트래킹된 파일로 저장하기](#스테이징되지-않은-변경사항들의-현재-상태를-트래킹된-파일로-저장하기)
* [트래킹되지 않은 파일들까지 모두 포함해 현재 상태 저장하기](#트래킹되지-않은-파일들까지-모두-포함해-현재-상태-저장하기)
* [현재 상태를 메시지와 함께 저장하기](#현재-상태를-메시지와-함께-저장하기)
* [모든 무시된 파일, 트래킹되지 않은 파일, 트래킹된 파일들의 현재 상태 저장하기](#모든-무시된-파일-트래킹되지-않은-파일-트래킹된-파일들의-현재-상태-저장하기)
* [저장된 모든 스태시 리스트 나열하기](#저장된-모든-스태시-리스트-나열하기)
* [스태시 리스트에서 삭제하지 않고 스태시 적용하기](#스태시-리스트에서-삭제하지-않고-스태시-적용하기)
* [마지막으로 저장된 스태시 상태를 적용하고 스태시 리스트에서 삭제하기](#마지막으로-저장된-스태시-상태를-적용하고-스태시-리스트에서-삭제하기)
* [저장된 모든 스태시 삭제하기](#저장된-모든-스태시-삭제하기)
* [스태시로부터 단일 파일 가져오기](#스태시로부터-단일-파일-가져오기)
* [트래킹된 파일들 모두 보기](#트래킹된-파일들-모두-보기)
* [트래킹되지 않은 모든 파일 보기](#트래킹되지-않은-파일들-모두-보기)
* [무시된 파일들 모두 보기](#무시된-파일들-모두-보기)
* [저장소에 새로운 워킹 트리 생성하기 (git 2.5)](#저장소에-새로운-워킹-트리-생성하기-git-25)
* [HEAD로부터 새로운 워킹 트리 생성하기](#head로부터-새로운-워킹-트리-생성하기)
* [파일을 삭제하지 않고 언트래킹하기](#파일을-삭제하지-않고-언트래킹하기)
* [트래킹되지 않은 파일/디렉토리를 실제로 삭제하기 전에 어떤 파일/디렉토리가 삭제되는지 테스트 해보기](#트래킹되지-않은-파일디렉토리를-실제로-삭제하기-전에-어떤-파일디렉토리가-삭제되는지-테스트-해보기)
* [트래킹되지 않은 파일들 강제로 삭제하기](#트래킹되지-않은-파일들-강제로-삭제하기)
* [트래킹되지 않은 디렉토리 강제로 삭제하기](#트래킹되지-않은-디렉토리-강제로-삭제하기)
* [모든 서브 모듈 업데이트하기](#모든-서브-모듈-업데이트하기)
* [현재 브랜치에서 아직 마스터에 머지되지 않은 모든 커밋들 보기](#현재-브랜치에서-아직-마스터에-머지되지-않은-모든-커밋들-보기)
* [브랜치명 수정하기](#브랜치명-수정하기)
* ['feature' 브랜치를 마스터에 리베이스한 후 마스터에 머지하기](#feature-브랜치를-마스터에-리베이스한-후-마스터에-머지하기)
* [마스터 브랜치 아카이브](#마스터-브랜치-아카이브)
* [커밋 메시지는 변경하지 않고 이전 커밋 변경하기](#커밋시-파일-무시하기-예를-들어-changelog-파일)
* [원격지에서 삭제된 원격 브랜치 레퍼런스 제거하기](#원격지에서-삭제된-원격-브랜치-레퍼런스-제거하기)
* [첫 리비전의 커밋 해시값 가져오기](#첫-리비전의-커밋-해시값-가져오기)
* [버전 트리 시각화](#버전-트리-시각화)
* [트래킹된 하위폴더를 gh-pages 브랜치로 배포하기](#트래킹된-하위폴더를-gh-pages-브랜치로-배포하기)
* [subtree를 사용해 저장소에 프로젝트 추가하기](#subtree를-사용해-저장소에-프로젝트-추가하기)
* [subtree를 사용해 관련된 프로젝트의 최신 변경사항을 저장소로 가져오기](#subtree를-사용해-관련된-프로젝트의-최신-변경사항을-저장소로-가져오기)
* [브랜치를 히스토리와 함께 파일로 추출하기](#브랜치를-히스토리와-함께-파일로-추출하기)
* [번들 가져오기](#번들-가져오기)
* [현재 브랜치명 가져오기](#현재-브랜치명-가져오기)
* [커밋시 파일 무시하기 (예를 들어, Changelog 파일)](#커밋시-파일-무시하기-예를-들어-Changelog-파일)
* [리베이스 전에 변경사항 스태시하기](#리베이스-전에-변경사항-스태시하기)
* [ID로 풀 리퀘스트를 로컬 저장소로 가져오기](#id로-풀-리퀘스트를-로컬-저장소로-가져오기)
* [현재 브랜치의 가장 최근 태그 보기](#현재-브랜치의-가장-최근-태그-보기)
* [diff 워드 단위로 보기](#diff-워드-단위로-보기)
* [diff 도구를 사용해 변경사항 보기](#diff-도구를-사용해-변경사항-보기)
* [트래킹된 파일의 변경사항 무시하기](#트래킹된-파일의-변경사항-무시하기)
* [assume-unchanged 되돌리기](#assume-unchanged-되돌리기)
* [`.gitignore`에 명시된 파일들 삭제하기](#gitignore에-명시된-파일들-삭제하기)
* [삭제된 파일 복구하기](#삭제된-파일-복구하기)
* [특정 커밋으로의 파일로 복구하기](#특정-커밋으로의-파일로-복구하기)
* [pull시 머지하는 대신 항상 리베이스 하기](#pull시-머지하는-대신-항상-리베이스-하기)
* [모든 별칭과 설정값들 나열하기](#모든-별칭과-설정값들-나열하기)
* [대소문자 구별 활성화](#대소문자-구별-활성화)
* [커스텀 에디터 추가하기](#커스텀-에디터-추가하기)
* [오타 자동 수정 활성화](#오타-자동-수정-활성화)
* [변경사항이 어떤 릴리즈에 속하는지 확인하기](#변경사항이-어떤-릴리즈에-속하는지-확인하기)
* [명령어 테스트 해보기 (dry-run 플래그를 지원하는 모든 명령어에서 가능)](#명령어-테스트-해보기-dry-run-플래그를-지원하는-모든-명령어에서-가능)
* [커밋이 이전 커밋의 수정 버전임을 표시하기](#커밋이-이전-커밋의-수정-버전임을-표시하기)
* [fixup 커밋을 일반 커밋으로 스쿼시하기](#fixup-커밋을-일반-커밋으로-스쿼시하기)
* [커밋시 스테이징된 파일들 스킵하기](#커밋시-스테이징된-파일들-스킵하기)
* [대화형으로 스테이징하기](#대화형으로-스테이징하기)
* [무시된 파일들 나열하기](#무시된-파일들-나열하기)
* [무시된 파일들 상태 출력](#무시된-파일들-상태-출력)
* [Branch2에는 없고 Branch1에만 있는 커밋들 나열하기](#branch2에는-없고-branch1에만-있는-커밋들-나열하기)
* [마지막 n개의 커밋 나열하기](#마지막-n개의-커밋-나열하기)
* [이전에 충돌을 해결했던 방법을 기록하고 재사용하기](#이전에-충돌을-해결했던-방법을-기록하고-재사용하기)
* [모든 충돌된 파일들 에디터로 열기](#모든-충돌된-파일들-에디터로-열기)
* [unpacked 오브젝트의 갯수와 디스크 사용량 보기](#unpacked-오브젝트의-갯수와-디스크-사용량-보기)
* [오브젝트 데이터베이스에서 도달할 수 없는 오브젝트들 제거하기](#오브젝트-데이터베이스에서-도달할-수-없는-오브젝트들-제거하기)
* [gitweb으로 워킹 디렉토리 탐색하기](#gitweb으로-워킹-디렉토리-탐색하기)
* [커밋 로그에서 GPG 시그니쳐 보기](#커밋-로그에서-gpg-시그니쳐-보기)
* [글로벌 설정에서 엔트리 제거하기](#글로벌-설정에서-엔트리-제거하기)
* [히스토리가 없는 새로운 브랜치로 체크아웃하기](#히스토리가-없는-새로운-브랜치로-체크아웃하기)
* [다른 브랜치에서 파일내용 가져오기](#다른-브랜치에서-파일내용-가져오기)
* [루트 커밋과 머지 커밋만 나열하기](#루트-커밋과-머지-커밋만-나열하기)
* [대화형 리베이스로 이전 두 커밋 수정하기](#대화형-리베이스로-이전-두-커밋-수정하기)
* [작업중인 브랜치들 모두 나열하기](#작업중인-브랜치들-모두-나열하기)
* [이진 탐색으로 좋은/안좋은 커밋 검색하기](#이진-탐색으로-좋은안좋은-커밋-검색하기)
* [pre-commit과 commit-msg 깃 후킹 우회하기](#pre-commit과-commit-msg-깃-후킹-우회하기)
* [특정 파일에 대한 커밋과 변경사항 나열하기 (이름이 바뀐 파일도 추적)](#특정-파일에-대한-커밋과-변경사항-나열하기-이름이-바뀐-파일도-추적)
* [단일 브랜치 클론](#단일-브랜치-클론)
* [새로운 브랜치 생성과 동시에 스위칭](#새로운-브랜치-생성과-동시에-스위칭)
* [커밋시 파일 모드 변경 무시](#커밋시-파일-모드-변경-무시)
* [Git 터미널 색상 출력 비활성화](#git-터미널-색상-출력-비활성화)
* [특정 명령어에 대한 색상 설정 지정하기](#특정-명령어에-대한-색상-설정-지정하기)
* [모든 로컬 브랜치를 최근 커밋 날짜를 기준으로 정렬해 나열하기](#모든-로컬-브랜치를-최근-커밋-날짜를-기준으로-정렬해-나열하기)
* [트래킹된 파일에서 패턴(정규식이나 문자열)에 매칭되는 라인 검색](#트래킹된-파일에서-패턴정규식이나-문자열에-매칭되는-라인-검색)
* [저장소의 얕은 카피 버전 클론하기](#저장소의-얕은-카피-버전-클론하기)
* [모든 브랜치에서 주어진 텍스트로 커밋 로그 검색하기](#모든-브랜치에서-주어진-텍스트로-커밋-로그-검색하기)
* [브랜치의 첫 커밋 가져오기 (마스터 브랜치로부터 시작된)](#브랜치의-첫-커밋-가져오기-마스터-브랜치로부터-시작된)
* [스테이징된 파일들 언스테이징하기](#스테이징된-파일들-언스테이징하기)
* [원격 저장소에 강제 푸시하기](#원격-저장소에-강제-푸시하기)
* [저장소명 추가하기](#저장소명-추가하기)
* [주어진 파일의 각 라인별 author, 시간 그리고 최종 리비전명 보기](#주어진-파일의-각-라인별-author-시간-그리고-최종-리비전명-보기)
* [Author와 제목으로 커밋 그룹핑하기](#author와-제목으로-커밋-그룹핑하기)
* [다른 사람이 작업한 내용을 덮어쓰지 않고 강제 푸시하기](#다른-사람이-작업한-내용을-덮어쓰지-않고-강제-푸시하기)
* [특정 author가 기여한 라인수 보기](#특정-author가-기여한-라인수-보기)
* [Revert: 머지 복구하기](#revert-머지-복구하기)
* [특정 브랜치의 커밋 수 출력하기](#특정-브랜치의-커밋-수-출력하기)
* [별칭: git undo](#별칭-git-undo)
* [오브젝트에 노트(메모) 추가하기](#오브젝트에-노트메모-추가하기)
* [모든 깃 노트 보기](#모든-깃-노트-보기)
* [다른 저장소에 있는 커밋 적용하기](#다른-저장소에-있는-커밋-적용하기)
* [페치 레퍼런스 지정하기](#페치-레퍼런스-지정하기)
* [두 브랜치의 공통 조상 커밋 찾기](#두-브랜치의-공통-조상-커밋-찾기)
* [푸시되지 않은 커밋들 나열하기](#푸시되지-않은-커밋들-나열하기)
* [공백 변경사항을 제외한 모든 변경사항 추가하기](#공백-변경사항을-제외한-모든-변경사항-추가하기)
* [깃 설정 [로컬/글로벌] 수정하기](#깃-설정-로컬글로벌-수정하기)
* [특정 구간에서 blame 정보 보기](#특정-구간에서-blame-정보-보기)
* [Git의 논리적 변수 보기](#git의-논리적-변수-보기)
* [패치 파일 미리 포맷팅하기](#패치-파일-미리-포맷팅하기)
* [저장소명 가져오기](#저장소명-가져오기)
* [특정 날짜 구간 사이의 커밋 로그 출력하기](#특정-날짜-구간-사이의-커밋-로그-출력하기)
* [로그에서 author 제외하기](#로그에서-author-제외하기)
* [브랜치의 수정사항 요약하기](#브랜치의-수정사항-요약하기)
* [원격 저장소의 모든 레퍼런스 나열하기](#원격-저장소의-모든-레퍼런스-나열하기)
* [트래킹되지 않은 파일들 백업하기](#트래킹되지-않은-파일들-백업하기)
* [모든 git 명령어 별칭 나열하기](#모든-git-명령어-별칭-나열하기)
* [git 상태 간략하게 보기](#git-상태-간략하게-보기)
* [하루 전의 커밋으로 체크아웃하기](#하루-전의-커밋으로-체크아웃하기)

## 20개 내외의 명령어로 Git 사용하기
```sh
git help everyday
```

## Git과 함께 제공되는 유용한 가이드라인 보기
```sh
git help -g
```

## 내용으로 변경사항 검색
```sh
git log -S'<a term in the source>'
```

## 원격지 동기화 및 로컬 변경사항 덮어쓰기
```sh
git fetch origin && git reset --hard origin/master && git clean -f -d
```

## 특정 커밋까지의 모든 파일 나열하기
```sh
git ls-tree --name-only -r <commit-ish>
```

## 첫 번째 커밋 초기화
```sh
git update-ref -d HEAD
```

## 충돌된 모든 파일 나열하기
```sh
git diff --name-only --diff-filter=U
```

## 특정 커밋에서 변경된 모든 파일 나열하기
```sh
git diff-tree --no-commit-id --name-only -r <commit-ish>
```

## 마지막 커밋 이후로 스테이징되지 않은 변경사항 보기
```sh
git diff
```

## 커밋을 하기 위해 스테이징된 변경사항 보기
```sh
git diff --cached
```


__다른 방법:__
```sh
git diff --staged
```

## 스테이징된 변경사항과 스테이징되지 않은 변경사항 모두 보기
```sh
git diff HEAD
```

## 이미 마스터 브랜치에 머지된 모든 브랜치 나열하기
```sh
git branch --merged master
```

## 이전 브랜치로 전환하기
```sh
git checkout -
```


__다른 방법:__
```sh
git checkout @{-1}
```

## 이미 마스터 브랜치에 머지된 모든 브랜치들 삭제하기
```sh
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```


__다른 방법:__
```sh
git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d # will not delete master if master is not checked out
```

## 모든 브랜치들 및 그 브랜치들의 업스트림과 마지막 커밋 나열하기
```sh
git branch -vv
```

## 업스트림 브랜치 설정 (트래킹)
```sh
git branch -u origin/mybranch
```

## 로컬 브랜치 삭제
```sh
git branch -d <local_branchname>
```

## 원격 브랜치 삭제
```sh
git push origin --delete <remote_branchname>
```


__다른 방법:__
```sh
git push origin :<remote_branchname>
```

## 로컬 태그 삭제
```sh
git tag -d <tag-name>
```

## 원격 태그 삭제
```sh
git push origin :refs/tags/<tag-name>
```

## 로컬 변경사항을 헤드의 마지막 내용으로 되돌리기
```sh
git checkout -- <file_name>
```

## Revert: 새로운 커밋을 생성하면서 커밋 되돌리기
```sh
git revert <commit-ish>
```

## Reset: 커밋 제거 (프라이빗 브랜치에서만 사용하길 권고)
```sh
git reset <commit-ish>
```

## 이전 커밋 메시지 변경
```sh
git commit -v --amend
```

## 브랜치의 커밋중 업스트림에 머지되지 않은 커밋 히스토리 보기
```sh
git cherry -v master
```

## Author 수정하기
```sh
git commit --amend --author='Author Name <email@address.com>'
```

## 글로벌 설정에서 변경된 author로 author 재설정하기
```sh
git commit --amend --reset-author --no-edit
```

## 원격지 URL 변경하기
```sh
git remote set-url origin <URL>
```

## 모든 원격지 레퍼런스 리스트 나열하기
```sh
git remote
```


__다른 방법:__
```sh
git remote show
```

## 모든 로컬 및 원격지 브랜치 나열하기
```sh
git branch -a
```

## 원격지 브랜치만 나열하기
```sh
git branch -r
```

## 파일 변경사항의 전체가 아닌 일부만 스테이징하기
```sh
git add -p
```

## Git 배시 자동완성 사용하기
```sh
curl http://git.io/vfhol > ~/.git-completion.bash && echo '[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash' >> ~/.bashrc
```

## 2주 전부터 현재까지의 변경사항 보기
```sh
git log --no-merges --raw --since='2 weeks ago'
```


__다른 방법:__
```sh
git whatchanged --since='2 weeks ago'
```

## 마스터로부터 포크한 이후에 생성된 모든 커밋 보기
```sh
git log --no-merges --stat --reverse master..
```

## cherry-pick을 사용해 브랜치간 커밋 가져오기
```sh
git checkout <branch-name> && git cherry-pick <commit-ish>
```

## 해당 커밋 해시를 가지고 있는 브랜치들 검색하기
```sh
git branch -a --contains <commit-ish>
```


__다른 방법:__
```sh
git branch --contains <commit-ish>
```

## Git 명령어 별칭 지정
```sh
git config --global alias.<handle> <command> 
git config --global alias.st status
```

## 커밋하지 않은 트래킹된 파일들의 상태 저장하기
```sh
git stash
```


__다른 방법:__
```sh
git stash save
```

## 스테이징되지 않은 변경사항들의 현재 상태를 트래킹된 파일로 저장하기
```sh
git stash -k
```


__다른 방법:__
```sh
git stash --keep-index
```


```sh
git stash save --keep-index
```

## 트래킹되지 않은 파일들까지 모두 포함해 현재 상태 저장하기
```sh
git stash -u
```


__다른 방법:__
```sh
git stash save -u
```


```sh
git stash save --include-untracked
```

## 현재 상태를 메시지와 함께 저장하기
```sh
git stash save <message>
```

## 모든 무시된 파일, 트래킹되지 않은 파일, 트래킹된 파일들의 현재 상태 저장하기
```sh
git stash -a
```


__다른 방법:__
```sh
git stash --all
```


```sh
git stash save --all
```

## 저장된 모든 스태시 리스트 나열하기
```sh
git stash list
```

## 스태시 리스트에서 삭제하지 않고 스태시 적용하기
```sh
git stash apply <stash@{n}>
```

## 마지막으로 저장된 스태시 상태를 적용하고 스태시 리스트에서 삭제하기
```sh
git stash pop
```


__다른 방법:__
```sh
git stash apply stash@{0} && git stash drop stash@{0}
```

## 저장된 모든 스태시 삭제하기
```sh
git stash clear
```


__다른 방법:__
```sh
git stash drop <stash@{n}>
```

## 스태시로부터 단일 파일 가져오기
```sh
git checkout <stash@{n}> -- <file_path>
```


__다른 방법:__
```sh
git checkout stash@{0} -- <file_path>
```

## 트래킹된 파일들 모두 보기
```sh
git ls-files -t
```

## 트래킹되지 않은 파일들 모두 보기
```sh
git ls-files --others
```

## 무시된 파일들 모두 보기
```sh
git ls-files --others -i --exclude-standard
```

## 저장소에 새로운 워킹 트리 생성하기 (git 2.5)
```sh
git worktree add -b <branch-name> <path> <start-point>
```

## HEAD로부터 새로운 워킹 트리 생성하기
```sh
git worktree add --detach <path> HEAD
```

## 파일을 삭제하지 않고 언트래킹하기
```sh
git rm --cached <file_path>
```


__다른 방법:__
```sh
git rm --cached -r <directory_path>
```

## 트래킹되지 않은 파일/디렉토리를 실제로 삭제하기 전에 어떤 파일/디렉토리가 삭제되는지 테스트 해보기
```sh
git clean -n
```

## 트래킹되지 않은 파일들 강제로 삭제하기
```sh
git clean -f
```

## 트래킹되지 않은 디렉토리 강제로 삭제하기
```sh
git clean -f -d
```


__다른 방법:__
```sh
git clean -df
```

## 모든 서브 모듈 업데이트하기
```sh
git submodule foreach git pull
```


__다른 방법:__
```sh
git submodule update --init --recursive
```


```sh
git submodule update --remote
```

## 현재 브랜치에서 아직 마스터에 머지되지 않은 모든 커밋들 보기
```sh
git cherry -v master
```


__다른 방법:__
```sh
git cherry -v master <branch-to-be-merged>
```

## 브랜치명 수정하기
```sh
git branch -m <new-branch-name>
```


__다른 방법:__
```sh
git branch -m [<old-branch-name>] <new-branch-name>
```

## 'feature' 브랜치를 마스터에 리베이스한 후 마스터에 머지하기
```sh
git rebase master feature && git checkout master && git merge -
```

## 마스터 브랜치 아카이브
```sh
git archive master --format=zip --output=master.zip
```

## 커밋 메시지는 변경하지 않고 이전 커밋 변경하기
```sh
git add --all && git commit --amend --no-edit
```

## 원격지에서 삭제된 원격 브랜치 레퍼런스 제거하기
```sh
git fetch -p
```


__다른 방법:__
```sh
git remote prune origin
```

## 첫 리비전의 커밋 해시값 가져오기
```sh
 git rev-list --reverse HEAD | head -1
```


__다른 방법:__
```sh
git rev-list --max-parents=0 HEAD
```


```sh
git log --pretty=oneline | tail -1 | cut -c 1-40
```


```sh
git log --pretty=oneline --reverse | head -1 | cut -c 1-40
```

## 버전 트리 시각화
```sh
git log --pretty=oneline --graph --decorate --all
```


__다른 방법:__
```sh
gitk --all
```

## 트래킹된 하위폴더를 gh-pages 브랜치로 배포하기
```sh
git subtree push --prefix subfolder_name origin gh-pages
```

## subtree를 사용해 저장소에 프로젝트 추가하기
```sh
git subtree add --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## subtree를 사용해 관련된 프로젝트의 최신 변경사항을 저장소로 가져오기
```sh
git subtree pull --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## 브랜치를 히스토리와 함께 파일로 추출하기
```sh
git bundle create <file> <branch-name>
```

## 번들 가져오기
```sh
git clone repo.bundle <repo-dir> -b <branch-name>
```

## 현재 브랜치명 가져오기
```sh
git rev-parse --abbrev-ref HEAD
```

## 커밋시 파일 무시하기 (예를 들어, Changelog 파일)
```sh
git update-index --assume-unchanged Changelog; git commit -a; git update-index --no-assume-unchanged Changelog
```

## 리베이스 전에 변경사항 스태시하기
```sh
git rebase --autostash
```

## ID로 풀 리퀘스트를 로컬 저장소로 가져오기
```sh
git fetch origin pull/<id>/head:<branch-name>
```


__다른 방법:__
```sh
git pull origin pull/<id>/head:<branch-name>
```

## 현재 브랜치의 가장 최근 태그 보기
```sh
git describe --tags --abbrev=0
```

## diff 워드 단위로 보기
```sh
git diff --word-diff
```

## diff 도구를 사용해 변경사항 보기
```sh
git difftool -t <commit1> <commit2> <path>
```

## 트래킹된 파일의 변경사항 무시하기
```sh
git update-index --assume-unchanged <file_name>
```

## assume-unchanged 되돌리기
```sh
git update-index --no-assume-unchanged <file_name>
```

## `.gitignore`에 명시된 파일들 삭제하기
```sh
git clean -X -f
```

## 삭제된 파일 복구하기
```sh
git checkout <deleting_commit>^ -- <file_path>
```

## 특정 커밋으로의 파일로 복구하기
```sh
git checkout <commit-ish> -- <file_path>
```

## pull시 머지하는 대신 항상 리베이스 하기
```sh
git config --global pull.rebase true
```


__다른 방법:__
```sh
#git < 1.7.9
git config --global branch.autosetuprebase always
```

## 모든 별칭과 설정값들 나열하기
```sh
git config --list
```

## 대소문자 구별 활성화
```sh
git config --global core.ignorecase false
```

## 커스텀 에디터 추가하기
```sh
git config --global core.editor '$EDITOR'
```

## 오타 자동 수정 활성화
```sh
git config --global help.autocorrect 1
```

## 변경사항이 어떤 릴리즈에 속하는지 확인하기
```sh
git name-rev --name-only <SHA-1>
```

## 명령어 테스트 해보기 (dry-run 플래그를 지원하는 모든 명령어에서 가능)
```sh
git clean -fd --dry-run
```

## 커밋이 이전 커밋의 수정 버전임을 표시하기
```sh
git commit --fixup <SHA-1>
```

## fixup 커밋을 일반 커밋으로 스쿼시하기
```sh
git rebase -i --autosquash
```

## 커밋시 스테이징된 파일들 스킵하기
```sh
git commit --only <file_path>
```

## 대화형으로 스테이징하기
```sh
git add -i
```

## 무시된 파일들 나열하기
```sh
git check-ignore *
```

## 무시된 파일들 상태 출력
```sh
git status --ignored
```

## Branch2에는 없고 Branch1에만 있는 커밋들 나열하기
```sh
git log Branch1 ^Branch2
```

## 마지막 n개의 커밋 나열하기
```sh
git log -<n>
```


__다른 방법:__
```sh
git log -n <n>
```

## 이전에 충돌을 해결했던 방법을 기록하고 재사용하기
```sh
git config --global rerere.enabled 1
```

## 모든 충돌된 파일들 에디터로 열기
```sh
git diff --name-only | uniq | xargs $EDITOR
```

## unpacked 오브젝트의 갯수와 디스크 사용량 보기
```sh
git count-objects --human-readable
```

## 오브젝트 데이터베이스에서 도달할 수 없는 오브젝트들 제거하기
```sh
git gc --prune=now --aggressive
```

## gitweb으로 워킹 디렉토리 탐색하기
```sh
git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
```

## 커밋 로그에서 GPG 시그니쳐 보기
```sh
git log --show-signature
```

## 글로벌 설정에서 엔트리 제거하기
```sh
git config --global --unset <entry-name>
```

## 히스토리가 없는 새로운 브랜치로 체크아웃하기
```sh
git checkout --orphan <branch_name>
```

## 다른 브랜치에서 파일내용 가져오기
```sh
git show <branch_name>:<file_name>
```

## 루트 커밋과 머지 커밋만 나열하기
```sh
git log --first-parent
```

## 대화형 리베이스로 이전 두 커밋 수정하기
```sh
git rebase --interactive HEAD~2
```

## 작업중인 브랜치들 모두 나열하기
```sh
git checkout master && git branch --no-merged
```

## 이진 탐색으로 좋은/안좋은 커밋 검색하기
```sh
git bisect start                    # Search start 
git bisect bad                      # Set point to bad commit 
git bisect good v2.6.13-rc2         # Set point to good commit|tag 
git bisect bad                      # Say current state is bad 
git bisect good                     # Say current state is good 
git bisect reset                    # Finish search 

```

## pre-commit과 commit-msg 깃 후킹 우회하기
```sh
git commit --no-verify
```

## 특정 파일에 대한 커밋과 변경사항 나열하기 (이름이 바뀐 파일도 추적)
```sh
git log --follow -p -- <file_path>
```

## 단일 브랜치 클론
```sh
git clone -b <branch-name> --single-branch https://github.com/user/repo.git
```

## 새로운 브랜치 생성과 동시에 스위칭
```sh
git checkout -b <branch-name>
```


__다른 방법:__
```sh
git branch <branch-name> && git checkout <branch-name>
```

## 커밋시 파일 모드 변경 무시
```sh
git config core.fileMode false
```

## Git 터미널 색상 출력 비활성화
```sh
git config --global color.ui false
```

## 특정 명령어에 대한 색상 설정 지정하기
```sh
git config --global <specific command e.g branch, diff> <true, false or always>
```

## 모든 로컬 브랜치를 최근 커밋 날짜를 기준으로 정렬해 나열하기
```sh
git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/
```

## 트래킹된 파일에서 패턴(정규식이나 문자열)에 매칭되는 라인 검색
```sh
git grep --heading --line-number 'foo bar'
```

## 저장소의 얕은 카피 버전 클론하기
```sh
git clone https://github.com/user/repo.git --depth 1
```

## 모든 브랜치에서 주어진 텍스트로 커밋 로그 검색하기
```sh
git log --all --grep='<given-text>'
```

## 브랜치의 첫 커밋 가져오기 (마스터 브랜치로부터 시작된)
```sh
git log master..<branch-name> --oneline | tail -1
```

## 스테이징된 파일들 언스테이징하기
```sh
git reset HEAD <file-name>
```

## 원격 저장소에 강제 푸시하기
```sh
git push -f <remote-name> <branch-name>
```

## 저장소명 추가하기
```sh
git remote add <remote-nickname> <remote-url>
```

## 주어진 파일의 각 라인별 author, 시간 그리고 최종 리비전명 보기
```sh
git blame <file-name>
```

## Author와 제목으로 커밋 그룹핑하기
```sh
git shortlog
```

## 다른 사람이 작업한 내용을 덮어쓰지 않고 강제 푸시하기
```sh
git push --force-with-lease <remote-name> <branch-name>
```

## 특정 author가 기여한 라인수 보기
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | gawk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s removed lines: %s total lines: %s
", add, subs, loc }' -
```


__다른 방법:__
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | awk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s, removed lines: %s, total lines: %s
", add, subs, loc }' - # on Mac OSX
```

## Revert: 머지 복구하기
```sh
git revert -m 1 <commit-ish>
```

## 특정 브랜치의 커밋 수 출력하기
```sh
git rev-list --count <branch-name>
```

## 별칭: git undo
```sh
git config --global alias.undo '!f() { git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; }; f'
```

## 오브젝트에 노트(메모) 추가하기
```sh
git notes add -m 'Note on the previous commit....'
```

## 모든 깃 노트 보기
```sh
git log --show-notes='*'
```

## 다른 저장소에 있는 커밋 적용하기
```sh
git --git-dir=<source-dir>/.git format-patch -k -1 --stdout <SHA1> | git am -3 -k
```

## 페치 레퍼런스 지정하기
```sh
git fetch origin master:refs/remotes/origin/mymaster
```

## 두 브랜치의 공통 조상 커밋 찾기
```sh
diff -u <(git rev-list --first-parent BranchA) <(git rev-list --first-parent BranchB) | sed -ne 's/^ //p' | head -1
```

## 푸시되지 않은 커밋들 나열하기
```sh
git log --branches --not --remotes
```


__다른 방법:__
```sh
git log @{u}..
```


```sh
git cherry -v
```

## 공백 변경사항을 제외한 모든 변경사항 추가하기
```sh
git diff --ignore-all-space | git apply --cached
```

## 깃 설정 [로컬/글로벌] 수정하기
```sh
git config [--global] --edit
```

## 특정 구간에서 blame 정보 보기
```sh
git blame -L <start>,<end>
```

## Git의 논리적 변수 보기
```sh
git var -l | <variable>
```

## 패치 파일 미리 포맷팅하기
```sh
git format-patch -M upstream..topic
```

## 저장소명 가져오기
```sh
git rev-parse --show-toplevel
```

## 특정 날짜 구간 사이의 커밋 로그 출력하기
```sh
git log --since='FEB 1 2017' --until='FEB 14 2017'
```

## 로그에서 author 제외하기
```sh
git log --perl-regexp --author='^((?!excluded-author-regex).*)

```

## 브랜치의 수정사항 요약하기
```sh
git request-pull v1.0 https://git.ko.xz/project master:for-linus
```

## 원격 저장소의 모든 레퍼런스 나열하기
```sh
git ls-remote git://git.kernel.org/pub/scm/git/git.git
```

## 트래킹되지 않은 파일들 백업하기
```sh
git ls-files --others -i --exclude-standard | xargs zip untracked.zip
```

## 모든 git 명령어 별칭 나열하기
```sh
git config -l | grep alias | sed 's/^alias\.//g'
```


__다른 방법:__
```sh
git config -l | grep alias | cut -d '.' -f 2
```

## git 상태 간략하게 보기
```sh
git status --short --branch
```

## 하루 전의 커밋으로 체크아웃하기
```sh
git checkout master@{yesterday}
```
