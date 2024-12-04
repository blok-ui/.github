# Blok

A reactive UI framework for Haxe.

Here's a simple example:

```haxe
import blok.ui.*;
import blok.html.Html;
import blok.html.Client.mount;

function main() {
  var root = js.Browser.document.getElementById('root');
  mount(root, Counter.node({}));
}

class Counter extends Component {
  @:signal final count:Int = 0;

  function decrement(_:blok.html.HtmlEvents.Event) {
    count.update(count -> count > 0 ? count - 1 : 0);
  }

  function render() return Html.view(<div>
    <div>count</div>
    <button onClick=decrement>"-"</button>
    <button onClick={ _ -> count.update(count -> count + 1)}>"+"</button>
  </div>);
}
```
