# winbio::SetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong)

- ea: `0x1800be44c`
- end: `0x1800be5e0`
- name: `?SetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@K@Z`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041c14`
- `0x180045044`
- `0x180073538`
- `0x180085b00`

## callees

- `0x180011d90`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180035d78`
- `0x18005388c`
- `0x180068f60`
- `0x1800be39c`
- `0x1800be44c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be5ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be5ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800be58f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800be58f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800be501`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800be501`

## string_xrefs

- `0x1800be497`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be510`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be55d`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::SetBioRegKeyValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  int WinBioRegistryLocation; // eax
  unsigned int v6; // ebx
  const WCHAR *v7; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  __int64 v10; // rdx
  int RegKeyPathFromRegKeyName; // eax
  int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  HKEY hKey; // [rsp+50h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp+1Fh] BYREF
  LPCWSTR lpValueName; // [rsp+60h] [rbp+27h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v4 = a2;
  *(_DWORD *)Data = a3;
  std::wstring::wstring(v18, a2, a3, a4);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v18);
  v6 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
    goto LABEL_15;
  }
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
  {
    v10 = 771;
LABEL_5:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
           (const char *)Key,
           dwOptionsa);
    goto LABEL_6;
  }
  lpValueName = (LPCWSTR)byte_1800DC1E0;
  RegKeyPathFromRegKeyName = winbio::GetRegKeyPathFromRegKeyName(v4, &lpValueName);
  v6 = RegKeyPathFromRegKeyName;
  if ( RegKeyPathFromRegKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)RegKeyPathFromRegKeyName,
      dwOptionsa);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  Key = RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
  if ( Key )
  {
    v10 = 775;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v6 = 0;
LABEL_15:
  std::wstring::_Tidy_deallocate(v18);
  return v6;
}

```

## disassembly

```asm
0x1800be44c  mov     [rsp-8+arg_0], rbx
0x1800be451  mov     [rsp-8+arg_18], rdi
0x1800be456  push    rbp
0x1800be457  lea     rbp, [rsp-57h]
0x1800be45c  sub     rsp, 90h
0x1800be463  mov     rax, cs:__security_cookie
0x1800be46a  xor     rax, rsp
0x1800be46d  mov     [rbp+57h+var_8], rax
0x1800be471  mov     edi, edx
0x1800be473  mov     dword ptr [rbp+57h+Data], r8d
0x1800be477  lea     rcx, [rbp+57h+var_28]
0x1800be47b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800be480  nop
0x1800be481  lea     rcx, [rbp+57h+var_28]
0x1800be485  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800be48a  mov     ebx, eax
0x1800be48c  test    eax, eax
0x1800be48e  jns     short loc_1800BE4AD
0x1800be490  mov     rcx, [rbp+5Fh]; this
0x1800be494  mov     r9d, eax; char *
0x1800be497  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be49e  mov     edx, 2FFh; void *
0x1800be4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be4a8  jmp     loc_1800BE5B4
0x1800be4ad  mov     [rbp+57h+hKey], 0
0x1800be4b5  lea     rcx, [rbp+57h+hKey]
0x1800be4b9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800be4be  mov     r8, rax
0x1800be4c1  lea     rcx, [rbp+57h+var_28]
0x1800be4c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800be4ca  mov     rdx, rax; lpSubKey
0x1800be4cd  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800be4d6  mov     [rsp+90h+phkResult], r8; phkResult
0x1800be4db  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800be4e4  mov     [rsp+90h+samDesired], 0F003Fh; samDesired
0x1800be4ec  mov     [rsp+90h+dwOptions], 0; int
0x1800be4f4  xor     r9d, r9d; lpClass
0x1800be4f7  xor     r8d, r8d; Reserved
0x1800be4fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be501  call    cs:__imp_RegCreateKeyExW
0x1800be507  test    eax, eax
0x1800be509  jz      short loc_1800BE53A
0x1800be50b  mov     edx, 303h; void *
0x1800be510  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be517  mov     r9d, eax; char *
0x1800be51a  mov     rcx, [rbp+5Fh]; this
0x1800be51e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800be523  mov     ebx, eax
0x1800be525  mov     rcx, [rbp+57h+hKey]; hKey
0x1800be529  test    rcx, rcx
0x1800be52c  jz      loc_1800BE5B4
0x1800be532  call    cs:__imp_RegCloseKey
0x1800be538  jmp     short loc_1800BE5B4
0x1800be53a  lea     rax, byte_1800DC1E0
0x1800be541  mov     [rbp+57h+lpValueName], rax
0x1800be545  lea     rdx, [rbp+57h+lpValueName]
0x1800be549  mov     ecx, edi
0x1800be54b  call    ?GetRegKeyPathFromRegKeyName@winbio@@YAJW4RegKeyName@1@PEAPEBG@Z; winbio::GetRegKeyPathFromRegKeyName(winbio::RegKeyName,ushort const * *)
0x1800be550  mov     ebx, eax
0x1800be552  test    eax, eax
0x1800be554  jns     short loc_1800BE570
0x1800be556  mov     rcx, [rbp+5Fh]; this
0x1800be55a  mov     r9d, eax; char *
0x1800be55d  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be564  mov     edx, 306h; void *
0x1800be569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be56e  jmp     short loc_1800BE525
0x1800be570  mov     r9d, 4; dwType
0x1800be576  mov     [rsp+90h+samDesired], r9d; cbData
0x1800be57b  lea     rax, [rbp+57h+Data]
0x1800be57f  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x1800be584  xor     r8d, r8d; Reserved
0x1800be587  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x1800be58b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800be58f  call    cs:__imp_RegSetValueExW
0x1800be595  test    eax, eax
0x1800be597  jz      short loc_1800BE5A3
0x1800be599  mov     edx, 307h
0x1800be59e  jmp     loc_1800BE510
0x1800be5a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800be5a7  test    rcx, rcx
0x1800be5aa  jz      short loc_1800BE5B2
0x1800be5ac  call    cs:__imp_RegCloseKey
0x1800be5b2  xor     ebx, ebx
0x1800be5b4  lea     rcx, [rbp+57h+var_28]
0x1800be5b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be5bd  mov     eax, ebx
0x1800be5bf  mov     rcx, [rbp+57h+var_8]
0x1800be5c3  xor     rcx, rsp; StackCookie
0x1800be5c6  call    __security_check_cookie
0x1800be5cb  lea     r11, [rsp+90h+var_s0]
0x1800be5d3  mov     rbx, [r11+10h]
0x1800be5d7  mov     rdi, [r11+28h]
0x1800be5db  mov     rsp, r11
0x1800be5de  pop     rbp
0x1800be5df  retn
```
