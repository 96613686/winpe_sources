# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18005276c`
- end: `0x18005296d`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `513`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052974`
- `0x180057830`

## callees

- `0x180042fd8`
- `0x180051800`
- `0x18005276c`
- `0x180052f94`
- `0x18006d010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800527d9`
- `SHCORE!IUnknown_QueryService` at `0x1800528e6`
- `SHCORE!IUnknown_QueryService` at `0x1800527d9`
- `SHCORE!IUnknown_QueryService` at `0x1800528e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005280f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005280f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800527f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800527f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005288b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005290d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005288b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005290d`

## string_xrefs

- `0x1800527ef`: `urlmon.dll`
- `0x180052805`: `CoInternetCreateSecurityManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, unsigned int a3, unsigned int *a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  void *v9; // rcx
  void *v10; // rcx
  HRESULT v11; // ebx
  void *v12; // rcx
  HMODULE v14; // [rsp+50h] [rbp+20h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+28h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v14 = 0;
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v14 = Library;
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
      ATL::CComPtrBase<ISlideshowSettings>::~CComPtrBase<ISlideshowSettings>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
    }
    else
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0
        || (v11 = CoCreateInstance(
                    &CLSID_InternetSecurityManager,
                    0,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &ppvOut),
            v11 >= 0) )
      {
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppvOut
                                                                                                  + 40LL))(
                ppvOut,
                a1,
                a4,
                a3);
        v12 = ppvOut;
        ppvOut = 0;
        if ( v12 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
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
0x18005276c  mov     [rsp-18h+arg_10], rbx
0x180052771  mov     [rsp-18h+arg_18], rsi
0x180052776  mov     [rsp-18h+ppvOut], rdx
0x18005277b  push    rbp
0x18005277c  push    rdi
0x18005277d  push    r14
0x18005277f  mov     rbp, rsp
0x180052782  sub     rsp, 30h
0x180052786  mov     rdi, r9
0x180052789  mov     r14d, r8d
0x18005278c  mov     rsi, rcx
0x18005278f  test    rcx, rcx
0x180052792  jz      loc_180052953
0x180052798  test    r9, r9
0x18005279b  jz      loc_180052953
0x1800527a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x1800527a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x1800527ad  test    al, al
0x1800527af  jz      loc_1800528CA
0x1800527b5  mov     [rbp+arg_0], 0
0x1800527bd  mov     [rbp+ppvOut], 0
0x1800527c5  lea     r9, [rbp+ppvOut]; ppvOut
0x1800527c9  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800527d0  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800527d7  xor     ecx, ecx; punk
0x1800527d9  call    cs:__imp_IUnknown_QueryService
0x1800527df  test    eax, eax
0x1800527e1  jns     loc_180052897
0x1800527e7  xor     edx, edx; hFile
0x1800527e9  mov     r8d, 800h; dwFlags
0x1800527ef  lea     rcx, aUrlmonDll; "urlmon.dll"
0x1800527f6  call    cs:__imp_LoadLibraryExW
0x1800527fc  mov     [rbp+arg_0], rax
0x180052800  test    rax, rax
0x180052803  jz      short loc_180052850
0x180052805  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x18005280c  mov     rcx, rax; hModule
0x18005280f  call    cs:__imp_GetProcAddress
0x180052815  mov     rbx, rax
0x180052818  test    rax, rax
0x18005281b  jz      short loc_180052850
0x18005281d  mov     rcx, [rbp+ppvOut]
0x180052821  mov     [rbp+ppvOut], 0
0x180052829  test    rcx, rcx
0x18005282c  jz      short loc_18005283B
0x18005282e  mov     rdx, [rcx]
0x180052831  mov     rax, [rdx+10h]
0x180052835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005283a  nop
0x18005283b  xor     r8d, r8d
0x18005283e  lea     rdx, [rbp+ppvOut]
0x180052842  xor     ecx, ecx
0x180052844  mov     rax, rbx
0x180052847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005284c  test    eax, eax
0x18005284e  jns     short loc_180052897
0x180052850  mov     rcx, [rbp+ppvOut]
0x180052854  mov     [rbp+ppvOut], 0
0x18005285c  test    rcx, rcx
0x18005285f  jz      short loc_18005286E
0x180052861  mov     rax, [rcx]
0x180052864  mov     rax, [rax+10h]
0x180052868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005286d  nop
0x18005286e  lea     rax, [rbp+ppvOut]
0x180052872  mov     [rsp+30h+ppv], rax; ppv
0x180052877  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18005287e  xor     edx, edx; pUnkOuter
0x180052880  lea     r8d, [rdx+1]; dwClsContext
0x180052884  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18005288b  call    cs:__imp_CoCreateInstance
0x180052891  mov     ebx, eax
0x180052893  test    eax, eax
0x180052895  js      short loc_1800528B2
0x180052897  mov     rcx, [rbp+ppvOut]
0x18005289b  mov     rax, [rcx]
0x18005289e  mov     r9d, r14d
0x1800528a1  mov     r8, rdi
0x1800528a4  mov     rdx, rsi
0x1800528a7  mov     rax, [rax+28h]
0x1800528ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528b0  mov     ebx, eax
0x1800528b2  lea     rcx, [rbp+ppvOut]
0x1800528b6  call    ??1?$CComPtrBase@UISlideshowSettings@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISlideshowSettings>::~CComPtrBase<ISlideshowSettings>(void)
0x1800528bb  nop
0x1800528bc  lea     rcx, [rbp+arg_0]
0x1800528c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800528c5  jmp     loc_180052958
0x1800528ca  mov     [rbp+ppvOut], 0
0x1800528d2  lea     r9, [rbp+ppvOut]; ppvOut
0x1800528d6  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800528dd  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800528e4  xor     ecx, ecx; punk
0x1800528e6  call    cs:__imp_IUnknown_QueryService
0x1800528ec  test    eax, eax
0x1800528ee  jns     short loc_180052919
0x1800528f0  lea     rax, [rbp+ppvOut]
0x1800528f4  mov     [rsp+30h+ppv], rax; ppv
0x1800528f9  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180052900  xor     edx, edx; pUnkOuter
0x180052902  lea     r8d, [rdx+1]; dwClsContext
0x180052906  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18005290d  call    cs:__imp_CoCreateInstance
0x180052913  mov     ebx, eax
0x180052915  test    eax, eax
0x180052917  js      short loc_180052958
0x180052919  mov     rcx, [rbp+ppvOut]
0x18005291d  mov     rax, [rcx]
0x180052920  mov     r9d, r14d
0x180052923  mov     r8, rdi
0x180052926  mov     rdx, rsi
0x180052929  mov     rax, [rax+28h]
0x18005292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052932  mov     ebx, eax
0x180052934  mov     rcx, [rbp+ppvOut]
0x180052938  mov     [rbp+ppvOut], 0
0x180052940  test    rcx, rcx
0x180052943  jz      short loc_180052958
0x180052945  mov     rax, [rcx]
0x180052948  mov     rax, [rax+10h]
0x18005294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052951  jmp     short loc_180052958
0x180052953  mov     ebx, 80070057h
0x180052958  mov     eax, ebx
0x18005295a  mov     rbx, [rsp+30h+arg_10]
0x18005295f  mov     rsi, [rsp+30h+arg_18]
0x180052964  add     rsp, 30h
0x180052968  pop     r14
0x18005296a  pop     rdi
0x18005296b  pop     rbp
0x18005296c  retn
```
