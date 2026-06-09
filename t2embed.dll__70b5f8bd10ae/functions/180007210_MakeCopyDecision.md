# MakeCopyDecision

- ea: `0x180007210`
- end: `0x180007598`
- name: `MakeCopyDecision`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006d30`

## callees

- `0x180006400`
- `0x180006b30`
- `0x180007210`
- `0x1800075a0`
- `0x180007bf0`
- `0x180007dc0`
- `0x18000ed70`
- `0x18001c9ec`

## pseudocode

```c
__int64 __fastcall MakeCopyDecision(__int64 *a1, int a2, unsigned int *a3)
{
  __int64 v3; // rsi
  int v6; // eax
  int v7; // r12d
  __int64 v8; // r15
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // r15d
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // r14d
  int v18; // r10d
  __int64 v19; // r8
  __int64 *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdi
  int v24; // r14d
  int v25; // esi
  int v26; // edi
  int v27; // eax
  unsigned int v28; // esi
  int v29; // eax
  __int64 v30; // r8
  int v31; // esi
  int v32; // edi
  int v33; // eax
  __int64 v34; // rsi
  int v35; // edi
  int v36; // eax
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  signed int v40; // [rsp+30h] [rbp-38h] BYREF
  int v41; // [rsp+34h] [rbp-34h] BYREF
  int v42; // [rsp+38h] [rbp-30h] BYREF
  int v43; // [rsp+3Ch] [rbp-2Ch] BYREF
  int v44; // [rsp+40h] [rbp-28h] BYREF
  int v45; // [rsp+44h] [rbp-24h] BYREF
  __int64 v46; // [rsp+48h] [rbp-20h]
  __int64 v47; // [rsp+50h] [rbp-18h]
  __int64 v48; // [rsp+58h] [rbp-10h]
  int v49; // [rsp+B0h] [rbp+48h] BYREF
  int v50; // [rsp+B8h] [rbp+50h]
  int v51; // [rsp+C0h] [rbp+58h] BYREF
  int v52; // [rsp+C8h] [rbp+60h] BYREF

  v50 = a2;
  v3 = a2;
  v40 = 0;
  v41 = 0;
  v45 = 0;
  v52 = 0;
  v42 = 0;
  v44 = 0;
  v51 = 0;
  v49 = 0;
  v43 = 0;
  v6 = Findmatch((_DWORD)a1, a2, (unsigned int)&v40, (unsigned int)&v52, (__int64)&v51);
  v47 = v3;
  v7 = v6;
  if ( (int)v3 > 0 )
  {
    v8 = *(unsigned __int8 *)(v3 + *a1);
    _mm_lfence();
    v9 = a1[15];
    if ( v9 )
    {
      a1[15] = *(_QWORD *)(v9 + 8);
    }
    else
    {
      v14 = *((_DWORD *)a1 + 32);
      if ( v14 >= 4095 )
      {
        v38 = a1[18];
        v46 = a1[17];
        v39 = MTX_mem_malloc(v38, 0x10000);
        a1[17] = v39;
        if ( !v39 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        *(_QWORD *)(a1[17] + 65528) = v46;
        v14 = 0;
      }
      v9 = a1[17] + 16LL * v14;
      *((_DWORD *)a1 + 32) = v14 + 1;
    }
    v10 = *(unsigned __int8 *)(v3 + *a1 - 1);
    *(_DWORD *)v9 = v3 - 1;
    v11 = v8 | (v10 << 8);
    *(_QWORD *)(v9 + 8) = *(_QWORD *)(a1[14] + 8 * v11);
    *(_QWORD *)(a1[14] + 8 * v11) = v9;
  }
  v12 = v40;
  if ( v52 <= 0 || v40 >= *((_DWORD *)a1 + 11) )
    goto LABEL_6;
  LODWORD(v46) = v3 + 1;
  v15 = Findmatch((_DWORD)a1, (int)v3 + 1, (unsigned int)&v41, (unsigned int)&v42, (__int64)&v49);
  v16 = *a1;
  v17 = 0;
  v18 = v15;
  v40 = v15;
  v19 = *(unsigned __int8 *)(v3 + v16);
  v20 = (__int64 *)a1[11];
  v21 = *v20;
  v22 = v20[1];
  v48 = v21;
  v23 = *(__int16 *)(v22 + 2 * v19);
  if ( *(_WORD *)(v21 + 12 * v23 + 6) != (_WORD)v19 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v21 = v48;
    v18 = v40;
  }
  do
  {
    ++v17;
    LOWORD(v23) = *(_WORD *)(v21 + 12LL * (__int16)v23);
  }
  while ( (_WORD)v23 != 1 );
  v24 = v17 << 16;
  if ( v42 >= v52 && v51 > (v24 + v49 * v18) / (v18 + 1) )
    goto LABEL_26;
  if ( v7 > 3 )
  {
    v25 = v7 + v3;
    v41 = Findmatch((_DWORD)a1, v25, (unsigned int)&v41, (unsigned int)&v42, (__int64)&v49);
    v26 = v41;
    if ( v41 < 2 )
      goto LABEL_6;
    v45 = Findmatch((_DWORD)a1, v25 - 1, (unsigned int)&v45, (unsigned int)&v44, (__int64)&v43);
    if ( v45 <= v26 )
      goto LABEL_6;
    if ( v43 >= v49 )
      goto LABEL_6;
    v27 = MTX_AHUFF_BitsUsed(v12);
    v44 = v7 - 1;
    v28 = (v27 + 2) / 3;
    v52 = v12 + 1;
    v29 = EncodeLengthCost(a1, (unsigned int)(v7 - 1), v12 + 1, v28);
    v30 = v28;
    v31 = v52;
    v32 = v29;
    v33 = EncodeDistance2Cost(a1, (unsigned int)v52, v30);
    if ( (v7 * v51 + v41 * v49) / (v41 + v7) <= (v45 * v43 + v32 + v33) / (v7 + v45 - 1) )
      goto LABEL_6;
    v7 = v44;
    v12 = v31;
    LODWORD(v3) = v50;
  }
  if ( v7 != 2 )
    goto LABEL_6;
  if ( (int)v3 < 2 )
  {
    if ( (int)v3 < 1 )
      goto LABEL_6;
    v34 = v47;
    goto LABEL_29;
  }
  v34 = v47;
  if ( *(_BYTE *)(*a1 + v47) != *(_BYTE *)(*a1 + v47 - 2) )
  {
LABEL_29:
    if ( (int)v46 < *((_DWORD *)a1 + 9) && *(_BYTE *)(*a1 + v34 + 1) == *(_BYTE *)(*a1 + v34 - 1) )
    {
      v37 = MTX_AHUFF_WriteSymbolCost(a1[11], *((unsigned __int16 *)a1 + 24));
      if ( 2 * v51 > v24 + v37 )
        v7 = 0;
    }
    goto LABEL_6;
  }
  v35 = MTX_AHUFF_WriteSymbolCost(a1[11], *((unsigned __int16 *)a1 + 24));
  v36 = MTX_AHUFF_WriteSymbolCost(a1[11], *(unsigned __int8 *)(v34 + *a1 + 1));
  if ( 2 * v51 > v35 + v36 )
LABEL_26:
    v7 = 0;
LABEL_6:
  *a3 = v12;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007210  mov     [rsp-40h+arg_8], edx
0x180007214  push    rbp
0x180007215  push    rbx
0x180007216  push    rsi
0x180007217  push    rdi
0x180007218  push    r12
0x18000721a  push    r13
0x18000721c  push    r14
0x18000721e  push    r15
0x180007220  mov     rbp, rsp
0x180007223  sub     rsp, 68h
0x180007227  xor     edi, edi
0x180007229  movsxd  rsi, edx
0x18000722c  mov     r13, r8
0x18000722f  mov     [rbp+var_38], edi
0x180007232  lea     rax, [rbp+arg_10]
0x180007236  mov     [rbp+var_34], edi
0x180007239  mov     edx, esi
0x18000723b  mov     [rbp+var_24], edi
0x18000723e  lea     r9, [rbp+arg_18]
0x180007242  mov     [rbp+arg_18], edi
0x180007245  lea     r8, [rbp+var_38]
0x180007249  mov     [rbp+var_30], edi
0x18000724c  mov     rbx, rcx
0x18000724f  mov     [rbp+var_28], edi
0x180007252  mov     [rbp+arg_10], edi
0x180007255  mov     [rbp+arg_0], edi
0x180007258  mov     [rbp+var_2C], edi
0x18000725b  mov     [rsp+68h+var_48], rax
0x180007260  call    Findmatch
0x180007265  mov     [rbp+var_18], rsi
0x180007269  mov     r12d, eax
0x18000726c  test    esi, esi
0x18000726e  jle     short loc_1800072B5
0x180007270  mov     rcx, [rbx]
0x180007273  movzx   r15d, byte ptr [rsi+rcx]
0x180007278  lfence
0x18000727b  mov     r8, [rbx+78h]
0x18000727f  test    r8, r8
0x180007282  jz      short loc_1800072D7
0x180007284  mov     rcx, [r8+8]
0x180007288  mov     [rbx+78h], rcx
0x18000728c  mov     rax, [rbx]
0x18000728f  movzx   edx, byte ptr [rsi+rax-1]
0x180007294  lea     eax, [rsi-1]
0x180007297  mov     [r8], eax
0x18000729a  mov     rax, [rbx+70h]
0x18000729e  shl     rdx, 8
0x1800072a2  or      rdx, r15
0x1800072a5  mov     rcx, [rax+rdx*8]
0x1800072a9  mov     [r8+8], rcx
0x1800072ad  mov     rax, [rbx+70h]
0x1800072b1  mov     [rax+rdx*8], r8
0x1800072b5  cmp     [rbp+arg_18], 0
0x1800072b9  mov     r15d, [rbp+var_38]
0x1800072bd  jg      short loc_180007300
0x1800072bf  mov     [r13+0], r15d
0x1800072c3  mov     eax, r12d
0x1800072c6  add     rsp, 68h
0x1800072ca  pop     r15
0x1800072cc  pop     r14
0x1800072ce  pop     r13
0x1800072d0  pop     r12
0x1800072d2  pop     rdi
0x1800072d3  pop     rsi
0x1800072d4  pop     rbx
0x1800072d5  pop     rbp
0x1800072d6  retn
0x1800072d7  mov     eax, [rbx+80h]
0x1800072dd  cmp     eax, 0FFFh
0x1800072e2  jge     loc_180007540
0x1800072e8  movsxd  r8, eax
0x1800072eb  shl     r8, 4
0x1800072ef  add     r8, [rbx+88h]
0x1800072f6  inc     eax
0x1800072f8  mov     [rbx+80h], eax
0x1800072fe  jmp     short loc_18000728C
0x180007300  cmp     r15d, [rbx+2Ch]
0x180007304  jge     short loc_1800072BF
0x180007306  lea     eax, [rsi+1]
0x180007309  lea     rcx, [rbp+arg_0]
0x18000730d  mov     dword ptr [rbp+var_20], eax
0x180007310  mov     [rsp+68h+var_48], rcx
0x180007315  lea     r9, [rbp+var_30]
0x180007319  mov     rcx, rbx
0x18000731c  lea     r8, [rbp+var_34]
0x180007320  mov     edx, eax
0x180007322  call    Findmatch
0x180007327  mov     rcx, [rbx]
0x18000732a  mov     r14d, edi
0x18000732d  mov     r10d, eax
0x180007330  mov     [rbp+var_38], eax
0x180007333  movzx   r8d, byte ptr [rsi+rcx]
0x180007338  mov     rcx, [rbx+58h]
0x18000733c  mov     r9, [rcx]
0x18000733f  mov     rcx, [rcx+8]
0x180007343  mov     [rbp+var_10], r9
0x180007347  movsx   rdi, word ptr [rcx+r8*2]
0x18000734c  lea     rdx, [rdi+rdi*2]
0x180007350  cmp     [r9+rdx*4+6], r8w
0x180007356  jnz     loc_180007586
0x18000735c  movsx   rax, di
0x180007360  inc     r14d
0x180007363  lea     rcx, [rax+rax*2]
0x180007367  movzx   edi, word ptr [r9+rcx*4]
0x18000736c  cmp     di, 1
0x180007370  jnz     short loc_18000735C
0x180007372  mov     eax, [rbp+arg_18]
0x180007375  shl     r14d, 10h
0x180007379  cmp     [rbp+var_30], eax
0x18000737c  jge     loc_1800074D0
0x180007382  cmp     r12d, 3
0x180007386  jle     loc_18000747F
0x18000738c  lea     rax, [rbp+arg_0]
0x180007390  add     esi, r12d
0x180007393  mov     edx, esi
0x180007395  mov     [rsp+68h+var_48], rax
0x18000739a  lea     r9, [rbp+var_30]
0x18000739e  mov     rcx, rbx
0x1800073a1  lea     r8, [rbp+var_34]
0x1800073a5  call    Findmatch
0x1800073aa  mov     [rbp+var_34], eax
0x1800073ad  mov     edi, eax
0x1800073af  cmp     eax, 2
0x1800073b2  jl      loc_1800072BF
0x1800073b8  lea     rax, [rbp+var_2C]
0x1800073bc  mov     rcx, rbx
0x1800073bf  lea     edx, [rsi-1]
0x1800073c2  mov     [rsp+68h+var_48], rax
0x1800073c7  lea     r9, [rbp+var_28]
0x1800073cb  lea     r8, [rbp+var_24]
0x1800073cf  call    Findmatch
0x1800073d4  mov     [rbp+var_24], eax
0x1800073d7  cmp     eax, edi
0x1800073d9  jle     loc_1800072BF
0x1800073df  mov     eax, [rbp+arg_0]
0x1800073e2  cmp     [rbp+var_2C], eax
0x1800073e5  jge     loc_1800072BF
0x1800073eb  mov     ecx, r15d
0x1800073ee  call    MTX_AHUFF_BitsUsed
0x1800073f3  lea     ecx, [rax+2]
0x1800073f6  mov     eax, 55555556h
0x1800073fb  imul    ecx
0x1800073fd  lea     ecx, [r12-1]
0x180007402  mov     esi, edx
0x180007404  mov     [rbp+var_28], ecx
0x180007407  lea     eax, [r15+1]
0x18000740b  shr     esi, 1Fh
0x18000740e  add     esi, edx
0x180007410  mov     [rbp+arg_18], eax
0x180007413  mov     edx, ecx
0x180007415  mov     r9d, esi
0x180007418  mov     rcx, rbx
0x18000741b  mov     r8d, eax
0x18000741e  call    EncodeLengthCost
0x180007423  mov     r8d, esi
0x180007426  mov     rcx, rbx
0x180007429  mov     esi, [rbp+arg_18]
0x18000742c  mov     edi, eax
0x18000742e  mov     edx, esi
0x180007430  call    EncodeDistance2Cost
0x180007435  mov     r8d, [rbp+var_24]
0x180007439  add     eax, edi
0x18000743b  mov     edx, [rbp+var_2C]
0x18000743e  imul    edx, r8d
0x180007442  lea     ecx, [r8-1]
0x180007446  add     ecx, r12d
0x180007449  add     eax, edx
0x18000744b  cdq
0x18000744c  idiv    ecx
0x18000744e  mov     edx, [rbp+arg_0]
0x180007451  mov     ecx, [rbp+arg_10]
0x180007454  mov     r8d, eax
0x180007457  mov     eax, [rbp+var_34]
0x18000745a  imul    edx, eax
0x18000745d  imul    ecx, r12d
0x180007461  add     edx, ecx
0x180007463  lea     ecx, [rax+r12]
0x180007467  mov     eax, edx
0x180007469  cdq
0x18000746a  idiv    ecx
0x18000746c  cmp     eax, r8d
0x18000746f  jle     loc_1800072BF
0x180007475  mov     r12d, [rbp+var_28]
0x180007479  mov     r15d, esi
0x18000747c  mov     esi, [rbp+arg_8]
0x18000747f  cmp     r12d, 2
0x180007483  jnz     loc_1800072BF
0x180007489  cmp     esi, r12d
0x18000748c  jl      short loc_1800074F2
0x18000748e  mov     rcx, [rbx]
0x180007491  mov     rsi, [rbp+var_18]
0x180007495  movzx   eax, byte ptr [rcx+rsi-2]
0x18000749a  cmp     [rcx+rsi], al
0x18000749d  jnz     short loc_1800074FF
0x18000749f  movzx   edx, word ptr [rbx+30h]
0x1800074a3  mov     rcx, [rbx+58h]
0x1800074a7  call    MTX_AHUFF_WriteSymbolCost
0x1800074ac  mov     rcx, [rbx]
0x1800074af  mov     edi, eax
0x1800074b1  movzx   edx, byte ptr [rsi+rcx+1]
0x1800074b6  mov     rcx, [rbx+58h]
0x1800074ba  call    MTX_AHUFF_WriteSymbolCost
0x1800074bf  mov     ecx, [rbp+arg_10]
0x1800074c2  add     eax, edi
0x1800074c4  add     ecx, ecx
0x1800074c6  cmp     ecx, eax
0x1800074c8  jle     loc_1800072BF
0x1800074ce  jmp     short loc_1800074EA
0x1800074d0  mov     eax, r10d
0x1800074d3  lea     ecx, [r10+1]
0x1800074d7  imul    eax, [rbp+arg_0]
0x1800074db  add     eax, r14d
0x1800074de  cdq
0x1800074df  idiv    ecx
0x1800074e1  cmp     [rbp+arg_10], eax
0x1800074e4  jle     loc_180007382
0x1800074ea  xor     r12d, r12d
0x1800074ed  jmp     loc_1800072BF
0x1800074f2  cmp     esi, 1
0x1800074f5  jl      loc_1800072BF
0x1800074fb  mov     rsi, [rbp+var_18]
0x1800074ff  mov     eax, dword ptr [rbp+var_20]
0x180007502  cmp     eax, [rbx+24h]
0x180007505  jge     loc_1800072BF
0x18000750b  mov     rcx, [rbx]
0x18000750e  movzx   eax, byte ptr [rcx+rsi-1]
0x180007513  cmp     [rcx+rsi+1], al
0x180007517  jnz     loc_1800072BF
0x18000751d  movzx   edx, word ptr [rbx+30h]
0x180007521  mov     rcx, [rbx+58h]
0x180007525  call    MTX_AHUFF_WriteSymbolCost
0x18000752a  mov     ecx, [rbp+arg_10]
0x18000752d  add     eax, r14d
0x180007530  lea     edx, [rcx+rcx]
0x180007533  xor     ecx, ecx
0x180007535  cmp     edx, eax
0x180007537  cmovg   r12d, ecx
0x18000753b  jmp     loc_1800072BF
0x180007540  mov     rax, [rbx+88h]
0x180007547  mov     edx, 10000h
0x18000754c  mov     rcx, [rbx+90h]
0x180007553  mov     [rbp+var_20], rax
0x180007557  call    MTX_mem_malloc
0x18000755c  mov     [rbx+88h], rax
0x180007563  test    rax, rax
0x180007566  jnz     short loc_18000756D
0x180007568  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000756d  mov     rax, [rbx+88h]
0x180007574  mov     rcx, [rbp+var_20]
0x180007578  mov     [rax+0FFF8h], rcx
0x18000757f  xor     eax, eax
0x180007581  jmp     loc_1800072E8
0x180007586  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000758b  mov     r9, [rbp+var_10]
0x18000758f  mov     r10d, [rbp+var_38]
0x180007593  jmp     loc_18000735C
```
