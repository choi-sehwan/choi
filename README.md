
# README 문서입니다. 

## **Preprocess**

### 필요 라이브러리

* ***numpy*** - version : 1.17.2
* ***pandas*** - version : 0.23.4

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

4. Train set 생성시에는 **label을 추가로 import**

```python 
preprocessing('train', activity, combat, pledge, trade, payment, label) 
```

* Test set 생성시에는 **label=None**

```python 
preprocessing('train', activity, combat, pledge, trade, payment, None) 
```

***

## **Model**

### 필요 라이브러리

* ***numpy*** - version : 1.17.2
* ***pandas*** - version : 0.23.4
* ***xgboost*** - version : 0.80
* ***sklearn.datasets*** - version : 0.19.2
* ***pickle*** 

### 실행 순서

1. 필요 라이브러리 

2. preprocess에서 생성한 **train_preprocess_1.csv import**

(import 시 dataframe 이름은 ***train_preprocess_1로 생성***)

3. 이후 순차적으로 각 cell을 실행  
( ***survival_binary64***, ***survival_binary4***, ***survival_time***, ***amount_binary1***, ***amount_spent*** )

4. 각 cell을 다 실행하면 model 폴더에 save 모델이 생성됨. 

***

## **Predict**

### 필요 라이브러리

* ***numpy*** - version : 1.17.2
* ***pandas*** - version : 0.23.4
* ***xgboost*** - version : 0.80
* ***sklearn.datasets*** - version : 0.19.2
* ***pickle*** 

### 실행 순서

1. 필요 라이브러리 

2. save 파일을 불러오기 위해 **path**에 model 파일의 경로 입력
```python
path="D:\\jupyternotebook\\Bigcon\\bigcon\\지하세탁소\\model"
```


3. 최종 predict을 하기 위해 **train_label** 데이터 set이 필요 
```python
lab=pd.read_csv("D:\\jupyternotebook\\Bigcon\\bigcon\\지하세탁소    +   \\raw\\train_label.csv", engine=’python)
```

4. predict을 해야하는 test1과 test2를 ***test1*** 과 ***test2*** 로 import

5. 이후 각 cell을 순차적으로 진행 

6. 마지막 cell까지 실행하면 predict 폴더에 최종 예측 테이블 생성
* test1_predict_1
* test2_predict_1

***
