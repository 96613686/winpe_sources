# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180010cb8`
- end: `0x1800111d3`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1307`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800114b4`
- `0x1800117f0`

## callees

- `0x1800041f8`
- `0x180004724`
- `0x180010cb8`
- `0x180012db0`
- `0x180014010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010e28`
- `msvcrt!wcscpy_s` at `0x180010fc2`
- `msvcrt!wcscpy_s` at `0x180010e28`
- `msvcrt!wcscpy_s` at `0x180010fc2`
- `msvcrt!wcscat_s` at `0x180010e72`
- `msvcrt!wcscat_s` at `0x180010eb4`
- `msvcrt!wcscat_s` at `0x180011004`
- `msvcrt!wcscat_s` at `0x180011046`
- `msvcrt!wcscat_s` at `0x180010e72`
- `msvcrt!wcscat_s` at `0x180010eb4`
- `msvcrt!wcscat_s` at `0x180011004`
- `msvcrt!wcscat_s` at `0x180011046`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180010f6f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011105`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180010f6f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011105`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f22`
- `ADVAPI32!RegOpenKeyExW` at `0x180011099`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f22`
- `ADVAPI32!RegOpenKeyExW` at `0x180011099`
- `ADVAPI32!RegCloseKey` at `0x180010f85`
- `ADVAPI32!RegCloseKey` at `0x1800110b8`
- `ADVAPI32!RegCloseKey` at `0x18001111b`
- `ADVAPI32!RegCloseKey` at `0x18001114e`
- `ADVAPI32!RegCloseKey` at `0x180011162`
- `ADVAPI32!RegCloseKey` at `0x180010f85`
- `ADVAPI32!RegCloseKey` at `0x1800110b8`
- `ADVAPI32!RegCloseKey` at `0x18001111b`
- `ADVAPI32!RegCloseKey` at `0x18001114e`
- `ADVAPI32!RegCloseKey` at `0x180011162`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010e0a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010e0a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d5d`

## string_xrefs

- `0x180010e1b`: `CLSID\`
- `0x180010fb5`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  errno_t v12; // eax
  errno_t v13; // eax
  errno_t v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  ppv = 0;
  v4 = a2;
  v28 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
    goto LABEL_66;
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( !a3 )
      {
        StringFromGUID2(rguid, sz, 64);
        v12 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
        if ( v12 )
        {
          if ( v12 == 12 )
            goto LABEL_69;
          if ( v12 == 22 || v12 == 34 )
            goto LABEL_71;
          if ( v12 != 80 )
            goto LABEL_70;
        }
        v13 = wcscat_s(Destination, 0x80u, sz);
        if ( v13 )
        {
          if ( v13 == 12 )
            goto LABEL_69;
          if ( v13 == 22 || v13 == 34 )
            goto LABEL_71;
          if ( v13 != 80 )
            goto LABEL_70;
        }
        v14 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
        if ( v14 )
        {
          if ( v14 == 12 )
            goto LABEL_69;
          if ( v14 == 22 || v14 == 34 )
            goto LABEL_71;
          if ( v14 != 80 )
            goto LABEL_70;
        }
        v15 = HKEY_CLASSES_ROOT;
        v27[1] = 0;
        v27[0] = 0xFFFFFFFF80000000uLL;
        v27[2] = 0;
        cSubKeys = 0;
        phkResult = 0;
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
        {
          v16 = phkResult;
          v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v16 )
            RegCloseKey(v16);
          if ( !v17 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
            v15 = (HKEY)v27[0];
          }
        }
        v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
        if ( v18 )
        {
          if ( v18 == 12 )
            goto LABEL_69;
          if ( v18 == 22 || v18 == 34 )
            goto LABEL_71;
          if ( v18 != 80 )
            goto LABEL_70;
        }
        v19 = wcscat_s(Destination, 0x80u, sz);
        if ( v19 )
        {
          if ( v19 == 12 )
            goto LABEL_69;
          if ( v19 == 22 || v19 == 34 )
            goto LABEL_71;
          if ( v19 != 80 )
            goto LABEL_70;
        }
        v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
        if ( !v20 )
        {
LABEL_58:
          hKey = 0;
          if ( !RegOpenKeyExW(v15, Destination, 0, 0x20019u, &hKey) )
          {
            v21 = hKey;
            v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
            if ( v21 )
              RegCloseKey(v21);
            if ( !v22 && !cSubKeys )
            {
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
              v15 = (HKEY)v27[0];
            }
          }
          if ( v15 )
            RegCloseKey(v15);
          goto LABEL_66;
        }
        if ( v20 != 12 )
        {
          if ( v20 != 22 && v20 != 34 )
          {
            if ( v20 == 80 )
              goto LABEL_58;
LABEL_70:
            ATL::AtlThrowImpl(-2147467259);
          }
LABEL_71:
          ATL::AtlThrowImpl(-2147024809);
        }
LABEL_69:
        ATL::AtlThrowImpl(-2147024882);
      }
LABEL_66:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 0;
    }
    v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v28);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v28);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180010cb8  mov     [rsp-8+arg_10], rbx
0x180010cbd  mov     [rsp-8+arg_18], rsi
0x180010cc2  push    rbp
0x180010cc3  push    rdi
0x180010cc4  push    r12
0x180010cc6  push    r14
0x180010cc8  push    r15
0x180010cca  lea     rbp, [rsp-140h]
0x180010cd2  sub     rsp, 240h
0x180010cd9  mov     rax, cs:__security_cookie
0x180010ce0  xor     rax, rsp
0x180010ce3  mov     [rbp+160h+var_30], rax
0x180010cea  xor     r15d, r15d
0x180010ced  xorps   xmm0, xmm0
0x180010cf0  mov     [rsp+260h+var_1F8], r15
0x180010cf5  mov     r14d, r8d
0x180010cf8  mov     rdi, rdx
0x180010cfb  mov     rbx, rcx
0x180010cfe  movups  [rbp+160h+var_1C8], xmm0
0x180010d02  test    rdx, rdx
0x180010d05  jz      loc_180011184
0x180010d0b  mov     eax, cs:GUID_NULL.Data1
0x180010d11  cmp     [rcx], eax
0x180010d13  jnz     short loc_180010D3A
0x180010d15  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180010d1b  cmp     [rcx+4], eax
0x180010d1e  jnz     short loc_180010D3A
0x180010d20  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180010d26  cmp     [rcx+8], eax
0x180010d29  jnz     short loc_180010D3A
0x180010d2b  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180010d31  cmp     [rcx+0Ch], eax
0x180010d34  jz      loc_180011184
0x180010d3a  lea     rax, [rsp+260h+var_1F8]
0x180010d3f  mov     r12d, 1
0x180010d45  mov     r8d, r12d; dwClsContext
0x180010d48  mov     [rsp+260h+ppv], rax; ppv
0x180010d4d  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180010d54  xor     edx, edx; pUnkOuter
0x180010d56  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180010d5d  call    cs:__imp_CoCreateInstance
0x180010d64  nop     dword ptr [rax+rax+00h]
0x180010d69  test    eax, eax
0x180010d6b  js      loc_18001116E
0x180010d71  jmp     short loc_180010DED
0x180010d73  mov     rax, [rdi+8]
0x180010d77  lea     r9, [rbp+160h+var_1C8]
0x180010d7b  mov     r8d, r12d
0x180010d7e  mov     rdx, rbx
0x180010d81  movups  xmm0, xmmword ptr [rax]
0x180010d84  movdqu  [rbp+160h+var_1C8], xmm0
0x180010d89  test    r14d, r14d
0x180010d8c  jz      short loc_180010DCD
0x180010d8e  cmp     ecx, r12d
0x180010d91  mov     rcx, [rsp+260h+var_1F8]
0x180010d96  mov     rax, [rcx]
0x180010d99  jnz     short loc_180010DA1
0x180010d9b  mov     rax, [rax+28h]
0x180010d9f  jmp     short loc_180010DA5
0x180010da1  mov     rax, [rax+38h]
0x180010da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010daa  mov     esi, eax
0x180010dac  test    eax, eax
0x180010dae  jns     short loc_180010DE9
0x180010db0  mov     rcx, [rsp+260h+var_1F8]
0x180010db5  test    rcx, rcx
0x180010db8  jz      short loc_180010DC6
0x180010dba  mov     rax, [rcx]
0x180010dbd  mov     rax, [rax+10h]
0x180010dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dc6  mov     eax, esi
0x180010dc8  jmp     loc_180011186
0x180010dcd  cmp     ecx, r12d
0x180010dd0  mov     rcx, [rsp+260h+var_1F8]
0x180010dd5  mov     rax, [rcx]
0x180010dd8  jnz     short loc_180010DE0
0x180010dda  mov     rax, [rax+30h]
0x180010dde  jmp     short loc_180010DE4
0x180010de0  mov     rax, [rax+40h]
0x180010de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010de9  add     rdi, 10h
0x180010ded  mov     ecx, [rdi]
0x180010def  test    ecx, ecx
0x180010df1  jnz     short loc_180010D73
0x180010df3  test    r14d, r14d
0x180010df6  jnz     loc_18001116E
0x180010dfc  lea     r8d, [rcx+40h]; cchMax
0x180010e00  mov     rcx, rbx; rguid
0x180010e03  lea     rdx, [rbp+160h+sz]; lpsz
0x180010e0a  call    cs:__imp_StringFromGUID2
0x180010e11  nop     dword ptr [rax+rax+00h]
0x180010e16  mov     ebx, 80h
0x180010e1b  lea     r8, aClsid; "CLSID\\"
0x180010e22  mov     edx, ebx; SizeInWords
0x180010e24  lea     rcx, [rbp+160h+Destination]; Destination
0x180010e28  call    cs:__imp_wcscpy_s
0x180010e2f  nop     dword ptr [rax+rax+00h]
0x180010e34  lea     r14d, [rbx-74h]
0x180010e38  lea     r12d, [rbx-30h]
0x180010e3c  test    eax, eax
0x180010e3e  jz      short loc_180010E64
0x180010e40  cmp     eax, r14d
0x180010e43  jz      loc_1800111B2
0x180010e49  cmp     eax, 16h
0x180010e4c  jz      loc_1800111C8
0x180010e52  cmp     eax, 22h ; '"'
0x180010e55  jz      loc_1800111C8
0x180010e5b  cmp     eax, r12d
0x180010e5e  jnz     loc_1800111BD
0x180010e64  lea     r8, [rbp+160h+sz]; Source
0x180010e6b  mov     rdx, rbx; SizeInWords
0x180010e6e  lea     rcx, [rbp+160h+Destination]; Destination
0x180010e72  call    cs:__imp_wcscat_s
0x180010e79  nop     dword ptr [rax+rax+00h]
0x180010e7e  test    eax, eax
0x180010e80  jz      short loc_180010EA6
0x180010e82  cmp     eax, r14d
0x180010e85  jz      loc_1800111B2
0x180010e8b  cmp     eax, 16h
0x180010e8e  jz      loc_1800111C8
0x180010e94  cmp     eax, 22h ; '"'
0x180010e97  jz      loc_1800111C8
0x180010e9d  cmp     eax, r12d
0x180010ea0  jnz     loc_1800111BD
0x180010ea6  lea     r8, aRequiredCatego; "\\Required Categories"
0x180010ead  mov     rdx, rbx; SizeInWords
0x180010eb0  lea     rcx, [rbp+160h+Destination]; Destination
0x180010eb4  call    cs:__imp_wcscat_s
0x180010ebb  nop     dword ptr [rax+rax+00h]
0x180010ec0  test    eax, eax
0x180010ec2  jz      short loc_180010EE8
0x180010ec4  cmp     eax, r14d
0x180010ec7  jz      loc_1800111B2
0x180010ecd  cmp     eax, 16h
0x180010ed0  jz      loc_1800111C8
0x180010ed6  cmp     eax, 22h ; '"'
0x180010ed9  jz      loc_1800111C8
0x180010edf  cmp     eax, r12d
0x180010ee2  jnz     loc_1800111BD
0x180010ee8  mov     rdi, 0FFFFFFFF80000000h
0x180010eef  mov     [rbp+160h+var_1D8], r15
0x180010ef3  lea     rax, [rsp+260h+phkResult]
0x180010ef8  mov     [rbp+160h+var_1E0], rdi
0x180010efc  mov     rcx, rdi; hKey
0x180010eff  mov     [rbp+160h+var_1D0], r15
0x180010f03  mov     r9d, 20019h; samDesired
0x180010f09  mov     [rsp+260h+cSubKeys], r15d
0x180010f0e  xor     r8d, r8d; ulOptions
0x180010f11  mov     [rsp+260h+phkResult], r15
0x180010f16  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180010f1a  mov     [rsp+260h+ppv], rax; phkResult
0x180010f1f  mov     rbx, r15
0x180010f22  call    cs:__imp_RegOpenKeyExW
0x180010f29  nop     dword ptr [rax+rax+00h]
0x180010f2e  test    eax, eax
0x180010f30  jnz     short loc_180010FB0
0x180010f32  mov     rbx, [rsp+260h+phkResult]
0x180010f37  lea     rax, [rsp+260h+cSubKeys]
0x180010f3c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180010f41  xor     r9d, r9d; lpReserved
0x180010f44  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180010f49  xor     r8d, r8d; lpcchClass
0x180010f4c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180010f51  xor     edx, edx; lpClass
0x180010f53  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180010f58  mov     rcx, rbx; hKey
0x180010f5b  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180010f60  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180010f65  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180010f6a  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180010f6f  call    cs:__imp_RegQueryInfoKeyW
0x180010f76  nop     dword ptr [rax+rax+00h]
0x180010f7b  mov     esi, eax
0x180010f7d  test    rbx, rbx
0x180010f80  jz      short loc_180010F94
0x180010f82  mov     rcx, rbx; hKey
0x180010f85  call    cs:__imp_RegCloseKey
0x180010f8c  nop     dword ptr [rax+rax+00h]
0x180010f91  mov     rbx, r15
0x180010f94  test    esi, esi
0x180010f96  jnz     short loc_180010FB0
0x180010f98  cmp     [rsp+260h+cSubKeys], r15d
0x180010f9d  jnz     short loc_180010FB0
0x180010f9f  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180010fa3  lea     rcx, [rbp+160h+var_1E0]; this
0x180010fa7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180010fac  mov     rdi, [rbp+160h+var_1E0]
0x180010fb0  mov     esi, 80h
0x180010fb5  lea     r8, aClsid; "CLSID\\"
0x180010fbc  mov     edx, esi; SizeInWords
0x180010fbe  lea     rcx, [rbp+160h+Destination]; Destination
0x180010fc2  call    cs:__imp_wcscpy_s
0x180010fc9  nop     dword ptr [rax+rax+00h]
0x180010fce  test    eax, eax
0x180010fd0  jz      short loc_180010FF6
0x180010fd2  cmp     eax, r14d
0x180010fd5  jz      loc_1800111B2
0x180010fdb  cmp     eax, 16h
0x180010fde  jz      loc_1800111C8
0x180010fe4  cmp     eax, 22h ; '"'
0x180010fe7  jz      loc_1800111C8
0x180010fed  cmp     eax, r12d
0x180010ff0  jnz     loc_1800111BD
0x180010ff6  lea     r8, [rbp+160h+sz]; Source
0x180010ffd  mov     rdx, rsi; SizeInWords
0x180011000  lea     rcx, [rbp+160h+Destination]; Destination
0x180011004  call    cs:__imp_wcscat_s
0x18001100b  nop     dword ptr [rax+rax+00h]
0x180011010  test    eax, eax
0x180011012  jz      short loc_180011038
0x180011014  cmp     eax, r14d
0x180011017  jz      loc_1800111B2
0x18001101d  cmp     eax, 16h
0x180011020  jz      loc_1800111C8
0x180011026  cmp     eax, 22h ; '"'
0x180011029  jz      loc_1800111C8
0x18001102f  cmp     eax, r12d
0x180011032  jnz     loc_1800111BD
0x180011038  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18001103f  mov     rdx, rsi; SizeInWords
0x180011042  lea     rcx, [rbp+160h+Destination]; Destination
0x180011046  call    cs:__imp_wcscat_s
0x18001104d  nop     dword ptr [rax+rax+00h]
0x180011052  test    eax, eax
0x180011054  jz      short loc_18001107A
0x180011056  cmp     eax, r14d
0x180011059  jz      loc_1800111B2
0x18001105f  cmp     eax, 16h
0x180011062  jz      loc_1800111C8
0x180011068  cmp     eax, 22h ; '"'
0x18001106b  jz      loc_1800111C8
0x180011071  cmp     eax, r12d
0x180011074  jnz     loc_1800111BD
0x18001107a  lea     rax, [rsp+260h+hKey]
0x18001107f  mov     [rsp+260h+hKey], r15
0x180011084  mov     r9d, 20019h; samDesired
0x18001108a  mov     [rsp+260h+ppv], rax; phkResult
0x18001108f  xor     r8d, r8d; ulOptions
0x180011092  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180011096  mov     rcx, rdi; hKey
0x180011099  call    cs:__imp_RegOpenKeyExW
0x1800110a0  nop     dword ptr [rax+rax+00h]
0x1800110a5  test    eax, eax
0x1800110a7  jnz     loc_180011146
0x1800110ad  mov     eax, r15d
0x1800110b0  test    rbx, rbx
0x1800110b3  jz      short loc_1800110C4
0x1800110b5  mov     rcx, rbx; hKey
0x1800110b8  call    cs:__imp_RegCloseKey
0x1800110bf  nop     dword ptr [rax+rax+00h]
0x1800110c4  mov     rbx, [rsp+260h+hKey]
0x1800110c9  test    eax, eax
0x1800110cb  jnz     short loc_180011146
0x1800110cd  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800110d2  lea     rax, [rsp+260h+cSubKeys]
0x1800110d7  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800110dc  xor     r9d, r9d; lpReserved
0x1800110df  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800110e4  xor     r8d, r8d; lpcchClass
0x1800110e7  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800110ec  xor     edx, edx; lpClass
0x1800110ee  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800110f3  mov     rcx, rbx; hKey
0x1800110f6  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800110fb  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180011100  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180011105  call    cs:__imp_RegQueryInfoKeyW
0x18001110c  nop     dword ptr [rax+rax+00h]
0x180011111  mov     esi, eax
0x180011113  test    rbx, rbx
0x180011116  jz      short loc_18001112A
0x180011118  mov     rcx, rbx; hKey
0x18001111b  call    cs:__imp_RegCloseKey
0x180011122  nop     dword ptr [rax+rax+00h]
0x180011127  mov     rbx, r15
0x18001112a  test    esi, esi
0x18001112c  jnz     short loc_18001115A
0x18001112e  cmp     [rsp+260h+cSubKeys], r15d
0x180011133  jnz     short loc_180011146
0x180011135  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180011139  lea     rcx, [rbp+160h+var_1E0]; this
0x18001113d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180011142  mov     rdi, [rbp+160h+var_1E0]
0x180011146  test    rbx, rbx
0x180011149  jz      short loc_18001115A
0x18001114b  mov     rcx, rbx; hKey
0x18001114e  call    cs:__imp_RegCloseKey
0x180011155  nop     dword ptr [rax+rax+00h]
0x18001115a  test    rdi, rdi
0x18001115d  jz      short loc_18001116E
0x18001115f  mov     rcx, rdi; hKey
0x180011162  call    cs:__imp_RegCloseKey
0x180011169  nop     dword ptr [rax+rax+00h]
0x18001116e  mov     rcx, [rsp+260h+var_1F8]
0x180011173  test    rcx, rcx
0x180011176  jz      short loc_180011184
0x180011178  mov     rax, [rcx]
0x18001117b  mov     rax, [rax+10h]
0x18001117f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011184  xor     eax, eax
  ... truncated ...
```
