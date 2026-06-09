# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180086578`
- end: `0x1800868b0`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `824`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008792c`
- `0x180088174`
- `0x1800887e0`

## callees

- `0x18004d580`
- `0x180052ea8`
- `0x180080fb0`
- `0x180085820`
- `0x1800864f0`
- `0x180086578`
- `0x1800869f4`
- `0x180086cd8`
- `0x180087100`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800866ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800866d4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800867b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800867d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800866ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800866d4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800867b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800867d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800866a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008679c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800866a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008679c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008675f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180086830`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008675f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180086830`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180086684`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180086684`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800865fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800865fe`

## string_xrefs

- `0x180086695`: `CLSID\`
- `0x18008678e`: `CLSID\`

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
  HKEY hKey[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
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
      v21 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v20[1] = 0;
      v20[0] = 0xFFFFFFFF80000000uLL;
      v20[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, SubKey);
          v12 = (HKEY)v20[0];
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
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v20);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    }
  }
  v8 = 0;
LABEL_26:
  wil::com_ptr_t<IUriBuilder,wil::err_exception_policy>::~com_ptr_t<IUriBuilder,wil::err_exception_policy>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180086578  mov     [rsp-8+arg_10], rbx
0x18008657d  mov     [rsp-8+arg_18], rsi
0x180086582  push    rbp
0x180086583  push    rdi
0x180086584  push    r12
0x180086586  push    r14
0x180086588  push    r15
0x18008658a  lea     rbp, [rsp-150h]
0x180086592  sub     rsp, 250h
0x180086599  mov     rax, cs:__security_cookie
0x1800865a0  xor     rax, rsp
0x1800865a3  mov     [rbp+170h+var_30], rax
0x1800865aa  xor     r15d, r15d
0x1800865ad  xorps   xmm0, xmm0
0x1800865b0  mov     [rbp+170h+var_1D0], r15
0x1800865b4  mov     r14d, r8d
0x1800865b7  mov     rbx, rdx
0x1800865ba  mov     rsi, rcx
0x1800865bd  movups  [rbp+170h+var_1C8], xmm0
0x1800865c1  test    rdx, rdx
0x1800865c4  jz      loc_180086877
0x1800865ca  lea     rdx, GUID_NULL; struct _GUID *
0x1800865d1  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800865d6  test    eax, eax
0x1800865d8  jnz     loc_180086877
0x1800865de  lea     rax, [rbp+170h+var_1D0]
0x1800865e2  xor     edx, edx; pUnkOuter
0x1800865e4  lea     r12d, [r15+1]
0x1800865e8  mov     [rsp+270h+ppv], rax; ppv
0x1800865ed  mov     r8d, r12d; dwClsContext
0x1800865f0  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800865f7  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800865fe  call    cs:__imp_CoCreateInstance
0x180086604  test    eax, eax
0x180086606  js      loc_180086877
0x18008660c  cmp     [rbx], r15d
0x18008660f  jz      short loc_18008666D
0x180086611  mov     rax, [rbx+8]
0x180086615  lea     r9, [rbp+170h+var_1C8]
0x180086619  mov     rcx, [rbp+170h+var_1D0]
0x18008661d  mov     r8d, r12d
0x180086620  mov     rdx, rsi
0x180086623  movups  xmm0, xmmword ptr [rax]
0x180086626  movdqu  [rbp+170h+var_1C8], xmm0
0x18008662b  mov     rax, [rcx]
0x18008662e  test    r14d, r14d
0x180086631  jz      short loc_180086653
0x180086633  cmp     [rbx], r12d
0x180086636  jnz     short loc_18008663E
0x180086638  mov     rax, [rax+28h]
0x18008663c  jmp     short loc_180086642
0x18008663e  mov     rax, [rax+38h]
0x180086642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086647  mov     edi, eax
0x180086649  test    eax, eax
0x18008664b  js      loc_18008687A
0x180086651  jmp     short loc_180086667
0x180086653  cmp     [rbx], r12d
0x180086656  jnz     short loc_18008665E
0x180086658  mov     rax, [rax+30h]
0x18008665c  jmp     short loc_180086662
0x18008665e  mov     rax, [rax+40h]
0x180086662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086667  add     rbx, 10h
0x18008666b  jmp     short loc_18008660C
0x18008666d  test    r14d, r14d
0x180086670  jnz     loc_180086877
0x180086676  lea     r8d, [r14+40h]; cchMax
0x18008667a  mov     rcx, rsi; rguid
0x18008667d  lea     rdx, [rbp+170h+sz]; lpsz
0x180086684  call    cs:__imp_StringFromGUID2
0x18008668a  mov     esi, 80h
0x18008668f  mov     [rbp+170h+var_1E0], r15
0x180086693  mov     edx, esi
0x180086695  lea     r8, aClsid; "CLSID\\"
0x18008669c  lea     rcx, [rbp+170h+SubKey]
0x1800866a0  call    cs:__imp__o_wcscpy_s
0x1800866a6  mov     ecx, eax; int
0x1800866a8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800866ad  lea     r8, [rbp+170h+sz]
0x1800866b4  mov     edx, esi
0x1800866b6  lea     rcx, [rbp+170h+SubKey]
0x1800866ba  call    cs:__imp__o_wcscat_s
0x1800866c0  mov     ecx, eax; int
0x1800866c2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800866c7  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800866ce  mov     edx, esi
0x1800866d0  lea     rcx, [rbp+170h+SubKey]
0x1800866d4  call    cs:__imp__o_wcscat_s
0x1800866da  mov     ecx, eax; int
0x1800866dc  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800866e1  mov     rdi, 0FFFFFFFF80000000h
0x1800866e8  mov     [rbp+170h+var_1F0], r15
0x1800866ec  mov     r14d, 20019h
0x1800866f2  mov     [rsp+270h+var_1F8], rdi
0x1800866f7  mov     r9d, r14d; unsigned int
0x1800866fa  mov     [rbp+170h+var_1E8], r15
0x1800866fe  mov     rdx, rdi; hKey
0x180086701  mov     [rsp+270h+hKey], r15
0x180086706  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18008670a  mov     [rsp+270h+var_208], r15
0x18008670f  lea     rcx, [rsp+270h+hKey]; this
0x180086714  mov     [rsp+270h+var_200], r15
0x180086719  mov     [rbp+170h+cSubKeys], r15d
0x18008671d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180086722  test    eax, eax
0x180086724  jnz     short loc_18008678E
0x180086726  mov     rcx, [rsp+270h+hKey]; hKey
0x18008672b  lea     rax, [rbp+170h+cSubKeys]
0x18008672f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180086734  xor     r9d, r9d; lpReserved
0x180086737  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18008673c  xor     r8d, r8d; lpcchClass
0x18008673f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180086744  xor     edx, edx; lpClass
0x180086746  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18008674b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180086750  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180086755  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18008675a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18008675f  call    cs:__imp_RegQueryInfoKeyW
0x180086765  lea     rcx, [rsp+270h+hKey]; this
0x18008676a  mov     ebx, eax
0x18008676c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180086771  test    ebx, ebx
0x180086773  jnz     short loc_18008678E
0x180086775  cmp     [rbp+170h+cSubKeys], r15d
0x180086779  jnz     short loc_18008678E
0x18008677b  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18008677f  lea     rcx, [rsp+270h+var_1F8]; this
0x180086784  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180086789  mov     rdi, [rsp+270h+var_1F8]
0x18008678e  lea     r8, aClsid; "CLSID\\"
0x180086795  mov     rdx, rsi
0x180086798  lea     rcx, [rbp+170h+SubKey]
0x18008679c  call    cs:__imp__o_wcscpy_s
0x1800867a2  mov     ecx, eax; int
0x1800867a4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800867a9  lea     r8, [rbp+170h+sz]
0x1800867b0  mov     rdx, rsi
0x1800867b3  lea     rcx, [rbp+170h+SubKey]
0x1800867b7  call    cs:__imp__o_wcscat_s
0x1800867bd  mov     ecx, eax; int
0x1800867bf  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800867c4  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800867cb  mov     rdx, rsi
0x1800867ce  lea     rcx, [rbp+170h+SubKey]
0x1800867d2  call    cs:__imp__o_wcscat_s
0x1800867d8  mov     ecx, eax; int
0x1800867da  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800867df  mov     r9d, r14d; unsigned int
0x1800867e2  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800867e6  mov     rdx, rdi; hKey
0x1800867e9  lea     rcx, [rsp+270h+hKey]; this
0x1800867ee  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800867f3  test    eax, eax
0x1800867f5  jnz     short loc_18008685A
0x1800867f7  mov     rcx, [rsp+270h+hKey]; hKey
0x1800867fc  lea     rax, [rbp+170h+cSubKeys]
0x180086800  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180086805  xor     r9d, r9d; lpReserved
0x180086808  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18008680d  xor     r8d, r8d; lpcchClass
0x180086810  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180086815  xor     edx, edx; lpClass
0x180086817  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18008681c  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180086821  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180086826  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18008682b  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180086830  call    cs:__imp_RegQueryInfoKeyW
0x180086836  lea     rcx, [rsp+270h+hKey]; this
0x18008683b  mov     ebx, eax
0x18008683d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180086842  test    ebx, ebx
0x180086844  jnz     short loc_18008685A
0x180086846  cmp     [rbp+170h+cSubKeys], r15d
0x18008684a  jnz     short loc_18008685A
0x18008684c  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180086850  lea     rcx, [rsp+270h+var_1F8]; this
0x180086855  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18008685a  lea     rcx, [rsp+270h+hKey]; this
0x18008685f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180086864  lea     rcx, [rsp+270h+var_1F8]; this
0x180086869  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18008686e  lea     rcx, [rbp+170h+var_1E0]
0x180086872  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180086877  mov     edi, r15d
0x18008687a  lea     rcx, [rbp+170h+var_1D0]
0x18008687e  call    ??1?$com_ptr_t@UIUriBuilder@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUriBuilder,wil::err_exception_policy>::~com_ptr_t<IUriBuilder,wil::err_exception_policy>(void)
0x180086883  mov     eax, edi
0x180086885  mov     rcx, [rbp+170h+var_30]
0x18008688c  xor     rcx, rsp; StackCookie
0x18008688f  call    __security_check_cookie
0x180086894  lea     r11, [rsp+270h+var_20]
0x18008689c  mov     rbx, [r11+40h]
0x1800868a0  mov     rsi, [r11+48h]
0x1800868a4  mov     rsp, r11
0x1800868a7  pop     r15
0x1800868a9  pop     r14
0x1800868ab  pop     r12
0x1800868ad  pop     rdi
0x1800868ae  pop     rbp
0x1800868af  retn
```
