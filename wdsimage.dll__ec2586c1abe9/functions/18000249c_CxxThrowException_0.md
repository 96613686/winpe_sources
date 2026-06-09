# _CxxThrowException_0

- ea: `0x18000249c`
- end: `0x1800024a2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e28`
- `0x180001e68`
- `0x180001e94`
- `0x18001036a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000249c`

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
0x18000249c  jmp     cs:__imp__CxxThrowException
```
