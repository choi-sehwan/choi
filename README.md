
# README 문서입니다. 

## **Preprocess**

### 필요 라이브러리

* numpy - version : 1.17.2
  
* pandas - version : 0.23.4

### 실행 순서

1. 필요 라이브러리 

2. ***def preprocessing*** 을 실행하여 함수 생성. 총 6가지 입력 값이 필요.
 * name : preprocess 과정을 거친 내보낼 데이터 셋에 이름 ex) ’train’
 * act : activity table dataframe 형태
 * com : combat table dataframe 형태
 * ple : pledge table dataframe 형태
 * tra : trade table dataframe 형태
 * pay : payment table dataframe 형태
 * lab : label table dataframe 형태 / **Test set** 을 생성하는 경우 반드시 **lab=None** 지정
 
3. 필수 데이터 import(***combat***, ***activity***, ***pledge***, ***trade***, ***payment***)

