# _HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor$0

- ea: `0x18000ed18`
- end: `0x18000ed2a`
- name: `_HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor$0`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed23`

## pseudocode

```c
void __fastcall HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(*(_QWORD *)(a2 + 48) + 48LL));
}

```

## disassembly

```asm
0x18000ed18  mov     rcx, [rdx+30h]
0x18000ed1f  add     rcx, 30h ; '0'
0x18000ed23  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
