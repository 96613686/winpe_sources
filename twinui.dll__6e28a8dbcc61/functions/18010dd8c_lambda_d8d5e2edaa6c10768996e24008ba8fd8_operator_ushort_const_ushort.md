# _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)

- ea: `0x18010dd8c`
- end: `0x18010df78`
- name: `??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180324838`

## callees

- `0x18003c5e4`
- `0x1800542a8`
- `0x1800b27ac`
- `0x18010dd8c`
- `0x18010df80`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010ddcb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010ded1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010df19`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010df42`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010ddcb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010ded1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010df19`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18010df42`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18010de7f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18010de7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ddb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ddb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010deb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010df61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010deb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010df61`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x18010de1d`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x18010de1d`

## string_xrefs

- `0x18010dde0`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18010de90`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18010dee2`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(HSTRING *a1, const WCHAR *a2, PWSTR *a3)
{
  HSTRING v6; // rcx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v8; // ebx
  __int64 v9; // rdx
  HSTRING v11; // rcx
  const WCHAR *v12; // r15
  bool v13; // bl
  PCWSTR v14; // rax
  __int64 v15; // r8
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  int v22; // [rsp+60h] [rbp+40h] BYREF
  PWSTR pszPath; // [rsp+70h] [rbp+50h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp+58h] BYREF

  *a3 = 0;
  v6 = *a1;
  if ( v6 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
    v8 = PathAllocCombine(StringRawBuffer, a2, 1u, a3);
    if ( v8 < 0 )
    {
      v9 = 263;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
        (const char *)(unsigned int)v8,
        savedregs);
      return (unsigned int)v8;
    }
    return 0;
  }
  v11 = a1[1];
  if ( v11 )
  {
    v22 = 0;
    v12 = WindowsGetStringRawBuffer(v11, 0);
    v8 = IsMrtResourceRedirectionEnabled(v12, &v22);
    if ( v8 < 0 )
    {
      v9 = 272;
      goto LABEL_4;
    }
    v13 = v22 == 0;
    v14 = WindowsGetStringRawBuffer(a1[1], 0);
    LOBYTE(v15) = v13;
    ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(&pszPath, v14, v15);
    v16 = pszPath;
    if ( pszPath )
    {
      if ( v22 )
      {
        v17 = -1;
        do
          ++v17;
        while ( pszPath[v17] );
        v8 = PathCchRemoveFileSpec(pszPath, v17 + 1);
        if ( v8 < 0 )
        {
          v18 = 283;
LABEL_15:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
            (const char *)(unsigned int)v8,
            savedregs);
          goto LABEL_16;
        }
        ppszPathOut = 0;
        v8 = PathAllocCombine(pszPath, L"Resources", 1u, &ppszPathOut);
        if ( v8 < 0 )
        {
          v19 = 285;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
            (const char *)(unsigned int)v8,
            savedregs);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_16:
          if ( pszPath )
            CoTaskMemFree(pszPath);
          return (unsigned int)v8;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszPath,
          0);
        v8 = PathAllocCombine(ppszPathOut, v12, 1u, &pszPath);
        if ( v8 < 0 )
        {
          v19 = 286;
          goto LABEL_20;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        v16 = pszPath;
      }
      v8 = PathAllocCombine(v16, a2, 1u, a3);
      if ( v8 >= 0 )
      {
        if ( pszPath )
          CoTaskMemFree(pszPath);
        return 0;
      }
      v18 = 289;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18010dd8c  push    rbp
0x18010dd8e  push    rbx
0x18010dd8f  push    rsi
0x18010dd90  push    rdi
0x18010dd91  push    r12
0x18010dd93  push    r14
0x18010dd95  push    r15; int
0x18010dd97  mov     rbp, rsp
0x18010dd9a  sub     rsp, 20h
0x18010dd9e  mov     rsi, r8
0x18010dda1  mov     r14, rdx
0x18010dda4  mov     rdi, rcx
0x18010dda7  xor     r12d, r12d
0x18010ddaa  mov     [r8], r12
0x18010ddad  mov     rcx, [rcx]; string
0x18010ddb0  test    rcx, rcx
0x18010ddb3  jz      short loc_18010DDFA
0x18010ddb5  xor     edx, edx; length
0x18010ddb7  call    cs:__imp_WindowsGetStringRawBuffer
0x18010ddbd  mov     rcx, rax; pszPathIn
0x18010ddc0  mov     r9, rsi; ppszPathOut
0x18010ddc3  lea     r8d, [r12+1]; dwFlags
0x18010ddc8  mov     rdx, r14; pszMore
0x18010ddcb  call    cs:__imp_PathAllocCombine
0x18010ddd1  mov     ebx, eax
0x18010ddd3  test    eax, eax
0x18010ddd5  jns     loc_18010DF67
0x18010dddb  mov     edx, 107h; void *
0x18010dde0  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18010dde7  mov     r9d, ebx; char *
0x18010ddea  mov     rcx, [rbp+38h]; this
0x18010ddee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ddf3  mov     eax, ebx
0x18010ddf5  jmp     loc_18010DF69
0x18010ddfa  mov     rcx, [rdi+8]; string
0x18010ddfe  test    rcx, rcx
0x18010de01  jz      loc_18010DF67
0x18010de07  mov     [rbp+arg_0], r12d
0x18010de0b  xor     edx, edx; length
0x18010de0d  call    cs:__imp_WindowsGetStringRawBuffer
0x18010de13  mov     r15, rax
0x18010de16  lea     rdx, [rbp+arg_0]
0x18010de1a  mov     rcx, rax
0x18010de1d  call    cs:__imp_IsMrtResourceRedirectionEnabled
0x18010de23  mov     ebx, eax
0x18010de25  test    eax, eax
0x18010de27  jns     short loc_18010DE30
0x18010de29  mov     edx, 110h
0x18010de2e  jmp     short loc_18010DDE0
0x18010de30  cmp     [rbp+arg_0], r12d
0x18010de34  setz    bl
0x18010de37  xor     edx, edx; length
0x18010de39  mov     rcx, [rdi+8]; string
0x18010de3d  call    cs:__imp_WindowsGetStringRawBuffer
0x18010de43  mov     rdx, rax
0x18010de46  mov     r8b, bl
0x18010de49  lea     rcx, [rbp+pszPath]
0x18010de4d  call    ?TryGetStagedPackagePathByFullNameAlloc@Common@ShellMRTHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG_N@Z; ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(ushort const *,bool)
0x18010de52  mov     rcx, [rbp+pszPath]; pszPath
0x18010de56  test    rcx, rcx
0x18010de59  jz      loc_18010DF67
0x18010de5f  mov     edi, 1
0x18010de64  cmp     [rbp+arg_0], r12d
0x18010de68  jz      loc_18010DF39
0x18010de6e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18010de72  inc     rdx
0x18010de75  cmp     [rcx+rdx*2], r12w
0x18010de7a  jnz     short loc_18010DE72
0x18010de7c  inc     rdx; cchPath
0x18010de7f  call    cs:__imp_PathCchRemoveFileSpec
0x18010de85  mov     ebx, eax
0x18010de87  test    eax, eax
0x18010de89  jns     short loc_18010DEBB
0x18010de8b  mov     edx, 11Bh; void *
0x18010de90  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18010de97  mov     r9d, ebx; char *
0x18010de9a  mov     rcx, [rbp+38h]; this
0x18010de9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010dea3  mov     rcx, [rbp+pszPath]; pv
0x18010dea7  test    rcx, rcx
0x18010deaa  jz      loc_18010DDF3
0x18010deb0  call    cs:__imp_CoTaskMemFree
0x18010deb6  jmp     loc_18010DDF3
0x18010debb  mov     [rbp+ppszPathOut], r12
0x18010debf  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18010dec3  mov     r8d, edi; dwFlags
0x18010dec6  lea     rdx, ?c_msResourcesRedirectFolderName@Common@ShellMRTHelper@@3QBGB; "Resources"
0x18010decd  mov     rcx, [rbp+pszPath]; pszPathIn
0x18010ded1  call    cs:__imp_PathAllocCombine
0x18010ded7  mov     ebx, eax
0x18010ded9  test    eax, eax
0x18010dedb  jns     short loc_18010DF00
0x18010dedd  mov     edx, 11Dh; void *
0x18010dee2  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18010dee9  mov     r9d, ebx; char *
0x18010deec  mov     rcx, [rbp+38h]; this
0x18010def0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010def5  lea     rcx, [rbp+ppszPathOut]
0x18010def9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010defe  jmp     short loc_18010DEA3
0x18010df00  xor     edx, edx
0x18010df02  lea     rcx, [rbp+pszPath]
0x18010df06  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010df0b  lea     r9, [rbp+pszPath]; ppszPathOut
0x18010df0f  mov     r8d, edi; dwFlags
0x18010df12  mov     rdx, r15; pszMore
0x18010df15  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18010df19  call    cs:__imp_PathAllocCombine
0x18010df1f  mov     ebx, eax
0x18010df21  test    eax, eax
0x18010df23  jns     short loc_18010DF2C
0x18010df25  mov     edx, 11Eh
0x18010df2a  jmp     short loc_18010DEE2
0x18010df2c  lea     rcx, [rbp+ppszPathOut]
0x18010df30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010df35  mov     rcx, [rbp+pszPath]; pszPathIn
0x18010df39  mov     r9, rsi; ppszPathOut
0x18010df3c  mov     r8d, edi; dwFlags
0x18010df3f  mov     rdx, r14; pszMore
0x18010df42  call    cs:__imp_PathAllocCombine
0x18010df48  mov     ebx, eax
0x18010df4a  test    eax, eax
0x18010df4c  jns     short loc_18010DF58
0x18010df4e  mov     edx, 121h
0x18010df53  jmp     loc_18010DE90
0x18010df58  mov     rcx, [rbp+pszPath]; pv
0x18010df5c  test    rcx, rcx
0x18010df5f  jz      short loc_18010DF67
0x18010df61  call    cs:__imp_CoTaskMemFree
0x18010df67  xor     eax, eax
0x18010df69  add     rsp, 20h
0x18010df6d  pop     r15
0x18010df6f  pop     r14
0x18010df71  pop     r12
0x18010df73  pop     rdi
0x18010df74  pop     rsi
0x18010df75  pop     rbx
0x18010df76  pop     rbp
0x18010df77  retn
```
