# Deep Learning Generative AI Project  
[Sk-Planet T academy 빅데이터 분석가 5기]
 

<h3>📌 Topic</h3>
<h3>생성모델을 활용한 사진 스타일 전이</h3>
✅ 생성형 AI 모델 중 현재 가장 활발히 사용되는 **stable diffusion model**을 활용하여 **음식의 배경이미지를 원하는 작가의 스타일 풍으로 변환해주는 프로젝트**

<img alt="image_main" src="https://github.com/2-sehee/ASAC_5th_DL_Project/assets/174074112/0287511b-e0b5-4a45-bac4-726d2647fc5e"/>

--------------------------------------
### 📌진행 과정
- 사용 모델: stable diffusion pix2pix
- 재학습 이유 : 기존 모델은 음식 사진으로 학습된 모델이 아니었기에 음식에 대한 detection이 제대로 이루어지지 않음. 배경을 변환해달라는 프롬프트가 제대로 반영되지 못하고 객체까지 변경되는 문제 발생
    <br>-> 음식 사진 데이터 셋으로 재학습 
  
- 모델의 데이터셋 구조에 맞추어 새로운 데이터셋 구축 
  - 총 2255개의 학습 데이터셋 구성(hugging face 업로드🤗)
            
            | input_image | edit_prompt | edited_image |
            | 수집한 작가의 음식 사진 | 작가이름+사진을 묘사하는 텍스트 | 작가 스타일 사진 |

    * 사진을 묘사하는 텍스트는 openAI api를 이용하여 생성
    * hugging face 업로드 데이터셋 예시 🤗
      ![데이터셋 예시5 (허깅페이스)](https://github.com/user-attachments/assets/001fc3ff-ffcd-4d06-b571-c791f1830211)

- 모델 재학습 : epoch 500, 1000, 1500, 2000, 2500 등으로 진행

--------------------------------------

### 🙋🏻 Members
<table>
  <tbody>
    <tr>
      <td align="center"><a href="https://github.com/heesunTUKorea">
          <img src="https://github.com/user-attachments/assets/2b574210-e820-47de-b93b-c6ccb47bf1d1" height="100px;" alt=""/><br /><sub><b>양희선</b></sub></a><br />데이터 전처리, 모델링</td>
      <td align="center"><a href="https://github.com/yeomsta">
          <img src="https://github.com/user-attachments/assets/59023b59-96a4-436a-8051-e387346f4cb7" height="100px;" alt=""/><br /><sub><b>염혜지</b></sub></a><br />프로젝트 매니징, 데이터 수집</td>
      <td align="center"><a href="https://github.com/2-sehee">
          <img src="https://github.com/user-attachments/assets/c2fb72f2-fe3f-4537-97a0-d1dfccaa4904" height="100px;" alt=""/><br /><sub><b>이세희</b></sub></a><br />프롬프트 엔지니어링, 모델링</td>
      <tr/>
      <td align="center"><a href="https://github.com/seolhada">
          <img src="https://github.com/user-attachments/assets/8c328aec-ec66-4206-805e-04eb11721c12" height="100px;" alt=""/><br /><sub><b>이설하</b></sub></a><br />데이터 수집, 데이터 전처리</td>
      <td align="center"><a href="https://github.com/oh-bom">
          <img src="https://github.com/user-attachments/assets/99bc3c31-9791-406b-a8b0-37b3591f82bd" height="100px;" alt=""/><br /><sub><b>임혜원</b></sub></a><br />데이터 셋 구축, 프롬프트 엔지니어링</td>
      <td align="center"><a href="https://github.com/LeekyeongChoi">
          <img src="https://github.com/user-attachments/assets/0b09f7f2-bf81-4725-8816-748713cd5760" height="100px;" alt=""/><br /><sub><b>최이경</b></sub></a><br />데이터 수집, 모델링</td>
    </tr>
  </tbody>
</table>
