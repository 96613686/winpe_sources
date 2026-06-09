# _CxxThrowException_0

- ea: `0x180001aac`
- end: `0x180001ab2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `51`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012d8`
- `0x180001300`
- `0x18000132c`
- `0x18000262c`
- `0x1800027ec`
- `0x180002900`
- `0x180002a14`
- `0x1800036fc`
- `0x180003870`
- `0x180004510`
- `0x180004640`
- `0x180004780`
- `0x180004940`
- `0x180004b50`
- `0x180004cc0`
- `0x180004ec0`
- `0x180005220`
- `0x1800054c0`
- `0x1800057b0`
- `0x180005900`
- `0x180005a00`
- `0x180005b90`
- `0x180005f18`
- `0x18000632c`
- `0x1800066c4`
- `0x180006818`
- `0x180006b88`
- `0x180006fb8`
- `0x1800073c4`
- `0x1800075e0`
- `0x180007720`
- `0x180007aa0`
- `0x18000908c`
- `0x18000996c`
- `0x18000a820`
- `0x18000acec`
- `0x18000aea4`
- `0x18000b540`
- `0x18000b6b8`
- `0x18000b804`
- `0x18000b880`
- `0x18000bde6`
- `0x18000be70`
- `0x18000be96`
- `0x18000bebc`
- `0x18000bfe6`
- `0x18000c424`
- `0x18000c5dc`
- `0x18000c660`
- `0x18000c686`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001aac`

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
0x180001aac  jmp     cs:__imp__CxxThrowException
```
