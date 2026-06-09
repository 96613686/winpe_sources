# _CxxThrowException_0

- ea: `0x180002b4c`
- end: `0x180002b52`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e28`
- `0x180001e68`
- `0x180001e94`
- `0x1800040a0`
- `0x180010c40`
- `0x180011740`
- `0x180013337`
- `0x180013646`
- `0x18001366d`
- `0x18001369b`
- `0x1800136b8`
- `0x1800136e6`
- `0x1800137a8`
- `0x1800137cf`
- `0x1800137ec`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180002b4c`

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
0x180002b4c  jmp     cs:__imp__CxxThrowException
```
