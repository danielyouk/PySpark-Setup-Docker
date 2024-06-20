# 데이터 전문가를 위한 실용적인 도커: 머신러닝을 위한 케글 수준의 분석 환경 구축 

## Goals
- 우리는 Hello World 프로젝트가 아닌 데이터 전문가에게 필요한 실제적이고 실용적인 지식에 초점을 맞춥니다. 
- 우리의 목표는 모든 도커 명령어를 외우는 것이 아닙니다. 대신 10개 정도의 핵심 도커 명령어를 깊이 있게 이해하고, 실제 환경에서 어떻게 활용하는지에 중점을 둡니다. 고기를 잡아 주는 것보다 고기 잡는 방법을 가르치는 것이 더 중요합니다.
- 데이터 전문가로서 필요한 클라우드에 대한 실제적인 기반을 다집니다. 


## Pre-Requisites
- 로컬 환경에 Visual Studio Code 설치를 부탁 드립니다. (추가 설치 Extention: vscode-pdf, Draw.io Integration)
- 깃허브 가입 (깃에 대한 지식 불필요. 가입만 요청 드립니다.)
- 파이썬, R 등의 경험이 있으면 도움이 되지만 꼭 필요한 것은 아닙니다. 


## Projects
- 클라우드에서 도커를 사용한 케글 수준의 분석 환경 구축 (Ubuntu Image, VSCode for Python, RStudio Sever for R)
- 클라우드와 로컬 환경의 연결
- (Optional) 윈도우즈 로컬 환경에서 도커를 사용한 케글 수준의 분석 환경 구축 (nvidia gpu)

## TechSkills You will get
- Docker 설치 (Windows, Linux, MAC)와 GPU 셋팅
- 다양한 도커 커맨드
- 다양한 리눅스 커맨드
- 클라우드 서비스 (Azure, AWS), 가상머신

## Requests from the Instructor
- 일방적인 수업이 아닌 양방향의 수업을 지향합니다. 게시판에서 질문을 적극적으로 활용하세요. (이해가 되실 때까지 지속적으로 질문을 던지시는 것이 중요합니다. 업무일 기준 2~3일 내에 답변을 드릴 수 있도록 최선을 다하겠습니다.)
- 다만, 질문이 이해될 수 있도록 (상식 수준에서), 다듬어 주세요.
- 게시판 공개가 어려운 경우에 메일로 연락주시길 요청 드립니다. (daniel@datatrain.education) 
- 수업을 빠르게 한 번 쭉 들으신 후에, 한 번 더 학습하실 것을 권장드립니다.   

## Steps  
### [Module 00 - 프로젝트의 소개](./CourseOverview.drawio)
### [Module 01 - 문제의 정의](./)
- 데브옵스 (DevOps: Dev + Ops)
- 서버관리

### [Module 02 - 도커의 세가지 주요 목표와 WORKFLOW](./Presentation/DockerArchitecture/DOCKER%20ARCHITECTURE%20OVERVIEW.pdf)
    . Portability (이동성): docker pull
    . Reproducibility (재현성): docker build
    . Containerization (가상화): docker run
- Dockefile (붕어빵 틀 설계도) ➡️ Image (붕어빵 틀) ➡️ Container (붕어빵) [링크](./Presentation/DockerArchitecture/붕어빵.pdf)
### Module 03 - 도커 설치 가이드
- [Windows 10 & 11](https://docs.docker.com/desktop/install/windows-install/)
  - Windows Powershell 관리자 계정 실행 --> wsl --install
  - Docker Desktop for Windows 다운로드 이후 설치  
- [Linux, Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- 클라우드 실습: [MAC](https://1drv.ms/w/s!AoSkNRaAbRTkiItYKP0_DGQSK2J6Cw?e=FSSmyZ) (in AWS) 
  - 무조건 dedicated host ip를 사용해야 함. 
  - dedicated host ip는 최소 보유 시간이 24시간
  - MAC 가상 머신은 Spot Discount 사용 옵션 불가 (Spot Discount는 모듈 06에서 자세히 설명)
  - Windows/Linux 가상 머신 비용 (한 달 10 달러 내외) vs. asw MAC 가상 머신 비용 (생성하는 순간 최소 40 달러)

### [Module 04 - 도커 명령어를 익히기 위한 2가지 기본원리](./Presentation/DockerIsEasy/TwoStragegytolearnDockerCommand.pdf)
- docker --help & [cheat sheet](https://docs.docker.com/get-started/docker_cheatsheet.pdf) 
- LLM에게 질문하기

### Module 05 - 도커 가상화에 대한 이해
- [도커의 기원 (What is Docker?)](https://www.docker.com/resources/what-container/)  
  - Standard
  - Lightweight ➡️ do not require an OS per application
  - Secure    
  - Linux Native
- [도커와 가상머신](https://www.docker.com/blog/containers-and-vms-together/)
  - 가상머신은 OS를 컨테이너화
  - 도커는 Application을 컨테이너화
  - [윈도우즈와 맥에서 도커의 적용](https://docs.docker.com/desktop/install/mac-install/)
- 도커에 대한 오해와 정정  

### [Module 06 - Azure에서 Ubuntu 가상 머신 구축하기](./Presentation/VMSetting/Cloud%20VM%20GPU%20Setting.pdf) 
- [Installation Commands](./command/docker_installation.txt)
- 로컬 환경과 가상 머신의 연결 -1 
  - ssh (Secure Shell)을 이용한 터미널 방식의 연결
  - RDP (Remote Desktop Protocol)을 이용한 GUI 방식의 연결
    - [vm Setting](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli)
    - Windows 로컬 환경에서 연결
    - [로컬 환경이 Windows가 아닌 경우](./Presentation/VMSetting/Connect%20between%20Locan%20and%20VM.pdf) 
- Chrome 설치 
  - wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb  
  - sudo dpkg -i google-chrome-stable_current_amd64.deb  
  - sudo apt-get install -f

- [Visual Studio Code 설치](https://code.visualstudio.com/docs/setup/linux) 
  - Dev Container Extension 설치: both in vm and local
  - Remote Tunnel Extension 설치: both in vm and local

- 로컬 환경과 가상 머신의 연결 -2  
  - Remote Tunnel 방식을 이용한 연결  
    - Turn On Remote Tunnel Access... (vm): only once
    - Install as a service Run (vm): only once
    - sign in with github (vm): only once --> 가상머신 Rebooting
    - ssh connect to vm from local ➡️  always
    - Connect to Tunnel... (local) ➡️  always
    - sign in with github (local): ➡️  always
    - select the vm (local) ➡️ always   
  

### Module 07 - 파이썬을 위한 도커

- 베이스 이미지를 가져오기 위한 도커 명령어:  
    docker pull < python gpu base image name:tag >  

- [파이썬 도커 환경을 위한 도커 파일](./Kaggle-Python-GPU/DockerFile)
- 비주얼 스튜디오에서 파이썬 도커 환경 연결하기   
        1) Add Dev Container Configuration Files...  
        2) From 'Dockerfile'
- [추가 설정](./Kaggle-Python-GPU/devcontainer_example.json)

- Speed Benchmark  
  - Local Machine: Intel(R) Core(TM) i7-1070CF CPU 8 Cores, 16 GB Physical Memory, NVIDIA GeForce RTX 3070 GPU 
  - Virtual Machine: AMD EPYC 7V12 64-Core Processor, 28 GB Physical Memory, NVIDIA Tesla T4 GPU

| Model \ Type | CPU | GPU |
| -------- | -------- | -------- |
| Local Machine  |  2s 5ms/stepsec  | 2s 6ms/step |
| Virtual Machine  |  1s 3ms/step  |  1s 2ms/step | 

### [Module 07-02 - PySpark](https://spark.apache.org/examples.html)
- Lazy evaluation에 대한 개념을 꼭 설명하기
- Dataframe의 분할에 대한 개념도 꼭 설명하기



### Module 08 - R을 위한 도커
- 베이스 이미지를 가져오기 위한 도커 명령어:    
    docker pull < r gpu base image name:tag>  
- Kaggle-gpu 이미지로부터 생성된 R 컨테이너를 RStudio Server IDE 환경에서 실행시키기 위한 도커 명령어:   
    docker run -d -p 8787:8787 --gpus all -v "< local path >:< container path >" --name < container name > < image name > /bin/bash -c "rstudio-server start && tail -f /dev/null"  
    cf)  docker run -p 8888:8888 --gpus all -v "< local path >:< container path >" --name < container name > < image name >  
- Port에 대한 이해
- [CMD/ENTRYPOINT에 대한 이해](https://github.com/Kaggle/docker-rstats/blob/main/Dockerfile)
- [torch](https://blogs.rstudio.com/ai/posts/2020-09-29-introducing-torch-for-r/) gpu 버전 확인  
  library(torch)  
  torch_tensor(1, device = "cuda")  
- [Keras를 실행하기 위한 Python Backend의 이해](./Presentation/PythonBackend/HOW%20WORK%20KERAS%20in%20R.pdf)  
  - Python 설치 경로 확인
    - docker exec -it < container name > R   
      library(reticulate)  
      py_config()
    - in RStudio   
      library(reticulate)  
      py_config()  
  
- docker build
  - [실습구조](./makeBetterImage.drawio)
  - [최신 RStudio Server 설치](https://posit.co/download/rstudio-server/) (메모리 사용량 모니터링)  
  - [setup.R](./Kaggle-R-GPU/setup.R) (RStudio에서 접근 가능한 디렉토리에 python과 keras 설치) 
  - [R 도커 환경을 위한 도커 파일](./Kaggle-R-GPU/Dockerfile) 
  - Image 생성 docker build --build-arg <변수명>=<값> -t < image name> .

- docker push from LM
  - docker login  
  - docker tag your-image:version registry(username@dockerhub)/your-image:version
  - docker push yourusername/your-repository:version 

- docker pull from VM
  - docker pull yourusername/your-repository:version



### Module 09 - 개발 환경 내의 도커 VS 도커 내의 개발 환경
- [Visual Studio Code 방식과 RStudio 방식의 비교](./Presentation/ExternalContainer_InternalContainer/Inside%20VS%20Outside.pdf)

### [Module 10 - 원격 연결 마스터하기: VSCode vs. Jupyter Server vs. RStudio Server](./Presentation/ConnectWithoutRDP/CONNECT%20WITHOUT%20RDP.pdf)
- VSCode
- Jupyter Server
- RStudio

### [Module 11 - 파일 공유 시스템 설정](https://1drv.ms/w/s!AoSkNRaAbRTkiItGeimXLeA9hiOEzg?e=eeXFES)
- ADLS2 (Azure Data Lake Storage Generation 2) 생성
- ADLS2 Mount in Ubuntu (Linux)
- ADLS2 Mount 방식을 사용하는 이유 [Granual Access Control: 링크1](https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-access-control-model?wt.mc_id=searchAPI_azureportal_inproduct_rmskilling&sessionId=416f578211824749b3736e7d6ad23833) & [Certification for Access Control: 링크2](https://learn.microsoft.com/en-us/credentials/certifications/identity-and-access-administrator/?source=recommendations)  
- ADLS2 Mount in Windows
- Microsoft Azure Storage Explorer를 이용한 ADLS2 Access (Windows & Linux & MAC)
- ADLS2 Mount 방식과 Azure Storage Explorer 방식이 가지는 제한사항
- [파일 공유 시스템의 실용적인 설정](./CourseOverview_includingFileSharing.drawio)


### Module 11-2 - 도커 컨테이너에 s3 마운트하기
- [Link 1](https://www.nakivo.com/blog/mount-amazon-s3-as-a-drive-how-to-guide/)  
  - apt-get install -y awscli 
  - aws configure  
  - aws s3 sync s3://your-bucket-name /path/to/local/directory
  - aws s3 sync s3://aws-ml-bucket-daniel /workspaces/PySpark-Setup-Docker-240510/s3-bucket
  - aws s3 sync /workspaces/PySpark-Setup-Docker-240510/s3-bucket s3://aws-ml-bucket-daniel


<!-- - [blobfuse2 설치](https://learn.microsoft.com/en-us/azure/storage/blobs/blobfuse2-how-to-deploy?tabs=Ubuntu)
- [Mount](https://learn.microsoft.com/en-us/azure/storage/blobs/blobfuse2-how-to-deploy?tabs=Ubuntu#how-to-mount-a-blob-container)
- [config.yaml](./ADLS2Mount/blobfuse/config.yaml)
- get the container key information  
        curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash    
        az login az storage account keys list --account-name YOUR_STORAGE_ACCOUNT_NAME --resource-group YOUR_RESOURCE_GROUP_NAM   --> 
### [Module 12 - 공동 작업을 위한 Setting](https://1drv.ms/w/s!AoSkNRaAbRTkiItNB1fc_cs6N11i_g?e=khCIAD)
- 새 사용자 (팀원) Account 생성 by admin
- 접근 권한 부여 by admin  
  - gui 방식을 이용한 VM 접근
  - ssh 엑세스 키 생성
- Tunnel 방식을 통한 연결 by user
- 진정한 Virtualization 구현
- VM과 Blob Storage 접근 권한 재설정


### [Module 13 (Optional) - 윈도우즈에 GPU 환경 구성하기](./Presentation/LMSetting/Windows%20GPU.pdf)

- Docker Install in Windows
- Nvidia GPU driver Install in Windows 
  - [Theroy](https://www.google.com/search?q=nvidia+gpu+driver+install+wsl+The+CUDA+driver+installed+on+Windows+host+will+be+stubbed+inside+the+WSL+2+as+libcuda.so&newwindow=1&sca_esv=591711254&sxsrf=AM9HkKkJtM1gNvF5wvkJv8itArMjoo1QpQ%3A1702845460276&ei=FFx_ZZ-kENyH9u8P7MWq0Aw&ved=0ahUKEwif_pDWqZeDAxXcg_0HHeyiCsoQ4dUDCBA&uact=5&oq=nvidia+gpu+driver+install+wsl+The+CUDA+driver+installed+on+Windows+host+will+be+stubbed+inside+the+WSL+2+as+libcuda.so&gs_lp=Egxnd3Mtd2l6LXNlcnAidm52aWRpYSBncHUgZHJpdmVyIGluc3RhbGwgd3NsIFRoZSBDVURBIGRyaXZlciBpbnN0YWxsZWQgb24gV2luZG93cyBob3N0IHdpbGwgYmUgc3R1YmJlZCBpbnNpZGUgdGhlIFdTTCAyIGFzIGxpYmN1ZGEuc28yBRAhGKABMgUQIRigATIFECEYoAEyBRAhGKABMgUQIRigATIIECEYFhgeGB1I3A9QmQNYugVwAXgBkAEAmAGgAaABoAGqAQMwLjG4AQPIAQD4AQH4AQLCAgoQABhHGNYEGLAD4gMEGAAgQYgGAZAGCA&sclient=gws-wiz-serp)
  - [Download Link](https://www.nvidia.com/Download/index.aspx)
- Nvidia Container Toolkit Install in WSL2 
  - [Reference](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
  - [Scripts](./command/ContainerToolkit_installation_Windows.txt) 

### 스스로 공부해 볼 만한 주제들
- Kaggle 이미지로부터 가벼운 이미지 만들기 또는 패키지 추가하기 (클라우드 가격 정책의 이해)
- 주식 데이터 Web App 구현

### 디스커션 - Python vs. R    

