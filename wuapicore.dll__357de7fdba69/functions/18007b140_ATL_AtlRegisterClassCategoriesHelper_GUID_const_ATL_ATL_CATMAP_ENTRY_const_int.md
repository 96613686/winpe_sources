# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18007b140`
- end: `0x18007b5b8`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1144`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180077110`
- `0x180077230`

## callees

- `0x180004d50`
- `0x18007b140`
- `0x18007ce08`
- `0x18007d06c`
- `0x18009aff4`
- `0x18009b000`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b1e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b1e3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007b271`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007b271`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b3bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b505`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b3bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b3cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b53e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b54b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b3cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b53e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b54b`

## string_xrefs

- `0x18007b283`: `CLSID\`
- `0x18007b3fc`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
    || rguid->Data1 == GUID_NULL.Data1
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
  if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
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
0x18007b140  mov     [rsp-8+arg_10], rbx
0x18007b145  mov     [rsp-8+arg_18], rsi
0x18007b14a  push    rbp
0x18007b14b  push    rdi
0x18007b14c  push    r12
0x18007b14e  push    r14
0x18007b150  push    r15
0x18007b152  lea     rbp, [rsp-140h]
0x18007b15a  sub     rsp, 240h
0x18007b161  mov     rax, cs:__security_cookie
0x18007b168  xor     rax, rsp
0x18007b16b  mov     [rbp+160h+var_30], rax
0x18007b172  mov     r14d, r8d
0x18007b175  mov     rsi, rdx
0x18007b178  mov     rbx, rcx
0x18007b17b  xor     r15d, r15d
0x18007b17e  mov     [rbp+160h+var_1C8], r15
0x18007b182  xorps   xmm0, xmm0
0x18007b185  movups  [rbp+160h+var_1C0], xmm0
0x18007b189  test    rdx, rdx
0x18007b18c  jz      loc_18007B551
0x18007b192  mov     eax, cs:GUID_NULL.Data1
0x18007b198  cmp     [rcx], eax
0x18007b19a  jnz     short loc_18007B1C1
0x18007b19c  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18007b1a2  cmp     [rcx+4], eax
0x18007b1a5  jnz     short loc_18007B1C1
0x18007b1a7  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18007b1ad  cmp     [rcx+8], eax
0x18007b1b0  jnz     short loc_18007B1C1
0x18007b1b2  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18007b1b8  cmp     [rcx+0Ch], eax
0x18007b1bb  jz      loc_18007B551
0x18007b1c1  lea     rax, [rbp+160h+var_1C8]
0x18007b1c5  mov     [rsp+260h+ppv], rax; ppv
0x18007b1ca  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18007b1d1  mov     r12d, 1
0x18007b1d7  mov     r8d, r12d; dwClsContext
0x18007b1da  xor     edx, edx; pUnkOuter
0x18007b1dc  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007b1e3  call    cs:__imp_CoCreateInstance
0x18007b1e9  test    eax, eax
0x18007b1eb  js      loc_18007B551
0x18007b1f1  jmp     short loc_18007B254
0x18007b1f3  mov     rax, [rsi+8]
0x18007b1f7  movups  xmm0, xmmword ptr [rax]
0x18007b1fa  movdqu  [rbp+160h+var_1C0], xmm0
0x18007b1ff  lea     r9, [rbp+160h+var_1C0]
0x18007b203  mov     r8d, r12d
0x18007b206  mov     rdx, rbx
0x18007b209  test    r14d, r14d
0x18007b20c  jz      short loc_18007B235
0x18007b20e  cmp     ecx, r12d
0x18007b211  mov     rcx, [rbp+160h+var_1C8]
0x18007b215  mov     rax, [rcx]
0x18007b218  jnz     short loc_18007B220
0x18007b21a  mov     rax, [rax+28h]
0x18007b21e  jmp     short loc_18007B224
0x18007b220  mov     rax, [rax+38h]
0x18007b224  call    _guard_dispatch_icall
0x18007b229  mov     edi, eax
0x18007b22b  test    eax, eax
0x18007b22d  js      loc_18007B554
0x18007b233  jmp     short loc_18007B250
0x18007b235  cmp     ecx, r12d
0x18007b238  mov     rcx, [rbp+160h+var_1C8]
0x18007b23c  mov     rax, [rcx]
0x18007b23f  jnz     short loc_18007B247
0x18007b241  mov     rax, [rax+30h]
0x18007b245  jmp     short loc_18007B24B
0x18007b247  mov     rax, [rax+40h]
0x18007b24b  call    _guard_dispatch_icall
0x18007b250  add     rsi, 10h
0x18007b254  mov     ecx, [rsi]
0x18007b256  test    ecx, ecx
0x18007b258  jnz     short loc_18007B1F3
0x18007b25a  test    r14d, r14d
0x18007b25d  jnz     loc_18007B551
0x18007b263  lea     r8d, [rcx+40h]; cchMax
0x18007b267  lea     rdx, [rbp+160h+sz]; lpsz
0x18007b26e  mov     rcx, rbx; rguid
0x18007b271  call    cs:__imp_StringFromGUID2
0x18007b277  test    eax, eax
0x18007b279  jnz     short loc_18007B283
0x18007b27b  lea     edi, [rax+0Dh]
0x18007b27e  jmp     loc_18007B554
0x18007b283  lea     r8, aClsid; "CLSID\\"
0x18007b28a  mov     ebx, 80h
0x18007b28f  mov     edx, ebx; SizeInWords
0x18007b291  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b295  call    wcscpy_s
0x18007b29a  lea     esi, [rbx-30h]
0x18007b29d  lea     r12d, [rbx-74h]
0x18007b2a1  lea     r14d, [rbx-5Eh]
0x18007b2a5  test    eax, eax
0x18007b2a7  jz      short loc_18007B2CC
0x18007b2a9  cmp     eax, r12d
0x18007b2ac  jz      loc_18007B597
0x18007b2b2  cmp     eax, 16h
0x18007b2b5  jz      loc_18007B5AD
0x18007b2bb  cmp     eax, r14d
0x18007b2be  jz      loc_18007B5AD
0x18007b2c4  cmp     eax, esi
0x18007b2c6  jnz     loc_18007B5A2
0x18007b2cc  lea     r8, [rbp+160h+sz]; Source
0x18007b2d3  mov     rdx, rbx; SizeInWords
0x18007b2d6  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b2da  call    wcscat_s
0x18007b2df  test    eax, eax
0x18007b2e1  jz      short loc_18007B306
0x18007b2e3  cmp     eax, r12d
0x18007b2e6  jz      loc_18007B597
0x18007b2ec  cmp     eax, 16h
0x18007b2ef  jz      loc_18007B5AD
0x18007b2f5  cmp     eax, r14d
0x18007b2f8  jz      loc_18007B5AD
0x18007b2fe  cmp     eax, esi
0x18007b300  jnz     loc_18007B5A2
0x18007b306  lea     r8, aRequiredCatego; "\\Required Categories"
0x18007b30d  mov     rdx, rbx; SizeInWords
0x18007b310  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b314  call    wcscat_s
0x18007b319  test    eax, eax
0x18007b31b  jz      short loc_18007B340
0x18007b31d  cmp     eax, r12d
0x18007b320  jz      loc_18007B597
0x18007b326  cmp     eax, 16h
0x18007b329  jz      loc_18007B5AD
0x18007b32f  cmp     eax, r14d
0x18007b332  jz      loc_18007B5AD
0x18007b338  cmp     eax, esi
0x18007b33a  jnz     loc_18007B5A2
0x18007b340  mov     [rbp+160h+var_1E0], r15
0x18007b344  mov     [rsp+260h+var_1E8], 0FFFFFFFF80000000h
0x18007b34d  mov     [rbp+160h+var_1D8], r15
0x18007b351  mov     [rsp+260h+var_1F8], r15
0x18007b356  mov     [rsp+260h+hKey], r15
0x18007b35b  mov     [rsp+260h+var_1F0], r15
0x18007b360  mov     [rbp+160h+cSubKeys], r15d
0x18007b364  mov     r9d, 20019h; unsigned int
0x18007b36a  lea     r8, [rbp+160h+Destination]; wchar_t *
0x18007b36e  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18007b375  lea     rcx, [rsp+260h+hKey]; this
0x18007b37a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18007b37f  test    eax, eax
0x18007b381  jnz     short loc_18007B3FC
0x18007b383  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18007b388  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18007b38d  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18007b392  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18007b397  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18007b39c  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18007b3a1  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18007b3a6  lea     rax, [rbp+160h+cSubKeys]
0x18007b3aa  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18007b3af  xor     r9d, r9d; lpReserved
0x18007b3b2  xor     r8d, r8d; lpcchClass
0x18007b3b5  xor     edx, edx; lpClass
0x18007b3b7  mov     rbx, [rsp+260h+hKey]
0x18007b3bc  mov     rcx, rbx; hKey
0x18007b3bf  call    cs:__imp_RegQueryInfoKeyW
0x18007b3c5  mov     edi, eax
0x18007b3c7  test    rbx, rbx
0x18007b3ca  jz      short loc_18007B3DA
0x18007b3cc  mov     rcx, rbx; hKey
0x18007b3cf  call    cs:__imp_RegCloseKey
0x18007b3d5  mov     [rsp+260h+hKey], r15
0x18007b3da  mov     dword ptr [rsp+260h+var_1F8], r15d
0x18007b3df  test    edi, edi
0x18007b3e1  jnz     short loc_18007B3F7
0x18007b3e3  cmp     [rbp+160h+cSubKeys], r15d
0x18007b3e7  jnz     short loc_18007B3F7
0x18007b3e9  lea     rdx, [rbp+160h+Destination]; wchar_t *
0x18007b3ed  lea     rcx, [rsp+260h+var_1E8]; this
0x18007b3f2  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18007b3f7  mov     ebx, 80h
0x18007b3fc  lea     r8, aClsid; "CLSID\\"
0x18007b403  mov     rdx, rbx; SizeInWords
0x18007b406  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b40a  call    wcscpy_s
0x18007b40f  test    eax, eax
0x18007b411  jz      short loc_18007B436
0x18007b413  cmp     eax, r12d
0x18007b416  jz      loc_18007B597
0x18007b41c  cmp     eax, 16h
0x18007b41f  jz      loc_18007B5AD
0x18007b425  cmp     eax, r14d
0x18007b428  jz      loc_18007B5AD
0x18007b42e  cmp     eax, esi
0x18007b430  jnz     loc_18007B5A2
0x18007b436  lea     r8, [rbp+160h+sz]; Source
0x18007b43d  mov     rdx, rbx; SizeInWords
0x18007b440  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b444  call    wcscat_s
0x18007b449  test    eax, eax
0x18007b44b  jz      short loc_18007B470
0x18007b44d  cmp     eax, r12d
0x18007b450  jz      loc_18007B597
0x18007b456  cmp     eax, 16h
0x18007b459  jz      loc_18007B5AD
0x18007b45f  cmp     eax, r14d
0x18007b462  jz      loc_18007B5AD
0x18007b468  cmp     eax, esi
0x18007b46a  jnz     loc_18007B5A2
0x18007b470  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18007b477  mov     rdx, rbx; SizeInWords
0x18007b47a  lea     rcx, [rbp+160h+Destination]; Destination
0x18007b47e  call    wcscat_s
0x18007b483  test    eax, eax
0x18007b485  jz      short loc_18007B4AA
0x18007b487  cmp     eax, r12d
0x18007b48a  jz      loc_18007B597
0x18007b490  cmp     eax, 16h
0x18007b493  jz      loc_18007B5AD
0x18007b499  cmp     eax, r14d
0x18007b49c  jz      loc_18007B5AD
0x18007b4a2  cmp     eax, esi
0x18007b4a4  jnz     loc_18007B5A2
0x18007b4aa  mov     r9d, 20019h; unsigned int
0x18007b4b0  lea     r8, [rbp+160h+Destination]; wchar_t *
0x18007b4b4  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18007b4bb  lea     rcx, [rsp+260h+hKey]; this
0x18007b4c0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18007b4c5  mov     rbx, [rsp+260h+hKey]
0x18007b4ca  test    eax, eax
0x18007b4cc  jnz     short loc_18007B536
0x18007b4ce  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18007b4d3  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18007b4d8  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18007b4dd  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18007b4e2  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18007b4e7  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18007b4ec  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18007b4f1  lea     rax, [rbp+160h+cSubKeys]
0x18007b4f5  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18007b4fa  xor     r9d, r9d; lpReserved
0x18007b4fd  xor     r8d, r8d; lpcchClass
0x18007b500  xor     edx, edx; lpClass
0x18007b502  mov     rcx, rbx; hKey
0x18007b505  call    cs:__imp_RegQueryInfoKeyW
0x18007b50b  mov     edi, eax
0x18007b50d  test    rbx, rbx
0x18007b510  jz      short loc_18007B51E
0x18007b512  mov     rcx, rbx; hKey
0x18007b515  call    cs:__imp_RegCloseKey
0x18007b51b  mov     rbx, r15
0x18007b51e  test    edi, edi
0x18007b520  jnz     short loc_18007B536
0x18007b522  cmp     [rbp+160h+cSubKeys], r15d
0x18007b526  jnz     short loc_18007B536
0x18007b528  lea     rdx, [rbp+160h+Destination]; wchar_t *
0x18007b52c  lea     rcx, [rsp+260h+var_1E8]; this
0x18007b531  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18007b536  test    rbx, rbx
0x18007b539  jz      short loc_18007B544
0x18007b53b  mov     rcx, rbx; hKey
0x18007b53e  call    cs:__imp_RegCloseKey
0x18007b544  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007b54b  call    cs:__imp_RegCloseKey
0x18007b551  mov     edi, r15d
0x18007b554  mov     rcx, [rbp+160h+var_1C8]
0x18007b558  test    rcx, rcx
0x18007b55b  jz      short loc_18007B56A
0x18007b55d  mov     rdx, [rcx]
0x18007b560  mov     rax, [rdx+10h]
0x18007b564  call    _guard_dispatch_icall
0x18007b569  nop
0x18007b56a  mov     eax, edi
0x18007b56c  mov     rcx, [rbp+160h+var_30]
0x18007b573  xor     rcx, rsp; StackCookie
0x18007b576  call    __security_check_cookie
0x18007b57b  lea     r11, [rsp+260h+var_20]
0x18007b583  mov     rbx, [r11+40h]
0x18007b587  mov     rsi, [r11+48h]
0x18007b58b  mov     rsp, r11
0x18007b58e  pop     r15
0x18007b590  pop     r14
0x18007b592  pop     r12
0x18007b594  pop     rdi
0x18007b595  pop     rbp
0x18007b596  retn
0x18007b597  mov     ecx, 8007000Eh; int
0x18007b59c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007b5a2  mov     ecx, 80004005h; int
0x18007b5a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007b5ad  mov     ecx, 80070057h; int
0x18007b5b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
