# _HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection_::_1_::dtor$0

- ea: `0x18000ee17`
- end: `0x18000ee25`
- name: `_HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee1e`

## pseudocode

```c
void __fastcall HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 112));
}

```

## disassembly

```asm
0x18000ee17  lea     rcx, [rdx+70h]
0x18000ee1e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
