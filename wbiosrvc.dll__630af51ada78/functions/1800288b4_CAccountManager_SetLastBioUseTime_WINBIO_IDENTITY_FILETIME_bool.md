# CAccountManager::SetLastBioUseTime(_WINBIO_IDENTITY *,_FILETIME,bool)

- ea: `0x1800288b4`
- end: `0x180028ae2`
- name: `?SetLastBioUseTime@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@U_FILETIME@@_N@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct _WINBIO_IDENTITY *, struct _FILETIME, bool)`
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044e74`
- `0x180049970`
- `0x18004a2f0`
- `0x18008f340`
- `0x1800907a0`

## callees

- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x1800283dc`
- `0x1800288b4`
- `0x180028af0`
- `0x18002b2f8`
- `0x18002b7c0`
- `0x180035d78`
- `0x18005388c`
- `0x180058458`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028a6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028a6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a09`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a09`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028908`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028908`

## string_xrefs

- `0x18002898c`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180028a1b`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180028aae`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccountManager::SetLastBioUseTime(struct _WINBIO_IDENTITY *a1, struct _FILETIME a2, char a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int WinBioRegistryLocation; // eax
  __int64 v11; // rdx
  struct CAccountManager *v12; // rax
  const WCHAR *v13; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  __int64 v16; // rdx
  int dwOptions; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  struct _FILETIME v20; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp+1Fh] BYREF
  _BYTE v23[32]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(struct _FILETIME *)Data = a2;
  if ( !a1 )
  {
    v5 = -2147467261;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)v5,
      dwOptions);
    return v5;
  }
  if ( a1->Type != 3 || !IsValidSid(a1->Value.AccountSid.Data) )
  {
    v5 = -2147024809;
    goto LABEL_27;
  }
  v20 = 0;
  if ( !a3 && CAccountManager::GetLastBioUseTime(a1, &v20) >= 0 && (v20.dwHighDateTime || v20.dwLowDateTime) )
    return 0;
  std::wstring::wstring(v23, v6, v7, v8);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v23);
  v5 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    v11 = 1440;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
    goto LABEL_25;
  }
  std::wstring::append(v23, L"AccountInfo\\");
  WinBioRegistryLocation = IdentityToRegPath(a1, v23);
  v5 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    v11 = 1443;
    goto LABEL_14;
  }
  v12 = CAccountManager::Instance();
  winbio::lockable_object::lock_exclusive(v12, v21);
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
  {
    v16 = 1449;
  }
  else
  {
    Key = RegSetValueExW(hKey, L"LastBioUseTime", 0, 0xBu, Data, 8u);
    if ( !Key )
    {
      if ( hKey )
        RegCloseKey(hKey);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v21);
      v5 = 0;
      goto LABEL_25;
    }
    v16 = 1450;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v16,
         (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
         (const char *)Key,
         dwOptionsa);
  if ( hKey )
    RegCloseKey(hKey);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v21);
LABEL_25:
  std::wstring::_Tidy_deallocate(v23);
  return v5;
}

```

## disassembly

```asm
0x1800288b4  mov     [rsp-8+arg_10], rbx
0x1800288b9  mov     [rsp-8+arg_18], rdi
0x1800288be  push    rbp
0x1800288bf  lea     rbp, [rsp-57h]
0x1800288c4  sub     rsp, 0A0h
0x1800288cb  mov     rax, cs:__security_cookie
0x1800288d2  xor     rax, rsp
0x1800288d5  mov     [rbp+57h+var_10], rax
0x1800288d9  mov     bl, r8b
0x1800288dc  mov     rdi, rcx
0x1800288df  mov     qword ptr [rbp+57h+Data], rdx
0x1800288e3  test    rcx, rcx
0x1800288e6  jnz     short loc_1800288F2
0x1800288e8  mov     ebx, 80004003h
0x1800288ed  jmp     loc_180028AA7
0x1800288f2  cmp     dword ptr [rcx], 1
0x1800288f5  jz      loc_180028AA2
0x1800288fb  cmp     dword ptr [rcx], 3
0x1800288fe  jnz     loc_180028AA2
0x180028904  add     rcx, 8; pSid
0x180028908  call    cs:__imp_IsValidSid
0x18002890e  test    eax, eax
0x180028910  jz      loc_180028AA2
0x180028916  mov     qword ptr [rbp+57h+var_48.dwLowDateTime], 0
0x18002891e  test    bl, bl
0x180028920  jnz     short loc_180028945
0x180028922  lea     rdx, [rbp+57h+var_48]; struct _FILETIME *
0x180028926  mov     rcx, rdi; struct _WINBIO_IDENTITY *
0x180028929  call    ?GetLastBioUseTime@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@PEAU_FILETIME@@@Z; CAccountManager::GetLastBioUseTime(_WINBIO_IDENTITY *,_FILETIME *)
0x18002892e  test    eax, eax
0x180028930  js      short loc_180028945
0x180028932  cmp     [rbp+57h+var_48.dwHighDateTime], 0
0x180028936  jnz     short loc_18002893E
0x180028938  cmp     [rbp+57h+var_48.dwLowDateTime], 0
0x18002893c  jz      short loc_180028945
0x18002893e  xor     eax, eax
0x180028940  jmp     loc_180028AC1
0x180028945  lea     rcx, [rbp+57h+var_30]
0x180028949  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002894e  nop
0x18002894f  lea     rcx, [rbp+57h+var_30]
0x180028953  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180028958  mov     ebx, eax
0x18002895a  test    eax, eax
0x18002895c  jns     short loc_180028965
0x18002895e  mov     edx, 5A0h
0x180028963  jmp     short loc_18002898C
0x180028965  lea     rdx, aAccountinfo; "AccountInfo\\"
0x18002896c  lea     rcx, [rbp+57h+var_30]
0x180028970  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180028975  lea     rdx, [rbp+57h+var_30]
0x180028979  mov     rcx, rdi
0x18002897c  call    IdentityToRegPath
0x180028981  mov     ebx, eax
0x180028983  test    eax, eax
0x180028985  jns     short loc_1800289A4
0x180028987  mov     edx, 5A3h; void *
0x18002898c  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028993  mov     r9d, eax; char *
0x180028996  mov     rcx, [rbp+5Fh]; this
0x18002899a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002899f  jmp     loc_180028A97
0x1800289a4  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x1800289a9  lea     rdx, [rbp+57h+var_40]
0x1800289ad  mov     rcx, rax
0x1800289b0  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x1800289b5  mov     [rbp+57h+hKey], 0
0x1800289bd  lea     rcx, [rbp+57h+hKey]
0x1800289c1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800289c6  mov     r8, rax
0x1800289c9  lea     rcx, [rbp+57h+var_30]
0x1800289cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800289d2  mov     rdx, rax; lpSubKey
0x1800289d5  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x1800289de  mov     [rsp+0A0h+phkResult], r8; phkResult
0x1800289e3  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800289ec  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x1800289f4  mov     [rsp+0A0h+dwOptions], 0; unsigned int
0x1800289fc  xor     r9d, r9d; lpClass
0x1800289ff  xor     r8d, r8d; Reserved
0x180028a02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028a09  call    cs:__imp_RegCreateKeyExW
0x180028a0f  test    eax, eax
0x180028a11  jz      short loc_180028A47
0x180028a13  mov     edx, 5A9h; void *
0x180028a18  mov     r9d, eax; char *
0x180028a1b  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028a22  mov     rcx, [rbp+5Fh]; this
0x180028a26  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028a2b  mov     rcx, [rbp+57h+hKey]; hKey
0x180028a2f  test    rcx, rcx
0x180028a32  mov     ebx, eax
0x180028a34  jz      short loc_180028A3C
0x180028a36  call    cs:__imp_RegCloseKey
0x180028a3c  lea     rcx, [rbp+57h+var_40]; this
0x180028a40  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180028a45  jmp     short loc_180028A97
0x180028a47  mov     [rsp+0A0h+samDesired], 8; cbData
0x180028a4f  lea     rax, [rbp+57h+Data]
0x180028a53  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x180028a58  mov     r9d, 0Bh; dwType
0x180028a5e  xor     r8d, r8d; Reserved
0x180028a61  lea     rdx, aLastbiousetime; "LastBioUseTime"
0x180028a68  mov     rcx, [rbp+57h+hKey]; hKey
0x180028a6c  call    cs:__imp_RegSetValueExW
0x180028a72  test    eax, eax
0x180028a74  jz      short loc_180028A7D
0x180028a76  mov     edx, 5AAh
0x180028a7b  jmp     short loc_180028A18
0x180028a7d  mov     rcx, [rbp+57h+hKey]; hKey
0x180028a81  test    rcx, rcx
0x180028a84  jz      short loc_180028A8C
0x180028a86  call    cs:__imp_RegCloseKey
0x180028a8c  lea     rcx, [rbp+57h+var_40]; this
0x180028a90  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180028a95  xor     ebx, ebx
0x180028a97  lea     rcx, [rbp+57h+var_30]
0x180028a9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028aa0  jmp     short loc_180028ABF
0x180028aa2  mov     ebx, 80070057h
0x180028aa7  mov     rcx, [rbp+5Fh]; this
0x180028aab  mov     r9d, ebx; char *
0x180028aae  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028ab5  mov     edx, 58Eh; void *
0x180028aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028abf  mov     eax, ebx
0x180028ac1  mov     rcx, [rbp+57h+var_10]
0x180028ac5  xor     rcx, rsp; StackCookie
0x180028ac8  call    __security_check_cookie
0x180028acd  lea     r11, [rsp+0A0h+var_s0]
0x180028ad5  mov     rbx, [r11+20h]
0x180028ad9  mov     rdi, [r11+28h]
0x180028add  mov     rsp, r11
0x180028ae0  pop     rbp
0x180028ae1  retn
```
