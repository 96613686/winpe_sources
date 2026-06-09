# RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)

- ea: `0x180008920`
- end: `0x180009216`
- name: `?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z`
- size: `2294`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int, struct ITerminal **, struct ITSSession **, void *TokenHandle)`
- caller_count: `18`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008290`
- `0x180009ee0`
- `0x18000b2b0`
- `0x18000c430`
- `0x18000da10`
- `0x18002c6c0`
- `0x180060880`
- `0x180060ee0`
- `0x1800616a0`
- `0x180061860`
- `0x180061ab0`
- `0x180061d30`
- `0x180061fd0`
- `0x180062560`
- `0x180062690`
- `0x1800628f0`
- `0x180062ae0`
- `0x180063030`

## callees

- `0x180008920`
- `0x1800095a0`
- `0x180009940`
- `0x18000fbe0`
- `0x180013070`
- `0x18003444c`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180009185`
- `ntdll!RtlCaptureStackBackTrace` at `0x180009185`
- `ntdll!RtlReleaseResource` at `0x180008b90`
- `ntdll!RtlReleaseResource` at `0x180008dbc`
- `ntdll!RtlReleaseResource` at `0x180008ef2`
- `ntdll!RtlReleaseResource` at `0x180008b90`
- `ntdll!RtlReleaseResource` at `0x180008dbc`
- `ntdll!RtlReleaseResource` at `0x180008ef2`
- `ntdll!RtlAcquireResourceShared` at `0x180008f1a`
- `ntdll!RtlAcquireResourceShared` at `0x180008f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000902c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000902c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008ab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008ab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ace`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008e41`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ace`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f9f`
- `RPCRT4!RpcImpersonateClient` at `0x180008977`
- `RPCRT4!RpcImpersonateClient` at `0x180008977`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008e71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008e71`

## string_xrefs

- `0x18000914f`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180009080`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180008f74`: `CRpcUtils::GetClientToken`
- `0x180008eac`: `CTSSessionSecurityDescriptor::IsSameSessionId`
- `0x180008ed7`: `CTSSessionSecurityDescriptor::AccessCheck`
- `0x18000910f`: `ptrCache->AccessCheck FAILED with ERROR_ACCESS_DENIED`
- `0x1800091c0`: `CheckClientAccess failed: 0x%x in %s`
- `0x18000905d`: `GetTokenInformation failed: 0x%x in %s`
- `0x180008f7e`: `OpenThreadToken failed: 0x%x in %s`
- `0x180009013`: `OpenThreadToken failed: 0x%x in %s`
- `0x180008fd6`: `AccessCheck failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
  if ( qword_18012EDF8 )
  {
    v13 = qword_18012EDF8;
    TokenHandle = (_DWORD *)qword_18012EDF8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18012EDF8 + 8LL))(qword_18012EDF8);
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
         qword_1800DD3A0,
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
  if ( qword_18012EDF8 )
  {
    v16 = qword_18012EDF8;
    TokenHandle = (_DWORD *)qword_18012EDF8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18012EDF8 + 8LL))(qword_18012EDF8);
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
0x180008920  mov     [rsp-8+arg_0], rbx
0x180008925  mov     [rsp-8+arg_18], r9
0x18000892a  mov     [rsp-8+arg_10], r8d
0x18000892f  mov     [rsp-8+arg_8], edx
0x180008933  push    rbp
0x180008934  push    rsi
0x180008935  push    rdi
0x180008936  push    r12
0x180008938  push    r13
0x18000893a  push    r14
0x18000893c  push    r15
0x18000893e  lea     rbp, [rsp-17h]
0x180008943  sub     rsp, 0A0h
0x18000894a  mov     r13d, ecx
0x18000894d  xor     r12d, r12d
0x180008950  mov     [rbp+47h+var_98], r12
0x180008954  mov     ebx, r12d
0x180008957  mov     [rbp+47h+var_58], rbx
0x18000895b  mov     esi, r12d
0x18000895e  mov     [rbp+47h+var_50], r12
0x180008962  mov     [rbp+47h+var_70], r12
0x180008966  mov     [rbp+47h+var_90], r12
0x18000896a  mov     [rbp+47h+var_78], r12
0x18000896e  mov     rdi, [rbp+47h+TokenHandle]
0x180008972  mov     [rdi], r12d
0x180008975  xor     ecx, ecx; BindingHandle
0x180008977  call    cs:__imp_RpcImpersonateClient
0x18000897e  nop     dword ptr [rax+rax+00h]
0x180008983  mov     r14d, eax
0x180008986  test    eax, eax
0x180008988  jle     short loc_180008995
0x18000898a  movzx   r14d, ax
0x18000898e  or      r14d, 80070000h
0x180008995  test    r14d, r14d
0x180008998  js      loc_180009076
0x18000899e  mov     [rbp+47h+var_9C], 1
0x1800089a5  mov     r15d, 1
0x1800089ab  mov     [rdi], r15d
0x1800089ae  mov     rdi, r12
0x1800089b1  mov     [rbp+47h+TokenHandle], r12
0x1800089b5  mov     rax, cs:qword_18012EDF8
0x1800089bc  test    rax, rax
0x1800089bf  jz      loc_1800090A2
0x1800089c5  mov     rdi, rax
0x1800089c8  mov     [rbp+47h+TokenHandle], rax
0x1800089cc  mov     rax, [rax]
0x1800089cf  mov     rcx, rdi
0x1800089d2  mov     rax, [rax+8]
0x1800089d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089db  mov     rax, [rdi]
0x1800089de  lea     r9, [rbp+47h+var_70]
0x1800089e2  xor     r8d, r8d
0x1800089e5  mov     edx, r13d
0x1800089e8  mov     rcx, rdi
0x1800089eb  mov     rax, [rax+0A0h]
0x1800089f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089f7  mov     r14d, eax
0x1800089fa  test    eax, eax
0x1800089fc  js      loc_180009096
0x180008a02  test    rdi, rdi
0x180008a05  jz      short loc_180008A17
0x180008a07  mov     rax, [rdi]
0x180008a0a  mov     rcx, rdi
0x180008a0d  mov     rax, [rax+10h]
0x180008a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a16  nop
0x180008a17  mov     r12, [rbp+47h+arg_20]
0x180008a1b  test    r14d, r14d
0x180008a1e  jns     loc_180008D50
0x180008a24  xor     edi, edi
0x180008a26  mov     [rbp+47h+TokenHandle], rdi
0x180008a2a  mov     rax, cs:qword_18012EDF8
0x180008a31  test    rax, rax
0x180008a34  jz      short loc_180008A4C
0x180008a36  mov     rdi, rax
0x180008a39  mov     [rbp+47h+TokenHandle], rax
0x180008a3d  mov     rax, [rax]
0x180008a40  mov     rcx, rdi
0x180008a43  mov     rax, [rax+8]
0x180008a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a4c  mov     rax, [rdi]
0x180008a4f  lea     rdx, [rbp+47h+var_78]
0x180008a53  mov     rcx, rdi
0x180008a56  mov     rax, [rax+98h]
0x180008a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a62  mov     r14d, eax
0x180008a65  mov     rax, [rdi]
0x180008a68  mov     rcx, rdi
0x180008a6b  mov     rax, [rax+10h]
0x180008a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a74  nop
0x180008a75  test    r14d, r14d
0x180008a78  js      loc_180009125
0x180008a7e  mov     rcx, [rbp+47h+var_78]
0x180008a82  mov     rax, [rcx]
0x180008a85  lea     r8, [rbp+47h+var_98]
0x180008a89  mov     edx, r13d
0x180008a8c  mov     rax, [rax+18h]
0x180008a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a95  mov     r14d, eax
0x180008a98  test    eax, eax
0x180008a9a  js      loc_180008DCE
0x180008aa0  test    r15d, r15d
0x180008aa3  jz      loc_180008C65
0x180008aa9  xor     r15d, r15d
0x180008aac  mov     [rbp+47h+TokenHandle], r15
0x180008ab0  call    cs:__imp_GetCurrentThread
0x180008ab7  nop     dword ptr [rax+rax+00h]
0x180008abc  mov     rcx, rax; ThreadHandle
0x180008abf  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180008ac3  mov     edx, 0Eh; DesiredAccess
0x180008ac8  mov     r8d, 1; OpenAsSelf
0x180008ace  call    cs:__imp_OpenThreadToken
0x180008ad5  nop     dword ptr [rax+rax+00h]
0x180008ada  test    eax, eax
0x180008adc  jz      loc_180008F4D
0x180008ae2  mov     r14d, r15d
0x180008ae5  mov     rax, [rbp+47h+TokenHandle]
0x180008ae9  mov     rbx, rax
0x180008aec  mov     [rbp+47h+var_58], rax
0x180008af0  test    r14d, r14d
0x180008af3  js      loc_180009145
0x180008af9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008b00  mov     ecx, 0A88h; unsigned __int64
0x180008b05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008b0a  mov     rdi, rax
0x180008b0d  test    rax, rax
0x180008b10  jz      loc_1800091D6
0x180008b16  lea     rax, ??_7?$CTSPrivateObject@UIUserName@@@@6B@; const CTSPrivateObject<IUserName>::`vftable'
0x180008b1d  mov     [rdi], rax
0x180008b20  lea     rax, aUsername; "UserName"
0x180008b27  mov     [rdi+10h], rax
0x180008b2b  mov     [rdi+8], r15d
0x180008b2f  mov     dword ptr [rdi+0Ch], 1
0x180008b36  lea     rsi, [rdi+628h]
0x180008b3d  mov     [rsi+8], rsi
0x180008b41  mov     [rsi], rsi
0x180008b44  mov     r14, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180008b4b  test    r14, r14
0x180008b4e  jz      short loc_180008B9D
0x180008b50  lea     rdx, [r14+18h]; struct CResource *
0x180008b54  lea     rcx, [rbp+47h+Resource]; this
0x180008b58  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180008b5d  lea     rax, [r14+8]
0x180008b61  mov     rcx, [rax+8]
0x180008b65  cmp     [rcx], rax
0x180008b68  jnz     loc_180008D49
0x180008b6e  mov     [rsi], rax
0x180008b71  mov     [rsi+8], rcx
0x180008b75  mov     [rcx], rsi
0x180008b78  mov     [rax+8], rsi
0x180008b7c  cmp     [rbp+47h+var_60], 0
0x180008b80  jz      short loc_180008B9D
0x180008b82  mov     [rbp+47h+var_60], r15d
0x180008b86  mov     rcx, [rbp+47h+Resource]; Resource
0x180008b8a  cmp     dword ptr [rcx+60h], 0
0x180008b8e  jz      short loc_180008B9D
0x180008b90  call    cs:__imp_RtlReleaseResource
0x180008b97  nop     dword ptr [rax+rax+00h]
0x180008b9c  nop
0x180008b9d  mov     [rdi+18h], r15
0x180008ba1  mov     [rdi+20h], r15d
0x180008ba5  mov     dword ptr [rbp+47h+TokenHandle], r15d
0x180008ba9  mov     eax, 1
0x180008bae  lock xadd [rdi+20h], eax
0x180008bb3  inc     eax
0x180008bb5  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180008bbc  jz      loc_180009165
0x180008bc2  lea     rax, ??_7CUserName@@6B@; const CUserName::`vftable'
0x180008bc9  mov     [rdi], rax
0x180008bcc  mov     [rdi+638h], r15
0x180008bd3  and     dword ptr [rdi+640h], 0FFFFFFE0h
0x180008bda  mov     [rdi+648h], r15
0x180008be1  mov     [rdi+0A58h], r15
0x180008be8  mov     [rdi+0A60h], r15
0x180008bef  mov     [rdi+0A68h], r15
0x180008bf6  mov     [rdi+0A70h], r15
0x180008bfd  and     dword ptr [rdi+0A78h], 0FFFFFFFCh
0x180008c04  mov     rsi, rdi
0x180008c07  mov     [rbp+47h+var_50], rdi
0x180008c0b  mov     rcx, rdi
0x180008c0e  mov     rax, cs:off_1800CF218
0x180008c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c1a  mov     rax, [rdi]
0x180008c1d  mov     r8d, 1
0x180008c23  mov     rdx, rbx
0x180008c26  mov     rcx, rdi
0x180008c29  mov     rax, [rax+18h]
0x180008c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c32  mov     r14d, eax
0x180008c35  test    eax, eax
0x180008c37  js      loc_180009196
0x180008c3d  mov     rcx, [rbp+47h+var_98]
0x180008c41  mov     rax, [rcx]
0x180008c44  mov     r9d, [rbp+47h+arg_10]
0x180008c48  mov     r8, rdi
0x180008c4b  mov     edx, [rbp+47h+arg_8]
0x180008c4e  mov     rax, [rax+90h]
0x180008c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5a  mov     r14d, eax
0x180008c5d  test    eax, eax
0x180008c5f  js      loc_1800091B6
0x180008c65  test    r12, r12
0x180008c68  jz      short loc_180008C7E
0x180008c6a  mov     rcx, [rbp+47h+var_98]
0x180008c6e  mov     [r12], rcx
0x180008c72  mov     rax, [rcx]
0x180008c75  mov     rax, [rax+8]
0x180008c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7e  mov     rdx, [rbp+47h+arg_18]
0x180008c82  test    rdx, rdx
0x180008c85  jz      short loc_180008CA8
0x180008c87  cmp     [rbp+47h+var_9C], 0
0x180008c8b  jz      short loc_180008CA8
0x180008c8d  mov     rcx, [rbp+47h+var_98]
0x180008c91  mov     rax, [rcx]
0x180008c94  mov     rax, [rax+68h]
0x180008c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9d  mov     r14d, eax
0x180008ca0  test    eax, eax
0x180008ca2  js      loc_1800091FC
0x180008ca8  mov     rcx, [rbp+47h+var_78]
0x180008cac  test    rcx, rcx
0x180008caf  jz      short loc_180008CBE
0x180008cb1  mov     rax, [rcx]
0x180008cb4  mov     rax, [rax+10h]
0x180008cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbd  nop
0x180008cbe  mov     rcx, [rbp+47h+var_90]
0x180008cc2  test    rcx, rcx
0x180008cc5  jz      short loc_180008CD4
0x180008cc7  mov     rax, [rcx]
0x180008cca  mov     rax, [rax+10h]
0x180008cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd3  nop
0x180008cd4  mov     rcx, [rbp+47h+var_70]
0x180008cd8  test    rcx, rcx
0x180008cdb  jz      short loc_180008CEA
0x180008cdd  mov     rax, [rcx]
0x180008ce0  mov     rax, [rax+10h]
0x180008ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce9  nop
0x180008cea  test    rsi, rsi
0x180008ced  jz      short loc_180008CFF
0x180008cef  mov     rax, [rsi]
0x180008cf2  mov     rcx, rsi
0x180008cf5  mov     rax, [rax+10h]
0x180008cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfe  nop
0x180008cff  test    rbx, rbx
0x180008d02  jz      short loc_180008D14
0x180008d04  mov     rcx, rbx; hObject
0x180008d07  call    cs:__imp_CloseHandle
0x180008d0e  nop     dword ptr [rax+rax+00h]
0x180008d13  nop
0x180008d14  mov     rcx, [rbp+47h+var_98]
0x180008d18  test    rcx, rcx
0x180008d1b  jz      short loc_180008D2A
0x180008d1d  mov     rax, [rcx]
0x180008d20  mov     rax, [rax+10h]
0x180008d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d29  nop
0x180008d2a  mov     eax, r14d
0x180008d2d  mov     rbx, [rsp+0D0h+arg_0]
0x180008d35  add     rsp, 0A0h
0x180008d3c  pop     r15
0x180008d3e  pop     r14
0x180008d40  pop     r13
0x180008d42  pop     r12
0x180008d44  pop     rdi
0x180008d45  pop     rsi
0x180008d46  pop     rbp
0x180008d47  retn
0x180008d49  mov     ecx, 3
0x180008d4e  int     29h; Win8: RtlFailFast(ecx)
0x180008d50  mov     rcx, [rbp+47h+var_70]
0x180008d54  test    rcx, rcx
0x180008d57  jz      loc_180008A24
0x180008d5d  mov     rax, [rcx]
0x180008d60  lea     r8, [rbp+47h+var_90]
0x180008d64  lea     rdx, qword_1800DD3A0
0x180008d6b  mov     rax, [rax+20h]
0x180008d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d74  test    eax, eax
0x180008d76  js      loc_180008A24
0x180008d7c  mov     rdx, [rbp+47h+arg_18]; struct ITerminal **
0x180008d80  test    rdx, rdx
0x180008d83  jnz     loc_1800090C8
0x180008d89  mov     r14, [rbp+47h+var_90]
0x180008d8d  lea     rdi, [r14+648h]
0x180008d94  mov     [rbp+47h+var_48], rdi
0x180008d98  mov     [rbp+47h+var_40], 1
0x180008d9f  cmp     dword ptr [rdi+60h], 0
0x180008da3  jnz     loc_180008F15
0x180008da9  cmp     dword ptr [r14+640h], 0
0x180008db1  jnz     short loc_180008DEE
0x180008db3  cmp     dword ptr [rdi+60h], 0
0x180008db7  jz      short loc_180008DC9
0x180008db9  mov     rcx, rdi; Resource
0x180008dbc  call    cs:__imp_RtlReleaseResource
  ... truncated ...
```
