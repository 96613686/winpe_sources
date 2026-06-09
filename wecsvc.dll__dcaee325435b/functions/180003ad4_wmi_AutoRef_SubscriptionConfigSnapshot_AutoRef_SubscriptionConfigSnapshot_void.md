# wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(void)

- ea: `0x180003ad4`
- end: `0x180003ad9`
- name: `??1?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800204f2`
- `0x180020504`
- `0x180020734`
- `0x18002077c`
- `0x180020969`
- `0x180020a0b`
- `0x180020e8f`
- `0x180020fa3`
- `0x180020fcf`
- `0x180020ff3`
- `0x180021125`
- `0x180021424`
- `0x180022410`

## callees

- `0x18000526c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(__int64 a1)
{
  return wmi::AutoRef<AbstractEventProcessor>::Release(a1);
}

```

## disassembly

```asm
0x180003ad4  jmp     ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
```
