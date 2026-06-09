# [thunk]:CWSHExtension::Release`adjustor{32}' (void)

- ea: `0x180006120`
- end: `0x180006129`
- name: `?Release@CWSHExtension@@WCA@EAAKXZ`
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
  return CWSHExtension::Release((CWSHExtension *)(a1 - 32));
}

```

## disassembly

```asm
0x180006120  sub     rcx, 20h ; ' '; this
0x180006124  jmp     ?Release@CWSHExtension@@UEAAKXZ; CWSHExtension::Release(void)
```
