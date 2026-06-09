# [thunk]:CWerComSupportClassFactory::Release`adjustor{24}' (void)

- ea: `0x180002710`
- end: `0x180002719`
- name: `?Release@CWerComSupportClassFactory@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002700`

## pseudocode

```c
unsigned int __fastcall CWerComSupportClassFactory::Release(__int64 a1)
{
  return CWerComReport::Release((CWerComReport *)(a1 - 24));
}

```

## disassembly

```asm
0x180002710  sub     rcx, 18h; this
0x180002714  jmp     ?Release@CWerComReport@@UEAAKXZ; CWerComReport::Release(void)
```
