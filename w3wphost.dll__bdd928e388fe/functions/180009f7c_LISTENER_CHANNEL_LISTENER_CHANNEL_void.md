# LISTENER_CHANNEL::~LISTENER_CHANNEL(void)

- ea: `0x180009f7c`
- end: `0x180009ffe`
- name: `??1LISTENER_CHANNEL@@AEAA@XZ`
- size: `130`
- prototype: `void __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3b0`

## callees

- `0x180009f7c`
- `0x18000d010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009fc4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009fc4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180009fd1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180009fd1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009fde`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009fe8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009fde`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009fe8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009ff7`

## pseudocode

```c
void __fastcall LISTENER_CHANNEL::~LISTENER_CHANNEL(LISTENER_CHANNEL *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx

  *((_DWORD *)this + 2) = 1483829367;
  *(_QWORD *)this = &LISTENER_CHANNEL::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 39);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 39) = 0;
  }
  CReaderWriterLock3::~CReaderWriterLock3((LISTENER_CHANNEL *)((char *)this + 280));
  BUFFER::~BUFFER((LISTENER_CHANNEL *)((char *)this + 192));
  STRU::~STRU((LISTENER_CHANNEL *)((char *)this + 136));
  STRU::~STRU((LISTENER_CHANNEL *)((char *)this + 80));
  STRU::~STRU((LISTENER_CHANNEL *)((char *)this + 16));
}

```

## disassembly

```asm
0x180009f7c  push    rbx
0x180009f7e  sub     rsp, 20h
0x180009f82  lea     rax, ??_7LISTENER_CHANNEL@@6B@; const LISTENER_CHANNEL::`vftable'
0x180009f89  mov     dword ptr [rcx+8], 58717077h
0x180009f90  mov     [rcx], rax
0x180009f93  mov     rbx, rcx
0x180009f96  mov     rcx, [rcx+138h]
0x180009f9d  test    rcx, rcx
0x180009fa0  jz      short loc_180009FBD
0x180009fa2  mov     rax, [rcx]
0x180009fa5  mov     edx, 1
0x180009faa  mov     rax, [rax]
0x180009fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb2  mov     qword ptr [rbx+138h], 0
0x180009fbd  lea     rcx, [rbx+118h]
0x180009fc4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180009fca  lea     rcx, [rbx+0C0h]
0x180009fd1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180009fd7  lea     rcx, [rbx+88h]
0x180009fde  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009fe4  lea     rcx, [rbx+50h]
0x180009fe8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009fee  lea     rcx, [rbx+10h]
0x180009ff2  add     rsp, 20h
0x180009ff6  pop     rbx
0x180009ff7  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
