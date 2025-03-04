Simple timer model to manage some countdown.

```ts
import { reatomTimer } from '@reatom/timer'
```

```ts
export interface TimerAtom extends AtomMut<number> {
  // interval in ms
  intervalAtom: AtomMut<number> & {
    setSeconds: Action<[seconds: number], number>
  }
  // start timer by passed interval
  startTimer: Action<[delayInSeconds: number], Promise<void>>
  // stop timer manually
  stopTimer: Action<[], void>
  // track end of timer, do not call manually
  endTimer: Action<[], void>
}
```
