# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x140002bfc`
- end: `0x1400030b0`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000485c`
- `0x1400053a0`
- `0x140005c80`

## callees

- `0x140001490`
- `0x140002bfc`
- `0x140003298`
- `0x140003698`
- `0x140007010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002da4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002de0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002f12`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002f4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002da4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002de0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002f12`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140002f4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002d60`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002ed6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002d60`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140002ed6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140002d48`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140002d48`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140002ca1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140002ca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002f9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002f9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140002e8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140002ffb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140002e8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140002ffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002e9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000300b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003046`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002e9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000300b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003046`

## string_xrefs

- `0x140002d53`: `CLSID\`
- `0x140002ec9`: `CLSID\`

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
0x140002bfc  mov     [rsp-8+arg_10], rbx
0x140002c01  mov     [rsp-8+arg_18], rsi
0x140002c06  push    rbp
0x140002c07  push    rdi
0x140002c08  push    r12
0x140002c0a  push    r14
0x140002c0c  push    r15
0x140002c0e  lea     rbp, [rsp-140h]
0x140002c16  sub     rsp, 240h
0x140002c1d  mov     rax, cs:__security_cookie
0x140002c24  xor     rax, rsp
0x140002c27  mov     [rbp+160h+var_30], rax
0x140002c2e  xor     r15d, r15d
0x140002c31  xorps   xmm0, xmm0
0x140002c34  mov     [rsp+260h+var_1F8], r15
0x140002c39  mov     r14d, r8d
0x140002c3c  mov     rdi, rdx
0x140002c3f  mov     rbx, rcx
0x140002c42  movups  [rbp+160h+var_1C8], xmm0
0x140002c46  test    rdx, rdx
0x140002c49  jz      loc_140003062
0x140002c4f  mov     eax, cs:GUID_NULL.Data1
0x140002c55  cmp     [rcx], eax
0x140002c57  jnz     short loc_140002C7E
0x140002c59  mov     eax, dword ptr cs:GUID_NULL.Data2
0x140002c5f  cmp     [rcx+4], eax
0x140002c62  jnz     short loc_140002C7E
0x140002c64  mov     eax, dword ptr cs:GUID_NULL.Data4
0x140002c6a  cmp     [rcx+8], eax
0x140002c6d  jnz     short loc_140002C7E
0x140002c6f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x140002c75  cmp     [rcx+0Ch], eax
0x140002c78  jz      loc_140003062
0x140002c7e  lea     rax, [rsp+260h+var_1F8]
0x140002c83  mov     r12d, 1
0x140002c89  mov     r8d, r12d; dwClsContext
0x140002c8c  mov     [rsp+260h+ppv], rax; ppv
0x140002c91  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x140002c98  xor     edx, edx; pUnkOuter
0x140002c9a  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x140002ca1  call    cs:__imp_CoCreateInstance
0x140002ca7  test    eax, eax
0x140002ca9  js      loc_14000304C
0x140002caf  jmp     short loc_140002D2B
0x140002cb1  mov     rax, [rdi+8]
0x140002cb5  lea     r9, [rbp+160h+var_1C8]
0x140002cb9  mov     r8d, r12d
0x140002cbc  mov     rdx, rbx
0x140002cbf  movups  xmm0, xmmword ptr [rax]
0x140002cc2  movdqu  [rbp+160h+var_1C8], xmm0
0x140002cc7  test    r14d, r14d
0x140002cca  jz      short loc_140002D0B
0x140002ccc  cmp     ecx, r12d
0x140002ccf  mov     rcx, [rsp+260h+var_1F8]
0x140002cd4  mov     rax, [rcx]
0x140002cd7  jnz     short loc_140002CDF
0x140002cd9  mov     rax, [rax+28h]
0x140002cdd  jmp     short loc_140002CE3
0x140002cdf  mov     rax, [rax+38h]
0x140002ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ce8  mov     esi, eax
0x140002cea  test    eax, eax
0x140002cec  jns     short loc_140002D27
0x140002cee  mov     rcx, [rsp+260h+var_1F8]
0x140002cf3  test    rcx, rcx
0x140002cf6  jz      short loc_140002D04
0x140002cf8  mov     rax, [rcx]
0x140002cfb  mov     rax, [rax+10h]
0x140002cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d04  mov     eax, esi
0x140002d06  jmp     loc_140003064
0x140002d0b  cmp     ecx, r12d
0x140002d0e  mov     rcx, [rsp+260h+var_1F8]
0x140002d13  mov     rax, [rcx]
0x140002d16  jnz     short loc_140002D1E
0x140002d18  mov     rax, [rax+30h]
0x140002d1c  jmp     short loc_140002D22
0x140002d1e  mov     rax, [rax+40h]
0x140002d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d27  add     rdi, 10h
0x140002d2b  mov     ecx, [rdi]
0x140002d2d  test    ecx, ecx
0x140002d2f  jnz     short loc_140002CB1
0x140002d31  test    r14d, r14d
0x140002d34  jnz     loc_14000304C
0x140002d3a  lea     r8d, [rcx+40h]; cchMax
0x140002d3e  mov     rcx, rbx; rguid
0x140002d41  lea     rdx, [rbp+160h+sz]; lpsz
0x140002d48  call    cs:__imp_StringFromGUID2
0x140002d4e  mov     ebx, 80h
0x140002d53  lea     r8, aClsid; "CLSID\\"
0x140002d5a  mov     edx, ebx
0x140002d5c  lea     rcx, [rbp+160h+SubKey]
0x140002d60  call    cs:__imp__o_wcscpy_s
0x140002d66  lea     r14d, [rbx-74h]
0x140002d6a  lea     r12d, [rbx-30h]
0x140002d6e  test    eax, eax
0x140002d70  jz      short loc_140002D96
0x140002d72  cmp     eax, r14d
0x140002d75  jz      loc_14000308F
0x140002d7b  cmp     eax, 16h
0x140002d7e  jz      loc_1400030A5
0x140002d84  cmp     eax, 22h ; '"'
0x140002d87  jz      loc_1400030A5
0x140002d8d  cmp     eax, r12d
0x140002d90  jnz     loc_14000309A
0x140002d96  lea     r8, [rbp+160h+sz]
0x140002d9d  mov     rdx, rbx
0x140002da0  lea     rcx, [rbp+160h+SubKey]
0x140002da4  call    cs:__imp__o_wcscat_s
0x140002daa  test    eax, eax
0x140002dac  jz      short loc_140002DD2
0x140002dae  cmp     eax, r14d
0x140002db1  jz      loc_14000308F
0x140002db7  cmp     eax, 16h
0x140002dba  jz      loc_1400030A5
0x140002dc0  cmp     eax, 22h ; '"'
0x140002dc3  jz      loc_1400030A5
0x140002dc9  cmp     eax, r12d
0x140002dcc  jnz     loc_14000309A
0x140002dd2  lea     r8, aRequiredCatego; "\\Required Categories"
0x140002dd9  mov     rdx, rbx
0x140002ddc  lea     rcx, [rbp+160h+SubKey]
0x140002de0  call    cs:__imp__o_wcscat_s
0x140002de6  test    eax, eax
0x140002de8  jz      short loc_140002E0E
0x140002dea  cmp     eax, r14d
0x140002ded  jz      loc_14000308F
0x140002df3  cmp     eax, 16h
0x140002df6  jz      loc_1400030A5
0x140002dfc  cmp     eax, 22h ; '"'
0x140002dff  jz      loc_1400030A5
0x140002e05  cmp     eax, r12d
0x140002e08  jnz     loc_14000309A
0x140002e0e  mov     rdi, 0FFFFFFFF80000000h
0x140002e15  mov     [rbp+160h+var_1D8], r15
0x140002e19  lea     rax, [rsp+260h+phkResult]
0x140002e1e  mov     [rbp+160h+var_1E0], rdi
0x140002e22  mov     rcx, rdi; hKey
0x140002e25  mov     [rbp+160h+var_1D0], r15
0x140002e29  mov     r9d, 20019h; samDesired
0x140002e2f  mov     [rsp+260h+cSubKeys], r15d
0x140002e34  xor     r8d, r8d; ulOptions
0x140002e37  mov     [rsp+260h+phkResult], r15
0x140002e3c  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x140002e40  mov     [rsp+260h+ppv], rax; phkResult
0x140002e45  mov     rbx, r15
0x140002e48  call    cs:__imp_RegOpenKeyExW
0x140002e4e  test    eax, eax
0x140002e50  jnz     short loc_140002EC4
0x140002e52  mov     rbx, [rsp+260h+phkResult]
0x140002e57  lea     rax, [rsp+260h+cSubKeys]
0x140002e5c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140002e61  xor     r9d, r9d; lpReserved
0x140002e64  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140002e69  xor     r8d, r8d; lpcchClass
0x140002e6c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140002e71  xor     edx, edx; lpClass
0x140002e73  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140002e78  mov     rcx, rbx; hKey
0x140002e7b  mov     [rsp+260h+lpcValues], r15; lpcValues
0x140002e80  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140002e85  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140002e8a  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x140002e8f  call    cs:__imp_RegQueryInfoKeyW
0x140002e95  mov     esi, eax
0x140002e97  test    rbx, rbx
0x140002e9a  jz      short loc_140002EA8
0x140002e9c  mov     rcx, rbx; hKey
0x140002e9f  call    cs:__imp_RegCloseKey
0x140002ea5  mov     rbx, r15
0x140002ea8  test    esi, esi
0x140002eaa  jnz     short loc_140002EC4
0x140002eac  cmp     [rsp+260h+cSubKeys], r15d
0x140002eb1  jnz     short loc_140002EC4
0x140002eb3  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x140002eb7  lea     rcx, [rbp+160h+var_1E0]; this
0x140002ebb  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140002ec0  mov     rdi, [rbp+160h+var_1E0]
0x140002ec4  mov     esi, 80h
0x140002ec9  lea     r8, aClsid; "CLSID\\"
0x140002ed0  mov     edx, esi
0x140002ed2  lea     rcx, [rbp+160h+SubKey]
0x140002ed6  call    cs:__imp__o_wcscpy_s
0x140002edc  test    eax, eax
0x140002ede  jz      short loc_140002F04
0x140002ee0  cmp     eax, r14d
0x140002ee3  jz      loc_14000308F
0x140002ee9  cmp     eax, 16h
0x140002eec  jz      loc_1400030A5
0x140002ef2  cmp     eax, 22h ; '"'
0x140002ef5  jz      loc_1400030A5
0x140002efb  cmp     eax, r12d
0x140002efe  jnz     loc_14000309A
0x140002f04  lea     r8, [rbp+160h+sz]
0x140002f0b  mov     rdx, rsi
0x140002f0e  lea     rcx, [rbp+160h+SubKey]
0x140002f12  call    cs:__imp__o_wcscat_s
0x140002f18  test    eax, eax
0x140002f1a  jz      short loc_140002F40
0x140002f1c  cmp     eax, r14d
0x140002f1f  jz      loc_14000308F
0x140002f25  cmp     eax, 16h
0x140002f28  jz      loc_1400030A5
0x140002f2e  cmp     eax, 22h ; '"'
0x140002f31  jz      loc_1400030A5
0x140002f37  cmp     eax, r12d
0x140002f3a  jnz     loc_14000309A
0x140002f40  lea     r8, aImplementedCat; "\\Implemented Categories"
0x140002f47  mov     rdx, rsi
0x140002f4a  lea     rcx, [rbp+160h+SubKey]
0x140002f4e  call    cs:__imp__o_wcscat_s
0x140002f54  test    eax, eax
0x140002f56  jz      short loc_140002F7C
0x140002f58  cmp     eax, r14d
0x140002f5b  jz      loc_14000308F
0x140002f61  cmp     eax, 16h
0x140002f64  jz      loc_1400030A5
0x140002f6a  cmp     eax, 22h ; '"'
0x140002f6d  jz      loc_1400030A5
0x140002f73  cmp     eax, r12d
0x140002f76  jnz     loc_14000309A
0x140002f7c  lea     rax, [rsp+260h+hKey]
0x140002f81  mov     [rsp+260h+hKey], r15
0x140002f86  mov     r9d, 20019h; samDesired
0x140002f8c  mov     [rsp+260h+ppv], rax; phkResult
0x140002f91  xor     r8d, r8d; ulOptions
0x140002f94  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x140002f98  mov     rcx, rdi; hKey
0x140002f9b  call    cs:__imp_RegOpenKeyExW
0x140002fa1  test    eax, eax
0x140002fa3  jnz     loc_140003030
0x140002fa9  mov     eax, r15d
0x140002fac  test    rbx, rbx
0x140002faf  jz      short loc_140002FBA
0x140002fb1  mov     rcx, rbx; hKey
0x140002fb4  call    cs:__imp_RegCloseKey
0x140002fba  mov     rbx, [rsp+260h+hKey]
0x140002fbf  test    eax, eax
0x140002fc1  jnz     short loc_140003030
0x140002fc3  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140002fc8  lea     rax, [rsp+260h+cSubKeys]
0x140002fcd  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140002fd2  xor     r9d, r9d; lpReserved
0x140002fd5  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140002fda  xor     r8d, r8d; lpcchClass
0x140002fdd  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140002fe2  xor     edx, edx; lpClass
0x140002fe4  mov     [rsp+260h+lpcValues], r15; lpcValues
0x140002fe9  mov     rcx, rbx; hKey
0x140002fec  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140002ff1  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140002ff6  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x140002ffb  call    cs:__imp_RegQueryInfoKeyW
0x140003001  mov     esi, eax
0x140003003  test    rbx, rbx
0x140003006  jz      short loc_140003014
0x140003008  mov     rcx, rbx; hKey
0x14000300b  call    cs:__imp_RegCloseKey
0x140003011  mov     rbx, r15
0x140003014  test    esi, esi
0x140003016  jnz     short loc_14000303E
0x140003018  cmp     [rsp+260h+cSubKeys], r15d
0x14000301d  jnz     short loc_140003030
0x14000301f  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x140003023  lea     rcx, [rbp+160h+var_1E0]; this
0x140003027  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000302c  mov     rdi, [rbp+160h+var_1E0]
0x140003030  test    rbx, rbx
0x140003033  jz      short loc_14000303E
0x140003035  mov     rcx, rbx; hKey
0x140003038  call    cs:__imp_RegCloseKey
0x14000303e  test    rdi, rdi
0x140003041  jz      short loc_14000304C
0x140003043  mov     rcx, rdi; hKey
0x140003046  call    cs:__imp_RegCloseKey
0x14000304c  mov     rcx, [rsp+260h+var_1F8]
0x140003051  test    rcx, rcx
0x140003054  jz      short loc_140003062
0x140003056  mov     rax, [rcx]
0x140003059  mov     rax, [rax+10h]
0x14000305d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003062  xor     eax, eax
0x140003064  mov     rcx, [rbp+160h+var_30]
0x14000306b  xor     rcx, rsp; StackCookie
0x14000306e  call    __security_check_cookie
0x140003073  lea     r11, [rsp+260h+var_20]
0x14000307b  mov     rbx, [r11+40h]
0x14000307f  mov     rsi, [r11+48h]
0x140003083  mov     rsp, r11
0x140003086  pop     r15
0x140003088  pop     r14
0x14000308a  pop     r12
0x14000308c  pop     rdi
0x14000308d  pop     rbp
0x14000308e  retn
0x14000308f  mov     ecx, 8007000Eh; int
0x140003094  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000309a  mov     ecx, 80004005h; int
0x14000309f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
