# CommonUtilities::CreateDirectoryW(ushort const *)

- ea: `0x14019e7a0`
- end: `0x14019e910`
- name: `?CreateDirectoryW@CommonUtilities@@YAKPEBG@Z`
- size: `368`
- prototype: `unsigned int __fastcall(CommonUtilities *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14009310c`

## callees

- `0x1400c5b58`
- `0x14011ea40`
- `0x14019e7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14019e7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14019e89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14019e7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14019e89d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14019e8b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14019e8b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14019e7e2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14019e88d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14019e7e2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14019e88d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x14019e84a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x14019e84a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x14019e7c7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x14019e7c7`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x14019e831`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x14019e831`

## pseudocode

```c
DWORD __fastcall CommonUtilities::CreateDirectoryW(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD result; // eax
  unsigned int v4; // r11d
  LPWSTR v5; // rbx
  WCHAR v6; // ax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !PathIsRelativeW(this) )
  {
    if ( CreateDirectoryW(this, 0) )
      return 0;
    result = GetLastError();
    if ( result != 3 )
      return result;
    if ( StringCchCopyW(pszPath, 0x104u, this) < 0 || PathCchAddBackslash(pszPath, v4) < 0 )
      return 206;
    v5 = PathSkipRootW(pszPath);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = *v5;
        if ( !*v5 )
          break;
        do
        {
          if ( v6 == 92 )
            break;
          v6 = *++v5;
        }
        while ( *v5 );
        if ( *v5 )
        {
          *v5 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            result = GetLastError();
            if ( result != 183 )
              return result;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return 183;
          }
        }
        *v5++ = 92;
      }
      return 0;
    }
  }
  return 161;
}

```

## disassembly

```asm
0x14019e7a0  mov     [rsp+arg_8], rbx
0x14019e7a5  mov     [rsp+arg_10], rbp
0x14019e7aa  push    rdi
0x14019e7ab  sub     rsp, 240h
0x14019e7b2  mov     rax, cs:__security_cookie
0x14019e7b9  xor     rax, rsp
0x14019e7bc  mov     [rsp+248h+var_18], rax
0x14019e7c4  mov     rbx, rcx
0x14019e7c7  call    cs:__imp_PathIsRelativeW
0x14019e7ce  nop     dword ptr [rax+rax+00h]
0x14019e7d3  xor     edi, edi
0x14019e7d5  test    eax, eax
0x14019e7d7  jnz     loc_14019E8E5
0x14019e7dd  xor     edx, edx; lpSecurityAttributes
0x14019e7df  mov     rcx, rbx; lpPathName
0x14019e7e2  call    cs:__imp_CreateDirectoryW
0x14019e7e9  nop     dword ptr [rax+rax+00h]
0x14019e7ee  test    eax, eax
0x14019e7f0  jnz     loc_14019E8E1
0x14019e7f6  call    cs:__imp_GetLastError
0x14019e7fd  nop     dword ptr [rax+rax+00h]
0x14019e802  cmp     eax, 3
0x14019e805  jnz     loc_14019E8EA
0x14019e80b  mov     r11d, 104h
0x14019e811  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x14019e816  mov     edx, r11d; unsigned __int64
0x14019e819  mov     r8, rbx; unsigned __int16 *
0x14019e81c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14019e821  test    eax, eax
0x14019e823  js      loc_14019E8DA
0x14019e829  mov     edx, r11d; cchPath
0x14019e82c  lea     rcx, [rsp+248h+pszPath]; pszPath
0x14019e831  call    cs:__imp_PathCchAddBackslash
0x14019e838  nop     dword ptr [rax+rax+00h]
0x14019e83d  test    eax, eax
0x14019e83f  js      loc_14019E8DA
0x14019e845  lea     rcx, [rsp+248h+pszPath]; pszPath
0x14019e84a  call    cs:__imp_PathSkipRootW
0x14019e851  nop     dword ptr [rax+rax+00h]
0x14019e856  mov     rbx, rax
0x14019e859  test    rax, rax
0x14019e85c  jz      loc_14019E8E5
0x14019e862  lea     ebp, [rdi+5Ch]
0x14019e865  movzx   eax, word ptr [rbx]
0x14019e868  test    ax, ax
0x14019e86b  jz      short loc_14019E8E1
0x14019e86d  cmp     ax, bp
0x14019e870  jz      short loc_14019E87E
0x14019e872  add     rbx, 2
0x14019e876  movzx   eax, word ptr [rbx]
0x14019e879  test    ax, ax
0x14019e87c  jnz     short loc_14019E86D
0x14019e87e  cmp     [rbx], di
0x14019e881  jz      short loc_14019E8CA
0x14019e883  xor     edx, edx; lpSecurityAttributes
0x14019e885  mov     [rbx], di
0x14019e888  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x14019e88d  call    cs:__imp_CreateDirectoryW
0x14019e894  nop     dword ptr [rax+rax+00h]
0x14019e899  test    eax, eax
0x14019e89b  jnz     short loc_14019E8CA
0x14019e89d  call    cs:__imp_GetLastError
0x14019e8a4  nop     dword ptr [rax+rax+00h]
0x14019e8a9  cmp     eax, 0B7h
0x14019e8ae  jnz     short loc_14019E8EA
0x14019e8b0  lea     rcx, [rsp+248h+pszPath]; lpFileName
0x14019e8b5  call    cs:__imp_GetFileAttributesW
0x14019e8bc  nop     dword ptr [rax+rax+00h]
0x14019e8c1  cmp     eax, 0FFFFFFFFh
0x14019e8c4  jz      short loc_14019E8D3
0x14019e8c6  test    al, 10h
0x14019e8c8  jz      short loc_14019E8D3
0x14019e8ca  mov     [rbx], bp
0x14019e8cd  add     rbx, 2
0x14019e8d1  jmp     short loc_14019E865
0x14019e8d3  mov     eax, 0B7h
0x14019e8d8  jmp     short loc_14019E8EA
0x14019e8da  mov     eax, 0CEh
0x14019e8df  jmp     short loc_14019E8EA
0x14019e8e1  xor     eax, eax
0x14019e8e3  jmp     short loc_14019E8EA
0x14019e8e5  mov     eax, 0A1h
0x14019e8ea  mov     rcx, [rsp+248h+var_18]
0x14019e8f2  xor     rcx, rsp; StackCookie
0x14019e8f5  call    __security_check_cookie
0x14019e8fa  lea     r11, [rsp+248h+var_8]
0x14019e902  mov     rbx, [r11+18h]
0x14019e906  mov     rbp, [r11+20h]
0x14019e90a  mov     rsp, r11
0x14019e90d  pop     rdi
0x14019e90e  retn
```
