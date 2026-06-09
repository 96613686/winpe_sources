# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180005770`
- end: `0x180005be3`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1139`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004a70`
- `0x180004b70`

## callees

- `0x180005770`
- `0x1800078c8`
- `0x1800079ac`
- `0x180007c10`
- `0x18002ff8c`
- `0x18002ff98`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000589c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000589c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000580e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000580e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800059ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005b30`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800059ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005b30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b76`

## string_xrefs

- `0x1800058ae`: `CLSID\`
- `0x180005a27`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rsi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // ecx
  errno_t v11; // eax
  errno_t v12; // eax
  errno_t v13; // eax
  HKEY v14; // rbx
  LSTATUS v15; // edi
  errno_t v16; // eax
  errno_t v17; // eax
  errno_t v18; // eax
  int v19; // eax
  HKEY v20; // rbx
  LSTATUS v21; // edi
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  _QWORD v26[3]; // [rsp+78h] [rbp-88h] BYREF
  DWORD cSubKeys; // [rsp+90h] [rbp-70h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-68h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a2;
  ppv = 0;
  v29 = 0;
  if ( !a2
    || !rguid->Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4]
    || CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
    goto LABEL_67;
  }
  while ( 1 )
  {
    v10 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
      break;
    v29 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( a3 )
    {
      v6 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v29);
      else
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v29);
      v8 = v7;
      if ( v7 < 0 )
        goto LABEL_68;
    }
    else
    {
      v9 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 48))(ppv, rguid, 1, &v29);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 64))(ppv, rguid, 1, &v29);
    }
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( a3 )
    goto LABEL_67;
  if ( !StringFromGUID2(rguid, sz, 64) )
  {
    v8 = 13;
    goto LABEL_68;
  }
  v11 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
  if ( v11 )
  {
    if ( v11 == 12 )
      goto LABEL_71;
    if ( v11 == 22 || v11 == 34 )
      goto LABEL_73;
    if ( v11 != 80 )
      goto LABEL_72;
  }
  v12 = wcscat_s(Destination, 0x80u, sz);
  if ( v12 )
  {
    if ( v12 == 12 )
      goto LABEL_71;
    if ( v12 == 22 || v12 == 34 )
      goto LABEL_73;
    if ( v12 != 80 )
      goto LABEL_72;
  }
  v13 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
  if ( v13 )
  {
    if ( v13 == 12 )
      goto LABEL_71;
    if ( v13 == 22 || v13 == 34 )
      goto LABEL_73;
    if ( v13 != 80 )
      goto LABEL_72;
  }
  v26[1] = 0;
  v26[0] = 0xFFFFFFFF80000000uLL;
  v26[2] = 0;
  v24 = 0;
  hKey = 0;
  v25 = 0;
  cSubKeys = 0;
  if ( !ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
  {
    v14 = hKey;
    v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v14 )
    {
      RegCloseKey(v14);
      hKey = 0;
    }
    LODWORD(v24) = 0;
    if ( !v15 && !cSubKeys )
      ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
  }
  v16 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
  if ( v16 )
  {
    if ( v16 == 12 )
      goto LABEL_71;
    if ( v16 == 22 || v16 == 34 )
      goto LABEL_73;
    if ( v16 != 80 )
      goto LABEL_72;
  }
  v17 = wcscat_s(Destination, 0x80u, sz);
  if ( v17 )
  {
    if ( v17 == 12 )
      goto LABEL_71;
    if ( v17 == 22 || v17 == 34 )
      goto LABEL_73;
    if ( v17 != 80 )
      goto LABEL_72;
  }
  v18 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
  if ( v18 )
  {
    if ( v18 != 12 )
    {
      if ( v18 != 22 && v18 != 34 )
      {
        if ( v18 == 80 )
          goto LABEL_58;
LABEL_72:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_73:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_71:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_58:
  v19 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u);
  v20 = hKey;
  if ( !v19 )
  {
    v21 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v20 )
    {
      RegCloseKey(v20);
      v20 = 0;
    }
    if ( !v21 && !cSubKeys )
      ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
  }
  if ( v20 )
    RegCloseKey(v20);
  RegCloseKey(HKEY_CLASSES_ROOT);
LABEL_67:
  v8 = 0;
LABEL_68:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180005770  mov     [rsp-8+arg_10], rbx
0x180005775  mov     [rsp-8+arg_18], rsi
0x18000577a  push    rbp
0x18000577b  push    rdi
0x18000577c  push    r12
0x18000577e  push    r14
0x180005780  push    r15
0x180005782  lea     rbp, [rsp-140h]
0x18000578a  sub     rsp, 240h
0x180005791  mov     rax, cs:__security_cookie
0x180005798  xor     rax, rsp
0x18000579b  mov     [rbp+160h+var_30], rax
0x1800057a2  mov     r14d, r8d
0x1800057a5  mov     rsi, rdx
0x1800057a8  mov     rbx, rcx
0x1800057ab  xor     r15d, r15d
0x1800057ae  mov     [rbp+160h+var_1C8], r15
0x1800057b2  xorps   xmm0, xmm0
0x1800057b5  movups  [rbp+160h+var_1C0], xmm0
0x1800057b9  test    rdx, rdx
0x1800057bc  jz      loc_180005B7C
0x1800057c2  cmp     [rcx], r15d
0x1800057c5  jnz     short loc_1800057EC
0x1800057c7  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800057cd  cmp     [rcx+4], eax
0x1800057d0  jnz     short loc_1800057EC
0x1800057d2  mov     eax, dword ptr cs:GUID_NULL.Data4
0x1800057d8  cmp     [rcx+8], eax
0x1800057db  jnz     short loc_1800057EC
0x1800057dd  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800057e3  cmp     [rcx+0Ch], eax
0x1800057e6  jz      loc_180005B7C
0x1800057ec  lea     rax, [rbp+160h+var_1C8]
0x1800057f0  mov     [rsp+260h+ppv], rax; ppv
0x1800057f5  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800057fc  mov     r12d, 1
0x180005802  mov     r8d, r12d; dwClsContext
0x180005805  xor     edx, edx; pUnkOuter
0x180005807  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000580e  call    cs:__imp_CoCreateInstance
0x180005814  test    eax, eax
0x180005816  js      loc_180005B7C
0x18000581c  jmp     short loc_18000587F
0x18000581e  mov     rax, [rsi+8]
0x180005822  movups  xmm0, xmmword ptr [rax]
0x180005825  movdqu  [rbp+160h+var_1C0], xmm0
0x18000582a  lea     r9, [rbp+160h+var_1C0]
0x18000582e  mov     r8d, r12d
0x180005831  mov     rdx, rbx
0x180005834  test    r14d, r14d
0x180005837  jz      short loc_180005860
0x180005839  cmp     ecx, r12d
0x18000583c  mov     rcx, [rbp+160h+var_1C8]
0x180005840  mov     rax, [rcx]
0x180005843  jnz     short loc_18000584B
0x180005845  mov     rax, [rax+28h]
0x180005849  jmp     short loc_18000584F
0x18000584b  mov     rax, [rax+38h]
0x18000584f  call    _guard_dispatch_icall
0x180005854  mov     edi, eax
0x180005856  test    eax, eax
0x180005858  js      loc_180005B7F
0x18000585e  jmp     short loc_18000587B
0x180005860  cmp     ecx, r12d
0x180005863  mov     rcx, [rbp+160h+var_1C8]
0x180005867  mov     rax, [rcx]
0x18000586a  jnz     short loc_180005872
0x18000586c  mov     rax, [rax+30h]
0x180005870  jmp     short loc_180005876
0x180005872  mov     rax, [rax+40h]
0x180005876  call    _guard_dispatch_icall
0x18000587b  add     rsi, 10h
0x18000587f  mov     ecx, [rsi]
0x180005881  test    ecx, ecx
0x180005883  jnz     short loc_18000581E
0x180005885  test    r14d, r14d
0x180005888  jnz     loc_180005B7C
0x18000588e  lea     r8d, [rcx+40h]; cchMax
0x180005892  lea     rdx, [rbp+160h+sz]; lpsz
0x180005899  mov     rcx, rbx; rguid
0x18000589c  call    cs:__imp_StringFromGUID2
0x1800058a2  test    eax, eax
0x1800058a4  jnz     short loc_1800058AE
0x1800058a6  lea     edi, [rax+0Dh]
0x1800058a9  jmp     loc_180005B7F
0x1800058ae  lea     r8, aClsid; "CLSID\\"
0x1800058b5  mov     ebx, 80h
0x1800058ba  mov     edx, ebx; SizeInWords
0x1800058bc  lea     rcx, [rbp+160h+Destination]; Destination
0x1800058c0  call    wcscpy_s
0x1800058c5  lea     esi, [rbx-30h]
0x1800058c8  lea     r12d, [rbx-74h]
0x1800058cc  lea     r14d, [rbx-5Eh]
0x1800058d0  test    eax, eax
0x1800058d2  jz      short loc_1800058F7
0x1800058d4  cmp     eax, r12d
0x1800058d7  jz      loc_180005BC2
0x1800058dd  cmp     eax, 16h
0x1800058e0  jz      loc_180005BD8
0x1800058e6  cmp     eax, r14d
0x1800058e9  jz      loc_180005BD8
0x1800058ef  cmp     eax, esi
0x1800058f1  jnz     loc_180005BCD
0x1800058f7  lea     r8, [rbp+160h+sz]; Source
0x1800058fe  mov     rdx, rbx; SizeInWords
0x180005901  lea     rcx, [rbp+160h+Destination]; Destination
0x180005905  call    wcscat_s
0x18000590a  test    eax, eax
0x18000590c  jz      short loc_180005931
0x18000590e  cmp     eax, r12d
0x180005911  jz      loc_180005BC2
0x180005917  cmp     eax, 16h
0x18000591a  jz      loc_180005BD8
0x180005920  cmp     eax, r14d
0x180005923  jz      loc_180005BD8
0x180005929  cmp     eax, esi
0x18000592b  jnz     loc_180005BCD
0x180005931  lea     r8, aRequiredCatego; "\\Required Categories"
0x180005938  mov     rdx, rbx; SizeInWords
0x18000593b  lea     rcx, [rbp+160h+Destination]; Destination
0x18000593f  call    wcscat_s
0x180005944  test    eax, eax
0x180005946  jz      short loc_18000596B
0x180005948  cmp     eax, r12d
0x18000594b  jz      loc_180005BC2
0x180005951  cmp     eax, 16h
0x180005954  jz      loc_180005BD8
0x18000595a  cmp     eax, r14d
0x18000595d  jz      loc_180005BD8
0x180005963  cmp     eax, esi
0x180005965  jnz     loc_180005BCD
0x18000596b  mov     [rbp+160h+var_1E0], r15
0x18000596f  mov     [rsp+260h+var_1E8], 0FFFFFFFF80000000h
0x180005978  mov     [rbp+160h+var_1D8], r15
0x18000597c  mov     [rsp+260h+var_1F8], r15
0x180005981  mov     [rsp+260h+hKey], r15
0x180005986  mov     [rsp+260h+var_1F0], r15
0x18000598b  mov     [rbp+160h+cSubKeys], r15d
0x18000598f  mov     r9d, 20019h; unsigned int
0x180005995  lea     r8, [rbp+160h+Destination]; wchar_t *
0x180005999  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x1800059a0  lea     rcx, [rsp+260h+hKey]; this
0x1800059a5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800059aa  test    eax, eax
0x1800059ac  jnz     short loc_180005A27
0x1800059ae  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800059b3  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800059b8  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800059bd  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800059c2  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800059c7  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800059cc  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800059d1  lea     rax, [rbp+160h+cSubKeys]
0x1800059d5  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800059da  xor     r9d, r9d; lpReserved
0x1800059dd  xor     r8d, r8d; lpcchClass
0x1800059e0  xor     edx, edx; lpClass
0x1800059e2  mov     rbx, [rsp+260h+hKey]
0x1800059e7  mov     rcx, rbx; hKey
0x1800059ea  call    cs:__imp_RegQueryInfoKeyW
0x1800059f0  mov     edi, eax
0x1800059f2  test    rbx, rbx
0x1800059f5  jz      short loc_180005A05
0x1800059f7  mov     rcx, rbx; hKey
0x1800059fa  call    cs:__imp_RegCloseKey
0x180005a00  mov     [rsp+260h+hKey], r15
0x180005a05  mov     dword ptr [rsp+260h+var_1F8], r15d
0x180005a0a  test    edi, edi
0x180005a0c  jnz     short loc_180005A22
0x180005a0e  cmp     [rbp+160h+cSubKeys], r15d
0x180005a12  jnz     short loc_180005A22
0x180005a14  lea     rdx, [rbp+160h+Destination]; wchar_t *
0x180005a18  lea     rcx, [rsp+260h+var_1E8]; this
0x180005a1d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180005a22  mov     ebx, 80h
0x180005a27  lea     r8, aClsid; "CLSID\\"
0x180005a2e  mov     rdx, rbx; SizeInWords
0x180005a31  lea     rcx, [rbp+160h+Destination]; Destination
0x180005a35  call    wcscpy_s
0x180005a3a  test    eax, eax
0x180005a3c  jz      short loc_180005A61
0x180005a3e  cmp     eax, r12d
0x180005a41  jz      loc_180005BC2
0x180005a47  cmp     eax, 16h
0x180005a4a  jz      loc_180005BD8
0x180005a50  cmp     eax, r14d
0x180005a53  jz      loc_180005BD8
0x180005a59  cmp     eax, esi
0x180005a5b  jnz     loc_180005BCD
0x180005a61  lea     r8, [rbp+160h+sz]; Source
0x180005a68  mov     rdx, rbx; SizeInWords
0x180005a6b  lea     rcx, [rbp+160h+Destination]; Destination
0x180005a6f  call    wcscat_s
0x180005a74  test    eax, eax
0x180005a76  jz      short loc_180005A9B
0x180005a78  cmp     eax, r12d
0x180005a7b  jz      loc_180005BC2
0x180005a81  cmp     eax, 16h
0x180005a84  jz      loc_180005BD8
0x180005a8a  cmp     eax, r14d
0x180005a8d  jz      loc_180005BD8
0x180005a93  cmp     eax, esi
0x180005a95  jnz     loc_180005BCD
0x180005a9b  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180005aa2  mov     rdx, rbx; SizeInWords
0x180005aa5  lea     rcx, [rbp+160h+Destination]; Destination
0x180005aa9  call    wcscat_s
0x180005aae  test    eax, eax
0x180005ab0  jz      short loc_180005AD5
0x180005ab2  cmp     eax, r12d
0x180005ab5  jz      loc_180005BC2
0x180005abb  cmp     eax, 16h
0x180005abe  jz      loc_180005BD8
0x180005ac4  cmp     eax, r14d
0x180005ac7  jz      loc_180005BD8
0x180005acd  cmp     eax, esi
0x180005acf  jnz     loc_180005BCD
0x180005ad5  mov     r9d, 20019h; unsigned int
0x180005adb  lea     r8, [rbp+160h+Destination]; wchar_t *
0x180005adf  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x180005ae6  lea     rcx, [rsp+260h+hKey]; this
0x180005aeb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180005af0  mov     rbx, [rsp+260h+hKey]
0x180005af5  test    eax, eax
0x180005af7  jnz     short loc_180005B61
0x180005af9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005afe  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180005b03  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005b08  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180005b0d  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180005b12  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180005b17  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180005b1c  lea     rax, [rbp+160h+cSubKeys]
0x180005b20  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180005b25  xor     r9d, r9d; lpReserved
0x180005b28  xor     r8d, r8d; lpcchClass
0x180005b2b  xor     edx, edx; lpClass
0x180005b2d  mov     rcx, rbx; hKey
0x180005b30  call    cs:__imp_RegQueryInfoKeyW
0x180005b36  mov     edi, eax
0x180005b38  test    rbx, rbx
0x180005b3b  jz      short loc_180005B49
0x180005b3d  mov     rcx, rbx; hKey
0x180005b40  call    cs:__imp_RegCloseKey
0x180005b46  mov     rbx, r15
0x180005b49  test    edi, edi
0x180005b4b  jnz     short loc_180005B61
0x180005b4d  cmp     [rbp+160h+cSubKeys], r15d
0x180005b51  jnz     short loc_180005B61
0x180005b53  lea     rdx, [rbp+160h+Destination]; wchar_t *
0x180005b57  lea     rcx, [rsp+260h+var_1E8]; this
0x180005b5c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180005b61  test    rbx, rbx
0x180005b64  jz      short loc_180005B6F
0x180005b66  mov     rcx, rbx; hKey
0x180005b69  call    cs:__imp_RegCloseKey
0x180005b6f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005b76  call    cs:__imp_RegCloseKey
0x180005b7c  mov     edi, r15d
0x180005b7f  mov     rcx, [rbp+160h+var_1C8]
0x180005b83  test    rcx, rcx
0x180005b86  jz      short loc_180005B95
0x180005b88  mov     rdx, [rcx]
0x180005b8b  mov     rax, [rdx+10h]
0x180005b8f  call    _guard_dispatch_icall
0x180005b94  nop
0x180005b95  mov     eax, edi
0x180005b97  mov     rcx, [rbp+160h+var_30]
0x180005b9e  xor     rcx, rsp; StackCookie
0x180005ba1  call    __security_check_cookie
0x180005ba6  lea     r11, [rsp+260h+var_20]
0x180005bae  mov     rbx, [r11+40h]
0x180005bb2  mov     rsi, [r11+48h]
0x180005bb6  mov     rsp, r11
0x180005bb9  pop     r15
0x180005bbb  pop     r14
0x180005bbd  pop     r12
0x180005bbf  pop     rdi
0x180005bc0  pop     rbp
0x180005bc1  retn
0x180005bc2  mov     ecx, 8007000Eh; int
0x180005bc7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005bcd  mov     ecx, 80004005h; int
0x180005bd2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005bd8  mov     ecx, 80070057h; int
0x180005bdd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
