<div align="center">
  <h1>Cairo 🐺 </h1>
  <h2> ⚡ Супер ⚡ быстрый ⚡ компилятор для Cairo, написанный на 🦀 Rust 🦀 </h2>
  <img src="./resources/img/cairo-logo-square.png" height="200" width="200">
  <br />
  <a href="https://github.com/starkware-libs/cairo/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Сообщить о баге</a>
  -
  <a href="https://github.com/starkware-libs/cairo/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Предложить улучшение</a>
  -
  <a href="https://github.com/starkware-libs/cairo/discussions">Задать вопрос</a>
</div>

<div align="center">
<br />

[![GitHub Workflow Status](https://github.com/starkware-libs/cairo/actions/workflows/ci.yml/badge.svg)](https://github.com/starkware-libs/cairo/actions/workflows/ci.yml)
[![Project license](https://img.shields.io/github/license/starkware-libs/cairo.svg?style=flat-square)](LICENSE)
[![Pull Requests welcome](https://img.shields.io/badge/PRs-welcome-ff69b4.svg?style=flat-square)](https://github.com/starkware-libs/cairo/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)

</div>

<details open="open">
<summary>Содержание</summary>

- [О проекте](#about)
- [Начало](#getting-started)
  - [Подготовка](#prerequisites)
  - [Компиляция и запуск файлов Cairo](#compiling-and-running-cairo-files)
  - [Разработка](#development)
    - [Установка языкового сервера](#install-the-language-server)
- [Дорожная карта](#roadmap)
- [Поддержка](#support)
- [Поддержка по проекту](#project-assistance)
- [Вклад в дело](#contributing)
- [Авторы и контрибьюторы](#authors--contributors)
- [Безопасность](#security)
- [Лицензия](#license)

</details>

---

## О проекте
Cairo - это первый полноценный по Тьюрингу язык для создания доказуемых программ для общих вычислений
Cairo is the first Turing-complete language for creating provable programs for general computation.

## Начало

### Подготовка

- Установка [Rust](https://www.rust-lang.org/tools/install)
- Установим Rust:
```bash
rustup override set stable && rustup update
```

Убедитесь, что rust установлен корректно путем выполнения следующей команды:
```bash
cargo test
```

### Компиляция и запуск файлов Cairo

Скомпилируем Cairo в Sierra:
```bash
cargo run --bin cairo-compile -- --single-file /path/to/input.cairo /path/to/output.sierra --replace-ids
```

Скомпилируем Sierra в casm (Cairo assembly):
```bash
cargo run --bin sierra-compile -- /path/to/input.sierra /path/to/output.casm
```

Запустим код Cairo напрямую:
```bash
cargo run --bin cairo-run -- --single-file /path/to/file.cairo
```

Больше информации [здесь](./crates/cairo-lang-runner/README.md). Более того, вы можете найти примеры на Cairo в директории [examples](./examples) .

Для запуска специфических тестов, смотрите здесь: [cairo-test](./crates/cairo-lang-test-runner/README.md)

### Компиляция контрактов Starknet

Скомпилирует контракт Starknet в ContractClass Sierra:
```bash
cargo run --bin starknet-compile -- --single-file /path/to/input.cairo /path/to/output.json
```

Или укажем путь к контракту, если множество контрактов определены в одном и том же проекте:
```bash
cargo run --bin starknet-compile -- /path/to/input/crate /path/to/output.json --contract-path path::to::contract
```

Скомпилируем ContractClass, относящийся к CompiledClass'у:
```bash
cargo run --bin starknet-sierra-compile -- /path/to/input.json /path/to/output.casm
```

### Разработка

#### Установка языкового сервера

Следуйте инструкциям в [vscode-cairo](./vscode-cairo/README.md).

## Дорожная карта

Следующей целью является достижение паритета по возможностям со старой версией Cairo.
Вы можете отслеживать точный прогресс [здесь](./docs/FEATURE_PARITY.md).

## Поддержка
- Мы рекомендуем разработчикам задавать и отвечать на вопросы на [stackoverflow](https://stackoverflow.com/questions/tagged/cairo-lang).
- Контакты перечислены в [этом профиле GitHub](https://github.com/starkware-libs)

## Помощь проекту

Если вы хотите **поблагодарить** и/или поддержать активную разработку Cairo:

- Добавьте [GitHub Star](https://github.com/starkware-libs/cairo) в проект.
- Сделайте твит о вашей разработке на Cairo.
- Пишите интересные статьи о проекте на [Dev.to](https://dev.to/), [Medium](https://medium.com/) или в вашем личном блоге.

Вместе мы можем сделать Cairo **лучше**!

## Вклад

First off, thanks for taking the time to contribute! Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make will benefit everybody else and are **greatly appreciated**.

Please read [our contribution guidelines](docs/CONTRIBUTING.md), and thank you for being involved!

## Authors & contributors

For a full list of all authors and contributors, see [the contributors page](https://github.com/starkware-libs/cairo/contributors).

## Security

Cairo follows good practices of security, but 100% security cannot be assured.
Cairo is provided **"as is"** without any **warranty**. Use at your own risk.

_For more information and to report security issues, please refer to our [security documentation](docs/SECURITY.md)._

## License

This project is licensed under the **Apache 2.0**.

See [LICENSE](LICENSE) for more information.
