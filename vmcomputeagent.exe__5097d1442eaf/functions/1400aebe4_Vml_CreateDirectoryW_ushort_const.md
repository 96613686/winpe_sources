# Vml::CreateDirectoryW(ushort const *)

- ea: `0x1400aebe4`
- end: `0x1400aed41`
- name: `?CreateDirectoryW@Vml@@YAKPEBG@Z`
- size: `349`
- prototype: `unsigned int __fastcall(LPCWSTR lpPathName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1400ae8c8`
- `0x1400e0b10`

## callees

- `0x140005360`
- `0x1400aebe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aec2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aecf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aec2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aecf3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400aec05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400aec05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1400aeca7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1400aeca7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400aec20`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400aece9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400aec20`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400aece9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400aed02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400aed02`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1400aec98`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1400aec98`

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
0x1400aebe4  push    rbx
0x1400aebe6  push    rbp
0x1400aebe7  push    rsi
0x1400aebe8  push    rdi
0x1400aebe9  sub     rsp, 248h
0x1400aebf0  mov     rax, cs:__security_cookie
0x1400aebf7  xor     rax, rsp
0x1400aebfa  mov     [rsp+268h+var_38], rax
0x1400aec02  mov     rdi, rcx
0x1400aec05  call    cs:__imp_PathIsRelativeW
0x1400aec0b  xor     esi, esi
0x1400aec0d  test    eax, eax
0x1400aec0f  jz      short loc_1400AEC1B
0x1400aec11  mov     ebx, 0A1h
0x1400aec16  jmp     loc_1400AED1F
0x1400aec1b  xor     edx, edx; lpSecurityAttributes
0x1400aec1d  mov     rcx, rdi; lpPathName
0x1400aec20  call    cs:__imp_CreateDirectoryW
0x1400aec26  test    eax, eax
0x1400aec28  jnz     loc_1400AED1D
0x1400aec2e  call    cs:__imp_GetLastError
0x1400aec34  mov     ebx, eax
0x1400aec36  cmp     eax, 3
0x1400aec39  jnz     loc_1400AED1F
0x1400aec3f  mov     r9d, 104h
0x1400aec45  lea     rax, [rsp+268h+pszPath]
0x1400aec4a  mov     edx, r9d
0x1400aec4d  mov     ecx, 7FFFFFFEh
0x1400aec52  test    rcx, rcx
0x1400aec55  jz      short loc_1400AEC76
0x1400aec57  movzx   r8d, word ptr [rdi]
0x1400aec5b  test    r8w, r8w
0x1400aec5f  jz      short loc_1400AEC76
0x1400aec61  mov     [rax], r8w
0x1400aec65  add     rdi, 2
0x1400aec69  add     rax, 2
0x1400aec6d  dec     rcx
0x1400aec70  sub     rdx, 1
0x1400aec74  jnz     short loc_1400AEC52
0x1400aec76  test    rdx, rdx
0x1400aec79  lea     rcx, [rax-2]
0x1400aec7d  cmovnz  rcx, rax
0x1400aec81  mov     [rcx], si
0x1400aec84  jnz     short loc_1400AEC90
0x1400aec86  mov     ebx, 0CEh
0x1400aec8b  jmp     loc_1400AED1F
0x1400aec90  mov     rdx, r9; cchPath
0x1400aec93  lea     rcx, [rsp+268h+pszPath]; pszPath
0x1400aec98  call    cs:__imp_PathCchAddBackslash
0x1400aec9e  test    eax, eax
0x1400aeca0  js      short loc_1400AEC86
0x1400aeca2  lea     rcx, [rsp+268h+pszPath]; pszPath
0x1400aeca7  call    cs:__imp_PathSkipRootW
0x1400aecad  mov     rdi, rax
0x1400aecb0  test    rax, rax
0x1400aecb3  jz      loc_1400AEC11
0x1400aecb9  cmp     [rax], si
0x1400aecbc  jz      short loc_1400AED1D
0x1400aecbe  mov     ebp, 5Ch ; '\'
0x1400aecc3  lea     ebx, [rbp+5Bh]
0x1400aecc6  movzx   eax, word ptr [rdi]
0x1400aecc9  cmp     ax, bp
0x1400aeccc  jz      short loc_1400AECDA
0x1400aecce  add     rdi, 2
0x1400aecd2  movzx   eax, word ptr [rdi]
0x1400aecd5  test    ax, ax
0x1400aecd8  jnz     short loc_1400AECC9
0x1400aecda  cmp     [rdi], si
0x1400aecdd  jz      short loc_1400AED11
0x1400aecdf  xor     edx, edx; lpSecurityAttributes
0x1400aece1  mov     [rdi], si
0x1400aece4  lea     rcx, [rsp+268h+pszPath]; lpPathName
0x1400aece9  call    cs:__imp_CreateDirectoryW
0x1400aecef  test    eax, eax
0x1400aecf1  jnz     short loc_1400AED11
0x1400aecf3  call    cs:__imp_GetLastError
0x1400aecf9  cmp     eax, ebx
0x1400aecfb  jnz     short loc_1400AED3D
0x1400aecfd  lea     rcx, [rsp+268h+pszPath]; lpFileName
0x1400aed02  call    cs:__imp_GetFileAttributesW
0x1400aed08  cmp     eax, 0FFFFFFFFh
0x1400aed0b  jz      short loc_1400AED1F
0x1400aed0d  test    al, 10h
0x1400aed0f  jz      short loc_1400AED1F
0x1400aed11  mov     [rdi], bp
0x1400aed14  add     rdi, 2
0x1400aed18  cmp     [rdi], si
0x1400aed1b  jnz     short loc_1400AECC6
0x1400aed1d  mov     ebx, esi
0x1400aed1f  mov     eax, ebx
0x1400aed21  mov     rcx, [rsp+268h+var_38]
0x1400aed29  xor     rcx, rsp; StackCookie
0x1400aed2c  call    __security_check_cookie
0x1400aed31  add     rsp, 248h
0x1400aed38  pop     rdi
0x1400aed39  pop     rsi
0x1400aed3a  pop     rbp
0x1400aed3b  pop     rbx
0x1400aed3c  retn
0x1400aed3d  mov     ebx, eax
0x1400aed3f  jmp     short loc_1400AED1F
```
