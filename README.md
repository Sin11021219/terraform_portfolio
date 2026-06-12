<img width="952" height="606" alt="Terraform_構成図 drawio" src="https://github.com/user-attachments/assets/575f4323-f2e7-49a2-b156-1a20db2dee9a" />


### 構成の概要
Udemyの演習を通じてTerraformによる実践的なIaCを習得し、その成果としてCloudFront、ALB、EC2、RDSを組み合わせた高可用性なWeb3層アーキテクチャを構築

### 工夫した点
・パブリックサブネットにALB、プライベートサブネットにEC2とRDSを配置する強固な3層ネットワーク構造を採用し、不要なパブリックアクセスを遮断

・踏み台サーバーを廃止し、AWS Systems Manager Session Manager経由でのみ安全にEC2へアクセスできる運用にすることで、運用コストとセキュリティリスクを削減

### 苦労した点
・厳密なセキュリティグループの制御:ネットワーク分離に伴い、ALB ➔ EC2 ➔ RDS 間の通信フローを必要最低限のポートとソースに絞る必要があり、コード上でのセキュリティグループの依存関係の整理
