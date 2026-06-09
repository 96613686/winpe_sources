# _dynamic_atexit_destructor_for__s_PxeEndpoints__

- ea: `0x180012060`
- end: `0x18001208e`
- name: `_dynamic_atexit_destructor_for__s_PxeEndpoints__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012082`
- `WdsCommonLib!??1CBindPolicy@@QEAA@XZ` at `0x18001206b`
- `WdsCommonLib!??1CBindPolicy@@QEAA@XZ` at `0x18001206b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_PxeEndpoints__()
{
  CBindPolicy::~CBindPolicy((CBindPolicy *)qword_18001CC88);
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180012060  sub     rsp, 28h
0x180012064  lea     rcx, qword_18001CC88
0x18001206b  call    cs:__imp_??1CBindPolicy@@QEAA@XZ; CBindPolicy::~CBindPolicy(void)
0x180012072  nop     dword ptr [rax+rax+00h]
0x180012077  lea     rcx, CriticalSection
0x18001207e  add     rsp, 28h
0x180012082  jmp     cs:__imp_DeleteCriticalSection
```
