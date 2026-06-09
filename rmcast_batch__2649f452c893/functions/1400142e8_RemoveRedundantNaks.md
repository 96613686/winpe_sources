# RemoveRedundantNaks

- ea: `0x1400142e8`
- end: `0x140014530`
- name: `RemoveRedundantNaks`
- size: `584`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e03c`
- `0x14000f2d8`
- `0x140012efc`

## callees

- `0x1400090f8`
- `0x14000ef98`
- `0x1400142e8`

## pseudocode

```c
void __fastcall RemoveRedundantNaks(__int64 a1, _BYTE *a2, char a3)
{
  unsigned __int8 v4; // di
  unsigned __int8 v6; // cl
  unsigned __int8 v8; // si
  __int64 v9; // rax
  char v10; // r15
  _BYTE *v11; // r14
  char v12; // r8
  int v13; // r10d
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int8 v16; // si
  _BYTE *v17; // rbp
  __int64 v18; // rcx
  unsigned __int8 v19; // dl
  unsigned __int8 i; // r8
  __int64 v21; // rax
  unsigned __int8 j; // r8
  __int64 v23; // rax
  int v24; // edx
  unsigned int v25; // ecx

  v4 = a2[59] + a2[58];
  v6 = a2[62];
  if ( a2[57] < v6 )
  {
    if ( v6 )
    {
      v8 = 0;
      do
      {
        v9 = (unsigned __int8)a2[40 * v8 + 116];
        if ( (unsigned __int8)v9 < a2[57] || (unsigned __int8)v9 >= v6 || a2[40 * v9 + 117] == v6 )
        {
          ++v8;
        }
        else
        {
          v10 = a2[40 * v8 + 117];
          v11 = &a2[40 * v8];
          a2[40 * v9 + 117] = v6;
          FreeDataBuffer(a1, (__int64)(v11 + 96));
          v12 = a2[62];
          v13 = v4 - 1;
          if ( v8 != v13 )
          {
            v12 = a2[40 * v4 + 77];
            *((_OWORD *)v11 + 6) = *(_OWORD *)&a2[40 * v4 + 56];
            *((_OWORD *)v11 + 7) = *(_OWORD *)&a2[40 * v4 + 72];
            *((_QWORD *)v11 + 16) = *(_QWORD *)&a2[40 * v4 + 88];
          }
          v14 = 5LL * v4;
          *(_OWORD *)&a2[8 * v14 + 56] = 0;
          *(_OWORD *)&a2[8 * v14 + 72] = 0;
          *(_QWORD *)&a2[8 * v14 + 88] = 0;
          a2[40 * v8 + 117] = v10;
          if ( v8 != v13 )
          {
            a2[40 * v4 + 77] = v12;
            v15 = (unsigned __int8)a2[40 * v8 + 116];
            if ( (unsigned __int8)v15 < a2[62] )
              a2[40 * v15 + 117] = v8;
          }
          --a2[58];
          --v4;
        }
        v6 = a2[62];
      }
      while ( v8 < v6 );
    }
    if ( a3 )
    {
      v16 = 0;
      while ( v16 < v4 )
      {
        if ( v4 <= a2[57] )
          break;
        if ( a2[40 * v16 + 116] >= a2[62] )
        {
          v17 = &a2[40 * v16];
          FreeDataBuffer(a1, (__int64)(v17 + 96));
          if ( v16 != v4 - 1 )
          {
            *((_OWORD *)v17 + 6) = *(_OWORD *)&a2[40 * v4 + 56];
            *((_OWORD *)v17 + 7) = *(_OWORD *)&a2[40 * v4 + 72];
            *((_QWORD *)v17 + 16) = *(_QWORD *)&a2[40 * v4 + 88];
          }
          v18 = 5LL * v4;
          *(_OWORD *)&a2[8 * v18 + 56] = 0;
          *(_OWORD *)&a2[8 * v18 + 72] = 0;
          *(_QWORD *)&a2[8 * v18 + 88] = 0;
          --a2[59];
          --v4;
        }
        else
        {
          ++v16;
        }
      }
    }
  }
  v19 = a2[62];
  if ( v19 )
  {
    for ( i = 0; i < v19; ++i )
    {
      v21 = i;
      a2[40 * v21 + 117] = v19;
      v19 = a2[62];
    }
  }
  if ( v4 )
  {
    for ( j = 0; j < v4; ++j )
    {
      v23 = (unsigned __int8)a2[40 * j + 116];
      if ( (unsigned __int8)v23 < v19 )
      {
        a2[40 * v23 + 117] = j;
        v19 = a2[62];
      }
    }
  }
  if ( a3 )
  {
    v24 = (unsigned __int8)a2[58];
    v25 = (unsigned __int8)a2[57];
    if ( v24 + (unsigned int)(unsigned __int8)a2[59] >= v25 || v24 + (unsigned int)(unsigned __int8)a2[63] >= v25 )
      RemovePendingReceiverEntry(a2);
  }
}

```

## disassembly

```asm
0x1400142e8  push    rbx
0x1400142ea  push    rbp
0x1400142eb  push    rsi
0x1400142ec  push    rdi
0x1400142ed  push    r12
0x1400142ef  push    r13
0x1400142f1  push    r14
0x1400142f3  push    r15
0x1400142f5  sub     rsp, 28h
0x1400142f9  mov     dil, [rdx+3Ah]
0x1400142fd  mov     r13, rcx
0x140014300  add     dil, [rdx+3Bh]
0x140014304  mov     r12b, r8b
0x140014307  mov     cl, [rdx+3Eh]
0x14001430a  mov     rbx, rdx
0x14001430d  cmp     [rdx+39h], cl
0x140014310  jnb     loc_1400144A7
0x140014316  test    cl, cl
0x140014318  jz      loc_140014403
0x14001431e  xor     sil, sil
0x140014321  movzx   eax, sil
0x140014325  lea     rbp, [rax+rax*4]
0x140014329  movzx   eax, byte ptr [rbx+rbp*8+74h]
0x14001432e  cmp     al, [rbx+39h]
0x140014331  jb      loc_1400143F4
0x140014337  cmp     al, cl
0x140014339  jnb     loc_1400143F4
0x14001433f  lea     rdx, [rax+rax*4]
0x140014343  cmp     [rbx+rdx*8+75h], cl
0x140014347  jz      loc_1400143F4
0x14001434d  mov     r15b, [rbx+rbp*8+75h]
0x140014352  lea     r14, [rbx+rbp*8]
0x140014356  mov     [rbx+rdx*8+75h], cl
0x14001435a  lea     rdx, [r14+60h]
0x14001435e  mov     rcx, r13
0x140014361  call    FreeDataBuffer
0x140014366  mov     r8b, [rbx+3Eh]
0x14001436a  movzx   eax, dil
0x14001436e  movzx   r9d, sil
0x140014372  mov     edx, eax
0x140014374  lea     r10d, [rax-1]
0x140014378  cmp     r9d, r10d
0x14001437b  jz      short loc_1400143A9
0x14001437d  lea     rax, [rax+rax*4]
0x140014381  movups  xmm0, xmmword ptr [rbx+rax*8+38h]
0x140014386  mov     r8b, [rbx+rax*8+4Dh]
0x14001438b  movups  xmmword ptr [r14+60h], xmm0
0x140014390  movups  xmm1, xmmword ptr [rbx+rax*8+48h]
0x140014395  movups  xmmword ptr [r14+70h], xmm1
0x14001439a  movsd   xmm0, qword ptr [rbx+rax*8+58h]
0x1400143a0  movsd   qword ptr [r14+80h], xmm0
0x1400143a9  movzx   eax, dil
0x1400143ad  xorps   xmm0, xmm0
0x1400143b0  lea     rcx, [rax+rax*4]
0x1400143b4  xor     eax, eax
0x1400143b6  movups  xmmword ptr [rbx+rcx*8+38h], xmm0
0x1400143bb  movups  xmmword ptr [rbx+rcx*8+48h], xmm0
0x1400143c0  mov     [rbx+rcx*8+58h], rax
0x1400143c5  mov     [rbx+rbp*8+75h], r15b
0x1400143ca  cmp     r9d, r10d
0x1400143cd  jz      short loc_1400143EB
0x1400143cf  lea     rax, [rdx+rdx*4]
0x1400143d3  mov     [rbx+rax*8+4Dh], r8b
0x1400143d8  movzx   eax, byte ptr [rbx+rbp*8+74h]
0x1400143dd  cmp     al, [rbx+3Eh]
0x1400143e0  jnb     short loc_1400143EB
0x1400143e2  lea     rcx, [rax+rax*4]
0x1400143e6  mov     [rbx+rcx*8+75h], sil
0x1400143eb  dec     byte ptr [rbx+3Ah]
0x1400143ee  add     dil, 0FFh
0x1400143f2  jmp     short loc_1400143F7
0x1400143f4  inc     sil
0x1400143f7  mov     cl, [rbx+3Eh]
0x1400143fa  cmp     sil, cl
0x1400143fd  jb      loc_140014321
0x140014403  test    r12b, r12b
0x140014406  jz      loc_1400144A7
0x14001440c  xor     sil, sil
0x14001440f  test    dil, dil
0x140014412  jz      loc_1400144A7
0x140014418  cmp     dil, [rbx+39h]
0x14001441c  jbe     loc_1400144A7
0x140014422  movzx   eax, sil
0x140014426  lea     rcx, [rax+rax*4]
0x14001442a  mov     al, [rbx+3Eh]
0x14001442d  cmp     [rbx+rcx*8+74h], al
0x140014431  jnb     short loc_140014438
0x140014433  inc     sil
0x140014436  jmp     short loc_14001449E
0x140014438  lea     rbp, [rbx+rcx*8]
0x14001443c  mov     rcx, r13
0x14001443f  lea     rdx, [rbp+60h]
0x140014443  call    FreeDataBuffer
0x140014448  movzx   edx, dil
0x14001444c  movzx   eax, sil
0x140014450  lea     ecx, [rdx-1]
0x140014453  cmp     eax, ecx
0x140014455  jz      short loc_14001447B
0x140014457  lea     rcx, [rdx+rdx*4]
0x14001445b  movups  xmm0, xmmword ptr [rbx+rcx*8+38h]
0x140014460  movups  xmmword ptr [rbp+60h], xmm0
0x140014464  movups  xmm1, xmmword ptr [rbx+rcx*8+48h]
0x140014469  movups  xmmword ptr [rbp+70h], xmm1
0x14001446d  movsd   xmm0, qword ptr [rbx+rcx*8+58h]
0x140014473  movsd   qword ptr [rbp+80h], xmm0
0x14001447b  movzx   eax, dil
0x14001447f  xorps   xmm0, xmm0
0x140014482  lea     rcx, [rax+rax*4]
0x140014486  xor     eax, eax
0x140014488  movups  xmmword ptr [rbx+rcx*8+38h], xmm0
0x14001448d  movups  xmmword ptr [rbx+rcx*8+48h], xmm0
0x140014492  mov     [rbx+rcx*8+58h], rax
0x140014497  dec     byte ptr [rbx+3Bh]
0x14001449a  add     dil, 0FFh
0x14001449e  cmp     sil, dil
0x1400144a1  jb      loc_140014418
0x1400144a7  mov     dl, [rbx+3Eh]
0x1400144aa  test    dl, dl
0x1400144ac  jz      short loc_1400144C8
0x1400144ae  xor     r8b, r8b
0x1400144b1  movzx   eax, r8b
0x1400144b5  inc     r8b
0x1400144b8  lea     rcx, [rax+rax*4]
0x1400144bc  mov     [rbx+rcx*8+75h], dl
0x1400144c0  mov     dl, [rbx+3Eh]
0x1400144c3  cmp     r8b, dl
0x1400144c6  jb      short loc_1400144B1
0x1400144c8  test    dil, dil
0x1400144cb  jz      short loc_1400144F5
0x1400144cd  xor     r8b, r8b
0x1400144d0  movzx   eax, r8b
0x1400144d4  lea     rcx, [rax+rax*4]
0x1400144d8  movzx   eax, byte ptr [rbx+rcx*8+74h]
0x1400144dd  cmp     al, dl
0x1400144df  jnb     short loc_1400144ED
0x1400144e1  lea     rcx, [rax+rax*4]
0x1400144e5  mov     [rbx+rcx*8+75h], r8b
0x1400144ea  mov     dl, [rbx+3Eh]
0x1400144ed  inc     r8b
0x1400144f0  cmp     r8b, dil
0x1400144f3  jb      short loc_1400144D0
0x1400144f5  test    r12b, r12b
0x1400144f8  jz      short loc_14001451E
0x1400144fa  movzx   edx, byte ptr [rbx+3Ah]
0x1400144fe  movzx   eax, byte ptr [rbx+3Bh]
0x140014502  movzx   ecx, byte ptr [rbx+39h]
0x140014506  add     eax, edx
0x140014508  cmp     eax, ecx
0x14001450a  jnb     short loc_140014516
0x14001450c  movzx   eax, byte ptr [rbx+3Fh]
0x140014510  add     eax, edx
0x140014512  cmp     eax, ecx
0x140014514  jb      short loc_14001451E
0x140014516  mov     rcx, rbx
0x140014519  call    RemovePendingReceiverEntry
0x14001451e  add     rsp, 28h
0x140014522  pop     r15
0x140014524  pop     r14
0x140014526  pop     r13
0x140014528  pop     r12
0x14001452a  pop     rdi
0x14001452b  pop     rsi
0x14001452c  pop     rbp
0x14001452d  pop     rbx
0x14001452e  retn
```
