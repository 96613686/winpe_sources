# PathFindOnPathExA

- ea: `0x180018dd0`
- end: `0x18001901b`
- name: `PathFindOnPathExA`
- size: `587`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180018dc0`

## callees

- `0x180012550`
- `0x180017344`
- `0x1800185b0`
- `0x180018ce0`
- `0x180018dd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018f16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180018e76`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180018e76`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180018eaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180018eaf`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180018f00`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180018f35`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180018f00`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180018f35`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x180018e4f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x180018e4f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018e84`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018eca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018f93`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018e84`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018eca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendA` at `0x180018f93`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesA` at `0x180018e23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesA` at `0x180018e23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecA` at `0x180018e12`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecA` at `0x180018e12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180018f7b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180018f7b`

## pseudocode

```c
__int64 __fastcall PathFindOnPathExA(STRSAFE_LPSTR pszDest, LPCSTR *a2)
{
  int v4; // ebx
  const CHAR *v5; // rdx
  signed int EnvironmentVariableA; // eax
  DWORD v7; // esi
  CHAR *v8; // rax
  CHAR *v9; // rbx
  CHAR *PathA; // r14
  LPCSTR *i; // rsi
  CHAR pszDesta[272]; // [rsp+20h] [rbp-E0h] BYREF
  CHAR Buffer[256]; // [rsp+130h] [rbp+30h] BYREF

  if ( !pszDest || !PathIsFileSpecA(pszDest) )
    return 0;
  PathUnquoteSpacesA(pszDest);
  v4 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v5 = a2[v4];
      if ( !v5 || !*v5 )
        break;
      PathCombineA(pszDesta, v5, pszDest);
      if ( (unsigned int)PathFileExistsDefExtA(pszDesta) )
        goto LABEL_30;
      ++v4;
    }
  }
  GetSystemDirectoryA(pszDesta, 0x104u);
  if ( !PathAppendA(pszDesta, pszDest) )
    return 0;
  if ( !(unsigned int)PathFileExistsDefExtA(pszDesta) )
  {
    if ( GetWindowsDirectoryA(pszDesta, 0x104u) - 1 > 0x102 || !PathAppendA(pszDesta, pszDest) )
      return 0;
    if ( !(unsigned int)PathFileExistsDefExtA(pszDesta) )
    {
      EnvironmentVariableA = GetEnvironmentVariableA("PATH", Buffer, 0x100u);
      v7 = EnvironmentVariableA;
      if ( (unsigned __int64)EnvironmentVariableA < 0x100 )
      {
        if ( EnvironmentVariableA )
        {
          v9 = 0;
          PathA = Buffer;
LABEL_18:
          while ( 1 )
          {
            PathA = (CHAR *)NextPathA(PathA, pszDesta);
            if ( !PathA )
              break;
            if ( a2 )
            {
              for ( i = a2; *i; ++i )
              {
                if ( !lstrcmpiA(pszDesta, *i) )
                  goto LABEL_18;
              }
            }
            PathAppendA(pszDesta, pszDest);
            if ( (unsigned int)PathFileExistsDefExtA(pszDesta) )
            {
              StringCchCopyA(pszDest, 0x104u, pszDesta);
              if ( v9 )
                LocalFree(v9);
              return 1;
            }
          }
          if ( v9 )
            LocalFree(v9);
        }
      }
      else
      {
        v8 = (CHAR *)LocalAlloc(0x40u, EnvironmentVariableA);
        v9 = v8;
        if ( v8 )
        {
          GetEnvironmentVariableA("PATH", v8, v7);
          PathA = v9;
          goto LABEL_18;
        }
      }
      return 0;
    }
  }
LABEL_30:
  StringCchCopyA(pszDest, 0x104u, pszDesta);
  return 1;
}

```

## disassembly

```asm
0x180018dd0  mov     [rsp-8+arg_10], rbx
0x180018dd5  push    rbp
0x180018dd6  push    rsi
0x180018dd7  push    rdi
0x180018dd8  push    r12
0x180018dda  push    r13
0x180018ddc  push    r14
0x180018dde  push    r15
0x180018de0  lea     rbp, [rsp-140h]
0x180018de8  sub     rsp, 240h
0x180018def  mov     rax, cs:__security_cookie
0x180018df6  xor     rax, rsp
0x180018df9  mov     [rbp+170h+var_40], rax
0x180018e00  mov     r12d, r8d
0x180018e03  mov     r15, rdx
0x180018e06  mov     rdi, rcx
0x180018e09  test    rcx, rcx
0x180018e0c  jz      loc_180018FD8
0x180018e12  call    cs:__imp_PathIsFileSpecA
0x180018e18  test    eax, eax
0x180018e1a  jz      loc_180018FD8
0x180018e20  mov     rcx, rdi; lpsz
0x180018e23  call    cs:__imp_PathUnquoteSpacesA
0x180018e29  xor     ebx, ebx
0x180018e2b  mov     r13d, 104h
0x180018e31  test    r15, r15
0x180018e34  jz      short loc_180018E6E
0x180018e36  movsxd  rax, ebx
0x180018e39  mov     rdx, [r15+rax*8]; pszDir
0x180018e3d  test    rdx, rdx
0x180018e40  jz      short loc_180018E6E
0x180018e42  cmp     byte ptr [rdx], 0
0x180018e45  jz      short loc_180018E6E
0x180018e47  mov     r8, rdi; pszFile
0x180018e4a  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180018e4f  call    cs:__imp_PathCombineA
0x180018e55  mov     edx, r12d
0x180018e58  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018e5d  call    PathFileExistsDefExtA
0x180018e62  test    eax, eax
0x180018e64  jnz     loc_180019004
0x180018e6a  inc     ebx
0x180018e6c  jmp     short loc_180018E36
0x180018e6e  mov     edx, r13d; uSize
0x180018e71  lea     rcx, [rsp+270h+pszDest]; lpBuffer
0x180018e76  call    cs:__imp_GetSystemDirectoryA
0x180018e7c  mov     rdx, rdi; pszMore
0x180018e7f  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018e84  call    cs:__imp_PathAppendA
0x180018e8a  test    eax, eax
0x180018e8c  jz      loc_180018FD8
0x180018e92  mov     edx, r12d
0x180018e95  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018e9a  call    PathFileExistsDefExtA
0x180018e9f  test    eax, eax
0x180018ea1  jnz     loc_180019004
0x180018ea7  mov     edx, r13d; uSize
0x180018eaa  lea     rcx, [rsp+270h+pszDest]; lpBuffer
0x180018eaf  call    cs:__imp_GetWindowsDirectoryA
0x180018eb5  dec     eax
0x180018eb7  cmp     eax, 102h
0x180018ebc  ja      loc_180018FD8
0x180018ec2  mov     rdx, rdi; pszMore
0x180018ec5  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018eca  call    cs:__imp_PathAppendA
0x180018ed0  test    eax, eax
0x180018ed2  jz      loc_180018FD8
0x180018ed8  mov     edx, r12d
0x180018edb  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018ee0  call    PathFileExistsDefExtA
0x180018ee5  test    eax, eax
0x180018ee7  jnz     loc_180019004
0x180018eed  mov     ebx, 100h
0x180018ef2  lea     rdx, [rbp+170h+Buffer]; lpBuffer
0x180018ef6  mov     r8d, ebx; nSize
0x180018ef9  lea     rcx, aPath_0; "PATH"
0x180018f00  call    cs:__imp_GetEnvironmentVariableA
0x180018f06  movsxd  rsi, eax
0x180018f09  mov     rdx, rsi; uBytes
0x180018f0c  cmp     rsi, rbx
0x180018f0f  jb      short loc_180018F40
0x180018f11  mov     ecx, 40h ; '@'; uFlags
0x180018f16  call    cs:__imp_LocalAlloc
0x180018f1c  mov     rbx, rax
0x180018f1f  test    rax, rax
0x180018f22  jz      loc_180018FD8
0x180018f28  mov     r8d, esi; nSize
0x180018f2b  lea     rcx, aPath_0; "PATH"
0x180018f32  mov     rdx, rax; lpBuffer
0x180018f35  call    cs:__imp_GetEnvironmentVariableA
0x180018f3b  mov     r14, rbx
0x180018f3e  jmp     short loc_180018F4E
0x180018f40  test    eax, eax
0x180018f42  jz      loc_180018FD8
0x180018f48  xor     ebx, ebx
0x180018f4a  lea     r14, [rbp+170h+Buffer]
0x180018f4e  mov     r8d, r13d
0x180018f51  lea     rdx, [rsp+270h+pszDest]; pszPath
0x180018f56  mov     rcx, r14; pszSrc
0x180018f59  call    NextPathA
0x180018f5e  mov     r14, rax
0x180018f61  test    rax, rax
0x180018f64  jz      short loc_180018FCA
0x180018f66  test    r15, r15
0x180018f69  jz      short loc_180018F8B
0x180018f6b  mov     rsi, r15
0x180018f6e  mov     rdx, [rsi]; lpString2
0x180018f71  test    rdx, rdx
0x180018f74  jz      short loc_180018F8B
0x180018f76  lea     rcx, [rsp+270h+pszDest]; lpString1
0x180018f7b  call    cs:__imp_lstrcmpiA
0x180018f81  test    eax, eax
0x180018f83  jz      short loc_180018F4E
0x180018f85  add     rsi, 8
0x180018f89  jmp     short loc_180018F6E
0x180018f8b  mov     rdx, rdi; pszMore
0x180018f8e  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018f93  call    cs:__imp_PathAppendA
0x180018f99  mov     edx, r12d
0x180018f9c  lea     rcx, [rsp+270h+pszDest]; pszPath
0x180018fa1  call    PathFileExistsDefExtA
0x180018fa6  test    eax, eax
0x180018fa8  jz      short loc_180018F4E
0x180018faa  lea     r8, [rsp+270h+pszDest]; pszSrc
0x180018faf  mov     rdx, r13; cchDest
0x180018fb2  mov     rcx, rdi; pszDest
0x180018fb5  call    StringCchCopyA
0x180018fba  test    rbx, rbx
0x180018fbd  jz      short loc_180019014
0x180018fbf  mov     rcx, rbx; hMem
0x180018fc2  call    cs:__imp_LocalFree
0x180018fc8  jmp     short loc_180019014
0x180018fca  test    rbx, rbx
0x180018fcd  jz      short loc_180018FD8
0x180018fcf  mov     rcx, rbx; hMem
0x180018fd2  call    cs:__imp_LocalFree
0x180018fd8  xor     eax, eax
0x180018fda  mov     rcx, [rbp+170h+var_40]
0x180018fe1  xor     rcx, rsp; StackCookie
0x180018fe4  call    __security_check_cookie
0x180018fe9  mov     rbx, [rsp+270h+arg_10]
0x180018ff1  add     rsp, 240h
0x180018ff8  pop     r15
0x180018ffa  pop     r14
0x180018ffc  pop     r13
0x180018ffe  pop     r12
0x180019000  pop     rdi
0x180019001  pop     rsi
0x180019002  pop     rbp
0x180019003  retn
0x180019004  lea     r8, [rsp+270h+pszDest]; pszSrc
0x180019009  mov     rdx, r13; cchDest
0x18001900c  mov     rcx, rdi; pszDest
0x18001900f  call    StringCchCopyA
0x180019014  mov     eax, 1
0x180019019  jmp     short loc_180018FDA
```
