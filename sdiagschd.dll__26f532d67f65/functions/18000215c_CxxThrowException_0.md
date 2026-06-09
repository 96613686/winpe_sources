# _CxxThrowException_0

- ea: `0x18000215c`
- end: `0x180002162`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014b8`
- `0x1800014f8`
- `0x180001524`
- `0x18000afc0`
- `0x18000c010`
- `0x18000c9b7`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000215c`

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
0x18000215c  jmp     cs:__imp__CxxThrowException
```
