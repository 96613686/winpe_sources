# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18003c3b0`
- end: `0x18003c6df`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `815`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003cb6c`
- `0x18003cc14`

## callees

- `0x1800017f0`
- `0x180010db0`
- `0x180028a50`
- `0x18003c0d8`
- `0x18003c3b0`
- `0x18003c930`
- `0x18003c95c`
- `0x18003cb0c`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003c4f5`
- `msvcrt!wcscat_s` at `0x18003c50f`
- `msvcrt!wcscat_s` at `0x18003c5e8`
- `msvcrt!wcscat_s` at `0x18003c603`
- `msvcrt!wcscat_s` at `0x18003c4f5`
- `msvcrt!wcscat_s` at `0x18003c50f`
- `msvcrt!wcscat_s` at `0x18003c5e8`
- `msvcrt!wcscat_s` at `0x18003c603`
- `msvcrt!wcscpy_s` at `0x18003c4db`
- `msvcrt!wcscpy_s` at `0x18003c5cd`
- `msvcrt!wcscpy_s` at `0x18003c4db`
- `msvcrt!wcscpy_s` at `0x18003c5cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c591`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c65f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c591`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c65f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c438`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c438`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c4bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c4bf`

## string_xrefs

- `0x18003c4d0`: `CLSID\`
- `0x18003c5bf`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  errno_t v10; // eax
  errno_t v11; // eax
  HKEY v12; // rdi
  unsigned int v13; // r9d
  LSTATUS v14; // ebx
  errno_t v15; // eax
  errno_t v16; // eax
  errno_t v17; // eax
  unsigned int v18; // r9d
  LSTATUS v19; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
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
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, v13) )
      {
        v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v14 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
          v12 = (HKEY)v24[0];
        }
      }
      v15 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v16);
      v17 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v17);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, v18) )
      {
        v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v19 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18003c3b0  mov     [rsp-8+arg_10], rbx
0x18003c3b5  mov     [rsp-8+arg_18], rsi
0x18003c3ba  push    rbp
0x18003c3bb  push    rdi
0x18003c3bc  push    r12
0x18003c3be  push    r14
0x18003c3c0  push    r15
0x18003c3c2  lea     rbp, [rsp-150h]
0x18003c3ca  sub     rsp, 250h
0x18003c3d1  mov     rax, cs:__security_cookie
0x18003c3d8  xor     rax, rsp
0x18003c3db  mov     [rbp+170h+var_30], rax
0x18003c3e2  xor     r15d, r15d
0x18003c3e5  xorps   xmm0, xmm0
0x18003c3e8  mov     [rsp+270h+var_208], r15
0x18003c3ed  mov     r14d, r8d
0x18003c3f0  mov     rbx, rdx
0x18003c3f3  mov     rsi, rcx
0x18003c3f6  movups  [rbp+170h+var_1C8], xmm0
0x18003c3fa  test    rdx, rdx
0x18003c3fd  jz      loc_18003C6A5
0x18003c403  lea     rdx, GUID_NULL; struct _GUID *
0x18003c40a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18003c40f  test    eax, eax
0x18003c411  jnz     loc_18003C6A5
0x18003c417  lea     rax, [rsp+270h+var_208]
0x18003c41c  xor     edx, edx; pUnkOuter
0x18003c41e  lea     r12d, [r15+1]
0x18003c422  mov     [rsp+270h+ppv], rax; ppv
0x18003c427  mov     r8d, r12d; dwClsContext
0x18003c42a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18003c431  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18003c438  call    cs:__imp_CoCreateInstance
0x18003c43e  test    eax, eax
0x18003c440  js      loc_18003C6A5
0x18003c446  cmp     [rbx], r15d
0x18003c449  jz      short loc_18003C4A8
0x18003c44b  mov     rax, [rbx+8]
0x18003c44f  lea     r9, [rbp+170h+var_1C8]
0x18003c453  mov     rcx, [rsp+270h+var_208]
0x18003c458  mov     r8d, r12d
0x18003c45b  mov     rdx, rsi
0x18003c45e  movups  xmm0, xmmword ptr [rax]
0x18003c461  movdqu  [rbp+170h+var_1C8], xmm0
0x18003c466  mov     rax, [rcx]
0x18003c469  test    r14d, r14d
0x18003c46c  jz      short loc_18003C48E
0x18003c46e  cmp     [rbx], r12d
0x18003c471  jnz     short loc_18003C479
0x18003c473  mov     rax, [rax+28h]
0x18003c477  jmp     short loc_18003C47D
0x18003c479  mov     rax, [rax+38h]
0x18003c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c482  mov     edi, eax
0x18003c484  test    eax, eax
0x18003c486  js      loc_18003C6A8
0x18003c48c  jmp     short loc_18003C4A2
0x18003c48e  cmp     [rbx], r12d
0x18003c491  jnz     short loc_18003C499
0x18003c493  mov     rax, [rax+30h]
0x18003c497  jmp     short loc_18003C49D
0x18003c499  mov     rax, [rax+40h]
0x18003c49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4a2  add     rbx, 10h
0x18003c4a6  jmp     short loc_18003C446
0x18003c4a8  test    r14d, r14d
0x18003c4ab  jnz     loc_18003C6A5
0x18003c4b1  lea     r8d, [r14+40h]; cchMax
0x18003c4b5  mov     rcx, rsi; rguid
0x18003c4b8  lea     rdx, [rbp+170h+sz]; lpsz
0x18003c4bf  call    cs:__imp_StringFromGUID2
0x18003c4c5  mov     esi, 80h
0x18003c4ca  mov     [rbp+170h+var_1D0], r15
0x18003c4ce  mov     edx, esi; SizeInWords
0x18003c4d0  lea     r8, aClsid; "CLSID\\"
0x18003c4d7  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c4db  call    cs:__imp_wcscpy_s
0x18003c4e1  mov     ecx, eax; int
0x18003c4e3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c4e8  lea     r8, [rbp+170h+sz]; Source
0x18003c4ef  mov     edx, esi; SizeInWords
0x18003c4f1  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c4f5  call    cs:__imp_wcscat_s
0x18003c4fb  mov     ecx, eax; int
0x18003c4fd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c502  lea     r8, aRequiredCatego; "\\Required Categories"
0x18003c509  mov     edx, esi; SizeInWords
0x18003c50b  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c50f  call    cs:__imp_wcscat_s
0x18003c515  mov     ecx, eax; int
0x18003c517  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c51c  mov     rdi, 0FFFFFFFF80000000h
0x18003c523  mov     [rbp+170h+var_1E0], r15
0x18003c527  mov     rdx, rdi; hKey
0x18003c52a  mov     [rbp+170h+var_1E8], rdi
0x18003c52e  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18003c532  mov     [rbp+170h+var_1D8], r15
0x18003c536  lea     rcx, [rsp+270h+hKey]; this
0x18003c53b  mov     [rsp+270h+hKey], r15
0x18003c540  mov     [rsp+270h+var_1F8], r15
0x18003c545  mov     [rbp+170h+var_1F0], r15
0x18003c549  mov     [rsp+270h+cSubKeys], r15d
0x18003c54e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003c553  test    eax, eax
0x18003c555  jnz     short loc_18003C5BF
0x18003c557  mov     rcx, [rsp+270h+hKey]; hKey
0x18003c55c  lea     rax, [rsp+270h+cSubKeys]
0x18003c561  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003c566  xor     r9d, r9d; lpReserved
0x18003c569  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003c56e  xor     r8d, r8d; lpcchClass
0x18003c571  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003c576  xor     edx, edx; lpClass
0x18003c578  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18003c57d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18003c582  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003c587  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003c58c  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18003c591  call    cs:__imp_RegQueryInfoKeyW
0x18003c597  lea     rcx, [rsp+270h+hKey]; this
0x18003c59c  mov     ebx, eax
0x18003c59e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003c5a3  test    ebx, ebx
0x18003c5a5  jnz     short loc_18003C5BF
0x18003c5a7  cmp     [rsp+270h+cSubKeys], r15d
0x18003c5ac  jnz     short loc_18003C5BF
0x18003c5ae  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18003c5b2  lea     rcx, [rbp+170h+var_1E8]; this
0x18003c5b6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18003c5bb  mov     rdi, [rbp+170h+var_1E8]
0x18003c5bf  lea     r8, aClsid; "CLSID\\"
0x18003c5c6  mov     rdx, rsi; SizeInWords
0x18003c5c9  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c5cd  call    cs:__imp_wcscpy_s
0x18003c5d3  mov     ecx, eax; int
0x18003c5d5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c5da  lea     r8, [rbp+170h+sz]; Source
0x18003c5e1  mov     rdx, rsi; SizeInWords
0x18003c5e4  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c5e8  call    cs:__imp_wcscat_s
0x18003c5ee  mov     ecx, eax; int
0x18003c5f0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c5f5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18003c5fc  mov     rdx, rsi; SizeInWords
0x18003c5ff  lea     rcx, [rbp+170h+Destination]; Destination
0x18003c603  call    cs:__imp_wcscat_s
0x18003c609  mov     ecx, eax; int
0x18003c60b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003c610  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18003c614  mov     rdx, rdi; hKey
0x18003c617  lea     rcx, [rsp+270h+hKey]; this
0x18003c61c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003c621  test    eax, eax
0x18003c623  jnz     short loc_18003C689
0x18003c625  mov     rcx, [rsp+270h+hKey]; hKey
0x18003c62a  lea     rax, [rsp+270h+cSubKeys]
0x18003c62f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003c634  xor     r9d, r9d; lpReserved
0x18003c637  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003c63c  xor     r8d, r8d; lpcchClass
0x18003c63f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003c644  xor     edx, edx; lpClass
0x18003c646  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18003c64b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18003c650  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003c655  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003c65a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18003c65f  call    cs:__imp_RegQueryInfoKeyW
0x18003c665  lea     rcx, [rsp+270h+hKey]; this
0x18003c66a  mov     ebx, eax
0x18003c66c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003c671  test    ebx, ebx
0x18003c673  jnz     short loc_18003C689
0x18003c675  cmp     [rsp+270h+cSubKeys], r15d
0x18003c67a  jnz     short loc_18003C689
0x18003c67c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18003c680  lea     rcx, [rbp+170h+var_1E8]; this
0x18003c684  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18003c689  lea     rcx, [rsp+270h+hKey]; this
0x18003c68e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003c693  lea     rcx, [rbp+170h+var_1E8]; this
0x18003c697  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003c69c  lea     rcx, [rbp+170h+var_1D0]
0x18003c6a0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003c6a5  mov     edi, r15d
0x18003c6a8  lea     rcx, [rsp+270h+var_208]
0x18003c6ad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c6b2  mov     eax, edi
0x18003c6b4  mov     rcx, [rbp+170h+var_30]
0x18003c6bb  xor     rcx, rsp; StackCookie
0x18003c6be  call    __security_check_cookie
0x18003c6c3  lea     r11, [rsp+270h+var_20]
0x18003c6cb  mov     rbx, [r11+40h]
0x18003c6cf  mov     rsi, [r11+48h]
0x18003c6d3  mov     rsp, r11
0x18003c6d6  pop     r15
0x18003c6d8  pop     r14
0x18003c6da  pop     r12
0x18003c6dc  pop     rdi
0x18003c6dd  pop     rbp
0x18003c6de  retn
```
