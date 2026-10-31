# Era JSON (`github.com/era-lang-official/json`)

High-performance native JSON parser and serializer for the Era programming language.

## Installation

Add to your `era.mod`:
```
require (
    github.com/era-lang-official/json v1.0.0
)
```

## Usage

```era
import "github.com/era-lang-official/json";

fn main() {
    // Parsing
    let raw = "{\"name\": \"Era\", \"version\": 1, \"active\": true}";
    let val = parse(raw).unwrap();
    println(val.get("name".to_string()).unwrap().as_string().unwrap());

    // Serializing
    let mut props = Vec::<JsonProperty>::new();
    props.push(prop("ok".to_string(), bool_val(true)));
    props.push(prop("count".to_string(), int_val(42)));
    let text = stringify(object_val(props));
    println(text);
}
```

