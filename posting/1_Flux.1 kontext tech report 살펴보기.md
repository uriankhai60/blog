![Flux Kontext 이미지](../images/flux_kontext_1.png)  
<sup>[1] Flux Kontext</sup>

## 무엇인가?  
1. 최근 이미지 딥러닝 모델을 가장 잘 만드는 연구소중 하나인 Black Forest Labs에서  
활용도가 매우 높은 모델을 발표하였다.  
모델의 이름은 `FLUX.1 Kontext`로 이미지 편집(edit) 전용모델이다.  
  
2. 이미지 생성(generation)과 이미지 편집(editing)과 차이.  
가장 먼저 input에서 차이가 있다.
이미지 생성은 주로 "프롬프트"만 입력으로 받는다.  
이미지 편집은 "레퍼런스 이미지", "프롬프트"를 입력으로 받는다.
  
3. Kontext 이전의 image edit.  
기존에는 이미지 생성모델(flux1.dev, Stable diffusion)등을 이용하여 이미지 편집을 하였다.  
(e.g) 레퍼런스 이미지의 특정 영역(mask)에 노이즈를 뿌리고 프롬프트를 먾어 새롭게 만들기.  
하지만 이와 같은 방식에는 큰 단점이 있다.  

4. 기존 생성모델을 이용한 이미지 편집의 단점과 Kontext의 장점.  
편집될 영역(mask)을 의식적으로 생각하여 명시적으로 지정한다는 것은 매우 어렵고 피곤한 일이다.  
실수로 해당 영역 지정을 놓치게 된다고 하면,  
이미지는 수정되었는데 기존 물체의 그림자가 남는것과 같이 기형적인 이미지가 생성된다.  
하지만 Kontext는 영역 지정이 아닌 프롬프트만을 받아 instruction을 수행하므로  
이미지 전체 영역에서 수정이 잘된다.  
쉽게 정리하면 아래 LaMa에서의 Failcase와는 다르게  
`remove couple from image`라는 프롬프트만으로도  
관련된 그림자와 명암을 전체적으로 조절하여 이미지를 편집한다.

![LaMA_edgecase](../images/flux_kontext_2.png)
<sup>[2] LaMa Failcase</sup>
  

4. 레포트에서는 이미지 편집(image edit)을 두가지로 나눠서 설명하고 있다.  
첫번째로는 레퍼런스 이미지의 특정 영역만을 수정하는 Local editing.  
두번째로는 레퍼런스 이미지의 컨셉을 유지한채로 새롭게 만드는 Generative editing.  
전자는 


## 실무에서 활용 방안  
1. 현업에서 이미지 생성 엔지니어 업무를 하면서 어려운은 타겟에 적젏한 데이터를 모으는 것이였다.  
(ex) "동양인 20대 여성 이미지", "음식을 먹고있는 나이든 서양인"  
Kontext는 
...

## 핵심 기술  
...

---
[1] https://bfl.ai/announcements/flux-1-kontext  
[2] https://medium.com/gliacloud/removing-any-object-from-your-photo-with-lama-7e966765fadc  


