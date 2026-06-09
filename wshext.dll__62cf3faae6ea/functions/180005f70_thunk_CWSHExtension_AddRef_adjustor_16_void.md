# [thunk]:CWSHExtension::AddRef`adjustor{16}' (void)

- ea: `0x180005f70`
- end: `0x180005f79`
- name: `?AddRef@CWSHExtension@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005f40`

## pseudocode

```c
__int64 __fastcall CWSHExtension::AddRef(__int64 a1)
{
  return CWSHExtension::AddRef((CWSHExtension *)(a1 - 16));
}

```

## disassembly

```asm
0x180005f70  sub     rcx, 10h; this
0x180005f74  jmp     ?AddRef@CWSHExtension@@UEAAKXZ; CWSHExtension::AddRef(void)
```
