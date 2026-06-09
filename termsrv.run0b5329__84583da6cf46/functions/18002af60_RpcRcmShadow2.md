# RpcRcmShadow2

- ea: `0x18002af60`
- end: `0x18002b50f`
- name: `RpcRcmShadow2`
- size: `1455`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int, _DWORD *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800092f0`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x1800127b0`
- `0x180013150`
- `0x180015ab0`
- `0x18002af60`
- `0x18002b518`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x18005bad8`
- `0x18005c478`
- `0x18007a328`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b19e`
- `RPCRT4!RpcRevertToSelf` at `0x18002b1ee`
- `RPCRT4!RpcRevertToSelf` at `0x18002b3f4`
- `RPCRT4!RpcRevertToSelf` at `0x18002b1ee`
- `RPCRT4!RpcRevertToSelf` at `0x18002b3f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b1cb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b1cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b486`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b48f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b486`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b48f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b49f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b49f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4af`
- `SspiCli!GetUserNameExW` at `0x18002b135`
- `SspiCli!GetUserNameExW` at `0x18002b191`
- `SspiCli!GetUserNameExW` at `0x18002b135`
- `SspiCli!GetUserNameExW` at `0x18002b191`

## string_xrefs

- `0x18002b24b`: `GetSessionAgent failed: 0x%x in %s`
- `0x18002b289`: `CreateShadowInivitation failed: 0x%x in %s`
- `0x18002b368`: `StringCchCopyW failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RpcRcmShadow2(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  signed int v9; // esi
  OLECHAR *v10; // r14
  OLECHAR *v11; // rbx
  unsigned __int16 *v12; // r13
  int LastError; // edi
  int v14; // eax
  char v15; // r15
  struct ITSSession *v16; // rbx
  int UserNameDomain; // eax
  const char *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  WCHAR *v24; // rax
  bool v25; // sf
  bool v26; // sf
  int SessionAgent; // eax
  int v28; // eax
  __int128 v29; // xmm0
  __int128 v30; // xmm0
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  RPC_STATUS v36; // eax
  BSTR v39; // [rsp+48h] [rbp-B8h]
  ULONG nSize; // [rsp+50h] [rbp-B0h] BYREF
  int TokenHandle; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-98h]
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, __int64 *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  struct IRdpSessionAgent *v48; // [rsp+88h] [rbp-78h] BYREF
  struct ITSSession *v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v50; // [rsp+98h] [rbp-68h]
  __int128 v51; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v52[592]; // [rsp+B0h] [rbp-50h] BYREF

  v50 = a6;
  TokenHandle = 0;
  bstrString = 0;
  v9 = 0;
  v49 = 0;
  v48 = 0;
  v10 = 0;
  v47 = 0;
  v11 = 0;
  v46 = 0;
  v12 = 0;
  nSize = 0;
  pv = 0;
  v43 = 0;
  v44 = a4;
  v51 = EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v52, 0, "RpcRcmShadow2");
  LastError = RCMRpcPrologueEx(a2, 0x10u, 0, 0, &v49, &TokenHandle);
  if ( LastError < 0 )
  {
    v14 = 1;
    if ( LastError != -2147022646 )
      v14 = 4;
    _DbgPrintMessage(v14, "RCMRpcPrologue failed: 0x%x", LastError);
    goto LABEL_5;
  }
  v16 = v49;
  UserNameDomain = CHelper::GetUserNameDomain(v49, (unsigned __int16 **)&pv, &v43);
  LastError = UserNameDomain;
  if ( UserNameDomain >= 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)pv + v19) );
    v20 = -1;
    do
      ++v20;
    while ( v43[v20] );
    v21 = v20 + v19 + 2;
    v22 = 2 * v21;
    if ( !is_mul_ok(v21, 2u) )
      v22 = -1;
    v12 = (unsigned __int16 *)operator new[](v22, (const struct std::nothrow_t *)std::nothrow);
    if ( !v12 )
      goto LABEL_17;
    UserNameDomain = StringCchPrintfW(v12, v21, L"%s\\%s", v43, pv);
    LastError = UserNameDomain;
    if ( UserNameDomain < 0 )
    {
      v18 = "StringCchPrintf failed: 0x%x in %s";
      goto LABEL_8;
    }
    nSize = 0;
    if ( !GetUserNameExW(NameSamCompatible, 0, &nSize) )
    {
      if ( GetLastError() != 234 || !nSize )
        goto LABEL_27;
      v23 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v23 = -1;
      v24 = (WCHAR *)operator new[](v23, (const struct std::nothrow_t *)std::nothrow);
      v10 = v24;
      if ( !v24 )
      {
LABEL_17:
        LastError = -2147024882;
        goto LABEL_9;
      }
      if ( !GetUserNameExW(NameSamCompatible, v24, &nSize) )
      {
LABEL_27:
        LastError = GetLastError();
        v25 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v25 = LastError < 0;
        }
        if ( v25 )
        {
          _DbgPrintMessage(8, "GetUserNameEx failed: 0x%x in %s", (unsigned int)LastError, "RpcRcmShadow2");
          goto LABEL_9;
        }
      }
    }
    v39 = SysAllocString(v10);
    if ( !v39 )
    {
      LastError = -2147024882;
      v11 = 0;
      goto LABEL_5;
    }
    if ( TokenHandle )
    {
      LastError = RpcRevertToSelf();
      v26 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v26 = LastError < 0;
      }
      if ( v26 )
      {
        _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x in %s", (unsigned int)LastError, "RpcRcmShadow2");
LABEL_38:
        v15 = a2;
LABEL_71:
        v11 = v39;
        goto LABEL_72;
      }
      TokenHandle = 0;
    }
    SessionAgent = GetSessionAgent(a2, &v48);
    LastError = SessionAgent;
    if ( SessionAgent < 0 )
    {
      _DbgPrintMessage(8, "GetSessionAgent failed: 0x%x in %s", (unsigned int)SessionAgent, "RpcRcmShadow2");
      goto LABEL_38;
    }
    v28 = (*(__int64 (__fastcall **)(struct IRdpSessionAgent *, BSTR, _QWORD, _QWORD, _DWORD *, BSTR *))(*(_QWORD *)v48 + 24LL))(
            v48,
            v39,
            a3,
            v44,
            a5,
            &bstrString);
    LastError = v28;
    if ( v28 < 0 )
    {
      _DbgPrintMessage(8, "CreateShadowInivitation failed: 0x%x in %s", (unsigned int)v28, "RpcRcmShadow2");
      goto LABEL_38;
    }
    if ( *a5 )
    {
      if ( *a5 != 1 )
      {
        if ( *a5 == 6 )
          v29 = EVENT_TS_SHADOW_BUSY;
        else
          v29 = EVENT_TS_SHADOW_POLICY;
        v51 = v29;
        goto LABEL_57;
      }
      if ( a3 == 1 )
        v30 = EVENT_TS_SHADOW_CONTROL_PERMISSION_DENY;
      else
        v30 = EVENT_TS_SHADOW_VIEW_PERMISSION_DENY;
    }
    else if ( a3 == 1 )
    {
      v30 = EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW;
    }
    else
    {
      v30 = EVENT_TS_SHADOW_VIEW_PERMISSION_ALLOW;
    }
    v51 = v30;
LABEL_57:
    v15 = a2;
    v31 = CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned long>(
            (unsigned int)&CrimsonHelper::s_instance,
            (unsigned int)&v51,
            (_DWORD)v12,
            (_DWORD)v10,
            a2);
    LastError = v31;
    if ( v31 > 0 )
      LastError = (unsigned __int16)v31 | 0x80070000;
    if ( LastError >= 0 )
    {
      v32 = StringCchCopyW(v50, a7, bstrString);
      LastError = v32;
      if ( v32 >= 0 )
      {
        v33 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v16 + 104LL))(
                v16,
                &v47);
        if ( v33 >= 0 )
        {
          v34 = (**v47)(v47, qword_1800D7370, &v46);
          if ( v34 >= 0 )
          {
            v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 544LL))(v46);
            if ( v35 < 0 )
              _DbgPrintMessage(8, "spRemoteTerminal->StartShadow2 failed: 0x%x", (unsigned int)v35);
          }
          else
          {
            _DbgPrintMessage(8, "spTerminal->QueryInterface failed: 0x%x", (unsigned int)v34);
          }
        }
        else
        {
          _DbgPrintMessage(8, "spSession->getTerminal failed: 0x%x", (unsigned int)v33);
        }
        LastError = 0;
      }
      else
      {
        _DbgPrintMessage(8, "StringCchCopyW failed: 0x%x in %s", (unsigned int)v32, "RpcRcmShadow2");
      }
    }
    else
    {
      _DbgPrintMessage(8, "TS_RAISE_EVENT_3 failed: 0x%x in %s", (unsigned int)LastError, "RpcRcmShadow2");
    }
    goto LABEL_71;
  }
  v18 = "CHelper::GetUserNameDomain failed: 0x%x in %s";
LABEL_8:
  _DbgPrintMessage(8, v18, (unsigned int)UserNameDomain, "RpcRcmShadow2");
LABEL_9:
  v11 = 0;
LABEL_5:
  v15 = a2;
LABEL_72:
  if ( !TokenHandle )
    goto LABEL_77;
  v36 = RpcRevertToSelf();
  v9 = v36;
  if ( v36 > 0 )
    v9 = (unsigned __int16)v36 | 0x80070000;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v9);
    LastError = -2147024891;
  }
  else
  {
LABEL_77:
    if ( LastError >= 0 )
      goto LABEL_80;
  }
  if ( (unsigned int)CrimsonHelper::RaiseEvent<unsigned short const *,unsigned short const *,long,unsigned long>(
                       (CrimsonHelper *)&CrimsonHelper::s_instance,
                       LastError,
                       v15) )
    _DbgPrintMessage(8, "TS_RAISE_EVENT_4 failed: 0x%x", v9);
LABEL_80:
  operator delete(v10);
  operator delete(v12);
  SysFreeString(bstrString);
  SysFreeString(v11);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v43 )
    CoTaskMemFree(v43);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v52);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v46);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v47);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v49);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002af60  mov     [rsp-8+arg_0], rbx
0x18002af65  push    rbp
0x18002af66  push    rsi
0x18002af67  push    rdi
0x18002af68  push    r12
0x18002af6a  push    r13
0x18002af6c  push    r14
0x18002af6e  push    r15
0x18002af70  lea     rbp, [rsp-210h]
0x18002af78  sub     rsp, 310h
0x18002af7f  mov     rax, cs:__security_cookie
0x18002af86  xor     rax, rsp
0x18002af89  mov     [rbp+240h+var_40], rax
0x18002af90  mov     rax, [rbp+240h+arg_28]
0x18002af97  lea     rcx, [rbp+240h+var_290]; this
0x18002af9b  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW
0x18002afa2  mov     r15, [rbp+240h+arg_20]
0x18002afa9  mov     r12d, r8d
0x18002afac  mov     [rbp+240h+var_2A8], rax
0x18002afb0  lea     r8, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002afb7  xor     eax, eax
0x18002afb9  mov     dword ptr [rsp+340h+var_300], edx
0x18002afbd  mov     edi, edx
0x18002afbf  mov     [rsp+340h+var_2EC], eax
0x18002afc3  xor     edx, edx; int
0x18002afc5  mov     [rsp+340h+bstrString], rax
0x18002afca  mov     esi, eax
0x18002afcc  mov     [rbp+240h+var_2B0], rax
0x18002afd0  mov     [rbp+240h+var_2B8], rax
0x18002afd4  mov     r14d, eax
0x18002afd7  mov     [rbp+240h+var_2C0], rax
0x18002afdb  mov     ebx, eax
0x18002afdd  mov     [rsp+340h+var_2C8], rax
0x18002afe2  mov     r13d, eax
0x18002afe5  mov     [rsp+340h+nSize], eax
0x18002afe9  mov     [rsp+340h+pv], rax
0x18002afee  mov     [rsp+340h+var_2E0], rax
0x18002aff3  mov     [rsp+340h+var_2D8], r9d
0x18002aff8  movdqu  [rbp+240h+var_2A0], xmm0
0x18002affd  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002b002  lea     rax, [rsp+340h+var_2EC]
0x18002b007  xor     r9d, r9d; struct ITerminal **
0x18002b00a  mov     [rsp+340h+TokenHandle], rax; TokenHandle
0x18002b00f  lea     edx, [r13+10h]; unsigned int
0x18002b013  lea     rax, [rbp+240h+var_2B0]
0x18002b017  xor     r8d, r8d; int
0x18002b01a  mov     ecx, edi; unsigned int
0x18002b01c  mov     [rsp+340h+var_320], rax; struct ITSSession **
0x18002b021  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18002b026  mov     edi, eax
0x18002b028  test    eax, eax
0x18002b02a  jns     short loc_18002B05A
0x18002b02c  lea     eax, [r13+1]
0x18002b030  cmp     edi, 800708CAh
0x18002b036  lea     ecx, [rax+3]
0x18002b039  mov     r8d, edi
0x18002b03c  cmovnz  eax, ecx
0x18002b03f  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18002b046  mov     ecx, eax; int
0x18002b048  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b04d  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002b052  xor     r12d, r12d
0x18002b055  jmp     loc_18002B3ED
0x18002b05a  mov     rbx, [rbp+240h+var_2B0]
0x18002b05e  lea     r8, [rsp+340h+var_2E0]; unsigned __int16 **
0x18002b063  mov     rcx, rbx; struct ITSSession *
0x18002b066  lea     rdx, [rsp+340h+pv]; unsigned __int16 **
0x18002b06b  call    ?GetUserNameDomain@CHelper@@SAJPEAUITSSession@@PEAPEAG1@Z; CHelper::GetUserNameDomain(ITSSession *,ushort * *,ushort * *)
0x18002b070  xor     r8d, r8d
0x18002b073  mov     edi, eax
0x18002b075  test    eax, eax
0x18002b077  jns     short loc_18002B099
0x18002b079  lea     rdx, aChelperGetuser_0; "CHelper::GetUserNameDomain failed: 0x%x"...
0x18002b080  mov     r8d, eax
0x18002b083  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002b08a  mov     ecx, 8; int
0x18002b08f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b094  mov     rbx, rsi
0x18002b097  jmp     short loc_18002B04D
0x18002b099  mov     rax, [rsp+340h+pv]
0x18002b09e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b0a2  mov     rcx, r9
0x18002b0a5  inc     rcx
0x18002b0a8  cmp     [rax+rcx*2], r8w
0x18002b0ad  jnz     short loc_18002B0A5
0x18002b0af  mov     rdx, [rsp+340h+var_2E0]
0x18002b0b4  mov     rax, r9
0x18002b0b7  inc     rax
0x18002b0ba  cmp     [rdx+rax*2], r8w
0x18002b0bf  jnz     short loc_18002B0B7
0x18002b0c1  lea     rdi, [rcx+2]
0x18002b0c5  add     rdi, rax
0x18002b0c8  mov     eax, 2
0x18002b0cd  mul     rdi
0x18002b0d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b0d7  cmovb   rax, r9
0x18002b0db  mov     rcx, rax; unsigned __int64
0x18002b0de  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b0e3  mov     r13, rax
0x18002b0e6  test    rax, rax
0x18002b0e9  jnz     short loc_18002B0F2
0x18002b0eb  mov     edi, 8007000Eh
0x18002b0f0  jmp     short loc_18002B094
0x18002b0f2  mov     rax, [rsp+340h+pv]
0x18002b0f7  lea     r8, aSS_0; "%s\\%s"
0x18002b0fe  mov     r9, [rsp+340h+var_2E0]
0x18002b103  mov     rdx, rdi; unsigned __int64
0x18002b106  mov     rcx, r13; unsigned __int16 *
0x18002b109  mov     [rsp+340h+var_320], rax
0x18002b10e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b113  mov     edi, eax
0x18002b115  test    eax, eax
0x18002b117  jns     short loc_18002B125
0x18002b119  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18002b120  jmp     loc_18002B080
0x18002b125  xor     edi, edi
0x18002b127  lea     r8, [rsp+340h+nSize]; nSize
0x18002b12c  xor     edx, edx; lpNameBuffer
0x18002b12e  mov     [rsp+340h+nSize], edi
0x18002b132  lea     ecx, [rdi+2]; NameFormat
0x18002b135  call    cs:__imp_GetUserNameExW
0x18002b13b  movzx   eax, al
0x18002b13e  test    eax, eax
0x18002b140  jnz     loc_18002B1C8
0x18002b146  call    cs:__imp_GetLastError
0x18002b14c  cmp     eax, 0EAh
0x18002b151  jnz     short loc_18002B19E
0x18002b153  mov     eax, [rsp+340h+nSize]
0x18002b157  test    eax, eax
0x18002b159  jz      short loc_18002B19E
0x18002b15b  mov     ecx, eax
0x18002b15d  lea     eax, [rdi+2]
0x18002b160  mul     rcx
0x18002b163  lea     rcx, [rdi-1]
0x18002b167  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b16e  cmovb   rax, rcx
0x18002b172  mov     rcx, rax; unsigned __int64
0x18002b175  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b17a  mov     r14, rax
0x18002b17d  test    rax, rax
0x18002b180  jz      loc_18002B0EB
0x18002b186  lea     r8, [rsp+340h+nSize]; nSize
0x18002b18b  mov     rdx, rax; lpNameBuffer
0x18002b18e  lea     ecx, [rdi+2]; NameFormat
0x18002b191  call    cs:__imp_GetUserNameExW
0x18002b197  movzx   eax, al
0x18002b19a  test    eax, eax
0x18002b19c  jnz     short loc_18002B1C8
0x18002b19e  call    cs:__imp_GetLastError
0x18002b1a4  mov     edi, eax
0x18002b1a6  test    eax, eax
0x18002b1a8  jle     short loc_18002B1B5
0x18002b1aa  movzx   edi, di
0x18002b1ad  or      edi, 80070000h
0x18002b1b3  test    edi, edi
0x18002b1b5  jns     short loc_18002B1C6
0x18002b1b7  mov     r8d, edi
0x18002b1ba  lea     rdx, aGetusernameexF; "GetUserNameEx failed: 0x%x in %s"
0x18002b1c1  jmp     loc_18002B083
0x18002b1c6  xor     edi, edi
0x18002b1c8  mov     rcx, r14; psz
0x18002b1cb  call    cs:__imp_SysAllocString
0x18002b1d1  mov     [rsp+340h+var_2F8], rax
0x18002b1d6  test    rax, rax
0x18002b1d9  jnz     short loc_18002B1E8
0x18002b1db  mov     edi, 8007000Eh
0x18002b1e0  mov     rbx, rax
0x18002b1e3  jmp     loc_18002B04D
0x18002b1e8  cmp     [rsp+340h+var_2EC], edi
0x18002b1ec  jz      short loc_18002B235
0x18002b1ee  call    cs:__imp_RpcRevertToSelf
0x18002b1f4  mov     edi, eax
0x18002b1f6  xor     eax, eax
0x18002b1f8  test    edi, edi
0x18002b1fa  jle     short loc_18002B207
0x18002b1fc  movzx   edi, di
0x18002b1ff  or      edi, 80070000h
0x18002b205  test    edi, edi
0x18002b207  jns     short loc_18002B231
0x18002b209  mov     r8d, edi
0x18002b20c  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: 0x%x in %s"
0x18002b213  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002b21a  mov     ecx, 8; int
0x18002b21f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b224  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002b229  xor     r12d, r12d
0x18002b22c  jmp     loc_18002B3E8
0x18002b231  mov     [rsp+340h+var_2EC], eax
0x18002b235  mov     ecx, dword ptr [rsp+340h+var_300]; unsigned int
0x18002b239  lea     rdx, [rbp+240h+var_2B8]; struct IRdpSessionAgent **
0x18002b23d  call    ?GetSessionAgent@@YAJKPEAPEAUIRdpSessionAgent@@@Z; GetSessionAgent(ulong,IRdpSessionAgent * *)
0x18002b242  mov     edi, eax
0x18002b244  test    eax, eax
0x18002b246  jns     short loc_18002B254
0x18002b248  mov     r8d, eax
0x18002b24b  lea     rdx, aGetsessionagen; "GetSessionAgent failed: 0x%x in %s"
0x18002b252  jmp     short loc_18002B213
0x18002b254  mov     rcx, [rbp+240h+var_2B8]
0x18002b258  lea     rdx, [rsp+340h+bstrString]
0x18002b25d  mov     r9d, [rsp+340h+var_2D8]
0x18002b262  mov     r8d, r12d
0x18002b265  mov     [rsp+340h+TokenHandle], rdx
0x18002b26a  mov     rdx, [rsp+340h+var_2F8]
0x18002b26f  mov     rax, [rcx]
0x18002b272  mov     [rsp+340h+var_320], r15
0x18002b277  mov     rax, [rax+18h]
0x18002b27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b280  mov     edi, eax
0x18002b282  test    eax, eax
0x18002b284  jns     short loc_18002B292
0x18002b286  mov     r8d, eax
0x18002b289  lea     rdx, aCreateshadowin; "CreateShadowInivitation failed: 0x%x in"...
0x18002b290  jmp     short loc_18002B213
0x18002b292  mov     ecx, [r15]
0x18002b295  test    ecx, ecx
0x18002b297  jz      short loc_18002B2D6
0x18002b299  sub     ecx, 1
0x18002b29c  jz      short loc_18002B2BA
0x18002b29e  cmp     ecx, 5
0x18002b2a1  jz      short loc_18002B2AC
0x18002b2a3  movups  xmm0, cs:EVENT_TS_SHADOW_POLICY
0x18002b2aa  jmp     short loc_18002B2B3
0x18002b2ac  movups  xmm0, cs:EVENT_TS_SHADOW_BUSY
0x18002b2b3  movdqu  [rbp+240h+var_2A0], xmm0
0x18002b2b8  jmp     short loc_18002B2F5
0x18002b2ba  mov     eax, 1
0x18002b2bf  cmp     r12d, eax
0x18002b2c2  jnz     short loc_18002B2CD
0x18002b2c4  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_DENY
0x18002b2cb  jmp     short loc_18002B2F0
0x18002b2cd  movups  xmm0, cs:EVENT_TS_SHADOW_VIEW_PERMISSION_DENY
0x18002b2d4  jmp     short loc_18002B2F0
0x18002b2d6  mov     eax, 1
0x18002b2db  cmp     r12d, eax
0x18002b2de  jnz     short loc_18002B2E9
0x18002b2e0  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW
0x18002b2e7  jmp     short loc_18002B2F0
0x18002b2e9  movups  xmm0, cs:EVENT_TS_SHADOW_VIEW_PERMISSION_ALLOW
0x18002b2f0  movdqa  [rbp+240h+var_2A0], xmm0
0x18002b2f5  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002b2fa  lea     rdx, [rbp+240h+var_2A0]
0x18002b2fe  mov     r9, r14
0x18002b301  mov     dword ptr [rsp+340h+var_320], r15d
0x18002b306  mov     r8, r13
0x18002b309  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002b310  call    ??$RaiseEvent@PEAGPEAGK@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG1K@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ulong>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ulong)
0x18002b315  xor     r12d, r12d
0x18002b318  mov     edi, eax
0x18002b31a  test    eax, eax
0x18002b31c  jle     short loc_18002B327
0x18002b31e  movzx   edi, ax
0x18002b321  or      edi, 80070000h
0x18002b327  test    edi, edi
0x18002b329  jns     short loc_18002B34B
0x18002b32b  mov     r8d, edi
0x18002b32e  lea     rdx, aTsRaiseEvent3F_1; "TS_RAISE_EVENT_3 failed: 0x%x in %s"
0x18002b335  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002b33c  mov     ecx, 8; int
0x18002b341  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b346  jmp     loc_18002B3E8
0x18002b34b  mov     edx, dword ptr [rbp+240h+arg_30]; unsigned __int64
0x18002b351  mov     r8, [rsp+340h+bstrString]; unsigned __int16 *
0x18002b356  mov     rcx, [rbp+240h+var_2A8]; unsigned __int16 *
0x18002b35a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b35f  mov     edi, eax
0x18002b361  test    eax, eax
0x18002b363  jns     short loc_18002B371
0x18002b365  mov     r8d, eax
0x18002b368  lea     rdx, aStringcchcopyw; "StringCchCopyW failed: 0x%x in %s"
0x18002b36f  jmp     short loc_18002B335
0x18002b371  mov     rax, [rbx]
0x18002b374  lea     rdx, [rbp+240h+var_2C0]
0x18002b378  mov     rcx, rbx
0x18002b37b  mov     rax, [rax+68h]
0x18002b37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b384  test    eax, eax
0x18002b386  jns     short loc_18002B391
0x18002b388  lea     rdx, aSpsessionGette; "spSession->getTerminal failed: 0x%x"
0x18002b38f  jmp     short loc_18002B3D8
0x18002b391  mov     rcx, [rbp+240h+var_2C0]
0x18002b395  lea     r8, [rsp+340h+var_2C8]
0x18002b39a  lea     rdx, qword_1800D7370
0x18002b3a1  mov     rax, [rcx]
0x18002b3a4  mov     rax, [rax]
0x18002b3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ac  test    eax, eax
0x18002b3ae  jns     short loc_18002B3B9
0x18002b3b0  lea     rdx, aSpterminalQuer; "spTerminal->QueryInterface failed: 0x%x"
0x18002b3b7  jmp     short loc_18002B3D8
0x18002b3b9  mov     rcx, [rsp+340h+var_2C8]
0x18002b3be  mov     rax, [rcx]
0x18002b3c1  mov     rax, [rax+220h]
0x18002b3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3cd  test    eax, eax
0x18002b3cf  jns     short loc_18002B3E5
0x18002b3d1  lea     rdx, aSpremotetermin; "spRemoteTerminal->StartShadow2 failed: "...
0x18002b3d8  mov     r8d, eax
0x18002b3db  mov     ecx, 8; int
0x18002b3e0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b3e5  mov     edi, r12d
  ... truncated ...
```
