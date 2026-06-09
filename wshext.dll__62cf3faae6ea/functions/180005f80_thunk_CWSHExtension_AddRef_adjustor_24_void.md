# [thunk]:CWSHExtension::AddRef`adjustor{24}' (void)

- ea: `0x180005f80`
- end: `0x180005f89`
- name: `?AddRef@CWSHExtension@@WBI@EAAKXZ`
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
  return CWSHExtension::AddRef((CWSHExtension *)(a1 - 24));
}

```

## disassembly

```asm
0x180005f80  sub     rcx, 18h; this
0x180005f84  jmp     ?AddRef@CWSHExtension@@UEAAKXZ; CWSHExtension::AddRef(void)
```
