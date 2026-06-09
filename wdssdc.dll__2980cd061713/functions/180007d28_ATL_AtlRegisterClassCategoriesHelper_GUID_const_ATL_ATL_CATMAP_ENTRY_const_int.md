# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180007d28`
- end: `0x180008243`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1307`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800085d4`
- `0x180008980`

## callees

- `0x1800015b0`
- `0x18000335c`
- `0x1800037ec`
- `0x180007d28`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180007ee2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180007f24`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180008074`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800080b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180007ee2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180007f24`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180008074`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800080b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180007e98`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180008032`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180007e98`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180008032`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007fdf`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008175`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007fdf`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008175`
- `ADVAPI32!RegCloseKey` at `0x180007ff5`
- `ADVAPI32!RegCloseKey` at `0x180008128`
- `ADVAPI32!RegCloseKey` at `0x18000818b`
- `ADVAPI32!RegCloseKey` at `0x1800081be`
- `ADVAPI32!RegCloseKey` at `0x1800081d2`
- `ADVAPI32!RegCloseKey` at `0x180007ff5`
- `ADVAPI32!RegCloseKey` at `0x180008128`
- `ADVAPI32!RegCloseKey` at `0x18000818b`
- `ADVAPI32!RegCloseKey` at `0x1800081be`
- `ADVAPI32!RegCloseKey` at `0x1800081d2`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f92`
- `ADVAPI32!RegOpenKeyExW` at `0x180008109`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f92`
- `ADVAPI32!RegOpenKeyExW` at `0x180008109`
- `ole32!StringFromGUID2` at `0x180007e7a`
- `ole32!StringFromGUID2` at `0x180007e7a`
- `ole32!CoCreateInstance` at `0x180007dcd`
- `ole32!CoCreateInstance` at `0x180007dcd`

## string_xrefs

- `0x180007e8b`: `CLSID\`
- `0x180008025`: `CLSID\`

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
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[128]; // [rsp+B0h] [rbp-50h] BYREF
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
        v12 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
        if ( v12 )
        {
          if ( v12 == 12 )
            goto LABEL_69;
          if ( v12 == 22 || v12 == 34 )
            goto LABEL_71;
          if ( v12 != 80 )
            goto LABEL_70;
        }
        v13 = _o_wcscat_s(SubKey, 128, sz);
        if ( v13 )
        {
          if ( v13 == 12 )
            goto LABEL_69;
          if ( v13 == 22 || v13 == 34 )
            goto LABEL_71;
          if ( v13 != 80 )
            goto LABEL_70;
        }
        v14 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
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
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
        {
          v16 = phkResult;
          v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v16 )
            RegCloseKey(v16);
          if ( !v17 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
            v15 = (HKEY)v27[0];
          }
        }
        v18 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
        if ( v18 )
        {
          if ( v18 == 12 )
            goto LABEL_69;
          if ( v18 == 22 || v18 == 34 )
            goto LABEL_71;
          if ( v18 != 80 )
            goto LABEL_70;
        }
        v19 = _o_wcscat_s(SubKey, 128, sz);
        if ( v19 )
        {
          if ( v19 == 12 )
            goto LABEL_69;
          if ( v19 == 22 || v19 == 34 )
            goto LABEL_71;
          if ( v19 != 80 )
            goto LABEL_70;
        }
        v20 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
        if ( !v20 )
        {
LABEL_58:
          hKey = 0;
          if ( !RegOpenKeyExW(v15, SubKey, 0, 0x20019u, &hKey) )
          {
            v21 = hKey;
            v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
            if ( v21 )
              RegCloseKey(v21);
            if ( !v22 && !cSubKeys )
            {
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
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
0x180007d28  mov     [rsp-8+arg_10], rbx
0x180007d2d  mov     [rsp-8+arg_18], rsi
0x180007d32  push    rbp
0x180007d33  push    rdi
0x180007d34  push    r12
0x180007d36  push    r14
0x180007d38  push    r15
0x180007d3a  lea     rbp, [rsp-140h]
0x180007d42  sub     rsp, 240h
0x180007d49  mov     rax, cs:__security_cookie
0x180007d50  xor     rax, rsp
0x180007d53  mov     [rbp+160h+var_30], rax
0x180007d5a  xor     r15d, r15d
0x180007d5d  xorps   xmm0, xmm0
0x180007d60  mov     [rsp+260h+var_1F8], r15
0x180007d65  mov     r14d, r8d
0x180007d68  mov     rdi, rdx
0x180007d6b  mov     rbx, rcx
0x180007d6e  movups  [rbp+160h+var_1C8], xmm0
0x180007d72  test    rdx, rdx
0x180007d75  jz      loc_1800081F4
0x180007d7b  mov     eax, cs:GUID_NULL.Data1
0x180007d81  cmp     [rcx], eax
0x180007d83  jnz     short loc_180007DAA
0x180007d85  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180007d8b  cmp     [rcx+4], eax
0x180007d8e  jnz     short loc_180007DAA
0x180007d90  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180007d96  cmp     [rcx+8], eax
0x180007d99  jnz     short loc_180007DAA
0x180007d9b  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180007da1  cmp     [rcx+0Ch], eax
0x180007da4  jz      loc_1800081F4
0x180007daa  lea     rax, [rsp+260h+var_1F8]
0x180007daf  mov     r12d, 1
0x180007db5  mov     r8d, r12d; dwClsContext
0x180007db8  mov     [rsp+260h+ppv], rax; ppv
0x180007dbd  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180007dc4  xor     edx, edx; pUnkOuter
0x180007dc6  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180007dcd  call    cs:__imp_CoCreateInstance
0x180007dd4  nop     dword ptr [rax+rax+00h]
0x180007dd9  test    eax, eax
0x180007ddb  js      loc_1800081DE
0x180007de1  jmp     short loc_180007E5D
0x180007de3  mov     rax, [rdi+8]
0x180007de7  lea     r9, [rbp+160h+var_1C8]
0x180007deb  mov     r8d, r12d
0x180007dee  mov     rdx, rbx
0x180007df1  movups  xmm0, xmmword ptr [rax]
0x180007df4  movdqu  [rbp+160h+var_1C8], xmm0
0x180007df9  test    r14d, r14d
0x180007dfc  jz      short loc_180007E3D
0x180007dfe  cmp     ecx, r12d
0x180007e01  mov     rcx, [rsp+260h+var_1F8]
0x180007e06  mov     rax, [rcx]
0x180007e09  jnz     short loc_180007E11
0x180007e0b  mov     rax, [rax+28h]
0x180007e0f  jmp     short loc_180007E15
0x180007e11  mov     rax, [rax+38h]
0x180007e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1a  mov     esi, eax
0x180007e1c  test    eax, eax
0x180007e1e  jns     short loc_180007E59
0x180007e20  mov     rcx, [rsp+260h+var_1F8]
0x180007e25  test    rcx, rcx
0x180007e28  jz      short loc_180007E36
0x180007e2a  mov     rax, [rcx]
0x180007e2d  mov     rax, [rax+10h]
0x180007e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e36  mov     eax, esi
0x180007e38  jmp     loc_1800081F6
0x180007e3d  cmp     ecx, r12d
0x180007e40  mov     rcx, [rsp+260h+var_1F8]
0x180007e45  mov     rax, [rcx]
0x180007e48  jnz     short loc_180007E50
0x180007e4a  mov     rax, [rax+30h]
0x180007e4e  jmp     short loc_180007E54
0x180007e50  mov     rax, [rax+40h]
0x180007e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e59  add     rdi, 10h
0x180007e5d  mov     ecx, [rdi]
0x180007e5f  test    ecx, ecx
0x180007e61  jnz     short loc_180007DE3
0x180007e63  test    r14d, r14d
0x180007e66  jnz     loc_1800081DE
0x180007e6c  lea     r8d, [rcx+40h]; cchMax
0x180007e70  mov     rcx, rbx; rguid
0x180007e73  lea     rdx, [rbp+160h+sz]; lpsz
0x180007e7a  call    cs:__imp_StringFromGUID2
0x180007e81  nop     dword ptr [rax+rax+00h]
0x180007e86  mov     ebx, 80h
0x180007e8b  lea     r8, aClsid; "CLSID\\"
0x180007e92  mov     edx, ebx
0x180007e94  lea     rcx, [rbp+160h+SubKey]
0x180007e98  call    cs:__imp__o_wcscpy_s
0x180007e9f  nop     dword ptr [rax+rax+00h]
0x180007ea4  lea     r14d, [rbx-74h]
0x180007ea8  lea     r12d, [rbx-30h]
0x180007eac  test    eax, eax
0x180007eae  jz      short loc_180007ED4
0x180007eb0  cmp     eax, r14d
0x180007eb3  jz      loc_180008222
0x180007eb9  cmp     eax, 16h
0x180007ebc  jz      loc_180008238
0x180007ec2  cmp     eax, 22h ; '"'
0x180007ec5  jz      loc_180008238
0x180007ecb  cmp     eax, r12d
0x180007ece  jnz     loc_18000822D
0x180007ed4  lea     r8, [rbp+160h+sz]
0x180007edb  mov     rdx, rbx
0x180007ede  lea     rcx, [rbp+160h+SubKey]
0x180007ee2  call    cs:__imp__o_wcscat_s
0x180007ee9  nop     dword ptr [rax+rax+00h]
0x180007eee  test    eax, eax
0x180007ef0  jz      short loc_180007F16
0x180007ef2  cmp     eax, r14d
0x180007ef5  jz      loc_180008222
0x180007efb  cmp     eax, 16h
0x180007efe  jz      loc_180008238
0x180007f04  cmp     eax, 22h ; '"'
0x180007f07  jz      loc_180008238
0x180007f0d  cmp     eax, r12d
0x180007f10  jnz     loc_18000822D
0x180007f16  lea     r8, aRequiredCatego; "\\Required Categories"
0x180007f1d  mov     rdx, rbx
0x180007f20  lea     rcx, [rbp+160h+SubKey]
0x180007f24  call    cs:__imp__o_wcscat_s
0x180007f2b  nop     dword ptr [rax+rax+00h]
0x180007f30  test    eax, eax
0x180007f32  jz      short loc_180007F58
0x180007f34  cmp     eax, r14d
0x180007f37  jz      loc_180008222
0x180007f3d  cmp     eax, 16h
0x180007f40  jz      loc_180008238
0x180007f46  cmp     eax, 22h ; '"'
0x180007f49  jz      loc_180008238
0x180007f4f  cmp     eax, r12d
0x180007f52  jnz     loc_18000822D
0x180007f58  mov     rdi, 0FFFFFFFF80000000h
0x180007f5f  mov     [rbp+160h+var_1D8], r15
0x180007f63  lea     rax, [rsp+260h+phkResult]
0x180007f68  mov     [rbp+160h+var_1E0], rdi
0x180007f6c  mov     rcx, rdi; hKey
0x180007f6f  mov     [rbp+160h+var_1D0], r15
0x180007f73  mov     r9d, 20019h; samDesired
0x180007f79  mov     [rsp+260h+cSubKeys], r15d
0x180007f7e  xor     r8d, r8d; ulOptions
0x180007f81  mov     [rsp+260h+phkResult], r15
0x180007f86  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180007f8a  mov     [rsp+260h+ppv], rax; phkResult
0x180007f8f  mov     rbx, r15
0x180007f92  call    cs:__imp_RegOpenKeyExW
0x180007f99  nop     dword ptr [rax+rax+00h]
0x180007f9e  test    eax, eax
0x180007fa0  jnz     short loc_180008020
0x180007fa2  mov     rbx, [rsp+260h+phkResult]
0x180007fa7  lea     rax, [rsp+260h+cSubKeys]
0x180007fac  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180007fb1  xor     r9d, r9d; lpReserved
0x180007fb4  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007fb9  xor     r8d, r8d; lpcchClass
0x180007fbc  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007fc1  xor     edx, edx; lpClass
0x180007fc3  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180007fc8  mov     rcx, rbx; hKey
0x180007fcb  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180007fd0  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180007fd5  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180007fda  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180007fdf  call    cs:__imp_RegQueryInfoKeyW
0x180007fe6  nop     dword ptr [rax+rax+00h]
0x180007feb  mov     esi, eax
0x180007fed  test    rbx, rbx
0x180007ff0  jz      short loc_180008004
0x180007ff2  mov     rcx, rbx; hKey
0x180007ff5  call    cs:__imp_RegCloseKey
0x180007ffc  nop     dword ptr [rax+rax+00h]
0x180008001  mov     rbx, r15
0x180008004  test    esi, esi
0x180008006  jnz     short loc_180008020
0x180008008  cmp     [rsp+260h+cSubKeys], r15d
0x18000800d  jnz     short loc_180008020
0x18000800f  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180008013  lea     rcx, [rbp+160h+var_1E0]; this
0x180008017  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000801c  mov     rdi, [rbp+160h+var_1E0]
0x180008020  mov     esi, 80h
0x180008025  lea     r8, aClsid; "CLSID\\"
0x18000802c  mov     edx, esi
0x18000802e  lea     rcx, [rbp+160h+SubKey]
0x180008032  call    cs:__imp__o_wcscpy_s
0x180008039  nop     dword ptr [rax+rax+00h]
0x18000803e  test    eax, eax
0x180008040  jz      short loc_180008066
0x180008042  cmp     eax, r14d
0x180008045  jz      loc_180008222
0x18000804b  cmp     eax, 16h
0x18000804e  jz      loc_180008238
0x180008054  cmp     eax, 22h ; '"'
0x180008057  jz      loc_180008238
0x18000805d  cmp     eax, r12d
0x180008060  jnz     loc_18000822D
0x180008066  lea     r8, [rbp+160h+sz]
0x18000806d  mov     rdx, rsi
0x180008070  lea     rcx, [rbp+160h+SubKey]
0x180008074  call    cs:__imp__o_wcscat_s
0x18000807b  nop     dword ptr [rax+rax+00h]
0x180008080  test    eax, eax
0x180008082  jz      short loc_1800080A8
0x180008084  cmp     eax, r14d
0x180008087  jz      loc_180008222
0x18000808d  cmp     eax, 16h
0x180008090  jz      loc_180008238
0x180008096  cmp     eax, 22h ; '"'
0x180008099  jz      loc_180008238
0x18000809f  cmp     eax, r12d
0x1800080a2  jnz     loc_18000822D
0x1800080a8  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800080af  mov     rdx, rsi
0x1800080b2  lea     rcx, [rbp+160h+SubKey]
0x1800080b6  call    cs:__imp__o_wcscat_s
0x1800080bd  nop     dword ptr [rax+rax+00h]
0x1800080c2  test    eax, eax
0x1800080c4  jz      short loc_1800080EA
0x1800080c6  cmp     eax, r14d
0x1800080c9  jz      loc_180008222
0x1800080cf  cmp     eax, 16h
0x1800080d2  jz      loc_180008238
0x1800080d8  cmp     eax, 22h ; '"'
0x1800080db  jz      loc_180008238
0x1800080e1  cmp     eax, r12d
0x1800080e4  jnz     loc_18000822D
0x1800080ea  lea     rax, [rsp+260h+hKey]
0x1800080ef  mov     [rsp+260h+hKey], r15
0x1800080f4  mov     r9d, 20019h; samDesired
0x1800080fa  mov     [rsp+260h+ppv], rax; phkResult
0x1800080ff  xor     r8d, r8d; ulOptions
0x180008102  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180008106  mov     rcx, rdi; hKey
0x180008109  call    cs:__imp_RegOpenKeyExW
0x180008110  nop     dword ptr [rax+rax+00h]
0x180008115  test    eax, eax
0x180008117  jnz     loc_1800081B6
0x18000811d  mov     eax, r15d
0x180008120  test    rbx, rbx
0x180008123  jz      short loc_180008134
0x180008125  mov     rcx, rbx; hKey
0x180008128  call    cs:__imp_RegCloseKey
0x18000812f  nop     dword ptr [rax+rax+00h]
0x180008134  mov     rbx, [rsp+260h+hKey]
0x180008139  test    eax, eax
0x18000813b  jnz     short loc_1800081B6
0x18000813d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180008142  lea     rax, [rsp+260h+cSubKeys]
0x180008147  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000814c  xor     r9d, r9d; lpReserved
0x18000814f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180008154  xor     r8d, r8d; lpcchClass
0x180008157  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000815c  xor     edx, edx; lpClass
0x18000815e  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180008163  mov     rcx, rbx; hKey
0x180008166  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000816b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180008170  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180008175  call    cs:__imp_RegQueryInfoKeyW
0x18000817c  nop     dword ptr [rax+rax+00h]
0x180008181  mov     esi, eax
0x180008183  test    rbx, rbx
0x180008186  jz      short loc_18000819A
0x180008188  mov     rcx, rbx; hKey
0x18000818b  call    cs:__imp_RegCloseKey
0x180008192  nop     dword ptr [rax+rax+00h]
0x180008197  mov     rbx, r15
0x18000819a  test    esi, esi
0x18000819c  jnz     short loc_1800081CA
0x18000819e  cmp     [rsp+260h+cSubKeys], r15d
0x1800081a3  jnz     short loc_1800081B6
0x1800081a5  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800081a9  lea     rcx, [rbp+160h+var_1E0]; this
0x1800081ad  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800081b2  mov     rdi, [rbp+160h+var_1E0]
0x1800081b6  test    rbx, rbx
0x1800081b9  jz      short loc_1800081CA
0x1800081bb  mov     rcx, rbx; hKey
0x1800081be  call    cs:__imp_RegCloseKey
0x1800081c5  nop     dword ptr [rax+rax+00h]
0x1800081ca  test    rdi, rdi
0x1800081cd  jz      short loc_1800081DE
0x1800081cf  mov     rcx, rdi; hKey
0x1800081d2  call    cs:__imp_RegCloseKey
0x1800081d9  nop     dword ptr [rax+rax+00h]
0x1800081de  mov     rcx, [rsp+260h+var_1F8]
0x1800081e3  test    rcx, rcx
0x1800081e6  jz      short loc_1800081F4
0x1800081e8  mov     rax, [rcx]
0x1800081eb  mov     rax, [rax+10h]
0x1800081ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081f4  xor     eax, eax
  ... truncated ...
```
