# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180006598`
- end: `0x1800068e6`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `846`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007854`
- `0x18000821c`
- `0x180008890`

## callees

- `0x180001330`
- `0x180002570`
- `0x180003768`
- `0x180003774`
- `0x180005798`
- `0x180006510`
- `0x180006598`
- `0x180006ad4`
- `0x180006cac`
- `0x1800070c8`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000671b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006735`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006817`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006832`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000671b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006735`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006817`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006832`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006701`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800067fc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006701`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800067fc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800066e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800066e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006618`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006618`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800067c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006891`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800067c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006891`

## string_xrefs

- `0x1800066f6`: `CLSID\`
- `0x1800067ee`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rax
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  LSTATUS InfoKeyW; // ebx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  LSTATUS v20; // ebx
  DWORD cSubKeys[2]; // [rsp+60h] [rbp-A0h] BYREF
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
    while ( 1 )
    {
      v11 = *(_DWORD *)v4;
      if ( !*(_DWORD *)v4 )
        break;
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      if ( a3 )
      {
        v7 = *(_QWORD *)ppv;
        if ( v11 == 1 )
          v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 40))(ppv, rguid, 1, &v26);
        else
          v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 56))(ppv, rguid, 1, &v26);
        v9 = v8;
        if ( v8 < 0 )
        {
          ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(&ppv);
          return v9;
        }
      }
      else
      {
        v10 = *(_QWORD *)ppv;
        if ( v11 == 1 )
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v26);
        else
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v12 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v12);
      v13 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v13);
      v14 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v14);
      v15 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys[0] = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        InfoKeyW = RegQueryInfoKeyW(hKey[0], 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !InfoKeyW && !cSubKeys[0] )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
          v15 = (HKEY)v24[0];
        }
      }
      v17 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v17);
      v18 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v18);
      v19 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v19);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v15, SubKey, 0x20019u) )
      {
        v20 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v20 && !cSubKeys[0] )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
    ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(&ppv);
  }
  else
  {
    ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(&ppv);
  }
  return 0;
}

```

## disassembly

```asm
0x180006598  mov     [rsp-8+arg_10], rbx
0x18000659d  mov     [rsp-8+arg_18], rsi
0x1800065a2  push    rbp
0x1800065a3  push    rdi
0x1800065a4  push    r12
0x1800065a6  push    r14
0x1800065a8  push    r15
0x1800065aa  lea     rbp, [rsp-150h]
0x1800065b2  sub     rsp, 250h
0x1800065b9  mov     rax, cs:__security_cookie
0x1800065c0  xor     rax, rsp
0x1800065c3  mov     [rbp+170h+var_30], rax
0x1800065ca  xor     r15d, r15d
0x1800065cd  xorps   xmm0, xmm0
0x1800065d0  mov     [rsp+270h+var_208], r15
0x1800065d5  mov     r14d, r8d
0x1800065d8  mov     rbx, rdx
0x1800065db  mov     rdi, rcx
0x1800065de  movups  [rbp+170h+var_1C8], xmm0
0x1800065e2  test    rdx, rdx
0x1800065e5  jz      short loc_180006626
0x1800065e7  lea     rdx, GUID_NULL
0x1800065ee  call    InlineIsEqualGUID
0x1800065f3  test    eax, eax
0x1800065f5  jnz     short loc_180006626
0x1800065f7  lea     rax, [rsp+270h+var_208]
0x1800065fc  xor     edx, edx; pUnkOuter
0x1800065fe  lea     r12d, [r15+1]
0x180006602  mov     [rsp+270h+ppv], rax; ppv
0x180006607  mov     r8d, r12d; dwClsContext
0x18000660a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180006611  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180006618  call    cs:__imp_CoCreateInstance
0x18000661e  test    eax, eax
0x180006620  jns     loc_1800066C8
0x180006626  lea     rcx, [rsp+270h+var_208]
0x18000662b  call    ??1?$CComPtr@UICatRegister@@@ATL@@QEAA@XZ; ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(void)
0x180006630  xor     eax, eax
0x180006632  mov     rcx, [rbp+170h+var_30]
0x180006639  xor     rcx, rsp; StackCookie
0x18000663c  call    __security_check_cookie
0x180006641  lea     r11, [rsp+270h+var_20]
0x180006649  mov     rbx, [r11+40h]
0x18000664d  mov     rsi, [r11+48h]
0x180006651  mov     rsp, r11
0x180006654  pop     r15
0x180006656  pop     r14
0x180006658  pop     r12
0x18000665a  pop     rdi
0x18000665b  pop     rbp
0x18000665c  retn
0x18000665d  mov     rax, [rbx+8]
0x180006661  lea     r9, [rbp+170h+var_1C8]
0x180006665  mov     r8d, r12d
0x180006668  mov     rdx, rdi
0x18000666b  movups  xmm0, xmmword ptr [rax]
0x18000666e  movdqu  [rbp+170h+var_1C8], xmm0
0x180006673  test    r14d, r14d
0x180006676  jz      short loc_1800066A8
0x180006678  cmp     ecx, r12d
0x18000667b  mov     rcx, [rsp+270h+var_208]
0x180006680  mov     rax, [rcx]
0x180006683  jnz     short loc_18000668B
0x180006685  mov     rax, [rax+28h]
0x180006689  jmp     short loc_18000668F
0x18000668b  mov     rax, [rax+38h]
0x18000668f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006694  mov     esi, eax
0x180006696  test    eax, eax
0x180006698  jns     short loc_1800066C4
0x18000669a  lea     rcx, [rsp+270h+var_208]
0x18000669f  call    ??1?$CComPtr@UICatRegister@@@ATL@@QEAA@XZ; ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(void)
0x1800066a4  mov     eax, esi
0x1800066a6  jmp     short loc_180006632
0x1800066a8  cmp     ecx, r12d
0x1800066ab  mov     rcx, [rsp+270h+var_208]
0x1800066b0  mov     rax, [rcx]
0x1800066b3  jnz     short loc_1800066BB
0x1800066b5  mov     rax, [rax+30h]
0x1800066b9  jmp     short loc_1800066BF
0x1800066bb  mov     rax, [rax+40h]
0x1800066bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c4  add     rbx, 10h
0x1800066c8  mov     ecx, [rbx]
0x1800066ca  test    ecx, ecx
0x1800066cc  jnz     short loc_18000665D
0x1800066ce  test    r14d, r14d
0x1800066d1  jnz     loc_1800068D7
0x1800066d7  lea     r8d, [rcx+40h]; cchMax
0x1800066db  mov     rcx, rdi; rguid
0x1800066de  lea     rdx, [rbp+170h+sz]; lpsz
0x1800066e5  call    cs:__imp_StringFromGUID2
0x1800066eb  mov     esi, 80h
0x1800066f0  mov     [rbp+170h+var_1D0], r15
0x1800066f4  mov     edx, esi
0x1800066f6  lea     r8, aClsid; "CLSID\\"
0x1800066fd  lea     rcx, [rbp+170h+SubKey]
0x180006701  call    cs:__imp__o_wcscpy_s
0x180006707  mov     ecx, eax; int
0x180006709  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000670e  lea     r8, [rbp+170h+sz]
0x180006715  mov     edx, esi
0x180006717  lea     rcx, [rbp+170h+SubKey]
0x18000671b  call    cs:__imp__o_wcscat_s
0x180006721  mov     ecx, eax; int
0x180006723  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006728  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000672f  mov     edx, esi
0x180006731  lea     rcx, [rbp+170h+SubKey]
0x180006735  call    cs:__imp__o_wcscat_s
0x18000673b  mov     ecx, eax; int
0x18000673d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006742  mov     rdi, 0FFFFFFFF80000000h
0x180006749  mov     [rbp+170h+var_1E0], r15
0x18000674d  mov     r14d, 20019h
0x180006753  mov     [rbp+170h+var_1E8], rdi
0x180006757  mov     r9d, r14d; unsigned int
0x18000675a  mov     [rbp+170h+var_1D8], r15
0x18000675e  mov     rdx, rdi; hKey
0x180006761  mov     [rsp+270h+hKey], r15
0x180006766  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18000676a  mov     [rsp+270h+var_1F8], r15
0x18000676f  lea     rcx, [rsp+270h+hKey]; this
0x180006774  mov     [rbp+170h+var_1F0], r15
0x180006778  mov     [rsp+270h+cSubKeys], r15d
0x18000677d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006782  test    eax, eax
0x180006784  jnz     short loc_1800067EE
0x180006786  mov     rcx, [rsp+270h+hKey]; hKey
0x18000678b  lea     rax, [rsp+270h+cSubKeys]
0x180006790  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006795  xor     r9d, r9d; lpReserved
0x180006798  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000679d  xor     r8d, r8d; lpcchClass
0x1800067a0  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800067a5  xor     edx, edx; lpClass
0x1800067a7  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800067ac  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800067b1  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800067b6  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800067bb  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800067c0  call    cs:__imp_RegQueryInfoKeyW
0x1800067c6  lea     rcx, [rsp+270h+hKey]; this
0x1800067cb  mov     ebx, eax
0x1800067cd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800067d2  test    ebx, ebx
0x1800067d4  jnz     short loc_1800067EE
0x1800067d6  cmp     [rsp+270h+cSubKeys], r15d
0x1800067db  jnz     short loc_1800067EE
0x1800067dd  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800067e1  lea     rcx, [rbp+170h+var_1E8]; this
0x1800067e5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800067ea  mov     rdi, [rbp+170h+var_1E8]
0x1800067ee  lea     r8, aClsid; "CLSID\\"
0x1800067f5  mov     rdx, rsi
0x1800067f8  lea     rcx, [rbp+170h+SubKey]
0x1800067fc  call    cs:__imp__o_wcscpy_s
0x180006802  mov     ecx, eax; int
0x180006804  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006809  lea     r8, [rbp+170h+sz]
0x180006810  mov     rdx, rsi
0x180006813  lea     rcx, [rbp+170h+SubKey]
0x180006817  call    cs:__imp__o_wcscat_s
0x18000681d  mov     ecx, eax; int
0x18000681f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006824  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000682b  mov     rdx, rsi
0x18000682e  lea     rcx, [rbp+170h+SubKey]
0x180006832  call    cs:__imp__o_wcscat_s
0x180006838  mov     ecx, eax; int
0x18000683a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000683f  mov     r9d, r14d; unsigned int
0x180006842  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180006846  mov     rdx, rdi; hKey
0x180006849  lea     rcx, [rsp+270h+hKey]; this
0x18000684e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006853  test    eax, eax
0x180006855  jnz     short loc_1800068BB
0x180006857  mov     rcx, [rsp+270h+hKey]; hKey
0x18000685c  lea     rax, [rsp+270h+cSubKeys]
0x180006861  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006866  xor     r9d, r9d; lpReserved
0x180006869  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000686e  xor     r8d, r8d; lpcchClass
0x180006871  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006876  xor     edx, edx; lpClass
0x180006878  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000687d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180006882  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006887  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000688c  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180006891  call    cs:__imp_RegQueryInfoKeyW
0x180006897  lea     rcx, [rsp+270h+hKey]; this
0x18000689c  mov     ebx, eax
0x18000689e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800068a3  test    ebx, ebx
0x1800068a5  jnz     short loc_1800068BB
0x1800068a7  cmp     [rsp+270h+cSubKeys], r15d
0x1800068ac  jnz     short loc_1800068BB
0x1800068ae  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800068b2  lea     rcx, [rbp+170h+var_1E8]; this
0x1800068b6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800068bb  lea     rcx, [rsp+270h+hKey]; this
0x1800068c0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800068c5  lea     rcx, [rbp+170h+var_1E8]; this
0x1800068c9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800068ce  lea     rcx, [rbp+170h+var_1D0]
0x1800068d2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800068d7  lea     rcx, [rsp+270h+var_208]
0x1800068dc  call    ??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)
0x1800068e1  jmp     loc_180006630
```
