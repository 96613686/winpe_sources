# CWerComReport::Release(void)

- ea: `0x180002700`
- end: `0x180002705`
- name: `?Release@CWerComReport@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(CWerComReport *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180007560`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall CWerComReport::Release(CWerComReport *this)
{
  return CManagedObj::Release(this);
}

```

## disassembly

```asm
0x180002700  jmp     ?Release@CManagedObj@@UEAAKXZ; CManagedObj::Release(void)
```
