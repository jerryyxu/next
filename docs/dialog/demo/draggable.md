# 可拖拽

- order: 9

使用 `react-draggable` 库，实现可拖拽对话框。

:::lang=en-us
# Basic

- order: 9

Draggable dialog.
:::
---

````jsx
import { Dialog, Button } from '@alifd/next';
import Draggable  from 'react-draggable';

class Demo extends React.Component {
    state = {
        visible: false
    };

    onOpen = () => {
        this.setState({
            visible: true
        });
    };

    onClose = reason => {
        console.log(reason);

        this.setState({
            visible: false
        });
    };

    render() {
        return (
            <div>
                <Button onClick={this.onOpen} type="primary">
                    Open dialog
                </Button>
                <Draggable handle='.next-dialog-header'>
                    <Dialog
                        animation={false}
                        title="Welcome to Alibaba.com"
                        visible={this.state.visible}
                        onOk={this.onClose.bind(this, 'okClick')}
                        onCancel={this.onClose.bind(this, 'cancelClick')}
                        onClose={this.onClose}>
                        Start your business here by searching a popular product
                    </Dialog>
                </Draggable>
            </div>
        );
    }
}

ReactDOM.render(<Demo />, mountNode);
````
