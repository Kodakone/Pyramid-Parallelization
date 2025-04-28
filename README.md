# Pyramid-Parallelization


 ResNeXt의 Split-Transform-Merge 기법의 개념을 활용. 
이에 응용한 기법인 Pyramid-Parallelization 고안, 딥러닝 모델에 대한 더 깊은 Layer를 구성할 수 있음.


![image](https://github.com/user-attachments/assets/d0028f76-2be0-4808-86d6-65e501f63452)

기존의 VoxelNet 기반 모델 구조 중 3D SparseConv 단계에 STM(Split-Transform-Merge) 기법, Pyramid-Parallelization 기법 적용해 보았음.
이는 기존 모델에 비해 더 깊은 구조를 적용하여 더 좋은 성능을 보임.

Pyramid 병렬은 ResNeXt 논문 아이디어와 같이 병렬 배치 그룹을 더 많이 나눌수록 성능이 더 좋아지게 되나, 적절한 채널 수를 설정해야 함.


## 3D Sparse Convolution layers

![image](https://github.com/user-attachments/assets/92b37c40-77e7-4b59-9f7f-cfb8b51c2f2b)

![image](https://github.com/user-attachments/assets/a4de8f84-8728-4431-b1a3-2c12acf793d0)

일반적인 3D Sparse Convolution Layer, Sparse Basic Block 내부 상황


![image](https://github.com/user-attachments/assets/c1584a6e-b98b-4bd4-9889-fa928aaf6036)

3D Convolution Layer에 STM(Split-Transform-Merge) 기법 적용 시


![image](https://github.com/user-attachments/assets/e20f8185-e1ea-4df9-aea0-25d472654b11)

3D Convolution Layer에 Pyramid-Parallelization 기법 적용 시



## Result 

![image](https://github.com/user-attachments/assets/bd5b9684-82dc-4645-bfa6-c2168b1437b6)

Kitti Dataset SECOND Model AP(Average Precision)

![image](https://github.com/user-attachments/assets/3e52a4b0-8885-41cb-a042-dc49cc3edc7f)

Kitti Dataset PV-RCNN Model AP

![image](https://github.com/user-attachments/assets/ff1af6d0-9a57-4c0e-824c-6be230ab8427)

Once Dataset SECOND Model AP


SECOND 모델에서 Pyramid 기법이 대체로 높은 성능.
