# Microsoft::Diagnostics::UtcApiManager::IsMultiUserAwareProcess(bool &)

- ea: `0x1801df0e0`
- end: `0x1801df3bb`
- name: `?IsMultiUserAwareProcess@UtcApiManager@Diagnostics@Microsoft@@AEAAJAEA_N@Z`
- size: `731`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800eaaec`

## callees

- `0x18001cf30`
- `0x18001d160`
- `0x180026ecc`
- `0x180032718`
- `0x18003fd8c`
- `0x1800495cc`
- `0x18008bd1c`
- `0x180101300`
- `0x18012de40`
- `0x1801300b0`
- `0x1801d14c4`
- `0x1801d15b0`
- `0x1801dd5f8`
- `0x1801df0e0`
- `0x1801e49a4`
- `0x1802b4e44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801df15c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801df1bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801df15c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801df1bf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801df224`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801df224`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x1801df285`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x1801df285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1801df2fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1801df2fb`

## string_xrefs

- `0x1801df11a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801df240`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801df29e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801df336`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801df31d`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1801df1b8`: `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2.dll`
- `0x1801df155`: `api-ms-win-appmodel-runtime-internal-l1-1-2.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::IsMultiUserAwareProcess(
        Microsoft::Diagnostics::UtcApiManager *this,
        bool *a2)
{
  __int64 v3; // rdx
  unsigned int RpcCallerPid; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rax
  Microsoft::Diagnostics::ApiServer *v7; // rcx
  HANDLE v8; // rbx
  const char *v9; // r9
  WCHAR *v10; // r8
  LONG v11; // eax
  PWSTR *v12; // rax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  const wchar_t *v15; // rdx
  int IsEffectiveSupportedUsersMultiple; // eax
  UINT32 packageFullNameLength; // [rsp+20h] [rbp-29h] BYREF
  __int64 v19; // [rsp+28h] [rbp-21h] BYREF
  DWORD dwProcessId[4]; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-9h] BYREF
  __int64 v22; // [rsp+48h] [rbp-1h] BYREF
  char v23; // [rsp+50h] [rbp+7h]
  PWSTR packageFullName[2]; // [rsp+58h] [rbp+Fh] BYREF
  UINT32 v25; // [rsp+68h] [rbp+1Fh]
  unsigned __int64 v26; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  if ( (unsigned __int8)IsGetPackageFullNamePresent(this) )
  {
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(dwProcessId, &unk_18043B978);
    if ( !byte_18043B970 )
    {
      Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-internal-l1-1-2.dll", 0, 0x800u);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &qword_18043BB08,
        Library);
      byte_18043B970 = 1;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(dwProcessId);
    if ( !qword_18043BB08 )
    {
      v3 = 6400;
      goto LABEL_3;
    }
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(dwProcessId, &unk_18043B9C8);
    if ( !byte_18043B971 )
    {
      v6 = LoadLibraryExW(L"ext-ms-onecore-appmodel-staterepository-cache-l1-1-2.dll", 0, 0x800u);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &qword_18043BB10,
        v6);
      byte_18043B971 = 1;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(dwProcessId);
    if ( !qword_18043BB10 )
    {
      v3 = 6401;
      goto LABEL_3;
    }
    dwProcessId[0] = 0;
    RpcCallerPid = Microsoft::Diagnostics::ApiServer::GetRpcCallerPid(v7, dwProcessId);
    if ( (RpcCallerPid & 0x80000000) != 0 )
    {
      v3 = 6404;
      goto LABEL_4;
    }
    v8 = OpenProcess(0x1000u, 0, dwProcessId[0]);
    *(_QWORD *)dwProcessId = v8;
    if ( !v8 )
    {
      RpcCallerPid = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x1907,
                       (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                       v9);
LABEL_34:
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(dwProcessId);
      return RpcCallerPid;
    }
    std::wstring::wstring(packageFullName, 128, 0);
    packageFullNameLength = v25;
    v10 = (WCHAR *)packageFullName;
    if ( v26 > 7 )
      v10 = packageFullName[0];
    v11 = GetPackageFullName(v8, &packageFullNameLength, v10);
    RpcCallerPid = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x190C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v11,
        packageFullNameLength);
LABEL_21:
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)packageFullName);
      goto LABEL_34;
    }
    v12 = packageFullName;
    if ( v26 > 7 )
      v12 = (PWSTR *)packageFullName[0];
    if ( *(_WORD *)v12 )
    {
      std::wstring::resize(packageFullName, packageFullNameLength);
      v19 = 0;
      v21 = &v19;
      v22 = 0;
      v23 = 1;
      RpcCallerPid = SRCacheManager_Open(0, &v22);
      wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v21);
      if ( (RpcCallerPid & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
          (const char *)RpcCallerPid,
          packageFullNameLength);
        v13 = RpcCallerPid;
        v14 = 6419;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)v13,
          packageFullNameLength);
        wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v19, 0);
        goto LABEL_21;
      }
      v15 = (const wchar_t *)packageFullName;
      if ( v26 > 7 )
        v15 = packageFullName[0];
      IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                            (struct StateRepository::Cache::Manager_NoThrow *)&v19,
                                            v15,
                                            a2);
      RpcCallerPid = IsEffectiveSupportedUsersMultiple;
      if ( IsEffectiveSupportedUsersMultiple < 0 )
      {
        v13 = (unsigned int)IsEffectiveSupportedUsersMultiple;
        v14 = 6424;
        goto LABEL_27;
      }
      wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v19, 0);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)packageFullName);
    RpcCallerPid = 0;
    goto LABEL_34;
  }
  v3 = 6399;
LABEL_3:
  RpcCallerPid = -2147024846;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
    (const char *)RpcCallerPid,
    packageFullNameLength);
  return RpcCallerPid;
}

```

## disassembly

```asm
0x1801df0e0  push    rbp
0x1801df0e2  push    rbx
0x1801df0e3  push    rsi
0x1801df0e4  push    rdi
0x1801df0e5  lea     rbp, [rsp-3Fh]
0x1801df0ea  sub     rsp, 88h
0x1801df0f1  mov     rax, cs:__security_cookie
0x1801df0f8  xor     rax, rsp
0x1801df0fb  mov     [rbp+57h+var_28], rax
0x1801df0ff  mov     rdi, rdx
0x1801df102  xor     esi, esi
0x1801df104  mov     [rdx], sil
0x1801df107  call    IsGetPackageFullNamePresent
0x1801df10c  test    al, al
0x1801df10e  jnz     short loc_1801DF132
0x1801df110  mov     edx, 18FFh; void *
0x1801df115  mov     ebx, 80070032h
0x1801df11a  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801df121  mov     r9d, ebx; char *
0x1801df124  mov     rcx, [rbp+5Fh]; this
0x1801df128  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801df12d  jmp     loc_1801DF3A0
0x1801df132  lea     rdx, unk_18043B978
0x1801df139  lea     rcx, [rbp+57h+dwProcessId]
0x1801df13d  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801df142  mov     ebx, 800h
0x1801df147  cmp     cs:byte_18043B970, sil
0x1801df14e  jnz     short loc_1801DF17E
0x1801df150  mov     r8d, ebx; dwFlags
0x1801df153  xor     edx, edx; hFile
0x1801df155  lea     rcx, aApiMsWinAppmod_0; "api-ms-win-appmodel-runtime-internal-l1"...
0x1801df15c  call    cs:__imp_LoadLibraryExW
0x1801df163  nop     dword ptr [rax+rax+00h]
0x1801df168  mov     rdx, rax
0x1801df16b  lea     rcx, qword_18043BB08
0x1801df172  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1801df177  mov     cs:byte_18043B970, 1
0x1801df17e  lea     rcx, [rbp+57h+dwProcessId]
0x1801df182  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801df187  cmp     cs:qword_18043BB08, rsi
0x1801df18e  jnz     short loc_1801DF19A
0x1801df190  mov     edx, 1900h
0x1801df195  jmp     loc_1801DF115
0x1801df19a  lea     rdx, unk_18043B9C8
0x1801df1a1  lea     rcx, [rbp+57h+dwProcessId]
0x1801df1a5  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801df1aa  cmp     cs:byte_18043B971, sil
0x1801df1b1  jnz     short loc_1801DF1E1
0x1801df1b3  mov     r8d, ebx; dwFlags
0x1801df1b6  xor     edx, edx; hFile
0x1801df1b8  lea     rcx, aExtMsOnecoreAp_1; "ext-ms-onecore-appmodel-staterepository"...
0x1801df1bf  call    cs:__imp_LoadLibraryExW
0x1801df1c6  nop     dword ptr [rax+rax+00h]
0x1801df1cb  mov     rdx, rax
0x1801df1ce  lea     rcx, qword_18043BB10
0x1801df1d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1801df1da  mov     cs:byte_18043B971, 1
0x1801df1e1  lea     rcx, [rbp+57h+dwProcessId]
0x1801df1e5  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801df1ea  cmp     cs:qword_18043BB10, rsi
0x1801df1f1  jnz     short loc_1801DF1FD
0x1801df1f3  mov     edx, 1901h
0x1801df1f8  jmp     loc_1801DF115
0x1801df1fd  mov     [rbp+57h+dwProcessId], esi
0x1801df200  lea     rdx, [rbp+57h+dwProcessId]; unsigned int *
0x1801df204  call    ?GetRpcCallerPid@ApiServer@Diagnostics@Microsoft@@IEAAJAEAK@Z; Microsoft::Diagnostics::ApiServer::GetRpcCallerPid(ulong &)
0x1801df209  mov     ebx, eax
0x1801df20b  test    eax, eax
0x1801df20d  jns     short loc_1801DF219
0x1801df20f  mov     edx, 1904h
0x1801df214  jmp     loc_1801DF11A
0x1801df219  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1801df21d  xor     edx, edx; bInheritHandle
0x1801df21f  mov     ecx, 1000h; dwDesiredAccess
0x1801df224  call    cs:__imp_OpenProcess
0x1801df22b  nop     dword ptr [rax+rax+00h]
0x1801df230  mov     rbx, rax
0x1801df233  mov     qword ptr [rbp+57h+dwProcessId], rax
0x1801df237  test    rax, rax
0x1801df23a  jnz     short loc_1801DF258
0x1801df23c  mov     rcx, [rbp+5Fh]; this
0x1801df240  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801df247  mov     edx, 1907h; void *
0x1801df24c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801df251  mov     ebx, eax
0x1801df253  jmp     loc_1801DF397
0x1801df258  xor     r8d, r8d
0x1801df25b  mov     edx, 80h
0x1801df260  lea     rcx, [rbp+57h+packageFullName]
0x1801df264  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801df269  nop
0x1801df26a  mov     eax, [rbp+57h+var_38]
0x1801df26d  mov     [rbp+57h+packageFullNameLength], eax
0x1801df270  lea     r8, [rbp+57h+packageFullName]
0x1801df274  cmp     [rbp+57h+var_30], 7
0x1801df279  cmova   r8, [rbp+57h+packageFullName]; packageFullName
0x1801df27e  lea     rdx, [rbp+57h+packageFullNameLength]; packageFullNameLength
0x1801df282  mov     rcx, rbx; hProcess
0x1801df285  call    cs:__imp_GetPackageFullName
0x1801df28c  nop     dword ptr [rax+rax+00h]
0x1801df291  mov     ebx, eax
0x1801df293  test    eax, eax
0x1801df295  jns     short loc_1801DF2BE
0x1801df297  mov     rcx, [rbp+5Fh]; this
0x1801df29b  mov     r9d, eax; char *
0x1801df29e  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801df2a5  mov     edx, 190Ch; void *
0x1801df2aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801df2af  nop
0x1801df2b0  lea     rcx, [rbp+57h+packageFullName]; this
0x1801df2b4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801df2b9  jmp     loc_1801DF397
0x1801df2be  lea     rax, [rbp+57h+packageFullName]
0x1801df2c2  cmp     [rbp+57h+var_30], 7
0x1801df2c7  cmova   rax, [rbp+57h+packageFullName]
0x1801df2cc  cmp     [rax], si
0x1801df2cf  jz      loc_1801DF38C
0x1801df2d5  mov     edx, [rbp+57h+packageFullNameLength]
0x1801df2d8  lea     rcx, [rbp+57h+packageFullName]
0x1801df2dc  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801df2e1  mov     [rbp+57h+var_78], rsi
0x1801df2e5  lea     rax, [rbp+57h+var_78]
0x1801df2e9  mov     [rbp+57h+var_60], rax
0x1801df2ed  mov     [rbp+57h+var_58], rsi
0x1801df2f1  mov     [rbp+57h+var_50], 1
0x1801df2f5  lea     rdx, [rbp+57h+var_58]
0x1801df2f9  xor     ecx, ecx
0x1801df2fb  call    cs:__imp_SRCacheManager_Open
0x1801df302  nop     dword ptr [rax+rax+00h]
0x1801df307  mov     ebx, eax
0x1801df309  lea     rcx, [rbp+57h+var_60]
0x1801df30d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1801df312  test    ebx, ebx
0x1801df314  jns     short loc_1801DF356
0x1801df316  mov     rcx, [rbp+5Fh]; this
0x1801df31a  mov     r9d, ebx; char *
0x1801df31d  lea     r8, aOnecorePrivate; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801df324  mov     edx, 0A5h; void *
0x1801df329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801df32e  mov     r9d, ebx; char *
0x1801df331  mov     edx, 1913h; void *
0x1801df336  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801df33d  mov     rcx, [rbp+5Fh]; this
0x1801df341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801df346  xor     edx, edx
0x1801df348  lea     rcx, [rbp+57h+var_78]
0x1801df34c  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x1801df351  jmp     loc_1801DF2B0
0x1801df356  lea     rdx, [rbp+57h+packageFullName]
0x1801df35a  cmp     [rbp+57h+var_30], 7
0x1801df35f  cmova   rdx, [rbp+57h+packageFullName]; wchar_t *
0x1801df364  mov     r8, rdi; bool *
0x1801df367  lea     rcx, [rbp+57h+var_78]; struct StateRepository::Cache::Manager_NoThrow *
0x1801df36b  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x1801df370  mov     ebx, eax
0x1801df372  test    eax, eax
0x1801df374  jns     short loc_1801DF380
0x1801df376  mov     r9d, eax
0x1801df379  mov     edx, 1918h
0x1801df37e  jmp     short loc_1801DF336
0x1801df380  xor     edx, edx
0x1801df382  lea     rcx, [rbp+57h+var_78]
0x1801df386  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x1801df38b  nop
0x1801df38c  lea     rcx, [rbp+57h+packageFullName]; this
0x1801df390  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801df395  mov     ebx, esi
0x1801df397  lea     rcx, [rbp+57h+dwProcessId]
0x1801df39b  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801df3a0  mov     eax, ebx
0x1801df3a2  mov     rcx, [rbp+57h+var_28]
0x1801df3a6  xor     rcx, rsp; StackCookie
0x1801df3a9  call    __security_check_cookie
0x1801df3ae  add     rsp, 88h
0x1801df3b5  pop     rdi
0x1801df3b6  pop     rsi
0x1801df3b7  pop     rbx
0x1801df3b8  pop     rbp
0x1801df3b9  retn
```
