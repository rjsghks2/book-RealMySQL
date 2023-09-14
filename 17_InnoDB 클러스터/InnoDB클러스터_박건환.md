### InnoDB 클러스터 요구사항

> InnoDB 클러스터 요구사항은 다음과 같음.

- MySOL 서버 5.7.17 이상   
- MySQL 셀 1.0.8 이상  
- MySOL 라우터 2.1.2 이상   
- Performance 스키마 활성화  
- Python 2.7 버전 이상

## 17.5 InnoDB 클러스터 생성

- InnoDB 클러스터 구축 순서는 다음과 같다.  
> MySQL Shell 에서 dba.configureInstance() 메서드 실행하여 서버 설정 및 계정 생성  
> dba.createCluster() 메서드 실행하여 클러스터 생성(그룹 복제 설정, 그룹 복제 분산 복구에 사용되는 DB계정 생성)  
> addlnstance() 메서드를 통해 InnoDB 클러스터 인스턴스 추가
> MySQL 라우터 설정
> describe() 메서드를 통해 모니터링

## 17.7 클러스터 작업

- (Cluster).switchToMultiPrimaryMode()
> 클러스터를 멀티 프라이머리 모드로 전환하는 명령어

- (Cluster).switchToSinglePrimaryMode([instance])
> 클러스터를 싱글 프라이머리 모드로 전환하는 명령어

- (Cluster).setPrimarylnstance(instance)
> 인자로 주어진 서버를 클러스터의 새로운 프라이머리 서버로 설정하는 명령어

- Cluster).removeinstance(instance)
> 인자로 지정된 서버를 클러스터에서 제거하는 명령어

- (Cluster).dissolve()
> 메서드를 실행할 때 클러스터와 관련된 모든 메타데이터 및 설정, 계정을 삭제하고 그룹 복제를 중단하는 명령어

- (Cluster).options()
> 클러스터의 각 서버의 설정 정보를 JSON 포맷으로 출력

- (Cluster).setOption (option,value)
> 클러스터의 모든 인스턴스에 대해 설정을 변경하거나, ClusterName과 같이 클러스터 단위의 설정을 변경

- (Cluster).setlnstanceOption (instance ,option ,value)
> 클러스터 인스턴스별로 설정을 변경하는 명령어

Q. MySQL에서 키 값이 언더스코어(_)로 시작하는 태그는 어떤 태그인가?
> 빌트인된 태그로, MySQL 라우터의 동작에 영향을 준다. _hidden ,  _disconnect_existing_sessions_when_hidden 태그가 있다.


