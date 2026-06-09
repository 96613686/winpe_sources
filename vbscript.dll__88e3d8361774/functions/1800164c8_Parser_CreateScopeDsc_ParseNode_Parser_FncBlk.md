# Parser::CreateScopeDsc(ParseNode *,Parser::FncBlk * *)

- ea: `0x1800164c8`
- end: `0x180016854`
- name: `?CreateScopeDsc@Parser@@AEAAXPEAUParseNode@@PEAPEAUFncBlk@1@@Z`
- size: `908`
- prototype: `void __fastcall(Parser *__hidden this, struct ParseNode *, struct Parser::FncBlk **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800159a0`

## callees

- `0x18000d4dc`
- `0x1800164c8`
- `0x180076746`

## import_xrefs

- `msvcrt!malloc` at `0x1800167a9`
- `msvcrt!malloc` at `0x1800167f2`
- `msvcrt!malloc` at `0x1800167a9`
- `msvcrt!malloc` at `0x1800167f2`

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
0x1800164c8  mov     [rsp+arg_10], r8
0x1800164cd  mov     [rsp+arg_8], rdx
0x1800164d2  push    rbx
0x1800164d3  push    rbp
0x1800164d4  push    rsi
0x1800164d5  push    rdi
0x1800164d6  push    r13
0x1800164d8  push    r14
0x1800164da  push    r15
0x1800164dc  sub     rsp, 20h
0x1800164e0  mov     r11d, [rdx]
0x1800164e3  mov     r10, rdx
0x1800164e6  inc     dword ptr [rcx+148h]
0x1800164ec  mov     rbx, rcx
0x1800164ef  mov     r9, [rdx+28h]
0x1800164f3  xor     r14d, r14d
0x1800164f6  mov     [rsp+58h+arg_0], r11d
0x1800164fb  test    r9, r9
0x1800164fe  jnz     short loc_18001651E
0x180016500  neg     r14d
0x180016503  movsx   eax, r14w
0x180016507  cmp     eax, r14d
0x18001650a  jz      loc_180016821
0x180016510  mov     edx, 3E9h; int
0x180016515  mov     rcx, rbx; this
0x180016518  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18001651e  mov     rcx, [r9+20h]
0x180016522  dec     r14d
0x180016525  mov     eax, [rbx+148h]
0x18001652b  mov     [rcx+14h], eax
0x18001652e  mov     [rcx+18h], r9
0x180016532  mov     [r9+18h], r14d
0x180016536  mov     r9, [r9+10h]
0x18001653a  jmp     short loc_1800164FB
0x18001653c  inc     ebp
0x18001653e  mov     [rax+18h], ebp
0x180016541  mov     rax, [rax+10h]
0x180016545  test    rax, rax
0x180016548  jnz     short loc_18001653C
0x18001654a  movsx   eax, bp
0x18001654d  cmp     eax, ebp
0x18001654f  jnz     short loc_180016510
0x180016551  lea     eax, [r14+r13]
0x180016555  lea     esi, ds:48h[rax*8]
0x18001655c  test    esi, esi
0x18001655e  jle     loc_1800167B4
0x180016564  mov     eax, [rbx+1Ch]
0x180016567  mov     r15d, [rbx+18h]
0x18001656b  sub     eax, r15d
0x18001656e  cmp     esi, eax
0x180016570  jg      loc_180016779
0x180016576  lea     eax, [r15+rsi]
0x18001657a  mov     [rbx+18h], eax
0x18001657d  movsxd  rax, r15d
0x180016580  add     rax, [rbx+10h]
0x180016584  lea     rdi, [rax+8]
0x180016588  mov     rax, [rsp+58h+arg_10]
0x18001658d  mov     [rax], rdi
0x180016590  test    rdi, rdi
0x180016593  jz      loc_1800167C0
0x180016599  movsxd  r8, esi; Size
0x18001659c  xor     edx, edx; Val
0x18001659e  mov     rcx, rdi; void *
0x1800165a1  sub     ebp, r13d
0x1800165a4  call    memset_0
0x1800165a9  lea     eax, [rsi-18h]
0x1800165ac  mov     rsi, [rsp+58h+arg_8]
0x1800165b1  mov     [rdi+8], eax
0x1800165b4  mov     eax, [rsi+4]
0x1800165b7  and     eax, 4002h
0x1800165bc  or      eax, [rbx+280h]
0x1800165c2  or      [rdi+44h], eax
0x1800165c5  mov     rdx, [rsi+40h]
0x1800165c9  xor     ecx, ecx
0x1800165cb  test    rdx, rdx
0x1800165ce  jnz     loc_18001683F
0x1800165d4  mov     [rdi+40h], bp
0x1800165d8  lea     r9, [rdi+48h]
0x1800165dc  mov     [rdi+42h], cx
0x1800165e0  mov     ebp, 4000h
0x1800165e5  mov     [rdi+3Ch], r14w
0x1800165ea  mov     [rdi+3Eh], r13w
0x1800165ef  mov     edi, 302h
0x1800165f4  mov     r8, [rsi+28h]
0x1800165f8  test    r8, r8
0x1800165fb  jz      loc_1800166E8
0x180016601  test    [r8+4], ebp
0x180016605  jnz     short loc_18001666D
0x180016607  mov     r11, [r8+20h]
0x18001660b  movzx   eax, word ptr [r11+0Ah]
0x180016610  test    bp, ax
0x180016613  jnz     short loc_180016658
0x180016615  mov     ecx, [r11+28h]
0x180016619  or      ax, bp
0x18001661c  mov     [r11+0Ah], ax
0x180016621  mov     eax, [rbx+264h]
0x180016627  add     eax, 8
0x18001662a  mov     [r11+10h], eax
0x18001662e  mov     edx, [rbx+264h]
0x180016634  mov     rax, [rbx+278h]
0x18001663b  add     edx, 0Dh
0x18001663e  lea     edx, [rdx+rcx*2]
0x180016641  and     edx, 0FFFFFFFCh
0x180016644  mov     [rbx+264h], edx
0x18001664a  mov     [rax], r11
0x18001664d  lea     rax, [r11+20h]
0x180016651  mov     [rbx+278h], rax
0x180016658  mov     eax, [r11+10h]
0x18001665c  mov     [r9], eax
0x18001665f  mov     eax, [r8+4]
0x180016663  and     eax, edi
0x180016665  mov     [r9+4], eax
0x180016669  add     r9, 8
0x18001666d  mov     r8, [r8+10h]
0x180016671  jmp     short loc_1800165F8
0x180016673  test    rax, rax
0x180016676  jz      short loc_1800166B4
0x180016678  mov     rcx, [rax+20h]
0x18001667c  mov     r8d, [rbx+148h]
0x180016683  cmp     [rcx+14h], r8d
0x180016687  jnz     short loc_1800166D1
0x180016689  mov     rdx, [rcx+18h]
0x18001668d  test    rdx, rdx
0x180016690  jnz     short loc_1800166DF
0x180016692  mov     [rcx+14h], r8d
0x180016696  mov     [rcx+18h], rax
0x18001669a  mov     ecx, [rax+4]
0x18001669d  test    ecx, 3400h
0x1800166a3  jnz     short loc_1800166D5
0x1800166a5  inc     r13d
0x1800166a8  mov     ecx, r13d
0x1800166ab  mov     [rax+18h], ecx
0x1800166ae  mov     rax, [rax+10h]
0x1800166b2  jmp     short loc_180016673
0x1800166b4  xor     ebp, ebp
0x1800166b6  cmp     r11d, 3Ch ; '<'
0x1800166ba  cmovnz  ebp, r13d
0x1800166be  xor     eax, eax
0x1800166c0  cmp     r11d, 2Dh ; '-'
0x1800166c4  cmovnz  r13d, eax
0x1800166c8  mov     rax, [r10+38h]
0x1800166cc  jmp     loc_180016545
0x1800166d1  xor     edx, edx
0x1800166d3  jmp     short loc_18001668D
0x1800166d5  or      ecx, r9d
0x1800166d8  mov     [rax+4], ecx
0x1800166db  xor     ecx, ecx
0x1800166dd  jmp     short loc_1800166AB
0x1800166df  mov     ecx, [rdx+18h]
0x1800166e2  or      [rax+4], r9d
0x1800166e6  jmp     short loc_1800166AB
0x1800166e8  cmp     [rsp+58h+arg_0], 2Dh ; '-'
0x1800166ed  jnz     short loc_18001676A
0x1800166ef  mov     r8, [rsi+30h]
0x1800166f3  test    r8, r8
0x1800166f6  jz      short loc_18001676A
0x1800166f8  test    [r8+4], ebp
0x1800166fc  jnz     short loc_180016764
0x1800166fe  mov     r11, [r8+20h]
0x180016702  movzx   eax, word ptr [r11+0Ah]
0x180016707  test    bp, ax
0x18001670a  jnz     short loc_18001674F
0x18001670c  mov     ecx, [r11+28h]
0x180016710  or      ax, bp
0x180016713  mov     [r11+0Ah], ax
0x180016718  mov     eax, [rbx+264h]
0x18001671e  add     eax, 8
0x180016721  mov     [r11+10h], eax
0x180016725  mov     edx, [rbx+264h]
0x18001672b  mov     rax, [rbx+278h]
0x180016732  add     edx, 0Dh
0x180016735  lea     edx, [rdx+rcx*2]
0x180016738  and     edx, 0FFFFFFFCh
0x18001673b  mov     [rbx+264h], edx
0x180016741  mov     [rax], r11
0x180016744  lea     rax, [r11+20h]
0x180016748  mov     [rbx+278h], rax
0x18001674f  mov     eax, [r11+10h]
0x180016753  mov     [r9], eax
0x180016756  mov     eax, [r8+4]
0x18001675a  and     eax, edi
0x18001675c  mov     [r9+4], eax
0x180016760  add     r9, 8
0x180016764  mov     r8, [r8+10h]
0x180016768  jmp     short loc_1800166F3
0x18001676a  add     rsp, 20h
0x18001676e  pop     r15
0x180016770  pop     r14
0x180016772  pop     r13
0x180016774  pop     rdi
0x180016775  pop     rsi
0x180016776  pop     rbp
0x180016777  pop     rbx
0x180016778  retn
0x180016779  mov     edi, [rbx+24h]
0x18001677c  cmp     esi, edi
0x18001677e  jge     short loc_1800167E4
0x180016780  cmp     [rbx+1Ch], esi
0x180016783  mov     eax, esi
0x180016785  mov     ecx, [rbx+20h]
0x180016788  cmovg   eax, [rbx+1Ch]
0x18001678c  add     eax, eax
0x18001678e  cmp     ecx, eax
0x180016790  cmovle  ecx, eax
0x180016793  cmp     ecx, edi
0x180016795  jle     short loc_180016815
0x180016797  lea     eax, [rdi+8]
0x18001679a  cmp     eax, edi
0x18001679c  jl      short loc_1800167B4
0x18001679e  cmp     eax, esi
0x1800167a0  jl      short loc_1800167B4
0x1800167a2  movsxd  rcx, edi
0x1800167a5  add     rcx, 8; Size
0x1800167a9  call    cs:__imp_malloc
0x1800167af  test    rax, rax
0x1800167b2  jnz     short loc_1800167CE
0x1800167b4  mov     rax, [rsp+58h+arg_10]
0x1800167b9  mov     qword ptr [rax], 0
0x1800167c0  mov     edx, 3E9h; int
0x1800167c5  mov     rcx, rbx; this
0x1800167c8  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x1800167ce  mov     rcx, [rbx+10h]
0x1800167d2  xor     r15d, r15d
0x1800167d5  mov     [rax], rcx
0x1800167d8  mov     [rbx+10h], rax
0x1800167dc  mov     [rbx+1Ch], edi
0x1800167df  jmp     loc_180016576
0x1800167e4  lea     eax, [rsi+8]
0x1800167e7  cmp     eax, esi
0x1800167e9  jl      short loc_1800167B4
0x1800167eb  movsxd  rcx, esi
0x1800167ee  add     rcx, 8; Size
0x1800167f2  call    cs:__imp_malloc
0x1800167f8  test    rax, rax
0x1800167fb  jz      short loc_1800167B4
0x1800167fd  mov     rdx, [rbx+10h]
0x180016801  cmp     r15d, [rbx+1Ch]
0x180016805  jge     short loc_180016833
0x180016807  mov     rcx, [rdx]
0x18001680a  mov     [rax], rcx
0x18001680d  mov     [rdx], rax
0x180016810  jmp     loc_180016584
0x180016815  mov     edi, ecx
0x180016817  cmp     esi, ecx
0x180016819  jle     loc_180016797
0x18001681f  jmp     short loc_1800167B4
0x180016821  mov     rax, [rdx+30h]
0x180016825  xor     r13d, r13d
0x180016828  mov     r9d, 4000h
0x18001682e  jmp     loc_180016673
0x180016833  mov     [rax], rdx
0x180016836  mov     [rbx+10h], rax
0x18001683a  jmp     loc_180016584
0x18001683f  mov     eax, [rdx+28h]
0x180016842  mov     rdx, [rdx+10h]
0x180016846  inc     eax
0x180016848  cmp     ecx, eax
0x18001684a  cmovge  eax, ecx
0x18001684d  mov     ecx, eax
0x18001684f  jmp     loc_1800165CB
```
