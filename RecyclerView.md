# RecyclerView

1. recyclerview: 많은 수의 데이터 집합을 제한된 영역에서 유연하게 표시할 수 있도록 도와주는 위젯이다.
2. recycle? recyclerview는 아이템을 표시하기 위해 생성한 뷰를 재활용한다. 그리고 이를 위해 viewHolder패턴을 사용한다.



## RecyclerView

 v7 지원 라이브러리(v7 Support Library)에서 제공되는 위젯으로, 앞서 소개한 구성 요소들을 통해, 사용자 데이터를 리스트 형태로 화면에 표시하는 컨테이너 역할을 수행한다.

## Adapter

리사이클러뷰에 표시될 아이템 뷰를 생성하는 역할은 어댑터가 담당, 사용자 데이터 리스트로부터 아이템 뷰를 만든다.

Adapter class는 RecyclerView.Adapter<Adapter.ViewHolder> 상속.

## LayoutManager

리사이클러뷰가 아이템을 화면에 표시할 때, 아이템 뷰들이 리사이클러뷰 내부에서 배치되는 형태를 관리한다.

1. LinearLayoutManager : 수평(Horizontal) 또는 수직(Vertical) 방향, 일렬(Linear)로 아이템 뷰 배치.
2. GridLayoutManager : 바둑판 모양의 격자(Grid) 형태로 아이템 뷰 배치.
3. StaggeredGridLayoutManager : 엇갈림(Staggered) 격자(Grid) 형태로 아이템 뷰 배치.

## ViewHolder

화면에 표시될 아이템 뷰를 저장하는 객체이다.



## 사용법

1. 사용할 Activity에 RecyclerView 추가.

2. RecyclerView에서 사용할 Item Layout생성.

3. RecyclerView Adapter 구현.

   1. onCreateViewHolder(ViewGroup parent, int viewType): viewType 형태의 아이템 뷰를 위한 뷰홀더 객체 생성.
   2. onBindViewHolder(ViewHolder holder, int position): position에 해당하는 데이터를 뷰홀더의 아이템뷰에 표시.
   3. getItemCount(): 전체 아이템 갯수 리턴.

4. RecyclerView에 Adapter와 LayoutManager 지정.

   ```java
   RecyclerView recyclerView = findViewById(R.id.recycler1) ;
   recyclerView.setLayoutManager(new LinearLayoutManager(this)) ;
   //LayoutManager 지정
   SimpleTextAdapter adapter = new SimpleTextAdapter(list) ;
   recyclerView.setAdapter(adapter) ;
   //Adapter 지정
   ```