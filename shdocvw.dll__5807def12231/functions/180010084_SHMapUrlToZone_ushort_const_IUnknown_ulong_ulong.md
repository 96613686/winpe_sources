# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x180010084`
- end: `0x18001027a`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `502`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f1e0`
- `0x1800115bc`

## callees

- `0x180002240`
- `0x1800065e4`
- `0x18000cb2c`
- `0x180010084`
- `0x1800117d0`
- `0x180029010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800100e8`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800101f7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800100e8`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800101f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001011e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001011e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010105`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010105`

## string_xrefs

- `0x1800100fe`: `urlmon.dll`
- `0x180010114`: `CoInternetCreateSecurityManager`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  HMODULE Library; // rax
  struct IUnknown *v7; // rdx
  FARPROC ProcAddress; // rbx
  void *v9; // rcx
  void *v10; // rcx
  int v11; // ebx
  struct IUnknown *v12; // rdx
  void *v13; // rcx
  HMODULE v15; // [rsp+50h] [rbp+20h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+28h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v15 = 0;
      ppvOut = 0;
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
      v11 = IECreateInstance(
              &CLSID_InternetSecurityManager,
              v7,
              1u,
              &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
              &ppvOut);
      if ( v11 >= 0 )
LABEL_13:
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1024);
      wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v15);
    }
    else
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0
        || (v11 = IECreateInstance(
                    &CLSID_InternetSecurityManager,
                    v12,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &ppvOut),
            v11 >= 0) )
      {
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1024);
        v13 = ppvOut;
        ppvOut = 0;
        if ( v13 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
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
0x180010084  mov     [rsp-18h+arg_10], rbx
0x180010089  mov     [rsp-18h+ppvOut], rdx
0x18001008e  push    rbp
0x18001008f  push    rsi
0x180010090  push    rdi
0x180010091  mov     rbp, rsp
0x180010094  sub     rsp, 30h
0x180010098  mov     rdi, r9
0x18001009b  mov     rsi, rcx
0x18001009e  test    rcx, rcx
0x1800100a1  jz      loc_180010266
0x1800100a7  test    r9, r9
0x1800100aa  jz      loc_180010266
0x1800100b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x1800100b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x1800100bc  test    al, al
0x1800100be  jz      loc_1800101DB
0x1800100c4  mov     [rbp+arg_0], 0
0x1800100cc  mov     [rbp+ppvOut], 0
0x1800100d4  lea     r9, [rbp+ppvOut]; ppvOut
0x1800100d8  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800100df  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800100e6  xor     ecx, ecx; punk
0x1800100e8  call    cs:__imp_IUnknown_QueryService
0x1800100ee  test    eax, eax
0x1800100f0  jns     loc_1800101A5
0x1800100f6  xor     edx, edx; hFile
0x1800100f8  mov     r8d, 800h; dwFlags
0x1800100fe  lea     rcx, aUrlmonDll_0; "urlmon.dll"
0x180010105  call    cs:__imp_LoadLibraryExW
0x18001010b  mov     [rbp+arg_0], rax
0x18001010f  test    rax, rax
0x180010112  jz      short loc_18001015F
0x180010114  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x18001011b  mov     rcx, rax; hModule
0x18001011e  call    cs:__imp_GetProcAddress
0x180010124  mov     rbx, rax
0x180010127  test    rax, rax
0x18001012a  jz      short loc_18001015F
0x18001012c  mov     rcx, [rbp+ppvOut]
0x180010130  mov     [rbp+ppvOut], 0
0x180010138  test    rcx, rcx
0x18001013b  jz      short loc_18001014A
0x18001013d  mov     rdx, [rcx]
0x180010140  mov     rax, [rdx+10h]
0x180010144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010149  nop
0x18001014a  xor     r8d, r8d
0x18001014d  lea     rdx, [rbp+ppvOut]
0x180010151  xor     ecx, ecx
0x180010153  mov     rax, rbx
0x180010156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001015b  test    eax, eax
0x18001015d  jns     short loc_1800101A5
0x18001015f  mov     rcx, [rbp+ppvOut]
0x180010163  mov     [rbp+ppvOut], 0
0x18001016b  test    rcx, rcx
0x18001016e  jz      short loc_18001017D
0x180010170  mov     rax, [rcx]
0x180010173  mov     rax, [rax+10h]
0x180010177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017c  nop
0x18001017d  lea     rax, [rbp+ppvOut]
0x180010181  mov     [rsp+30h+var_10], rax; void **
0x180010186  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x18001018d  mov     r8d, 1; unsigned int
0x180010193  lea     rcx, CLSID_InternetSecurityManager; struct _GUID *
0x18001019a  call    ?IECreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; IECreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18001019f  mov     ebx, eax
0x1800101a1  test    eax, eax
0x1800101a3  js      short loc_1800101C3
0x1800101a5  mov     rcx, [rbp+ppvOut]
0x1800101a9  mov     rax, [rcx]
0x1800101ac  mov     r9d, 400h
0x1800101b2  mov     r8, rdi
0x1800101b5  mov     rdx, rsi
0x1800101b8  mov     rax, [rax+28h]
0x1800101bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c1  mov     ebx, eax
0x1800101c3  lea     rcx, [rbp+ppvOut]
0x1800101c7  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x1800101cc  nop
0x1800101cd  lea     rcx, [rbp+arg_0]
0x1800101d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800101d6  jmp     loc_18001026B
0x1800101db  mov     [rbp+ppvOut], 0
0x1800101e3  lea     r9, [rbp+ppvOut]; ppvOut
0x1800101e7  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800101ee  lea     rdx, IID_IInternetSecurityManager; guidService
0x1800101f5  xor     ecx, ecx; punk
0x1800101f7  call    cs:__imp_IUnknown_QueryService
0x1800101fd  test    eax, eax
0x1800101ff  jns     short loc_180010229
0x180010201  lea     rax, [rbp+ppvOut]
0x180010205  mov     [rsp+30h+var_10], rax; void **
0x18001020a  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x180010211  mov     r8d, 1; unsigned int
0x180010217  lea     rcx, CLSID_InternetSecurityManager; struct _GUID *
0x18001021e  call    ?IECreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; IECreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180010223  mov     ebx, eax
0x180010225  test    eax, eax
0x180010227  js      short loc_18001026B
0x180010229  mov     rcx, [rbp+ppvOut]
0x18001022d  mov     rax, [rcx]
0x180010230  mov     r9d, 400h
0x180010236  mov     r8, rdi
0x180010239  mov     rdx, rsi
0x18001023c  mov     rax, [rax+28h]
0x180010240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010245  mov     ebx, eax
0x180010247  mov     rcx, [rbp+ppvOut]
0x18001024b  mov     [rbp+ppvOut], 0
0x180010253  test    rcx, rcx
0x180010256  jz      short loc_18001026B
0x180010258  mov     rax, [rcx]
0x18001025b  mov     rax, [rax+10h]
0x18001025f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010264  jmp     short loc_18001026B
0x180010266  mov     ebx, 80070057h
0x18001026b  mov     eax, ebx
0x18001026d  mov     rbx, [rsp+30h+arg_10]
0x180010272  add     rsp, 30h
0x180010276  pop     rdi
0x180010277  pop     rsi
0x180010278  pop     rbp
0x180010279  retn
```
