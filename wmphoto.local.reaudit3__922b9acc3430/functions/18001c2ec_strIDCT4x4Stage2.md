# strIDCT4x4Stage2

- ea: `0x18001c2ec`
- end: `0x18001c5ae`
- name: `strIDCT4x4Stage2`
- size: `706`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f3b4`
- `0x180019fa0`
- `0x18001cd90`
- `0x180026620`

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
0x18001c2ec  mov     [rsp+arg_0], rcx
0x18001c2f1  push    rbx
0x18001c2f2  push    rbp
0x18001c2f3  push    rsi
0x18001c2f4  push    rdi
0x18001c2f5  push    r12
0x18001c2f7  push    r13
0x18001c2f9  push    r14
0x18001c2fb  push    r15
0x18001c2fd  sub     rsp, 18h
0x18001c301  mov     r11d, [rcx+1C0h]
0x18001c308  mov     rsi, rcx
0x18001c30b  mov     edx, [rcx+0C0h]
0x18001c311  mov     r8d, [rcx+80h]
0x18001c318  add     edx, r11d
0x18001c31b  mov     r10d, [rcx+180h]
0x18001c322  mov     eax, edx
0x18001c324  sar     eax, 1
0x18001c326  sub     r8d, r10d
0x18001c329  sub     r11d, eax
0x18001c32c  mov     ebx, r8d
0x18001c32f  lea     eax, [rdx+2]
0x18001c332  lea     eax, [rdx+rax*2]
0x18001c335  sar     eax, 3
0x18001c338  sub     ebx, eax
0x18001c33a  lea     ecx, [r11+2]
0x18001c33e  lea     ecx, [r11+rcx*2]
0x18001c342  sar     ecx, 3
0x18001c345  lea     eax, [r8+1]
0x18001c349  mov     r8d, [rsi+240h]
0x18001c350  sar     eax, 1
0x18001c352  lea     r9d, [rbx+2]
0x18001c356  sub     eax, ecx
0x18001c358  lea     r9d, [rbx+r9*2]
0x18001c35c  sar     r9d, 3
0x18001c360  add     r9d, edx
0x18001c363  lea     ecx, [rax+r10]
0x18001c367  mov     edx, ecx
0x18001c369  lea     eax, [r9+1]
0x18001c36d  sar     eax, 1
0x18001c36f  sub     edx, eax
0x18001c371  lea     eax, [rcx+2]
0x18001c374  lea     eax, [rcx+rax*2]
0x18001c377  mov     [rsp+58h+var_54], edx
0x18001c37b  sar     eax, 3
0x18001c37e  lea     ecx, [rbx+1]
0x18001c381  sar     ecx, 1
0x18001c383  sub     ecx, eax
0x18001c385  lea     r12d, [rdx+r9]
0x18001c389  mov     r9d, [rsi+340h]
0x18001c390  sub     ecx, r11d
0x18001c393  mov     edx, [rsi+200h]
0x18001c399  sub     ebx, ecx
0x18001c39b  mov     r11d, [rsi+280h]
0x18001c3a2  sub     edx, r8d
0x18001c3a5  mov     [rsp+58h+arg_18], ecx
0x18001c3a9  mov     r13d, edx
0x18001c3ac  mov     ecx, [rsi+300h]
0x18001c3b2  add     ecx, r9d
0x18001c3b5  mov     [rsp+58h+var_58], ebx
0x18001c3b8  mov     eax, ecx
0x18001c3ba  sar     eax, 1
0x18001c3bc  sub     r9d, eax
0x18001c3bf  lea     eax, [rcx+2]
0x18001c3c2  lea     eax, [rcx+rax*2]
0x18001c3c5  sar     eax, 3
0x18001c3c8  sub     r13d, eax
0x18001c3cb  lea     eax, [rdx+1]
0x18001c3ce  sar     eax, 1
0x18001c3d0  lea     r14d, ds:4[r13*2]
0x18001c3d8  add     r14d, r13d
0x18001c3db  sar     r14d, 3
0x18001c3df  add     r14d, ecx
0x18001c3e2  lea     ecx, [r9+2]
0x18001c3e6  lea     ecx, [r9+rcx*2]
0x18001c3ea  sar     ecx, 3
0x18001c3ed  sub     eax, ecx
0x18001c3ef  lea     ecx, [rax+r8]
0x18001c3f3  mov     edx, ecx
0x18001c3f5  lea     eax, [r14+1]
0x18001c3f9  sar     eax, 1
0x18001c3fb  sub     edx, eax
0x18001c3fd  lea     eax, [rcx+2]
0x18001c400  lea     eax, [rcx+rax*2]
0x18001c403  mov     [rsp+58h+arg_8], edx
0x18001c407  sar     eax, 3
0x18001c40a  lea     ecx, [r13+1]
0x18001c40e  sar     ecx, 1
0x18001c410  sub     ecx, eax
0x18001c412  sub     ecx, r9d
0x18001c415  mov     [rsp+58h+arg_10], ecx
0x18001c419  mov     ecx, [rsi+380h]
0x18001c41f  mov     edi, [rsi+3C0h]
0x18001c425  mov     r10d, [rsi+2C0h]
0x18001c42c  add     edi, r11d
0x18001c42f  sub     r10d, ecx
0x18001c432  mov     r9d, edi
0x18001c435  sar     r9d, 1
0x18001c438  mov     r8d, r10d
0x18001c43b  sar     r8d, 1
0x18001c43e  lea     edx, [r8+rcx]
0x18001c442  lea     eax, [rdx+1]
0x18001c445  lea     ecx, [rax+rax*2]
0x18001c448  sar     ecx, 3
0x18001c44b  sub     r11d, ecx
0x18001c44e  sub     r11d, r9d
0x18001c451  lea     eax, [r11+1]
0x18001c455  lea     eax, [rax+rax*2]
0x18001c458  sar     eax, 2
0x18001c45b  add     eax, edx
0x18001c45d  mov     edx, [rsi]
0x18001c45f  mov     ecx, eax
0x18001c461  sub     ecx, r8d
0x18001c464  mov     ebp, ecx
0x18001c466  lea     eax, [rax+rax*2]
0x18001c469  neg     ebp
0x18001c46b  add     eax, 4
0x18001c46e  lea     ebx, [rcx+r10]
0x18001c472  sar     eax, 3
0x18001c475  mov     ecx, [rsi+140h]
0x18001c47b  sub     r11d, eax
0x18001c47e  mov     r10d, [rsi+100h]
0x18001c485  add     edx, ecx
0x18001c487  sub     r10d, [rsi+40h]
0x18001c48b  neg     ebx
0x18001c48d  mov     rax, [rsp+58h+arg_0]
0x18001c492  mov     esi, edx
0x18001c494  lea     r15d, [r11+r9]
0x18001c498  sub     esi, r10d
0x18001c49b  sub     edi, r15d
0x18001c49e  inc     esi
0x18001c4a0  sar     esi, 1
0x18001c4a2  mov     r11d, esi
0x18001c4a5  sub     esi, [rax+40h]
0x18001c4a8  sub     edx, esi
0x18001c4aa  sub     r11d, ecx
0x18001c4ad  lea     r9d, [rdx+rdi]
0x18001c4b1  mov     edx, [rsp+58h+arg_8]
0x18001c4b5  sub     edx, r12d
0x18001c4b8  mov     r8d, r9d
0x18001c4bb  add     edx, r14d
0x18001c4be  sub     r8d, edx
0x18001c4c1  sar     r8d, 1
0x18001c4c4  mov     ecx, r8d
0x18001c4c7  sub     r8d, r12d
0x18001c4ca  sub     ecx, edi
0x18001c4cc  sub     r9d, r8d
0x18001c4cf  mov     [rax], r9d
0x18001c4d2  mov     rdi, rax
0x18001c4d5  mov     r9d, [rsp+58h+arg_10]
0x18001c4da  sub     r13d, r9d
0x18001c4dd  sub     r13d, [rsp+58h+arg_18]
0x18001c4e2  lea     eax, [rcx+rdx]
0x18001c4e5  mov     [rdi+300h], eax
0x18001c4eb  mov     [rdi+0C0h], ecx
0x18001c4f1  mov     [rdi+3C0h], r8d
0x18001c4f8  lea     r8d, [r11+r10]
0x18001c4fc  add     r8d, ebx
0x18001c4ff  mov     edx, r8d
0x18001c502  sub     edx, r13d
0x18001c505  sar     edx, 1
0x18001c507  mov     ecx, edx
0x18001c509  sub     edx, [rsp+58h+arg_18]
0x18001c50d  sub     ecx, ebx
0x18001c50f  sub     r8d, edx
0x18001c512  sub     r9d, [rsp+58h+var_58]
0x18001c516  mov     [rdi+100h], r8d
0x18001c51d  lea     eax, [rcx+r13]
0x18001c521  mov     [rdi+200h], eax
0x18001c527  lea     eax, [r11+rbp]
0x18001c52b  mov     [rdi+1C0h], ecx
0x18001c531  mov     [rdi+2C0h], edx
0x18001c537  mov     r8d, [rsp+58h+arg_8]
0x18001c53c  mov     edx, eax
0x18001c53e  sub     r8d, [rsp+58h+var_54]
0x18001c543  sub     edx, r9d
0x18001c546  sar     edx, 1
0x18001c548  mov     ecx, edx
0x18001c54a  sub     edx, [rsp+58h+var_58]
0x18001c54d  sub     eax, edx
0x18001c54f  sub     ecx, ebp
0x18001c551  mov     [rdi+40h], eax
0x18001c554  lea     eax, [rcx+r9]
0x18001c558  mov     [rdi+340h], eax
0x18001c55e  lea     eax, [rsi+r15]
0x18001c562  mov     [rdi+80h], ecx
0x18001c568  mov     [rdi+380h], edx
0x18001c56e  mov     edx, eax
0x18001c570  sub     edx, r8d
0x18001c573  sar     edx, 1
0x18001c575  mov     ecx, edx
0x18001c577  sub     edx, [rsp+58h+var_54]
0x18001c57b  sub     ecx, r15d
0x18001c57e  sub     eax, edx
0x18001c580  mov     [rdi+140h], eax
0x18001c586  lea     eax, [rcx+r8]
0x18001c58a  mov     [rdi+240h], eax
0x18001c590  mov     [rdi+180h], ecx
0x18001c596  mov     [rdi+280h], edx
0x18001c59c  add     rsp, 18h
0x18001c5a0  pop     r15
0x18001c5a2  pop     r14
0x18001c5a4  pop     r13
0x18001c5a6  pop     r12
0x18001c5a8  pop     rdi
0x18001c5a9  pop     rsi
0x18001c5aa  pop     rbp
0x18001c5ab  pop     rbx
0x18001c5ac  retn
```
