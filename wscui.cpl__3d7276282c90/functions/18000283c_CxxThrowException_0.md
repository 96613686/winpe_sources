# _CxxThrowException_0

- ea: `0x18000283c`
- end: `0x180002842`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c7c`
- `0x180001d20`
- `0x180003288`
- `0x1800032b0`
- `0x1800032dc`
- `0x1800044f8`
- `0x18000afa7`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000283c`

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
0x18000283c  jmp     cs:__imp__CxxThrowException
```
