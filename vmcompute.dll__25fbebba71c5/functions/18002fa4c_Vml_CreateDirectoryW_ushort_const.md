# Vml::CreateDirectoryW(ushort const *)

- ea: `0x18002fa4c`
- end: `0x18002fbda`
- name: `?CreateDirectoryW@Vml@@YAKPEBG@Z`
- size: `398`
- prototype: `unsigned int __fastcall(LPCWSTR lpPathName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180035610`
- `0x1800362d0`
- `0x180053208`

## callees

- `0x180002f50`
- `0x18002fa4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fa8e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fb6f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fa8e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fb6f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002fb94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002fb94`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002fb27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002fb27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18002fa6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18002fa6d`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002fb12`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002fb12`

## pseudocode

```c
__int64 __fastcall Vml::CreateDirectoryW(LPCWSTR lpPathName, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  WCHAR *v7; // rcx
  LPWSTR v8; // rax
  LPWSTR v9; // rdi
  WCHAR v10; // ax
  DWORD v11; // eax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-248h] BYREF

  v2 = lpPathName;
  if ( PathIsRelativeW(lpPathName) )
    return 161;
  if ( CreateDirectoryW(v2, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError != 3 )
    return LastError;
  v4 = pszPath;
  v5 = 260;
  v6 = 2147483646;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v6;
    --v5;
  }
  while ( v5 );
  v7 = v4 - 1;
  if ( v5 )
    v7 = v4;
  *v7 = 0;
  if ( !v5 || PathCchAddBackslash(pszPath, 0x104u) < 0 )
    return 206;
  v8 = PathSkipRootW(pszPath);
  v9 = v8;
  if ( v8 )
  {
    if ( *v8 )
    {
      LastError = 183;
      while ( 1 )
      {
        v10 = *v9;
        do
        {
          if ( v10 == 92 )
            break;
          v10 = *++v9;
        }
        while ( *v9 );
        if ( *v9 )
        {
          *v9 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            v11 = GetLastError();
            if ( v11 != 183 )
              return v11;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return LastError;
          }
        }
        *v9++ = 92;
        if ( !*v9 )
          return 0;
      }
    }
    return 0;
  }
  return 161;
}

```

## disassembly

```asm
0x18002fa4c  push    rbx
0x18002fa4e  push    rbp
0x18002fa4f  push    rsi
0x18002fa50  push    rdi
0x18002fa51  sub     rsp, 248h
0x18002fa58  mov     rax, cs:__security_cookie
0x18002fa5f  xor     rax, rsp
0x18002fa62  mov     [rsp+268h+var_38], rax
0x18002fa6a  mov     rdi, rcx
0x18002fa6d  call    cs:__imp_PathIsRelativeW
0x18002fa74  nop     dword ptr [rax+rax+00h]
0x18002fa79  xor     esi, esi
0x18002fa7b  test    eax, eax
0x18002fa7d  jz      short loc_18002FA89
0x18002fa7f  mov     ebx, 0A1h
0x18002fa84  jmp     loc_18002FBB7
0x18002fa89  xor     edx, edx; lpSecurityAttributes
0x18002fa8b  mov     rcx, rdi; lpPathName
0x18002fa8e  call    cs:__imp_CreateDirectoryW
0x18002fa95  nop     dword ptr [rax+rax+00h]
0x18002fa9a  test    eax, eax
0x18002fa9c  jnz     loc_18002FBB5
0x18002faa2  call    cs:__imp_GetLastError
0x18002faa9  nop     dword ptr [rax+rax+00h]
0x18002faae  mov     ebx, eax
0x18002fab0  cmp     eax, 3
0x18002fab3  jnz     loc_18002FBB7
0x18002fab9  mov     r9d, 104h
0x18002fabf  lea     rax, [rsp+268h+pszPath]
0x18002fac4  mov     edx, r9d
0x18002fac7  mov     ecx, 7FFFFFFEh
0x18002facc  test    rcx, rcx
0x18002facf  jz      short loc_18002FAF0
0x18002fad1  movzx   r8d, word ptr [rdi]
0x18002fad5  test    r8w, r8w
0x18002fad9  jz      short loc_18002FAF0
0x18002fadb  mov     [rax], r8w
0x18002fadf  add     rdi, 2
0x18002fae3  add     rax, 2
0x18002fae7  dec     rcx
0x18002faea  sub     rdx, 1
0x18002faee  jnz     short loc_18002FACC
0x18002faf0  test    rdx, rdx
0x18002faf3  lea     rcx, [rax-2]
0x18002faf7  cmovnz  rcx, rax
0x18002fafb  mov     [rcx], si
0x18002fafe  jnz     short loc_18002FB0A
0x18002fb00  mov     ebx, 0CEh
0x18002fb05  jmp     loc_18002FBB7
0x18002fb0a  mov     rdx, r9; cchPath
0x18002fb0d  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18002fb12  call    cs:__imp_PathCchAddBackslash
0x18002fb19  nop     dword ptr [rax+rax+00h]
0x18002fb1e  test    eax, eax
0x18002fb20  js      short loc_18002FB00
0x18002fb22  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18002fb27  call    cs:__imp_PathSkipRootW
0x18002fb2e  nop     dword ptr [rax+rax+00h]
0x18002fb33  mov     rdi, rax
0x18002fb36  test    rax, rax
0x18002fb39  jz      loc_18002FA7F
0x18002fb3f  cmp     [rax], si
0x18002fb42  jz      short loc_18002FBB5
0x18002fb44  mov     ebp, 5Ch ; '\'
0x18002fb49  lea     ebx, [rbp+5Bh]
0x18002fb4c  movzx   eax, word ptr [rdi]
0x18002fb4f  cmp     ax, bp
0x18002fb52  jz      short loc_18002FB60
0x18002fb54  add     rdi, 2
0x18002fb58  movzx   eax, word ptr [rdi]
0x18002fb5b  test    ax, ax
0x18002fb5e  jnz     short loc_18002FB4F
0x18002fb60  cmp     [rdi], si
0x18002fb63  jz      short loc_18002FBA9
0x18002fb65  xor     edx, edx; lpSecurityAttributes
0x18002fb67  mov     [rdi], si
0x18002fb6a  lea     rcx, [rsp+268h+pszPath]; lpPathName
0x18002fb6f  call    cs:__imp_CreateDirectoryW
0x18002fb76  nop     dword ptr [rax+rax+00h]
0x18002fb7b  test    eax, eax
0x18002fb7d  jnz     short loc_18002FBA9
0x18002fb7f  call    cs:__imp_GetLastError
0x18002fb86  nop     dword ptr [rax+rax+00h]
0x18002fb8b  cmp     eax, ebx
0x18002fb8d  jnz     short loc_18002FBD6
0x18002fb8f  lea     rcx, [rsp+268h+pszPath]; lpFileName
0x18002fb94  call    cs:__imp_GetFileAttributesW
0x18002fb9b  nop     dword ptr [rax+rax+00h]
0x18002fba0  cmp     eax, 0FFFFFFFFh
0x18002fba3  jz      short loc_18002FBB7
0x18002fba5  test    al, 10h
0x18002fba7  jz      short loc_18002FBB7
0x18002fba9  mov     [rdi], bp
0x18002fbac  add     rdi, 2
0x18002fbb0  cmp     [rdi], si
0x18002fbb3  jnz     short loc_18002FB4C
0x18002fbb5  mov     ebx, esi
0x18002fbb7  mov     eax, ebx
0x18002fbb9  mov     rcx, [rsp+268h+var_38]
0x18002fbc1  xor     rcx, rsp; StackCookie
0x18002fbc4  call    __security_check_cookie
0x18002fbc9  add     rsp, 248h
0x18002fbd0  pop     rdi
0x18002fbd1  pop     rsi
0x18002fbd2  pop     rbp
0x18002fbd3  pop     rbx
0x18002fbd4  retn
0x18002fbd6  mov     ebx, eax
0x18002fbd8  jmp     short loc_18002FBB7
```
