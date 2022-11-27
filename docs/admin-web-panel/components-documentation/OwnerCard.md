# Owner Card

## Path
src/components/OwnerCard/OwnerCard.js

## Child Components
```js
import CardBlock from "../CardBlock/CardBlock";
<CardBlock title="Details" content={details}/>
```

```js
import CardItem from "../CardItem/CardItem";
<CardItem title="Username" content={owner.username}/>
```

## Props

| Name | Type | Default | Description |
|:-----|:-----|:-----|:-----|
| owner | object | {"username": "username", "name": "name", "email": "email", "properties": []} | Owner details to be displayed on the card |

