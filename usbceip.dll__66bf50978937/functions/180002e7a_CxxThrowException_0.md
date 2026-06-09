# _CxxThrowException_0

- ea: `0x180002e7a`
- end: `0x180002e80`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a48`
- `0x180002a70`
- `0x1800059e0`
- `0x180008020`
- `0x18000c404`
- `0x18000e328`
- `0x18001063e`
- `0x1800107a3`
- `0x1800108d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002e7a`

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
0x180002e7a  jmp     cs:__imp__CxxThrowException
```
