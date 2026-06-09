# _CxxThrowException_0

- ea: `0x180003f4c`
- end: `0x180003f52`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f98`
- `0x180002fd8`
- `0x180003004`
- `0x18001a367`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180003f4c`

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
0x180003f4c  jmp     cs:__imp__CxxThrowException
```
