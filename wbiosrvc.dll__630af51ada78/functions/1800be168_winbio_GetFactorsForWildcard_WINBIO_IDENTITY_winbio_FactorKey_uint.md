# winbio::GetFactorsForWildcard(_WINBIO_IDENTITY *,winbio::FactorKey,uint *)

- ea: `0x1800be168`
- end: `0x1800be396`
- name: `?GetFactorsForWildcard@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4FactorKey@1@PEAI@Z`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016d38`
- `0x1800be068`

## callees

- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x1800165d8`
- `0x180033378`
- `0x18005388c`
- `0x180068f60`
- `0x180069cc8`
- `0x1800be168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be35f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be35f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be2fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be2fd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be34a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be34a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be281`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be281`

## string_xrefs

- `0x1800be1a6`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be22e`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800be295`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::GetFactorsForWildcard(winbio *a1, struct _WINBIO_IDENTITY *a2, _DWORD *a3)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  int KeyValueFromFactorKey; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int WinBioRegistryLocation; // eax
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  int v13; // ebx
  DWORD v14; // esi
  DWORD i; // edx
  LSTATUS v16; // eax
  HKEY v17; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  LPCWSTR lpValue; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = (unsigned int)a2;
  if ( !a1 )
  {
    v5 = 460;
LABEL_3:
    KeyValueFromFactorKey = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)KeyValueFromFactorKey,
      phkResult);
    return (unsigned int)KeyValueFromFactorKey;
  }
  if ( !a3 )
  {
    v5 = 461;
    goto LABEL_3;
  }
  LOBYTE(a2) = 1;
  KeyValueFromFactorKey = winbio::ValidateIdentity(a1, a2, (bool)a3);
  if ( KeyValueFromFactorKey < 0 )
  {
    v5 = 463;
    goto LABEL_4;
  }
  *a3 = 0;
  lpValue = (LPCWSTR)byte_1800DC1E0;
  KeyValueFromFactorKey = winbio::GetKeyValueFromFactorKey(v4, &lpValue);
  if ( KeyValueFromFactorKey < 0 )
  {
    v5 = 468;
    goto LABEL_4;
  }
  std::wstring::wstring(v26, v7, v8, v9);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v26);
  KeyValueFromFactorKey = WinBioRegistryLocation;
  if ( WinBioRegistryLocation >= 0 )
  {
    std::wstring::append(v26, L"AccountInfo\\");
    hkey = 0;
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hkey);
    if ( v12 )
    {
      KeyValueFromFactorKey = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x1DB,
                                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
                                (const char *)v12,
                                phkResulta);
    }
    else
    {
      v13 = 0;
      v14 = 0;
      memset_0(SubKey, 0, 0x208u);
      for ( i = 0; ; i = v14 )
      {
        cchName = 260;
        v16 = RegEnumKeyExW(hkey, i, SubKey, &cchName, 0, 0, 0, 0);
        v17 = hkey;
        if ( v16 )
          break;
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(hkey, SubKey, lpValue, 0x20000010u, 0, &pvData, &pcbData) )
          v13 |= pvData;
        ++v14;
        memset_0(SubKey, 0, 0x208u);
      }
      *a3 = v13;
      RegCloseKey(v17);
      hkey = 0;
      KeyValueFromFactorKey = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      phkResult);
  }
  std::wstring::_Tidy_deallocate(v26);
  return (unsigned int)KeyValueFromFactorKey;
}

```

## disassembly

```asm
0x1800be168  push    rbp
0x1800be16a  push    rbx
0x1800be16b  push    rsi
0x1800be16c  push    rdi
0x1800be16d  push    r14
0x1800be16f  lea     rbp, [rsp-1A0h]
0x1800be177  sub     rsp, 2A0h
0x1800be17e  mov     rax, cs:__security_cookie
0x1800be185  xor     rax, rsp
0x1800be188  mov     [rbp+1C0h+var_30], rax
0x1800be18f  mov     rdi, r8
0x1800be192  mov     esi, edx
0x1800be194  xor     r14d, r14d
0x1800be197  test    rcx, rcx
0x1800be19a  jnz     short loc_1800BE1C1
0x1800be19c  mov     edx, 1CCh; void *
0x1800be1a1  mov     ebx, 80004003h
0x1800be1a6  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be1ad  mov     r9d, ebx; char *
0x1800be1b0  mov     rcx, [rbp+1C8h]; this
0x1800be1b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be1bc  jmp     loc_1800BE377
0x1800be1c1  test    rdi, rdi
0x1800be1c4  jnz     short loc_1800BE1CD
0x1800be1c6  mov     edx, 1CDh
0x1800be1cb  jmp     short loc_1800BE1A1
0x1800be1cd  mov     dl, 1; struct _WINBIO_IDENTITY *
0x1800be1cf  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x1800be1d4  mov     ebx, eax
0x1800be1d6  test    eax, eax
0x1800be1d8  jns     short loc_1800BE1E1
0x1800be1da  mov     edx, 1CFh
0x1800be1df  jmp     short loc_1800BE1A6
0x1800be1e1  mov     [rdi], r14d
0x1800be1e4  lea     rax, byte_1800DC1E0
0x1800be1eb  mov     [rsp+2C0h+lpValue], rax
0x1800be1f0  lea     rdx, [rsp+2C0h+lpValue]
0x1800be1f5  mov     ecx, esi
0x1800be1f7  call    ?GetKeyValueFromFactorKey@winbio@@YAJW4FactorKey@1@PEAPEBG@Z; winbio::GetKeyValueFromFactorKey(winbio::FactorKey,ushort const * *)
0x1800be1fc  mov     ebx, eax
0x1800be1fe  test    eax, eax
0x1800be200  jns     short loc_1800BE209
0x1800be202  mov     edx, 1D4h
0x1800be207  jmp     short loc_1800BE1A6
0x1800be209  lea     rcx, [rsp+2C0h+var_260]
0x1800be20e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800be213  nop
0x1800be214  lea     rcx, [rsp+2C0h+var_260]
0x1800be219  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800be21e  mov     ebx, eax
0x1800be220  test    eax, eax
0x1800be222  jns     short loc_1800BE244
0x1800be224  mov     rcx, [rbp+1C8h]; this
0x1800be22b  mov     r9d, eax; char *
0x1800be22e  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be235  mov     edx, 1D7h; void *
0x1800be23a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be23f  jmp     loc_1800BE36D
0x1800be244  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800be24b  lea     rcx, [rsp+2C0h+var_260]
0x1800be250  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800be255  mov     [rsp+2C0h+hkey], r14
0x1800be25a  lea     rcx, [rsp+2C0h+var_260]
0x1800be25f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800be264  mov     rdx, rax; lpSubKey
0x1800be267  lea     rax, [rsp+2C0h+hkey]
0x1800be26c  mov     [rsp+2C0h+phkResult], rax; unsigned int
0x1800be271  mov     r9d, 20019h; samDesired
0x1800be277  xor     r8d, r8d; ulOptions
0x1800be27a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be281  call    cs:__imp_RegOpenKeyExW
0x1800be287  test    eax, eax
0x1800be289  jz      short loc_1800BE2AD
0x1800be28b  mov     rcx, [rbp+1C8h]; this
0x1800be292  mov     r9d, eax; char *
0x1800be295  lea     r8, aOnecoreDsSecur_48; "onecore\\ds\\security\\biometrics\\serv"...
0x1800be29c  mov     edx, 1DBh; void *
0x1800be2a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800be2a6  mov     ebx, eax
0x1800be2a8  jmp     loc_1800BE36D
0x1800be2ad  mov     ebx, r14d
0x1800be2b0  mov     esi, r14d
0x1800be2b3  xor     edx, edx; Val
0x1800be2b5  mov     r8d, 208h; Size
0x1800be2bb  lea     rcx, [rbp+1C0h+SubKey]; void *
0x1800be2bf  call    memset_0
0x1800be2c4  xor     edx, edx
0x1800be2c6  jmp     short loc_1800BE320
0x1800be2c8  mov     [rsp+2C0h+var_270], r14d
0x1800be2cd  mov     [rsp+2C0h+var_26C], 4
0x1800be2d5  lea     rax, [rsp+2C0h+var_26C]
0x1800be2da  mov     [rsp+2C0h+pcbData], rax; pcbData
0x1800be2df  lea     rax, [rsp+2C0h+var_270]
0x1800be2e4  mov     [rsp+2C0h+pvData], rax; pvData
0x1800be2e9  mov     [rsp+2C0h+phkResult], r14; pdwType
0x1800be2ee  mov     r9d, 20000010h; dwFlags
0x1800be2f4  mov     r8, [rsp+2C0h+lpValue]; lpValue
0x1800be2f9  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800be2fd  call    cs:__imp_RegGetValueW
0x1800be303  test    eax, eax
0x1800be305  jnz     short loc_1800BE30B
0x1800be307  or      ebx, [rsp+2C0h+var_270]
0x1800be30b  inc     esi
0x1800be30d  xor     edx, edx; Val
0x1800be30f  mov     r8d, 208h; Size
0x1800be315  lea     rcx, [rbp+1C0h+SubKey]; void *
0x1800be319  call    memset_0
0x1800be31e  mov     edx, esi; dwIndex
0x1800be320  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800be325  mov     [rsp+2C0h+pcbData], r14; lpcchClass
0x1800be32a  mov     [rsp+2C0h+pvData], r14; lpClass
0x1800be32f  mov     [rsp+2C0h+phkResult], r14; lpReserved
0x1800be334  mov     [rsp+2C0h+cchName], 104h
0x1800be33c  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x1800be341  lea     r8, [rbp+1C0h+SubKey]; lpName
0x1800be345  mov     rcx, [rsp+2C0h+hkey]; hKey
0x1800be34a  call    cs:__imp_RegEnumKeyExW
0x1800be350  mov     rcx, [rsp+2C0h+hkey]; hKey
0x1800be355  test    eax, eax
0x1800be357  jz      loc_1800BE2C8
0x1800be35d  mov     [rdi], ebx
0x1800be35f  call    cs:__imp_RegCloseKey
0x1800be365  mov     [rsp+2C0h+hkey], r14
0x1800be36a  mov     ebx, r14d
0x1800be36d  lea     rcx, [rsp+2C0h+var_260]
0x1800be372  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800be377  mov     eax, ebx
0x1800be379  mov     rcx, [rbp+1C0h+var_30]
0x1800be380  xor     rcx, rsp; StackCookie
0x1800be383  call    __security_check_cookie
0x1800be388  add     rsp, 2A0h
0x1800be38f  pop     r14
0x1800be391  pop     rdi
0x1800be392  pop     rsi
0x1800be393  pop     rbx
0x1800be394  pop     rbp
0x1800be395  retn
```
