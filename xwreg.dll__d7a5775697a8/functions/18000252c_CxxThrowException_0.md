# _CxxThrowException_0

- ea: `0x18000252c`
- end: `0x180002532`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001528`
- `0x180001568`
- `0x180001594`
- `0x180003ca8`
- `0x180012957`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000252c`

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
0x18000252c  jmp     cs:__imp__CxxThrowException
```
