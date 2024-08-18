#### [Sk-Planet T academy 빅데이터 분석가 5기] 
## Deep Learning Generative AI Project


### 📌 Topic
#### 생성모델을 활용한 사진 스타일 전이
✅ 생성형 AI 모델 중 현재 가장 활발히 사용되는 <b>stable diffusion model</b>을 활용하여 <br/> 음식의 배경이미지를 <b>원하는 작가의 스타일 풍으로 변환</b>해주는 프로젝트
<img alt="image_main" width="800px;" src="https://github.com/2-sehee/ASAC_5th_DL_Project/assets/174074112/0287511b-e0b5-4a45-bac4-726d2647fc5e"/>

#### 📷 결과 예시
<table>
 <tbody>
  <tr>
   <td align="center" width="600px"/>
    <b>결과 예시 1. 배달의 민족</b>
   </td>
   <td align="center" width="600px" />
    <b>결과 예시 2. 쿠팡이츠</b>
   </td>
  </tr>
   <td align="center" />
    <img src="https://github.com/user-attachments/assets/805cd5ea-b6df-4466-b0eb-edb4656f33e2"/>
   </td>
   <td align="center" />
    <img src="https://github.com/user-attachments/assets/2995c57f-82a4-4c96-8e78-39931e22faf3"/>
   </td>
  </tr>
 </tbody>
</table>

<br/>

### 📌 기획 의도
<table>
 <tbody>
  <tr>
   <td align="center" width="400px"/>
    1. "음식 맛은 미각보다 시각이 먼저 판단한다"
   </td>
   <td align="center" width="600px" />
    2. "메뉴 이미지는 가게를 결정하는 중요요소"
   </td>
  </tr>
   <td align="center" />
    <img src="https://github.com/user-attachments/assets/45771837-71d8-4ad9-9530-7e57733543b5"/>
   </td>
   <td align="center" />
    <img src="https://github.com/user-attachments/assets/433c0320-4914-41c4-b19a-5b6c8334dded"/>
   </td>
  </tr>
 </tbody>
</table>

###### 출처 1 | https://biz.chosun.com/site/data/html_dir/2014/07/06/2014070602531.html
###### 출처 2 | https://ceo.baemin.com/guide/10369

<br/>

> ### 💡 Ideation
> #### 평범한 사진을 푸드 포토그래퍼의 사진처럼 바꾸면 어떨까?

<br/>
<hr/>
<br/>

### 📌 데이터 수집
- 사진 작가 이미지 (학습 대상) 
  * 사진 작가 19명, 총 451장의 이미지 수집
  
- 평범한 사진 이미지 (변환 대상)
  * 조원 6명, 총 421장의 이미지 수집
    <img alt="image_content" width="800px;" src="https://github.com/user-attachments/assets/317bd5a6-e9de-473b-a440-ab4caf7a6dd3"/>

<br/>

### 📌 진행 과정
- 사용 모델: stable diffusion pix2pix
- 재학습 이유 : 기존 모델은 음식 사진으로 학습된 모델이 아니었기에 음식에 대한 detection이 제대로 이루어지지 않음. <br/>배경을 변환해달라는 프롬프트가 제대로 반영되지 못하고 객체까지 변경되는 문제 발생
    <br> → 음식 사진 데이터 셋으로 재학습 
  
- 모델의 데이터셋 구조에 맞추어 새로운 데이터셋 구축 
  - 총 2255개의 학습 데이터셋 구성(hugging face 업로드🤗)
            
            | input_image | edit_prompt | edited_image |
            | 수집한 작가의 음식 사진 | 작가이름+사진을 묘사하는 텍스트 | 작가 스타일 사진 |

    * 사진을 묘사하는 텍스트는 openAI api를 이용하여 생성
    * hugging face 업로드 데이터셋 예시 🤗
      <img alt="image_huggingface" width="800px;" src="https://github.com/user-attachments/assets/001fc3ff-ffcd-4d06-b571-c791f1830211"/>


- 모델 재학습 : epoch 500, 1000, 1500, 2000, 2500 등으로 진행
  * 대용량 이미지 학습을 위해 Google Colab Pro+에서 A100 GPU 사용
    
<br/>
<hr/>
<br/>

### 📌 학습 결과
<img alt="image_result_changes" width="800px;" src="https://github.com/user-attachments/assets/76eae5de-5ab5-4623-bf35-b0cfd8730f5a"/>

<br/>
<br/>


### ✅ 최종 선정 모델 → Stable Diffusion Pix2Pix, epoch=2000
<img alt="image_result_final" width="800px;" src="https://github.com/user-attachments/assets/5d4316ed-33ed-467e-b4c7-a6db0988df57"/>

#### ➕ 최종 모델 결과 예시
<img alt="image_result_final2" width="800px;" src="https://github.com/user-attachments/assets/b6967815-df47-477a-8de5-e2a676c0952a"/>



<br/>
<hr/>
<br/>

### 🙋🏻 Members
<table>
  <tbody>
    <tr>
      <td align="center" width="250px;"><a href="https://github.com/heesunTUKorea">
          <img src="https://github.com/user-attachments/assets/2b574210-e820-47de-b93b-c6ccb47bf1d1" height="100px;" alt=""/><br /><sub><b>양희선</b></sub></a><br />
       - 모델 논문 리뷰<br/>
       - 데이터 전처리<br/>
       - 모델링<br/>
      </td>
      <td align="center" width="250px;"><a href="https://github.com/yeomsta">
          <img src="https://github.com/user-attachments/assets/59023b59-96a4-436a-8051-e387346f4cb7" height="100px;" alt=""/><br /><sub><b>염혜지</b></sub></a><br />
       - 프로젝트 매니징<br/>
       - 앱 데모 구성<br/>
       - 데이터 수집<br/>
      </td>
      <td align="center" width="250px;"><a href="https://github.com/2-sehee">
          <img src="https://github.com/user-attachments/assets/c2fb72f2-fe3f-4537-97a0-d1dfccaa4904" height="100px;" alt=""/><br /><sub><b>이세희</b></sub></a><br />
       - 실제 비즈니스에 적용<br/>
       - 프롬프트 엔지니어링<br/>
       - 모델링<br/>
      </td>
      <tr/>
      <td align="center" width="250px;"><a href="https://github.com/seolhada">
          <img src="https://github.com/user-attachments/assets/8c328aec-ec66-4206-805e-04eb11721c12" height="100px;" alt=""/><br /><sub><b>이설하</b></sub></a><br />
       - 데이터 수집<br/>
       - 데이터 전처리<br/>
      </td>
      <td align="center" width="250px;"><a href="https://github.com/oh-bom">
          <img src="https://github.com/user-attachments/assets/99bc3c31-9791-406b-a8b0-37b3591f82bd" height="100px;" alt=""/><br /><sub><b>임혜원</b></sub></a><br />
       - 모델 서칭<br/>
       - 데이터 셋 구축<br/> 
       - 프롬프트 엔지니어링<br/>
      </td>
      <td align="center" width="250px;"><a href="https://github.com/LeekyeongChoi">
          <img src="https://github.com/user-attachments/assets/0b09f7f2-bf81-4725-8816-748713cd5760" height="100px;" alt=""/><br /><sub><b>최이경</b></sub></a><br />
       - 데이터 수집<br/>
       - 모델링<br/>
      </td>
    </tr>
  </tbody>
</table>


<br/>
<hr/>
<br/>

### 🛠️ Languages and Libraries

<div>
 <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
 <img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" />
 <img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white" />
 <img src="https://img.shields.io/badge/Selenium-43B02A?style=flat-square&logo=selenium&logoColor=white" />
 <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" />
 <img src="https://img.shields.io/badge/Remove.bg-54616C?style=flat-square&logo=removedotbg&logoColor=white" />
</div>

