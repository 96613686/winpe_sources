# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::find_switch_word(ushort const *,unsigned __int64 &,unsigned __int64 &)

- ea: `0x18001d144`
- end: `0x18001d339`
- name: `?find_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NPEBGAEA_K1@Z`
- size: `501`
- prototype: `char __fastcall(__int64, const WCHAR *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d3e8`

## callees

- `0x18000a380`
- `0x18000ac70`
- `0x18001ce30`
- `0x18001d144`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d269`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d269`

## pseudocode

```c
char __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::find_switch_word(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  const WCHAR *lpString2; // rdi
  unsigned __int64 cchCount2; // rbp
  const WCHAR *v8; // r15
  const WCHAR *v9; // rbx
  const WCHAR *v10; // rsi
  char result; // al
  unsigned __int16 *v12; // r14

  lpString2 = a2;
  if ( **(_QWORD **)a1 && a2 && *a2 )
  {
    mlib::m_traits<unsigned short>::CStrlen(a2, 0x10000);
    do
    {
      if ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*lpString2) )
        break;
      ++lpString2;
    }
    while ( lpString2 );
    if ( lpString2 )
    {
      cchCount2 = 0;
      if ( *lpString2 )
      {
        do
        {
          if ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(lpString2[cchCount2]) )
            break;
          ++cchCount2;
        }
        while ( lpString2[cchCount2] );
      }
      v8 = *(const WCHAR **)(*(_QWORD *)a1 + 24LL);
      v9 = v8;
      v10 = &v8[**(_QWORD **)a1];
      while ( 1 )
      {
LABEL_12:
        while ( *v9 == 34 )
        {
          v9 = (const WCHAR *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::delimit_quoted_string(
                                a1,
                                v9,
                                34);
          if ( v9 == v10 )
            return 0;
        }
        if ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v9) )
          break;
        if ( *v9 != 45 && *v9 != 47 && *v9 != 8211 && *v9 != 8260 )
        {
          while ( 1 )
          {
            if ( ++v9 == v10 )
              return 0;
            if ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v9) )
              goto LABEL_12;
          }
        }
        if ( ++v9 == v10 || v10 - v9 < cchCount2 )
          return 0;
        if ( CompareStringW(0x400u, 0x1001u, v9, cchCount2, lpString2, cchCount2) == 2 )
        {
          v12 = (unsigned __int16 *)&v9[cchCount2];
          if ( v12 == v10 || (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v12) )
          {
            result = 1;
            *a3 = v9 - v8 - 1;
            *a4 = cchCount2 + 1;
            return result;
          }
          v9 += cchCount2;
          if ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v12) )
          {
            while ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v9) )
            {
              if ( ++v9 == v10 )
                return 0;
            }
          }
        }
      }
      while ( ++v9 != v10 )
      {
        if ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v9) )
          goto LABEL_12;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001d144  mov     [rsp+arg_10], r8
0x18001d149  push    rbx
0x18001d14a  push    rbp
0x18001d14b  push    rsi
0x18001d14c  push    rdi
0x18001d14d  push    r12
0x18001d14f  push    r13
0x18001d151  push    r14
0x18001d153  push    r15
0x18001d155  sub     rsp, 38h
0x18001d159  mov     rax, [rcx]
0x18001d15c  xor     r14d, r14d
0x18001d15f  mov     r13, r9
0x18001d162  mov     rdi, rdx
0x18001d165  mov     r12, rcx
0x18001d168  cmp     [rax], r14
0x18001d16b  jz      loc_18001D1F2
0x18001d171  test    rdx, rdx
0x18001d174  jz      short loc_18001D1F2
0x18001d176  cmp     [rdx], r14w
0x18001d17a  jz      short loc_18001D1F2
0x18001d17c  mov     edx, 10000h
0x18001d181  mov     rcx, rdi
0x18001d184  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18001d189  movzx   ecx, word ptr [rdi]
0x18001d18c  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d191  test    al, al
0x18001d193  jz      short loc_18001D19B
0x18001d195  add     rdi, 2
0x18001d199  jnz     short loc_18001D189
0x18001d19b  test    rdi, rdi
0x18001d19e  jz      short loc_18001D1F2
0x18001d1a0  mov     rbp, r14
0x18001d1a3  cmp     [rdi], r14w
0x18001d1a7  jz      short loc_18001D1C0
0x18001d1a9  movzx   ecx, word ptr [rdi+rbp*2]
0x18001d1ad  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d1b2  test    al, al
0x18001d1b4  jnz     short loc_18001D1C0
0x18001d1b6  inc     rbp
0x18001d1b9  cmp     [rdi+rbp*2], r14w
0x18001d1be  jnz     short loc_18001D1A9
0x18001d1c0  mov     rax, [r12]
0x18001d1c4  mov     r15, [rax+18h]
0x18001d1c8  mov     rax, [rax]
0x18001d1cb  mov     rbx, r15
0x18001d1ce  lea     rsi, [r15+rax*2]
0x18001d1d2  mov     eax, 22h ; '"'
0x18001d1d7  cmp     [rbx], ax
0x18001d1da  jnz     short loc_18001D205
0x18001d1dc  mov     r8d, eax
0x18001d1df  mov     rdx, rbx
0x18001d1e2  mov     rcx, r12
0x18001d1e5  call    ?delimit_quoted_string@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAPEBGPEBGG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::delimit_quoted_string(ushort const *,ushort)
0x18001d1ea  mov     rbx, rax
0x18001d1ed  cmp     rax, rsi
0x18001d1f0  jnz     short loc_18001D1D2
0x18001d1f2  xor     al, al
0x18001d1f4  add     rsp, 38h
0x18001d1f8  pop     r15
0x18001d1fa  pop     r14
0x18001d1fc  pop     r13
0x18001d1fe  pop     r12
0x18001d200  pop     rdi
0x18001d201  pop     rsi
0x18001d202  pop     rbp
0x18001d203  pop     rbx
0x18001d204  retn
0x18001d205  movzx   ecx, word ptr [rbx]
0x18001d208  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d20d  test    al, al
0x18001d20f  jnz     loc_18001D2E5
0x18001d215  cmp     word ptr [rbx], 2Dh ; '-'
0x18001d219  jz      short loc_18001D239
0x18001d21b  cmp     word ptr [rbx], 2Fh ; '/'
0x18001d21f  jz      short loc_18001D239
0x18001d221  mov     eax, 2013h
0x18001d226  cmp     [rbx], ax
0x18001d229  jz      short loc_18001D239
0x18001d22b  mov     eax, 2044h
0x18001d230  cmp     [rbx], ax
0x18001d233  jnz     loc_18001D308
0x18001d239  add     rbx, 2
0x18001d23d  cmp     rbx, rsi
0x18001d240  jz      short loc_18001D1F2
0x18001d242  mov     rax, rsi
0x18001d245  sub     rax, rbx
0x18001d248  sar     rax, 1
0x18001d24b  cmp     rax, rbp
0x18001d24e  jb      short loc_18001D1F2
0x18001d250  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x18001d254  mov     r9d, ebp; cchCount1
0x18001d257  mov     r8, rbx; lpString1
0x18001d25a  mov     [rsp+78h+lpString2], rdi; lpString2
0x18001d25f  mov     edx, 1001h; dwCmpFlags
0x18001d264  mov     ecx, 400h; Locale
0x18001d269  call    cs:__imp_CompareStringW
0x18001d26f  cmp     eax, 2
0x18001d272  mov     eax, 22h ; '"'
0x18001d277  jnz     loc_18001D1D7
0x18001d27d  lea     r14, [rbx+rbp*2]
0x18001d281  cmp     r14, rsi
0x18001d284  jz      loc_18001D316
0x18001d28a  movzx   ecx, word ptr [r14]
0x18001d28e  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d293  test    al, al
0x18001d295  jnz     short loc_18001D316
0x18001d297  movzx   ecx, word ptr [r14]
0x18001d29b  mov     rbx, r14
0x18001d29e  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d2a3  xor     r14d, r14d
0x18001d2a6  test    al, al
0x18001d2a8  lea     eax, [r14+22h]
0x18001d2ac  jnz     loc_18001D1D7
0x18001d2b2  movzx   ecx, word ptr [rbx]
0x18001d2b5  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d2ba  test    al, al
0x18001d2bc  jnz     loc_18001D1D2
0x18001d2c2  add     rbx, 2
0x18001d2c6  cmp     rbx, rsi
0x18001d2c9  jnz     short loc_18001D2B2
0x18001d2cb  jmp     loc_18001D1F2
0x18001d2d0  movzx   ecx, word ptr [rbx]
0x18001d2d3  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d2d8  test    al, al
0x18001d2da  mov     eax, 22h ; '"'
0x18001d2df  jz      loc_18001D1D7
0x18001d2e5  add     rbx, 2
0x18001d2e9  cmp     rbx, rsi
0x18001d2ec  jnz     short loc_18001D2D0
0x18001d2ee  jmp     loc_18001D1F2
0x18001d2f3  movzx   ecx, word ptr [rbx]
0x18001d2f6  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001d2fb  test    al, al
0x18001d2fd  mov     eax, 22h ; '"'
0x18001d302  jnz     loc_18001D1D7
0x18001d308  add     rbx, 2
0x18001d30c  cmp     rbx, rsi
0x18001d30f  jnz     short loc_18001D2F3
0x18001d311  jmp     loc_18001D1F2
0x18001d316  mov     rcx, [rsp+78h+arg_10]
0x18001d31e  sub     rbx, r15
0x18001d321  sar     rbx, 1
0x18001d324  mov     al, 1
0x18001d326  dec     rbx
0x18001d329  mov     [rcx], rbx
0x18001d32c  lea     rcx, [rbp+1]
0x18001d330  mov     [r13+0], rcx
0x18001d334  jmp     loc_18001D1F4
```
