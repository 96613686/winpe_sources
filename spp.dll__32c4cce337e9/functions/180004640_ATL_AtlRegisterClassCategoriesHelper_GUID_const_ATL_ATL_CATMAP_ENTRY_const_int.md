# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180004640`
- end: `0x18000495a`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `794`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d584`
- `0x18000d618`
- `0x18000fa34`

## callees

- `0x180002274`
- `0x180002344`
- `0x180004640`
- `0x180005de4`
- `0x18000805c`
- `0x18000c7a8`
- `0x18000ce4c`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180004787`
- `msvcrt!wcscat_s` at `0x18000479a`
- `msvcrt!wcscat_s` at `0x18000486e`
- `msvcrt!wcscat_s` at `0x180004882`
- `msvcrt!wcscat_s` at `0x180004787`
- `msvcrt!wcscat_s` at `0x18000479a`
- `msvcrt!wcscat_s` at `0x18000486e`
- `msvcrt!wcscat_s` at `0x180004882`
- `msvcrt!wcscpy_s` at `0x180004774`
- `msvcrt!wcscpy_s` at `0x18000485a`
- `msvcrt!wcscpy_s` at `0x180004774`
- `msvcrt!wcscpy_s` at `0x18000485a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800046c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800046c8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004758`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004758`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000481e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800048da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000481e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800048da`

## string_xrefs

- `0x180004769`: `CLSID\`
- `0x18000484c`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // ecx
  HKEY v11; // rdi
  LSTATUS v12; // ebx
  LSTATUS v13; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v18[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v20; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v20 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( 1 )
    {
      v10 = *(_DWORD *)v4;
      if ( !*(_DWORD *)v4 )
        break;
      v20 = *(_OWORD *)*((_QWORD *)v4 + 1);
      if ( a3 )
      {
        v6 = *(_QWORD *)ppv;
        if ( v10 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v20);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v20);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_27;
      }
      else
      {
        v9 = *(_QWORD *)ppv;
        if ( v10 == 1 )
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 48))(ppv, rguid, 1, &v20);
        else
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 64))(ppv, rguid, 1, &v20);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v19 = 0;
      wcscpy_s(Destination, 0x80u, L"CLSID\\");
      wcscat_s(Destination, 0x80u, sz);
      wcscat_s(Destination, 0x80u, L"\\Required Categories");
      v11 = HKEY_CLASSES_ROOT;
      v18[1] = 0;
      v18[0] = 0xFFFFFFFF80000000uLL;
      v18[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v12 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v12 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v18, Destination);
          v11 = (HKEY)v18[0];
        }
      }
      wcscpy_s(Destination, 0x80u, L"CLSID\\");
      wcscat_s(Destination, 0x80u, sz);
      wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v11, Destination, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v18, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v18);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    }
  }
  v8 = 0;
LABEL_27:
  ATL::CComPtrBase<IVssEnumObject>::~CComPtrBase<IVssEnumObject>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180004640  mov     [rsp-8+arg_10], rbx
0x180004645  mov     [rsp-8+arg_18], rsi
0x18000464a  push    rbp
0x18000464b  push    rdi
0x18000464c  push    r12
0x18000464e  push    r14
0x180004650  push    r15
0x180004652  lea     rbp, [rsp-150h]
0x18000465a  sub     rsp, 250h
0x180004661  mov     rax, cs:__security_cookie
0x180004668  xor     rax, rsp
0x18000466b  mov     [rbp+170h+var_30], rax
0x180004672  xor     r15d, r15d
0x180004675  xorps   xmm0, xmm0
0x180004678  mov     [rsp+270h+var_208], r15
0x18000467d  mov     r14d, r8d
0x180004680  mov     rbx, rdx
0x180004683  mov     rsi, rcx
0x180004686  movups  [rbp+170h+var_1C8], xmm0
0x18000468a  test    rdx, rdx
0x18000468d  jz      loc_180004920
0x180004693  lea     rdx, GUID_NULL; struct _GUID *
0x18000469a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000469f  test    eax, eax
0x1800046a1  jnz     loc_180004920
0x1800046a7  lea     rax, [rsp+270h+var_208]
0x1800046ac  xor     edx, edx; pUnkOuter
0x1800046ae  lea     r12d, [r15+1]
0x1800046b2  mov     [rsp+270h+ppv], rax; ppv
0x1800046b7  mov     r8d, r12d; dwClsContext
0x1800046ba  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800046c1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800046c8  call    cs:__imp_CoCreateInstance
0x1800046ce  test    eax, eax
0x1800046d0  js      loc_180004920
0x1800046d6  jmp     short loc_18000473B
0x1800046d8  mov     rax, [rbx+8]
0x1800046dc  lea     r9, [rbp+170h+var_1C8]
0x1800046e0  mov     r8d, r12d
0x1800046e3  mov     rdx, rsi
0x1800046e6  movups  xmm0, xmmword ptr [rax]
0x1800046e9  movdqu  [rbp+170h+var_1C8], xmm0
0x1800046ee  test    r14d, r14d
0x1800046f1  jz      short loc_18000471B
0x1800046f3  cmp     ecx, r12d
0x1800046f6  mov     rcx, [rsp+270h+var_208]
0x1800046fb  mov     rax, [rcx]
0x1800046fe  jnz     short loc_180004706
0x180004700  mov     rax, [rax+28h]
0x180004704  jmp     short loc_18000470A
0x180004706  mov     rax, [rax+38h]
0x18000470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000470f  mov     edi, eax
0x180004711  test    eax, eax
0x180004713  js      loc_180004923
0x180004719  jmp     short loc_180004737
0x18000471b  cmp     ecx, r12d
0x18000471e  mov     rcx, [rsp+270h+var_208]
0x180004723  mov     rax, [rcx]
0x180004726  jnz     short loc_18000472E
0x180004728  mov     rax, [rax+30h]
0x18000472c  jmp     short loc_180004732
0x18000472e  mov     rax, [rax+40h]
0x180004732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004737  add     rbx, 10h
0x18000473b  mov     ecx, [rbx]
0x18000473d  test    ecx, ecx
0x18000473f  jnz     short loc_1800046D8
0x180004741  test    r14d, r14d
0x180004744  jnz     loc_180004920
0x18000474a  lea     r8d, [rcx+40h]; cchMax
0x18000474e  mov     rcx, rsi; rguid
0x180004751  lea     rdx, [rbp+170h+sz]; lpsz
0x180004758  call    cs:__imp_StringFromGUID2
0x18000475e  mov     esi, 80h
0x180004763  mov     [rbp+170h+var_1D0], r15
0x180004767  mov     edx, esi; SizeInWords
0x180004769  lea     r8, aClsid; "CLSID\\"
0x180004770  lea     rcx, [rbp+170h+Destination]; Destination
0x180004774  call    cs:__imp_wcscpy_s
0x18000477a  lea     r8, [rbp+170h+sz]; Source
0x180004781  mov     edx, esi; SizeInWords
0x180004783  lea     rcx, [rbp+170h+Destination]; Destination
0x180004787  call    cs:__imp_wcscat_s
0x18000478d  lea     r8, aRequiredCatego; "\\Required Categories"
0x180004794  mov     edx, esi; SizeInWords
0x180004796  lea     rcx, [rbp+170h+Destination]; Destination
0x18000479a  call    cs:__imp_wcscat_s
0x1800047a0  mov     rdi, 0FFFFFFFF80000000h
0x1800047a7  mov     [rbp+170h+var_1E0], r15
0x1800047ab  mov     r14d, 20019h
0x1800047b1  mov     [rbp+170h+var_1E8], rdi
0x1800047b5  mov     r9d, r14d; unsigned int
0x1800047b8  mov     [rbp+170h+var_1D8], r15
0x1800047bc  mov     rdx, rdi; hKey
0x1800047bf  mov     [rsp+270h+hKey], r15
0x1800047c4  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1800047c8  mov     [rsp+270h+var_1F8], r15
0x1800047cd  lea     rcx, [rsp+270h+hKey]; this
0x1800047d2  mov     [rbp+170h+var_1F0], r15
0x1800047d6  mov     [rsp+270h+cSubKeys], r15d
0x1800047db  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800047e0  test    eax, eax
0x1800047e2  jnz     short loc_18000484C
0x1800047e4  mov     rcx, [rsp+270h+hKey]; hKey
0x1800047e9  lea     rax, [rsp+270h+cSubKeys]
0x1800047ee  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800047f3  xor     r9d, r9d; lpReserved
0x1800047f6  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800047fb  xor     r8d, r8d; lpcchClass
0x1800047fe  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180004803  xor     edx, edx; lpClass
0x180004805  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000480a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000480f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180004814  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180004819  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000481e  call    cs:__imp_RegQueryInfoKeyW
0x180004824  lea     rcx, [rsp+270h+hKey]; this
0x180004829  mov     ebx, eax
0x18000482b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004830  test    ebx, ebx
0x180004832  jnz     short loc_18000484C
0x180004834  cmp     [rsp+270h+cSubKeys], r15d
0x180004839  jnz     short loc_18000484C
0x18000483b  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18000483f  lea     rcx, [rbp+170h+var_1E8]; this
0x180004843  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004848  mov     rdi, [rbp+170h+var_1E8]
0x18000484c  lea     r8, aClsid; "CLSID\\"
0x180004853  mov     rdx, rsi; SizeInWords
0x180004856  lea     rcx, [rbp+170h+Destination]; Destination
0x18000485a  call    cs:__imp_wcscpy_s
0x180004860  lea     r8, [rbp+170h+sz]; Source
0x180004867  mov     rdx, rsi; SizeInWords
0x18000486a  lea     rcx, [rbp+170h+Destination]; Destination
0x18000486e  call    cs:__imp_wcscat_s
0x180004874  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000487b  mov     rdx, rsi; SizeInWords
0x18000487e  lea     rcx, [rbp+170h+Destination]; Destination
0x180004882  call    cs:__imp_wcscat_s
0x180004888  mov     r9d, r14d; unsigned int
0x18000488b  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18000488f  mov     rdx, rdi; hKey
0x180004892  lea     rcx, [rsp+270h+hKey]; this
0x180004897  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000489c  test    eax, eax
0x18000489e  jnz     short loc_180004904
0x1800048a0  mov     rcx, [rsp+270h+hKey]; hKey
0x1800048a5  lea     rax, [rsp+270h+cSubKeys]
0x1800048aa  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800048af  xor     r9d, r9d; lpReserved
0x1800048b2  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800048b7  xor     r8d, r8d; lpcchClass
0x1800048ba  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800048bf  xor     edx, edx; lpClass
0x1800048c1  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800048c6  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800048cb  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800048d0  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800048d5  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800048da  call    cs:__imp_RegQueryInfoKeyW
0x1800048e0  lea     rcx, [rsp+270h+hKey]; this
0x1800048e5  mov     ebx, eax
0x1800048e7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800048ec  test    ebx, ebx
0x1800048ee  jnz     short loc_180004904
0x1800048f0  cmp     [rsp+270h+cSubKeys], r15d
0x1800048f5  jnz     short loc_180004904
0x1800048f7  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800048fb  lea     rcx, [rbp+170h+var_1E8]; this
0x1800048ff  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004904  lea     rcx, [rsp+270h+hKey]; this
0x180004909  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000490e  lea     rcx, [rbp+170h+var_1E8]; this
0x180004912  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004917  lea     rcx, [rbp+170h+var_1D0]
0x18000491b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004920  mov     edi, r15d
0x180004923  lea     rcx, [rsp+270h+var_208]
0x180004928  call    ??1?$CComPtrBase@UIVssEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IVssEnumObject>::~CComPtrBase<IVssEnumObject>(void)
0x18000492d  mov     eax, edi
0x18000492f  mov     rcx, [rbp+170h+var_30]
0x180004936  xor     rcx, rsp; StackCookie
0x180004939  call    __security_check_cookie
0x18000493e  lea     r11, [rsp+270h+var_20]
0x180004946  mov     rbx, [r11+40h]
0x18000494a  mov     rsi, [r11+48h]
0x18000494e  mov     rsp, r11
0x180004951  pop     r15
0x180004953  pop     r14
0x180004955  pop     r12
0x180004957  pop     rdi
0x180004958  pop     rbp
0x180004959  retn
```
