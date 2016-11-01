# Drab

Query and update browser DOM objects directly from the server side. No javascript programming needed anymore!

## Warning: this software is still experimental!

See [Demo Page](https://tg.pl/drab) to live demo and description.

## Installation

  So far the process of the installation is rather manually, in the future will be automatized.

  1. Add `drab` to your list of dependencies in `mix.exs` in your Phoenix application:

    ```elixir
    def deps do
      [{:drab, git: "https://github.com/grych/drab.git"}]
    end
    ```

  2. Install dependencies:

    ```bash
    mix deps.get
    ```

  3. Install Drab Javascript library (TODO: to be done as npm package):

    ```bash
    cd web/static/js/
    ln -s ../../../deps/drab/web/static/js/drab.js drab.js
    ```

  4. Add `node-uuid` to `package.json`:

    ```json
    "dependencies": {
      "node-uuid": "~1.4.0"
    }
    ```

  5. And install it:

    ```bash
    npm install
    ```

  6. Initialize `drab.js` by adding the following to `web/static/js/app.js` in your application:

    ```javascript
    import Drab from "./drab"
    let ds = new Drab()
    ```

  7. Add cipher keys to `config/dev.exs` (or `prod.exs`):

    ```elixir
    config :cipher, keyphrase: "sdjv8eieudvicd",
                ivphrase: "d9sdidbnbbdhdh",
                magic_token: "ddh9d99hhffbbssid"
    ```

  8. Initialize websockets by adding the following to `lib/endpoing.ex`:

    ```elixie
    socket "/drab/socket", Drab.Socket
    ```

  9. 
