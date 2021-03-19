## 1. VPC , 서버용 Subnet, Kubernetes 용 Subnet 생성
### Product and Service -> Networking -> VPC 선택
 - VPC 이름 : lab-vpc
 - IP 주소 범위 : 10.0.0.0/16
### Product and Service -> VPC -> Network ACL 생성 선택
 - Network ACL 이름 : lab1-vpc-web-nacl 
 - VPC : lab-vpc 선택 후 생성 클릭

### lab1-vpc-web-nacl 선택 후 상단 'Rule 설정' 클릭

#### inbound 규칙 설정

우선순위 | 프로토콜 | 접근소스 | 포트 | 허용여부 
---- | ---- | ---- | ---- | ---- 
0 | ICMP | 0.0.0.0/0 | | 허용 
1 | TCP | 0.0.0.0/0 | 80 | 허용
2 | TCP | myIP | 22 | 허용
197 | TCP | 0.0.0.0/0 | 22 | 차단
