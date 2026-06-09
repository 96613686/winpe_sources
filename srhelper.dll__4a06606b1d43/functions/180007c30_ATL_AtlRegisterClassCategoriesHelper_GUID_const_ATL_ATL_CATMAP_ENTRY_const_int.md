# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180007c30`
- end: `0x180007fc9`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `921`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a3c0`
- `0x18000a500`

## callees

- `0x180007c30`
- `0x180008308`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180007d96`
- `msvcrt!wcscpy_s` at `0x180007e8b`
- `msvcrt!wcscpy_s` at `0x180007d96`
- `msvcrt!wcscpy_s` at `0x180007e8b`
- `msvcrt!wcscat_s` at `0x180007daa`
- `msvcrt!wcscat_s` at `0x180007dbe`
- `msvcrt!wcscat_s` at `0x180007e9f`
- `msvcrt!wcscat_s` at `0x180007eb3`
- `msvcrt!wcscat_s` at `0x180007daa`
- `msvcrt!wcscat_s` at `0x180007dbe`
- `msvcrt!wcscat_s` at `0x180007e9f`
- `msvcrt!wcscat_s` at `0x180007eb3`
- `ADVAPI32!RegOpenKeyExW` at `0x180007e01`
- `ADVAPI32!RegOpenKeyExW` at `0x180007ed5`
- `ADVAPI32!RegOpenKeyExW` at `0x180007e01`
- `ADVAPI32!RegOpenKeyExW` at `0x180007ed5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007e48`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007f35`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007e48`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007f35`
- `ADVAPI32!RegCloseKey` at `0x180007e58`
- `ADVAPI32!RegCloseKey` at `0x180007eee`
- `ADVAPI32!RegCloseKey` at `0x180007f45`
- `ADVAPI32!RegCloseKey` at `0x180007f72`
- `ADVAPI32!RegCloseKey` at `0x180007f80`
- `ADVAPI32!RegCloseKey` at `0x180007e58`
- `ADVAPI32!RegCloseKey` at `0x180007eee`
- `ADVAPI32!RegCloseKey` at `0x180007f45`
- `ADVAPI32!RegCloseKey` at `0x180007f72`
- `ADVAPI32!RegCloseKey` at `0x180007f80`
- `ole32!StringFromGUID2` at `0x180007d7c`
- `ole32!StringFromGUID2` at `0x180007d7c`
- `ole32!CoCreateInstance` at `0x180007cd5`
- `ole32!CoCreateInstance` at `0x180007cd5`

## string_xrefs

- `0x180007d88`: `CLSID\`
- `0x180007e7d`: `CLSID\`

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
  HKEY v12; // rdi
  HKEY v13; // rbx
  LSTATUS v14; // esi
  HKEY v15; // rbx
  LSTATUS v16; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v21[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  ppv = 0;
  v4 = a2;
  v22 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_36:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( !a3 )
      {
        StringFromGUID2(rguid, sz, 64);
        wcscpy_s(Destination, 0x80u, L"CLSID\\");
        wcscat_s(Destination, 0x80u, sz);
        wcscat_s(Destination, 0x80u, L"\\Required Categories");
        v12 = HKEY_CLASSES_ROOT;
        v21[1] = 0;
        v21[0] = 0xFFFFFFFF80000000uLL;
        v21[2] = 0;
        cSubKeys = 0;
        phkResult = 0;
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
        {
          v13 = phkResult;
          v14 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v13 )
            RegCloseKey(v13);
          if ( !v14 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v21, Destination);
            v12 = (HKEY)v21[0];
          }
        }
        wcscpy_s(Destination, 0x80u, L"CLSID\\");
        wcscat_s(Destination, 0x80u, sz);
        wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
        hKey = 0;
        if ( !RegOpenKeyExW(v12, Destination, 0, 0x20019u, &hKey) )
        {
          v15 = hKey;
          v16 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v15 )
            RegCloseKey(v15);
          if ( !v16 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v21, Destination);
            v12 = (HKEY)v21[0];
          }
        }
        if ( v12 )
          RegCloseKey(v12);
      }
      goto LABEL_36;
    }
    v22 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v22);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v22);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v22)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v22);
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
0x180007c30  mov     [rsp-8+arg_10], rbx
0x180007c35  mov     [rsp-8+arg_18], rsi
0x180007c3a  push    rbp
0x180007c3b  push    rdi
0x180007c3c  push    r12
0x180007c3e  push    r14
0x180007c40  push    r15
0x180007c42  lea     rbp, [rsp-140h]
0x180007c4a  sub     rsp, 240h
0x180007c51  mov     rax, cs:__security_cookie
0x180007c58  xor     rax, rsp
0x180007c5b  mov     [rbp+160h+var_30], rax
0x180007c62  xor     r15d, r15d
0x180007c65  xorps   xmm0, xmm0
0x180007c68  mov     [rsp+260h+var_1F8], r15
0x180007c6d  mov     r14d, r8d
0x180007c70  mov     rdi, rdx
0x180007c73  mov     rbx, rcx
0x180007c76  movups  [rbp+160h+var_1C8], xmm0
0x180007c7a  test    rdx, rdx
0x180007c7d  jz      loc_180007F9C
0x180007c83  mov     eax, cs:GUID_NULL.Data1
0x180007c89  cmp     [rcx], eax
0x180007c8b  jnz     short loc_180007CB2
0x180007c8d  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180007c93  cmp     [rcx+4], eax
0x180007c96  jnz     short loc_180007CB2
0x180007c98  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180007c9e  cmp     [rcx+8], eax
0x180007ca1  jnz     short loc_180007CB2
0x180007ca3  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180007ca9  cmp     [rcx+0Ch], eax
0x180007cac  jz      loc_180007F9C
0x180007cb2  lea     rax, [rsp+260h+var_1F8]
0x180007cb7  mov     r12d, 1
0x180007cbd  mov     r8d, r12d; dwClsContext
0x180007cc0  mov     [rsp+260h+ppv], rax; ppv
0x180007cc5  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180007ccc  xor     edx, edx; pUnkOuter
0x180007cce  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180007cd5  call    cs:__imp_CoCreateInstance
0x180007cdb  test    eax, eax
0x180007cdd  js      loc_180007F86
0x180007ce3  jmp     short loc_180007D5F
0x180007ce5  mov     rax, [rdi+8]
0x180007ce9  lea     r9, [rbp+160h+var_1C8]
0x180007ced  mov     r8d, r12d
0x180007cf0  mov     rdx, rbx
0x180007cf3  movups  xmm0, xmmword ptr [rax]
0x180007cf6  movdqu  [rbp+160h+var_1C8], xmm0
0x180007cfb  test    r14d, r14d
0x180007cfe  jz      short loc_180007D3F
0x180007d00  cmp     ecx, r12d
0x180007d03  mov     rcx, [rsp+260h+var_1F8]
0x180007d08  mov     rax, [rcx]
0x180007d0b  jnz     short loc_180007D13
0x180007d0d  mov     rax, [rax+28h]
0x180007d11  jmp     short loc_180007D17
0x180007d13  mov     rax, [rax+38h]
0x180007d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1c  mov     esi, eax
0x180007d1e  test    eax, eax
0x180007d20  jns     short loc_180007D5B
0x180007d22  mov     rcx, [rsp+260h+var_1F8]
0x180007d27  test    rcx, rcx
0x180007d2a  jz      short loc_180007D38
0x180007d2c  mov     rax, [rcx]
0x180007d2f  mov     rax, [rax+10h]
0x180007d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d38  mov     eax, esi
0x180007d3a  jmp     loc_180007F9E
0x180007d3f  cmp     ecx, r12d
0x180007d42  mov     rcx, [rsp+260h+var_1F8]
0x180007d47  mov     rax, [rcx]
0x180007d4a  jnz     short loc_180007D52
0x180007d4c  mov     rax, [rax+30h]
0x180007d50  jmp     short loc_180007D56
0x180007d52  mov     rax, [rax+40h]
0x180007d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5b  add     rdi, 10h
0x180007d5f  mov     ecx, [rdi]
0x180007d61  test    ecx, ecx
0x180007d63  jnz     short loc_180007CE5
0x180007d65  test    r14d, r14d
0x180007d68  jnz     loc_180007F86
0x180007d6e  lea     r8d, [rcx+40h]; cchMax
0x180007d72  mov     rcx, rbx; rguid
0x180007d75  lea     rdx, [rbp+160h+sz]; lpsz
0x180007d7c  call    cs:__imp_StringFromGUID2
0x180007d82  mov     r14d, 80h
0x180007d88  lea     r8, aClsid; "CLSID\\"
0x180007d8f  mov     edx, r14d; SizeInWords
0x180007d92  lea     rcx, [rbp+160h+Destination]; Destination
0x180007d96  call    cs:__imp_wcscpy_s
0x180007d9c  lea     r8, [rbp+160h+sz]; Source
0x180007da3  mov     edx, r14d; SizeInWords
0x180007da6  lea     rcx, [rbp+160h+Destination]; Destination
0x180007daa  call    cs:__imp_wcscat_s
0x180007db0  lea     r8, aRequiredCatego; "\\Required Categories"
0x180007db7  mov     edx, r14d; SizeInWords
0x180007dba  lea     rcx, [rbp+160h+Destination]; Destination
0x180007dbe  call    cs:__imp_wcscat_s
0x180007dc4  mov     rdi, 0FFFFFFFF80000000h
0x180007dcb  mov     [rbp+160h+var_1D8], r15
0x180007dcf  lea     rax, [rsp+260h+phkResult]
0x180007dd4  mov     [rbp+160h+var_1E0], rdi
0x180007dd8  mov     r12d, 20019h
0x180007dde  mov     [rsp+260h+ppv], rax; phkResult
0x180007de3  mov     r9d, r12d; samDesired
0x180007de6  mov     [rbp+160h+var_1D0], r15
0x180007dea  mov     rcx, rdi; hKey
0x180007ded  mov     [rsp+260h+cSubKeys], r15d
0x180007df2  xor     r8d, r8d; ulOptions
0x180007df5  mov     [rsp+260h+phkResult], r15
0x180007dfa  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180007dfe  mov     rbx, r15
0x180007e01  call    cs:__imp_RegOpenKeyExW
0x180007e07  test    eax, eax
0x180007e09  jnz     short loc_180007E7D
0x180007e0b  mov     rbx, [rsp+260h+phkResult]
0x180007e10  lea     rax, [rsp+260h+cSubKeys]
0x180007e15  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180007e1a  xor     r9d, r9d; lpReserved
0x180007e1d  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007e22  xor     r8d, r8d; lpcchClass
0x180007e25  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007e2a  xor     edx, edx; lpClass
0x180007e2c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180007e31  mov     rcx, rbx; hKey
0x180007e34  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180007e39  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180007e3e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180007e43  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180007e48  call    cs:__imp_RegQueryInfoKeyW
0x180007e4e  mov     esi, eax
0x180007e50  test    rbx, rbx
0x180007e53  jz      short loc_180007E61
0x180007e55  mov     rcx, rbx; hKey
0x180007e58  call    cs:__imp_RegCloseKey
0x180007e5e  mov     rbx, r15
0x180007e61  test    esi, esi
0x180007e63  jnz     short loc_180007E7D
0x180007e65  cmp     [rsp+260h+cSubKeys], r15d
0x180007e6a  jnz     short loc_180007E7D
0x180007e6c  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180007e70  lea     rcx, [rbp+160h+var_1E0]; this
0x180007e74  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007e79  mov     rdi, [rbp+160h+var_1E0]
0x180007e7d  lea     r8, aClsid; "CLSID\\"
0x180007e84  mov     rdx, r14; SizeInWords
0x180007e87  lea     rcx, [rbp+160h+Destination]; Destination
0x180007e8b  call    cs:__imp_wcscpy_s
0x180007e91  lea     r8, [rbp+160h+sz]; Source
0x180007e98  mov     rdx, r14; SizeInWords
0x180007e9b  lea     rcx, [rbp+160h+Destination]; Destination
0x180007e9f  call    cs:__imp_wcscat_s
0x180007ea5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180007eac  mov     rdx, r14; SizeInWords
0x180007eaf  lea     rcx, [rbp+160h+Destination]; Destination
0x180007eb3  call    cs:__imp_wcscat_s
0x180007eb9  lea     rax, [rsp+260h+hKey]
0x180007ebe  mov     [rsp+260h+hKey], r15
0x180007ec3  mov     r9d, r12d; samDesired
0x180007ec6  mov     [rsp+260h+ppv], rax; phkResult
0x180007ecb  xor     r8d, r8d; ulOptions
0x180007ece  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180007ed2  mov     rcx, rdi; hKey
0x180007ed5  call    cs:__imp_RegOpenKeyExW
0x180007edb  test    eax, eax
0x180007edd  jnz     loc_180007F6A
0x180007ee3  mov     eax, r15d
0x180007ee6  test    rbx, rbx
0x180007ee9  jz      short loc_180007EF4
0x180007eeb  mov     rcx, rbx; hKey
0x180007eee  call    cs:__imp_RegCloseKey
0x180007ef4  mov     rbx, [rsp+260h+hKey]
0x180007ef9  test    eax, eax
0x180007efb  jnz     short loc_180007F6A
0x180007efd  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180007f02  lea     rax, [rsp+260h+cSubKeys]
0x180007f07  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007f0c  xor     r9d, r9d; lpReserved
0x180007f0f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007f14  xor     r8d, r8d; lpcchClass
0x180007f17  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180007f1c  xor     edx, edx; lpClass
0x180007f1e  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180007f23  mov     rcx, rbx; hKey
0x180007f26  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180007f2b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180007f30  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180007f35  call    cs:__imp_RegQueryInfoKeyW
0x180007f3b  mov     esi, eax
0x180007f3d  test    rbx, rbx
0x180007f40  jz      short loc_180007F4E
0x180007f42  mov     rcx, rbx; hKey
0x180007f45  call    cs:__imp_RegCloseKey
0x180007f4b  mov     rbx, r15
0x180007f4e  test    esi, esi
0x180007f50  jnz     short loc_180007F78
0x180007f52  cmp     [rsp+260h+cSubKeys], r15d
0x180007f57  jnz     short loc_180007F6A
0x180007f59  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180007f5d  lea     rcx, [rbp+160h+var_1E0]; this
0x180007f61  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007f66  mov     rdi, [rbp+160h+var_1E0]
0x180007f6a  test    rbx, rbx
0x180007f6d  jz      short loc_180007F78
0x180007f6f  mov     rcx, rbx; hKey
0x180007f72  call    cs:__imp_RegCloseKey
0x180007f78  test    rdi, rdi
0x180007f7b  jz      short loc_180007F86
0x180007f7d  mov     rcx, rdi; hKey
0x180007f80  call    cs:__imp_RegCloseKey
0x180007f86  mov     rcx, [rsp+260h+var_1F8]
0x180007f8b  test    rcx, rcx
0x180007f8e  jz      short loc_180007F9C
0x180007f90  mov     rax, [rcx]
0x180007f93  mov     rax, [rax+10h]
0x180007f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9c  xor     eax, eax
0x180007f9e  mov     rcx, [rbp+160h+var_30]
0x180007fa5  xor     rcx, rsp; StackCookie
0x180007fa8  call    __security_check_cookie
0x180007fad  lea     r11, [rsp+260h+var_20]
0x180007fb5  mov     rbx, [r11+40h]
0x180007fb9  mov     rsi, [r11+48h]
0x180007fbd  mov     rsp, r11
0x180007fc0  pop     r15
0x180007fc2  pop     r14
0x180007fc4  pop     r12
0x180007fc6  pop     rdi
0x180007fc7  pop     rbp
0x180007fc8  retn
```
