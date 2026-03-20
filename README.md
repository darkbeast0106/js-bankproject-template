# BankProject

BMSZC Petrik Szoftverfejlesztőinek js automatizált tesztelést bemutató projektje.

## Projekt létrehozás lépései

- Projekt létrehozása (ha még nincs package.json állomány)
  - test script-nek "vitest" legyen megadva
  - a projekt típusa module legyen

```sh
npm init
```

- [vitest](https://vitest.dev/) telepítése

```sh
npm install --save-dev vitest
```

## Klónozás után telepítés lépései

- node modulok telepítése

```sh
npm install
```

- Tesztek futtatása

```sh
npm run test
```

- Futtatás watch módban (Folyamatosan figyeli a fájl változásokat, és változáskor újra lefuttatja az összes tesztet)

```sh
npx vitest --watch
```

- Futtatás coverage módban (tesztlefedetséget is kiírja, telepíteni kell hozzá a `@vitest/coverage-v8` packaget, de ezt felajánlja az első futtatásnál)

```sh
npx vitest --coverage
```

## Javasolt vscode bővítmények

- [vitest](https://marketplace.visualstudio.com/items?itemName=vitest.explorer)
  - vscode testing menüpontja használható lest vitesthez
  - A bővítmény megfelelő működéséhez szükséges lehet vite / vitest config fájl létrehozására
- [vitest snippets](https://marketplace.visualstudio.com/items?itemName=deinsoftware.vitest-snippets)
  - különböző rövidítésekkel egészíti ki a codehelpert, amivel kódblockkok legenerálhatóak.

## Teszt fájl létrehozása

- Teszt fájloknak az alábbi reguláros kifejezésnek kell megfelelnie: `**/__tests__/**/*.[jt]s?(x), **/?(*.)+(spec|test).[tj]s?(x)`
- Reguláris kifejezés jelentése
  - Bármilyen javascriptnek megfelelő fájl, ami:
    - Bárhol egy `__tests__` nevű mappában vagy annak almappáiban van vagy
    - A fájl neve `.spec`-el vagy `.test`-el végződik
    - Fájlok kiterjesztése az alábbi lehet:
      - js: hagyományos javascript fájl
      - ts: typescript fájl
      - jsx: react javascript fájl
      - tsx: react typescript fájl

### Update vitest 4-es verziótól

- A reguláris kifejezés megváltozott: `**/*.{test,spec}.?(c|m)[jt]s?(x)`
- Alapból már csak olyan fájlokat fogad el, aminek a neve `.test` vagy `.spec`-el végződik
- Új fájlkiterjesztéseket elfogad
  - cjs: commonjs fájl
  - mjs: ecmascript module fájl

## Segédlet

Halász Gábor egységtesztelés segédlete elérhető [itt](https://segedletek.level14.hu/2019/03/02/nunit.html)
