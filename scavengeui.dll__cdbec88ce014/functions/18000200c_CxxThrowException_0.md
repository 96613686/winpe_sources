# _CxxThrowException_0

- ea: `0x18000200c`
- end: `0x180002012`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001398`
- `0x1800013d8`
- `0x180001404`
- `0x180003c64`
- `0x180003f66`
- `0x180003f8c`
- `0x180003ff1`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000200c`

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
0x18000200c  jmp     cs:__imp__CxxThrowException
```
