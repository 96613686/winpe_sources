# PerfCache::`scalar deleting destructor'(uint)

- ea: `0x18000ec80`
- end: `0x18000ecb0`
- name: `??_GPerfCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `PerfCache *__fastcall(PerfCache *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ea34`
- `0x18000ec80`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ec9c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ec9c`

## pseudocode

```c
PerfCache *__fastcall PerfCache::`scalar deleting destructor'(PerfCache *this, char a2)
{
  PerfCache::~PerfCache(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18000ec80  mov     [rsp+arg_0], rbx
0x18000ec85  push    rdi
0x18000ec86  sub     rsp, 20h
0x18000ec8a  mov     ebx, edx
0x18000ec8c  mov     rdi, rcx
0x18000ec8f  call    ??1PerfCache@@UEAA@XZ; PerfCache::~PerfCache(void)
0x18000ec94  test    bl, 1
0x18000ec97  jz      short loc_18000ECA2
0x18000ec99  mov     rcx, rdi
0x18000ec9c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000eca2  mov     rax, rdi
0x18000eca5  mov     rbx, [rsp+28h+arg_0]
0x18000ecaa  add     rsp, 20h
0x18000ecae  pop     rdi
0x18000ecaf  retn
```
