# UserHelpers::Impersonator::Impersonate(void)

- ea: `0x180446240`
- end: `0x1804463c5`
- name: `?Impersonate@Impersonator@UserHelpers@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1804452b0`

## callees

- `0x180033f28`
- `0x1800795e4`
- `0x180086f44`
- `0x1800a14f8`
- `0x1800e3810`
- `0x1801588c4`
- `0x18015d524`
- `0x180446240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180446357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180446357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180446331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180446331`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180446349`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180446349`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18044637d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18044637d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1804462a6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1804462a6`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x1804462f4`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x1804462f4`

## string_xrefs

- `0x180446269`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x180446305`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x180446364`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x18044638b`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall UserHelpers::Impersonator::Impersonate(__int64 a1, _QWORD *a2, __int64 a3, const char *a4)
{
  __int64 v6; // rdi
  BOOL v7; // edi
  void *v8; // rcx
  void *v9; // rcx
  unsigned int v10; // eax
  HANDLE CurrentThread; // rax
  const char *v12; // r9
  const char *v13; // r9
  void *v14; // rax
  unsigned int v16; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  void *Block; // [rsp+60h] [rbp+30h] BYREF
  void *v20; // [rsp+68h] [rbp+38h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  if ( ((v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD8,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
      a4);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&v20, -6);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v6);
  v7 = EqualSid(*(PSID *)v20, *(PSID *)Block);
  v8 = Block;
  Block = 0;
  if ( v8 )
    operator delete(v8);
  v9 = v20;
  v20 = 0;
  if ( v9 )
    operator delete(v9);
  if ( v7 )
  {
    *a2 = -1;
  }
  else
  {
    if ( !`UserHelpers::Impersonator::Impersonate'::`2'::s_disabledPredefinedCache )
    {
      v10 = RegDisablePredefinedCacheEx();
      if ( v10 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xE3,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
          (const char *)v10,
          v16);
      `UserHelpers::Impersonator::Impersonate'::`2'::s_disabledPredefinedCache = 1;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xED,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        v12);
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 8)) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF2,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        v13);
    v14 = TokenHandle;
    TokenHandle = 0;
    *a2 = v14;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  return a2;
}

```

## disassembly

```asm
0x180446240  mov     [rsp-18h+arg_8], rbx
0x180446245  push    rbp
0x180446246  push    rsi
0x180446247  push    rdi
0x180446248  mov     rbp, rsp
0x18044624b  sub     rsp, 30h
0x18044624f  mov     rbx, rdx
0x180446252  mov     rsi, rcx
0x180446255  mov     rcx, [rbp+18h]; this
0x180446259  mov     rdi, [rsi+8]
0x18044625d  lea     rax, [rdi+1]
0x180446261  test    rax, 0FFFFFFFFFFFFFFFEh
0x180446267  jnz     short loc_18044627B
0x180446269  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x180446270  mov     edx, 0D8h; void *
0x180446275  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18044627b  mov     rdx, 0FFFFFFFFFFFFFFFAh
0x180446282  lea     rcx, [rbp+arg_18]
0x180446286  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18044628b  nop
0x18044628c  mov     rdx, rdi
0x18044628f  lea     rcx, [rbp+Block]
0x180446293  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180446298  mov     rdx, [rbp+Block]
0x18044629c  mov     rdx, [rdx]; pSid2
0x18044629f  mov     rcx, [rbp+arg_18]
0x1804462a3  mov     rcx, [rcx]; pSid1
0x1804462a6  call    cs:__imp_EqualSid
0x1804462ac  mov     edi, eax
0x1804462ae  mov     rcx, [rbp+Block]; Block
0x1804462b2  mov     [rbp+Block], 0
0x1804462ba  test    rcx, rcx
0x1804462bd  jz      short loc_1804462C5
0x1804462bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804462c4  nop
0x1804462c5  mov     rcx, [rbp+arg_18]; Block
0x1804462c9  mov     [rbp+arg_18], 0
0x1804462d1  test    rcx, rcx
0x1804462d4  jz      short loc_1804462DB
0x1804462d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804462db  test    edi, edi
0x1804462dd  jz      short loc_1804462EB
0x1804462df  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1804462e6  jmp     loc_1804463B5
0x1804462eb  cmp     cs:?s_disabledPredefinedCache@?1??Impersonate@Impersonator@UserHelpers@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ@4_NA, 0; bool `UserHelpers::Impersonator::Impersonate(void)'::`2'::s_disabledPredefinedCache
0x1804462f2  jnz     short loc_18044631E
0x1804462f4  call    cs:__imp_RegDisablePredefinedCacheEx
0x1804462fa  test    eax, eax
0x1804462fc  jz      short loc_180446317
0x1804462fe  mov     rcx, [rbp+18h]; this
0x180446302  mov     r9d, eax; char *
0x180446305  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x18044630c  mov     edx, 0E3h; void *
0x180446311  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180446317  mov     cs:?s_disabledPredefinedCache@?1??Impersonate@Impersonator@UserHelpers@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ@4_NA, 1; bool `UserHelpers::Impersonator::Impersonate(void)'::`2'::s_disabledPredefinedCache
0x18044631e  mov     [rbp+TokenHandle], 0
0x180446326  xor     edx, edx
0x180446328  lea     rcx, [rbp+TokenHandle]
0x18044632c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180446331  call    cs:__imp_GetCurrentThread
0x180446337  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18044633b  mov     edx, 0F01FFh; DesiredAccess
0x180446340  mov     r8d, 1; OpenAsSelf
0x180446346  mov     rcx, rax; ThreadHandle
0x180446349  call    cs:__imp_OpenThreadToken
0x18044634f  test    eax, eax
0x180446351  jnz     short loc_180446379
0x180446353  mov     rdi, [rbp+18h]
0x180446357  call    cs:__imp_GetLastError
0x18044635d  cmp     eax, 3F0h
0x180446362  jz      short loc_180446379
0x180446364  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x18044636b  mov     edx, 0EDh; void *
0x180446370  mov     rcx, rdi; this
0x180446373  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180446379  mov     rcx, [rsi+8]; hToken
0x18044637d  call    cs:__imp_ImpersonateLoggedOnUser
0x180446383  mov     rcx, [rbp+18h]; this
0x180446387  test    eax, eax
0x180446389  jnz     short loc_18044639D
0x18044638b  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x180446392  mov     edx, 0F2h; void *
0x180446397  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18044639d  mov     rax, [rbp+TokenHandle]
0x1804463a1  mov     [rbp+TokenHandle], 0
0x1804463a9  mov     [rbx], rax
0x1804463ac  lea     rcx, [rbp+TokenHandle]
0x1804463b0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1804463b5  mov     rax, rbx
0x1804463b8  mov     rbx, [rsp+30h+arg_8]
0x1804463bd  add     rsp, 30h
0x1804463c1  pop     rdi
0x1804463c2  pop     rsi
0x1804463c3  pop     rbp
0x1804463c4  retn
```
