# TelnetProtocolHandler

- ea: `0x180001c20`
- end: `0x180001f90`
- name: `TelnetProtocolHandler`
- size: `880`
- prototype: `UINT __fastcall(HWND hwnd, __int64, const CHAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c20`
- `0x1800021a6`
- `0x1800021e0`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryA` at `0x180001f2e`
- `KERNEL32!GetSystemWindowsDirectoryA` at `0x180001f2e`
- `USER32!CharPrevA` at `0x180001d26`
- `USER32!CharPrevA` at `0x180001d42`
- `USER32!CharPrevA` at `0x180001d26`
- `USER32!CharPrevA` at `0x180001d42`
- `USER32!CharNextA` at `0x180001cf8`
- `USER32!CharNextA` at `0x180001d6f`
- `USER32!CharNextA` at `0x180001cf8`
- `USER32!CharNextA` at `0x180001d6f`
- `SHELL32!ShellExecuteA` at `0x180001f5f`
- `SHELL32!ShellExecuteA` at `0x180001f5f`
- `SHLWAPI!StrCmpNIA` at `0x180001c94`
- `SHLWAPI!StrCmpNIA` at `0x180001cb5`
- `SHLWAPI!StrCmpNIA` at `0x180001c94`
- `SHLWAPI!StrCmpNIA` at `0x180001cb5`
- `SHLWAPI!StrChrA` at `0x180001ce4`
- `SHLWAPI!StrChrA` at `0x180001d5b`
- `SHLWAPI!StrChrA` at `0x180001da7`
- `SHLWAPI!StrChrA` at `0x180001f0b`
- `SHLWAPI!StrChrA` at `0x180001ce4`
- `SHLWAPI!StrChrA` at `0x180001d5b`
- `SHLWAPI!StrChrA` at `0x180001da7`
- `SHLWAPI!StrChrA` at `0x180001f0b`
- `SHLWAPI!__imp_ParseURLA` at `0x180001c6c`
- `SHLWAPI!__imp_ParseURLA` at `0x180001c6c`

## pseudocode

```c
UINT __fastcall TelnetProtocolHandler(HWND hwnd, __int64 a2, const CHAR *a3)
{
  CHAR *pszSuffix; // rbx
  CHAR v5; // al
  const CHAR *v6; // rdi
  __int64 v7; // rax
  LPSTR v8; // rax
  const CHAR *v9; // rsi
  __int64 v10; // r8
  unsigned __int64 v11; // rax
  CHAR v12; // al
  CHAR *v13; // rcx
  CHAR *v14; // rdx
  CHAR v15; // al
  CHAR *v16; // rcx
  __int64 v17; // rdx
  CHAR *v18; // rdx
  CHAR v19; // al
  CHAR *v20; // rdi
  char *v21; // rcx
  char v22; // al
  char v23; // al
  int v24; // r8d
  char v25; // dl
  __int64 v26; // r8
  PSTR v27; // rax
  UINT result; // eax
  PARSEDURLA ppu; // [rsp+30h] [rbp-D0h] BYREF
  CHAR Buffer[272]; // [rsp+60h] [rbp-A0h] BYREF

  *(_QWORD *)&ppu.cbSize = 40;
  pszSuffix = (CHAR *)a3;
  memset(&ppu.pszProtocol, 0, 32);
  if ( ParseURLA(a3, &ppu) >= 0
    && (ppu.nScheme == 7
     || !StrCmpNIA(ppu.pszProtocol, "rlogin:", ppu.cchProtocol)
     || !StrCmpNIA(ppu.pszProtocol, "tn3270:", ppu.cchProtocol)) )
  {
    pszSuffix = (CHAR *)ppu.pszSuffix;
  }
  if ( pszSuffix )
  {
    v5 = *pszSuffix;
    v6 = pszSuffix;
    while ( v5 && StrChrA("\\/", v5) )
    {
      v6 = CharNextA(v6);
      v5 = *v6;
    }
    if ( *v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      v8 = CharPrevA(v6, &v6[v7]);
      v9 = v8;
      if ( v8 > v6 )
      {
        while ( StrChrA("\\/", *v8) )
        {
          v8 = CharPrevA(v6, v9);
          v9 = v8;
        }
        *CharNextA(v9) = 0;
      }
    }
    if ( v6 > pszSuffix )
    {
      v10 = -1;
      do
        ++v10;
      while ( v6[v10] );
      memmove_0(pszSuffix, v6, v10 + 1);
    }
  }
  v11 = (unsigned __int64)StrChrA(pszSuffix, 0x40u);
  if ( v11 )
    pszSuffix = (CHAR *)(v11 + 1);
  v12 = *pszSuffix;
  v13 = pszSuffix;
  if ( *pszSuffix )
  {
    v14 = pszSuffix;
    do
    {
      if ( v12 != 34 && v12 != 39 )
        *v13++ = v12;
      v12 = *++v14;
    }
    while ( *v14 );
  }
  *v13 = 0;
  v15 = *pszSuffix;
  if ( *pszSuffix )
  {
    v16 = pszSuffix;
    do
    {
      if ( ((v15 - 45) & 0xFD) == 0 )
      {
        LOBYTE(v11) = v16[1] - 65;
        if ( (unsigned __int8)v11 <= 0x25u )
        {
          v17 = 0x2100000021LL;
          if ( _bittest64(&v17, v11) )
          {
            if ( v16 == pszSuffix
              || (v18 = v16 - 1, *(v16 - 1) == 32)
              || (v11 = (unsigned int)(*v18 - 9), (unsigned int)v11 <= 4)
              || *v18 == 34
              || *v18 == 39 )
            {
LABEL_41:
              v19 = v16[1];
              v20 = v16;
              v21 = v16 + 2;
              if ( ((v19 - 70) & 0xDF) == 0 )
              {
                while ( 1 )
                {
                  v22 = *v21;
                  if ( !*v21 || v22 != 32 && (unsigned int)(v22 - 9) > 4 )
                    break;
                  ++v21;
                }
                v23 = *v21;
                if ( *v21 == 34 || v23 == 39 )
                {
                  ++v21;
                  v24 = 1;
                  v23 = *v21;
                }
                else
                {
                  v24 = 0;
                }
                if ( v23 )
                {
                  v25 = *v21;
                  do
                  {
                    if ( (v25 == 32 || (unsigned int)(v25 - 9) <= 4) && !v24 )
                      break;
                    if ( (v25 == 34 || v25 == 39) && v24 )
                      break;
                    v25 = *++v21;
                  }
                  while ( *v21 );
                }
              }
              v26 = -1;
              do
                ++v26;
              while ( v21[v26] );
              v11 = (unsigned __int64)memmove_0(v20, v21, v26 + 1);
              v16 = v20 - 1;
            }
            else
            {
              while ( v18 >= pszSuffix )
              {
                if ( *v18 == 58 )
                  goto LABEL_41;
                if ( (unsigned __int8)(*v18 - 48) > 9u )
                  break;
                --v18;
              }
            }
          }
        }
      }
      v15 = *++v16;
    }
    while ( *v16 );
  }
  v27 = StrChrA(pszSuffix, 0x3Au);
  if ( v27 )
    *v27 = 32;
  Buffer[0] = 0;
  result = GetSystemWindowsDirectoryA(Buffer, 0x104u);
  if ( result )
    return (unsigned int)ShellExecuteA(hwnd, 0, "telnet.exe", pszSuffix, Buffer, 5);
  return result;
}

```

## disassembly

```asm
0x180001c20  mov     [rsp-8+arg_8], rbx; TelnetProtocolHandler
0x180001c25  mov     [rsp-8+arg_18], rsi
0x180001c2a  push    rbp
0x180001c2b  push    rdi
0x180001c2c  push    r14
0x180001c2e  lea     rbp, [rsp-80h]
0x180001c33  sub     rsp, 180h
0x180001c3a  mov     rax, cs:__security_cookie
0x180001c41  xor     rax, rsp
0x180001c44  mov     [rbp+90h+var_20], rax
0x180001c48  xorps   xmm0, xmm0
0x180001c4b  mov     qword ptr [rsp+190h+ppu.cbSize], 28h ; '('
0x180001c54  mov     r14, rcx
0x180001c57  lea     rdx, [rsp+190h+ppu]; ppu
0x180001c5c  mov     rcx, r8; pcszURL
0x180001c5f  mov     rbx, r8
0x180001c62  movups  xmmword ptr [rsp+190h+ppu.pszProtocol], xmm0
0x180001c67  movups  xmmword ptr [rsp+190h+ppu.pszSuffix], xmm0
0x180001c6c  call    cs:__imp_ParseURLA
0x180001c73  nop     dword ptr [rax+rax+00h]
0x180001c78  test    eax, eax
0x180001c7a  js      short loc_180001CCA
0x180001c7c  cmp     [rsp+190h+ppu.nScheme], 7
0x180001c81  jz      short loc_180001CC5
0x180001c83  mov     r8d, [rsp+190h+ppu.cchProtocol]; nChar
0x180001c88  lea     rdx, psz2; "rlogin:"
0x180001c8f  mov     rcx, [rsp+190h+ppu.pszProtocol]; psz1
0x180001c94  call    cs:__imp_StrCmpNIA
0x180001c9b  nop     dword ptr [rax+rax+00h]
0x180001ca0  test    eax, eax
0x180001ca2  jz      short loc_180001CC5
0x180001ca4  mov     r8d, [rsp+190h+ppu.cchProtocol]; nChar
0x180001ca9  lea     rdx, aTn3270; "tn3270:"
0x180001cb0  mov     rcx, [rsp+190h+ppu.pszProtocol]; psz1
0x180001cb5  call    cs:__imp_StrCmpNIA
0x180001cbc  nop     dword ptr [rax+rax+00h]
0x180001cc1  test    eax, eax
0x180001cc3  jnz     short loc_180001CCA
0x180001cc5  mov     rbx, [rsp+190h+ppu.pszSuffix]
0x180001cca  test    rbx, rbx
0x180001ccd  jz      loc_180001D9F
0x180001cd3  mov     al, [rbx]
0x180001cd5  mov     rdi, rbx
0x180001cd8  jmp     short loc_180001D09
0x180001cda  movsx   edx, al; wMatch
0x180001cdd  lea     rcx, pszStart; "\\/"
0x180001ce4  call    cs:__imp_StrChrA
0x180001ceb  nop     dword ptr [rax+rax+00h]
0x180001cf0  test    rax, rax
0x180001cf3  jz      short loc_180001D0D
0x180001cf5  mov     rcx, rdi; lpsz
0x180001cf8  call    cs:__imp_CharNextA
0x180001cff  nop     dword ptr [rax+rax+00h]
0x180001d04  mov     rdi, rax
0x180001d07  mov     al, [rax]
0x180001d09  test    al, al
0x180001d0b  jnz     short loc_180001CDA
0x180001d0d  cmp     byte ptr [rdi], 0
0x180001d10  jz      short loc_180001D7E
0x180001d12  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001d16  inc     rax
0x180001d19  cmp     byte ptr [rdi+rax], 0
0x180001d1d  jnz     short loc_180001D16
0x180001d1f  lea     rdx, [rax+rdi]; lpszCurrent
0x180001d23  mov     rcx, rdi; lpszStart
0x180001d26  call    cs:__imp_CharPrevA
0x180001d2d  nop     dword ptr [rax+rax+00h]
0x180001d32  mov     rsi, rax
0x180001d35  cmp     rax, rdi
0x180001d38  jbe     short loc_180001D7E
0x180001d3a  jmp     short loc_180001D51
0x180001d3c  mov     rdx, rsi; lpszCurrent
0x180001d3f  mov     rcx, rdi; lpszStart
0x180001d42  call    cs:__imp_CharPrevA
0x180001d49  nop     dword ptr [rax+rax+00h]
0x180001d4e  mov     rsi, rax
0x180001d51  movsx   edx, byte ptr [rax]; wMatch
0x180001d54  lea     rcx, pszStart; "\\/"
0x180001d5b  call    cs:__imp_StrChrA
0x180001d62  nop     dword ptr [rax+rax+00h]
0x180001d67  test    rax, rax
0x180001d6a  jnz     short loc_180001D3C
0x180001d6c  mov     rcx, rsi; lpsz
0x180001d6f  call    cs:__imp_CharNextA
0x180001d76  nop     dword ptr [rax+rax+00h]
0x180001d7b  mov     byte ptr [rax], 0
0x180001d7e  cmp     rdi, rbx
0x180001d81  jbe     short loc_180001D9F
0x180001d83  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001d87  inc     r8
0x180001d8a  cmp     byte ptr [rdi+r8], 0
0x180001d8f  jnz     short loc_180001D87
0x180001d91  inc     r8; Size
0x180001d94  mov     rdx, rdi; Src
0x180001d97  mov     rcx, rbx; void *
0x180001d9a  call    memmove_0
0x180001d9f  mov     edx, 40h ; '@'; wMatch
0x180001da4  mov     rcx, rbx; pszStart
0x180001da7  call    cs:__imp_StrChrA
0x180001dae  nop     dword ptr [rax+rax+00h]
0x180001db3  test    rax, rax
0x180001db6  jz      short loc_180001DBC
0x180001db8  lea     rbx, [rax+1]
0x180001dbc  mov     al, [rbx]
0x180001dbe  mov     rcx, rbx
0x180001dc1  mov     esi, 1
0x180001dc6  test    al, al
0x180001dc8  jz      short loc_180001DE3
0x180001dca  mov     rdx, rbx
0x180001dcd  cmp     al, 22h ; '"'
0x180001dcf  jz      short loc_180001DDA
0x180001dd1  cmp     al, 27h ; '''
0x180001dd3  jz      short loc_180001DDA
0x180001dd5  mov     [rcx], al
0x180001dd7  add     rcx, rsi
0x180001dda  add     rdx, rsi
0x180001ddd  mov     al, [rdx]
0x180001ddf  test    al, al
0x180001de1  jnz     short loc_180001DCD
0x180001de3  mov     byte ptr [rcx], 0
0x180001de6  mov     al, [rbx]
0x180001de8  test    al, al
0x180001dea  jz      loc_180001F03
0x180001df0  mov     rcx, rbx
0x180001df3  sub     al, 2Dh ; '-'
0x180001df5  test    al, 0FDh
0x180001df7  jnz     loc_180001EF6
0x180001dfd  mov     al, [rcx+1]
0x180001e00  sub     al, 41h ; 'A'
0x180001e02  cmp     al, 25h ; '%'
0x180001e04  ja      loc_180001EF6
0x180001e0a  mov     rdx, 2100000021h
0x180001e14  bt      rdx, rax
0x180001e18  jnb     loc_180001EF6
0x180001e1e  cmp     rcx, rbx
0x180001e21  jz      short loc_180001E41
0x180001e23  lea     rdx, [rcx-1]
0x180001e27  cmp     byte ptr [rdx], 20h ; ' '
0x180001e2a  jz      short loc_180001E41
0x180001e2c  movsx   eax, byte ptr [rdx]
0x180001e2f  sub     eax, 9
0x180001e32  cmp     eax, 4
0x180001e35  jbe     short loc_180001E41
0x180001e37  cmp     byte ptr [rdx], 22h ; '"'
0x180001e3a  jz      short loc_180001E41
0x180001e3c  cmp     byte ptr [rdx], 27h ; '''
0x180001e3f  jnz     short loc_180001E6A
0x180001e41  mov     al, [rcx+1]
0x180001e44  mov     rdi, rcx
0x180001e47  add     rcx, 2
0x180001e4b  sub     al, 46h ; 'F'
0x180001e4d  test    al, 0DFh
0x180001e4f  jnz     loc_180001ED6
0x180001e55  jmp     short loc_180001E86
0x180001e57  mov     al, [rdx]
0x180001e59  cmp     al, 3Ah ; ':'
0x180001e5b  jz      short loc_180001E41
0x180001e5d  sub     al, 30h ; '0'
0x180001e5f  cmp     al, 9
0x180001e61  ja      loc_180001EF6
0x180001e67  sub     rdx, rsi
0x180001e6a  cmp     rdx, rbx
0x180001e6d  jnb     short loc_180001E57
0x180001e6f  jmp     loc_180001EF6
0x180001e74  cmp     al, 20h ; ' '
0x180001e76  jz      short loc_180001E83
0x180001e78  movsx   eax, al
0x180001e7b  sub     eax, 9
0x180001e7e  cmp     eax, 4
0x180001e81  ja      short loc_180001E8C
0x180001e83  add     rcx, rsi
0x180001e86  mov     al, [rcx]
0x180001e88  test    al, al
0x180001e8a  jnz     short loc_180001E74
0x180001e8c  mov     al, [rcx]
0x180001e8e  cmp     al, 22h ; '"'
0x180001e90  jz      short loc_180001E9B
0x180001e92  cmp     al, 27h ; '''
0x180001e94  jz      short loc_180001E9B
0x180001e96  xor     r8d, r8d
0x180001e99  jmp     short loc_180001EA3
0x180001e9b  add     rcx, rsi
0x180001e9e  mov     r8d, esi
0x180001ea1  mov     al, [rcx]
0x180001ea3  test    al, al
0x180001ea5  jz      short loc_180001ED6
0x180001ea7  mov     dl, [rcx]
0x180001ea9  cmp     dl, 20h ; ' '
0x180001eac  jz      short loc_180001EB9
0x180001eae  movsx   eax, dl
0x180001eb1  sub     eax, 9
0x180001eb4  cmp     eax, 4
0x180001eb7  ja      short loc_180001EBE
0x180001eb9  test    r8d, r8d
0x180001ebc  jz      short loc_180001ED6
0x180001ebe  cmp     dl, 22h ; '"'
0x180001ec1  jz      short loc_180001EC8
0x180001ec3  cmp     dl, 27h ; '''
0x180001ec6  jnz     short loc_180001ECD
0x180001ec8  test    r8d, r8d
0x180001ecb  jnz     short loc_180001ED6
0x180001ecd  add     rcx, rsi
0x180001ed0  mov     dl, [rcx]
0x180001ed2  test    dl, dl
0x180001ed4  jnz     short loc_180001EA9
0x180001ed6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001eda  inc     r8
0x180001edd  cmp     byte ptr [rcx+r8], 0
0x180001ee2  jnz     short loc_180001EDA
0x180001ee4  mov     rdx, rcx; Src
0x180001ee7  inc     r8; Size
0x180001eea  mov     rcx, rdi; void *
0x180001eed  call    memmove_0
0x180001ef2  lea     rcx, [rdi-1]
0x180001ef6  add     rcx, rsi
0x180001ef9  mov     al, [rcx]
0x180001efb  test    al, al
0x180001efd  jnz     loc_180001DF3
0x180001f03  mov     edx, 3Ah ; ':'; wMatch
0x180001f08  mov     rcx, rbx; pszStart
0x180001f0b  call    cs:__imp_StrChrA
0x180001f12  nop     dword ptr [rax+rax+00h]
0x180001f17  test    rax, rax
0x180001f1a  jz      short loc_180001F1F
0x180001f1c  mov     byte ptr [rax], 20h ; ' '
0x180001f1f  mov     edx, 104h; uSize
0x180001f24  mov     [rsp+190h+Buffer], 0
0x180001f29  lea     rcx, [rsp+190h+Buffer]; lpBuffer
0x180001f2e  call    cs:__imp_GetSystemWindowsDirectoryA
0x180001f35  nop     dword ptr [rax+rax+00h]
0x180001f3a  test    eax, eax
0x180001f3c  jz      short loc_180001F6B
0x180001f3e  lea     rax, [rsp+190h+Buffer]
0x180001f43  mov     [rsp+190h+nShowCmd], 5; nShowCmd
0x180001f4b  mov     r9, rbx; lpParameters
0x180001f4e  mov     [rsp+190h+lpDirectory], rax; lpDirectory
0x180001f53  lea     r8, File; "telnet.exe"
0x180001f5a  xor     edx, edx; lpOperation
0x180001f5c  mov     rcx, r14; hwnd
0x180001f5f  call    cs:__imp_ShellExecuteA
0x180001f66  nop     dword ptr [rax+rax+00h]
0x180001f6b  mov     rcx, [rbp+90h+var_20]
0x180001f6f  xor     rcx, rsp; StackCookie
0x180001f72  call    __security_check_cookie
0x180001f77  lea     r11, [rsp+190h+var_10]
0x180001f7f  mov     rbx, [r11+28h]
0x180001f83  mov     rsi, [r11+38h]
0x180001f87  mov     rsp, r11
0x180001f8a  pop     r14
0x180001f8c  pop     rdi
0x180001f8d  pop     rbp
0x180001f8e  retn
```
