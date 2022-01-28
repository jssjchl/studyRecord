React-router-dom

클론코딩을 통해 리액트의 구조 및 문법을 익히려고 게시판을 짜는 중이였다. 근데 암만 똑같이 해도 자동완성은 물론이고 기능 실행도 안될 뿐더러 제대로 링크를 걸어줘도 불러오지 못하는 사태가,,



하지만 검색해보니 이유는 현 프로젝트의 구조는 reac-router-dom v5이고, 현재는 v6이였다. 애초에 yarn을 통해 깔 때 최신버전 기준으로 설치가 되다보니 버전이 안맞은 것이였다. 하지만 나는 v6기준으로 코드를 변경하기로

```javascript
import React from 'react';
import { BrowserRouter, Route, Switch} from 'react-router-dom';
import UserListComponent from "../user/UserListComponent";
import AddUserComponent from "../user/AddUserComponent";
import EditUserComponent from "../user/EditUserComponent";

const AppRouter = () => {
   return(
     <div>
       <BrowserRouter>
        <div style={style}>
          <Switch>
            <Route exact path="/" component={UserListComponent} />
            <Route path="/users" component={UserListComponent} />
            <Route path="/add-user" component={AddUserComponent} />
            <Route path="/edit-user" component={EditUserComponent} />
          </Switch>
        </div>
       </BrowserRouter>
     </div>
   );
}

const style = {
  color: 'red',
  margin: '10px'
}

export default AppRouter;
```

기존 v5기준 코드가 이렇다면

```javascript
import React from 'react';
import { BrowserRouter, Route, Routes } from 'react-router-dom';
import AddUserComponent from '../user/AddUserComponent';
import EditUserComponent from '../user/EditUserComponent';
import UserListComponent from '../user/UserListComponent';
const RouterComponent = () => {
    return (
        <div>
            <BrowserRouter>
            <div style={style}>
                <Routes>
                    <Route path="/" element={<UserListComponent/>} />
                    <Route path="/users" element={<UserListComponent/>}/>
                    <Route path="/add-users" element={<AddUserComponent/>}/>
                    <Route path="/edit-users" element={<EditUserComponent/>}/>
                </Routes>
            </div>
            </BrowserRouter>
        </div>
    );
};
const style={
    color :'red',
    margin:'10px'
}

export default RouterComponent;
```

현재는 이렇게 변경된다. 

차이점은 Switch가 네이밍이 변경되어 Routes로 변경되었다. 



여기서 Switch란 여러 Route를 감싸 규칙이 일치하는 라우트 하나만을 렌더링 시켜주는 역할을 한다. (지금은 Routes)



또한 exact옵션이 삭제되었다. exact는 기존에 루트 페이지같은 경우 모든 페이지를 불러오는 현상이 있었는데, v6에서 이 기능이 삭제되고 알아서 정확히 매칭된다고 한다. 

참고: https://kyung-a.tistory.com/36