# _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)

- ea: `0x180016314`
- end: `0x1800164b2`
- name: `?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z`
- size: `414`
- prototype: `__int64 __fastcall(const WCHAR *, const wchar_t *, int, char, __int64, unsigned __int16 *lpString1)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180016180`

## callees

- `0x180002610`
- `0x18000a1c8`
- `0x18000a67c`
- `0x180016314`
- `0x1800165c8`
- `0x18001672c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800163cb`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800163cb`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180016386`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180016386`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001644d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001644d`

## pseudocode

```c
__int64 __fastcall _AppendPathAndCreateFolder(
        const WCHAR *a1,
        const wchar_t *a2,
        int a3,
        char a4,
        __int64 a5,
        unsigned __int16 *lpString1)
{
  HRESULT v10; // ebx
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *i; // rax
  const unsigned __int16 *v13; // rdx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r9
  __int64 v16; // rdi
  int cchCount1; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+250h] [rbp+150h] BYREF

  v10 = StringCchCopyW(pszPath, 0x104u, lpString1);
  if ( v10 >= 0 )
  {
    v10 = PathCchAppend(pszPath, 0x104u, a1);
    if ( v10 >= 0 )
    {
      for ( i = wcsstr(pszPath, v11); i; i = wcsstr(i, v13) )
        *i = 92;
      v10 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v10 >= 0 )
      {
        cchCount1 = 0;
        v14 = -1;
        do
          ++v14;
        while ( lpString1[v14] );
        v10 = ULongLongToULong(v14, (unsigned int *)&cchCount1);
        if ( v10 >= 0 )
        {
          v19 = 0;
          do
            ++v15;
          while ( pszPathOut[v15] );
          v10 = ULongLongToULong(v15, &v19);
          if ( v10 >= 0 )
          {
            v16 = (unsigned int)cchCount1;
            v10 = -2147024809;
            if ( v19 > cchCount1
              && CompareStringOrdinal(lpString1, cchCount1, pszPathOut, cchCount1, 0) == 2
              && pszPathOut[v16] == 92 )
            {
              v10 = StringCchCopyW(lpString1, 0x104u, pszPathOut);
              if ( v10 >= 0 )
                return (unsigned int)_SetSecurityOnFileOrFolder(lpString1, a2, a3, a4);
            }
          }
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016314  push    rbp
0x180016316  push    rbx
0x180016317  push    rsi
0x180016318  push    rdi
0x180016319  push    r12
0x18001631b  push    r13
0x18001631d  push    r14
0x18001631f  push    r15
0x180016321  lea     rbp, [rsp-378h]
0x180016329  sub     rsp, 478h
0x180016330  mov     rax, cs:__security_cookie
0x180016337  xor     rax, rsp
0x18001633a  mov     [rbp+3B0h+var_50], rax
0x180016341  mov     rsi, [rbp+3B0h+lpString1]
0x180016348  mov     r15d, r8d
0x18001634b  mov     r14, rdx
0x18001634e  mov     rdi, rcx
0x180016351  mov     r8, rsi; unsigned __int16 *
0x180016354  lea     rcx, [rbp+3B0h+pszPath]; unsigned __int16 *
0x18001635b  mov     edx, 104h; unsigned __int64
0x180016360  mov     r12d, r9d
0x180016363  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016368  xor     r13d, r13d
0x18001636b  mov     ebx, eax
0x18001636d  test    eax, eax
0x18001636f  js      loc_18001648D
0x180016375  mov     r8, rdi; pszMore
0x180016378  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18001637f  mov     edi, 104h
0x180016384  mov     edx, edi; cchPath
0x180016386  call    cs:__imp_PathCchAppend
0x18001638c  mov     ebx, eax
0x18001638e  test    eax, eax
0x180016390  js      loc_18001648D
0x180016396  lea     rcx, [rbp+3B0h+pszPath]; unsigned __int16 *
0x18001639d  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x1800163a2  test    rax, rax
0x1800163a5  jz      short loc_1800163B9
0x1800163a7  mov     rcx, rax; unsigned __int16 *
0x1800163aa  mov     word ptr [rax], 5Ch ; '\'
0x1800163af  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x1800163b4  test    rax, rax
0x1800163b7  jnz     short loc_1800163A7
0x1800163b9  xor     r9d, r9d; dwFlags
0x1800163bc  lea     r8, [rbp+3B0h+pszPath]; pszPathIn
0x1800163c3  mov     rdx, rdi; cchPathOut
0x1800163c6  lea     rcx, [rsp+4B0h+pszPathOut]; pszPathOut
0x1800163cb  call    cs:__imp_PathCchCanonicalizeEx
0x1800163d1  mov     ebx, eax
0x1800163d3  test    eax, eax
0x1800163d5  js      loc_18001648D
0x1800163db  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800163df  mov     [rsp+4B0h+cchCount1], r13d
0x1800163e4  mov     rcx, r9
0x1800163e7  inc     rcx; unsigned __int64
0x1800163ea  cmp     [rsi+rcx*2], r13w
0x1800163ef  jnz     short loc_1800163E7
0x1800163f1  lea     rdx, [rsp+4B0h+cchCount1]; unsigned int *
0x1800163f6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800163fb  mov     ebx, eax
0x1800163fd  test    eax, eax
0x1800163ff  js      loc_18001648D
0x180016405  mov     [rsp+4B0h+var_478], r13d
0x18001640a  lea     rax, [rsp+4B0h+pszPathOut]
0x18001640f  inc     r9
0x180016412  cmp     [rax+r9*2], r13w
0x180016417  jnz     short loc_18001640F
0x180016419  lea     rdx, [rsp+4B0h+var_478]; unsigned int *
0x18001641e  mov     rcx, r9; unsigned __int64
0x180016421  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180016426  mov     ebx, eax
0x180016428  test    eax, eax
0x18001642a  js      short loc_18001648D
0x18001642c  mov     edi, [rsp+4B0h+cchCount1]
0x180016430  mov     ebx, 80070057h
0x180016435  cmp     [rsp+4B0h+var_478], edi
0x180016439  jbe     short loc_18001648D
0x18001643b  mov     r9d, edi; cchCount2
0x18001643e  mov     [rsp+4B0h+bIgnoreCase], r13d; bIgnoreCase
0x180016443  lea     r8, [rsp+4B0h+pszPathOut]; lpString2
0x180016448  mov     edx, edi; cchCount1
0x18001644a  mov     rcx, rsi; lpString1
0x18001644d  call    cs:__imp_CompareStringOrdinal
0x180016453  cmp     eax, 2
0x180016456  jnz     short loc_18001648D
0x180016458  lea     ecx, [rax+5Ah]
0x18001645b  cmp     [rsp+rdi*2+4B0h+pszPathOut], cx
0x180016460  jnz     short loc_18001648D
0x180016462  lea     r8, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180016467  mov     edx, 104h; unsigned __int64
0x18001646c  mov     rcx, rsi; unsigned __int16 *
0x18001646f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016474  mov     ebx, eax
0x180016476  test    eax, eax
0x180016478  js      short loc_18001648D
0x18001647a  mov     r9d, r12d
0x18001647d  mov     r8d, r15d
0x180016480  mov     rdx, r14
0x180016483  mov     rcx, rsi
0x180016486  call    ?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z; _SetSecurityOnFileOrFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS)
0x18001648b  mov     ebx, eax
0x18001648d  mov     eax, ebx
0x18001648f  mov     rcx, [rbp+3B0h+var_50]
0x180016496  xor     rcx, rsp; StackCookie
0x180016499  call    __security_check_cookie
0x18001649e  add     rsp, 478h
0x1800164a5  pop     r15
0x1800164a7  pop     r14
0x1800164a9  pop     r13
0x1800164ab  pop     r12
0x1800164ad  pop     rdi
0x1800164ae  pop     rsi
0x1800164af  pop     rbx
0x1800164b0  pop     rbp
0x1800164b1  retn
```
