# CRpcUtils::GetClientLUID(_LUID *)

- ea: `0x180003c70`
- end: `0x180003e21`
- name: `?GetClientLUID@CRpcUtils@@SAJPEAU_LUID@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026fd0`
- `0x1800270e0`

## callees

- `0x180003c70`
- `0x180003f30`
- `0x18001a280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003df7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003df7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cf8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003cdf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003dc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003dc6`
- `RPCRT4!RpcImpersonateClient` at `0x180003cbd`
- `RPCRT4!RpcImpersonateClient` at `0x180003cbd`
- `RPCRT4!RpcRevertToSelf` at `0x180003d1b`
- `RPCRT4!RpcRevertToSelf` at `0x180003d1b`

## string_xrefs

- `0x180003cd6`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180003d57`: `CRpcUtils::GetClientToken`
- `0x180003d50`: `OpenThreadToken failed: 0x%x in %s`
- `0x180003d96`: `GetClientToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetClientLUID(struct _LUID *a1)
{
  void *v1; // rsi
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v7; // eax
  bool v8; // sf
  void *v9; // rax
  signed int v10; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-58h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-50h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+70h] [rbp-18h]

  v1 = 0;
  *a1 = 0;
  ReturnLength = 0;
  v15 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  TokenHandle = 0;
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    v7 = RpcRevertToSelf();
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v7);
      v4 = -2147024891;
    }
    else
    {
      if ( v4 >= 0 )
      {
        v9 = TokenHandle;
        goto LABEL_18;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v4, "CRpcUtils::GetClientToken");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v4, "CRpcUtils::GetClientToken");
  }
  v9 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    goto LABEL_19;
  }
LABEL_18:
  v1 = v9;
LABEL_19:
  if ( v4 >= 0 )
  {
    if ( GetTokenInformation(v1, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
    {
      *a1 = *(struct _LUID *)((char *)TokenInformation + 8);
    }
    else
    {
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
    }
  }
  else
  {
    _DbgPrintMessage(8, "GetClientToken failed: 0x%x in %s", v4, "CRpcUtils::GetClientLUID");
  }
  if ( v1 )
    CloseHandle(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003c70  mov     [rsp+arg_8], rbx
0x180003c75  mov     [rsp+arg_10], rsi
0x180003c7a  push    rdi
0x180003c7b  sub     rsp, 80h
0x180003c82  mov     rax, cs:__security_cookie
0x180003c89  xor     rax, rsp
0x180003c8c  mov     [rsp+88h+var_10], rax
0x180003c91  xorps   xmm0, xmm0
0x180003c94  xor     esi, esi
0x180003c96  mov     [rcx], rsi
0x180003c99  mov     rdi, rcx
0x180003c9c  xor     eax, eax
0x180003c9e  mov     [rsp+88h+var_58], esi
0x180003ca2  xor     ecx, ecx; BindingHandle
0x180003ca4  mov     [rsp+88h+var_18], rax
0x180003ca9  movups  [rsp+88h+TokenInformation], xmm0
0x180003cae  mov     [rsp+88h+TokenHandle], rsi
0x180003cb3  movups  [rsp+88h+var_38], xmm0
0x180003cb8  movups  [rsp+88h+var_28], xmm0
0x180003cbd  call    cs:__imp_RpcImpersonateClient
0x180003cc3  mov     ebx, eax
0x180003cc5  test    eax, eax
0x180003cc7  jle     short loc_180003CD2
0x180003cc9  movzx   ebx, ax
0x180003ccc  or      ebx, 80070000h
0x180003cd2  test    ebx, ebx
0x180003cd4  jns     short loc_180003CDF
0x180003cd6  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed: 0x%x in %s"
0x180003cdd  jmp     short loc_180003D57
0x180003cdf  call    cs:__imp_GetCurrentThread
0x180003ce5  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180003cea  mov     edx, 0Eh; DesiredAccess
0x180003cef  mov     rcx, rax; ThreadHandle
0x180003cf2  mov     r8d, 1; OpenAsSelf
0x180003cf8  call    cs:__imp_OpenThreadToken
0x180003cfe  test    eax, eax
0x180003d00  jnz     short loc_180003D19
0x180003d02  call    cs:__imp_GetLastError
0x180003d08  mov     ebx, eax
0x180003d0a  test    eax, eax
0x180003d0c  jle     short loc_180003D1B
0x180003d0e  movzx   ebx, ax
0x180003d11  or      ebx, 80070000h
0x180003d17  jmp     short loc_180003D1B
0x180003d19  mov     ebx, esi
0x180003d1b  call    cs:__imp_RpcRevertToSelf
0x180003d21  test    eax, eax
0x180003d23  jle     short loc_180003D2F
0x180003d25  movzx   eax, ax
0x180003d28  or      eax, 80070000h
0x180003d2d  test    eax, eax
0x180003d2f  jns     short loc_180003D4C
0x180003d31  mov     r8d, eax
0x180003d34  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180003d3b  mov     ecx, 8; int
0x180003d40  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003d45  mov     ebx, 80070005h
0x180003d4a  jmp     short loc_180003D6B
0x180003d4c  test    ebx, ebx
0x180003d4e  jns     short loc_180003D80
0x180003d50  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x180003d57  lea     r9, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken"
0x180003d5e  mov     r8d, ebx
0x180003d61  mov     ecx, 8; int
0x180003d66  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003d6b  mov     rax, [rsp+88h+TokenHandle]
0x180003d70  test    rax, rax
0x180003d73  jz      short loc_180003D85
0x180003d75  mov     rcx, rax; hObject
0x180003d78  call    cs:__imp_CloseHandle
0x180003d7e  jmp     short loc_180003D88
0x180003d80  mov     rax, [rsp+88h+TokenHandle]
0x180003d85  mov     rsi, rax
0x180003d88  test    ebx, ebx
0x180003d8a  jns     short loc_180003DA9
0x180003d8c  lea     r9, aCrpcutilsGetcl_2; "CRpcUtils::GetClientLUID"
0x180003d93  mov     r8d, ebx
0x180003d96  lea     rdx, aGetclienttoken; "GetClientToken failed: 0x%x in %s"
0x180003d9d  mov     ecx, 8; int
0x180003da2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003da7  jmp     short loc_180003DEF
0x180003da9  lea     rax, [rsp+88h+var_58]
0x180003dae  mov     r9d, 38h ; '8'; TokenInformationLength
0x180003db4  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x180003db9  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180003dbe  mov     edx, 0Ah; TokenInformationClass
0x180003dc3  mov     rcx, rsi; TokenHandle
0x180003dc6  call    cs:__imp_GetTokenInformation
0x180003dcc  test    eax, eax
0x180003dce  jnz     short loc_180003DE7
0x180003dd0  call    cs:__imp_GetLastError
0x180003dd6  mov     ebx, eax
0x180003dd8  test    eax, eax
0x180003dda  jle     short loc_180003DEF
0x180003ddc  movzx   ebx, ax
0x180003ddf  or      ebx, 80070000h
0x180003de5  jmp     short loc_180003DEF
0x180003de7  mov     rax, qword ptr [rsp+88h+TokenInformation+8]
0x180003dec  mov     [rdi], rax
0x180003def  test    rsi, rsi
0x180003df2  jz      short loc_180003DFD
0x180003df4  mov     rcx, rsi; hObject
0x180003df7  call    cs:__imp_CloseHandle
0x180003dfd  mov     eax, ebx
0x180003dff  mov     rcx, [rsp+88h+var_10]
0x180003e04  xor     rcx, rsp; StackCookie
0x180003e07  call    __security_check_cookie
0x180003e0c  lea     r11, [rsp+88h+var_8]
0x180003e14  mov     rbx, [r11+18h]
0x180003e18  mov     rsi, [r11+20h]
0x180003e1c  mov     rsp, r11
0x180003e1f  pop     rdi
0x180003e20  retn
```
