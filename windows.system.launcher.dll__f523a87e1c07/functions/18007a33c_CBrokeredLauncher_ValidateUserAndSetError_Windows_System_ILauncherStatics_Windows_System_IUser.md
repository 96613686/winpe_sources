# CBrokeredLauncher::_ValidateUserAndSetError(Windows::System::ILauncherStatics *,Windows::System::IUser *)

- ea: `0x18007a33c`
- end: `0x18007a53c`
- name: `?_ValidateUserAndSetError@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAUIUser@34@@Z`
- size: `512`
- prototype: `void __fastcall(struct Windows::System::ILauncherStatics *, struct Windows::System::IUser *)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050d60`
- `0x180050f10`
- `0x180051420`
- `0x180051530`
- `0x180085a80`
- `0x180085c40`

## callees

- `0x18000f194`
- `0x18002cec0`
- `0x18003ab7c`
- `0x180042254`
- `0x180042590`
- `0x180053018`
- `0x18006323c`
- `0x18007a33c`
- `0x18007a544`
- `0x18007a5c8`
- `0x18007a668`
- `0x18008a030`
- `0x18008b61c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a3fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a3fe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007a47b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007a47b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18007a450`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18007a450`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18007a4d5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18007a4d5`

## string_xrefs

- `0x18007a3b1`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007a42c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007a461`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007a48c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18007a4e2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CBrokeredLauncher::_ValidateUserAndSetError(
        struct Windows::System::ILauncherStatics *a1,
        struct Windows::System::IUser *a2)
{
  int v4; // eax
  unsigned int *v5; // rdx
  int CallingProcessId; // eax
  int v7; // eax
  int v8; // eax
  void *TokenHandle; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v10; // [rsp+28h] [rbp-58h] BYREF
  __int64 v11; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+38h] [rbp-48h] BYREF
  __int64 v13; // [rsp+40h] [rbp-40h] BYREF
  HANDLE ProcessHandle; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v15[8]; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(v15);
  v11 = 0;
  wil::com_ptr_t<Windows::System::Internal::IUserManagerStatics,wil::err_exception_policy>::query_to<Windows::System::Internal::ISignInStateManager>(
    v15,
    &v11);
  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v11 + 136LL))(
         v11,
         a2,
         &v13);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x378,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v4,
      (int)TokenHandle);
  v12 = 0;
  wil::GetProcessHandleForClientOfObject(&ProcessHandle, a1, 4096);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) && (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
  {
    v10 = 0;
    CallingProcessId = UserAwareCallerIdentity::GetCallingProcessId((UserAwareCallerIdentity *)&v10, v5);
    if ( CallingProcessId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x385,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)CallingProcessId,
        (int)TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    v7 = UMgrOpenProcessTokenForQuery(v10, &TokenHandle);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x386,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v7,
        (int)TokenHandle);
  }
  v8 = UMgrQueryUserContext(TokenHandle, &v12);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v8,
      (int)TokenHandle);
  if ( v13 != v12 )
  {
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"user", 5u, 4u);
    RoOriginateError(2147942487LL, v17);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)0x80070057LL,
      (int)TokenHandle);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v11);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v15);
}

```

## disassembly

```asm
0x18007a33c  mov     [rsp-8+arg_10], rbx
0x18007a341  mov     [rsp-8+arg_18], rdi
0x18007a346  push    rbp
0x18007a347  mov     rbp, rsp
0x18007a34a  sub     rsp, 80h
0x18007a351  mov     rax, cs:__security_cookie
0x18007a358  xor     rax, rsp
0x18007a35b  mov     [rbp+var_8], rax
0x18007a35f  mov     rbx, rdx
0x18007a362  mov     rdi, rcx
0x18007a365  lea     rcx, [rbp+var_30]
0x18007a369  call    ??$GetActivationFactory@UIUserManagerStatics@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(ushort const *)
0x18007a36e  nop
0x18007a36f  mov     [rbp+var_50], 0
0x18007a377  lea     rdx, [rbp+var_50]
0x18007a37b  lea     rcx, [rbp+var_30]
0x18007a37f  call    ??$query_to@UISignInStateManager@Internal@System@Windows@@@?$com_ptr_t@UIUserManagerStatics@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUISignInStateManager@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::IUserManagerStatics,wil::err_exception_policy>::query_to<Windows::System::Internal::ISignInStateManager>(Windows::System::Internal::ISignInStateManager * *)
0x18007a384  mov     [rbp+var_40], 0
0x18007a38c  mov     rcx, [rbp+var_50]
0x18007a390  mov     rax, [rcx]
0x18007a393  lea     r8, [rbp+var_40]
0x18007a397  mov     rdx, rbx
0x18007a39a  mov     rax, [rax+88h]
0x18007a3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3a6  mov     rcx, [rbp+8]; this
0x18007a3aa  test    eax, eax
0x18007a3ac  jns     short loc_18007A3C3
0x18007a3ae  mov     r9d, eax; char *
0x18007a3b1  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007a3b8  mov     edx, 378h; void *
0x18007a3bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a3c3  mov     [rbp+var_48], 0
0x18007a3cb  mov     r8d, 1000h
0x18007a3d1  mov     rdx, rdi
0x18007a3d4  lea     rcx, [rbp+ProcessHandle]
0x18007a3d8  call    ?GetProcessHandleForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetProcessHandleForClientOfObject(IUnknown *,ulong)
0x18007a3dd  nop
0x18007a3de  mov     [rbp+TokenHandle], 0
0x18007a3e6  xor     edx, edx
0x18007a3e8  lea     rcx, [rbp+TokenHandle]
0x18007a3ec  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007a3f1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007a3f5  mov     edx, 8; DesiredAccess
0x18007a3fa  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18007a3fe  call    cs:__imp_OpenProcessToken
0x18007a404  test    eax, eax
0x18007a406  jnz     short loc_18007A473
0x18007a408  call    IsUMgrOpenProcessHandleForAccessPresent
0x18007a40d  test    al, al
0x18007a40f  jz      short loc_18007A473
0x18007a411  mov     [rbp+var_58], 0
0x18007a418  lea     rcx, [rbp+var_58]; this
0x18007a41c  call    ?GetCallingProcessId@UserAwareCallerIdentity@@YAJPEAK@Z; UserAwareCallerIdentity::GetCallingProcessId(ulong *)
0x18007a421  mov     rcx, [rbp+8]; this
0x18007a425  test    eax, eax
0x18007a427  jns     short loc_18007A43E
0x18007a429  mov     r9d, eax; char *
0x18007a42c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007a433  mov     edx, 385h; void *
0x18007a438  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a43e  xor     edx, edx
0x18007a440  lea     rcx, [rbp+TokenHandle]
0x18007a444  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007a449  lea     rdx, [rbp+TokenHandle]
0x18007a44d  mov     ecx, [rbp+var_58]
0x18007a450  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18007a456  mov     rcx, [rbp+8]; this
0x18007a45a  test    eax, eax
0x18007a45c  jns     short loc_18007A473
0x18007a45e  mov     r9d, eax; char *
0x18007a461  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007a468  mov     edx, 386h; void *
0x18007a46d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a473  lea     rdx, [rbp+var_48]
0x18007a477  mov     rcx, [rbp+TokenHandle]
0x18007a47b  call    cs:__imp_UMgrQueryUserContext
0x18007a481  mov     rcx, [rbp+8]; this
0x18007a485  test    eax, eax
0x18007a487  jns     short loc_18007A49E
0x18007a489  mov     r9d, eax; char *
0x18007a48c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007a493  mov     edx, 38Ah; void *
0x18007a498  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a49e  mov     rax, [rbp+var_48]
0x18007a4a2  cmp     [rbp+var_40], rax
0x18007a4a6  jz      short loc_18007A4F4
0x18007a4a8  mov     [rbp+var_10], 0
0x18007a4b0  mov     r9d, 4; unsigned int
0x18007a4b6  lea     r8d, [r9+1]; unsigned int
0x18007a4ba  lea     rdx, aUser; "user"
0x18007a4c1  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18007a4c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007a4ca  mov     rdx, [rbp+var_10]
0x18007a4ce  mov     ebx, 80070057h
0x18007a4d3  mov     ecx, ebx
0x18007a4d5  call    cs:__imp_RoOriginateError
0x18007a4db  mov     rcx, [rbp+8]; this
0x18007a4df  mov     r9d, ebx; char *
0x18007a4e2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18007a4e9  mov     edx, 38Fh; void *
0x18007a4ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a4f4  lea     rcx, [rbp+TokenHandle]
0x18007a4f8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007a4fd  nop
0x18007a4fe  lea     rcx, [rbp+ProcessHandle]
0x18007a502  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007a507  nop
0x18007a508  lea     rcx, [rbp+var_50]
0x18007a50c  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18007a511  nop
0x18007a512  lea     rcx, [rbp+var_30]
0x18007a516  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18007a51b  mov     rcx, [rbp+var_8]
0x18007a51f  xor     rcx, rsp; StackCookie
0x18007a522  call    __security_check_cookie
0x18007a527  lea     r11, [rsp+80h+var_s0]
0x18007a52f  mov     rbx, [r11+20h]
0x18007a533  mov     rdi, [r11+28h]
0x18007a537  mov     rsp, r11
0x18007a53a  pop     rbp
0x18007a53b  retn
```
