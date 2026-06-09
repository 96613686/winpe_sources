# PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(void)

- ea: `0x1800094bc`
- end: `0x180009517`
- name: `??1PROTOCOL_MANAGER_ENTRY@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009520`

## callees

- `0x1800094bc`
- `0x180009d60`
- `0x18000d010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800094f4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800094f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009501`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009501`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009510`

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
0x1800094bc  push    rbx
0x1800094be  sub     rsp, 20h
0x1800094c2  mov     rbx, rcx
0x1800094c5  call    ?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ; PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)
0x1800094ca  mov     rcx, [rbx+100h]
0x1800094d1  test    rcx, rcx
0x1800094d4  jz      short loc_1800094ED
0x1800094d6  mov     rax, [rcx]
0x1800094d9  mov     rax, [rax+8]
0x1800094dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094e2  mov     qword ptr [rbx+100h], 0
0x1800094ed  lea     rcx, [rbx+140h]
0x1800094f4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800094fa  lea     rcx, [rbx+88h]
0x180009501  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009507  lea     rcx, [rbx+10h]
0x18000950b  add     rsp, 20h
0x18000950f  pop     rbx
0x180009510  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
