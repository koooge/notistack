<p align="center">
  <a href="https://notistack.com/" rel="noopener" target="_blank"><img width="756" src="https://notistack.com/img/notistack-banner.png" alt="notistack logo"></a></p>
</p>

<div align="center">

[**Notistack**](https://notistack.com) is a notification library which makes it extremely easy to display notifications on your web apps. It is highly customizable and enables you to stack snackbars/toasts on top of one another.
</br>
**Visit [documentation website](https://notistack.com/examples) for demos**.

[![npm version](https://img.shields.io/npm/v/notistack.svg?label=version)](https://www.npmjs.com/package/notistack)
[![npm downloads](https://img.shields.io/npm/dm/notistack.svg)](https://www.npmjs.com/package/notistack)
[![package license](https://img.shields.io/npm/l/notistack.svg)](https://www.npmjs.com/package/notistack)


</div>



| Stacking behaviour | Dismiss oldest when reached maxSnack (3 here)|
| --- | --- |
| <img width="400" src="https://i.imgur.com/MtijvAK.gif"/>    | <img width="400" src="https://i.imgur.com/urX47Wn.gif"/>|


Table of Contents
--
- [How to use](#how-to-use)
- [Online demo](#online-demo)
- [Documentation](https://notistack.com/api-reference)
- [Redux / Mobx support](#redux-and-mobx-support)


## Getting Started
Use your preferred package manager:
```
npm install notistack
yarn add notistack
```

If you're using Material-UI version 4.x.x or lower, download a compatible version of notistack using:
```
npm install notistack@latest-mui-v4
yarn add notistack@latest-mui-v4
```

### How to use

**1:** Wrap your app inside a `SnackbarProvider` component: (see [docs](https://notistack.com/api-reference) for a full list of available props)
<br />
**Note:** If you're using material-ui `ThemeProvider`, make sure `SnackbarProvider` is a child of it.
```jsx
import { SnackbarProvider } from 'notistack';

<SnackbarProvider maxSnack={3}>
    <App />
</SnackbarProvider>

```


**2:** Export any component that needs to send notification using `withSnackbar`. By doing this, you'll have access to methods `enqueueSnackbar` and `closeSnackbar`, where the former can be used to send snackbars.

```javascript
import { withSnackbar } from 'notistack';

class MyComponent extends Component {
  handleNetworkRequest = () => {
     fetchSomeData()
        .then(() => this.props.enqueueSnackbar('Successfully fetched the data.'))
        .catch(() => this.props.enqueueSnackbar('Failed fetching data.'));
  };

  render(){
     //...
  };

};

export default withSnackbar(MyComponent);
```

**2 (alternative):** You can use `useSnackbar` hook in your functional components as well.

```javascript
import { useSnackbar } from 'notistack';

const MyButton = () => {
    const { enqueueSnackbar, closeSnackbar } = useSnackbar();

    const handleClick = () => {
        enqueueSnackbar('I love hooks');
    };

    return (
        <Button onClick={handleClick}>Show snackbar</Button>
    );
}
```

### Online demo
**Visit [`documentation website`](https://notistack.com/examples) to see all the demos.**</br>
Or play with a minimal working example: [codesandbox](https://codesandbox.io/s/github/iamhosseindhv/notistack/tree/master/examples/simple-example??hidenavigation=1&module=%2FApp.js) </br>


### Redux and Mobx support:
notistack is compatible with state management libraries such as Redux and Mobx.

### Contribution
Open an issue and your problem will be solved.


### Author - Contact
Hossein Dehnokhalaji

<a href="https://www.instagram.com/iamhosseindhv"><img src="https://github.com/iamhosseindhv/Rentaly/blob/master/Gifs/instagram.png" alt="Hossein Dehnokhalaji Instagram profile" align="right" width="32" height="32"/></a>
<a href="https://www.linkedin.com/in/iamhosseindhv"><img src="https://github.com/iamhosseindhv/Rentaly/blob/master/Gifs/linkedin.png" alt="Hossein Dehnokhalaji Linkedin profile" align="right" width="32" height="32"/></a>
<a href="mailto:hossein.dehnavi98@yahoo.com"><img src="https://github.com/iamhosseindhv/Rentaly/blob/master/Gifs/contact.png" alt="Hossein Dehnokhalaji email address" align="right" width="32" height="32"/></a>
