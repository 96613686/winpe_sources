# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18001b7b0`
- end: `0x18001badf`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `815`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c014`
- `0x18001c194`

## callees

- `0x180001ec0`
- `0x18001b168`
- `0x18001b1c0`
- `0x18001b5a4`
- `0x18001b7b0`
- `0x18001bd50`
- `0x18001bd7c`
- `0x18001bf44`
- `0x18001bfb4`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b8f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b90f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b9e8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001ba03`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b8f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b90f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001b9e8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001ba03`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001b8db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001b9cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001b8db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001b9cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001b991`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ba5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001b991`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ba5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b838`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b838`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001b8bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001b8bf`

## string_xrefs

- `0x18001b8d0`: `CLSID\`
- `0x18001b9bf`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned int v13; // r9d
  LSTATUS v14; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r9d
  LSTATUS v19; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
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
    while ( *(_DWORD *)v4 )
    {
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v26);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v26);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v26);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, v13) )
      {
        v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v14 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
          v12 = (HKEY)v24[0];
        }
      }
      v15 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v16);
      v17 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v17);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, v18) )
      {
        v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v19 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
  }
  v8 = 0;
LABEL_26:
  wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x18001b7b0  mov     [rsp-8+arg_10], rbx
0x18001b7b5  mov     [rsp-8+arg_18], rsi
0x18001b7ba  push    rbp
0x18001b7bb  push    rdi
0x18001b7bc  push    r12
0x18001b7be  push    r14
0x18001b7c0  push    r15
0x18001b7c2  lea     rbp, [rsp-150h]
0x18001b7ca  sub     rsp, 250h
0x18001b7d1  mov     rax, cs:__security_cookie
0x18001b7d8  xor     rax, rsp
0x18001b7db  mov     [rbp+170h+var_30], rax
0x18001b7e2  xor     r15d, r15d
0x18001b7e5  xorps   xmm0, xmm0
0x18001b7e8  mov     [rsp+270h+var_208], r15
0x18001b7ed  mov     r14d, r8d
0x18001b7f0  mov     rbx, rdx
0x18001b7f3  mov     rsi, rcx
0x18001b7f6  movups  [rbp+170h+var_1C8], xmm0
0x18001b7fa  test    rdx, rdx
0x18001b7fd  jz      loc_18001BAA5
0x18001b803  lea     rdx, GUID_NULL; struct _GUID *
0x18001b80a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001b80f  test    eax, eax
0x18001b811  jnz     loc_18001BAA5
0x18001b817  lea     rax, [rsp+270h+var_208]
0x18001b81c  xor     edx, edx; pUnkOuter
0x18001b81e  lea     r12d, [r15+1]
0x18001b822  mov     [rsp+270h+ppv], rax; ppv
0x18001b827  mov     r8d, r12d; dwClsContext
0x18001b82a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18001b831  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18001b838  call    cs:__imp_CoCreateInstance
0x18001b83e  test    eax, eax
0x18001b840  js      loc_18001BAA5
0x18001b846  cmp     [rbx], r15d
0x18001b849  jz      short loc_18001B8A8
0x18001b84b  mov     rax, [rbx+8]
0x18001b84f  lea     r9, [rbp+170h+var_1C8]
0x18001b853  mov     rcx, [rsp+270h+var_208]
0x18001b858  mov     r8d, r12d
0x18001b85b  mov     rdx, rsi
0x18001b85e  movups  xmm0, xmmword ptr [rax]
0x18001b861  movdqu  [rbp+170h+var_1C8], xmm0
0x18001b866  mov     rax, [rcx]
0x18001b869  test    r14d, r14d
0x18001b86c  jz      short loc_18001B88E
0x18001b86e  cmp     [rbx], r12d
0x18001b871  jnz     short loc_18001B879
0x18001b873  mov     rax, [rax+28h]
0x18001b877  jmp     short loc_18001B87D
0x18001b879  mov     rax, [rax+38h]
0x18001b87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b882  mov     edi, eax
0x18001b884  test    eax, eax
0x18001b886  js      loc_18001BAA8
0x18001b88c  jmp     short loc_18001B8A2
0x18001b88e  cmp     [rbx], r12d
0x18001b891  jnz     short loc_18001B899
0x18001b893  mov     rax, [rax+30h]
0x18001b897  jmp     short loc_18001B89D
0x18001b899  mov     rax, [rax+40h]
0x18001b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a2  add     rbx, 10h
0x18001b8a6  jmp     short loc_18001B846
0x18001b8a8  test    r14d, r14d
0x18001b8ab  jnz     loc_18001BAA5
0x18001b8b1  lea     r8d, [r14+40h]; cchMax
0x18001b8b5  mov     rcx, rsi; rguid
0x18001b8b8  lea     rdx, [rbp+170h+sz]; lpsz
0x18001b8bf  call    cs:__imp_StringFromGUID2
0x18001b8c5  mov     esi, 80h
0x18001b8ca  mov     [rbp+170h+var_1D0], r15
0x18001b8ce  mov     edx, esi
0x18001b8d0  lea     r8, aClsid; "CLSID\\"
0x18001b8d7  lea     rcx, [rbp+170h+SubKey]
0x18001b8db  call    cs:__imp__o_wcscpy_s
0x18001b8e1  mov     ecx, eax; int
0x18001b8e3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b8e8  lea     r8, [rbp+170h+sz]
0x18001b8ef  mov     edx, esi
0x18001b8f1  lea     rcx, [rbp+170h+SubKey]
0x18001b8f5  call    cs:__imp__o_wcscat_s
0x18001b8fb  mov     ecx, eax; int
0x18001b8fd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b902  lea     r8, aRequiredCatego; "\\Required Categories"
0x18001b909  mov     edx, esi
0x18001b90b  lea     rcx, [rbp+170h+SubKey]
0x18001b90f  call    cs:__imp__o_wcscat_s
0x18001b915  mov     ecx, eax; int
0x18001b917  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b91c  mov     rdi, 0FFFFFFFF80000000h
0x18001b923  mov     [rbp+170h+var_1E0], r15
0x18001b927  mov     rdx, rdi; hKey
0x18001b92a  mov     [rbp+170h+var_1E8], rdi
0x18001b92e  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18001b932  mov     [rbp+170h+var_1D8], r15
0x18001b936  lea     rcx, [rsp+270h+hKey]; this
0x18001b93b  mov     [rsp+270h+hKey], r15
0x18001b940  mov     [rsp+270h+var_1F8], r15
0x18001b945  mov     [rbp+170h+var_1F0], r15
0x18001b949  mov     [rsp+270h+cSubKeys], r15d
0x18001b94e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001b953  test    eax, eax
0x18001b955  jnz     short loc_18001B9BF
0x18001b957  mov     rcx, [rsp+270h+hKey]; hKey
0x18001b95c  lea     rax, [rsp+270h+cSubKeys]
0x18001b961  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001b966  xor     r9d, r9d; lpReserved
0x18001b969  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001b96e  xor     r8d, r8d; lpcchClass
0x18001b971  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001b976  xor     edx, edx; lpClass
0x18001b978  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001b97d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001b982  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001b987  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001b98c  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001b991  call    cs:__imp_RegQueryInfoKeyW
0x18001b997  lea     rcx, [rsp+270h+hKey]; this
0x18001b99c  mov     ebx, eax
0x18001b99e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001b9a3  test    ebx, ebx
0x18001b9a5  jnz     short loc_18001B9BF
0x18001b9a7  cmp     [rsp+270h+cSubKeys], r15d
0x18001b9ac  jnz     short loc_18001B9BF
0x18001b9ae  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18001b9b2  lea     rcx, [rbp+170h+var_1E8]; this
0x18001b9b6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001b9bb  mov     rdi, [rbp+170h+var_1E8]
0x18001b9bf  lea     r8, aClsid; "CLSID\\"
0x18001b9c6  mov     rdx, rsi
0x18001b9c9  lea     rcx, [rbp+170h+SubKey]
0x18001b9cd  call    cs:__imp__o_wcscpy_s
0x18001b9d3  mov     ecx, eax; int
0x18001b9d5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b9da  lea     r8, [rbp+170h+sz]
0x18001b9e1  mov     rdx, rsi
0x18001b9e4  lea     rcx, [rbp+170h+SubKey]
0x18001b9e8  call    cs:__imp__o_wcscat_s
0x18001b9ee  mov     ecx, eax; int
0x18001b9f0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b9f5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18001b9fc  mov     rdx, rsi
0x18001b9ff  lea     rcx, [rbp+170h+SubKey]
0x18001ba03  call    cs:__imp__o_wcscat_s
0x18001ba09  mov     ecx, eax; int
0x18001ba0b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001ba10  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18001ba14  mov     rdx, rdi; hKey
0x18001ba17  lea     rcx, [rsp+270h+hKey]; this
0x18001ba1c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ba21  test    eax, eax
0x18001ba23  jnz     short loc_18001BA89
0x18001ba25  mov     rcx, [rsp+270h+hKey]; hKey
0x18001ba2a  lea     rax, [rsp+270h+cSubKeys]
0x18001ba2f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001ba34  xor     r9d, r9d; lpReserved
0x18001ba37  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001ba3c  xor     r8d, r8d; lpcchClass
0x18001ba3f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001ba44  xor     edx, edx; lpClass
0x18001ba46  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001ba4b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001ba50  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001ba55  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001ba5a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001ba5f  call    cs:__imp_RegQueryInfoKeyW
0x18001ba65  lea     rcx, [rsp+270h+hKey]; this
0x18001ba6a  mov     ebx, eax
0x18001ba6c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ba71  test    ebx, ebx
0x18001ba73  jnz     short loc_18001BA89
0x18001ba75  cmp     [rsp+270h+cSubKeys], r15d
0x18001ba7a  jnz     short loc_18001BA89
0x18001ba7c  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18001ba80  lea     rcx, [rbp+170h+var_1E8]; this
0x18001ba84  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001ba89  lea     rcx, [rsp+270h+hKey]; this
0x18001ba8e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ba93  lea     rcx, [rbp+170h+var_1E8]; this
0x18001ba97  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ba9c  lea     rcx, [rbp+170h+var_1D0]
0x18001baa0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001baa5  mov     edi, r15d
0x18001baa8  lea     rcx, [rsp+270h+var_208]
0x18001baad  call    ??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)
0x18001bab2  mov     eax, edi
0x18001bab4  mov     rcx, [rbp+170h+var_30]
0x18001babb  xor     rcx, rsp; StackCookie
0x18001babe  call    __security_check_cookie
0x18001bac3  lea     r11, [rsp+270h+var_20]
0x18001bacb  mov     rbx, [r11+40h]
0x18001bacf  mov     rsi, [r11+48h]
0x18001bad3  mov     rsp, r11
0x18001bad6  pop     r15
0x18001bad8  pop     r14
0x18001bada  pop     r12
0x18001badc  pop     rdi
0x18001badd  pop     rbp
0x18001bade  retn
```
