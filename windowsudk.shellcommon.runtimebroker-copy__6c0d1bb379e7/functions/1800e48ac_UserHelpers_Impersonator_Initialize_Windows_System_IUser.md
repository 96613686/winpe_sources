# UserHelpers::Impersonator::Initialize(Windows::System::IUser *)

- ea: `0x1800e48ac`
- end: `0x1800e4d60`
- name: `?Initialize@Impersonator@UserHelpers@@AEAAXPEAUIUser@System@Windows@@@Z`
- size: `1204`
- prototype: `void __fastcall(UserHelpers::Impersonator *__hidden this, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180445090`

## callees

- `0x18002e634`
- `0x18007c5dc`
- `0x1800a14f8`
- `0x1800e3810`
- `0x1800e488c`
- `0x1800e48ac`
- `0x1800e4df4`
- `0x1800e4e18`
- `0x1800e6508`
- `0x180148a78`
- `0x1801588c4`
- `0x18015cb00`
- `0x180278160`
- `0x18044642c`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e4afa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e4afa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e4957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e4957`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800e4b06`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800e4b06`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e4bb6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e4c86`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e4bb6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e4c86`
- `ntdll!RtlIsMultiSessionSku` at `0x1800e4b26`
- `ntdll!RtlIsMultiSessionSku` at `0x1800e4b26`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800e4b34`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800e4b34`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e49c2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e49c2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800e4ac5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800e4ac5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800e4b5e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800e4b5e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x1800e4ce8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x1800e4ce8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x1800e4c26`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x1800e4c26`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800e4915`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800e4a36`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800e4915`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800e4a36`

## string_xrefs

- `0x1800e4926`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4974`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e49d3`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4a0d`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4a47`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4a98`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4ad6`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4b14`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4b6f`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4bc4`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4bfa`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4c37`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4c94`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4cbc`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`
- `0x1800e4cf9`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall UserHelpers::Impersonator::Initialize(
        UserHelpers::Impersonator *this,
        struct Windows::System::IUser *a2)
{
  __int64 v4; // rsi
  int UserContext; // eax
  CallerIdentity *CurrentProcess; // rax
  bool *v7; // r8
  int IsProcessAppContainer; // eax
  int ActivationFactory; // eax
  _QWORD *v10; // rsi
  int v11; // eax
  void *v12; // rdx
  int v13; // eax
  _QWORD *v14; // rbx
  const char *v15; // r9
  int ConstrainedUserToken; // eax
  DWORD CurrentProcessId; // eax
  const char *v18; // r9
  int UserToken; // eax
  const char *v20; // r9
  HANDLE *p_hExistingToken; // rcx
  const char *v22; // r9
  int SessionUserToken; // eax
  const char *v24; // r9
  const char *v25; // r9
  int ImpersonationTokenForContext; // eax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-60h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-60h]
  _BYTE v29[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD pSessionId; // [rsp+34h] [rbp-4Ch] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-48h] BYREF
  HANDLE v32; // [rsp+40h] [rbp-40h] BYREF
  UserHelpers *v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v36; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( a2 )
  {
    v29[0] = 0;
    CurrentProcess = (CallerIdentity *)GetCurrentProcess();
    IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v29, v7);
    if ( IsProcessAppContainer < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        (const char *)(unsigned int)IsProcessAppContainer,
        TokenType);
    wil::open_current_access_token(&v33);
    v34 = 0;
    v36 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v36, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v34);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x112,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        (const char *)(unsigned int)ActivationFactory,
        TokenType);
    v10 = (_QWORD *)((char *)this + 16);
    v11 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, char *))(*(_QWORD *)v34 + 136LL))(
            v34,
            a2,
            (char *)this + 16);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        (const char *)(unsigned int)v11,
        TokenType);
    if ( !UserHelpers::IsSystemAccount(v33, v12) )
    {
      v32 = 0;
      v13 = UMgrQueryUserContext(0, &v32);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x11B,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
          (const char *)(unsigned int)v13,
          TokenType);
      if ( v32 == (HANDLE)*v10 )
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          (char *)this + 8,
          &v33);
    }
    v14 = (_QWORD *)((char *)this + 8);
    if ( ((*v14 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( v29[0] )
      {
        if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x126,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
            v15);
        *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v14;
        hstringHeader.Reserved.Reserved2[16] = 1;
        ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *v10, 0, &hstringHeader.Reserved.Reserved2[8]);
        if ( ConstrainedUserToken < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x127,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
            (const char *)(unsigned int)ConstrainedUserToken,
            TokenType);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
      }
      else
      {
        pSessionId = 0;
        CurrentProcessId = GetCurrentProcessId();
        if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x12D,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
            v18);
        if ( (unsigned __int8)RtlIsMultiSessionSku(retaddr)
          && pSessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
        {
          hExistingToken = 0;
          hstringHeader.Reserved.Reserved1 = &hExistingToken;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          hstringHeader.Reserved.Reserved2[16] = 1;
          UserToken = UMgrQueryUserToken(*v10, &hstringHeader.Reserved.Reserved2[8]);
          if ( UserToken < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x134,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              (const char *)(unsigned int)UserToken,
              TokenType);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v14;
          hstringHeader.Reserved.Reserved2[16] = 1;
          if ( !DuplicateTokenEx(
                  hExistingToken,
                  0x2000000u,
                  0,
                  SecurityImpersonation,
                  TokenImpersonation,
                  (PHANDLE)&hstringHeader.Reserved.Reserved2[8]) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x135,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              v20);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          p_hExistingToken = &hExistingToken;
        }
        else
        {
          v32 = 0;
          if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x141,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              v22);
          hstringHeader.Reserved.Reserved1 = &v32;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          hstringHeader.Reserved.Reserved2[16] = 1;
          SessionUserToken = UMgrQuerySessionUserToken(pSessionId, &hstringHeader.Reserved.Reserved2[8]);
          if ( SessionUserToken < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x142,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              (const char *)(unsigned int)SessionUserToken,
              TokenType);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          hExistingToken = 0;
          hstringHeader.Reserved.Reserved1 = &hExistingToken;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          hstringHeader.Reserved.Reserved2[16] = 1;
          if ( !DuplicateTokenEx(
                  v32,
                  0x2000000u,
                  0,
                  SecurityImpersonation,
                  TokenImpersonation,
                  (PHANDLE)&hstringHeader.Reserved.Reserved2[8]) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x145,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              v24);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x146,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              v25);
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v14;
          hstringHeader.Reserved.Reserved2[16] = 1;
          ImpersonationTokenForContext = UMgrGetImpersonationTokenForContext(
                                           hExistingToken,
                                           *v10,
                                           &hstringHeader.Reserved.Reserved2[8]);
          if ( ImpersonationTokenForContext < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x147,
              (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
              (const char *)(unsigned int)ImpersonationTokenForContext,
              TokenTypea);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
          p_hExistingToken = &v32;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(p_hExistingToken);
      }
    }
    wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v34);
  }
  else
  {
    UserContext = UMgrQueryUserContext(0, (char *)this + 16);
    if ( UserContext < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
        (const char *)(unsigned int)UserContext,
        TokenType);
    wil::open_current_access_token(&v33);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 8,
      &v33);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
}

```

## disassembly

```asm
0x1800e48ac  mov     [rsp-18h+arg_10], rbx
0x1800e48b1  mov     [rsp-18h+arg_18], rsi
0x1800e48b6  push    rbp
0x1800e48b7  push    rdi
0x1800e48b8  push    r14
0x1800e48ba  mov     rbp, rsp
0x1800e48bd  sub     rsp, 80h
0x1800e48c4  mov     rax, cs:__security_cookie
0x1800e48cb  xor     rax, rsp
0x1800e48ce  mov     [rbp+var_8], rax
0x1800e48d2  mov     rdi, rdx
0x1800e48d5  mov     rbx, rcx
0x1800e48d8  xor     r14d, r14d
0x1800e48db  mov     rsi, [rcx]
0x1800e48de  mov     [rcx], rdx
0x1800e48e1  test    rdx, rdx
0x1800e48e4  jz      short loc_1800E48F5
0x1800e48e6  mov     rax, [rdx]
0x1800e48e9  mov     rcx, rdx
0x1800e48ec  mov     rax, [rax+8]
0x1800e48f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e48f5  test    rsi, rsi
0x1800e48f8  jz      short loc_1800E490A
0x1800e48fa  mov     rax, [rsi]
0x1800e48fd  mov     rcx, rsi
0x1800e4900  mov     rax, [rax+10h]
0x1800e4904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4909  nop
0x1800e490a  test    rdi, rdi
0x1800e490d  jnz     short loc_1800E4953
0x1800e490f  lea     rdx, [rbx+10h]
0x1800e4913  xor     ecx, ecx
0x1800e4915  call    cs:__imp_UMgrQueryUserContext
0x1800e491b  test    eax, eax
0x1800e491d  jns     short loc_1800E4938
0x1800e491f  mov     rcx, [rbp+18h]; this
0x1800e4923  mov     r9d, eax; char *
0x1800e4926  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e492d  mov     edx, 108h; void *
0x1800e4932  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4938  lea     rcx, [rbp+var_38]
0x1800e493c  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x1800e4941  lea     rcx, [rbx+8]
0x1800e4945  lea     rdx, [rbp+var_38]
0x1800e4949  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e494e  jmp     loc_1800E4D33
0x1800e4953  mov     [rbp+var_50], r14b
0x1800e4957  call    cs:__imp_GetCurrentProcess
0x1800e495d  mov     rcx, rax; this
0x1800e4960  lea     rdx, [rbp+var_50]; void *
0x1800e4964  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x1800e4969  mov     rcx, [rbp+18h]; this
0x1800e496d  test    eax, eax
0x1800e496f  jns     short loc_1800E4986
0x1800e4971  mov     r9d, eax; char *
0x1800e4974  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e497b  mov     edx, 10Eh; void *
0x1800e4980  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4986  lea     rcx, [rbp+var_38]
0x1800e498a  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x1800e498f  nop
0x1800e4990  mov     [rbp+var_30], r14
0x1800e4994  mov     [rbp+var_10], r14
0x1800e4998  mov     r9d, 23h ; '#'; unsigned int
0x1800e499e  lea     r8d, [r9+1]; unsigned int
0x1800e49a2  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QB_WB; "Windows.System.Internal.UserManager"
0x1800e49a9  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800e49ad  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x1800e49b2  nop
0x1800e49b3  lea     r8, [rbp+var_30]
0x1800e49b7  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800e49be  mov     rcx, [rbp+var_10]
0x1800e49c2  call    cs:__imp_RoGetActivationFactory
0x1800e49c8  mov     rcx, [rbp+18h]; this
0x1800e49cc  test    eax, eax
0x1800e49ce  jns     short loc_1800E49E5
0x1800e49d0  mov     r9d, eax; char *
0x1800e49d3  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e49da  mov     edx, 112h; void *
0x1800e49df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e49e5  mov     rcx, [rbp+var_30]
0x1800e49e9  lea     rsi, [rbx+10h]
0x1800e49ed  mov     rax, [rcx]
0x1800e49f0  mov     r8, rsi
0x1800e49f3  mov     rdx, rdi
0x1800e49f6  mov     rax, [rax+88h]
0x1800e49fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4a02  mov     rcx, [rbp+18h]; this
0x1800e4a06  test    eax, eax
0x1800e4a08  jns     short loc_1800E4A1F
0x1800e4a0a  mov     r9d, eax; char *
0x1800e4a0d  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4a14  mov     edx, 113h; void *
0x1800e4a19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4a1f  mov     rcx, [rbp+var_38]; this
0x1800e4a23  call    ?IsSystemAccount@UserHelpers@@YA_NPEAX@Z; UserHelpers::IsSystemAccount(void *)
0x1800e4a28  test    al, al
0x1800e4a2a  jnz     short loc_1800E4A6F
0x1800e4a2c  mov     [rbp+var_40], r14
0x1800e4a30  lea     rdx, [rbp+var_40]
0x1800e4a34  xor     ecx, ecx
0x1800e4a36  call    cs:__imp_UMgrQueryUserContext
0x1800e4a3c  mov     rcx, [rbp+18h]; this
0x1800e4a40  test    eax, eax
0x1800e4a42  jns     short loc_1800E4A59
0x1800e4a44  mov     r9d, eax; char *
0x1800e4a47  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4a4e  mov     edx, 11Bh; void *
0x1800e4a53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4a59  mov     rax, [rsi]
0x1800e4a5c  cmp     [rbp+var_40], rax
0x1800e4a60  jnz     short loc_1800E4A6F
0x1800e4a62  lea     rcx, [rbx+8]
0x1800e4a66  lea     rdx, [rbp+var_38]
0x1800e4a6a  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800e4a6f  add     rbx, 8
0x1800e4a73  mov     rax, [rbx]
0x1800e4a76  inc     rax
0x1800e4a79  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e4a7f  jnz     loc_1800E4D29
0x1800e4a85  cmp     [rbp+var_50], r14b
0x1800e4a89  jz      short loc_1800E4AF6
0x1800e4a8b  mov     rdi, [rbp+18h]
0x1800e4a8f  call    IsUMgrGetImpersonationTokenForContextPresent
0x1800e4a94  test    al, al
0x1800e4a96  jnz     short loc_1800E4AAD
0x1800e4a98  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4a9f  mov     edx, 126h; void *
0x1800e4aa4  mov     rcx, rdi; this
0x1800e4aa7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e4aad  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800e4ab1  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4ab5  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4ab9  lea     r9, [rbp+hstringHeader.Reserved+8]
0x1800e4abd  xor     r8d, r8d
0x1800e4ac0  mov     rdx, [rsi]
0x1800e4ac3  xor     ecx, ecx
0x1800e4ac5  call    cs:__imp_UMgrGetConstrainedUserToken
0x1800e4acb  mov     rcx, [rbp+18h]; this
0x1800e4acf  test    eax, eax
0x1800e4ad1  jns     short loc_1800E4AE8
0x1800e4ad3  mov     r9d, eax; char *
0x1800e4ad6  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4add  mov     edx, 127h; void *
0x1800e4ae2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4ae8  lea     rcx, [rbp+hstringHeader]
0x1800e4aec  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4af1  jmp     loc_1800E4D29
0x1800e4af6  mov     [rbp+pSessionId], r14d
0x1800e4afa  call    cs:__imp_GetCurrentProcessId
0x1800e4b00  mov     ecx, eax; dwProcessId
0x1800e4b02  lea     rdx, [rbp+pSessionId]; pSessionId
0x1800e4b06  call    cs:__imp_ProcessIdToSessionId
0x1800e4b0c  mov     rcx, [rbp+18h]; this
0x1800e4b10  test    eax, eax
0x1800e4b12  jnz     short loc_1800E4B26
0x1800e4b14  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4b1b  mov     edx, 12Dh; void *
0x1800e4b20  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e4b26  call    cs:__imp_RtlIsMultiSessionSku
0x1800e4b2c  test    al, al
0x1800e4b2e  jz      loc_1800E4BE9
0x1800e4b34  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800e4b3a  cmp     [rbp+pSessionId], eax
0x1800e4b3d  jnz     loc_1800E4BE9
0x1800e4b43  mov     [rbp+hExistingToken], r14
0x1800e4b47  lea     rax, [rbp+hExistingToken]
0x1800e4b4b  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x1800e4b4f  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4b53  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4b57  lea     rdx, [rbp+hstringHeader.Reserved+8]
0x1800e4b5b  mov     rcx, [rsi]
0x1800e4b5e  call    cs:__imp_UMgrQueryUserToken
0x1800e4b64  mov     rcx, [rbp+18h]; this
0x1800e4b68  test    eax, eax
0x1800e4b6a  jns     short loc_1800E4B81
0x1800e4b6c  mov     r9d, eax; char *
0x1800e4b6f  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4b76  mov     edx, 134h; void *
0x1800e4b7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4b81  lea     rcx, [rbp+hstringHeader]
0x1800e4b85  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4b8a  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800e4b8e  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4b92  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4b96  lea     rax, [rbp+hstringHeader.Reserved+8]
0x1800e4b9a  mov     [rsp+80h+phNewToken], rax; phNewToken
0x1800e4b9f  mov     r9d, 2; ImpersonationLevel
0x1800e4ba5  mov     [rsp+80h+TokenType], r9d; TokenType
0x1800e4baa  xor     r8d, r8d; lpTokenAttributes
0x1800e4bad  mov     edx, 2000000h; dwDesiredAccess
0x1800e4bb2  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x1800e4bb6  call    cs:__imp_DuplicateTokenEx
0x1800e4bbc  mov     rcx, [rbp+18h]; this
0x1800e4bc0  test    eax, eax
0x1800e4bc2  jnz     short loc_1800E4BD6
0x1800e4bc4  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4bcb  mov     edx, 135h; void *
0x1800e4bd0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e4bd6  lea     rcx, [rbp+hstringHeader]
0x1800e4bda  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4bdf  nop
0x1800e4be0  lea     rcx, [rbp+hExistingToken]
0x1800e4be4  jmp     loc_1800E4D23
0x1800e4be9  mov     [rbp+var_40], r14
0x1800e4bed  mov     rdi, [rbp+18h]
0x1800e4bf1  call    IsUMgrGetImpersonationTokenForContextPresent
0x1800e4bf6  test    al, al
0x1800e4bf8  jnz     short loc_1800E4C0F
0x1800e4bfa  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4c01  mov     edx, 141h; void *
0x1800e4c06  mov     rcx, rdi; this
0x1800e4c09  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e4c0f  lea     rax, [rbp+var_40]
0x1800e4c13  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x1800e4c17  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4c1b  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4c1f  lea     rdx, [rbp+hstringHeader.Reserved+8]
0x1800e4c23  mov     ecx, [rbp+pSessionId]
0x1800e4c26  call    cs:__imp_UMgrQuerySessionUserToken
0x1800e4c2c  mov     rcx, [rbp+18h]; this
0x1800e4c30  test    eax, eax
0x1800e4c32  jns     short loc_1800E4C49
0x1800e4c34  mov     r9d, eax; char *
0x1800e4c37  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4c3e  mov     edx, 142h; void *
0x1800e4c43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4c49  lea     rcx, [rbp+hstringHeader]
0x1800e4c4d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4c52  mov     [rbp+hExistingToken], r14
0x1800e4c56  lea     rax, [rbp+hExistingToken]
0x1800e4c5a  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x1800e4c5e  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4c62  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4c66  lea     rax, [rbp+hstringHeader.Reserved+8]
0x1800e4c6a  mov     [rsp+80h+phNewToken], rax; phNewToken
0x1800e4c6f  mov     r9d, 2; ImpersonationLevel
0x1800e4c75  mov     [rsp+80h+TokenType], r9d; int
0x1800e4c7a  xor     r8d, r8d; lpTokenAttributes
0x1800e4c7d  mov     edx, 2000000h; dwDesiredAccess
0x1800e4c82  mov     rcx, [rbp+var_40]; hExistingToken
0x1800e4c86  call    cs:__imp_DuplicateTokenEx
0x1800e4c8c  mov     rcx, [rbp+18h]; this
0x1800e4c90  test    eax, eax
0x1800e4c92  jnz     short loc_1800E4CA6
0x1800e4c94  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4c9b  mov     edx, 145h; void *
0x1800e4ca0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e4ca6  lea     rcx, [rbp+hstringHeader]
0x1800e4caa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4caf  mov     rdi, [rbp+18h]
0x1800e4cb3  call    IsUMgrGetImpersonationTokenForContextPresent
0x1800e4cb8  test    al, al
0x1800e4cba  jnz     short loc_1800E4CD1
0x1800e4cbc  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4cc3  mov     edx, 146h; void *
0x1800e4cc8  mov     rcx, rdi; this
0x1800e4ccb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e4cd1  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800e4cd5  mov     qword ptr [rbp+hstringHeader.Reserved+8], r14
0x1800e4cd9  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x1800e4cdd  lea     r8, [rbp+hstringHeader.Reserved+8]
0x1800e4ce1  mov     rdx, [rsi]
0x1800e4ce4  mov     rcx, [rbp+hExistingToken]
0x1800e4ce8  call    cs:__imp_UMgrGetImpersonationTokenForContext
0x1800e4cee  mov     rcx, [rbp+18h]; this
0x1800e4cf2  test    eax, eax
0x1800e4cf4  jns     short loc_1800E4D0B
0x1800e4cf6  mov     r9d, eax; char *
0x1800e4cf9  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x1800e4d00  mov     edx, 147h; void *
0x1800e4d05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4d0b  lea     rcx, [rbp+hstringHeader]
0x1800e4d0f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e4d14  nop
0x1800e4d15  lea     rcx, [rbp+hExistingToken]
0x1800e4d19  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e4d1e  nop
0x1800e4d1f  lea     rcx, [rbp+var_40]
0x1800e4d23  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e4d28  nop
0x1800e4d29  lea     rcx, [rbp+var_30]
0x1800e4d2d  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1800e4d32  nop
0x1800e4d33  lea     rcx, [rbp+var_38]
0x1800e4d37  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e4d3c  mov     rcx, [rbp+var_8]
0x1800e4d40  xor     rcx, rsp; StackCookie
0x1800e4d43  call    __security_check_cookie
0x1800e4d48  lea     r11, [rsp+80h+var_s0]
0x1800e4d50  mov     rbx, [r11+30h]
0x1800e4d54  mov     rsi, [r11+38h]
0x1800e4d58  mov     rsp, r11
0x1800e4d5b  pop     r14
0x1800e4d5d  pop     rdi
0x1800e4d5e  pop     rbp
0x1800e4d5f  retn
```
