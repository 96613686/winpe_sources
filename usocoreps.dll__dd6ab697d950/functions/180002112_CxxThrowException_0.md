# _CxxThrowException_0

- ea: `0x180002112`
- end: `0x180002118`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f94`
- `0x180001fbc`
- `0x180002f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002112`

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
0x180002112  jmp     cs:__imp__CxxThrowException
```
