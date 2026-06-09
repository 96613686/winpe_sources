# PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(void)

- ea: `0x180009f54`
- end: `0x180009fc0`
- name: `??1PROTOCOL_MANAGER_ENTRY@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009fc8`

## callees

- `0x180009f54`
- `0x18000a93c`
- `0x18000e010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009f8c`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009f8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009f9f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009f9f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009fb4`

## pseudocode

```c
void __fastcall PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(PROTOCOL_MANAGER_ENTRY *this)
{
  __int64 v2; // rcx

  PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(this);
  v2 = *((_QWORD *)this + 32);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 32) = 0;
  }
  CReaderWriterLock3::~CReaderWriterLock3((PROTOCOL_MANAGER_ENTRY *)((char *)this + 320));
  STRU::~STRU((PROTOCOL_MANAGER_ENTRY *)((char *)this + 136));
  STRU::~STRU((PROTOCOL_MANAGER_ENTRY *)((char *)this + 16));
}

```

## disassembly

```asm
0x180009f54  push    rbx
0x180009f56  sub     rsp, 20h
0x180009f5a  mov     rbx, rcx
0x180009f5d  call    ?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ; PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)
0x180009f62  mov     rcx, [rbx+100h]
0x180009f69  test    rcx, rcx
0x180009f6c  jz      short loc_180009F85
0x180009f6e  mov     rax, [rcx]
0x180009f71  mov     rax, [rax+8]
0x180009f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f7a  mov     qword ptr [rbx+100h], 0
0x180009f85  lea     rcx, [rbx+140h]
0x180009f8c  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180009f93  nop     dword ptr [rax+rax+00h]
0x180009f98  lea     rcx, [rbx+88h]
0x180009f9f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009fa6  nop     dword ptr [rax+rax+00h]
0x180009fab  lea     rcx, [rbx+10h]
0x180009faf  add     rsp, 20h
0x180009fb3  pop     rbx
0x180009fb4  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
