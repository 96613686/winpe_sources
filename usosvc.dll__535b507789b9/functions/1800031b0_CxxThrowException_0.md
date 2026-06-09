# _CxxThrowException_0

- ea: `0x1800031b0`
- end: `0x1800031b6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003060`
- `0x180005990`
- `0x180006460`
- `0x180009600`
- `0x18000a244`
- `0x18000a26c`
- `0x18000a2c8`
- `0x18000a308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800031b0`

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
0x1800031b0  jmp     cs:__imp__CxxThrowException
```
