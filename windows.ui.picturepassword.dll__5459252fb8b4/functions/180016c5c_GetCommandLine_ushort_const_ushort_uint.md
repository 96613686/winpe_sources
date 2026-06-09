# _GetCommandLine(ushort const *,ushort *,uint)

- ea: `0x180016c5c`
- end: `0x180016d06`
- name: `?_GetCommandLine@@YAJPEBGPEAGI@Z`
- size: `170`
- prototype: `HRESULT __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180016dfc`

## callees

- `0x180002610`
- `0x1800092b8`
- `0x18000a254`
- `0x180016c5c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016c89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016c89`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180016cb2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180016cb2`

## string_xrefs

- `0x180016ca1`: `rundll32.exe`

## pseudocode

```c
HRESULT __fastcall _GetCommandLine(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT result; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 || (result = ResultFromKnownLastError(), result >= 0) )
  {
    result = PathCchAppend(Buffer, 0x104u, L"rundll32.exe");
    if ( result >= 0 )
      return StringCchPrintfW(
               a2,
               0x104u,
               L"\"%s\" %s %s",
               Buffer,
               L"-localserver",
               L"22d8c27b-47a1-48d1-ad08-7da7abd79617");
  }
  return result;
}

```

## disassembly

```asm
0x180016c5c  push    rbx
0x180016c5e  sub     rsp, 250h
0x180016c65  mov     rax, cs:__security_cookie
0x180016c6c  xor     rax, rsp
0x180016c6f  mov     [rsp+258h+var_18], rax
0x180016c77  xor     eax, eax
0x180016c79  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180016c7e  mov     [rdx], ax
0x180016c81  mov     rbx, rdx
0x180016c84  mov     edx, 104h; uSize
0x180016c89  call    cs:__imp_GetSystemDirectoryW
0x180016c8f  dec     eax
0x180016c91  cmp     eax, 102h
0x180016c96  jbe     short loc_180016CA1
0x180016c98  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016c9d  test    eax, eax
0x180016c9f  js      short loc_180016CED
0x180016ca1  lea     r8, aRundll32Exe; "rundll32.exe"
0x180016ca8  mov     edx, 104h; cchPath
0x180016cad  lea     rcx, [rsp+258h+Buffer]; pszPath
0x180016cb2  call    cs:__imp_PathCchAppend
0x180016cb8  test    eax, eax
0x180016cba  js      short loc_180016CED
0x180016cbc  lea     rax, Name; "22d8c27b-47a1-48d1-ad08-7da7abd79617"
0x180016cc3  mov     edx, 104h; unsigned __int64
0x180016cc8  mov     [rsp+258h+var_230], rax
0x180016ccd  lea     r9, [rsp+258h+Buffer]
0x180016cd2  lea     rax, aLocalserver; "-localserver"
0x180016cd9  mov     rcx, rbx; unsigned __int16 *
0x180016cdc  lea     r8, aSSS; "\"%s\" %s %s"
0x180016ce3  mov     [rsp+258h+var_238], rax
0x180016ce8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016ced  mov     rcx, [rsp+258h+var_18]
0x180016cf5  xor     rcx, rsp; StackCookie
0x180016cf8  call    __security_check_cookie
0x180016cfd  add     rsp, 250h
0x180016d04  pop     rbx
0x180016d05  retn
```
