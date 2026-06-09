# strIDCT4x4Stage2

- ea: `0x18001c0e8`
- end: `0x18001c3a9`
- name: `strIDCT4x4Stage2`
- size: `705`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f244`
- `0x180019da0`
- `0x18001cb70`
- `0x1800263c0`

## pseudocode

```c
__int64 __fastcall strIDCT4x4Stage2(_DWORD *a1)
{
  int v1; // r11d
  _DWORD *v2; // rsi
  int v3; // edx
  int v4; // r10d
  int v5; // r11d
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  int v10; // r12d
  int v11; // r9d
  int v12; // ecx
  int v13; // ebx
  int v14; // r11d
  int v15; // edx
  int v16; // ecx
  int v17; // r9d
  int v18; // r13d
  int v19; // r14d
  int v20; // ecx
  int v21; // ecx
  int v22; // edi
  int v23; // r10d
  int v24; // r11d
  int v25; // eax
  int v26; // ecx
  int v27; // ebp
  int v28; // ebx
  int v29; // ecx
  int v30; // edx
  int v31; // r10d
  int v32; // ebx
  int v33; // r15d
  int v34; // edi
  int v35; // r11d
  int v36; // r11d
  int v37; // r9d
  int v38; // edx
  int v39; // ecx
  int v40; // r8d
  int v41; // ecx
  int v42; // r13d
  int v43; // ecx
  int v44; // edx
  int v45; // ecx
  int v46; // ecx
  int v47; // edx
  int v48; // eax
  int v49; // ecx
  int v50; // ecx
  int v51; // edx
  int v52; // ecx
  __int64 result; // rax
  int v54; // [rsp+0h] [rbp-58h]
  int v55; // [rsp+4h] [rbp-54h]
  int v57; // [rsp+68h] [rbp+10h]
  int v58; // [rsp+70h] [rbp+18h]
  int v59; // [rsp+78h] [rbp+20h]

  v1 = a1[112];
  v2 = a1;
  v3 = v1 + a1[48];
  v4 = a1[96];
  v5 = v1 - (v3 >> 1);
  v6 = a1[32] - v4 - ((v3 + 2 * (v3 + 2)) >> 3);
  v7 = a1[144];
  v8 = v3 + ((v6 + 2 * (v6 + 2)) >> 3);
  v9 = ((a1[32] - v4 + 1) >> 1) - ((v5 + 2 * (v5 + 2)) >> 3) + v4;
  v55 = v9 - ((v8 + 1) >> 1);
  v10 = v55 + v8;
  v11 = v2[208];
  v12 = ((v6 + 1) >> 1) - ((v9 + 2 * (v9 + 2)) >> 3) - v5;
  v13 = v6 - v12;
  v14 = v2[160];
  v15 = v2[128] - v7;
  v59 = v12;
  v16 = v11 + v2[192];
  v54 = v13;
  v17 = v11 - (v16 >> 1);
  v18 = v15 - ((v16 + 2 * (v16 + 2)) >> 3);
  v19 = v16 + ((v18 + 2 * v18 + 4) >> 3);
  v20 = ((v15 + 1) >> 1) - ((v17 + 2 * (v17 + 2)) >> 3) + v7;
  v57 = v20 - ((v19 + 1) >> 1);
  v58 = ((v18 + 1) >> 1) - ((v20 + 2 * (v20 + 2)) >> 3) - v17;
  v21 = v2[224];
  v22 = v14 + v2[240];
  v23 = v2[176] - v21;
  v24 = v14 - ((3 * ((v23 >> 1) + v21 + 1)) >> 3) - (v22 >> 1);
  v25 = (v23 >> 1) + v21 + ((3 * (v24 + 1)) >> 2);
  v26 = v21 + ((3 * (v24 + 1)) >> 2);
  v27 = -v26;
  v28 = v26 + v23;
  v29 = v2[80];
  v30 = v29 + *v2;
  v31 = v2[64] - v2[16];
  v32 = -v28;
  v33 = v24 - ((3 * v25 + 4) >> 3) + (v22 >> 1);
  v34 = v22 - v33;
  v35 = (v30 - v31 + 1) >> 1;
  LODWORD(v2) = v35 - a1[16];
  v36 = v35 - v29;
  v37 = v30 - (_DWORD)v2 + v34;
  v38 = v19 + v57 - v10;
  v39 = (v37 - v38) >> 1;
  v40 = v39 - v10;
  v41 = v39 - v34;
  *a1 = v37 - v40;
  v42 = v18 - v58 - v59;
  a1[192] = v41 + v38;
  a1[48] = v41;
  a1[240] = v40;
  v43 = (v32 + v36 + v31 - v42) >> 1;
  v44 = v43 - v59;
  v45 = v43 - v32;
  a1[64] = v32 + v36 + v31 - v44;
  a1[128] = v45 + v42;
  a1[112] = v45;
  a1[176] = v44;
  v46 = (v36 + v27 - (v58 - v54)) >> 1;
  v47 = v46 - v54;
  v48 = v36 + v27 - (v46 - v54);
  v49 = v46 - v27;
  a1[16] = v48;
  a1[208] = v49 + v58 - v54;
  a1[32] = v49;
  a1[224] = v47;
  v50 = ((int)v2 + v33 - (v57 - v55)) >> 1;
  v51 = v50 - v55;
  v52 = v50 - v33;
  a1[80] = (_DWORD)v2 + v33 - v51;
  result = (unsigned int)(v52 + v57 - v55);
  a1[144] = result;
  a1[96] = v52;
  a1[160] = v51;
  return result;
}

```

## disassembly

```asm
0x18001c0e8  mov     [rsp+arg_0], rcx
0x18001c0ed  push    rbx
0x18001c0ee  push    rbp
0x18001c0ef  push    rsi
0x18001c0f0  push    rdi
0x18001c0f1  push    r12
0x18001c0f3  push    r13
0x18001c0f5  push    r14
0x18001c0f7  push    r15
0x18001c0f9  sub     rsp, 18h
0x18001c0fd  mov     r11d, [rcx+1C0h]
0x18001c104  mov     rsi, rcx
0x18001c107  mov     edx, [rcx+0C0h]
0x18001c10d  mov     r8d, [rcx+80h]
0x18001c114  add     edx, r11d
0x18001c117  mov     r10d, [rcx+180h]
0x18001c11e  mov     eax, edx
0x18001c120  sar     eax, 1
0x18001c122  sub     r8d, r10d
0x18001c125  sub     r11d, eax
0x18001c128  mov     ebx, r8d
0x18001c12b  lea     eax, [rdx+2]
0x18001c12e  lea     eax, [rdx+rax*2]
0x18001c131  sar     eax, 3
0x18001c134  sub     ebx, eax
0x18001c136  lea     ecx, [r11+2]
0x18001c13a  lea     ecx, [r11+rcx*2]
0x18001c13e  sar     ecx, 3
0x18001c141  lea     eax, [r8+1]
0x18001c145  mov     r8d, [rsi+240h]
0x18001c14c  sar     eax, 1
0x18001c14e  lea     r9d, [rbx+2]
0x18001c152  sub     eax, ecx
0x18001c154  lea     r9d, [rbx+r9*2]
0x18001c158  sar     r9d, 3
0x18001c15c  add     r9d, edx
0x18001c15f  lea     ecx, [rax+r10]
0x18001c163  mov     edx, ecx
0x18001c165  lea     eax, [r9+1]
0x18001c169  sar     eax, 1
0x18001c16b  sub     edx, eax
0x18001c16d  lea     eax, [rcx+2]
0x18001c170  lea     eax, [rcx+rax*2]
0x18001c173  mov     [rsp+58h+var_54], edx
0x18001c177  sar     eax, 3
0x18001c17a  lea     ecx, [rbx+1]
0x18001c17d  sar     ecx, 1
0x18001c17f  sub     ecx, eax
0x18001c181  lea     r12d, [rdx+r9]
0x18001c185  mov     r9d, [rsi+340h]
0x18001c18c  sub     ecx, r11d
0x18001c18f  mov     edx, [rsi+200h]
0x18001c195  sub     ebx, ecx
0x18001c197  mov     r11d, [rsi+280h]
0x18001c19e  sub     edx, r8d
0x18001c1a1  mov     [rsp+58h+arg_18], ecx
0x18001c1a5  mov     r13d, edx
0x18001c1a8  mov     ecx, [rsi+300h]
0x18001c1ae  add     ecx, r9d
0x18001c1b1  mov     [rsp+58h+var_58], ebx
0x18001c1b4  mov     eax, ecx
0x18001c1b6  sar     eax, 1
0x18001c1b8  sub     r9d, eax
0x18001c1bb  lea     eax, [rcx+2]
0x18001c1be  lea     eax, [rcx+rax*2]
0x18001c1c1  sar     eax, 3
0x18001c1c4  sub     r13d, eax
0x18001c1c7  lea     eax, [rdx+1]
0x18001c1ca  sar     eax, 1
0x18001c1cc  lea     r14d, ds:4[r13*2]
0x18001c1d4  add     r14d, r13d
0x18001c1d7  sar     r14d, 3
0x18001c1db  add     r14d, ecx
0x18001c1de  lea     ecx, [r9+2]
0x18001c1e2  lea     ecx, [r9+rcx*2]
0x18001c1e6  sar     ecx, 3
0x18001c1e9  sub     eax, ecx
0x18001c1eb  lea     ecx, [rax+r8]
0x18001c1ef  mov     edx, ecx
0x18001c1f1  lea     eax, [r14+1]
0x18001c1f5  sar     eax, 1
0x18001c1f7  sub     edx, eax
0x18001c1f9  lea     eax, [rcx+2]
0x18001c1fc  lea     eax, [rcx+rax*2]
0x18001c1ff  mov     [rsp+58h+arg_8], edx
0x18001c203  sar     eax, 3
0x18001c206  lea     ecx, [r13+1]
0x18001c20a  sar     ecx, 1
0x18001c20c  sub     ecx, eax
0x18001c20e  sub     ecx, r9d
0x18001c211  mov     [rsp+58h+arg_10], ecx
0x18001c215  mov     ecx, [rsi+380h]
0x18001c21b  mov     edi, [rsi+3C0h]
0x18001c221  mov     r10d, [rsi+2C0h]
0x18001c228  add     edi, r11d
0x18001c22b  sub     r10d, ecx
0x18001c22e  mov     r9d, edi
0x18001c231  sar     r9d, 1
0x18001c234  mov     r8d, r10d
0x18001c237  sar     r8d, 1
0x18001c23a  lea     edx, [r8+rcx]
0x18001c23e  lea     eax, [rdx+1]
0x18001c241  lea     ecx, [rax+rax*2]
0x18001c244  sar     ecx, 3
0x18001c247  sub     r11d, ecx
0x18001c24a  sub     r11d, r9d
0x18001c24d  lea     eax, [r11+1]
0x18001c251  lea     eax, [rax+rax*2]
0x18001c254  sar     eax, 2
0x18001c257  add     eax, edx
0x18001c259  mov     edx, [rsi]
0x18001c25b  mov     ecx, eax
0x18001c25d  sub     ecx, r8d
0x18001c260  mov     ebp, ecx
0x18001c262  lea     eax, [rax+rax*2]
0x18001c265  neg     ebp
0x18001c267  add     eax, 4
0x18001c26a  lea     ebx, [rcx+r10]
0x18001c26e  sar     eax, 3
0x18001c271  mov     ecx, [rsi+140h]
0x18001c277  sub     r11d, eax
0x18001c27a  mov     r10d, [rsi+100h]
0x18001c281  add     edx, ecx
0x18001c283  sub     r10d, [rsi+40h]
0x18001c287  neg     ebx
0x18001c289  mov     rax, [rsp+58h+arg_0]
0x18001c28e  mov     esi, edx
0x18001c290  lea     r15d, [r11+r9]
0x18001c294  sub     esi, r10d
0x18001c297  sub     edi, r15d
0x18001c29a  inc     esi
0x18001c29c  sar     esi, 1
0x18001c29e  mov     r11d, esi
0x18001c2a1  sub     esi, [rax+40h]
0x18001c2a4  sub     edx, esi
0x18001c2a6  sub     r11d, ecx
0x18001c2a9  lea     r9d, [rdx+rdi]
0x18001c2ad  mov     edx, [rsp+58h+arg_8]
0x18001c2b1  sub     edx, r12d
0x18001c2b4  mov     r8d, r9d
0x18001c2b7  add     edx, r14d
0x18001c2ba  sub     r8d, edx
0x18001c2bd  sar     r8d, 1
0x18001c2c0  mov     ecx, r8d
0x18001c2c3  sub     r8d, r12d
0x18001c2c6  sub     ecx, edi
0x18001c2c8  sub     r9d, r8d
0x18001c2cb  mov     [rax], r9d
0x18001c2ce  mov     rdi, rax
0x18001c2d1  mov     r9d, [rsp+58h+arg_10]
0x18001c2d6  sub     r13d, r9d
0x18001c2d9  sub     r13d, [rsp+58h+arg_18]
0x18001c2de  lea     eax, [rcx+rdx]
0x18001c2e1  mov     [rdi+300h], eax
0x18001c2e7  mov     [rdi+0C0h], ecx
0x18001c2ed  mov     [rdi+3C0h], r8d
0x18001c2f4  lea     r8d, [r11+r10]
0x18001c2f8  add     r8d, ebx
0x18001c2fb  mov     edx, r8d
0x18001c2fe  sub     edx, r13d
0x18001c301  sar     edx, 1
0x18001c303  mov     ecx, edx
0x18001c305  sub     edx, [rsp+58h+arg_18]
0x18001c309  sub     ecx, ebx
0x18001c30b  sub     r8d, edx
0x18001c30e  sub     r9d, [rsp+58h+var_58]
0x18001c312  mov     [rdi+100h], r8d
0x18001c319  lea     eax, [rcx+r13]
0x18001c31d  mov     [rdi+200h], eax
0x18001c323  lea     eax, [r11+rbp]
0x18001c327  mov     [rdi+1C0h], ecx
0x18001c32d  mov     [rdi+2C0h], edx
0x18001c333  mov     r8d, [rsp+58h+arg_8]
0x18001c338  mov     edx, eax
0x18001c33a  sub     r8d, [rsp+58h+var_54]
0x18001c33f  sub     edx, r9d
0x18001c342  sar     edx, 1
0x18001c344  mov     ecx, edx
0x18001c346  sub     edx, [rsp+58h+var_58]
0x18001c349  sub     eax, edx
0x18001c34b  sub     ecx, ebp
0x18001c34d  mov     [rdi+40h], eax
0x18001c350  lea     eax, [rcx+r9]
0x18001c354  mov     [rdi+340h], eax
0x18001c35a  lea     eax, [rsi+r15]
0x18001c35e  mov     [rdi+80h], ecx
0x18001c364  mov     [rdi+380h], edx
0x18001c36a  mov     edx, eax
0x18001c36c  sub     edx, r8d
0x18001c36f  sar     edx, 1
0x18001c371  mov     ecx, edx
0x18001c373  sub     edx, [rsp+58h+var_54]
0x18001c377  sub     ecx, r15d
0x18001c37a  sub     eax, edx
0x18001c37c  mov     [rdi+140h], eax
0x18001c382  lea     eax, [rcx+r8]
0x18001c386  mov     [rdi+240h], eax
0x18001c38c  mov     [rdi+180h], ecx
0x18001c392  mov     [rdi+280h], edx
0x18001c398  add     rsp, 18h
0x18001c39c  pop     r15
0x18001c39e  pop     r14
0x18001c3a0  pop     r13
0x18001c3a2  pop     r12
0x18001c3a4  pop     rdi
0x18001c3a5  pop     rsi
0x18001c3a6  pop     rbp
0x18001c3a7  pop     rbx
0x18001c3a8  retn
```
