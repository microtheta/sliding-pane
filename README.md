## React Sliding Pane
Panel that slides outside of window. Like panels from Google Tag Manager.

### When to use (UX)
I found sliding pane very helpful in situations when normal modal window (or just popup) is not enough: long paginated lists, multistep form, nested popups.

### [Open demo](https://dimitrydushkin.github.io/sliding-pane/example.html)

### How to use
Install module and peer dependencies:
`npm i --save react react-dom react-modal react-addons-css-transition-group react-sliding-pane`

```js
import { Component } from 'react';
import SlidingPane from 'react-sliding-pane';
import 'react-sliding-pane/dist/react-sliding-pane.css';

export default class SomeComponent extends Component {
    constructor(props) {
        super(props);
        this.state = { isPaneOpen: false };
    }

    render() {
        return <div>
            <button onClick={() => this.setState({ isPaneOne: true })}>Click me to open pane!</button>
            <SlidingPane
                isOpen={ this.state.isPaneOpen }
                title='Hey, it is pane title'
                onRequestClose={() => {
                    // triggered on "<" on left top click or on outside click
                    this.setState({ isPaneOpen: false });
                }}>
                <div>And I am pane content </div>
            </SlidingPane>
        </div>;
    }
}
```