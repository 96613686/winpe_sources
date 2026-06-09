# GetKnownFolderSubFolder(_GUID const &,ushort const *,ushort const *,Windows::Internal::String *)

- ea: `0x18008b6a0`
- end: `0x18008b861`
- name: `?GetKnownFolderSubFolder@@YAJAEBU_GUID@@PEBG1PEAVString@Internal@Windows@@@Z`
- size: `449`
- prototype: `int(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180020760`
- `0x18011ecd8`
- `0x18011fd44`

## callees

- `0x1800237c8`
- `0x18008a6f0`
- `0x18008b6a0`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008b773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008b773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b78a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b78a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b79a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b79a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b816`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008b730`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008b844`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008b730`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008b844`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18008b70a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18008b70a`

## string_xrefs

- `0x18008b7d7`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18008b7f8`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
__int64 __fastcall GetKnownFolderSubFolder(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  unsigned __int64 v7; // rdi
  HRESULT v8; // eax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  HSTRING v11; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  HRESULT v15; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPathOut[520]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  ppszPath = 0;
  v17 = 0;
  v18 = 0;
  if ( !a4 )
  {
    v9 = -2147467261;
    v13 = 139;
    goto LABEL_14;
  }
  v7 = -1;
  v17 = -1;
  v18 = -1;
  v8 = SHGetKnownFolderPath(a1, 0x8000u, 0, &ppszPath);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v8,
      (int)ppszPath);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return v9;
  }
  v10 = PathCchCombine(pszPathOut, 0x208u, ppszPath, a2);
  v9 = v10;
  if ( v10 < 0 )
  {
    v14 = (unsigned int)v10;
    v13 = 143;
    goto LABEL_15;
  }
  if ( a3 )
  {
    v15 = PathCchCombine(pszPathOut, 0x208u, pszPathOut, a3);
    v9 = v15;
    if ( v15 < 0 )
    {
      v14 = (unsigned int)v15;
      v13 = 147;
      goto LABEL_15;
    }
  }
  string = 0;
  do
    ++v7;
  while ( pszPathOut[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    v9 = -2147024362;
    goto LABEL_13;
  }
  v9 = WindowsCreateString(pszPathOut, v7, &string);
  if ( (v9 & 0x80000000) != 0 )
  {
LABEL_13:
    v13 = 150;
LABEL_14:
    v14 = v9;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)v14,
      (int)ppszPath);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    return v9;
  }
  v11 = *a4;
  *a4 = string;
  WindowsDeleteString(v11);
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 0;
}

```

## disassembly

```asm
0x18008b6a0  push    rbp
0x18008b6a2  push    rbx
0x18008b6a3  push    rsi
0x18008b6a4  push    rdi
0x18008b6a5  push    r12
0x18008b6a7  push    r14
0x18008b6a9  push    r15
0x18008b6ab  lea     rbp, [rsp-360h]
0x18008b6b3  sub     rsp, 460h
0x18008b6ba  mov     rax, cs:__security_cookie
0x18008b6c1  xor     rax, rsp
0x18008b6c4  mov     [rbp+390h+var_40], rax
0x18008b6cb  xor     r12d, r12d
0x18008b6ce  mov     rsi, r9
0x18008b6d1  mov     [rsp+490h+ppszPath], r12; int
0x18008b6d6  mov     r14, r8
0x18008b6d9  mov     [rsp+490h+var_468], r12
0x18008b6de  mov     r15, rdx
0x18008b6e1  mov     [rsp+490h+var_460], r12
0x18008b6e6  test    r9, r9
0x18008b6e9  jz      loc_18008B81E
0x18008b6ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008b6f3  lea     r9, [rsp+490h+ppszPath]; ppszPath
0x18008b6f8  xor     r8d, r8d; hToken
0x18008b6fb  mov     [rsp+490h+var_468], rdi
0x18008b700  mov     edx, 8000h; dwFlags
0x18008b705  mov     [rsp+490h+var_460], rdi
0x18008b70a  call    cs:__imp_SHGetKnownFolderPath
0x18008b710  mov     ebx, eax
0x18008b712  test    eax, eax
0x18008b714  js      loc_18008B7F1
0x18008b71a  mov     r8, [rsp+490h+ppszPath]; pszPathIn
0x18008b71f  lea     rcx, [rsp+490h+pszPathOut]; pszPathOut
0x18008b724  mov     r9, r15; pszMore
0x18008b727  mov     r15d, 208h
0x18008b72d  mov     edx, r15d; cchPathOut
0x18008b730  call    cs:__imp_PathCchCombine
0x18008b736  mov     ebx, eax
0x18008b738  test    eax, eax
0x18008b73a  js      loc_18008B82A
0x18008b740  test    r14, r14
0x18008b743  jnz     loc_18008B834
0x18008b749  mov     [rsp+490h+string], r12
0x18008b74e  lea     rax, [rsp+490h+pszPathOut]
0x18008b753  inc     rdi
0x18008b756  cmp     [rax+rdi*2], r12w
0x18008b75b  jnz     short loc_18008B753
0x18008b75d  mov     eax, 0FFFFFFFFh
0x18008b762  cmp     rdi, rax
0x18008b765  ja      short loc_18008B7C3
0x18008b767  mov     edx, edi; length
0x18008b769  lea     r8, [rsp+490h+string]; string
0x18008b76e  lea     rcx, [rsp+490h+pszPathOut]; sourceString
0x18008b773  call    cs:__imp_WindowsCreateString
0x18008b779  mov     ebx, eax
0x18008b77b  test    eax, eax
0x18008b77d  js      short loc_18008B7C8
0x18008b77f  mov     rax, [rsp+490h+string]
0x18008b784  mov     rcx, [rsi]; string
0x18008b787  mov     [rsi], rax
0x18008b78a  call    cs:__imp_WindowsDeleteString
0x18008b790  mov     rcx, [rsp+490h+ppszPath]; pv
0x18008b795  test    rcx, rcx
0x18008b798  jz      short loc_18008B7A0
0x18008b79a  call    cs:__imp_CoTaskMemFree
0x18008b7a0  xor     eax, eax
0x18008b7a2  mov     rcx, [rbp+390h+var_40]
0x18008b7a9  xor     rcx, rsp; StackCookie
0x18008b7ac  call    __security_check_cookie
0x18008b7b1  add     rsp, 460h
0x18008b7b8  pop     r15
0x18008b7ba  pop     r14
0x18008b7bc  pop     r12
0x18008b7be  pop     rdi
0x18008b7bf  pop     rsi
0x18008b7c0  pop     rbx
0x18008b7c1  pop     rbp
0x18008b7c2  retn
0x18008b7c3  mov     ebx, 80070216h
0x18008b7c8  mov     edx, 96h; void *
0x18008b7cd  mov     r9d, ebx; char *
0x18008b7d0  mov     rcx, [rbp+398h]; this
0x18008b7d7  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18008b7de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b7e3  lea     rcx, [rsp+490h+ppszPath]
0x18008b7e8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008b7ed  mov     eax, ebx
0x18008b7ef  jmp     short loc_18008B7A2
0x18008b7f1  mov     rcx, [rbp+398h]; this
0x18008b7f8  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18008b7ff  mov     r9d, ebx; char *
0x18008b802  mov     edx, 8Dh; void *
0x18008b807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b80c  mov     rcx, [rsp+490h+ppszPath]; pv
0x18008b811  test    rcx, rcx
0x18008b814  jz      short loc_18008B7ED
0x18008b816  call    cs:__imp_CoTaskMemFree
0x18008b81c  jmp     short loc_18008B7ED
0x18008b81e  mov     ebx, 80004003h
0x18008b823  mov     edx, 8Bh
0x18008b828  jmp     short loc_18008B7CD
0x18008b82a  mov     r9d, eax
0x18008b82d  mov     edx, 8Fh
0x18008b832  jmp     short loc_18008B7D0
0x18008b834  mov     r9, r14; pszMore
0x18008b837  lea     r8, [rsp+490h+pszPathOut]; pszPathIn
0x18008b83c  mov     rdx, r15; cchPathOut
0x18008b83f  lea     rcx, [rsp+490h+pszPathOut]; pszPathOut
0x18008b844  call    cs:__imp_PathCchCombine
0x18008b84a  mov     ebx, eax
0x18008b84c  test    eax, eax
0x18008b84e  jns     loc_18008B749
0x18008b854  mov     r9d, eax
0x18008b857  mov     edx, 93h
0x18008b85c  jmp     loc_18008B7D0
```
