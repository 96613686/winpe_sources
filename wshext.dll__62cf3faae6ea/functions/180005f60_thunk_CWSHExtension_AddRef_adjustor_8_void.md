# [thunk]:CWSHExtension::AddRef`adjustor{8}' (void)

- ea: `0x180005f60`
- end: `0x180005f69`
- name: `?AddRef@CWSHExtension@@W7EAAKXZ`
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
  return CWSHExtension::AddRef((CWSHExtension *)(a1 - 8));
}

```

## disassembly

```asm
0x180005f60  sub     rcx, 8; this
0x180005f64  jmp     ?AddRef@CWSHExtension@@UEAAKXZ; CWSHExtension::AddRef(void)
```
