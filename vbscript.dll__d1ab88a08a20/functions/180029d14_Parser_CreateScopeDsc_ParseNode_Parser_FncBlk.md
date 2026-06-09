# Parser::CreateScopeDsc(ParseNode *,Parser::FncBlk * *)

- ea: `0x180029d14`
- end: `0x18002a0b1`
- name: `?CreateScopeDsc@Parser@@AEAAXPEAUParseNode@@PEAPEAUFncBlk@1@@Z`
- size: `925`
- prototype: `void __fastcall(Parser *__hidden this, struct ParseNode *, struct Parser::FncBlk **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800291dc`

## callees

- `0x18000b714`
- `0x180029d14`
- `0x180079436`

## import_xrefs

- `msvcrt!malloc` at `0x180029ffa`
- `msvcrt!malloc` at `0x18002a049`
- `msvcrt!malloc` at `0x180029ffa`
- `msvcrt!malloc` at `0x18002a049`

## pseudocode

```c
void __fastcall Parser::CreateScopeDsc(Parser *this, struct ParseNode *a2, struct Parser::FncBlk **a3)
{
  int v3; // r11d
  __int64 v6; // r9
  int v7; // r14d
  int v8; // r14d
  __int64 v9; // rcx
  int v10; // ebp
  __int64 i; // rax
  int v12; // esi
  int v13; // r15d
  char *v14; // rax
  char *v15; // rdi
  __int16 v16; // bp
  __int64 v17; // rdx
  int v18; // ecx
  _DWORD *v19; // r9
  __int64 j; // r8
  __int64 v21; // r11
  __int16 v22; // ax
  int v23; // ecx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  int v26; // r8d
  __int64 v27; // rdx
  int v28; // ecx
  int v29; // r13d
  int v30; // ecx
  __int64 v31; // rax
  __int64 k; // r8
  __int64 v33; // r11
  __int16 v34; // ax
  int v35; // ecx
  _QWORD *v36; // rax
  int v37; // edi
  int v38; // eax
  int v39; // ecx
  int v40; // eax
  _QWORD *v41; // rax
  char **v42; // rdx
  int v43; // eax
  int v44; // eax
  int v45; // [rsp+60h] [rbp+8h]

  v3 = *(_DWORD *)a2;
  ++*((_DWORD *)this + 82);
  v6 = *((_QWORD *)a2 + 5);
  v7 = 0;
  v45 = v3;
  while ( v6 )
  {
    v9 = *(_QWORD *)(v6 + 32);
    --v7;
    *(_DWORD *)(v9 + 20) = *((_DWORD *)this + 82);
    *(_QWORD *)(v9 + 24) = v6;
    *(_DWORD *)(v6 + 24) = v7;
    v6 = *(_QWORD *)(v6 + 16);
  }
  v8 = -v7;
  if ( (__int16)v8 != v8 )
    goto LABEL_4;
  v31 = *((_QWORD *)a2 + 6);
  v29 = 0;
  while ( v31 )
  {
    v25 = *(_QWORD *)(v31 + 32);
    v26 = *((_DWORD *)this + 82);
    if ( *(_DWORD *)(v25 + 20) == v26 )
      v27 = *(_QWORD *)(v25 + 24);
    else
      v27 = 0;
    if ( v27 )
    {
      v30 = *(_DWORD *)(v27 + 24);
      *(_DWORD *)(v31 + 4) |= 0x4000u;
    }
    else
    {
      *(_DWORD *)(v25 + 20) = v26;
      *(_QWORD *)(v25 + 24) = v31;
      v28 = *(_DWORD *)(v31 + 4);
      if ( (v28 & 0x3400) != 0 )
      {
        *(_DWORD *)(v31 + 4) = v28 | 0x4000;
        v30 = 0;
      }
      else
      {
        v30 = ++v29;
      }
    }
    *(_DWORD *)(v31 + 24) = v30;
    v31 = *(_QWORD *)(v31 + 16);
  }
  v10 = 0;
  if ( v3 != 60 )
    v10 = v29;
  if ( v3 != 45 )
    v29 = 0;
  for ( i = *((_QWORD *)a2 + 7); i; i = *(_QWORD *)(i + 16) )
    *(_DWORD *)(i + 24) = ++v10;
  if ( (__int16)v10 != v10 )
LABEL_4:
    Parser::Error(this, 1001);
  v12 = 8 * (v8 + v29) + 72;
  if ( v12 <= 0 )
    goto LABEL_55;
  v13 = *((_DWORD *)this + 6);
  if ( v12 <= *((_DWORD *)this + 7) - v13 )
  {
LABEL_11:
    *((_DWORD *)this + 6) = v13 + v12;
    v14 = (char *)(*((_QWORD *)this + 2) + v13);
    goto LABEL_12;
  }
  v37 = *((_DWORD *)this + 9);
  if ( v12 < v37 )
  {
    v38 = 8 * (v8 + v29) + 72;
    v39 = *((_DWORD *)this + 8);
    if ( *((_DWORD *)this + 7) > v12 )
      v38 = *((_DWORD *)this + 7);
    v40 = 2 * v38;
    if ( v39 <= v40 )
      v39 = v40;
    if ( v39 > v37 || (v37 = v39, v12 <= v39) )
    {
      if ( v37 + 8 > v37 && v37 + 8 >= v12 )
      {
        v41 = malloc(v37 + 8LL);
        if ( v41 )
        {
          v13 = 0;
          *v41 = *((_QWORD *)this + 2);
          *((_QWORD *)this + 2) = v41;
          *((_DWORD *)this + 7) = v37;
          goto LABEL_11;
        }
      }
    }
LABEL_55:
    *a3 = 0;
LABEL_56:
    Parser::Error(this, 1001);
  }
  if ( 8 * (v8 + v29) + 80 <= 8 * (v8 + v29) + 72 )
    goto LABEL_55;
  v14 = (char *)malloc(v12 + 8LL);
  if ( !v14 )
    goto LABEL_55;
  v42 = (char **)*((_QWORD *)this + 2);
  if ( v13 >= *((_DWORD *)this + 7) )
  {
    *(_QWORD *)v14 = v42;
    *((_QWORD *)this + 2) = v14;
  }
  else
  {
    *(_QWORD *)v14 = *v42;
    *v42 = v14;
  }
LABEL_12:
  v15 = v14 + 8;
  *a3 = (struct Parser::FncBlk *)(v14 + 8);
  if ( v14 == (char *)-8LL )
    goto LABEL_56;
  v16 = v10 - v29;
  memset_0(v15, 0, v12);
  *((_DWORD *)v15 + 2) = 8 * (v8 + v29) + 48;
  *((_DWORD *)v15 + 17) |= *((_DWORD *)this + 160) | *((_DWORD *)a2 + 1) & 0x4002;
  v17 = *((_QWORD *)a2 + 8);
  v18 = 0;
  while ( v17 )
  {
    v43 = *(_DWORD *)(v17 + 40);
    v17 = *(_QWORD *)(v17 + 16);
    v44 = v43 + 1;
    if ( v18 >= v44 )
      v44 = v18;
    v18 = v44;
  }
  *((_WORD *)v15 + 32) = v16;
  v19 = v15 + 72;
  *((_WORD *)v15 + 33) = v18;
  *((_WORD *)v15 + 30) = v8;
  *((_WORD *)v15 + 31) = v29;
  for ( j = *((_QWORD *)a2 + 5); j; j = *(_QWORD *)(j + 16) )
  {
    if ( (*(_DWORD *)(j + 4) & 0x4000) == 0 )
    {
      v21 = *(_QWORD *)(j + 32);
      v22 = *(_WORD *)(v21 + 10);
      if ( (v22 & 0x4000) == 0 )
      {
        v23 = *(_DWORD *)(v21 + 40);
        *(_WORD *)(v21 + 10) = v22 | 0x4000;
        *(_DWORD *)(v21 + 16) = *((_DWORD *)this + 153) + 8;
        v24 = (_QWORD *)*((_QWORD *)this + 79);
        *((_DWORD *)this + 153) = (*((_DWORD *)this + 153) + 13 + 2 * v23) & 0xFFFFFFFC;
        *v24 = v21;
        *((_QWORD *)this + 79) = v21 + 32;
      }
      *v19 = *(_DWORD *)(v21 + 16);
      v19[1] = *(_DWORD *)(j + 4) & 0x302;
      v19 += 2;
    }
  }
  if ( v45 == 45 )
  {
    for ( k = *((_QWORD *)a2 + 6); k; k = *(_QWORD *)(k + 16) )
    {
      if ( (*(_DWORD *)(k + 4) & 0x4000) == 0 )
      {
        v33 = *(_QWORD *)(k + 32);
        v34 = *(_WORD *)(v33 + 10);
        if ( (v34 & 0x4000) == 0 )
        {
          v35 = *(_DWORD *)(v33 + 40);
          *(_WORD *)(v33 + 10) = v34 | 0x4000;
          *(_DWORD *)(v33 + 16) = *((_DWORD *)this + 153) + 8;
          v36 = (_QWORD *)*((_QWORD *)this + 79);
          *((_DWORD *)this + 153) = (*((_DWORD *)this + 153) + 13 + 2 * v35) & 0xFFFFFFFC;
          *v36 = v33;
          *((_QWORD *)this + 79) = v33 + 32;
        }
        *v19 = *(_DWORD *)(v33 + 16);
        v19[1] = *(_DWORD *)(k + 4) & 0x302;
        v19 += 2;
      }
    }
  }
}

```

## disassembly

```asm
0x180029d14  mov     [rsp+arg_10], r8
0x180029d19  mov     [rsp+arg_8], rdx
0x180029d1e  push    rbx
0x180029d1f  push    rbp
0x180029d20  push    rsi
0x180029d21  push    rdi
0x180029d22  push    r13
0x180029d24  push    r14
0x180029d26  push    r15
0x180029d28  sub     rsp, 20h
0x180029d2c  mov     r11d, [rdx]
0x180029d2f  mov     r10, rdx
0x180029d32  inc     dword ptr [rcx+148h]
0x180029d38  mov     rbx, rcx
0x180029d3b  mov     r9, [rdx+28h]
0x180029d3f  xor     r14d, r14d
0x180029d42  mov     [rsp+58h+arg_0], r11d
0x180029d47  test    r9, r9
0x180029d4a  jnz     short loc_180029D6A
0x180029d4c  neg     r14d
0x180029d4f  movsx   eax, r14w
0x180029d53  cmp     eax, r14d
0x180029d56  jz      loc_18002A07E
0x180029d5c  mov     edx, 3E9h; int
0x180029d61  mov     rcx, rbx; this
0x180029d64  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180029d6a  mov     rcx, [r9+20h]
0x180029d6e  dec     r14d
0x180029d71  mov     eax, [rbx+148h]
0x180029d77  mov     [rcx+14h], eax
0x180029d7a  mov     [rcx+18h], r9
0x180029d7e  mov     [r9+18h], r14d
0x180029d82  mov     r9, [r9+10h]
0x180029d86  jmp     short loc_180029D47
0x180029d88  inc     ebp
0x180029d8a  mov     [rax+18h], ebp
0x180029d8d  mov     rax, [rax+10h]
0x180029d91  test    rax, rax
0x180029d94  jnz     short loc_180029D88
0x180029d96  movsx   eax, bp
0x180029d99  cmp     eax, ebp
0x180029d9b  jnz     short loc_180029D5C
0x180029d9d  lea     eax, [r14+r13]
0x180029da1  lea     esi, ds:48h[rax*8]
0x180029da8  test    esi, esi
0x180029daa  jle     loc_18002A00B
0x180029db0  mov     eax, [rbx+1Ch]
0x180029db3  mov     r15d, [rbx+18h]
0x180029db7  sub     eax, r15d
0x180029dba  cmp     esi, eax
0x180029dbc  jg      loc_180029FC6
0x180029dc2  lea     eax, [r15+rsi]
0x180029dc6  mov     [rbx+18h], eax
0x180029dc9  movsxd  rax, r15d
0x180029dcc  add     rax, [rbx+10h]
0x180029dd0  lea     rdi, [rax+8]
0x180029dd4  mov     rax, [rsp+58h+arg_10]
0x180029dd9  mov     [rax], rdi
0x180029ddc  test    rdi, rdi
0x180029ddf  jz      loc_18002A017
0x180029de5  movsxd  r8, esi; Size
0x180029de8  xor     edx, edx; Val
0x180029dea  mov     rcx, rdi; void *
0x180029ded  sub     ebp, r13d
0x180029df0  call    memset_0
0x180029df5  lea     eax, [rsi-18h]
0x180029df8  mov     rsi, [rsp+58h+arg_8]
0x180029dfd  mov     [rdi+8], eax
0x180029e00  mov     eax, [rsi+4]
0x180029e03  and     eax, 4002h
0x180029e08  or      eax, [rbx+280h]
0x180029e0e  or      [rdi+44h], eax
0x180029e11  mov     rdx, [rsi+40h]
0x180029e15  xor     ecx, ecx
0x180029e17  test    rdx, rdx
0x180029e1a  jnz     loc_18002A09C
0x180029e20  mov     [rdi+40h], bp
0x180029e24  lea     r9, [rdi+48h]
0x180029e28  mov     [rdi+42h], cx
0x180029e2c  mov     ebp, 4000h
0x180029e31  mov     [rdi+3Ch], r14w
0x180029e36  mov     [rdi+3Eh], r13w
0x180029e3b  mov     edi, 302h
0x180029e40  mov     r8, [rsi+28h]
0x180029e44  test    r8, r8
0x180029e47  jz      loc_180029F34
0x180029e4d  test    [r8+4], ebp
0x180029e51  jnz     short loc_180029EB9
0x180029e53  mov     r11, [r8+20h]
0x180029e57  movzx   eax, word ptr [r11+0Ah]
0x180029e5c  test    bp, ax
0x180029e5f  jnz     short loc_180029EA4
0x180029e61  mov     ecx, [r11+28h]
0x180029e65  or      ax, bp
0x180029e68  mov     [r11+0Ah], ax
0x180029e6d  mov     eax, [rbx+264h]
0x180029e73  add     eax, 8
0x180029e76  mov     [r11+10h], eax
0x180029e7a  mov     edx, [rbx+264h]
0x180029e80  mov     rax, [rbx+278h]
0x180029e87  add     edx, 0Dh
0x180029e8a  lea     edx, [rdx+rcx*2]
0x180029e8d  and     edx, 0FFFFFFFCh
0x180029e90  mov     [rbx+264h], edx
0x180029e96  mov     [rax], r11
0x180029e99  lea     rax, [r11+20h]
0x180029e9d  mov     [rbx+278h], rax
0x180029ea4  mov     eax, [r11+10h]
0x180029ea8  mov     [r9], eax
0x180029eab  mov     eax, [r8+4]
0x180029eaf  and     eax, edi
0x180029eb1  mov     [r9+4], eax
0x180029eb5  add     r9, 8
0x180029eb9  mov     r8, [r8+10h]
0x180029ebd  jmp     short loc_180029E44
0x180029ebf  test    rax, rax
0x180029ec2  jz      short loc_180029F00
0x180029ec4  mov     rcx, [rax+20h]
0x180029ec8  mov     r8d, [rbx+148h]
0x180029ecf  cmp     [rcx+14h], r8d
0x180029ed3  jnz     short loc_180029F1D
0x180029ed5  mov     rdx, [rcx+18h]
0x180029ed9  test    rdx, rdx
0x180029edc  jnz     short loc_180029F2B
0x180029ede  mov     [rcx+14h], r8d
0x180029ee2  mov     [rcx+18h], rax
0x180029ee6  mov     ecx, [rax+4]
0x180029ee9  test    ecx, 3400h
0x180029eef  jnz     short loc_180029F21
0x180029ef1  inc     r13d
0x180029ef4  mov     ecx, r13d
0x180029ef7  mov     [rax+18h], ecx
0x180029efa  mov     rax, [rax+10h]
0x180029efe  jmp     short loc_180029EBF
0x180029f00  xor     ebp, ebp
0x180029f02  cmp     r11d, 3Ch ; '<'
0x180029f06  cmovnz  ebp, r13d
0x180029f0a  xor     eax, eax
0x180029f0c  cmp     r11d, 2Dh ; '-'
0x180029f10  cmovnz  r13d, eax
0x180029f14  mov     rax, [r10+38h]
0x180029f18  jmp     loc_180029D91
0x180029f1d  xor     edx, edx
0x180029f1f  jmp     short loc_180029ED9
0x180029f21  or      ecx, r9d
0x180029f24  mov     [rax+4], ecx
0x180029f27  xor     ecx, ecx
0x180029f29  jmp     short loc_180029EF7
0x180029f2b  mov     ecx, [rdx+18h]
0x180029f2e  or      [rax+4], r9d
0x180029f32  jmp     short loc_180029EF7
0x180029f34  cmp     [rsp+58h+arg_0], 2Dh ; '-'
0x180029f39  jnz     short loc_180029FB6
0x180029f3b  mov     r8, [rsi+30h]
0x180029f3f  test    r8, r8
0x180029f42  jz      short loc_180029FB6
0x180029f44  test    [r8+4], ebp
0x180029f48  jnz     short loc_180029FB0
0x180029f4a  mov     r11, [r8+20h]
0x180029f4e  movzx   eax, word ptr [r11+0Ah]
0x180029f53  test    bp, ax
0x180029f56  jnz     short loc_180029F9B
0x180029f58  mov     ecx, [r11+28h]
0x180029f5c  or      ax, bp
0x180029f5f  mov     [r11+0Ah], ax
0x180029f64  mov     eax, [rbx+264h]
0x180029f6a  add     eax, 8
0x180029f6d  mov     [r11+10h], eax
0x180029f71  mov     edx, [rbx+264h]
0x180029f77  mov     rax, [rbx+278h]
0x180029f7e  add     edx, 0Dh
0x180029f81  lea     edx, [rdx+rcx*2]
0x180029f84  and     edx, 0FFFFFFFCh
0x180029f87  mov     [rbx+264h], edx
0x180029f8d  mov     [rax], r11
0x180029f90  lea     rax, [r11+20h]
0x180029f94  mov     [rbx+278h], rax
0x180029f9b  mov     eax, [r11+10h]
0x180029f9f  mov     [r9], eax
0x180029fa2  mov     eax, [r8+4]
0x180029fa6  and     eax, edi
0x180029fa8  mov     [r9+4], eax
0x180029fac  add     r9, 8
0x180029fb0  mov     r8, [r8+10h]
0x180029fb4  jmp     short loc_180029F3F
0x180029fb6  add     rsp, 20h
0x180029fba  pop     r15
0x180029fbc  pop     r14
0x180029fbe  pop     r13
0x180029fc0  pop     rdi
0x180029fc1  pop     rsi
0x180029fc2  pop     rbp
0x180029fc3  pop     rbx
0x180029fc4  retn
0x180029fc6  mov     edi, [rbx+24h]
0x180029fc9  cmp     esi, edi
0x180029fcb  jge     short loc_18002A03B
0x180029fcd  cmp     [rbx+1Ch], esi
0x180029fd0  mov     eax, esi
0x180029fd2  mov     ecx, [rbx+20h]
0x180029fd5  cmovg   eax, [rbx+1Ch]
0x180029fd9  add     eax, eax
0x180029fdb  cmp     ecx, eax
0x180029fdd  cmovle  ecx, eax
0x180029fe0  cmp     ecx, edi
0x180029fe2  jle     loc_18002A072
0x180029fe8  lea     eax, [rdi+8]
0x180029feb  cmp     eax, edi
0x180029fed  jl      short loc_18002A00B
0x180029fef  cmp     eax, esi
0x180029ff1  jl      short loc_18002A00B
0x180029ff3  movsxd  rcx, edi
0x180029ff6  add     rcx, 8; Size
0x180029ffa  call    cs:__imp_malloc
0x18002a001  nop     dword ptr [rax+rax+00h]
0x18002a006  test    rax, rax
0x18002a009  jnz     short loc_18002A025
0x18002a00b  mov     rax, [rsp+58h+arg_10]
0x18002a010  mov     qword ptr [rax], 0
0x18002a017  mov     edx, 3E9h; int
0x18002a01c  mov     rcx, rbx; this
0x18002a01f  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18002a025  mov     rcx, [rbx+10h]
0x18002a029  xor     r15d, r15d
0x18002a02c  mov     [rax], rcx
0x18002a02f  mov     [rbx+10h], rax
0x18002a033  mov     [rbx+1Ch], edi
0x18002a036  jmp     loc_180029DC2
0x18002a03b  lea     eax, [rsi+8]
0x18002a03e  cmp     eax, esi
0x18002a040  jl      short loc_18002A00B
0x18002a042  movsxd  rcx, esi
0x18002a045  add     rcx, 8; Size
0x18002a049  call    cs:__imp_malloc
0x18002a050  nop     dword ptr [rax+rax+00h]
0x18002a055  test    rax, rax
0x18002a058  jz      short loc_18002A00B
0x18002a05a  mov     rdx, [rbx+10h]
0x18002a05e  cmp     r15d, [rbx+1Ch]
0x18002a062  jge     short loc_18002A090
0x18002a064  mov     rcx, [rdx]
0x18002a067  mov     [rax], rcx
0x18002a06a  mov     [rdx], rax
0x18002a06d  jmp     loc_180029DD0
0x18002a072  mov     edi, ecx
0x18002a074  cmp     esi, ecx
0x18002a076  jle     loc_180029FE8
0x18002a07c  jmp     short loc_18002A00B
0x18002a07e  mov     rax, [rdx+30h]
0x18002a082  xor     r13d, r13d
0x18002a085  mov     r9d, 4000h
0x18002a08b  jmp     loc_180029EBF
0x18002a090  mov     [rax], rdx
0x18002a093  mov     [rbx+10h], rax
0x18002a097  jmp     loc_180029DD0
0x18002a09c  mov     eax, [rdx+28h]
0x18002a09f  mov     rdx, [rdx+10h]
0x18002a0a3  inc     eax
0x18002a0a5  cmp     ecx, eax
0x18002a0a7  cmovge  eax, ecx
0x18002a0aa  mov     ecx, eax
0x18002a0ac  jmp     loc_180029E17
```
