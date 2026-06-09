# _CxxThrowException_0

- ea: `0x1800026ac`
- end: `0x1800026b2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002038`
- `0x180002078`
- `0x1800020a4`
- `0x18000dbba`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800026ac`

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
0x1800026ac  jmp     cs:__imp__CxxThrowException
```
