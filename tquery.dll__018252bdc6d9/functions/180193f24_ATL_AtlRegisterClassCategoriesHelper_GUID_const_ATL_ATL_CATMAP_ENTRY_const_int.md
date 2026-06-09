# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180193f24`
- end: `0x18019425f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180198ab0`
- `0x18019a3c0`
- `0x18019b020`

## callees

- `0x1800601c0`
- `0x1800bd068`
- `0x180176e60`
- `0x180188d90`
- `0x180192700`
- `0x180193f24`
- `0x180194384`
- `0x180195180`
- `0x180197da4`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194069`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194083`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194165`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194180`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194069`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194083`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194165`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180194180`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18019404f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18019414a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18019404f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18019414a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180193fac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180193fac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180194033`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180194033`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18019410e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801941df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18019410e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801941df`

## string_xrefs

- `0x180194044`: `CLSID\`
- `0x18019413c`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
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
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180193f24  mov     [rsp-8+arg_10], rbx
0x180193f29  mov     [rsp-8+arg_18], rsi
0x180193f2e  push    rbp
0x180193f2f  push    rdi
0x180193f30  push    r12
0x180193f32  push    r14
0x180193f34  push    r15
0x180193f36  lea     rbp, [rsp-150h]
0x180193f3e  sub     rsp, 250h
0x180193f45  mov     rax, cs:__security_cookie
0x180193f4c  xor     rax, rsp
0x180193f4f  mov     [rbp+170h+var_30], rax
0x180193f56  xor     r15d, r15d
0x180193f59  xorps   xmm0, xmm0
0x180193f5c  mov     [rsp+270h+var_208], r15
0x180193f61  mov     r14d, r8d
0x180193f64  mov     rbx, rdx
0x180193f67  mov     rsi, rcx
0x180193f6a  movups  [rbp+170h+var_1C8], xmm0
0x180193f6e  test    rdx, rdx
0x180193f71  jz      loc_180194225
0x180193f77  lea     rdx, GUID_NULL
0x180193f7e  call    InlineIsEqualGUID
0x180193f83  test    eax, eax
0x180193f85  jnz     loc_180194225
0x180193f8b  lea     rax, [rsp+270h+var_208]
0x180193f90  xor     edx, edx; pUnkOuter
0x180193f92  lea     r12d, [r15+1]
0x180193f96  mov     [rsp+270h+ppv], rax; ppv
0x180193f9b  mov     r8d, r12d; dwClsContext
0x180193f9e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180193fa5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180193fac  call    cs:__imp_CoCreateInstance
0x180193fb2  test    eax, eax
0x180193fb4  js      loc_180194225
0x180193fba  cmp     [rbx], r15d
0x180193fbd  jz      short loc_18019401C
0x180193fbf  mov     rax, [rbx+8]
0x180193fc3  lea     r9, [rbp+170h+var_1C8]
0x180193fc7  mov     rcx, [rsp+270h+var_208]
0x180193fcc  mov     r8d, r12d
0x180193fcf  mov     rdx, rsi
0x180193fd2  movups  xmm0, xmmword ptr [rax]
0x180193fd5  movdqu  [rbp+170h+var_1C8], xmm0
0x180193fda  mov     rax, [rcx]
0x180193fdd  test    r14d, r14d
0x180193fe0  jz      short loc_180194002
0x180193fe2  cmp     [rbx], r12d
0x180193fe5  jnz     short loc_180193FED
0x180193fe7  mov     rax, [rax+28h]
0x180193feb  jmp     short loc_180193FF1
0x180193fed  mov     rax, [rax+38h]
0x180193ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193ff6  mov     edi, eax
0x180193ff8  test    eax, eax
0x180193ffa  js      loc_180194228
0x180194000  jmp     short loc_180194016
0x180194002  cmp     [rbx], r12d
0x180194005  jnz     short loc_18019400D
0x180194007  mov     rax, [rax+30h]
0x18019400b  jmp     short loc_180194011
0x18019400d  mov     rax, [rax+40h]
0x180194011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194016  add     rbx, 10h
0x18019401a  jmp     short loc_180193FBA
0x18019401c  test    r14d, r14d
0x18019401f  jnz     loc_180194225
0x180194025  lea     r8d, [r14+40h]; cchMax
0x180194029  mov     rcx, rsi; rguid
0x18019402c  lea     rdx, [rbp+170h+sz]; lpsz
0x180194033  call    cs:__imp_StringFromGUID2
0x180194039  mov     esi, 80h
0x18019403e  mov     [rbp+170h+var_1D0], r15
0x180194042  mov     edx, esi
0x180194044  lea     r8, aClsid_0; "CLSID\\"
0x18019404b  lea     rcx, [rbp+170h+SubKey]
0x18019404f  call    cs:__imp__o_wcscpy_s
0x180194055  mov     ecx, eax; int
0x180194057  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18019405c  lea     r8, [rbp+170h+sz]
0x180194063  mov     edx, esi
0x180194065  lea     rcx, [rbp+170h+SubKey]
0x180194069  call    cs:__imp__o_wcscat_s
0x18019406f  mov     ecx, eax; int
0x180194071  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180194076  lea     r8, aRequiredCatego; "\\Required Categories"
0x18019407d  mov     edx, esi
0x18019407f  lea     rcx, [rbp+170h+SubKey]
0x180194083  call    cs:__imp__o_wcscat_s
0x180194089  mov     ecx, eax; int
0x18019408b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180194090  mov     rdi, 0FFFFFFFF80000000h
0x180194097  mov     [rbp+170h+var_1E0], r15
0x18019409b  mov     r14d, 20019h
0x1801940a1  mov     [rbp+170h+var_1E8], rdi
0x1801940a5  mov     r9d, r14d; unsigned int
0x1801940a8  mov     [rbp+170h+var_1D8], r15
0x1801940ac  mov     rdx, rdi; hKey
0x1801940af  mov     [rsp+270h+hKey], r15
0x1801940b4  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1801940b8  mov     [rsp+270h+var_1F8], r15
0x1801940bd  lea     rcx, [rsp+270h+hKey]; this
0x1801940c2  mov     [rbp+170h+var_1F0], r15
0x1801940c6  mov     [rsp+270h+cSubKeys], r15d
0x1801940cb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1801940d0  test    eax, eax
0x1801940d2  jnz     short loc_18019413C
0x1801940d4  mov     rcx, [rsp+270h+hKey]; hKey
0x1801940d9  lea     rax, [rsp+270h+cSubKeys]
0x1801940de  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1801940e3  xor     r9d, r9d; lpReserved
0x1801940e6  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1801940eb  xor     r8d, r8d; lpcchClass
0x1801940ee  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1801940f3  xor     edx, edx; lpClass
0x1801940f5  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1801940fa  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1801940ff  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180194104  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180194109  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18019410e  call    cs:__imp_RegQueryInfoKeyW
0x180194114  lea     rcx, [rsp+270h+hKey]; this
0x180194119  mov     ebx, eax
0x18019411b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180194120  test    ebx, ebx
0x180194122  jnz     short loc_18019413C
0x180194124  cmp     [rsp+270h+cSubKeys], r15d
0x180194129  jnz     short loc_18019413C
0x18019412b  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18019412f  lea     rcx, [rbp+170h+var_1E8]; this
0x180194133  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180194138  mov     rdi, [rbp+170h+var_1E8]
0x18019413c  lea     r8, aClsid_0; "CLSID\\"
0x180194143  mov     rdx, rsi
0x180194146  lea     rcx, [rbp+170h+SubKey]
0x18019414a  call    cs:__imp__o_wcscpy_s
0x180194150  mov     ecx, eax; int
0x180194152  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180194157  lea     r8, [rbp+170h+sz]
0x18019415e  mov     rdx, rsi
0x180194161  lea     rcx, [rbp+170h+SubKey]
0x180194165  call    cs:__imp__o_wcscat_s
0x18019416b  mov     ecx, eax; int
0x18019416d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180194172  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180194179  mov     rdx, rsi
0x18019417c  lea     rcx, [rbp+170h+SubKey]
0x180194180  call    cs:__imp__o_wcscat_s
0x180194186  mov     ecx, eax; int
0x180194188  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18019418d  mov     r9d, r14d; unsigned int
0x180194190  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180194194  mov     rdx, rdi; hKey
0x180194197  lea     rcx, [rsp+270h+hKey]; this
0x18019419c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1801941a1  test    eax, eax
0x1801941a3  jnz     short loc_180194209
0x1801941a5  mov     rcx, [rsp+270h+hKey]; hKey
0x1801941aa  lea     rax, [rsp+270h+cSubKeys]
0x1801941af  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1801941b4  xor     r9d, r9d; lpReserved
0x1801941b7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1801941bc  xor     r8d, r8d; lpcchClass
0x1801941bf  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1801941c4  xor     edx, edx; lpClass
0x1801941c6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1801941cb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1801941d0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1801941d5  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1801941da  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1801941df  call    cs:__imp_RegQueryInfoKeyW
0x1801941e5  lea     rcx, [rsp+270h+hKey]; this
0x1801941ea  mov     ebx, eax
0x1801941ec  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801941f1  test    ebx, ebx
0x1801941f3  jnz     short loc_180194209
0x1801941f5  cmp     [rsp+270h+cSubKeys], r15d
0x1801941fa  jnz     short loc_180194209
0x1801941fc  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x180194200  lea     rcx, [rbp+170h+var_1E8]; this
0x180194204  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180194209  lea     rcx, [rsp+270h+hKey]; this
0x18019420e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180194213  lea     rcx, [rbp+170h+var_1E8]; this
0x180194217  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18019421c  lea     rcx, [rbp+170h+var_1D0]
0x180194220  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180194225  mov     edi, r15d
0x180194228  lea     rcx, [rsp+270h+var_208]; void *
0x18019422d  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x180194232  mov     eax, edi
0x180194234  mov     rcx, [rbp+170h+var_30]
0x18019423b  xor     rcx, rsp; StackCookie
0x18019423e  call    __security_check_cookie
0x180194243  lea     r11, [rsp+270h+var_20]
0x18019424b  mov     rbx, [r11+40h]
0x18019424f  mov     rsi, [r11+48h]
0x180194253  mov     rsp, r11
0x180194256  pop     r15
0x180194258  pop     r14
0x18019425a  pop     r12
0x18019425c  pop     rdi
0x18019425d  pop     rbp
0x18019425e  retn
```
