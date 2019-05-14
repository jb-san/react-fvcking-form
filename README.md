# WIP
# react-fvcking-form

TODO: write a catchy tagline

## Install
`npm i react-fvcking-form`
## Usage

```
import React, {useState, useEffect} from 'react'
import {userForm,useValue} from 'react-fvcking-form'

function App(){
  const [getState,formRef] = useForm(`myForm`)
  const handleSubmit = (e) => {
  ...
  }
  return <form onSubmit={handleSubmit} ref={formRef}><Firstname/><Lastname/><Fullname></form>
}

function Firstname(){
  return <input id=`firstname`/>
}

function Lastname(){
  return <input id=`lastname`/>
}

function Fullname(){
  const [fullname, setFullname] = useState(``)
  
  // get methods, to avoid rerendering, would like to return value but not sure if itll cause performance problems
  const getFirstname = useValue(`#firstname`)
  const getLastname = useValue(`#lastname`)
  
  useEffect(()=>{
    setFullname(`${getFirstname()} ${getLastname()}`)
  })
  
  return <span>{fullname}</span>
}
```
