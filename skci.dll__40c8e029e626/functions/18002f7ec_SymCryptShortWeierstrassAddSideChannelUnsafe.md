# SymCryptShortWeierstrassAddSideChannelUnsafe

- ea: `0x18002f7ec`
- end: `0x180030023`
- name: `SymCryptShortWeierstrassAddSideChannelUnsafe`
- size: `2103`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18002f1c0`

## callees

- `0x180025590`
- `0x18002574c`
- `0x180025818`
- `0x18002584c`
- `0x180029328`
- `0x18002aec4`
- `0x18002f7ec`
- `0x180033950`

## pseudocode

```c
__int64 __fastcall SymCryptShortWeierstrassAddSideChannelUnsafe(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // rsi
  __int64 v11; // r12
  unsigned int v13; // edx
  unsigned int v14; // r9d
  unsigned int i; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r14
  int v28; // ebx
  __int64 v29; // r12
  __int64 v30; // r15
  unsigned int v31; // r9d
  unsigned int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // r9d
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rbx
  __int64 v39; // rdi
  __int64 v40; // rdx
  __int64 v41; // [rsp+30h] [rbp-79h] BYREF
  __int64 v42; // [rsp+38h] [rbp-71h]
  __int64 v43; // [rsp+40h] [rbp-69h]
  __int64 v44; // [rsp+48h] [rbp-61h]
  __int64 v45; // [rsp+50h] [rbp-59h]
  __int64 v46; // [rsp+58h] [rbp-51h]
  __int64 v47; // [rsp+60h] [rbp-49h]
  __int64 v48; // [rsp+68h] [rbp-41h]
  __int64 v49; // [rsp+70h] [rbp-39h]
  __int64 j; // [rsp+78h] [rbp-31h]
  __int64 v51; // [rsp+80h] [rbp-29h]
  __int64 v52; // [rsp+88h] [rbp-21h]
  __int64 v53; // [rsp+90h] [rbp-19h]
  __int64 v54; // [rsp+98h] [rbp-11h]
  __int64 v55; // [rsp+A0h] [rbp-9h]

  v6 = *(_QWORD *)(a1 + 616);
  LODWORD(v49) = *(_DWORD *)(a1 + 36);
  v53 = a4;
  j = (unsigned int)(2 * v49);
  v11 = j + a2 + 32;
  v52 = v11;
  memset_0(&v41, 0, 0x40u);
  v13 = 16 * *(_DWORD *)(v6 + 4);
  v14 = 0;
  for ( i = 0; i < v13; v14 |= *(_DWORD *)(v11 + 4 * v16) )
    v16 = i++;
  if ( (unsigned __int64)-(__int64)v14 >> 32 != -1 )
  {
    v17 = a3;
    return SymCryptEcpointCopy(a1, v17, a4);
  }
  v19 = 0;
  v20 = 0;
  v21 = a3 + j + 32;
  for ( j = v21; v20 < v13; v19 |= *(_DWORD *)(v21 + 4 * v22) )
    v22 = v20++;
  if ( (unsigned __int64)-(__int64)v19 >> 32 != -1 )
  {
    v17 = a2;
    return SymCryptEcpointCopy(a1, v17, a4);
  }
  v23 = 0;
  v51 = a2 + 32;
  v24 = (unsigned int)v49 + 32LL;
  v49 = a2 + v24;
  v55 = a3 + v24;
  v54 = a3 + 32;
  do
  {
    v25 = (unsigned int)((*(_DWORD *)(v6 + 4) << 6) - 64);
    *(&v41 + v23++) = a5;
    *(_QWORD *)(v25 + a5) = 0;
    *(_QWORD *)(v25 + a5 + 8) = 0;
    *(_QWORD *)(v25 + a5 + 16) = 0;
    *(_QWORD *)(v25 + a5 + 24) = 0;
    *(_QWORD *)(v25 + a5 + 32) = 0;
    *(_QWORD *)(v25 + a5 + 40) = 0;
    *(_QWORD *)(v25 + a5 + 48) = 0;
    *(_QWORD *)(v25 + a5 + 56) = 0;
    v26 = *(unsigned int *)(a1 + 36);
    a5 += v26;
  }
  while ( v23 != 8 );
  v27 = a6 - (unsigned int)(8 * v26);
  SymCryptModSquare(v6, v52, v41, a5, v27);
  v28 = v42;
  SymCryptModMul(v6, v52, v41, v42, a5, v27);
  SymCryptModSquare(v6, v21, v47, a5, v27);
  v29 = v43;
  SymCryptModMul(v6, v51, v47, v43, a5, v27);
  v30 = v44;
  SymCryptModMul(v6, v54, v41, v44, a5, v27);
  SymCryptModSub(v6, v30, v29, v46, a5, v27);
  SymCryptModMul(v6, v55, v28, v48, a5, v27);
  SymCryptModMul(v6, j, v47, v28, a5, v27);
  SymCryptModMul(v6, v49, v28, v28, a5, v27);
  SymCryptModSub(v6, v48, v28, v48, a5, v27);
  v31 = 0;
  v32 = 16 * *(_DWORD *)(v6 + 4);
  if ( v32 )
  {
    v33 = 0;
    do
    {
      v31 |= *(_DWORD *)(v46 + 4 * v33);
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 < v32 );
  }
  v34 = v31;
  v35 = 0;
  v36 = -v34;
  if ( v32 )
  {
    v37 = 0;
    do
    {
      v35 |= *(_DWORD *)(v48 + 4 * v37);
      v37 = (unsigned int)(v37 + 1);
    }
    while ( (unsigned int)v37 < v32 );
  }
  v38 = v45;
  if ( (HIDWORD(v36) | ((unsigned __int64)-(__int64)v35 >> 32)) == 0xFFFFFFFF )
  {
    SymCryptModAdd(v6, v52, j, v45, a5, v27);
    SymCryptModSquare(v6, v38, v38, a5, v27);
    SymCryptModSub(v6, v38, v41, v38, a5, v27);
    SymCryptModSub(v6, v38, v47, v38, a5, v27);
    SymCryptModMul(v6, v38, v46, v38, a5, v27);
    SymCryptModAdd(v6, v48, v48, v48, a5, v27);
    SymCryptModAdd(v6, v46, v46, v30, a5, v27);
    SymCryptModSquare(v6, v30, v30, a5, v27);
    SymCryptModMul(v6, v30, v46, v46, a5, v27);
    SymCryptModMul(v6, v29, v30, v30, a5, v27);
    SymCryptModSquare(v6, v48, v29, a5, v27);
    SymCryptModSub(v6, v29, v46, v29, a5, v27);
    SymCryptModSub(v6, v29, v30, v29, a5, v27);
    SymCryptModSub(v6, v29, v30, v29, a5, v27);
    SymCryptModSub(v6, v30, v29, v30, a5, v27);
    SymCryptModMul(v6, v30, v48, v30, a5, v27);
    SymCryptModMul(v6, v42, v46, v47, a5, v27);
    SymCryptModAdd(v6, v47, v47, v47, a5, v27);
    SymCryptModSub(v6, v30, v47, v30, a5, v27);
    v39 = v53;
    SymCryptFdefModElementCopy(v6, v29, v53 + 32);
    SymCryptFdefModElementCopy(v6, v30, *(unsigned int *)(a1 + 36) + v39 + 32);
    v40 = v38;
  }
  else
  {
    SymCryptFdefModElementCopy(v6, v41, v45);
    SymCryptModSquare(v6, v51, v41, a5, v27);
    SymCryptModSquare(v6, v49, v30, a5, v27);
    SymCryptModSquare(v6, v30, v46, a5, v27);
    SymCryptModAdd(v6, v51, v30, v42, a5, v27);
    SymCryptModSquare(v6, v42, v42, a5, v27);
    SymCryptModSub(v6, v42, v41, v42, a5, v27);
    SymCryptModSub(v6, v42, v46, v42, a5, v27);
    SymCryptModAdd(v6, v42, v42, v42, a5, v27);
    SymCryptModSquare(v6, v38, v29, a5, v27);
    SymCryptModMul(v6, v29, *(_QWORD *)(a1 + 632), v29, a5, v27);
    SymCryptModAdd(v6, v29, v41, v29, a5, v27);
    SymCryptModAdd(v6, v41, v41, v41, a5, v27);
    SymCryptModAdd(v6, v29, v41, v29, a5, v27);
    SymCryptModSquare(v6, v29, v41, a5, v27);
    SymCryptModSub(v6, v41, v42, v41, a5, v27);
    SymCryptModSub(v6, v41, v42, v41, a5, v27);
    SymCryptModSub(v6, v42, v41, v42, a5, v27);
    SymCryptModMul(v6, v29, v42, v42, a5, v27);
    SymCryptModAdd(v6, v46, v46, v46, a5, v27);
    SymCryptModAdd(v6, v46, v46, v46, a5, v27);
    SymCryptModAdd(v6, v46, v46, v46, a5, v27);
    SymCryptModSub(v6, v42, v46, v42, a5, v27);
    SymCryptModAdd(v6, v49, v52, v29, a5, v27);
    SymCryptModSquare(v6, v29, v29, a5, v27);
    SymCryptModSub(v6, v29, v30, v29, a5, v27);
    SymCryptModSub(v6, v29, v38, v29, a5, v27);
    v39 = v53;
    SymCryptFdefModElementCopy(v6, v41, v53 + 32);
    SymCryptFdefModElementCopy(v6, v42, *(unsigned int *)(a1 + 36) + v39 + 32);
    v40 = v29;
  }
  return SymCryptFdefModElementCopy(v6, v40, (unsigned int)(2 * *(_DWORD *)(a1 + 36)) + v39 + 32);
}

```

## disassembly

```asm
0x18002f7ec  push    rbp
0x18002f7ee  push    rbx
0x18002f7ef  push    rsi
0x18002f7f0  push    rdi
0x18002f7f1  push    r12
0x18002f7f3  push    r13
0x18002f7f5  push    r14
0x18002f7f7  push    r15
0x18002f7f9  lea     rbp, [rsp-0Fh]
0x18002f7fe  sub     rsp, 0B8h
0x18002f805  mov     eax, [rcx+24h]
0x18002f808  lea     r12, [rdx+20h]
0x18002f80c  mov     rsi, [rcx+268h]
0x18002f813  mov     r14, rdx
0x18002f816  mov     rdi, [rbp+47h+arg_20]
0x18002f81a  xor     edx, edx; Val
0x18002f81c  mov     dword ptr [rbp+47h+var_80], eax
0x18002f81f  mov     rbx, r8
0x18002f822  add     eax, eax
0x18002f824  mov     [rbp+47h+var_60], r9
0x18002f828  mov     r13, rcx
0x18002f82b  mov     [rbp+47h+var_78], rax
0x18002f82f  add     r12, rax
0x18002f832  lea     r8d, [rdx+40h]; Size
0x18002f836  lea     rcx, [rbp+47h+var_C0]; void *
0x18002f83a  mov     [rbp+47h+var_68], r12
0x18002f83e  mov     r15, r9
0x18002f841  call    memset_0
0x18002f846  mov     edx, [rsi+4]
0x18002f849  xor     r10d, r10d
0x18002f84c  shl     edx, 4
0x18002f84f  mov     r9d, r10d
0x18002f852  mov     ecx, r10d
0x18002f855  test    edx, edx
0x18002f857  jz      short loc_18002F865
0x18002f859  mov     eax, ecx
0x18002f85b  inc     ecx
0x18002f85d  or      r9d, [r12+rax*4]
0x18002f861  cmp     ecx, edx
0x18002f863  jb      short loc_18002F859
0x18002f865  mov     eax, r9d
0x18002f868  neg     rax
0x18002f86b  shr     rax, 20h
0x18002f86f  not     eax
0x18002f871  test    eax, eax
0x18002f873  jz      short loc_18002F888
0x18002f875  mov     rdx, rbx
0x18002f878  mov     r8, r15
0x18002f87b  mov     rcx, r13
0x18002f87e  call    SymCryptEcpointCopy
0x18002f883  jmp     loc_18003000E
0x18002f888  mov     r12, [rbp+47h+var_78]
0x18002f88c  mov     r8d, r10d
0x18002f88f  add     r12, 20h ; ' '
0x18002f893  mov     ecx, r10d
0x18002f896  add     r12, rbx
0x18002f899  mov     [rbp+47h+var_78], r12
0x18002f89d  test    edx, edx
0x18002f89f  jz      short loc_18002F8AD
0x18002f8a1  mov     eax, ecx
0x18002f8a3  inc     ecx
0x18002f8a5  or      r8d, [r12+rax*4]
0x18002f8a9  cmp     ecx, edx
0x18002f8ab  jb      short loc_18002F8A1
0x18002f8ad  mov     eax, r8d
0x18002f8b0  neg     rax
0x18002f8b3  shr     rax, 20h
0x18002f8b7  not     eax
0x18002f8b9  test    eax, eax
0x18002f8bb  jz      short loc_18002F8C2
0x18002f8bd  mov     rdx, r14
0x18002f8c0  jmp     short loc_18002F878
0x18002f8c2  lea     rax, [r14+20h]
0x18002f8c6  mov     rdx, r10
0x18002f8c9  mov     [rbp+47h+var_70], rax
0x18002f8cd  mov     eax, dword ptr [rbp+47h+var_80]
0x18002f8d0  lea     rcx, [rax+20h]
0x18002f8d4  add     rax, 20h ; ' '
0x18002f8d8  add     rcx, r14
0x18002f8db  mov     [rbp+47h+var_80], rcx
0x18002f8df  add     rax, rbx
0x18002f8e2  lea     rcx, [rbx+20h]
0x18002f8e6  mov     [rbp+47h+var_50], rax
0x18002f8ea  mov     [rbp+47h+var_58], rcx
0x18002f8ee  mov     eax, [rsi+4]
0x18002f8f1  shl     eax, 6
0x18002f8f4  sub     eax, 40h ; '@'
0x18002f8f7  mov     [rbp+rdx*8+47h+var_C0], rdi
0x18002f8fc  inc     rdx
0x18002f8ff  mov     [rax+rdi], r10
0x18002f903  mov     [rax+rdi+8], r10
0x18002f908  mov     [rax+rdi+10h], r10
0x18002f90d  mov     [rax+rdi+18h], r10
0x18002f912  mov     [rax+rdi+20h], r10
0x18002f917  mov     [rax+rdi+28h], r10
0x18002f91c  mov     [rax+rdi+30h], r10
0x18002f921  mov     [rax+rdi+38h], r10
0x18002f926  mov     eax, [r13+24h]
0x18002f92a  add     rdi, rax
0x18002f92d  cmp     rdx, 8
0x18002f931  jnz     short loc_18002F8EE
0x18002f933  mov     r14, [rbp+47h+arg_28]
0x18002f937  mov     r9, rdi
0x18002f93a  mov     r8, [rbp+47h+var_C0]
0x18002f93e  mov     rdx, [rbp+47h+var_68]
0x18002f942  shl     eax, 3
0x18002f945  mov     ecx, eax
0x18002f947  sub     r14, rcx
0x18002f94a  mov     rcx, rsi
0x18002f94d  mov     [rsp+0F0h+var_D0], r14
0x18002f952  call    SymCryptModSquare
0x18002f957  mov     rbx, [rbp+47h+var_B8]
0x18002f95b  mov     rcx, rsi
0x18002f95e  mov     r8, [rbp+47h+var_C0]
0x18002f962  mov     r9, rbx
0x18002f965  mov     rdx, [rbp+47h+var_68]
0x18002f969  mov     [rsp+0F0h+var_C8], r14
0x18002f96e  mov     [rsp+0F0h+var_D0], rdi
0x18002f973  call    SymCryptModMul
0x18002f978  mov     r8, [rbp+47h+var_90]
0x18002f97c  mov     r9, rdi
0x18002f97f  mov     rdx, r12
0x18002f982  mov     [rsp+0F0h+var_D0], r14
0x18002f987  mov     rcx, rsi
0x18002f98a  call    SymCryptModSquare
0x18002f98f  mov     r12, [rbp+47h+var_B0]
0x18002f993  mov     rcx, rsi
0x18002f996  mov     r8, [rbp+47h+var_90]
0x18002f99a  mov     r9, r12
0x18002f99d  mov     rdx, [rbp+47h+var_70]
0x18002f9a1  mov     [rsp+0F0h+var_C8], r14
0x18002f9a6  mov     [rsp+0F0h+var_D0], rdi
0x18002f9ab  call    SymCryptModMul
0x18002f9b0  mov     r15, [rbp+47h+var_A8]
0x18002f9b4  mov     rcx, rsi
0x18002f9b7  mov     r8, [rbp+47h+var_C0]
0x18002f9bb  mov     r9, r15
0x18002f9be  mov     rdx, [rbp+47h+var_58]
0x18002f9c2  mov     [rsp+0F0h+var_C8], r14
0x18002f9c7  mov     [rsp+0F0h+var_D0], rdi
0x18002f9cc  call    SymCryptModMul
0x18002f9d1  mov     r9, [rbp+47h+var_98]
0x18002f9d5  mov     r8, r12
0x18002f9d8  mov     rdx, r15
0x18002f9db  mov     [rsp+0F0h+var_C8], r14
0x18002f9e0  mov     rcx, rsi
0x18002f9e3  mov     [rsp+0F0h+var_D0], rdi
0x18002f9e8  call    SymCryptModSub
0x18002f9ed  mov     r9, [rbp+47h+var_88]
0x18002f9f1  mov     r8, rbx
0x18002f9f4  mov     rdx, [rbp+47h+var_50]
0x18002f9f8  mov     rcx, rsi
0x18002f9fb  mov     [rsp+0F0h+var_C8], r14
0x18002fa00  mov     [rsp+0F0h+var_D0], rdi
0x18002fa05  call    SymCryptModMul
0x18002fa0a  mov     r8, [rbp+47h+var_90]
0x18002fa0e  mov     r9, rbx
0x18002fa11  mov     rdx, [rbp+47h+var_78]
0x18002fa15  mov     rcx, rsi
0x18002fa18  mov     [rsp+0F0h+var_C8], r14
0x18002fa1d  mov     [rsp+0F0h+var_D0], rdi
0x18002fa22  call    SymCryptModMul
0x18002fa27  mov     rdx, [rbp+47h+var_80]
0x18002fa2b  mov     r9, rbx
0x18002fa2e  mov     r8, rbx
0x18002fa31  mov     [rsp+0F0h+var_C8], r14
0x18002fa36  mov     rcx, rsi
0x18002fa39  mov     [rsp+0F0h+var_D0], rdi
0x18002fa3e  call    SymCryptModMul
0x18002fa43  mov     r9, [rbp+47h+var_88]
0x18002fa47  mov     r8, rbx
0x18002fa4a  mov     rdx, r9
0x18002fa4d  mov     [rsp+0F0h+var_C8], r14
0x18002fa52  mov     rcx, rsi
0x18002fa55  mov     [rsp+0F0h+var_D0], rdi
0x18002fa5a  call    SymCryptModSub
0x18002fa5f  mov     edx, [rsi+4]
0x18002fa62  xor     r9d, r9d
0x18002fa65  shl     edx, 4
0x18002fa68  test    edx, edx
0x18002fa6a  jz      short loc_18002FA7C
0x18002fa6c  mov     r8, [rbp+47h+var_98]
0x18002fa70  xor     ecx, ecx
0x18002fa72  or      r9d, [r8+rcx*4]
0x18002fa76  inc     ecx
0x18002fa78  cmp     ecx, edx
0x18002fa7a  jb      short loc_18002FA72
0x18002fa7c  mov     ecx, r9d
0x18002fa7f  xor     r9d, r9d
0x18002fa82  neg     rcx
0x18002fa85  test    edx, edx
0x18002fa87  jz      short loc_18002FA9C
0x18002fa89  mov     r10, [rbp+47h+var_88]
0x18002fa8d  xor     r8d, r8d
0x18002fa90  or      r9d, [r10+r8*4]
0x18002fa94  inc     r8d
0x18002fa97  cmp     r8d, edx
0x18002fa9a  jb      short loc_18002FA90
0x18002fa9c  mov     rbx, [rbp+47h+var_A0]
0x18002faa0  shr     rcx, 20h
0x18002faa4  mov     eax, r9d
0x18002faa7  neg     rax
0x18002faaa  shr     rax, 20h
0x18002faae  or      eax, ecx
0x18002fab0  mov     rcx, rsi
0x18002fab3  not     eax
0x18002fab5  test    eax, eax
0x18002fab7  jz      loc_18002FDC8
0x18002fabd  mov     rdx, [rbp+47h+var_C0]
0x18002fac1  mov     r8, rbx
0x18002fac4  call    SymCryptFdefModElementCopy
0x18002fac9  mov     r8, [rbp+47h+var_C0]
0x18002facd  mov     r9, rdi
0x18002fad0  mov     rdx, [rbp+47h+var_70]
0x18002fad4  mov     rcx, rsi
0x18002fad7  mov     [rsp+0F0h+var_D0], r14
0x18002fadc  call    SymCryptModSquare
0x18002fae1  mov     rdx, [rbp+47h+var_80]
0x18002fae5  mov     r9, rdi
0x18002fae8  mov     r8, r15
0x18002faeb  mov     [rsp+0F0h+var_D0], r14
0x18002faf0  mov     rcx, rsi
0x18002faf3  call    SymCryptModSquare
0x18002faf8  mov     r8, [rbp+47h+var_98]
0x18002fafc  mov     r9, rdi
0x18002faff  mov     rdx, r15
0x18002fb02  mov     [rsp+0F0h+var_D0], r14
0x18002fb07  mov     rcx, rsi
0x18002fb0a  call    SymCryptModSquare
0x18002fb0f  mov     r9, [rbp+47h+var_B8]
0x18002fb13  mov     r8, r15
0x18002fb16  mov     rdx, [rbp+47h+var_70]
0x18002fb1a  mov     rcx, rsi
0x18002fb1d  mov     [rsp+0F0h+var_C8], r14
0x18002fb22  mov     [rsp+0F0h+var_D0], rdi
0x18002fb27  call    SymCryptModAdd
0x18002fb2c  mov     r8, [rbp+47h+var_B8]
0x18002fb30  mov     r9, rdi
0x18002fb33  mov     rdx, r8
0x18002fb36  mov     [rsp+0F0h+var_D0], r14
0x18002fb3b  mov     rcx, rsi
0x18002fb3e  call    SymCryptModSquare
0x18002fb43  mov     r9, [rbp+47h+var_B8]
0x18002fb47  mov     rcx, rsi
0x18002fb4a  mov     r8, [rbp+47h+var_C0]
0x18002fb4e  mov     rdx, r9
0x18002fb51  mov     [rsp+0F0h+var_C8], r14
0x18002fb56  mov     [rsp+0F0h+var_D0], rdi
0x18002fb5b  call    SymCryptModSub
0x18002fb60  mov     r9, [rbp+47h+var_B8]
0x18002fb64  mov     rcx, rsi
0x18002fb67  mov     r8, [rbp+47h+var_98]
0x18002fb6b  mov     rdx, r9
0x18002fb6e  mov     [rsp+0F0h+var_C8], r14
0x18002fb73  mov     [rsp+0F0h+var_D0], rdi
0x18002fb78  call    SymCryptModSub
0x18002fb7d  mov     rax, [rbp+47h+var_B8]
0x18002fb81  mov     rcx, rsi
0x18002fb84  mov     r9, rax
0x18002fb87  mov     [rsp+0F0h+var_C8], r14
0x18002fb8c  mov     r8, rax
0x18002fb8f  mov     [rsp+0F0h+var_D0], rdi
0x18002fb94  mov     rdx, rax
0x18002fb97  call    SymCryptModAdd
0x18002fb9c  mov     r9, rdi
0x18002fb9f  mov     [rsp+0F0h+var_D0], r14
0x18002fba4  mov     r8, r12
0x18002fba7  mov     rdx, rbx
0x18002fbaa  mov     rcx, rsi
0x18002fbad  call    SymCryptModSquare
0x18002fbb2  mov     r8, [r13+278h]
0x18002fbb9  mov     r9, r12
0x18002fbbc  mov     rdx, r12
0x18002fbbf  mov     [rsp+0F0h+var_C8], r14
0x18002fbc4  mov     rcx, rsi
0x18002fbc7  mov     [rsp+0F0h+var_D0], rdi
0x18002fbcc  call    SymCryptModMul
0x18002fbd1  mov     r8, [rbp+47h+var_C0]
0x18002fbd5  mov     r9, r12
0x18002fbd8  mov     rdx, r12
0x18002fbdb  mov     [rsp+0F0h+var_C8], r14
0x18002fbe0  mov     rcx, rsi
0x18002fbe3  mov     [rsp+0F0h+var_D0], rdi
0x18002fbe8  call    SymCryptModAdd
0x18002fbed  mov     rax, [rbp+47h+var_C0]
0x18002fbf1  mov     [rsp+0F0h+var_C8], r14
0x18002fbf6  mov     r9, rax
0x18002fbf9  mov     r8, rax
0x18002fbfc  mov     [rsp+0F0h+var_D0], rdi
0x18002fc01  mov     rdx, rax
0x18002fc04  mov     rcx, rsi
0x18002fc07  call    SymCryptModAdd
0x18002fc0c  mov     r8, [rbp+47h+var_C0]
0x18002fc10  mov     r9, r12
0x18002fc13  mov     rdx, r12
0x18002fc16  mov     [rsp+0F0h+var_C8], r14
0x18002fc1b  mov     rcx, rsi
0x18002fc1e  mov     [rsp+0F0h+var_D0], rdi
0x18002fc23  call    SymCryptModAdd
0x18002fc28  mov     r8, [rbp+47h+var_C0]
  ... truncated ...
```
