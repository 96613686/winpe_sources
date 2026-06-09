# _CxxThrowException_0

- ea: `0x180002ac0`
- end: `0x180002ac6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180002948`
- `0x180002970`
- `0x180004c48`
- `0x180004e10`
- `0x180004fa0`
- `0x180005650`
- `0x18000a498`
- `0x18000a6c0`
- `0x18000a970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002ac0`

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
0x180002ac0  jmp     cs:__imp__CxxThrowException
```
