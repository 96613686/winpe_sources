# _CxxThrowException

- ea: `0x180004234`
- end: `0x18000423a`
- name: `_CxxThrowException`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180004084`
- `0x1800040ac`
- `0x18000e97c`
- `0x18000f370`
- `0x18000fc9c`
- `0x180015c4c`
- `0x180015dcc`
- `0x18001604c`
- `0x18001bfd0`
- `0x18001c150`
- `0x18001c2d0`
- `0x18001cb40`
- `0x180022c0c`
- `0x180023660`
- `0x18002a93c`
- `0x18002b3fc`
- `0x18002b474`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180004234`

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
0x180004234  jmp     cs:__imp__CxxThrowException
```
