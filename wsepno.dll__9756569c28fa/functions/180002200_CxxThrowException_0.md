# _CxxThrowException_0

- ea: `0x180002200`
- end: `0x180002206`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002088`
- `0x1800020b0`
- `0x180002e48`
- `0x180002eb0`
- `0x180003000`
- `0x1800037a0`
- `0x18000c790`
- `0x18000c7fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002200`

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
0x180002200  jmp     cs:__imp__CxxThrowException
```
