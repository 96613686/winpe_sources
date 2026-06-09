# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180010dcc`
- end: `0x18001128c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013ad0`
- `0x180013bd0`

## callees

- `0x1800020e0`
- `0x180010dcc`
- `0x180011478`
- `0x180011958`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010f7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010fba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800110ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011128`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010f7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010fba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800110ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011128`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010f3a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800110b0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010f3a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800110b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010f22`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010f22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010e73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010e73`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011069`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800111d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011069`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800111d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011175`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001118e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800111e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001118e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800111e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011220`

## string_xrefs

- `0x180010f28`: `CLSID\`
- `0x18001109e`: `CLSID\`

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

  v4 = a2;
  ppv = 0;
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
  {
LABEL_66:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_66;
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
      v27[0] = 0xFFFFFFFF80000000uLL;
      v27[1] = 0;
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
0x180010dcc  mov     [rsp-8+arg_10], rbx
0x180010dd1  mov     [rsp-8+arg_18], rsi
0x180010dd6  push    rbp
0x180010dd7  push    rdi
0x180010dd8  push    r12
0x180010dda  push    r14
0x180010ddc  push    r15
0x180010dde  lea     rbp, [rsp-140h]
0x180010de6  sub     rsp, 240h
0x180010ded  mov     rax, cs:__security_cookie
0x180010df4  xor     rax, rsp
0x180010df7  mov     [rbp+160h+var_30], rax
0x180010dfe  mov     r14d, r8d
0x180010e01  mov     rdi, rdx
0x180010e04  mov     rbx, rcx
0x180010e07  xor     r15d, r15d
0x180010e0a  mov     [rsp+260h+var_1F8], r15
0x180010e0f  xorps   xmm0, xmm0
0x180010e12  movups  [rbp+160h+var_1C8], xmm0
0x180010e16  test    rdx, rdx
0x180010e19  jnz     short loc_180010E20
0x180010e1b  jmp     loc_18001123E
0x180010e20  mov     eax, cs:GUID_NULL.Data1
0x180010e26  cmp     [rcx], eax
0x180010e28  jnz     short loc_180010E50
0x180010e2a  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180010e30  cmp     [rcx+4], eax
0x180010e33  jnz     short loc_180010E50
0x180010e35  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180010e3b  cmp     [rcx+8], eax
0x180010e3e  jnz     short loc_180010E50
0x180010e40  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180010e46  cmp     [rcx+0Ch], eax
0x180010e49  jnz     short loc_180010E50
0x180010e4b  jmp     loc_18001123E
0x180010e50  lea     rax, [rsp+260h+var_1F8]
0x180010e55  mov     [rsp+260h+ppv], rax; ppv
0x180010e5a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180010e61  mov     r12d, 1
0x180010e67  mov     r8d, r12d; dwClsContext
0x180010e6a  xor     edx, edx; pUnkOuter
0x180010e6c  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180010e73  call    cs:__imp_CoCreateInstance
0x180010e79  test    eax, eax
0x180010e7b  jns     loc_180010F01
0x180010e81  jmp     loc_180011227
0x180010e86  mov     rax, [rdi+8]
0x180010e8a  movups  xmm0, xmmword ptr [rax]
0x180010e8d  movdqu  [rbp+160h+var_1C8], xmm0
0x180010e92  lea     r9, [rbp+160h+var_1C8]
0x180010e96  mov     r8d, r12d
0x180010e99  mov     rdx, rbx
0x180010e9c  test    r14d, r14d
0x180010e9f  jz      short loc_180010EE1
0x180010ea1  cmp     ecx, r12d
0x180010ea4  mov     rcx, [rsp+260h+var_1F8]
0x180010ea9  mov     rax, [rcx]
0x180010eac  jnz     short loc_180010EB4
0x180010eae  mov     rax, [rax+28h]
0x180010eb2  jmp     short loc_180010EB8
0x180010eb4  mov     rax, [rax+38h]
0x180010eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ebd  mov     esi, eax
0x180010ebf  test    eax, eax
0x180010ec1  jns     short loc_180010EFD
0x180010ec3  mov     rcx, [rsp+260h+var_1F8]
0x180010ec8  test    rcx, rcx
0x180010ecb  jz      short loc_180010EDA
0x180010ecd  mov     rax, [rcx]
0x180010ed0  mov     rax, [rax+10h]
0x180010ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed9  nop
0x180010eda  mov     eax, esi
0x180010edc  jmp     loc_180011240
0x180010ee1  cmp     ecx, r12d
0x180010ee4  mov     rcx, [rsp+260h+var_1F8]
0x180010ee9  mov     rax, [rcx]
0x180010eec  jnz     short loc_180010EF4
0x180010eee  mov     rax, [rax+30h]
0x180010ef2  jmp     short loc_180010EF8
0x180010ef4  mov     rax, [rax+40h]
0x180010ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efd  add     rdi, 10h
0x180010f01  mov     ecx, [rdi]
0x180010f03  test    ecx, ecx
0x180010f05  jnz     loc_180010E86
0x180010f0b  test    r14d, r14d
0x180010f0e  jnz     loc_180011227
0x180010f14  lea     r8d, [rcx+40h]; cchMax
0x180010f18  lea     rdx, [rbp+160h+sz]; lpsz
0x180010f1f  mov     rcx, rbx; rguid
0x180010f22  call    cs:__imp_StringFromGUID2
0x180010f28  lea     r8, aClsid; "CLSID\\"
0x180010f2f  mov     ebx, 80h
0x180010f34  mov     edx, ebx
0x180010f36  lea     rcx, [rbp+160h+SubKey]
0x180010f3a  call    cs:__imp__o_wcscpy_s
0x180010f40  lea     r14d, [rbx-74h]
0x180010f44  lea     r12d, [rbx-30h]
0x180010f48  test    eax, eax
0x180010f4a  jz      short loc_180010F70
0x180010f4c  cmp     eax, r14d
0x180010f4f  jz      loc_18001126B
0x180010f55  cmp     eax, 16h
0x180010f58  jz      loc_180011281
0x180010f5e  cmp     eax, 22h ; '"'
0x180010f61  jz      loc_180011281
0x180010f67  cmp     eax, r12d
0x180010f6a  jnz     loc_180011276
0x180010f70  lea     r8, [rbp+160h+sz]
0x180010f77  mov     rdx, rbx
0x180010f7a  lea     rcx, [rbp+160h+SubKey]
0x180010f7e  call    cs:__imp__o_wcscat_s
0x180010f84  test    eax, eax
0x180010f86  jz      short loc_180010FAC
0x180010f88  cmp     eax, r14d
0x180010f8b  jz      loc_18001126B
0x180010f91  cmp     eax, 16h
0x180010f94  jz      loc_180011281
0x180010f9a  cmp     eax, 22h ; '"'
0x180010f9d  jz      loc_180011281
0x180010fa3  cmp     eax, r12d
0x180010fa6  jnz     loc_180011276
0x180010fac  lea     r8, aRequiredCatego; "\\Required Categories"
0x180010fb3  mov     rdx, rbx
0x180010fb6  lea     rcx, [rbp+160h+SubKey]
0x180010fba  call    cs:__imp__o_wcscat_s
0x180010fc0  test    eax, eax
0x180010fc2  jz      short loc_180010FE8
0x180010fc4  cmp     eax, r14d
0x180010fc7  jz      loc_18001126B
0x180010fcd  cmp     eax, 16h
0x180010fd0  jz      loc_180011281
0x180010fd6  cmp     eax, 22h ; '"'
0x180010fd9  jz      loc_180011281
0x180010fdf  cmp     eax, r12d
0x180010fe2  jnz     loc_180011276
0x180010fe8  mov     rdi, 0FFFFFFFF80000000h
0x180010fef  mov     [rbp+160h+var_1E0], rdi
0x180010ff3  mov     [rbp+160h+var_1D8], r15
0x180010ff7  mov     [rbp+160h+var_1D0], r15
0x180010ffb  mov     rbx, r15
0x180010ffe  mov     [rsp+260h+cSubKeys], r15d
0x180011003  mov     [rsp+260h+phkResult], r15
0x180011008  lea     rax, [rsp+260h+phkResult]
0x18001100d  mov     [rsp+260h+ppv], rax; phkResult
0x180011012  mov     r9d, 20019h; samDesired
0x180011018  xor     r8d, r8d; ulOptions
0x18001101b  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18001101f  mov     rcx, rdi; hKey
0x180011022  call    cs:__imp_RegOpenKeyExW
0x180011028  test    eax, eax
0x18001102a  jnz     short loc_18001109E
0x18001102c  mov     rbx, [rsp+260h+phkResult]
0x180011031  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180011036  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001103b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180011040  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180011045  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18001104a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001104f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180011054  lea     rax, [rsp+260h+cSubKeys]
0x180011059  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18001105e  xor     r9d, r9d; lpReserved
0x180011061  xor     r8d, r8d; lpcchClass
0x180011064  xor     edx, edx; lpClass
0x180011066  mov     rcx, rbx; hKey
0x180011069  call    cs:__imp_RegQueryInfoKeyW
0x18001106f  mov     esi, eax
0x180011071  test    rbx, rbx
0x180011074  jz      short loc_180011082
0x180011076  mov     rcx, rbx; hKey
0x180011079  call    cs:__imp_RegCloseKey
0x18001107f  mov     rbx, r15
0x180011082  test    esi, esi
0x180011084  jnz     short loc_18001109E
0x180011086  cmp     [rsp+260h+cSubKeys], r15d
0x18001108b  jnz     short loc_18001109E
0x18001108d  lea     rdx, [rbp+160h+SubKey]; wchar_t *
0x180011091  lea     rcx, [rbp+160h+var_1E0]; this
0x180011095  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18001109a  mov     rdi, [rbp+160h+var_1E0]
0x18001109e  lea     r8, aClsid; "CLSID\\"
0x1800110a5  mov     esi, 80h
0x1800110aa  mov     edx, esi
0x1800110ac  lea     rcx, [rbp+160h+SubKey]
0x1800110b0  call    cs:__imp__o_wcscpy_s
0x1800110b6  test    eax, eax
0x1800110b8  jz      short loc_1800110DE
0x1800110ba  cmp     eax, r14d
0x1800110bd  jz      loc_18001126B
0x1800110c3  cmp     eax, 16h
0x1800110c6  jz      loc_180011281
0x1800110cc  cmp     eax, 22h ; '"'
0x1800110cf  jz      loc_180011281
0x1800110d5  cmp     eax, r12d
0x1800110d8  jnz     loc_180011276
0x1800110de  lea     r8, [rbp+160h+sz]
0x1800110e5  mov     rdx, rsi
0x1800110e8  lea     rcx, [rbp+160h+SubKey]
0x1800110ec  call    cs:__imp__o_wcscat_s
0x1800110f2  test    eax, eax
0x1800110f4  jz      short loc_18001111A
0x1800110f6  cmp     eax, r14d
0x1800110f9  jz      loc_18001126B
0x1800110ff  cmp     eax, 16h
0x180011102  jz      loc_180011281
0x180011108  cmp     eax, 22h ; '"'
0x18001110b  jz      loc_180011281
0x180011111  cmp     eax, r12d
0x180011114  jnz     loc_180011276
0x18001111a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180011121  mov     rdx, rsi
0x180011124  lea     rcx, [rbp+160h+SubKey]
0x180011128  call    cs:__imp__o_wcscat_s
0x18001112e  test    eax, eax
0x180011130  jz      short loc_180011156
0x180011132  cmp     eax, r14d
0x180011135  jz      loc_18001126B
0x18001113b  cmp     eax, 16h
0x18001113e  jz      loc_180011281
0x180011144  cmp     eax, 22h ; '"'
0x180011147  jz      loc_180011281
0x18001114d  cmp     eax, r12d
0x180011150  jnz     loc_180011276
0x180011156  mov     [rsp+260h+hKey], r15
0x18001115b  lea     rax, [rsp+260h+hKey]
0x180011160  mov     [rsp+260h+ppv], rax; phkResult
0x180011165  mov     r9d, 20019h; samDesired
0x18001116b  xor     r8d, r8d; ulOptions
0x18001116e  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180011172  mov     rcx, rdi; hKey
0x180011175  call    cs:__imp_RegOpenKeyExW
0x18001117b  test    eax, eax
0x18001117d  jnz     loc_18001120A
0x180011183  mov     eax, r15d
0x180011186  test    rbx, rbx
0x180011189  jz      short loc_180011194
0x18001118b  mov     rcx, rbx; hKey
0x18001118e  call    cs:__imp_RegCloseKey
0x180011194  mov     rbx, [rsp+260h+hKey]
0x180011199  test    eax, eax
0x18001119b  jnz     short loc_18001120A
0x18001119d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800111a2  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800111a7  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800111ac  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800111b1  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800111b6  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800111bb  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800111c0  lea     rax, [rsp+260h+cSubKeys]
0x1800111c5  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800111ca  xor     r9d, r9d; lpReserved
0x1800111cd  xor     r8d, r8d; lpcchClass
0x1800111d0  xor     edx, edx; lpClass
0x1800111d2  mov     rcx, rbx; hKey
0x1800111d5  call    cs:__imp_RegQueryInfoKeyW
0x1800111db  mov     esi, eax
0x1800111dd  test    rbx, rbx
0x1800111e0  jz      short loc_1800111EE
0x1800111e2  mov     rcx, rbx; hKey
0x1800111e5  call    cs:__imp_RegCloseKey
0x1800111eb  mov     rbx, r15
0x1800111ee  test    esi, esi
0x1800111f0  jnz     short loc_180011218
0x1800111f2  cmp     [rsp+260h+cSubKeys], r15d
0x1800111f7  jnz     short loc_18001120A
0x1800111f9  lea     rdx, [rbp+160h+SubKey]; wchar_t *
0x1800111fd  lea     rcx, [rbp+160h+var_1E0]; this
0x180011201  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180011206  mov     rdi, [rbp+160h+var_1E0]
0x18001120a  test    rbx, rbx
0x18001120d  jz      short loc_180011218
0x18001120f  mov     rcx, rbx; hKey
0x180011212  call    cs:__imp_RegCloseKey
0x180011218  test    rdi, rdi
0x18001121b  jz      short loc_180011227
0x18001121d  mov     rcx, rdi; hKey
0x180011220  call    cs:__imp_RegCloseKey
0x180011226  nop
0x180011227  mov     rcx, [rsp+260h+var_1F8]
0x18001122c  test    rcx, rcx
0x18001122f  jz      short loc_18001123E
0x180011231  mov     rax, [rcx]
0x180011234  mov     rax, [rax+10h]
0x180011238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001123d  nop
0x18001123e  xor     eax, eax
0x180011240  mov     rcx, [rbp+160h+var_30]
0x180011247  xor     rcx, rsp; StackCookie
0x18001124a  call    __security_check_cookie
0x18001124f  lea     r11, [rsp+260h+var_20]
0x180011257  mov     rbx, [r11+40h]
0x18001125b  mov     rsi, [r11+48h]
0x18001125f  mov     rsp, r11
0x180011262  pop     r15
0x180011264  pop     r14
0x180011266  pop     r12
0x180011268  pop     rdi
0x180011269  pop     rbp
  ... truncated ...
```
