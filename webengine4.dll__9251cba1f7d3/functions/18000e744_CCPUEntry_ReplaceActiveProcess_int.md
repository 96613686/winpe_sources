# CCPUEntry::ReplaceActiveProcess(int)

- ea: `0x18000e744`
- end: `0x18000e8fa`
- name: `?ReplaceActiveProcess@CCPUEntry@@QEAAJH@Z`
- size: `438`
- prototype: `__int64 __fastcall(CCPUEntry *__hidden this, int)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x18000de60`
- `0x18000e348`
- `0x18000e458`
- `0x1800209c0`
- `0x180020c68`

## callees

- `0x18000e744`
- `0x18001b780`
- `0x18001c8b8`
- `0x18001ca7c`
- `0x18001dc88`
- `0x18001f05c`
- `0x18001f098`
- `0x180049b14`
- `0x180049b60`
- `0x18004d3c4`
- `0x18004d474`
- `0x18004d690`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e780`
- `KERNEL32!EnterCriticalSection` at `0x18000e819`
- `KERNEL32!EnterCriticalSection` at `0x18000e870`
- `KERNEL32!EnterCriticalSection` at `0x18000e780`
- `KERNEL32!EnterCriticalSection` at `0x18000e819`
- `KERNEL32!EnterCriticalSection` at `0x18000e870`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7a6`
- `KERNEL32!LeaveCriticalSection` at `0x18000e831`
- `KERNEL32!LeaveCriticalSection` at `0x18000e888`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8d4`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7a6`
- `KERNEL32!LeaveCriticalSection` at `0x18000e831`
- `KERNEL32!LeaveCriticalSection` at `0x18000e888`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8d4`
- `KERNEL32!Sleep` at `0x18000e8a2`
- `KERNEL32!Sleep` at `0x18000e8a2`
- `KERNEL32!SwitchToThread` at `0x18000e88e`
- `KERNEL32!SwitchToThread` at `0x18000e88e`

## pseudocode

```c
__int64 __fastcall CCPUEntry::ReplaceActiveProcess(CCPUEntry *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  unsigned int v5; // ebx
  CProcessEntry *v6; // rax
  CProcessEntry *v7; // rax
  CProcessEntry *v8; // rbp
  unsigned int v9; // r14d
  __int64 v10; // rsi

  if ( g_fShuttingDown == 1 )
    return 2147500037LL;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_DWORD *)this + 34) && TimeClass::AgeInSeconds((CCPUEntry *)((char *)this + 128)) < 5 )
  {
    LeaveCriticalSection(v4);
    return *((_QWORD *)this + 3) == 0 ? 0x80004005 : 0;
  }
  else
  {
    v5 = *((_DWORD *)this + 2) + (_InterlockedIncrement((volatile signed __int32 *)this + 1) << 8);
    v6 = (CProcessEntry *)MemAlloc(0x1F8u);
    if ( v6 && (v7 = CProcessEntry::CProcessEntry(v6, this, *(_DWORD *)this, v5), (v8 = v7) != 0) )
    {
      v9 = CProcessEntry::Init(v7);
      if ( v9 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        *((_QWORD *)v8 + 43) = *((_QWORD *)this + 14);
        *((_QWORD *)this + 14) = v8;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
      }
      else
      {
        CReadWriteSpinLock::AcquireWriterLock((CCPUEntry *)((char *)this + 12));
        v10 = *((_QWORD *)this + 3);
        *((_QWORD *)this + 3) = v8;
        CReadWriteSpinLock::ReleaseWriterLock((CCPUEntry *)((char *)this + 12));
        if ( v10 )
        {
          CProcessEntry::AddRef((CProcessEntry *)v10);
          PerfIncrementGlobalCounter(7u);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
          *(_QWORD *)(v10 + 344) = *((_QWORD *)this + 14);
          *((_QWORD *)this + 14) = v10;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
          SwitchToThread();
          if ( *(_DWORD *)(v10 + 328) == 1 )
            Sleep(0x3E8u);
          CProcessEntry::SendKillMessage((CProcessEntry *)v10, a2 != 0 ? 2 : 0);
          CProcessEntry::Release((CProcessEntry *)v10);
        }
      }
    }
    else
    {
      v9 = -2147024882;
    }
    TimeClass::SnapCurrentTime((CCPUEntry *)((char *)this + 128));
    LeaveCriticalSection(v4);
    return v9;
  }
}

```

## disassembly

```asm
0x18000e744  mov     rax, rsp
0x18000e747  mov     [rax+8], rbx
0x18000e74b  mov     [rax+18h], rbp
0x18000e74f  mov     [rax+20h], rsi
0x18000e753  mov     [rax+10h], edx
0x18000e756  push    rdi
0x18000e757  push    r12
0x18000e759  push    r13
0x18000e75b  push    r14
0x18000e75d  push    r15
0x18000e75f  sub     rsp, 20h
0x18000e763  cmp     cs:?g_fShuttingDown@@3HA, 1; int g_fShuttingDown
0x18000e76a  mov     rdi, rcx
0x18000e76d  jnz     short loc_18000E779
0x18000e76f  mov     eax, 80004005h
0x18000e774  jmp     loc_18000E8DD
0x18000e779  lea     r15, [rcx+48h]
0x18000e77d  mov     rcx, r15; lpCriticalSection
0x18000e780  call    cs:__imp_EnterCriticalSection
0x18000e786  cmp     dword ptr [rdi+88h], 0
0x18000e78d  lea     r13, [rdi+80h]
0x18000e794  jz      short loc_18000E7C1
0x18000e796  mov     rcx, r13; this
0x18000e799  call    ?AgeInSeconds@TimeClass@@QEAAKXZ; TimeClass::AgeInSeconds(void)
0x18000e79e  cmp     eax, 5
0x18000e7a1  jnb     short loc_18000E7C1
0x18000e7a3  mov     rcx, r15; lpCriticalSection
0x18000e7a6  call    cs:__imp_LeaveCriticalSection
0x18000e7ac  mov     rax, [rdi+18h]
0x18000e7b0  neg     rax
0x18000e7b3  sbb     eax, eax
0x18000e7b5  not     eax
0x18000e7b7  and     eax, 80004005h
0x18000e7bc  jmp     loc_18000E8DD
0x18000e7c1  mov     ebx, 1
0x18000e7c6  lock xadd [rdi+4], ebx
0x18000e7cb  inc     ebx
0x18000e7cd  mov     ecx, 1F8h; unsigned __int64
0x18000e7d2  shl     ebx, 8
0x18000e7d5  add     ebx, [rdi+8]
0x18000e7d8  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000e7dd  test    rax, rax
0x18000e7e0  jz      loc_18000E8C3
0x18000e7e6  mov     r8d, [rdi]; unsigned int
0x18000e7e9  mov     r9d, ebx; unsigned int
0x18000e7ec  mov     rdx, rdi; struct CCPUEntry *
0x18000e7ef  mov     rcx, rax; this
0x18000e7f2  call    ??0CProcessEntry@@QEAA@PEAVCCPUEntry@@KK@Z; CProcessEntry::CProcessEntry(CCPUEntry *,ulong,ulong)
0x18000e7f7  mov     rbp, rax
0x18000e7fa  test    rax, rax
0x18000e7fd  jz      loc_18000E8C3
0x18000e803  mov     rcx, rax; this
0x18000e806  call    ?Init@CProcessEntry@@QEAAJXZ; CProcessEntry::Init(void)
0x18000e80b  lea     r12, [rdi+20h]
0x18000e80f  mov     r14d, eax
0x18000e812  test    eax, eax
0x18000e814  jz      short loc_18000E83C
0x18000e816  mov     rcx, r12; lpCriticalSection
0x18000e819  call    cs:__imp_EnterCriticalSection
0x18000e81f  mov     rcx, [rdi+70h]
0x18000e823  mov     [rbp+158h], rcx
0x18000e82a  mov     rcx, r12; lpCriticalSection
0x18000e82d  mov     [rdi+70h], rbp
0x18000e831  call    cs:__imp_LeaveCriticalSection
0x18000e837  jmp     loc_18000E8C9
0x18000e83c  lea     rcx, [rdi+0Ch]; this
0x18000e840  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x18000e845  mov     rsi, [rdi+18h]
0x18000e849  lea     rcx, [rdi+0Ch]; this
0x18000e84d  mov     [rdi+18h], rbp
0x18000e851  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x18000e856  test    rsi, rsi
0x18000e859  jz      short loc_18000E8C9
0x18000e85b  mov     rcx, rsi; this
0x18000e85e  call    ?AddRef@CProcessEntry@@QEAAXXZ; CProcessEntry::AddRef(void)
0x18000e863  mov     ecx, 7; unsigned int
0x18000e868  call    ?PerfIncrementGlobalCounter@@YAXK@Z; PerfIncrementGlobalCounter(ulong)
0x18000e86d  mov     rcx, r12; lpCriticalSection
0x18000e870  call    cs:__imp_EnterCriticalSection
0x18000e876  mov     rax, [rdi+70h]
0x18000e87a  mov     rcx, r12; lpCriticalSection
0x18000e87d  mov     [rsi+158h], rax
0x18000e884  mov     [rdi+70h], rsi
0x18000e888  call    cs:__imp_LeaveCriticalSection
0x18000e88e  call    cs:__imp_SwitchToThread
0x18000e894  cmp     dword ptr [rsi+148h], 1
0x18000e89b  jnz     short loc_18000E8A8
0x18000e89d  mov     ecx, 3E8h; dwMilliseconds
0x18000e8a2  call    cs:__imp_Sleep
0x18000e8a8  neg     [rsp+48h+arg_8]
0x18000e8ac  mov     rcx, rsi; this
0x18000e8af  sbb     edx, edx
0x18000e8b1  and     edx, 2; int
0x18000e8b4  call    ?SendKillMessage@CProcessEntry@@QEAAXH@Z; CProcessEntry::SendKillMessage(int)
0x18000e8b9  mov     rcx, rsi; this
0x18000e8bc  call    ?Release@CProcessEntry@@QEAAXXZ; CProcessEntry::Release(void)
0x18000e8c1  jmp     short loc_18000E8C9
0x18000e8c3  mov     r14d, 8007000Eh
0x18000e8c9  mov     rcx, r13; this
0x18000e8cc  call    ?SnapCurrentTime@TimeClass@@QEAAXXZ; TimeClass::SnapCurrentTime(void)
0x18000e8d1  mov     rcx, r15; lpCriticalSection
0x18000e8d4  call    cs:__imp_LeaveCriticalSection
0x18000e8da  mov     eax, r14d
0x18000e8dd  mov     rbx, [rsp+48h+arg_0]
0x18000e8e2  mov     rbp, [rsp+48h+arg_10]
0x18000e8e7  mov     rsi, [rsp+48h+arg_18]
0x18000e8ec  add     rsp, 20h
0x18000e8f0  pop     r15
0x18000e8f2  pop     r14
0x18000e8f4  pop     r13
0x18000e8f6  pop     r12
0x18000e8f8  pop     rdi
0x18000e8f9  retn
```
