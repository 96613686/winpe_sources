# [thunk]:CWSHExtension::Release`adjustor{16}' (void)

- ea: `0x180006100`
- end: `0x180006109`
- name: `?Release@CWSHExtension@@WBA@EAAKXZ`
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
  return CWSHExtension::Release((CWSHExtension *)(a1 - 16));
}

```

## disassembly

```asm
0x180006100  sub     rcx, 10h; this
0x180006104  jmp     ?Release@CWSHExtension@@UEAAKXZ; CWSHExtension::Release(void)
```
