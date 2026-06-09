# LISTENER_CHANNEL::~LISTENER_CHANNEL(void)

- ea: `0x18000ab7c`
- end: `0x18000ac1b`
- name: `??1LISTENER_CHANNEL@@AEAA@XZ`
- size: `159`
- prototype: `void __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b090`

## callees

- `0x18000ab7c`
- `0x18000e010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000abc4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000abc4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000abd7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000abd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000abea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000abfa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000abea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000abfa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ac0f`

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
0x18000ab7c  push    rbx
0x18000ab7e  sub     rsp, 20h
0x18000ab82  lea     rax, ??_7LISTENER_CHANNEL@@6B@; const LISTENER_CHANNEL::`vftable'
0x18000ab89  mov     dword ptr [rcx+8], 58717077h
0x18000ab90  mov     [rcx], rax
0x18000ab93  mov     rbx, rcx
0x18000ab96  mov     rcx, [rcx+138h]
0x18000ab9d  test    rcx, rcx
0x18000aba0  jz      short loc_18000ABBD
0x18000aba2  mov     rax, [rcx]
0x18000aba5  mov     edx, 1
0x18000abaa  mov     rax, [rax]
0x18000abad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb2  mov     qword ptr [rbx+138h], 0
0x18000abbd  lea     rcx, [rbx+118h]
0x18000abc4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000abcb  nop     dword ptr [rax+rax+00h]
0x18000abd0  lea     rcx, [rbx+0C0h]
0x18000abd7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000abde  nop     dword ptr [rax+rax+00h]
0x18000abe3  lea     rcx, [rbx+88h]
0x18000abea  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000abf1  nop     dword ptr [rax+rax+00h]
0x18000abf6  lea     rcx, [rbx+50h]
0x18000abfa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ac01  nop     dword ptr [rax+rax+00h]
0x18000ac06  lea     rcx, [rbx+10h]
0x18000ac0a  add     rsp, 20h
0x18000ac0e  pop     rbx
0x18000ac0f  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
