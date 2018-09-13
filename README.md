# simple-google-auth
google auth react component

simple google auth for react

## how to use
```javascript
import React from 'react'
import GoogleAuth, {GoogleLogout} from 'simple-google-auth'

const GoogleButton = ({ onClick }) => (<button name="google" onClick={onClick}>google sign up</buttom>)

class LoginPage extends React.Component{

    googleLoginHandler =  ({ profile }) => {
          const input = {
            first_name: profile.firstName,
            last_name: profile.lastName,
            email: profile.email,
            google_id: profile.id,
          }
          console.log(input) 
      }
    
    logout = () => {
        GoogleLogout()
    }

    render(){
        return(
            <div>
            <GoogleAuth
              component={GoogleButton}
              onSuccess={this.googleLoginHandler}
              appId={GOOGLE_APP_ID}
            />
            <button onCLick={this.logut}>logout</buttom>
            </div>
        )
    }
}


```