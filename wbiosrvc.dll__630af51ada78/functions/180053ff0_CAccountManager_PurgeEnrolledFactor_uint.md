# CAccountManager::PurgeEnrolledFactor(uint)

- ea: `0x180053ff0`
- end: `0x1800546d4`
- name: `?PurgeEnrolledFactor@CAccountManager@@SAJI@Z`
- size: `1764`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c810`

## callees

- `0x18000367c`
- `0x18000986c`
- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x18001693c`
- `0x180029600`
- `0x18002b2f8`
- `0x180035d78`
- `0x18003c468`
- `0x18003c8dc`
- `0x180046664`
- `0x1800530c4`
- `0x18005388c`
- `0x180053ff0`
- `0x180068f60`
- `0x180069cc8`
- `0x1800778e8`
- `0x180077910`
- `0x180077af8`
- `0x180077fcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800541e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180054342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800544a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800541e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180054342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800544a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005448b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005448b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005411a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005458f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054622`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005468b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005411a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005458f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054622`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005468b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800541ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800541ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800542fb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800542fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180054426`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180054426`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180054438`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180054438`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800543ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800543ed`

## string_xrefs

- `0x180054033`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180054077`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800540fd`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800541c4`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180054314`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180054535`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800545c8`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CAccountManager::PurgeEnrolledFactor(winbio *a1, unsigned int a2)
{
  unsigned int v2; // edi
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  int WinBioRegistryLocation; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  PHKEY v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // ebx
  struct CAccountManager *v15; // rax
  unsigned int v16; // eax
  DWORD i; // esi
  unsigned int v18; // eax
  BOOL v19; // ebx
  PSID v20; // rcx
  void *v21; // rcx
  _OWORD *v22; // rbx
  _OWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  int phkResult; // [rsp+20h] [rbp-158h]
  unsigned int phkResulta; // [rsp+20h] [rbp-158h]
  unsigned int phkResultb; // [rsp+20h] [rbp-158h]
  unsigned int phkResultc; // [rsp+20h] [rbp-158h]
  int phkResultd; // [rsp+20h] [rbp-158h]
  bool v32[8]; // [rsp+60h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-110h] BYREF
  void *v34; // [rsp+70h] [rbp-108h] BYREF
  __int128 v35; // [rsp+78h] [rbp-100h]
  DWORD cSubKeys; // [rsp+88h] [rbp-F0h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-ECh] BYREF
  PSID pSourceSid; // [rsp+90h] [rbp-E8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp-E0h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-D8h] BYREF
  LPWSTR lpName[3]; // [rsp+A8h] [rbp-D0h] BYREF
  PSID *p_pSourceSid; // [rsp+C0h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+C8h] [rbp-B0h] BYREF
  char v44; // [rsp+D0h] [rbp-A8h]
  _BYTE v45[40]; // [rsp+D8h] [rbp-A0h] BYREF
  struct _WINBIO_IDENTITY pDestinationSid; // [rsp+100h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v2 = (unsigned int)a1;
  v3 = winbio::ValidateFactor(a1, a2);
  v7 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
    return v7;
  }
  std::wstring::wstring(v45, v4, v5, v6);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v45);
  v10 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      phkResult);
    std::wstring::_Tidy_deallocate(v45);
    return v10;
  }
  std::wstring::append(v45, L"AccountInfo\\");
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, v12);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
            (const char *)v13,
            phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_28:
    std::wstring::_Tidy_deallocate(v45);
    return v14;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v34);
  v15 = CAccountManager::Instance();
  winbio::lockable_object::lock_shared(v15, &SRWLock);
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v16 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v16 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1FD,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
            (const char *)v16,
            phkResultb);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    if ( v34 )
    {
      std::_Deallocate<16>(v34, 4 * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v34) >> 2));
      v34 = 0;
      v35 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( cSubKeys )
  {
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
    pSourceSid = (PSID)cSubKeys;
    if ( cSubKeys > 0x86BCA1AF286BCA1BuLL * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v34) >> 2) )
      std::vector<_WINBIO_IDENTITY>::_Reallocate<0>(&v34, &pSourceSid);
    for ( i = 0; ; ++i )
    {
      cchName = lpName[1] - lpName[0];
      v18 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
      if ( v18 )
        break;
      memset_0(&pDestinationSid, 0, sizeof(pDestinationSid));
      pSourceSid = 0;
      p_pSourceSid = &pSourceSid;
      Sid = 0;
      v44 = 1;
      v19 = ConvertStringSidToSidW(lpName[0], &Sid);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pSourceSid);
      if ( v19 )
      {
        pDestinationSid.Type = 3;
        if ( CopySid(0x44u, pDestinationSid.Value.AccountSid.Data, pSourceSid) )
        {
          pDestinationSid.Value.Null = GetLengthSid(pSourceSid);
          if ( (_QWORD)v35 == *((_QWORD *)&v35 + 1) )
            std::vector<_WINBIO_IDENTITY>::_Emplace_reallocate<_WINBIO_IDENTITY const &>(&v34, v35, &pDestinationSid);
          else
            std::vector<_WINBIO_IDENTITY>::_Emplace_back_with_unused_capacity<_WINBIO_IDENTITY const &>(
              &v34,
              &pDestinationSid);
        }
      }
      v20 = pSourceSid;
      pSourceSid = 0;
      if ( v20 )
        LocalFree(v20);
    }
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x207,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
            (const char *)v18,
            phkResultc);
    std::vector<unsigned short>::_Tidy(lpName);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    if ( v34 )
    {
      std::_Deallocate<16>(v34, 4 * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v34) >> 2));
      v34 = 0;
      v35 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v21 = v34;
  v22 = v34;
  v23 = (_OWORD *)v35;
  while ( v22 != v23 )
  {
    *(_OWORD *)&pDestinationSid.Type = *v22;
    *(_OWORD *)&pDestinationSid.Value.AccountSid.Data[8] = v22[1];
    *(_OWORD *)&pDestinationSid.Value.AccountSid.Data[24] = v22[2];
    *(_OWORD *)&pDestinationSid.Value.AccountSid.Data[40] = v22[3];
    *(_OWORD *)&pDestinationSid.Value.AccountSid.Data[52] = *(_OWORD *)((char *)v22 + 60);
    v32[0] = 0;
    v24 = CAccountManager::SetEnrolledFactorState(&pDestinationSid, v2, 0, 0, v32);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
        (const char *)(unsigned int)v24,
        phkResultd);
      if ( v34 )
      {
        std::_Deallocate<16>(v34, 4 * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v34) >> 2));
        v34 = 0;
        v35 = 0;
      }
      if ( hKey )
        RegCloseKey(hKey);
LABEL_46:
      std::wstring::_Tidy_deallocate(v45);
      return v25;
    }
    v26 = CAccountManager::PurgeBioTimestamps(&pDestinationSid);
    v25 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
        (const char *)(unsigned int)v26,
        phkResultd);
      if ( v34 )
      {
        std::_Deallocate<16>(v34, 4 * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v34) >> 2));
        v34 = 0;
        v35 = 0;
      }
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_46;
    }
    v22 = (_OWORD *)((char *)v22 + 76);
    v21 = v34;
  }
  if ( v21 )
  {
    std::_Deallocate<16>(v21, 4 * ((__int64)(*((_QWORD *)&v35 + 1) - (_QWORD)v21) >> 2));
    v34 = 0;
    v35 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(v45);
  return 0;
}

```

## disassembly

```asm
0x180053ff0  mov     [rsp+arg_8], rbx
0x180053ff5  mov     [rsp+arg_10], rsi
0x180053ffa  push    rdi
0x180053ffb  push    r14
0x180053ffd  push    r15
0x180053fff  sub     rsp, 160h
0x180054006  mov     rax, cs:__security_cookie
0x18005400d  xor     rax, rsp
0x180054010  mov     [rsp+178h+var_28], rax
0x180054018  mov     edi, ecx
0x18005401a  call    ?ValidateFactor@winbio@@YAJI@Z; winbio::ValidateFactor(uint)
0x18005401f  mov     ebx, eax
0x180054021  xor     r15d, r15d
0x180054024  test    eax, eax
0x180054026  jns     short loc_18005404B
0x180054028  mov     rcx, [rsp+178h]; this
0x180054030  mov     r9d, eax; char *
0x180054033  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18005403a  mov     edx, 1EBh; void *
0x18005403f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054044  mov     eax, ebx
0x180054046  jmp     loc_1800546AA
0x18005404b  lea     rcx, [rsp+178h+var_A0]
0x180054053  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180054058  nop
0x180054059  lea     rcx, [rsp+178h+var_A0]
0x180054061  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180054066  mov     ebx, eax
0x180054068  test    eax, eax
0x18005406a  jns     short loc_18005409D
0x18005406c  mov     rcx, [rsp+178h]; this
0x180054074  mov     r9d, eax; char *
0x180054077  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18005407e  mov     edx, 1EEh; void *
0x180054083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054088  nop
0x180054089  lea     rcx, [rsp+178h+var_A0]
0x180054091  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054096  mov     eax, ebx
0x180054098  jmp     loc_1800546AA
0x18005409d  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800540a4  lea     rcx, [rsp+178h+var_A0]
0x1800540ac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800540b1  mov     [rsp+178h+hKey], r15
0x1800540b6  lea     rcx, [rsp+178h+hKey]
0x1800540bb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800540c0  mov     r8, rax
0x1800540c3  lea     rcx, [rsp+178h+var_A0]
0x1800540cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800540d0  mov     rdx, rax; lpSubKey
0x1800540d3  mov     [rsp+178h+phkResult], r8; unsigned int
0x1800540d8  mov     r9d, 20019h; samDesired
0x1800540de  xor     r8d, r8d; ulOptions
0x1800540e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800540e8  call    cs:__imp_RegOpenKeyExW
0x1800540ee  test    eax, eax
0x1800540f0  jz      short loc_180054135
0x1800540f2  mov     rcx, [rsp+178h]; this
0x1800540fa  mov     r9d, eax; char *
0x1800540fd  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180054104  mov     edx, 1F2h; void *
0x180054109  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005410e  mov     ebx, eax
0x180054110  mov     rcx, [rsp+178h+hKey]; hKey
0x180054115  test    rcx, rcx
0x180054118  jz      short loc_180054121
0x18005411a  call    cs:__imp_RegCloseKey
0x180054120  nop
0x180054121  lea     rcx, [rsp+178h+var_A0]
0x180054129  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005412e  mov     eax, ebx
0x180054130  jmp     loc_1800546AA
0x180054135  lea     rcx, [rsp+178h+var_108]
0x18005413a  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18005413f  nop
0x180054140  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180054145  lea     rdx, [rsp+178h+SRWLock]
0x18005414d  mov     rcx, rax
0x180054150  call    ?lock_shared@lockable_object@winbio@@QEBA?AVSyncLockShared@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_shared(void)
0x180054155  nop
0x180054156  mov     [rsp+178h+cSubKeys], r15d
0x18005415e  mov     [rsp+178h+cbMaxSubKeyLen], r15d
0x180054166  mov     [rsp+178h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18005416b  mov     [rsp+178h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180054170  mov     [rsp+178h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180054175  mov     [rsp+178h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18005417a  mov     [rsp+178h+lpcValues], r15; lpcValues
0x18005417f  mov     [rsp+178h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180054184  lea     rax, [rsp+178h+cbMaxSubKeyLen]
0x18005418c  mov     [rsp+178h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180054191  lea     rax, [rsp+178h+cSubKeys]
0x180054199  mov     [rsp+178h+phkResult], rax; unsigned int
0x18005419e  xor     r9d, r9d; lpReserved
0x1800541a1  xor     r8d, r8d; lpcchClass
0x1800541a4  xor     edx, edx; lpClass
0x1800541a6  mov     rcx, [rsp+178h+hKey]; hKey
0x1800541ab  call    cs:__imp_RegQueryInfoKeyW
0x1800541b1  test    eax, eax
0x1800541b3  jz      loc_18005424E
0x1800541b9  mov     rcx, [rsp+178h]; this
0x1800541c1  mov     r9d, eax; char *
0x1800541c4  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800541cb  mov     edx, 1FDh; void *
0x1800541d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800541d5  mov     ebx, eax
0x1800541d7  mov     rcx, [rsp+178h+SRWLock]; SRWLock
0x1800541df  test    rcx, rcx
0x1800541e2  jz      short loc_1800541EB
0x1800541e4  call    cs:__imp_ReleaseSRWLockShared
0x1800541ea  nop
0x1800541eb  mov     rcx, [rsp+178h+var_108]
0x1800541f0  test    rcx, rcx
0x1800541f3  jz      short loc_180054229
0x1800541f5  mov     rax, qword ptr [rsp+178h+var_100+8]
0x1800541fd  sub     rax, rcx
0x180054200  sar     rax, 2
0x180054204  mov     rdi, 86BCA1AF286BCA1Bh
0x18005420e  imul    rax, rdi
0x180054212  imul    rdx, rax, 4Ch ; 'L'
0x180054216  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005421b  mov     [rsp+178h+var_108], r15
0x180054220  xorps   xmm0, xmm0
0x180054223  movdqu  [rsp+178h+var_100], xmm0
0x180054229  mov     rcx, [rsp+178h+hKey]; hKey
0x18005422e  test    rcx, rcx
0x180054231  jz      short loc_18005423A
0x180054233  call    cs:__imp_RegCloseKey
0x180054239  nop
0x18005423a  lea     rcx, [rsp+178h+var_A0]
0x180054242  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054247  mov     eax, ebx
0x180054249  jmp     loc_1800546AA
0x18005424e  cmp     [rsp+178h+cSubKeys], r15d
0x180054256  jbe     loc_180054498
0x18005425c  mov     edx, [rsp+178h+cbMaxSubKeyLen]
0x180054263  inc     edx
0x180054265  lea     rcx, [rsp+178h+lpName]
0x18005426d  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180054272  nop
0x180054273  mov     ecx, [rsp+178h+cSubKeys]
0x18005427a  mov     [rsp+178h+pSourceSid], rcx
0x180054282  mov     rax, qword ptr [rsp+178h+var_100+8]
0x18005428a  sub     rax, [rsp+178h+var_108]
0x18005428f  sar     rax, 2
0x180054293  mov     rdi, 86BCA1AF286BCA1Bh
0x18005429d  imul    rax, rdi
0x1800542a1  cmp     rcx, rax
0x1800542a4  jbe     short loc_1800542B8
0x1800542a6  lea     rdx, [rsp+178h+pSourceSid]
0x1800542ae  lea     rcx, [rsp+178h+var_108]
0x1800542b3  call    ??$_Reallocate@$0A@@?$vector@U_WINBIO_IDENTITY@@V?$allocator@U_WINBIO_IDENTITY@@@std@@@std@@AEAAXAEA_K@Z; std::vector<_WINBIO_IDENTITY>::_Reallocate<0>(unsigned __int64 &)
0x1800542b8  mov     esi, r15d
0x1800542bb  mov     r8, [rsp+178h+lpName]; lpName
0x1800542c3  mov     rax, [rsp+178h+var_C8]
0x1800542cb  sub     rax, r8
0x1800542ce  sar     rax, 1
0x1800542d1  mov     [rsp+178h+cchName], eax
0x1800542d8  mov     [rsp+178h+lpcValues], r15; lpftLastWriteTime
0x1800542dd  mov     [rsp+178h+lpcbMaxClassLen], r15; lpcchClass
0x1800542e2  mov     [rsp+178h+lpcbMaxSubKeyLen], r15; lpClass
0x1800542e7  mov     [rsp+178h+phkResult], r15; unsigned int
0x1800542ec  lea     r9, [rsp+178h+cchName]; lpcchName
0x1800542f4  mov     edx, esi; dwIndex
0x1800542f6  mov     rcx, [rsp+178h+hKey]; hKey
0x1800542fb  call    cs:__imp_RegEnumKeyExW
0x180054301  test    eax, eax
0x180054303  jz      loc_1800543A2
0x180054309  mov     rcx, [rsp+178h]; this
0x180054311  mov     r9d, eax; char *
0x180054314  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18005431b  mov     edx, 207h; void *
0x180054320  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180054325  mov     ebx, eax
0x180054327  lea     rcx, [rsp+178h+lpName]
0x18005432f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180054334  nop
0x180054335  mov     rcx, [rsp+178h+SRWLock]; SRWLock
0x18005433d  test    rcx, rcx
0x180054340  jz      short loc_180054349
0x180054342  call    cs:__imp_ReleaseSRWLockShared
0x180054348  nop
0x180054349  mov     rcx, [rsp+178h+var_108]
0x18005434e  test    rcx, rcx
0x180054351  jz      short loc_18005437D
0x180054353  mov     rax, qword ptr [rsp+178h+var_100+8]
0x18005435b  sub     rax, rcx
0x18005435e  sar     rax, 2
0x180054362  imul    rax, rdi
0x180054366  imul    rdx, rax, 4Ch ; 'L'
0x18005436a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005436f  mov     [rsp+178h+var_108], r15
0x180054374  xorps   xmm0, xmm0
0x180054377  movdqu  [rsp+178h+var_100], xmm0
0x18005437d  mov     rcx, [rsp+178h+hKey]; hKey
0x180054382  test    rcx, rcx
0x180054385  jz      short loc_18005438E
0x180054387  call    cs:__imp_RegCloseKey
0x18005438d  nop
0x18005438e  lea     rcx, [rsp+178h+var_A0]
0x180054396  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005439b  mov     eax, ebx
0x18005439d  jmp     loc_1800546AA
0x1800543a2  xor     edx, edx; Val
0x1800543a4  lea     r8d, [rdx+4Ch]; Size
0x1800543a8  lea     rcx, [rsp+178h+pDestinationSid]; void *
0x1800543b0  call    memset_0
0x1800543b5  mov     [rsp+178h+pSourceSid], r15
0x1800543bd  lea     rax, [rsp+178h+pSourceSid]
0x1800543c5  mov     [rsp+178h+var_B8], rax
0x1800543cd  mov     [rsp+178h+Sid], r15
0x1800543d5  mov     [rsp+178h+var_A8], 1
0x1800543dd  lea     rdx, [rsp+178h+Sid]; Sid
0x1800543e5  mov     rcx, [rsp+178h+lpName]; StringSid
0x1800543ed  call    cs:__imp_ConvertStringSidToSidW
0x1800543f3  mov     ebx, eax
0x1800543f5  lea     rcx, [rsp+178h+var_B8]
0x1800543fd  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180054402  test    ebx, ebx
0x180054404  jz      short loc_180054476
0x180054406  mov     dword ptr [rsp+178h+pDestinationSid], 3
0x180054411  mov     r8, [rsp+178h+pSourceSid]; pSourceSid
0x180054419  lea     rdx, [rsp+178h+pDestinationSid+8]; pDestinationSid
0x180054421  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180054426  call    cs:__imp_CopySid
0x18005442c  test    eax, eax
0x18005442e  jz      short loc_180054476
0x180054430  mov     rcx, [rsp+178h+pSourceSid]; pSid
0x180054438  call    cs:__imp_GetLengthSid
0x18005443e  mov     dword ptr [rsp+178h+pDestinationSid+4], eax
0x180054445  mov     rdx, qword ptr [rsp+178h+var_100]
0x18005444a  lea     rcx, [rsp+178h+var_108]
0x18005444f  cmp     rdx, qword ptr [rsp+178h+var_100+8]
0x180054457  jz      short loc_180054468
0x180054459  lea     rdx, [rsp+178h+pDestinationSid]
0x180054461  call    ??$_Emplace_back_with_unused_capacity@AEBU_WINBIO_IDENTITY@@@?$vector@U_WINBIO_IDENTITY@@V?$allocator@U_WINBIO_IDENTITY@@@std@@@std@@AEAAAEAU_WINBIO_IDENTITY@@AEBU2@@Z; std::vector<_WINBIO_IDENTITY>::_Emplace_back_with_unused_capacity<_WINBIO_IDENTITY const &>(_WINBIO_IDENTITY const &)
0x180054466  jmp     short loc_180054476
0x180054468  lea     r8, [rsp+178h+pDestinationSid]
0x180054470  call    ??$_Emplace_reallocate@AEBU_WINBIO_IDENTITY@@@?$vector@U_WINBIO_IDENTITY@@V?$allocator@U_WINBIO_IDENTITY@@@std@@@std@@AEAAPEAU_WINBIO_IDENTITY@@QEAU2@AEBU2@@Z; std::vector<_WINBIO_IDENTITY>::_Emplace_reallocate<_WINBIO_IDENTITY const &>(_WINBIO_IDENTITY * const,_WINBIO_IDENTITY const &)
0x180054475  nop
0x180054476  mov     rcx, [rsp+178h+pSourceSid]; hMem
0x18005447e  mov     [rsp+178h+pSourceSid], r15
0x180054486  test    rcx, rcx
0x180054489  jz      short loc_180054491
0x18005448b  call    cs:__imp_LocalFree
0x180054491  inc     esi
0x180054493  jmp     loc_1800542BB
0x180054498  mov     rcx, [rsp+178h+SRWLock]; SRWLock
0x1800544a0  test    rcx, rcx
0x1800544a3  jz      short loc_1800544AB
0x1800544a5  call    cs:__imp_ReleaseSRWLockShared
0x1800544ab  mov     rcx, [rsp+178h+var_108]
0x1800544b0  mov     rbx, rcx
0x1800544b3  mov     r14, qword ptr [rsp+178h+var_100]
0x1800544b8  cmp     rbx, r14
0x1800544bb  jz      loc_180054648
0x1800544c1  movups  xmm0, xmmword ptr [rbx]
0x1800544c4  movaps  [rsp+178h+pDestinationSid], xmm0
0x1800544cc  movups  xmm1, xmmword ptr [rbx+10h]
0x1800544d0  movaps  [rsp+178h+var_68], xmm1
0x1800544d8  movups  xmm0, xmmword ptr [rbx+20h]
0x1800544dc  movaps  [rsp+178h+var_58], xmm0
0x1800544e4  movups  xmm1, xmmword ptr [rbx+30h]
0x1800544e8  movaps  [rsp+178h+var_48], xmm1
0x1800544f0  movups  xmm0, xmmword ptr [rbx+3Ch]
0x1800544f4  movups  [rsp+178h+var_48+0Ch], xmm0
0x1800544fc  mov     [rsp+178h+var_118], r15b
0x180054501  lea     rax, [rsp+178h+var_118]
0x180054506  mov     [rsp+178h+phkResult], rax; int
0x18005450b  xor     r9d, r9d; bool
0x18005450e  xor     r8d, r8d; unsigned int
0x180054511  mov     edx, edi; unsigned int
0x180054513  lea     rcx, [rsp+178h+pDestinationSid]; this
0x18005451b  call    ?SetEnrolledFactorState@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@IK_NPEA_N@Z; CAccountManager::SetEnrolledFactorState(_WINBIO_IDENTITY *,uint,ulong,bool,bool *)
0x180054520  mov     esi, eax
0x180054522  test    eax, eax
0x180054524  jns     loc_1800545AA
0x18005452a  mov     rcx, [rsp+178h]; this
0x180054532  mov     r9d, eax; char *
0x180054535  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18005453c  mov     edx, 220h; void *
0x180054541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054546  nop
0x180054547  mov     rcx, [rsp+178h+var_108]
0x18005454c  test    rcx, rcx
0x18005454f  jz      short loc_180054585
0x180054551  mov     rax, qword ptr [rsp+178h+var_100+8]
0x180054559  sub     rax, rcx
0x18005455c  sar     rax, 2
0x180054560  mov     rdi, 86BCA1AF286BCA1Bh
0x18005456a  imul    rax, rdi
0x18005456e  imul    rdx, rax, 4Ch ; 'L'
0x180054572  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180054577  mov     [rsp+178h+var_108], r15
0x18005457c  xorps   xmm0, xmm0
0x18005457f  movdqu  [rsp+178h+var_100], xmm0
0x180054585  mov     rcx, [rsp+178h+hKey]; hKey
0x18005458a  test    rcx, rcx
0x18005458d  jz      short loc_180054596
0x18005458f  call    cs:__imp_RegCloseKey
0x180054595  nop
  ... truncated ...
```
