# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180003ae0`
- end: `0x180003e0f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `815`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004314`
- `0x180004494`

## callees

- `0x1800027f0`
- `0x1800036d0`
- `0x180003728`
- `0x1800038d4`
- `0x180003ae0`
- `0x180004080`
- `0x1800040ac`
- `0x1800042b4`
- `0x180004674`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003c25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003c3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003d18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003d33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003c25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003c3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003d18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180003d33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003c0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003cfd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003c0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003cfd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b68`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003bef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003bef`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003cc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003d8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003cc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003d8f`

## string_xrefs

- `0x180003c00`: `CLSID\`
- `0x180003cef`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  HKEY v12; // rdi
  unsigned int v13; // r9d
  LSTATUS v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r9d
  LSTATUS v19; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v26 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v26);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v26);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v26);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, v13) )
      {
        v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v14 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
          v12 = (HKEY)v24[0];
        }
      }
      v15 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v16);
      v17 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v17);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, v18) )
      {
        v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v19 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180003ae0  mov     [rsp-8+arg_10], rbx
0x180003ae5  mov     [rsp-8+arg_18], rsi
0x180003aea  push    rbp
0x180003aeb  push    rdi
0x180003aec  push    r12
0x180003aee  push    r14
0x180003af0  push    r15
0x180003af2  lea     rbp, [rsp-150h]
0x180003afa  sub     rsp, 250h
0x180003b01  mov     rax, cs:__security_cookie
0x180003b08  xor     rax, rsp
0x180003b0b  mov     [rbp+170h+var_30], rax
0x180003b12  xor     r15d, r15d
0x180003b15  xorps   xmm0, xmm0
0x180003b18  mov     [rsp+270h+var_208], r15
0x180003b1d  mov     r14d, r8d
0x180003b20  mov     rbx, rdx
0x180003b23  mov     rsi, rcx
0x180003b26  movups  [rbp+170h+var_1C8], xmm0
0x180003b2a  test    rdx, rdx
0x180003b2d  jz      loc_180003DD5
0x180003b33  lea     rdx, GUID_NULL
0x180003b3a  call    InlineIsEqualGUID
0x180003b3f  test    eax, eax
0x180003b41  jnz     loc_180003DD5
0x180003b47  lea     rax, [rsp+270h+var_208]
0x180003b4c  xor     edx, edx; pUnkOuter
0x180003b4e  lea     r12d, [r15+1]
0x180003b52  mov     [rsp+270h+ppv], rax; ppv
0x180003b57  mov     r8d, r12d; dwClsContext
0x180003b5a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003b61  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003b68  call    cs:__imp_CoCreateInstance
0x180003b6e  test    eax, eax
0x180003b70  js      loc_180003DD5
0x180003b76  cmp     [rbx], r15d
0x180003b79  jz      short loc_180003BD8
0x180003b7b  mov     rax, [rbx+8]
0x180003b7f  lea     r9, [rbp+170h+var_1C8]
0x180003b83  mov     rcx, [rsp+270h+var_208]
0x180003b88  mov     r8d, r12d
0x180003b8b  mov     rdx, rsi
0x180003b8e  movups  xmm0, xmmword ptr [rax]
0x180003b91  movdqu  [rbp+170h+var_1C8], xmm0
0x180003b96  mov     rax, [rcx]
0x180003b99  test    r14d, r14d
0x180003b9c  jz      short loc_180003BBE
0x180003b9e  cmp     [rbx], r12d
0x180003ba1  jnz     short loc_180003BA9
0x180003ba3  mov     rax, [rax+28h]
0x180003ba7  jmp     short loc_180003BAD
0x180003ba9  mov     rax, [rax+38h]
0x180003bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb2  mov     edi, eax
0x180003bb4  test    eax, eax
0x180003bb6  js      loc_180003DD8
0x180003bbc  jmp     short loc_180003BD2
0x180003bbe  cmp     [rbx], r12d
0x180003bc1  jnz     short loc_180003BC9
0x180003bc3  mov     rax, [rax+30h]
0x180003bc7  jmp     short loc_180003BCD
0x180003bc9  mov     rax, [rax+40h]
0x180003bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd2  add     rbx, 10h
0x180003bd6  jmp     short loc_180003B76
0x180003bd8  test    r14d, r14d
0x180003bdb  jnz     loc_180003DD5
0x180003be1  lea     r8d, [r14+40h]; cchMax
0x180003be5  mov     rcx, rsi; rguid
0x180003be8  lea     rdx, [rbp+170h+sz]; lpsz
0x180003bef  call    cs:__imp_StringFromGUID2
0x180003bf5  mov     esi, 80h
0x180003bfa  mov     [rbp+170h+var_1D0], r15
0x180003bfe  mov     edx, esi
0x180003c00  lea     r8, aClsid; "CLSID\\"
0x180003c07  lea     rcx, [rbp+170h+SubKey]
0x180003c0b  call    cs:__imp__o_wcscpy_s
0x180003c11  mov     ecx, eax; int
0x180003c13  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003c18  lea     r8, [rbp+170h+sz]
0x180003c1f  mov     edx, esi
0x180003c21  lea     rcx, [rbp+170h+SubKey]
0x180003c25  call    cs:__imp__o_wcscat_s
0x180003c2b  mov     ecx, eax; int
0x180003c2d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003c32  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003c39  mov     edx, esi
0x180003c3b  lea     rcx, [rbp+170h+SubKey]
0x180003c3f  call    cs:__imp__o_wcscat_s
0x180003c45  mov     ecx, eax; int
0x180003c47  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003c4c  mov     rdi, 0FFFFFFFF80000000h
0x180003c53  mov     [rbp+170h+var_1E0], r15
0x180003c57  mov     rdx, rdi; hKey
0x180003c5a  mov     [rbp+170h+var_1E8], rdi
0x180003c5e  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180003c62  mov     [rbp+170h+var_1D8], r15
0x180003c66  lea     rcx, [rsp+270h+hKey]; this
0x180003c6b  mov     [rsp+270h+hKey], r15
0x180003c70  mov     [rsp+270h+var_1F8], r15
0x180003c75  mov     [rbp+170h+var_1F0], r15
0x180003c79  mov     [rsp+270h+cSubKeys], r15d
0x180003c7e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180003c83  test    eax, eax
0x180003c85  jnz     short loc_180003CEF
0x180003c87  mov     rcx, [rsp+270h+hKey]; hKey
0x180003c8c  lea     rax, [rsp+270h+cSubKeys]
0x180003c91  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003c96  xor     r9d, r9d; lpReserved
0x180003c99  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003c9e  xor     r8d, r8d; lpcchClass
0x180003ca1  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003ca6  xor     edx, edx; lpClass
0x180003ca8  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003cad  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180003cb2  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003cb7  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003cbc  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180003cc1  call    cs:__imp_RegQueryInfoKeyW
0x180003cc7  lea     rcx, [rsp+270h+hKey]; this
0x180003ccc  mov     ebx, eax
0x180003cce  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003cd3  test    ebx, ebx
0x180003cd5  jnz     short loc_180003CEF
0x180003cd7  cmp     [rsp+270h+cSubKeys], r15d
0x180003cdc  jnz     short loc_180003CEF
0x180003cde  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180003ce2  lea     rcx, [rbp+170h+var_1E8]; this
0x180003ce6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003ceb  mov     rdi, [rbp+170h+var_1E8]
0x180003cef  lea     r8, aClsid; "CLSID\\"
0x180003cf6  mov     rdx, rsi
0x180003cf9  lea     rcx, [rbp+170h+SubKey]
0x180003cfd  call    cs:__imp__o_wcscpy_s
0x180003d03  mov     ecx, eax; int
0x180003d05  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003d0a  lea     r8, [rbp+170h+sz]
0x180003d11  mov     rdx, rsi
0x180003d14  lea     rcx, [rbp+170h+SubKey]
0x180003d18  call    cs:__imp__o_wcscat_s
0x180003d1e  mov     ecx, eax; int
0x180003d20  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003d25  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003d2c  mov     rdx, rsi
0x180003d2f  lea     rcx, [rbp+170h+SubKey]
0x180003d33  call    cs:__imp__o_wcscat_s
0x180003d39  mov     ecx, eax; int
0x180003d3b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003d40  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180003d44  mov     rdx, rdi; hKey
0x180003d47  lea     rcx, [rsp+270h+hKey]; this
0x180003d4c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180003d51  test    eax, eax
0x180003d53  jnz     short loc_180003DB9
0x180003d55  mov     rcx, [rsp+270h+hKey]; hKey
0x180003d5a  lea     rax, [rsp+270h+cSubKeys]
0x180003d5f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003d64  xor     r9d, r9d; lpReserved
0x180003d67  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003d6c  xor     r8d, r8d; lpcchClass
0x180003d6f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003d74  xor     edx, edx; lpClass
0x180003d76  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003d7b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180003d80  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003d85  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003d8a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180003d8f  call    cs:__imp_RegQueryInfoKeyW
0x180003d95  lea     rcx, [rsp+270h+hKey]; this
0x180003d9a  mov     ebx, eax
0x180003d9c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003da1  test    ebx, ebx
0x180003da3  jnz     short loc_180003DB9
0x180003da5  cmp     [rsp+270h+cSubKeys], r15d
0x180003daa  jnz     short loc_180003DB9
0x180003dac  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180003db0  lea     rcx, [rbp+170h+var_1E8]; this
0x180003db4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003db9  lea     rcx, [rsp+270h+hKey]; this
0x180003dbe  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003dc3  lea     rcx, [rbp+170h+var_1E8]; this
0x180003dc7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003dcc  lea     rcx, [rbp+170h+var_1D0]
0x180003dd0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003dd5  mov     edi, r15d
0x180003dd8  lea     rcx, [rsp+270h+var_208]
0x180003ddd  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x180003de2  mov     eax, edi
0x180003de4  mov     rcx, [rbp+170h+var_30]
0x180003deb  xor     rcx, rsp; StackCookie
0x180003dee  call    __security_check_cookie
0x180003df3  lea     r11, [rsp+270h+var_20]
0x180003dfb  mov     rbx, [r11+40h]
0x180003dff  mov     rsi, [r11+48h]
0x180003e03  mov     rsp, r11
0x180003e06  pop     r15
0x180003e08  pop     r14
0x180003e0a  pop     r12
0x180003e0c  pop     rdi
0x180003e0d  pop     rbp
0x180003e0e  retn
```
