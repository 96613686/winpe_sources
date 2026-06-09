# CWebPlatStorageServer::CheckAccess(void)

- ea: `0x180058e90`
- end: `0x180059024`
- name: `?CheckAccess@CWebPlatStorageServer@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(PSID **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047690`

## callees

- `0x180058e90`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180058f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180058f09`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058f22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058f94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058f94`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180058fd2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180058fd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058ff7`
- `RPCRT4!RpcRevertToSelf` at `0x180058f51`
- `RPCRT4!RpcRevertToSelf` at `0x180058f6e`
- `RPCRT4!RpcRevertToSelf` at `0x180058f51`
- `RPCRT4!RpcRevertToSelf` at `0x180058f6e`
- `RPCRT4!RpcImpersonateClient` at `0x180058ee2`
- `RPCRT4!RpcImpersonateClient` at `0x180058ee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWebPlatStorageServer::CheckAccess(PSID **this)
{
  RPC_STATUS v2; // eax
  signed int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  RPC_STATUS v6; // eax
  signed int v7; // eax
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-78h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147418113;
LABEL_13:
      RpcRevertToSelf();
      goto LABEL_23;
    }
    v6 = RpcRevertToSelf();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_13;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      if ( EqualSid(TokenInformation[0], *this[18]) )
        v3 = 0;
      else
        v3 = -2147024891;
    }
    else
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147418113;
    }
  }
LABEL_23:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180058e90  mov     [rsp+arg_8], rbx
0x180058e95  mov     [rsp+arg_10], rbp
0x180058e9a  push    rdi
0x180058e9b  sub     rsp, 0C0h
0x180058ea2  mov     rax, cs:__security_cookie
0x180058ea9  xor     rax, rsp
0x180058eac  mov     [rsp+0C8h+var_18], rax
0x180058eb4  xor     edx, edx; Val
0x180058eb6  mov     [rsp+0C8h+var_94], 0
0x180058ebe  mov     rdi, rcx
0x180058ec1  mov     [rsp+0C8h+TokenHandle], 0
0x180058eca  lea     rcx, [rsp+0C8h+TokenInformation]; void *
0x180058ecf  lea     r8d, [rdx+58h]; Size
0x180058ed3  call    memset_0
0x180058ed8  xor     ecx, ecx; BindingHandle
0x180058eda  mov     [rsp+0C8h+var_90], 0
0x180058ee2  call    cs:__imp_RpcImpersonateClient
0x180058ee8  mov     ebx, eax
0x180058eea  mov     ebp, 80070000h
0x180058eef  test    eax, eax
0x180058ef1  jle     short loc_180058EF8
0x180058ef3  movzx   ebx, ax
0x180058ef6  or      ebx, ebp
0x180058ef8  test    ebx, ebx
0x180058efa  jns     short loc_180058F09
0x180058efc  mov     [rsp+0C8h+var_94], 2B5h
0x180058f04  jmp     loc_180058FED
0x180058f09  call    cs:__imp_GetCurrentThread
0x180058f0f  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180058f14  mov     edx, 20008h; DesiredAccess
0x180058f19  mov     rcx, rax; ThreadHandle
0x180058f1c  mov     r8d, 1; OpenAsSelf
0x180058f22  call    cs:__imp_OpenThreadToken
0x180058f28  test    eax, eax
0x180058f2a  jnz     short loc_180058F51
0x180058f2c  call    cs:__imp_GetLastError
0x180058f32  mov     ebx, eax
0x180058f34  test    eax, eax
0x180058f36  jle     short loc_180058F3D
0x180058f38  movzx   ebx, ax
0x180058f3b  or      ebx, ebp
0x180058f3d  test    ebx, ebx
0x180058f3f  mov     [rsp+0C8h+var_94], 2B8h
0x180058f47  mov     eax, 8000FFFFh
0x180058f4c  cmovns  ebx, eax
0x180058f4f  jmp     short loc_180058F6E
0x180058f51  call    cs:__imp_RpcRevertToSelf
0x180058f57  mov     ebx, eax
0x180058f59  test    eax, eax
0x180058f5b  jle     short loc_180058F62
0x180058f5d  movzx   ebx, ax
0x180058f60  or      ebx, ebp
0x180058f62  test    ebx, ebx
0x180058f64  jns     short loc_180058F76
0x180058f66  mov     [rsp+0C8h+var_94], 2BDh
0x180058f6e  call    cs:__imp_RpcRevertToSelf
0x180058f74  jmp     short loc_180058FED
0x180058f76  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180058f7b  lea     rax, [rsp+0C8h+var_90]
0x180058f80  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180058f86  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180058f8b  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180058f90  lea     edx, [r9-57h]; TokenInformationClass
0x180058f94  call    cs:__imp_GetTokenInformation
0x180058f9a  test    eax, eax
0x180058f9c  jnz     short loc_180058FC3
0x180058f9e  call    cs:__imp_GetLastError
0x180058fa4  mov     ebx, eax
0x180058fa6  test    eax, eax
0x180058fa8  jle     short loc_180058FAF
0x180058faa  movzx   ebx, ax
0x180058fad  or      ebx, ebp
0x180058faf  test    ebx, ebx
0x180058fb1  mov     [rsp+0C8h+var_94], 2C0h
0x180058fb9  mov     eax, 8000FFFFh
0x180058fbe  cmovns  ebx, eax
0x180058fc1  jmp     short loc_180058FED
0x180058fc3  mov     rdx, [rdi+90h]
0x180058fca  mov     rcx, [rsp+0C8h+TokenInformation]; pSid1
0x180058fcf  mov     rdx, [rdx]; pSid2
0x180058fd2  call    cs:__imp_EqualSid
0x180058fd8  test    eax, eax
0x180058fda  jz      short loc_180058FE0
0x180058fdc  xor     ebx, ebx
0x180058fde  jmp     short loc_180058FED
0x180058fe0  mov     [rsp+0C8h+var_94], 2CDh
0x180058fe8  mov     ebx, 80070005h
0x180058fed  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x180058ff2  test    rcx, rcx
0x180058ff5  jz      short loc_180058FFD
0x180058ff7  call    cs:__imp_CloseHandle
0x180058ffd  mov     eax, ebx
0x180058fff  mov     rcx, [rsp+0C8h+var_18]
0x180059007  xor     rcx, rsp; StackCookie
0x18005900a  call    __security_check_cookie
0x18005900f  lea     r11, [rsp+0C8h+var_8]
0x180059017  mov     rbx, [r11+18h]
0x18005901b  mov     rbp, [r11+20h]
0x18005901f  mov     rsp, r11
0x180059022  pop     rdi
0x180059023  retn
```
