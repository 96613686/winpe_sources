# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800039fc`
- end: `0x180003d32`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `822`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004e70`
- `0x180005834`

## callees

- `0x180002ae8`
- `0x180002b7c`
- `0x1800037ac`
- `0x1800039fc`
- `0x1800041b0`
- `0x1800041e0`
- `0x180004754`
- `0x180005c64`
- `0x180005e40`
- `0x18001e9f0`
- `0x180020010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003b33`
- `msvcrt!wcscpy_s` at `0x180003c26`
- `msvcrt!wcscpy_s` at `0x180003b33`
- `msvcrt!wcscpy_s` at `0x180003c26`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003be4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003cab`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003be4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003cab`
- `ole32!StringFromGUID2` at `0x180003b11`
- `ole32!StringFromGUID2` at `0x180003b11`
- `ole32!CoCreateInstance` at `0x180003a84`
- `ole32!CoCreateInstance` at `0x180003a84`

## string_xrefs

- `0x180003b28`: `CLSID\`
- `0x180003c18`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r9
  HKEY v14; // rdi
  LSTATUS v15; // ebx
  errno_t v16; // eax
  unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r9
  LSTATUS v21; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v28 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v28);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v28);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v27 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v26[1] = 0;
      v26[0] = 0xFFFFFFFF80000000uLL;
      v26[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
          v14 = (HKEY)v26[0];
        }
      }
      v16 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v17, (unsigned __int64)sz, v18);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v19, (unsigned __int64)L"\\Implemented Categories", v20);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, Destination, 0x20019u) )
      {
        v21 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v21 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v26);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
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
0x1800039fc  mov     [rsp-8+arg_10], rbx
0x180003a01  mov     [rsp-8+arg_18], rsi
0x180003a06  push    rbp
0x180003a07  push    rdi
0x180003a08  push    r12
0x180003a0a  push    r14
0x180003a0c  push    r15
0x180003a0e  lea     rbp, [rsp-150h]
0x180003a16  sub     rsp, 250h
0x180003a1d  mov     rax, cs:__security_cookie
0x180003a24  xor     rax, rsp
0x180003a27  mov     [rbp+170h+var_30], rax
0x180003a2e  xor     r15d, r15d
0x180003a31  xorps   xmm0, xmm0
0x180003a34  mov     [rsp+270h+var_208], r15
0x180003a39  mov     r14d, r8d
0x180003a3c  mov     rbx, rdx
0x180003a3f  mov     rsi, rcx
0x180003a42  movups  [rbp+170h+var_1C8], xmm0
0x180003a46  test    rdx, rdx
0x180003a49  jz      loc_180003CF7
0x180003a4f  lea     rdx, GUID_NULL
0x180003a56  call    InlineIsEqualGUID
0x180003a5b  test    eax, eax
0x180003a5d  jnz     loc_180003CF7
0x180003a63  lea     rax, [rsp+270h+var_208]
0x180003a68  xor     edx, edx; pUnkOuter
0x180003a6a  lea     r12d, [r15+1]
0x180003a6e  mov     [rsp+270h+ppv], rax; ppv
0x180003a73  mov     r8d, r12d; dwClsContext
0x180003a76  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003a7d  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003a84  call    cs:__imp_CoCreateInstance
0x180003a8b  nop     dword ptr [rax+rax+00h]
0x180003a90  test    eax, eax
0x180003a92  js      loc_180003CF7
0x180003a98  cmp     [rbx], r15d
0x180003a9b  jz      short loc_180003AFA
0x180003a9d  mov     rax, [rbx+8]
0x180003aa1  lea     r9, [rbp+170h+var_1C8]
0x180003aa5  mov     rcx, [rsp+270h+var_208]
0x180003aaa  mov     r8d, r12d
0x180003aad  mov     rdx, rsi
0x180003ab0  movups  xmm0, xmmword ptr [rax]
0x180003ab3  movdqu  [rbp+170h+var_1C8], xmm0
0x180003ab8  mov     rax, [rcx]
0x180003abb  test    r14d, r14d
0x180003abe  jz      short loc_180003AE0
0x180003ac0  cmp     [rbx], r12d
0x180003ac3  jnz     short loc_180003ACB
0x180003ac5  mov     rax, [rax+28h]
0x180003ac9  jmp     short loc_180003ACF
0x180003acb  mov     rax, [rax+38h]
0x180003acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad4  mov     edi, eax
0x180003ad6  test    eax, eax
0x180003ad8  js      loc_180003CFA
0x180003ade  jmp     short loc_180003AF4
0x180003ae0  cmp     [rbx], r12d
0x180003ae3  jnz     short loc_180003AEB
0x180003ae5  mov     rax, [rax+30h]
0x180003ae9  jmp     short loc_180003AEF
0x180003aeb  mov     rax, [rax+40h]
0x180003aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af4  add     rbx, 10h
0x180003af8  jmp     short loc_180003A98
0x180003afa  test    r14d, r14d
0x180003afd  jnz     loc_180003CF7
0x180003b03  lea     r8d, [r14+40h]; cchMax
0x180003b07  mov     rcx, rsi; rguid
0x180003b0a  lea     rdx, [rbp+170h+sz]; lpsz
0x180003b11  call    cs:__imp_StringFromGUID2
0x180003b18  nop     dword ptr [rax+rax+00h]
0x180003b1d  mov     esi, 80h
0x180003b22  mov     [rbp+170h+var_1D0], r15
0x180003b26  mov     edx, esi; SizeInWords
0x180003b28  lea     r8, aClsid; "CLSID\\"
0x180003b2f  lea     rcx, [rbp+170h+Destination]; Destination
0x180003b33  call    cs:__imp_wcscpy_s
0x180003b3a  nop     dword ptr [rax+rax+00h]
0x180003b3f  mov     ecx, eax; int
0x180003b41  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003b46  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180003b4d  lea     rcx, [rbp+170h+Destination]; this
0x180003b51  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180003b56  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003b5d  lea     rcx, [rbp+170h+Destination]; this
0x180003b61  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180003b66  mov     rdi, 0FFFFFFFF80000000h
0x180003b6d  mov     [rbp+170h+var_1E0], r15
0x180003b71  mov     r14d, 20019h
0x180003b77  mov     [rbp+170h+var_1E8], rdi
0x180003b7b  mov     r9d, r14d; unsigned int
0x180003b7e  mov     [rbp+170h+var_1D8], r15
0x180003b82  mov     rdx, rdi; hKey
0x180003b85  mov     [rsp+270h+hKey], r15
0x180003b8a  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180003b8e  mov     [rsp+270h+var_1F8], r15
0x180003b93  lea     rcx, [rsp+270h+hKey]; this
0x180003b98  mov     [rbp+170h+var_1F0], r15
0x180003b9c  mov     [rsp+270h+cSubKeys], r15d
0x180003ba1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180003ba6  test    eax, eax
0x180003ba8  jnz     short loc_180003C18
0x180003baa  mov     rcx, [rsp+270h+hKey]; hKey
0x180003baf  lea     rax, [rsp+270h+cSubKeys]
0x180003bb4  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003bb9  xor     r9d, r9d; lpReserved
0x180003bbc  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003bc1  xor     r8d, r8d; lpcchClass
0x180003bc4  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003bc9  xor     edx, edx; lpClass
0x180003bcb  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003bd0  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180003bd5  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003bda  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003bdf  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180003be4  call    cs:__imp_RegQueryInfoKeyW
0x180003beb  nop     dword ptr [rax+rax+00h]
0x180003bf0  lea     rcx, [rsp+270h+hKey]; this
0x180003bf5  mov     ebx, eax
0x180003bf7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003bfc  test    ebx, ebx
0x180003bfe  jnz     short loc_180003C18
0x180003c00  cmp     [rsp+270h+cSubKeys], r15d
0x180003c05  jnz     short loc_180003C18
0x180003c07  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180003c0b  lea     rcx, [rbp+170h+var_1E8]; this
0x180003c0f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003c14  mov     rdi, [rbp+170h+var_1E8]
0x180003c18  lea     r8, aClsid; "CLSID\\"
0x180003c1f  mov     rdx, rsi; SizeInWords
0x180003c22  lea     rcx, [rbp+170h+Destination]; Destination
0x180003c26  call    cs:__imp_wcscpy_s
0x180003c2d  nop     dword ptr [rax+rax+00h]
0x180003c32  mov     ecx, eax; int
0x180003c34  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003c39  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180003c40  lea     rcx, [rbp+170h+Destination]; this
0x180003c44  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180003c49  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003c50  lea     rcx, [rbp+170h+Destination]; this
0x180003c54  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180003c59  mov     r9d, r14d; unsigned int
0x180003c5c  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180003c60  mov     rdx, rdi; hKey
0x180003c63  lea     rcx, [rsp+270h+hKey]; this
0x180003c68  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180003c6d  test    eax, eax
0x180003c6f  jnz     short loc_180003CDB
0x180003c71  mov     rcx, [rsp+270h+hKey]; hKey
0x180003c76  lea     rax, [rsp+270h+cSubKeys]
0x180003c7b  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003c80  xor     r9d, r9d; lpReserved
0x180003c83  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003c88  xor     r8d, r8d; lpcchClass
0x180003c8b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003c90  xor     edx, edx; lpClass
0x180003c92  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003c97  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180003c9c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003ca1  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003ca6  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180003cab  call    cs:__imp_RegQueryInfoKeyW
0x180003cb2  nop     dword ptr [rax+rax+00h]
0x180003cb7  lea     rcx, [rsp+270h+hKey]; this
0x180003cbc  mov     ebx, eax
0x180003cbe  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003cc3  test    ebx, ebx
0x180003cc5  jnz     short loc_180003CDB
0x180003cc7  cmp     [rsp+270h+cSubKeys], r15d
0x180003ccc  jnz     short loc_180003CDB
0x180003cce  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180003cd2  lea     rcx, [rbp+170h+var_1E8]; this
0x180003cd6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003cdb  lea     rcx, [rsp+270h+hKey]; this
0x180003ce0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003ce5  lea     rcx, [rbp+170h+var_1E8]; this
0x180003ce9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180003cee  lea     rcx, [rbp+170h+var_1D0]
0x180003cf2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003cf7  mov     edi, r15d
0x180003cfa  lea     rcx, [rsp+270h+var_208]
0x180003cff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003d04  mov     eax, edi
0x180003d06  mov     rcx, [rbp+170h+var_30]
0x180003d0d  xor     rcx, rsp; StackCookie
0x180003d10  call    __security_check_cookie
0x180003d15  lea     r11, [rsp+270h+var_20]
0x180003d1d  mov     rbx, [r11+40h]
0x180003d21  mov     rsi, [r11+48h]
0x180003d25  mov     rsp, r11
0x180003d28  pop     r15
0x180003d2a  pop     r14
0x180003d2c  pop     r12
0x180003d2e  pop     rdi
0x180003d2f  pop     rbp
0x180003d30  retn
```
