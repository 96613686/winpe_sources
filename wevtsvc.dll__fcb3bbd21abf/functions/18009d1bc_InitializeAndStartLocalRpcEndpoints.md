# InitializeAndStartLocalRpcEndpoints

- ea: `0x18009d1bc`
- end: `0x18009d835`
- name: `InitializeAndStartLocalRpcEndpoints`
- size: `1657`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009daf0`

## callees

- `0x180001008`
- `0x180017b60`
- `0x18002fa38`
- `0x180033ae0`
- `0x18003ee78`
- `0x180047fd8`
- `0x180064854`
- `0x180070418`
- `0x18008cb3c`
- `0x180092008`
- `0x180092ee4`
- `0x180098c50`
- `0x18009aee0`
- `0x18009ce14`
- `0x18009d1bc`
- `0x18009e770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d3eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d3eb`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18009d31d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18009d467`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18009d31d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18009d467`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009d76e`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009d76e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18009d6b6`
- `RPCRT4!RpcServerRegisterIf3` at `0x18009d6b6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18009d754`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18009d754`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18009d584`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18009d609`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18009d584`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18009d609`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d274`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d3e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d274`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d3e1`

## pseudocode

```c
__int64 __fastcall InitializeAndStartLocalRpcEndpoints(_DWORD *a1)
{
  int *v1; // r9
  PSECURITY_DESCRIPTOR *v2; // rax
  DWORD LastError; // eax
  unsigned int v4; // r14d
  PVOID *v5; // rcx
  __int64 v6; // rdx
  RPC_STATUS v7; // eax
  PSECURITY_DESCRIPTOR *v8; // rax
  DWORD v9; // eax
  PVOID *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // eax
  RPC_WSTR *v16; // r9
  unsigned __int16 *v17; // rcx
  unsigned int v18; // eax
  RPC_WSTR *v19; // r9
  __int64 v20; // r9
  void *SecurityDescriptor; // [rsp+40h] [rbp-59h] BYREF
  void *v23; // [rsp+48h] [rbp-51h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-41h] BYREF
  _WORD v26[8]; // [rsp+68h] [rbp-31h] BYREF
  RPC_WSTR ServerPrincName[2]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v28; // [rsp+88h] [rbp-11h]
  int v29; // [rsp+98h] [rbp-1h] BYREF
  char v30; // [rsp+9Ch] [rbp+3h]
  _BYTE v31[16]; // [rsp+A0h] [rbp+7h] BYREF
  int v32; // [rsp+B0h] [rbp+17h] BYREF
  int v33; // [rsp+B4h] [rbp+1Bh]
  int v34; // [rsp+B8h] [rbp+1Fh]
  int v35; // [rsp+BCh] [rbp+23h]

  v29 = 0;
  v32 = a1[2];
  v33 = a1[3];
  v34 = a1[4];
  v35 = a1[5];
  v30 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v29);
  if ( (unsigned int)dword_18010F008 > 5 )
  {
    if ( v30 && (v32 || v33 || v34 || v35) )
      v1 = &v32;
    else
      v1 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18010F008,
      &unk_1800FBE40,
      v31,
      v1);
  }
  SecurityDescriptor = 0;
  v2 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3153509613-960666"
           "767-3724611135-2725662640-12138253-543910227-1950414635-4190290187)",
          1u,
          v2,
          0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      {
        v6 = 39;
LABEL_19:
        WPP_SF_d(v5[2], v6, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v4);
        goto LABEL_105;
      }
    }
    goto LABEL_105;
  }
  v7 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"eventlog", SecurityDescriptor);
  v4 = v7;
  if ( !v7 || v7 == 1740 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids,
        (unsigned int)L"ncalrpc",
        (__int64)L"eventlog");
    }
    SecurityDescriptorSize = 0;
    v23 = 0;
    v8 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v23);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:LSG:LSD:P(A;;0x12019b;;;WD)(A;;0x12008f;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)(A;;0x1;;;OW)",
            1u,
            v8,
            &SecurityDescriptorSize) )
    {
      v9 = GetLastError();
      v4 = v9;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_104;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v9);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 8) == 0 || *((_BYTE *)v10 + 25) < 2u )
        goto LABEL_104;
      v11 = 43;
LABEL_96:
      v20 = v4;
      goto LABEL_86;
    }
    v12 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\pipe\\eventlog", v23);
    v4 = v12;
    if ( !v12 || v12 == 1740 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids,
          (unsigned int)L"ncacn_np",
          (__int64)L"\\pipe\\eventlog");
      }
      *(_OWORD *)ServerPrincName = 0;
      v28 = 0;
      std::wstring::_Construct<1,wchar_t const *>(ServerPrincName, v13, 5);
      v25[0] = v26;
      v25[1] = v26;
      v26[0] = 0;
      if ( !(unsigned __int8)GetLocalComputerDnsName(v25)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
      }
      std::wstring::_Append<wchar_t>(ServerPrincName);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v25);
      v14 = (unsigned __int16 *)ServerPrincName;
      if ( *((_QWORD *)&v28 + 1) > 7u )
        v14 = ServerPrincName[0];
      v15 = RpcServerRegisterAuthInfoW(v14, 9u, 0, 0);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v15);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v16 = ServerPrincName;
        if ( *((_QWORD *)&v28 + 1) > 7u )
          v16 = (RPC_WSTR *)ServerPrincName[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v16);
      }
      v17 = (unsigned __int16 *)ServerPrincName;
      if ( *((_QWORD *)&v28 + 1) > 7u )
        v17 = ServerPrincName[0];
      v18 = RpcServerRegisterAuthInfoW(v17, 0x10u, 0, 0);
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v18);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v19 = ServerPrincName;
        if ( *((_QWORD *)&v28 + 1) > 7u )
          v19 = (RPC_WSTR *)ServerPrincName[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v19);
      }
      std::wstring::~wstring(ServerPrincName);
      v12 = RpcServerRegisterIf3(
              qword_1800E1ED0,
              0,
              0,
              17,
              1234,
              0,
              RpcInterfaceSecurityCallbackLegacy,
              SecurityDescriptor);
      v4 = v12;
      if ( !v12 )
      {
        byte_180110118 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
        }
        v4 = RpcServerRegisterIfEx(
               qword_1800DFBE0,
               0,
               0,
               9u,
               0x4D2u,
               (RPC_IF_CALLBACK_FN *)RpcInterfaceSecurityCallback);
        if ( !v4 )
        {
          byte_180111705 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
          }
          v29 = 2;
          if ( (unsigned int)dword_18010F008 > 5 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18010F008,
              byte_1800FBF7B,
              v31,
              0);
          v4 = 0;
          goto LABEL_104;
        }
        RpcServerUnregisterIfEx(qword_1800E1ED0, 0, 1);
        byte_180110118 = 0;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_104:
          tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v23);
          goto LABEL_105;
        }
        v11 = 53;
        goto LABEL_96;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_104;
      }
      v11 = 51;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_104;
      }
      v11 = 44;
    }
    v20 = v12;
LABEL_86:
    WPP_SF_d(v10[2], v11, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v20);
    goto LABEL_104;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 40;
    goto LABEL_19;
  }
LABEL_105:
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
  TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v29);
  return v4;
}

```

## disassembly

```asm
0x18009d1bc  push    rbp
0x18009d1be  push    rbx
0x18009d1bf  push    rsi
0x18009d1c0  push    rdi
0x18009d1c1  push    r14
0x18009d1c3  lea     rbp, [rsp-37h]
0x18009d1c8  sub     rsp, 0D0h
0x18009d1cf  mov     rax, cs:__security_cookie
0x18009d1d6  xor     rax, rsp
0x18009d1d9  mov     [rbp+57h+var_30], rax
0x18009d1dd  mov     [rbp+57h+var_58], 0
0x18009d1e4  mov     eax, [rcx+8]
0x18009d1e7  mov     [rbp+57h+var_40], eax
0x18009d1ea  mov     eax, [rcx+0Ch]
0x18009d1ed  mov     [rbp+57h+var_3C], eax
0x18009d1f0  mov     eax, [rcx+10h]
0x18009d1f3  mov     [rbp+57h+var_38], eax
0x18009d1f6  mov     eax, [rcx+14h]
0x18009d1f9  mov     [rbp+57h+var_34], eax
0x18009d1fc  mov     [rbp+57h+var_54], 1
0x18009d200  lea     rcx, [rbp+57h+var_58]
0x18009d204  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18009d209  mov     eax, cs:dword_18010F008
0x18009d20f  cmp     eax, 5
0x18009d212  jbe     short loc_18009D252
0x18009d214  cmp     [rbp+57h+var_54], 0
0x18009d218  jz      short loc_18009D238
0x18009d21a  cmp     [rbp+57h+var_40], 0
0x18009d21e  jnz     short loc_18009D232
0x18009d220  cmp     [rbp+57h+var_3C], 0
0x18009d224  jnz     short loc_18009D232
0x18009d226  cmp     [rbp+57h+var_38], 0
0x18009d22a  jnz     short loc_18009D232
0x18009d22c  cmp     [rbp+57h+var_34], 0
0x18009d230  jz      short loc_18009D238
0x18009d232  lea     r9, [rbp+57h+var_40]
0x18009d236  jmp     short loc_18009D23B
0x18009d238  xor     r9d, r9d
0x18009d23b  lea     r8, [rbp+57h+var_50]
0x18009d23f  lea     rdx, unk_1800FBE40
0x18009d246  lea     rcx, dword_18010F008
0x18009d24d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009d252  mov     [rbp+57h+SecurityDescriptor], 0
0x18009d25a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18009d25e  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x18009d263  xor     r9d, r9d; SecurityDescriptorSize
0x18009d266  mov     r8, rax; SecurityDescriptor
0x18009d269  lea     edx, [r9+1]; StringSDRevision
0x18009d26d  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18009d274  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18009d27a  test    eax, eax
0x18009d27c  jnz     loc_18009D306
0x18009d282  call    cs:__imp_GetLastError
0x18009d288  mov     r14d, eax
0x18009d28b  lea     rdi, WPP_GLOBAL_Control
0x18009d292  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d299  cmp     rcx, rdi
0x18009d29c  jz      loc_18009D806
0x18009d2a2  lea     rsi, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009d2a9  mov     bl, 8
0x18009d2ab  test    [rcx+1Ch], bl
0x18009d2ae  jz      short loc_18009D2D1
0x18009d2b0  cmp     byte ptr [rcx+19h], 2
0x18009d2b4  jb      short loc_18009D2D1
0x18009d2b6  mov     edx, 26h ; '&'
0x18009d2bb  mov     r9d, eax
0x18009d2be  mov     r8, rsi
0x18009d2c1  mov     rcx, [rcx+10h]
0x18009d2c5  call    WPP_SF_d
0x18009d2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d2d1  cmp     rcx, rdi
0x18009d2d4  jz      loc_18009D806
0x18009d2da  test    [rcx+1Ch], bl
0x18009d2dd  jz      loc_18009D806
0x18009d2e3  cmp     byte ptr [rcx+19h], 2
0x18009d2e7  jb      loc_18009D806
0x18009d2ed  mov     edx, 27h ; '''
0x18009d2f2  mov     r8, rsi
0x18009d2f5  mov     r9d, r14d
0x18009d2f8  mov     rcx, [rcx+10h]
0x18009d2fc  call    WPP_SF_d
0x18009d301  jmp     loc_18009D806
0x18009d306  mov     r9, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18009d30a  lea     r8, ServiceName; "eventlog"
0x18009d311  mov     edx, 0Ah; MaxCalls
0x18009d316  lea     rcx, Protseq; "ncalrpc"
0x18009d31d  call    cs:__imp_RpcServerUseProtseqEpW
0x18009d323  mov     r14d, eax
0x18009d326  test    eax, eax
0x18009d328  jz      short loc_18009D36B
0x18009d32a  cmp     eax, 6CCh
0x18009d32f  jz      short loc_18009D36B
0x18009d331  lea     rdi, WPP_GLOBAL_Control
0x18009d338  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d33f  cmp     rcx, rdi
0x18009d342  jz      loc_18009D806
0x18009d348  mov     bl, 8
0x18009d34a  test    [rcx+1Ch], bl
0x18009d34d  jz      loc_18009D806
0x18009d353  cmp     byte ptr [rcx+19h], 2
0x18009d357  jb      loc_18009D806
0x18009d35d  mov     edx, 28h ; '('
0x18009d362  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009d369  jmp     short loc_18009D2F5
0x18009d36b  lea     rdi, WPP_GLOBAL_Control
0x18009d372  lea     rsi, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009d379  mov     bl, 8
0x18009d37b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d382  cmp     rcx, rdi
0x18009d385  jz      short loc_18009D3B6
0x18009d387  test    [rcx+1Ch], bl
0x18009d38a  jz      short loc_18009D3B6
0x18009d38c  cmp     byte ptr [rcx+19h], 5
0x18009d390  jb      short loc_18009D3B6
0x18009d392  mov     edx, 29h ; ')'
0x18009d397  lea     rax, ServiceName; "eventlog"
0x18009d39e  mov     qword ptr [rsp+0F0h+MaxCalls], rax
0x18009d3a3  lea     r9, Protseq; "ncalrpc"
0x18009d3aa  mov     r8, rsi
0x18009d3ad  mov     rcx, [rcx+10h]
0x18009d3b1  call    WPP_SF_SS
0x18009d3b6  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18009d3bd  mov     [rbp+57h+var_A8], 0
0x18009d3c5  lea     rcx, [rbp+57h+var_A8]
0x18009d3c9  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x18009d3ce  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18009d3d2  mov     r8, rax; SecurityDescriptor
0x18009d3d5  mov     edx, 1; StringSDRevision
0x18009d3da  lea     rcx, aOLsgLsdPA0x120; "O:LSG:LSD:P(A;;0x12019b;;;WD)(A;;0x1200"...
0x18009d3e1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18009d3e7  test    eax, eax
0x18009d3e9  jnz     short loc_18009D450
0x18009d3eb  call    cs:__imp_GetLastError
0x18009d3f1  mov     r14d, eax
0x18009d3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d3fb  cmp     rcx, rdi
0x18009d3fe  jz      loc_18009D7FD
0x18009d404  test    [rcx+1Ch], bl
0x18009d407  jz      short loc_18009D42A
0x18009d409  cmp     byte ptr [rcx+19h], 2
0x18009d40d  jb      short loc_18009D42A
0x18009d40f  mov     edx, 2Ah ; '*'
0x18009d414  mov     r9d, eax
0x18009d417  mov     r8, rsi
0x18009d41a  mov     rcx, [rcx+10h]
0x18009d41e  call    WPP_SF_d
0x18009d423  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d42a  cmp     rcx, rdi
0x18009d42d  jz      loc_18009D7FD
0x18009d433  test    [rcx+1Ch], bl
0x18009d436  jz      loc_18009D7FD
0x18009d43c  cmp     byte ptr [rcx+19h], 2
0x18009d440  jb      loc_18009D7FD
0x18009d446  mov     edx, 2Bh ; '+'
0x18009d44b  jmp     loc_18009D797
0x18009d450  mov     r9, [rbp+57h+var_A8]; SecurityDescriptor
0x18009d454  lea     r8, aPipeEventlog; "\\pipe\\eventlog"
0x18009d45b  mov     edx, 0Ah; MaxCalls
0x18009d460  lea     rcx, aNcacnNp; "ncacn_np"
0x18009d467  call    cs:__imp_RpcServerUseProtseqEpW
0x18009d46d  mov     r14d, eax
0x18009d470  test    eax, eax
0x18009d472  jz      short loc_18009D4A8
0x18009d474  cmp     eax, 6CCh
0x18009d479  jz      short loc_18009D4A8
0x18009d47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d482  cmp     rcx, rdi
0x18009d485  jz      loc_18009D7FD
0x18009d48b  test    [rcx+1Ch], bl
0x18009d48e  jz      loc_18009D7FD
0x18009d494  cmp     byte ptr [rcx+19h], 2
0x18009d498  jb      loc_18009D7FD
0x18009d49e  mov     edx, 2Ch ; ','
0x18009d4a3  jmp     loc_18009D6EB
0x18009d4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d4af  cmp     rcx, rdi
0x18009d4b2  jz      short loc_18009D4E3
0x18009d4b4  test    [rcx+1Ch], bl
0x18009d4b7  jz      short loc_18009D4E3
0x18009d4b9  cmp     byte ptr [rcx+19h], 5
0x18009d4bd  jb      short loc_18009D4E3
0x18009d4bf  mov     edx, 2Dh ; '-'
0x18009d4c4  lea     rax, aPipeEventlog; "\\pipe\\eventlog"
0x18009d4cb  mov     qword ptr [rsp+0F0h+MaxCalls], rax
0x18009d4d0  lea     r9, aNcacnNp; "ncacn_np"
0x18009d4d7  mov     r8, rsi
0x18009d4da  mov     rcx, [rcx+10h]
0x18009d4de  call    WPP_SF_SS
0x18009d4e3  xorps   xmm0, xmm0
0x18009d4e6  movups  xmmword ptr [rbp+57h+ServerPrincName], xmm0
0x18009d4ea  xorps   xmm1, xmm1
0x18009d4ed  movdqu  [rbp+57h+var_68], xmm1
0x18009d4f2  mov     r8d, 5
0x18009d4f8  lea     rcx, [rbp+57h+ServerPrincName]
0x18009d4fc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18009d501  lea     rax, [rbp+57h+var_88]
0x18009d505  mov     [rbp+57h+var_98], rax
0x18009d509  lea     rax, [rbp+57h+var_88]
0x18009d50d  mov     [rbp+57h+var_90], rax
0x18009d511  xor     eax, eax
0x18009d513  mov     [rbp+57h+var_88], ax
0x18009d517  lea     rcx, [rbp+57h+var_98]
0x18009d51b  call    ?GetLocalComputerDnsName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; GetLocalComputerDnsName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18009d520  test    al, al
0x18009d522  jnz     short loc_18009D54C
0x18009d524  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d52b  cmp     rcx, rdi
0x18009d52e  jz      short loc_18009D54C
0x18009d530  test    [rcx+1Ch], bl
0x18009d533  jz      short loc_18009D54C
0x18009d535  cmp     byte ptr [rcx+19h], 1
0x18009d539  jb      short loc_18009D54C
0x18009d53b  mov     edx, 2Eh ; '.'
0x18009d540  mov     r8, rsi
0x18009d543  mov     rcx, [rcx+10h]
0x18009d547  call    WPP_SF_
0x18009d54c  mov     r8, [rbp+57h+var_90]
0x18009d550  mov     rdx, [rbp+57h+var_98]
0x18009d554  sub     r8, rdx
0x18009d557  sar     r8, 1
0x18009d55a  lea     rcx, [rbp+57h+ServerPrincName]; Src
0x18009d55e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18009d563  lea     rcx, [rbp+57h+var_98]; void *
0x18009d567  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009d56c  lea     rcx, [rbp+57h+ServerPrincName]
0x18009d570  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18009d575  cmova   rcx, [rbp+57h+ServerPrincName]; ServerPrincName
0x18009d57a  xor     r9d, r9d; Arg
0x18009d57d  xor     r8d, r8d; GetKeyFn
0x18009d580  lea     edx, [r9+9]; AuthnSvc
0x18009d584  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18009d58a  test    eax, eax
0x18009d58c  jz      short loc_18009D5BB
0x18009d58e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d595  cmp     rcx, rdi
0x18009d598  jz      short loc_18009D5F1
0x18009d59a  test    [rcx+1Ch], bl
0x18009d59d  jz      short loc_18009D5F1
0x18009d59f  cmp     byte ptr [rcx+19h], 1
0x18009d5a3  jb      short loc_18009D5F1
0x18009d5a5  mov     edx, 2Fh ; '/'
0x18009d5aa  mov     r9d, eax
0x18009d5ad  mov     r8, rsi
0x18009d5b0  mov     rcx, [rcx+10h]
0x18009d5b4  call    WPP_SF_d
0x18009d5b9  jmp     short loc_18009D5F1
0x18009d5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d5c2  cmp     rcx, rdi
0x18009d5c5  jz      short loc_18009D5F1
0x18009d5c7  test    [rcx+1Ch], bl
0x18009d5ca  jz      short loc_18009D5F1
0x18009d5cc  cmp     byte ptr [rcx+19h], 5
0x18009d5d0  jb      short loc_18009D5F1
0x18009d5d2  lea     r9, [rbp+57h+ServerPrincName]
0x18009d5d6  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18009d5db  cmova   r9, [rbp+57h+ServerPrincName]
0x18009d5e0  mov     edx, 30h ; '0'
0x18009d5e5  mov     r8, rsi
0x18009d5e8  mov     rcx, [rcx+10h]
0x18009d5ec  call    WPP_SF_S
0x18009d5f1  lea     rcx, [rbp+57h+ServerPrincName]
0x18009d5f5  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18009d5fa  cmova   rcx, [rbp+57h+ServerPrincName]; ServerPrincName
0x18009d5ff  xor     r9d, r9d; Arg
0x18009d602  xor     r8d, r8d; GetKeyFn
0x18009d605  lea     edx, [r9+10h]; AuthnSvc
0x18009d609  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18009d60f  test    eax, eax
0x18009d611  jz      short loc_18009D640
0x18009d613  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d61a  cmp     rcx, rdi
0x18009d61d  jz      short loc_18009D676
0x18009d61f  test    [rcx+1Ch], bl
0x18009d622  jz      short loc_18009D676
0x18009d624  cmp     byte ptr [rcx+19h], 1
0x18009d628  jb      short loc_18009D676
0x18009d62a  mov     edx, 31h ; '1'
0x18009d62f  mov     r9d, eax
0x18009d632  mov     r8, rsi
0x18009d635  mov     rcx, [rcx+10h]
0x18009d639  call    WPP_SF_d
0x18009d63e  jmp     short loc_18009D676
0x18009d640  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d647  cmp     rcx, rdi
0x18009d64a  jz      short loc_18009D676
0x18009d64c  test    [rcx+1Ch], bl
0x18009d64f  jz      short loc_18009D676
0x18009d651  cmp     byte ptr [rcx+19h], 5
0x18009d655  jb      short loc_18009D676
0x18009d657  lea     r9, [rbp+57h+ServerPrincName]
0x18009d65b  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18009d660  cmova   r9, [rbp+57h+ServerPrincName]
0x18009d665  mov     edx, 32h ; '2'
0x18009d66a  mov     r8, rsi
0x18009d66d  mov     rcx, [rcx+10h]
0x18009d671  call    WPP_SF_S
0x18009d676  lea     rcx, [rbp+57h+ServerPrincName]
0x18009d67a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009d67f  mov     rax, [rbp+57h+SecurityDescriptor]
0x18009d683  mov     [rsp+0F0h+var_B8], rax
  ... truncated ...
```
