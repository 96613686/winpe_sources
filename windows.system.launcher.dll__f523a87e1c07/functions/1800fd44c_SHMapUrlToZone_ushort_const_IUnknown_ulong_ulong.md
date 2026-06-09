# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x1800fd44c`
- end: `0x1800fd646`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `506`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d970`
- `0x1800fdb44`

## callees

- `0x18006323c`
- `0x1800fc4cc`
- `0x1800fd44c`
- `0x1800fddc4`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fd4e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fd4e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800fd4ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800fd4ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fd563`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fd5e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fd563`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fd5e8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fd4b1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fd5c1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fd4b1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fd5c1`

## string_xrefs

- `0x1800fd4dd`: `CoInternetCreateSecurityManager`
- `0x1800fd4c7`: `urlmon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  void *v8; // rcx
  void *v9; // rcx
  HRESULT v10; // ebx
  void *v11; // rcx
  HMODULE v13; // [rsp+50h] [rbp+20h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+28h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v13 = 0;
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoInternetCreateSecurityManager");
        if ( ProcAddress )
        {
          v8 = ppvOut;
          ppvOut = 0;
          if ( v8 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( ((int (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(0, &ppvOut, 0) >= 0 )
            goto LABEL_13;
        }
      }
      v9 = ppvOut;
      ppvOut = 0;
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      v10 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut);
      if ( v10 >= 0 )
LABEL_13:
        v10 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0
        || (v10 = CoCreateInstance(
                    &CLSID_InternetSecurityManager,
                    0,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &ppvOut),
            v10 >= 0) )
      {
        v10 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
        v11 = ppvOut;
        ppvOut = 0;
        if ( v11 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800fd44c  mov     [rsp-18h+arg_10], rbx
0x1800fd451  mov     [rsp-18h+ppvOut], rdx
0x1800fd456  push    rbp
0x1800fd457  push    rsi
0x1800fd458  push    r14
0x1800fd45a  mov     rbp, rsp
0x1800fd45d  sub     rsp, 30h
0x1800fd461  mov     rsi, r9
0x1800fd464  mov     r14, rcx
0x1800fd467  test    rcx, rcx
0x1800fd46a  jz      loc_1800FD631
0x1800fd470  test    r9, r9
0x1800fd473  jz      loc_1800FD631
0x1800fd479  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x1800fd480  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x1800fd485  test    al, al
0x1800fd487  jz      loc_1800FD5A5
0x1800fd48d  mov     [rbp+arg_0], 0
0x1800fd495  mov     [rbp+ppvOut], 0
0x1800fd49d  lea     r9, [rbp+ppvOut]; ppvOut
0x1800fd4a1  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800fd4a8  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800fd4af  xor     ecx, ecx; punk
0x1800fd4b1  call    cs:__imp_IUnknown_QueryService
0x1800fd4b7  test    eax, eax
0x1800fd4b9  jns     loc_1800FD56F
0x1800fd4bf  xor     edx, edx; hFile
0x1800fd4c1  mov     r8d, 800h; dwFlags
0x1800fd4c7  lea     rcx, aUrlmonDll; "urlmon.dll"
0x1800fd4ce  call    cs:__imp_LoadLibraryExW
0x1800fd4d4  mov     [rbp+arg_0], rax
0x1800fd4d8  test    rax, rax
0x1800fd4db  jz      short loc_1800FD528
0x1800fd4dd  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x1800fd4e4  mov     rcx, rax; hModule
0x1800fd4e7  call    cs:__imp_GetProcAddress
0x1800fd4ed  mov     rbx, rax
0x1800fd4f0  test    rax, rax
0x1800fd4f3  jz      short loc_1800FD528
0x1800fd4f5  mov     rcx, [rbp+ppvOut]
0x1800fd4f9  mov     [rbp+ppvOut], 0
0x1800fd501  test    rcx, rcx
0x1800fd504  jz      short loc_1800FD513
0x1800fd506  mov     rdx, [rcx]
0x1800fd509  mov     rax, [rdx+10h]
0x1800fd50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd512  nop
0x1800fd513  xor     r8d, r8d
0x1800fd516  lea     rdx, [rbp+ppvOut]
0x1800fd51a  xor     ecx, ecx
0x1800fd51c  mov     rax, rbx
0x1800fd51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd524  test    eax, eax
0x1800fd526  jns     short loc_1800FD56F
0x1800fd528  mov     rcx, [rbp+ppvOut]
0x1800fd52c  mov     [rbp+ppvOut], 0
0x1800fd534  test    rcx, rcx
0x1800fd537  jz      short loc_1800FD546
0x1800fd539  mov     rax, [rcx]
0x1800fd53c  mov     rax, [rax+10h]
0x1800fd540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd545  nop
0x1800fd546  lea     rax, [rbp+ppvOut]
0x1800fd54a  mov     [rsp+30h+ppv], rax; ppv
0x1800fd54f  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800fd556  xor     edx, edx; pUnkOuter
0x1800fd558  lea     r8d, [rdx+1]; dwClsContext
0x1800fd55c  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800fd563  call    cs:__imp_CoCreateInstance
0x1800fd569  mov     ebx, eax
0x1800fd56b  test    eax, eax
0x1800fd56d  js      short loc_1800FD58D
0x1800fd56f  mov     rcx, [rbp+ppvOut]
0x1800fd573  mov     rax, [rcx]
0x1800fd576  mov     r9d, 1
0x1800fd57c  mov     r8, rsi
0x1800fd57f  mov     rdx, r14
0x1800fd582  mov     rax, [rax+28h]
0x1800fd586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd58b  mov     ebx, eax
0x1800fd58d  lea     rcx, [rbp+ppvOut]
0x1800fd591  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800fd596  nop
0x1800fd597  lea     rcx, [rbp+arg_0]
0x1800fd59b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800fd5a0  jmp     loc_1800FD636
0x1800fd5a5  mov     [rbp+ppvOut], 0
0x1800fd5ad  lea     r9, [rbp+ppvOut]; ppvOut
0x1800fd5b1  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800fd5b8  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800fd5bf  xor     ecx, ecx; punk
0x1800fd5c1  call    cs:__imp_IUnknown_QueryService
0x1800fd5c7  test    eax, eax
0x1800fd5c9  jns     short loc_1800FD5F4
0x1800fd5cb  lea     rax, [rbp+ppvOut]
0x1800fd5cf  mov     [rsp+30h+ppv], rax; ppv
0x1800fd5d4  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800fd5db  xor     edx, edx; pUnkOuter
0x1800fd5dd  lea     r8d, [rdx+1]; dwClsContext
0x1800fd5e1  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800fd5e8  call    cs:__imp_CoCreateInstance
0x1800fd5ee  mov     ebx, eax
0x1800fd5f0  test    eax, eax
0x1800fd5f2  js      short loc_1800FD636
0x1800fd5f4  mov     rcx, [rbp+ppvOut]
0x1800fd5f8  mov     rax, [rcx]
0x1800fd5fb  mov     r9d, 1
0x1800fd601  mov     r8, rsi
0x1800fd604  mov     rdx, r14
0x1800fd607  mov     rax, [rax+28h]
0x1800fd60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd610  mov     ebx, eax
0x1800fd612  mov     rcx, [rbp+ppvOut]
0x1800fd616  mov     [rbp+ppvOut], 0
0x1800fd61e  test    rcx, rcx
0x1800fd621  jz      short loc_1800FD636
0x1800fd623  mov     rax, [rcx]
0x1800fd626  mov     rax, [rax+10h]
0x1800fd62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd62f  jmp     short loc_1800FD636
0x1800fd631  mov     ebx, 80070057h
0x1800fd636  mov     eax, ebx
0x1800fd638  mov     rbx, [rsp+30h+arg_10]
0x1800fd63d  add     rsp, 30h
0x1800fd641  pop     r14
0x1800fd643  pop     rsi
0x1800fd644  pop     rbp
0x1800fd645  retn
```
