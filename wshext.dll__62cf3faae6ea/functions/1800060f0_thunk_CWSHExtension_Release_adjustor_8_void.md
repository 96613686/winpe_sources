# [thunk]:CWSHExtension::Release`adjustor{8}' (void)

- ea: `0x1800060f0`
- end: `0x1800060f9`
- name: `?Release@CWSHExtension@@W7EAAKXZ`
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
  return CWSHExtension::Release((CWSHExtension *)(a1 - 8));
}

```

## disassembly

```asm
0x1800060f0  sub     rcx, 8; this
0x1800060f4  jmp     ?Release@CWSHExtension@@UEAAKXZ; CWSHExtension::Release(void)
```
