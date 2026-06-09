# CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)

- ea: `0x180007dec`
- end: `0x180008204`
- name: `?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z`
- size: `1048`
- prototype: `__int64 __fastcall(CommandLineBase *this, const wchar_t **, unsigned __int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800084bc`

## callees

- `0x180007dec`
- `0x18000820c`
- `0x180010310`
- `0x180014724`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007fbc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007fbc`

## pseudocode

```c
__int64 __fastcall CommandLineBase::Parse(
        CommandLineBase *this,
        const wchar_t **a2,
        unsigned __int64 a3,
        const wchar_t **a4)
{
  const wchar_t **v6; // r14
  CommandLineBase *v7; // r13
  unsigned __int64 v8; // rcx
  __int64 result; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // rdi
  struct CommandLineArg *v12; // rcx
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  const wchar_t *v16; // r12
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r15
  __int64 v19; // rdx
  const WCHAR *v20; // r14
  WCHAR v21; // ax
  const wchar_t **v22; // rdx
  __int64 cchCount2; // r13
  wchar_t *v24; // rax
  __int64 v25; // rdi
  struct CommandLineArg *v26; // rdx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rdx
  struct CommandLineArg *v29; // rcx
  __int64 v30; // r14
  int v31; // eax
  unsigned __int64 v32; // r15
  __int64 v33; // r8
  _DWORD *i; // r9
  int v35; // [rsp+50h] [rbp-51h]
  unsigned __int64 v37; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-39h]
  PCNZWCH lpString2; // [rsp+70h] [rbp-31h]
  PCNZWCH lpString1; // [rsp+78h] [rbp-29h]
  PCNZWCH *v41; // [rsp+80h] [rbp-21h]
  unsigned __int64 v42; // [rsp+88h] [rbp-19h]
  __int64 v43; // [rsp+90h] [rbp-11h]
  unsigned __int64 v44; // [rsp+98h] [rbp-9h]
  CommandLineBase *v45; // [rsp+A0h] [rbp-1h]
  struct CommandLineArg *v46; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int64 v47; // [rsp+B0h] [rbp+Fh] BYREF

  v38 = a3;
  v45 = this;
  v6 = a2;
  v7 = this;
  if ( a4 )
    *a4 = 0;
  v46 = 0;
  v47 = 0;
  (**(void (__fastcall ***)(CommandLineBase *, struct CommandLineArg **, unsigned __int64 *))this)(this, &v46, &v47);
  v8 = v47;
  if ( v47 > 0x40 )
    return 2147942456LL;
  v10 = 0;
  if ( v47 )
  {
    v11 = 0;
    do
    {
      v12 = v46;
      if ( (*(_DWORD *)((_BYTE *)v46 + v11 + 48) & 4) == 0 )
      {
        memset(
          (char *)v7 + *(_QWORD *)((char *)v46 + v11 + 8),
          0,
          *(_QWORD *)((char *)v46 + v11 + 16) * *(_QWORD *)((char *)v46 + v11 + 24));
        v12 = v46;
      }
      *(_QWORD *)((char *)v12 + v11 + 32) = 0;
      ++v10;
      v8 = v47;
      v11 += 56;
    }
    while ( v10 < v47 );
  }
  v37 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
  {
    v26 = v46;
    goto LABEL_56;
  }
  v15 = 0;
  v44 = 0;
  do
  {
    v16 = v6[v15];
    if ( (*(unsigned __int8 (__fastcall **)(CommandLineBase *, _QWORD))(*(_QWORD *)v7 + 8LL))(v7, *v16) )
    {
      v17 = v47;
      v18 = 0;
      if ( v47 )
      {
        v19 = 0;
        v43 = 0;
        while ( 1 )
        {
          v20 = *(const WCHAR **)((char *)v46 + v19);
          if ( v20 )
          {
            v21 = *v20;
            if ( *v20 )
              break;
          }
LABEL_27:
          v19 += 56;
          ++v18;
          v43 = v19;
          if ( v18 >= v17 )
            goto LABEL_28;
        }
        v42 = v14 + 1;
        v35 = 1;
        lpString1 = v16 + 1;
        v22 = &a2[v44 + 1];
        while ( 1 )
        {
          LODWORD(cchCount2) = -1;
          v41 = v22;
          if ( v21 == 32 )
          {
            do
              ++v20;
            while ( *v20 == 32 );
          }
          lpString2 = v20;
          v24 = wcschr(v20, 0x20u);
          v20 = v24;
          if ( v24 && (cchCount2 = v24 - lpString2, (unsigned __int64)(cchCount2 + 0x80000000LL) > 0xFFFFFFFF)
            || CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, cchCount2) != 2 )
          {
LABEL_26:
            v17 = v47;
            v19 = v43;
            goto LABEL_27;
          }
          if ( (_DWORD)cchCount2 == -1 )
            break;
          if ( v42 >= v38 )
            goto LABEL_26;
          ++v35;
          v22 = v41 + 1;
          lpString1 = *v41;
          v21 = *v20;
          ++v42;
        }
        v25 = 56 * v18;
        if ( *((_QWORD *)v46 + 7 * v18 + 4) && (*((_BYTE *)v46 + v25 + 48) & 0x18) == 0 )
        {
          if ( a4 )
            *a4 = v16;
          return 2147942485LL;
        }
        v6 = a2;
        v7 = v45;
        result = CommandLineBase::ParseArg(v45, &v37, v35, a2, v38, v18, v46, v47, v16, a4);
        if ( (int)result < 0 )
          return result;
        v8 = v47;
        if ( v18 < v47 )
        {
          v26 = v46;
          if ( (*((_BYTE *)v46 + v25 + 48) & 0x20) == 0 )
          {
            v27 = v37;
            goto LABEL_50;
          }
          break;
        }
      }
LABEL_28:
      if ( a4 )
        *a4 = v16;
      return 2147942422LL;
    }
    v28 = v47;
    if ( v13 >= v47 )
      goto LABEL_28;
    v29 = v46;
    v30 = 56 * v13;
    while ( 1 )
    {
      v31 = *(_DWORD *)((char *)v29 + v30 + 48);
      if ( (v31 & 1) == 0 || *(_QWORD *)((char *)v29 + v30 + 32) && (v31 & 0x10) == 0 )
        goto LABEL_45;
      v32 = v14;
      result = CommandLineBase::ParseArg(
                 v7,
                 &v37,
                 0,
                 a2,
                 v38,
                 v13,
                 v29,
                 v28,
                 *(const wchar_t **)((char *)v29 + v30),
                 a4);
      if ( (int)result < 0 )
        return result;
      v14 = v37;
      if ( v37 > v32 )
        break;
      v29 = v46;
      v28 = v47;
LABEL_45:
      ++v13;
      v30 += 56;
      if ( v13 >= v28 )
        goto LABEL_28;
    }
    v8 = v47;
    v27 = v37 - 1;
    if ( v13 >= v47 )
      goto LABEL_28;
    v26 = v46;
    v6 = a2;
    if ( (*((_BYTE *)v46 + 56 * v13 + 48) & 0x10) == 0 )
      ++v13;
LABEL_50:
    v14 = v27 + 1;
    v15 = v14;
    v37 = v14;
    v44 = v14;
  }
  while ( v14 < v38 );
LABEL_56:
  v33 = 0;
  if ( !v8 )
    return 0;
  for ( i = (_DWORD *)((char *)v26 + 48); *((_QWORD *)i - 2) || (*i & 2) == 0; i += 14 )
  {
    if ( ++v33 >= v8 )
      return 0;
  }
  if ( a4 )
    *a4 = (const wchar_t *)*((_QWORD *)v26 + 7 * v33);
  return 2147942560LL;
}

```

## disassembly

```asm
0x180007dec  mov     [rsp-8+arg_10], rbx
0x180007df1  push    rbp
0x180007df2  push    rsi
0x180007df3  push    rdi
0x180007df4  push    r12
0x180007df6  push    r13
0x180007df8  push    r14
0x180007dfa  push    r15
0x180007dfc  lea     rbp, [rsp-1Fh]
0x180007e01  sub     rsp, 0C0h
0x180007e08  mov     rax, cs:__security_cookie
0x180007e0f  xor     rax, rsp
0x180007e12  mov     [rbp+4Fh+var_38], rax
0x180007e16  xor     eax, eax
0x180007e18  mov     [rbp+4Fh+var_88], r8
0x180007e1c  mov     [rbp+4Fh+var_98], rdx
0x180007e20  mov     rbx, r9
0x180007e23  mov     [rbp+4Fh+var_50], rcx
0x180007e27  mov     r15, r8
0x180007e2a  mov     r14, rdx
0x180007e2d  mov     r13, rcx
0x180007e30  test    r9, r9
0x180007e33  jz      short loc_180007E38
0x180007e35  mov     [r9], rax
0x180007e38  mov     [rbp+4Fh+var_48], rax
0x180007e3c  lea     r8, [rbp+4Fh+var_40]
0x180007e40  mov     [rbp+4Fh+var_40], rax
0x180007e44  lea     rdx, [rbp+4Fh+var_48]
0x180007e48  mov     rax, [rcx]
0x180007e4b  mov     rax, [rax]
0x180007e4e  call    _guard_dispatch_icall
0x180007e53  mov     rcx, [rbp+4Fh+var_40]
0x180007e57  cmp     rcx, 40h ; '@'
0x180007e5b  jbe     short loc_180007E67
0x180007e5d  mov     eax, 80070038h
0x180007e62  jmp     loc_1800081C6
0x180007e67  xor     r10d, r10d
0x180007e6a  mov     esi, r10d
0x180007e6d  test    rcx, rcx
0x180007e70  jz      short loc_180007EB7
0x180007e72  mov     edi, r10d
0x180007e75  mov     rcx, [rbp+4Fh+var_48]
0x180007e79  mov     eax, [rdi+rcx+30h]
0x180007e7d  test    al, 4
0x180007e7f  jnz     short loc_180007EA2
0x180007e81  mov     r8, [rdi+rcx+18h]
0x180007e86  xor     edx, edx; Val
0x180007e88  imul    r8, [rdi+rcx+10h]; Size
0x180007e8e  mov     rcx, [rdi+rcx+8]
0x180007e93  add     rcx, r13; void *
0x180007e96  call    memset
0x180007e9b  mov     rcx, [rbp+4Fh+var_48]
0x180007e9f  xor     r10d, r10d
0x180007ea2  mov     [rdi+rcx+20h], r10
0x180007ea7  inc     rsi
0x180007eaa  mov     rcx, [rbp+4Fh+var_40]
0x180007eae  add     rdi, 38h ; '8'
0x180007eb2  cmp     rsi, rcx
0x180007eb5  jb      short loc_180007E75
0x180007eb7  mov     [rbp+4Fh+var_90], r10
0x180007ebb  mov     rsi, r10
0x180007ebe  mov     rdi, r10
0x180007ec1  test    r15, r15
0x180007ec4  jz      loc_18000819B
0x180007eca  mov     rax, r10
0x180007ecd  mov     [rbp+4Fh+var_58], rax
0x180007ed1  mov     r12, [r14+rax*8]
0x180007ed5  mov     rcx, r13
0x180007ed8  mov     rax, [r13+0]
0x180007edc  movzx   edx, word ptr [r12]
0x180007ee1  mov     rax, [rax+8]
0x180007ee5  call    _guard_dispatch_icall
0x180007eea  xor     r10d, r10d
0x180007eed  test    al, al
0x180007eef  jz      loc_1800080BA
0x180007ef5  mov     rcx, [rbp+4Fh+var_40]
0x180007ef9  mov     r15d, r10d
0x180007efc  test    rcx, rcx
0x180007eff  jz      loc_180008018
0x180007f05  mov     edx, r10d
0x180007f08  mov     [rbp+4Fh+var_60], rdx
0x180007f0c  mov     rax, [rbp+4Fh+var_48]
0x180007f10  mov     r14, [rdx+rax]
0x180007f14  test    r14, r14
0x180007f17  jz      loc_180008004
0x180007f1d  movzx   eax, word ptr [r14]
0x180007f21  cmp     r10w, ax
0x180007f25  jz      loc_180008004
0x180007f2b  mov     rdx, [rbp+4Fh+var_98]
0x180007f2f  lea     rcx, [rdi+1]
0x180007f33  mov     [rbp+4Fh+var_68], rcx
0x180007f37  lea     r8, [r12+2]
0x180007f3c  mov     rcx, [rbp+4Fh+var_58]
0x180007f40  mov     [rbp+4Fh+var_A0], 1
0x180007f47  mov     [rbp+4Fh+lpString1], r8
0x180007f4b  lea     rdx, [rdx+rcx*8]
0x180007f4f  add     rdx, 8
0x180007f53  or      r13d, 0FFFFFFFFh
0x180007f57  mov     [rbp+4Fh+var_70], rdx
0x180007f5b  lea     ecx, [r13+21h]
0x180007f5f  cmp     cx, ax
0x180007f62  jnz     short loc_180007F6E
0x180007f64  add     r14, 2
0x180007f68  cmp     cx, [r14]
0x180007f6c  jz      short loc_180007F64
0x180007f6e  mov     edx, ecx; Ch
0x180007f70  mov     [rbp+4Fh+var_80], r14
0x180007f74  mov     rcx, r14; Str
0x180007f77  call    wcschr
0x180007f7c  mov     rcx, [rbp+4Fh+var_80]
0x180007f80  mov     r14, rax
0x180007f83  test    rax, rax
0x180007f86  jz      short loc_180007FA3
0x180007f88  mov     r13, rax
0x180007f8b  mov     edx, 0FFFFFFFFh
0x180007f90  sub     r13, rcx
0x180007f93  mov     eax, 80000000h
0x180007f98  sar     r13, 1
0x180007f9b  add     rax, r13
0x180007f9e  cmp     rax, rdx
0x180007fa1  ja      short loc_180007FF9
0x180007fa3  mov     r8, [rbp+4Fh+lpString1]; lpString1
0x180007fa7  or      r9d, 0FFFFFFFFh; cchCount1
0x180007fab  mov     [rsp+0F0h+cchCount2], r13d; cchCount2
0x180007fb0  mov     [rsp+0F0h+lpString2], rcx; lpString2
0x180007fb5  lea     edx, [r9+2]; dwCmpFlags
0x180007fb9  lea     ecx, [rdx+7Eh]; Locale
0x180007fbc  call    cs:__imp_CompareStringW
0x180007fc2  cmp     eax, 2
0x180007fc5  jnz     short loc_180007FF9
0x180007fc7  cmp     r13d, 0FFFFFFFFh
0x180007fcb  jz      short loc_18000802A
0x180007fcd  mov     rcx, [rbp+4Fh+var_68]
0x180007fd1  cmp     rcx, [rbp+4Fh+var_88]
0x180007fd5  jnb     short loc_180007FF9
0x180007fd7  mov     rdx, [rbp+4Fh+var_70]
0x180007fdb  inc     [rbp+4Fh+var_A0]
0x180007fde  mov     rax, [rdx]
0x180007fe1  add     rdx, 8
0x180007fe5  inc     rcx
0x180007fe8  mov     [rbp+4Fh+lpString1], rax
0x180007fec  movzx   eax, word ptr [r14]
0x180007ff0  mov     [rbp+4Fh+var_68], rcx
0x180007ff4  jmp     loc_180007F53
0x180007ff9  mov     rcx, [rbp+4Fh+var_40]
0x180007ffd  xor     r10d, r10d
0x180008000  mov     rdx, [rbp+4Fh+var_60]
0x180008004  add     rdx, 38h ; '8'
0x180008008  inc     r15
0x18000800b  mov     [rbp+4Fh+var_60], rdx
0x18000800f  cmp     r15, rcx
0x180008012  jb      loc_180007F0C
0x180008018  test    rbx, rbx
0x18000801b  jz      short loc_180008020
0x18000801d  mov     [rbx], r12
0x180008020  mov     eax, 80070016h
0x180008025  jmp     loc_1800081C6
0x18000802a  mov     rcx, [rbp+4Fh+var_48]
0x18000802e  imul    rdi, r15, 38h ; '8'
0x180008032  cmp     qword ptr [rdi+rcx+20h], 0
0x180008038  jbe     short loc_180008045
0x18000803a  test    byte ptr [rdi+rcx+30h], 18h
0x18000803f  jz      loc_18000818C
0x180008045  mov     rax, [rbp+4Fh+var_40]
0x180008049  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x18000804d  mov     r14, [rbp+4Fh+var_98]
0x180008051  mov     r13, [rbp+4Fh+var_50]
0x180008055  mov     r9, r14; wchar_t **
0x180008058  movsxd  r8, [rbp+4Fh+var_A0]; unsigned __int64
0x18000805c  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x180008061  mov     [rsp+0F0h+var_B0], r12; wchar_t *
0x180008066  mov     [rsp+0F0h+var_B8], rax; unsigned __int64
0x18000806b  mov     rax, [rbp+4Fh+var_88]
0x18000806f  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x180008074  mov     rcx, r13; this
0x180008077  mov     qword ptr [rsp+0F0h+cchCount2], r15; unsigned __int64
0x18000807c  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x180008081  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x180008086  xor     r10d, r10d
0x180008089  test    eax, eax
0x18000808b  js      loc_1800081C6
0x180008091  mov     rcx, [rbp+4Fh+var_40]
0x180008095  cmp     r15, rcx
0x180008098  jnb     loc_180008018
0x18000809e  mov     rdx, [rbp+4Fh+var_48]
0x1800080a2  lea     r8d, [r10+20h]
0x1800080a6  test    [rdi+rdx+30h], r8b
0x1800080ab  jnz     loc_18000819F
0x1800080b1  mov     rdi, [rbp+4Fh+var_90]
0x1800080b5  jmp     loc_180008172
0x1800080ba  mov     rdx, [rbp+4Fh+var_40]
0x1800080be  cmp     rsi, rdx
0x1800080c1  jnb     loc_180008018
0x1800080c7  mov     rcx, [rbp+4Fh+var_48]
0x1800080cb  imul    r14, rsi, 38h ; '8'
0x1800080cf  mov     eax, [r14+rcx+30h]
0x1800080d4  test    al, 1
0x1800080d6  jz      short loc_18000813B
0x1800080d8  cmp     [r14+rcx+20h], r10
0x1800080dd  jbe     short loc_1800080E3
0x1800080df  test    al, 10h
0x1800080e1  jz      short loc_18000813B
0x1800080e3  mov     rax, [r14+rcx]
0x1800080e7  xor     r8d, r8d; unsigned __int64
0x1800080ea  mov     r9, [rbp+4Fh+var_98]; wchar_t **
0x1800080ee  mov     r15, rdi
0x1800080f1  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x1800080f6  mov     [rsp+0F0h+var_B0], rax; wchar_t *
0x1800080fb  mov     rax, [rbp+4Fh+var_88]
0x1800080ff  mov     [rsp+0F0h+var_B8], rdx; unsigned __int64
0x180008104  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x180008108  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x18000810d  mov     rcx, r13; this
0x180008110  mov     qword ptr [rsp+0F0h+cchCount2], rsi; unsigned __int64
0x180008115  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x18000811a  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x18000811f  xor     r10d, r10d
0x180008122  test    eax, eax
0x180008124  js      loc_1800081C6
0x18000812a  mov     rdi, [rbp+4Fh+var_90]
0x18000812e  cmp     rdi, r15
0x180008131  ja      short loc_18000814C
0x180008133  mov     rcx, [rbp+4Fh+var_48]
0x180008137  mov     rdx, [rbp+4Fh+var_40]
0x18000813b  inc     rsi
0x18000813e  add     r14, 38h ; '8'
0x180008142  cmp     rsi, rdx
0x180008145  jb      short loc_1800080CF
0x180008147  jmp     loc_180008018
0x18000814c  mov     rcx, [rbp+4Fh+var_40]
0x180008150  dec     rdi
0x180008153  cmp     rsi, rcx
0x180008156  jnb     loc_180008018
0x18000815c  mov     rdx, [rbp+4Fh+var_48]
0x180008160  mov     r14, [rbp+4Fh+var_98]
0x180008164  imul    rax, rsi, 38h ; '8'
0x180008168  test    byte ptr [rax+rdx+30h], 10h
0x18000816d  jnz     short loc_180008172
0x18000816f  inc     rsi
0x180008172  inc     rdi
0x180008175  mov     rax, rdi
0x180008178  mov     [rbp+4Fh+var_90], rdi
0x18000817c  mov     [rbp+4Fh+var_58], rax
0x180008180  cmp     rdi, [rbp+4Fh+var_88]
0x180008184  jb      loc_180007ED1
0x18000818a  jmp     short loc_18000819F
0x18000818c  test    rbx, rbx
0x18000818f  jz      short loc_180008194
0x180008191  mov     [rbx], r12
0x180008194  mov     eax, 80070055h
0x180008199  jmp     short loc_1800081C6
0x18000819b  mov     rdx, [rbp+4Fh+var_48]
0x18000819f  mov     r8, r10
0x1800081a2  test    rcx, rcx
0x1800081a5  jz      short loc_1800081C4
0x1800081a7  lea     r9, [rdx+30h]
0x1800081ab  cmp     [r9-10h], r10
0x1800081af  ja      short loc_1800081B8
0x1800081b1  mov     eax, [r9]
0x1800081b4  test    al, 2
0x1800081b6  jnz     short loc_1800081ED
0x1800081b8  inc     r8
0x1800081bb  add     r9, 38h ; '8'
0x1800081bf  cmp     r8, rcx
0x1800081c2  jb      short loc_1800081AB
0x1800081c4  xor     eax, eax
0x1800081c6  mov     rcx, [rbp+4Fh+var_38]
0x1800081ca  xor     rcx, rsp; StackCookie
0x1800081cd  call    __security_check_cookie
0x1800081d2  mov     rbx, [rsp+0F0h+arg_10]
0x1800081da  add     rsp, 0C0h
0x1800081e1  pop     r15
0x1800081e3  pop     r14
0x1800081e5  pop     r13
0x1800081e7  pop     r12
0x1800081e9  pop     rdi
0x1800081ea  pop     rsi
0x1800081eb  pop     rbp
0x1800081ec  retn
0x1800081ed  test    rbx, rbx
0x1800081f0  jz      short loc_1800081FD
0x1800081f2  imul    rax, r8, 38h ; '8'
0x1800081f6  mov     rcx, [rax+rdx]
0x1800081fa  mov     [rbx], rcx
0x1800081fd  mov     eax, 800700A0h
0x180008202  jmp     short loc_1800081C6
```
