# SETUP ENVIRONMENT

## Requirement

- Node: 20.11.0
- yarn

## Installation

1. Create `env.development.local` and copy below content

```shell
ENV_VARIABLE="server_only_variable"
NEXT_PUBLIC_ENV_VARIABLE="public_variable"
API_URL=https://api.dev.ssc-fansite.com
API_KEY=
I18N_INPUT=./[ProjectName] Messages List.xlsx
I18N_SHEETS=Locale Messages,Server Error Messages
I18N_OUTPUT=./public/static/locales
PORT=4000
MUNICIPAL_URL=https://mypg.jp/
MUL_PAY_DOMAIN=
SHOP_ID=
NEXT_PUBLIC_GOOGLE_TAG_MANAGER_ID=
API_CMS_URL=

```

2. Install packages

```shell
yarn install
```

3. Add NODE_OPTIONS

Add global `win-node-env` (for Windows user):

```shell
npm install -g win-node-env
```

4. Start development server

```shell
yarn dev
```

5. Access development server
   Access: http://shibushi.localhost:4000
