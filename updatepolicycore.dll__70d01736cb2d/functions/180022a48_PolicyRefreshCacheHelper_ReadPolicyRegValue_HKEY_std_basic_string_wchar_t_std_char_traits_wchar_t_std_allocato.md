# PolicyRefreshCacheHelper::ReadPolicyRegValue(HKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> &)

- ea: `0x180022a48`
- end: `0x180022f9d`
- name: `?ReadPolicyRegValue@PolicyRefreshCacheHelper@@CAJPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z`
- size: `1365`
- prototype: `int __fastcall(HKEY hKey, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180022a48`
- `0x1800236b8`

## callees

- `0x18000aac0`
- `0x18000f27c`
- `0x18000fb4c`
- `0x180010260`
- `0x1800191d4`
- `0x18001eea4`
- `0x180022a48`
- `0x1800244e8`
- `0x180024738`
- `0x1800256d4`
- `0x1800258bc`
- `0x18002bfcc`
- `0x18002c120`
- `0x18002d264`
- `0x18002ffd0`
- `0x180036a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022da5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022da5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022d60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022e76`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022d60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022e76`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180022ab6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180022d20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180022ab6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180022d20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022e4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022f82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022e4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022f82`

## string_xrefs

- `0x180022ec4`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180022ee1`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180022f19`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180022f3e`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180022f65`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall PolicyRefreshCacheHelper::ReadPolicyRegValue(HKEY hKey, __int64 a2, __int64 a3)
{
  DWORD v6; // r12d
  unsigned int i; // eax
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r8
  void *v13; // rbx
  unsigned __int64 v14; // rdx
  void **v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  void **v21; // r9
  char *v22; // rdi
  __int64 v23; // rbx
  DWORD v24; // edi
  unsigned int v25; // eax
  __int64 v26; // rcx
  int PolicyRegValue; // eax
  __int64 v29; // rdx
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  _BYTE v33[32]; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  void *v38[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v39; // [rsp+88h] [rbp-78h]
  unsigned __int64 v40; // [rsp+90h] [rbp-70h]
  _BYTE v41[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h]
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v6 = 0;
  cchValueName = 260;
  Type = 0;
  for ( i = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, 0, 0);
        ;
        i = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, 0, 0) )
  {
    if ( i == 259 )
    {
      v24 = 0;
      cchName = 260;
      i = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( i == 259 )
        return 0;
      while ( 1 )
      {
        if ( i )
        {
          v29 = 165;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v29,
                   (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
                   (const char *)i,
                   lpReserved);
        }
        Src = 0;
        v25 = RegOpenKeyExW(hKey, Name, 0, 0xF003Fu, (PHKEY)&Src);
        if ( v25 )
          break;
        v26 = *(_QWORD *)(a2 + 16);
        if ( v26 == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        std::wstring::wstring(v33, v26, L"|", 1);
        std::operator+<wchar_t>(v41, v33, Name);
        std::wstring::~wstring(v33);
        PolicyRegValue = PolicyRefreshCacheHelper::ReadPolicyRegValue((HKEY)Src);
        v9 = PolicyRegValue;
        if ( PolicyRegValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAD,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
            (const char *)(unsigned int)PolicyRegValue,
            lpReservedb);
          std::wstring::~wstring(v41);
          goto LABEL_49;
        }
        cchName = 260;
        ++v24;
        std::wstring::~wstring(v41);
        if ( Src )
          RegCloseKey((HKEY)Src);
        i = RegEnumKeyExW(hKey, v24, Name, &cchName, 0, 0, 0, 0);
        if ( i == 259 )
          return 0;
      }
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA9,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
             (const char *)v25,
             lpReserveda);
LABEL_49:
      if ( Src )
        RegCloseKey((HKEY)Src);
      return v9;
    }
    if ( i )
      break;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    v40 = 7;
    LOWORD(v38[0]) = 0;
    if ( Type == 1 )
    {
      Src = 0;
      v11 = RegQueryStringValue(hKey, 0, ValueName, &Src);
      v9 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
          (const char *)(unsigned int)v11,
          lpReserved);
        if ( Src )
          SusFree(Src);
LABEL_43:
        std::wstring::~wstring(v38);
        return v9;
      }
      v13 = Src;
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)Src + v14) );
      if ( v14 > v40 )
      {
        std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(v38, v14, v12, Src);
      }
      else
      {
        v15 = v38;
        if ( v40 > 7 )
          v15 = (void **)v38[0];
        v39 = v14;
        v16 = 2 * v14;
        memmove(v15, Src, 2 * v14);
        *(_WORD *)((char *)v15 + v16) = 0;
      }
      if ( v13 )
        SusFree(v13);
    }
    else if ( Type == 4 )
    {
      LODWORD(Src) = 0;
      v8 = RegQueryDwordValue(hKey, 0, ValueName, &Src);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
          (const char *)(unsigned int)v8,
          lpReserved);
        goto LABEL_43;
      }
      v10 = std::to_wstring(v33);
      std::wstring::operator=(v38, v10);
      std::wstring::~wstring(v33);
    }
    else
    {
      v39 = 1;
      LODWORD(v38[0]) = asc_18003F428[0];
    }
    v17 = *(_QWORD *)(a2 + 16);
    if ( v17 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v33, v17, L"|", 1);
    std::operator+<wchar_t>(v41, v33, ValueName);
    std::wstring::~wstring(v33);
    if ( v42 )
    {
      if ( v39 )
      {
        v18 = std::map<std::wstring,std::wstring>::operator[](a3, v41);
        if ( (void **)v18 != v38 )
        {
          v20 = v39;
          v21 = v38;
          if ( v40 > 7 )
            v21 = (void **)v38[0];
          if ( v39 > *(_QWORD *)(v18 + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(v18, v39, v19, v21);
          }
          else
          {
            v22 = (char *)v18;
            if ( *(_QWORD *)(v18 + 24) > 7u )
              v22 = *(char **)v18;
            *(_QWORD *)(v18 + 16) = v39;
            v23 = 2 * v20;
            memmove(v22, v21, 2 * v20);
            *(_WORD *)&v22[v23] = 0;
          }
        }
      }
    }
    cchValueName = 260;
    ++v6;
    std::wstring::~wstring(v41);
    std::wstring::~wstring(v38);
  }
  v29 = 118;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v29,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
           (const char *)i,
           lpReserved);
}

```

## disassembly

```asm
0x180022a48  mov     [rsp-8+arg_18], rbx
0x180022a4d  push    rbp
0x180022a4e  push    rsi
0x180022a4f  push    rdi
0x180022a50  push    r12
0x180022a52  push    r13
0x180022a54  push    r14
0x180022a56  push    r15
0x180022a58  lea     rbp, [rsp-3F0h]
0x180022a60  sub     rsp, 4F0h
0x180022a67  mov     rax, cs:__security_cookie
0x180022a6e  xor     rax, rsp
0x180022a71  mov     [rbp+420h+var_40], rax
0x180022a78  mov     r13, r8
0x180022a7b  mov     r14, rdx
0x180022a7e  mov     r15, rcx
0x180022a81  xor     esi, esi
0x180022a83  mov     r12d, esi
0x180022a86  mov     [rsp+520h+cchValueName], 104h
0x180022a8e  mov     [rsp+520h+Type], esi
0x180022a92  mov     [rsp+520h+lpcbData], rsi; lpcbData
0x180022a97  mov     [rsp+520h+lpData], rsi; lpData
0x180022a9c  lea     rax, [rsp+520h+Type]
0x180022aa1  mov     [rsp+520h+lpType], rax; lpType
0x180022aa6  mov     [rsp+520h+lpReserved], rsi; lpReserved
0x180022aab  lea     r9, [rsp+520h+cchValueName]; lpcchValueName
0x180022ab0  lea     r8, [rbp+420h+ValueName]; lpValueName
0x180022ab4  xor     edx, edx; dwIndex
0x180022ab6  call    cs:__imp_RegEnumValueW
0x180022abc  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180022ac6  lea     rbx, asc_18003F42C; "|"
0x180022acd  jmp     loc_180022D26
0x180022ad2  test    eax, eax
0x180022ad4  jnz     loc_180022F14
0x180022ada  xorps   xmm0, xmm0
0x180022add  movups  xmmword ptr [rsp+520h+var_4A8], xmm0
0x180022ae2  mov     [rbp+420h+var_498], rsi
0x180022ae6  mov     [rbp+420h+var_490], 7
0x180022aee  mov     word ptr [rsp+520h+var_4A8], si
0x180022af3  mov     eax, [rsp+520h+Type]
0x180022af7  sub     eax, 1
0x180022afa  jz      short loc_180022B69
0x180022afc  cmp     eax, 3
0x180022aff  jz      short loc_180022B1E
0x180022b01  mov     [rbp+420h+var_498], 1
0x180022b09  mov     eax, dword ptr cs:asc_18003F428; "."
0x180022b0f  mov     word ptr [rsp+520h+var_4A8], ax
0x180022b14  mov     word ptr [rsp+520h+var_4A8+2], si
0x180022b19  jmp     loc_180022BFF
0x180022b1e  mov     dword ptr [rsp+520h+Src], esi
0x180022b22  lea     r9, [rsp+520h+Src]
0x180022b27  lea     r8, [rbp+420h+ValueName]
0x180022b2b  xor     edx, edx
0x180022b2d  mov     rcx, r15
0x180022b30  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x180022b35  mov     ebx, eax
0x180022b37  test    eax, eax
0x180022b39  js      loc_180022EBA
0x180022b3f  mov     edx, dword ptr [rsp+520h+Src]
0x180022b43  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022b48  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@K@Z; std::to_wstring(ulong)
0x180022b4d  mov     rdx, rax
0x180022b50  lea     rcx, [rsp+520h+var_4A8]
0x180022b55  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022b5a  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022b5f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022b64  jmp     loc_180022BF8
0x180022b69  mov     [rsp+520h+Src], rsi
0x180022b6e  lea     r9, [rsp+520h+Src]
0x180022b73  lea     r8, [rbp+420h+ValueName]
0x180022b77  xor     edx, edx
0x180022b79  mov     rcx, r15
0x180022b7c  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x180022b81  mov     ebx, eax
0x180022b83  test    eax, eax
0x180022b85  js      loc_180022ED7
0x180022b8b  mov     rbx, [rsp+520h+Src]
0x180022b90  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022b94  inc     rdx
0x180022b97  cmp     [rbx+rdx*2], si
0x180022b9b  jnz     short loc_180022B94
0x180022b9d  cmp     rdx, [rbp+420h+var_490]
0x180022ba1  ja      short loc_180022BDD
0x180022ba3  lea     rsi, [rsp+520h+var_4A8]
0x180022ba8  cmp     [rbp+420h+var_490], 7
0x180022bad  cmova   rsi, [rsp+520h+var_4A8]
0x180022bb3  mov     [rbp+420h+var_498], rdx
0x180022bb7  lea     rdi, [rdx+rdx]
0x180022bbb  mov     r8, rdi; Size
0x180022bbe  mov     rdx, rbx; Src
0x180022bc1  mov     rcx, rsi; void *
0x180022bc4  call    memmove
0x180022bc9  xor     eax, eax
0x180022bcb  mov     [rdi+rsi], ax
0x180022bcf  xor     esi, esi
0x180022bd1  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180022bdb  jmp     short loc_180022BEB
0x180022bdd  mov     r9, rbx
0x180022be0  lea     rcx, [rsp+520h+var_4A8]
0x180022be5  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x180022bea  nop
0x180022beb  test    rbx, rbx
0x180022bee  jz      short loc_180022BF8
0x180022bf0  mov     rcx, rbx; lpMem
0x180022bf3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180022bf8  lea     rbx, asc_18003F42C; "|"
0x180022bff  mov     rcx, [r14+10h]
0x180022c03  mov     rax, rdi
0x180022c06  sub     rax, rcx
0x180022c09  cmp     rax, 1
0x180022c0d  jb      loc_180022F97
0x180022c13  mov     r9, r14
0x180022c16  cmp     qword ptr [r14+18h], 7
0x180022c1b  jbe     short loc_180022C20
0x180022c1d  mov     r9, [r14]
0x180022c20  mov     [rsp+520h+lpData], 1; __int64
0x180022c29  mov     [rsp+520h+lpType], rbx; Src
0x180022c2e  mov     [rsp+520h+lpReserved], rcx; __int64
0x180022c33  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022c38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180022c3d  nop
0x180022c3e  lea     r8, [rbp+420h+ValueName]
0x180022c42  lea     rdx, [rsp+520h+var_4E0]
0x180022c47  lea     rcx, [rbp+420h+var_488]
0x180022c4b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180022c50  nop
0x180022c51  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022c56  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022c5b  cmp     [rbp+420h+var_478], rsi
0x180022c5f  jz      short loc_180022CD9
0x180022c61  cmp     [rbp+420h+var_498], rsi
0x180022c65  jz      short loc_180022CD9
0x180022c67  lea     rdx, [rbp+420h+var_488]
0x180022c6b  mov     rcx, r13
0x180022c6e  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x180022c73  lea     rcx, [rsp+520h+var_4A8]
0x180022c78  cmp     rax, rcx
0x180022c7b  jz      short loc_180022CD9
0x180022c7d  mov     rdx, [rbp+420h+var_498]
0x180022c81  lea     r9, [rsp+520h+var_4A8]
0x180022c86  cmp     [rbp+420h+var_490], 7
0x180022c8b  cmova   r9, [rsp+520h+var_4A8]
0x180022c91  cmp     rdx, [rax+18h]
0x180022c95  ja      short loc_180022CD1
0x180022c97  mov     rdi, rax
0x180022c9a  cmp     qword ptr [rax+18h], 7
0x180022c9f  jbe     short loc_180022CA4
0x180022ca1  mov     rdi, [rax]
0x180022ca4  mov     [rax+10h], rdx
0x180022ca8  lea     rbx, [rdx+rdx]
0x180022cac  mov     r8, rbx; Size
0x180022caf  mov     rdx, r9; Src
0x180022cb2  mov     rcx, rdi; void *
0x180022cb5  call    memmove
0x180022cba  mov     [rbx+rdi], si
0x180022cbe  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180022cc8  lea     rbx, asc_18003F42C; "|"
0x180022ccf  jmp     short loc_180022CD9
0x180022cd1  mov     rcx, rax
0x180022cd4  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x180022cd9  mov     [rsp+520h+cchValueName], 104h
0x180022ce1  inc     r12d
0x180022ce4  lea     rcx, [rbp+420h+var_488]; void *
0x180022ce8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022ced  nop
0x180022cee  lea     rcx, [rsp+520h+var_4A8]; void *
0x180022cf3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022cf8  mov     [rsp+520h+lpcbData], rsi; lpcbData
0x180022cfd  mov     [rsp+520h+lpData], rsi; lpData
0x180022d02  lea     rax, [rsp+520h+Type]
0x180022d07  mov     [rsp+520h+lpType], rax; lpType
0x180022d0c  mov     [rsp+520h+lpReserved], rsi; unsigned int
0x180022d11  lea     r9, [rsp+520h+cchValueName]; lpcchValueName
0x180022d16  lea     r8, [rbp+420h+ValueName]; lpValueName
0x180022d1a  mov     edx, r12d; dwIndex
0x180022d1d  mov     rcx, r15; hKey
0x180022d20  call    cs:__imp_RegEnumValueW
0x180022d26  cmp     eax, 103h
0x180022d2b  jnz     loc_180022AD2
0x180022d31  mov     edi, esi
0x180022d33  mov     [rsp+520h+cchName], 104h
0x180022d3b  mov     [rsp+520h+lpcbData], rsi; lpftLastWriteTime
0x180022d40  mov     [rsp+520h+lpData], rsi; lpcchClass
0x180022d45  mov     [rsp+520h+lpType], rsi; lpClass
0x180022d4a  mov     [rsp+520h+lpReserved], rsi; lpReserved
0x180022d4f  lea     r9, [rsp+520h+cchName]; lpcchName
0x180022d54  lea     r8, [rbp+420h+Name]; lpName
0x180022d5b  xor     edx, edx; dwIndex
0x180022d5d  mov     rcx, r15; hKey
0x180022d60  call    cs:__imp_RegEnumKeyExW
0x180022d66  cmp     eax, 103h
0x180022d6b  jz      loc_180022E8E
0x180022d71  mov     r12, 7FFFFFFFFFFFFFFEh
0x180022d7b  test    eax, eax
0x180022d7d  jnz     loc_180022F8A
0x180022d83  mov     [rsp+520h+Src], rsi
0x180022d88  lea     rax, [rsp+520h+Src]
0x180022d8d  mov     [rsp+520h+lpReserved], rax; unsigned int
0x180022d92  mov     r9d, 0F003Fh; samDesired
0x180022d98  xor     r8d, r8d; ulOptions
0x180022d9b  lea     rdx, [rbp+420h+Name]; lpSubKey
0x180022da2  mov     rcx, r15; hKey
0x180022da5  call    cs:__imp_RegOpenKeyExW
0x180022dab  test    eax, eax
0x180022dad  jnz     loc_180022F5B
0x180022db3  mov     rcx, [r14+10h]
0x180022db7  mov     rax, r12
0x180022dba  sub     rax, rcx
0x180022dbd  cmp     rax, 1
0x180022dc1  jb      loc_180022F91
0x180022dc7  mov     r9, r14
0x180022dca  cmp     qword ptr [r14+18h], 7
0x180022dcf  jbe     short loc_180022DD4
0x180022dd1  mov     r9, [r14]
0x180022dd4  mov     [rsp+520h+lpData], 1; __int64
0x180022ddd  mov     [rsp+520h+lpType], rbx; Src
0x180022de2  mov     [rsp+520h+lpReserved], rcx; int
0x180022de7  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022dec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180022df1  nop
0x180022df2  lea     r8, [rbp+420h+Name]
0x180022df9  lea     rdx, [rsp+520h+var_4E0]
0x180022dfe  lea     rcx, [rbp+420h+var_488]
0x180022e02  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180022e07  nop
0x180022e08  lea     rcx, [rsp+520h+var_4E0]; void *
0x180022e0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022e12  mov     r8, r13
0x180022e15  lea     rdx, [rbp+420h+var_488]
0x180022e19  mov     rcx, [rsp+520h+Src]; hKey
0x180022e1e  call    ?ReadPolicyRegValue@PolicyRefreshCacheHelper@@CAJPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z; PolicyRefreshCacheHelper::ReadPolicyRegValue(HKEY__ *,std::wstring &,std::map<std::wstring,std::wstring> &)
0x180022e23  mov     ebx, eax
0x180022e25  test    eax, eax
0x180022e27  js      loc_180022F34
0x180022e2d  mov     [rsp+520h+cchName], 104h
0x180022e35  inc     edi
0x180022e37  lea     rcx, [rbp+420h+var_488]; void *
0x180022e3b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022e40  nop
0x180022e41  mov     rcx, [rsp+520h+Src]; hKey
0x180022e46  test    rcx, rcx
0x180022e49  jz      short loc_180022E51
0x180022e4b  call    cs:__imp_RegCloseKey
0x180022e51  mov     [rsp+520h+lpcbData], rsi; lpftLastWriteTime
0x180022e56  mov     [rsp+520h+lpData], rsi; lpcchClass
0x180022e5b  mov     [rsp+520h+lpType], rsi; lpClass
0x180022e60  mov     [rsp+520h+lpReserved], rsi; lpReserved
0x180022e65  lea     r9, [rsp+520h+cchName]; lpcchName
0x180022e6a  lea     r8, [rbp+420h+Name]; lpName
0x180022e71  mov     edx, edi; dwIndex
0x180022e73  mov     rcx, r15; hKey
0x180022e76  call    cs:__imp_RegEnumKeyExW
0x180022e7c  cmp     eax, 103h
0x180022e81  lea     rbx, asc_18003F42C; "|"
0x180022e88  jnz     loc_180022D7B
0x180022e8e  xor     eax, eax
0x180022e90  mov     rcx, [rbp+420h+var_40]
0x180022e97  xor     rcx, rsp; StackCookie
0x180022e9a  call    __security_check_cookie
0x180022e9f  mov     rbx, [rsp+520h+arg_18]
0x180022ea7  add     rsp, 4F0h
0x180022eae  pop     r15
0x180022eb0  pop     r14
0x180022eb2  pop     r13
0x180022eb4  pop     r12
0x180022eb6  pop     rdi
0x180022eb7  pop     rsi
0x180022eb8  pop     rbp
0x180022eb9  retn
0x180022eba  mov     rcx, [rbp+428h]; this
0x180022ec1  mov     r9d, eax; char *
0x180022ec4  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180022ecb  mov     edx, 7Fh; void *
0x180022ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ed5  jmp     short loc_180022F03
0x180022ed7  mov     rcx, [rbp+428h]; this
0x180022ede  mov     r9d, eax; char *
0x180022ee1  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180022ee8  mov     edx, 86h; void *
0x180022eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ef2  nop
0x180022ef3  mov     rcx, [rsp+520h+Src]; lpMem
0x180022ef8  test    rcx, rcx
0x180022efb  jz      short loc_180022F03
0x180022efd  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180022f02  nop
0x180022f03  lea     rcx, [rsp+520h+var_4A8]; void *
0x180022f08  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022f0d  mov     eax, ebx
0x180022f0f  jmp     loc_180022E90
0x180022f14  mov     edx, 76h ; 'v'; void *
0x180022f19  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180022f20  mov     r9d, eax; char *
0x180022f23  mov     rcx, [rbp+428h]; this
0x180022f2a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022f2f  jmp     loc_180022E90
0x180022f34  mov     rcx, [rbp+428h]; this
0x180022f3b  mov     r9d, eax; char *
0x180022f3e  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180022f45  mov     edx, 0ADh; void *
  ... truncated ...
```
