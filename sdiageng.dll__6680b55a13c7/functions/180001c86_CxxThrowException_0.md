# _CxxThrowException_0

- ea: `0x180001c86`
- end: `0x180001c8c`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001488`
- `0x1800014b0`
- `0x1800014dc`
- `0x18000ff80`
- `0x1800111b0`
- `0x180023e08`
- `0x180029d8c`
- `0x180029e3a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001c86`

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
0x180001c86  jmp     cs:__imp__CxxThrowException
```
