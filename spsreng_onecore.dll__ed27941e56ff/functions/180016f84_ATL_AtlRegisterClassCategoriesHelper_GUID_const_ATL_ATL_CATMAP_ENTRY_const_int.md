# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180016f84`
- end: `0x1800172bf`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001adc0`
- `0x18001ba74`
- `0x18001c9f0`

## callees

- `0x180002db8`
- `0x1800034b0`
- `0x1800147ec`
- `0x180014f98`
- `0x180016efc`
- `0x180016f84`
- `0x180017414`
- `0x1800195c4`
- `0x180019ea0`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800170c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800170e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800171c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800171e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800170c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800170e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800171c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800171e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800170af`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800171aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800170af`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800171aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017093`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017093`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001700c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001700c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001716e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001723f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001716e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001723f`

## string_xrefs

- `0x1800170a4`: `CLSID\`
- `0x18001719c`: `CLSID\`

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
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv, a2);
  return v8;
}

```

## disassembly

```asm
0x180016f84  mov     [rsp-8+arg_10], rbx
0x180016f89  mov     [rsp-8+arg_18], rsi
0x180016f8e  push    rbp
0x180016f8f  push    rdi
0x180016f90  push    r12
0x180016f92  push    r14
0x180016f94  push    r15
0x180016f96  lea     rbp, [rsp-150h]
0x180016f9e  sub     rsp, 250h
0x180016fa5  mov     rax, cs:__security_cookie
0x180016fac  xor     rax, rsp
0x180016faf  mov     [rbp+170h+var_30], rax
0x180016fb6  xor     r15d, r15d
0x180016fb9  xorps   xmm0, xmm0
0x180016fbc  mov     [rsp+270h+var_208], r15
0x180016fc1  mov     r14d, r8d
0x180016fc4  mov     rbx, rdx
0x180016fc7  mov     rsi, rcx
0x180016fca  movups  [rbp+170h+var_1C8], xmm0
0x180016fce  test    rdx, rdx
0x180016fd1  jz      loc_180017285
0x180016fd7  lea     rdx, GUID_NULL
0x180016fde  call    InlineIsEqualGUID
0x180016fe3  test    eax, eax
0x180016fe5  jnz     loc_180017285
0x180016feb  lea     rax, [rsp+270h+var_208]
0x180016ff0  xor     edx, edx; pUnkOuter
0x180016ff2  lea     r12d, [r15+1]
0x180016ff6  mov     [rsp+270h+ppv], rax; ppv
0x180016ffb  mov     r8d, r12d; dwClsContext
0x180016ffe  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180017005  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18001700c  call    cs:__imp_CoCreateInstance
0x180017012  test    eax, eax
0x180017014  js      loc_180017285
0x18001701a  cmp     [rbx], r15d
0x18001701d  jz      short loc_18001707C
0x18001701f  mov     rax, [rbx+8]
0x180017023  lea     r9, [rbp+170h+var_1C8]
0x180017027  mov     rcx, [rsp+270h+var_208]
0x18001702c  mov     r8d, r12d
0x18001702f  mov     rdx, rsi
0x180017032  movups  xmm0, xmmword ptr [rax]
0x180017035  movdqu  [rbp+170h+var_1C8], xmm0
0x18001703a  mov     rax, [rcx]
0x18001703d  test    r14d, r14d
0x180017040  jz      short loc_180017062
0x180017042  cmp     [rbx], r12d
0x180017045  jnz     short loc_18001704D
0x180017047  mov     rax, [rax+28h]
0x18001704b  jmp     short loc_180017051
0x18001704d  mov     rax, [rax+38h]
0x180017051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017056  mov     edi, eax
0x180017058  test    eax, eax
0x18001705a  js      loc_180017288
0x180017060  jmp     short loc_180017076
0x180017062  cmp     [rbx], r12d
0x180017065  jnz     short loc_18001706D
0x180017067  mov     rax, [rax+30h]
0x18001706b  jmp     short loc_180017071
0x18001706d  mov     rax, [rax+40h]
0x180017071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017076  add     rbx, 10h
0x18001707a  jmp     short loc_18001701A
0x18001707c  test    r14d, r14d
0x18001707f  jnz     loc_180017285
0x180017085  lea     r8d, [r14+40h]; cchMax
0x180017089  mov     rcx, rsi; rguid
0x18001708c  lea     rdx, [rbp+170h+sz]; lpsz
0x180017093  call    cs:__imp_StringFromGUID2
0x180017099  mov     esi, 80h
0x18001709e  mov     [rbp+170h+var_1D0], r15
0x1800170a2  mov     edx, esi
0x1800170a4  lea     r8, aClsid; "CLSID\\"
0x1800170ab  lea     rcx, [rbp+170h+SubKey]
0x1800170af  call    cs:__imp__o_wcscpy_s
0x1800170b5  mov     ecx, eax; int
0x1800170b7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800170bc  lea     r8, [rbp+170h+sz]
0x1800170c3  mov     edx, esi
0x1800170c5  lea     rcx, [rbp+170h+SubKey]
0x1800170c9  call    cs:__imp__o_wcscat_s
0x1800170cf  mov     ecx, eax; int
0x1800170d1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800170d6  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800170dd  mov     edx, esi
0x1800170df  lea     rcx, [rbp+170h+SubKey]
0x1800170e3  call    cs:__imp__o_wcscat_s
0x1800170e9  mov     ecx, eax; int
0x1800170eb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800170f0  mov     rdi, 0FFFFFFFF80000000h
0x1800170f7  mov     [rbp+170h+var_1E0], r15
0x1800170fb  mov     r14d, 20019h
0x180017101  mov     [rbp+170h+var_1E8], rdi
0x180017105  mov     r9d, r14d; unsigned int
0x180017108  mov     [rbp+170h+var_1D8], r15
0x18001710c  mov     rdx, rdi; hKey
0x18001710f  mov     [rsp+270h+hKey], r15
0x180017114  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180017118  mov     [rsp+270h+var_1F8], r15
0x18001711d  lea     rcx, [rsp+270h+hKey]; this
0x180017122  mov     [rbp+170h+var_1F0], r15
0x180017126  mov     [rsp+270h+cSubKeys], r15d
0x18001712b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180017130  test    eax, eax
0x180017132  jnz     short loc_18001719C
0x180017134  mov     rcx, [rsp+270h+hKey]; hKey
0x180017139  lea     rax, [rsp+270h+cSubKeys]
0x18001713e  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180017143  xor     r9d, r9d; lpReserved
0x180017146  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001714b  xor     r8d, r8d; lpcchClass
0x18001714e  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180017153  xor     edx, edx; lpClass
0x180017155  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001715a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001715f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017164  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180017169  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001716e  call    cs:__imp_RegQueryInfoKeyW
0x180017174  lea     rcx, [rsp+270h+hKey]; this
0x180017179  mov     ebx, eax
0x18001717b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017180  test    ebx, ebx
0x180017182  jnz     short loc_18001719C
0x180017184  cmp     [rsp+270h+cSubKeys], r15d
0x180017189  jnz     short loc_18001719C
0x18001718b  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18001718f  lea     rcx, [rbp+170h+var_1E8]; this
0x180017193  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180017198  mov     rdi, [rbp+170h+var_1E8]
0x18001719c  lea     r8, aClsid; "CLSID\\"
0x1800171a3  mov     rdx, rsi
0x1800171a6  lea     rcx, [rbp+170h+SubKey]
0x1800171aa  call    cs:__imp__o_wcscpy_s
0x1800171b0  mov     ecx, eax; int
0x1800171b2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800171b7  lea     r8, [rbp+170h+sz]
0x1800171be  mov     rdx, rsi
0x1800171c1  lea     rcx, [rbp+170h+SubKey]
0x1800171c5  call    cs:__imp__o_wcscat_s
0x1800171cb  mov     ecx, eax; int
0x1800171cd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800171d2  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800171d9  mov     rdx, rsi
0x1800171dc  lea     rcx, [rbp+170h+SubKey]
0x1800171e0  call    cs:__imp__o_wcscat_s
0x1800171e6  mov     ecx, eax; int
0x1800171e8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800171ed  mov     r9d, r14d; unsigned int
0x1800171f0  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800171f4  mov     rdx, rdi; hKey
0x1800171f7  lea     rcx, [rsp+270h+hKey]; this
0x1800171fc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180017201  test    eax, eax
0x180017203  jnz     short loc_180017269
0x180017205  mov     rcx, [rsp+270h+hKey]; hKey
0x18001720a  lea     rax, [rsp+270h+cSubKeys]
0x18001720f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180017214  xor     r9d, r9d; lpReserved
0x180017217  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001721c  xor     r8d, r8d; lpcchClass
0x18001721f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180017224  xor     edx, edx; lpClass
0x180017226  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001722b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180017230  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017235  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001723a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001723f  call    cs:__imp_RegQueryInfoKeyW
0x180017245  lea     rcx, [rsp+270h+hKey]; this
0x18001724a  mov     ebx, eax
0x18001724c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017251  test    ebx, ebx
0x180017253  jnz     short loc_180017269
0x180017255  cmp     [rsp+270h+cSubKeys], r15d
0x18001725a  jnz     short loc_180017269
0x18001725c  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180017260  lea     rcx, [rbp+170h+var_1E8]; this
0x180017264  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180017269  lea     rcx, [rsp+270h+hKey]; this
0x18001726e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017273  lea     rcx, [rbp+170h+var_1E8]; this
0x180017277  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001727c  lea     rcx, [rbp+170h+var_1D0]
0x180017280  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017285  mov     edi, r15d
0x180017288  lea     rcx, [rsp+270h+var_208]
0x18001728d  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180017292  mov     eax, edi
0x180017294  mov     rcx, [rbp+170h+var_30]
0x18001729b  xor     rcx, rsp; StackCookie
0x18001729e  call    __security_check_cookie
0x1800172a3  lea     r11, [rsp+270h+var_20]
0x1800172ab  mov     rbx, [r11+40h]
0x1800172af  mov     rsi, [r11+48h]
0x1800172b3  mov     rsp, r11
0x1800172b6  pop     r15
0x1800172b8  pop     r14
0x1800172ba  pop     r12
0x1800172bc  pop     rdi
0x1800172bd  pop     rbp
0x1800172be  retn
```
