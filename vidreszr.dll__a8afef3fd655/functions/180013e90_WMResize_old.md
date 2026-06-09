# WMResize_old

- ea: `0x180013e90`
- end: `0x180014131`
- name: `WMResize_old`
- size: `673`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013230`
- `0x180013b90`

## callees

- `0x180009e30`
- `0x18000eae0`
- `0x180013e90`

## pseudocode

```c
__int64 __fastcall WMResize_old(
        __int64 a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        int *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // eax
  _DWORD *v13; // rax
  unsigned int v14; // edi
  int v15; // ecx
  int v16; // edx
  int v17; // eax
  CClipResize *v18; // rbp
  double v19; // xmm1_8
  int v20; // r8d
  int v21; // r10d
  int v22; // ecx
  int v23; // eax
  __int64 result; // rax
  int v25; // eax
  unsigned int v26; // ecx

  if ( !a4 || !a7 || !a1 )
    return 1;
  v9 = *(_DWORD *)(a1 + 44) / 2;
  if ( !*(_DWORD *)(a1 + 1084) )
    v9 = *(_DWORD *)(a1 + 44);
  v10 = *(_QWORD *)(a1 + 8);
  v11 = *(_DWORD *)(v10 + 16);
  if ( v11 == 1448433993 || v11 == 808596553 || v11 == 842094169 )
  {
    *a4 = 3 * *(_DWORD *)(v10 + 4) * *(_DWORD *)(v10 + 8) / 2;
    v12 = 3 * *(_DWORD *)(a1 + 40) * v9 / 2;
  }
  else
  {
    *a4 = 4 * *(_DWORD *)(v10 + 8) * ((*(_DWORD *)(v10 + 4) * *(unsigned __int16 *)(v10 + 14) / 8 + 3) / 4);
    v12 = 4 * v9 * ((*(_DWORD *)(a1 + 40) * *(unsigned __int16 *)(*(_QWORD *)(a1 + 8) + 14LL) / 8 + 3) / 4);
  }
  *a7 = v12;
  if ( a6 < v12 || a3 < *a4 )
  {
    result = 2147500037LL;
    *a4 = 0;
    *a7 = 0;
    return result;
  }
  if ( !a2 || !a5 )
    return 1;
  if ( !*(_DWORD *)(a1 + 1080) || (v13 = *(_DWORD **)(a1 + 8), v14 = v13[4], v14 == 808596553) || v14 == 1448433993 )
  {
    v25 = CMSMtoN::Resize(
            (CMSMtoN *)(a1 + 72),
            *(struct tagBITMAPINFOHEADER **)(a1 + 8),
            a2,
            a5,
            *(_DWORD *)(a1 + 40),
            v9);
    v26 = 0;
    if ( !v25 )
      return (unsigned int)-2147467259;
    return v26;
  }
  else
  {
    v15 = *(_DWORD *)(a1 + 40);
    v16 = v13[2];
    v17 = v13[1];
    v18 = (CClipResize *)(a1 + 856);
    v19 = (double)v17 / (double)v15;
    v20 = v15 * v9;
    v21 = v16 * v17;
    if ( v14 == 842150992 )
    {
      v22 = 3 * v21 / 2;
      v23 = 3 * v20 / 2;
    }
    else
    {
      v22 = 5 * v21 / 4;
      v23 = 5 * v20 / 4;
    }
    CClipResize::ClipResizeHighQuality(
      v18,
      a2,
      &a2[v21],
      &a2[v22],
      a5,
      &a5[v20],
      &a5[v23],
      v19,
      0.0,
      (double)v16 / (double)v9,
      0.0,
      v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180013e90  mov     [rsp+arg_8], rbx
0x180013e95  mov     [rsp+arg_10], rsi
0x180013e9a  push    rdi
0x180013e9b  sub     rsp, 60h
0x180013e9f  mov     rsi, rdx
0x180013ea2  mov     r10, rcx
0x180013ea5  test    r9, r9
0x180013ea8  jz      loc_180014119
0x180013eae  mov     rdi, [rsp+68h+arg_30]
0x180013eb6  test    rdi, rdi
0x180013eb9  jz      loc_180014119
0x180013ebf  test    rcx, rcx
0x180013ec2  jz      loc_180014119
0x180013ec8  mov     eax, [rcx+2Ch]
0x180013ecb  cdq
0x180013ecc  sub     eax, edx
0x180013ece  sar     eax, 1
0x180013ed0  cmp     dword ptr [rcx+43Ch], 0
0x180013ed7  mov     ebx, eax
0x180013ed9  cmovz   ebx, [rcx+2Ch]
0x180013edd  mov     rcx, [rcx+8]
0x180013ee1  mov     eax, [rcx+10h]
0x180013ee4  cmp     eax, 56555949h
0x180013ee9  jz      short loc_180013F4A
0x180013eeb  cmp     eax, 30323449h
0x180013ef0  jz      short loc_180013F4A
0x180013ef2  cmp     eax, 32315659h
0x180013ef7  jz      short loc_180013F4A
0x180013ef9  movzx   eax, word ptr [rcx+0Eh]
0x180013efd  imul    eax, [rcx+4]
0x180013f01  cdq
0x180013f02  and     edx, 7
0x180013f05  add     eax, edx
0x180013f07  sar     eax, 3
0x180013f0a  add     eax, 3
0x180013f0d  cdq
0x180013f0e  and     edx, 3
0x180013f11  add     eax, edx
0x180013f13  sar     eax, 2
0x180013f16  imul    eax, [rcx+8]
0x180013f1a  shl     eax, 2
0x180013f1d  mov     [r9], eax
0x180013f20  mov     rax, [r10+8]
0x180013f24  movzx   eax, word ptr [rax+0Eh]
0x180013f28  imul    eax, [r10+28h]
0x180013f2d  cdq
0x180013f2e  and     edx, 7
0x180013f31  add     eax, edx
0x180013f33  sar     eax, 3
0x180013f36  add     eax, 3
0x180013f39  cdq
0x180013f3a  and     edx, 3
0x180013f3d  add     eax, edx
0x180013f3f  sar     eax, 2
0x180013f42  imul    eax, ebx
0x180013f45  shl     eax, 2
0x180013f48  jmp     short loc_180013F6B
0x180013f4a  mov     eax, [rcx+8]
0x180013f4d  imul    eax, [rcx+4]
0x180013f51  lea     eax, [rax+rax*2]
0x180013f54  cdq
0x180013f55  sub     eax, edx
0x180013f57  sar     eax, 1
0x180013f59  mov     [r9], eax
0x180013f5c  mov     eax, ebx
0x180013f5e  imul    eax, [r10+28h]
0x180013f63  lea     eax, [rax+rax*2]
0x180013f66  cdq
0x180013f67  sub     eax, edx
0x180013f69  sar     eax, 1
0x180013f6b  mov     [rdi], eax
0x180013f6d  cmp     [rsp+68h+arg_28], eax
0x180013f74  jb      loc_1800140FA
0x180013f7a  cmp     r8d, [r9]
0x180013f7d  jb      loc_1800140FA
0x180013f83  test    rsi, rsi
0x180013f86  jz      loc_180014119
0x180013f8c  mov     r11, [rsp+68h+arg_20]
0x180013f94  test    r11, r11
0x180013f97  jz      loc_180014119
0x180013f9d  cmp     dword ptr [r10+438h], 0
0x180013fa5  jz      loc_1800140BA
0x180013fab  mov     rax, [r10+8]
0x180013faf  mov     edi, [rax+10h]
0x180013fb2  cmp     edi, 30323449h
0x180013fb8  jz      loc_1800140BA
0x180013fbe  cmp     edi, 56555949h
0x180013fc4  jz      loc_1800140BA
0x180013fca  mov     ecx, [r10+28h]
0x180013fce  mov     r8d, ebx
0x180013fd1  mov     edx, [rax+8]
0x180013fd4  mov     eax, [rax+4]
0x180013fd7  mov     [rsp+68h+arg_0], rbp
0x180013fdc  lea     rbp, [r10+358h]
0x180013fe3  movd    xmm0, ecx
0x180013fe7  mov     r10d, eax
0x180013fea  cvtdq2pd xmm0, xmm0
0x180013fee  movd    xmm1, eax
0x180013ff2  cvtdq2pd xmm1, xmm1
0x180013ff6  movd    xmm2, edx
0x180013ffa  divsd   xmm1, xmm0
0x180013ffe  movd    xmm0, ebx
0x180014002  cvtdq2pd xmm0, xmm0
0x180014006  cvtdq2pd xmm2, xmm2
0x18001400a  imul    r8d, ecx
0x18001400e  imul    r10d, edx
0x180014012  divsd   xmm2, xmm0
0x180014016  cmp     edi, 32323450h
0x18001401c  jnz     short loc_180014034
0x18001401e  lea     eax, [r10+r10*2]
0x180014022  cdq
0x180014023  sub     eax, edx
0x180014025  sar     eax, 1
0x180014027  mov     ecx, eax
0x180014029  lea     eax, [r8+r8*2]
0x18001402d  cdq
0x18001402e  sub     eax, edx
0x180014030  sar     eax, 1
0x180014032  jmp     short loc_18001404F
0x180014034  lea     eax, [r10+r10*4]
0x180014038  cdq
0x180014039  and     edx, 3
0x18001403c  lea     ecx, [rdx+rax]
0x18001403f  lea     eax, [r8+r8*4]
0x180014043  sar     ecx, 2
0x180014046  cdq
0x180014047  and     edx, 3
0x18001404a  add     eax, edx
0x18001404c  sar     eax, 2
0x18001404f  mov     [rsp+68h+var_10], edi; unsigned int
0x180014053  xorps   xmm0, xmm0
0x180014056  movsd   [rsp+68h+var_18], xmm0; double
0x18001405c  movsd   [rsp+68h+var_20], xmm2; double
0x180014062  movsd   [rsp+68h+var_28], xmm0; double
0x180014068  movsxd  rdx, eax
0x18001406b  movsxd  rax, r8d
0x18001406e  add     rdx, r11
0x180014071  movsd   [rsp+68h+var_30], xmm1; double
0x180014077  add     rax, r11
0x18001407a  mov     [rsp+68h+var_38], rdx; unsigned __int8 *
0x18001407f  mov     rdx, rsi; unsigned __int8 *
0x180014082  movsxd  r9, ecx
0x180014085  mov     rcx, rbp; this
0x180014088  movsxd  r8, r10d
0x18001408b  add     r9, rsi; unsigned __int8 *
0x18001408e  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x180014093  add     r8, rsi; unsigned __int8 *
0x180014096  mov     [rsp+68h+var_48], r11; unsigned __int8 *
0x18001409b  call    ?ClipResizeHighQuality@CClipResize@@QEAAXPEBE00PEAE11NNNNK@Z; CClipResize::ClipResizeHighQuality(uchar const *,uchar const *,uchar const *,uchar *,uchar *,uchar *,double,double,double,double,ulong)
0x1800140a0  mov     rbp, [rsp+68h+arg_0]
0x1800140a5  xor     eax, eax
0x1800140a7  mov     rbx, [rsp+68h+arg_8]
0x1800140ac  mov     rsi, [rsp+68h+arg_10]
0x1800140b4  add     rsp, 60h
0x1800140b8  pop     rdi
0x1800140b9  retn
0x1800140ba  mov     eax, [r10+28h]
0x1800140be  lea     rcx, [r10+48h]; this
0x1800140c2  mov     rdx, [r10+8]; struct tagBITMAPINFOHEADER *
0x1800140c6  mov     r9, r11; unsigned __int8 *
0x1800140c9  mov     dword ptr [rsp+68h+var_40], ebx; int
0x1800140cd  mov     r8, rsi; unsigned __int8 *
0x1800140d0  mov     dword ptr [rsp+68h+var_48], eax; int
0x1800140d4  call    ?Resize@CMSMtoN@@UEAAHPEAUtagBITMAPINFOHEADER@@PEBEPEAEHH@Z; CMSMtoN::Resize(tagBITMAPINFOHEADER *,uchar const *,uchar *,int,int)
0x1800140d9  xor     ecx, ecx
0x1800140db  mov     edx, 80004005h
0x1800140e0  test    eax, eax
0x1800140e2  cmovz   ecx, edx
0x1800140e5  mov     eax, ecx
0x1800140e7  mov     rbx, [rsp+68h+arg_8]
0x1800140ec  mov     rsi, [rsp+68h+arg_10]
0x1800140f4  add     rsp, 60h
0x1800140f8  pop     rdi
0x1800140f9  retn
0x1800140fa  xor     ecx, ecx
0x1800140fc  mov     eax, 80004005h
0x180014101  mov     [r9], ecx
0x180014104  mov     [rdi], ecx
0x180014106  mov     rbx, [rsp+68h+arg_8]
0x18001410b  mov     rsi, [rsp+68h+arg_10]
0x180014113  add     rsp, 60h
0x180014117  pop     rdi
0x180014118  retn
0x180014119  mov     rbx, [rsp+68h+arg_8]
0x18001411e  mov     eax, 1
0x180014123  mov     rsi, [rsp+68h+arg_10]
0x18001412b  add     rsp, 60h
0x18001412f  pop     rdi
0x180014130  retn
```
