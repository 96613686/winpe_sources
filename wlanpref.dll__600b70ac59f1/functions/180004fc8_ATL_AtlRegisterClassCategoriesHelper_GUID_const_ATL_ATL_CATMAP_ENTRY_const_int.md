# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180004fc8`
- end: `0x180005303`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ae68`
- `0x18000bd64`
- `0x18000c5b0`

## callees

- `0x180002cc0`
- `0x180003458`
- `0x180004c00`
- `0x180004fc8`
- `0x180005814`
- `0x180007534`
- `0x1800080c4`
- `0x180009034`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000510d`
- `msvcrt!wcscat_s` at `0x180005127`
- `msvcrt!wcscat_s` at `0x180005209`
- `msvcrt!wcscat_s` at `0x180005224`
- `msvcrt!wcscat_s` at `0x18000510d`
- `msvcrt!wcscat_s` at `0x180005127`
- `msvcrt!wcscat_s` at `0x180005209`
- `msvcrt!wcscat_s` at `0x180005224`
- `msvcrt!wcscpy_s` at `0x1800050f3`
- `msvcrt!wcscpy_s` at `0x1800051ee`
- `msvcrt!wcscpy_s` at `0x1800050f3`
- `msvcrt!wcscpy_s` at `0x1800051ee`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800050d7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800050d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005050`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005050`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800051b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005283`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800051b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005283`

## string_xrefs

- `0x1800050e8`: `CLSID\`
- `0x1800051e0`: `CLSID\`

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
0x180004fc8  mov     [rsp-8+arg_10], rbx
0x180004fcd  mov     [rsp-8+arg_18], rsi
0x180004fd2  push    rbp
0x180004fd3  push    rdi
0x180004fd4  push    r12
0x180004fd6  push    r14
0x180004fd8  push    r15
0x180004fda  lea     rbp, [rsp-150h]
0x180004fe2  sub     rsp, 250h
0x180004fe9  mov     rax, cs:__security_cookie
0x180004ff0  xor     rax, rsp
0x180004ff3  mov     [rbp+170h+var_30], rax
0x180004ffa  xor     r15d, r15d
0x180004ffd  xorps   xmm0, xmm0
0x180005000  mov     [rsp+270h+var_208], r15
0x180005005  mov     r14d, r8d
0x180005008  mov     rbx, rdx
0x18000500b  mov     rsi, rcx
0x18000500e  movups  [rbp+170h+var_1C8], xmm0
0x180005012  test    rdx, rdx
0x180005015  jz      loc_1800052C9
0x18000501b  lea     rdx, GUID_NULL; struct _GUID *
0x180005022  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180005027  test    eax, eax
0x180005029  jnz     loc_1800052C9
0x18000502f  lea     rax, [rsp+270h+var_208]
0x180005034  xor     edx, edx; pUnkOuter
0x180005036  lea     r12d, [r15+1]
0x18000503a  mov     [rsp+270h+ppv], rax; ppv
0x18000503f  mov     r8d, r12d; dwClsContext
0x180005042  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180005049  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180005050  call    cs:__imp_CoCreateInstance
0x180005056  test    eax, eax
0x180005058  js      loc_1800052C9
0x18000505e  cmp     [rbx], r15d
0x180005061  jz      short loc_1800050C0
0x180005063  mov     rax, [rbx+8]
0x180005067  lea     r9, [rbp+170h+var_1C8]
0x18000506b  mov     rcx, [rsp+270h+var_208]
0x180005070  mov     r8d, r12d
0x180005073  mov     rdx, rsi
0x180005076  movups  xmm0, xmmword ptr [rax]
0x180005079  movdqu  [rbp+170h+var_1C8], xmm0
0x18000507e  mov     rax, [rcx]
0x180005081  test    r14d, r14d
0x180005084  jz      short loc_1800050A6
0x180005086  cmp     [rbx], r12d
0x180005089  jnz     short loc_180005091
0x18000508b  mov     rax, [rax+28h]
0x18000508f  jmp     short loc_180005095
0x180005091  mov     rax, [rax+38h]
0x180005095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509a  mov     edi, eax
0x18000509c  test    eax, eax
0x18000509e  js      loc_1800052CC
0x1800050a4  jmp     short loc_1800050BA
0x1800050a6  cmp     [rbx], r12d
0x1800050a9  jnz     short loc_1800050B1
0x1800050ab  mov     rax, [rax+30h]
0x1800050af  jmp     short loc_1800050B5
0x1800050b1  mov     rax, [rax+40h]
0x1800050b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ba  add     rbx, 10h
0x1800050be  jmp     short loc_18000505E
0x1800050c0  test    r14d, r14d
0x1800050c3  jnz     loc_1800052C9
0x1800050c9  lea     r8d, [r14+40h]; cchMax
0x1800050cd  mov     rcx, rsi; rguid
0x1800050d0  lea     rdx, [rbp+170h+sz]; lpsz
0x1800050d7  call    cs:__imp_StringFromGUID2
0x1800050dd  mov     esi, 80h
0x1800050e2  mov     [rbp+170h+var_1D0], r15
0x1800050e6  mov     edx, esi; SizeInWords
0x1800050e8  lea     r8, aClsid; "CLSID\\"
0x1800050ef  lea     rcx, [rbp+170h+Destination]; Destination
0x1800050f3  call    cs:__imp_wcscpy_s
0x1800050f9  mov     ecx, eax; int
0x1800050fb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005100  lea     r8, [rbp+170h+sz]; Source
0x180005107  mov     edx, esi; SizeInWords
0x180005109  lea     rcx, [rbp+170h+Destination]; Destination
0x18000510d  call    cs:__imp_wcscat_s
0x180005113  mov     ecx, eax; int
0x180005115  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000511a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180005121  mov     edx, esi; SizeInWords
0x180005123  lea     rcx, [rbp+170h+Destination]; Destination
0x180005127  call    cs:__imp_wcscat_s
0x18000512d  mov     ecx, eax; int
0x18000512f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005134  mov     rdi, 0FFFFFFFF80000000h
0x18000513b  mov     [rbp+170h+var_1E0], r15
0x18000513f  mov     r14d, 20019h
0x180005145  mov     [rbp+170h+var_1E8], rdi
0x180005149  mov     r9d, r14d; unsigned int
0x18000514c  mov     [rbp+170h+var_1D8], r15
0x180005150  mov     rdx, rdi; hKey
0x180005153  mov     [rsp+270h+hKey], r15
0x180005158  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18000515c  mov     [rsp+270h+var_1F8], r15
0x180005161  lea     rcx, [rsp+270h+hKey]; this
0x180005166  mov     [rbp+170h+var_1F0], r15
0x18000516a  mov     [rsp+270h+cSubKeys], r15d
0x18000516f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005174  test    eax, eax
0x180005176  jnz     short loc_1800051E0
0x180005178  mov     rcx, [rsp+270h+hKey]; hKey
0x18000517d  lea     rax, [rsp+270h+cSubKeys]
0x180005182  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005187  xor     r9d, r9d; lpReserved
0x18000518a  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000518f  xor     r8d, r8d; lpcchClass
0x180005192  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005197  xor     edx, edx; lpClass
0x180005199  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000519e  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800051a3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800051a8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800051ad  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800051b2  call    cs:__imp_RegQueryInfoKeyW
0x1800051b8  lea     rcx, [rsp+270h+hKey]; this
0x1800051bd  mov     ebx, eax
0x1800051bf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800051c4  test    ebx, ebx
0x1800051c6  jnz     short loc_1800051E0
0x1800051c8  cmp     [rsp+270h+cSubKeys], r15d
0x1800051cd  jnz     short loc_1800051E0
0x1800051cf  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800051d3  lea     rcx, [rbp+170h+var_1E8]; this
0x1800051d7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800051dc  mov     rdi, [rbp+170h+var_1E8]
0x1800051e0  lea     r8, aClsid; "CLSID\\"
0x1800051e7  mov     rdx, rsi; SizeInWords
0x1800051ea  lea     rcx, [rbp+170h+Destination]; Destination
0x1800051ee  call    cs:__imp_wcscpy_s
0x1800051f4  mov     ecx, eax; int
0x1800051f6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800051fb  lea     r8, [rbp+170h+sz]; Source
0x180005202  mov     rdx, rsi; SizeInWords
0x180005205  lea     rcx, [rbp+170h+Destination]; Destination
0x180005209  call    cs:__imp_wcscat_s
0x18000520f  mov     ecx, eax; int
0x180005211  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005216  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000521d  mov     rdx, rsi; SizeInWords
0x180005220  lea     rcx, [rbp+170h+Destination]; Destination
0x180005224  call    cs:__imp_wcscat_s
0x18000522a  mov     ecx, eax; int
0x18000522c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005231  mov     r9d, r14d; unsigned int
0x180005234  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180005238  mov     rdx, rdi; hKey
0x18000523b  lea     rcx, [rsp+270h+hKey]; this
0x180005240  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005245  test    eax, eax
0x180005247  jnz     short loc_1800052AD
0x180005249  mov     rcx, [rsp+270h+hKey]; hKey
0x18000524e  lea     rax, [rsp+270h+cSubKeys]
0x180005253  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005258  xor     r9d, r9d; lpReserved
0x18000525b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180005260  xor     r8d, r8d; lpcchClass
0x180005263  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005268  xor     edx, edx; lpClass
0x18000526a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000526f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180005274  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180005279  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000527e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180005283  call    cs:__imp_RegQueryInfoKeyW
0x180005289  lea     rcx, [rsp+270h+hKey]; this
0x18000528e  mov     ebx, eax
0x180005290  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005295  test    ebx, ebx
0x180005297  jnz     short loc_1800052AD
0x180005299  cmp     [rsp+270h+cSubKeys], r15d
0x18000529e  jnz     short loc_1800052AD
0x1800052a0  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800052a4  lea     rcx, [rbp+170h+var_1E8]; this
0x1800052a8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800052ad  lea     rcx, [rsp+270h+hKey]; this
0x1800052b2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800052b7  lea     rcx, [rbp+170h+var_1E8]; this
0x1800052bb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800052c0  lea     rcx, [rbp+170h+var_1D0]
0x1800052c4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800052c9  mov     edi, r15d
0x1800052cc  lea     rcx, [rsp+270h+var_208]
0x1800052d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800052d6  mov     eax, edi
0x1800052d8  mov     rcx, [rbp+170h+var_30]
0x1800052df  xor     rcx, rsp; StackCookie
0x1800052e2  call    __security_check_cookie
0x1800052e7  lea     r11, [rsp+270h+var_20]
0x1800052ef  mov     rbx, [r11+40h]
0x1800052f3  mov     rsi, [r11+48h]
0x1800052f7  mov     rsp, r11
0x1800052fa  pop     r15
0x1800052fc  pop     r14
0x1800052fe  pop     r12
0x180005300  pop     rdi
0x180005301  pop     rbp
0x180005302  retn
```
