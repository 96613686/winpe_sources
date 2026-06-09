# _CxxThrowException_0

- ea: `0x14000191c`
- end: `0x140001922`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001318`
- `0x140001340`
- `0x14000136c`
- `0x140005500`
- `0x140006950`
- `0x14000793a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000191c`

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
0x14000191c  jmp     cs:__imp__CxxThrowException
```
