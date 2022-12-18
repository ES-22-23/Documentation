# VideoModal

## Path
src/components/VideoModal/VideoModal.js

## Child Components
```js
import { DefaultPlayer as Video } from 'react-html5video';
<Video autoPlay loop muted
       controls={['PlayPause', 'Seek', 'Time', 'Volume', 'Fullscreen']} >
    <source src={src} type="video/mp4" />
</Video>
```

## Props

| Name | Type | Default  | Description |
|:-----|:-----|:---------|:-----|
| intrusion | object | null     | The intrusion to display |
| handleClose | function | () => {} | The function to call when the modal is closed |

