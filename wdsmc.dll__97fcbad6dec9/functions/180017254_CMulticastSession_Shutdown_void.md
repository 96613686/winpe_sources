# CMulticastSession::Shutdown(void)

- ea: `0x180017254`
- end: `0x180017409`
- name: `?Shutdown@CMulticastSession@@QEAAKXZ`
- size: `437`
- prototype: `unsigned int __fastcall(CMulticastSession *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016e70`
- `0x1800197e0`
- `0x18001a83c`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000a3c4`
- `0x18000c6c0`
- `0x1800150c0`
- `0x180017254`
- `0x18001a9a8`
- `0x1800227d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800172cb`
- `KERNEL32!GetCurrentThreadId` at `0x1800172fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800172cb`
- `KERNEL32!GetCurrentThreadId` at `0x1800172fa`
- `KERNEL32!SwitchToThread` at `0x1800172e6`
- `KERNEL32!SwitchToThread` at `0x1800172e6`
- `KERNEL32!LeaveCriticalSection` at `0x1800172a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800172a8`
- `KERNEL32!EnterCriticalSection` at `0x180017273`
- `KERNEL32!EnterCriticalSection` at `0x180017273`

## string_xrefs

- `0x18001730f`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`
- `0x1800173ce`: `WDSMCSE[%s] Shutdown complete.`

## pseudocode

```c
__int64 __fastcall CMulticastSession::Shutdown(CMulticastSession *this)
{
  unsigned int v2; // eax
  const char *v3; // rdx
  volatile signed __int32 *v4; // rbx
  int v5; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v7; // eax
  DWORD v8; // eax
  int v9; // r9d
  const char *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // eax
  const char *v14; // rdx
  unsigned int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // eax
  const char *v18; // rdx
  void *v19; // rcx
  char *v21; // [rsp+30h] [rbp-28h] BYREF
  int v22; // [rsp+38h] [rbp-20h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = CTransportServer::Shutdown((LPCRITICAL_SECTION)((char *)this + 312));
  ElValidateWin32(v2, v3, "base\\eco\\wds\\transport\\server\\mc\\mcsession.cpp", 0xDBu);
  *((_QWORD *)this + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v22 = 0;
  v4 = (volatile signed __int32 *)((char *)this + 16144);
  v21 = (char *)this + 16144;
  while ( 1 )
  {
    v5 = 0;
    if ( *((_DWORD *)this + 4038) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = _InterlockedCompareExchange(v4, CurrentThreadId, 0);
    if ( !v7 || v7 == CurrentThreadId )
      break;
    if ( (unsigned int)++v5 >= *((_DWORD *)this + 4038) )
      goto LABEL_6;
  }
  _InterlockedAdd((volatile signed __int32 *)this + 4037, 1u);
  _InterlockedExchange((volatile __int32 *)this + 4046, 1);
  v22 = 0;
  v8 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd(v4, 0) != v8 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v9,
      0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4037, 0xFFFFFFFF) == 1 )
    _InterlockedExchange(v4, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 16144);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v21);
  ElValidateWin32(0, v10, "base\\eco\\wds\\transport\\server\\mc\\mcsession.cpp", 0xE7u);
  v11 = CContentCache::Shutdown((LPCRITICAL_SECTION)this + 370);
  v13 = ElValidateWin32(v11, v12, "base\\eco\\wds\\transport\\server\\mc\\apsrvdatastate.cpp", 0x6Fu);
  ElValidateWin32(v13, v14, "base\\eco\\wds\\transport\\server\\mc\\mcsession.cpp", 0xECu);
  v15 = CApSrvCIRState::Shutdown((CMulticastSession *)((char *)this + 14600));
  ElValidateWin32(v15, v16, "base\\eco\\wds\\transport\\server\\mc\\mcsession.cpp", 0xEDu);
  v17 = CTransportServer::Shutdown((LPCRITICAL_SECTION)((char *)this + 312));
  ElValidateWin32(v17, v18, "base\\eco\\wds\\transport\\server\\mc\\mcsession.cpp", 0xEEu);
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"WDSMCSE[%s] Shutdown complete.", *((_QWORD *)this + 6));
  v19 = (void *)*((_QWORD *)this + 6);
  if ( v19 )
  {
    operator delete(v19);
    *((_QWORD *)this + 6) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180017254  mov     [rsp+arg_0], rbx
0x180017259  mov     [rsp+arg_8], rbp
0x18001725e  mov     [rsp+arg_10], rsi
0x180017263  push    rdi
0x180017264  push    r12
0x180017266  push    r14
0x180017268  sub     rsp, 40h
0x18001726c  mov     rdi, rcx
0x18001726f  add     rcx, 8; lpCriticalSection
0x180017273  call    cs:__imp_EnterCriticalSection
0x180017279  lea     r14, [rdi+138h]
0x180017280  mov     rcx, r14; lpCriticalSection
0x180017283  call    ?Shutdown@CTransportServer@@QEAAKXZ; CTransportServer::Shutdown(void)
0x180017288  lea     r12, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001728f  mov     ecx, eax; unsigned int
0x180017291  mov     r8, r12; char *
0x180017294  mov     r9d, 0DBh; unsigned int
0x18001729a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001729f  and     qword ptr [rdi+50h], 0
0x1800172a4  lea     rcx, [rdi+8]; lpCriticalSection
0x1800172a8  call    cs:__imp_LeaveCriticalSection
0x1800172ae  and     [rsp+58h+var_20], 0
0x1800172b3  lea     rbx, [rdi+3F10h]
0x1800172ba  mov     [rsp+58h+var_28], rbx
0x1800172bf  mov     ebp, 1
0x1800172c4  xor     esi, esi
0x1800172c6  cmp     [rbx+8], esi
0x1800172c9  jbe     short loc_1800172E6
0x1800172cb  call    cs:__imp_GetCurrentThreadId
0x1800172d1  mov     ecx, eax
0x1800172d3  xor     eax, eax
0x1800172d5  lock cmpxchg [rbx], ecx
0x1800172d9  jz      short loc_1800172EE
0x1800172db  cmp     eax, ecx
0x1800172dd  jz      short loc_1800172EE
0x1800172df  add     esi, ebp
0x1800172e1  cmp     esi, [rbx+8]
0x1800172e4  jb      short loc_1800172CB
0x1800172e6  call    cs:__imp_SwitchToThread
0x1800172ec  jmp     short loc_1800172C4
0x1800172ee  lock add [rbx+4], ebp
0x1800172f2  xchg    ebp, [rbx+28h]
0x1800172f5  and     [rsp+58h+var_20], 0
0x1800172fa  call    cs:__imp_GetCurrentThreadId
0x180017300  xor     ecx, ecx
0x180017302  lock xadd [rbx], ecx
0x180017306  cmp     ecx, eax
0x180017308  jz      short loc_180017327
0x18001730a  and     [rsp+58h+var_38], 0
0x18001730f  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180017316  mov     edx, 99h; unsigned int
0x18001731b  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180017322  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180017327  or      eax, 0FFFFFFFFh
0x18001732a  lock xadd [rbx+4], eax
0x18001732f  cmp     eax, 1
0x180017332  jnz     short loc_180017338
0x180017334  xor     eax, eax
0x180017336  xchg    eax, [rbx]
0x180017338  mov     rcx, rbx
0x18001733b  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x180017340  lea     rcx, [rsp+58h+var_28]
0x180017345  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18001734a  mov     r9d, 0E7h; unsigned int
0x180017350  mov     r8, r12; char *
0x180017353  xor     ecx, ecx; unsigned int
0x180017355  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001735a  lea     rcx, [rdi+39D0h]; lpCriticalSection
0x180017361  call    ?Shutdown@CContentCache@@QEAAKXZ; CContentCache::Shutdown(void)
0x180017366  mov     ecx, eax; unsigned int
0x180017368  lea     r8, aBaseEcoWdsTran_24; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001736f  mov     r9d, 6Fh ; 'o'; unsigned int
0x180017375  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001737a  mov     ecx, eax; unsigned int
0x18001737c  mov     r9d, 0ECh; unsigned int
0x180017382  mov     r8, r12; char *
0x180017385  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001738a  lea     rcx, [rdi+3908h]; this
0x180017391  call    ?Shutdown@CApSrvCIRState@@QEAAKXZ; CApSrvCIRState::Shutdown(void)
0x180017396  mov     ecx, eax; unsigned int
0x180017398  mov     r9d, 0EDh; unsigned int
0x18001739e  mov     r8, r12; char *
0x1800173a1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800173a6  mov     rcx, r14; lpCriticalSection
0x1800173a9  call    ?Shutdown@CTransportServer@@QEAAKXZ; CTransportServer::Shutdown(void)
0x1800173ae  mov     ecx, eax; unsigned int
0x1800173b0  mov     r9d, 0EEh; unsigned int
0x1800173b6  mov     r8, r12; char *
0x1800173b9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800173be  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800173c5  test    rax, rax
0x1800173c8  jz      short loc_1800173DB
0x1800173ca  mov     rdx, [rdi+30h]
0x1800173ce  lea     rcx, aWdsmcseSShutdo; "WDSMCSE[%s] Shutdown complete."
0x1800173d5  call    cs:__guard_dispatch_icall_fptr
0x1800173db  mov     rcx, [rdi+30h]; void *
0x1800173df  test    rcx, rcx
0x1800173e2  jz      short loc_1800173EE
0x1800173e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800173e9  and     qword ptr [rdi+30h], 0
0x1800173ee  mov     rbx, [rsp+58h+arg_0]
0x1800173f3  xor     eax, eax
0x1800173f5  mov     rbp, [rsp+58h+arg_8]
0x1800173fa  mov     rsi, [rsp+58h+arg_10]
0x1800173ff  add     rsp, 40h
0x180017403  pop     r14
0x180017405  pop     r12
0x180017407  pop     rdi
0x180017408  retn
```
