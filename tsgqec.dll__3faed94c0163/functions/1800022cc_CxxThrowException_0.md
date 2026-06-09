# _CxxThrowException_0

- ea: `0x1800022cc`
- end: `0x1800022d2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001678`
- `0x1800016b8`
- `0x1800016e4`
- `0x18000af94`
- `0x18000b296`
- `0x18000b2bc`
- `0x18000b30f`
- `0x18000b335`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800022cc`

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
0x1800022cc  jmp     cs:__imp__CxxThrowException
```
