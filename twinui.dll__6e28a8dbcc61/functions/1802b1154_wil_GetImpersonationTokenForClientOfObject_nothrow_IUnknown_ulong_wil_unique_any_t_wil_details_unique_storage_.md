# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1802b1154`
- end: `0x1802b12db`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802aff68`

## callees

- `0x18003c5e4`
- `0x180062a94`
- `0x1800ead54`
- `0x1801045d4`
- `0x1802af30c`
- `0x1802b1154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b11ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b11ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b11cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b11cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b11e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b11e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802b1223`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802b1223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802b1210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802b1210`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b125a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b125a`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1802b1171`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1802b1171`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802b12ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802b12c8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802b12ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802b12c8`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, void **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v17; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v17);
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
  v7 = v17 != 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a3,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_17;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a3,
      0);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_17:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v13;
}

```

## disassembly

```asm
0x1802b1154  mov     rax, rsp
0x1802b1157  mov     [rax+8], rbx
0x1802b115b  mov     [rax+10h], edx
0x1802b115e  push    rdi
0x1802b115f  sub     rsp, 30h
0x1802b1163  mov     rdi, r8
0x1802b1166  mov     dword ptr [rax+10h], 0
0x1802b116d  lea     rdx, [rax+10h]
0x1802b1171  call    cs:__imp_CoImpersonateClientOfObject
0x1802b1177  mov     ebx, eax
0x1802b1179  test    eax, eax
0x1802b117b  jns     short loc_1802B11B6
0x1802b117d  mov     rcx, [rsp+38h]; this
0x1802b1182  mov     r9d, eax; char *
0x1802b1185  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802b118c  mov     edx, 157h; void *
0x1802b1191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b1196  mov     rcx, [rsp+38h]; this
0x1802b119b  mov     r9d, ebx; char *
0x1802b119e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802b11a5  mov     edx, 177h; void *
0x1802b11aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b11af  mov     eax, ebx
0x1802b11b1  jmp     loc_1802B12D0
0x1802b11b6  xor     bl, bl
0x1802b11b8  cmp     [rsp+38h+arg_8], 0
0x1802b11bd  jz      short loc_1802B11C1
0x1802b11bf  mov     bl, 1
0x1802b11c1  xor     edx, edx
0x1802b11c3  mov     rcx, rdi
0x1802b11c6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b11cb  call    cs:__imp_GetCurrentThread
0x1802b11d1  mov     r9, rdi; TokenHandle
0x1802b11d4  mov     edx, 8; DesiredAccess
0x1802b11d9  lea     r8d, [rdx-7]; OpenAsSelf
0x1802b11dd  mov     rcx, rax; ThreadHandle
0x1802b11e0  call    cs:__imp_OpenThreadToken
0x1802b11e6  test    eax, eax
0x1802b11e8  jnz     loc_1802B12C4
0x1802b11ee  call    cs:__imp_GetLastError
0x1802b11f4  test    bl, bl
0x1802b11f6  jnz     loc_1802B1297
0x1802b11fc  cmp     eax, 3F0h
0x1802b1201  jnz     loc_1802B1297
0x1802b1207  mov     [rsp+38h+TokenHandle], 0
0x1802b1210  call    cs:__imp_GetCurrentProcess
0x1802b1216  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1802b121b  mov     edx, 0Ah; DesiredAccess
0x1802b1220  mov     rcx, rax; ProcessHandle
0x1802b1223  call    cs:__imp_OpenProcessToken
0x1802b1229  test    eax, eax
0x1802b122b  jnz     short loc_1802B1234
0x1802b122d  mov     edx, 182h
0x1802b1232  jmp     short loc_1802B1269
0x1802b1234  xor     edx, edx
0x1802b1236  mov     rcx, rdi
0x1802b1239  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b123e  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1802b1243  mov     r9d, 2; ImpersonationLevel
0x1802b1249  mov     [rsp+38h+TokenType], r9d; TokenType
0x1802b124e  xor     r8d, r8d; lpTokenAttributes
0x1802b1251  lea     edx, [r9+6]; dwDesiredAccess
0x1802b1255  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1802b125a  call    cs:__imp_DuplicateTokenEx
0x1802b1260  test    eax, eax
0x1802b1262  jnz     short loc_1802B128B
0x1802b1264  mov     edx, 184h; void *
0x1802b1269  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802b1270  mov     rcx, [rsp+38h]; this
0x1802b1275  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b127a  mov     ebx, eax
0x1802b127c  lea     rcx, [rsp+38h+TokenHandle]
0x1802b1281  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b1286  jmp     loc_1802B11AF
0x1802b128b  lea     rcx, [rsp+38h+TokenHandle]
0x1802b1290  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b1295  jmp     short loc_1802B12CE
0x1802b1297  test    eax, eax
0x1802b1299  jz      short loc_1802B12C4
0x1802b129b  mov     rcx, [rsp+38h]; this
0x1802b12a0  mov     r9d, eax; char *
0x1802b12a3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802b12aa  mov     edx, 188h; void *
0x1802b12af  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802b12b4  mov     edi, eax
0x1802b12b6  test    bl, bl
0x1802b12b8  jz      short loc_1802B12C0
0x1802b12ba  call    cs:__imp_CoRevertToSelf
0x1802b12c0  mov     eax, edi
0x1802b12c2  jmp     short loc_1802B12D0
0x1802b12c4  test    bl, bl
0x1802b12c6  jz      short loc_1802B12CE
0x1802b12c8  call    cs:__imp_CoRevertToSelf
0x1802b12ce  xor     eax, eax
0x1802b12d0  mov     rbx, [rsp+38h+arg_0]
0x1802b12d5  add     rsp, 30h
0x1802b12d9  pop     rdi
0x1802b12da  retn
```
