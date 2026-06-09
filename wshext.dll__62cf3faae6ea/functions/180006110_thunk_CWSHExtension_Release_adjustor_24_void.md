# [thunk]:CWSHExtension::Release`adjustor{24}' (void)

- ea: `0x180006110`
- end: `0x180006119`
- name: `?Release@CWSHExtension@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800060d0`

## pseudocode

```c
__int64 __fastcall CWSHExtension::Release(__int64 a1)
{
  return CWSHExtension::Release((CWSHExtension *)(a1 - 24));
}

```

## disassembly

```asm
0x180006110  sub     rcx, 18h; this
0x180006114  jmp     ?Release@CWSHExtension@@UEAAKXZ; CWSHExtension::Release(void)
```
