# CommonUtilities::CreateDirectoryW(ushort const *)

- ea: `0x140080d18`
- end: `0x140080e88`
- name: `?CreateDirectoryW@CommonUtilities@@YAKPEBG@Z`
- size: `368`
- prototype: `unsigned int __fastcall(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140080ed8`
- `0x1400a8fd0`
- `0x1400b61e0`

## callees

- `0x140080d18`
- `0x1400a5420`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140080d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140080e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140080d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140080e15`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140080d3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140080d3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x140080dc2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x140080dc2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140080d5a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140080e05`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140080d5a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140080e05`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140080e2d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140080e2d`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x140080da9`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x140080da9`

## pseudocode

```c
DWORD __fastcall CommonUtilities::CreateDirectoryW(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *a2)
{
  DWORD result; // eax
  size_t *v4; // r8
  unsigned int v5; // r11d
  LPWSTR v6; // rbx
  WCHAR v7; // ax
  DWORD FileAttributesW; // eax
  size_t v9; // [rsp+20h] [rbp-238h]
  wchar_t pszDest[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !PathIsRelativeW(pszSrc) )
  {
    if ( CreateDirectoryW(pszSrc, 0) )
      return 0;
    result = GetLastError();
    if ( result != 3 )
      return result;
    if ( StringCopyWorkerW(pszDest, 0x104u, v4, pszSrc, v9) < 0 || PathCchAddBackslash(pszDest, v5) < 0 )
      return 206;
    v6 = PathSkipRootW(pszDest);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        do
        {
          if ( v7 == 92 )
            break;
          v7 = *++v6;
        }
        while ( *v6 );
        if ( *v6 )
        {
          *v6 = 0;
          if ( !CreateDirectoryW(pszDest, 0) )
          {
            result = GetLastError();
            if ( result != 183 )
              return result;
            FileAttributesW = GetFileAttributesW(pszDest);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return 183;
          }
        }
        *v6++ = 92;
      }
      return 0;
    }
  }
  return 161;
}

```

## disassembly

```asm
0x140080d18  mov     [rsp+arg_8], rbx
0x140080d1d  mov     [rsp+arg_10], rbp
0x140080d22  push    rdi
0x140080d23  sub     rsp, 250h
0x140080d2a  mov     rax, cs:__security_cookie
0x140080d31  xor     rax, rsp
0x140080d34  mov     [rsp+258h+var_18], rax
0x140080d3c  mov     rbx, rcx
0x140080d3f  call    cs:__imp_PathIsRelativeW
0x140080d46  nop     dword ptr [rax+rax+00h]
0x140080d4b  xor     edi, edi
0x140080d4d  test    eax, eax
0x140080d4f  jnz     loc_140080E5D
0x140080d55  xor     edx, edx; lpSecurityAttributes
0x140080d57  mov     rcx, rbx; lpPathName
0x140080d5a  call    cs:__imp_CreateDirectoryW
0x140080d61  nop     dword ptr [rax+rax+00h]
0x140080d66  test    eax, eax
0x140080d68  jnz     loc_140080E59
0x140080d6e  call    cs:__imp_GetLastError
0x140080d75  nop     dword ptr [rax+rax+00h]
0x140080d7a  cmp     eax, 3
0x140080d7d  jnz     loc_140080E62
0x140080d83  mov     r11d, 104h
0x140080d89  lea     rcx, [rsp+258h+pszDest]; pszDest
0x140080d8e  mov     edx, r11d; cchDest
0x140080d91  mov     r9, rbx; pszSrc
0x140080d94  call    StringCopyWorkerW
0x140080d99  test    eax, eax
0x140080d9b  js      loc_140080E52
0x140080da1  mov     edx, r11d; cchPath
0x140080da4  lea     rcx, [rsp+258h+pszDest]; pszPath
0x140080da9  call    cs:__imp_PathCchAddBackslash
0x140080db0  nop     dword ptr [rax+rax+00h]
0x140080db5  test    eax, eax
0x140080db7  js      loc_140080E52
0x140080dbd  lea     rcx, [rsp+258h+pszDest]; pszPath
0x140080dc2  call    cs:__imp_PathSkipRootW
0x140080dc9  nop     dword ptr [rax+rax+00h]
0x140080dce  mov     rbx, rax
0x140080dd1  test    rax, rax
0x140080dd4  jz      loc_140080E5D
0x140080dda  lea     ebp, [rdi+5Ch]
0x140080ddd  movzx   eax, word ptr [rbx]
0x140080de0  test    ax, ax
0x140080de3  jz      short loc_140080E59
0x140080de5  cmp     ax, bp
0x140080de8  jz      short loc_140080DF6
0x140080dea  add     rbx, 2
0x140080dee  movzx   eax, word ptr [rbx]
0x140080df1  test    ax, ax
0x140080df4  jnz     short loc_140080DE5
0x140080df6  cmp     [rbx], di
0x140080df9  jz      short loc_140080E42
0x140080dfb  xor     edx, edx; lpSecurityAttributes
0x140080dfd  mov     [rbx], di
0x140080e00  lea     rcx, [rsp+258h+pszDest]; lpPathName
0x140080e05  call    cs:__imp_CreateDirectoryW
0x140080e0c  nop     dword ptr [rax+rax+00h]
0x140080e11  test    eax, eax
0x140080e13  jnz     short loc_140080E42
0x140080e15  call    cs:__imp_GetLastError
0x140080e1c  nop     dword ptr [rax+rax+00h]
0x140080e21  cmp     eax, 0B7h
0x140080e26  jnz     short loc_140080E62
0x140080e28  lea     rcx, [rsp+258h+pszDest]; lpFileName
0x140080e2d  call    cs:__imp_GetFileAttributesW
0x140080e34  nop     dword ptr [rax+rax+00h]
0x140080e39  cmp     eax, 0FFFFFFFFh
0x140080e3c  jz      short loc_140080E4B
0x140080e3e  test    al, 10h
0x140080e40  jz      short loc_140080E4B
0x140080e42  mov     [rbx], bp
0x140080e45  add     rbx, 2
0x140080e49  jmp     short loc_140080DDD
0x140080e4b  mov     eax, 0B7h
0x140080e50  jmp     short loc_140080E62
0x140080e52  mov     eax, 0CEh
0x140080e57  jmp     short loc_140080E62
0x140080e59  xor     eax, eax
0x140080e5b  jmp     short loc_140080E62
0x140080e5d  mov     eax, 0A1h
0x140080e62  mov     rcx, [rsp+258h+var_18]
0x140080e6a  xor     rcx, rsp; StackCookie
0x140080e6d  call    __security_check_cookie
0x140080e72  lea     r11, [rsp+258h+var_8]
0x140080e7a  mov     rbx, [r11+18h]
0x140080e7e  mov     rbp, [r11+20h]
0x140080e82  mov     rsp, r11
0x140080e85  pop     rdi
0x140080e86  retn
```
