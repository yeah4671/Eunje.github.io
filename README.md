<!DOCTYPE html>
<html lang="en">
<head>
  
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>은제</title>
   
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Noto Serif KR', 'Arial', sans-serif;
            font-size: 18px;
            line-height: 1.95;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f9f9f9;
            color: #333;
        }
        div {
            text-align: left;
            max-width: 800px;
        }
        span {
            display: inline;
            user-select: text;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .highlight {
            background-color: #FE0100; 
            transition: background-color 0.3s ease; 
        } 
      
        .no-highlight {
            pointer-events: none; 
            cursor: default; 
        }
      /* 이게 뭐냐면요 사람마다 메인페이지 통글에 포함 된 문장이 다르자나요?
          예를들어 "효정이가 [사과를]먹었다 에서 [사과를]만 메인페이지 글에 들어갔다면, 내부 설명 페이지에 들어갔을때도 그 단어에만 하이라이트가 됩니다. 
          그리고 그 부분을 클릭해야?!?!?!?! 진짜 그사람의 사이트로 연결되규요 !! 밑에 링크 거는 곳 있어용 에시 페이지 주소니까 각 개인의 주소 넣으시면 됩니당. 모르시는 거 항시 물어보시고용 ~~*/
         /* */
         /*그르니까 메인 페이지는 제가 단톡에 보낸 동영상에서 보실 수 있어여. 디자인팀 피그마 링크에서 보면 좀 더 이해될 거요. 메인페이지에 총 22분의 글이 합쳐서 쓰여있고,
 클릭하면 각 글 조각마다 지정된 색들이 알아서 하이라이트 됩니다. 동영상 보면 좀 더 이해가 될 거야 ~) 그리고 그 하이라이트 된 부분을 한 번 더 누르면 개인의 설명페이지로 이동하고요,
 그 설명페이지에 하이라이트 된 단락을 클릭하면 최종 개인 페이지가 나온다고 보시면 됩니다. 용갱 수민씨는 지금 총 22분의 설명하는 페이지를 열분씩 나눠서 만들어주시면 될 것 같아요ㅎㅎ. 이해 안되시먄 바로 연락 . 이해 안되시먄 바로 연락 @@   */
    </style>
</head>
<body>
    <div>
        <span class="no-highlight">내가 선택한 사람들에게서 나를 침범해 오는, '선택하지 않은 말'들
            왜인지 아이러니하다.
            스스로 선택한 사람들과의 대화는 종종 흥미로움과 당황스러움을 동반한다. 예기치 못한 '말'들 속에서(그것이 설령 좋은 말일 지라도)</span>
        <span>우리의 대화는 선택과 침범의 연속이다. 내가 선택한 너이니 받아들여야 할까?</span>
        <span class="no-highlight">얼마만큼 받아들여야 할까. 어떻게 받아들일까 . ?
            이 웹사이트에서는 일상에서 그렇듯 많은 사람들 중 스스로 선택한 침범을 경험해 볼 수 있다.</span>
    </div>
    <script>
       
        const spans = document.querySelectorAll('span');

        
        let lastClicked = null;

       
        spans.forEach(span => {
            span.addEventListener('click', () => {
                // 'no-highlight' 클래스를 가진 단락은 하이라이트가 나타나지 않아용 ~~
                if (span.classList.contains('no-highlight')) return;

                // 이미 하이라이트된 단락을 눌렀을때 ~~@@
                if (span === lastClicked) {
                    window.location.href = ''; // 링크 넣으시면 됩니두. 이게 그 레알 사이트 주소! 
                    return;
                }

                
                spans.forEach(s => s.classList.remove('highlight'));

                // 클릭한 span에만 하이라이트를 추가하게 해둔거구용 
                span.classList.add('highlight');

                // 이것은 마지막으로 하이라이트 된 문장 냅두기 티비 
                lastClicked = span;
            });
        });
    </script>
</body>
</html>
