# RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)

- ea: `0x1800092f0`
- end: `0x180009b7f`
- name: `?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z`
- size: `2191`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, struct ITerminal **, struct ITSSession **, _DWORD *TokenHandle)`
- caller_count: `18`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007870`
- `0x180008cb0`
- `0x18000a770`
- `0x18000c3e0`
- `0x18000d290`
- `0x18002af60`
- `0x18005d970`
- `0x18005df80`
- `0x18005e710`
- `0x18005e8c0`
- `0x18005eaf0`
- `0x18005ed60`
- `0x18005efe0`
- `0x18005f550`
- `0x18005f670`
- `0x18005f8d0`
- `0x18005fab0`
- `0x18005fff0`

## callees

- `0x1800092f0`
- `0x180009ee0`
- `0x18000a210`
- `0x18000f540`
- `0x1800127e0`
- `0x1800326dc`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180009af4`
- `ntdll!RtlCaptureStackBackTrace` at `0x180009af4`
- `ntdll!RtlReleaseResource` at `0x18000954e`
- `ntdll!RtlReleaseResource` at `0x18000976d`
- `ntdll!RtlReleaseResource` at `0x180009885`
- `ntdll!RtlReleaseResource` at `0x18000954e`
- `ntdll!RtlReleaseResource` at `0x18000976d`
- `ntdll!RtlReleaseResource` at `0x180009885`
- `ntdll!RtlAcquireResourceShared` at `0x1800098a7`
- `ntdll!RtlAcquireResourceShared` at `0x1800098a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000995d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000995d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000947a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800097ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000947a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800097ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009492`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800097e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009492`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800097e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000982d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000982d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009920`
- `RPCRT4!RpcImpersonateClient` at `0x180009347`
- `RPCRT4!RpcImpersonateClient` at `0x180009347`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009810`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009810`

## string_xrefs

- `0x18000983f`: `CTSSessionSecurityDescriptor::IsSameSessionId`
- `0x180009abe`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000986a`: `CTSSessionSecurityDescriptor::AccessCheck`
- `0x1800099ef`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800098f5`: `CRpcUtils::GetClientToken`
- `0x180009a7e`: `ptrCache->AccessCheck FAILED with ERROR_ACCESS_DENIED`
- `0x180009b29`: `CheckClientAccess failed: 0x%x in %s`
- `0x1800099cc`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800098ff`: `OpenThreadToken failed: 0x%x in %s`
- `0x180009988`: `OpenThreadToken failed: 0x%x in %s`
- `0x180009951`: `AccessCheck failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RCMRpcPrologueEx(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        struct ITerminal **a4,
        struct ITSSession **a5,
        _DWORD *TokenHandle)
{
  void *v7; // rbx
  _QWORD *v8; // rsi
  _DWORD *v9; // rdi
  RPC_STATUS v10; // eax
  signed int Terminal; // r14d
  int v12; // r15d
  __int64 v13; // rdi
  int v14; // eax
  int v15; // r14d
  __int64 v16; // rdi
  int v17; // eax
  HANDLE v18; // rax
  _DWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rdi
  _QWORD *v22; // rsi
  _QWORD *v23; // r14
  void **v24; // rcx
  char v25; // al
  int v26; // eax
  int v27; // eax
  struct ITSSession *v28; // rcx
  int v29; // eax
  CCachedTerminalInfo *v31; // r14
  struct _RTL_RESOURCE *v32; // rdi
  CTSSecurityDescriptor *v33; // rax
  signed int v34; // r15d
  HANDLE CurrentThread; // rax
  int v36; // eax
  signed int v37; // eax
  int v38; // eax
  signed int LastError; // eax
  signed int v40; // eax
  int TokenInformation; // [rsp+30h] [rbp-59h] BYREF
  int v42; // [rsp+34h] [rbp-55h]
  struct ITSSession *v43; // [rsp+38h] [rbp-51h] BYREF
  CCachedTerminalInfo *v44; // [rsp+40h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-41h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-39h] BYREF
  __int64 v47; // [rsp+58h] [rbp-31h] BYREF
  __int64 v48; // [rsp+60h] [rbp-29h] BYREF
  PRTL_RESOURCE Resource; // [rsp+68h] [rbp-21h] BYREF
  int v50; // [rsp+70h] [rbp-19h]
  _DWORD *v51; // [rsp+78h] [rbp-11h]
  _QWORD *v52; // [rsp+80h] [rbp-9h]
  char *v53; // [rsp+88h] [rbp-1h]
  int v54; // [rsp+90h] [rbp+7h]

  v43 = 0;
  v7 = 0;
  v51 = 0;
  v8 = 0;
  v52 = 0;
  v48 = 0;
  v44 = 0;
  v47 = 0;
  v9 = TokenHandle;
  *TokenHandle = 0;
  v10 = RpcImpersonateClient(0);
  Terminal = v10;
  if ( v10 > 0 )
    Terminal = (unsigned __int16)v10 | 0x80070000;
  if ( Terminal < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", Terminal, "RCMRpcPrologueEx");
    goto LABEL_36;
  }
  v42 = 1;
  v12 = 1;
  *v9 = 1;
  v13 = 0;
  TokenHandle = 0;
  if ( qword_180128DF0 )
  {
    v13 = qword_180128DF0;
    TokenHandle = (_DWORD *)qword_180128DF0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v13 + 160LL))(v13, a1, 0, &v48);
    v15 = v14;
    if ( v14 < 0 )
      _DbgPrintMessage(8, "GetStorageForSession failed: 0x%x in %s", (unsigned int)v14, "CHelper::GetStorageForSession");
  }
  else
  {
    v15 = -2147418113;
    _DbgPrintMessage(
      8,
      "GetInstanceOfRemoteConnectionManager failed: 0x%x in %s",
      2147549183LL,
      "CHelper::GetStorageForSession");
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v15 < 0
    || !v48
    || (*(int (__fastcall **)(__int64, __int64 *, CCachedTerminalInfo **))(*(_QWORD *)v48 + 32LL))(
         v48,
         qword_1800D7380,
         &v44) < 0 )
  {
    goto LABEL_10;
  }
  if ( a4 )
  {
    Terminal = CCachedTerminalInfo::GetTerminal(v44, a4);
    if ( Terminal < 0 )
      goto LABEL_76;
    v42 = 0;
  }
  v31 = v44;
  v32 = (struct _RTL_RESOURCE *)((char *)v44 + 1608);
  v53 = (char *)v44 + 1608;
  v54 = 1;
  if ( *((_DWORD *)v44 + 426) )
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v44 + 1608), 1u);
  if ( !*((_DWORD *)v31 + 400) )
  {
    if ( LODWORD(v32[1].Lock.DebugInfo) )
      RtlReleaseResource(v32);
    goto LABEL_10;
  }
  v33 = (CCachedTerminalInfo *)((char *)v31 + 1744);
  Resource = (PRTL_RESOURCE)((char *)v31 + 1744);
  if ( a3 )
  {
    LODWORD(TokenHandle) = 0;
    hObject = 0;
    TokenInformation = 0;
    ReturnLength = 0;
    v34 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
      goto LABEL_93;
    LastError = GetLastError();
    v34 = LastError;
    if ( LastError > 0 )
      v34 = (unsigned __int16)LastError | 0x80070000;
    if ( v34 >= 0 )
    {
LABEL_93:
      if ( GetTokenInformation(hObject, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
        goto LABEL_63;
      v40 = GetLastError();
      v34 = v40;
      if ( v40 > 0 )
        v34 = (unsigned __int16)v40 | 0x80070000;
      if ( v34 >= 0 )
      {
LABEL_63:
        v36 = TokenInformation;
        LODWORD(TokenHandle) = TokenInformation;
      }
      else
      {
        _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v34, "CUtils::GetUserSessionId");
        v36 = (int)TokenHandle;
      }
    }
    else
    {
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v34, "CUtils::GetUserSessionId");
      v36 = (int)TokenHandle;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      v36 = (int)TokenHandle;
    }
    if ( v34 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CUtils::GetUserSessionId() failed: 0x%x in %s",
        v34,
        "CTSSessionSecurityDescriptor::IsSameSessionId");
      Terminal = -2147024891;
      _DbgPrintMessage(
        8,
        "IsSameSessionId failed: 0x%x in %s",
        (unsigned int)v34,
        "CTSSessionSecurityDescriptor::AccessCheck");
      goto LABEL_68;
    }
    if ( v36 == a1 )
    {
      v33 = (CCachedTerminalInfo *)((char *)v31 + 1720);
      if ( !*((_QWORD *)v31 + 216) )
      {
        Terminal = -2147467259;
        _DbgPrintMessage(
          8,
          "AppContainer SD is NOT initialized! failed: 0x%x in %s",
          2147500037LL,
          "CTSSessionSecurityDescriptor::AccessCheck");
        goto LABEL_68;
      }
    }
    else
    {
      v33 = (CTSSecurityDescriptor *)Resource;
    }
  }
  v38 = CTSSecurityDescriptor::AccessCheck(v33, a2);
  Terminal = v38;
  if ( v38 < 0 )
    _DbgPrintMessage(
      8,
      "AccessCheck failed: 0x%x in %s",
      (unsigned int)v38,
      "CTSSessionSecurityDescriptor::AccessCheck");
LABEL_68:
  if ( LODWORD(v32[1].Lock.DebugInfo) )
    RtlReleaseResource(v32);
  if ( Terminal < 0 )
  {
    if ( Terminal == -2147024891 )
    {
      _DbgPrintMessage(8, "ptrCache->AccessCheck FAILED with ERROR_ACCESS_DENIED");
      goto LABEL_36;
    }
    v12 = 1;
LABEL_76:
    if ( Terminal == -2147467263 )
      goto LABEL_10;
    goto LABEL_72;
  }
  v12 = 0;
LABEL_72:
  if ( !a5 )
    goto LABEL_36;
LABEL_10:
  v16 = 0;
  TokenHandle = 0;
  if ( qword_180128DF0 )
  {
    v16 = qword_180128DF0;
    TokenHandle = (_DWORD *)qword_180128DF0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
  }
  Terminal = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 152LL))(v16, &v47);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( Terminal < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", Terminal, "RCMRpcPrologueEx");
    goto LABEL_36;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ITSSession **))(*(_QWORD *)v47 + 24LL))(v47, a1, &v43);
  Terminal = v17;
  if ( v17 < 0 )
  {
    _DbgPrintMessage(4, "FindSessionById failed: 0x%x in %s", v17, "RCMRpcPrologueEx");
    goto LABEL_36;
  }
  if ( v12 )
  {
    TokenHandle = 0;
    v18 = GetCurrentThread();
    if ( OpenThreadToken(v18, 0xEu, 1, (PHANDLE)&TokenHandle) )
    {
      Terminal = 0;
    }
    else
    {
      v37 = GetLastError();
      Terminal = v37;
      if ( v37 > 0 )
        Terminal = (unsigned __int16)v37 | 0x80070000;
      if ( Terminal < 0 )
      {
        _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", Terminal, "CRpcUtils::GetClientToken");
        v19 = TokenHandle;
        if ( TokenHandle )
        {
          CloseHandle(TokenHandle);
          goto LABEL_19;
        }
LABEL_18:
        v7 = v19;
        v51 = v19;
LABEL_19:
        if ( Terminal < 0 )
        {
          _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", Terminal, "RCMRpcPrologueEx");
          goto LABEL_36;
        }
        v20 = operator new(0xA88u, (const struct std::nothrow_t *)std::nothrow);
        v21 = v20;
        if ( !v20 )
        {
          Terminal = -2147024882;
          _DbgPrintMessage(8, "CUtils::GetInstanceOfUserName failed: 0x%x in %s", -2147024882, "RCMRpcPrologueEx");
          goto LABEL_36;
        }
        *v20 = &CTSPrivateObject<IUserName>::`vftable';
        v20[2] = "UserName";
        *((_DWORD *)v20 + 2) = 0;
        *((_DWORD *)v20 + 3) = 1;
        v22 = v20 + 197;
        v20[198] = v20 + 197;
        v20[197] = v20 + 197;
        v23 = g_pObjectTracker;
        if ( g_pObjectTracker )
        {
          CAutoExclusiveLock::CAutoExclusiveLock(
            (CAutoExclusiveLock *)&Resource,
            (struct CResource *)((char *)g_pObjectTracker + 24));
          v24 = (void **)v23[2];
          if ( *v24 != v23 + 1 )
            __fastfail(3u);
          *v22 = v23 + 1;
          v21[198] = v24;
          *v24 = v22;
          v23[2] = v22;
          if ( v50 )
          {
            v50 = 0;
            if ( LODWORD(Resource[1].Lock.DebugInfo) )
              RtlReleaseResource(Resource);
          }
        }
        v21[3] = 0;
        *((_DWORD *)v21 + 8) = 0;
        LODWORD(TokenHandle) = 0;
        v25 = _InterlockedIncrement((volatile signed __int32 *)v21 + 8);
        if ( g_bCaptureObjectStackTrace == 1 )
          RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v21[6 * (v25 & 0x1F) + 5], (PULONG)&TokenHandle);
        *v21 = &CUserName::`vftable';
        v21[199] = 0;
        *((_DWORD *)v21 + 400) &= 0xFFFFFFE0;
        v21[201] = 0;
        v21[331] = 0;
        v21[332] = 0;
        v21[333] = 0;
        v21[334] = 0;
        *((_DWORD *)v21 + 670) &= 0xFFFFFFFC;
        v8 = v21;
        v52 = v21;
        ((void (__fastcall *)(_QWORD *))CTSPrivateObject<IUserName>::AddRef)(v21);
        v26 = (*(__int64 (__fastcall **)(_QWORD *, void *, __int64))(*v21 + 24LL))(v21, v7, 1);
        Terminal = v26;
        if ( v26 < 0 )
        {
          _DbgPrintMessage(8, "ptrRequestorUserName->Initialize failed: 0x%x in %s", v26, "RCMRpcPrologueEx");
          goto LABEL_36;
        }
        v27 = (*(__int64 (__fastcall **)(struct ITSSession *, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)v43 + 144LL))(
                v43,
                a2,
                v21,
                a3);
        Terminal = v27;
        if ( v27 < 0 )
        {
          _DbgPrintMessage(8, "CheckClientAccess failed: 0x%x in %s", v27, "RCMRpcPrologueEx");
          goto LABEL_36;
        }
        goto LABEL_30;
      }
    }
    v19 = TokenHandle;
    goto LABEL_18;
  }
LABEL_30:
  if ( a5 )
  {
    v28 = v43;
    *a5 = v43;
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v28 + 8LL))(v28);
  }
  if ( a4 )
  {
    if ( v42 )
    {
      v29 = (*(__int64 (__fastcall **)(struct ITSSession *))(*(_QWORD *)v43 + 104LL))(v43);
      Terminal = v29;
      if ( v29 < 0 )
        _DbgPrintMessage(4, "Session->getTerminal failed: 0x%x", v29);
    }
  }
LABEL_36:
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v44 )
    (*(void (__fastcall **)(CCachedTerminalInfo *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v8 )
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  if ( v7 )
    CloseHandle(v7);
  if ( v43 )
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v43 + 16LL))(v43);
  return (unsigned int)Terminal;
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp-8+arg_0], rbx
0x1800092f5  mov     [rsp-8+arg_18], r9
0x1800092fa  mov     [rsp-8+arg_10], r8d
0x1800092ff  mov     [rsp-8+arg_8], edx
0x180009303  push    rbp
0x180009304  push    rsi
0x180009305  push    rdi
0x180009306  push    r12
0x180009308  push    r13
0x18000930a  push    r14
0x18000930c  push    r15
0x18000930e  lea     rbp, [rsp-17h]
0x180009313  sub     rsp, 0A0h
0x18000931a  mov     r13d, ecx
0x18000931d  xor     r12d, r12d
0x180009320  mov     [rbp+47h+var_98], r12
0x180009324  mov     ebx, r12d
0x180009327  mov     [rbp+47h+var_58], rbx
0x18000932b  mov     esi, r12d
0x18000932e  mov     [rbp+47h+var_50], r12
0x180009332  mov     [rbp+47h+var_70], r12
0x180009336  mov     [rbp+47h+var_90], r12
0x18000933a  mov     [rbp+47h+var_78], r12
0x18000933e  mov     rdi, [rbp+47h+TokenHandle]
0x180009342  mov     [rdi], r12d
0x180009345  xor     ecx, ecx; BindingHandle
0x180009347  call    cs:__imp_RpcImpersonateClient
0x18000934d  mov     r14d, eax
0x180009350  test    eax, eax
0x180009352  jle     short loc_18000935F
0x180009354  movzx   r14d, ax
0x180009358  or      r14d, 80070000h
0x18000935f  test    r14d, r14d
0x180009362  js      loc_1800099E5
0x180009368  mov     [rbp+47h+var_9C], 1
0x18000936f  mov     r15d, 1
0x180009375  mov     [rdi], r15d
0x180009378  mov     rdi, r12
0x18000937b  mov     [rbp+47h+TokenHandle], r12
0x18000937f  mov     rax, cs:qword_180128DF0
0x180009386  test    rax, rax
0x180009389  jz      loc_180009A11
0x18000938f  mov     rdi, rax
0x180009392  mov     [rbp+47h+TokenHandle], rax
0x180009396  mov     rax, [rax]
0x180009399  mov     rcx, rdi
0x18000939c  mov     rax, [rax+8]
0x1800093a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a5  mov     rax, [rdi]
0x1800093a8  lea     r9, [rbp+47h+var_70]
0x1800093ac  xor     r8d, r8d
0x1800093af  mov     edx, r13d
0x1800093b2  mov     rcx, rdi
0x1800093b5  mov     rax, [rax+0A0h]
0x1800093bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c1  mov     r14d, eax
0x1800093c4  test    eax, eax
0x1800093c6  js      loc_180009A05
0x1800093cc  test    rdi, rdi
0x1800093cf  jz      short loc_1800093E1
0x1800093d1  mov     rax, [rdi]
0x1800093d4  mov     rcx, rdi
0x1800093d7  mov     rax, [rax+10h]
0x1800093db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e0  nop
0x1800093e1  mov     r12, [rbp+47h+arg_20]
0x1800093e5  test    r14d, r14d
0x1800093e8  jns     loc_180009701
0x1800093ee  xor     edi, edi
0x1800093f0  mov     [rbp+47h+TokenHandle], rdi
0x1800093f4  mov     rax, cs:qword_180128DF0
0x1800093fb  test    rax, rax
0x1800093fe  jz      short loc_180009416
0x180009400  mov     rdi, rax
0x180009403  mov     [rbp+47h+TokenHandle], rax
0x180009407  mov     rax, [rax]
0x18000940a  mov     rcx, rdi
0x18000940d  mov     rax, [rax+8]
0x180009411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009416  mov     rax, [rdi]
0x180009419  lea     rdx, [rbp+47h+var_78]
0x18000941d  mov     rcx, rdi
0x180009420  mov     rax, [rax+98h]
0x180009427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000942c  mov     r14d, eax
0x18000942f  mov     rax, [rdi]
0x180009432  mov     rcx, rdi
0x180009435  mov     rax, [rax+10h]
0x180009439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943e  nop
0x18000943f  test    r14d, r14d
0x180009442  js      loc_180009A94
0x180009448  mov     rcx, [rbp+47h+var_78]
0x18000944c  mov     rax, [rcx]
0x18000944f  lea     r8, [rbp+47h+var_98]
0x180009453  mov     edx, r13d
0x180009456  mov     rax, [rax+18h]
0x18000945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945f  mov     r14d, eax
0x180009462  test    eax, eax
0x180009464  js      loc_180009779
0x18000946a  test    r15d, r15d
0x18000946d  jz      loc_18000961D
0x180009473  xor     r15d, r15d
0x180009476  mov     [rbp+47h+TokenHandle], r15
0x18000947a  call    cs:__imp_GetCurrentThread
0x180009480  mov     rcx, rax; ThreadHandle
0x180009483  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180009487  mov     edx, 0Eh; DesiredAccess
0x18000948c  mov     r8d, 1; OpenAsSelf
0x180009492  call    cs:__imp_OpenThreadToken
0x180009498  test    eax, eax
0x18000949a  jz      loc_1800098D4
0x1800094a0  mov     r14d, r15d
0x1800094a3  mov     rax, [rbp+47h+TokenHandle]
0x1800094a7  mov     rbx, rax
0x1800094aa  mov     [rbp+47h+var_58], rax
0x1800094ae  test    r14d, r14d
0x1800094b1  js      loc_180009AB4
0x1800094b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800094be  mov     ecx, 0A88h; unsigned __int64
0x1800094c3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800094c8  mov     rdi, rax
0x1800094cb  test    rax, rax
0x1800094ce  jz      loc_180009B3F
0x1800094d4  lea     rax, ??_7?$CTSPrivateObject@UIUserName@@@@6B@; const CTSPrivateObject<IUserName>::`vftable'
0x1800094db  mov     [rdi], rax
0x1800094de  lea     rax, aUsername; "UserName"
0x1800094e5  mov     [rdi+10h], rax
0x1800094e9  mov     [rdi+8], r15d
0x1800094ed  mov     dword ptr [rdi+0Ch], 1
0x1800094f4  lea     rsi, [rdi+628h]
0x1800094fb  mov     [rsi+8], rsi
0x1800094ff  mov     [rsi], rsi
0x180009502  mov     r14, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180009509  test    r14, r14
0x18000950c  jz      short loc_180009555
0x18000950e  lea     rdx, [r14+18h]; struct CResource *
0x180009512  lea     rcx, [rbp+47h+Resource]; this
0x180009516  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18000951b  lea     rax, [r14+8]
0x18000951f  mov     rcx, [rax+8]
0x180009523  cmp     [rcx], rax
0x180009526  jnz     loc_1800096FA
0x18000952c  mov     [rsi], rax
0x18000952f  mov     [rsi+8], rcx
0x180009533  mov     [rcx], rsi
0x180009536  mov     [rax+8], rsi
0x18000953a  cmp     [rbp+47h+var_60], 0
0x18000953e  jz      short loc_180009555
0x180009540  mov     [rbp+47h+var_60], r15d
0x180009544  mov     rcx, [rbp+47h+Resource]; Resource
0x180009548  cmp     dword ptr [rcx+60h], 0
0x18000954c  jz      short loc_180009555
0x18000954e  call    cs:__imp_RtlReleaseResource
0x180009554  nop
0x180009555  mov     [rdi+18h], r15
0x180009559  mov     [rdi+20h], r15d
0x18000955d  mov     dword ptr [rbp+47h+TokenHandle], r15d
0x180009561  mov     eax, 1
0x180009566  lock xadd [rdi+20h], eax
0x18000956b  inc     eax
0x18000956d  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180009574  jz      loc_180009AD4
0x18000957a  lea     rax, ??_7CUserName@@6B@; const CUserName::`vftable'
0x180009581  mov     [rdi], rax
0x180009584  mov     [rdi+638h], r15
0x18000958b  and     dword ptr [rdi+640h], 0FFFFFFE0h
0x180009592  mov     [rdi+648h], r15
0x180009599  mov     [rdi+0A58h], r15
0x1800095a0  mov     [rdi+0A60h], r15
0x1800095a7  mov     [rdi+0A68h], r15
0x1800095ae  mov     [rdi+0A70h], r15
0x1800095b5  and     dword ptr [rdi+0A78h], 0FFFFFFFCh
0x1800095bc  mov     rsi, rdi
0x1800095bf  mov     [rbp+47h+var_50], rdi
0x1800095c3  mov     rcx, rdi
0x1800095c6  mov     rax, cs:off_1800C91D8
0x1800095cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d2  mov     rax, [rdi]
0x1800095d5  mov     r8d, 1
0x1800095db  mov     rdx, rbx
0x1800095de  mov     rcx, rdi
0x1800095e1  mov     rax, [rax+18h]
0x1800095e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ea  mov     r14d, eax
0x1800095ed  test    eax, eax
0x1800095ef  js      loc_180009AFF
0x1800095f5  mov     rcx, [rbp+47h+var_98]
0x1800095f9  mov     rax, [rcx]
0x1800095fc  mov     r9d, [rbp+47h+arg_10]
0x180009600  mov     r8, rdi
0x180009603  mov     edx, [rbp+47h+arg_8]
0x180009606  mov     rax, [rax+90h]
0x18000960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009612  mov     r14d, eax
0x180009615  test    eax, eax
0x180009617  js      loc_180009B1F
0x18000961d  test    r12, r12
0x180009620  jz      short loc_180009636
0x180009622  mov     rcx, [rbp+47h+var_98]
0x180009626  mov     [r12], rcx
0x18000962a  mov     rax, [rcx]
0x18000962d  mov     rax, [rax+8]
0x180009631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009636  mov     rdx, [rbp+47h+arg_18]
0x18000963a  test    rdx, rdx
0x18000963d  jz      short loc_180009660
0x18000963f  cmp     [rbp+47h+var_9C], 0
0x180009643  jz      short loc_180009660
0x180009645  mov     rcx, [rbp+47h+var_98]
0x180009649  mov     rax, [rcx]
0x18000964c  mov     rax, [rax+68h]
0x180009650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009655  mov     r14d, eax
0x180009658  test    eax, eax
0x18000965a  js      loc_180009B65
0x180009660  mov     rcx, [rbp+47h+var_78]
0x180009664  test    rcx, rcx
0x180009667  jz      short loc_180009676
0x180009669  mov     rax, [rcx]
0x18000966c  mov     rax, [rax+10h]
0x180009670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009675  nop
0x180009676  mov     rcx, [rbp+47h+var_90]
0x18000967a  test    rcx, rcx
0x18000967d  jz      short loc_18000968C
0x18000967f  mov     rax, [rcx]
0x180009682  mov     rax, [rax+10h]
0x180009686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968b  nop
0x18000968c  mov     rcx, [rbp+47h+var_70]
0x180009690  test    rcx, rcx
0x180009693  jz      short loc_1800096A2
0x180009695  mov     rax, [rcx]
0x180009698  mov     rax, [rax+10h]
0x18000969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a1  nop
0x1800096a2  test    rsi, rsi
0x1800096a5  jz      short loc_1800096B7
0x1800096a7  mov     rax, [rsi]
0x1800096aa  mov     rcx, rsi
0x1800096ad  mov     rax, [rax+10h]
0x1800096b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b6  nop
0x1800096b7  test    rbx, rbx
0x1800096ba  jz      short loc_1800096C6
0x1800096bc  mov     rcx, rbx; hObject
0x1800096bf  call    cs:__imp_CloseHandle
0x1800096c5  nop
0x1800096c6  mov     rcx, [rbp+47h+var_98]
0x1800096ca  test    rcx, rcx
0x1800096cd  jz      short loc_1800096DC
0x1800096cf  mov     rax, [rcx]
0x1800096d2  mov     rax, [rax+10h]
0x1800096d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096db  nop
0x1800096dc  mov     eax, r14d
0x1800096df  mov     rbx, [rsp+0D0h+arg_0]
0x1800096e7  add     rsp, 0A0h
0x1800096ee  pop     r15
0x1800096f0  pop     r14
0x1800096f2  pop     r13
0x1800096f4  pop     r12
0x1800096f6  pop     rdi
0x1800096f7  pop     rsi
0x1800096f8  pop     rbp
0x1800096f9  retn
0x1800096fa  mov     ecx, 3
0x1800096ff  int     29h; Win8: RtlFailFast(ecx)
0x180009701  mov     rcx, [rbp+47h+var_70]
0x180009705  test    rcx, rcx
0x180009708  jz      loc_1800093EE
0x18000970e  mov     rax, [rcx]
0x180009711  lea     r8, [rbp+47h+var_90]
0x180009715  lea     rdx, qword_1800D7380
0x18000971c  mov     rax, [rax+20h]
0x180009720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009725  test    eax, eax
0x180009727  js      loc_1800093EE
0x18000972d  mov     rdx, [rbp+47h+arg_18]; struct ITerminal **
0x180009731  test    rdx, rdx
0x180009734  jnz     loc_180009A37
0x18000973a  mov     r14, [rbp+47h+var_90]
0x18000973e  lea     rdi, [r14+648h]
0x180009745  mov     [rbp+47h+var_48], rdi
0x180009749  mov     [rbp+47h+var_40], 1
0x180009750  cmp     dword ptr [rdi+60h], 0
0x180009754  jnz     loc_1800098A2
0x18000975a  cmp     dword ptr [r14+640h], 0
0x180009762  jnz     short loc_180009799
0x180009764  cmp     dword ptr [rdi+60h], 0
0x180009768  jz      short loc_180009774
0x18000976a  mov     rcx, rdi; Resource
0x18000976d  call    cs:__imp_RtlReleaseResource
0x180009773  nop
0x180009774  jmp     loc_1800093EE
0x180009779  lea     r9, aRcmrpcprologue_0; "RCMRpcPrologueEx"
0x180009780  mov     r8d, eax
0x180009783  lea     rdx, aFindsessionbyi_0; "FindSessionById failed: 0x%x in %s"
  ... truncated ...
```
