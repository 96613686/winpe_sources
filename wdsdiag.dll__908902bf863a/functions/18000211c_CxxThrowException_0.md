# _CxxThrowException_0

- ea: `0x18000211c`
- end: `0x180002122`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002004`
- `0x1800020d0`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000211c`

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
0x18000211c  jmp     cs:__imp__CxxThrowException
```
