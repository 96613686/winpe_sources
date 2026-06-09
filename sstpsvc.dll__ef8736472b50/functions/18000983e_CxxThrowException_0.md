# _CxxThrowException_0

- ea: `0x18000983e`
- end: `0x180009844`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180008610`
- `0x180008850`
- `0x180008f6c`
- `0x180009068`
- `0x180009094`
- `0x18001004c`
- `0x18001042c`
- `0x18001058c`
- `0x18001286c`
- `0x18001292c`
- `0x180012ae8`
- `0x18001406c`
- `0x180014168`
- `0x18001d320`
- `0x18001d33d`
- `0x18001d36d`
- `0x18001d38a`
- `0x18001d6e7`
- `0x18001d726`
- `0x18001d753`
- `0x18001d789`
- `0x18001d7b8`
- `0x18001d80a`
- `0x18001d846`
- `0x18001d96f`
- `0x18001d999`
- `0x18001d9c7`
- `0x18001da61`
- `0x18001dab3`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000983e`

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
0x18000983e  jmp     cs:__imp__CxxThrowException
```
