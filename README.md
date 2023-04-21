## Context API

리액트 프로젝트에서 전역적으로 사용할 데이터 있을 때 유용

#### 전역상태 관리

- 리액트 애플리케이션은 컴포넌트 간 데이터를 props로 전달하기 때문에 컴포넌트 여기저기서 필요한 데이터 있을 때 주로 최상위 컴포넌트인 App의 state에 넣어 관리 => 유지보수성 낮아질 수 있음
- 리덕스나 MobX 같은 상태 관리 라이브러리 사용할 수 있음
- 리액트 v16.3 업데이트 이후 Context API가 많이 개선되어 별도 라이브러리 사용 없이 전역 상태 관리 쉽게 가능

#### Context 만들기

- 새 Context 만들 때 createContext 함수 사용
- 파라미터에 해당 Context의 기본 상태 지정

##### Consumer 사용

- props로 받아오는것이 아닌 Consumer 컴포넌트 통해 데이터 받아옴

##### Provider

- Context의 value 변경 가능
- 파라미터로 기본값 넣어주는 것은 Provide 사용하지 않았을 때만 사용됨, Provide 사용했는데 value 명시 안 할 경우, 이 기본값 사용하지 않기 때문에 오류 발생

##### 동적 Context 사용

- value에 함수 전달 가능

##### Consumer 대신 Hook 또는 static contextType 사용

- useContext Hook 사용 : 함수형 컴포넌트에서 Context 편리하게 사용가능
  -static contextType 정의 : 클래스 메서드에서도 Context에 넣어 둔 함수 호출 가능하지만 한 클래스에서 하나의 Context 밖에 사용 못함
