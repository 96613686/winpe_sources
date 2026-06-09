# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18001dde0`
- end: `0x18001e023`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `579`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e02c`

## callees

- `0x18001dde0`
- `0x18001eeb4`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001de45`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001df8b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001de45`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001df8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001de68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001de68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001df5e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001df5e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dfb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dfb8`

## string_xrefs

- `0x18001de61`: `urlmon.dll`
- `0x18001de80`: `CoInternetCreateSecurityManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  HMODULE v6; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  void *v9; // rcx
  void *v10; // rcx
  HRESULT v11; // edi
  void *v12; // rcx
  void *ppvOut; // [rsp+58h] [rbp+28h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v6 = 0;
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v6 = Library;
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
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
      if ( ppvOut )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      if ( v6 )
        FreeLibrary(v6);
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
        v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
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
0x18001dde0  mov     [rsp-18h+arg_10], rbx
0x18001dde5  mov     [rsp-18h+arg_18], rdi
0x18001ddea  mov     [rsp-18h+ppvOut], rdx
0x18001ddef  push    rbp
0x18001ddf0  push    r14
0x18001ddf2  push    r15
0x18001ddf4  mov     rbp, rsp
0x18001ddf7  sub     rsp, 30h
0x18001ddfb  mov     r14, r9
0x18001ddfe  mov     r15, rcx
0x18001de01  test    rcx, rcx
0x18001de04  jz      loc_18001E007
0x18001de0a  test    r9, r9
0x18001de0d  jz      loc_18001E007
0x18001de13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x18001de1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x18001de1f  test    al, al
0x18001de21  jz      loc_18001DF6F
0x18001de27  xor     ebx, ebx
0x18001de29  mov     [rbp+arg_0], rbx
0x18001de2d  mov     [rbp+ppvOut], rbx
0x18001de31  lea     r9, [rbp+ppvOut]; ppvOut
0x18001de35  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001de3c  lea     rdx, IID_IInternetSecurityManager; guidService
0x18001de43  xor     ecx, ecx; punk
0x18001de45  call    cs:__imp_IUnknown_QueryService
0x18001de4c  nop     dword ptr [rax+rax+00h]
0x18001de51  test    eax, eax
0x18001de53  jns     loc_18001DF1E
0x18001de59  xor     edx, edx; hFile
0x18001de5b  mov     r8d, 800h; dwFlags
0x18001de61  lea     rcx, LibFileName; "urlmon.dll"
0x18001de68  call    cs:__imp_LoadLibraryExW
0x18001de6f  nop     dword ptr [rax+rax+00h]
0x18001de74  mov     rbx, rax
0x18001de77  mov     [rbp+arg_0], rax
0x18001de7b  test    rax, rax
0x18001de7e  jz      short loc_18001DED1
0x18001de80  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x18001de87  mov     rcx, rax; hModule
0x18001de8a  call    cs:__imp_GetProcAddress
0x18001de91  nop     dword ptr [rax+rax+00h]
0x18001de96  mov     rdi, rax
0x18001de99  test    rax, rax
0x18001de9c  jz      short loc_18001DED1
0x18001de9e  mov     rcx, [rbp+ppvOut]
0x18001dea2  mov     [rbp+ppvOut], 0
0x18001deaa  test    rcx, rcx
0x18001dead  jz      short loc_18001DEBC
0x18001deaf  mov     rdx, [rcx]
0x18001deb2  mov     rax, [rdx+10h]
0x18001deb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001debb  nop
0x18001debc  xor     r8d, r8d
0x18001debf  lea     rdx, [rbp+ppvOut]
0x18001dec3  xor     ecx, ecx
0x18001dec5  mov     rax, rdi
0x18001dec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001decd  test    eax, eax
0x18001decf  jns     short loc_18001DF1E
0x18001ded1  mov     rcx, [rbp+ppvOut]
0x18001ded5  mov     [rbp+ppvOut], 0
0x18001dedd  test    rcx, rcx
0x18001dee0  jz      short loc_18001DEEF
0x18001dee2  mov     rax, [rcx]
0x18001dee5  mov     rax, [rax+10h]
0x18001dee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deee  nop
0x18001deef  lea     rax, [rbp+ppvOut]
0x18001def3  mov     [rsp+30h+ppv], rax; ppv
0x18001def8  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001deff  xor     edx, edx; pUnkOuter
0x18001df01  lea     r8d, [rdx+1]; dwClsContext
0x18001df05  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18001df0c  call    cs:__imp_CoCreateInstance
0x18001df13  nop     dword ptr [rax+rax+00h]
0x18001df18  mov     edi, eax
0x18001df1a  test    eax, eax
0x18001df1c  js      short loc_18001DF3C
0x18001df1e  mov     rcx, [rbp+ppvOut]
0x18001df22  mov     rax, [rcx]
0x18001df25  mov     r9d, 1
0x18001df2b  mov     r8, r14
0x18001df2e  mov     rdx, r15
0x18001df31  mov     rax, [rax+28h]
0x18001df35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df3a  mov     edi, eax
0x18001df3c  mov     rcx, [rbp+ppvOut]
0x18001df40  test    rcx, rcx
0x18001df43  jz      short loc_18001DF52
0x18001df45  mov     rax, [rcx]
0x18001df48  mov     rax, [rax+10h]
0x18001df4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df51  nop
0x18001df52  test    rbx, rbx
0x18001df55  jz      loc_18001E00C
0x18001df5b  mov     rcx, rbx; hLibModule
0x18001df5e  call    cs:__imp_FreeLibrary
0x18001df65  nop     dword ptr [rax+rax+00h]
0x18001df6a  jmp     loc_18001E00C
0x18001df6f  mov     [rbp+ppvOut], 0
0x18001df77  lea     r9, [rbp+ppvOut]; ppvOut
0x18001df7b  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001df82  lea     rdx, IID_IInternetSecurityManager; guidService
0x18001df89  xor     ecx, ecx; punk
0x18001df8b  call    cs:__imp_IUnknown_QueryService
0x18001df92  nop     dword ptr [rax+rax+00h]
0x18001df97  test    eax, eax
0x18001df99  jns     short loc_18001DFCA
0x18001df9b  lea     rax, [rbp+ppvOut]
0x18001df9f  mov     [rsp+30h+ppv], rax; ppv
0x18001dfa4  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001dfab  xor     edx, edx; pUnkOuter
0x18001dfad  lea     r8d, [rdx+1]; dwClsContext
0x18001dfb1  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18001dfb8  call    cs:__imp_CoCreateInstance
0x18001dfbf  nop     dword ptr [rax+rax+00h]
0x18001dfc4  mov     edi, eax
0x18001dfc6  test    eax, eax
0x18001dfc8  js      short loc_18001E00C
0x18001dfca  mov     rcx, [rbp+ppvOut]
0x18001dfce  mov     rax, [rcx]
0x18001dfd1  mov     r9d, 1
0x18001dfd7  mov     r8, r14
0x18001dfda  mov     rdx, r15
0x18001dfdd  mov     rax, [rax+28h]
0x18001dfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfe6  mov     edi, eax
0x18001dfe8  mov     rcx, [rbp+ppvOut]
0x18001dfec  mov     [rbp+ppvOut], 0
0x18001dff4  test    rcx, rcx
0x18001dff7  jz      short loc_18001E00C
0x18001dff9  mov     rax, [rcx]
0x18001dffc  mov     rax, [rax+10h]
0x18001e000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e005  jmp     short loc_18001E00C
0x18001e007  mov     edi, 80070057h
0x18001e00c  mov     eax, edi
0x18001e00e  mov     rbx, [rsp+30h+arg_10]
0x18001e013  mov     rdi, [rsp+30h+arg_18]
0x18001e018  add     rsp, 30h
0x18001e01c  pop     r15
0x18001e01e  pop     r14
0x18001e020  pop     rbp
0x18001e021  retn
```
