# BaseSrvSxsCreateActivationContext

- ea: `0x180005ac0`
- end: `0x180005ac5`
- name: `BaseSrvSxsCreateActivationContext`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800048a0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall BaseSrvSxsCreateActivationContext(__int64 a1)
{
  return BaseSrvSxsCreateActivationContextFromMessage(a1);
}

```

## disassembly

```asm
0x180005ac0  jmp     BaseSrvSxsCreateActivationContextFromMessage
```
