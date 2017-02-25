# React Confirm Dialog
A component to replace the native confirm for use with React. Renders the confirm dialog outside of your component appended to `body`.

## Usage
Pass the function to perform on confirmation to the `action` prop. Pass the arguments to the `actionArgs` prop.
```
class App extends React.Component {
  sum(args) { 
    alert(args.a + args.b); 
  }
  render() {
    return (
      <ReactConfirmLink action={this.sum} actionArgs={{a:1, b:2}}>
        <a href="#">Click me to trigger the confirm popup</a>
      </ReactConfirmLink>
    );
  }
}
```

## Props
- `action`: The action to perform when the user confirms.
- `actionArgs`: Arguments to be passed to the action.
- `confirmMessage`: The message to display to the user in the confirm dialog (defaults to "Are you sure that you want to do this?").
- `confirmText`: The text to display in the confirm button (defaults to "Yes please").
- `cancelText`: The text to display in the cancel button (defaults to "No thank you").

### Setting default props
You can change the default props globally for all confirms with ConfirmLink.defaultProps[prop_name].
  
Eg. `ConfirmLink.defaultProps.confirmMessage = 'Say this by default in all confirm messages';`

## Styling

There are two styles included in Confirm.css for the modal background and the confirm content:
```
.react-confirm-dialog-bg {
  ...
}
.react-confirm-dialog-content {
  ...
}
```
These have minimal properties to create a modal effect.

To style the confirm and cancel buttons, add styles for the class combinations `react-confirm-dialog-button confirm` and `react-confirm-dialog-button cancel`