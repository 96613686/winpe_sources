# _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)

- ea: `0x1800089a8`
- end: `0x180008b42`
- name: `?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z`
- size: `410`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64, __int64, __int64, unsigned __int16 *lpString1)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000868c`

## callees

- `0x180002230`
- `0x1800058f4`
- `0x1800089a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008a65`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008a81`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008a65`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008a81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008af2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008af2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008a46`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008a46`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180008a9f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180008a9f`

## pseudocode

```c
__int64 __fastcall _AppendPathAndCreateFolder(
        const WCHAR *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 *lpString1)
{
  WCHAR *v6; // r9
  unsigned __int16 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  WCHAR *v11; // rcx
  HRESULT v12; // ebx
  wchar_t *i; // rax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdi
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR pszPath[264]; // [rsp+240h] [rbp-258h] BYREF

  v6 = pszPath;
  v8 = lpString1;
  v9 = 260;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*v8 )
      break;
    *v6++ = *v8++;
    --v10;
    --v9;
  }
  while ( v9 );
  v11 = v6 - 1;
  v12 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v11 = v6;
  *v11 = 0;
  if ( v9 )
  {
    v12 = PathCchAppend(pszPath, 0x104u, a1);
    if ( v12 >= 0 )
    {
      for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
        *i = 92;
      v12 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v12 >= 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( lpString1[v15] );
        if ( v15 > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        do
          ++v14;
        while ( pszPathOut[v14] );
        if ( v14 > 0xFFFFFFFF )
        {
          return (unsigned int)-2147024362;
        }
        else
        {
          v12 = -2147024809;
          if ( (unsigned int)v14 > (unsigned int)v15
            && CompareStringOrdinal(lpString1, v15, pszPathOut, v15, 0) == 2
            && pszPathOut[(unsigned int)v15] == 92 )
          {
            return (unsigned int)StringCchCopyW(lpString1, 0x104u, pszPathOut);
          }
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800089a8  push    rbx
0x1800089aa  push    rbp
0x1800089ab  push    rsi
0x1800089ac  push    rdi
0x1800089ad  push    r14
0x1800089af  push    r15
0x1800089b1  sub     rsp, 468h
0x1800089b8  mov     rax, cs:__security_cookie
0x1800089bf  xor     rax, rsp
0x1800089c2  mov     [rsp+498h+var_48], rax
0x1800089ca  mov     rsi, [rsp+498h+lpString1]
0x1800089d2  lea     r9, [rsp+498h+pszPath]
0x1800089da  mov     r15d, 104h
0x1800089e0  mov     r10, rcx
0x1800089e3  mov     rcx, rsi
0x1800089e6  mov     edx, r15d
0x1800089e9  mov     eax, 7FFFFFFEh
0x1800089ee  xor     ebp, ebp
0x1800089f0  test    rax, rax
0x1800089f3  jz      short loc_180008A14
0x1800089f5  movzx   r8d, word ptr [rcx]
0x1800089f9  test    r8w, r8w
0x1800089fd  jz      short loc_180008A14
0x1800089ff  mov     [r9], r8w
0x180008a03  add     rcx, 2
0x180008a07  add     r9, 2
0x180008a0b  dec     rax
0x180008a0e  sub     rdx, 1
0x180008a12  jnz     short loc_1800089F0
0x180008a14  mov     rax, rdx
0x180008a17  lea     rcx, [r9-2]
0x180008a1b  neg     rax
0x180008a1e  sbb     ebx, ebx
0x180008a20  not     ebx
0x180008a22  and     ebx, 8007007Ah
0x180008a28  test    rdx, rdx
0x180008a2b  cmovnz  rcx, r9
0x180008a2f  mov     [rcx], bp
0x180008a32  jz      loc_180008B20
0x180008a38  mov     r8, r10; pszMore
0x180008a3b  lea     rcx, [rsp+498h+pszPath]; pszPath
0x180008a43  mov     rdx, r15; cchPath
0x180008a46  call    cs:__imp_PathCchAppend
0x180008a4c  mov     ebx, eax
0x180008a4e  test    eax, eax
0x180008a50  js      loc_180008B20
0x180008a56  lea     rdx, SubStr; "/"
0x180008a5d  lea     rcx, [rsp+498h+pszPath]; Str
0x180008a65  call    cs:__imp_wcsstr
0x180008a6b  mov     r14d, 5Ch ; '\'
0x180008a71  jmp     short loc_180008A87
0x180008a73  lea     rdx, SubStr; "/"
0x180008a7a  mov     [rax], r14w
0x180008a7e  mov     rcx, rax; Str
0x180008a81  call    cs:__imp_wcsstr
0x180008a87  test    rax, rax
0x180008a8a  jnz     short loc_180008A73
0x180008a8c  xor     r9d, r9d; dwFlags
0x180008a8f  lea     r8, [rsp+498h+pszPath]; pszPathIn
0x180008a97  mov     rdx, r15; cchPathOut
0x180008a9a  lea     rcx, [rsp+498h+pszPathOut]; pszPathOut
0x180008a9f  call    cs:__imp_PathCchCanonicalizeEx
0x180008aa5  mov     ebx, eax
0x180008aa7  test    eax, eax
0x180008aa9  js      short loc_180008B20
0x180008aab  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008aaf  mov     rdi, rax
0x180008ab2  inc     rdi
0x180008ab5  cmp     [rsi+rdi*2], bp
0x180008ab9  jnz     short loc_180008AB2
0x180008abb  mov     ecx, 0FFFFFFFFh
0x180008ac0  cmp     rdi, rcx
0x180008ac3  ja      short loc_180008B1B
0x180008ac5  lea     rdx, [rsp+498h+pszPathOut]
0x180008aca  inc     rax
0x180008acd  cmp     [rdx+rax*2], bp
0x180008ad1  jnz     short loc_180008ACA
0x180008ad3  cmp     rax, rcx
0x180008ad6  ja      short loc_180008B1B
0x180008ad8  mov     ebx, 80070057h
0x180008add  cmp     eax, edi
0x180008adf  jbe     short loc_180008B20
0x180008ae1  mov     r9d, edi; cchCount2
0x180008ae4  mov     [rsp+498h+bIgnoreCase], ebp; bIgnoreCase
0x180008ae8  lea     r8, [rsp+498h+pszPathOut]; lpString2
0x180008aed  mov     edx, edi; cchCount1
0x180008aef  mov     rcx, rsi; lpString1
0x180008af2  call    cs:__imp_CompareStringOrdinal
0x180008af8  cmp     eax, 2
0x180008afb  jnz     short loc_180008B20
0x180008afd  mov     eax, edi
0x180008aff  cmp     [rsp+rax*2+498h+pszPathOut], r14w
0x180008b05  jnz     short loc_180008B20
0x180008b07  lea     r8, [rsp+498h+pszPathOut]; unsigned __int16 *
0x180008b0c  mov     rdx, r15; unsigned __int64
0x180008b0f  mov     rcx, rsi; unsigned __int16 *
0x180008b12  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008b17  mov     ebx, eax
0x180008b19  jmp     short loc_180008B20
0x180008b1b  mov     ebx, 80070216h
0x180008b20  mov     eax, ebx
0x180008b22  mov     rcx, [rsp+498h+var_48]
0x180008b2a  xor     rcx, rsp; StackCookie
0x180008b2d  call    __security_check_cookie
0x180008b32  add     rsp, 468h
0x180008b39  pop     r15
0x180008b3b  pop     r14
0x180008b3d  pop     rdi
0x180008b3e  pop     rsi
0x180008b3f  pop     rbp
0x180008b40  pop     rbx
0x180008b41  retn
```
