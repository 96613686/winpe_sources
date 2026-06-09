# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x180043ab0`
- end: `0x180043c91`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `481`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d244`
- `0x180067cfc`

## callees

- `0x180036f50`
- `0x18003b124`
- `0x18004306c`
- `0x180043ab0`
- `0x180043e78`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180043b1b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180043c06`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180043b1b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180043c06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043b38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043b51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043b51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043bcb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043c2d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043bcb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043c2d`

## string_xrefs

- `0x180043b2b`: `urlmon.dll`
- `0x180043b47`: `CoInternetCreateSecurityManager`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, unsigned int a3, unsigned int *a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  void *v9; // rcx
  void *v10; // rcx
  HRESULT v11; // ebx
  HRESULT v12; // eax
  void *v13; // rcx
  HMODULE v15; // [rsp+30h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-18h] BYREF

  if ( a1 && a4 )
  {
    ppvOut = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(
                            &`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl,
                            a2) )
    {
      v15 = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v15 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoInternetCreateSecurityManager");
        if ( ProcAddress )
        {
          v9 = ppvOut;
          ppvOut = 0;
          if ( v9 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
          if ( ((int (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(0, &ppvOut, 0) >= 0 )
            goto LABEL_13;
        }
      }
      v10 = ppvOut;
      ppvOut = 0;
      if ( v10 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
      v11 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut);
      if ( v11 >= 0 )
LABEL_13:
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppvOut
                                                                                                  + 40LL))(
                ppvOut,
                a1,
                a4,
                a3);
      wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v15);
    }
    else if ( IUnknown_QueryService(
                0,
                &IID_IInternetSecurityManager,
                &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                &ppvOut) >= 0
           || (v11 = CoCreateInstance(
                       &CLSID_InternetSecurityManager,
                       0,
                       1u,
                       &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                       &ppvOut),
               v11 >= 0) )
    {
      v12 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppvOut
                                                                                                + 40LL))(
              ppvOut,
              a1,
              a4,
              a3);
      v13 = ppvOut;
      v11 = v12;
      ppvOut = 0;
      if ( v13 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180043ab0  push    rbp
0x180043ab2  push    rbx
0x180043ab3  push    rsi
0x180043ab4  push    rdi
0x180043ab5  push    r14
0x180043ab7  mov     rbp, rsp
0x180043aba  sub     rsp, 50h
0x180043abe  mov     rax, cs:__security_cookie
0x180043ac5  xor     rax, rsp
0x180043ac8  mov     [rbp+var_10], rax
0x180043acc  mov     rdi, r9
0x180043acf  mov     r14d, r8d
0x180043ad2  mov     rsi, rcx
0x180043ad5  test    rcx, rcx
0x180043ad8  jz      loc_180043C73
0x180043ade  test    r9, r9
0x180043ae1  jz      loc_180043C73
0x180043ae7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x180043aee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x180043af3  xor     ecx, ecx; punk
0x180043af5  mov     [rbp+ppvOut], 0
0x180043afd  lea     r9, [rbp+ppvOut]; ppvOut
0x180043b01  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180043b08  lea     rdx, IID_IInternetSecurityManager; guidService
0x180043b0f  test    al, al
0x180043b11  jz      loc_180043C06
0x180043b17  mov     [rbp+var_20], rcx
0x180043b1b  call    cs:__imp_IUnknown_QueryService
0x180043b21  test    eax, eax
0x180043b23  jns     loc_180043BD7
0x180043b29  xor     edx, edx; hFile
0x180043b2b  lea     rcx, aUrlmonDll; "urlmon.dll"
0x180043b32  mov     r8d, 800h; dwFlags
0x180043b38  call    cs:__imp_LoadLibraryExW
0x180043b3e  mov     [rbp+var_20], rax
0x180043b42  test    rax, rax
0x180043b45  jz      short loc_180043B91
0x180043b47  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x180043b4e  mov     rcx, rax; hModule
0x180043b51  call    cs:__imp_GetProcAddress
0x180043b57  mov     rbx, rax
0x180043b5a  test    rax, rax
0x180043b5d  jz      short loc_180043B91
0x180043b5f  mov     rcx, [rbp+ppvOut]
0x180043b63  mov     [rbp+ppvOut], 0
0x180043b6b  test    rcx, rcx
0x180043b6e  jz      short loc_180043B7C
0x180043b70  mov     rdx, [rcx]
0x180043b73  mov     rax, [rdx+10h]
0x180043b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b7c  xor     r8d, r8d
0x180043b7f  lea     rdx, [rbp+ppvOut]
0x180043b83  xor     ecx, ecx
0x180043b85  mov     rax, rbx
0x180043b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b8d  test    eax, eax
0x180043b8f  jns     short loc_180043BD7
0x180043b91  mov     rcx, [rbp+ppvOut]
0x180043b95  mov     [rbp+ppvOut], 0
0x180043b9d  test    rcx, rcx
0x180043ba0  jz      short loc_180043BAE
0x180043ba2  mov     rax, [rcx]
0x180043ba5  mov     rax, [rax+10h]
0x180043ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bae  xor     edx, edx; pUnkOuter
0x180043bb0  lea     rax, [rbp+ppvOut]
0x180043bb4  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180043bbb  mov     [rsp+50h+ppv], rax; ppv
0x180043bc0  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180043bc7  lea     r8d, [rdx+1]; dwClsContext
0x180043bcb  call    cs:__imp_CoCreateInstance
0x180043bd1  mov     ebx, eax
0x180043bd3  test    eax, eax
0x180043bd5  js      short loc_180043BF2
0x180043bd7  mov     rcx, [rbp+ppvOut]
0x180043bdb  mov     r9d, r14d
0x180043bde  mov     r8, rdi
0x180043be1  mov     rdx, rsi
0x180043be4  mov     rax, [rcx]
0x180043be7  mov     rax, [rax+28h]
0x180043beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bf0  mov     ebx, eax
0x180043bf2  lea     rcx, [rbp+ppvOut]
0x180043bf6  call    ??1?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(void)
0x180043bfb  lea     rcx, [rbp+var_20]
0x180043bff  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180043c04  jmp     short loc_180043C78
0x180043c06  call    cs:__imp_IUnknown_QueryService
0x180043c0c  test    eax, eax
0x180043c0e  jns     short loc_180043C39
0x180043c10  xor     edx, edx; pUnkOuter
0x180043c12  lea     rax, [rbp+ppvOut]
0x180043c16  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180043c1d  mov     [rsp+50h+ppv], rax; ppv
0x180043c22  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180043c29  lea     r8d, [rdx+1]; dwClsContext
0x180043c2d  call    cs:__imp_CoCreateInstance
0x180043c33  mov     ebx, eax
0x180043c35  test    eax, eax
0x180043c37  js      short loc_180043C78
0x180043c39  mov     rcx, [rbp+ppvOut]
0x180043c3d  mov     r9d, r14d
0x180043c40  mov     r8, rdi
0x180043c43  mov     rdx, rsi
0x180043c46  mov     rax, [rcx]
0x180043c49  mov     rax, [rax+28h]
0x180043c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c52  mov     rcx, [rbp+ppvOut]
0x180043c56  mov     ebx, eax
0x180043c58  mov     [rbp+ppvOut], 0
0x180043c60  test    rcx, rcx
0x180043c63  jz      short loc_180043C78
0x180043c65  mov     rax, [rcx]
0x180043c68  mov     rax, [rax+10h]
0x180043c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c71  jmp     short loc_180043C78
0x180043c73  mov     ebx, 80070057h
0x180043c78  mov     eax, ebx
0x180043c7a  mov     rcx, [rbp+var_10]
0x180043c7e  xor     rcx, rsp; StackCookie
0x180043c81  call    __security_check_cookie
0x180043c86  add     rsp, 50h
0x180043c8a  pop     r14
0x180043c8c  pop     rdi
0x180043c8d  pop     rsi
0x180043c8e  pop     rbx
0x180043c8f  pop     rbp
0x180043c90  retn
```
