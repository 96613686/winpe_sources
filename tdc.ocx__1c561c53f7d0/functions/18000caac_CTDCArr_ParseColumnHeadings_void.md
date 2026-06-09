# CTDCArr::ParseColumnHeadings(void)

- ea: `0x18000caac`
- end: `0x18000cea6`
- name: `?ParseColumnHeadings@CTDCArr@@AEAAJXZ`
- size: `1018`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000baa0`

## callees

- `0x18000caac`
- `0x180014232`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000cb1c`
- `ole32!CoTaskMemRealloc` at `0x18000cb1c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce68`
- `SHLWAPI!StrCmpIW` at `0x18000cc58`
- `SHLWAPI!StrCmpIW` at `0x18000cc87`
- `SHLWAPI!StrCmpIW` at `0x18000ccb6`
- `SHLWAPI!StrCmpIW` at `0x18000cce5`
- `SHLWAPI!StrCmpIW` at `0x18000cd14`
- `SHLWAPI!StrCmpIW` at `0x18000cc58`
- `SHLWAPI!StrCmpIW` at `0x18000cc87`
- `SHLWAPI!StrCmpIW` at `0x18000ccb6`
- `SHLWAPI!StrCmpIW` at `0x18000cce5`
- `SHLWAPI!StrCmpIW` at `0x18000cd14`

## pseudocode

```c
__int64 __fastcall CTDCArr::ParseColumnHeadings(CTDCArr *this)
{
  unsigned __int64 v1; // rax
  __int64 v3; // r13
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // rdi
  LPVOID v7; // rax
  unsigned int v8; // edi
  _WORD *v9; // rdx
  __int64 v10; // rbp
  __int64 v11; // rbx
  __int64 v12; // r14
  OLECHAR *v13; // r12
  OLECHAR v14; // ax
  OLECHAR *v15; // rcx
  const WCHAR *v16; // rbx
  __int16 *v17; // r14
  WCHAR v18; // ax
  _WORD *v19; // rcx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rcx
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rcx
  const WCHAR *v24; // rcx
  int v25; // ecx
  __int16 v26; // ax
  int v27; // r10d
  int v28; // r9d
  int v29; // edx
  int v30; // r8d
  bool v31; // cc
  OLECHAR v32; // cx
  OLECHAR *v33; // rax
  OLECHAR *v34; // rdx
  OLECHAR *v35; // r8
  __int64 v37; // [rsp+68h] [rbp+10h]

  v1 = *((_QWORD *)this + 23);
  v3 = *((int *)this + 28);
  v4 = v1 + v3;
  if ( v1 + v3 < v1 || v4 >= 0x7FFFFFFF )
    return (unsigned int)-2147024809;
  v5 = *((_QWORD *)this + 24);
  if ( v4 > v5 )
  {
    if ( !v5 )
      LODWORD(v5) = 8;
    while ( v4 > (unsigned int)v5 )
      LODWORD(v5) = 2 * v5;
    v6 = (unsigned int)v5;
    v7 = CoTaskMemRealloc(*((LPVOID *)this + 22), 8LL * (unsigned int)v5);
    if ( !v7 )
      return (unsigned int)-2147024882;
    *((_QWORD *)this + 24) = v6;
    *((_QWORD *)this + 22) = v7;
  }
  memmove_0((void *)(*((_QWORD *)this + 22) + 8 * v3), *((const void **)this + 22), 8LL * *((_QWORD *)this + 23));
  v9 = (_WORD *)*((_QWORD *)this + 22);
  if ( v9 < &v9[4 * v3] )
  {
    do
    {
      if ( v9 )
        *v9 = 0;
      v9 += 4;
    }
    while ( (unsigned __int64)v9 < *((_QWORD *)this + 22) + 8 * v3 );
  }
  *((_QWORD *)this + 23) += v3;
  v8 = 0;
LABEL_98:
  if ( (int)v3 > 0 )
  {
    v10 = *((_QWORD *)this + 22);
    v11 = 3LL * (unsigned int)v3;
    v12 = ***((_QWORD ***)this + 16);
    v37 = v12;
    v13 = *(OLECHAR **)(v12 + 24LL * (unsigned int)v3 - 16);
    *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 8;
    if ( !v13 )
      goto LABEL_96;
    v14 = *v13;
    if ( *v13 )
    {
      v15 = v13;
      while ( v14 != 58 )
      {
        v14 = *++v15;
        if ( !*v15 )
          goto LABEL_83;
      }
      if ( v15 )
      {
        v16 = v15 + 1;
        *v15 = 0;
        v17 = 0;
        if ( v15 == (OLECHAR *)-2LL )
        {
          v20 = &psz1;
        }
        else
        {
          v18 = *v16;
          if ( *v16 )
          {
            v19 = v15 + 1;
            while ( v18 != 32 )
            {
              v18 = *++v19;
              if ( !*v19 )
                goto LABEL_31;
            }
            if ( v19 )
            {
              *v19 = 0;
              v17 = v19 + 1;
            }
          }
LABEL_31:
          v20 = v16;
        }
        if ( !StrCmpIW(v20, L"int") )
        {
          *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 3;
          goto LABEL_82;
        }
        v21 = &psz1;
        if ( v16 )
          v21 = v16;
        if ( !StrCmpIW(v21, L"float") )
        {
          *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 5;
          goto LABEL_82;
        }
        v22 = &psz1;
        if ( v16 )
          v22 = v16;
        if ( !StrCmpIW(v22, L"string") )
        {
          *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 8;
          goto LABEL_82;
        }
        v23 = &psz1;
        if ( v16 )
          v23 = v16;
        if ( !StrCmpIW(v23, L"boolean") )
        {
          *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 11;
          goto LABEL_82;
        }
        v24 = &psz1;
        if ( v16 )
          v24 = v16;
        if ( !StrCmpIW(v24, L"date") )
        {
          *(_WORD *)(v10 + 8LL * (unsigned int)v3 - 8) = 7;
          v25 = 0;
          if ( !v17 )
            goto LABEL_81;
          v26 = *v17;
          if ( !*v17 )
            goto LABEL_81;
          v27 = 0;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          while ( 1 )
          {
            if ( v26 == 68 )
            {
LABEL_61:
              v28 = v27;
              goto LABEL_62;
            }
            if ( v26 == 77 )
              break;
            switch ( v26 )
            {
              case 'Y':
                goto LABEL_59;
              case 'd':
                goto LABEL_61;
              case 'm':
                goto LABEL_60;
              case 'y':
LABEL_59:
                v30 = v27;
                break;
            }
LABEL_62:
            ++v17;
            ++v27;
            v26 = *v17;
            if ( !*v17 )
            {
              if ( v28 < v29 && v29 < v30 )
              {
                v25 = 1;
                goto LABEL_81;
              }
              if ( v28 >= v30 )
              {
                v31 = v29 < v30;
              }
              else
              {
                if ( v29 < v28 )
                {
                  v25 = 3;
                  goto LABEL_81;
                }
                v31 = v29 < v30;
                if ( v29 > v30 )
                {
                  v25 = 2;
                  goto LABEL_81;
                }
              }
              if ( v31 && v30 < v28 )
              {
                v25 = 4;
              }
              else if ( v30 >= v29 || v29 >= v28 )
              {
                if ( v30 < v28 && v28 < v29 )
                  v25 = 6;
              }
              else
              {
                v25 = 5;
              }
LABEL_81:
              *(_DWORD *)(v10 + 8LL * (unsigned int)v3 - 4) = v25;
              goto LABEL_82;
            }
          }
LABEL_60:
          v29 = v27;
          goto LABEL_62;
        }
LABEL_82:
        v12 = v37;
        v11 = 3LL * (unsigned int)v3;
      }
    }
LABEL_83:
    v32 = *v13;
    if ( !*v13 )
      goto LABEL_95;
    v33 = 0;
    v34 = 0;
    v35 = v13;
    while ( v32 == 32 || v32 == 9 )
    {
      if ( v33 )
        goto LABEL_91;
LABEL_92:
      v32 = *++v35;
      if ( !*v35 )
      {
        if ( v34 )
        {
          v34[1] = 0;
          goto LABEL_96;
        }
LABEL_95:
        *v13 = 0;
LABEL_96:
        *(_QWORD *)(v12 + 8 * v11 - 16) = SysAllocString(v13);
        SysFreeString(v13);
        if ( *(_QWORD *)(v12 + 8 * v11 - 16) )
        {
          LODWORD(v3) = v3 - 1;
          goto LABEL_98;
        }
        return (unsigned int)-2147024882;
      }
    }
    if ( !v33 )
      v33 = v13;
    v34 = v33;
LABEL_91:
    *v33++ = v32;
    goto LABEL_92;
  }
  return v8;
}

```

## disassembly

```asm
0x18000caac  mov     [rsp+arg_10], rbx
0x18000cab1  push    rbp
0x18000cab2  push    rsi
0x18000cab3  push    rdi
0x18000cab4  push    r12
0x18000cab6  push    r13
0x18000cab8  push    r14
0x18000caba  push    r15
0x18000cabc  sub     rsp, 20h
0x18000cac0  mov     rax, [rcx+0B8h]
0x18000cac7  mov     rsi, rcx
0x18000caca  movsxd  r13, dword ptr [rcx+70h]
0x18000cace  lea     rdx, [rax+r13]
0x18000cad2  cmp     rdx, rax
0x18000cad5  jb      loc_18000CE8A
0x18000cadb  cmp     rdx, 7FFFFFFFh
0x18000cae2  jnb     loc_18000CE8A
0x18000cae8  mov     rcx, [rcx+0C0h]
0x18000caef  mov     edi, 8
0x18000caf4  cmp     rdx, rcx
0x18000caf7  jbe     short loc_18000CB44
0x18000caf9  test    rcx, rcx
0x18000cafc  jnz     short loc_18000CB04
0x18000cafe  mov     ecx, edi
0x18000cb00  jmp     short loc_18000CB04
0x18000cb02  add     ecx, ecx
0x18000cb04  mov     eax, ecx
0x18000cb06  cmp     rdx, rax
0x18000cb09  ja      short loc_18000CB02
0x18000cb0b  mov     edi, ecx
0x18000cb0d  mov     rcx, [rsi+0B0h]; pv
0x18000cb14  lea     rdx, ds:0[rdi*8]; cb
0x18000cb1c  call    cs:__imp_CoTaskMemRealloc
0x18000cb22  test    rax, rax
0x18000cb25  jnz     short loc_18000CB31
0x18000cb27  mov     edi, 8007000Eh
0x18000cb2c  jmp     loc_18000CE8F
0x18000cb31  mov     [rsi+0C0h], rdi
0x18000cb38  mov     edi, 8
0x18000cb3d  mov     [rsi+0B0h], rax
0x18000cb44  mov     rdx, [rsi+0B0h]; Src
0x18000cb4b  mov     r8, [rsi+0B8h]
0x18000cb52  shl     r8, 3; Size
0x18000cb56  lea     rcx, [rdx+r13*8]; void *
0x18000cb5a  call    memmove_0
0x18000cb5f  mov     rdx, [rsi+0B0h]
0x18000cb66  xor     r11d, r11d
0x18000cb69  lea     rax, [rdx+r13*8]
0x18000cb6d  cmp     rdx, rax
0x18000cb70  jnb     short loc_18000CB8E
0x18000cb72  test    rdx, rdx
0x18000cb75  jz      short loc_18000CB7B
0x18000cb77  mov     [rdx], r11w
0x18000cb7b  mov     rax, [rsi+0B0h]
0x18000cb82  add     rdx, rdi
0x18000cb85  lea     rcx, [rax+r13*8]
0x18000cb89  cmp     rdx, rcx
0x18000cb8c  jb      short loc_18000CB72
0x18000cb8e  add     [rsi+0B8h], r13
0x18000cb95  mov     edi, r11d
0x18000cb98  jmp     loc_18000CE7F
0x18000cb9d  mov     rax, [rsi+80h]
0x18000cba4  mov     rbp, [rsi+0B0h]
0x18000cbab  mov     r15d, r13d
0x18000cbae  mov     rcx, [rax]
0x18000cbb1  lea     rbx, [r15+r15*2]
0x18000cbb5  mov     [rsp+58h+arg_0], rbx
0x18000cbba  mov     r14, [rcx]
0x18000cbbd  mov     [rsp+58h+arg_8], r14
0x18000cbc2  mov     r12, [r14+rbx*8-10h]
0x18000cbc7  mov     word ptr [rbp+r15*8-8], 8
0x18000cbcf  test    r12, r12
0x18000cbd2  jz      loc_18000CE57
0x18000cbd8  movzx   eax, word ptr [r12]
0x18000cbdd  test    ax, ax
0x18000cbe0  jz      loc_18000CE02
0x18000cbe6  mov     rcx, r12
0x18000cbe9  cmp     ax, 3Ah ; ':'
0x18000cbed  jz      short loc_18000CC00
0x18000cbef  add     rcx, 2
0x18000cbf3  movzx   eax, word ptr [rcx]
0x18000cbf6  test    ax, ax
0x18000cbf9  jnz     short loc_18000CBE9
0x18000cbfb  jmp     loc_18000CE02
0x18000cc00  test    rcx, rcx
0x18000cc03  jz      loc_18000CE02
0x18000cc09  lea     rbx, [rcx+2]
0x18000cc0d  mov     [rcx], r11w
0x18000cc11  mov     r14, r11
0x18000cc14  test    rbx, rbx
0x18000cc17  jz      short loc_18000CC4A
0x18000cc19  movzx   eax, word ptr [rbx]
0x18000cc1c  test    ax, ax
0x18000cc1f  jz      short loc_18000CC45
0x18000cc21  mov     rcx, rbx
0x18000cc24  cmp     ax, 20h ; ' '
0x18000cc28  jz      short loc_18000CC38
0x18000cc2a  add     rcx, 2
0x18000cc2e  movzx   eax, word ptr [rcx]
0x18000cc31  test    ax, ax
0x18000cc34  jnz     short loc_18000CC24
0x18000cc36  jmp     short loc_18000CC45
0x18000cc38  test    rcx, rcx
0x18000cc3b  jz      short loc_18000CC45
0x18000cc3d  mov     [rcx], r11w
0x18000cc41  lea     r14, [rcx+2]
0x18000cc45  mov     rcx, rbx
0x18000cc48  jmp     short loc_18000CC51
0x18000cc4a  lea     rcx, psz1; psz1
0x18000cc51  lea     rdx, aInt; "int"
0x18000cc58  call    cs:__imp_StrCmpIW
0x18000cc5e  xor     r11d, r11d
0x18000cc61  test    eax, eax
0x18000cc63  jnz     short loc_18000CC72
0x18000cc65  mov     word ptr [rbp+r15*8-8], 3
0x18000cc6d  jmp     loc_18000CDF8
0x18000cc72  test    rbx, rbx
0x18000cc75  lea     rcx, psz1
0x18000cc7c  lea     rdx, aFloat; "float"
0x18000cc83  cmovnz  rcx, rbx; psz1
0x18000cc87  call    cs:__imp_StrCmpIW
0x18000cc8d  xor     r11d, r11d
0x18000cc90  test    eax, eax
0x18000cc92  jnz     short loc_18000CCA1
0x18000cc94  mov     word ptr [rbp+r15*8-8], 5
0x18000cc9c  jmp     loc_18000CDF8
0x18000cca1  test    rbx, rbx
0x18000cca4  lea     rcx, psz1
0x18000ccab  lea     rdx, aString; "string"
0x18000ccb2  cmovnz  rcx, rbx; psz1
0x18000ccb6  call    cs:__imp_StrCmpIW
0x18000ccbc  xor     r11d, r11d
0x18000ccbf  test    eax, eax
0x18000ccc1  jnz     short loc_18000CCD0
0x18000ccc3  mov     word ptr [rbp+r15*8-8], 8
0x18000cccb  jmp     loc_18000CDF8
0x18000ccd0  test    rbx, rbx
0x18000ccd3  lea     rcx, psz1
0x18000ccda  lea     rdx, aBoolean; "boolean"
0x18000cce1  cmovnz  rcx, rbx; psz1
0x18000cce5  call    cs:__imp_StrCmpIW
0x18000cceb  xor     r11d, r11d
0x18000ccee  test    eax, eax
0x18000ccf0  jnz     short loc_18000CCFF
0x18000ccf2  mov     word ptr [rbp+r15*8-8], 0Bh
0x18000ccfa  jmp     loc_18000CDF8
0x18000ccff  test    rbx, rbx
0x18000cd02  lea     rcx, psz1
0x18000cd09  lea     rdx, aDate; "date"
0x18000cd10  cmovnz  rcx, rbx; psz1
0x18000cd14  call    cs:__imp_StrCmpIW
0x18000cd1a  xor     r11d, r11d
0x18000cd1d  test    eax, eax
0x18000cd1f  jnz     loc_18000CDF8
0x18000cd25  mov     word ptr [rbp+r15*8-8], 7
0x18000cd2d  mov     ecx, r11d
0x18000cd30  test    r14, r14
0x18000cd33  jz      loc_18000CDF3
0x18000cd39  movzx   eax, word ptr [r14]
0x18000cd3d  test    ax, ax
0x18000cd40  jz      loc_18000CDF3
0x18000cd46  mov     r10d, r11d
0x18000cd49  mov     r9d, r11d
0x18000cd4c  mov     edx, r11d
0x18000cd4f  mov     r8d, r11d
0x18000cd52  cmp     ax, 44h ; 'D'
0x18000cd56  jz      short loc_18000CD80
0x18000cd58  cmp     ax, 4Dh ; 'M'
0x18000cd5c  jz      short loc_18000CD7B
0x18000cd5e  cmp     ax, 59h ; 'Y'
0x18000cd62  jz      short loc_18000CD76
0x18000cd64  cmp     ax, 64h ; 'd'
0x18000cd68  jz      short loc_18000CD80
0x18000cd6a  cmp     ax, 6Dh ; 'm'
0x18000cd6e  jz      short loc_18000CD7B
0x18000cd70  cmp     ax, 79h ; 'y'
0x18000cd74  jnz     short loc_18000CD83
0x18000cd76  mov     r8d, r10d
0x18000cd79  jmp     short loc_18000CD83
0x18000cd7b  mov     edx, r10d
0x18000cd7e  jmp     short loc_18000CD83
0x18000cd80  mov     r9d, r10d
0x18000cd83  add     r14, 2
0x18000cd87  inc     r10d
0x18000cd8a  movzx   eax, word ptr [r14]
0x18000cd8e  test    ax, ax
0x18000cd91  jnz     short loc_18000CD52
0x18000cd93  cmp     r9d, edx
0x18000cd96  jge     short loc_18000CDA4
0x18000cd98  cmp     edx, r8d
0x18000cd9b  jge     short loc_18000CDA4
0x18000cd9d  mov     ecx, 1
0x18000cda2  jmp     short loc_18000CDF3
0x18000cda4  cmp     r9d, r8d
0x18000cda7  jge     short loc_18000CDC1
0x18000cda9  cmp     edx, r9d
0x18000cdac  jge     short loc_18000CDB5
0x18000cdae  mov     ecx, 3
0x18000cdb3  jmp     short loc_18000CDF3
0x18000cdb5  cmp     edx, r8d
0x18000cdb8  jle     short loc_18000CDC4
0x18000cdba  mov     ecx, 2
0x18000cdbf  jmp     short loc_18000CDF3
0x18000cdc1  cmp     edx, r8d
0x18000cdc4  jge     short loc_18000CDD2
0x18000cdc6  cmp     r8d, r9d
0x18000cdc9  jge     short loc_18000CDD2
0x18000cdcb  mov     ecx, 4
0x18000cdd0  jmp     short loc_18000CDF3
0x18000cdd2  cmp     r8d, edx
0x18000cdd5  jge     short loc_18000CDE3
0x18000cdd7  cmp     edx, r9d
0x18000cdda  jge     short loc_18000CDE3
0x18000cddc  mov     ecx, 5
0x18000cde1  jmp     short loc_18000CDF3
0x18000cde3  cmp     r8d, r9d
0x18000cde6  jge     short loc_18000CDF3
0x18000cde8  cmp     r9d, edx
0x18000cdeb  mov     eax, 6
0x18000cdf0  cmovl   ecx, eax
0x18000cdf3  mov     [rbp+r15*8-4], ecx
0x18000cdf8  mov     r14, [rsp+58h+arg_8]
0x18000cdfd  mov     rbx, [rsp+58h+arg_0]
0x18000ce02  movzx   ecx, word ptr [r12]
0x18000ce07  test    cx, cx
0x18000ce0a  jz      short loc_18000CE52
0x18000ce0c  mov     rax, r11
0x18000ce0f  mov     rdx, r11
0x18000ce12  mov     r8, r12
0x18000ce15  cmp     cx, 20h ; ' '
0x18000ce19  jz      short loc_18000CE2D
0x18000ce1b  cmp     cx, 9
0x18000ce1f  jz      short loc_18000CE2D
0x18000ce21  test    rax, rax
0x18000ce24  cmovz   rax, r12
0x18000ce28  mov     rdx, rax
0x18000ce2b  jmp     short loc_18000CE32
0x18000ce2d  test    rax, rax
0x18000ce30  jz      short loc_18000CE39
0x18000ce32  mov     [rax], cx
0x18000ce35  add     rax, 2
0x18000ce39  add     r8, 2
0x18000ce3d  movzx   ecx, word ptr [r8]
0x18000ce41  test    cx, cx
0x18000ce44  jnz     short loc_18000CE15
0x18000ce46  test    rdx, rdx
0x18000ce49  jz      short loc_18000CE52
0x18000ce4b  mov     [rdx+2], r11w
0x18000ce50  jmp     short loc_18000CE57
0x18000ce52  mov     [r12], r11w
0x18000ce57  mov     rcx, r12; psz
0x18000ce5a  call    cs:__imp_SysAllocString
0x18000ce60  mov     rcx, r12; bstrString
0x18000ce63  mov     [r14+rbx*8-10h], rax
0x18000ce68  call    cs:__imp_SysFreeString
0x18000ce6e  xor     r11d, r11d
0x18000ce71  cmp     [r14+rbx*8-10h], r11
0x18000ce76  jz      loc_18000CB27
0x18000ce7c  dec     r13d
0x18000ce7f  test    r13d, r13d
0x18000ce82  jg      loc_18000CB9D
0x18000ce88  jmp     short loc_18000CE8F
0x18000ce8a  mov     edi, 80070057h
0x18000ce8f  mov     rbx, [rsp+58h+arg_10]
0x18000ce94  mov     eax, edi
0x18000ce96  add     rsp, 20h
0x18000ce9a  pop     r15
0x18000ce9c  pop     r14
0x18000ce9e  pop     r13
0x18000cea0  pop     r12
0x18000cea2  pop     rdi
0x18000cea3  pop     rsi
0x18000cea4  pop     rbp
0x18000cea5  retn
```
