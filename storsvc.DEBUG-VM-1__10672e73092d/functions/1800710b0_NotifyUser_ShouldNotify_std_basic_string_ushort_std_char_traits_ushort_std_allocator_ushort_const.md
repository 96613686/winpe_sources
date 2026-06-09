# NotifyUser::ShouldNotify(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800710b0`
- end: `0x18007124e`
- name: `?ShouldNotify@NotifyUser@@QEAAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006fd7c`

## callees

- `0x18000d030`
- `0x180014a00`
- `0x180017500`
- `0x180019d4c`
- `0x18001c5ec`
- `0x18001dcf4`
- `0x180057218`
- `0x1800702f4`
- `0x1800705f4`
- `0x1800710b0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800711eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800711eb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800711ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800711ab`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007119b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007119b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800711c3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800711c3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180071167`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180071167`

## string_xrefs

- `0x1800711f3`: `UserImpersonationFailed`

## pseudocode

```c
char __fastcall NotifyUser::ShouldNotify(_QWORD *a1, __int64 a2)
{
  char ShouldNotify; // bl
  DWORD LastError; // ebx
  __int64 v7; // rax
  HANDLE Token; // [rsp+30h] [rbp-9h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-1h] BYREF
  __int64 v10; // [rsp+40h] [rbp+7h] BYREF
  char v11; // [rsp+49h] [rbp+10h]
  __int64 v12; // [rsp+50h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+27h] BYREF
  __int64 v14; // [rsp+78h] [rbp+3Fh]

  v12 = 0;
  hExistingToken = 0;
  Token = 0;
  v10 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
              v14,
              &v10) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 136LL))(v10, *a1, &v12) >= 0
    && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hExistingToken,
          0),
        (int)UMgrQueryUserToken(v12, &hExistingToken) >= 0)
    && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &Token,
          0),
        DuplicateTokenEx(hExistingToken, 4u, 0, SecurityImpersonation, TokenImpersonation, &Token))
    && SetThreadToken(0, Token) )
  {
    v11 = 1;
    ShouldNotify = RegistryHelpers::ShouldNotify(a2);
    RevertToSelf();
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return ShouldNotify;
  }
  else
  {
    LastError = GetLastError();
    v7 = std::string::string(&hstringHeader, "UserImpersonationFailed");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v7, LastError);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return 0;
  }
}

```

## disassembly

```asm
0x1800710b0  mov     [rsp-8+arg_10], rbx
0x1800710b5  mov     [rsp-8+arg_18], rdi
0x1800710ba  push    rbp
0x1800710bb  lea     rbp, [rsp-57h]
0x1800710c0  sub     rsp, 90h
0x1800710c7  mov     rax, cs:__security_cookie
0x1800710ce  xor     rax, rsp
0x1800710d1  mov     [rbp+57h+var_10], rax
0x1800710d5  mov     rbx, rdx
0x1800710d8  mov     rdi, rcx
0x1800710db  mov     [rbp+57h+var_40], 0
0x1800710e3  mov     [rbp+57h+hExistingToken], 0
0x1800710eb  mov     [rbp+57h+Token], 0
0x1800710f3  mov     [rbp+57h+var_50], 0
0x1800710fb  mov     [rbp+57h+var_18], 0
0x180071103  mov     r9d, 23h ; '#'; unsigned int
0x180071109  lea     r8d, [r9+1]; unsigned int
0x18007110d  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180071114  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180071118  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007111d  lea     rdx, [rbp+57h+var_50]
0x180071121  mov     rcx, [rbp+57h+var_18]
0x180071125  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18007112a  test    eax, eax
0x18007112c  js      loc_1800711EB
0x180071132  mov     rcx, [rbp+57h+var_50]
0x180071136  mov     rax, [rcx]
0x180071139  lea     r8, [rbp+57h+var_40]
0x18007113d  mov     rdx, [rdi]
0x180071140  mov     rax, [rax+88h]
0x180071147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007114c  test    eax, eax
0x18007114e  js      loc_1800711EB
0x180071154  xor     edx, edx
0x180071156  lea     rcx, [rbp+57h+hExistingToken]
0x18007115a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007115f  lea     rdx, [rbp+57h+hExistingToken]
0x180071163  mov     rcx, [rbp+57h+var_40]
0x180071167  call    cs:__imp_UMgrQueryUserToken
0x18007116d  test    eax, eax
0x18007116f  js      short loc_1800711EB
0x180071171  xor     edx, edx
0x180071173  lea     rcx, [rbp+57h+Token]
0x180071177  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007117c  lea     rax, [rbp+57h+Token]
0x180071180  mov     [rsp+90h+phNewToken], rax; phNewToken
0x180071185  mov     r9d, 2; ImpersonationLevel
0x18007118b  mov     [rsp+90h+TokenType], r9d; TokenType
0x180071190  xor     r8d, r8d; lpTokenAttributes
0x180071193  lea     edx, [r9+2]; dwDesiredAccess
0x180071197  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x18007119b  call    cs:__imp_DuplicateTokenEx
0x1800711a1  test    eax, eax
0x1800711a3  jz      short loc_1800711EB
0x1800711a5  mov     rdx, [rbp+57h+Token]; Token
0x1800711a9  xor     ecx, ecx; Thread
0x1800711ab  call    cs:__imp_SetThreadToken
0x1800711b1  test    eax, eax
0x1800711b3  jz      short loc_1800711EB
0x1800711b5  mov     [rbp+57h+var_47], 1
0x1800711b9  mov     rcx, rbx
0x1800711bc  call    ?ShouldNotify@RegistryHelpers@@SAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryHelpers::ShouldNotify(std::wstring const &)
0x1800711c1  mov     bl, al
0x1800711c3  call    cs:__imp_RevertToSelf
0x1800711c9  nop
0x1800711ca  lea     rcx, [rbp+57h+var_50]
0x1800711ce  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800711d3  nop
0x1800711d4  lea     rcx, [rbp+57h+Token]
0x1800711d8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800711dd  nop
0x1800711de  lea     rcx, [rbp+57h+hExistingToken]
0x1800711e2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800711e7  mov     al, bl
0x1800711e9  jmp     short loc_18007122D
0x1800711eb  call    cs:__imp_GetLastError
0x1800711f1  mov     ebx, eax
0x1800711f3  lea     rdx, aUserimpersonat; "UserImpersonationFailed"
0x1800711fa  lea     rcx, [rbp+57h+hstringHeader]
0x1800711fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180071203  mov     edx, ebx
0x180071205  mov     rcx, rax
0x180071208  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x18007120d  nop
0x18007120e  lea     rcx, [rbp+57h+var_50]
0x180071212  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071217  nop
0x180071218  lea     rcx, [rbp+57h+Token]
0x18007121c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071221  nop
0x180071222  lea     rcx, [rbp+57h+hExistingToken]
0x180071226  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007122b  xor     al, al
0x18007122d  mov     rcx, [rbp+57h+var_10]
0x180071231  xor     rcx, rsp; StackCookie
0x180071234  call    __security_check_cookie
0x180071239  lea     r11, [rsp+90h+var_s0]
0x180071241  mov     rbx, [r11+20h]
0x180071245  mov     rdi, [r11+28h]
0x180071249  mov     rsp, r11
0x18007124c  pop     rbp
0x18007124d  retn
```
