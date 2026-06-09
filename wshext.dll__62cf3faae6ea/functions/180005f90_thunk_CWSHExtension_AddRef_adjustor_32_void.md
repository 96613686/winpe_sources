# [thunk]:CWSHExtension::AddRef`adjustor{32}' (void)

- ea: `0x180005f90`
- end: `0x180005f99`
- name: `?AddRef@CWSHExtension@@WCA@EAAKXZ`
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
  return CWSHExtension::AddRef((CWSHExtension *)(a1 - 32));
}

```

## disassembly

```asm
0x180005f90  sub     rcx, 20h ; ' '; this
0x180005f94  jmp     ?AddRef@CWSHExtension@@UEAAKXZ; CWSHExtension::AddRef(void)
```
