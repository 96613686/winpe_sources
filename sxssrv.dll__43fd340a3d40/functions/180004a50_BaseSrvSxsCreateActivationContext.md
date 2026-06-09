# BaseSrvSxsCreateActivationContext

- ea: `0x180004a50`
- end: `0x180004a55`
- name: `BaseSrvSxsCreateActivationContext`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004a60`

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
0x180004a50  jmp     BaseSrvSxsCreateActivationContextFromMessage
```
