# _CxxThrowException_0

- ea: `0x140002c88`
- end: `0x140002c8e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002ab4`
- `0x140005420`
- `0x140005e90`
- `0x14000950c`
- `0x14000a1a8`
- `0x14000a1d0`
- `0x14000a22c`
- `0x14000a26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002c88`

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
0x140002c88  jmp     cs:__imp__CxxThrowException
```
