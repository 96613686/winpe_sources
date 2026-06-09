# CWSHExtension::GetCurFile(ushort * *)

- ea: `0x180006a40`
- end: `0x180006a46`
- name: `?GetCurFile@CWSHExtension@@UEAAJPEAPEAG@Z`
- size: `6`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CWSHExtension::GetCurFile(CWSHExtension *this, unsigned __int16 **a2)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180006a40  mov     eax, 80004001h
0x180006a45  retn
```
