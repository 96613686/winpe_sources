# RenameItemHelper(HWND__ *,IUnknown *,IShellItem *,ushort const *,ushort const *,ushort const *,ulong,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)

- ea: `0x1805cb330`
- end: `0x1805cb869`
- name: `?RenameItemHelper@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIShellItem@@PEBG33KW4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1337`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct IUnknown *@<rdx>, struct IShellItem *@<r8>, const unsigned __int16 *@<r9>, PCWSTR pszMore, const unsigned __int16 *, unsigned int, enum FOLDER_ENUM_MODE, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18052abe0`

## callees

- `0x180038f50`
- `0x1800783fc`
- `0x1800b5d60`
- `0x1800ee270`
- `0x1800f0a50`
- `0x180117f6c`
- `0x1801ac7c0`
- `0x1801ff4d0`
- `0x180210328`
- `0x18027dd3c`
- `0x180315e30`
- `0x1803b1f60`
- `0x18052dc04`
- `0x1805cab04`
- `0x1805cb330`
- `0x1805cb870`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1805cb5e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1805cb5e0`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1805cb555`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1805cb555`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805cb3a8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805cb717`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805cb3a8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805cb717`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805cb597`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805cb5b9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805cb597`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805cb5b9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805cb512`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805cb512`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb4b5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb6a1`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb810`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb4b5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb6a1`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805cb810`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocQueryKeyW` at `0x1805cb63b`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocQueryKeyW` at `0x1805cb63b`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1805cb607`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1805cb607`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RenameItemHelper(
        HWND a1,
        struct IUnknown *a2,
        struct IShellItem *a3,
        const unsigned __int16 *a4,
        PCWSTR pszMore,
        unsigned __int16 *a6,
        unsigned int a7,
        enum FOLDER_ENUM_MODE a8,
        struct _ITEMID_CHILD **a9)
{
  const WCHAR *v9; // r15
  HRESULT v11; // eax
  unsigned int v12; // ebx
  int v13; // r14d
  int v14; // eax
  int v15; // ebx
  HINSTANCE v16; // rax
  HINSTANCE v17; // rax
  const WCHAR *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  const WCHAR *ExtensionW; // r12
  const WCHAR *v26; // rax
  int v27; // r15d
  HINSTANCE v28; // rax
  int v29; // eax
  HINSTANCE v30; // rax
  int v31; // eax
  HINSTANCE v32; // rax
  __int64 v33; // r8
  HINSTANCE v34; // rax
  __int64 v35; // r8
  int fuStyle; // [rsp+20h] [rbp-71h]
  int fuStylea; // [rsp+20h] [rbp-71h]
  __int64 v39; // [rsp+40h] [rbp-51h] BYREF
  PWSTR pszSpec; // [rsp+48h] [rbp-49h] BYREF
  LPWSTR pszPath; // [rsp+50h] [rbp-41h] BYREF
  const unsigned __int16 *v42; // [rsp+58h] [rbp-39h]
  unsigned __int16 *v43; // [rsp+60h] [rbp-31h]
  struct IShellItem *v44; // [rsp+68h] [rbp-29h]
  IUnknown *punkSite; // [rsp+70h] [rbp-21h]
  PCWSTR ppszExt; // [rsp+78h] [rbp-19h] BYREF
  PWSTR ppszPathOut; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v9 = a4;
  v42 = a4;
  v44 = a3;
  punkSite = a2;
  v43 = a6;
  if ( a9 )
    *a9 = 0;
  v39 = 0;
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v11 = PathAllocCombine(v9, pszMore, 0, &ppszPathOut);
  v12 = v11;
  if ( v11 >= 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszSpec,
      a6,
      -1);
    if ( !pszSpec )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B6,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\shapi.cpp",
        (const char *)0x8007000ELL,
        fuStyle);
LABEL_7:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszSpec);
      goto LABEL_51;
    }
    v13 = -2147023673;
    v14 = PathCleanupSpec(v9, pszSpec);
    if ( v14 )
    {
      if ( a1 )
      {
        v15 = v14 & 8;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
        {
          v16 = Shell32Instance::get((Shell32Instance *)&v39);
          MessageBoxHelper::ShellMessageBoxTextScaled___1(
            v16,
            a1,
            (LPCWSTR)(v15 != 0 ? 6268LL : 4109LL),
            (LPCWSTR)0x1034,
            0x10u);
        }
        else
        {
          v17 = Shell32Instance::get((Shell32Instance *)&v39);
          ShellMessageBoxW(v17, a1, (LPCWSTR)(v15 != 0 ? 6268LL : 4109LL), (LPCWSTR)0x1034, 0x10u);
        }
      }
      goto LABEL_50;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPath,
      a6,
      -1);
    v18 = pszPath;
    if ( !pszPath )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\shapi.cpp",
        (const char *)0x8007000ELL,
        fuStyle);
LABEL_15:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszPath);
      goto LABEL_7;
    }
    PathRemoveBlanksW(pszPath);
    LOBYTE(v19) = 2;
    LOBYTE(v20) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl'::`2'::impl,
      v20,
      v19);
    if ( *v18 )
    {
      ppszExt = 0;
      v21 = -1;
      do
        ++v21;
      while ( v18[v21] );
      if ( PathCchFindExtension(v18, v21 + 1, &ppszExt) >= 0 && ppszExt == v18 && *v18 == 46 )
      {
        LOBYTE(v22) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl'::`2'::impl,
          v22,
          0);
        LOBYTE(v23) = 1;
        LOBYTE(v24) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl'::`2'::impl,
          v24,
          v23);
      }
      ExtensionW = PathFindExtensionW(pszMore);
      if ( *ExtensionW )
      {
        v26 = PathFindExtensionW(v18);
        if ( CompareStringW(0x7Fu, 1u, ExtensionW, -1, v26, -1) != 2 )
        {
          v27 = 6;
          ppszExt = 0;
          if ( !PathIsDirectoryW(ppszPathOut) )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &ppszExt,
              0);
            if ( AssocQueryKeyW(0, ASSOCKEY_SHELLEXECCLASS, ExtensionW, 0, (HKEY *)&ppszExt) >= 0 )
            {
              if ( a1 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
                {
                  v28 = Shell32Instance::get((Shell32Instance *)&v39);
                  v29 = MessageBoxHelper::ShellMessageBoxTextScaled___1(
                          v28,
                          a1,
                          (LPCWSTR)0x1010,
                          (LPCWSTR)0x1034,
                          0x34u);
                }
                else
                {
                  v30 = Shell32Instance::get((Shell32Instance *)&v39);
                  v29 = ShellMessageBoxW(v30, a1, (LPCWSTR)0x1010, (LPCWSTR)0x1034, 0x34u);
                }
                v27 = v29;
              }
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&ppszExt);
          if ( v27 != 6 )
            goto LABEL_49;
          v9 = v42;
        }
      }
      v31 = RenameWithOperationsEngine(a1, punkSite, v44, v43, a7, a8, a9);
      v13 = v31;
      if ( v31 >= 0 )
      {
        ppszExt = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszExt,
          0);
        PathAllocCombine(v9, v18, 0, (PWSTR *)&ppszExt);
        if ( !ppszExt )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72B,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\shapi.cpp",
            (const char *)0x8007000ELL,
            fuStylea);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppszExt);
          goto LABEL_15;
        }
        CheckShortcutRename(ppszPathOut, ppszExt);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppszExt);
LABEL_49:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszPath);
LABEL_50:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszSpec);
        v12 = v13;
        goto LABEL_51;
      }
      if ( v31 != -2147024894 || !a1 )
        goto LABEL_49;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      {
        v32 = Shell32Instance::get((Shell32Instance *)&v39);
        v33 = 4132;
LABEL_46:
        MessageBoxHelper::ShellMessageBoxTextScaled___1(v32, a1, (LPCWSTR)v33, (LPCWSTR)0x1034, 0x10u);
        goto LABEL_49;
      }
      v34 = Shell32Instance::get((Shell32Instance *)&v39);
      v35 = 4132;
    }
    else
    {
      if ( !a1 )
        goto LABEL_49;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      {
        v32 = Shell32Instance::get((Shell32Instance *)&v39);
        v33 = 4123;
        goto LABEL_46;
      }
      v34 = Shell32Instance::get((Shell32Instance *)&v39);
      v35 = 4123;
    }
    ShellMessageBoxW(v34, a1, (LPCWSTR)v35, (LPCWSTR)0x1034, 0x10u);
    goto LABEL_49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6B3,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\shapi.cpp",
    (const char *)(unsigned int)v11,
    fuStyle);
LABEL_51:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v39);
  return v12;
}

```

## disassembly

```asm
0x1805cb330  push    rbp
0x1805cb332  push    rbx
0x1805cb333  push    rsi
0x1805cb334  push    rdi
0x1805cb335  push    r12
0x1805cb337  push    r13
0x1805cb339  push    r14
0x1805cb33b  push    r15
0x1805cb33d  lea     rbp, [rsp-7]
0x1805cb342  sub     rsp, 98h
0x1805cb349  mov     rax, cs:__security_cookie
0x1805cb350  xor     rax, rsp
0x1805cb353  mov     [rbp+3Fh+var_48], rax
0x1805cb357  mov     r15, r9
0x1805cb35a  mov     [rbp+3Fh+var_78], r9
0x1805cb35e  mov     [rbp+3Fh+var_68], r8
0x1805cb362  mov     [rbp+3Fh+punkSite], rdx
0x1805cb366  mov     rdi, rcx
0x1805cb369  mov     rsi, [rbp+3Fh+pszMore]
0x1805cb36d  mov     r12, [rbp+3Fh+arg_28]
0x1805cb371  mov     [rbp+3Fh+var_70], r12
0x1805cb375  mov     r13, [rbp+3Fh+arg_40]
0x1805cb37c  xor     r14d, r14d
0x1805cb37f  test    r13, r13
0x1805cb382  jz      short loc_1805CB388
0x1805cb384  mov     [r13+0], r14
0x1805cb388  mov     [rbp+3Fh+var_90], r14
0x1805cb38c  mov     [rbp+3Fh+ppszPathOut], r14
0x1805cb390  xor     edx, edx
0x1805cb392  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1805cb396  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1805cb39b  lea     r9, [rbp+3Fh+ppszPathOut]; ppszPathOut
0x1805cb39f  xor     r8d, r8d; dwFlags
0x1805cb3a2  mov     rdx, rsi; pszMore
0x1805cb3a5  mov     rcx, r15; pszPathIn
0x1805cb3a8  call    cs:__imp_PathAllocCombine
0x1805cb3af  nop     dword ptr [rax+rax+00h]
0x1805cb3b4  mov     ebx, eax
0x1805cb3b6  test    eax, eax
0x1805cb3b8  jns     short loc_1805CB3D7
0x1805cb3ba  mov     rcx, [rbp+47h]; this
0x1805cb3be  mov     r9d, eax; char *
0x1805cb3c1  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805cb3c8  mov     edx, 6B3h; void *
0x1805cb3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805cb3d2  jmp     loc_1805CB833
0x1805cb3d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805cb3db  mov     rdx, r12
0x1805cb3de  lea     rcx, [rbp+3Fh+pszSpec]
0x1805cb3e2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1805cb3e7  nop
0x1805cb3e8  mov     rdx, [rbp+3Fh+pszSpec]; pszSpec
0x1805cb3ec  test    rdx, rdx
0x1805cb3ef  jnz     short loc_1805CB41D
0x1805cb3f1  mov     rcx, [rbp+47h]; this
0x1805cb3f5  mov     ebx, 8007000Eh
0x1805cb3fa  mov     r9d, ebx; char *
0x1805cb3fd  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805cb404  mov     edx, 6B6h; void *
0x1805cb409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805cb40e  nop
0x1805cb40f  lea     rcx, [rbp+3Fh+pszSpec]
0x1805cb413  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805cb418  jmp     loc_1805CB833
0x1805cb41d  mov     r14d, 800704C7h
0x1805cb423  mov     rcx, r15; pszDir
0x1805cb426  call    PathCleanupSpec
0x1805cb42b  mov     ebx, eax
0x1805cb42d  test    eax, eax
0x1805cb42f  jz      loc_1805CB4C6
0x1805cb435  test    rdi, rdi
0x1805cb438  jz      loc_1805CB827
0x1805cb43e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805cb445  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805cb44a  and     ebx, 8
0x1805cb44d  lea     rcx, [rbp+3Fh+var_90]; this
0x1805cb451  test    al, al
0x1805cb453  jz      short loc_1805CB48A
0x1805cb455  neg     ebx
0x1805cb457  sbb     rbx, rbx
0x1805cb45a  and     ebx, 86Fh
0x1805cb460  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb465  mov     rcx, rax; hAppInst
0x1805cb468  mov     [rsp+0D0h+fuStyle], 10h; UINT
0x1805cb470  mov     r9d, 1034h; lpcTitle
0x1805cb476  lea     r8, [rbx+100Dh]; lpcText
0x1805cb47d  mov     rdx, rdi; hWnd
0x1805cb480  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805cb485  jmp     loc_1805CB827
0x1805cb48a  neg     ebx
0x1805cb48c  sbb     rbx, rbx
0x1805cb48f  and     ebx, 86Fh
0x1805cb495  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb49a  mov     rcx, rax; hAppInst
0x1805cb49d  mov     [rsp+0D0h+fuStyle], 10h; fuStyle
0x1805cb4a5  mov     r9d, 1034h; lpcTitle
0x1805cb4ab  lea     r8, [rbx+100Dh]; lpcText
0x1805cb4b2  mov     rdx, rdi; hWnd
0x1805cb4b5  call    cs:__imp_ShellMessageBoxW
0x1805cb4bc  nop     dword ptr [rax+rax+00h]
0x1805cb4c1  jmp     loc_1805CB827
0x1805cb4c6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805cb4ca  mov     rdx, r12
0x1805cb4cd  lea     rcx, [rbp+3Fh+pszPath]
0x1805cb4d1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1805cb4d6  nop
0x1805cb4d7  mov     rbx, [rbp+3Fh+pszPath]
0x1805cb4db  xor     r12d, r12d
0x1805cb4de  test    rbx, rbx
0x1805cb4e1  jnz     short loc_1805CB50F
0x1805cb4e3  mov     rcx, [rbp+47h]; this
0x1805cb4e7  mov     ebx, 8007000Eh
0x1805cb4ec  mov     r9d, ebx; char *
0x1805cb4ef  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805cb4f6  mov     edx, 6CEh; void *
0x1805cb4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805cb500  nop
0x1805cb501  lea     rcx, [rbp+3Fh+pszPath]
0x1805cb505  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805cb50a  jmp     loc_1805CB40F
0x1805cb50f  mov     rcx, rbx; pszPath
0x1805cb512  call    cs:__imp_PathRemoveBlanksW
0x1805cb519  nop     dword ptr [rax+rax+00h]
0x1805cb51e  mov     r8b, 2
0x1805cb521  mov     dl, 1
0x1805cb523  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805cb52a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805cb52f  cmp     [rbx], r12w
0x1805cb533  jz      loc_1805CB7B6
0x1805cb539  mov     [rbp+3Fh+ppszExt], r12
0x1805cb53d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1805cb541  inc     rdx
0x1805cb544  cmp     [rbx+rdx*2], r12w
0x1805cb549  jnz     short loc_1805CB541
0x1805cb54b  inc     rdx; cchPath
0x1805cb54e  lea     r8, [rbp+3Fh+ppszExt]; ppszExt
0x1805cb552  mov     rcx, rbx; pszPath
0x1805cb555  call    cs:__imp_PathCchFindExtension
0x1805cb55c  nop     dword ptr [rax+rax+00h]
0x1805cb561  test    eax, eax
0x1805cb563  js      short loc_1805CB594
0x1805cb565  cmp     [rbp+3Fh+ppszExt], rbx
0x1805cb569  jnz     short loc_1805CB594
0x1805cb56b  cmp     word ptr [rbx], 2Eh ; '.'
0x1805cb56f  jnz     short loc_1805CB594
0x1805cb571  xor     r8d, r8d
0x1805cb574  mov     dl, 1
0x1805cb576  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805cb57d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805cb582  mov     r8b, 1
0x1805cb585  mov     dl, r8b
0x1805cb588  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805cb58f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805cb594  mov     rcx, rsi; pszPath
0x1805cb597  call    cs:__imp_PathFindExtensionW
0x1805cb59e  nop     dword ptr [rax+rax+00h]
0x1805cb5a3  mov     r12, rax
0x1805cb5a6  mov     esi, 1034h
0x1805cb5ab  xor     ecx, ecx
0x1805cb5ad  cmp     [rax], cx
0x1805cb5b0  jz      loc_1805CB6C7
0x1805cb5b6  mov     rcx, rbx; pszPath
0x1805cb5b9  call    cs:__imp_PathFindExtensionW
0x1805cb5c0  nop     dword ptr [rax+rax+00h]
0x1805cb5c5  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1805cb5cd  mov     qword ptr [rsp+0D0h+fuStyle], rax; lpString2
0x1805cb5d2  or      r9d, 0FFFFFFFFh; cchCount1
0x1805cb5d6  mov     r8, r12; lpString1
0x1805cb5d9  lea     edx, [r9+2]; dwCmpFlags
0x1805cb5dd  lea     ecx, [rdx+7Eh]; Locale
0x1805cb5e0  call    cs:__imp_CompareStringW
0x1805cb5e7  nop     dword ptr [rax+rax+00h]
0x1805cb5ec  cmp     eax, 2
0x1805cb5ef  jz      loc_1805CB6C7
0x1805cb5f5  mov     r15d, 6
0x1805cb5fb  mov     [rbp+3Fh+ppszExt], 0
0x1805cb603  mov     rcx, [rbp+3Fh+ppszPathOut]; pszPath
0x1805cb607  call    cs:__imp_PathIsDirectoryW
0x1805cb60e  nop     dword ptr [rax+rax+00h]
0x1805cb613  test    eax, eax
0x1805cb615  jnz     loc_1805CB6B0
0x1805cb61b  xor     edx, edx
0x1805cb61d  lea     rcx, [rbp+3Fh+ppszExt]
0x1805cb621  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1805cb626  lea     rax, [rbp+3Fh+ppszExt]
0x1805cb62a  mov     qword ptr [rsp+0D0h+fuStyle], rax; phkeyOut
0x1805cb62f  xor     r9d, r9d; pszExtra
0x1805cb632  mov     r8, r12; pszAssoc
0x1805cb635  lea     edx, [r15-5]; key
0x1805cb639  xor     ecx, ecx; flags
0x1805cb63b  call    cs:__imp_AssocQueryKeyW
0x1805cb642  nop     dword ptr [rax+rax+00h]
0x1805cb647  test    eax, eax
0x1805cb649  js      short loc_1805CB6B0
0x1805cb64b  test    rdi, rdi
0x1805cb64e  jz      short loc_1805CB6B0
0x1805cb650  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805cb657  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805cb65c  lea     rcx, [rbp+3Fh+var_90]; this
0x1805cb660  test    al, al
0x1805cb662  jz      short loc_1805CB685
0x1805cb664  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb669  mov     rcx, rax; hAppInst
0x1805cb66c  mov     [rsp+0D0h+fuStyle], 34h ; '4'; UINT
0x1805cb674  mov     r9d, esi; lpcTitle
0x1805cb677  lea     r8d, [rsi-24h]; lpcText
0x1805cb67b  mov     rdx, rdi; hWnd
0x1805cb67e  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805cb683  jmp     short loc_1805CB6AD
0x1805cb685  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb68a  mov     rcx, rax; hAppInst
0x1805cb68d  mov     [rsp+0D0h+fuStyle], 34h ; '4'; fuStyle
0x1805cb695  mov     r9, rsi; lpcTitle
0x1805cb698  mov     r8d, 1010h; lpcText
0x1805cb69e  mov     rdx, rdi; hWnd
0x1805cb6a1  call    cs:__imp_ShellMessageBoxW
0x1805cb6a8  nop     dword ptr [rax+rax+00h]
0x1805cb6ad  mov     r15d, eax
0x1805cb6b0  lea     rcx, [rbp+3Fh+ppszExt]
0x1805cb6b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1805cb6b9  cmp     r15d, 6
0x1805cb6bd  jnz     loc_1805CB81D
0x1805cb6c3  mov     r15, [rbp+3Fh+var_78]
0x1805cb6c7  mov     [rsp+0D0h+var_A0], r13; struct _ITEMID_CHILD **
0x1805cb6cc  mov     eax, [rbp+3Fh+arg_38]
0x1805cb6d2  mov     [rsp+0D0h+cchCount2], eax; enum FOLDER_ENUM_MODE
0x1805cb6d6  mov     eax, [rbp+3Fh+arg_30]
0x1805cb6d9  mov     [rsp+0D0h+fuStyle], eax; int
0x1805cb6dd  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x1805cb6e1  mov     r8, [rbp+3Fh+var_68]; struct IShellItem *
0x1805cb6e5  mov     rdx, [rbp+3Fh+punkSite]; punkSite
0x1805cb6e9  mov     rcx, rdi; HWND
0x1805cb6ec  call    ?RenameWithOperationsEngine@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIShellItem@@PEBGKW4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; RenameWithOperationsEngine(HWND__ *,IUnknown *,IShellItem *,ushort const *,ulong,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x1805cb6f1  mov     r14d, eax
0x1805cb6f4  xor     r12d, r12d
0x1805cb6f7  test    eax, eax
0x1805cb6f9  js      short loc_1805CB76E
0x1805cb6fb  mov     [rbp+3Fh+ppszExt], r12
0x1805cb6ff  xor     edx, edx
0x1805cb701  lea     rcx, [rbp+3Fh+ppszExt]
0x1805cb705  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1805cb70a  lea     r9, [rbp+3Fh+ppszExt]; ppszPathOut
0x1805cb70e  xor     r8d, r8d; dwFlags
0x1805cb711  mov     rdx, rbx; pszMore
0x1805cb714  mov     rcx, r15; pszPathIn
0x1805cb717  call    cs:__imp_PathAllocCombine
0x1805cb71e  nop     dword ptr [rax+rax+00h]
0x1805cb723  mov     rdx, [rbp+3Fh+ppszExt]; unsigned __int16 *
0x1805cb727  test    rdx, rdx
0x1805cb72a  jnz     short loc_1805CB757
0x1805cb72c  mov     rcx, [rbp+47h]; this
0x1805cb730  mov     ebx, 8007000Eh
0x1805cb735  mov     r9d, ebx; char *
0x1805cb738  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805cb73f  mov     edx, 72Bh; void *
0x1805cb744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805cb749  lea     rcx, [rbp+3Fh+ppszExt]
0x1805cb74d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805cb752  jmp     loc_1805CB501
0x1805cb757  mov     rcx, [rbp+3Fh+ppszPathOut]; unsigned __int16 *
0x1805cb75b  call    ?CheckShortcutRename@@YAXPEBG0@Z; CheckShortcutRename(ushort const *,ushort const *)
0x1805cb760  lea     rcx, [rbp+3Fh+ppszExt]
0x1805cb764  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805cb769  jmp     loc_1805CB81D
0x1805cb76e  cmp     eax, 80070002h
0x1805cb773  jnz     loc_1805CB81D
0x1805cb779  test    rdi, rdi
0x1805cb77c  jz      loc_1805CB81D
0x1805cb782  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805cb789  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805cb78e  lea     rcx, [rbp+3Fh+var_90]; this
0x1805cb792  test    al, al
0x1805cb794  jz      short loc_1805CB7A6
0x1805cb796  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb79b  mov     r9, rsi
0x1805cb79e  mov     r8d, 1024h
0x1805cb7a4  jmp     short loc_1805CB7DE
0x1805cb7a6  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb7ab  mov     r9, rsi
0x1805cb7ae  mov     r8d, 1024h
0x1805cb7b4  jmp     short loc_1805CB802
0x1805cb7b6  test    rdi, rdi
0x1805cb7b9  jz      short loc_1805CB81D
0x1805cb7bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805cb7c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805cb7c7  lea     rcx, [rbp+3Fh+var_90]; this
0x1805cb7cb  test    al, al
0x1805cb7cd  jz      short loc_1805CB7F3
0x1805cb7cf  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb7d4  mov     r9d, 1034h; lpcTitle
0x1805cb7da  lea     r8d, [r9-19h]; lpcText
0x1805cb7de  mov     [rsp+0D0h+fuStyle], 10h; UINT
0x1805cb7e6  mov     rcx, rax; hAppInst
0x1805cb7e9  mov     rdx, rdi; hWnd
0x1805cb7ec  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805cb7f1  jmp     short loc_1805CB81D
0x1805cb7f3  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805cb7f8  mov     r9d, 1034h; lpcTitle
0x1805cb7fe  lea     r8d, [r9-19h]; lpcText
0x1805cb802  mov     [rsp+0D0h+fuStyle], 10h; fuStyle
  ... truncated ...
```
