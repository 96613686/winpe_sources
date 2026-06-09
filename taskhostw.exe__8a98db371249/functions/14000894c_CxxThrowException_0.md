# _CxxThrowException_0

- ea: `0x14000894c`
- end: `0x140008952`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1400072bc`
- `0x140008258`
- `0x140008298`
- `0x1400082c4`
- `0x14000a1f8`
- `0x14000add0`
- `0x14000aded`
- `0x14000ae14`
- `0x14000af00`
- `0x14000afdb`
- `0x14000b018`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000894c`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x14000894c  jmp     cs:__imp__CxxThrowException
```
