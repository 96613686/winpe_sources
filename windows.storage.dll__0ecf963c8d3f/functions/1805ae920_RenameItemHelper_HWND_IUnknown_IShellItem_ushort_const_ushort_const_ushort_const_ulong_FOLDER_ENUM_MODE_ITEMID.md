# RenameItemHelper(HWND__ *,IUnknown *,IShellItem *,ushort const *,ushort const *,ushort const *,ulong,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)

- ea: `0x1805ae920`
- end: `0x1805aee20`
- name: `?RenameItemHelper@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIShellItem@@PEBG33KW4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1280`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct IUnknown *@<rdx>, struct IShellItem *@<r8>, const unsigned __int16 *@<r9>, PCWSTR pszMore, const unsigned __int16 *, unsigned int, enum FOLDER_ENUM_MODE, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180514670`

## callees

- `0x18001abcc`
- `0x1800432f0`
- `0x18004a030`
- `0x18007e930`
- `0x1800b72b0`
- `0x18018fd20`
- `0x1801ae9bc`
- `0x18021dbd0`
- `0x1802ed61c`
- `0x1803052c4`
- `0x1803a4cb0`
- `0x180517614`
- `0x1805ae138`
- `0x1805ae920`
- `0x1805aee28`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1805aebac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1805aebac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805aec75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805aec75`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1805aeb33`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1805aeb33`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805ae998`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805aecdb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805ae998`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1805aecdb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805aeb6f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805aeb8b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805aeb6f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1805aeb8b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805aeaf6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805aeaf6`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aea9f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aec61`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aedce`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aea9f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aec61`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1805aedce`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocQueryKeyW` at `0x1805aebfb`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocQueryKeyW` at `0x1805aebfb`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1805aebcd`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1805aebcd`

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
  PCWSTR pszPathIn; // [rsp+58h] [rbp-39h]
  unsigned __int16 *v43; // [rsp+60h] [rbp-31h]
  struct IShellItem *v44; // [rsp+68h] [rbp-29h]
  IUnknown *punkSite; // [rsp+70h] [rbp-21h]
  PCWSTR ppszExt; // [rsp+78h] [rbp-19h] BYREF
  PWSTR ppszPathOut; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v9 = a4;
  pszPathIn = a4;
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
      goto LABEL_53;
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
      goto LABEL_52;
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
          if ( ppszExt )
            RegCloseKey((HKEY)ppszExt);
          if ( v27 != 6 )
            goto LABEL_51;
          v9 = pszPathIn;
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
LABEL_51:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszPath);
LABEL_52:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&pszSpec);
        v12 = v13;
        goto LABEL_53;
      }
      if ( v31 != -2147024894 || !a1 )
        goto LABEL_51;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      {
        v32 = Shell32Instance::get((Shell32Instance *)&v39);
        v33 = 4132;
LABEL_48:
        MessageBoxHelper::ShellMessageBoxTextScaled___1(v32, a1, (LPCWSTR)v33, (LPCWSTR)0x1034, 0x10u);
        goto LABEL_51;
      }
      v34 = Shell32Instance::get((Shell32Instance *)&v39);
      v35 = 4132;
    }
    else
    {
      if ( !a1 )
        goto LABEL_51;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      {
        v32 = Shell32Instance::get((Shell32Instance *)&v39);
        v33 = 4123;
        goto LABEL_48;
      }
      v34 = Shell32Instance::get((Shell32Instance *)&v39);
      v35 = 4123;
    }
    ShellMessageBoxW(v34, a1, (LPCWSTR)v35, (LPCWSTR)0x1034, 0x10u);
    goto LABEL_51;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6B3,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\shapi.cpp",
    (const char *)(unsigned int)v11,
    fuStyle);
LABEL_53:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v39);
  return v12;
}

```

## disassembly

```asm
0x1805ae920  push    rbp
0x1805ae922  push    rbx
0x1805ae923  push    rsi
0x1805ae924  push    rdi
0x1805ae925  push    r12
0x1805ae927  push    r13
0x1805ae929  push    r14
0x1805ae92b  push    r15
0x1805ae92d  lea     rbp, [rsp-7]
0x1805ae932  sub     rsp, 98h
0x1805ae939  mov     rax, cs:__security_cookie
0x1805ae940  xor     rax, rsp
0x1805ae943  mov     [rbp+3Fh+var_48], rax
0x1805ae947  mov     r15, r9
0x1805ae94a  mov     [rbp+3Fh+pszPathIn], r9
0x1805ae94e  mov     [rbp+3Fh+var_68], r8
0x1805ae952  mov     [rbp+3Fh+punkSite], rdx
0x1805ae956  mov     rdi, rcx
0x1805ae959  mov     rsi, [rbp+3Fh+pszMore]
0x1805ae95d  mov     r12, [rbp+3Fh+arg_28]
0x1805ae961  mov     [rbp+3Fh+var_70], r12
0x1805ae965  mov     r13, [rbp+3Fh+arg_40]
0x1805ae96c  xor     r14d, r14d
0x1805ae96f  test    r13, r13
0x1805ae972  jz      short loc_1805AE978
0x1805ae974  mov     [r13+0], r14
0x1805ae978  mov     [rbp+3Fh+var_90], r14
0x1805ae97c  mov     [rbp+3Fh+ppszPathOut], r14
0x1805ae980  xor     edx, edx
0x1805ae982  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1805ae986  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1805ae98b  lea     r9, [rbp+3Fh+ppszPathOut]; ppszPathOut
0x1805ae98f  xor     r8d, r8d; dwFlags
0x1805ae992  mov     rdx, rsi; pszMore
0x1805ae995  mov     rcx, r15; pszPathIn
0x1805ae998  call    cs:__imp_PathAllocCombine
0x1805ae99e  mov     ebx, eax
0x1805ae9a0  test    eax, eax
0x1805ae9a2  jns     short loc_1805AE9C1
0x1805ae9a4  mov     rcx, [rbp+47h]; this
0x1805ae9a8  mov     r9d, eax; char *
0x1805ae9ab  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805ae9b2  mov     edx, 6B3h; void *
0x1805ae9b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805ae9bc  jmp     loc_1805AEDEB
0x1805ae9c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805ae9c5  mov     rdx, r12
0x1805ae9c8  lea     rcx, [rbp+3Fh+pszSpec]
0x1805ae9cc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1805ae9d1  nop
0x1805ae9d2  mov     rdx, [rbp+3Fh+pszSpec]; pszSpec
0x1805ae9d6  test    rdx, rdx
0x1805ae9d9  jnz     short loc_1805AEA07
0x1805ae9db  mov     rcx, [rbp+47h]; this
0x1805ae9df  mov     ebx, 8007000Eh
0x1805ae9e4  mov     r9d, ebx; char *
0x1805ae9e7  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805ae9ee  mov     edx, 6B6h; void *
0x1805ae9f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805ae9f8  nop
0x1805ae9f9  lea     rcx, [rbp+3Fh+pszSpec]
0x1805ae9fd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805aea02  jmp     loc_1805AEDEB
0x1805aea07  mov     r14d, 800704C7h
0x1805aea0d  mov     rcx, r15; pszDir
0x1805aea10  call    PathCleanupSpec
0x1805aea15  mov     ebx, eax
0x1805aea17  test    eax, eax
0x1805aea19  jz      loc_1805AEAAA
0x1805aea1f  test    rdi, rdi
0x1805aea22  jz      loc_1805AEDDF
0x1805aea28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805aea2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805aea34  and     ebx, 8
0x1805aea37  lea     rcx, [rbp+3Fh+var_90]; this
0x1805aea3b  test    al, al
0x1805aea3d  jz      short loc_1805AEA74
0x1805aea3f  neg     ebx
0x1805aea41  sbb     rbx, rbx
0x1805aea44  and     ebx, 86Fh
0x1805aea4a  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aea4f  mov     rcx, rax; hAppInst
0x1805aea52  mov     [rsp+0D0h+fuStyle], 10h; UINT
0x1805aea5a  mov     r9d, 1034h; lpcTitle
0x1805aea60  lea     r8, [rbx+100Dh]; lpcText
0x1805aea67  mov     rdx, rdi; hWnd
0x1805aea6a  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805aea6f  jmp     loc_1805AEDDF
0x1805aea74  neg     ebx
0x1805aea76  sbb     rbx, rbx
0x1805aea79  and     ebx, 86Fh
0x1805aea7f  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aea84  mov     rcx, rax; hAppInst
0x1805aea87  mov     [rsp+0D0h+fuStyle], 10h; fuStyle
0x1805aea8f  mov     r9d, 1034h; lpcTitle
0x1805aea95  lea     r8, [rbx+100Dh]; lpcText
0x1805aea9c  mov     rdx, rdi; hWnd
0x1805aea9f  call    cs:__imp_ShellMessageBoxW
0x1805aeaa5  jmp     loc_1805AEDDF
0x1805aeaaa  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805aeaae  mov     rdx, r12
0x1805aeab1  lea     rcx, [rbp+3Fh+pszPath]
0x1805aeab5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1805aeaba  nop
0x1805aeabb  mov     rbx, [rbp+3Fh+pszPath]
0x1805aeabf  xor     r12d, r12d
0x1805aeac2  test    rbx, rbx
0x1805aeac5  jnz     short loc_1805AEAF3
0x1805aeac7  mov     rcx, [rbp+47h]; this
0x1805aeacb  mov     ebx, 8007000Eh
0x1805aead0  mov     r9d, ebx; char *
0x1805aead3  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805aeada  mov     edx, 6CEh; void *
0x1805aeadf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805aeae4  nop
0x1805aeae5  lea     rcx, [rbp+3Fh+pszPath]
0x1805aeae9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805aeaee  jmp     loc_1805AE9F9
0x1805aeaf3  mov     rcx, rbx; pszPath
0x1805aeaf6  call    cs:__imp_PathRemoveBlanksW
0x1805aeafc  mov     r8b, 2
0x1805aeaff  mov     dl, 1
0x1805aeb01  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805aeb08  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805aeb0d  cmp     [rbx], r12w
0x1805aeb11  jz      loc_1805AED74
0x1805aeb17  mov     [rbp+3Fh+ppszExt], r12
0x1805aeb1b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1805aeb1f  inc     rdx
0x1805aeb22  cmp     [rbx+rdx*2], r12w
0x1805aeb27  jnz     short loc_1805AEB1F
0x1805aeb29  inc     rdx; cchPath
0x1805aeb2c  lea     r8, [rbp+3Fh+ppszExt]; ppszExt
0x1805aeb30  mov     rcx, rbx; pszPath
0x1805aeb33  call    cs:__imp_PathCchFindExtension
0x1805aeb39  test    eax, eax
0x1805aeb3b  js      short loc_1805AEB6C
0x1805aeb3d  cmp     [rbp+3Fh+ppszExt], rbx
0x1805aeb41  jnz     short loc_1805AEB6C
0x1805aeb43  cmp     word ptr [rbx], 2Eh ; '.'
0x1805aeb47  jnz     short loc_1805AEB6C
0x1805aeb49  xor     r8d, r8d
0x1805aeb4c  mov     dl, 1
0x1805aeb4e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805aeb55  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805aeb5a  mov     r8b, 1
0x1805aeb5d  mov     dl, r8b
0x1805aeb60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles> `wil::Feature<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::GetImpl(void)'::`2'::impl
0x1805aeb67  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowRenameOfExtensionOnlyFiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1805aeb6c  mov     rcx, rsi; pszPath
0x1805aeb6f  call    cs:__imp_PathFindExtensionW
0x1805aeb75  mov     r12, rax
0x1805aeb78  mov     esi, 1034h
0x1805aeb7d  xor     ecx, ecx
0x1805aeb7f  cmp     [rax], cx
0x1805aeb82  jz      loc_1805AEC8B
0x1805aeb88  mov     rcx, rbx; pszPath
0x1805aeb8b  call    cs:__imp_PathFindExtensionW
0x1805aeb91  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1805aeb99  mov     qword ptr [rsp+0D0h+fuStyle], rax; lpString2
0x1805aeb9e  or      r9d, 0FFFFFFFFh; cchCount1
0x1805aeba2  mov     r8, r12; lpString1
0x1805aeba5  lea     edx, [r9+2]; dwCmpFlags
0x1805aeba9  lea     ecx, [rdx+7Eh]; Locale
0x1805aebac  call    cs:__imp_CompareStringW
0x1805aebb2  cmp     eax, 2
0x1805aebb5  jz      loc_1805AEC8B
0x1805aebbb  mov     r15d, 6
0x1805aebc1  mov     [rbp+3Fh+ppszExt], 0
0x1805aebc9  mov     rcx, [rbp+3Fh+ppszPathOut]; pszPath
0x1805aebcd  call    cs:__imp_PathIsDirectoryW
0x1805aebd3  test    eax, eax
0x1805aebd5  jnz     loc_1805AEC69
0x1805aebdb  xor     edx, edx
0x1805aebdd  lea     rcx, [rbp+3Fh+ppszExt]
0x1805aebe1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1805aebe6  lea     rax, [rbp+3Fh+ppszExt]
0x1805aebea  mov     qword ptr [rsp+0D0h+fuStyle], rax; phkeyOut
0x1805aebef  xor     r9d, r9d; pszExtra
0x1805aebf2  mov     r8, r12; pszAssoc
0x1805aebf5  lea     edx, [r15-5]; key
0x1805aebf9  xor     ecx, ecx; flags
0x1805aebfb  call    cs:__imp_AssocQueryKeyW
0x1805aec01  xor     r12d, r12d
0x1805aec04  test    eax, eax
0x1805aec06  js      short loc_1805AEC6C
0x1805aec08  test    rdi, rdi
0x1805aec0b  jz      short loc_1805AEC6C
0x1805aec0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805aec14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805aec19  lea     rcx, [rbp+3Fh+var_90]; this
0x1805aec1d  test    al, al
0x1805aec1f  jz      short loc_1805AEC45
0x1805aec21  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aec26  mov     rcx, rax; hAppInst
0x1805aec29  mov     [rsp+0D0h+fuStyle], 34h ; '4'; UINT
0x1805aec31  mov     r9d, esi; lpcTitle
0x1805aec34  lea     r8d, [rsi-24h]; lpcText
0x1805aec38  mov     rdx, rdi; hWnd
0x1805aec3b  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805aec40  mov     r15d, eax
0x1805aec43  jmp     short loc_1805AEC6C
0x1805aec45  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aec4a  mov     rcx, rax; hAppInst
0x1805aec4d  mov     [rsp+0D0h+fuStyle], 34h ; '4'; fuStyle
0x1805aec55  mov     r9, rsi; lpcTitle
0x1805aec58  mov     r8d, 1010h; lpcText
0x1805aec5e  mov     rdx, rdi; hWnd
0x1805aec61  call    cs:__imp_ShellMessageBoxW
0x1805aec67  jmp     short loc_1805AEC40
0x1805aec69  xor     r12d, r12d
0x1805aec6c  mov     rcx, [rbp+3Fh+ppszExt]; hKey
0x1805aec70  test    rcx, rcx
0x1805aec73  jz      short loc_1805AEC7B
0x1805aec75  call    cs:__imp_RegCloseKey
0x1805aec7b  cmp     r15d, 6
0x1805aec7f  jnz     loc_1805AEDD5
0x1805aec85  mov     r15, [rbp+3Fh+pszPathIn]
0x1805aec89  jmp     short loc_1805AEC8E
0x1805aec8b  xor     r12d, r12d
0x1805aec8e  mov     [rsp+0D0h+var_A0], r13; struct _ITEMID_CHILD **
0x1805aec93  mov     eax, [rbp+3Fh+arg_38]
0x1805aec99  mov     [rsp+0D0h+cchCount2], eax; enum FOLDER_ENUM_MODE
0x1805aec9d  mov     eax, [rbp+3Fh+arg_30]
0x1805aeca0  mov     [rsp+0D0h+fuStyle], eax; int
0x1805aeca4  mov     r9, [rbp+3Fh+var_70]; unsigned __int16 *
0x1805aeca8  mov     r8, [rbp+3Fh+var_68]; struct IShellItem *
0x1805aecac  mov     rdx, [rbp+3Fh+punkSite]; punkSite
0x1805aecb0  mov     rcx, rdi; HWND
0x1805aecb3  call    ?RenameWithOperationsEngine@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIShellItem@@PEBGKW4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; RenameWithOperationsEngine(HWND__ *,IUnknown *,IShellItem *,ushort const *,ulong,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x1805aecb8  mov     r14d, eax
0x1805aecbb  test    eax, eax
0x1805aecbd  js      short loc_1805AED2C
0x1805aecbf  mov     [rbp+3Fh+ppszExt], r12
0x1805aecc3  xor     edx, edx
0x1805aecc5  lea     rcx, [rbp+3Fh+ppszExt]
0x1805aecc9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1805aecce  lea     r9, [rbp+3Fh+ppszExt]; ppszPathOut
0x1805aecd2  xor     r8d, r8d; dwFlags
0x1805aecd5  mov     rdx, rbx; pszMore
0x1805aecd8  mov     rcx, r15; pszPathIn
0x1805aecdb  call    cs:__imp_PathAllocCombine
0x1805aece1  mov     rdx, [rbp+3Fh+ppszExt]; unsigned __int16 *
0x1805aece5  test    rdx, rdx
0x1805aece8  jnz     short loc_1805AED15
0x1805aecea  mov     rcx, [rbp+47h]; this
0x1805aecee  mov     ebx, 8007000Eh
0x1805aecf3  mov     r9d, ebx; char *
0x1805aecf6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805aecfd  mov     edx, 72Bh; void *
0x1805aed02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805aed07  lea     rcx, [rbp+3Fh+ppszExt]
0x1805aed0b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805aed10  jmp     loc_1805AEAE5
0x1805aed15  mov     rcx, [rbp+3Fh+ppszPathOut]; unsigned __int16 *
0x1805aed19  call    ?CheckShortcutRename@@YAXPEBG0@Z; CheckShortcutRename(ushort const *,ushort const *)
0x1805aed1e  lea     rcx, [rbp+3Fh+ppszExt]
0x1805aed22  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x1805aed27  jmp     loc_1805AEDD5
0x1805aed2c  cmp     eax, 80070002h
0x1805aed31  jnz     loc_1805AEDD5
0x1805aed37  test    rdi, rdi
0x1805aed3a  jz      loc_1805AEDD5
0x1805aed40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805aed47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805aed4c  lea     rcx, [rbp+3Fh+var_90]; this
0x1805aed50  test    al, al
0x1805aed52  jz      short loc_1805AED64
0x1805aed54  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aed59  mov     r9, rsi
0x1805aed5c  mov     r8d, 1024h
0x1805aed62  jmp     short loc_1805AED9C
0x1805aed64  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aed69  mov     r9, rsi
0x1805aed6c  mov     r8d, 1024h
0x1805aed72  jmp     short loc_1805AEDC0
0x1805aed74  test    rdi, rdi
0x1805aed77  jz      short loc_1805AEDD5
0x1805aed79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1805aed80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1805aed85  lea     rcx, [rbp+3Fh+var_90]; this
0x1805aed89  test    al, al
0x1805aed8b  jz      short loc_1805AEDB1
0x1805aed8d  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aed92  mov     r9d, 1034h; lpcTitle
0x1805aed98  lea     r8d, [r9-19h]; lpcText
0x1805aed9c  mov     [rsp+0D0h+fuStyle], 10h; UINT
0x1805aeda4  mov     rcx, rax; hAppInst
0x1805aeda7  mov     rdx, rdi; hWnd
0x1805aedaa  call    MessageBoxHelper__ShellMessageBoxTextScaled___1
0x1805aedaf  jmp     short loc_1805AEDD5
0x1805aedb1  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1805aedb6  mov     r9d, 1034h; lpcTitle
0x1805aedbc  lea     r8d, [r9-19h]; lpcText
0x1805aedc0  mov     [rsp+0D0h+fuStyle], 10h; fuStyle
0x1805aedc8  mov     rdx, rdi; hWnd
0x1805aedcb  mov     rcx, rax; hAppInst
0x1805aedce  call    cs:__imp_ShellMessageBoxW
0x1805aedd4  nop
0x1805aedd5  lea     rcx, [rbp+3Fh+pszPath]
  ... truncated ...
```
