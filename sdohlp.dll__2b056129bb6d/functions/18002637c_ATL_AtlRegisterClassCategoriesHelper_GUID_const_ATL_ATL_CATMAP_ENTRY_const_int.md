# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18002637c`
- end: `0x1800266b7`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a580`
- `0x18002c394`
- `0x18002cba0`

## callees

- `0x180024850`
- `0x180024cac`
- `0x180025f74`
- `0x18002637c`
- `0x180026a40`
- `0x1800277bc`
- `0x180029c20`
- `0x18002cc74`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800264c1`
- `msvcrt!wcscat_s` at `0x1800264db`
- `msvcrt!wcscat_s` at `0x1800265bd`
- `msvcrt!wcscat_s` at `0x1800265d8`
- `msvcrt!wcscat_s` at `0x1800264c1`
- `msvcrt!wcscat_s` at `0x1800264db`
- `msvcrt!wcscat_s` at `0x1800265bd`
- `msvcrt!wcscat_s` at `0x1800265d8`
- `msvcrt!wcscpy_s` at `0x1800264a7`
- `msvcrt!wcscpy_s` at `0x1800265a2`
- `msvcrt!wcscpy_s` at `0x1800264a7`
- `msvcrt!wcscpy_s` at `0x1800265a2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026566`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026637`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026566`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026637`
- `ole32!CoCreateInstance` at `0x180026404`
- `ole32!CoCreateInstance` at `0x180026404`
- `ole32!StringFromGUID2` at `0x18002648b`
- `ole32!StringFromGUID2` at `0x18002648b`

## string_xrefs

- `0x18002649c`: `CLSID\`
- `0x180026594`: `CLSID\`

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
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18002637c  mov     [rsp-8+arg_10], rbx
0x180026381  mov     [rsp-8+arg_18], rsi
0x180026386  push    rbp
0x180026387  push    rdi
0x180026388  push    r12
0x18002638a  push    r14
0x18002638c  push    r15
0x18002638e  lea     rbp, [rsp-150h]
0x180026396  sub     rsp, 250h
0x18002639d  mov     rax, cs:__security_cookie
0x1800263a4  xor     rax, rsp
0x1800263a7  mov     [rbp+170h+var_30], rax
0x1800263ae  xor     r15d, r15d
0x1800263b1  xorps   xmm0, xmm0
0x1800263b4  mov     [rsp+270h+var_208], r15
0x1800263b9  mov     r14d, r8d
0x1800263bc  mov     rbx, rdx
0x1800263bf  mov     rsi, rcx
0x1800263c2  movups  [rbp+170h+var_1C8], xmm0
0x1800263c6  test    rdx, rdx
0x1800263c9  jz      loc_18002667D
0x1800263cf  lea     rdx, GUID_NULL
0x1800263d6  call    InlineIsEqualGUID
0x1800263db  test    eax, eax
0x1800263dd  jnz     loc_18002667D
0x1800263e3  lea     rax, [rsp+270h+var_208]
0x1800263e8  xor     edx, edx; pUnkOuter
0x1800263ea  lea     r12d, [r15+1]
0x1800263ee  mov     [rsp+270h+ppv], rax; ppv
0x1800263f3  mov     r8d, r12d; dwClsContext
0x1800263f6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800263fd  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180026404  call    cs:__imp_CoCreateInstance
0x18002640a  test    eax, eax
0x18002640c  js      loc_18002667D
0x180026412  cmp     [rbx], r15d
0x180026415  jz      short loc_180026474
0x180026417  mov     rax, [rbx+8]
0x18002641b  lea     r9, [rbp+170h+var_1C8]
0x18002641f  mov     rcx, [rsp+270h+var_208]
0x180026424  mov     r8d, r12d
0x180026427  mov     rdx, rsi
0x18002642a  movups  xmm0, xmmword ptr [rax]
0x18002642d  movdqu  [rbp+170h+var_1C8], xmm0
0x180026432  mov     rax, [rcx]
0x180026435  test    r14d, r14d
0x180026438  jz      short loc_18002645A
0x18002643a  cmp     [rbx], r12d
0x18002643d  jnz     short loc_180026445
0x18002643f  mov     rax, [rax+28h]
0x180026443  jmp     short loc_180026449
0x180026445  mov     rax, [rax+38h]
0x180026449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002644e  mov     edi, eax
0x180026450  test    eax, eax
0x180026452  js      loc_180026680
0x180026458  jmp     short loc_18002646E
0x18002645a  cmp     [rbx], r12d
0x18002645d  jnz     short loc_180026465
0x18002645f  mov     rax, [rax+30h]
0x180026463  jmp     short loc_180026469
0x180026465  mov     rax, [rax+40h]
0x180026469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002646e  add     rbx, 10h
0x180026472  jmp     short loc_180026412
0x180026474  test    r14d, r14d
0x180026477  jnz     loc_18002667D
0x18002647d  lea     r8d, [r14+40h]; cchMax
0x180026481  mov     rcx, rsi; rguid
0x180026484  lea     rdx, [rbp+170h+sz]; lpsz
0x18002648b  call    cs:__imp_StringFromGUID2
0x180026491  mov     esi, 80h
0x180026496  mov     [rbp+170h+var_1D0], r15
0x18002649a  mov     edx, esi; SizeInWords
0x18002649c  lea     r8, aClsid; "CLSID\\"
0x1800264a3  lea     rcx, [rbp+170h+Destination]; Destination
0x1800264a7  call    cs:__imp_wcscpy_s
0x1800264ad  mov     ecx, eax; int
0x1800264af  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800264b4  lea     r8, [rbp+170h+sz]; Source
0x1800264bb  mov     edx, esi; SizeInWords
0x1800264bd  lea     rcx, [rbp+170h+Destination]; Destination
0x1800264c1  call    cs:__imp_wcscat_s
0x1800264c7  mov     ecx, eax; int
0x1800264c9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800264ce  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800264d5  mov     edx, esi; SizeInWords
0x1800264d7  lea     rcx, [rbp+170h+Destination]; Destination
0x1800264db  call    cs:__imp_wcscat_s
0x1800264e1  mov     ecx, eax; int
0x1800264e3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800264e8  mov     rdi, 0FFFFFFFF80000000h
0x1800264ef  mov     [rbp+170h+var_1E0], r15
0x1800264f3  mov     r14d, 20019h
0x1800264f9  mov     [rbp+170h+var_1E8], rdi
0x1800264fd  mov     r9d, r14d; unsigned int
0x180026500  mov     [rbp+170h+var_1D8], r15
0x180026504  mov     rdx, rdi; hKey
0x180026507  mov     [rsp+270h+hKey], r15
0x18002650c  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180026510  mov     [rsp+270h+var_1F8], r15
0x180026515  lea     rcx, [rsp+270h+hKey]; this
0x18002651a  mov     [rbp+170h+var_1F0], r15
0x18002651e  mov     [rsp+270h+cSubKeys], r15d
0x180026523  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180026528  test    eax, eax
0x18002652a  jnz     short loc_180026594
0x18002652c  mov     rcx, [rsp+270h+hKey]; hKey
0x180026531  lea     rax, [rsp+270h+cSubKeys]
0x180026536  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002653b  xor     r9d, r9d; lpReserved
0x18002653e  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180026543  xor     r8d, r8d; lpcchClass
0x180026546  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002654b  xor     edx, edx; lpClass
0x18002654d  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180026552  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180026557  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002655c  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180026561  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180026566  call    cs:__imp_RegQueryInfoKeyW
0x18002656c  lea     rcx, [rsp+270h+hKey]; this
0x180026571  mov     ebx, eax
0x180026573  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026578  test    ebx, ebx
0x18002657a  jnz     short loc_180026594
0x18002657c  cmp     [rsp+270h+cSubKeys], r15d
0x180026581  jnz     short loc_180026594
0x180026583  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180026587  lea     rcx, [rbp+170h+var_1E8]; this
0x18002658b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180026590  mov     rdi, [rbp+170h+var_1E8]
0x180026594  lea     r8, aClsid; "CLSID\\"
0x18002659b  mov     rdx, rsi; SizeInWords
0x18002659e  lea     rcx, [rbp+170h+Destination]; Destination
0x1800265a2  call    cs:__imp_wcscpy_s
0x1800265a8  mov     ecx, eax; int
0x1800265aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800265af  lea     r8, [rbp+170h+sz]; Source
0x1800265b6  mov     rdx, rsi; SizeInWords
0x1800265b9  lea     rcx, [rbp+170h+Destination]; Destination
0x1800265bd  call    cs:__imp_wcscat_s
0x1800265c3  mov     ecx, eax; int
0x1800265c5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800265ca  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800265d1  mov     rdx, rsi; SizeInWords
0x1800265d4  lea     rcx, [rbp+170h+Destination]; Destination
0x1800265d8  call    cs:__imp_wcscat_s
0x1800265de  mov     ecx, eax; int
0x1800265e0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800265e5  mov     r9d, r14d; unsigned int
0x1800265e8  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1800265ec  mov     rdx, rdi; hKey
0x1800265ef  lea     rcx, [rsp+270h+hKey]; this
0x1800265f4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800265f9  test    eax, eax
0x1800265fb  jnz     short loc_180026661
0x1800265fd  mov     rcx, [rsp+270h+hKey]; hKey
0x180026602  lea     rax, [rsp+270h+cSubKeys]
0x180026607  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002660c  xor     r9d, r9d; lpReserved
0x18002660f  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180026614  xor     r8d, r8d; lpcchClass
0x180026617  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002661c  xor     edx, edx; lpClass
0x18002661e  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180026623  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180026628  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002662d  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180026632  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180026637  call    cs:__imp_RegQueryInfoKeyW
0x18002663d  lea     rcx, [rsp+270h+hKey]; this
0x180026642  mov     ebx, eax
0x180026644  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026649  test    ebx, ebx
0x18002664b  jnz     short loc_180026661
0x18002664d  cmp     [rsp+270h+cSubKeys], r15d
0x180026652  jnz     short loc_180026661
0x180026654  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180026658  lea     rcx, [rbp+170h+var_1E8]; this
0x18002665c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180026661  lea     rcx, [rsp+270h+hKey]; this
0x180026666  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002666b  lea     rcx, [rbp+170h+var_1E8]; this
0x18002666f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026674  lea     rcx, [rbp+170h+var_1D0]
0x180026678  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002667d  mov     edi, r15d
0x180026680  lea     rcx, [rsp+270h+var_208]
0x180026685  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002668a  mov     eax, edi
0x18002668c  mov     rcx, [rbp+170h+var_30]
0x180026693  xor     rcx, rsp; StackCookie
0x180026696  call    __security_check_cookie
0x18002669b  lea     r11, [rsp+270h+var_20]
0x1800266a3  mov     rbx, [r11+40h]
0x1800266a7  mov     rsi, [r11+48h]
0x1800266ab  mov     rsp, r11
0x1800266ae  pop     r15
0x1800266b0  pop     r14
0x1800266b2  pop     r12
0x1800266b4  pop     rdi
0x1800266b5  pop     rbp
0x1800266b6  retn
```
