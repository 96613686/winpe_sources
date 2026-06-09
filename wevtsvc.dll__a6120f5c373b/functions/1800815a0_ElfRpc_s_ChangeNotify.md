# ElfRpc_s_ChangeNotify

- ea: `0x1800815a0`
- end: `0x180081a91`
- name: `ElfRpc_s_ChangeNotify`
- size: `1265`
- prototype: `__int64 __fastcall(struct _IELF_HANDLE *, DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000104c`
- `0x180007edc`
- `0x180017c44`
- `0x180033ae0`
- `0x18003420c`
- `0x18003617c`
- `0x18005ff90`
- `0x180064854`
- `0x180066580`
- `0x1800781c4`
- `0x1800815a0`
- `0x180092008`
- `0x180092ee4`
- `0x18009aee0`
- `0x18009f6d8`
- `0x1800a7b60`
- `0x1800c4b68`
- `0x1800c4c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800818b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008197b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800818b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008197b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800818ae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800818ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008188a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008188a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008184c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008184c`
- `RPCRT4!RpcImpersonateClient` at `0x1800817ef`
- `RPCRT4!RpcImpersonateClient` at `0x1800817ef`
- `RPCRT4!RpcRevertToSelf` at `0x18008185f`
- `RPCRT4!RpcRevertToSelf` at `0x18008185f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180081830`
- `RPCRT4!I_RpcMapWin32Status` at `0x180081830`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ElfRpc_s_ChangeNotify(struct _IELF_HANDLE *a1, DWORD dwProcessId, int a3)
{
  void *v3; // r12
  _DWORD *v6; // r9
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  __int64 v10; // r15
  struct LOGFILE *v11; // rcx
  int v12; // eax
  unsigned int RpcClientPid; // eax
  unsigned int v14; // eax
  RPC_STATUS v15; // edi
  HANDLE v16; // rax
  HANDLE v17; // rbx
  HANDLE *v18; // rdi
  HANDLE CurrentProcess; // rax
  DWORD v20; // ebx
  __int64 v21; // rax
  DWORD LastError; // edi
  int v23; // ebx
  const char *v25; // r9
  unsigned int v26; // ebx
  int v27; // [rsp+40h] [rbp-A8h] BYREF
  HANDLE hSourceProcessHandle; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-98h] BYREF
  __int64 v30; // [rsp+58h] [rbp-90h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-88h] BYREF
  char v32; // [rsp+70h] [rbp-78h]
  EvtException *v33; // [rsp+78h] [rbp-70h] BYREF
  int v34; // [rsp+80h] [rbp-68h] BYREF
  char v35; // [rsp+84h] [rbp-64h]
  char v36; // [rsp+88h] [rbp-60h] BYREF
  _DWORD v37[4]; // [rsp+98h] [rbp-50h] BYREF

  v3 = (void *)a3;
  v27 = 0;
  _InterlockedIncrement64(&g_ElfRpcCallsTotal);
  v34 = 0;
  v35 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v34);
  if ( (unsigned int)dword_18010F008 > 5 )
  {
    LODWORD(hSourceProcessHandle) = GetRpcClientPid();
    if ( v35 && (v37[0] || v37[1] || v37[2] || v37[3]) )
      v6 = v37;
    else
      LODWORD(v6) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18010F008,
      (unsigned int)&byte_1800FDACF,
      (unsigned int)&v36,
      (_DWORD)v6,
      (__int64)&hSourceProcessHandle);
  }
  v31[0] = &v34;
  v31[1] = &v27;
  v32 = 1;
  v7 = VerifyElfHandle(a1);
  v8 = v7;
  v27 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
        (unsigned int)v7);
      v8 = v27;
    }
    goto LABEL_57;
  }
  v9 = *((_DWORD *)a1 + 8) & 4;
  if ( v9 || (*((_BYTE *)a1 + 32) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = "remote";
      if ( !v9 )
        v25 = "backup";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, v25);
    }
    goto LABEL_64;
  }
  v10 = *((_QWORD *)a1 + 2);
  if ( !v10 || (v11 = *(struct LOGFILE **)(v10 + 32)) == 0 )
  {
LABEL_64:
    v26 = -1073741816;
    v27 = -1073741816;
    goto LABEL_65;
  }
  v12 = LegacyAccessCheck(v11, a1, v9 + 1, 0);
  v27 = v12;
  if ( v12 < 0 )
  {
LABEL_20:
    v8 = v12;
LABEL_57:
    tlx::_UndoSolo__ElfRpc_s_ChangeNotify_::_2_::_lambda_1___::__UndoSolo__ElfRpc_s_ChangeNotify_::_2_::_lambda_1___(v31);
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v34);
    return v8;
  }
  if ( *((_DWORD *)a1 + 11) == 5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids);
    }
    v8 = -1073741670;
    goto LABEL_27;
  }
  if ( BYTE4(g_service[60].Ptr) )
  {
    v8 = -1073741823;
LABEL_27:
    v27 = v8;
    goto LABEL_57;
  }
  RpcClientPid = GetRpcClientPid();
  if ( RpcClientPid
    && RpcClientPid != dwProcessId
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
      dwProcessId,
      RpcClientPid);
  }
  v14 = RpcImpersonateClient(0);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, v14);
    }
    v12 = I_RpcMapWin32Status(v15);
    v27 = v12;
    goto LABEL_20;
  }
  hSourceProcessHandle = 0;
  v16 = OpenProcess(0x40u, 0, dwProcessId);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hSourceProcessHandle, v16);
  RpcRevertToSelf();
  v17 = hSourceProcessHandle;
  if ( (unsigned __int64)hSourceProcessHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    v23 = DosErrorToNtStatus(LastError);
    v27 = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, LastError);
      v23 = v27;
    }
    if ( v23 == -1073741813 )
    {
      v23 = -1073741816;
      v27 = -1073741816;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hSourceProcessHandle);
    v8 = v23;
    goto LABEL_57;
  }
  v29 = 0;
  v18 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&v29);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v17, v3, CurrentProcess, v18, 0, 0, 2u) )
  {
    v20 = GetLastError();
    v8 = DosErrorToNtStatus(v20);
    v27 = v8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, v20);
      v8 = v27;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v29);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hSourceProcessHandle);
    goto LABEL_57;
  }
  try
  {
    v21 = v29;
    v29 = 0;
    v30 = v21;
    ChannelManager::AddLegacySubscriber(&g_service[45], *(_QWORD *)(*(_QWORD *)(v10 + 32) + 88LL), a1, &v30);
    ++*((_DWORD *)a1 + 11);
    v26 = 0;
    v27 = 0;
  }
  catch ( EvtException *v33 )
  {
    v27 = DosErrorToNtStatus(*((_DWORD *)v33 + 6));
    v26 = v27;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v29);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hSourceProcessHandle);
LABEL_65:
  tlx::_UndoSolo__ElfRpc_s_ChangeNotify_::_2_::_lambda_1___::__UndoSolo__ElfRpc_s_ChangeNotify_::_2_::_lambda_1___(v31);
  TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v34);
  return v26;
}

```

## disassembly

```asm
0x1800815a0  mov     r11, rsp
0x1800815a3  push    rbx
0x1800815a4  push    rsi
0x1800815a5  push    rdi
0x1800815a6  push    r12
0x1800815a8  push    r13
0x1800815aa  push    r14
0x1800815ac  push    r15
0x1800815ae  sub     rsp, 0B0h
0x1800815b5  mov     rax, cs:__security_cookie
0x1800815bc  xor     rax, rsp
0x1800815bf  mov     [rsp+0E8h+var_40], rax
0x1800815c7  movsxd  r12, r8d
0x1800815ca  mov     rbx, rdx
0x1800815cd  mov     r14, rcx
0x1800815d0  xor     r13d, r13d
0x1800815d3  mov     [rsp+0E8h+var_A8], r13d
0x1800815d8  lock inc cs:?g_ElfRpcCallsTotal@@3_JA; __int64 g_ElfRpcCallsTotal
0x1800815e0  mov     [r11-68h], r13d
0x1800815e4  mov     [r11-64h], r13b
0x1800815e8  lea     rcx, [r11-68h]
0x1800815ec  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800815f1  mov     eax, cs:dword_18010F008
0x1800815f7  cmp     eax, 5
0x1800815fa  jbe     short loc_180081669
0x1800815fc  call    ?GetRpcClientPid@@YAKXZ; GetRpcClientPid(void)
0x180081601  mov     dword ptr [rsp+0E8h+hSourceProcessHandle], eax
0x180081605  cmp     [rsp+0E8h+var_64], r13b
0x18008160d  jz      short loc_180081641
0x18008160f  cmp     [rsp+0E8h+var_50], r13d
0x180081617  jnz     short loc_180081637
0x180081619  cmp     [rsp+0E8h+var_4C], r13d
0x180081621  jnz     short loc_180081637
0x180081623  cmp     [rsp+0E8h+var_48], r13d
0x18008162b  jnz     short loc_180081637
0x18008162d  cmp     [rsp+0E8h+var_44], r13d
0x180081635  jz      short loc_180081641
0x180081637  lea     r9, [rsp+0E8h+var_50]
0x18008163f  jmp     short loc_180081644
0x180081641  mov     r9, r13
0x180081644  lea     rax, [rsp+0E8h+hSourceProcessHandle]
0x180081649  mov     qword ptr [rsp+0E8h+dwDesiredAccess], rax
0x18008164e  lea     r8, [rsp+0E8h+var_60]
0x180081656  lea     rdx, byte_1800FDACF
0x18008165d  lea     rcx, dword_18010F008
0x180081664  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180081669  lea     rax, [rsp+0E8h+var_68]
0x180081671  mov     [rsp+0E8h+var_88], rax
0x180081676  lea     rax, [rsp+0E8h+var_A8]
0x18008167b  mov     [rsp+0E8h+var_80], rax
0x180081680  mov     [rsp+0E8h+var_78], 1
0x180081685  mov     rcx, r14
0x180081688  call    VerifyElfHandle
0x18008168d  mov     edi, eax
0x18008168f  mov     [rsp+0E8h+var_A8], eax
0x180081693  test    eax, eax
0x180081695  jns     short loc_1800816E6
0x180081697  lea     rsi, WPP_GLOBAL_Control
0x18008169e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800816a5  cmp     rcx, rsi
0x1800816a8  jz      loc_1800819E4
0x1800816ae  test    dword ptr [rcx+1Ch], 1000h
0x1800816b5  jz      loc_1800819E4
0x1800816bb  cmp     byte ptr [rcx+19h], 2
0x1800816bf  jb      loc_1800819E4
0x1800816c5  mov     edx, 24h ; '$'
0x1800816ca  mov     r9d, eax
0x1800816cd  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x1800816d4  mov     rcx, [rcx+10h]
0x1800816d8  call    WPP_SF_d
0x1800816dd  mov     edi, [rsp+0E8h+var_A8]
0x1800816e1  jmp     loc_1800819E4
0x1800816e6  mov     eax, [r14+20h]
0x1800816ea  and     eax, 4
0x1800816ed  jnz     loc_180081A00
0x1800816f3  test    byte ptr [r14+20h], 2
0x1800816f8  jnz     loc_180081A00
0x1800816fe  mov     r15, [r14+10h]
0x180081702  test    r15, r15
0x180081705  jz      loc_180081A4B
0x18008170b  mov     rcx, [r15+20h]; struct LOGFILE *
0x18008170f  test    rcx, rcx
0x180081712  jz      loc_180081A4B
0x180081718  xor     r9d, r9d; bool
0x18008171b  lea     r8d, [rax+1]; unsigned int
0x18008171f  mov     rdx, r14; struct _IELF_HANDLE *
0x180081722  call    ?LegacyAccessCheck@@YAJPEAULOGFILE@@PEAU_IELF_HANDLE@@K_N@Z; LegacyAccessCheck(LOGFILE *,_IELF_HANDLE *,ulong,bool)
0x180081727  mov     [rsp+0E8h+var_A8], eax
0x18008172b  test    eax, eax
0x18008172d  jns     short loc_180081736
0x18008172f  mov     edi, eax
0x180081731  jmp     loc_1800819E4
0x180081736  cmp     dword ptr [r14+2Ch], 5
0x18008173b  jnz     short loc_180081782
0x18008173d  lea     rsi, WPP_GLOBAL_Control
0x180081744  mov     rcx, cs:WPP_GLOBAL_Control
0x18008174b  cmp     rcx, rsi
0x18008174e  jz      short loc_180081774
0x180081750  test    dword ptr [rcx+1Ch], 1000h
0x180081757  jz      short loc_180081774
0x180081759  cmp     byte ptr [rcx+19h], 2
0x18008175d  jb      short loc_180081774
0x18008175f  mov     edx, 26h ; '&'
0x180081764  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x18008176b  mov     rcx, [rcx+10h]
0x18008176f  call    WPP_SF_
0x180081774  mov     edi, 0C000009Ah
0x180081779  mov     [rsp+0E8h+var_A8], edi
0x18008177d  jmp     loc_1800819E4
0x180081782  mov     rax, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180081789  cmp     [rax+1E4h], r13b
0x180081790  jz      short loc_180081799
0x180081792  mov     edi, 0C0000001h
0x180081797  jmp     short loc_180081779
0x180081799  call    ?GetRpcClientPid@@YAKXZ; GetRpcClientPid(void)
0x18008179e  test    eax, eax
0x1800817a0  jz      short loc_1800817E6
0x1800817a2  cmp     eax, ebx
0x1800817a4  jz      short loc_1800817E6
0x1800817a6  lea     rsi, WPP_GLOBAL_Control
0x1800817ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800817b4  cmp     rcx, rsi
0x1800817b7  jz      short loc_1800817ED
0x1800817b9  test    dword ptr [rcx+1Ch], 1000h
0x1800817c0  jz      short loc_1800817ED
0x1800817c2  cmp     byte ptr [rcx+19h], 3
0x1800817c6  jb      short loc_1800817ED
0x1800817c8  mov     edx, 27h ; '''
0x1800817cd  mov     [rsp+0E8h+dwDesiredAccess], eax
0x1800817d1  mov     r9d, ebx
0x1800817d4  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x1800817db  mov     rcx, [rcx+10h]
0x1800817df  call    WPP_SF_DD
0x1800817e4  jmp     short loc_1800817ED
0x1800817e6  lea     rsi, WPP_GLOBAL_Control
0x1800817ed  xor     ecx, ecx; BindingHandle
0x1800817ef  call    cs:__imp_RpcImpersonateClient
0x1800817f5  mov     edi, eax
0x1800817f7  test    eax, eax
0x1800817f9  jz      short loc_18008183F
0x1800817fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180081802  cmp     rcx, rsi
0x180081805  jz      short loc_18008182E
0x180081807  test    dword ptr [rcx+1Ch], 1000h
0x18008180e  jz      short loc_18008182E
0x180081810  cmp     byte ptr [rcx+19h], 2
0x180081814  jb      short loc_18008182E
0x180081816  mov     edx, 28h ; '('
0x18008181b  mov     r9d, eax
0x18008181e  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x180081825  mov     rcx, [rcx+10h]
0x180081829  call    WPP_SF_d
0x18008182e  mov     ecx, edi; Status
0x180081830  call    cs:__imp_I_RpcMapWin32Status
0x180081836  mov     [rsp+0E8h+var_A8], eax
0x18008183a  jmp     loc_18008172F
0x18008183f  mov     [rsp+0E8h+hSourceProcessHandle], r13
0x180081844  mov     r8d, ebx; dwProcessId
0x180081847  xor     edx, edx; bInheritHandle
0x180081849  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18008184c  call    cs:__imp_OpenProcess
0x180081852  mov     rdx, rax
0x180081855  lea     rcx, [rsp+0E8h+hSourceProcessHandle]
0x18008185a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008185f  call    cs:__imp_RpcRevertToSelf
0x180081865  mov     rbx, [rsp+0E8h+hSourceProcessHandle]
0x18008186a  lea     rax, [rbx+1]
0x18008186e  cmp     rax, 1
0x180081872  jbe     loc_18008197B
0x180081878  mov     [rsp+0E8h+var_98], r13
0x18008187d  lea     rcx, [rsp+0E8h+var_98]
0x180081882  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180081887  mov     rdi, rax
0x18008188a  call    cs:__imp_GetCurrentProcess
0x180081890  mov     rdx, r12; hSourceHandle
0x180081893  mov     [rsp+0E8h+dwOptions], 2; dwOptions
0x18008189b  mov     [rsp+0E8h+bInheritHandle], r13d; bInheritHandle
0x1800818a0  mov     [rsp+0E8h+dwDesiredAccess], r13d; dwDesiredAccess
0x1800818a5  mov     r9, rdi; lpTargetHandle
0x1800818a8  mov     r8, rax; hTargetProcessHandle
0x1800818ab  mov     rcx, rbx; hSourceProcessHandle
0x1800818ae  call    cs:__imp_DuplicateHandle
0x1800818b4  test    eax, eax
0x1800818b6  jnz     short loc_18008191E
0x1800818b8  call    cs:__imp_GetLastError
0x1800818be  mov     ebx, eax
0x1800818c0  mov     ecx, eax; unsigned int
0x1800818c2  call    ?DosErrorToNtStatus@@YAJK@Z; DosErrorToNtStatus(ulong)
0x1800818c7  mov     edi, eax
0x1800818c9  mov     [rsp+0E8h+var_A8], eax
0x1800818cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800818d4  cmp     rcx, rsi
0x1800818d7  jz      short loc_180081904
0x1800818d9  test    dword ptr [rcx+1Ch], 1000h
0x1800818e0  jz      short loc_180081904
0x1800818e2  cmp     byte ptr [rcx+19h], 2
0x1800818e6  jb      short loc_180081904
0x1800818e8  mov     edx, 2Ah ; '*'
0x1800818ed  mov     r9d, ebx
0x1800818f0  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x1800818f7  mov     rcx, [rcx+10h]
0x1800818fb  call    WPP_SF_d
0x180081900  mov     edi, [rsp+0E8h+var_A8]
0x180081904  lea     rcx, [rsp+0E8h+var_98]
0x180081909  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008190e  nop
0x18008190f  lea     rcx, [rsp+0E8h+hSourceProcessHandle]
0x180081914  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180081919  jmp     loc_1800819E4
0x18008191e  mov     rax, [rsp+0E8h+var_98]
0x180081923  mov     [rsp+0E8h+var_98], r13
0x180081928  mov     [rsp+0E8h+var_90], rax
0x18008192d  mov     rdx, [r15+20h]
0x180081931  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180081938  add     rcx, 168h
0x18008193f  lea     r9, [rsp+0E8h+var_90]
0x180081944  mov     r8, r14
0x180081947  mov     rdx, [rdx+58h]
0x18008194b  call    ?AddLegacySubscriber@ChannelManager@@QEAAXPEB_WPEAU_IELF_HANDLE@@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; ChannelManager::AddLegacySubscriber(wchar_t const *,_IELF_HANDLE *,tlx::unique_any<tlx::file_handle_traits>)
0x180081950  inc     dword ptr [r14+2Ch]
0x180081954  mov     ebx, r13d
0x180081957  mov     [rsp+0E8h+var_A8], ebx
0x18008195b  jmp     short loc_180081961
0x18008195d  mov     ebx, [rsp+0E8h+var_A8]
0x180081961  lea     rcx, [rsp+0E8h+var_98]
0x180081966  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008196b  nop
0x18008196c  lea     rcx, [rsp+0E8h+hSourceProcessHandle]
0x180081971  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180081976  jmp     loc_180081A54
0x18008197b  call    cs:__imp_GetLastError
0x180081981  mov     edi, eax
0x180081983  mov     ecx, eax; unsigned int
0x180081985  call    ?DosErrorToNtStatus@@YAJK@Z; DosErrorToNtStatus(ulong)
0x18008198a  mov     ebx, eax
0x18008198c  mov     [rsp+0E8h+var_A8], eax
0x180081990  mov     rcx, cs:WPP_GLOBAL_Control
0x180081997  cmp     rcx, rsi
0x18008199a  jz      short loc_1800819C7
0x18008199c  test    dword ptr [rcx+1Ch], 1000h
0x1800819a3  jz      short loc_1800819C7
0x1800819a5  cmp     byte ptr [rcx+19h], 2
0x1800819a9  jb      short loc_1800819C7
0x1800819ab  mov     edx, 29h ; ')'
0x1800819b0  mov     r9d, edi
0x1800819b3  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x1800819ba  mov     rcx, [rcx+10h]
0x1800819be  call    WPP_SF_d
0x1800819c3  mov     ebx, [rsp+0E8h+var_A8]
0x1800819c7  cmp     ebx, 0C000000Bh
0x1800819cd  jnz     short loc_1800819D8
0x1800819cf  mov     ebx, 0C0000008h
0x1800819d4  mov     [rsp+0E8h+var_A8], ebx
0x1800819d8  lea     rcx, [rsp+0E8h+hSourceProcessHandle]
0x1800819dd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800819e2  mov     edi, ebx
0x1800819e4  lea     rcx, [rsp+0E8h+var_88]
0x1800819e9  call    tlx___UndoSolo__ElfRpc_s_ChangeNotify____2____lambda_1_______UndoSolo__ElfRpc_s_ChangeNotify____2____lambda_1___
0x1800819ee  nop
0x1800819ef  lea     rcx, [rsp+0E8h+var_68]
0x1800819f7  call    ??1?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(void)
0x1800819fc  mov     eax, edi
0x1800819fe  jmp     short loc_180081A6E
0x180081a00  lea     rsi, WPP_GLOBAL_Control
0x180081a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180081a0e  cmp     rcx, rsi
0x180081a11  jz      short loc_180081A4B
0x180081a13  test    dword ptr [rcx+1Ch], 1000h
0x180081a1a  jz      short loc_180081A4B
0x180081a1c  cmp     byte ptr [rcx+19h], 2
0x180081a20  jb      short loc_180081A4B
0x180081a22  lea     rdx, aBackup; "backup"
0x180081a29  lea     r9, aRemote; "remote"
0x180081a30  test    eax, eax
0x180081a32  cmovz   r9, rdx
0x180081a36  mov     edx, 25h ; '%'
0x180081a3b  lea     r8, WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids
0x180081a42  mov     rcx, [rcx+10h]
0x180081a46  call    WPP_SF_s
0x180081a4b  mov     ebx, 0C0000008h
0x180081a50  mov     [rsp+0E8h+var_A8], ebx
0x180081a54  lea     rcx, [rsp+0E8h+var_88]
0x180081a59  call    tlx___UndoSolo__ElfRpc_s_ChangeNotify____2____lambda_1_______UndoSolo__ElfRpc_s_ChangeNotify____2____lambda_1___
0x180081a5e  nop
0x180081a5f  lea     rcx, [rsp+0E8h+var_68]
0x180081a67  call    ??1?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(void)
0x180081a6c  mov     eax, ebx
0x180081a6e  mov     rcx, [rsp+0E8h+var_40]
0x180081a76  xor     rcx, rsp; StackCookie
0x180081a79  call    __security_check_cookie
0x180081a7e  add     rsp, 0B0h
0x180081a85  pop     r15
0x180081a87  pop     r14
0x180081a89  pop     r13
0x180081a8b  pop     r12
0x180081a8d  pop     rdi
0x180081a8e  pop     rsi
0x180081a8f  pop     rbx
0x180081a90  retn
```
