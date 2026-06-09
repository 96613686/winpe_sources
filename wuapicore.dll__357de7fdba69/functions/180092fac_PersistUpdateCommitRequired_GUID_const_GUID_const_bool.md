# PersistUpdateCommitRequired(_GUID const *,_GUID const &,bool)

- ea: `0x180092fac`
- end: `0x1800932a2`
- name: `?PersistUpdateCommitRequired@@YAXPEBU_GUID@@AEBU1@_N@Z`
- size: `758`
- prototype: `void __fastcall(GUID *rguid, GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025948`

## callees

- `0x18002ded8`
- `0x180090bc8`
- `0x180091d18`
- `0x1800928f0`
- `0x180092fac`
- `0x180093cf4`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180092fed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009300b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180092fed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009300b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093125`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800930f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093275`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800930f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093275`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180093163`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009325d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180093163`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009325d`

## string_xrefs

- `0x18009309f`: `PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u`
- `0x180093176`: `PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PersistUpdateCommitRequired(GUID *rguid, GUID *a2)
{
  __int64 v3; // rcx
  __int64 RegKeyPath; // rax
  __int64 v5; // r9
  wchar_t *v6; // r8
  __int64 v7; // rdx
  wchar_t v8; // ax
  wchar_t *v9; // rax
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  DWORD v12; // esi
  __int64 v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // rdx
  __int64 v16; // r9
  wchar_t v17; // ax
  wchar_t *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // [rsp+40h] [rbp-C0h]
  REGSAM samDesired; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR Name[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t v25[264]; // [rsp+100h] [rbp+0h] BYREF

  StringFromGUID2(a2, sz, 39);
  if ( rguid )
  {
    StringFromGUID2(rguid, Name, 39);
    RegKeyPath = GetRegKeyPath(2);
    v5 = 260;
    v6 = v25;
    v7 = RegKeyPath - (_QWORD)v25;
    do
    {
      if ( v5 == -2147483386 )
        break;
      v8 = *(wchar_t *)((char *)v6 + v7);
      if ( !v8 )
        break;
      *v6++ = v8;
      --v5;
    }
    while ( v5 );
    v9 = v6 - 1;
    if ( v5 )
      v9 = v6;
    *v9 = 0;
    StringCchCatW(v25, 0x104u, L"\\");
    StringCchCatW(v25, 0x104u, Name);
    WUTrace(0, 0, 32, 5, 0, L"PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u", Name, sz, 0);
    RegDelValue(v10, v25, sz);
  }
  else
  {
    hKey = 0;
    samDesired = 8;
    SetRegistryType(v3, &samDesired);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v11 = (const WCHAR *)GetRegKeyPath(2);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, samDesired, &hKey) )
    {
      v12 = 0;
      samDesired = 39;
      if ( !RegEnumKeyExW(hKey, 0, Name, &samDesired, 0, 0, 0, 0) )
      {
        do
        {
          LODWORD(v20) = 0;
          WUTrace(
            0,
            0,
            32,
            5,
            0,
            L"PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u",
            Name,
            sz,
            v20);
          v13 = GetRegKeyPath(2);
          v14 = 260;
          v15 = v25;
          v16 = v13 - (_QWORD)v25;
          do
          {
            if ( v14 == -2147483386 )
              break;
            v17 = *(wchar_t *)((char *)v15 + v16);
            if ( !v17 )
              break;
            *v15++ = v17;
            --v14;
          }
          while ( v14 );
          v18 = v15 - 1;
          if ( v14 )
            v18 = v15;
          *v18 = 0;
          StringCchCatW(v25, 0x104u, L"\\");
          StringCchCatW(v25, 0x104u, Name);
          RegDelValue(v19, v25, sz);
          ++v12;
          samDesired = 39;
        }
        while ( !RegEnumKeyExW(hKey, v12, Name, &samDesired, 0, 0, 0, 0) );
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180092fac  mov     [rsp-8+arg_10], rbx
0x180092fb1  mov     [rsp-8+arg_18], rsi
0x180092fb6  push    rbp
0x180092fb7  push    rdi
0x180092fb8  push    r14
0x180092fba  lea     rbp, [rsp-220h]
0x180092fc2  sub     rsp, 320h
0x180092fc9  mov     rax, cs:__security_cookie
0x180092fd0  xor     rax, rsp
0x180092fd3  mov     [rbp+230h+var_20], rax
0x180092fda  mov     rax, rdx
0x180092fdd  mov     rbx, rcx
0x180092fe0  mov     r8d, 27h ; '''; cchMax
0x180092fe6  lea     rdx, [rbp+230h+sz]; lpsz
0x180092fea  mov     rcx, rax; rguid
0x180092fed  call    cs:__imp_StringFromGUID2
0x180092ff3  xor     r14d, r14d
0x180092ff6  test    rbx, rbx
0x180092ff9  jz      loc_1800930D3
0x180092fff  lea     r8d, [r14+27h]; cchMax
0x180093003  lea     rdx, [rsp+330h+Name]; lpsz
0x180093008  mov     rcx, rbx; rguid
0x18009300b  call    cs:__imp_StringFromGUID2
0x180093011  lea     ecx, [r14+2]
0x180093015  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18009301a  mov     rdx, rax
0x18009301d  mov     ebx, 104h
0x180093022  mov     r9d, ebx
0x180093025  lea     r8, [rbp+230h+var_230]
0x180093029  lea     rax, [rbp+230h+var_230]
0x18009302d  sub     rdx, rax
0x180093030  lea     rcx, [r9+7FFFFEFAh]
0x180093037  test    rcx, rcx
0x18009303a  jz      short loc_180093054
0x18009303c  movzx   eax, word ptr [rdx+r8]
0x180093041  test    ax, ax
0x180093044  jz      short loc_180093054
0x180093046  mov     [r8], ax
0x18009304a  add     r8, 2
0x18009304e  sub     r9, 1
0x180093052  jnz     short loc_180093030
0x180093054  lea     rax, [r8-2]
0x180093058  test    r9, r9
0x18009305b  cmovnz  rax, r8
0x18009305f  mov     [rax], r14w
0x180093063  lea     r8, SubBlock; "\\"
0x18009306a  mov     rdx, rbx; unsigned __int64
0x18009306d  lea     rcx, [rbp+230h+var_230]; wchar_t *
0x180093071  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180093076  lea     r8, [rsp+330h+Name]; wchar_t *
0x18009307b  mov     rdx, rbx; unsigned __int64
0x18009307e  lea     rcx, [rbp+230h+var_230]; wchar_t *
0x180093082  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180093087  mov     [rsp+330h+var_2F0], r14d
0x18009308c  lea     rax, [rbp+230h+sz]
0x180093090  mov     [rsp+330h+lpftLastWriteTime], rax
0x180093095  lea     rax, [rsp+330h+Name]
0x18009309a  mov     [rsp+330h+lpcchClass], rax
0x18009309f  lea     rdi, aPersistupdatec_0; "PersistUpdateCommitRequired: idSrv=%ws,"...
0x1800930a6  mov     [rsp+330h+lpClass], rdi
0x1800930ab  mov     [rsp+330h+phkResult], r14
0x1800930b0  xor     edx, edx
0x1800930b2  xor     ecx, ecx
0x1800930b4  lea     r9d, [rdx+5]
0x1800930b8  lea     r8d, [rdx+20h]
0x1800930bc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800930c1  lea     r8, [rbp+230h+sz]
0x1800930c5  lea     rdx, [rbp+230h+var_230]
0x1800930c9  call    ?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z; RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1800930ce  jmp     loc_18009327B
0x1800930d3  mov     [rsp+330h+hKey], r14
0x1800930d8  mov     [rsp+330h+samDesired], 8
0x1800930e0  lea     rdx, [rsp+330h+samDesired]
0x1800930e5  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x1800930ea  mov     rcx, [rsp+330h+hKey]; hKey
0x1800930ef  test    rcx, rcx
0x1800930f2  jz      short loc_1800930FF
0x1800930f4  call    cs:__imp_RegCloseKey
0x1800930fa  mov     [rsp+330h+hKey], r14
0x1800930ff  mov     ecx, 2
0x180093104  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180093109  lea     rcx, [rsp+330h+hKey]
0x18009310e  mov     [rsp+330h+phkResult], rcx; phkResult
0x180093113  mov     r9d, [rsp+330h+samDesired]; samDesired
0x180093118  xor     r8d, r8d; ulOptions
0x18009311b  mov     rdx, rax; lpSubKey
0x18009311e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093125  call    cs:__imp_RegOpenKeyExW
0x18009312b  test    eax, eax
0x18009312d  jnz     loc_18009326B
0x180093133  mov     esi, r14d
0x180093136  mov     [rsp+330h+samDesired], 27h ; '''
0x18009313e  mov     [rsp+330h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180093143  mov     [rsp+330h+lpcchClass], r14; lpcchClass
0x180093148  mov     [rsp+330h+lpClass], r14; lpClass
0x18009314d  mov     [rsp+330h+phkResult], r14; lpReserved
0x180093152  lea     r9, [rsp+330h+samDesired]; lpcchName
0x180093157  lea     r8, [rsp+330h+Name]; lpName
0x18009315c  xor     edx, edx; dwIndex
0x18009315e  mov     rcx, [rsp+330h+hKey]; hKey
0x180093163  call    cs:__imp_RegEnumKeyExW
0x180093169  test    eax, eax
0x18009316b  jnz     loc_18009326B
0x180093171  mov     ebx, 104h
0x180093176  lea     rdi, aPersistupdatec_0; "PersistUpdateCommitRequired: idSrv=%ws,"...
0x18009317d  mov     [rsp+330h+var_2F0], r14d
0x180093182  lea     rax, [rbp+230h+sz]
0x180093186  mov     [rsp+330h+lpftLastWriteTime], rax
0x18009318b  lea     rax, [rsp+330h+Name]
0x180093190  mov     [rsp+330h+lpcchClass], rax
0x180093195  mov     [rsp+330h+lpClass], rdi
0x18009319a  mov     [rsp+330h+phkResult], r14
0x18009319f  xor     edx, edx
0x1800931a1  xor     ecx, ecx
0x1800931a3  lea     r9d, [rdx+5]
0x1800931a7  lea     r8d, [rdx+20h]
0x1800931ab  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800931b0  mov     ecx, 2
0x1800931b5  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1800931ba  mov     r9, rax
0x1800931bd  mov     r8, rbx
0x1800931c0  lea     rdx, [rbp+230h+var_230]
0x1800931c4  lea     rax, [rbp+230h+var_230]
0x1800931c8  sub     r9, rax
0x1800931cb  lea     rcx, [r8+7FFFFEFAh]
0x1800931d2  test    rcx, rcx
0x1800931d5  jz      short loc_1800931EE
0x1800931d7  movzx   eax, word ptr [r9+rdx]
0x1800931dc  test    ax, ax
0x1800931df  jz      short loc_1800931EE
0x1800931e1  mov     [rdx], ax
0x1800931e4  add     rdx, 2
0x1800931e8  sub     r8, 1
0x1800931ec  jnz     short loc_1800931CB
0x1800931ee  lea     rax, [rdx-2]
0x1800931f2  test    r8, r8
0x1800931f5  cmovnz  rax, rdx
0x1800931f9  mov     [rax], r14w
0x1800931fd  lea     r8, SubBlock; "\\"
0x180093204  mov     rdx, rbx; unsigned __int64
0x180093207  lea     rcx, [rbp+230h+var_230]; wchar_t *
0x18009320b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180093210  lea     r8, [rsp+330h+Name]; wchar_t *
0x180093215  mov     rdx, rbx; unsigned __int64
0x180093218  lea     rcx, [rbp+230h+var_230]; wchar_t *
0x18009321c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180093221  lea     r8, [rbp+230h+sz]
0x180093225  lea     rdx, [rbp+230h+var_230]
0x180093229  call    ?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z; RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18009322e  inc     esi
0x180093230  mov     [rsp+330h+samDesired], 27h ; '''
0x180093238  mov     [rsp+330h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18009323d  mov     [rsp+330h+lpcchClass], r14; lpcchClass
0x180093242  mov     [rsp+330h+lpClass], r14; lpClass
0x180093247  mov     [rsp+330h+phkResult], r14; lpReserved
0x18009324c  lea     r9, [rsp+330h+samDesired]; lpcchName
0x180093251  lea     r8, [rsp+330h+Name]; lpName
0x180093256  mov     edx, esi; dwIndex
0x180093258  mov     rcx, [rsp+330h+hKey]; hKey
0x18009325d  call    cs:__imp_RegEnumKeyExW
0x180093263  test    eax, eax
0x180093265  jz      loc_18009317D
0x18009326b  mov     rcx, [rsp+330h+hKey]; hKey
0x180093270  test    rcx, rcx
0x180093273  jz      short loc_18009327B
0x180093275  call    cs:__imp_RegCloseKey
0x18009327b  mov     rcx, [rbp+230h+var_20]
0x180093282  xor     rcx, rsp; StackCookie
0x180093285  call    __security_check_cookie
0x18009328a  lea     r11, [rsp+330h+var_10]
0x180093292  mov     rbx, [r11+30h]
0x180093296  mov     rsi, [r11+38h]
0x18009329a  mov     rsp, r11
0x18009329d  pop     r14
0x18009329f  pop     rdi
0x1800932a0  pop     rbp
0x1800932a1  retn
```
