# CRpcHandler::Initialize(CInterfaceMonitor *,CMulticastHandler *)

- ea: `0x1800042f0`
- end: `0x180004812`
- name: `?Initialize@CRpcHandler@@UEAAKPEAVCInterfaceMonitor@@PEAVCMulticastHandler@@@Z`
- size: `1314`
- prototype: `unsigned int __fastcall(CRpcHandler *__hidden this, struct CInterfaceMonitor *, struct CMulticastHandler *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000195c`
- `0x180003944`
- `0x180003d70`
- `0x1800042f0`
- `0x180004818`
- `0x18000625c`
- `0x18000e310`

## import_xrefs

- `msvcrt!clock` at `0x1800045de`
- `msvcrt!clock` at `0x1800045ec`
- `msvcrt!clock` at `0x18000467d`
- `msvcrt!clock` at `0x1800045de`
- `msvcrt!clock` at `0x1800045ec`
- `msvcrt!clock` at `0x18000467d`
- `KERNEL32!GetLastError` at `0x1800047d7`
- `KERNEL32!GetLastError` at `0x1800047d7`
- `KERNEL32!InterlockedPushEntrySList` at `0x180004379`
- `KERNEL32!InterlockedPushEntrySList` at `0x180004379`
- `KERNEL32!SleepEx` at `0x180004665`
- `KERNEL32!SleepEx` at `0x180004665`
- `KERNEL32!CreateThread` at `0x1800047b5`
- `KERNEL32!CreateThread` at `0x1800047b5`
- `ADVAPI32!RegOpenKeyExW` at `0x180004406`
- `ADVAPI32!RegOpenKeyExW` at `0x180004406`
- `ADVAPI32!RegCloseKey` at `0x1800043d6`
- `ADVAPI32!RegCloseKey` at `0x18000454e`
- `ADVAPI32!RegCloseKey` at `0x1800043d6`
- `ADVAPI32!RegCloseKey` at `0x18000454e`
- `RPCRT4!RpcBindingVectorFree` at `0x18000450b`
- `RPCRT4!RpcBindingVectorFree` at `0x18000450b`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180004777`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180004777`
- `RPCRT4!RpcEpRegisterW` at `0x180004721`
- `RPCRT4!RpcEpRegisterW` at `0x180004721`
- `RPCRT4!RpcServerInqBindings` at `0x1800046ea`
- `RPCRT4!RpcServerInqBindings` at `0x1800046ea`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800046c0`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800046c0`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000461b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000461b`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004520`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004535`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004520`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004535`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004465`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800044c1`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004599`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000464f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004801`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004465`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800044c1`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004599`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000464f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004801`
- `WdsServerCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000443e`
- `WdsServerCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180004486`
- `WdsServerCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000443e`
- `WdsServerCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180004486`
- `WdsServerCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x1800045b8`
- `WdsServerCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x1800045b8`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800044f5`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800044f5`

## string_xrefs

- `0x1800043f8`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x18000447b`: `EnableImpersonateLogging`
- `0x18000458f`: `[RPC] Client Impersonation Logging=%s`

## pseudocode

```c
__int64 __fastcall CRpcHandler::Initialize(
        CRpcHandler *this,
        struct CInterfaceMonitor *a2,
        struct CMulticastHandler *a3)
{
  unsigned int v4; // r15d
  int v5; // r14d
  struct _SLIST_ENTRY *v6; // rax
  __int64 v7; // rdx
  struct _SLIST_ENTRY *v8; // rbx
  DWORD ValueDword; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int *v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // rdx
  const wchar_t *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rdx
  clock_t v19; // edi
  unsigned int v20; // eax
  __int64 v21; // rdx
  DWORD v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // edx
  CRpcHandler *v30; // rcx
  unsigned int Spn; // eax
  __int64 v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rdx
  HANDLE Thread; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-40h]
  RPC_IF_CALLBACK_FN *IfCallback; // [rsp+28h] [rbp-38h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-20h] BYREF
  RPC_WSTR Endpoint; // [rsp+48h] [rbp-18h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+58h] BYREF

  ServerPrincName = 0;
  v4 = 0;
  Endpoint = 0;
  v5 = 0;
  BindingVector = 0;
  hKey = 0;
  while ( 1 )
  {
    v6 = (struct _SLIST_ENTRY *)operator new(0x900u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v6;
    if ( !v6 )
      break;
    *((_QWORD *)&v6[138].Next + 1) = 0;
    v6[139].Next = 0;
    *((_DWORD *)&v6[139].Next + 3) = 0;
    *((_QWORD *)&v6[141].Next + 1) = 0;
    v6[142].Next = 0;
    v6[138].Next = 0;
    RpcRequest::Cleanup((RpcRequest *)v6);
    InterlockedPushEntrySList((PSLIST_HEADER)this + 2, v8 + 143);
    _InterlockedIncrement((volatile signed __int32 *)this + 12);
    if ( (unsigned int)++v5 >= 0x100 )
    {
      *((_DWORD *)this + 17) = 1024;
      goto LABEL_6;
    }
  }
  v4 = 8;
LABEL_6:
  ValueDword = ElValidateWin32(v4, v7, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 60);
  if ( ValueDword )
    goto LABEL_13;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
          0,
          0x20119u,
          &hKey);
  ValueDword = ElValidateWin32(v10, v11, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 69);
  if ( ValueDword )
    goto LABEL_13;
  v12 = (unsigned int *)((char *)this + 88);
  ValueDword = CRegKey::GetValueDword((CRegKey *)&hKey, L"RpcPort", (unsigned int *)this + 22);
  if ( (ValueDword & 0xFFFFFFFD) != 0 )
    goto LABEL_13;
  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Using Tcp Port %u for Rpc Calls.", *v12);
  v13 = CRegKey::GetValueDword((CRegKey *)&hKey, L"EnableImpersonateLogging", (unsigned int *)this + 40);
  ValueDword = v13;
  if ( (v13 & 0xFFFFFFFD) != 0 )
  {
    ElValidateWin32(v13, v14, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 91);
LABEL_13:
    CTrace::Trace((CTrace *)qword_180039310, 0x100000u, L"[RPC] Initialization Failed (rc=%u)", ValueDword);
    LODWORD(IfCallback) = 5;
    LODWORD(phkResult) = *((_DWORD *)this + 22);
    CEventLog::Log((CEventLog *)qword_180039300, 0xC1010400, 2, 2, phkResult, IfCallback, ValueDword);
    goto LABEL_14;
  }
  v16 = L"Enabled";
  if ( !*((_DWORD *)this + 40) )
    v16 = L"Disabled";
  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Client Impersonation Logging=%s", v16);
  v17 = FormatString(&Endpoint, 0x10u, L"%u", *v12);
  ValueDword = ElValidateWin32(v17, v18, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 105);
  if ( ValueDword )
    goto LABEL_13;
  v19 = clock();
  if ( clock() - v19 < 120000 )
  {
    while ( 1 )
    {
      v20 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_ip_tcp", 0xAu, Endpoint, 0);
      v22 = ElValidateWin32(v20, v21, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 120);
      ValueDword = v22;
      if ( v22 != 1740 )
        break;
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Duplicate endpoint detected. Retrying in 2 seconds.");
      SleepEx(0x7D0u, 1);
      CWdsService::UpdateProgress((CWdsService *)&qword_180028BD0);
      if ( clock() - v19 >= 120000 )
        goto LABEL_13;
    }
    if ( v22 )
      goto LABEL_13;
  }
  v23 = RpcServerRegisterIfEx(qword_18001E7F0, 0, 0, 0x10u, 0x4D2u, 0);
  ValueDword = ElValidateWin32(v23, v24, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 159);
  if ( ValueDword )
    goto LABEL_13;
  v25 = RpcServerInqBindings(&BindingVector);
  ValueDword = ElValidateWin32(v25, v26, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 168);
  if ( ValueDword )
    goto LABEL_13;
  v27 = RpcEpRegisterW(qword_18001E7F0, BindingVector, 0, 0);
  ValueDword = ElValidateWin32(v27, v28, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 178);
  if ( ValueDword )
    goto LABEL_13;
  Spn = CRpcHandler::MakeSpn(v30, v29, &ServerPrincName);
  ValueDword = ElValidateWin32(Spn, v32, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 186);
  if ( ValueDword )
    goto LABEL_13;
  v33 = RpcServerRegisterAuthInfoW(ServerPrincName, 9u, 0, 0);
  ValueDword = ElValidateWin32(v33, v34, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 193);
  if ( ValueDword )
    goto LABEL_13;
  Thread = CreateThread(0, 0, CRpcHandler::_ServerThread, this, 0, 0);
  *((_QWORD *)this + 10) = Thread;
  if ( (unsigned int)ElValidateGleTrue(Thread == 0) )
  {
    ValueDword = GetLastError();
    if ( ValueDword )
      goto LABEL_13;
  }
  else
  {
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Initialized");
  }
LABEL_14:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( ServerPrincName )
    WdsPrivateHpFree(ServerPrincName);
  if ( Endpoint )
  {
    WdsPrivateHpFree(Endpoint);
    Endpoint = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return ValueDword;
}

```

## disassembly

```asm
0x1800042f0  mov     [rsp-38h+arg_8], rbx
0x1800042f5  push    rbp
0x1800042f6  push    rsi
0x1800042f7  push    rdi
0x1800042f8  push    r12
0x1800042fa  push    r13
0x1800042fc  push    r14
0x1800042fe  push    r15
0x180004300  mov     rbp, rsp
0x180004303  sub     rsp, 60h
0x180004307  xor     r12d, r12d
0x18000430a  mov     rsi, rcx
0x18000430d  mov     [rbp+ServerPrincName], r12
0x180004311  mov     r15d, r12d
0x180004314  mov     [rbp+Endpoint], r12
0x180004318  mov     r14d, r12d
0x18000431b  mov     [rbp+BindingVector], r12
0x18000431f  mov     [rbp+hKey], r12
0x180004323  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000432a  mov     ecx, 900h; unsigned __int64
0x18000432f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004334  mov     rbx, rax
0x180004337  test    rax, rax
0x18000433a  jz      short loc_18000439E
0x18000433c  mov     rcx, rax; this
0x18000433f  mov     [rax+8A8h], r12
0x180004346  mov     [rax+8B0h], r12
0x18000434d  mov     [rax+8BCh], r12d
0x180004354  mov     [rax+8D8h], r12
0x18000435b  mov     [rax+8E0h], r12
0x180004362  mov     [rax+8A0h], r12
0x180004369  call    ?Cleanup@RpcRequest@@QEAAXXZ; RpcRequest::Cleanup(void)
0x18000436e  lea     rdx, [rbx+8F0h]; ListEntry
0x180004375  lea     rcx, [rsi+20h]; ListHead
0x180004379  call    cs:__imp_InterlockedPushEntrySList
0x180004380  nop     dword ptr [rax+rax+00h]
0x180004385  lock inc dword ptr [rsi+30h]
0x180004389  inc     r14d
0x18000438c  cmp     r14d, 100h
0x180004393  jb      short loc_180004323
0x180004395  mov     dword ptr [rsi+44h], 400h
0x18000439c  jmp     short loc_1800043A4
0x18000439e  mov     r15d, 8
0x1800043a4  lea     r13, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x1800043ab  mov     r9d, 3Ch ; '<'
0x1800043b1  mov     r8, r13
0x1800043b4  mov     ecx, r15d
0x1800043b7  call    ElValidateWin32
0x1800043bc  lea     r15, qword_180039310
0x1800043c3  mov     ebx, eax
0x1800043c5  test    eax, eax
0x1800043c7  jnz     loc_1800044AF
0x1800043cd  mov     rcx, [rbp+hKey]; hKey
0x1800043d1  test    rcx, rcx
0x1800043d4  jz      short loc_1800043E6
0x1800043d6  call    cs:__imp_RegCloseKey
0x1800043dd  nop     dword ptr [rax+rax+00h]
0x1800043e2  mov     [rbp+hKey], r12
0x1800043e6  lea     rax, [rbp+hKey]
0x1800043ea  mov     r9d, 20119h; samDesired
0x1800043f0  xor     r8d, r8d; ulOptions
0x1800043f3  mov     [rsp+60h+phkResult], rax; phkResult
0x1800043f8  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800043ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004406  call    cs:__imp_RegOpenKeyExW
0x18000440d  nop     dword ptr [rax+rax+00h]
0x180004412  mov     r9d, 45h ; 'E'
0x180004418  mov     r8, r13
0x18000441b  mov     ecx, eax
0x18000441d  call    ElValidateWin32
0x180004422  mov     ebx, eax
0x180004424  test    eax, eax
0x180004426  jnz     loc_1800044AF
0x18000442c  lea     rdi, [rsi+58h]
0x180004430  mov     r8, rdi
0x180004433  lea     rdx, aRpcport; "RpcPort"
0x18000443a  lea     rcx, [rbp+hKey]
0x18000443e  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180004445  nop     dword ptr [rax+rax+00h]
0x18000444a  mov     ebx, eax
0x18000444c  test    eax, 0FFFFFFFDh
0x180004451  jnz     short loc_1800044AF
0x180004453  mov     r9d, [rdi]
0x180004456  lea     r8, aRpcUsingTcpPor; "[RPC] Using Tcp Port %u for Rpc Calls."
0x18000445d  mov     edx, 20000h
0x180004462  mov     rcx, r15
0x180004465  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000446c  nop     dword ptr [rax+rax+00h]
0x180004471  lea     r14, [rsi+0A0h]
0x180004478  mov     r8, r14
0x18000447b  lea     rdx, aEnableimperson; "EnableImpersonateLogging"
0x180004482  lea     rcx, [rbp+hKey]
0x180004486  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000448d  nop     dword ptr [rax+rax+00h]
0x180004492  mov     ebx, eax
0x180004494  test    eax, 0FFFFFFFDh
0x180004499  jz      loc_180004575
0x18000449f  mov     r9d, 5Bh ; '['
0x1800044a5  mov     r8, r13
0x1800044a8  mov     ecx, eax
0x1800044aa  call    ElValidateWin32
0x1800044af  mov     r9d, ebx
0x1800044b2  lea     r8, aRpcInitializat; "[RPC] Initialization Failed (rc=%u)"
0x1800044b9  mov     edx, 100000h
0x1800044be  mov     rcx, r15
0x1800044c1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800044c8  nop     dword ptr [rax+rax+00h]
0x1800044cd  mov     eax, [rsi+58h]
0x1800044d0  lea     rcx, qword_180039300
0x1800044d7  mov     r8d, 2
0x1800044dd  mov     [rsp+60h+var_30], ebx
0x1800044e1  mov     r9d, r8d
0x1800044e4  mov     dword ptr [rsp+60h+IfCallback], 5
0x1800044ec  mov     edx, 0C1010400h
0x1800044f1  mov     dword ptr [rsp+60h+phkResult], eax
0x1800044f5  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800044fc  nop     dword ptr [rax+rax+00h]
0x180004501  cmp     [rbp+BindingVector], r12
0x180004505  jz      short loc_180004517
0x180004507  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000450b  call    cs:__imp_RpcBindingVectorFree
0x180004512  nop     dword ptr [rax+rax+00h]
0x180004517  mov     rcx, [rbp+ServerPrincName]
0x18000451b  test    rcx, rcx
0x18000451e  jz      short loc_18000452C
0x180004520  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180004527  nop     dword ptr [rax+rax+00h]
0x18000452c  mov     rcx, [rbp+Endpoint]
0x180004530  test    rcx, rcx
0x180004533  jz      short loc_180004545
0x180004535  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000453c  nop     dword ptr [rax+rax+00h]
0x180004541  mov     [rbp+Endpoint], r12
0x180004545  mov     rcx, [rbp+hKey]; hKey
0x180004549  test    rcx, rcx
0x18000454c  jz      short loc_18000455A
0x18000454e  call    cs:__imp_RegCloseKey
0x180004555  nop     dword ptr [rax+rax+00h]
0x18000455a  mov     eax, ebx
0x18000455c  mov     rbx, [rsp+60h+arg_8]
0x180004564  add     rsp, 60h
0x180004568  pop     r15
0x18000456a  pop     r14
0x18000456c  pop     r13
0x18000456e  pop     r12
0x180004570  pop     rdi
0x180004571  pop     rsi
0x180004572  pop     rbp
0x180004573  retn
0x180004575  cmp     [r14], r12d
0x180004578  lea     rax, aDisabled; "Disabled"
0x18000457f  lea     r9, aEnabled; "Enabled"
0x180004586  mov     edx, 20000h
0x18000458b  cmovz   r9, rax
0x18000458f  lea     r8, aRpcClientImper; "[RPC] Client Impersonation Logging=%s"
0x180004596  mov     rcx, r15
0x180004599  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800045a0  nop     dword ptr [rax+rax+00h]
0x1800045a5  mov     r9d, [rdi]
0x1800045a8  lea     r8, aU; "%u"
0x1800045af  mov     edx, 10h
0x1800045b4  lea     rcx, [rbp+Endpoint]
0x1800045b8  call    cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x1800045bf  nop     dword ptr [rax+rax+00h]
0x1800045c4  mov     r9d, 69h ; 'i'
0x1800045ca  mov     r8, r13
0x1800045cd  mov     ecx, eax
0x1800045cf  call    ElValidateWin32
0x1800045d4  mov     ebx, eax
0x1800045d6  test    eax, eax
0x1800045d8  jnz     loc_1800044AF
0x1800045de  call    cs:__imp_clock
0x1800045e5  nop     dword ptr [rax+rax+00h]
0x1800045ea  mov     edi, eax
0x1800045ec  call    cs:__imp_clock
0x1800045f3  nop     dword ptr [rax+rax+00h]
0x1800045f8  sub     eax, edi
0x1800045fa  mov     r14d, 1D4C0h
0x180004600  cmp     eax, r14d
0x180004603  jge     loc_1800046A1
0x180004609  mov     r8, [rbp+Endpoint]; Endpoint
0x18000460d  lea     rcx, Protseq; "ncacn_ip_tcp"
0x180004614  xor     r9d, r9d; SecurityDescriptor
0x180004617  lea     edx, [r9+0Ah]; MaxCalls
0x18000461b  call    cs:__imp_RpcServerUseProtseqEpW
0x180004622  nop     dword ptr [rax+rax+00h]
0x180004627  mov     r9d, 78h ; 'x'
0x18000462d  mov     r8, r13
0x180004630  mov     ecx, eax
0x180004632  call    ElValidateWin32
0x180004637  mov     ebx, eax
0x180004639  cmp     eax, 6CCh
0x18000463e  jnz     short loc_180004699
0x180004640  lea     r8, aDuplicateEndpo; "Duplicate endpoint detected. Retrying i"...
0x180004647  mov     edx, 20000h
0x18000464c  mov     rcx, r15
0x18000464f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180004656  nop     dword ptr [rax+rax+00h]
0x18000465b  mov     edx, 1; bAlertable
0x180004660  mov     ecx, 7D0h; dwMilliseconds
0x180004665  call    cs:__imp_SleepEx
0x18000466c  nop     dword ptr [rax+rax+00h]
0x180004671  lea     rcx, qword_180028BD0; this
0x180004678  call    ?UpdateProgress@CWdsService@@QEAAKXZ; CWdsService::UpdateProgress(void)
0x18000467d  call    cs:__imp_clock
0x180004684  nop     dword ptr [rax+rax+00h]
0x180004689  sub     eax, edi
0x18000468b  cmp     eax, r14d
0x18000468e  jl      loc_180004609
0x180004694  jmp     loc_1800044AF
0x180004699  test    eax, eax
0x18000469b  jnz     loc_1800044AF
0x1800046a1  mov     [rsp+60h+IfCallback], r12; IfCallback
0x1800046a6  lea     rcx, qword_18001E7F0; IfSpec
0x1800046ad  mov     r9d, 10h; Flags
0x1800046b3  mov     dword ptr [rsp+60h+phkResult], 4D2h; MaxCalls
0x1800046bb  xor     r8d, r8d; MgrEpv
0x1800046be  xor     edx, edx; MgrTypeUuid
0x1800046c0  call    cs:__imp_RpcServerRegisterIfEx
0x1800046c7  nop     dword ptr [rax+rax+00h]
0x1800046cc  mov     r9d, 9Fh
0x1800046d2  mov     r8, r13
0x1800046d5  mov     ecx, eax
0x1800046d7  call    ElValidateWin32
0x1800046dc  mov     ebx, eax
0x1800046de  test    eax, eax
0x1800046e0  jnz     loc_1800044AF
0x1800046e6  lea     rcx, [rbp+BindingVector]; BindingVector
0x1800046ea  call    cs:__imp_RpcServerInqBindings
0x1800046f1  nop     dword ptr [rax+rax+00h]
0x1800046f6  mov     r9d, 0A8h
0x1800046fc  mov     r8, r13
0x1800046ff  mov     ecx, eax
0x180004701  call    ElValidateWin32
0x180004706  mov     ebx, eax
0x180004708  test    eax, eax
0x18000470a  jnz     loc_1800044AF
0x180004710  mov     rdx, [rbp+BindingVector]; BindingVector
0x180004714  lea     rcx, qword_18001E7F0; IfSpec
0x18000471b  xor     r9d, r9d; Annotation
0x18000471e  xor     r8d, r8d; UuidVector
0x180004721  call    cs:__imp_RpcEpRegisterW
0x180004728  nop     dword ptr [rax+rax+00h]
0x18000472d  mov     r9d, 0B2h
0x180004733  mov     r8, r13
0x180004736  mov     ecx, eax
0x180004738  call    ElValidateWin32
0x18000473d  mov     ebx, eax
0x18000473f  test    eax, eax
0x180004741  jnz     loc_1800044AF
0x180004747  lea     r8, [rbp+ServerPrincName]; unsigned __int16 **
0x18000474b  call    ?MakeSpn@CRpcHandler@@AEAAKKPEAPEAG@Z; CRpcHandler::MakeSpn(ulong,ushort * *)
0x180004750  mov     ecx, eax
0x180004752  mov     r9d, 0BAh
0x180004758  mov     r8, r13
0x18000475b  call    ElValidateWin32
0x180004760  mov     ebx, eax
0x180004762  test    eax, eax
0x180004764  jnz     loc_1800044AF
0x18000476a  mov     rcx, [rbp+ServerPrincName]; ServerPrincName
0x18000476e  lea     edx, [rax+9]; AuthnSvc
0x180004771  xor     r9d, r9d; Arg
0x180004774  xor     r8d, r8d; GetKeyFn
0x180004777  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18000477e  nop     dword ptr [rax+rax+00h]
0x180004783  mov     r9d, 0C1h
0x180004789  mov     r8, r13
0x18000478c  mov     ecx, eax
0x18000478e  call    ElValidateWin32
0x180004793  mov     ebx, eax
0x180004795  test    eax, eax
0x180004797  jnz     loc_1800044AF
0x18000479d  mov     [rsp+60h+IfCallback], r12; lpThreadId
0x1800047a2  lea     r8, ?_ServerThread@CRpcHandler@@SAKPEAX@Z; lpStartAddress
0x1800047a9  mov     r9, rsi; lpParameter
0x1800047ac  mov     dword ptr [rsp+60h+phkResult], r12d; dwCreationFlags
0x1800047b1  xor     edx, edx; dwStackSize
0x1800047b3  xor     ecx, ecx; lpThreadAttributes
0x1800047b5  call    cs:__imp_CreateThread
0x1800047bc  nop     dword ptr [rax+rax+00h]
0x1800047c1  test    rax, rax
0x1800047c4  mov     [rsi+50h], rax
0x1800047c8  mov     ecx, r12d
0x1800047cb  setz    cl
0x1800047ce  call    ElValidateGleTrue
0x1800047d3  test    eax, eax
0x1800047d5  jz      short loc_1800047F2
0x1800047d7  call    cs:__imp_GetLastError
0x1800047de  nop     dword ptr [rax+rax+00h]
0x1800047e3  mov     ebx, eax
0x1800047e5  test    eax, eax
0x1800047e7  jz      loc_180004501
0x1800047ed  jmp     loc_1800044AF
0x1800047f2  lea     r8, aRpcInitialized; "[RPC] Initialized"
0x1800047f9  mov     edx, 20000h
0x1800047fe  mov     rcx, r15
0x180004801  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180004808  nop     dword ptr [rax+rax+00h]
0x18000480d  jmp     loc_180004501
```
