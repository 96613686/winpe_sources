# CWdsService::Shutdown(int,ulong)

- ea: `0x18000d380`
- end: `0x18000d92b`
- name: `?Shutdown@CWdsService@@QEAAKHK@Z`
- size: `1451`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x1800034b8`
- `0x180003944`
- `0x180006f14`
- `0x180008214`
- `0x180008464`
- `0x18000d380`
- `0x18000e180`
- `0x18000e310`
- `0x18000f0dc`
- `0x18000f304`
- `0x1800105f0`
- `0x180011104`
- `0x18001393c`
- `0x1800139c4`
- `0x18001ae58`
- `0x18001b694`
- `0x18001c12a`
- `0x18001c150`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d4ab`
- `KERNEL32!GetLastError` at `0x18000d4ab`
- `KERNEL32!LeaveCriticalSection` at `0x18000d5d7`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000d715`
- `KERNEL32!LeaveCriticalSection` at `0x18000d5d7`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000d715`
- `KERNEL32!EnterCriticalSection` at `0x18000d5b2`
- `KERNEL32!EnterCriticalSection` at `0x18000d5c1`
- `KERNEL32!EnterCriticalSection` at `0x18000d68d`
- `KERNEL32!EnterCriticalSection` at `0x18000d5b2`
- `KERNEL32!EnterCriticalSection` at `0x18000d5c1`
- `KERNEL32!EnterCriticalSection` at `0x18000d68d`
- `KERNEL32!WaitForSingleObject` at `0x18000d49b`
- `KERNEL32!WaitForSingleObject` at `0x18000d49b`
- `KERNEL32!CloseHandle` at `0x18000d524`
- `KERNEL32!CloseHandle` at `0x18000d524`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d76d`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d76d`
- `WS2_32!__imp_WSACleanup` at `0x18000d75d`
- `WS2_32!__imp_WSACleanup` at `0x18000d75d`
- `ole32!CoUninitialize` at `0x18000d7c4`
- `ole32!CoUninitialize` at `0x18000d7c4`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000d4f6`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000d4f6`
- `RPCRT4!RpcMgmtStopServerListening` at `0x18000d464`
- `RPCRT4!RpcMgmtStopServerListening` at `0x18000d464`
- `VSSAPI!?Uninitialize@CVssJetWriter@@QEAAXXZ` at `0x18000d7a0`
- `VSSAPI!?Uninitialize@CVssJetWriter@@QEAAXXZ` at `0x18000d7a0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d4de`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d552`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d6d2`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d4de`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d552`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d6d2`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000d418`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18000d418`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000d7d2`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000d7d2`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000d81a`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000d849`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000d81a`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000d849`
- `WdsServerCommonLib!?Shutdown@CEventLog@@QEAAKXZ` at `0x18000d8a1`
- `WdsServerCommonLib!?Shutdown@CEventLog@@QEAAKXZ` at `0x18000d8a1`
- `WdsServerCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x18000d8d0`
- `WdsServerCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x18000d8d0`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x18000d587`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x18000d587`
- `WdsDiag!WdsDiagShutdown` at `0x18000d8b5`
- `WdsDiag!WdsDiagShutdown` at `0x18000d8b5`
- `ualapi!UalStop` at `0x18000d88a`
- `ualapi!UalStop` at `0x18000d88a`

## pseudocode

```c
__int64 __fastcall CWdsService::Shutdown(CWdsService *this, int a2, unsigned int a3)
{
  volatile __int32 *v3; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rdx
  DWORD LastError; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  void *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rbx
  CWdsProvider *v26; // rbx
  CWdsProvider *v27; // rax
  CWdsProvider *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  CWdsProvider *v31; // r14
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // esi
  unsigned int Error; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // r8
  unsigned int v48; // edx
  char v50[8]; // [rsp+30h] [rbp-2F8h] BYREF
  int v51; // [rsp+38h] [rbp-2F0h]
  int v52; // [rsp+40h] [rbp-2E8h] BYREF
  __int128 v53; // [rsp+44h] [rbp-2E4h]
  char v54[668]; // [rsp+54h] [rbp-2D4h] BYREF

  v3 = (volatile __int32 *)((char *)this + 67264);
  _InterlockedExchange((volatile __int32 *)this + 16813, 1);
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(v50, (char *)this + 67264);
  _InterlockedExchange(v3 + 10, 1);
  CAutoTypeLock<CSpinLock>::Unlock(v50);
  CTimer<CMadcapHandler>::Delete(v3);
  CAutoTypeLock<CSpinLock>::Unlock(v50);
  if ( v51 )
    WdsAssert("onecore\\internal\\base\\inc\\private\\eco\\wds\\locks.h", 0x16Bu, "m_uLockCount == 0", 1, 0);
  v7 = CInterfaceMonitor::Shutdown((CWdsService *)((char *)this + 56));
  ElValidateWin32_3(v7, v8, v9, 163);
  v10 = CUdpHandler::ShutdownPhysicalEndpoints((CWdsService *)((char *)this + 1160));
  ElValidateWin32_3(v10, v11, v12, 168);
  LODWORD(v15) = 0;
  if ( *((_QWORD *)this + 8370) )
  {
    v15 = (unsigned int)RpcMgmtStopServerListening(0);
    if ( !(unsigned int)ElValidateWin32(v15, v16, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 328) )
    {
      if ( WaitForSingleObject(*((HANDLE *)this + 8370), 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        LODWORD(v15) = ElValidateWin32(LastError, v18, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 336);
      }
      else
      {
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Listen Stopped.");
        v15 = (unsigned int)RpcServerUnregisterIf(qword_18001E7F0, 0, 0);
        if ( !(unsigned int)ElValidateWin32(v15, v19, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 349) )
        {
          v20 = (void *)*((_QWORD *)this + 8370);
          if ( v20 )
          {
            CloseHandle(v20);
            *((_QWORD *)this + 8370) = 0;
          }
        }
      }
    }
    if ( (_DWORD)v15 )
      CTrace::Trace((CTrace *)qword_180039310, 0x80000u, L"[RPC] Failed to stop Listen (rc=%u)", (unsigned int)v15);
  }
  ElValidateWin32_3((unsigned int)v15, v13, v14, 173);
  ElValidateWin32_0(0, v21, v22, 779);
  CWdsService::UpdateProgress(this);
  CCompPort::Shutdown((CWdsService *)((char *)this + 67176));
  ElValidateWin32_0(0, v23, v24, 793);
  CWdsService::UpdateProgress(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  v25 = *((_QWORD *)this + 8382);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  if ( v25 )
  {
    v26 = (CWdsProvider *)*((_QWORD *)this + 8383);
    while ( v26 )
    {
      v27 = (CWdsProvider *)*((_QWORD *)this + 8382);
      v28 = (CWdsProvider *)*((_QWORD *)this + 8383);
      if ( v27 == v28 )
      {
        *((_QWORD *)this + 8383) = 0;
        *((_QWORD *)this + 8382) = 0;
      }
      else if ( v26 == v27 )
      {
        v29 = *((_QWORD *)v27 + 34);
        *((_QWORD *)this + 8382) = v29;
        *(_QWORD *)(v29 + 280) = 0;
      }
      else if ( v26 == v28 )
      {
        v30 = *((_QWORD *)v28 + 35);
        *((_QWORD *)this + 8383) = v30;
        *(_QWORD *)(v30 + 272) = 0;
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)v26 + 35) + 272LL) = *((_QWORD *)v26 + 34);
        *(_QWORD *)(*((_QWORD *)v26 + 34) + 280LL) = *((_QWORD *)v26 + 35);
      }
      --*((_DWORD *)this + 16778);
      v31 = v26;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
      v26 = (CWdsProvider *)*((_QWORD *)this + 8382);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
      if ( v26 )
        v26 = (CWdsProvider *)*((_QWORD *)this + 8383);
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[%s] Shutting down", *((_QWORD *)v31 + 2));
      v32 = CWdsProvider::Shutdown(v31);
      ElValidateWin32(v32, v33, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 546);
      (*(void (__fastcall **)(CWdsProvider *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  ElValidateWin32_0(0, v34, v35, 802);
  CWdsService::UpdateProgress(this);
  v36 = CInterfaceHandler::Shutdown((CWdsService *)((char *)this + 48));
  v39 = 0;
  if ( (unsigned int)ElValidateWin32_0(v36, v37, v38, 811) )
    v39 = v36;
  CWdsService::UpdateProgress(this);
  if ( WSACleanup() )
  {
    Error = WSAGetLastError();
    v39 = ElValidateWin32_0(Error, v41, v42, 820);
  }
  CWdsService::UpdateProgress(this);
  if ( dword_180028178 )
    CVssJetWriter::Uninitialize((CVssJetWriter *)&off_180028160);
  dword_180028178 = 0;
  if ( (int)ElValidateHr(0, v43, v44, 629) >= 0 )
    CoUninitialize();
  v45 = WIN32_FROM_HRESULT(0);
  if ( (unsigned int)ElValidateWin32_0(v45, v46, v47, 828) )
    v39 = v45;
  CWdsService::UpdateProgress(this);
  if ( a3 )
    v39 = a3;
  if ( a2 )
  {
    if ( !v39 )
    {
      CEventLog::Log((CEventLog *)qword_180039300, 0x41010102u, 0);
      goto LABEL_44;
    }
    v48 = -1056898813;
  }
  else
  {
    if ( !a3 )
      goto LABEL_44;
    v48 = -1056898815;
  }
  CEventLog::Log((CEventLog *)qword_180039300, v48, 1);
LABEL_44:
  memset_0(v54, 0, sizeof(v54));
  v52 = 688;
  v53 = SumGuid_WDS;
  if ( (unsigned int)DelayLoadUalApi() )
    UalStop(&v52);
  CWdsService::UpdateProgress(this);
  CEventLog::Shutdown((CEventLog *)qword_180039300);
  CWdsService::UpdateProgress(this);
  WdsDiagShutdown();
  CWdsService::UpdateProgress(this);
  CTrace::Shutdown((CTrace *)qword_180039310);
  CWdsService::UpdateProgress(this);
  CWdsService::ChangeState(this, 1u, 1, v39);
  McGenEventUnregister_EventUnregister();
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x18000d380  mov     [rsp+arg_8], rbx
0x18000d385  mov     [rsp+arg_18], rbp
0x18000d38a  push    rsi
0x18000d38b  push    rdi
0x18000d38c  push    r12
0x18000d38e  push    r14
0x18000d390  push    r15
0x18000d392  sub     rsp, 300h
0x18000d399  mov     rax, cs:__security_cookie
0x18000d3a0  xor     rax, rsp
0x18000d3a3  mov     [rsp+328h+var_38], rax
0x18000d3ab  lea     rbx, [rcx+106C0h]
0x18000d3b2  mov     r12d, edx
0x18000d3b5  mov     rdi, rcx
0x18000d3b8  mov     esi, 1
0x18000d3bd  mov     eax, esi
0x18000d3bf  mov     rdx, rbx
0x18000d3c2  xchg    eax, [rcx+106B4h]
0x18000d3c8  lea     rcx, [rsp+328h+var_2F8]
0x18000d3cd  mov     ebp, r8d
0x18000d3d0  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x18000d3d5  mov     eax, esi
0x18000d3d7  lea     rcx, [rsp+328h+var_2F8]
0x18000d3dc  xchg    eax, [rbx+28h]
0x18000d3df  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000d3e4  mov     rcx, rbx
0x18000d3e7  call    ?Delete@?$CTimer@VCMadcapHandler@@@@AEAAXXZ; CTimer<CMadcapHandler>::Delete(void)
0x18000d3ec  lea     rcx, [rsp+328h+var_2F8]
0x18000d3f1  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000d3f6  cmp     [rsp+328h+var_2F0], 0
0x18000d3fb  jz      short loc_18000D424
0x18000d3fd  and     [rsp+328h+var_308], 0
0x18000d402  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000d409  mov     r9d, esi
0x18000d40c  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x18000d413  mov     edx, 16Bh
0x18000d418  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000d41f  nop     dword ptr [rax+rax+00h]
0x18000d424  lea     rcx, [rdi+38h]; this
0x18000d428  call    ?Shutdown@CInterfaceMonitor@@QEAAKXZ; CInterfaceMonitor::Shutdown(void)
0x18000d42d  mov     ecx, eax
0x18000d42f  mov     r9d, 0A3h
0x18000d435  call    ElValidateWin32_3
0x18000d43a  lea     rcx, [rdi+488h]; this
0x18000d441  call    ?ShutdownPhysicalEndpoints@CUdpHandler@@QEAAKXZ; CUdpHandler::ShutdownPhysicalEndpoints(void)
0x18000d446  mov     ecx, eax
0x18000d448  mov     r9d, 0A8h
0x18000d44e  call    ElValidateWin32_3
0x18000d453  xor     ebx, ebx
0x18000d455  cmp     [rdi+10590h], rbx
0x18000d45c  jz      loc_18000D55E
0x18000d462  xor     ecx, ecx; Binding
0x18000d464  call    cs:__imp_RpcMgmtStopServerListening
0x18000d46b  nop     dword ptr [rax+rax+00h]
0x18000d470  lea     rsi, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x18000d477  mov     r9d, 148h
0x18000d47d  mov     r8, rsi
0x18000d480  mov     ecx, eax
0x18000d482  mov     ebx, eax
0x18000d484  call    ElValidateWin32
0x18000d489  test    eax, eax
0x18000d48b  jnz     loc_18000D538
0x18000d491  mov     rcx, [rdi+10590h]; hHandle
0x18000d498  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d49b  call    cs:__imp_WaitForSingleObject
0x18000d4a2  nop     dword ptr [rax+rax+00h]
0x18000d4a7  test    eax, eax
0x18000d4a9  jz      short loc_18000D4CB
0x18000d4ab  call    cs:__imp_GetLastError
0x18000d4b2  nop     dword ptr [rax+rax+00h]
0x18000d4b7  mov     r9d, 150h
0x18000d4bd  mov     r8, rsi
0x18000d4c0  mov     ecx, eax
0x18000d4c2  call    ElValidateWin32
0x18000d4c7  mov     ebx, eax
0x18000d4c9  jmp     short loc_18000D538
0x18000d4cb  lea     r8, aRpcListenStopp; "[RPC] Listen Stopped."
0x18000d4d2  mov     edx, 20000h
0x18000d4d7  lea     rcx, qword_180039310
0x18000d4de  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d4e5  nop     dword ptr [rax+rax+00h]
0x18000d4ea  xor     r8d, r8d; WaitForCallsToComplete
0x18000d4ed  lea     rcx, qword_18001E7F0; IfSpec
0x18000d4f4  xor     edx, edx; MgrTypeUuid
0x18000d4f6  call    cs:__imp_RpcServerUnregisterIf
0x18000d4fd  nop     dword ptr [rax+rax+00h]
0x18000d502  mov     r9d, 15Dh
0x18000d508  mov     r8, rsi
0x18000d50b  mov     ecx, eax
0x18000d50d  mov     ebx, eax
0x18000d50f  call    ElValidateWin32
0x18000d514  test    eax, eax
0x18000d516  jnz     short loc_18000D538
0x18000d518  mov     rcx, [rdi+10590h]; hObject
0x18000d51f  test    rcx, rcx
0x18000d522  jz      short loc_18000D538
0x18000d524  call    cs:__imp_CloseHandle
0x18000d52b  nop     dword ptr [rax+rax+00h]
0x18000d530  and     qword ptr [rdi+10590h], 0
0x18000d538  test    ebx, ebx
0x18000d53a  jz      short loc_18000D55E
0x18000d53c  mov     r9d, ebx
0x18000d53f  lea     r8, aRpcFailedToSto; "[RPC] Failed to stop Listen (rc=%u)"
0x18000d546  mov     edx, 80000h
0x18000d54b  lea     rcx, qword_180039310
0x18000d552  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d559  nop     dword ptr [rax+rax+00h]
0x18000d55e  mov     r9d, 0ADh
0x18000d564  mov     ecx, ebx
0x18000d566  call    ElValidateWin32_3
0x18000d56b  xor     ecx, ecx
0x18000d56d  mov     r9d, 30Bh
0x18000d573  call    ElValidateWin32_0
0x18000d578  mov     rcx, rdi; this
0x18000d57b  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d580  lea     rcx, [rdi+10668h]
0x18000d587  call    cs:__imp_?Shutdown@CCompPort@@QEAAKXZ; CCompPort::Shutdown(void)
0x18000d58e  nop     dword ptr [rax+rax+00h]
0x18000d593  xor     ecx, ecx
0x18000d595  mov     r9d, 319h
0x18000d59b  call    ElValidateWin32_0
0x18000d5a0  mov     rcx, rdi; this
0x18000d5a3  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d5a8  lea     rsi, [rdi+10600h]
0x18000d5af  mov     rcx, rsi; lpCriticalSection
0x18000d5b2  call    cs:__imp_EnterCriticalSection
0x18000d5b9  nop     dword ptr [rax+rax+00h]
0x18000d5be  mov     rcx, rsi; lpCriticalSection
0x18000d5c1  call    cs:__imp_EnterCriticalSection
0x18000d5c8  nop     dword ptr [rax+rax+00h]
0x18000d5cd  mov     rbx, [rdi+105F0h]
0x18000d5d4  mov     rcx, rsi; lpCriticalSection
0x18000d5d7  call    cs:__imp_LeaveCriticalSection
0x18000d5de  nop     dword ptr [rax+rax+00h]
0x18000d5e3  test    rbx, rbx
0x18000d5e6  jz      loc_18000D712
0x18000d5ec  mov     rbx, [rdi+105F8h]
0x18000d5f3  jmp     loc_18000D709
0x18000d5f8  mov     rax, [rdi+105F0h]
0x18000d5ff  mov     rcx, [rdi+105F8h]
0x18000d606  cmp     rax, rcx
0x18000d609  jnz     short loc_18000D61D
0x18000d60b  and     qword ptr [rdi+105F8h], 0
0x18000d613  and     qword ptr [rdi+105F0h], 0
0x18000d61b  jmp     short loc_18000D681
0x18000d61d  cmp     rbx, rax
0x18000d620  jnz     short loc_18000D63A
0x18000d622  mov     rax, [rax+110h]
0x18000d629  mov     [rdi+105F0h], rax
0x18000d630  and     qword ptr [rax+118h], 0
0x18000d638  jmp     short loc_18000D681
0x18000d63a  cmp     rbx, rcx
0x18000d63d  jnz     short loc_18000D657
0x18000d63f  mov     rax, [rcx+118h]
0x18000d646  mov     [rdi+105F8h], rax
0x18000d64d  and     qword ptr [rax+110h], 0
0x18000d655  jmp     short loc_18000D681
0x18000d657  mov     rcx, [rbx+118h]
0x18000d65e  mov     rax, [rbx+110h]
0x18000d665  mov     [rcx+110h], rax
0x18000d66c  mov     rcx, [rbx+110h]
0x18000d673  mov     rax, [rbx+118h]
0x18000d67a  mov     [rcx+118h], rax
0x18000d681  dec     dword ptr [rdi+10628h]
0x18000d687  mov     rcx, rsi; lpCriticalSection
0x18000d68a  mov     r14, rbx
0x18000d68d  call    cs:__imp_EnterCriticalSection
0x18000d694  nop     dword ptr [rax+rax+00h]
0x18000d699  mov     rbx, [rdi+105F0h]
0x18000d6a0  mov     rcx, rsi; lpCriticalSection
0x18000d6a3  call    cs:__imp_LeaveCriticalSection
0x18000d6aa  nop     dword ptr [rax+rax+00h]
0x18000d6af  test    rbx, rbx
0x18000d6b2  jz      short loc_18000D6BB
0x18000d6b4  mov     rbx, [rdi+105F8h]
0x18000d6bb  mov     r9, [r14+10h]
0x18000d6bf  lea     r8, aSShuttingDown; "[%s] Shutting down"
0x18000d6c6  mov     edx, 20000h
0x18000d6cb  lea     rcx, qword_180039310
0x18000d6d2  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d6d9  nop     dword ptr [rax+rax+00h]
0x18000d6de  mov     rcx, r14; this
0x18000d6e1  call    ?Shutdown@CWdsProvider@@QEAAKXZ; CWdsProvider::Shutdown(void)
0x18000d6e6  mov     ecx, eax
0x18000d6e8  lea     r8, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18000d6ef  mov     r9d, 222h
0x18000d6f5  call    ElValidateWin32
0x18000d6fa  mov     rax, [r14]
0x18000d6fd  mov     rcx, r14
0x18000d700  mov     rax, [rax+8]
0x18000d704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d709  test    rbx, rbx
0x18000d70c  jnz     loc_18000D5F8
0x18000d712  mov     rcx, rsi; lpCriticalSection
0x18000d715  call    cs:__imp_LeaveCriticalSection
0x18000d71c  nop     dword ptr [rax+rax+00h]
0x18000d721  xor     ecx, ecx
0x18000d723  mov     r9d, 322h
0x18000d729  call    ElValidateWin32_0
0x18000d72e  mov     rcx, rdi; this
0x18000d731  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d736  lea     rcx, [rdi+30h]; this
0x18000d73a  call    ?Shutdown@CInterfaceHandler@@QEAAKXZ; CInterfaceHandler::Shutdown(void)
0x18000d73f  mov     r9d, 32Bh
0x18000d745  mov     ecx, eax
0x18000d747  mov     ebx, eax
0x18000d749  call    ElValidateWin32_0
0x18000d74e  xor     esi, esi
0x18000d750  mov     rcx, rdi; this
0x18000d753  test    eax, eax
0x18000d755  cmovnz  esi, ebx
0x18000d758  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d75d  call    cs:__imp_WSACleanup
0x18000d764  nop     dword ptr [rax+rax+00h]
0x18000d769  test    eax, eax
0x18000d76b  jz      short loc_18000D788
0x18000d76d  call    cs:__imp_WSAGetLastError
0x18000d774  nop     dword ptr [rax+rax+00h]
0x18000d779  mov     ecx, eax
0x18000d77b  mov     r9d, 334h
0x18000d781  call    ElValidateWin32_0
0x18000d786  mov     esi, eax
0x18000d788  mov     rcx, rdi; this
0x18000d78b  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d790  cmp     cs:dword_180028178, 0
0x18000d797  jz      short loc_18000D7AC
0x18000d799  lea     rcx, off_180028160
0x18000d7a0  call    cs:__imp_?Uninitialize@CVssJetWriter@@QEAAXXZ; CVssJetWriter::Uninitialize(void)
0x18000d7a7  nop     dword ptr [rax+rax+00h]
0x18000d7ac  and     cs:dword_180028178, 0
0x18000d7b3  xor     ecx, ecx
0x18000d7b5  mov     r9d, 275h
0x18000d7bb  call    ElValidateHr
0x18000d7c0  test    eax, eax
0x18000d7c2  js      short loc_18000D7D0
0x18000d7c4  call    cs:__imp_CoUninitialize
0x18000d7cb  nop     dword ptr [rax+rax+00h]
0x18000d7d0  xor     ecx, ecx
0x18000d7d2  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000d7d9  nop     dword ptr [rax+rax+00h]
0x18000d7de  mov     ecx, eax
0x18000d7e0  mov     r9d, 33Ch
0x18000d7e6  mov     ebx, eax
0x18000d7e8  call    ElValidateWin32_0
0x18000d7ed  test    eax, eax
0x18000d7ef  mov     rcx, rdi; this
0x18000d7f2  cmovnz  esi, ebx
0x18000d7f5  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d7fa  test    ebp, ebp
0x18000d7fc  lea     r14, qword_180039300
0x18000d803  cmovnz  esi, ebp
0x18000d806  test    r12d, r12d
0x18000d809  jz      short loc_18000D82F
0x18000d80b  mov     rcx, r14
0x18000d80e  test    esi, esi
0x18000d810  jnz     short loc_18000D828
0x18000d812  xor     r8d, r8d
0x18000d815  mov     edx, 41010102h
0x18000d81a  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000d821  nop     dword ptr [rax+rax+00h]
0x18000d826  jmp     short loc_18000D855
0x18000d828  mov     edx, 0C1010103h
0x18000d82d  jmp     short loc_18000D83B
0x18000d82f  test    ebp, ebp
0x18000d831  jz      short loc_18000D855
0x18000d833  mov     edx, 0C1010101h
0x18000d838  mov     rcx, r14
0x18000d83b  mov     r9d, 5
0x18000d841  mov     [rsp+328h+var_308], esi
0x18000d845  lea     r8d, [r9-4]
0x18000d849  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000d850  nop     dword ptr [rax+rax+00h]
0x18000d855  xor     edx, edx; Val
0x18000d857  lea     rcx, [rsp+328h+var_2D4]; void *
0x18000d85c  mov     r8d, 29Ch; Size
0x18000d862  call    memset_0
0x18000d867  movups  xmm0, cs:SumGuid_WDS
0x18000d86e  mov     [rsp+328h+var_2E8], 2B0h
0x18000d876  movdqu  [rsp+328h+var_2E4], xmm0
0x18000d87c  call    ?DelayLoadUalApi@@YAHXZ; DelayLoadUalApi(void)
0x18000d881  test    eax, eax
0x18000d883  jz      short loc_18000D896
0x18000d885  lea     rcx, [rsp+328h+var_2E8]
0x18000d88a  call    cs:__imp_UalStop
0x18000d891  nop     dword ptr [rax+rax+00h]
0x18000d896  mov     rcx, rdi; this
0x18000d899  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d89e  mov     rcx, r14
0x18000d8a1  call    cs:__imp_?Shutdown@CEventLog@@QEAAKXZ; CEventLog::Shutdown(void)
0x18000d8a8  nop     dword ptr [rax+rax+00h]
0x18000d8ad  mov     rcx, rdi; this
0x18000d8b0  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d8b5  call    cs:__imp_?WdsDiagShutdown@@YAKXZ; WdsDiagShutdown(void)
0x18000d8bc  nop     dword ptr [rax+rax+00h]
0x18000d8c1  mov     rcx, rdi; this
0x18000d8c4  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000d8c9  lea     rcx, qword_180039310
0x18000d8d0  call    cs:__imp_?Shutdown@CTrace@@QEAAKXZ; CTrace::Shutdown(void)
0x18000d8d7  nop     dword ptr [rax+rax+00h]
0x18000d8dc  mov     rcx, rdi; this
  ... truncated ...
```
