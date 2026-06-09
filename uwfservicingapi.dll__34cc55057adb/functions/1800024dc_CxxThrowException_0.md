# _CxxThrowException_0

- ea: `0x1800024dc`
- end: `0x1800024e2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d78`
- `0x180001db8`
- `0x180001de4`
- `0x18000556b`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800024dc`

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
0x1800024dc  jmp     cs:__imp__CxxThrowException
```
