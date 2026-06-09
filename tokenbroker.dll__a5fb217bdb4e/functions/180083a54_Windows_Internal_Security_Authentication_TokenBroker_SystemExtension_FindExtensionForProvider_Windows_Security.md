# Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(Windows::Security::Credentials::IWebAccountProvider *,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension,std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>> &,std::optional<Windows::Internal::Security::Authentication::TokenBroker::ExtensionType>)

- ea: `0x180083a54`
- end: `0x180083da8`
- name: `?FindExtensionForProvider@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAV?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@V?$optional@W4ExtensionType@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `9`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180081890`
- `0x18009b7d0`
- `0x1800a6138`
- `0x1800bf168`
- `0x1800bffa8`
- `0x1800e27f8`
- `0x180102ab8`
- `0x180103b70`
- `0x1801065e4`

## callees

- `0x18000bd40`
- `0x18002d940`
- `0x180031cf8`
- `0x1800372d0`
- `0x18004ba4c`
- `0x18004e750`
- `0x180053718`
- `0x180056ea4`
- `0x18005d118`
- `0x18007cde4`
- `0x1800827d4`
- `0x180083a54`
- `0x18008e690`
- `0x18009b8bc`
- `0x18009c614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083c5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083d18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083d6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083c5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083d18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180083d6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083bbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083c8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083d9b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180083b4b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180083b4b`

## string_xrefs

- `0x180083ab7`: `onecore\ds\security\tokenbroker\sysext\lib\sysext.cpp`
- `0x180083b83`: `onecore\ds\security\tokenbroker\sysext\lib\sysext.cpp`
- `0x180083cee`: `onecore\ds\security\tokenbroker\sysext\lib\sysext.cpp`
- `0x180083b3d`: `Software\Microsoft\Windows NT\CurrentVersion\TokenBroker\Extensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(
        __int64 (__fastcall ***a1)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  int v3; // edi
  int v5; // eax
  unsigned int ExtensionRegistrations; // ebx
  LSTATUS v8; // eax
  bool IsSystemProvider; // r15
  __int64 v10; // r12
  __int64 v11; // r14
  HSTRING v12; // rbx
  PSRWLOCK v13; // rsi
  const unsigned __int16 *v14; // rdx
  int ExtensionWithId; // eax
  unsigned int v16; // edi
  HKEY phkResult; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v18; // [rsp+28h] [rbp-58h] BYREF
  HSTRING v19; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-40h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-38h]
  HSTRING v23[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  char v25; // [rsp+D4h] [rbp+54h]

  v25 = BYTE4(a3);
  v3 = a3;
  v19 = 0;
  v18 = 0;
  string = 0;
  v5 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
         a1,
         &v19,
         &v18,
         &string);
  ExtensionRegistrations = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\sysext\\lib\\sysext.cpp",
      (const char *)(unsigned int)v5,
      (int)phkResult);
LABEL_3:
    if ( string )
      WindowsDeleteString(string);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v19 )
      WindowsDeleteString(v19);
    return ExtensionRegistrations;
  }
  if ( !g_initialized )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &g_registrationsLock);
    if ( !g_initialized )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v8 = RegOpenKeyW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\TokenBroker\\Extensions",
             &phkResult);
      ExtensionRegistrations = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          ExtensionRegistrations = (unsigned __int16)v8 | 0x80070000;
      }
      else
      {
        ExtensionRegistrations = Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration::LoadExtensionRegistrations(phkResult);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      if ( (ExtensionRegistrations & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F6,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\sysext\\lib\\sysext.cpp",
          (const char *)ExtensionRegistrations,
          (int)phkResult);
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        goto LABEL_3;
      }
      g_initialized = 1;
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  IsSystemProvider = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider((struct Windows::Security::Credentials::IWebAccountProvider *)a1);
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&phkResult, &g_registrationsLock);
  v10 = *((_QWORD *)&g_registrations + 1);
  v11 = g_registrations;
  v12 = string;
  while ( 1 )
  {
    if ( v11 == v10 )
      goto LABEL_34;
    std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
      &SRWLock,
      v11);
    v13 = SRWLock;
    if ( Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration::IsProviderIdMatch(
           (Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration *)SRWLock,
           v12)
      && (!v25 || LODWORD(v13->Ptr) == v3) )
    {
      break;
    }
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    v11 += 16;
  }
  if ( IsSystemProvider && (HIDWORD(v13[8].Ptr) & (__int64)v13[8].Ptr) == 0 )
  {
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
LABEL_34:
    if ( phkResult )
      ReleaseSRWLockShared((PSRWLOCK)phkResult);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v19 )
      WindowsDeleteString(v19);
    return 2147942402LL;
  }
  v14 = (const unsigned __int16 *)&v13[4];
  if ( v13[7].Ptr > (PVOID)7 )
    v14 = *(const unsigned __int16 **)v14;
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v23, v14);
  ExtensionWithId = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionWithId(v23[0]);
  v16 = ExtensionWithId;
  if ( ExtensionWithId >= 0 )
  {
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    if ( phkResult )
      ReleaseSRWLockShared((PSRWLOCK)phkResult);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v19 )
      WindowsDeleteString(v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\sysext\\lib\\sysext.cpp",
      (const char *)(unsigned int)ExtensionWithId,
      (int)phkResult);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    if ( phkResult )
      ReleaseSRWLockShared((PSRWLOCK)phkResult);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v19 )
      WindowsDeleteString(v19);
    return v16;
  }
}

```

## disassembly

```asm
0x180083a54  mov     [rsp-38h+arg_18], rbx
0x180083a59  mov     [rsp-38h+arg_10], r8
0x180083a5e  push    rbp
0x180083a5f  push    rsi
0x180083a60  push    rdi
0x180083a61  push    r12
0x180083a63  push    r13
0x180083a65  push    r14
0x180083a67  push    r15
0x180083a69  mov     rbp, rsp
0x180083a6c  sub     rsp, 80h
0x180083a73  mov     rax, cs:__security_cookie
0x180083a7a  xor     rax, rsp
0x180083a7d  mov     [rbp+var_10], rax
0x180083a81  mov     rdi, r8
0x180083a84  mov     r13, rdx
0x180083a87  mov     rsi, rcx
0x180083a8a  xor     r14d, r14d
0x180083a8d  mov     [rbp+var_50], r14
0x180083a91  mov     [rbp+var_58], r14
0x180083a95  mov     [rbp+string], r14
0x180083a99  lea     r9, [rbp+string]; struct Windows::Internal::String *
0x180083a9d  lea     r8, [rbp+var_58]; struct Windows::Internal::String *
0x180083aa1  lea     rdx, [rbp+var_50]; struct Windows::Internal::String *
0x180083aa5  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x180083aaa  mov     ebx, eax
0x180083aac  test    eax, eax
0x180083aae  jns     short loc_180083AFF
0x180083ab0  mov     rcx, [rbp+38h]; this
0x180083ab4  mov     r9d, eax; char *
0x180083ab7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\tokenbroker\\sys"...
0x180083abe  mov     edx, 1EFh; void *
0x180083ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ac8  nop
0x180083ac9  mov     rcx, [rbp+string]; string
0x180083acd  test    rcx, rcx
0x180083ad0  jz      short loc_180083AD9
0x180083ad2  call    cs:__imp_WindowsDeleteString
0x180083ad8  nop
0x180083ad9  mov     rcx, [rbp+var_58]; string
0x180083add  test    rcx, rcx
0x180083ae0  jz      short loc_180083AE9
0x180083ae2  call    cs:__imp_WindowsDeleteString
0x180083ae8  nop
0x180083ae9  mov     rcx, [rbp+var_50]; string
0x180083aed  test    rcx, rcx
0x180083af0  jz      short loc_180083AF8
0x180083af2  call    cs:__imp_WindowsDeleteString
0x180083af8  mov     eax, ebx
0x180083afa  jmp     loc_180083C97
0x180083aff  cmp     cs:?g_initialized@@3EA, r14b; uchar g_initialized
0x180083b06  jnz     loc_180083BC3
0x180083b0c  lea     rdx, ?g_registrationsLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock g_registrationsLock
0x180083b13  lea     rcx, [rbp+SRWLock]
0x180083b17  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180083b1c  nop
0x180083b1d  cmp     cs:?g_initialized@@3EA, r14b; uchar g_initialized
0x180083b24  jnz     loc_180083BB4
0x180083b2a  mov     [rbp+phkResult], r14
0x180083b2e  xor     edx, edx
0x180083b30  lea     rcx, [rbp+phkResult]
0x180083b34  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180083b39  lea     r8, [rbp+phkResult]; phkResult
0x180083b3d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x180083b44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083b4b  call    cs:__imp_RegOpenKeyW
0x180083b51  mov     ebx, eax
0x180083b53  test    eax, eax
0x180083b55  jnz     short loc_180083B64
0x180083b57  mov     rcx, [rbp+phkResult]; hKey
0x180083b5b  call    ?LoadExtensionRegistrations@SystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUHKEY__@@AEAV?$vector@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration::LoadExtensionRegistrations(HKEY__ *,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration>> &)
0x180083b60  mov     ebx, eax
0x180083b62  jmp     short loc_180083B6F
0x180083b64  jle     short loc_180083B6F
0x180083b66  movzx   ebx, ax
0x180083b69  or      ebx, 80070000h
0x180083b6f  lea     rcx, [rbp+phkResult]
0x180083b73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180083b78  test    ebx, ebx
0x180083b7a  jns     short loc_180083BAD
0x180083b7c  mov     rcx, [rbp+38h]; this
0x180083b80  mov     r9d, ebx; char *
0x180083b83  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\tokenbroker\\sys"...
0x180083b8a  mov     edx, 1F6h; void *
0x180083b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083b94  nop
0x180083b95  mov     rcx, [rbp+SRWLock]; SRWLock
0x180083b99  test    rcx, rcx
0x180083b9c  jz      loc_180083AC9
0x180083ba2  call    cs:__imp_ReleaseSRWLockExclusive
0x180083ba8  jmp     loc_180083AC9
0x180083bad  mov     cs:?g_initialized@@3EA, 1; uchar g_initialized
0x180083bb4  mov     rcx, [rbp+SRWLock]; SRWLock
0x180083bb8  test    rcx, rcx
0x180083bbb  jz      short loc_180083BC3
0x180083bbd  call    cs:__imp_ReleaseSRWLockExclusive
0x180083bc3  mov     rcx, rsi; struct Windows::Security::Credentials::IWebAccountProvider *
0x180083bc6  call    ?IsSystemProvider@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA_NPEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider(Windows::Security::Credentials::IWebAccountProvider *)
0x180083bcb  mov     r15b, al
0x180083bce  lea     rdx, ?g_registrationsLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock g_registrationsLock
0x180083bd5  lea     rcx, [rbp+phkResult]
0x180083bd9  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180083bde  nop
0x180083bdf  mov     r14, qword ptr cs:?g_registrations@@3V?$vector@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@A; std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration>> g_registrations
0x180083be6  mov     r12, qword ptr cs:?g_registrations@@3V?$vector@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VSystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@A+8; std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration>> g_registrations
0x180083bed  mov     rbx, [rbp+string]
0x180083bf1  cmp     r14, r12
0x180083bf4  jz      short loc_180083C54
0x180083bf6  mov     rdx, r14
0x180083bf9  lea     rcx, [rbp+SRWLock]
0x180083bfd  call    ??0?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext> const &)
0x180083c02  nop
0x180083c03  mov     rdx, rbx; HSTRING
0x180083c06  mov     rsi, [rbp+SRWLock]
0x180083c0a  mov     rcx, rsi; this
0x180083c0d  call    ?IsProviderIdMatch@SystemExtensionRegistration@TokenBroker@Authentication@Security@Internal@Windows@@QEBA_NPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtensionRegistration::IsProviderIdMatch(HSTRING__ *)
0x180083c12  test    al, al
0x180083c14  jz      short loc_180083C20
0x180083c16  cmp     byte ptr [rbp+arg_10+4], 0
0x180083c1a  jz      short loc_180083C34
0x180083c1c  cmp     [rsi], edi
0x180083c1e  jz      short loc_180083C34
0x180083c20  mov     rcx, [rbp+var_38]; this
0x180083c24  test    rcx, rcx
0x180083c27  jz      short loc_180083C2E
0x180083c29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083c2e  add     r14, 10h
0x180083c32  jmp     short loc_180083BF1
0x180083c34  test    r15b, r15b
0x180083c37  jz      loc_180083CBE
0x180083c3d  mov     eax, [rsi+44h]
0x180083c40  test    [rsi+40h], eax
0x180083c43  jnz     short loc_180083CBE
0x180083c45  mov     rcx, [rbp+var_38]; this
0x180083c49  test    rcx, rcx
0x180083c4c  jz      short loc_180083C54
0x180083c4e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083c53  nop
0x180083c54  mov     rcx, [rbp+phkResult]; SRWLock
0x180083c58  test    rcx, rcx
0x180083c5b  jz      short loc_180083C64
0x180083c5d  call    cs:__imp_ReleaseSRWLockShared
0x180083c63  nop
0x180083c64  test    rbx, rbx
0x180083c67  jz      short loc_180083C73
0x180083c69  mov     rcx, rbx; string
0x180083c6c  call    cs:__imp_WindowsDeleteString
0x180083c72  nop
0x180083c73  mov     rcx, [rbp+var_58]; string
0x180083c77  test    rcx, rcx
0x180083c7a  jz      short loc_180083C83
0x180083c7c  call    cs:__imp_WindowsDeleteString
0x180083c82  nop
0x180083c83  mov     rcx, [rbp+var_50]; string
0x180083c87  test    rcx, rcx
0x180083c8a  jz      short loc_180083C92
0x180083c8c  call    cs:__imp_WindowsDeleteString
0x180083c92  mov     eax, 80070002h
0x180083c97  mov     rcx, [rbp+var_10]
0x180083c9b  xor     rcx, rsp; StackCookie
0x180083c9e  call    __security_check_cookie
0x180083ca3  mov     rbx, [rsp+80h+arg_18]
0x180083cab  add     rsp, 80h
0x180083cb2  pop     r15
0x180083cb4  pop     r14
0x180083cb6  pop     r13
0x180083cb8  pop     r12
0x180083cba  pop     rdi
0x180083cbb  pop     rsi
0x180083cbc  pop     rbp
0x180083cbd  retn
0x180083cbe  lea     rdx, [rsi+20h]
0x180083cc2  cmp     qword ptr [rdx+18h], 7
0x180083cc7  jbe     short loc_180083CCC
0x180083cc9  mov     rdx, [rdx]; unsigned __int16 *
0x180083ccc  lea     rcx, [rbp+var_30]; this
0x180083cd0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180083cd5  mov     rdx, r13
0x180083cd8  mov     rcx, [rbp+var_30]
0x180083cdc  call    ?FindExtensionWithId@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAV?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionWithId(HSTRING__ *,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension> &)
0x180083ce1  mov     edi, eax
0x180083ce3  test    eax, eax
0x180083ce5  jns     short loc_180083D54
0x180083ce7  mov     rcx, [rbp+38h]; this
0x180083ceb  mov     r9d, eax; char *
0x180083cee  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\tokenbroker\\sys"...
0x180083cf5  mov     edx, 207h; void *
0x180083cfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083cff  nop
0x180083d00  mov     rcx, [rbp+var_38]; this
0x180083d04  test    rcx, rcx
0x180083d07  jz      short loc_180083D0F
0x180083d09  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083d0e  nop
0x180083d0f  mov     rcx, [rbp+phkResult]; SRWLock
0x180083d13  test    rcx, rcx
0x180083d16  jz      short loc_180083D1F
0x180083d18  call    cs:__imp_ReleaseSRWLockShared
0x180083d1e  nop
0x180083d1f  test    rbx, rbx
0x180083d22  jz      short loc_180083D2E
0x180083d24  mov     rcx, rbx; string
0x180083d27  call    cs:__imp_WindowsDeleteString
0x180083d2d  nop
0x180083d2e  mov     rcx, [rbp+var_58]; string
0x180083d32  test    rcx, rcx
0x180083d35  jz      short loc_180083D3E
0x180083d37  call    cs:__imp_WindowsDeleteString
0x180083d3d  nop
0x180083d3e  mov     rcx, [rbp+var_50]; string
0x180083d42  test    rcx, rcx
0x180083d45  jz      short loc_180083D4D
0x180083d47  call    cs:__imp_WindowsDeleteString
0x180083d4d  mov     eax, edi
0x180083d4f  jmp     loc_180083C97
0x180083d54  mov     rcx, [rbp+var_38]; this
0x180083d58  test    rcx, rcx
0x180083d5b  jz      short loc_180083D63
0x180083d5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083d62  nop
0x180083d63  mov     rcx, [rbp+phkResult]; SRWLock
0x180083d67  test    rcx, rcx
0x180083d6a  jz      short loc_180083D73
0x180083d6c  call    cs:__imp_ReleaseSRWLockShared
0x180083d72  nop
0x180083d73  test    rbx, rbx
0x180083d76  jz      short loc_180083D82
0x180083d78  mov     rcx, rbx; string
0x180083d7b  call    cs:__imp_WindowsDeleteString
0x180083d81  nop
0x180083d82  mov     rcx, [rbp+var_58]; string
0x180083d86  test    rcx, rcx
0x180083d89  jz      short loc_180083D92
0x180083d8b  call    cs:__imp_WindowsDeleteString
0x180083d91  nop
0x180083d92  mov     rcx, [rbp+var_50]; string
0x180083d96  test    rcx, rcx
0x180083d99  jz      short loc_180083DA1
0x180083d9b  call    cs:__imp_WindowsDeleteString
0x180083da1  xor     eax, eax
0x180083da3  jmp     loc_180083C97
```
