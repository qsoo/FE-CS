## CI/CD

🌱: 이해 못 한 부분

<br>

**학습 목표: 지속적 통합과 지속적 배포의 개념에 대해 이해하고 차이점을 안다**

<br>

### 요약

<br>

![ci-cd.png](CI_CD.assets/ci_cd.png)

<center><a href="https://aws.amazon.com/ko/devops/continuous-integration/">CI/CD process</a></center>

- 지속적인 통합, 배포, 제공은 하나의 파이프라인에 속한 세 단계

<br>

### CI, Continuous Integration(지속적 통합)

<br>

자동화된 **빌드 및 테스트**가 수행된 후 개발자가 코드 변경 사항을 중앙 레포지토리에 정기적으로 병합하는 소프트웨어 개발 방식

#### 왜 필요한가

- `Integration hell` 방지
  - Integration hell: 개발 구성원들이 개발하는데보다 통합하는 과정에서 많은 시간과 비용이 소모되는 현상
- 개발팀과 운영팀 간의 커뮤니케이션 원활
- (테스트를 통과한 코드만 병합되니) 일정한 퀄리티의 코드 품질 확보 가능

<br>

### CD, Continuous Delivery(지속적 제공)/ Deployment(지속적 배포)

<br>

#### Continuous Delivery, 지속적 제공

CI의 빌드 자동화, 유닛 및 통합 테스트 수행 후 유효한 코드를 레포지토리에 자동으로 릴리즈

목표: **프로덕션 환경으로 배포할 준비**가 되어 있는 코드베이스를 확보

<br>

#### Contunuous Deployment, 지속적 배포

애플리케이션을 프로덕션으로 릴리즈하는 작업의 자동화

<br>

### CI/CI tools

- Jenkins
- Circle CI
- Travis CI

<br>

#### 참고 자료

[Red Hat, CI/CD(지속적 통합/지속적 제공): 개념, 방법, 장점, 구현 과정](https://www.redhat.com/ko/topics/devops/what-is-ci-cd)

[AWS, 지속적 통합이란 무엇입니까?](https://aws.amazon.com/ko/devops/continuous-integration/)

[ATLASSIAN, What is Continuous Integration?](https://www.atlassian.com/continuous-delivery/continuous-integration)

