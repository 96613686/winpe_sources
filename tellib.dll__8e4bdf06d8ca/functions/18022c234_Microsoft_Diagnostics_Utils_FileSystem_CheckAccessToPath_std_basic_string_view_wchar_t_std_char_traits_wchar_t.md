# Microsoft::Diagnostics::Utils::FileSystem::CheckAccessToPath(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *,ulong,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *)

- ea: `0x18022c234`
- end: `0x18022c6a6`
- name: `?CheckAccessToPath@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAXKAEA_NPEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `1138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18022ca48`
- `0x18022d4bc`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180034d94`
- `0x180035698`
- `0x18006dd98`
- `0x18006f66c`
- `0x18007fae8`
- `0x180089d90`
- `0x18008bd1c`
- `0x18012de40`
- `0x18022c234`
- `0x18022c988`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022c4f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18022c4f5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18022c3c1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18022c3c1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18022c37d`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18022c37d`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18022c5a1`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18022c5a1`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18022c2f8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18022c2f8`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::CheckAccessToPath(
        _QWORD *a1,
        void *a2,
        __int64 a3,
        bool *a4,
        HANDLE *a5)
{
  const WCHAR *v7; // rcx
  DWORD NamedSecurityInfoW; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  const char *v12; // r9
  unsigned int LastError; // ebx
  int v14; // eax
  unsigned int v15; // edi
  const WCHAR *v16; // rcx
  HANDLE FileW; // rax
  const char *v18; // r9
  unsigned int v19; // ebx
  DWORD SecurityInfo; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-B8h]
  int ppsidGroupa; // [rsp+20h] [rbp-B8h]
  unsigned int ppsidGroupb; // [rsp+20h] [rbp-B8h]
  int ppsidGroupc; // [rsp+20h] [rbp-B8h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+40h] [rbp-98h] BYREF
  DWORD AccessMask[4]; // [rsp+50h] [rbp-88h] BYREF
  void *phNewToken; // [rsp+60h] [rbp-78h] BYREF
  PACL ppDacl; // [rsp+68h] [rbp-70h] BYREF
  PSID v32; // [rsp+70h] [rbp-68h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp-60h] BYREF
  LPCWSTR pObjectName[3]; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int64 v35; // [rsp+98h] [rbp-40h]
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    AccessMask[0] = 0x40000000;
    *a4 = 0;
    std::wstring::wstring((__int64)pObjectName, a1);
    ppSecurityDescriptor[0] = 0;
    ppsidOwner = 0;
    v32 = 0;
    ppDacl = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      ppSecurityDescriptor,
      0);
    v7 = (const WCHAR *)pObjectName;
    if ( v35 > 7 )
      v7 = pObjectName[0];
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           v7,
                           SE_FILE_OBJECT,
                           7u,
                           &ppsidOwner,
                           &v32,
                           &ppDacl,
                           0,
                           ppSecurityDescriptor);
    if ( NamedSecurityInfoW )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x647,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
             (const char *)NamedSecurityInfoW,
             ppsidGroup);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return v9;
    }
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    MapGenericMask(AccessMask, &GenericMapping);
    phNewToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phNewToken,
      0);
    if ( !DuplicateTokenEx(a2, 0xF01FFu, 0, SecurityIdentification, TokenImpersonation, &phNewToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x655,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                    v12);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return LastError;
    }
    v14 = Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(
            a4,
            AccessMask[0],
            ppSecurityDescriptor[0],
            phNewToken,
            &GenericMapping);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)(unsigned int)v14,
        ppsidGroupa);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return v15;
    }
    if ( !*a4 || !a5 )
      goto LABEL_11;
    v16 = (const WCHAR *)pObjectName;
    if ( v35 > 7 )
      v16 = pObjectName[0];
    FileW = CreateFileW(v16, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a5,
      FileW);
    if ( (((unsigned __int64)*a5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v19 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x672,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
              v18);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return v19;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      ppSecurityDescriptor,
      0);
    SecurityInfo = GetSecurityInfo(*a5, SE_FILE_OBJECT, 7u, &ppsidOwner, &v32, &ppDacl, 0, ppSecurityDescriptor);
    if ( SecurityInfo )
    {
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x67F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
              (const char *)SecurityInfo,
              ppsidGroupb);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return v21;
    }
    v22 = Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(
            a4,
            AccessMask[0],
            ppSecurityDescriptor[0],
            phNewToken,
            &GenericMapping);
    v23 = v22;
    if ( v22 >= 0 )
    {
LABEL_11:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
      (const char *)(unsigned int)v22,
      ppsidGroupc);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(ppSecurityDescriptor);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pObjectName);
    result = v23;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x68B,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18022c234  mov     r11, rsp
0x18022c237  push    rbx
0x18022c238  push    rsi
0x18022c239  push    rdi
0x18022c23a  sub     rsp, 0C0h
0x18022c241  mov     rax, cs:__security_cookie
0x18022c248  xor     rax, rsp
0x18022c24b  mov     [rsp+0D8h+var_28], rax
0x18022c253  mov     rbx, r9
0x18022c256  mov     rdi, rdx
0x18022c259  mov     rsi, [rsp+0D8h+arg_20]
0x18022c261  mov     [rsp+0D8h+AccessMask], 40000000h
0x18022c269  mov     byte ptr [r9], 0
0x18022c26d  mov     rdx, rcx
0x18022c270  lea     rcx, [r11-58h]
0x18022c274  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18022c279  mov     [rsp+0D8h+var_98], 0
0x18022c282  mov     [rsp+0D8h+ppsidOwner], 0
0x18022c28b  mov     [rsp+0D8h+var_68], 0
0x18022c294  mov     [rsp+0D8h+var_70], 0
0x18022c29d  xor     edx, edx
0x18022c29f  lea     rcx, [rsp+0D8h+var_98]
0x18022c2a4  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18022c2a9  lea     rcx, [rsp+0D8h+pObjectName]
0x18022c2b1  cmp     [rsp+0D8h+var_40], 7
0x18022c2ba  cmova   rcx, [rsp+0D8h+pObjectName]; pObjectName
0x18022c2c3  lea     rax, [rsp+0D8h+var_98]
0x18022c2c8  mov     [rsp+0D8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18022c2cd  mov     [rsp+0D8h+ppSacl], 0; ppSacl
0x18022c2d6  lea     rax, [rsp+0D8h+var_70]
0x18022c2db  mov     [rsp+0D8h+ppDacl], rax; ppDacl
0x18022c2e0  lea     rax, [rsp+0D8h+var_68]
0x18022c2e5  mov     [rsp+0D8h+ppsidGroup], rax; unsigned int
0x18022c2ea  lea     r9, [rsp+0D8h+ppsidOwner]; ppsidOwner
0x18022c2ef  mov     edx, 1; ObjectType
0x18022c2f4  lea     r8d, [rdx+6]; SecurityInfo
0x18022c2f8  call    cs:__imp_GetNamedSecurityInfoW
0x18022c2ff  nop     dword ptr [rax+rax+00h]
0x18022c304  test    eax, eax
0x18022c306  jz      short loc_18022C344
0x18022c308  mov     rcx, [rsp+0D8h]; this
0x18022c310  mov     r9d, eax; char *
0x18022c313  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c31a  mov     edx, 647h; void *
0x18022c31f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18022c324  mov     ebx, eax
0x18022c326  lea     rcx, [rsp+0D8h+var_98]
0x18022c32b  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c330  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c338  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c33d  mov     eax, ebx
0x18022c33f  jmp     loc_18022C68A
0x18022c344  mov     [rsp+0D8h+GenericMapping.GenericRead], 120089h
0x18022c34f  mov     [rsp+0D8h+GenericMapping.GenericWrite], 120116h
0x18022c35a  mov     [rsp+0D8h+GenericMapping.GenericExecute], 1200A0h
0x18022c365  mov     [rsp+0D8h+GenericMapping.GenericAll], 1F01FFh
0x18022c370  lea     rdx, [rsp+0D8h+GenericMapping]; GenericMapping
0x18022c378  lea     rcx, [rsp+0D8h+AccessMask]; AccessMask
0x18022c37d  call    cs:__imp_MapGenericMask
0x18022c384  nop     dword ptr [rax+rax+00h]
0x18022c389  mov     [rsp+0D8h+phNewToken], 0
0x18022c392  xor     edx, edx
0x18022c394  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c399  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18022c39e  lea     rax, [rsp+0D8h+phNewToken]
0x18022c3a3  mov     [rsp+0D8h+ppDacl], rax; phNewToken
0x18022c3a8  mov     dword ptr [rsp+0D8h+ppsidGroup], 2; TokenType
0x18022c3b0  mov     r9d, 1; ImpersonationLevel
0x18022c3b6  xor     r8d, r8d; lpTokenAttributes
0x18022c3b9  mov     edx, 0F01FFh; dwDesiredAccess
0x18022c3be  mov     rcx, rdi; hExistingToken
0x18022c3c1  call    cs:__imp_DuplicateTokenEx
0x18022c3c8  nop     dword ptr [rax+rax+00h]
0x18022c3cd  test    eax, eax
0x18022c3cf  jnz     short loc_18022C414
0x18022c3d1  mov     rcx, [rsp+0D8h]; this
0x18022c3d9  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c3e0  mov     edx, 655h; void *
0x18022c3e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18022c3ea  mov     ebx, eax
0x18022c3ec  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c3f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c3f6  lea     rcx, [rsp+0D8h+var_98]
0x18022c3fb  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c400  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c408  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c40d  mov     eax, ebx
0x18022c40f  jmp     loc_18022C68A
0x18022c414  lea     rax, [rsp+0D8h+GenericMapping]
0x18022c41c  mov     [rsp+0D8h+ppsidGroup], rax; int
0x18022c421  mov     r9, [rsp+0D8h+phNewToken]; void *
0x18022c426  mov     r8, [rsp+0D8h+var_98]; void *
0x18022c42b  mov     edx, [rsp+0D8h+AccessMask]; unsigned int
0x18022c42f  mov     rcx, rbx; bool *
0x18022c432  call    ?CheckTokenAccess@Os@Utils@Diagnostics@Microsoft@@SAJAEA_NKPEAX1AEAU_GENERIC_MAPPING@@@Z; Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(bool &,ulong,void *,void *,_GENERIC_MAPPING &)
0x18022c437  mov     edi, eax
0x18022c439  test    eax, eax
0x18022c43b  jns     short loc_18022C481
0x18022c43d  mov     rcx, [rsp+0D8h]; this
0x18022c445  mov     r9d, eax; char *
0x18022c448  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c44f  mov     edx, 65Ch; void *
0x18022c454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022c459  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c45e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c463  lea     rcx, [rsp+0D8h+var_98]
0x18022c468  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c46d  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c475  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c47a  mov     eax, edi
0x18022c47c  jmp     loc_18022C68A
0x18022c481  cmp     byte ptr [rbx], 0
0x18022c484  jnz     short loc_18022C4AE
0x18022c486  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c48b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c490  lea     rcx, [rsp+0D8h+var_98]
0x18022c495  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c49a  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c4a2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c4a7  xor     eax, eax
0x18022c4a9  jmp     loc_18022C68A
0x18022c4ae  test    rsi, rsi
0x18022c4b1  jz      loc_18022C661
0x18022c4b7  lea     rcx, [rsp+0D8h+pObjectName]
0x18022c4bf  cmp     [rsp+0D8h+var_40], 7
0x18022c4c8  cmova   rcx, [rsp+0D8h+pObjectName]; lpFileName
0x18022c4d1  mov     [rsp+0D8h+ppSacl], 0; hTemplateFile
0x18022c4da  mov     dword ptr [rsp+0D8h+ppDacl], 2000000h; dwFlagsAndAttributes
0x18022c4e2  mov     r8d, 3; dwShareMode
0x18022c4e8  mov     dword ptr [rsp+0D8h+ppsidGroup], r8d; dwCreationDisposition
0x18022c4ed  xor     r9d, r9d; lpSecurityAttributes
0x18022c4f0  mov     edx, 80000000h; dwDesiredAccess
0x18022c4f5  call    cs:__imp_CreateFileW
0x18022c4fc  nop     dword ptr [rax+rax+00h]
0x18022c501  mov     rdx, rax
0x18022c504  mov     rcx, rsi
0x18022c507  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18022c50c  mov     rax, [rsi]
0x18022c50f  inc     rax
0x18022c512  test    rax, 0FFFFFFFFFFFFFFFEh
0x18022c518  jnz     short loc_18022C55D
0x18022c51a  mov     rcx, [rsp+0D8h]; this
0x18022c522  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c529  mov     edx, 672h; void *
0x18022c52e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18022c533  mov     ebx, eax
0x18022c535  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c53a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c53f  lea     rcx, [rsp+0D8h+var_98]
0x18022c544  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c549  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c551  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c556  mov     eax, ebx
0x18022c558  jmp     loc_18022C68A
0x18022c55d  xor     edx, edx
0x18022c55f  lea     rcx, [rsp+0D8h+var_98]
0x18022c564  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18022c569  lea     rax, [rsp+0D8h+var_98]
0x18022c56e  mov     [rsp+0D8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18022c573  mov     [rsp+0D8h+ppSacl], 0; ppSacl
0x18022c57c  lea     rax, [rsp+0D8h+var_70]
0x18022c581  mov     [rsp+0D8h+ppDacl], rax; ppDacl
0x18022c586  lea     rax, [rsp+0D8h+var_68]
0x18022c58b  mov     [rsp+0D8h+ppsidGroup], rax; unsigned int
0x18022c590  lea     r9, [rsp+0D8h+ppsidOwner]; ppsidOwner
0x18022c595  mov     edx, 1; ObjectType
0x18022c59a  lea     r8d, [rdx+6]; SecurityInfo
0x18022c59e  mov     rcx, [rsi]; handle
0x18022c5a1  call    cs:__imp_GetSecurityInfo
0x18022c5a8  nop     dword ptr [rax+rax+00h]
0x18022c5ad  test    eax, eax
0x18022c5af  jz      short loc_18022C5F7
0x18022c5b1  mov     rcx, [rsp+0D8h]; this
0x18022c5b9  mov     r9d, eax; char *
0x18022c5bc  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c5c3  mov     edx, 67Fh; void *
0x18022c5c8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18022c5cd  mov     ebx, eax
0x18022c5cf  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c5d4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c5d9  lea     rcx, [rsp+0D8h+var_98]
0x18022c5de  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c5e3  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c5eb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c5f0  mov     eax, ebx
0x18022c5f2  jmp     loc_18022C68A
0x18022c5f7  lea     rax, [rsp+0D8h+GenericMapping]
0x18022c5ff  mov     [rsp+0D8h+ppsidGroup], rax; int
0x18022c604  mov     r9, [rsp+0D8h+phNewToken]; void *
0x18022c609  mov     r8, [rsp+0D8h+var_98]; void *
0x18022c60e  mov     edx, [rsp+0D8h+AccessMask]; unsigned int
0x18022c612  mov     rcx, rbx; bool *
0x18022c615  call    ?CheckTokenAccess@Os@Utils@Diagnostics@Microsoft@@SAJAEA_NKPEAX1AEAU_GENERIC_MAPPING@@@Z; Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(bool &,ulong,void *,void *,_GENERIC_MAPPING &)
0x18022c61a  mov     ebx, eax
0x18022c61c  test    eax, eax
0x18022c61e  jns     short loc_18022C661
0x18022c620  mov     rcx, [rsp+0D8h]; this
0x18022c628  mov     r9d, eax; char *
0x18022c62b  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18022c632  mov     edx, 685h; void *
0x18022c637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022c63c  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c641  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c646  lea     rcx, [rsp+0D8h+var_98]
0x18022c64b  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c650  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c658  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c65d  mov     eax, ebx
0x18022c65f  jmp     short loc_18022C68A
0x18022c661  lea     rcx, [rsp+0D8h+phNewToken]
0x18022c666  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022c66b  lea     rcx, [rsp+0D8h+var_98]
0x18022c670  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18022c675  lea     rcx, [rsp+0D8h+pObjectName]; this
0x18022c67d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022c682  xor     eax, eax
0x18022c684  jmp     short loc_18022C68A
0x18022c686  mov     eax, [rsp+0D8h+AccessMask]
0x18022c68a  mov     rcx, [rsp+0D8h+var_28]
0x18022c692  xor     rcx, rsp; StackCookie
0x18022c695  call    __security_check_cookie
0x18022c69a  add     rsp, 0C0h
0x18022c6a1  pop     rdi
0x18022c6a2  pop     rsi
0x18022c6a3  pop     rbx
0x18022c6a4  retn
```
