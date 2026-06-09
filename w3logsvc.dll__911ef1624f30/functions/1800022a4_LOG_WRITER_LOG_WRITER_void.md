# LOG_WRITER::~LOG_WRITER(void)

- ea: `0x1800022a4`
- end: `0x18000238d`
- name: `??1LOG_WRITER@@UEAA@XZ`
- size: `233`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800023a0`

## callees

- `0x180001048`
- `0x1800022a4`
- `0x180004b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002333`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002333`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000230c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002340`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000236d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000230c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002340`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000236d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002386`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000234d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000235a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002363`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000234d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000235a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002363`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002302`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180002302`

## pseudocode

```c
void __fastcall LOG_WRITER::~LOG_WRITER(struct _RTL_CRITICAL_SECTION *this)
{
  STRA *p_LockCount; // rsi
  void *SpinCount; // rcx
  __int64 v4; // rdi

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&LOG_WRITER::`vftable';
  p_LockCount = (STRA *)&this[3].LockCount;
  if ( LODWORD(this[4].OwningThread) )
    LOG_WRITER::Flush((LOG_WRITER *)this, 0);
  SpinCount = (void *)this[15].SpinCount;
  if ( SpinCount != (void *)-1LL )
  {
    CloseHandle(SpinCount);
    this[15].SpinCount = -1;
  }
  v4 = *(_QWORD *)&this->LockCount;
  if ( v4 )
  {
    MULTISZ::~MULTISZ((MULTISZ *)(v4 + 160));
    STRU::~STRU((STRU *)(v4 + 104));
    STRU::~STRU((STRU *)(v4 + 48));
    operator delete((void *)v4);
    *(_QWORD *)&this->LockCount = 0;
  }
  DeleteCriticalSection(this + 17);
  STRU::~STRU((STRU *)&this[14]);
  STRA::~STRA((STRA *)&this[12].OwningThread);
  STRA::~STRA((STRA *)&this[4].LockSemaphore);
  STRA::~STRA(p_LockCount);
  STRU::~STRU((STRU *)&this[1].SpinCount);
  STRU::~STRU((STRU *)&this->OwningThread);
}

```

## disassembly

```asm
0x1800022a4  mov     [rsp+arg_0], rbx
0x1800022a9  mov     [rsp+arg_8], rsi
0x1800022ae  push    rdi
0x1800022af  sub     rsp, 20h
0x1800022b3  mov     rbx, rcx
0x1800022b6  lea     rax, ??_7LOG_WRITER@@6B@; const LOG_WRITER::`vftable'
0x1800022bd  mov     [rcx], rax
0x1800022c0  lea     rsi, [rcx+80h]
0x1800022c7  cmp     dword ptr [rsi+30h], 0
0x1800022cb  jbe     short loc_1800022D4
0x1800022cd  xor     edx, edx; int
0x1800022cf  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x1800022d4  mov     rcx, [rbx+278h]; hObject
0x1800022db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800022df  jz      short loc_1800022F2
0x1800022e1  call    cs:__imp_CloseHandle
0x1800022e7  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x1800022f2  mov     rdi, [rbx+8]
0x1800022f6  test    rdi, rdi
0x1800022f9  jz      short loc_18000232C
0x1800022fb  lea     rcx, [rdi+0A0h]
0x180002302  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180002308  lea     rcx, [rdi+68h]
0x18000230c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002312  lea     rcx, [rdi+30h]
0x180002316  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000231c  mov     rcx, rdi; Block
0x18000231f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002324  mov     qword ptr [rbx+8], 0
0x18000232c  lea     rcx, [rbx+2A8h]; lpCriticalSection
0x180002333  call    cs:__imp_DeleteCriticalSection
0x180002339  lea     rcx, [rbx+230h]
0x180002340  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002346  lea     rcx, [rbx+1F0h]
0x18000234d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002353  lea     rcx, [rbx+0B8h]
0x18000235a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002360  mov     rcx, rsi
0x180002363  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002369  lea     rcx, [rbx+48h]
0x18000236d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002373  lea     rcx, [rbx+10h]
0x180002377  mov     rbx, [rsp+28h+arg_0]
0x18000237c  mov     rsi, [rsp+28h+arg_8]
0x180002381  add     rsp, 20h
0x180002385  pop     rdi
0x180002386  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
