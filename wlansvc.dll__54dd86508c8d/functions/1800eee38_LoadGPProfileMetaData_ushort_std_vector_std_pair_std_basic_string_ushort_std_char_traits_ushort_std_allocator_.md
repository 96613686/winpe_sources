# LoadGPProfileMetaData(ushort *,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<uchar,std::allocator<uchar>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<uchar,std::allocator<uchar>>>>> &)

- ea: `0x1800eee38`
- end: `0x1800ef4b7`
- name: `?LoadGPProfileMetaData@@YAJPEAGAEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@@2@@std@@@Z`
- size: `1663`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180105384`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180036110`
- `0x18003fda0`
- `0x18007d770`
- `0x1800c2f98`
- `0x1800ca87c`
- `0x1800eee38`
- `0x180106340`
- `0x180108cfc`
- `0x1801bdc08`
- `0x1801bdf44`
- `0x1801be66c`
- `0x1801bf5fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ef08b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ef08b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eeed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eeffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ef17e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eeed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eeffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ef17e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ef1e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ef1e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ef2b4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ef2b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef41d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef41d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef458`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800eef95`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800eef95`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LoadGPProfileMetaData(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  signed int v3; // edi
  LSTATUS v4; // eax
  LSTATUS v5; // esi
  PVOID *v6; // rcx
  int v7; // r14d
  DWORD i; // r13d
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  WCHAR *v11; // rax
  int v12; // edx
  int v13; // r8d
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  unsigned __int64 v16; // rax
  WCHAR *v17; // r15
  BYTE *v18; // rax
  const struct std::nothrow_t *v19; // rdx
  BYTE *v20; // r14
  DWORD v21; // edi
  __int64 *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  const struct std::nothrow_t *v26; // rdx
  __int64 v28; // [rsp+0h] [rbp-378h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-318h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-314h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-310h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-308h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-300h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-2FCh] BYREF
  DWORD v35; // [rsp+80h] [rbp-2F8h]
  int v36; // [rsp+84h] [rbp-2F4h]
  DWORD v37; // [rsp+88h] [rbp-2F0h]
  HKEY hKey; // [rsp+90h] [rbp-2E8h] BYREF
  HKEY v39; // [rsp+98h] [rbp-2E0h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-2D8h]
  WCHAR *v41; // [rsp+A8h] [rbp-2D0h]
  BYTE *v42; // [rsp+B0h] [rbp-2C8h]
  __int64 v43; // [rsp+B8h] [rbp-2C0h]
  WCHAR *v44; // [rsp+C0h] [rbp-2B8h] BYREF
  _QWORD v45[3]; // [rsp+C8h] [rbp-2B0h] BYREF
  _BYTE v46[24]; // [rsp+E0h] [rbp-298h] BYREF
  _BYTE v47[56]; // [rsp+F8h] [rbp-280h] BYREF
  WCHAR Name[264]; // [rsp+130h] [rbp-248h] BYREF

  v40 = a2;
  v2 = a1;
  v43 = a2;
  hKey = 0;
  v3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Wlansvc\\MigrationData\\Migration\\GroupPolicy\\Profiles",
         0,
         0x20019u,
         &hKey);
  v5 = v4;
  if ( !v4 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_14:
    v7 = 0;
    for ( i = 0; ; ++i )
    {
      v37 = i;
      if ( v5 == 259 || v7 )
      {
        if ( v3 >= 0 && !v7 )
          v3 = -2147023728;
        goto LABEL_74;
      }
      cchName = 260;
      v5 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v5 )
        goto LABEL_69;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, Name);
      phkResult = 0;
      v9 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v5 = v9;
      if ( v9 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            91,
            (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
            (unsigned int)Name,
            v9);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        v3 = v5 > 0 ? (unsigned __int16)v5 | 0x80070000 : v5;
      }
      else
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 >= 0 )
        break;
LABEL_70:
      ;
    }
    v10 = RegQueryValueExW(phkResult, L"Name", 0, 0, (LPBYTE)Name, &cchName);
    v5 = v10;
    if ( v10 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          92,
          (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
          (unsigned int)L"Name",
          v10);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      else
        v3 = v5;
      if ( v3 < 0 )
        goto LABEL_67;
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = Name;
    do
    {
      v12 = *(WCHAR *)((char *)v11 + v2 - (_QWORD)Name);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    if ( !v13 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_S(v6[2], 93, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, Name);
      v7 = 1;
      v36 = 1;
      v39 = 0;
      v14 = RegOpenKeyExW(phkResult, L"MetaData", 0, 0x20019u, &v39);
      v3 = v14;
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      cbMaxValueNameLen = 0;
      cbMaxValueLen = 0;
      if ( v3 >= 0 )
      {
        v15 = RegQueryInfoKeyW(v39, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
        v3 = v15;
        if ( v15 > 0 )
          v3 = (unsigned __int16)v15 | 0x80070000;
        if ( v3 >= 0 )
        {
          v16 = 2LL * (cbMaxValueNameLen + 1);
          if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
            v16 = -1;
          v17 = (WCHAR *)operator new[](v16, (const struct std::nothrow_t *)std::nothrow);
          v41 = v17;
          v18 = (BYTE *)operator new[](cbMaxValueLen, (const struct std::nothrow_t *)std::nothrow);
          v20 = v18;
          v42 = v18;
          if ( v17 && (v21 = 0, v35 = 0, v18) )
          {
            while ( v5 != 259 )
            {
              cchValueName = cbMaxValueNameLen + 1;
              cbData = cbMaxValueLen;
              v5 = RegEnumValueW(v39, v21, v17, &cchValueName, 0, 0, v20, &cbData);
              if ( !v5 && !(unsigned int)IsBlockedMetaData(v17) )
              {
                try
                {
                  v22 = (__int64 *)std::vector<unsigned char>::vector<unsigned char>(v46, v20, &v20[cbData]);
                  v44 = v17;
                  v23 = v22[2];
                  v22[2] = 0;
                  v24 = v22[1];
                  v22[1] = 0;
                  v25 = *v22;
                  *v22 = 0;
                  v45[0] = v25;
                  v45[1] = v24;
                  v45[2] = v23;
                  std::pair<std::wstring,std::vector<unsigned char>>::pair<std::wstring,std::vector<unsigned char>>(
                    v47,
                    &v44);
                  std::vector<std::pair<std::wstring,std::vector<unsigned char>>>::push_back(v40, v47);
                  std::pair<std::wstring,std::vector<unsigned char>>::~pair<std::wstring,std::vector<unsigned char>>(v47);
                  std::vector<unsigned char>::_Tidy(v45);
                  std::vector<unsigned char>::_Tidy(v46);
                }
                catch ( std::bad_alloc )
                {
                  v19 = (const struct std::nothrow_t *)&v28;
                  cchValueName = 14;
                  v5 = 14;
                  i = v37;
                  v21 = v35;
                  v17 = v41;
                  v20 = v42;
                  v40 = v43;
                }
              }
              v35 = ++v21;
            }
            v3 = 0;
            v5 = 0;
          }
          else
          {
            v3 = -2147024882;
            v5 = 14;
          }
          operator delete(v17, v19);
          operator delete(v20, v26);
          v7 = v36;
          v2 = a1;
        }
      }
      if ( v39 )
        RegCloseKey(v39);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_67:
    if ( !phkResult )
      goto LABEL_70;
    RegCloseKey(phkResult);
    phkResult = 0;
LABEL_69:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_70;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Wlansvc\\MigrationData\\Migration\\GroupPolicy\\Profiles",
      v4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  else
    v3 = v5;
  if ( v3 >= 0 )
    goto LABEL_14;
LABEL_74:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    WPP_SF_d(v6[2], 94, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800eee38  mov     r11, rsp
0x1800eee3b  mov     [r11+18h], rbx
0x1800eee3f  mov     [r11+20h], rsi
0x1800eee43  mov     [r11+8], rcx
0x1800eee47  push    rdi
0x1800eee48  push    r12
0x1800eee4a  push    r13
0x1800eee4c  push    r14
0x1800eee4e  push    r15
0x1800eee50  sub     rsp, 350h
0x1800eee57  mov     rax, cs:__security_cookie
0x1800eee5e  xor     rax, rsp
0x1800eee61  mov     [rsp+378h+var_38], rax
0x1800eee69  mov     [rsp+378h+var_2D8], rdx
0x1800eee71  mov     r15, rcx
0x1800eee74  mov     [rsp+378h+var_2C0], rdx
0x1800eee7c  xor     ebx, ebx
0x1800eee7e  mov     [r11-2E8h], rbx
0x1800eee85  mov     edi, ebx
0x1800eee87  lea     r12, WPP_GLOBAL_Control
0x1800eee8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eee95  cmp     rcx, r12
0x1800eee98  jz      short loc_1800EEEB3
0x1800eee9a  test    byte ptr [rcx+1Ch], 10h
0x1800eee9e  jz      short loc_1800EEEB3
0x1800eeea0  lea     edx, [rbx+58h]
0x1800eeea3  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800eeeaa  mov     rcx, [rcx+10h]
0x1800eeeae  call    WPP_SF_
0x1800eeeb3  lea     rax, [rsp+378h+hKey]
0x1800eeebb  mov     [rsp+378h+phkResult], rax; phkResult
0x1800eeec0  mov     r9d, 20019h; samDesired
0x1800eeec6  xor     r8d, r8d; ulOptions
0x1800eeec9  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Wlansvc\\Migration"...
0x1800eeed0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eeed7  call    cs:__imp_RegOpenKeyExW
0x1800eeedd  mov     esi, eax
0x1800eeedf  test    eax, eax
0x1800eeee1  jz      short loc_1800EEF37
0x1800eeee3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eeeea  cmp     rcx, r12
0x1800eeeed  jz      short loc_1800EEF1C
0x1800eeeef  test    byte ptr [rcx+1Ch], 2
0x1800eeef3  jz      short loc_1800EEF1C
0x1800eeef5  mov     edx, 59h ; 'Y'
0x1800eeefa  mov     dword ptr [rsp+378h+phkResult], eax
0x1800eeefe  lea     r9, aSoftwareMicros_17; "Software\\Microsoft\\Wlansvc\\Migration"...
0x1800eef05  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800eef0c  mov     rcx, [rcx+10h]
0x1800eef10  call    WPP_SF_SD
0x1800eef15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eef1c  test    esi, esi
0x1800eef1e  jg      short loc_1800EEF24
0x1800eef20  mov     edi, esi
0x1800eef22  jmp     short loc_1800EEF2D
0x1800eef24  movzx   edi, si
0x1800eef27  or      edi, 80070000h
0x1800eef2d  test    edi, edi
0x1800eef2f  js      loc_1800EF446
0x1800eef35  jmp     short loc_1800EEF3E
0x1800eef37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eef3e  mov     r14d, ebx
0x1800eef41  mov     r13d, ebx
0x1800eef44  mov     [rsp+378h+var_2F0], r13d
0x1800eef4c  cmp     esi, 103h
0x1800eef52  jz      loc_1800EF437
0x1800eef58  test    r14d, r14d
0x1800eef5b  jnz     loc_1800EF437
0x1800eef61  mov     [rsp+378h+cchName], 104h
0x1800eef69  mov     [rsp+378h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800eef6e  mov     [rsp+378h+lpcchClass], rbx; lpcchClass
0x1800eef73  mov     [rsp+378h+lpClass], rbx; lpClass
0x1800eef78  mov     [rsp+378h+phkResult], rbx; lpReserved
0x1800eef7d  lea     r9, [rsp+378h+cchName]; lpcchName
0x1800eef82  lea     r8, [rsp+378h+Name]; lpName
0x1800eef8a  mov     edx, r13d; dwIndex
0x1800eef8d  mov     rcx, [rsp+378h+hKey]; hKey
0x1800eef95  call    cs:__imp_RegEnumKeyExW
0x1800eef9b  mov     esi, eax
0x1800eef9d  test    eax, eax
0x1800eef9f  jnz     loc_1800EF428
0x1800eefa5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eefac  cmp     rcx, r12
0x1800eefaf  jz      short loc_1800EEFD2
0x1800eefb1  test    byte ptr [rcx+1Ch], 10h
0x1800eefb5  jz      short loc_1800EEFD2
0x1800eefb7  lea     edx, [rax+5Ah]
0x1800eefba  lea     r9, [rsp+378h+Name]
0x1800eefc2  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800eefc9  mov     rcx, [rcx+10h]
0x1800eefcd  call    WPP_SF_S
0x1800eefd2  mov     [rsp+378h+var_308], rbx
0x1800eefd7  lea     rax, [rsp+378h+var_308]
0x1800eefdc  mov     [rsp+378h+phkResult], rax; phkResult
0x1800eefe1  mov     r9d, 20019h; samDesired
0x1800eefe7  xor     r8d, r8d; ulOptions
0x1800eefea  lea     rdx, [rsp+378h+Name]; lpSubKey
0x1800eeff2  mov     rcx, [rsp+378h+hKey]; hKey
0x1800eeffa  call    cs:__imp_RegOpenKeyExW
0x1800ef000  mov     esi, eax
0x1800ef002  test    eax, eax
0x1800ef004  jz      short loc_1800EF053
0x1800ef006  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef00d  cmp     rcx, r12
0x1800ef010  jz      short loc_1800EF040
0x1800ef012  test    byte ptr [rcx+1Ch], 2
0x1800ef016  jz      short loc_1800EF040
0x1800ef018  mov     edx, 5Bh ; '['
0x1800ef01d  mov     dword ptr [rsp+378h+phkResult], eax
0x1800ef021  lea     r9, [rsp+378h+Name]
0x1800ef029  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800ef030  mov     rcx, [rcx+10h]
0x1800ef034  call    WPP_SF_SD
0x1800ef039  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef040  test    esi, esi
0x1800ef042  jg      short loc_1800EF048
0x1800ef044  mov     edi, esi
0x1800ef046  jmp     short loc_1800EF05A
0x1800ef048  movzx   edi, si
0x1800ef04b  or      edi, 80070000h
0x1800ef051  jmp     short loc_1800EF05A
0x1800ef053  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef05a  test    edi, edi
0x1800ef05c  js      loc_1800EF42F
0x1800ef062  lea     rax, [rsp+378h+cchName]
0x1800ef067  mov     [rsp+378h+lpClass], rax; lpcbData
0x1800ef06c  lea     rax, [rsp+378h+Name]
0x1800ef074  mov     [rsp+378h+phkResult], rax; lpData
0x1800ef079  xor     r9d, r9d; lpType
0x1800ef07c  xor     r8d, r8d; lpReserved
0x1800ef07f  lea     rdx, aName_2; "Name"
0x1800ef086  mov     rcx, [rsp+378h+var_308]; hKey
0x1800ef08b  call    cs:__imp_RegQueryValueExW
0x1800ef091  mov     esi, eax
0x1800ef093  test    eax, eax
0x1800ef095  jz      short loc_1800EF0EB
0x1800ef097  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef09e  cmp     rcx, r12
0x1800ef0a1  jz      short loc_1800EF0D0
0x1800ef0a3  test    byte ptr [rcx+1Ch], 2
0x1800ef0a7  jz      short loc_1800EF0D0
0x1800ef0a9  mov     edx, 5Ch ; '\'
0x1800ef0ae  mov     dword ptr [rsp+378h+phkResult], eax
0x1800ef0b2  lea     r9, aName_2; "Name"
0x1800ef0b9  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800ef0c0  mov     rcx, [rcx+10h]
0x1800ef0c4  call    WPP_SF_SD
0x1800ef0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef0d0  test    esi, esi
0x1800ef0d2  jg      short loc_1800EF0D8
0x1800ef0d4  mov     edi, esi
0x1800ef0d6  jmp     short loc_1800EF0E1
0x1800ef0d8  movzx   edi, si
0x1800ef0db  or      edi, 80070000h
0x1800ef0e1  test    edi, edi
0x1800ef0e3  js      loc_1800EF411
0x1800ef0e9  jmp     short loc_1800EF0F2
0x1800ef0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef0f2  lea     rax, [rsp+378h+Name]
0x1800ef0fa  mov     r9, r15
0x1800ef0fd  sub     r9, rax
0x1800ef100  movzx   r8d, word ptr [rax]
0x1800ef104  movzx   edx, word ptr [rax+r9]
0x1800ef109  sub     r8d, edx
0x1800ef10c  jnz     short loc_1800EF116
0x1800ef10e  add     rax, 2
0x1800ef112  test    edx, edx
0x1800ef114  jnz     short loc_1800EF100
0x1800ef116  test    r8d, r8d
0x1800ef119  jnz     loc_1800EF411
0x1800ef11f  cmp     rcx, r12
0x1800ef122  jz      short loc_1800EF146
0x1800ef124  test    byte ptr [rcx+1Ch], 10h
0x1800ef128  jz      short loc_1800EF146
0x1800ef12a  lea     edx, [r8+5Dh]
0x1800ef12e  lea     r9, [rsp+378h+Name]
0x1800ef136  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1800ef13d  mov     rcx, [rcx+10h]
0x1800ef141  call    WPP_SF_S
0x1800ef146  mov     r14d, 1
0x1800ef14c  mov     [rsp+378h+var_2F4], r14d
0x1800ef154  mov     [rsp+378h+var_2E0], rbx
0x1800ef15c  lea     rax, [rsp+378h+var_2E0]
0x1800ef164  mov     [rsp+378h+phkResult], rax; phkResult
0x1800ef169  mov     r9d, 20019h; samDesired
0x1800ef16f  xor     r8d, r8d; ulOptions
0x1800ef172  lea     rdx, aMetadata_1; "MetaData"
0x1800ef179  mov     rcx, [rsp+378h+var_308]; hKey
0x1800ef17e  call    cs:__imp_RegOpenKeyExW
0x1800ef184  mov     edi, eax
0x1800ef186  test    eax, eax
0x1800ef188  jle     short loc_1800EF193
0x1800ef18a  movzx   edi, ax
0x1800ef18d  or      edi, 80070000h
0x1800ef193  mov     [rsp+378h+cbMaxValueNameLen], ebx
0x1800ef197  mov     [rsp+378h+cbMaxValueLen], ebx
0x1800ef19b  test    edi, edi
0x1800ef19d  js      loc_1800EF3F7
0x1800ef1a3  mov     [rsp+378h+var_320], rbx; lpftLastWriteTime
0x1800ef1a8  mov     [rsp+378h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800ef1ad  lea     rax, [rsp+378h+cbMaxValueLen]
0x1800ef1b2  mov     [rsp+378h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800ef1b7  lea     rax, [rsp+378h+cbMaxValueNameLen]
0x1800ef1bc  mov     [rsp+378h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800ef1c1  mov     [rsp+378h+lpftLastWriteTime], rbx; lpcValues
0x1800ef1c6  mov     [rsp+378h+lpcchClass], rbx; lpcbMaxClassLen
0x1800ef1cb  mov     [rsp+378h+lpClass], rbx; lpcbMaxSubKeyLen
0x1800ef1d0  mov     [rsp+378h+phkResult], rbx; lpcSubKeys
0x1800ef1d5  xor     r9d, r9d; lpReserved
0x1800ef1d8  xor     r8d, r8d; lpcchClass
0x1800ef1db  xor     edx, edx; lpClass
0x1800ef1dd  mov     rcx, [rsp+378h+var_2E0]; hKey
0x1800ef1e5  call    cs:__imp_RegQueryInfoKeyW
0x1800ef1eb  mov     edi, eax
0x1800ef1ed  test    eax, eax
0x1800ef1ef  jle     short loc_1800EF1FA
0x1800ef1f1  movzx   edi, ax
0x1800ef1f4  or      edi, 80070000h
0x1800ef1fa  test    edi, edi
0x1800ef1fc  js      loc_1800EF3F7
0x1800ef202  mov     ecx, [rsp+378h+cbMaxValueNameLen]
0x1800ef206  inc     ecx
0x1800ef208  mov     eax, 2
0x1800ef20d  mul     rcx
0x1800ef210  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ef217  cmovb   rax, rcx
0x1800ef21b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ef222  mov     rcx, rax; unsigned __int64
0x1800ef225  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ef22a  mov     r15, rax
0x1800ef22d  mov     [rsp+378h+var_2D0], rax
0x1800ef235  mov     ecx, [rsp+378h+cbMaxValueLen]; unsigned __int64
0x1800ef239  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ef240  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ef245  mov     r14, rax
0x1800ef248  mov     [rsp+378h+var_2C8], rax
0x1800ef250  test    r15, r15
0x1800ef253  jz      loc_1800EF3CD
0x1800ef259  mov     edi, ebx
0x1800ef25b  mov     [rsp+378h+var_2F8], ebx
0x1800ef262  test    rax, rax
0x1800ef265  jz      loc_1800EF3CD
0x1800ef26b  cmp     esi, 103h
0x1800ef271  jz      loc_1800EF3C7
0x1800ef277  mov     eax, [rsp+378h+cbMaxValueNameLen]
0x1800ef27b  inc     eax
0x1800ef27d  mov     [rsp+378h+cchValueName], eax
0x1800ef281  mov     eax, [rsp+378h+cbMaxValueLen]
0x1800ef285  mov     [rsp+378h+cbData], eax
0x1800ef289  lea     rax, [rsp+378h+cbData]
0x1800ef28e  mov     [rsp+378h+lpftLastWriteTime], rax; lpcbData
0x1800ef293  mov     [rsp+378h+lpcchClass], r14; lpData
0x1800ef298  mov     [rsp+378h+lpClass], rbx; lpType
0x1800ef29d  mov     [rsp+378h+phkResult], rbx; lpReserved
0x1800ef2a2  lea     r9, [rsp+378h+cchValueName]; lpcchValueName
0x1800ef2a7  mov     r8, r15; lpValueName
0x1800ef2aa  mov     edx, edi; dwIndex
0x1800ef2ac  mov     rcx, [rsp+378h+var_2E0]; hKey
0x1800ef2b4  call    cs:__imp_RegEnumValueW
0x1800ef2ba  mov     esi, eax
0x1800ef2bc  test    eax, eax
0x1800ef2be  jnz     loc_1800EF3B9
0x1800ef2c4  mov     rcx, r15; unsigned __int16 *
0x1800ef2c7  call    ?IsBlockedMetaData@@YAHPEBG@Z; IsBlockedMetaData(ushort const *)
0x1800ef2cc  test    eax, eax
0x1800ef2ce  jnz     loc_1800EF3B9
0x1800ef2d4  mov     r8d, [rsp+378h+cbData]
0x1800ef2d9  add     r8, r14
0x1800ef2dc  mov     rdx, r14
0x1800ef2df  lea     rcx, [rsp+378h+var_298]
0x1800ef2e7  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x1800ef2ec  mov     r8, rax
0x1800ef2ef  mov     [rsp+378h+var_2B8], r15
0x1800ef2f7  mov     rdx, [rax+10h]
0x1800ef2fb  mov     [rax+10h], rbx
0x1800ef2ff  mov     rcx, [rax+8]
0x1800ef303  mov     [rax+8], rbx
0x1800ef307  mov     rax, [rax]
0x1800ef30a  mov     [r8], rbx
0x1800ef30d  mov     [rsp+378h+var_2B0], rax
0x1800ef315  mov     [rsp+378h+var_2A8], rcx
0x1800ef31d  mov     [rsp+378h+var_2A0], rdx
0x1800ef325  lea     rdx, [rsp+378h+var_2B8]
0x1800ef32d  lea     rcx, [rsp+378h+var_280]
0x1800ef335  call    ??$?0PEAGV?$vector@EV?$allocator@E@std@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@QEAA@$$QEAU?$pair@PEAGV?$vector@EV?$allocator@E@std@@@std@@@1@@Z; std::pair<std::wstring,std::vector<uchar>>::pair<std::wstring,std::vector<uchar>>(std::pair<ushort *,std::vector<uchar>> &&)
0x1800ef33a  nop
0x1800ef33b  lea     rdx, [rsp+378h+var_280]
0x1800ef343  mov     rcx, [rsp+378h+var_2D8]
0x1800ef34b  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@2@@Z; std::vector<std::pair<std::wstring,std::vector<uchar>>>::push_back(std::pair<std::wstring,std::vector<uchar>> &&)
0x1800ef350  nop
0x1800ef351  lea     rcx, [rsp+378h+var_280]
0x1800ef359  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring,std::vector<uchar>>::~pair<std::wstring,std::vector<uchar>>(void)
0x1800ef35e  nop
0x1800ef35f  lea     rcx, [rsp+378h+var_2B0]
0x1800ef367  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ef36c  nop
0x1800ef36d  lea     rcx, [rsp+378h+var_298]
0x1800ef375  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ef37a  nop
0x1800ef37b  jmp     short loc_1800EF3B9
  ... truncated ...
```
