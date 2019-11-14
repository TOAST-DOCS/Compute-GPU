## GPU Instance 활성화

GPU Instance를 사용하기 위해서는 먼저 Compute > GPU Instance 생성요청을 해야 합니다.

### 서비스 선택 > GPU Instance 를 클릭합니다.

![GPU_Instance_activation_1_modify.png](http://static.toastoven.net/prod_gpu/GPU_Instance_activation_1_modify.png)  

### 서비스 활성화 확인버튼을 클릭합니다.

![GPU_Instance_activation_2_modify.png](http://static.toastoven.net/prod_gpu/GPU_Instance_activation_2_modify.png)



## GPU Instance 생성 요청

### Compute > GPU Instance 으로 이동한 뒤, 신청(1:1문의) 버튼을 클릭합니다.

![GPU_Instance_apply_1_modify.png](http://static.toastoven.net/prod_gpu/GPU_Instance_apply_1_modify.png)


### 문의 제목과 문의 내용을 작성한후 확인 버튼을 클릭합니다.

GPU Instance는 2가지 사양으로 제공됩니다.

* g2.c8m96 + GPU 1개
    * vCPU 8개, 메모리 96GB, GPU 1개
* g2.c16m192 + GPU 2개
    * vCPU 16개, 메모리 192GB, GPU 2개

![GPU_Instance_apply_2_modify.png](http://static.toastoven.net/prod_gpu/GPU_Instance_apply_2_modify.png)





## GPU Instance 접속

인스턴스 생성 완료 후 SSH를 사용하여 인스턴스에 접근합니다.
인스턴스에 Floating IP가 연결되어있어야 하며 보안그룹에서 TCP 포트 22(SSH)가 허용되어야 합니다.

SSH 클라이언트와 설정한 키페어를 이용해 인스턴스에 접속 합니다. 
SSH 연결에 대한 자세한 가이드는 [SSH 연결 가이드](https://docs.toast.com/ko/Compute/Instance/ko/overview/#linux)를 참고하시기 바랍니다.



## GPU 정보 확인 방법

```
# GPU 정보 확인
shell > nvidia-smi
```

![GPU_assign_1.png](http://static.toastoven.net/prod_gpu/GPU_assign_1.png)

* GPU 0 할당 : 1개
* Name : Tesla T4
* Persistence_mode : On
* Temp : 44C
* Pwr Usage/Capacity : 28W / 70W
* Memory-Usage : 15079MiB
* GPU-Util : 0%
