# CTransportServer::Shutdown(void)

- ea: `0x1800150c0`
- end: `0x1800152ef`
- name: `?Shutdown@CTransportServer@@QEAAKXZ`
- size: `559`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800147e4`
- `0x1800148b4`
- `0x180017254`
- `0x180017410`

## callees

- `0x180008738`
- `0x180008d38`
- `0x18000e454`
- `0x18000f5cc`
- `0x180011bbc`
- `0x1800150c0`
- `0x180016454`
- `0x180016800`
- `0x18001a9a8`
- `0x1800227d4`
- `0x1800229c0`
- `0x180025850`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180015280`
- `KERNEL32!CloseHandle` at `0x180015280`
- `KERNEL32!GetCurrentThreadId` at `0x18001513f`
- `KERNEL32!GetCurrentThreadId` at `0x180015173`
- `KERNEL32!GetCurrentThreadId` at `0x18001513f`
- `KERNEL32!GetCurrentThreadId` at `0x180015173`
- `KERNEL32!SwitchToThread` at `0x18001515b`
- `KERNEL32!SwitchToThread` at `0x18001515b`
- `KERNEL32!LeaveCriticalSection` at `0x1800150ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800152d1`
- `KERNEL32!LeaveCriticalSection` at `0x1800150ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800152d1`
- `KERNEL32!EnterCriticalSection` at `0x1800150e7`
- `KERNEL32!EnterCriticalSection` at `0x18001526e`
- `KERNEL32!EnterCriticalSection` at `0x1800150e7`
- `KERNEL32!EnterCriticalSection` at `0x18001526e`
- `WDSSRV!WdsEndpointClose` at `0x18001510d`
- `WDSSRV!WdsEndpointClose` at `0x18001510d`

## string_xrefs

- `0x18001518d`: `(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()`

## pseudocode

```c
__int64 __fastcall CTransportServer::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rdi
  unsigned int v3; // eax
  const char *v4; // rdx
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
  HANDLE OwningThread; // rcx
  __int64 v22; // [rsp+20h] [rbp-28h]
  volatile __int32 *p_SpinCount; // [rsp+30h] [rbp-18h] BYREF
  int v24; // [rsp+38h] [rbp-10h]

  _InterlockedExchange((volatile __int32 *)&lpCriticalSection[56].OwningThread, 1);
  EnterCriticalSection(lpCriticalSection);
  v2 = *(_QWORD *)&lpCriticalSection[55].LockCount;
  *(_QWORD *)&lpCriticalSection[55].LockCount = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( v2 )
  {
    v3 = WdsEndpointClose(v2);
    ElValidateWin32(v3, v4, "internal\\onecorebase\\inc\\wdssrv.h", 0x3F7u);
  }
  v24 = 0;
  p_SpinCount = (volatile __int32 *)&lpCriticalSection[334].SpinCount;
  while ( 1 )
  {
    v5 = 0;
    if ( LODWORD(lpCriticalSection[335].DebugInfo) )
      break;
LABEL_8:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)&lpCriticalSection[334].SpinCount, CurrentThreadId, 0);
    if ( !v7 || v7 == CurrentThreadId )
      break;
    if ( (unsigned int)++v5 >= LODWORD(lpCriticalSection[335].DebugInfo) )
      goto LABEL_8;
  }
  _InterlockedAdd((volatile signed __int32 *)&lpCriticalSection[334].SpinCount + 1, 1u);
  _InterlockedExchange((volatile __int32 *)&lpCriticalSection[335].SpinCount, 1);
  v24 = 0;
  v8 = GetCurrentThreadId();
  if ( _InterlockedExchangeAdd(p_SpinCount, 0) != v8 )
    WdsAssert(
      "internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h",
      0x99u,
      "(ULONG) _InterlockedExchangeAdd((LONG volatile*)&(m_uOwnerThread), 0) == GetCurrentThreadId()",
      v9,
      0);
  if ( _InterlockedExchangeAdd(p_SpinCount + 1, 0xFFFFFFFF) == 1 )
    _InterlockedExchange(p_SpinCount, 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)&lpCriticalSection[334].SpinCount);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&p_SpinCount);
  ElValidateWin32(0, v10, "base\\eco\\wds\\transport\\server\\mc\\tpsrvqccstate.cpp", 0x5Fu);
  CTpSrvQCR::Reset((CTpSrvQCR *)&lpCriticalSection[333], 0);
  v11 = CTpSrvDataState::Shutdown((CTpSrvDataState *)&lpCriticalSection[336].LockCount);
  ElValidateWin32(v11, v12, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x16Au);
  v13 = CTpSrvKickDemote::Shutdown((CTpSrvKickDemote *)&lpCriticalSection[133]);
  ElValidateWin32(v13, v14, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x16Fu);
  v15 = CTpSrvClients::Shutdown((CTpSrvClients *)&lpCriticalSection[61]);
  ElValidateWin32(v15, v16, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x170u);
  v17 = CTpSrvSharedAddress::Shutdown((CTpSrvSharedAddress *)&lpCriticalSection[329].LockSemaphore);
  ElValidateWin32(v17, v18, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x171u);
  EnterCriticalSection(lpCriticalSection);
  v19 = *(void **)&lpCriticalSection[356].LockCount;
  if ( v19 )
  {
    CloseHandle(v19);
    *(_QWORD *)&lpCriticalSection[356].LockCount = 0;
  }
  OwningThread = lpCriticalSection[2].OwningThread;
  if ( OwningThread )
  {
    operator delete(OwningThread);
    lpCriticalSection[2].OwningThread = 0;
  }
  if ( HIDWORD(lpCriticalSection[56].OwningThread) )
  {
    LODWORD(v22) = 1;
    CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 12, 1, v22);
    HIDWORD(lpCriticalSection[56].OwningThread) = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1800150c0  mov     [rsp+arg_0], rbx
0x1800150c5  mov     [rsp+arg_8], rsi
0x1800150ca  mov     [rsp+arg_10], rdi
0x1800150cf  push    r14
0x1800150d1  sub     rsp, 40h
0x1800150d5  mov     r14d, 1
0x1800150db  mov     rbx, rcx
0x1800150de  mov     eax, r14d
0x1800150e1  xchg    eax, [rcx+8D0h]
0x1800150e7  call    cs:__imp_EnterCriticalSection
0x1800150ed  mov     rdi, [rbx+8A0h]
0x1800150f4  mov     rcx, rbx; lpCriticalSection
0x1800150f7  and     qword ptr [rbx+8A0h], 0
0x1800150ff  call    cs:__imp_LeaveCriticalSection
0x180015105  test    rdi, rdi
0x180015108  jz      short loc_180015127
0x18001510a  mov     rcx, rdi
0x18001510d  call    cs:__imp_WdsEndpointClose
0x180015113  mov     r9d, 3F7h; unsigned int
0x180015119  lea     r8, aInternalOnecor_2; "internal\\onecorebase\\inc\\wdssrv.h"
0x180015120  mov     ecx, eax; unsigned int
0x180015122  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015127  and     [rsp+48h+var_10], 0
0x18001512c  lea     rdi, [rbx+3450h]
0x180015133  mov     [rsp+48h+var_18], rdi
0x180015138  xor     esi, esi
0x18001513a  cmp     [rdi+8], esi
0x18001513d  jbe     short loc_18001515B
0x18001513f  call    cs:__imp_GetCurrentThreadId
0x180015145  mov     ecx, eax
0x180015147  xor     eax, eax
0x180015149  lock cmpxchg [rdi], ecx
0x18001514d  jz      short loc_180015163
0x18001514f  cmp     eax, ecx
0x180015151  jz      short loc_180015163
0x180015153  add     esi, r14d
0x180015156  cmp     esi, [rdi+8]
0x180015159  jb      short loc_18001513F
0x18001515b  call    cs:__imp_SwitchToThread
0x180015161  jmp     short loc_180015138
0x180015163  lock add [rdi+4], r14d
0x180015168  mov     eax, r14d
0x18001516b  xchg    eax, [rdi+28h]
0x18001516e  and     [rsp+48h+var_10], 0
0x180015173  call    cs:__imp_GetCurrentThreadId
0x180015179  mov     rcx, [rsp+48h+var_18]
0x18001517e  xor     edx, edx
0x180015180  lock xadd [rcx], edx
0x180015184  cmp     edx, eax
0x180015186  jz      short loc_1800151A5
0x180015188  and     [rsp+48h+var_28], 0
0x18001518d  lea     r8, aUlongInterlock; "(ULONG) _InterlockedExchangeAdd((LONG v"...
0x180015194  mov     edx, 99h; unsigned int
0x180015199  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800151a0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800151a5  mov     rdx, [rsp+48h+var_18]
0x1800151aa  or      eax, 0FFFFFFFFh
0x1800151ad  lock xadd [rdx+4], eax
0x1800151b2  cmp     eax, r14d
0x1800151b5  jnz     short loc_1800151C0
0x1800151b7  mov     rax, [rsp+48h+var_18]
0x1800151bc  xor     edx, edx
0x1800151be  xchg    edx, [rax]
0x1800151c0  mov     rcx, rdi
0x1800151c3  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x1800151c8  lea     rcx, [rsp+48h+var_18]
0x1800151cd  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x1800151d2  mov     r9d, 5Fh ; '_'; unsigned int
0x1800151d8  lea     r8, aBaseEcoWdsTran_2; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800151df  xor     ecx, ecx; unsigned int
0x1800151e1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800151e6  lea     rcx, [rbx+3408h]; this
0x1800151ed  xor     edx, edx; unsigned __int64
0x1800151ef  call    ?Reset@CTpSrvQCR@@QEAAX_K@Z; CTpSrvQCR::Reset(unsigned __int64)
0x1800151f4  lea     rcx, [rbx+3488h]; this
0x1800151fb  call    ?Shutdown@CTpSrvDataState@@QEAAKXZ; CTpSrvDataState::Shutdown(void)
0x180015200  lea     rdi, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015207  mov     ecx, eax; unsigned int
0x180015209  mov     r8, rdi; char *
0x18001520c  mov     r9d, 16Ah; unsigned int
0x180015212  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015217  lea     rcx, [rbx+14C8h]; this
0x18001521e  call    ?Shutdown@CTpSrvKickDemote@@QEAAKXZ; CTpSrvKickDemote::Shutdown(void)
0x180015223  mov     ecx, eax; unsigned int
0x180015225  mov     r9d, 16Fh; unsigned int
0x18001522b  mov     r8, rdi; char *
0x18001522e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015233  lea     rcx, [rbx+988h]; this
0x18001523a  call    ?Shutdown@CTpSrvClients@@QEAAKXZ; CTpSrvClients::Shutdown(void)
0x18001523f  mov     ecx, eax; unsigned int
0x180015241  mov     r9d, 170h; unsigned int
0x180015247  mov     r8, rdi; char *
0x18001524a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001524f  lea     rcx, [rbx+3380h]; this
0x180015256  call    ?Shutdown@CTpSrvSharedAddress@@QEAAKXZ; CTpSrvSharedAddress::Shutdown(void)
0x18001525b  mov     ecx, eax; unsigned int
0x18001525d  mov     r9d, 171h; unsigned int
0x180015263  mov     r8, rdi; char *
0x180015266  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001526b  mov     rcx, rbx; lpCriticalSection
0x18001526e  call    cs:__imp_EnterCriticalSection
0x180015274  mov     rcx, [rbx+37A8h]; hObject
0x18001527b  test    rcx, rcx
0x18001527e  jz      short loc_18001528E
0x180015280  call    cs:__imp_CloseHandle
0x180015286  and     qword ptr [rbx+37A8h], 0
0x18001528e  mov     rcx, [rbx+60h]; void *
0x180015292  test    rcx, rcx
0x180015295  jz      short loc_1800152A1
0x180015297  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001529c  and     qword ptr [rbx+60h], 0
0x1800152a1  cmp     dword ptr [rbx+8D4h], 0
0x1800152a8  jz      short loc_1800152CE
0x1800152aa  mov     r9d, r14d
0x1800152ad  mov     [rsp+48h+var_28], r14d
0x1800152b2  mov     r8d, 0Ch
0x1800152b8  lea     rcx, qword_1800336A0; this
0x1800152bf  mov     edx, r14d; unsigned int
0x1800152c2  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x1800152c7  and     dword ptr [rbx+8D4h], 0
0x1800152ce  mov     rcx, rbx; lpCriticalSection
0x1800152d1  call    cs:__imp_LeaveCriticalSection
0x1800152d7  mov     rbx, [rsp+48h+arg_0]
0x1800152dc  xor     eax, eax
0x1800152de  mov     rsi, [rsp+48h+arg_8]
0x1800152e3  mov     rdi, [rsp+48h+arg_10]
0x1800152e8  add     rsp, 40h
0x1800152ec  pop     r14
0x1800152ee  retn
```
