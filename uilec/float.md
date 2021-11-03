 # float 해제 하는 방법
 ## overflow방법
 float이 된 부모 요소에게 visible을 제외한 overflow를 부여하면 됩니다. 
 하지만 이 방법에도 치명적인 단점이 있습니다. 만약 이 부모 요소 안에 부모의 영역을 벗어나는 팝업과 같은 자식 콘텐츠가 있다고 가정한다면 그 팝업의 내용이 보이지 않는 현상이 일어납니다.

overflow의 유일하고 가장 큰 단점 중에 하나입니다.

그래서 이 방법을 사용하여 float을 해제할 때는 이처럼 안에 내용 중에 부모의 내용을 넘쳐나서 노출되는 콘텐츠는 없는지 확인이 될 때 사용하여야 합니다.

## 인접 형제 요소의 clear를 부여하는 방법
<div class="box_wrap">
  <div class="box_parent">
    <div class="box box1">box1</div>
    <div class="box box2">box2</div>
    <div class="clear"></div>
  </div>
</div>

.clear {
  clear: both;
}

하지만 이를 위해서는 아무런 의미가 없는 빈 태그를 이용해야 하기 때문에 시맨틱적인 요소에선 불필요한 요소가 생기는 것이기 때문에 조금 번잡하다는 단점이 있습니다.

## 가상요소를 이용한 clear 속성을 이용한 해제

.box_parent:after {
  display: block;
  clear: both;
  content: '';
}

지금까지의 해제 방법으로 보편적으로 가장 많이 사용하고 있는 해제 방법 중에 하나입니다.

 