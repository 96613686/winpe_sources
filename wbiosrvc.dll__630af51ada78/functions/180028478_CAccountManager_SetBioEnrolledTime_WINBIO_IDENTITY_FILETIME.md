# CAccountManager::SetBioEnrolledTime(_WINBIO_IDENTITY *,_FILETIME)

- ea: `0x180028478`
- end: `0x1800286ab`
- name: `?SetBioEnrolledTime@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@U_FILETIME@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(struct _WINBIO_IDENTITY *, struct _FILETIME)`
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
- `0x180028478`
- `0x1800286b4`
- `0x180028af0`
- `0x18002b2f8`
- `0x18002b7c0`
- `0x180035d78`
- `0x18005388c`
- `0x180058458`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002862c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002862c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028650`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800285ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800285ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800285c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800285c9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800284c6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800284c6`

## string_xrefs

- `0x18002854c`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180028611`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180028679`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccountManager::SetBioEnrolledTime(struct _WINBIO_IDENTITY *a1, struct _FILETIME a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int BioEnrolledTime; // esi
  __int64 v6; // r8
  __int64 v7; // r9
  int WinBioRegistryLocation; // eax
  __int64 v9; // rdx
  struct CAccountManager *v10; // rax
  const WCHAR *v11; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  __int64 v14; // rdx
  int dwOptions; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  struct _FILETIME v19; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp+7h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(struct _FILETIME *)Data = a2;
  if ( !a1 )
  {
    v3 = -2147467261;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x546,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)v3,
      dwOptions);
    return v3;
  }
  if ( a1->Type != 3 || !IsValidSid(a1->Value.AccountSid.Data) )
  {
    v3 = -2147024809;
    goto LABEL_26;
  }
  v19 = 0;
  BioEnrolledTime = CAccountManager::GetBioEnrolledTime(a1, &v19);
  if ( BioEnrolledTime != -2147024894 && (v19.dwHighDateTime || v19.dwLowDateTime) )
    return BioEnrolledTime;
  std::wstring::wstring(v22, v4, v6, v7);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v22);
  v3 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation >= 0 )
  {
    std::wstring::append(v22, L"AccountInfo\\");
    WinBioRegistryLocation = IdentityToRegPath(a1, v22);
    v3 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation < 0 )
    {
      v9 = 1364;
      goto LABEL_12;
    }
    v10 = CAccountManager::Instance();
    winbio::lockable_object::lock_exclusive(v10, v20);
    hKey = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
    if ( Key )
    {
      v14 = 1370;
LABEL_17:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v14,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
             (const char *)Key,
             dwOptionsa);
      if ( hKey )
        RegCloseKey(hKey);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v20);
      goto LABEL_20;
    }
    Key = RegSetValueExW(hKey, L"BioEnrolledTime", 0, 0xBu, Data, 8u);
    if ( Key )
    {
      v14 = 1371;
      goto LABEL_17;
    }
    if ( hKey )
      RegCloseKey(hKey);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v20);
    std::wstring::_Tidy_deallocate(v22);
    return BioEnrolledTime;
  }
  v9 = 1361;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
    (const char *)(unsigned int)WinBioRegistryLocation,
    dwOptions);
LABEL_20:
  std::wstring::_Tidy_deallocate(v22);
  return v3;
}

```

## disassembly

```asm
0x180028478  mov     [rsp-8+arg_10], rbx
0x18002847d  push    rbp
0x18002847e  push    rsi
0x18002847f  push    rdi
0x180028480  lea     rbp, [rsp-47h]
0x180028485  sub     rsp, 0A0h
0x18002848c  mov     rax, cs:__security_cookie
0x180028493  xor     rax, rsp
0x180028496  mov     [rbp+57h+var_20], rax
0x18002849a  mov     rdi, rcx
0x18002849d  mov     qword ptr [rbp+57h+Data], rdx
0x1800284a1  test    rcx, rcx
0x1800284a4  jnz     short loc_1800284B0
0x1800284a6  mov     ebx, 80004003h
0x1800284ab  jmp     loc_180028672
0x1800284b0  cmp     dword ptr [rcx], 1
0x1800284b3  jz      loc_18002866D
0x1800284b9  cmp     dword ptr [rcx], 3
0x1800284bc  jnz     loc_18002866D
0x1800284c2  add     rcx, 8; pSid
0x1800284c6  call    cs:__imp_IsValidSid
0x1800284cc  test    eax, eax
0x1800284ce  jz      loc_18002866D
0x1800284d4  mov     qword ptr [rbp+57h+var_58.dwLowDateTime], 0
0x1800284dc  lea     rdx, [rbp+57h+var_58]; struct _FILETIME *
0x1800284e0  mov     rcx, rdi; struct _WINBIO_IDENTITY *
0x1800284e3  call    ?GetBioEnrolledTime@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@PEAU_FILETIME@@@Z; CAccountManager::GetBioEnrolledTime(_WINBIO_IDENTITY *,_FILETIME *)
0x1800284e8  mov     esi, eax
0x1800284ea  cmp     eax, 80070002h
0x1800284ef  jz      short loc_180028505
0x1800284f1  cmp     [rbp+57h+var_58.dwHighDateTime], 0
0x1800284f5  jnz     loc_180028669
0x1800284fb  cmp     [rbp+57h+var_58.dwLowDateTime], 0
0x1800284ff  jnz     loc_180028669
0x180028505  lea     rcx, [rbp+57h+var_40]
0x180028509  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002850e  nop
0x18002850f  lea     rcx, [rbp+57h+var_40]
0x180028513  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180028518  mov     ebx, eax
0x18002851a  test    eax, eax
0x18002851c  jns     short loc_180028525
0x18002851e  mov     edx, 551h
0x180028523  jmp     short loc_18002854C
0x180028525  lea     rdx, aAccountinfo; "AccountInfo\\"
0x18002852c  lea     rcx, [rbp+57h+var_40]
0x180028530  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180028535  lea     rdx, [rbp+57h+var_40]
0x180028539  mov     rcx, rdi
0x18002853c  call    IdentityToRegPath
0x180028541  mov     ebx, eax
0x180028543  test    eax, eax
0x180028545  jns     short loc_180028564
0x180028547  mov     edx, 554h; void *
0x18002854c  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028553  mov     r9d, eax; char *
0x180028556  mov     rcx, [rbp+5Fh]; this
0x18002855a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002855f  jmp     loc_18002863C
0x180028564  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180028569  lea     rdx, [rbp+57h+var_50]
0x18002856d  mov     rcx, rax
0x180028570  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x180028575  mov     [rbp+57h+hKey], 0
0x18002857d  lea     rcx, [rbp+57h+hKey]
0x180028581  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180028586  mov     r8, rax
0x180028589  lea     rcx, [rbp+57h+var_40]
0x18002858d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028592  mov     rdx, rax; lpSubKey
0x180028595  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18002859e  mov     [rsp+0B0h+phkResult], r8; phkResult
0x1800285a3  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800285ac  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x1800285b4  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x1800285bc  xor     r9d, r9d; lpClass
0x1800285bf  xor     r8d, r8d; Reserved
0x1800285c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800285c9  call    cs:__imp_RegCreateKeyExW
0x1800285cf  test    eax, eax
0x1800285d1  jz      short loc_1800285DA
0x1800285d3  mov     edx, 55Ah
0x1800285d8  jmp     short loc_18002860E
0x1800285da  mov     [rsp+0B0h+samDesired], 8; cbData
0x1800285e2  lea     rax, [rbp+57h+Data]
0x1800285e6  mov     qword ptr [rsp+0B0h+dwOptions], rax; unsigned int
0x1800285eb  mov     r9d, 0Bh; dwType
0x1800285f1  xor     r8d, r8d; Reserved
0x1800285f4  lea     rdx, aBioenrolledtim; "BioEnrolledTime"
0x1800285fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800285ff  call    cs:__imp_RegSetValueExW
0x180028605  test    eax, eax
0x180028607  jz      short loc_180028647
0x180028609  mov     edx, 55Bh; void *
0x18002860e  mov     r9d, eax; char *
0x180028611  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028618  mov     rcx, [rbp+5Fh]; this
0x18002861c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028621  mov     rcx, [rbp+57h+hKey]; hKey
0x180028625  test    rcx, rcx
0x180028628  mov     ebx, eax
0x18002862a  jz      short loc_180028632
0x18002862c  call    cs:__imp_RegCloseKey
0x180028632  lea     rcx, [rbp+57h+var_50]; this
0x180028636  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18002863b  nop
0x18002863c  lea     rcx, [rbp+57h+var_40]
0x180028640  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028645  jmp     short loc_18002868A
0x180028647  mov     rcx, [rbp+57h+hKey]; hKey
0x18002864b  test    rcx, rcx
0x18002864e  jz      short loc_180028656
0x180028650  call    cs:__imp_RegCloseKey
0x180028656  lea     rcx, [rbp+57h+var_50]; this
0x18002865a  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18002865f  nop
0x180028660  lea     rcx, [rbp+57h+var_40]
0x180028664  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028669  mov     eax, esi
0x18002866b  jmp     short loc_18002868C
0x18002866d  mov     ebx, 80070057h
0x180028672  mov     rcx, [rbp+5Fh]; this
0x180028676  mov     r9d, ebx; char *
0x180028679  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180028680  mov     edx, 546h; void *
0x180028685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002868a  mov     eax, ebx
0x18002868c  mov     rcx, [rbp+57h+var_20]
0x180028690  xor     rcx, rsp; StackCookie
0x180028693  call    __security_check_cookie
0x180028698  mov     rbx, [rsp+0B0h+arg_10]
0x1800286a0  add     rsp, 0A0h
0x1800286a7  pop     rdi
0x1800286a8  pop     rsi
0x1800286a9  pop     rbp
0x1800286aa  retn
```
