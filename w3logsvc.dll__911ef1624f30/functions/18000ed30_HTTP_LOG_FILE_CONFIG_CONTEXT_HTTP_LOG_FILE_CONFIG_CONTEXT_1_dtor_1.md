# _HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor$1

- ea: `0x18000ed30`
- end: `0x18000ed42`
- name: `_HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor$1`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed3b`

## pseudocode

```c
void __fastcall HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(*(_QWORD *)(a2 + 48) + 104LL));
}

```

## disassembly

```asm
0x18000ed30  mov     rcx, [rdx+30h]
0x18000ed37  add     rcx, 68h ; 'h'
0x18000ed3b  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
