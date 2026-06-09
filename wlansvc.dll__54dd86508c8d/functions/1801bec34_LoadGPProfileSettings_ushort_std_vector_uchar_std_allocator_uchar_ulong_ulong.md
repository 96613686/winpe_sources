# LoadGPProfileSettings(ushort *,std::vector<uchar,std::allocator<uchar>> &,ulong &,ulong &)

- ea: `0x1801bec34`
- end: `0x1801bf114`
- name: `?LoadGPProfileSettings@@YAJPEAGAEAV?$vector@EV?$allocator@E@std@@@std@@AEAK2@Z`
- size: `1248`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180105384`

## callees

- `0x180011530`
- `0x18001c9cc`
- `0x180036110`
- `0x18003fda0`
- `0x18006a050`
- `0x180106340`
- `0x180107330`
- `0x18010de0c`
- `0x1801bec34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bee07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801beea5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bef11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bef9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bf01d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bee07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801beea5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bef11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bef9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bf01d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801becc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bedd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801becc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bedd1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801bed67`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801bed67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LoadGPProfileSettings(__int64 a1, __int64 a2, BYTE *a3, BYTE *a4)
{
  HKEY *phkResult; // rax
  LSTATUS v9; // eax
  int v10; // ebx
  DWORD v11; // esi
  HKEY *v12; // rax
  WCHAR *v13; // rax
  int v14; // ecx
  int v15; // edx
  LSTATUS v16; // eax
  LPBYTE v17; // rdx
  __int64 v18; // rsi
  unsigned __int64 v19; // rcx
  BYTE *v20; // rax
  size_t v21; // rbx
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  _QWORD *v24; // rcx
  int v25; // edx
  WCHAR *v26; // r9
  HKEY v28; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v29; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v33; // [rsp+5Ch] [rbp-A4h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids);
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Wlansvc\\MigrationData\\Migration\\GroupPolicy\\Profiles",
         0,
         0x20019u,
         phkResult);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
        (unsigned int)L"Software\\Microsoft\\Wlansvc\\MigrationData\\Migration\\GroupPolicy\\Profiles",
        v9);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
    v11 = 0;
    while ( 1 )
    {
      do
      {
        if ( v10 == 259 )
        {
          v10 = -2147023728;
          goto LABEL_63;
        }
        cchName = 260;
        v10 = RegEnumKeyExW(hKey, v11++, Name, &cchName, 0, 0, 0, 0);
      }
      while ( v10 );
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, Name);
      v28 = 0;
      v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v28);
      v10 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, v12);
      if ( v10 )
        break;
      v10 = RegQueryValueExW(v28, L"Name", 0, 0, (LPBYTE)Name, &cchName);
      if ( v10 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v25 = 77;
          v26 = (WCHAR *)L"Name";
LABEL_58:
          WPP_SF_SD(v24[2], v25, (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, (_DWORD)v26, v10);
          goto LABEL_59;
        }
        goto LABEL_59;
      }
      v13 = Name;
      do
      {
        v14 = *(WCHAR *)((char *)v13 + a1 - (_QWORD)Name);
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, Name);
        cbData = 4;
        v16 = RegQueryValueExW(v28, L"ProfileIndex", 0, 0, a4, &cbData);
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              79,
              (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
              a1,
              v16);
          *(_DWORD *)a4 = 0;
        }
        v29 = 0;
        if ( !RegQueryValueExW(v28, L"Delta", 0, 0, 0, &v29) && v29 )
        {
          v17 = *(LPBYTE *)a2;
          v18 = *(_QWORD *)(a2 + 8);
          v19 = v18 - *(_QWORD *)a2;
          if ( v29 < v19 )
          {
            v20 = &v17[v29];
            goto LABEL_39;
          }
          if ( v29 > v19 )
          {
            if ( (unsigned __int64)v29 <= *(_QWORD *)(a2 + 16) - (_QWORD)v17 )
            {
              v21 = v29 - v19;
              memset_0(*(void **)(a2 + 8), 0, v21);
              v20 = (BYTE *)(v21 + v18);
LABEL_39:
              *(_QWORD *)(a2 + 8) = v20;
            }
            else
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, v29);
            }
          }
          v22 = RegQueryValueExW(v28, L"Delta", 0, 0, *(LPBYTE *)a2, &v29);
          if ( v22 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
                (unsigned int)L"Name",
                v22);
            if ( *(_QWORD *)a2 != *(_QWORD *)(a2 + 8) )
              *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
          }
        }
        v33 = 4;
        v23 = RegQueryValueExW(v28, L"Flags", 0, 0, a3, &v33);
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              81,
              (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
              a1,
              v23);
          *(_DWORD *)a3 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
        v10 = 0;
        goto LABEL_63;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v25 = 76;
      v26 = Name;
      goto LABEL_58;
    }
LABEL_59:
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
  }
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801bec34  push    rbp
0x1801bec36  push    rbx
0x1801bec37  push    rsi
0x1801bec38  push    rdi
0x1801bec39  push    r12
0x1801bec3b  push    r14
0x1801bec3d  push    r15
0x1801bec3f  lea     rbp, [rsp-180h]
0x1801bec47  sub     rsp, 280h
0x1801bec4e  mov     rax, cs:__security_cookie
0x1801bec55  xor     rax, rsp
0x1801bec58  mov     [rbp+1B0h+var_40], rax
0x1801bec5f  mov     r14, r9
0x1801bec62  mov     r12, r8
0x1801bec65  mov     rdi, rdx
0x1801bec68  mov     r15, rcx
0x1801bec6b  lea     rsi, WPP_GLOBAL_Control
0x1801bec72  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bec79  cmp     rcx, rsi
0x1801bec7c  jz      short loc_1801BEC99
0x1801bec7e  test    byte ptr [rcx+1Ch], 10h
0x1801bec82  jz      short loc_1801BEC99
0x1801bec84  mov     edx, 49h ; 'I'
0x1801bec89  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bec90  mov     rcx, [rcx+10h]
0x1801bec94  call    WPP_SF_
0x1801bec99  mov     [rsp+2B0h+hKey], 0
0x1801beca2  lea     rcx, [rsp+2B0h+hKey]
0x1801beca7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801becac  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801becb1  mov     r9d, 20019h; samDesired
0x1801becb7  xor     r8d, r8d; ulOptions
0x1801becba  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Wlansvc\\Migration"...
0x1801becc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801becc8  call    cs:__imp_RegOpenKeyExW
0x1801becce  mov     ebx, eax
0x1801becd0  test    eax, eax
0x1801becd2  jz      short loc_1801BED1C
0x1801becd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801becdb  cmp     rcx, rsi
0x1801becde  jz      short loc_1801BED06
0x1801bece0  test    byte ptr [rcx+1Ch], 2
0x1801bece4  jz      short loc_1801BED06
0x1801bece6  mov     edx, 4Ah ; 'J'
0x1801beceb  mov     dword ptr [rsp+2B0h+phkResult], eax
0x1801becef  lea     r9, aSoftwareMicros_17; "Software\\Microsoft\\Wlansvc\\Migration"...
0x1801becf6  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801becfd  mov     rcx, [rcx+10h]
0x1801bed01  call    WPP_SF_SD
0x1801bed06  test    ebx, ebx
0x1801bed08  jle     loc_1801BF0E7
0x1801bed0e  movzx   ebx, bx
0x1801bed11  or      ebx, 80070000h
0x1801bed17  jmp     loc_1801BF0E7
0x1801bed1c  xor     esi, esi
0x1801bed1e  cmp     ebx, 103h
0x1801bed24  jz      loc_1801BF0E2
0x1801bed2a  mov     [rsp+2B0h+cchName], 104h
0x1801bed32  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1801bed3b  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x1801bed44  mov     [rsp+2B0h+lpClass], 0; lpClass
0x1801bed4d  mov     [rsp+2B0h+phkResult], 0; lpReserved
0x1801bed56  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1801bed5b  lea     r8, [rsp+2B0h+Name]; lpName
0x1801bed60  mov     edx, esi; dwIndex
0x1801bed62  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801bed67  call    cs:__imp_RegEnumKeyExW
0x1801bed6d  mov     ebx, eax
0x1801bed6f  inc     esi
0x1801bed71  test    eax, eax
0x1801bed73  jnz     short loc_1801BED1E
0x1801bed75  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bed7c  lea     rax, WPP_GLOBAL_Control
0x1801bed83  cmp     rcx, rax
0x1801bed86  jz      short loc_1801BEDA6
0x1801bed88  test    byte ptr [rcx+1Ch], 10h
0x1801bed8c  jz      short loc_1801BEDA6
0x1801bed8e  lea     edx, [rbx+4Bh]
0x1801bed91  lea     r9, [rsp+2B0h+Name]
0x1801bed96  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bed9d  mov     rcx, [rcx+10h]
0x1801beda1  call    WPP_SF_S
0x1801beda6  mov     [rsp+2B0h+var_270], 0
0x1801bedaf  lea     rcx, [rsp+2B0h+var_270]
0x1801bedb4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801bedb9  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801bedbe  mov     r9d, 20019h; samDesired
0x1801bedc4  xor     r8d, r8d; ulOptions
0x1801bedc7  lea     rdx, [rsp+2B0h+Name]; lpSubKey
0x1801bedcc  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801bedd1  call    cs:__imp_RegOpenKeyExW
0x1801bedd7  mov     ebx, eax
0x1801bedd9  test    eax, eax
0x1801beddb  jnz     loc_1801BF092
0x1801bede1  lea     rax, [rsp+2B0h+cchName]
0x1801bede6  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1801bedeb  lea     rax, [rsp+2B0h+Name]
0x1801bedf0  mov     [rsp+2B0h+phkResult], rax; lpData
0x1801bedf5  xor     r9d, r9d; lpType
0x1801bedf8  xor     r8d, r8d; lpReserved
0x1801bedfb  lea     rdx, aName_2; "Name"
0x1801bee02  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1801bee07  call    cs:__imp_RegQueryValueExW
0x1801bee0d  mov     ebx, eax
0x1801bee0f  test    eax, eax
0x1801bee11  jnz     loc_1801BF06B
0x1801bee17  lea     rax, [rsp+2B0h+Name]
0x1801bee1c  mov     r8, r15
0x1801bee1f  sub     r8, rax
0x1801bee22  movzx   edx, word ptr [rax]
0x1801bee25  movzx   ecx, word ptr [rax+r8]
0x1801bee2a  sub     edx, ecx
0x1801bee2c  jnz     short loc_1801BEE36
0x1801bee2e  add     rax, 2
0x1801bee32  test    ecx, ecx
0x1801bee34  jnz     short loc_1801BEE22
0x1801bee36  test    edx, edx
0x1801bee38  jz      short loc_1801BEE49
0x1801bee3a  lea     rcx, [rsp+2B0h+var_270]
0x1801bee3f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bee44  jmp     loc_1801BED1E
0x1801bee49  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bee50  lea     rbx, WPP_GLOBAL_Control
0x1801bee57  cmp     rcx, rbx
0x1801bee5a  jz      short loc_1801BEE7C
0x1801bee5c  test    byte ptr [rcx+1Ch], 10h
0x1801bee60  jz      short loc_1801BEE7C
0x1801bee62  mov     edx, 4Eh ; 'N'
0x1801bee67  lea     r9, [rsp+2B0h+Name]
0x1801bee6c  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bee73  mov     rcx, [rcx+10h]
0x1801bee77  call    WPP_SF_S
0x1801bee7c  mov     [rsp+2B0h+cbData], 4
0x1801bee84  lea     rax, [rsp+2B0h+cbData]
0x1801bee89  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1801bee8e  mov     [rsp+2B0h+phkResult], r14; lpData
0x1801bee93  xor     r9d, r9d; lpType
0x1801bee96  xor     r8d, r8d; lpReserved
0x1801bee99  lea     rdx, aProfileindex_0; "ProfileIndex"
0x1801beea0  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1801beea5  call    cs:__imp_RegQueryValueExW
0x1801beeab  test    eax, eax
0x1801beead  jz      short loc_1801BEEE4
0x1801beeaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beeb6  cmp     rcx, rbx
0x1801beeb9  jz      short loc_1801BEEDD
0x1801beebb  test    byte ptr [rcx+1Ch], 8
0x1801beebf  jz      short loc_1801BEEDD
0x1801beec1  mov     edx, 4Fh ; 'O'
0x1801beec6  mov     dword ptr [rsp+2B0h+phkResult], eax
0x1801beeca  mov     r9, r15
0x1801beecd  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801beed4  mov     rcx, [rcx+10h]
0x1801beed8  call    WPP_SF_SD
0x1801beedd  mov     dword ptr [r14], 0
0x1801beee4  mov     [rsp+2B0h+var_268], 0
0x1801beeec  lea     rax, [rsp+2B0h+var_268]
0x1801beef1  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1801beef6  mov     [rsp+2B0h+phkResult], 0; lpData
0x1801beeff  xor     r9d, r9d; lpType
0x1801bef02  xor     r8d, r8d; lpReserved
0x1801bef05  lea     rdx, aDelta_0; "Delta"
0x1801bef0c  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1801bef11  call    cs:__imp_RegQueryValueExW
0x1801bef17  test    eax, eax
0x1801bef19  jnz     loc_1801BEFF4
0x1801bef1f  mov     eax, [rsp+2B0h+var_268]
0x1801bef23  test    eax, eax
0x1801bef25  jz      loc_1801BEFF4
0x1801bef2b  mov     ebx, eax
0x1801bef2d  mov     rdx, [rdi]
0x1801bef30  mov     rsi, [rdi+8]
0x1801bef34  mov     rcx, rsi
0x1801bef37  sub     rcx, rdx
0x1801bef3a  cmp     rax, rcx
0x1801bef3d  jnb     short loc_1801BEF44
0x1801bef3f  add     rax, rdx
0x1801bef42  jmp     short loc_1801BEF73
0x1801bef44  jbe     short loc_1801BEF77
0x1801bef46  mov     rax, [rdi+10h]
0x1801bef4a  sub     rax, rdx
0x1801bef4d  cmp     rbx, rax
0x1801bef50  jbe     short loc_1801BEF5F
0x1801bef52  mov     rdx, rbx
0x1801bef55  mov     rcx, rdi
0x1801bef58  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801bef5d  jmp     short loc_1801BEF77
0x1801bef5f  sub     rbx, rcx
0x1801bef62  mov     r8, rbx; Size
0x1801bef65  xor     edx, edx; Val
0x1801bef67  mov     rcx, rsi; void *
0x1801bef6a  call    memset_0
0x1801bef6f  lea     rax, [rbx+rsi]
0x1801bef73  mov     [rdi+8], rax
0x1801bef77  lea     rax, [rsp+2B0h+var_268]
0x1801bef7c  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1801bef81  mov     rax, [rdi]
0x1801bef84  mov     [rsp+2B0h+phkResult], rax; lpData
0x1801bef89  xor     r9d, r9d; lpType
0x1801bef8c  xor     r8d, r8d; lpReserved
0x1801bef8f  lea     rdx, aDelta_0; "Delta"
0x1801bef96  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1801bef9b  call    cs:__imp_RegQueryValueExW
0x1801befa1  test    eax, eax
0x1801befa3  jz      short loc_1801BEFED
0x1801befa5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801befac  lea     rbx, WPP_GLOBAL_Control
0x1801befb3  cmp     rcx, rbx
0x1801befb6  jz      short loc_1801BEFDE
0x1801befb8  test    byte ptr [rcx+1Ch], 8
0x1801befbc  jz      short loc_1801BEFDE
0x1801befbe  mov     edx, 50h ; 'P'
0x1801befc3  mov     dword ptr [rsp+2B0h+phkResult], eax
0x1801befc7  lea     r9, aName_2; "Name"
0x1801befce  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801befd5  mov     rcx, [rcx+10h]
0x1801befd9  call    WPP_SF_SD
0x1801befde  mov     rax, [rdi]
0x1801befe1  cmp     rax, [rdi+8]
0x1801befe5  jz      short loc_1801BEFF4
0x1801befe7  mov     [rdi+8], rax
0x1801befeb  jmp     short loc_1801BEFF4
0x1801befed  lea     rbx, WPP_GLOBAL_Control
0x1801beff4  mov     [rsp+2B0h+var_254], 4
0x1801beffc  lea     rax, [rsp+2B0h+var_254]
0x1801bf001  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1801bf006  mov     [rsp+2B0h+phkResult], r12; lpData
0x1801bf00b  xor     r9d, r9d; lpType
0x1801bf00e  xor     r8d, r8d; lpReserved
0x1801bf011  lea     rdx, aFlags_1; "Flags"
0x1801bf018  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1801bf01d  call    cs:__imp_RegQueryValueExW
0x1801bf023  test    eax, eax
0x1801bf025  jz      short loc_1801BF05D
0x1801bf027  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bf02e  cmp     rcx, rbx
0x1801bf031  jz      short loc_1801BF055
0x1801bf033  test    byte ptr [rcx+1Ch], 8
0x1801bf037  jz      short loc_1801BF055
0x1801bf039  mov     edx, 51h ; 'Q'
0x1801bf03e  mov     dword ptr [rsp+2B0h+phkResult], eax
0x1801bf042  mov     r9, r15
0x1801bf045  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bf04c  mov     rcx, [rcx+10h]
0x1801bf050  call    WPP_SF_SD
0x1801bf055  mov     dword ptr [r12], 0
0x1801bf05d  lea     rcx, [rsp+2B0h+var_270]
0x1801bf062  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bf067  xor     ebx, ebx
0x1801bf069  jmp     short loc_1801BF0E7
0x1801bf06b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bf072  lea     rax, WPP_GLOBAL_Control
0x1801bf079  cmp     rcx, rax
0x1801bf07c  jz      short loc_1801BF0C9
0x1801bf07e  test    byte ptr [rcx+1Ch], 2
0x1801bf082  jz      short loc_1801BF0C9
0x1801bf084  mov     edx, 4Dh ; 'M'
0x1801bf089  lea     r9, aName_2; "Name"
0x1801bf090  jmp     short loc_1801BF0B5
0x1801bf092  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bf099  lea     rax, WPP_GLOBAL_Control
0x1801bf0a0  cmp     rcx, rax
0x1801bf0a3  jz      short loc_1801BF0C9
0x1801bf0a5  test    byte ptr [rcx+1Ch], 2
0x1801bf0a9  jz      short loc_1801BF0C9
0x1801bf0ab  mov     edx, 4Ch ; 'L'
0x1801bf0b0  lea     r9, [rsp+2B0h+Name]
0x1801bf0b5  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1801bf0b9  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bf0c0  mov     rcx, [rcx+10h]
0x1801bf0c4  call    WPP_SF_SD
0x1801bf0c9  test    ebx, ebx
0x1801bf0cb  jle     short loc_1801BF0D6
0x1801bf0cd  movzx   ebx, bx
0x1801bf0d0  or      ebx, 80070000h
0x1801bf0d6  lea     rcx, [rsp+2B0h+var_270]
0x1801bf0db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bf0e0  jmp     short loc_1801BF0E7
0x1801bf0e2  mov     ebx, 80070490h
0x1801bf0e7  lea     rcx, [rsp+2B0h+hKey]
0x1801bf0ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bf0f1  mov     eax, ebx
0x1801bf0f3  mov     rcx, [rbp+1B0h+var_40]
0x1801bf0fa  xor     rcx, rsp; StackCookie
0x1801bf0fd  call    __security_check_cookie
0x1801bf102  add     rsp, 280h
0x1801bf109  pop     r15
0x1801bf10b  pop     r14
0x1801bf10d  pop     r12
0x1801bf10f  pop     rdi
0x1801bf110  pop     rsi
0x1801bf111  pop     rbx
0x1801bf112  pop     rbp
0x1801bf113  retn
```
