# RpcRcmShadow2

- ea: `0x18002c6c0`
- end: `0x18002ccb2`
- name: `RpcRcmShadow2`
- size: `1522`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008920`
- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x180012d10`
- `0x1800139c0`
- `0x180016558`
- `0x18002c6c0`
- `0x18002ccb8`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x18005e888`
- `0x18005f2a4`
- `0x18007d9d8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c910`
- `RPCRT4!RpcRevertToSelf` at `0x18002c96c`
- `RPCRT4!RpcRevertToSelf` at `0x18002cb78`
- `RPCRT4!RpcRevertToSelf` at `0x18002c96c`
- `RPCRT4!RpcRevertToSelf` at `0x18002cb78`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c943`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c943`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cc10`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cc1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cc10`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cc1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc4b`
- `SspiCli!GetUserNameExW` at `0x18002c895`
- `SspiCli!GetUserNameExW` at `0x18002c8fd`
- `SspiCli!GetUserNameExW` at `0x18002c895`
- `SspiCli!GetUserNameExW` at `0x18002c8fd`

## string_xrefs

- `0x18002c9cf`: `GetSessionAgent failed: 0x%x in %s`
- `0x18002ca0d`: `CreateShadowInivitation failed: 0x%x in %s`
- `0x18002caec`: `StringCchCopyW failed: 0x%x in %s`

## pseudocode

```c
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
          v34 = (**v47)(v47, qword_1800DD390, &v46);
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
0x18002c6c0  mov     [rsp-8+arg_0], rbx
0x18002c6c5  push    rbp
0x18002c6c6  push    rsi
0x18002c6c7  push    rdi
0x18002c6c8  push    r12
0x18002c6ca  push    r13
0x18002c6cc  push    r14
0x18002c6ce  push    r15
0x18002c6d0  lea     rbp, [rsp-210h]
0x18002c6d8  sub     rsp, 310h
0x18002c6df  mov     rax, cs:__security_cookie
0x18002c6e6  xor     rax, rsp
0x18002c6e9  mov     [rbp+240h+var_40], rax
0x18002c6f0  mov     rax, [rbp+240h+arg_28]
0x18002c6f7  lea     rcx, [rbp+240h+var_290]; this
0x18002c6fb  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW
0x18002c702  mov     r15, [rbp+240h+arg_20]
0x18002c709  mov     r12d, r8d
0x18002c70c  mov     [rbp+240h+var_2A8], rax
0x18002c710  lea     r8, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002c717  xor     eax, eax
0x18002c719  mov     dword ptr [rsp+340h+var_300], edx
0x18002c71d  mov     edi, edx
0x18002c71f  mov     [rsp+340h+var_2EC], eax
0x18002c723  xor     edx, edx; int
0x18002c725  mov     [rsp+340h+bstrString], rax
0x18002c72a  mov     esi, eax
0x18002c72c  mov     [rbp+240h+var_2B0], rax
0x18002c730  mov     [rbp+240h+var_2B8], rax
0x18002c734  mov     r14d, eax
0x18002c737  mov     [rbp+240h+var_2C0], rax
0x18002c73b  mov     ebx, eax
0x18002c73d  mov     [rsp+340h+var_2C8], rax
0x18002c742  mov     r13d, eax
0x18002c745  mov     [rsp+340h+nSize], eax
0x18002c749  mov     [rsp+340h+pv], rax
0x18002c74e  mov     [rsp+340h+var_2E0], rax
0x18002c753  mov     [rsp+340h+var_2D8], r9d
0x18002c758  movdqu  [rbp+240h+var_2A0], xmm0
0x18002c75d  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002c762  lea     rax, [rsp+340h+var_2EC]
0x18002c767  xor     r9d, r9d; struct ITerminal **
0x18002c76a  mov     [rsp+340h+TokenHandle], rax; TokenHandle
0x18002c76f  lea     edx, [r13+10h]; unsigned int
0x18002c773  lea     rax, [rbp+240h+var_2B0]
0x18002c777  xor     r8d, r8d; int
0x18002c77a  mov     ecx, edi; unsigned int
0x18002c77c  mov     [rsp+340h+var_320], rax; struct ITSSession **
0x18002c781  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18002c786  mov     edi, eax
0x18002c788  test    eax, eax
0x18002c78a  jns     short loc_18002C7BA
0x18002c78c  lea     eax, [r13+1]
0x18002c790  cmp     edi, 800708CAh
0x18002c796  lea     ecx, [rax+3]
0x18002c799  mov     r8d, edi
0x18002c79c  cmovnz  eax, ecx
0x18002c79f  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18002c7a6  mov     ecx, eax; int
0x18002c7a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c7ad  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002c7b2  xor     r12d, r12d
0x18002c7b5  jmp     loc_18002CB71
0x18002c7ba  mov     rbx, [rbp+240h+var_2B0]
0x18002c7be  lea     r8, [rsp+340h+var_2E0]; unsigned __int16 **
0x18002c7c3  mov     rcx, rbx; struct ITSSession *
0x18002c7c6  lea     rdx, [rsp+340h+pv]; unsigned __int16 **
0x18002c7cb  call    ?GetUserNameDomain@CHelper@@SAJPEAUITSSession@@PEAPEAG1@Z; CHelper::GetUserNameDomain(ITSSession *,ushort * *,ushort * *)
0x18002c7d0  xor     r8d, r8d
0x18002c7d3  mov     edi, eax
0x18002c7d5  test    eax, eax
0x18002c7d7  jns     short loc_18002C7F9
0x18002c7d9  lea     rdx, aChelperGetuser_0; "CHelper::GetUserNameDomain failed: 0x%x"...
0x18002c7e0  mov     r8d, eax
0x18002c7e3  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002c7ea  mov     ecx, 8; int
0x18002c7ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c7f4  mov     rbx, rsi
0x18002c7f7  jmp     short loc_18002C7AD
0x18002c7f9  mov     rax, [rsp+340h+pv]
0x18002c7fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c802  mov     rcx, r9
0x18002c805  inc     rcx
0x18002c808  cmp     [rax+rcx*2], r8w
0x18002c80d  jnz     short loc_18002C805
0x18002c80f  mov     rdx, [rsp+340h+var_2E0]
0x18002c814  mov     rax, r9
0x18002c817  inc     rax
0x18002c81a  cmp     [rdx+rax*2], r8w
0x18002c81f  jnz     short loc_18002C817
0x18002c821  lea     rdi, [rcx+2]
0x18002c825  add     rdi, rax
0x18002c828  mov     eax, 2
0x18002c82d  mul     rdi
0x18002c830  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c837  cmovb   rax, r9
0x18002c83b  mov     rcx, rax; unsigned __int64
0x18002c83e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002c843  mov     r13, rax
0x18002c846  test    rax, rax
0x18002c849  jnz     short loc_18002C852
0x18002c84b  mov     edi, 8007000Eh
0x18002c850  jmp     short loc_18002C7F4
0x18002c852  mov     rax, [rsp+340h+pv]
0x18002c857  lea     r8, aSS_0; "%s\\%s"
0x18002c85e  mov     r9, [rsp+340h+var_2E0]
0x18002c863  mov     rdx, rdi; unsigned __int64
0x18002c866  mov     rcx, r13; unsigned __int16 *
0x18002c869  mov     [rsp+340h+var_320], rax
0x18002c86e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c873  mov     edi, eax
0x18002c875  test    eax, eax
0x18002c877  jns     short loc_18002C885
0x18002c879  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18002c880  jmp     loc_18002C7E0
0x18002c885  xor     edi, edi
0x18002c887  lea     r8, [rsp+340h+nSize]; nSize
0x18002c88c  xor     edx, edx; lpNameBuffer
0x18002c88e  mov     [rsp+340h+nSize], edi
0x18002c892  lea     ecx, [rdi+2]; NameFormat
0x18002c895  call    cs:__imp_GetUserNameExW
0x18002c89c  nop     dword ptr [rax+rax+00h]
0x18002c8a1  movzx   eax, al
0x18002c8a4  test    eax, eax
0x18002c8a6  jnz     loc_18002C940
0x18002c8ac  call    cs:__imp_GetLastError
0x18002c8b3  nop     dword ptr [rax+rax+00h]
0x18002c8b8  cmp     eax, 0EAh
0x18002c8bd  jnz     short loc_18002C910
0x18002c8bf  mov     eax, [rsp+340h+nSize]
0x18002c8c3  test    eax, eax
0x18002c8c5  jz      short loc_18002C910
0x18002c8c7  mov     ecx, eax
0x18002c8c9  lea     eax, [rdi+2]
0x18002c8cc  mul     rcx
0x18002c8cf  lea     rcx, [rdi-1]
0x18002c8d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c8da  cmovb   rax, rcx
0x18002c8de  mov     rcx, rax; unsigned __int64
0x18002c8e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002c8e6  mov     r14, rax
0x18002c8e9  test    rax, rax
0x18002c8ec  jz      loc_18002C84B
0x18002c8f2  lea     r8, [rsp+340h+nSize]; nSize
0x18002c8f7  mov     rdx, rax; lpNameBuffer
0x18002c8fa  lea     ecx, [rdi+2]; NameFormat
0x18002c8fd  call    cs:__imp_GetUserNameExW
0x18002c904  nop     dword ptr [rax+rax+00h]
0x18002c909  movzx   eax, al
0x18002c90c  test    eax, eax
0x18002c90e  jnz     short loc_18002C940
0x18002c910  call    cs:__imp_GetLastError
0x18002c917  nop     dword ptr [rax+rax+00h]
0x18002c91c  mov     edi, eax
0x18002c91e  test    eax, eax
0x18002c920  jle     short loc_18002C92D
0x18002c922  movzx   edi, di
0x18002c925  or      edi, 80070000h
0x18002c92b  test    edi, edi
0x18002c92d  jns     short loc_18002C93E
0x18002c92f  mov     r8d, edi
0x18002c932  lea     rdx, aGetusernameexF; "GetUserNameEx failed: 0x%x in %s"
0x18002c939  jmp     loc_18002C7E3
0x18002c93e  xor     edi, edi
0x18002c940  mov     rcx, r14; psz
0x18002c943  call    cs:__imp_SysAllocString
0x18002c94a  nop     dword ptr [rax+rax+00h]
0x18002c94f  mov     [rsp+340h+var_2F8], rax
0x18002c954  test    rax, rax
0x18002c957  jnz     short loc_18002C966
0x18002c959  mov     edi, 8007000Eh
0x18002c95e  mov     rbx, rax
0x18002c961  jmp     loc_18002C7AD
0x18002c966  cmp     [rsp+340h+var_2EC], edi
0x18002c96a  jz      short loc_18002C9B9
0x18002c96c  call    cs:__imp_RpcRevertToSelf
0x18002c973  nop     dword ptr [rax+rax+00h]
0x18002c978  mov     edi, eax
0x18002c97a  xor     eax, eax
0x18002c97c  test    edi, edi
0x18002c97e  jle     short loc_18002C98B
0x18002c980  movzx   edi, di
0x18002c983  or      edi, 80070000h
0x18002c989  test    edi, edi
0x18002c98b  jns     short loc_18002C9B5
0x18002c98d  mov     r8d, edi
0x18002c990  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: 0x%x in %s"
0x18002c997  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002c99e  mov     ecx, 8; int
0x18002c9a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c9a8  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002c9ad  xor     r12d, r12d
0x18002c9b0  jmp     loc_18002CB6C
0x18002c9b5  mov     [rsp+340h+var_2EC], eax
0x18002c9b9  mov     ecx, dword ptr [rsp+340h+var_300]; unsigned int
0x18002c9bd  lea     rdx, [rbp+240h+var_2B8]; struct IRdpSessionAgent **
0x18002c9c1  call    ?GetSessionAgent@@YAJKPEAPEAUIRdpSessionAgent@@@Z; GetSessionAgent(ulong,IRdpSessionAgent * *)
0x18002c9c6  mov     edi, eax
0x18002c9c8  test    eax, eax
0x18002c9ca  jns     short loc_18002C9D8
0x18002c9cc  mov     r8d, eax
0x18002c9cf  lea     rdx, aGetsessionagen; "GetSessionAgent failed: 0x%x in %s"
0x18002c9d6  jmp     short loc_18002C997
0x18002c9d8  mov     rcx, [rbp+240h+var_2B8]
0x18002c9dc  lea     rdx, [rsp+340h+bstrString]
0x18002c9e1  mov     r9d, [rsp+340h+var_2D8]
0x18002c9e6  mov     r8d, r12d
0x18002c9e9  mov     [rsp+340h+TokenHandle], rdx
0x18002c9ee  mov     rdx, [rsp+340h+var_2F8]
0x18002c9f3  mov     rax, [rcx]
0x18002c9f6  mov     [rsp+340h+var_320], r15
0x18002c9fb  mov     rax, [rax+18h]
0x18002c9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca04  mov     edi, eax
0x18002ca06  test    eax, eax
0x18002ca08  jns     short loc_18002CA16
0x18002ca0a  mov     r8d, eax
0x18002ca0d  lea     rdx, aCreateshadowin; "CreateShadowInivitation failed: 0x%x in"...
0x18002ca14  jmp     short loc_18002C997
0x18002ca16  mov     ecx, [r15]
0x18002ca19  test    ecx, ecx
0x18002ca1b  jz      short loc_18002CA5A
0x18002ca1d  sub     ecx, 1
0x18002ca20  jz      short loc_18002CA3E
0x18002ca22  cmp     ecx, 5
0x18002ca25  jz      short loc_18002CA30
0x18002ca27  movups  xmm0, cs:EVENT_TS_SHADOW_POLICY
0x18002ca2e  jmp     short loc_18002CA37
0x18002ca30  movups  xmm0, cs:EVENT_TS_SHADOW_BUSY
0x18002ca37  movdqu  [rbp+240h+var_2A0], xmm0
0x18002ca3c  jmp     short loc_18002CA79
0x18002ca3e  mov     eax, 1
0x18002ca43  cmp     r12d, eax
0x18002ca46  jnz     short loc_18002CA51
0x18002ca48  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_DENY
0x18002ca4f  jmp     short loc_18002CA74
0x18002ca51  movups  xmm0, cs:EVENT_TS_SHADOW_VIEW_PERMISSION_DENY
0x18002ca58  jmp     short loc_18002CA74
0x18002ca5a  mov     eax, 1
0x18002ca5f  cmp     r12d, eax
0x18002ca62  jnz     short loc_18002CA6D
0x18002ca64  movups  xmm0, cs:EVENT_TS_SHADOW_CONTROL_PERMISSION_ALLOW
0x18002ca6b  jmp     short loc_18002CA74
0x18002ca6d  movups  xmm0, cs:EVENT_TS_SHADOW_VIEW_PERMISSION_ALLOW
0x18002ca74  movdqa  [rbp+240h+var_2A0], xmm0
0x18002ca79  mov     r15d, dword ptr [rsp+340h+var_300]
0x18002ca7e  lea     rdx, [rbp+240h+var_2A0]
0x18002ca82  mov     r9, r14
0x18002ca85  mov     dword ptr [rsp+340h+var_320], r15d
0x18002ca8a  mov     r8, r13
0x18002ca8d  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002ca94  call    ??$RaiseEvent@PEAGPEAGK@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG1K@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ulong>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ulong)
0x18002ca99  xor     r12d, r12d
0x18002ca9c  mov     edi, eax
0x18002ca9e  test    eax, eax
0x18002caa0  jle     short loc_18002CAAB
0x18002caa2  movzx   edi, ax
0x18002caa5  or      edi, 80070000h
0x18002caab  test    edi, edi
0x18002caad  jns     short loc_18002CACF
0x18002caaf  mov     r8d, edi
0x18002cab2  lea     rdx, aTsRaiseEvent3F_1; "TS_RAISE_EVENT_3 failed: 0x%x in %s"
0x18002cab9  lea     r9, aRpcrcmshadow2; "RpcRcmShadow2"
0x18002cac0  mov     ecx, 8; int
0x18002cac5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002caca  jmp     loc_18002CB6C
0x18002cacf  mov     edx, dword ptr [rbp+240h+arg_30]; unsigned __int64
0x18002cad5  mov     r8, [rsp+340h+bstrString]; unsigned __int16 *
0x18002cada  mov     rcx, [rbp+240h+var_2A8]; unsigned __int16 *
0x18002cade  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cae3  mov     edi, eax
0x18002cae5  test    eax, eax
0x18002cae7  jns     short loc_18002CAF5
0x18002cae9  mov     r8d, eax
0x18002caec  lea     rdx, aStringcchcopyw; "StringCchCopyW failed: 0x%x in %s"
0x18002caf3  jmp     short loc_18002CAB9
0x18002caf5  mov     rax, [rbx]
0x18002caf8  lea     rdx, [rbp+240h+var_2C0]
0x18002cafc  mov     rcx, rbx
0x18002caff  mov     rax, [rax+68h]
0x18002cb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb08  test    eax, eax
0x18002cb0a  jns     short loc_18002CB15
0x18002cb0c  lea     rdx, aSpsessionGette; "spSession->getTerminal failed: 0x%x"
0x18002cb13  jmp     short loc_18002CB5C
0x18002cb15  mov     rcx, [rbp+240h+var_2C0]
0x18002cb19  lea     r8, [rsp+340h+var_2C8]
0x18002cb1e  lea     rdx, qword_1800DD390
0x18002cb25  mov     rax, [rcx]
0x18002cb28  mov     rax, [rax]
0x18002cb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb30  test    eax, eax
0x18002cb32  jns     short loc_18002CB3D
0x18002cb34  lea     rdx, aSpterminalQuer; "spTerminal->QueryInterface failed: 0x%x"
0x18002cb3b  jmp     short loc_18002CB5C
0x18002cb3d  mov     rcx, [rsp+340h+var_2C8]
0x18002cb42  mov     rax, [rcx]
0x18002cb45  mov     rax, [rax+220h]
0x18002cb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb51  test    eax, eax
  ... truncated ...
```
