# _CxxThrowException_0

- ea: `0x140002c68`
- end: `0x140002c6e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a84`
- `0x140005400`
- `0x140005e70`
- `0x14000953c`
- `0x14000a1d8`
- `0x14000a200`
- `0x14000a25c`
- `0x14000a29c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002c68`

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
0x140002c68  jmp     cs:__imp__CxxThrowException
```
