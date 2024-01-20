# Rust JSON Serialization and Deserialization 🦀📄

This Rust project demonstrates how to work with JSON using the `serde` crate. It includes a simple example of serializing and deserializing JSON data.

## Features ✨

- **Serialization**: Convert Rust data structures into JSON format.
- **Deserialization**: Parse JSON data into Rust data structures.

## Project Structure 📂

- **main.rs**: Contains the main code demonstrating JSON serialization and deserialization.
- **Cargo.toml**: The project's configuration file.

## Dependencies 📦

This project uses the following external crate:

- **serde**: A powerful serialization/deserialization library for Rust.

## Usage 🚀

Clone the repository and run the following command to execute the program:

```bash
cargo run
```

This will output the JSON representation of an article with paragraphs to the console.

## Code Overview 🧐

```rust
use serde::{Deserialize, Serialize};

#[derive(Serialize, Deserialize)]
struct Paragraph {
    name: String,
}

#[derive(Serialize, Deserialize)]
struct Article {
    article: String,
    author: String,
    paragraph: Vec<Paragraph>,
}

fn main() {
    let article: Article = Article {
        article: String::from("how to work with JSON in Rust"),
        author: String::from("Mohit"),
        paragraph: vec![
            Paragraph {
                name: String::from("first sentence"),
            },
            Paragraph {
                name: String::from("Body of the paragraph"),
            },
            Paragraph {
                name: String::from("End of the paragraph"),
            },
        ],
    };

    let json = serde_json::to_string(&article).unwrap();
    println!("The JSON is: {}", json);
}
```

## Contributing 🤝

Contributions are welcome! Feel free to open issues or pull requests.

## License 📄

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Happy coding! 🚀🦀

----------------------------------------
