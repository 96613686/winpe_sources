# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180051234`
- end: `0x1800513c7`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e4dc`

## callees

- `0x180019b14`
- `0x18001ca50`
- `0x18001cc38`
- `0x18001e340`
- `0x18003e898`
- `0x18004504c`
- `0x180051234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800512fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800512fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800512c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800512c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800512ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800512ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005130f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005130f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180051346`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180051346`
- `combase!__imp_CoImpersonateClientOfObject` at `0x180051251`
- `combase!__imp_CoImpersonateClientOfObject` at `0x180051251`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800513a6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800513b4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800513a6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800513b4`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
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
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v13;
}

```

## disassembly

```asm
0x180051234  mov     rax, rsp
0x180051237  mov     [rax+8], rbx
0x18005123b  mov     [rax+10h], edx
0x18005123e  push    rdi
0x18005123f  sub     rsp, 30h
0x180051243  lea     rdx, [rax+10h]
0x180051247  mov     dword ptr [rax+10h], 0
0x18005124e  mov     rdi, r8
0x180051251  call    cs:__imp_CoImpersonateClientOfObject
0x180051257  mov     ebx, eax
0x180051259  test    eax, eax
0x18005125b  jns     short loc_180051296
0x18005125d  mov     rcx, [rsp+38h]; this
0x180051262  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180051269  mov     r9d, eax; char *
0x18005126c  mov     edx, 157h; void *
0x180051271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051276  mov     rcx, [rsp+38h]; this
0x18005127b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180051282  mov     r9d, ebx; char *
0x180051285  mov     edx, 177h; void *
0x18005128a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005128f  mov     eax, ebx
0x180051291  jmp     loc_1800513BC
0x180051296  xor     bl, bl
0x180051298  cmp     [rsp+38h+arg_8], 0
0x18005129d  jz      short loc_1800512A1
0x18005129f  mov     bl, 1
0x1800512a1  xor     edx, edx
0x1800512a3  mov     rcx, rdi
0x1800512a6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800512ab  call    cs:__imp_GetCurrentThread
0x1800512b1  mov     edx, 8; DesiredAccess
0x1800512b6  mov     r9, rdi; TokenHandle
0x1800512b9  mov     rcx, rax; ThreadHandle
0x1800512bc  lea     r8d, [rdx-7]; OpenAsSelf
0x1800512c0  call    cs:__imp_OpenThreadToken
0x1800512c6  test    eax, eax
0x1800512c8  jnz     loc_1800513B0
0x1800512ce  call    cs:__imp_GetLastError
0x1800512d4  test    bl, bl
0x1800512d6  jnz     loc_180051383
0x1800512dc  cmp     eax, 3F0h
0x1800512e1  jnz     loc_180051383
0x1800512e7  xor     edx, edx
0x1800512e9  mov     [rsp+38h+TokenHandle], 0
0x1800512f2  lea     rcx, [rsp+38h+TokenHandle]
0x1800512f7  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800512fc  call    cs:__imp_GetCurrentProcess
0x180051302  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180051307  mov     edx, 0Ah; DesiredAccess
0x18005130c  mov     rcx, rax; ProcessHandle
0x18005130f  call    cs:__imp_OpenProcessToken
0x180051315  test    eax, eax
0x180051317  jnz     short loc_180051320
0x180051319  mov     edx, 182h
0x18005131e  jmp     short loc_180051355
0x180051320  xor     edx, edx
0x180051322  mov     rcx, rdi
0x180051325  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005132a  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18005132f  mov     r9d, 2; ImpersonationLevel
0x180051335  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18005133a  xor     r8d, r8d; lpTokenAttributes
0x18005133d  mov     [rsp+38h+TokenType], r9d; TokenType
0x180051342  lea     edx, [r9+6]; dwDesiredAccess
0x180051346  call    cs:__imp_DuplicateTokenEx
0x18005134c  test    eax, eax
0x18005134e  jnz     short loc_180051377
0x180051350  mov     edx, 184h; void *
0x180051355  mov     rcx, [rsp+38h]; this
0x18005135a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180051361  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051366  lea     rcx, [rsp+38h+TokenHandle]
0x18005136b  mov     ebx, eax
0x18005136d  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180051372  jmp     loc_18005128F
0x180051377  lea     rcx, [rsp+38h+TokenHandle]
0x18005137c  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180051381  jmp     short loc_1800513BA
0x180051383  test    eax, eax
0x180051385  jz      short loc_1800513B0
0x180051387  mov     rcx, [rsp+38h]; this
0x18005138c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180051393  mov     r9d, eax; char *
0x180051396  mov     edx, 188h; void *
0x18005139b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800513a0  mov     edi, eax
0x1800513a2  test    bl, bl
0x1800513a4  jz      short loc_1800513AC
0x1800513a6  call    cs:__imp_CoRevertToSelf
0x1800513ac  mov     eax, edi
0x1800513ae  jmp     short loc_1800513BC
0x1800513b0  test    bl, bl
0x1800513b2  jz      short loc_1800513BA
0x1800513b4  call    cs:__imp_CoRevertToSelf
0x1800513ba  xor     eax, eax
0x1800513bc  mov     rbx, [rsp+38h+arg_0]
0x1800513c1  add     rsp, 30h
0x1800513c5  pop     rdi
0x1800513c6  retn
```
