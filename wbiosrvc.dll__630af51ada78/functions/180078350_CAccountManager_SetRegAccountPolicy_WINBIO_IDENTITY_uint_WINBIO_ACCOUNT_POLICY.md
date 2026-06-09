# CAccountManager::SetRegAccountPolicy(_WINBIO_IDENTITY *,uint,_WINBIO_ACCOUNT_POLICY *)

- ea: `0x180078350`
- end: `0x18007864e`
- name: `?SetRegAccountPolicy@CAccountManager@@AEAAJPEAU_WINBIO_IDENTITY@@IPEAU_WINBIO_ACCOUNT_POLICY@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(CAccountManager *__hidden this, struct _WINBIO_IDENTITY *, unsigned int, struct _WINBIO_ACCOUNT_POLICY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007824c`

## callees

- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180035d78`
- `0x18003f80c`
- `0x18005388c`
- `0x180058458`
- `0x180068f60`
- `0x180077660`
- `0x180077ee8`
- `0x180078350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007846c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007846c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800784a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800785e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800784a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800785e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007843b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078575`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007843b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078575`

## string_xrefs

- `0x1800783c8`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x18007844a`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800784db`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180078584`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAccountManager::SetRegAccountPolicy(
        CAccountManager *this,
        struct _WINBIO_IDENTITY *a2,
        __int64 a3,
        struct _WINBIO_ACCOUNT_POLICY *a4)
{
  unsigned int v5; // r14d
  int WinBioRegistryLocation; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  PHKEY phkResult; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  const WCHAR *v20; // rax
  PHKEY v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rdx
  int dwOptions; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-79h]
  DWORD dwDisposition; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  BYTE v30[8]; // [rsp+60h] [rbp-39h] BYREF
  HKEY v31; // [rsp+68h] [rbp-31h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v33[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v34[32]; // [rsp+98h] [rbp-1h] BYREF
  _BYTE v35[32]; // [rsp+B8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a3;
  std::wstring::wstring(v34, a2, a3, a4);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v34);
  v8 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    v9 = 1056;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
    goto LABEL_28;
  }
  std::wstring::append(v34, L"AccountInfo\\");
  WinBioRegistryLocation = IdentityToRegPath(a2, v34);
  v8 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation < 0 )
  {
    v9 = 1059;
    goto LABEL_5;
  }
  hKey = 0;
  dwDisposition = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
  v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0xF003Fu, 0, phkResult, &dwDisposition);
  if ( v12 )
  {
    v16 = 1063;
LABEL_8:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v16,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
           (const char *)v12,
           dwOptionsa);
    goto LABEL_9;
  }
  if ( dwDisposition == 1 )
  {
    *(_DWORD *)Data = 0;
    v12 = RegSetValueExW(hKey, L"EnrolledFactors", 0, 4u, Data, 4u);
    if ( v12 )
    {
      v16 = 1071;
      goto LABEL_8;
    }
  }
  std::wstring::wstring(v33, v13, v14, v15);
  v17 = CAccountManager::FactorToStringFactor(v5, v33);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x436,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)v17,
      dwOptionsa);
LABEL_16:
    std::wstring::_Tidy_deallocate(v33);
LABEL_9:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  v19 = std::operator+<unsigned short>(v35, v18, v33);
  std::wstring::operator=(v33, v19);
  std::wstring::_Tidy_deallocate(v35);
  v31 = 0;
  dwDisposition = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v31);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
  v22 = RegCreateKeyExW(hKey, v20, 0, 0, 0, 0xF003Fu, 0, v21, &dwDisposition);
  if ( v22 )
  {
    v23 = 1083;
    goto LABEL_19;
  }
  *(_DWORD *)v30 = a4->AntiSpoofBehavior != WINBIO_ANTI_SPOOF_DISABLE;
  v22 = RegSetValueExW(v31, L"AntiSpoofing", 0, 4u, v30, 4u);
  if ( v22 )
  {
    v23 = 1094;
LABEL_19:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v23,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
           (const char *)v22,
           dwOptionsb);
    if ( v31 )
      RegCloseKey(v31);
    goto LABEL_16;
  }
  if ( v31 )
    RegCloseKey(v31);
  std::wstring::_Tidy_deallocate(v33);
  if ( hKey )
    RegCloseKey(hKey);
  v8 = 0;
LABEL_28:
  std::wstring::_Tidy_deallocate(v34);
  return v8;
}

```

## disassembly

```asm
0x180078350  mov     [rsp-8+arg_0], rbx
0x180078355  mov     [rsp-8+arg_18], rsi
0x18007835a  push    rbp
0x18007835b  push    rdi
0x18007835c  push    r14
0x18007835e  lea     rbp, [rsp-47h]
0x180078363  sub     rsp, 0E0h
0x18007836a  mov     rax, cs:__security_cookie
0x180078371  xor     rax, rsp
0x180078374  mov     [rbp+57h+var_18], rax
0x180078378  mov     rsi, r9
0x18007837b  mov     r14d, r8d
0x18007837e  mov     rdi, rdx
0x180078381  lea     rcx, [rbp+57h+var_58]
0x180078385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007838a  nop
0x18007838b  lea     rcx, [rbp+57h+var_58]
0x18007838f  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180078394  mov     ebx, eax
0x180078396  test    eax, eax
0x180078398  jns     short loc_1800783A1
0x18007839a  mov     edx, 420h
0x18007839f  jmp     short loc_1800783C8
0x1800783a1  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800783a8  lea     rcx, [rbp+57h+var_58]
0x1800783ac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800783b1  lea     rdx, [rbp+57h+var_58]
0x1800783b5  mov     rcx, rdi
0x1800783b8  call    IdentityToRegPath
0x1800783bd  mov     ebx, eax
0x1800783bf  test    eax, eax
0x1800783c1  jns     short loc_1800783E0
0x1800783c3  mov     edx, 423h; void *
0x1800783c8  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800783cf  mov     r9d, eax; char *
0x1800783d2  mov     rcx, [rbp+5Fh]; this
0x1800783d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800783db  jmp     loc_18007861F
0x1800783e0  mov     [rbp+57h+hKey], 0
0x1800783e8  mov     [rbp+57h+dwDisposition], 0
0x1800783ef  lea     rcx, [rbp+57h+hKey]
0x1800783f3  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800783f8  mov     r8, rax
0x1800783fb  lea     rcx, [rbp+57h+var_58]
0x1800783ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078404  mov     rdx, rax; lpSubKey
0x180078407  lea     rax, [rbp+57h+dwDisposition]
0x18007840b  mov     [rsp+0F0h+lpdwDisposition], rax; lpdwDisposition
0x180078410  mov     [rsp+0F0h+phkResult], r8; phkResult
0x180078415  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007841e  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x180078426  mov     [rsp+0F0h+dwOptions], 0; int
0x18007842e  xor     r9d, r9d; lpClass
0x180078431  xor     r8d, r8d; Reserved
0x180078434  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007843b  call    cs:__imp_RegCreateKeyExW
0x180078441  test    eax, eax
0x180078443  jz      short loc_180078477
0x180078445  mov     edx, 427h; void *
0x18007844a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180078451  mov     r9d, eax; char *
0x180078454  mov     rcx, [rbp+5Fh]; this
0x180078458  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007845d  mov     ebx, eax
0x18007845f  mov     rcx, [rbp+57h+hKey]; hKey
0x180078463  test    rcx, rcx
0x180078466  jz      loc_18007861F
0x18007846c  call    cs:__imp_RegCloseKey
0x180078472  jmp     loc_18007861F
0x180078477  mov     edi, 4
0x18007847c  cmp     [rbp+57h+dwDisposition], 1
0x180078480  jnz     short loc_1800784B8
0x180078482  mov     dword ptr [rbp+57h+Data], 0
0x180078489  mov     [rsp+0F0h+samDesired], edi; cbData
0x18007848d  lea     rax, [rbp+57h+Data]
0x180078491  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x180078496  mov     r9d, edi; dwType
0x180078499  xor     r8d, r8d; Reserved
0x18007849c  lea     rdx, aEnrolledfactor; "EnrolledFactors"
0x1800784a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800784a7  call    cs:__imp_RegSetValueExW
0x1800784ad  test    eax, eax
0x1800784af  jz      short loc_1800784B8
0x1800784b1  mov     edx, 42Fh
0x1800784b6  jmp     short loc_18007844A
0x1800784b8  lea     rcx, [rbp+57h+var_78]
0x1800784bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800784c1  nop
0x1800784c2  lea     rdx, [rbp+57h+var_78]
0x1800784c6  mov     ecx, r14d
0x1800784c9  call    ?FactorToStringFactor@CAccountManager@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CAccountManager::FactorToStringFactor(uint,std::wstring &)
0x1800784ce  mov     ebx, eax
0x1800784d0  test    eax, eax
0x1800784d2  jns     short loc_1800784FB
0x1800784d4  mov     rcx, [rbp+5Fh]; this
0x1800784d8  mov     r9d, eax; char *
0x1800784db  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800784e2  mov     edx, 436h; void *
0x1800784e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800784ec  nop
0x1800784ed  lea     rcx, [rbp+57h+var_78]
0x1800784f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800784f6  jmp     loc_18007845F
0x1800784fb  lea     r8, [rbp+57h+var_78]
0x1800784ff  lea     rcx, [rbp+57h+var_38]
0x180078503  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180078508  mov     rdx, rax
0x18007850b  lea     rcx, [rbp+57h+var_78]
0x18007850f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180078514  lea     rcx, [rbp+57h+var_38]
0x180078518  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007851d  mov     [rbp+57h+var_88], 0
0x180078525  mov     [rbp+57h+dwDisposition], 0
0x18007852c  lea     rcx, [rbp+57h+var_88]
0x180078530  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180078535  mov     r8, rax
0x180078538  lea     rcx, [rbp+57h+var_78]
0x18007853c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078541  mov     rdx, rax; lpSubKey
0x180078544  lea     rax, [rbp+57h+dwDisposition]
0x180078548  mov     [rsp+0F0h+lpdwDisposition], rax; lpdwDisposition
0x18007854d  mov     [rsp+0F0h+phkResult], r8; phkResult
0x180078552  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007855b  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x180078563  mov     [rsp+0F0h+dwOptions], 0; unsigned int
0x18007856b  xor     r9d, r9d; lpClass
0x18007856e  xor     r8d, r8d; Reserved
0x180078571  mov     rcx, [rbp+57h+hKey]; hKey
0x180078575  call    cs:__imp_RegCreateKeyExW
0x18007857b  test    eax, eax
0x18007857d  jz      short loc_1800785B1
0x18007857f  mov     edx, 43Bh; void *
0x180078584  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18007858b  mov     r9d, eax; char *
0x18007858e  mov     rcx, [rbp+5Fh]; this
0x180078592  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180078597  mov     ebx, eax
0x180078599  mov     rcx, [rbp+57h+var_88]; hKey
0x18007859d  test    rcx, rcx
0x1800785a0  jz      loc_1800784ED
0x1800785a6  call    cs:__imp_RegCloseKey
0x1800785ac  jmp     loc_1800784ED
0x1800785b1  mov     dword ptr [rbp+57h+var_90], 1
0x1800785b8  cmp     dword ptr [rsi+4Ch], 0
0x1800785bc  jnz     short loc_1800785C5
0x1800785be  mov     dword ptr [rbp+57h+var_90], 0
0x1800785c5  mov     [rsp+0F0h+samDesired], edi; cbData
0x1800785c9  lea     rax, [rbp+57h+var_90]
0x1800785cd  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x1800785d2  mov     r9d, edi; dwType
0x1800785d5  xor     r8d, r8d; Reserved
0x1800785d8  lea     rdx, aAntispoofing; "AntiSpoofing"
0x1800785df  mov     rcx, [rbp+57h+var_88]; hKey
0x1800785e3  call    cs:__imp_RegSetValueExW
0x1800785e9  test    eax, eax
0x1800785eb  jz      short loc_1800785F4
0x1800785ed  mov     edx, 446h
0x1800785f2  jmp     short loc_180078584
0x1800785f4  mov     rcx, [rbp+57h+var_88]; hKey
0x1800785f8  test    rcx, rcx
0x1800785fb  jz      short loc_180078604
0x1800785fd  call    cs:__imp_RegCloseKey
0x180078603  nop
0x180078604  lea     rcx, [rbp+57h+var_78]
0x180078608  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007860d  nop
0x18007860e  mov     rcx, [rbp+57h+hKey]; hKey
0x180078612  test    rcx, rcx
0x180078615  jz      short loc_18007861D
0x180078617  call    cs:__imp_RegCloseKey
0x18007861d  xor     ebx, ebx
0x18007861f  lea     rcx, [rbp+57h+var_58]
0x180078623  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078628  mov     eax, ebx
0x18007862a  mov     rcx, [rbp+57h+var_18]
0x18007862e  xor     rcx, rsp; StackCookie
0x180078631  call    __security_check_cookie
0x180078636  lea     r11, [rsp+0F0h+var_10]
0x18007863e  mov     rbx, [r11+20h]
0x180078642  mov     rsi, [r11+38h]
0x180078646  mov     rsp, r11
0x180078649  pop     r14
0x18007864b  pop     rdi
0x18007864c  pop     rbp
0x18007864d  retn
```
