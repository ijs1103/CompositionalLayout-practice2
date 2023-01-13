# CompositionalLayout-practice2

![Simulator Screen Recording - iPhone 13 Pro - 2023-01-13 at 14 32 17](https://user-images.githubusercontent.com/42196410/212244931-ea11ed00-a03f-4344-bb78-d89504cd413c.gif)



## 🧩 개요

- `CompositionalLayout`로 spotify 결제 페이지의 Carousel을 표현.

## 🤔 배운 내용

### ✔️ Carousel 표시하기

```
// 그룹을 수평으로 위치시키고
NSCollectionLayoutGroup.horizontal(layoutSize: groupSize, subitems: [item])

// 수평스크롤 시 그룹의 가운데에 오게 설정
section.orthogonalScrollingBehavior = .groupPagingCentered

```
### ✔️ pageControl

```
// section의 index를 구하여 print 하기.
section.visibleItemsInvalidationHandler = { (items, offset, env) in

  // section의 전체 너비를 스크롤이 된 x값(offset.x)으로 나누고 반올림하여 index를 구하였다.
  let index = Int((offset.x / env.container.contentSize.width).rounded(.up))
  
  print("--> \(index)")
  
  // pageControl의 currentPage를 세팅
  self.pageControl.currentPage = index
}
```

