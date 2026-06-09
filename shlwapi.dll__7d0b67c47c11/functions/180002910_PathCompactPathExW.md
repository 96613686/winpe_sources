# PathCompactPathExW

- ea: `0x180002910`
- end: `0x180002ba2`
- name: `PathCompactPathExW`
- size: `658`
- prototype: `BOOL __stdcall(LPWSTR pszOut, LPCWSTR pszSrc, UINT cchMax, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002910`
- `0x180003400`
- `0x180003560`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800029aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800029aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002964`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800029b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002a6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002964`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800029b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002a6d`

## pseudocode

```c
BOOL __stdcall PathCompactPathExW(LPWSTR pszOut, LPCWSTR pszSrc, UINT cchMax, DWORD dwFlags)
{
  unsigned __int64 v4; // rbp
  WCHAR v8; // ax
  WCHAR v9; // r15
  LPCWSTR v10; // rcx
  const WCHAR *FileNameW; // r14
  int v12; // r13d
  unsigned int v13; // eax
  unsigned __int64 v14; // rax
  LPWSTR v15; // rcx
  unsigned __int64 v16; // rcx
  const wchar_t *v17; // r9
  WCHAR *v18; // r8
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  WCHAR *v21; // rcx
  unsigned __int64 v22; // rax
  LPWSTR v23; // rcx
  unsigned __int64 v24; // rcx
  const wchar_t *v25; // r14
  __int64 v26; // rax
  WCHAR *v27; // rdx
  unsigned __int64 v28; // rbx
  WCHAR *v29; // rcx
  unsigned int v30; // ebp
  __int64 v31; // rdx
  WCHAR v32; // cx

  v4 = cchMax;
  if ( !pszSrc || !pszOut || !cchMax )
    return 0;
  memset_0(pszOut, 0, 2LL * cchMax);
  if ( lstrlenW(pszSrc) + 1 < (unsigned int)v4 )
  {
    StringCchCopyW(pszOut, v4, pszSrc);
  }
  else
  {
    v8 = *pszSrc;
    v9 = 92;
    if ( *pszSrc )
    {
      v10 = pszSrc;
      do
      {
        if ( v8 == 47 || v8 == 92 )
          v9 = v8;
        v8 = *++v10;
      }
      while ( *v10 );
    }
    FileNameW = PathFindFileNameW(pszSrc);
    v12 = lstrlenW(FileNameW);
    if ( FileNameW == pszSrc && (unsigned int)v4 > 3 )
    {
      StringCchCopyW(pszOut, (unsigned int)(v4 - 3), pszSrc);
      if ( v4 <= 0x7FFFFFFF )
      {
        v22 = v4;
        v23 = pszOut;
        do
        {
          if ( !*v23 )
            break;
          ++v23;
          --v22;
        }
        while ( v22 );
        v24 = v22 ? v4 - v22 : 0LL;
        if ( v22 )
        {
          v25 = L"...";
          v26 = 2147483646;
          v27 = &pszOut[v24];
          v28 = v4 - v24;
          if ( v4 != v24 )
          {
            do
            {
              if ( !v26 )
                break;
              if ( !*v25 )
                break;
              *v27++ = *v25++;
              --v26;
              --v28;
            }
            while ( v28 );
          }
          v29 = v27 - 1;
          if ( v28 )
            v29 = v27;
          *v29 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
      if ( (unsigned int)v4 < 7 )
      {
        v30 = v4 - 1;
        if ( v30 )
        {
          do
          {
            v31 = v13;
            if ( v13 == 3 )
              v32 = v9;
            else
              v32 = 46;
            ++v13;
            pszOut[v31] = v32;
          }
          while ( v13 < v30 );
        }
      }
      else
      {
        if ( (int)v4 - v12 - 4 >= 0 )
          v13 = v4 - v12 - 4;
        StringCchCopyW(pszOut, (int)v13, pszSrc);
        if ( v4 <= 0x7FFFFFFF )
        {
          v14 = v4;
          v15 = pszOut;
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v14;
          }
          while ( v14 );
          v16 = v14 ? v4 - v14 : 0LL;
          if ( v14 )
          {
            v17 = L".../";
            v18 = &pszOut[v16];
            v19 = 2147483646;
            v20 = v4 - v16;
            if ( v4 != v16 )
            {
              do
              {
                if ( !v19 )
                  break;
                if ( !*v17 )
                  break;
                *v18++ = *v17++;
                --v19;
                --v20;
              }
              while ( v20 );
            }
            v21 = v18 - 1;
            if ( v20 )
              v21 = v18;
            *v21 = 0;
          }
        }
        pszOut[lstrlenW(pszOut) - 1] = v9;
        if ( (unsigned int)v4 <= v12 + 4 )
        {
          StringCchCopyW(pszOut + 4, (int)v4 - 7, FileNameW);
          FileNameW = L"...";
        }
        StringCchCatW(pszOut, v4, FileNameW);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002910  push    rbx
0x180002912  push    rbp
0x180002913  push    rsi
0x180002914  push    rdi
0x180002915  push    r12
0x180002917  push    r13
0x180002919  push    r14
0x18000291b  push    r15
0x18000291d  sub     rsp, 28h
0x180002921  xor     r12d, r12d
0x180002924  mov     ebp, r8d
0x180002927  mov     rsi, rdx
0x18000292a  mov     rdi, rcx
0x18000292d  test    rdx, rdx
0x180002930  jnz     short loc_180002945
0x180002932  xor     eax, eax
0x180002934  add     rsp, 28h
0x180002938  pop     r15
0x18000293a  pop     r14
0x18000293c  pop     r13
0x18000293e  pop     r12
0x180002940  pop     rdi
0x180002941  pop     rsi
0x180002942  pop     rbp
0x180002943  pop     rbx
0x180002944  retn
0x180002945  test    rdi, rdi
0x180002948  jz      short loc_180002932
0x18000294a  test    r8d, r8d
0x18000294d  jz      short loc_180002932
0x18000294f  lea     r8, ds:0[rbp*2]; Size
0x180002957  xor     edx, edx; Val
0x180002959  mov     rbx, rbp
0x18000295c  call    memset_0
0x180002961  mov     rcx, rsi; lpString
0x180002964  call    cs:__imp_lstrlenW
0x18000296a  inc     eax
0x18000296c  cmp     eax, ebp
0x18000296e  jb      loc_180002B31
0x180002974  movzx   eax, word ptr [rsi]
0x180002977  mov     edx, 5Ch ; '\'
0x18000297c  movzx   r15d, dx
0x180002980  test    ax, ax
0x180002983  jz      short loc_1800029A7
0x180002985  mov     rcx, rsi
0x180002988  cmp     ax, 2Fh ; '/'
0x18000298c  jz      loc_180002B44
0x180002992  cmp     ax, dx
0x180002995  jz      loc_180002B44
0x18000299b  add     rcx, 2
0x18000299f  movzx   eax, word ptr [rcx]
0x1800029a2  test    ax, ax
0x1800029a5  jnz     short loc_180002988
0x1800029a7  mov     rcx, rsi; pszPath
0x1800029aa  call    cs:__imp_PathFindFileNameW
0x1800029b0  mov     rcx, rax; lpString
0x1800029b3  mov     r14, rax
0x1800029b6  call    cs:__imp_lstrlenW
0x1800029bc  mov     r13d, eax
0x1800029bf  cmp     r14, rsi
0x1800029c2  jz      loc_180002AA0
0x1800029c8  mov     eax, r12d
0x1800029cb  cmp     ebp, 7
0x1800029ce  jb      loc_180002B52
0x1800029d4  mov     ecx, ebp
0x1800029d6  mov     r8, rsi; unsigned __int16 *
0x1800029d9  sub     ecx, r13d
0x1800029dc  add     ecx, 0FFFFFFFCh
0x1800029df  cmovns  eax, ecx
0x1800029e2  mov     rcx, rdi; unsigned __int16 *
0x1800029e5  movsxd  rdx, eax; unsigned __int64
0x1800029e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800029ed  cmp     rbx, 7FFFFFFFh
0x1800029f4  ja      short loc_180002A6A
0x1800029f6  mov     rax, rbx
0x1800029f9  mov     rcx, rdi
0x1800029fc  cmp     [rcx], r12w
0x180002a00  jz      short loc_180002A0C
0x180002a02  add     rcx, 2
0x180002a06  sub     rax, 1
0x180002a0a  jnz     short loc_1800029FC
0x180002a0c  test    rax, rax
0x180002a0f  jz      loc_180002B7C
0x180002a15  mov     rcx, rbx
0x180002a18  sub     rcx, rax
0x180002a1b  test    rax, rax
0x180002a1e  jz      short loc_180002A6A
0x180002a20  mov     rdx, rbx
0x180002a23  lea     r9, asc_18003BF28; ".../"
0x180002a2a  lea     r8, [rdi+rcx*2]
0x180002a2e  mov     eax, 7FFFFFFEh
0x180002a33  sub     rdx, rcx
0x180002a36  jz      short loc_180002A5B
0x180002a38  test    rax, rax
0x180002a3b  jz      short loc_180002A5B
0x180002a3d  movzx   ecx, word ptr [r9]
0x180002a41  test    cx, cx
0x180002a44  jz      short loc_180002A5B
0x180002a46  mov     [r8], cx
0x180002a4a  add     r9, 2
0x180002a4e  add     r8, 2
0x180002a52  dec     rax
0x180002a55  sub     rdx, 1
0x180002a59  jnz     short loc_180002A38
0x180002a5b  test    rdx, rdx
0x180002a5e  lea     rcx, [r8-2]
0x180002a62  cmovnz  rcx, r8
0x180002a66  mov     [rcx], r12w
0x180002a6a  mov     rcx, rdi; lpString
0x180002a6d  call    cs:__imp_lstrlenW
0x180002a73  movsxd  rcx, eax
0x180002a76  lea     eax, [r13+4]
0x180002a7a  mov     [rdi+rcx*2-2], r15w
0x180002a80  cmp     ebp, eax
0x180002a82  jbe     loc_180002B84
0x180002a88  mov     r8, r14; unsigned __int16 *
0x180002a8b  mov     rdx, rbx; unsigned __int64
0x180002a8e  mov     rcx, rdi; unsigned __int16 *
0x180002a91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002a96  mov     eax, 1
0x180002a9b  jmp     loc_180002934
0x180002aa0  cmp     ebp, 3
0x180002aa3  jbe     loc_1800029C8
0x180002aa9  lea     edx, [rbp-3]; unsigned __int64
0x180002aac  mov     r8, rsi; unsigned __int16 *
0x180002aaf  mov     rcx, rdi; unsigned __int16 *
0x180002ab2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002ab7  cmp     rbx, 7FFFFFFFh
0x180002abe  ja      short loc_180002A96
0x180002ac0  mov     rax, rbx
0x180002ac3  mov     rcx, rdi
0x180002ac6  cmp     [rcx], r12w
0x180002aca  jz      short loc_180002AD6
0x180002acc  add     rcx, 2
0x180002ad0  sub     rax, 1
0x180002ad4  jnz     short loc_180002AC6
0x180002ad6  test    rax, rax
0x180002ad9  jz      short loc_180002B4D
0x180002adb  mov     rcx, rbx
0x180002ade  sub     rcx, rax
0x180002ae1  test    rax, rax
0x180002ae4  jz      short loc_180002A96
0x180002ae6  lea     r14, asc_18003BF48; "..."
0x180002aed  mov     eax, 7FFFFFFEh
0x180002af2  lea     rdx, [rdi+rcx*2]
0x180002af6  sub     rbx, rcx
0x180002af9  jz      short loc_180002B1D
0x180002afb  test    rax, rax
0x180002afe  jz      short loc_180002B1D
0x180002b00  movzx   ecx, word ptr [r14]
0x180002b04  test    cx, cx
0x180002b07  jz      short loc_180002B1D
0x180002b09  mov     [rdx], cx
0x180002b0c  add     r14, 2
0x180002b10  add     rdx, 2
0x180002b14  dec     rax
0x180002b17  sub     rbx, 1
0x180002b1b  jnz     short loc_180002AFB
0x180002b1d  test    rbx, rbx
0x180002b20  lea     rcx, [rdx-2]
0x180002b24  cmovnz  rcx, rdx
0x180002b28  mov     [rcx], r12w
0x180002b2c  jmp     loc_180002A96
0x180002b31  mov     r8, rsi; unsigned __int16 *
0x180002b34  mov     rdx, rbx; unsigned __int64
0x180002b37  mov     rcx, rdi; unsigned __int16 *
0x180002b3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002b3f  jmp     loc_180002A96
0x180002b44  movzx   r15d, ax
0x180002b48  jmp     loc_18000299B
0x180002b4d  mov     rcx, r12
0x180002b50  jmp     short loc_180002AE1
0x180002b52  sub     ebp, 1
0x180002b55  jz      loc_180002A96
0x180002b5b  mov     edx, eax
0x180002b5d  cmp     eax, 3
0x180002b60  jnz     short loc_180002B68
0x180002b62  movzx   ecx, r15w
0x180002b66  jmp     short loc_180002B6D
0x180002b68  mov     ecx, 2Eh ; '.'
0x180002b6d  inc     eax
0x180002b6f  mov     [rdi+rdx*2], cx
0x180002b73  cmp     eax, ebp
0x180002b75  jb      short loc_180002B5B
0x180002b77  jmp     loc_180002A96
0x180002b7c  mov     rcx, r12
0x180002b7f  jmp     loc_180002A1B
0x180002b84  lea     eax, [rbp-7]
0x180002b87  mov     r8, r14; unsigned __int16 *
0x180002b8a  movsxd  rdx, eax; unsigned __int64
0x180002b8d  lea     rcx, [rdi+8]; unsigned __int16 *
0x180002b91  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002b96  lea     r14, asc_18003BF48; "..."
0x180002b9d  jmp     loc_180002A88
```
