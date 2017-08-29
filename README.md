# tutorial-python-build
[![Build Status](https://travis-ci.org/pincoin/tutorial-python-build.svg?branch=master)](https://travis-ci.org/pincoin/tutorial-python-build)
[![codecov](https://codecov.io/gh/pincoin/tutorial-python-build/branch/master/graph/badge.svg)](https://codecov.io/gh/pincoin/tutorial-python-build)

## setuptools
* [setup.py](setup.py)

## tox
`tox-quickstart` 명령어로 `tox.ini` 파일을 만들 수 있다. 가장 간단한 `tox.ini` 파일은 다음과 같다:

```
[tox]
envlist = py27, py34, py35, py36

[testenv]
commands = coverage run -m unittest discover
deps =
    coverage
```

`[tox]` 섹션의 `envlist` 변수는 테스트하려는 파이썬 버전을 나열한다. 위 예시에서는 2.7, 3.4, 3.5, 3.6 버전으로 테스트할 것이다.

`[testenv]` 섹션의 `commands` 변수는 테스트를 실행하는 명령어의 예시는 다음과 같다.

* `coverage run -m unittest discover`
* `coverage run -a setup.py test`
* `python setup.py test`
* `pytest`
* `nosetests package.module`
* `trial package.module`

`[testenv]` 섹션의 `deps` 변수로 테스트 실행을 위해 의존성 설치해야 하는 패키지를 나열할 수 있다.

위 예시에서는 `coverage` 유틸리티를 이용해 테스트를 실행하기로 했으므로 `coverage` 패키지를 임시 설치하여 테스트 진행한다.

## coverage
커버리지 검사

```
coverage run -m unittest discover
```

커버리지 보고서 확인
```
coverage report -m
```

# 실행 방법
## 테스트 실행 방법
파이썬 인터프리터로 직접 실행하는 방법

```
python -m unittest discover
```

setuptools 유틸리티로 호출하는 방법

```
python setup.py test
```

coverage 유틸리티로 호출하는 방법

```
coverage run -m unittest discover
```

tox 유틸리티로 호출하는 방법

```
tox
```

## 패키지 빌드
다음 명령어로 패키지를 빌드하면 `dist/tutorial-python-build-0.1.tar.gz` 파일이 생성된다.
```
python setup.py sdist
```

## 패키지 설치
setuptools 유틸리티로 소스 디렉토리에서 수동 설치

```
python setup.py install -f
```

pip으로 소스 디렉토리에서 수동 설치

```
pip install .

```

pip으로 빌드 패키지로 설치

```
pip install tutorial-python-build-0.1.tar.gz
```
