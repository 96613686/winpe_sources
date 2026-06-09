# winbio::UpdateFactorsRegKey(_WINBIO_IDENTITY *,uint,winbio::FactorKey,bool)

- ea: `0x1800528a0`
- end: `0x180052c24`
- name: `?UpdateFactorsRegKey@winbio@@YAJPEAU_WINBIO_IDENTITY@@IW4FactorKey@1@_N@Z`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800782e4`

## callees

- `0x18000367c`
- `0x18000986c`
- `0x180011d90`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180016430`
- `0x1800165d8`
- `0x180016650`
- `0x180033378`
- `0x180035d78`
- `0x1800488d0`
- `0x180051284`
- `0x1800528a0`
- `0x1800530c4`
- `0x18005388c`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052b00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052b00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180052ab1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180052ab1`

## string_xrefs

- `0x1800528e2`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x18005290e`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x18005294a`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800529b0`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180052b3a`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180052b64`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180052b9b`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winbio::UpdateFactorsRegKey(WCHAR *a1, unsigned int a2)
{
  int Identities; // ebx
  int v6; // eax
  int FactorsForSID; // edi
  struct _WINBIO_IDENTITY *v8; // rdx
  bool v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  WCHAR **v12; // rbx
  WCHAR **v13; // r14
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int RegPathForSID; // eax
  const WCHAR *v18; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  int KeyValueFromFactorKey; // eax
  __int64 v22; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-49h]
  BYTE Data[8]; // [rsp+50h] [rbp-19h] BYREF
  void *v25; // [rsp+58h] [rbp-11h] BYREF
  WCHAR **v26; // [rsp+60h] [rbp-9h]
  char *v27; // [rsp+68h] [rbp-1h]
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  LPCWSTR lpValueName; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  lpValueName = a1;
  if ( !a1 )
  {
    Identities = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)0x80004003LL,
      dwOptions);
    return (unsigned int)Identities;
  }
  v6 = winbio::ValidateFactor((winbio *)a2, a2);
  FactorsForSID = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    return (unsigned int)FactorsForSID;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v25);
  if ( *(_DWORD *)a1 == 1 )
  {
    LOBYTE(v8) = 1;
    Identities = winbio::ValidateIdentity((winbio *)a1, v8, v9);
    if ( Identities < 0 )
    {
      v10 = 707;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
        (const char *)(unsigned int)Identities,
        dwOptions);
LABEL_11:
      if ( v25 )
        std::_Deallocate<16>(v25, (v27 - (_BYTE *)v25) & 0xFFFFFFFFFFFFFFF8uLL);
      return (unsigned int)Identities;
    }
    Identities = winbio::GetIdentities((__int64)&v25);
    if ( Identities < 0 )
    {
      v10 = 708;
      goto LABEL_10;
    }
LABEL_24:
    v12 = (WCHAR **)v25;
    v13 = v26;
    while ( 1 )
    {
      if ( v12 == v13 )
      {
        if ( v25 )
          std::_Deallocate<16>(v25, (v27 - (_BYTE *)v25) & 0xFFFFFFFFFFFFFFF8uLL);
        return 0;
      }
      *(_DWORD *)Data = 0;
      FactorsForSID = winbio::GetFactorsForSID(*v12, 2, Data);
      if ( FactorsForSID < 0 )
      {
        v11 = 723;
        goto LABEL_18;
      }
      *(_DWORD *)Data |= a2;
      std::wstring::wstring(v30, v14, v15, v16);
      RegPathForSID = winbio::GetRegPathForSID(*v12, v30);
      FactorsForSID = RegPathForSID;
      if ( RegPathForSID < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E4,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
          (const char *)(unsigned int)RegPathForSID,
          dwOptions);
LABEL_42:
        std::wstring::_Tidy_deallocate(v30);
        goto LABEL_19;
      }
      hKey = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
      Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        break;
      lpValueName = (LPCWSTR)byte_1800DC1E0;
      KeyValueFromFactorKey = winbio::GetKeyValueFromFactorKey(2, &lpValueName);
      FactorsForSID = KeyValueFromFactorKey;
      if ( KeyValueFromFactorKey < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
          (const char *)(unsigned int)KeyValueFromFactorKey,
          dwOptions);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_42;
      }
      Key = RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
      if ( Key )
      {
        v22 = 747;
        goto LABEL_38;
      }
      if ( hKey )
        RegCloseKey(hKey);
      std::wstring::_Tidy_deallocate(v30);
      ++v12;
    }
    v22 = 743;
LABEL_38:
    Identities = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v22,
                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
                   (const char *)Key,
                   dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::_Tidy_deallocate(v30);
    goto LABEL_11;
  }
  if ( *(_DWORD *)a1 == 3 )
  {
    FactorsForSID = winbio::ValidateIdentity((winbio *)a1, 0, v9);
    if ( FactorsForSID < 0 )
    {
      v11 = 712;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
        (const char *)(unsigned int)FactorsForSID,
        dwOptions);
LABEL_19:
      if ( v25 )
        std::_Deallocate<16>(v25, (v27 - (_BYTE *)v25) & 0xFFFFFFFFFFFFFFF8uLL);
      return (unsigned int)FactorsForSID;
    }
    if ( v26 == (WCHAR **)v27 )
      std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(&v25, v26, &lpValueName);
    else
      *v26++ = a1;
    goto LABEL_24;
  }
  if ( v25 )
    std::_Deallocate<16>(v25, (v27 - (_BYTE *)v25) & 0xFFFFFFFFFFFFFFF8uLL);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800528a0  mov     [rsp-8+arg_10], rbx
0x1800528a5  mov     [rsp-8+arg_18], rsi
0x1800528aa  push    rbp
0x1800528ab  push    rdi
0x1800528ac  push    r14
0x1800528ae  lea     rbp, [rsp-47h]
0x1800528b3  sub     rsp, 0B0h
0x1800528ba  mov     rax, cs:__security_cookie
0x1800528c1  xor     rax, rsp
0x1800528c4  mov     [rbp+57h+var_20], rax
0x1800528c8  mov     esi, edx
0x1800528ca  mov     rbx, rcx
0x1800528cd  mov     [rbp+57h+lpValueName], rcx
0x1800528d1  test    rcx, rcx
0x1800528d4  jnz     short loc_1800528FA
0x1800528d6  mov     rcx, [rbp+5Fh]; this
0x1800528da  mov     ebx, 80004003h
0x1800528df  mov     r9d, ebx; char *
0x1800528e2  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800528e9  mov     edx, 2BDh; void *
0x1800528ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800528f3  mov     eax, ebx
0x1800528f5  jmp     loc_180052C00
0x1800528fa  mov     ecx, esi; this
0x1800528fc  call    ?ValidateFactor@winbio@@YAJI@Z; winbio::ValidateFactor(uint)
0x180052901  mov     edi, eax
0x180052903  test    eax, eax
0x180052905  jns     short loc_180052926
0x180052907  mov     rcx, [rbp+5Fh]; this
0x18005290b  mov     r9d, eax; char *
0x18005290e  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180052915  mov     edx, 2BEh; void *
0x18005291a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005291f  mov     eax, edi
0x180052921  jmp     loc_180052C00
0x180052926  lea     rcx, [rbp+57h+var_68]
0x18005292a  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18005292f  nop
0x180052930  cmp     dword ptr [rbx], 1
0x180052933  jnz     short loc_180052992
0x180052935  mov     dl, 1; struct _WINBIO_IDENTITY *
0x180052937  mov     rcx, rbx; this
0x18005293a  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x18005293f  mov     ebx, eax
0x180052941  test    eax, eax
0x180052943  jns     short loc_18005297C
0x180052945  mov     edx, 2C3h; void *
0x18005294a  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180052951  mov     r9d, ebx; char *
0x180052954  mov     rcx, [rbp+5Fh]; this
0x180052958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005295d  nop
0x18005295e  mov     rcx, [rbp+57h+var_68]
0x180052962  test    rcx, rcx
0x180052965  jz      short loc_1800528F3
0x180052967  mov     rdx, [rbp+57h+var_58]
0x18005296b  sub     rdx, rcx
0x18005296e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052972  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052977  jmp     loc_1800528F3
0x18005297c  lea     rcx, [rbp+57h+var_68]
0x180052980  call    ?GetIdentities@winbio@@YAJPEAV?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@@Z; winbio::GetIdentities(std::vector<_WINBIO_IDENTITY *> *)
0x180052985  mov     ebx, eax
0x180052987  test    eax, eax
0x180052989  jns     short loc_180052A07
0x18005298b  mov     edx, 2C4h
0x180052990  jmp     short loc_18005294A
0x180052992  cmp     dword ptr [rbx], 3
0x180052995  jnz     loc_180052BE2
0x18005299b  xor     edx, edx; struct _WINBIO_IDENTITY *
0x18005299d  mov     rcx, rbx; this
0x1800529a0  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x1800529a5  mov     edi, eax
0x1800529a7  test    eax, eax
0x1800529a9  jns     short loc_1800529E6
0x1800529ab  mov     edx, 2C8h; void *
0x1800529b0  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800529b7  mov     r9d, edi; char *
0x1800529ba  mov     rcx, [rbp+5Fh]; this
0x1800529be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800529c3  nop
0x1800529c4  mov     rcx, [rbp+57h+var_68]
0x1800529c8  test    rcx, rcx
0x1800529cb  jz      loc_18005291F
0x1800529d1  mov     rdx, [rbp+57h+var_58]
0x1800529d5  sub     rdx, rcx
0x1800529d8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800529dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800529e1  jmp     loc_18005291F
0x1800529e6  mov     rdx, [rbp+57h+var_60]
0x1800529ea  cmp     rdx, [rbp+57h+var_58]
0x1800529ee  jz      short loc_1800529FA
0x1800529f0  mov     [rdx], rbx
0x1800529f3  add     [rbp+57h+var_60], 8
0x1800529f8  jmp     short loc_180052A07
0x1800529fa  lea     r8, [rbp+57h+lpValueName]
0x1800529fe  lea     rcx, [rbp+57h+var_68]
0x180052a02  call    ??$_Emplace_reallocate@AEBQEAU_WINBIO_IDENTITY@@@?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@AEAAPEAPEAU_WINBIO_IDENTITY@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(_WINBIO_IDENTITY * * const,_WINBIO_IDENTITY * const &)
0x180052a07  mov     rbx, [rbp+57h+var_68]
0x180052a0b  mov     r14, [rbp+57h+var_60]
0x180052a0f  cmp     rbx, r14
0x180052a12  jz      loc_180052BC5
0x180052a18  mov     dword ptr [rbp+57h+Data], 0
0x180052a1f  lea     r8, [rbp+57h+Data]
0x180052a23  mov     edx, 2
0x180052a28  mov     rcx, [rbx]
0x180052a2b  call    ?GetFactorsForSID@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4FactorKey@1@PEAI@Z; winbio::GetFactorsForSID(_WINBIO_IDENTITY *,winbio::FactorKey,uint *)
0x180052a30  mov     edi, eax
0x180052a32  test    eax, eax
0x180052a34  js      loc_180052BBB
0x180052a3a  or      dword ptr [rbp+57h+Data], esi
0x180052a3d  lea     rcx, [rbp+57h+var_40]
0x180052a41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180052a46  nop
0x180052a47  lea     rdx, [rbp+57h+var_40]
0x180052a4b  mov     rcx, [rbx]
0x180052a4e  call    ?GetRegPathForSID@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winbio::GetRegPathForSID(_WINBIO_IDENTITY *,std::wstring *)
0x180052a53  mov     edi, eax
0x180052a55  test    eax, eax
0x180052a57  js      loc_180052B94
0x180052a5d  mov     [rbp+57h+hKey], 0
0x180052a65  lea     rcx, [rbp+57h+hKey]
0x180052a69  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180052a6e  mov     r8, rax
0x180052a71  lea     rcx, [rbp+57h+var_40]
0x180052a75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052a7a  mov     rdx, rax; lpSubKey
0x180052a7d  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x180052a86  mov     [rsp+0C0h+phkResult], r8; phkResult
0x180052a8b  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180052a94  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x180052a9c  mov     [rsp+0C0h+dwOptions], 0; unsigned int
0x180052aa4  xor     r9d, r9d; lpClass
0x180052aa7  xor     r8d, r8d; Reserved
0x180052aaa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052ab1  call    cs:__imp_RegCreateKeyExW
0x180052ab7  test    eax, eax
0x180052ab9  jnz     loc_180052B5C
0x180052abf  lea     rax, byte_1800DC1E0
0x180052ac6  mov     [rbp+57h+lpValueName], rax
0x180052aca  lea     rdx, [rbp+57h+lpValueName]
0x180052ace  mov     ecx, 2
0x180052ad3  call    ?GetKeyValueFromFactorKey@winbio@@YAJW4FactorKey@1@PEAPEBG@Z; winbio::GetKeyValueFromFactorKey(winbio::FactorKey,ushort const * *)
0x180052ad8  mov     edi, eax
0x180052ada  test    eax, eax
0x180052adc  js      short loc_180052B33
0x180052ade  mov     [rsp+0C0h+samDesired], 4; cbData
0x180052ae6  lea     rax, [rbp+57h+Data]
0x180052aea  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180052aef  mov     r9d, 4; dwType
0x180052af5  xor     r8d, r8d; Reserved
0x180052af8  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x180052afc  mov     rcx, [rbp+57h+hKey]; hKey
0x180052b00  call    cs:__imp_RegSetValueExW
0x180052b06  test    eax, eax
0x180052b08  jnz     short loc_180052B2C
0x180052b0a  mov     rcx, [rbp+57h+hKey]; hKey
0x180052b0e  test    rcx, rcx
0x180052b11  jz      short loc_180052B1A
0x180052b13  call    cs:__imp_RegCloseKey
0x180052b19  nop
0x180052b1a  lea     rcx, [rbp+57h+var_40]
0x180052b1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052b23  add     rbx, 8
0x180052b27  jmp     loc_180052A0F
0x180052b2c  mov     edx, 2EBh
0x180052b31  jmp     short loc_180052B61
0x180052b33  mov     rcx, [rbp+5Fh]; this
0x180052b37  mov     r9d, edi; char *
0x180052b3a  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180052b41  mov     edx, 2EAh; void *
0x180052b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b4b  mov     rcx, [rbp+57h+hKey]; hKey
0x180052b4f  test    rcx, rcx
0x180052b52  jz      short loc_180052BAD
0x180052b54  call    cs:__imp_RegCloseKey
0x180052b5a  jmp     short loc_180052BAD
0x180052b5c  mov     edx, 2E7h; void *
0x180052b61  mov     r9d, eax; char *
0x180052b64  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180052b6b  mov     rcx, [rbp+5Fh]; this
0x180052b6f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180052b74  mov     rcx, [rbp+57h+hKey]; hKey
0x180052b78  test    rcx, rcx
0x180052b7b  mov     ebx, eax
0x180052b7d  jz      short loc_180052B86
0x180052b7f  call    cs:__imp_RegCloseKey
0x180052b85  nop
0x180052b86  lea     rcx, [rbp+57h+var_40]
0x180052b8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052b8f  jmp     loc_18005295E
0x180052b94  mov     rcx, [rbp+5Fh]; this
0x180052b98  mov     r9d, edi; char *
0x180052b9b  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x180052ba2  mov     edx, 2E4h; void *
0x180052ba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bac  nop
0x180052bad  lea     rcx, [rbp+57h+var_40]
0x180052bb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052bb6  jmp     loc_1800529C4
0x180052bbb  mov     edx, 2D3h
0x180052bc0  jmp     loc_1800529B0
0x180052bc5  mov     rcx, [rbp+57h+var_68]
0x180052bc9  test    rcx, rcx
0x180052bcc  jz      short loc_180052BDE
0x180052bce  mov     rdx, [rbp+57h+var_58]
0x180052bd2  sub     rdx, rcx
0x180052bd5  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052bd9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052bde  xor     eax, eax
0x180052be0  jmp     short loc_180052C00
0x180052be2  mov     rcx, [rbp+57h+var_68]
0x180052be6  test    rcx, rcx
0x180052be9  jz      short loc_180052BFB
0x180052beb  mov     rdx, [rbp+57h+var_58]
0x180052bef  sub     rdx, rcx
0x180052bf2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052bf6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052bfb  mov     eax, 80070057h
0x180052c00  mov     rcx, [rbp+57h+var_20]
0x180052c04  xor     rcx, rsp; StackCookie
0x180052c07  call    __security_check_cookie
0x180052c0c  lea     r11, [rsp+0C0h+var_10]
0x180052c14  mov     rbx, [r11+30h]
0x180052c18  mov     rsi, [r11+38h]
0x180052c1c  mov     rsp, r11
0x180052c1f  pop     r14
0x180052c21  pop     rdi
0x180052c22  pop     rbp
0x180052c23  retn
```
