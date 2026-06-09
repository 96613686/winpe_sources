# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180013004`
- end: `0x18001350d`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1289`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015654`
- `0x180015c50`

## callees

- `0x1800065bc`
- `0x180013004`
- `0x180013e88`
- `0x18001b420`
- `0x180020010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800131b1`
- `msvcrt!wcscat_s` at `0x1800131ed`
- `msvcrt!wcscat_s` at `0x180013336`
- `msvcrt!wcscat_s` at `0x180013372`
- `msvcrt!wcscat_s` at `0x1800131b1`
- `msvcrt!wcscat_s` at `0x1800131ed`
- `msvcrt!wcscat_s` at `0x180013336`
- `msvcrt!wcscat_s` at `0x180013372`
- `msvcrt!wcscpy_s` at `0x18001316d`
- `msvcrt!wcscpy_s` at `0x1800132fa`
- `msvcrt!wcscpy_s` at `0x18001316d`
- `msvcrt!wcscpy_s` at `0x1800132fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800130ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800130ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013151`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013151`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800132ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013429`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800132ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013429`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800133d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001346b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800133d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001346b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800133bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800133bf`

## string_xrefs

- `0x18001315b`: `CLSID\`
- `0x1800132e8`: `CLSID\`

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
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  _QWORD v29[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  ppv = 0;
  v30 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4]
    || CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
    goto LABEL_66;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
      {
LABEL_66:
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return 0;
      }
      StringFromGUID2(rguid, sz, 64);
      v29[3] = 0;
      v12 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_72;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = wcscat_s(Destination, 0x80u, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_72;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      if ( !v14 )
        goto LABEL_37;
      if ( v14 != 12 )
      {
        if ( v14 != 22 && v14 != 34 )
        {
          if ( v14 == 80 )
          {
LABEL_37:
            v15 = HKEY_CLASSES_ROOT;
            v29[0] = 0xFFFFFFFF80000000uLL;
            v29[1] = 0;
            v29[2] = 0;
            v26 = 0;
            v27 = 0;
            v28 = 0;
            cSubKeys = 0;
            phkResult = 0;
            if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
            {
              v16 = phkResult;
              v26 = phkResult;
              v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
              if ( v16 )
              {
                RegCloseKey(v16);
                v26 = 0;
              }
              if ( !v17 && !cSubKeys )
              {
                ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v29, Destination);
                v15 = (HKEY)v29[0];
              }
            }
            v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
            if ( v18 )
            {
              if ( v18 == 12 )
                goto LABEL_69;
              if ( v18 == 22 || v18 == 34 )
                goto LABEL_74;
              if ( v18 != 80 )
                goto LABEL_73;
            }
            v19 = wcscat_s(Destination, 0x80u, sz);
            if ( v19 )
            {
              if ( v19 == 12 )
                goto LABEL_69;
              if ( v19 == 22 || v19 == 34 )
                goto LABEL_74;
              if ( v19 != 80 )
                goto LABEL_73;
            }
            v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
            if ( !v20 )
            {
LABEL_58:
              phkResult = 0;
              if ( !RegOpenKeyExW(v15, Destination, 0, 0x20019u, &phkResult) )
              {
                v21 = phkResult;
                v26 = phkResult;
                v22 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
                if ( v21 )
                {
                  RegCloseKey(v21);
                  v26 = 0;
                }
                if ( !v22 && !cSubKeys )
                {
                  ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v29, Destination);
                  v15 = (HKEY)v29[0];
                }
              }
              if ( v15 )
              {
                RegCloseKey(v15);
                v29[0] = 0;
              }
              goto LABEL_66;
            }
            if ( v20 != 12 )
            {
              if ( v20 != 22 && v20 != 34 )
              {
                if ( v20 == 80 )
                  goto LABEL_58;
LABEL_73:
                ATL::AtlThrowImpl(-2147467259);
              }
LABEL_74:
              ATL::AtlThrowImpl(-2147024809);
            }
LABEL_69:
            ATL::AtlThrowImpl(-2147024882);
          }
LABEL_70:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_71:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_72:
      ATL::AtlThrowImpl(-2147024882);
    }
    v30 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v30);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v30);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v30)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v30);
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
0x180013004  mov     [rsp-8+arg_10], rbx
0x180013009  mov     [rsp-8+arg_18], rsi
0x18001300e  push    rbp
0x18001300f  push    rdi
0x180013010  push    r12
0x180013012  push    r14
0x180013014  push    r15
0x180013016  lea     rbp, [rsp-150h]
0x18001301e  sub     rsp, 250h
0x180013025  mov     rax, cs:__security_cookie
0x18001302c  xor     rax, rsp
0x18001302f  mov     [rbp+170h+var_30], rax
0x180013036  mov     r14d, r8d
0x180013039  mov     rdi, rdx
0x18001303c  mov     rbx, rcx
0x18001303f  xor     r15d, r15d
0x180013042  mov     [rsp+270h+var_210], r15
0x180013047  xorps   xmm0, xmm0
0x18001304a  movups  [rbp+170h+var_1C0], xmm0
0x18001304e  test    rdx, rdx
0x180013051  jnz     short loc_180013058
0x180013053  jmp     loc_180013488
0x180013058  mov     eax, cs:GUID_NULL.Data1
0x18001305e  cmp     [rcx], eax
0x180013060  jnz     short loc_180013088
0x180013062  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180013068  cmp     [rcx+4], eax
0x18001306b  jnz     short loc_180013088
0x18001306d  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180013073  cmp     [rcx+8], eax
0x180013076  jnz     short loc_180013088
0x180013078  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18001307e  cmp     [rcx+0Ch], eax
0x180013081  jnz     short loc_180013088
0x180013083  jmp     loc_180013488
0x180013088  lea     rax, [rsp+270h+var_210]
0x18001308d  mov     [rsp+270h+ppv], rax; ppv
0x180013092  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180013099  mov     r12d, 1
0x18001309f  mov     r8d, r12d; dwClsContext
0x1800130a2  xor     edx, edx; pUnkOuter
0x1800130a4  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800130ab  call    cs:__imp_CoCreateInstance
0x1800130b1  test    eax, eax
0x1800130b3  jns     short loc_180013134
0x1800130b5  jmp     loc_180013488
0x1800130ba  mov     rax, [rdi+8]
0x1800130be  movups  xmm0, xmmword ptr [rax]
0x1800130c1  movdqu  [rbp+170h+var_1C0], xmm0
0x1800130c6  lea     r9, [rbp+170h+var_1C0]
0x1800130ca  mov     r8d, r12d
0x1800130cd  mov     rdx, rbx
0x1800130d0  test    r14d, r14d
0x1800130d3  jz      short loc_180013114
0x1800130d5  cmp     ecx, r12d
0x1800130d8  mov     rcx, [rsp+270h+var_210]
0x1800130dd  mov     rax, [rcx]
0x1800130e0  jnz     short loc_1800130E8
0x1800130e2  mov     rax, [rax+28h]
0x1800130e6  jmp     short loc_1800130EC
0x1800130e8  mov     rax, [rax+38h]
0x1800130ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130f1  mov     esi, eax
0x1800130f3  test    eax, eax
0x1800130f5  jns     short loc_180013130
0x1800130f7  mov     rcx, [rsp+270h+var_210]
0x1800130fc  test    rcx, rcx
0x1800130ff  jz      short loc_18001310D
0x180013101  mov     rax, [rcx]
0x180013104  mov     rax, [rax+10h]
0x180013108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001310d  mov     eax, esi
0x18001310f  jmp     loc_1800134A0
0x180013114  cmp     ecx, r12d
0x180013117  mov     rcx, [rsp+270h+var_210]
0x18001311c  mov     rax, [rcx]
0x18001311f  jnz     short loc_180013127
0x180013121  mov     rax, [rax+30h]
0x180013125  jmp     short loc_18001312B
0x180013127  mov     rax, [rax+40h]
0x18001312b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013130  add     rdi, 10h
0x180013134  mov     ecx, [rdi]
0x180013136  test    ecx, ecx
0x180013138  jnz     short loc_1800130BA
0x18001313a  test    r14d, r14d
0x18001313d  jnz     loc_180013488
0x180013143  lea     r8d, [rcx+40h]; cchMax
0x180013147  lea     rdx, [rbp+170h+sz]; lpsz
0x18001314e  mov     rcx, rbx; rguid
0x180013151  call    cs:__imp_StringFromGUID2
0x180013157  mov     [rbp+170h+var_1C8], r15
0x18001315b  lea     r8, aClsid; "CLSID\\"
0x180013162  mov     ebx, 80h
0x180013167  mov     edx, ebx; SizeInWords
0x180013169  lea     rcx, [rbp+170h+Destination]; Destination
0x18001316d  call    cs:__imp_wcscpy_s
0x180013173  lea     r14d, [rbx-74h]
0x180013177  lea     r12d, [rbx-30h]
0x18001317b  test    eax, eax
0x18001317d  jz      short loc_1800131A3
0x18001317f  cmp     eax, r14d
0x180013182  jz      loc_1800134EC
0x180013188  cmp     eax, 16h
0x18001318b  jz      loc_1800134E1
0x180013191  cmp     eax, 22h ; '"'
0x180013194  jz      loc_1800134E1
0x18001319a  cmp     eax, r12d
0x18001319d  jnz     loc_1800134D6
0x1800131a3  lea     r8, [rbp+170h+sz]; Source
0x1800131aa  mov     rdx, rbx; SizeInWords
0x1800131ad  lea     rcx, [rbp+170h+Destination]; Destination
0x1800131b1  call    cs:__imp_wcscat_s
0x1800131b7  test    eax, eax
0x1800131b9  jz      short loc_1800131DF
0x1800131bb  cmp     eax, r14d
0x1800131be  jz      loc_1800134EC
0x1800131c4  cmp     eax, 16h
0x1800131c7  jz      loc_1800134E1
0x1800131cd  cmp     eax, 22h ; '"'
0x1800131d0  jz      loc_1800134E1
0x1800131d6  cmp     eax, r12d
0x1800131d9  jnz     loc_1800134D6
0x1800131df  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800131e6  mov     rdx, rbx; SizeInWords
0x1800131e9  lea     rcx, [rbp+170h+Destination]; Destination
0x1800131ed  call    cs:__imp_wcscat_s
0x1800131f3  test    eax, eax
0x1800131f5  jz      short loc_18001321B
0x1800131f7  cmp     eax, r14d
0x1800131fa  jz      loc_1800134EC
0x180013200  cmp     eax, 16h
0x180013203  jz      loc_1800134E1
0x180013209  cmp     eax, 22h ; '"'
0x18001320c  jz      loc_1800134E1
0x180013212  cmp     eax, r12d
0x180013215  jnz     loc_1800134D6
0x18001321b  mov     rdi, 0FFFFFFFF80000000h
0x180013222  mov     [rbp+170h+var_1E0], rdi
0x180013226  mov     [rbp+170h+var_1D8], r15
0x18001322a  mov     [rbp+170h+var_1D0], r15
0x18001322e  mov     rbx, r15
0x180013231  mov     [rsp+270h+var_1F8], rbx
0x180013236  mov     [rbp+170h+var_1F0], r15
0x18001323a  mov     [rbp+170h+var_1E8], r15
0x18001323e  mov     [rsp+270h+cSubKeys], r15d
0x180013243  mov     [rsp+270h+phkResult], r15
0x180013248  lea     rax, [rsp+270h+phkResult]
0x18001324d  mov     [rsp+270h+ppv], rax; phkResult
0x180013252  mov     r9d, 20019h; samDesired
0x180013258  xor     r8d, r8d; ulOptions
0x18001325b  lea     rdx, [rbp+170h+Destination]; lpSubKey
0x18001325f  mov     rcx, rdi; hKey
0x180013262  call    cs:__imp_RegOpenKeyExW
0x180013268  test    eax, eax
0x18001326a  jnz     short loc_1800132E8
0x18001326c  mov     rbx, [rsp+270h+phkResult]
0x180013271  mov     [rsp+270h+var_1F8], rbx
0x180013276  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001327b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180013280  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180013285  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001328a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001328f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180013294  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180013299  lea     rax, [rsp+270h+cSubKeys]
0x18001329e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800132a3  xor     r9d, r9d; lpReserved
0x1800132a6  xor     r8d, r8d; lpcchClass
0x1800132a9  xor     edx, edx; lpClass
0x1800132ab  mov     rcx, rbx; hKey
0x1800132ae  call    cs:__imp_RegQueryInfoKeyW
0x1800132b4  mov     esi, eax
0x1800132b6  test    rbx, rbx
0x1800132b9  jz      short loc_1800132CC
0x1800132bb  mov     rcx, rbx; hKey
0x1800132be  call    cs:__imp_RegCloseKey
0x1800132c4  mov     rbx, r15
0x1800132c7  mov     [rsp+270h+var_1F8], rbx
0x1800132cc  test    esi, esi
0x1800132ce  jnz     short loc_1800132E8
0x1800132d0  cmp     [rsp+270h+cSubKeys], r15d
0x1800132d5  jnz     short loc_1800132E8
0x1800132d7  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800132db  lea     rcx, [rbp+170h+var_1E0]; this
0x1800132df  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800132e4  mov     rdi, [rbp+170h+var_1E0]
0x1800132e8  lea     r8, aClsid; "CLSID\\"
0x1800132ef  mov     esi, 80h
0x1800132f4  mov     edx, esi; SizeInWords
0x1800132f6  lea     rcx, [rbp+170h+Destination]; Destination
0x1800132fa  call    cs:__imp_wcscpy_s
0x180013300  test    eax, eax
0x180013302  jz      short loc_180013328
0x180013304  cmp     eax, r14d
0x180013307  jz      loc_1800134CB
0x18001330d  cmp     eax, 16h
0x180013310  jz      loc_180013502
0x180013316  cmp     eax, 22h ; '"'
0x180013319  jz      loc_180013502
0x18001331f  cmp     eax, r12d
0x180013322  jnz     loc_1800134F7
0x180013328  lea     r8, [rbp+170h+sz]; Source
0x18001332f  mov     rdx, rsi; SizeInWords
0x180013332  lea     rcx, [rbp+170h+Destination]; Destination
0x180013336  call    cs:__imp_wcscat_s
0x18001333c  test    eax, eax
0x18001333e  jz      short loc_180013364
0x180013340  cmp     eax, r14d
0x180013343  jz      loc_1800134CB
0x180013349  cmp     eax, 16h
0x18001334c  jz      loc_180013502
0x180013352  cmp     eax, 22h ; '"'
0x180013355  jz      loc_180013502
0x18001335b  cmp     eax, r12d
0x18001335e  jnz     loc_1800134F7
0x180013364  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18001336b  mov     rdx, rsi; SizeInWords
0x18001336e  lea     rcx, [rbp+170h+Destination]; Destination
0x180013372  call    cs:__imp_wcscat_s
0x180013378  test    eax, eax
0x18001337a  jz      short loc_1800133A0
0x18001337c  cmp     eax, r14d
0x18001337f  jz      loc_1800134CB
0x180013385  cmp     eax, 16h
0x180013388  jz      loc_180013502
0x18001338e  cmp     eax, 22h ; '"'
0x180013391  jz      loc_180013502
0x180013397  cmp     eax, r12d
0x18001339a  jnz     loc_1800134F7
0x1800133a0  mov     [rsp+270h+phkResult], r15
0x1800133a5  lea     rax, [rsp+270h+phkResult]
0x1800133aa  mov     [rsp+270h+ppv], rax; phkResult
0x1800133af  mov     r9d, 20019h; samDesired
0x1800133b5  xor     r8d, r8d; ulOptions
0x1800133b8  lea     rdx, [rbp+170h+Destination]; lpSubKey
0x1800133bc  mov     rcx, rdi; hKey
0x1800133bf  call    cs:__imp_RegOpenKeyExW
0x1800133c5  test    eax, eax
0x1800133c7  jnz     loc_180013463
0x1800133cd  mov     eax, r15d
0x1800133d0  test    rbx, rbx
0x1800133d3  jz      short loc_1800133E3
0x1800133d5  mov     rcx, rbx; hKey
0x1800133d8  call    cs:__imp_RegCloseKey
0x1800133de  mov     [rsp+270h+var_1F8], r15
0x1800133e3  mov     rbx, [rsp+270h+phkResult]
0x1800133e8  mov     [rsp+270h+var_1F8], rbx
0x1800133ed  test    eax, eax
0x1800133ef  jnz     short loc_180013463
0x1800133f1  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800133f6  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800133fb  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180013400  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180013405  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001340a  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001340f  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180013414  lea     rax, [rsp+270h+cSubKeys]
0x180013419  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001341e  xor     r9d, r9d; lpReserved
0x180013421  xor     r8d, r8d; lpcchClass
0x180013424  xor     edx, edx; lpClass
0x180013426  mov     rcx, rbx; hKey
0x180013429  call    cs:__imp_RegQueryInfoKeyW
0x18001342f  mov     esi, eax
0x180013431  test    rbx, rbx
0x180013434  jz      short loc_180013447
0x180013436  mov     rcx, rbx; hKey
0x180013439  call    cs:__imp_RegCloseKey
0x18001343f  mov     rbx, r15
0x180013442  mov     [rsp+270h+var_1F8], rbx
0x180013447  test    esi, esi
0x180013449  jnz     short loc_180013463
0x18001344b  cmp     [rsp+270h+cSubKeys], r15d
0x180013450  jnz     short loc_180013463
0x180013452  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180013456  lea     rcx, [rbp+170h+var_1E0]; this
0x18001345a  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001345f  mov     rdi, [rbp+170h+var_1E0]
0x180013463  test    rbx, rbx
0x180013466  jz      short loc_180013476
0x180013468  mov     rcx, rbx; hKey
0x18001346b  call    cs:__imp_RegCloseKey
0x180013471  mov     [rsp+270h+var_1F8], r15
0x180013476  test    rdi, rdi
0x180013479  jz      short loc_180013488
0x18001347b  mov     rcx, rdi; hKey
0x18001347e  call    cs:__imp_RegCloseKey
0x180013484  mov     [rbp+170h+var_1E0], r15
0x180013488  mov     rcx, [rsp+270h+var_210]
0x18001348d  test    rcx, rcx
0x180013490  jz      short loc_18001349E
0x180013492  mov     rax, [rcx]
0x180013495  mov     rax, [rax+10h]
0x180013499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001349e  xor     eax, eax
0x1800134a0  mov     rcx, [rbp+170h+var_30]
0x1800134a7  xor     rcx, rsp; StackCookie
0x1800134aa  call    __security_check_cookie
0x1800134af  lea     r11, [rsp+270h+var_20]
  ... truncated ...
```
