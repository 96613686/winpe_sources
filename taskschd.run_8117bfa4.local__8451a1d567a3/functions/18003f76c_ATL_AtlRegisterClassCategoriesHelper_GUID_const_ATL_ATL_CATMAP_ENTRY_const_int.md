# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18003f76c`
- end: `0x18003fa96`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `810`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003ff90`
- `0x18004003c`

## callees

- `0x180001880`
- `0x180011934`
- `0x18002a6c0`
- `0x18003f468`
- `0x18003f76c`
- `0x18003fd14`
- `0x18003fd48`
- `0x18003ff2c`
- `0x1800400fc`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18003f8a3`
- `msvcrt!wcscpy_s` at `0x18003f98d`
- `msvcrt!wcscpy_s` at `0x18003f8a3`
- `msvcrt!wcscpy_s` at `0x18003f98d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f94b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003fa0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f94b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003fa0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7f4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f881`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f881`

## string_xrefs

- `0x18003f898`: `CLSID\`
- `0x18003f97f`: `CLSID\`

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
  unsigned int v15; // r9d
  LSTATUS v16; // ebx
  errno_t v17; // eax
  unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r9
  unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // r9
  unsigned int v22; // r9d
  LSTATUS v23; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v28[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v30; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v30 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v30 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v30);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v30);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v30);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v30);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v29 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v28[1] = 0;
      v28[0] = 0xFFFFFFFF80000000uLL;
      v28[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, v15) )
      {
        v16 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v16 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v28, Destination);
          v14 = (HKEY)v28[0];
        }
      }
      v17 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v17);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v18, (unsigned __int64)sz, v19);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v20, (unsigned __int64)L"\\Implemented Categories", v21);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, Destination, v22) )
      {
        v23 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v23 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v28, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v28);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
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
0x18003f76c  mov     [rsp-8+arg_10], rbx
0x18003f771  mov     [rsp-8+arg_18], rsi
0x18003f776  push    rbp
0x18003f777  push    rdi
0x18003f778  push    r12
0x18003f77a  push    r14
0x18003f77c  push    r15
0x18003f77e  lea     rbp, [rsp-150h]
0x18003f786  sub     rsp, 250h
0x18003f78d  mov     rax, cs:__security_cookie
0x18003f794  xor     rax, rsp
0x18003f797  mov     [rbp+170h+var_30], rax
0x18003f79e  xor     r15d, r15d
0x18003f7a1  xorps   xmm0, xmm0
0x18003f7a4  mov     [rsp+270h+var_208], r15
0x18003f7a9  mov     r14d, r8d
0x18003f7ac  mov     rbx, rdx
0x18003f7af  mov     rsi, rcx
0x18003f7b2  movups  [rbp+170h+var_1C8], xmm0
0x18003f7b6  test    rdx, rdx
0x18003f7b9  jz      loc_18003FA5B
0x18003f7bf  lea     rdx, GUID_NULL; struct _GUID *
0x18003f7c6  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18003f7cb  test    eax, eax
0x18003f7cd  jnz     loc_18003FA5B
0x18003f7d3  lea     rax, [rsp+270h+var_208]
0x18003f7d8  xor     edx, edx; pUnkOuter
0x18003f7da  lea     r12d, [r15+1]
0x18003f7de  mov     [rsp+270h+ppv], rax; ppv
0x18003f7e3  mov     r8d, r12d; dwClsContext
0x18003f7e6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18003f7ed  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18003f7f4  call    cs:__imp_CoCreateInstance
0x18003f7fb  nop     dword ptr [rax+rax+00h]
0x18003f800  test    eax, eax
0x18003f802  js      loc_18003FA5B
0x18003f808  cmp     [rbx], r15d
0x18003f80b  jz      short loc_18003F86A
0x18003f80d  mov     rax, [rbx+8]
0x18003f811  lea     r9, [rbp+170h+var_1C8]
0x18003f815  mov     rcx, [rsp+270h+var_208]
0x18003f81a  mov     r8d, r12d
0x18003f81d  mov     rdx, rsi
0x18003f820  movups  xmm0, xmmword ptr [rax]
0x18003f823  movdqu  [rbp+170h+var_1C8], xmm0
0x18003f828  mov     rax, [rcx]
0x18003f82b  test    r14d, r14d
0x18003f82e  jz      short loc_18003F850
0x18003f830  cmp     [rbx], r12d
0x18003f833  jnz     short loc_18003F83B
0x18003f835  mov     rax, [rax+28h]
0x18003f839  jmp     short loc_18003F83F
0x18003f83b  mov     rax, [rax+38h]
0x18003f83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f844  mov     edi, eax
0x18003f846  test    eax, eax
0x18003f848  js      loc_18003FA5E
0x18003f84e  jmp     short loc_18003F864
0x18003f850  cmp     [rbx], r12d
0x18003f853  jnz     short loc_18003F85B
0x18003f855  mov     rax, [rax+30h]
0x18003f859  jmp     short loc_18003F85F
0x18003f85b  mov     rax, [rax+40h]
0x18003f85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f864  add     rbx, 10h
0x18003f868  jmp     short loc_18003F808
0x18003f86a  test    r14d, r14d
0x18003f86d  jnz     loc_18003FA5B
0x18003f873  lea     r8d, [r14+40h]; cchMax
0x18003f877  mov     rcx, rsi; rguid
0x18003f87a  lea     rdx, [rbp+170h+sz]; lpsz
0x18003f881  call    cs:__imp_StringFromGUID2
0x18003f888  nop     dword ptr [rax+rax+00h]
0x18003f88d  mov     esi, 80h
0x18003f892  mov     [rbp+170h+var_1D0], r15
0x18003f896  mov     edx, esi; SizeInWords
0x18003f898  lea     r8, aClsid; "CLSID\\"
0x18003f89f  lea     rcx, [rbp+170h+Destination]; Destination
0x18003f8a3  call    cs:__imp_wcscpy_s
0x18003f8aa  nop     dword ptr [rax+rax+00h]
0x18003f8af  mov     ecx, eax; int
0x18003f8b1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003f8b6  lea     r8, [rbp+170h+sz]; unsigned __int64
0x18003f8bd  lea     rcx, [rbp+170h+Destination]; this
0x18003f8c1  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18003f8c6  lea     r8, aRequiredCatego; "\\Required Categories"
0x18003f8cd  lea     rcx, [rbp+170h+Destination]; this
0x18003f8d1  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18003f8d6  mov     rdi, 0FFFFFFFF80000000h
0x18003f8dd  mov     [rbp+170h+var_1E0], r15
0x18003f8e1  mov     rdx, rdi; hKey
0x18003f8e4  mov     [rbp+170h+var_1E8], rdi
0x18003f8e8  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18003f8ec  mov     [rbp+170h+var_1D8], r15
0x18003f8f0  lea     rcx, [rsp+270h+hKey]; this
0x18003f8f5  mov     [rsp+270h+hKey], r15
0x18003f8fa  mov     [rsp+270h+var_1F8], r15
0x18003f8ff  mov     [rbp+170h+var_1F0], r15
0x18003f903  mov     [rsp+270h+cSubKeys], r15d
0x18003f908  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f90d  test    eax, eax
0x18003f90f  jnz     short loc_18003F97F
0x18003f911  mov     rcx, [rsp+270h+hKey]; hKey
0x18003f916  lea     rax, [rsp+270h+cSubKeys]
0x18003f91b  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003f920  xor     r9d, r9d; lpReserved
0x18003f923  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003f928  xor     r8d, r8d; lpcchClass
0x18003f92b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003f930  xor     edx, edx; lpClass
0x18003f932  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18003f937  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18003f93c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003f941  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003f946  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18003f94b  call    cs:__imp_RegQueryInfoKeyW
0x18003f952  nop     dword ptr [rax+rax+00h]
0x18003f957  lea     rcx, [rsp+270h+hKey]; this
0x18003f95c  mov     ebx, eax
0x18003f95e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f963  test    ebx, ebx
0x18003f965  jnz     short loc_18003F97F
0x18003f967  cmp     [rsp+270h+cSubKeys], r15d
0x18003f96c  jnz     short loc_18003F97F
0x18003f96e  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18003f972  lea     rcx, [rbp+170h+var_1E8]; this
0x18003f976  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18003f97b  mov     rdi, [rbp+170h+var_1E8]
0x18003f97f  lea     r8, aClsid; "CLSID\\"
0x18003f986  mov     rdx, rsi; SizeInWords
0x18003f989  lea     rcx, [rbp+170h+Destination]; Destination
0x18003f98d  call    cs:__imp_wcscpy_s
0x18003f994  nop     dword ptr [rax+rax+00h]
0x18003f999  mov     ecx, eax; int
0x18003f99b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003f9a0  lea     r8, [rbp+170h+sz]; unsigned __int64
0x18003f9a7  lea     rcx, [rbp+170h+Destination]; this
0x18003f9ab  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18003f9b0  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18003f9b7  lea     rcx, [rbp+170h+Destination]; this
0x18003f9bb  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18003f9c0  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18003f9c4  mov     rdx, rdi; hKey
0x18003f9c7  lea     rcx, [rsp+270h+hKey]; this
0x18003f9cc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f9d1  test    eax, eax
0x18003f9d3  jnz     short loc_18003FA3F
0x18003f9d5  mov     rcx, [rsp+270h+hKey]; hKey
0x18003f9da  lea     rax, [rsp+270h+cSubKeys]
0x18003f9df  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003f9e4  xor     r9d, r9d; lpReserved
0x18003f9e7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003f9ec  xor     r8d, r8d; lpcchClass
0x18003f9ef  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003f9f4  xor     edx, edx; lpClass
0x18003f9f6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18003f9fb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18003fa00  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003fa05  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003fa0a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18003fa0f  call    cs:__imp_RegQueryInfoKeyW
0x18003fa16  nop     dword ptr [rax+rax+00h]
0x18003fa1b  lea     rcx, [rsp+270h+hKey]; this
0x18003fa20  mov     ebx, eax
0x18003fa22  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003fa27  test    ebx, ebx
0x18003fa29  jnz     short loc_18003FA3F
0x18003fa2b  cmp     [rsp+270h+cSubKeys], r15d
0x18003fa30  jnz     short loc_18003FA3F
0x18003fa32  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18003fa36  lea     rcx, [rbp+170h+var_1E8]; this
0x18003fa3a  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18003fa3f  lea     rcx, [rsp+270h+hKey]; this
0x18003fa44  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003fa49  lea     rcx, [rbp+170h+var_1E8]; this
0x18003fa4d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003fa52  lea     rcx, [rbp+170h+var_1D0]
0x18003fa56  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003fa5b  mov     edi, r15d
0x18003fa5e  lea     rcx, [rsp+270h+var_208]
0x18003fa63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003fa68  mov     eax, edi
0x18003fa6a  mov     rcx, [rbp+170h+var_30]
0x18003fa71  xor     rcx, rsp; StackCookie
0x18003fa74  call    __security_check_cookie
0x18003fa79  lea     r11, [rsp+270h+var_20]
0x18003fa81  mov     rbx, [r11+40h]
0x18003fa85  mov     rsi, [r11+48h]
0x18003fa89  mov     rsp, r11
0x18003fa8c  pop     r15
0x18003fa8e  pop     r14
0x18003fa90  pop     r12
0x18003fa92  pop     rdi
0x18003fa93  pop     rbp
0x18003fa94  retn
```
