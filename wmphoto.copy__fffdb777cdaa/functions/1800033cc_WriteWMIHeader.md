# WriteWMIHeader

- ea: `0x1800033cc`
- end: `0x180003756`
- name: `WriteWMIHeader`
- size: `906`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000129c`
- `0x180007340`

## callees

- `0x1800021c0`
- `0x1800033cc`
- `0x180003760`
- `0x18000c2e0`

## pseudocode

```c
__int64 __fastcall WriteWMIHeader(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v3; // r14d
  _QWORD *v4; // rdx
  _QWORD *v5; // r8
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  unsigned int v8; // r15d
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r11d
  unsigned int v22; // r11d
  int v23; // r8d
  int v24; // r14d
  int v25; // edx
  unsigned int *v26; // rbx
  unsigned int v27; // r11d
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // r8
  unsigned int v31; // r11d
  __int64 v32; // rax
  __int64 v33; // r8
  unsigned int v34; // r11d
  __int64 v35; // r8
  __int64 v36; // r8
  __int64 v37; // r8

  v1 = *(_QWORD *)(a1 + 34368);
  if ( ((*(_QWORD *)(a1 + 8) + 15LL) & 0xFFFFFFFFFFFFFFF0uLL) > 0xFF0
    || (v3 = 1, ((*(_QWORD *)(a1 + 16) + 15LL) & 0xFFFFFFFFFFFFFFF0uLL) > 0xFF0) )
  {
    v3 = 0;
  }
  v4 = (_QWORD *)(a1 + 34264);
  v5 = (_QWORD *)(a1 + 34272);
  v6 = (_QWORD *)(a1 + 34256);
  v7 = (_QWORD *)(a1 + 34248);
  if ( !*(_DWORD *)(a1 + 34280) )
  {
    *v4 = 0;
    *v5 = 0;
    *v6 = 0;
    *v7 = 0;
  }
  if ( *v7 || *v6 || *v4 || (v8 = 0, *v5) )
    v8 = 1;
  v9 = 0;
  do
    putBit16z(*(_QWORD *)(a1 + 34368), (unsigned __int8)gGDISignature[v9++], 8);
  while ( v9 != v10 );
  putBit16z(v1, 1, 4);
  v12 = v11 - 1;
  if ( *(_DWORD *)(a1 + 160) )
  {
    putBit16z(v1, *(_DWORD *)(a1 + 156) & 1, 1);
    v13 = 1;
    v11 = v12;
  }
  else
  {
    v13 = 0;
  }
  putBit16z(v1, v13, v11);
  if ( *(_DWORD *)(a1 + 216) || (v14 = 0, *(_DWORD *)(a1 + 16604)) )
    v14 = 1;
  putBit16z(v1, v14, 1);
  putBit16z(v1, *(_DWORD *)(a1 + 168) & 1, v15);
  putBit16z(v1, *(_DWORD *)(a1 + 124) & 7, v12);
  putBit16z(v1, *(_DWORD *)(a1 + 34228) & 1, 1);
  putBit16z(v1, v12 & *(_DWORD *)(a1 + 152), 2);
  putBit16z(v1, v3, 1);
  putBit16z(v1, 1, v16);
  putBit16z(v1, v8, v17);
  putBit16z(v1, *(_DWORD *)(a1 + 34232) & 1, v18);
  putBit16z(v1, 0, 2);
  if ( !*(_DWORD *)(a1 + 34220) || (v19 = 1, !*(_DWORD *)(a1 + 56)) )
    v19 = 0;
  putBit16z(v1, v19, 1);
  putBit16z(v1, *(_DWORD *)(a1 + 34220) & 1, v20);
  putBit16z(v1, v21 & *(_DWORD *)(a1 + 24), 4);
  v23 = *(_DWORD *)(a1 + 28);
  if ( v23 || !*(_DWORD *)(a1 + 32996) )
    v22 &= v23;
  putBit16z(v1, v22, 4);
  v24 = v3 ^ 1;
  putBit32(v1, (unsigned int)(*(_DWORD *)(a1 + 8) - 1), (unsigned int)(16 * (v24 + 1)));
  putBit32(v1, (unsigned int)(*(_DWORD *)(a1 + 16) - 1), (unsigned int)(16 * (v24 + 1)));
  v25 = *(_DWORD *)(a1 + 216);
  v26 = (unsigned int *)(a1 + 16604);
  if ( v25 || *v26 )
  {
    putBit16z(v1, v25 & 0xFFF, 12);
    putBit16z(v1, v27 & *v26, v28);
  }
  v29 = 0;
  if ( *(_DWORD *)(a1 + 216) )
  {
    v30 = (unsigned int)(8 * v24 + 8);
    do
    {
      putBit16z(
        v1,
        ~(-1 << (8 * v24 + 8))
      & (unsigned int)(*(_DWORD *)(a1 + 4LL * (unsigned int)(v29 + 1) + 220) - *(_DWORD *)(a1 + 4 * v29 + 220)),
        v30);
      v29 = v31;
    }
    while ( v31 < *(_DWORD *)(a1 + 216) );
    v26 = (unsigned int *)(a1 + 16604);
  }
  v32 = 0;
  if ( *v26 )
  {
    v33 = (unsigned int)(8 * v24 + 8);
    do
    {
      putBit16z(
        v1,
        ~(-1 << (8 * v24 + 8))
      & (unsigned int)(*(_DWORD *)(a1 + 4LL * (unsigned int)(v32 + 1) + 16608) - *(_DWORD *)(a1 + 4 * v32 + 16608)),
        v33);
      v32 = v34;
    }
    while ( v34 < *v26 );
  }
  if ( v8 )
  {
    putBit16z(v1, *(_DWORD *)(a1 + 34248) & 0x3F, 6);
    putBit16z(v1, *(_DWORD *)(a1 + 34256) & 0x3F, v35);
    putBit16z(v1, *(_DWORD *)(a1 + 34264) & 0x3F, v36);
    putBit16z(v1, *(_DWORD *)(a1 + 34272) & 0x3F, v37);
  }
  putBit16z(v1, 0, -*(_DWORD *)(v1 + 8) & 7);
  return WriteImagePlaneHeader(a1);
}

```

## disassembly

```asm
0x1800033cc  push    rbx
0x1800033ce  push    rbp
0x1800033cf  push    rsi
0x1800033d0  push    rdi
0x1800033d1  push    r12
0x1800033d3  push    r14
0x1800033d5  push    r15
0x1800033d7  sub     rsp, 20h
0x1800033db  mov     rax, [rcx+8]
0x1800033df  mov     r11d, 0Fh
0x1800033e5  mov     rsi, [rcx+8640h]
0x1800033ec  add     rax, r11
0x1800033ef  mov     rdi, rcx
0x1800033f2  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800033f6  xor     r12d, r12d
0x1800033f9  mov     ecx, 0FF0h
0x1800033fe  lea     ebp, [r11-0Eh]
0x180003402  cmp     rax, rcx
0x180003405  ja      short loc_18000341A
0x180003407  mov     rax, [rdi+10h]
0x18000340b  mov     r14d, ebp
0x18000340e  add     rax, r11
0x180003411  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003415  cmp     rax, rcx
0x180003418  jbe     short loc_18000341D
0x18000341a  mov     r14d, r12d
0x18000341d  lea     rdx, [rdi+85D8h]
0x180003424  lea     r8, [rdi+85E0h]
0x18000342b  lea     rcx, [rdi+85D0h]
0x180003432  lea     rax, [rdi+85C8h]
0x180003439  cmp     [rdi+85E8h], r12d
0x180003440  jnz     short loc_18000344E
0x180003442  mov     [rdx], r12
0x180003445  mov     [r8], r12
0x180003448  mov     [rcx], r12
0x18000344b  mov     [rax], r12
0x18000344e  cmp     [rax], r12
0x180003451  jnz     short loc_180003465
0x180003453  cmp     [rcx], r12
0x180003456  jnz     short loc_180003465
0x180003458  cmp     [rdx], r12
0x18000345b  jnz     short loc_180003465
0x18000345d  mov     r15d, r12d
0x180003460  cmp     [r8], r12
0x180003463  jz      short loc_180003468
0x180003465  mov     r15d, ebp
0x180003468  mov     rbx, r12
0x18000346b  mov     rcx, [rdi+8640h]
0x180003472  lea     rax, gGDISignature; "WMPHOTO"
0x180003479  movsx   eax, byte ptr [rbx+rax]
0x18000347d  mov     r8d, 8
0x180003483  movzx   edx, al
0x180003486  call    putBit16z
0x18000348b  add     rbx, rbp
0x18000348e  cmp     rbx, r8
0x180003491  jnz     short loc_18000346B
0x180003493  mov     r8d, 4
0x180003499  mov     edx, ebp
0x18000349b  mov     rcx, rsi
0x18000349e  call    putBit16z
0x1800034a3  lea     ebx, [r8-1]
0x1800034a7  cmp     [rdi+0A0h], r12d
0x1800034ae  jnz     short loc_1800034B5
0x1800034b0  mov     edx, r12d
0x1800034b3  jmp     short loc_1800034CD
0x1800034b5  mov     edx, [rdi+9Ch]
0x1800034bb  mov     r8d, ebp
0x1800034be  and     edx, ebp
0x1800034c0  mov     rcx, rsi
0x1800034c3  call    putBit16z
0x1800034c8  mov     edx, ebp
0x1800034ca  mov     r8d, ebx
0x1800034cd  mov     rcx, rsi
0x1800034d0  call    putBit16z
0x1800034d5  cmp     [rdi+0D8h], r12d
0x1800034dc  jnz     short loc_1800034EA
0x1800034de  mov     edx, r12d
0x1800034e1  cmp     [rdi+40DCh], r12d
0x1800034e8  jz      short loc_1800034EC
0x1800034ea  mov     edx, ebp
0x1800034ec  mov     r8d, ebp
0x1800034ef  mov     rcx, rsi
0x1800034f2  call    putBit16z
0x1800034f7  mov     edx, [rdi+0A8h]
0x1800034fd  mov     rcx, rsi
0x180003500  and     edx, ebp
0x180003502  call    putBit16z
0x180003507  mov     edx, [rdi+7Ch]
0x18000350a  mov     r8d, ebx
0x18000350d  and     edx, 7
0x180003510  mov     rcx, rsi
0x180003513  call    putBit16z
0x180003518  mov     edx, [rdi+85B4h]
0x18000351e  mov     r8d, ebp
0x180003521  and     edx, ebp
0x180003523  mov     rcx, rsi
0x180003526  call    putBit16z
0x18000352b  mov     edx, [rdi+98h]
0x180003531  mov     rcx, rsi
0x180003534  and     edx, ebx
0x180003536  mov     ebx, 2
0x18000353b  mov     r8d, ebx
0x18000353e  call    putBit16z
0x180003543  mov     edx, r14d
0x180003546  mov     rcx, rsi
0x180003549  mov     r8d, ebp
0x18000354c  call    putBit16z
0x180003551  mov     edx, ebp
0x180003553  mov     rcx, rsi
0x180003556  call    putBit16z
0x18000355b  mov     edx, r15d
0x18000355e  mov     rcx, rsi
0x180003561  call    putBit16z
0x180003566  mov     edx, [rdi+85B8h]
0x18000356c  mov     rcx, rsi
0x18000356f  and     edx, ebp
0x180003571  call    putBit16z
0x180003576  xor     edx, edx
0x180003578  mov     rcx, rsi
0x18000357b  mov     r8d, ebx
0x18000357e  call    putBit16z
0x180003583  cmp     [rdi+85ACh], r12d
0x18000358a  jz      short loc_180003594
0x18000358c  mov     edx, ebp
0x18000358e  cmp     [rdi+38h], r12d
0x180003592  jnz     short loc_180003597
0x180003594  mov     edx, r12d
0x180003597  mov     r8d, ebp
0x18000359a  mov     rcx, rsi
0x18000359d  call    putBit16z
0x1800035a2  mov     edx, [rdi+85ACh]
0x1800035a8  mov     rcx, rsi
0x1800035ab  and     edx, ebp
0x1800035ad  call    putBit16z
0x1800035b2  mov     edx, [rdi+18h]
0x1800035b5  mov     r8d, 4
0x1800035bb  and     edx, r11d
0x1800035be  mov     rcx, rsi
0x1800035c1  call    putBit16z
0x1800035c6  mov     r8d, [rdi+1Ch]
0x1800035ca  test    r8d, r8d
0x1800035cd  jnz     short loc_1800035D8
0x1800035cf  cmp     [rdi+80E4h], r12d
0x1800035d6  jnz     short loc_1800035DB
0x1800035d8  and     r11d, r8d
0x1800035db  mov     r8d, 4
0x1800035e1  mov     edx, r11d
0x1800035e4  mov     rcx, rsi
0x1800035e7  call    putBit16z
0x1800035ec  mov     edx, [rdi+8]
0x1800035ef  xor     r14d, ebp
0x1800035f2  sub     edx, ebp
0x1800035f4  mov     rcx, rsi
0x1800035f7  lea     ebx, [r14+1]
0x1800035fb  shl     ebx, 4
0x1800035fe  mov     r8d, ebx
0x180003601  call    putBit32
0x180003606  mov     edx, [rdi+10h]
0x180003609  mov     r8d, ebx
0x18000360c  sub     edx, ebp
0x18000360e  mov     rcx, rsi
0x180003611  call    putBit32
0x180003616  mov     edx, [rdi+0D8h]
0x18000361c  lea     rbx, [rdi+40DCh]
0x180003623  test    edx, edx
0x180003625  jnz     short loc_18000362C
0x180003627  cmp     [rbx], r12d
0x18000362a  jz      short loc_180003650
0x18000362c  mov     r11d, 0FFFh
0x180003632  mov     r8d, 0Ch
0x180003638  and     edx, r11d
0x18000363b  mov     rcx, rsi
0x18000363e  call    putBit16z
0x180003643  mov     edx, [rbx]
0x180003645  mov     rcx, rsi
0x180003648  and     edx, r11d
0x18000364b  call    putBit16z
0x180003650  or      ebp, 0FFFFFFFFh
0x180003653  mov     eax, r12d
0x180003656  cmp     [rdi+0D8h], r12d
0x18000365d  jbe     short loc_1800036A0
0x18000365f  lea     r8d, ds:8[r14*8]
0x180003667  mov     ebx, ebp
0x180003669  mov     ecx, r8d
0x18000366c  shl     ebx, cl
0x18000366e  not     ebx
0x180003670  lea     r11d, [rax+1]
0x180003674  mov     rcx, rsi
0x180003677  mov     edx, [rdi+r11*4+0DCh]
0x18000367f  sub     edx, [rdi+rax*4+0DCh]
0x180003686  and     edx, ebx
0x180003688  call    putBit16z
0x18000368d  mov     eax, r11d
0x180003690  cmp     r11d, [rdi+0D8h]
0x180003697  jb      short loc_180003670
0x180003699  lea     rbx, [rdi+40DCh]
0x1800036a0  mov     eax, r12d
0x1800036a3  cmp     [rbx], r12d
0x1800036a6  jbe     short loc_1800036DC
0x1800036a8  lea     r8d, ds:8[r14*8]
0x1800036b0  mov     ecx, r8d
0x1800036b3  shl     ebp, cl
0x1800036b5  not     ebp
0x1800036b7  lea     r11d, [rax+1]
0x1800036bb  mov     rcx, rsi
0x1800036be  mov     edx, [rdi+r11*4+40E0h]
0x1800036c6  sub     edx, [rdi+rax*4+40E0h]
0x1800036cd  and     edx, ebp
0x1800036cf  call    putBit16z
0x1800036d4  mov     eax, r11d
0x1800036d7  cmp     r11d, [rbx]
0x1800036da  jb      short loc_1800036B7
0x1800036dc  test    r15d, r15d
0x1800036df  jz      short loc_18000372B
0x1800036e1  mov     edx, [rdi+85C8h]
0x1800036e7  mov     r8d, 6
0x1800036ed  and     edx, 3Fh
0x1800036f0  mov     rcx, rsi
0x1800036f3  call    putBit16z
0x1800036f8  mov     edx, [rdi+85D0h]
0x1800036fe  mov     rcx, rsi
0x180003701  and     edx, 3Fh
0x180003704  call    putBit16z
0x180003709  mov     edx, [rdi+85D8h]
0x18000370f  mov     rcx, rsi
0x180003712  and     edx, 3Fh
0x180003715  call    putBit16z
0x18000371a  mov     edx, [rdi+85E0h]
0x180003720  mov     rcx, rsi
0x180003723  and     edx, 3Fh
0x180003726  call    putBit16z
0x18000372b  mov     r8d, [rsi+8]
0x18000372f  xor     edx, edx
0x180003731  neg     r8d
0x180003734  mov     rcx, rsi
0x180003737  and     r8d, 7
0x18000373b  call    putBit16z
0x180003740  mov     rcx, rdi
0x180003743  add     rsp, 20h
0x180003747  pop     r15
0x180003749  pop     r14
0x18000374b  pop     r12
0x18000374d  pop     rdi
0x18000374e  pop     rsi
0x18000374f  pop     rbp
0x180003750  pop     rbx
0x180003751  jmp     WriteImagePlaneHeader
```
