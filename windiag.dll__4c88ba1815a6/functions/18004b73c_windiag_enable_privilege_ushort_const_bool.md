# windiag::enable_privilege(ushort const *,bool)

- ea: `0x18004b73c`
- end: `0x18004ba39`
- name: `?enable_privilege@windiag@@YA?AV?$shared_ptr@X@std@@PEBG_N@Z`
- size: `765`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c5c0`
- `0x18004ec90`
- `0x180081a00`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x180042990`
- `0x18004b73c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b79a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b79a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004b7e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004b7e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b7fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b7fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b7af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b7af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b82e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b82e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004b8a6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004b8a6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004b77d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004b77d`

## string_xrefs

- `0x18004b921`: `enable_privilege`
- `0x18004b95b`: `enable_privilege`
- `0x18004b995`: `enable_privilege`
- `0x18004b9cf`: `enable_privilege`
- `0x18004ba09`: `enable_privilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall windiag::enable_privilege(_QWORD *a1, const WCHAR *a2, char a3)
{
  DWORD LastError; // eax
  HANDLE CurrentThread; // rax
  BOOL v7; // eax
  DWORD v8; // eax
  void *v9; // rcx
  HANDLE CurrentProcess; // rax
  DWORD v11; // eax
  void *v12; // rcx
  BOOL v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  void *v17; // rdx
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-C0h] BYREF
  void *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct _TOKEN_PRIVILEGES v22; // [rsp+58h] [rbp-A8h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp-98h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+90h] [rbp-70h] BYREF

  Luid = 0;
  if ( !LookupPrivilegeValueW(0, a2, &Luid) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "enable_privilege",
        440);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v7 = OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle);
  if ( a3 )
  {
    if ( !v7 && GetLastError() != 1008 )
    {
      v8 = GetLastError();
      if ( v8 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v8,
          0,
          "[%s:%d] failed; ",
          "enable_privilege",
          444);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
  }
  v9 = TokenHandle;
  if ( !TokenHandle )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      if ( a3 )
      {
        v11 = GetLastError();
        if ( v11 )
        {
          windiag::system_exception::system_exception(
            (windiag::system_exception *)pExceptionObject,
            v11,
            0,
            "[%s:%d] failed; ",
            "enable_privilege",
            448);
          throw (windiag::system_exception *)pExceptionObject;
        }
      }
      goto LABEL_11;
    }
    v9 = TokenHandle;
  }
  ReturnLength = 16;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = Luid;
  NewState.Privileges[0].Attributes = 2;
  PreviousState = 0;
  v14 = AdjustTokenPrivileges(v9, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  if ( a3 )
  {
    if ( !v14 )
    {
      v15 = GetLastError();
      if ( v15 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v15,
          0,
          "[%s:%d] failed; ",
          "enable_privilege",
          454);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    if ( GetLastError() )
    {
      v16 = GetLastError();
      if ( v16 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v16,
          0,
          "[%s:%d] failed; ",
          "enable_privilege",
          456);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
  }
  else if ( !v14 || GetLastError() )
  {
LABEL_11:
    a1[1] = 0;
    *a1 = 0;
    goto LABEL_12;
  }
  v17 = TokenHandle;
  TokenHandle = 0;
  v21 = v17;
  v22 = PreviousState;
  std::shared_ptr<void>::shared_ptr<void>(a1, v17, &v21);
LABEL_12:
  v12 = TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18004b73c  mov     [rsp-8+arg_10], rbx
0x18004b741  push    rbp
0x18004b742  push    rsi
0x18004b743  push    rdi
0x18004b744  lea     rbp, [rsp-3D0h]
0x18004b74c  sub     rsp, 4D0h
0x18004b753  mov     rax, cs:__security_cookie
0x18004b75a  xor     rax, rsp
0x18004b75d  mov     [rbp+3E0h+var_20], rax
0x18004b764  mov     dil, r8b
0x18004b767  mov     rbx, rcx
0x18004b76a  mov     qword ptr [rsp+4E0h+Luid.LowPart], rcx
0x18004b76f  xor     esi, esi
0x18004b771  mov     qword ptr [rsp+4E0h+Luid.LowPart], rsi
0x18004b776  lea     r8, [rsp+4E0h+Luid]; lpLuid
0x18004b77b  xor     ecx, ecx; lpSystemName
0x18004b77d  call    cs:__imp_LookupPrivilegeValueW
0x18004b783  test    eax, eax
0x18004b785  jnz     short loc_18004B795
0x18004b787  call    cs:__imp_GetLastError
0x18004b78d  test    eax, eax
0x18004b78f  jnz     loc_18004B98B
0x18004b795  mov     [rsp+4E0h+TokenHandle], rsi
0x18004b79a  call    cs:__imp_GetCurrentThread
0x18004b7a0  lea     r9, [rsp+4E0h+TokenHandle]; TokenHandle
0x18004b7a5  xor     r8d, r8d; OpenAsSelf
0x18004b7a8  lea     edx, [r8+28h]; DesiredAccess
0x18004b7ac  mov     rcx, rax; ThreadHandle
0x18004b7af  call    cs:__imp_OpenThreadToken
0x18004b7b5  test    dil, dil
0x18004b7b8  jz      short loc_18004B7D9
0x18004b7ba  test    eax, eax
0x18004b7bc  jnz     short loc_18004B7D9
0x18004b7be  call    cs:__imp_GetLastError
0x18004b7c4  cmp     eax, 3F0h
0x18004b7c9  jz      short loc_18004B7D9
0x18004b7cb  call    cs:__imp_GetLastError
0x18004b7d1  test    eax, eax
0x18004b7d3  jnz     loc_18004B9C5
0x18004b7d9  mov     rcx, [rsp+4E0h+TokenHandle]
0x18004b7de  test    rcx, rcx
0x18004b7e1  jnz     short loc_18004B85E
0x18004b7e3  mov     [rsp+4E0h+TokenHandle], rsi
0x18004b7e8  call    cs:__imp_GetCurrentProcess
0x18004b7ee  lea     r8, [rsp+4E0h+TokenHandle]; TokenHandle
0x18004b7f3  mov     edx, 28h ; '('; DesiredAccess
0x18004b7f8  mov     rcx, rax; ProcessHandle
0x18004b7fb  call    cs:__imp_OpenProcessToken
0x18004b801  test    eax, eax
0x18004b803  jnz     short loc_18004B859
0x18004b805  test    dil, dil
0x18004b808  jz      short loc_18004B818
0x18004b80a  call    cs:__imp_GetLastError
0x18004b810  test    eax, eax
0x18004b812  jnz     loc_18004B9FF
0x18004b818  mov     [rbx+8], rsi
0x18004b81c  mov     [rbx], rsi
0x18004b81f  mov     rcx, [rsp+4E0h+TokenHandle]; hObject
0x18004b824  test    rcx, rcx
0x18004b827  jz      short loc_18004B834
0x18004b829  mov     [rsp+4E0h+TokenHandle], rsi
0x18004b82e  call    cs:__imp_CloseHandle
0x18004b834  mov     rax, rbx
0x18004b837  mov     rcx, [rbp+3E0h+var_20]
0x18004b83e  xor     rcx, rsp; StackCookie
0x18004b841  call    __security_check_cookie
0x18004b846  mov     rbx, [rsp+4E0h+arg_10]
0x18004b84e  add     rsp, 4D0h
0x18004b855  pop     rdi
0x18004b856  pop     rsi
0x18004b857  pop     rbp
0x18004b858  retn
0x18004b859  mov     rcx, [rsp+4E0h+TokenHandle]; TokenHandle
0x18004b85e  mov     r9d, 10h; BufferLength
0x18004b864  mov     [rsp+4E0h+var_4A8], r9d
0x18004b869  mov     [rsp+4E0h+NewState.PrivilegeCount], 1
0x18004b871  mov     rax, qword ptr [rsp+4E0h+Luid.LowPart]
0x18004b876  mov     qword ptr [rsp+4E0h+NewState.Privileges.Luid.LowPart], rax
0x18004b87b  mov     [rsp+4E0h+NewState.Privileges.Attributes], 2
0x18004b883  xorps   xmm0, xmm0
0x18004b886  movups  xmmword ptr [rsp+4E0h+var_468.PrivilegeCount], xmm0
0x18004b88b  lea     rax, [rsp+4E0h+var_4A8]
0x18004b890  mov     [rsp+4E0h+ReturnLength], rax; ReturnLength
0x18004b895  lea     rax, [rsp+4E0h+var_468]
0x18004b89a  mov     [rsp+4E0h+PreviousState], rax; PreviousState
0x18004b89f  lea     r8, [rsp+4E0h+NewState]; NewState
0x18004b8a4  xor     edx, edx; DisableAllPrivileges
0x18004b8a6  call    cs:__imp_AdjustTokenPrivileges
0x18004b8ac  test    dil, dil
0x18004b8af  jz      short loc_18004B8D5
0x18004b8b1  test    eax, eax
0x18004b8b3  jnz     short loc_18004B8BF
0x18004b8b5  call    cs:__imp_GetLastError
0x18004b8bb  test    eax, eax
0x18004b8bd  jnz     short loc_18004B917
0x18004b8bf  call    cs:__imp_GetLastError
0x18004b8c5  test    eax, eax
0x18004b8c7  jz      short loc_18004B8EB
0x18004b8c9  call    cs:__imp_GetLastError
0x18004b8cf  test    eax, eax
0x18004b8d1  jnz     short loc_18004B951
0x18004b8d3  jmp     short loc_18004B8EB
0x18004b8d5  test    eax, eax
0x18004b8d7  jz      loc_18004B818
0x18004b8dd  call    cs:__imp_GetLastError
0x18004b8e3  test    eax, eax
0x18004b8e5  jnz     loc_18004B818
0x18004b8eb  mov     rdx, [rsp+4E0h+TokenHandle]
0x18004b8f0  mov     [rsp+4E0h+TokenHandle], rsi
0x18004b8f5  mov     [rsp+4E0h+var_490], rdx
0x18004b8fa  movups  xmm0, xmmword ptr [rsp+4E0h+var_468.PrivilegeCount]
0x18004b8ff  movdqu  [rsp+4E0h+var_488], xmm0
0x18004b905  lea     r8, [rsp+4E0h+var_490]
0x18004b90a  mov     rcx, rbx
0x18004b90d  call    ??$?0XV_lambda_6dbd409283590aacaf700c1e725eab3a_@@$0A@@?$shared_ptr@X@std@@QEAA@PEAXV_lambda_6dbd409283590aacaf700c1e725eab3a_@@@Z; std::shared_ptr<void>::shared_ptr<void>(void *,_lambda_6dbd409283590aacaf700c1e725eab3a_)
0x18004b912  jmp     loc_18004B81F
0x18004b917  mov     edx, eax; __int64
0x18004b919  mov     dword ptr [rsp+4E0h+ReturnLength], 1C6h
0x18004b921  lea     rax, aEnablePrivileg; "enable_privilege"
0x18004b928  mov     [rsp+4E0h+PreviousState], rax
0x18004b92d  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004b934  xor     r8d, r8d; void *
0x18004b937  lea     rcx, [rbp+3E0h+pExceptionObject]; this
0x18004b93b  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004b940  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004b947  lea     rcx, [rbp+3E0h+pExceptionObject]; pExceptionObject
0x18004b94b  call    _CxxThrowException_0
0x18004b951  mov     edx, eax; __int64
0x18004b953  mov     dword ptr [rsp+4E0h+ReturnLength], 1C8h
0x18004b95b  lea     rax, aEnablePrivileg; "enable_privilege"
0x18004b962  mov     [rsp+4E0h+PreviousState], rax
0x18004b967  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004b96e  xor     r8d, r8d; void *
0x18004b971  lea     rcx, [rbp+3E0h+pExceptionObject]; this
0x18004b975  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004b97a  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004b981  lea     rcx, [rbp+3E0h+pExceptionObject]; pExceptionObject
0x18004b985  call    _CxxThrowException_0
0x18004b98b  mov     edx, eax; __int64
0x18004b98d  mov     dword ptr [rsp+4E0h+ReturnLength], 1B8h
0x18004b995  lea     rax, aEnablePrivileg; "enable_privilege"
0x18004b99c  mov     [rsp+4E0h+PreviousState], rax
0x18004b9a1  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004b9a8  xor     r8d, r8d; void *
0x18004b9ab  lea     rcx, [rbp+3E0h+pExceptionObject]; this
0x18004b9af  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004b9b4  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004b9bb  lea     rcx, [rbp+3E0h+pExceptionObject]; pExceptionObject
0x18004b9bf  call    _CxxThrowException_0
0x18004b9c5  mov     edx, eax; __int64
0x18004b9c7  mov     dword ptr [rsp+4E0h+ReturnLength], 1BCh
0x18004b9cf  lea     rax, aEnablePrivileg; "enable_privilege"
0x18004b9d6  mov     [rsp+4E0h+PreviousState], rax
0x18004b9db  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004b9e2  xor     r8d, r8d; void *
0x18004b9e5  lea     rcx, [rbp+3E0h+pExceptionObject]; this
0x18004b9e9  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004b9ee  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004b9f5  lea     rcx, [rbp+3E0h+pExceptionObject]; pExceptionObject
0x18004b9f9  call    _CxxThrowException_0
0x18004b9ff  mov     edx, eax; __int64
0x18004ba01  mov     dword ptr [rsp+4E0h+ReturnLength], 1C0h
0x18004ba09  lea     rax, aEnablePrivileg; "enable_privilege"
0x18004ba10  mov     [rsp+4E0h+PreviousState], rax
0x18004ba15  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004ba1c  xor     r8d, r8d; void *
0x18004ba1f  lea     rcx, [rbp+3E0h+pExceptionObject]; this
0x18004ba23  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004ba28  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004ba2f  lea     rcx, [rbp+3E0h+pExceptionObject]; pExceptionObject
0x18004ba33  call    _CxxThrowException_0
```
