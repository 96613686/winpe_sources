# _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)

- ea: `0x180288dec`
- end: `0x18028902c`
- name: `??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1802c58d4`

## callees

- `0x18001d664`
- `0x1800237c8`
- `0x1800c7c34`
- `0x18014b060`
- `0x180288dec`
- `0x180289034`
- `0x1802cc14c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180288e9d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288e2b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288f34`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288f88`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288fdd`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288e2b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288f34`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288f88`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180288fdd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180288edf`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180288edf`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x180288e7d`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x180288e7d`

## string_xrefs

- `0x180288e40`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180288ef2`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180288f47`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180288f9b`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180288ff0`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(HSTRING *a1, const WCHAR *a2, PWSTR *a3)
{
  HSTRING v6; // rcx
  const WCHAR *StringRawBuffer; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HSTRING v11; // rcx
  const WCHAR *v12; // r15
  bool v13; // bl
  PCWSTR v14; // rax
  __int64 v15; // r8
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  HRESULT v18; // eax
  HRESULT v19; // eax
  PWSTR *v20; // rax
  HRESULT v21; // eax
  HRESULT v22; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  int v25; // [rsp+60h] [rbp+40h] BYREF
  PWSTR pszPath; // [rsp+70h] [rbp+50h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp+58h] BYREF

  *a3 = 0;
  v6 = *a1;
  if ( v6 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
    v8 = PathAllocCombine(StringRawBuffer, a2, 1u, a3);
    if ( (v8 & 0x80000000) != 0 )
    {
      v9 = 263;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
        (const char *)v8,
        savedregs);
      return v8;
    }
  }
  else
  {
    v11 = a1[1];
    if ( v11 )
    {
      v25 = 0;
      v12 = WindowsGetStringRawBuffer(v11, 0);
      v8 = IsMrtResourceRedirectionEnabled(v12, &v25);
      if ( (v8 & 0x80000000) != 0 )
      {
        v9 = 272;
        goto LABEL_4;
      }
      v13 = v25 == 0;
      v14 = WindowsGetStringRawBuffer(a1[1], 0);
      LOBYTE(v15) = v13;
      ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(&pszPath, v14, v15);
      v16 = pszPath;
      if ( pszPath )
      {
        if ( v25 )
        {
          v17 = -1;
          do
            ++v17;
          while ( pszPath[v17] );
          v18 = PathCchRemoveFileSpec(pszPath, v17 + 1);
          v8 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11B,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v18,
              savedregs);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
            return v8;
          }
          ppszPathOut = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &ppszPathOut,
            0);
          v19 = PathAllocCombine(pszPath, L"Resources", 1u, &ppszPathOut);
          v8 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11D,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v19,
              savedregs);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
            return v8;
          }
          v20 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
          v21 = PathAllocCombine(ppszPathOut, v12, 1u, v20);
          v8 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11E,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v21,
              savedregs);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
            return v8;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v16 = pszPath;
        }
        v22 = PathAllocCombine(v16, a2, 1u, a3);
        v8 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x121,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
            (const char *)(unsigned int)v22,
            savedregs);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
          return v8;
        }
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180288dec  push    rbp
0x180288dee  push    rbx
0x180288def  push    rsi
0x180288df0  push    rdi
0x180288df1  push    r12
0x180288df3  push    r14
0x180288df5  push    r15; int
0x180288df7  mov     rbp, rsp
0x180288dfa  sub     rsp, 20h
0x180288dfe  mov     rsi, r8
0x180288e01  mov     r14, rdx
0x180288e04  mov     rdi, rcx
0x180288e07  xor     r12d, r12d
0x180288e0a  mov     [r8], r12
0x180288e0d  mov     rcx, [rcx]; string
0x180288e10  test    rcx, rcx
0x180288e13  jz      short loc_180288E5A
0x180288e15  xor     edx, edx; length
0x180288e17  call    cs:__imp_WindowsGetStringRawBuffer
0x180288e1d  mov     rcx, rax; pszPathIn
0x180288e20  mov     r9, rsi; ppszPathOut
0x180288e23  lea     r8d, [r12+1]; dwFlags
0x180288e28  mov     rdx, r14; pszMore
0x180288e2b  call    cs:__imp_PathAllocCombine
0x180288e31  mov     ebx, eax
0x180288e33  test    eax, eax
0x180288e35  jns     loc_18028901B
0x180288e3b  mov     edx, 107h; void *
0x180288e40  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180288e47  mov     r9d, ebx; char *
0x180288e4a  mov     rcx, [rbp+38h]; this
0x180288e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180288e53  mov     eax, ebx
0x180288e55  jmp     loc_18028901D
0x180288e5a  mov     rcx, [rdi+8]; string
0x180288e5e  test    rcx, rcx
0x180288e61  jz      loc_18028901B
0x180288e67  mov     [rbp+arg_0], r12d
0x180288e6b  xor     edx, edx; length
0x180288e6d  call    cs:__imp_WindowsGetStringRawBuffer
0x180288e73  mov     r15, rax
0x180288e76  lea     rdx, [rbp+arg_0]
0x180288e7a  mov     rcx, rax
0x180288e7d  call    cs:__imp_IsMrtResourceRedirectionEnabled
0x180288e83  mov     ebx, eax
0x180288e85  test    eax, eax
0x180288e87  jns     short loc_180288E90
0x180288e89  mov     edx, 110h
0x180288e8e  jmp     short loc_180288E40
0x180288e90  cmp     [rbp+arg_0], r12d
0x180288e94  setz    bl
0x180288e97  xor     edx, edx; length
0x180288e99  mov     rcx, [rdi+8]; string
0x180288e9d  call    cs:__imp_WindowsGetStringRawBuffer
0x180288ea3  mov     rdx, rax
0x180288ea6  mov     r8b, bl
0x180288ea9  lea     rcx, [rbp+pszPath]
0x180288ead  call    ?TryGetStagedPackagePathByFullNameAlloc@Common@ShellMRTHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG_N@Z; ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(ushort const *,bool)
0x180288eb2  mov     rcx, [rbp+pszPath]; pszPath
0x180288eb6  test    rcx, rcx
0x180288eb9  jz      loc_180289011
0x180288ebf  mov     edi, 1
0x180288ec4  cmp     [rbp+arg_0], r12d
0x180288ec8  jz      loc_180288FD4
0x180288ece  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180288ed2  inc     rdx
0x180288ed5  cmp     [rcx+rdx*2], r12w
0x180288eda  jnz     short loc_180288ED2
0x180288edc  inc     rdx; cchPath
0x180288edf  call    cs:__imp_PathCchRemoveFileSpec
0x180288ee5  mov     ebx, eax
0x180288ee7  test    eax, eax
0x180288ee9  jns     short loc_180288F13
0x180288eeb  mov     rcx, [rbp+38h]; this
0x180288eef  mov     r9d, eax; char *
0x180288ef2  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180288ef9  mov     edx, 11Bh; void *
0x180288efe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180288f03  nop
0x180288f04  lea     rcx, [rbp+pszPath]
0x180288f08  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180288f0d  nop
0x180288f0e  jmp     loc_180288E53
0x180288f13  mov     [rbp+ppszPathOut], r12
0x180288f17  xor     edx, edx
0x180288f19  lea     rcx, [rbp+ppszPathOut]
0x180288f1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180288f22  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180288f26  mov     r8d, edi; dwFlags
0x180288f29  lea     rdx, ?c_msResourcesRedirectFolderName@Common@ShellMRTHelper@@3QBGB; "Resources"
0x180288f30  mov     rcx, [rbp+pszPath]; pszPathIn
0x180288f34  call    cs:__imp_PathAllocCombine
0x180288f3a  mov     ebx, eax
0x180288f3c  test    eax, eax
0x180288f3e  jns     short loc_180288F72
0x180288f40  mov     rcx, [rbp+38h]; this
0x180288f44  mov     r9d, eax; char *
0x180288f47  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180288f4e  mov     edx, 11Dh; void *
0x180288f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180288f58  nop
0x180288f59  lea     rcx, [rbp+ppszPathOut]
0x180288f5d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180288f62  nop
0x180288f63  lea     rcx, [rbp+pszPath]
0x180288f67  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180288f6c  nop
0x180288f6d  jmp     loc_180288E53
0x180288f72  lea     rcx, [rbp+pszPath]
0x180288f76  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180288f7b  mov     r9, rax; ppszPathOut
0x180288f7e  mov     r8d, edi; dwFlags
0x180288f81  mov     rdx, r15; pszMore
0x180288f84  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180288f88  call    cs:__imp_PathAllocCombine
0x180288f8e  mov     ebx, eax
0x180288f90  test    eax, eax
0x180288f92  jns     short loc_180288FC6
0x180288f94  mov     rcx, [rbp+38h]; this
0x180288f98  mov     r9d, eax; char *
0x180288f9b  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180288fa2  mov     edx, 11Eh; void *
0x180288fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180288fac  nop
0x180288fad  lea     rcx, [rbp+ppszPathOut]
0x180288fb1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180288fb6  nop
0x180288fb7  lea     rcx, [rbp+pszPath]
0x180288fbb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180288fc0  nop
0x180288fc1  jmp     loc_180288E53
0x180288fc6  lea     rcx, [rbp+ppszPathOut]
0x180288fca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180288fcf  nop
0x180288fd0  mov     rcx, [rbp+pszPath]; pszPathIn
0x180288fd4  mov     r9, rsi; ppszPathOut
0x180288fd7  mov     r8d, edi; dwFlags
0x180288fda  mov     rdx, r14; pszMore
0x180288fdd  call    cs:__imp_PathAllocCombine
0x180288fe3  mov     ebx, eax
0x180288fe5  test    eax, eax
0x180288fe7  jns     short loc_180289011
0x180288fe9  mov     rcx, [rbp+38h]; this
0x180288fed  mov     r9d, eax; char *
0x180288ff0  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180288ff7  mov     edx, 121h; void *
0x180288ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180289001  nop
0x180289002  lea     rcx, [rbp+pszPath]
0x180289006  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18028900b  nop
0x18028900c  jmp     loc_180288E53
0x180289011  lea     rcx, [rbp+pszPath]
0x180289015  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18028901a  nop
0x18028901b  xor     eax, eax
0x18028901d  add     rsp, 20h
0x180289021  pop     r15
0x180289023  pop     r14
0x180289025  pop     r12
0x180289027  pop     rdi
0x180289028  pop     rsi
0x180289029  pop     rbx
0x18028902a  pop     rbp
0x18028902b  retn
```
