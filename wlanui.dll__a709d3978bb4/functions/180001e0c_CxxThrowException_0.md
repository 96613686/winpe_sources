# _CxxThrowException_0

- ea: `0x180001e0c`
- end: `0x180001e12`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001378`
- `0x1800013a0`
- `0x1800013cc`
- `0x18001c37c`
- `0x18001c408`
- `0x18001c449`
- `0x18001c4cd`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001e0c`

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
0x180001e0c  jmp     cs:__imp__CxxThrowException
```
