# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1800349c8`
- end: `0x180034ba1`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800348f0`

## callees

- `0x1800349c8`
- `0x1800e2988`
- `0x1800e34bc`
- `0x1800e3660`
- `0x18028b564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034aad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034aad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034a55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034a6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034a6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b36`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034aef`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034aef`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1800349e5`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1800349e5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034b76`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034b99`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034b76`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034b99`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  void *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edi
  bool v14; // bl
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v18; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v18 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v14 = v18 != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_24;
  LastError = GetLastError();
  if ( !v14 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
      v11 = TokenHandle;
      *a3 = 0;
      if ( DuplicateTokenEx(v11, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
      {
        if ( TokenHandle )
          CloseHandle(TokenHandle);
        return 0;
      }
      v12 = 388;
    }
    else
    {
      v12 = 386;
    }
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v12,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
           v10);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v5;
  }
  if ( !LastError )
  {
LABEL_24:
    if ( v14 )
      CoRevertToSelf();
    return 0;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v14 )
    CoRevertToSelf();
  return v13;
}

```

## disassembly

```asm
0x1800349c8  mov     rax, rsp
0x1800349cb  mov     [rax+8], rbx
0x1800349cf  mov     [rax+10h], edx
0x1800349d2  push    rdi
0x1800349d3  sub     rsp, 30h
0x1800349d7  lea     rdx, [rax+10h]
0x1800349db  mov     dword ptr [rax+10h], 0
0x1800349e2  mov     rdi, r8
0x1800349e5  call    cs:__imp_CoImpersonateClientOfObject
0x1800349eb  mov     ebx, eax
0x1800349ed  test    eax, eax
0x1800349ef  jns     short loc_180034A30
0x1800349f1  mov     rcx, [rsp+38h]; this
0x1800349f6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1800349fd  mov     r9d, eax; char *
0x180034a00  mov     edx, 157h; void *
0x180034a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a0a  mov     rcx, [rsp+38h]; this
0x180034a0f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180034a16  mov     r9d, ebx; char *
0x180034a19  mov     edx, 177h; void *
0x180034a1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a23  mov     eax, ebx
0x180034a25  mov     rbx, [rsp+38h+arg_0]
0x180034a2a  add     rsp, 30h
0x180034a2e  pop     rdi
0x180034a2f  retn
0x180034a30  xor     bl, bl
0x180034a32  cmp     [rsp+38h+arg_8], 0
0x180034a37  jnz     loc_180034B7E
0x180034a3d  mov     rcx, [rdi]; hObject
0x180034a40  lea     rax, [rcx-1]
0x180034a44  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a48  jbe     loc_180034B85
0x180034a4e  mov     qword ptr [rdi], 0
0x180034a55  call    cs:__imp_GetCurrentThread
0x180034a5b  mov     edx, 8; DesiredAccess
0x180034a60  mov     r9, rdi; TokenHandle
0x180034a63  mov     rcx, rax; ThreadHandle
0x180034a66  lea     r8d, [rdx-7]; OpenAsSelf
0x180034a6a  call    cs:__imp_OpenThreadToken
0x180034a70  test    eax, eax
0x180034a72  jnz     loc_180034B72
0x180034a78  call    cs:__imp_GetLastError
0x180034a7e  test    bl, bl
0x180034a80  jnz     loc_180034B41
0x180034a86  cmp     eax, 3F0h
0x180034a8b  jnz     loc_180034B41
0x180034a91  mov     [rsp+38h+TokenHandle], 0
0x180034a9a  call    cs:__imp_GetCurrentProcess
0x180034aa0  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180034aa5  mov     edx, 0Ah; DesiredAccess
0x180034aaa  mov     rcx, rax; ProcessHandle
0x180034aad  call    cs:__imp_OpenProcessToken
0x180034ab3  test    eax, eax
0x180034ab5  jz      loc_180034B6B
0x180034abb  mov     rcx, [rdi]; hObject
0x180034abe  lea     rax, [rcx-1]
0x180034ac2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034ac6  jbe     loc_180034B8F
0x180034acc  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180034ad1  mov     r9d, 2; ImpersonationLevel
0x180034ad7  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180034adc  xor     r8d, r8d; lpTokenAttributes
0x180034adf  mov     qword ptr [rdi], 0
0x180034ae6  mov     [rsp+38h+TokenType], r9d; TokenType
0x180034aeb  lea     edx, [r9+6]; dwDesiredAccess
0x180034aef  call    cs:__imp_DuplicateTokenEx
0x180034af5  test    eax, eax
0x180034af7  jz      short loc_180034B10
0x180034af9  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180034afe  test    rcx, rcx
0x180034b01  jz      short loc_180034B09
0x180034b03  call    cs:__imp_CloseHandle
0x180034b09  xor     eax, eax
0x180034b0b  jmp     loc_180034A25
0x180034b10  mov     edx, 184h; void *
0x180034b15  mov     rcx, [rsp+38h]; this
0x180034b1a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180034b21  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034b26  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180034b2b  mov     ebx, eax
0x180034b2d  test    rcx, rcx
0x180034b30  jz      loc_180034A23
0x180034b36  call    cs:__imp_CloseHandle
0x180034b3c  jmp     loc_180034A23
0x180034b41  test    eax, eax
0x180034b43  jz      short loc_180034B72
0x180034b45  mov     rcx, [rsp+38h]; this
0x180034b4a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180034b51  mov     r9d, eax; char *
0x180034b54  mov     edx, 188h; void *
0x180034b59  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034b5e  mov     edi, eax
0x180034b60  test    bl, bl
0x180034b62  jnz     short loc_180034B99
0x180034b64  mov     eax, edi
0x180034b66  jmp     loc_180034A25
0x180034b6b  mov     edx, 182h
0x180034b70  jmp     short loc_180034B15
0x180034b72  test    bl, bl
0x180034b74  jz      short loc_180034B09
0x180034b76  call    cs:__imp_CoRevertToSelf
0x180034b7c  jmp     short loc_180034B09
0x180034b7e  mov     bl, 1
0x180034b80  jmp     loc_180034A3D
0x180034b85  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180034b8a  jmp     loc_180034A4E
0x180034b8f  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180034b94  jmp     loc_180034ACC
0x180034b99  call    cs:__imp_CoRevertToSelf
0x180034b9f  jmp     short loc_180034B64
```
