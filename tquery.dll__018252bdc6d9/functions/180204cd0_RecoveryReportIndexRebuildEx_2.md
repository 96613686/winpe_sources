# RecoveryReportIndexRebuildEx_2

- ea: `0x180204cd0`
- end: `0x1802050ab`
- name: `RecoveryReportIndexRebuildEx_2`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180204c60`

## callees

- `0x18002e6fc`
- `0x180043d18`
- `0x18006380c`
- `0x180075d8c`
- `0x180078410`
- `0x18008b084`
- `0x18008facc`
- `0x1800983c0`
- `0x18009e510`
- `0x18009e614`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x1801710e4`
- `0x180188d90`
- `0x18018e778`
- `0x18019b924`
- `0x1801a40f0`
- `0x1801a444c`
- `0x1801a8e38`
- `0x1801f9f0c`
- `0x180204b64`
- `0x180204cd0`
- `0x180205100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180204f9c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180204f9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180204d28`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180204d28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020500a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020500a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180205056`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180205056`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180204e53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180204e53`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180204ea0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18020504b`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180204ea0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18020504b`

## string_xrefs

- `0x180204e68`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180204eb5`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180204f50`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180204e92`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx_2(__int64 a1, struct CEventLog *a2)
{
  const wchar_t *v3; // rcx
  const wchar_t *Catalog; // rdi
  const OLECHAR *v5; // rdx
  HKEY *phkResult; // rax
  const WCHAR *v7; // rdx
  unsigned int Key; // eax
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // kr10_8
  wchar_t *v14; // rax
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  void *v19; // r11
  bool v21; // al
  wchar_t *v22; // rdx
  LSTATUS v23; // eax
  bool v24; // sf
  unsigned int dwOptions; // [rsp+20h] [rbp-A28h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A28h]
  HKEY hkey; // [rsp+50h] [rbp-9F8h] BYREF
  int pvData; // [rsp+58h] [rbp-9F0h] BYREF
  HANDLE v29[2]; // [rsp+60h] [rbp-9E8h] BYREF
  int v30; // [rsp+70h] [rbp-9D8h] BYREF
  __int64 v31; // [rsp+78h] [rbp-9D0h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-9C8h] BYREF
  wchar_t v33; // [rsp+A0h] [rbp-9A8h] BYREF
  _BYTE v34[160]; // [rsp+A8h] [rbp-9A0h] BYREF
  _BYTE v35[2248]; // [rsp+148h] [rbp-900h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A48h] [rbp+0h]

  v30 = 0;
  v31 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v30);
  LogIndexCorruptionEx_1(a2);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    v29[0] = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)&v33, a2);
      v5 = &psz;
      if ( Catalog )
        v5 = Catalog;
      CLMString::operator=(v34, v5);
      CLMString::operator=(v35, &psz);
      CSearchEventEntry::SetError((CSearchEventEntry *)&v33, -1073473535);
      CSearchEventEntry::ReportError((CSearchEventEntry *)&v33, 0xC0001B80, L"The catalog is corrupt", 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)&v33);
    }
    try
    {
      std::wstring::wstring(lpSubKey);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v7 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v7 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v7, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v9 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v9 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v9,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        253,
        "onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h");
    }
    v10 = -1;
    do
      ++v10;
    while ( Catalog[v10] );
    v11 = v10 + 1;
    v13 = v10 + 1;
    v12 = 2 * (v10 + 1);
    if ( !is_mul_ok(v13, 2u) )
      v12 = -1;
    v14 = (wchar_t *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v14;
    if ( !v14 )
    {
      v15 = -2147024882;
      v16 = 2147942414LL;
      v17 = 257;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v16,
        dwOptionsa);
      SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v30);
      return v15;
    }
    v18 = StringCchCopyW(v14, v11, Catalog);
    v15 = v18;
    if ( v18 < 0 )
    {
      v16 = (unsigned int)v18;
      v17 = 259;
      goto LABEL_22;
    }
    hkey = 0;
    v29[0] = CreateThread(0, 0, ResetUserCatalog, v19, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v29);
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
  }
  else
  {
    hkey = 0;
    v21 = MapRegistryKeyPath(v3, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", &v33);
    v22 = &v33;
    if ( !v21 )
      v22 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v22, 0, 0xF003Fu, &hkey);
    v24 = v23 < 0;
    if ( v23 > 0 )
      v24 = 1;
    if ( !v24 )
    {
      pvData = 3;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      ShutdownSelf_1(a2, (__int64)L"The catalog is corrupt");
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v30);
  return 0;
}

```

## disassembly

```asm
0x180204cd0  push    rbx
0x180204cd2  push    rsi
0x180204cd3  push    rdi
0x180204cd4  push    r14
0x180204cd6  sub     rsp, 0A28h
0x180204cdd  mov     rax, cs:__security_cookie
0x180204ce4  xor     rax, rsp
0x180204ce7  mov     [rsp+0A48h+var_38], rax
0x180204cef  mov     rsi, rdx
0x180204cf2  xor     ebx, ebx
0x180204cf4  mov     [rsp+0A48h+var_9D8], ebx
0x180204cf8  or      r14, 0FFFFFFFFFFFFFFFFh
0x180204cfc  mov     [rsp+0A48h+var_9D0], r14
0x180204d01  lea     rcx, [rsp+0A48h+var_9D8]; this
0x180204d06  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x180204d0b  nop
0x180204d0c  mov     rcx, rsi
0x180204d0f  call    LogIndexCorruptionEx_1
0x180204d14  xor     r9d, r9d; Context
0x180204d17  xor     r8d, r8d; Parameter
0x180204d1a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180204d21  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180204d28  call    cs:__imp_InitOnceExecuteOnce
0x180204d2e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180204d34  jz      loc_180204FC0
0x180204d3a  call    PerUserCatalogNameForCorruption__GetCatalog
0x180204d3f  test    rax, rax
0x180204d42  jz      loc_180204FC0
0x180204d48  call    PerUserCatalogNameForCorruption__GetCatalog
0x180204d4d  mov     rdi, rax
0x180204d50  mov     [rsp+0A48h+var_9E8], rax
0x180204d55  test    rsi, rsi
0x180204d58  jz      short loc_180204DD7
0x180204d5a  mov     rdx, rsi; struct CEventLog *
0x180204d5d  lea     rcx, [rsp+0A48h+var_9A8]; this
0x180204d65  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x180204d6a  nop
0x180204d6b  lea     rdx, psz
0x180204d72  test    rdi, rdi
0x180204d75  cmovnz  rdx, rdi
0x180204d79  lea     rcx, [rsp+0A48h+var_9A0]
0x180204d81  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180204d86  lea     rdx, psz
0x180204d8d  lea     rcx, [rsp+0A48h+var_900]
0x180204d95  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180204d9a  mov     edx, 0C0041801h; int
0x180204d9f  lea     rcx, [rsp+0A48h+var_9A8]; this
0x180204da7  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x180204dac  xor     r9d, r9d
0x180204daf  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x180204db6  mov     edx, 0C0001B80h; unsigned int
0x180204dbb  lea     rcx, [rsp+0A48h+var_9A8]; this
0x180204dc3  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x180204dc8  nop
0x180204dc9  lea     rcx, [rsp+0A48h+var_9A8]; this
0x180204dd1  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x180204dd6  nop
0x180204dd7  mov     rdx, rdi
0x180204dda  lea     rcx, [rsp+0A48h+lpSubKey]
0x180204de2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180204de7  nop
0x180204de8  mov     r8d, 22h ; '"'
0x180204dee  lea     rdx, aSoftwareMicros_7; "\\SOFTWARE\\Microsoft\\Windows Search"
0x180204df5  lea     rcx, [rsp+0A48h+lpSubKey]; Src
0x180204dfd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180204e02  mov     [rsp+0A48h+hkey], rbx
0x180204e07  lea     rcx, [rsp+0A48h+hkey]
0x180204e0c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180204e11  lea     rdx, [rsp+0A48h+lpSubKey]
0x180204e19  cmp     [rsp+0A48h+var_9B0], 7
0x180204e22  cmova   rdx, [rsp+0A48h+lpSubKey]; lpSubKey
0x180204e2b  mov     [rsp+0A48h+lpdwDisposition], rbx; lpdwDisposition
0x180204e30  mov     [rsp+0A48h+phkResult], rax; phkResult
0x180204e35  mov     [rsp+0A48h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180204e3a  mov     [rsp+0A48h+samDesired], 0F003Fh; samDesired
0x180204e42  mov     [rsp+0A48h+dwOptions], ebx; unsigned int
0x180204e46  xor     r9d, r9d; lpClass
0x180204e49  xor     r8d, r8d; Reserved
0x180204e4c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180204e53  call    cs:__imp_RegCreateKeyExW
0x180204e59  mov     rcx, [rsp+0A48h]; this
0x180204e61  test    eax, eax
0x180204e63  jz      short loc_180204E79
0x180204e65  mov     r9d, eax; char *
0x180204e68  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180204e6f  mov     edx, 0F7h; void *
0x180204e74  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180204e79  mov     [rsp+0A48h+pvData], ebx
0x180204e7d  mov     r9d, 4; dwType
0x180204e83  mov     [rsp+0A48h+samDesired], r9d; cbData
0x180204e88  lea     rax, [rsp+0A48h+pvData]
0x180204e8d  mov     qword ptr [rsp+0A48h+dwOptions], rax; unsigned int
0x180204e92  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x180204e99  xor     edx, edx; pszSubKey
0x180204e9b  mov     rcx, [rsp+0A48h+hkey]; hkey
0x180204ea0  call    cs:__imp_SHSetValueW
0x180204ea6  mov     rcx, [rsp+0A48h]; this
0x180204eae  test    eax, eax
0x180204eb0  jz      short loc_180204EC7
0x180204eb2  mov     r9d, eax; char *
0x180204eb5  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180204ebc  mov     edx, 0FBh; void *
0x180204ec1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180204ec7  lea     rcx, [rsp+0A48h+hkey]
0x180204ecc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180204ed1  nop
0x180204ed2  lea     rcx, [rsp+0A48h+lpSubKey]
0x180204eda  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180204edf  nop
0x180204ee0  jmp     short loc_180204EED
0x180204ee2  xor     ebx, ebx
0x180204ee4  or      r14, 0FFFFFFFFFFFFFFFFh
0x180204ee8  mov     rdi, [rsp+0A48h+var_9E8]
0x180204eed  mov     rax, r14
0x180204ef0  inc     rax
0x180204ef3  cmp     [rdi+rax*2], bx
0x180204ef7  jnz     short loc_180204EF0
0x180204ef9  lea     rsi, [rax+1]
0x180204efd  mov     eax, 2
0x180204f02  mul     rsi
0x180204f05  cmovb   rax, r14
0x180204f09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180204f10  mov     rcx, rax; unsigned __int64
0x180204f13  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180204f18  mov     r11, rax
0x180204f1b  mov     [rsp+0A48h+hkey], rax
0x180204f20  test    rax, rax
0x180204f23  jnz     short loc_180204F34
0x180204f25  mov     edi, 8007000Eh
0x180204f2a  mov     r9d, edi
0x180204f2d  mov     edx, 101h
0x180204f32  jmp     short loc_180204F50
0x180204f34  mov     r8, rdi; wchar_t *
0x180204f37  mov     rdx, rsi; unsigned __int64
0x180204f3a  mov     rcx, r11; wchar_t *
0x180204f3d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180204f42  mov     edi, eax
0x180204f44  test    eax, eax
0x180204f46  jns     short loc_180204F80
0x180204f48  mov     r9d, eax; char *
0x180204f4b  mov     edx, 103h; void *
0x180204f50  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180204f57  mov     rcx, [rsp+0A48h]; this
0x180204f5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180204f64  lea     rcx, [rsp+0A48h+hkey]; this
0x180204f69  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x180204f6e  nop
0x180204f6f  lea     rcx, [rsp+0A48h+var_9D8]; this
0x180204f74  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x180204f79  mov     eax, edi
0x180204f7b  jmp     loc_18020508E
0x180204f80  mov     [rsp+0A48h+hkey], rbx
0x180204f85  mov     qword ptr [rsp+0A48h+samDesired], rbx; lpThreadId
0x180204f8a  mov     [rsp+0A48h+dwOptions], ebx; dwCreationFlags
0x180204f8e  mov     r9, r11; lpParameter
0x180204f91  lea     r8, ResetUserCatalog; lpStartAddress
0x180204f98  xor     edx, edx; dwStackSize
0x180204f9a  xor     ecx, ecx; lpThreadAttributes
0x180204f9c  call    cs:__imp_CreateThread
0x180204fa2  mov     [rsp+0A48h+var_9E8], rax
0x180204fa7  lea     rcx, [rsp+0A48h+var_9E8]
0x180204fac  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180204fb1  lea     rcx, [rsp+0A48h+hkey]; this
0x180204fb6  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x180204fbb  jmp     loc_180205082
0x180204fc0  mov     [rsp+0A48h+hkey], rbx
0x180204fc5  lea     r9, [rsp+0A48h+var_9A8]; wchar_t *
0x180204fcd  lea     rdi, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search"
0x180204fd4  mov     r8, rdi; wchar_t *
0x180204fd7  mov     r14, 0FFFFFFFF80000002h
0x180204fde  mov     rdx, r14; HKEY
0x180204fe1  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x180204fe6  lea     rdx, [rsp+0A48h+var_9A8]
0x180204fee  test    al, al
0x180204ff0  cmovz   rdx, rdi; lpSubKey
0x180204ff4  lea     rax, [rsp+0A48h+hkey]
0x180204ff9  mov     qword ptr [rsp+0A48h+dwOptions], rax; phkResult
0x180204ffe  mov     r9d, 0F003Fh; samDesired
0x180205004  xor     r8d, r8d; ulOptions
0x180205007  mov     rcx, r14; hKey
0x18020500a  call    cs:__imp_RegOpenKeyExW
0x180205010  test    eax, eax
0x180205012  jle     short loc_18020501E
0x180205014  movzx   eax, ax
0x180205017  or      eax, 80070000h
0x18020501c  test    eax, eax
0x18020501e  js      short loc_18020505C
0x180205020  mov     [rsp+0A48h+pvData], 3
0x180205028  mov     r9d, 4; dwType
0x18020502e  mov     [rsp+0A48h+samDesired], r9d; cbData
0x180205033  lea     rax, [rsp+0A48h+pvData]
0x180205038  mov     qword ptr [rsp+0A48h+dwOptions], rax; pvData
0x18020503d  lea     r8, aRebuildindex; "RebuildIndex"
0x180205044  xor     edx, edx; pszSubKey
0x180205046  mov     rcx, [rsp+0A48h+hkey]; hkey
0x18020504b  call    cs:__imp_SHSetValueW
0x180205051  mov     rcx, [rsp+0A48h+hkey]; hKey
0x180205056  call    cs:__imp_RegCloseKey
0x18020505c  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x180205062  jnz     short loc_180205082
0x180205064  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x18020506b  mov     qword ptr [rsp+0A48h+dwOptions], rax; __int64
0x180205070  mov     rcx, rsi; struct CEventLog *
0x180205073  call    ShutdownSelf_1
0x180205078  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x180205082  lea     rcx, [rsp+0A48h+var_9D8]; this
0x180205087  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x18020508c  xor     eax, eax
0x18020508e  mov     rcx, [rsp+0A48h+var_38]
0x180205096  xor     rcx, rsp; StackCookie
0x180205099  call    __security_check_cookie
0x18020509e  add     rsp, 0A28h
0x1802050a5  pop     r14
0x1802050a7  pop     rdi
0x1802050a8  pop     rsi
0x1802050a9  pop     rbx
0x1802050aa  retn
```
