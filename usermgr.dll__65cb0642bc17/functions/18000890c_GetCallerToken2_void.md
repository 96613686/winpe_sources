# GetCallerToken2(void * *)

- ea: `0x18000890c`
- end: `0x180008b0a`
- name: `?GetCallerToken2@@YAJPEAPEAX@Z`
- size: `510`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008630`
- `0x180048bc0`
- `0x18007bc10`

## callees

- `0x18000890c`
- `0x180008b10`
- `0x18000acdc`
- `0x18004e58c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008947`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008947`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008ad6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008ad6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800089e4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800089e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000896b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000896b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008999`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008999`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800089ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800089ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008980`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ab0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008980`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008af7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008af7`
- `ntdll!RtlNtStatusToDosError` at `0x180008a12`
- `ntdll!RtlNtStatusToDosError` at `0x180008a12`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008a0a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008a0a`
- `RPCRT4!RpcRevertToSelf` at `0x180008ae2`
- `RPCRT4!RpcRevertToSelf` at `0x180008ae2`
- `RPCRT4!RpcImpersonateClient` at `0x18000895a`
- `RPCRT4!RpcImpersonateClient` at `0x18000895a`

## string_xrefs

- `0x1800089b9`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800089f6`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008a2f`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008a68`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008a85`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008abe`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCallerToken2(PHANDLE TokenHandle)
{
  HRESULT v2; // eax
  RPC_STATUS v3; // eax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  const char *v7; // r9
  NTSTATUS v8; // eax
  signed int v9; // eax
  HANDLE v10; // rax
  const char *v11; // r9
  HANDLE v12; // rax
  const char *v13; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  char v17; // [rsp+60h] [rbp+10h]
  char v18; // [rsp+68h] [rbp+18h]
  void *TokenHandlea; // [rsp+70h] [rbp+20h] BYREF

  v17 = 0;
  v18 = 0;
  TokenHandlea = 0;
  *TokenHandle = 0;
  v2 = CoImpersonateClient();
  if ( v2 == -2147417833 )
  {
    v3 = RpcImpersonateClient(0);
    if ( v3 == 1725 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandlea,
          0);
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandlea) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v6);
        if ( !DuplicateTokenEx(TokenHandlea, 0, 0, SecurityImpersonation, TokenImpersonation, TokenHandle) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x97,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v7);
      }
    }
    else
    {
      v8 = I_RpcMapWin32Status(v3);
      v9 = RtlNtStatusToDosError(v8);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          (const char *)(unsigned int)v9,
          TokenType);
      v18 = 1;
      v10 = GetCurrentThread();
      if ( !OpenThreadToken(v10, 8u, 1, TokenHandle) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x9F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v11);
    }
  }
  else
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)(unsigned int)v2,
        TokenType);
    v17 = 1;
    v12 = GetCurrentThread();
    if ( !OpenThreadToken(v12, 8u, 1, TokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v13);
  }
  if ( v17 )
    CoRevertToSelf();
  if ( v18 )
    RpcRevertToSelf();
  if ( (char *)TokenHandlea - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandlea);
  return 0;
}

```

## disassembly

```asm
0x18000890c  mov     [rsp-8+arg_18], rbx
0x180008911  push    rbp
0x180008912  mov     rbp, rsp
0x180008915  sub     rsp, 50h
0x180008919  mov     rbx, rcx
0x18000891c  mov     [rbp+arg_0], 0
0x180008920  mov     [rbp+arg_8], 0
0x180008924  mov     [rbp+TokenHandle], 0
0x18000892c  lea     rax, [rbp+arg_0]
0x180008930  mov     [rbp+var_20], rax
0x180008934  lea     rax, [rbp+arg_8]
0x180008938  mov     [rbp+var_18], rax
0x18000893c  mov     [rbp+var_10], 1
0x180008940  mov     qword ptr [rcx], 0
0x180008947  call    cs:__imp_CoImpersonateClient
0x18000894d  cmp     eax, 80010117h
0x180008952  jnz     loc_180008A7A
0x180008958  xor     ecx, ecx; BindingHandle
0x18000895a  call    cs:__imp_RpcImpersonateClient
0x180008960  cmp     eax, 6BDh
0x180008965  jnz     loc_180008A08
0x18000896b  call    cs:__imp_GetCurrentThread
0x180008971  mov     rcx, rax; ThreadHandle
0x180008974  mov     r9, rbx; TokenHandle
0x180008977  mov     edx, 8; DesiredAccess
0x18000897c  lea     r8d, [rdx-7]; OpenAsSelf
0x180008980  call    cs:__imp_OpenThreadToken
0x180008986  test    eax, eax
0x180008988  jnz     loc_180008AD0
0x18000898e  xor     edx, edx
0x180008990  lea     rcx, [rbp+TokenHandle]
0x180008994  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180008999  call    cs:__imp_GetCurrentProcess
0x18000899f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800089a3  mov     edx, 0Ah; DesiredAccess
0x1800089a8  mov     rcx, rax; ProcessHandle
0x1800089ab  call    cs:__imp_OpenProcessToken
0x1800089b1  mov     rcx, [rbp+8]; this
0x1800089b5  test    eax, eax
0x1800089b7  jnz     short loc_1800089CB
0x1800089b9  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800089c0  mov     edx, 90h; void *
0x1800089c5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800089cb  mov     [rsp+50h+phNewToken], rbx; phNewToken
0x1800089d0  mov     r9d, 2; ImpersonationLevel
0x1800089d6  mov     [rsp+50h+TokenType], r9d; TokenType
0x1800089db  xor     r8d, r8d; lpTokenAttributes
0x1800089de  xor     edx, edx; dwDesiredAccess
0x1800089e0  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1800089e4  call    cs:__imp_DuplicateTokenEx
0x1800089ea  mov     rcx, [rbp+8]; this
0x1800089ee  test    eax, eax
0x1800089f0  jnz     loc_180008AD0
0x1800089f6  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800089fd  mov     edx, 97h; void *
0x180008a02  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008a08  mov     ecx, eax; Status
0x180008a0a  call    cs:__imp_I_RpcMapWin32Status
0x180008a10  mov     ecx, eax; Status
0x180008a12  call    cs:__imp_RtlNtStatusToDosError
0x180008a18  test    eax, eax
0x180008a1a  jle     short loc_180008A24
0x180008a1c  movzx   eax, ax
0x180008a1f  or      eax, 80070000h
0x180008a24  mov     rcx, [rbp+8]; this
0x180008a28  test    eax, eax
0x180008a2a  jns     short loc_180008A41
0x180008a2c  mov     r9d, eax; char *
0x180008a2f  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008a36  mov     edx, 9Dh; void *
0x180008a3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008a41  mov     [rbp+arg_8], 1
0x180008a45  call    cs:__imp_GetCurrentThread
0x180008a4b  mov     rcx, rax; ThreadHandle
0x180008a4e  mov     r9, rbx; TokenHandle
0x180008a51  mov     edx, 8; DesiredAccess
0x180008a56  lea     r8d, [rdx-7]; OpenAsSelf
0x180008a5a  call    cs:__imp_OpenThreadToken
0x180008a60  mov     rcx, [rbp+8]; this
0x180008a64  test    eax, eax
0x180008a66  jnz     short loc_180008AD0
0x180008a68  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008a6f  mov     edx, 9Fh; void *
0x180008a74  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008a7a  mov     rcx, [rbp+8]; this
0x180008a7e  test    eax, eax
0x180008a80  jns     short loc_180008A97
0x180008a82  mov     r9d, eax; char *
0x180008a85  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008a8c  mov     edx, 0A5h; void *
0x180008a91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008a97  mov     [rbp+arg_0], 1
0x180008a9b  call    cs:__imp_GetCurrentThread
0x180008aa1  mov     rcx, rax; ThreadHandle
0x180008aa4  mov     r9, rbx; TokenHandle
0x180008aa7  mov     edx, 8; DesiredAccess
0x180008aac  lea     r8d, [rdx-7]; OpenAsSelf
0x180008ab0  call    cs:__imp_OpenThreadToken
0x180008ab6  mov     rcx, [rbp+8]; this
0x180008aba  test    eax, eax
0x180008abc  jnz     short loc_180008AD0
0x180008abe  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008ac5  mov     edx, 0A7h; void *
0x180008aca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008ad0  cmp     [rbp+arg_0], 0
0x180008ad4  jz      short loc_180008ADC
0x180008ad6  call    cs:__imp_CoRevertToSelf
0x180008adc  cmp     [rbp+arg_8], 0
0x180008ae0  jz      short loc_180008AE9
0x180008ae2  call    cs:__imp_RpcRevertToSelf
0x180008ae8  nop
0x180008ae9  mov     rcx, [rbp+TokenHandle]; hObject
0x180008aed  lea     rax, [rcx-1]
0x180008af1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008af5  ja      short loc_180008AFD
0x180008af7  call    cs:__imp_CloseHandle
0x180008afd  xor     eax, eax
0x180008aff  mov     rbx, [rsp+50h+arg_18]
0x180008b04  add     rsp, 50h
0x180008b08  pop     rbp
0x180008b09  retn
```
