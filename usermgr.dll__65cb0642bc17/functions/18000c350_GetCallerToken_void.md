# GetCallerToken(void * *)

- ea: `0x18000c350`
- end: `0x18000c4ea`
- name: `?GetCallerToken@@YAJPEAPEAX@Z`
- size: `410`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024870`
- `0x18003b764`
- `0x180046338`
- `0x1800b3218`
- `0x1800b37b8`
- `0x1800b45ac`

## callees

- `0x18000acdc`
- `0x18000c350`
- `0x18004e58c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c48a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c48a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c44b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c44b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c45e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c45e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c3d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c3d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4df`
- `ntdll!RtlNtStatusToDosError` at `0x18000c39a`
- `ntdll!RtlNtStatusToDosError` at `0x18000c39a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c392`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c392`
- `RPCRT4!RpcRevertToSelf` at `0x18000c3e7`
- `RPCRT4!RpcRevertToSelf` at `0x18000c3e7`
- `RPCRT4!RpcImpersonateClient` at `0x18000c37f`
- `RPCRT4!RpcImpersonateClient` at `0x18000c37f`

## string_xrefs

- `0x18000c413`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c425`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c49d`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c4af`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCallerToken(PHANDLE phNewToken)
{
  RPC_STATUS v2; // eax
  NTSTATUS v3; // eax
  signed int v4; // eax
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  void *v8; // rsi
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  const char *v11; // r9
  DWORD LastError; // ebx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v15; // [rsp+60h] [rbp+8h]
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  TokenHandle = 0;
  *phNewToken = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 == 1725 )
  {
    v8 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v10);
    if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v11);
  }
  else
  {
    v3 = I_RpcMapWin32Status(v2);
    v4 = RtlNtStatusToDosError(v3);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)(unsigned int)v4,
        TokenType);
    v15 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v6);
  }
  if ( v15 )
    RpcRevertToSelf();
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18000c350  mov     [rsp+arg_10], rbx
0x18000c355  push    rbp
0x18000c356  push    rsi
0x18000c357  push    rdi
0x18000c358  sub     rsp, 40h
0x18000c35c  mov     rdi, rcx
0x18000c35f  mov     [rsp+58h+arg_0], 0
0x18000c364  xor     ebp, ebp
0x18000c366  mov     [rsp+58h+TokenHandle], rbp
0x18000c36b  lea     rax, [rsp+58h+arg_0]
0x18000c370  mov     [rsp+58h+var_28], rax
0x18000c375  mov     [rsp+58h+var_20], 1
0x18000c37a  mov     [rcx], rbp
0x18000c37d  xor     ecx, ecx; BindingHandle
0x18000c37f  call    cs:__imp_RpcImpersonateClient
0x18000c385  cmp     eax, 6BDh
0x18000c38a  jz      loc_18000C437
0x18000c390  mov     ecx, eax; Status
0x18000c392  call    cs:__imp_I_RpcMapWin32Status
0x18000c398  mov     ecx, eax; Status
0x18000c39a  call    cs:__imp_RtlNtStatusToDosError
0x18000c3a0  test    eax, eax
0x18000c3a2  jle     short loc_18000C3AC
0x18000c3a4  movzx   eax, ax
0x18000c3a7  or      eax, 80070000h
0x18000c3ac  mov     rcx, [rsp+58h]; this
0x18000c3b1  test    eax, eax
0x18000c3b3  js      short loc_18000C410
0x18000c3b5  mov     [rsp+58h+arg_0], 1
0x18000c3ba  call    cs:__imp_GetCurrentThread
0x18000c3c0  mov     rcx, rax; ThreadHandle
0x18000c3c3  mov     r9, rdi; TokenHandle
0x18000c3c6  mov     edx, 8; DesiredAccess
0x18000c3cb  mov     r8d, 1; OpenAsSelf
0x18000c3d1  call    cs:__imp_OpenThreadToken
0x18000c3d7  mov     rcx, [rsp+58h]; this
0x18000c3dc  test    eax, eax
0x18000c3de  jz      short loc_18000C425
0x18000c3e0  cmp     [rsp+58h+arg_0], 0
0x18000c3e5  jz      short loc_18000C3EE
0x18000c3e7  call    cs:__imp_RpcRevertToSelf
0x18000c3ed  nop
0x18000c3ee  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000c3f3  lea     rax, [rcx-1]
0x18000c3f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c3fb  jbe     loc_18000C4DF
0x18000c401  xor     eax, eax
0x18000c403  mov     rbx, [rsp+58h+arg_10]
0x18000c408  add     rsp, 40h
0x18000c40c  pop     rdi
0x18000c40d  pop     rsi
0x18000c40e  pop     rbp
0x18000c40f  retn
0x18000c410  mov     r9d, eax; char *
0x18000c413  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000c41a  mov     edx, 37h ; '7'; void *
0x18000c41f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c425  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000c42c  mov     edx, 39h ; '9'; void *
0x18000c431  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c437  mov     rsi, [rsp+58h+TokenHandle]
0x18000c43c  lea     rax, [rsi-1]
0x18000c440  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c444  jbe     short loc_18000C4C1
0x18000c446  mov     [rsp+58h+TokenHandle], rbp
0x18000c44b  call    cs:__imp_GetCurrentProcess
0x18000c451  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000c456  mov     edx, 0Ah; DesiredAccess
0x18000c45b  mov     rcx, rax; ProcessHandle
0x18000c45e  call    cs:__imp_OpenProcessToken
0x18000c464  mov     rcx, [rsp+58h]; this
0x18000c469  test    eax, eax
0x18000c46b  jz      short loc_18000C4AF
0x18000c46d  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x18000c472  mov     [rsp+58h+TokenType], 2; TokenType
0x18000c47a  mov     r9d, 2; ImpersonationLevel
0x18000c480  xor     r8d, r8d; lpTokenAttributes
0x18000c483  xor     edx, edx; dwDesiredAccess
0x18000c485  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x18000c48a  call    cs:__imp_DuplicateTokenEx
0x18000c490  mov     rcx, [rsp+58h]; this
0x18000c495  test    eax, eax
0x18000c497  jnz     loc_18000C3E0
0x18000c49d  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000c4a4  mov     edx, 33h ; '3'; void *
0x18000c4a9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c4af  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000c4b6  mov     edx, 2Dh ; '-'; void *
0x18000c4bb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c4c1  call    cs:__imp_GetLastError
0x18000c4c7  mov     ebx, eax
0x18000c4c9  mov     rcx, rsi; hObject
0x18000c4cc  call    cs:__imp_CloseHandle
0x18000c4d2  mov     ecx, ebx; dwErrCode
0x18000c4d4  call    cs:__imp_SetLastError
0x18000c4da  jmp     loc_18000C446
0x18000c4df  call    cs:__imp_CloseHandle
0x18000c4e5  jmp     loc_18000C401
```
