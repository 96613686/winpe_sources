# _CxxThrowException

- ea: `0x180003640`
- end: `0x180003646`
- name: `_CxxThrowException`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034c4`
- `0x1800034ec`
- `0x180005030`
- `0x18000bac0`
- `0x18000bc40`
- `0x18000bdc0`
- `0x18000c610`
- `0x180012814`
- `0x180013220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003640`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x180003640  jmp     cs:__imp__CxxThrowException
```
