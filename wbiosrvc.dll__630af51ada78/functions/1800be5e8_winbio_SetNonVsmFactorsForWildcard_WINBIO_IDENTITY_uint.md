# winbio::SetNonVsmFactorsForWildcard(_WINBIO_IDENTITY *,uint)

- ea: `0x1800be5e8`
- end: `0x1800be939`
- name: `?SetNonVsmFactorsForWildcard@winbio@@YAJPEAU_WINBIO_IDENTITY@@I@Z`
- size: `849`
- prototype: `__int64 __fastcall(winbio *__hidden this, struct _WINBIO_IDENTITY *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073ee4`

## callees

- `0x180011d90`
- `0x180014110`
- `0x1800142e0`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180033378`
- `0x18005388c`
- `0x180068f60`
- `0x180069cc8`
- `0x18007762c`
- `0x1800be5e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800be75d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800be75d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be89e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be8ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be89e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be8ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800be893`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800be893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800be7d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800be7d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be81d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be869`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be81d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be869`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be741`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be8ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be741`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be8ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be6d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be6d6`

## string_xrefs

- `0x1800be625`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be685`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be6ea`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winbio::SetNonVsmFactorsForWildcard(winbio *this, struct _WINBIO_IDENTITY *a2, bool a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int WinBioRegistryLocation; // eax
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  DWORD v8; // ebx
  __int64 v9; // rax
  const WCHAR *v10; // rax
  BYTE *v11; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  HKEY v19; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  int pvData; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD v22; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v23[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v24[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v25[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  *(_DWORD *)Data = (_DWORD)a2;
  if ( this )
  {
    LOBYTE(a2) = 1;
    v3 = winbio::ValidateIdentity(this, a2, a3);
    if ( (v3 & 0x80000000) != 0 )
    {
      v4 = 382;
      goto LABEL_3;
    }
    v23[0] = 0;
    v23[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v23[0]) = 0;
    WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v23);
    v3 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
        (const char *)(unsigned int)WinBioRegistryLocation,
        phkResult);
LABEL_22:
      std::wstring::_Tidy_deallocate(v23);
      return v3;
    }
    std::wstring::append(v23, L"AccountInfo\\");
    hKey = 0;
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x2001Fu, &hKey);
    if ( v7 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x185,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
             (const char *)v7,
             phkResulta);
      goto LABEL_22;
    }
    v8 = 0;
    memset_0(Name, 0, 0x208u);
    cchName = 260;
    if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
    {
LABEL_21:
      RegCloseKey(hKey);
      hKey = 0;
      v3 = 0;
      goto LABEL_22;
    }
    while ( !(unsigned int)_o__wcsicmp(Name, L".DEFAULT") )
    {
LABEL_20:
      ++v8;
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      if ( RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, 0) )
        goto LABEL_21;
    }
    v19 = 0;
    v9 = std::operator+<unsigned short>(v25, v23, L"\\");
    std::operator+<unsigned short>(v24, v9, Name);
    std::wstring::_Tidy_deallocate(v25);
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0x2001Fu, 0, &v19, 0) )
    {
      pvData = 0;
      pcbData = 4;
      if ( RegGetValueW(hKey, Name, L"NonVsmFactors", 0x20000010u, 0, &pvData, &pcbData) )
      {
        if ( !*(_DWORD *)Data )
        {
          v11 = Data;
LABEL_18:
          RegSetValueExW(v19, L"NonVsmFactors", 0, 4u, v11, 4u);
          RegCloseKey(v19);
          goto LABEL_19;
        }
        v18 = 0;
        v22 = 4;
        if ( !RegGetValueW(hKey, Name, L"EnrolledFactors", 0x20000010u, 0, &v18, &v22) )
        {
          v11 = (BYTE *)&v18;
          goto LABEL_18;
        }
      }
    }
LABEL_19:
    std::wstring::_Tidy_deallocate(v24);
    goto LABEL_20;
  }
  v3 = -2147467261;
  v4 = 380;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
    (const char *)v3,
    phkResult);
  return v3;
}

```

## disassembly

```asm
0x1800be5e8  mov     [rsp-8+arg_10], rbx
0x1800be5ed  push    rbp
0x1800be5ee  push    rsi
0x1800be5ef  push    rdi
0x1800be5f0  lea     rbp, [rsp-210h]
0x1800be5f8  sub     rsp, 310h
0x1800be5ff  mov     rax, cs:__security_cookie
0x1800be606  xor     rax, rsp
0x1800be609  mov     [rbp+220h+var_20], rax
0x1800be610  mov     dword ptr [rsp+320h+Data], edx
0x1800be614  xor     edi, edi
0x1800be616  test    rcx, rcx
0x1800be619  jnz     short loc_1800BE640
0x1800be61b  mov     ebx, 80004003h
0x1800be620  mov     edx, 17Ch; void *
0x1800be625  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be62c  mov     r9d, ebx; char *
0x1800be62f  mov     rcx, [rbp+228h]; this
0x1800be636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be63b  jmp     loc_1800BE915
0x1800be640  mov     dl, 1; struct _WINBIO_IDENTITY *
0x1800be642  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x1800be647  mov     ebx, eax
0x1800be649  test    eax, eax
0x1800be64b  jns     short loc_1800BE654
0x1800be64d  mov     edx, 17Eh
0x1800be652  jmp     short loc_1800BE625
0x1800be654  xorps   xmm0, xmm0
0x1800be657  movups  [rbp+220h+var_298], xmm0
0x1800be65b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800be663  movdqu  [rbp+220h+var_288], xmm1
0x1800be668  mov     word ptr [rbp+220h+var_298], di
0x1800be66c  lea     rcx, [rbp+220h+var_298]
0x1800be670  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800be675  mov     ebx, eax
0x1800be677  test    eax, eax
0x1800be679  jns     short loc_1800BE69B
0x1800be67b  mov     rcx, [rbp+228h]; this
0x1800be682  mov     r9d, eax; char *
0x1800be685  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be68c  mov     edx, 181h; void *
0x1800be691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be696  jmp     loc_1800BE90C
0x1800be69b  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800be6a2  lea     rcx, [rbp+220h+var_298]
0x1800be6a6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800be6ab  mov     [rsp+320h+hKey], rdi
0x1800be6b0  lea     rcx, [rbp+220h+var_298]
0x1800be6b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800be6b9  mov     rdx, rax; lpSubKey
0x1800be6bc  lea     rax, [rsp+320h+hKey]
0x1800be6c1  mov     [rsp+320h+phkResult], rax; unsigned int
0x1800be6c6  mov     r9d, 2001Fh; samDesired
0x1800be6cc  xor     r8d, r8d; ulOptions
0x1800be6cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be6d6  call    cs:__imp_RegOpenKeyExW
0x1800be6dc  test    eax, eax
0x1800be6de  jz      short loc_1800BE702
0x1800be6e0  mov     rcx, [rbp+228h]; this
0x1800be6e7  mov     r9d, eax; char *
0x1800be6ea  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be6f1  mov     edx, 185h; void *
0x1800be6f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800be6fb  mov     ebx, eax
0x1800be6fd  jmp     loc_1800BE90C
0x1800be702  mov     ebx, edi
0x1800be704  xor     edx, edx; Val
0x1800be706  mov     r8d, 208h; Size
0x1800be70c  lea     rcx, [rbp+220h+Name]; void *
0x1800be710  call    memset_0
0x1800be715  mov     [rsp+320h+cchName], 104h
0x1800be71d  mov     [rsp+320h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800be722  mov     [rsp+320h+lpcchClass], rdi; lpcchClass
0x1800be727  mov     [rsp+320h+lpClass], rdi; lpClass
0x1800be72c  mov     [rsp+320h+phkResult], rdi; lpReserved
0x1800be731  lea     r9, [rsp+320h+cchName]; lpcchName
0x1800be736  lea     r8, [rbp+220h+Name]; lpName
0x1800be73a  xor     edx, edx; dwIndex
0x1800be73c  mov     rcx, [rsp+320h+hKey]; hKey
0x1800be741  call    cs:__imp_RegEnumKeyExW
0x1800be747  test    eax, eax
0x1800be749  jnz     loc_1800BE8FA
0x1800be74f  lea     esi, [rax+4]
0x1800be752  lea     rdx, aDefault; ".DEFAULT"
0x1800be759  lea     rcx, [rbp+220h+Name]
0x1800be75d  call    cs:__imp__o__wcsicmp
0x1800be763  test    eax, eax
0x1800be765  jz      loc_1800BE8AD
0x1800be76b  mov     [rsp+320h+var_2B0], rdi
0x1800be770  lea     r8, asc_1800DC1E4; "\\"
0x1800be777  lea     rdx, [rbp+220h+var_298]
0x1800be77b  lea     rcx, [rbp+220h+var_258]
0x1800be77f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800be784  nop
0x1800be785  lea     r8, [rbp+220h+Name]
0x1800be789  mov     rdx, rax
0x1800be78c  lea     rcx, [rbp+220h+var_278]
0x1800be790  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800be795  nop
0x1800be796  lea     rcx, [rbp+220h+var_258]
0x1800be79a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be79f  lea     rcx, [rbp+220h+var_278]
0x1800be7a3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800be7a8  mov     rdx, rax; lpSubKey
0x1800be7ab  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x1800be7b0  lea     rax, [rsp+320h+var_2B0]
0x1800be7b5  mov     [rsp+320h+lpftLastWriteTime], rax; phkResult
0x1800be7ba  mov     [rsp+320h+lpcchClass], rdi; lpSecurityAttributes
0x1800be7bf  mov     dword ptr [rsp+320h+lpClass], 2001Fh; samDesired
0x1800be7c7  mov     dword ptr [rsp+320h+phkResult], edi; dwOptions
0x1800be7cb  xor     r9d, r9d; lpClass
0x1800be7ce  xor     r8d, r8d; Reserved
0x1800be7d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be7d8  call    cs:__imp_RegCreateKeyExW
0x1800be7de  test    eax, eax
0x1800be7e0  jnz     loc_1800BE8A4
0x1800be7e6  mov     [rsp+320h+pvData], edi
0x1800be7ea  mov     [rsp+320h+pcbData], esi
0x1800be7ee  lea     rax, [rsp+320h+pcbData]
0x1800be7f3  mov     [rsp+320h+lpcchClass], rax; pcbData
0x1800be7f8  lea     rax, [rsp+320h+pvData]
0x1800be7fd  mov     [rsp+320h+lpClass], rax; pvData
0x1800be802  mov     [rsp+320h+phkResult], rdi; pdwType
0x1800be807  mov     r9d, 20000010h; dwFlags
0x1800be80d  lea     r8, aNonvsmfactors; "NonVsmFactors"
0x1800be814  lea     rdx, [rbp+220h+Name]; lpSubKey
0x1800be818  mov     rcx, [rsp+320h+hKey]; hkey
0x1800be81d  call    cs:__imp_RegGetValueW
0x1800be823  test    eax, eax
0x1800be825  jz      short loc_1800BE8A4
0x1800be827  cmp     dword ptr [rsp+320h+Data], edi
0x1800be82b  jnz     short loc_1800BE834
0x1800be82d  lea     rax, [rsp+320h+Data]
0x1800be832  jmp     short loc_1800BE878
0x1800be834  mov     [rsp+320h+var_2B8], edi
0x1800be838  mov     [rbp+220h+var_2A0], esi
0x1800be83b  lea     rax, [rbp+220h+var_2A0]
0x1800be83f  mov     [rsp+320h+lpcchClass], rax; pcbData
0x1800be844  lea     rax, [rsp+320h+var_2B8]
0x1800be849  mov     [rsp+320h+lpClass], rax; pvData
0x1800be84e  mov     [rsp+320h+phkResult], rdi; pdwType
0x1800be853  mov     r9d, 20000010h; dwFlags
0x1800be859  lea     r8, aEnrolledfactor; "EnrolledFactors"
0x1800be860  lea     rdx, [rbp+220h+Name]; lpSubKey
0x1800be864  mov     rcx, [rsp+320h+hKey]; hkey
0x1800be869  call    cs:__imp_RegGetValueW
0x1800be86f  test    eax, eax
0x1800be871  jnz     short loc_1800BE8A4
0x1800be873  lea     rax, [rsp+320h+var_2B8]
0x1800be878  mov     dword ptr [rsp+320h+lpClass], esi; cbData
0x1800be87c  mov     [rsp+320h+phkResult], rax; lpData
0x1800be881  mov     r9d, esi; dwType
0x1800be884  xor     r8d, r8d; Reserved
0x1800be887  lea     rdx, aNonvsmfactors; "NonVsmFactors"
0x1800be88e  mov     rcx, [rsp+320h+var_2B0]; hKey
0x1800be893  call    cs:__imp_RegSetValueExW
0x1800be899  mov     rcx, [rsp+320h+var_2B0]; hKey
0x1800be89e  call    cs:__imp_RegCloseKey
0x1800be8a4  lea     rcx, [rbp+220h+var_278]
0x1800be8a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be8ad  inc     ebx
0x1800be8af  xor     edx, edx; Val
0x1800be8b1  mov     r8d, 208h; Size
0x1800be8b7  lea     rcx, [rbp+220h+Name]; void *
0x1800be8bb  call    memset_0
0x1800be8c0  mov     [rsp+320h+cchName], 104h
0x1800be8c8  mov     [rsp+320h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800be8cd  mov     [rsp+320h+lpcchClass], rdi; lpcchClass
0x1800be8d2  mov     [rsp+320h+lpClass], rdi; lpClass
0x1800be8d7  mov     [rsp+320h+phkResult], rdi; lpReserved
0x1800be8dc  lea     r9, [rsp+320h+cchName]; lpcchName
0x1800be8e1  lea     r8, [rbp+220h+Name]; lpName
0x1800be8e5  mov     edx, ebx; dwIndex
0x1800be8e7  mov     rcx, [rsp+320h+hKey]; hKey
0x1800be8ec  call    cs:__imp_RegEnumKeyExW
0x1800be8f2  test    eax, eax
0x1800be8f4  jz      loc_1800BE752
0x1800be8fa  mov     rcx, [rsp+320h+hKey]; hKey
0x1800be8ff  call    cs:__imp_RegCloseKey
0x1800be905  mov     [rsp+320h+hKey], rdi
0x1800be90a  mov     ebx, edi
0x1800be90c  lea     rcx, [rbp+220h+var_298]
0x1800be910  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be915  mov     eax, ebx
0x1800be917  mov     rcx, [rbp+220h+var_20]
0x1800be91e  xor     rcx, rsp; StackCookie
0x1800be921  call    __security_check_cookie
0x1800be926  mov     rbx, [rsp+320h+arg_10]
0x1800be92e  add     rsp, 310h
0x1800be935  pop     rdi
0x1800be936  pop     rsi
0x1800be937  pop     rbp
0x1800be938  retn
```
