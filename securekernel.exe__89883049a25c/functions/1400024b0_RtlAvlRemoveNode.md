# RtlAvlRemoveNode

- ea: `0x1400024b0`
- end: `0x1400028f5`
- name: `RtlAvlRemoveNode`
- size: `1093`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x140001320`
- `0x1400014b4`
- `0x140014dd0`
- `0x14002c288`
- `0x14002cb4c`
- `0x14002dca8`
- `0x140037398`
- `0x14003793c`
- `0x14003acd8`
- `0x14004c800`
- `0x14004c9ac`
- `0x14007115c`
- `0x140076948`
- `0x1400b0f54`
- `0x1400c0ae8`

## callees

- `0x1400024b0`
- `0x1400d5ec8`
- `0x1400d5ee8`

## pseudocode

```c
char __fastcall RtlAvlRemoveNode(unsigned __int64 *a1, __int64 a2)
{
  __int64 *v2; // r15
  __int64 *v3; // r14
  __int64 *v4; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned int v9; // ebp
  __int64 v10; // r13
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rcx
  char v16; // r12
  unsigned __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  char v20; // bp
  _BYTE *v21; // rsi
  unsigned __int8 v22; // r14
  __int64 v23; // r15
  unsigned __int64 *v24; // rax
  unsigned __int64 v25; // rdi
  char v26; // r13
  char v27; // dl
  unsigned __int8 v28; // cl
  unsigned __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rbp
  _QWORD *v32; // r14
  __int64 v33; // rax
  __int64 v34; // rbp
  unsigned __int64 v35; // rcx
  char v36; // cl
  unsigned __int64 v37; // r15
  bool v38; // zf
  _QWORD *v41; // [rsp+78h] [rbp+10h]

  v2 = *(__int64 **)a2;
  v3 = *(__int64 **)(a2 + 8);
  v4 = v3;
  if ( *(_QWORD *)a2 )
    v4 = *(__int64 **)a2;
  v6 = 0;
  if ( v2 )
    v6 = *(_QWORD *)(a2 + 8);
  if ( v6 )
  {
    if ( (*(_BYTE *)(a2 + 16) & 3) == 3 )
    {
      v7 = *(_QWORD *)a2;
      if ( v2[1] )
      {
        do
        {
          v8 = v7;
          v9 = 1;
          v7 = *(_QWORD *)(v7 + 8);
        }
        while ( *(_QWORD *)(v7 + 8) );
        v10 = *(_QWORD *)v7;
      }
      else
      {
        v10 = *v2;
        v9 = 0;
        v8 = *(_QWORD *)a2;
      }
    }
    else
    {
      v11 = (_QWORD *)*v3;
      v7 = *(_QWORD *)(a2 + 8);
      if ( *v3 )
      {
        do
        {
          v9 = 0;
          v8 = v7;
          v7 = (unsigned __int64)v11;
          v11 = (_QWORD *)*v11;
        }
        while ( v11 );
      }
      else
      {
        v9 = 1;
        v8 = *(_QWORD *)(a2 + 8);
      }
      v10 = *(_QWORD *)(v7 + 8);
    }
    *(_QWORD *)v7 = v2;
    *(_QWORD *)(v7 + 8) = v3;
    v12 = v2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v12 != a2 )
      RtlpRbReportFatalError(v12, a2, v2);
    v2[2] = v7 | v2[2] & 3;
    v13 = v3[2] & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v13 != a2 )
      RtlpRbReportFatalError(v13, a2, v3);
    v3[2] = v7 | v3[2] & 3;
    v14 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v14 != v8 )
      RtlpRbReportFatalError(v14, v8, v7);
    *(_QWORD *)(v8 + 8LL * v9) = v10;
    if ( v10 )
    {
      v15 = *(_QWORD **)(v10 + 16);
      if ( v15 != (_QWORD *)v7 )
        RtlpRbReportFatalError(v15, v7, v10);
      *(_QWORD *)(v10 + 16) = v8;
    }
    v16 = 3;
    if ( !v9 )
      v16 = 1;
    v6 = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v7 + 16) = v6;
    v17 = *(_QWORD *)(a2 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v17 )
    {
      v6 = 0;
      if ( *(_QWORD *)(v17 + 8) == a2 )
        v6 = 8;
      v18 = *(_QWORD *)(v6 + v17);
      if ( v18 != a2 )
        RtlpRbReportFatalError(v18, a2, v17);
      *(_QWORD *)(v6 + v17) = v7;
    }
    else
    {
      if ( *a1 != a2 )
        RtlpRbReportFatalError(*a1, a2, a1);
      *a1 = v7;
    }
    goto LABEL_50;
  }
  v8 = *(_QWORD *)(a2 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v4 )
  {
    v19 = v4[2];
    if ( v19 != a2 )
      RtlpRbReportFatalError(v19, a2, v4);
    v4[2] = v8;
  }
  if ( v8 )
  {
    if ( *(_QWORD *)(v8 + 8) == a2 )
    {
      v16 = 3;
      *(_QWORD *)(v8 + 8) = v4;
    }
    else
    {
      if ( *(_QWORD *)v8 != a2 )
        RtlpRbReportFatalError(*(_QWORD *)v8, a2, v8);
      v16 = 1;
      *(_QWORD *)v8 = v4;
    }
    while ( 1 )
    {
LABEL_50:
      v20 = *(_BYTE *)(v8 + 16);
      v21 = (_BYTE *)(v8 + 16);
      v22 = v20 & 3;
      if ( (v20 & 3) == ((unsigned __int8)v16 ^ 2) )
      {
        *v21 = v20 & 0xFC;
        v23 = *(_QWORD *)v21;
        goto LABEL_80;
      }
      if ( !v22 )
      {
        LOBYTE(v6) = v20 ^ (v16 ^ v20) & 3;
        *v21 = v6;
        return v6;
      }
      v23 = *(_QWORD *)v21;
      v24 = (unsigned __int64 *)(v8 + 8);
      if ( v16 != 1 )
        v24 = (unsigned __int64 *)v8;
      v25 = *v24;
      v26 = *(_BYTE *)(*v24 + 16) & 3;
      if ( v26 == ((unsigned __int8)v16 ^ 2) )
      {
        v6 = RtlpTreeDoubleRotateNodes(a1, v8, *v24, v16 == 1);
        *v21 &= 0xFCu;
        v8 = v6;
        v27 = *(_BYTE *)(v25 + 16);
        *(_BYTE *)(v25 + 16) = v27 & 0xFC;
        v28 = *(_BYTE *)(v6 + 16);
        LODWORD(v6) = v28 & 3;
        if ( v22 == (_DWORD)v6 )
        {
          LOBYTE(v6) = *v21;
          *v21 ^= (v22 ^ *v21 ^ 0xFE) & 3;
          *(_BYTE *)(v8 + 16) &= 0xFCu;
        }
        else
        {
          if ( v22 == ((v28 ^ 0xFE) & 3) )
          {
            LOBYTE(v6) = v27 ^ (v20 ^ v27) & 3;
            *(_BYTE *)(v25 + 16) = v6;
          }
          *(_BYTE *)(v8 + 16) &= 0xFCu;
        }
        goto LABEL_80;
      }
      v29 = *(_QWORD *)(v25 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v29 != v8 )
        RtlpRbReportFatalError(v29, v8, *v24);
      v30 = 0;
      if ( v16 == 1 )
        v30 = 8;
      v41 = (_QWORD *)(v8 + v30);
      if ( *(_QWORD *)(v8 + v30) != v25 )
        RtlpRbReportFatalError(*(_QWORD *)(v8 + v30), v25, v8);
      v31 = *(_QWORD *)v21;
      v32 = (_QWORD *)(*(_QWORD *)v21 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( !v32 )
        break;
      if ( v32[1] != v8 )
        goto LABEL_69;
      v32[1] = v25;
LABEL_72:
      v33 = 0;
      *(_QWORD *)(v25 + 16) ^= (*(_QWORD *)(v25 + 16) ^ v31) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v16 != 1 )
        v33 = 8;
      v34 = *(_QWORD *)(v33 + v25);
      if ( v34 )
      {
        v35 = *(_QWORD *)(v34 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v35 != v25 )
          RtlpRbReportFatalError(v35, v25, *(_QWORD *)(v33 + v25));
        *(_QWORD *)(v34 + 16) = v8 | *(_DWORD *)(v34 + 16) & 3;
      }
      *v41 = v34;
      *(_QWORD *)(v33 + v25) = v8;
      v6 = v25 | *(_DWORD *)v21 & 3;
      *(_QWORD *)v21 = v6;
      v36 = *(_BYTE *)(v25 + 16);
      if ( !v26 )
      {
        LOBYTE(v6) = v36 ^ (v16 ^ v36 ^ 0xFE) & 3;
        *(_BYTE *)(v25 + 16) = v6;
        return v6;
      }
      v8 = v25;
      *(_BYTE *)(v25 + 16) = v36 & 0xFC;
      *v21 &= 0xFCu;
LABEL_80:
      v37 = v23 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( !v37 )
        return v6;
      v38 = *(_QWORD *)(v37 + 8) == v8;
      v16 = 3;
      v8 = v37;
      if ( !v38 )
        v16 = 1;
    }
    v32 = a1;
LABEL_69:
    if ( *v32 != v8 )
      RtlpRbReportFatalError(*v32, v8, v32);
    *v32 = v25;
    goto LABEL_72;
  }
  if ( *a1 != a2 )
    RtlpRbReportFatalError(*a1, a2, a1);
  *a1 = (unsigned __int64)v4;
  return v6;
}

```

## disassembly

```asm
0x1400024b0  mov     [rsp+arg_10], rbx
0x1400024b5  mov     [rsp+arg_0], rcx
0x1400024ba  push    rbp
0x1400024bb  push    rsi
0x1400024bc  push    rdi
0x1400024bd  push    r12
0x1400024bf  push    r13
0x1400024c1  push    r14
0x1400024c3  push    r15
0x1400024c5  sub     rsp, 30h
0x1400024c9  mov     r15, [rdx]
0x1400024cc  mov     rsi, rdx
0x1400024cf  mov     r14, [rdx+8]
0x1400024d3  test    r15, r15
0x1400024d6  mov     rdi, r14
0x1400024d9  mov     rbp, rcx
0x1400024dc  cmovnz  rdi, r15
0x1400024e0  mov     edx, 1
0x1400024e5  xor     eax, eax
0x1400024e7  test    r15, r15
0x1400024ea  cmovnz  rax, r14
0x1400024ee  test    rax, rax
0x1400024f1  jz      loc_140002659
0x1400024f7  movzx   eax, byte ptr [rsi+10h]
0x1400024fb  and     al, 3
0x1400024fd  cmp     al, 3
0x1400024ff  jnz     short loc_14000252F
0x140002501  cmp     qword ptr [r15+8], 0
0x140002506  mov     rdi, r15
0x140002509  jz      short loc_140002525
0x14000250b  nop     dword ptr [rax+rax+00h]
0x140002510  mov     rbx, rdi
0x140002513  mov     ebp, edx
0x140002515  mov     rdi, [rdi+8]
0x140002519  cmp     qword ptr [rdi+8], 0
0x14000251e  jnz     short loc_140002510
0x140002520  mov     r13, [rdi]
0x140002523  jmp     short loc_14000255E
0x140002525  mov     r13, [rdi]
0x140002528  xor     ebp, ebp
0x14000252a  mov     rbx, rdi
0x14000252d  jmp     short loc_14000255E
0x14000252f  mov     rcx, [r14]
0x140002532  mov     rdi, r14
0x140002535  test    rcx, rcx
0x140002538  jz      short loc_140002555
0x14000253a  nop     word ptr [rax+rax+00h]
0x140002540  mov     rax, [rcx]
0x140002543  xor     ebp, ebp
0x140002545  mov     rbx, rdi
0x140002548  mov     rdi, rcx
0x14000254b  mov     rcx, rax
0x14000254e  test    rax, rax
0x140002551  jnz     short loc_140002540
0x140002553  jmp     short loc_14000255A
0x140002555  mov     ebp, edx
0x140002557  mov     rbx, r14
0x14000255a  mov     r13, [rdi+8]
0x14000255e  mov     [rdi], r15
0x140002561  mov     [rdi+8], r14
0x140002565  mov     rcx, [r15+10h]
0x140002569  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14000256d  cmp     rcx, rsi
0x140002570  jz      short loc_14000257D
0x140002572  mov     r8, r15
0x140002575  mov     rdx, rsi
0x140002578  call    RtlpRbReportFatalError
0x14000257d  mov     eax, [r15+10h]
0x140002581  and     eax, 3
0x140002584  or      rax, rdi
0x140002587  mov     [r15+10h], rax
0x14000258b  mov     rcx, [r14+10h]
0x14000258f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140002593  cmp     rcx, rsi
0x140002596  jz      short loc_1400025A3
0x140002598  mov     r8, r14
0x14000259b  mov     rdx, rsi
0x14000259e  call    RtlpRbReportFatalError
0x1400025a3  mov     eax, [r14+10h]
0x1400025a7  and     eax, 3
0x1400025aa  or      rax, rdi
0x1400025ad  mov     [r14+10h], rax
0x1400025b1  mov     rcx, [rdi+10h]
0x1400025b5  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400025b9  cmp     rcx, rbx
0x1400025bc  jz      short loc_1400025C9
0x1400025be  mov     r8, rdi
0x1400025c1  mov     rdx, rbx
0x1400025c4  call    RtlpRbReportFatalError
0x1400025c9  mov     eax, ebp
0x1400025cb  mov     [rbx+rax*8], r13
0x1400025cf  test    r13, r13
0x1400025d2  jz      short loc_1400025EC
0x1400025d4  mov     rcx, [r13+10h]
0x1400025d8  cmp     rcx, rdi
0x1400025db  jz      short loc_1400025E8
0x1400025dd  mov     r8, r13
0x1400025e0  mov     rdx, rdi
0x1400025e3  call    RtlpRbReportFatalError
0x1400025e8  mov     [r13+10h], rbx
0x1400025ec  test    ebp, ebp
0x1400025ee  mov     eax, 1
0x1400025f3  mov     r12d, 3
0x1400025f9  cmovz   r12d, eax
0x1400025fd  mov     rax, [rsi+10h]
0x140002601  mov     [rdi+10h], rax
0x140002605  mov     r8, [rsi+10h]
0x140002609  and     r8, 0FFFFFFFFFFFFFFFCh
0x14000260d  jnz     short loc_140002631
0x14000260f  mov     rbp, [rsp+68h+arg_0]
0x140002614  mov     rcx, [rbp+0]
0x140002618  cmp     rcx, rsi
0x14000261b  jz      short loc_140002628
0x14000261d  mov     r8, rbp
0x140002620  mov     rdx, rsi
0x140002623  call    RtlpRbReportFatalError
0x140002628  mov     [rbp+0], rdi
0x14000262c  jmp     loc_1400026D0
0x140002631  xor     eax, eax
0x140002633  mov     ecx, 8
0x140002638  cmp     [r8+8], rsi
0x14000263c  cmovz   eax, ecx
0x14000263f  mov     rcx, [rax+r8]
0x140002643  lea     r14, [rax+r8]
0x140002647  cmp     rcx, rsi
0x14000264a  jz      short loc_140002654
0x14000264c  mov     rdx, rsi
0x14000264f  call    RtlpRbReportFatalError
0x140002654  mov     [r14], rdi
0x140002657  jmp     short loc_1400026D0
0x140002659  mov     rbx, [rsi+10h]
0x14000265d  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140002661  test    rdi, rdi
0x140002664  jz      short loc_14000267E
0x140002666  mov     rcx, [rdi+10h]
0x14000266a  cmp     rcx, rsi
0x14000266d  jz      short loc_14000267A
0x14000266f  mov     r8, rdi
0x140002672  mov     rdx, rsi
0x140002675  call    RtlpRbReportFatalError
0x14000267a  mov     [rdi+10h], rbx
0x14000267e  test    rbx, rbx
0x140002681  jnz     short loc_1400026A0
0x140002683  mov     rcx, [rbp+0]
0x140002687  cmp     rcx, rsi
0x14000268a  jz      short loc_140002697
0x14000268c  mov     r8, rbp
0x14000268f  mov     rdx, rsi
0x140002692  call    RtlpRbReportFatalError
0x140002697  mov     [rbp+0], rdi
0x14000269b  jmp     loc_1400028DC
0x1400026a0  cmp     [rbx+8], rsi
0x1400026a4  jnz     short loc_1400026AF
0x1400026a6  mov     r12b, 3
0x1400026a9  mov     [rbx+8], rdi
0x1400026ad  jmp     short loc_1400026D0
0x1400026af  mov     rcx, [rbx]
0x1400026b2  cmp     rcx, rsi
0x1400026b5  jz      short loc_1400026C2
0x1400026b7  mov     r8, rbx
0x1400026ba  mov     rdx, rsi
0x1400026bd  call    RtlpRbReportFatalError
0x1400026c2  mov     r12b, 1
0x1400026c5  mov     [rbx], rdi
0x1400026c8  nop     dword ptr [rax+rax+00000000h]
0x1400026d0  movzx   ebp, byte ptr [rbx+10h]
0x1400026d4  lea     rsi, [rbx+10h]
0x1400026d8  movzx   r14d, bpl
0x1400026dc  movzx   ecx, r12b
0x1400026e0  and     r14b, 3
0x1400026e4  xor     cl, 2
0x1400026e7  cmp     r14b, cl
0x1400026ea  jnz     short loc_1400026FB
0x1400026ec  and     bpl, 0FCh
0x1400026f0  mov     [rsi], bpl
0x1400026f3  mov     r15, [rsi]
0x1400026f6  jmp     loc_140002889
0x1400026fb  test    r14b, r14b
0x1400026fe  jz      loc_1400028CE
0x140002704  mov     r15, [rsi]
0x140002707  lea     rax, [rbx+8]
0x14000270b  cmp     r12b, 1
0x14000270f  cmovnz  rax, rbx
0x140002713  mov     rdi, [rax]
0x140002716  movzx   r13d, byte ptr [rdi+10h]
0x14000271b  and     r13b, 3
0x14000271f  cmp     r13b, cl
0x140002722  jnz     short loc_1400027A0
0x140002724  mov     rcx, [rsp+68h+arg_0]
0x140002729  xor     r9d, r9d
0x14000272c  cmp     r12b, 1
0x140002730  mov     r8, rdi
0x140002733  mov     rdx, rbx
0x140002736  setz    r9b
0x14000273a  call    RtlpTreeDoubleRotateNodes
0x14000273f  and     byte ptr [rsi], 0FCh
0x140002742  mov     rbx, rax
0x140002745  movzx   edx, byte ptr [rdi+10h]
0x140002749  movzx   eax, dl
0x14000274c  movzx   r8d, r14b
0x140002750  and     al, 0FCh
0x140002752  mov     [rdi+10h], al
0x140002755  movzx   ecx, byte ptr [rbx+10h]
0x140002759  mov     eax, ecx
0x14000275b  and     eax, 3
0x14000275e  cmp     r8d, eax
0x140002761  jnz     short loc_14000277F
0x140002763  movzx   eax, byte ptr [rsi]
0x140002766  movzx   ecx, al
0x140002769  xor     cl, r14b
0x14000276c  xor     cl, 0FEh
0x14000276f  and     cl, 3
0x140002772  xor     cl, al
0x140002774  mov     [rsi], cl
0x140002776  and     byte ptr [rbx+10h], 0FCh
0x14000277a  jmp     loc_140002889
0x14000277f  xor     ecx, 0FFFFFFFEh
0x140002782  and     ecx, 3
0x140002785  cmp     r8d, ecx
0x140002788  jnz     short loc_140002797
0x14000278a  movzx   eax, dl
0x14000278d  xor     al, bpl
0x140002790  and     al, 3
0x140002792  xor     al, dl
0x140002794  mov     [rdi+10h], al
0x140002797  and     byte ptr [rbx+10h], 0FCh
0x14000279b  jmp     loc_140002889
0x1400027a0  mov     rcx, [rdi+10h]
0x1400027a4  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400027a8  cmp     rcx, rbx
0x1400027ab  jz      short loc_1400027B8
0x1400027ad  mov     r8, rdi
0x1400027b0  mov     rdx, rbx
0x1400027b3  call    RtlpRbReportFatalError
0x1400027b8  xor     eax, eax
0x1400027ba  mov     ecx, 8
0x1400027bf  cmp     r12b, 1
0x1400027c3  cmovz   eax, ecx
0x1400027c6  add     rax, rbx
0x1400027c9  mov     [rsp+68h+arg_8], rax
0x1400027ce  mov     rcx, [rax]
0x1400027d1  cmp     rcx, rdi
0x1400027d4  jz      short loc_1400027E1
0x1400027d6  mov     r8, rbx
0x1400027d9  mov     rdx, rdi
0x1400027dc  call    RtlpRbReportFatalError
0x1400027e1  mov     rbp, [rsi]
0x1400027e4  mov     r14, rbp
0x1400027e7  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400027eb  jnz     loc_1400028AA
0x1400027f1  mov     r14, [rsp+68h+arg_0]
0x1400027f6  mov     rcx, [r14]
0x1400027f9  cmp     rcx, rbx
0x1400027fc  jz      short loc_140002809
0x1400027fe  mov     r8, r14
0x140002801  mov     rdx, rbx
0x140002804  call    RtlpRbReportFatalError
0x140002809  mov     [r14], rdi
0x14000280c  mov     rax, [rdi+10h]
0x140002810  mov     ecx, 8
0x140002815  xor     rbp, rax
0x140002818  and     rbp, 0FFFFFFFFFFFFFFFCh
0x14000281c  xor     rbp, rax
0x14000281f  xor     eax, eax
0x140002821  cmp     r12b, 1
0x140002825  mov     [rdi+10h], rbp
0x140002829  cmovnz  eax, ecx
0x14000282c  mov     rbp, [rax+rdi]
0x140002830  lea     r14, [rax+rdi]
0x140002834  test    rbp, rbp
0x140002837  jz      short loc_14000285E
0x140002839  mov     rcx, [rbp+10h]
0x14000283d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140002841  cmp     rcx, rdi
0x140002844  jz      short loc_140002851
0x140002846  mov     r8, rbp
0x140002849  mov     rdx, rdi
0x14000284c  call    RtlpRbReportFatalError
0x140002851  mov     eax, [rbp+10h]
0x140002854  and     eax, 3
0x140002857  or      rax, rbx
0x14000285a  mov     [rbp+10h], rax
0x14000285e  mov     rax, [rsp+68h+arg_8]
0x140002863  mov     [rax], rbp
0x140002866  mov     [r14], rbx
0x140002869  mov     eax, [rsi]
0x14000286b  and     eax, 3
0x14000286e  or      rax, rdi
0x140002871  mov     [rsi], rax
0x140002874  movzx   ecx, byte ptr [rdi+10h]
0x140002878  test    r13b, r13b
0x14000287b  jz      short loc_1400028BD
0x14000287d  and     cl, 0FCh
0x140002880  mov     rbx, rdi
0x140002883  mov     [rdi+10h], cl
0x140002886  and     byte ptr [rsi], 0FCh
0x140002889  and     r15, 0FFFFFFFFFFFFFFFCh
0x14000288d  jz      short loc_1400028DC
0x14000288f  cmp     [r15+8], rbx
0x140002893  mov     r12d, 3
  ... truncated ...
```
