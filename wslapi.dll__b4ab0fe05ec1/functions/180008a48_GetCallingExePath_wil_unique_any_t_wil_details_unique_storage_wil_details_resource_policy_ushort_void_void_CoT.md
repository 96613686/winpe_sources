# _GetCallingExePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180008a48`
- end: `0x180008bd2`
- name: `?_GetCallingExePath@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(void **, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x180007344`
- `0x1800093ec`

## callees

- `0x180001dc0`
- `0x180004fb4`
- `0x180004fd4`
- `0x18000698c`
- `0x180006b80`
- `0x180008454`
- `0x180008678`
- `0x180008a48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008ab8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008ab8`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008b0c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180008b0c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180008aca`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180008aca`

## string_xrefs

- `0x180008b98`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall _GetCallingExePath(void **a1, __int64 a2, __int64 a3, const char *a4)
{
  unsigned int i; // edi
  const char *v6; // r9
  WCHAR *v7; // rbx
  HANDLE CurrentProcess; // rax
  const char *v9; // r9
  unsigned int LastError; // ebx
  HRESULT v11; // eax
  LPWSTR lpExeName; // [rsp+20h] [rbp-20h] BYREF
  void *v14; // [rsp+28h] [rbp-18h] BYREF
  DWORD dwSize; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  for ( i = 260; ; i *= 2 )
  {
    if ( i >= 0x7FE7 )
      return 0;
    if ( !i )
      break;
    dwSize = i - 1;
    lpExeName = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpExeName,
      0,
      i,
      a4);
    v7 = lpExeName;
    if ( !lpExeName )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0xFDC,
        (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, v7, &dwSize) )
    {
      v11 = PathCchRemoveFileSpec(lpExeName, i);
      LastError = v11;
      if ( v11 >= 0 )
      {
        v14 = *a1;
        *a1 = 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a1,
          &lpExeName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &lpExeName,
          &v14);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpExeName);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
        (const char *)(unsigned int)v11,
        (int)lpExeName);
      goto LABEL_11;
    }
    if ( GetLastError() != 122 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x98,
                    (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
                    v9);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpExeName);
      return LastError;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpExeName);
  }
  LastError = -2147024362;
  dwSize = -1;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
    (const char *)0x80070216LL,
    (int)lpExeName);
  return LastError;
}

```

## disassembly

```asm
0x180008a48  mov     [rsp-18h+arg_8], rbx
0x180008a4d  mov     [rsp-18h+arg_10], rsi
0x180008a52  push    rbp
0x180008a53  push    rdi
0x180008a54  push    r14
0x180008a56  mov     rbp, rsp
0x180008a59  sub     rsp, 40h
0x180008a5d  mov     rax, cs:__security_cookie
0x180008a64  xor     rax, rsp
0x180008a67  mov     [rbp+var_8], rax
0x180008a6b  mov     rsi, rcx
0x180008a6e  mov     edi, 104h
0x180008a73  cmp     edi, 7FE7h
0x180008a79  jnb     loc_180008B77
0x180008a7f  cmp     edi, 1
0x180008a82  jb      loc_180008BAA
0x180008a88  lea     eax, [rdi-1]
0x180008a8b  mov     r8d, edi
0x180008a8e  xor     edx, edx
0x180008a90  mov     [rbp+dwSize], eax
0x180008a93  lea     rcx, [rbp+lpExeName]
0x180008a97  mov     [rbp+lpExeName], 0
0x180008a9f  mov     r14d, edi
0x180008aa2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180008aa7  mov     rbx, [rbp+lpExeName]
0x180008aab  mov     rcx, [rbp+18h]; this
0x180008aaf  test    rbx, rbx
0x180008ab2  jz      loc_180008B98
0x180008ab8  call    cs:__imp_GetCurrentProcess
0x180008abe  lea     r9, [rbp+dwSize]; lpdwSize
0x180008ac2  mov     r8, rbx; lpExeName
0x180008ac5  mov     rcx, rax; hProcess
0x180008ac8  xor     edx, edx; dwFlags
0x180008aca  call    cs:__imp_QueryFullProcessImageNameW
0x180008ad0  test    eax, eax
0x180008ad2  jnz     short loc_180008B05
0x180008ad4  call    cs:__imp_GetLastError
0x180008ada  cmp     eax, 7Ah ; 'z'
0x180008add  jnz     short loc_180008AEC
0x180008adf  add     edi, edi
0x180008ae1  lea     rcx, [rbp+lpExeName]
0x180008ae5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008aea  jmp     short loc_180008A73
0x180008aec  mov     rcx, [rbp+18h]; this
0x180008af0  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008af7  mov     edx, 98h; void *
0x180008afc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b01  mov     ebx, eax
0x180008b03  jmp     short loc_180008B30
0x180008b05  mov     rcx, [rbp+lpExeName]; pszPath
0x180008b09  mov     rdx, r14; cchPath
0x180008b0c  call    cs:__imp_PathCchRemoveFileSpec
0x180008b12  mov     ebx, eax
0x180008b14  test    eax, eax
0x180008b16  jns     short loc_180008B3E
0x180008b18  mov     rcx, [rbp+18h]; this
0x180008b1c  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008b23  mov     r9d, eax; char *
0x180008b26  mov     edx, 9Eh; void *
0x180008b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b30  lea     rcx, [rbp+lpExeName]
0x180008b34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008b39  jmp     loc_180008BCE
0x180008b3e  mov     rax, [rsi]
0x180008b41  lea     rdx, [rbp+lpExeName]
0x180008b45  mov     rcx, rsi
0x180008b48  mov     [rbp+var_18], rax
0x180008b4c  mov     qword ptr [rsi], 0
0x180008b53  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180008b58  lea     rdx, [rbp+var_18]
0x180008b5c  lea     rcx, [rbp+lpExeName]
0x180008b60  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180008b65  lea     rcx, [rbp+var_18]
0x180008b69  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008b6e  lea     rcx, [rbp+lpExeName]
0x180008b72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008b77  xor     eax, eax
0x180008b79  mov     rcx, [rbp+var_8]
0x180008b7d  xor     rcx, rsp; StackCookie
0x180008b80  call    __security_check_cookie
0x180008b85  mov     rbx, [rsp+40h+arg_8]
0x180008b8a  mov     rsi, [rsp+40h+arg_10]
0x180008b8f  add     rsp, 40h
0x180008b93  pop     r14
0x180008b95  pop     rdi
0x180008b96  pop     rbp
0x180008b97  retn
0x180008b98  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008b9f  mov     edx, 0FDCh; void *
0x180008ba4  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180008baa  mov     rcx, [rbp+18h]; this
0x180008bae  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008bb5  mov     ebx, 80070216h
0x180008bba  mov     [rbp+dwSize], 0FFFFFFFFh
0x180008bc1  mov     r9d, ebx; char *
0x180008bc4  mov     edx, 8Dh; void *
0x180008bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bce  mov     eax, ebx
0x180008bd0  jmp     short loc_180008B79
```
