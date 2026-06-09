# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180016d08`
- end: `0x180017043`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a02c`
- `0x18001ac64`
- `0x18001b620`

## callees

- `0x180001a34`
- `0x18000daec`
- `0x18000e234`
- `0x180015290`
- `0x180016a1c`
- `0x180016d08`
- `0x1800173a4`
- `0x1800186d0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180016e4d`
- `msvcrt!wcscat_s` at `0x180016e67`
- `msvcrt!wcscat_s` at `0x180016f49`
- `msvcrt!wcscat_s` at `0x180016f64`
- `msvcrt!wcscat_s` at `0x180016e4d`
- `msvcrt!wcscat_s` at `0x180016e67`
- `msvcrt!wcscat_s` at `0x180016f49`
- `msvcrt!wcscat_s` at `0x180016f64`
- `msvcrt!wcscpy_s` at `0x180016e33`
- `msvcrt!wcscpy_s` at `0x180016f2e`
- `msvcrt!wcscpy_s` at `0x180016e33`
- `msvcrt!wcscpy_s` at `0x180016f2e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016e17`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016e17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d90`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016ef2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016ef2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016fc3`

## string_xrefs

- `0x180016e28`: `CLSID\`
- `0x180016f20`: `CLSID\`

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
  LSTATUS v13; // ebx
  errno_t v14; // eax
  errno_t v15; // eax
  errno_t v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v23 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180016d08  mov     [rsp-8+arg_10], rbx
0x180016d0d  mov     [rsp-8+arg_18], rsi
0x180016d12  push    rbp
0x180016d13  push    rdi
0x180016d14  push    r12
0x180016d16  push    r14
0x180016d18  push    r15
0x180016d1a  lea     rbp, [rsp-150h]
0x180016d22  sub     rsp, 250h
0x180016d29  mov     rax, cs:__security_cookie
0x180016d30  xor     rax, rsp
0x180016d33  mov     [rbp+170h+var_30], rax
0x180016d3a  xor     r15d, r15d
0x180016d3d  xorps   xmm0, xmm0
0x180016d40  mov     [rsp+270h+var_208], r15
0x180016d45  mov     r14d, r8d
0x180016d48  mov     rbx, rdx
0x180016d4b  mov     rsi, rcx
0x180016d4e  movups  [rbp+170h+var_1C8], xmm0
0x180016d52  test    rdx, rdx
0x180016d55  jz      loc_180017009
0x180016d5b  lea     rdx, GUID_NULL
0x180016d62  call    InlineIsEqualGUID
0x180016d67  test    eax, eax
0x180016d69  jnz     loc_180017009
0x180016d6f  lea     rax, [rsp+270h+var_208]
0x180016d74  xor     edx, edx; pUnkOuter
0x180016d76  lea     r12d, [r15+1]
0x180016d7a  mov     [rsp+270h+ppv], rax; ppv
0x180016d7f  mov     r8d, r12d; dwClsContext
0x180016d82  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180016d89  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180016d90  call    cs:__imp_CoCreateInstance
0x180016d96  test    eax, eax
0x180016d98  js      loc_180017009
0x180016d9e  cmp     [rbx], r15d
0x180016da1  jz      short loc_180016E00
0x180016da3  mov     rax, [rbx+8]
0x180016da7  lea     r9, [rbp+170h+var_1C8]
0x180016dab  mov     rcx, [rsp+270h+var_208]
0x180016db0  mov     r8d, r12d
0x180016db3  mov     rdx, rsi
0x180016db6  movups  xmm0, xmmword ptr [rax]
0x180016db9  movdqu  [rbp+170h+var_1C8], xmm0
0x180016dbe  mov     rax, [rcx]
0x180016dc1  test    r14d, r14d
0x180016dc4  jz      short loc_180016DE6
0x180016dc6  cmp     [rbx], r12d
0x180016dc9  jnz     short loc_180016DD1
0x180016dcb  mov     rax, [rax+28h]
0x180016dcf  jmp     short loc_180016DD5
0x180016dd1  mov     rax, [rax+38h]
0x180016dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dda  mov     edi, eax
0x180016ddc  test    eax, eax
0x180016dde  js      loc_18001700C
0x180016de4  jmp     short loc_180016DFA
0x180016de6  cmp     [rbx], r12d
0x180016de9  jnz     short loc_180016DF1
0x180016deb  mov     rax, [rax+30h]
0x180016def  jmp     short loc_180016DF5
0x180016df1  mov     rax, [rax+40h]
0x180016df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dfa  add     rbx, 10h
0x180016dfe  jmp     short loc_180016D9E
0x180016e00  test    r14d, r14d
0x180016e03  jnz     loc_180017009
0x180016e09  lea     r8d, [r14+40h]; cchMax
0x180016e0d  mov     rcx, rsi; rguid
0x180016e10  lea     rdx, [rbp+170h+sz]; lpsz
0x180016e17  call    cs:__imp_StringFromGUID2
0x180016e1d  mov     esi, 80h
0x180016e22  mov     [rbp+170h+var_1D0], r15
0x180016e26  mov     edx, esi; SizeInWords
0x180016e28  lea     r8, aClsid; "CLSID\\"
0x180016e2f  lea     rcx, [rbp+170h+Destination]; Destination
0x180016e33  call    cs:__imp_wcscpy_s
0x180016e39  mov     ecx, eax; int
0x180016e3b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016e40  lea     r8, [rbp+170h+sz]; Source
0x180016e47  mov     edx, esi; SizeInWords
0x180016e49  lea     rcx, [rbp+170h+Destination]; Destination
0x180016e4d  call    cs:__imp_wcscat_s
0x180016e53  mov     ecx, eax; int
0x180016e55  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016e5a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180016e61  mov     edx, esi; SizeInWords
0x180016e63  lea     rcx, [rbp+170h+Destination]; Destination
0x180016e67  call    cs:__imp_wcscat_s
0x180016e6d  mov     ecx, eax; int
0x180016e6f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016e74  mov     rdi, 0FFFFFFFF80000000h
0x180016e7b  mov     [rbp+170h+var_1E0], r15
0x180016e7f  mov     r14d, 20019h
0x180016e85  mov     [rbp+170h+var_1E8], rdi
0x180016e89  mov     r9d, r14d; unsigned int
0x180016e8c  mov     [rbp+170h+var_1D8], r15
0x180016e90  mov     rdx, rdi; hKey
0x180016e93  mov     [rsp+270h+hKey], r15
0x180016e98  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180016e9c  mov     [rsp+270h+var_1F8], r15
0x180016ea1  lea     rcx, [rsp+270h+hKey]; this
0x180016ea6  mov     [rbp+170h+var_1F0], r15
0x180016eaa  mov     [rsp+270h+cSubKeys], r15d
0x180016eaf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016eb4  test    eax, eax
0x180016eb6  jnz     short loc_180016F20
0x180016eb8  mov     rcx, [rsp+270h+hKey]; hKey
0x180016ebd  lea     rax, [rsp+270h+cSubKeys]
0x180016ec2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016ec7  xor     r9d, r9d; lpReserved
0x180016eca  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016ecf  xor     r8d, r8d; lpcchClass
0x180016ed2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016ed7  xor     edx, edx; lpClass
0x180016ed9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016ede  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180016ee3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016ee8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180016eed  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180016ef2  call    cs:__imp_RegQueryInfoKeyW
0x180016ef8  lea     rcx, [rsp+270h+hKey]; this
0x180016efd  mov     ebx, eax
0x180016eff  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016f04  test    ebx, ebx
0x180016f06  jnz     short loc_180016F20
0x180016f08  cmp     [rsp+270h+cSubKeys], r15d
0x180016f0d  jnz     short loc_180016F20
0x180016f0f  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180016f13  lea     rcx, [rbp+170h+var_1E8]; this
0x180016f17  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180016f1c  mov     rdi, [rbp+170h+var_1E8]
0x180016f20  lea     r8, aClsid; "CLSID\\"
0x180016f27  mov     rdx, rsi; SizeInWords
0x180016f2a  lea     rcx, [rbp+170h+Destination]; Destination
0x180016f2e  call    cs:__imp_wcscpy_s
0x180016f34  mov     ecx, eax; int
0x180016f36  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016f3b  lea     r8, [rbp+170h+sz]; Source
0x180016f42  mov     rdx, rsi; SizeInWords
0x180016f45  lea     rcx, [rbp+170h+Destination]; Destination
0x180016f49  call    cs:__imp_wcscat_s
0x180016f4f  mov     ecx, eax; int
0x180016f51  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016f56  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180016f5d  mov     rdx, rsi; SizeInWords
0x180016f60  lea     rcx, [rbp+170h+Destination]; Destination
0x180016f64  call    cs:__imp_wcscat_s
0x180016f6a  mov     ecx, eax; int
0x180016f6c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016f71  mov     r9d, r14d; unsigned int
0x180016f74  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180016f78  mov     rdx, rdi; hKey
0x180016f7b  lea     rcx, [rsp+270h+hKey]; this
0x180016f80  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016f85  test    eax, eax
0x180016f87  jnz     short loc_180016FED
0x180016f89  mov     rcx, [rsp+270h+hKey]; hKey
0x180016f8e  lea     rax, [rsp+270h+cSubKeys]
0x180016f93  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016f98  xor     r9d, r9d; lpReserved
0x180016f9b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016fa0  xor     r8d, r8d; lpcchClass
0x180016fa3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016fa8  xor     edx, edx; lpClass
0x180016faa  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016faf  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180016fb4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016fb9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180016fbe  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180016fc3  call    cs:__imp_RegQueryInfoKeyW
0x180016fc9  lea     rcx, [rsp+270h+hKey]; this
0x180016fce  mov     ebx, eax
0x180016fd0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016fd5  test    ebx, ebx
0x180016fd7  jnz     short loc_180016FED
0x180016fd9  cmp     [rsp+270h+cSubKeys], r15d
0x180016fde  jnz     short loc_180016FED
0x180016fe0  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180016fe4  lea     rcx, [rbp+170h+var_1E8]; this
0x180016fe8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180016fed  lea     rcx, [rsp+270h+hKey]; this
0x180016ff2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016ff7  lea     rcx, [rbp+170h+var_1E8]; this
0x180016ffb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017000  lea     rcx, [rbp+170h+var_1D0]
0x180017004  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017009  mov     edi, r15d
0x18001700c  lea     rcx, [rsp+270h+var_208]
0x180017011  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017016  mov     eax, edi
0x180017018  mov     rcx, [rbp+170h+var_30]
0x18001701f  xor     rcx, rsp; StackCookie
0x180017022  call    __security_check_cookie
0x180017027  lea     r11, [rsp+270h+var_20]
0x18001702f  mov     rbx, [r11+40h]
0x180017033  mov     rsi, [r11+48h]
0x180017037  mov     rsp, r11
0x18001703a  pop     r15
0x18001703c  pop     r14
0x18001703e  pop     r12
0x180017040  pop     rdi
0x180017041  pop     rbp
0x180017042  retn
```
