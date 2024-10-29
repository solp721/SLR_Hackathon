<div align="center">
    
![로고](https://raw.githubusercontent.com/UbSE-lab/class-review-site-server/refs/heads/main/images/Logo_Blue2.png)

</div>

---

[👉 사이트 보러가기](https://slr-phi.vercel.app/)

---

## **SLR**
> SLR(Sharing Lecture Review)은 수도권에 대학들이 집중됨에 따라 부산 지역에서 발생하는 위기감을 해결하기 위해 개발된 플랫폼입니다.  
> SLR은 부산 지역 대학생들이 타 대학의 강의 정보를 쉽게 접근할 수 있도록 하며 부산 지역 혁신사업과 융합해 학생들의 학문적 교류 활성화를 목표로 합니다.

---

### **History**
- 2024년 AI SW 동서대학교 창업동아리 (2024.04 - 2024.11) [Ver 1.0 : 진행 과정](https://github.com/amazon7737/class_review_site)
- 제9회 부산 ICT 융합 해커톤 대회 본선 (2024.07.04 - 2024.07.05) [Ver 2.0 : 진행 과정](https://github.com/solp721/SLR_Hackathon/tree/main/2024_busan_ict_hackathon)
- 제11회 대한민국 SW 융합 해커톤 대회 본선 (2024.08.23 - 2024.08.25) [Ver 3.0 : 진행 과정](https://github.com/solp721/SLR_Hackathon/tree/main/2024_korea_sw_hackathon)
- 2024 K-ICT WEEK in BUSAN 전시회 출품 (2024.09.10 - 2024.09.12)
- 2024 부산 잡페어 출품 예정
- 2024 동서대학교 Show Me The Dongseo 출품 예정

---

### **Skills**
* Next.js (Page Router)
* JavaScript
* Zustand
* Axios
* Styled-Components
* Vercel

---

### **System Architecture**

![architecture](https://github.com/user-attachments/assets/0e5ffb83-0046-41a0-9feb-7139200d9389)

---

## **주요 이슈 사항 및 해결 방법**

### **리뷰 욕설 탐지 필터링 서버와의 통신 지연 문제**

- **문제**:  
  댓글을 메인 서버에 전송하기 전에 거치는 욕설 필터링 서버에서 **평균 8초 이상의 통신 지연**이 발생하여 사용자 경험이 저하되었습니다.  
  통신이 실패하면 **리뷰가 유실되거나 UI가 멈추는 문제**도 발생했습니다.

- **해결 방법**:  
  - **클라이언트 측 1차 필터링 도입**: 명백한 욕설을 감지하기 위해 **클라이언트에 욕설 리스트를 구축**하고, 작성된 댓글을 리스트와 비교해 1초 내에 **즉시 차단**했습니다.  
  - **비동기 처리 및 로딩 스피너 사용**: 서버와의 통신 지연 시에도 **UI가 멈추지 않도록** 비동기 처리와 로딩 스피너를 적용했습니다.  
  - **AI 서버 호출 최적화**: 클라이언트의 리스트에 걸리지 않는 경우에만 **AI 필터링 서버를 호출**하도록 설계해 **불필요한 서버 요청을 줄이고 성능을 개선**했습니다.
