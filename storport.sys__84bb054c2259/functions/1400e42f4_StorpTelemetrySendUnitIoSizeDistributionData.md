# StorpTelemetrySendUnitIoSizeDistributionData

- ea: `0x1400e42f4`
- end: `0x1400e4a4d`
- name: `StorpTelemetrySendUnitIoSizeDistributionData`
- size: `1881`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14004e19c`
- `0x1401939ac`

## callees

- `0x1400290b0`
- `0x1400d4e84`
- `0x1400e42f4`
- `0x1400e6374`
- `0x1400e6414`
- `0x14014b400`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e49bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4a01`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e49bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4a01`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e4a1a`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e439c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e43aa`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e439c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e43aa`

## pseudocode

```c
__int64 __fastcall StorpTelemetrySendUnitIoSizeDistributionData(__int64 a1)
{
  __int64 v1; // r13
  _QWORD *v2; // r12
  void *v3; // r14
  unsigned int v4; // r15d
  unsigned int v5; // edi
  ULONG RecommendedSharedDataAlignment; // ebx
  ULONG v7; // eax
  __int64 v8; // rbx
  unsigned int i; // edx
  unsigned int v10; // r10d
  char *v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r11
  unsigned int v15; // r10d
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rdx
  int j; // esi
  int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  int v26; // r14d
  char *v27; // r15
  char *v28; // r13
  __int64 v29; // rbx
  size_t v30; // rdx
  size_t v31; // rdx
  size_t v32; // rdx
  size_t v33; // rdx
  const int *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rsi
  const int *v37; // rdi
  __int64 *v38; // r9
  __int64 v39; // rdi
  __int64 v40; // rsi
  __int64 v41; // rbx
  __int64 *v42; // rax
  void *v43; // rcx
  void *v44; // rcx
  int v46; // [rsp+1D0h] [rbp-80h]
  STRSAFE_LPSTR v47; // [rsp+1D8h] [rbp-78h]
  char v48; // [rsp+1E0h] [rbp-70h]
  char *Pool; // [rsp+200h] [rbp-50h]
  __int64 v51[18]; // [rsp+210h] [rbp-40h] BYREF
  __int64 v52[18]; // [rsp+2A0h] [rbp+50h] BYREF
  char pszDest[16]; // [rsp+330h] [rbp+E0h] BYREF
  int v54; // [rsp+340h] [rbp+F0h]
  char pszSrc[16]; // [rsp+348h] [rbp+F8h] BYREF
  int v56; // [rsp+358h] [rbp+108h]

  v1 = a1;
  v2 = 0;
  memset_0(v52, 0, sizeof(v52));
  memset_0(v51, 0, sizeof(v51));
  if ( *(_QWORD *)(v1 + 2384) )
  {
    v5 = HIDWORD(qword_140177050);
    Pool = (char *)RaidAllocatePool(72, (unsigned int)dword_140177064, 1700028754, *(_QWORD *)(v1 + 8));
    v3 = Pool;
    if ( Pool
      && (RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment(),
          v7 = KeGetRecommendedSharedDataAlignment(),
          (v2 = (_QWORD *)RaidAllocatePool(
                            72,
                            -RecommendedSharedDataAlignment & (16 * v5 + v7 - 1),
                            1700028754,
                            *(_QWORD *)(v1 + 8))) != 0) )
    {
      v4 = -1073741823;
      v8 = 0;
      v48 = 0;
      memmove(Pool, *(const void **)(v1 + 2384), (unsigned int)dword_140177064);
      for ( i = 1; i < g_RaidNumberProcessors; ++i )
      {
        v10 = 0;
        v11 = &Pool[(unsigned int)dword_14017705C * i];
        if ( v5 )
        {
          v12 = 0;
          do
          {
            ++v10;
            v13 = 16 * v12++;
            *(_QWORD *)&Pool[v13] += *(_QWORD *)&v11[v13];
            *(_QWORD *)&Pool[v13 + 8] += *(_QWORD *)&v11[v13 + 8];
          }
          while ( v10 < v5 );
        }
      }
      v14 = *(_QWORD *)(v1 + 2408);
      v15 = 0;
      if ( v5 )
      {
        v16 = 0;
        do
        {
          ++v15;
          v17 = 16 * v16++;
          v18 = *(_QWORD *)&Pool[v17] - *(_QWORD *)(v14 + v17);
          v2[(unsigned __int64)v17 / 8] = v18;
          v8 += v18;
          v2[(unsigned __int64)v17 / 8 + 1] = *(_QWORD *)&Pool[v17 + 8] - *(_QWORD *)(v14 + v17 + 8);
        }
        while ( v15 < v5 );
        v48 = v8;
      }
      memmove(*(void **)(v1 + 2408), Pool, (unsigned int)dword_14017705C);
      if ( v8 )
      {
        for ( j = 0; j < 2; ++j )
        {
          v20 = 0;
          while ( 1 )
          {
            v46 = v20;
            if ( v20 >= 9 )
              break;
            v21 = RaidAllocatePool(64, 351, 1700028754, *(_QWORD *)(v1 + 8));
            v22 = *(_QWORD *)(v1 + 8);
            v23 = v21;
            v47 = (STRSAFE_LPSTR)v20;
            v24 = j + v20 + 8LL * j;
            v52[v24] = v21;
            v25 = RaidAllocatePool(64, 351, 1700028754, v22);
            v51[v24] = v25;
            if ( !v23 || !v25 )
              goto LABEL_4;
            v26 = 0;
            v27 = (char *)v52[9 * j + (_QWORD)v47];
            v28 = (char *)v51[9 * j + (_QWORD)v47];
            do
            {
              v54 = 0;
              v56 = 0;
              *(_OWORD *)pszDest = 0;
              *(_OWORD *)pszSrc = 0;
              v29 = 2LL
                  * (j + (unsigned __int16)xmmword_140177020 * (v46 + v26 * (unsigned int)WORD1(xmmword_140177020)));
              StringCchPrintfA(
                pszDest,
                0x14u,
                "%lld",
                v2[2 * j
                 + 2 * (unsigned __int16)xmmword_140177020 * (v46 + v26 * (unsigned int)WORD1(xmmword_140177020))]);
              StringCchPrintfA(pszSrc, 0x14u, "%lld", v2[v29 + 1]);
              StringCchCatA(v27, v30, pszDest);
              StringCchCatA(v28, v31, pszSrc);
              if ( (unsigned int)v26 < 0xD )
              {
                StringCchCatA(v27, v32, ", ");
                StringCchCatA(v28, v33, ", ");
              }
              ++v26;
            }
            while ( v26 < 14 );
            v3 = Pool;
            v20 = v46 + 1;
            v4 = -1073741823;
            v1 = a1;
          }
        }
        v34 = *(const int **)(v1 + 160);
        if ( v34 )
        {
          v34 = (const int *)((char *)v34 + 90);
        }
        else
        {
          v35 = *(_QWORD *)(v1 + 152);
          if ( v35 && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 592LL) + 184LL) & 0x40) != 0 )
            v34 = (const int *)(v35 + 41);
        }
        if ( (byte_140177434 & 8) != 0 )
        {
          v36 = *(_QWORD *)(v1 + 24);
          v37 = &dword_140157D94;
          v38 = &qword_140155FE0;
          if ( v34 )
            v37 = v34;
          if ( *(_QWORD *)(v36 + 5144) )
            v38 = *(__int64 **)(v36 + 5144);
          McTemplateK0quuujjqzssszstuzzxssssssssssssssssssssssssssssssssssss_EtwWriteTransfer(
            (unsigned int)&StorPortEventProvider_Context,
            (unsigned int)IoSizeDistribution,
            0,
            *(_DWORD *)(v36 + 56),
            *(_BYTE *)(v1 + 104),
            *(_BYTE *)(v1 + 105),
            *(_BYTE *)(v1 + 106),
            v1 + 2104,
            v36 + 5128,
            *(_DWORD *)(v1 + 3432),
            *(_QWORD *)(v36 + 4784),
            v1 + 168,
            v1 + 177,
            v1 + 242,
            (__int64)v38,
            (__int64)v37,
            *(_BYTE *)(v1 + 506) & 1,
            2,
            (unsigned int)L"4K, 8K, 16K, 32K, 64K, 128K, 256K, 1M, 1M+",
            (unsigned int)L"128us, 256us, 512us, 1ms, 4ms, 16ms, 64ms, 128ms, 256ms, 512ms, 1000ms, 2000ms, 10000ms, 10000+ms",
            v48,
            v52[0],
            v51[0],
            v52[1],
            v51[1],
            v52[2],
            v51[2],
            v52[3],
            v51[3],
            v52[4],
            v51[4],
            v52[5],
            v51[5],
            v52[6],
            v51[6],
            v52[7],
            v51[7],
            v52[8],
            v51[8],
            v52[9],
            v51[9],
            v52[10],
            v51[10],
            v52[11],
            v51[11],
            v52[12],
            v51[12],
            v52[13],
            v51[13],
            v52[14],
            v51[14],
            v52[15],
            v51[15],
            v52[16],
            v51[16],
            v52[17],
            v51[17]);
        }
      }
    }
    else
    {
LABEL_4:
      v4 = -1073741801;
    }
  }
  else
  {
    v3 = 0;
    v4 = -1073741823;
  }
  v39 = 0;
  do
  {
    v40 = 9 * v39;
    v41 = 0;
    v42 = &v51[9 * v39];
    do
    {
      v43 = (void *)v52[9 * v39 + v41];
      if ( v43 )
      {
        ExFreePoolWithTag(v43, 0x65546152u);
        v52[v40 + v41] = 0;
        v42 = &v51[9 * v39];
      }
      v44 = (void *)v42[v41];
      if ( v44 )
      {
        ExFreePoolWithTag(v44, 0x65546152u);
        v51[v40 + v41] = 0;
        v42 = &v51[9 * v39];
      }
      ++v41;
    }
    while ( v41 != 9 );
    v39 = (unsigned int)(v39 + 1);
  }
  while ( (int)v39 < 2 );
  if ( v2 )
    ExFreePoolWithTag(v2, 0x65546152u);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x65546152u);
  return v4;
}

```

## disassembly

```asm
0x1400e42f4  push    rbp
0x1400e42f6  push    rbx
0x1400e42f7  push    rsi
0x1400e42f8  push    rdi
0x1400e42f9  push    r12
0x1400e42fb  push    r13
0x1400e42fd  push    r14
0x1400e42ff  push    r15
0x1400e4301  lea     rbp, [rsp-128h]
0x1400e4309  sub     rsp, 378h
0x1400e4310  mov     rax, cs:__security_cookie
0x1400e4317  xor     rax, rsp
0x1400e431a  mov     [rbp+160h+var_50], rax
0x1400e4321  mov     r13, rcx
0x1400e4324  mov     [rbp+160h+var_1A8], rcx
0x1400e4328  mov     ebx, 90h
0x1400e432d  lea     rcx, [rbp+160h+var_110]; void *
0x1400e4331  mov     r8d, ebx; Size
0x1400e4334  xor     edx, edx; Val
0x1400e4336  xor     r12d, r12d
0x1400e4339  call    memset_0
0x1400e433e  mov     r8d, ebx; Size
0x1400e4341  lea     rcx, [rbp+160h+var_1A0]; void *
0x1400e4345  xor     edx, edx; Val
0x1400e4347  call    memset_0
0x1400e434c  cmp     [r13+950h], r12
0x1400e4353  jnz     short loc_1400E4363
0x1400e4355  xor     r14d, r14d
0x1400e4358  mov     r15d, 0C0000001h
0x1400e435e  jmp     loc_1400E4968
0x1400e4363  mov     edx, cs:dword_140177064
0x1400e4369  mov     esi, 48h ; 'H'
0x1400e436e  mov     r9, [r13+8]
0x1400e4372  mov     ecx, esi
0x1400e4374  mov     edi, dword ptr cs:qword_140177050+4
0x1400e437a  mov     r8d, 65546152h
0x1400e4380  call    RaidAllocatePool
0x1400e4385  mov     [rbp+160h+var_1B0], rax
0x1400e4389  mov     r14, rax
0x1400e438c  test    rax, rax
0x1400e438f  jnz     short loc_1400E439C
0x1400e4391  mov     r15d, 0C0000017h
0x1400e4397  jmp     loc_1400E4968
0x1400e439c  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e43a3  nop     dword ptr [rax+rax+00h]
0x1400e43a8  mov     ebx, eax
0x1400e43aa  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e43b1  nop     dword ptr [rax+rax+00h]
0x1400e43b6  mov     r9, [r13+8]
0x1400e43ba  neg     ebx
0x1400e43bc  mov     r8d, 65546152h
0x1400e43c2  mov     rcx, rsi
0x1400e43c5  lea     edx, [rax-1]
0x1400e43c8  mov     eax, edi
0x1400e43ca  shl     eax, 4
0x1400e43cd  add     edx, eax
0x1400e43cf  mov     eax, ebx
0x1400e43d1  and     rdx, rax
0x1400e43d4  call    RaidAllocatePool
0x1400e43d9  mov     r12, rax
0x1400e43dc  test    rax, rax
0x1400e43df  jz      short loc_1400E4391
0x1400e43e1  mov     r8d, cs:dword_140177064; Size
0x1400e43e8  mov     r15d, 0C0000001h
0x1400e43ee  mov     rdx, [r13+950h]; Src
0x1400e43f5  xor     ebx, ebx
0x1400e43f7  mov     rcx, r14; void *
0x1400e43fa  mov     [rbp+160h+var_1DC], r15d
0x1400e43fe  mov     [rbp+160h+var_1D0], rbx
0x1400e4402  call    memmove
0x1400e4407  lea     edx, [rbx+1]
0x1400e440a  cmp     cs:g_RaidNumberProcessors, edx
0x1400e4410  jbe     short loc_1400E4458
0x1400e4412  mov     r8d, edx
0x1400e4415  xor     r10d, r10d
0x1400e4418  imul    r8d, cs:dword_14017705C
0x1400e4420  add     r8, r14
0x1400e4423  test    edi, edi
0x1400e4425  jz      short loc_1400E444E
0x1400e4427  xor     r9d, r9d
0x1400e442a  mov     rcx, r9
0x1400e442d  inc     r10d
0x1400e4430  shl     rcx, 4
0x1400e4434  inc     r9
0x1400e4437  mov     rax, [r8+rcx]
0x1400e443b  add     [r14+rcx], rax
0x1400e443f  mov     rax, [r8+rcx+8]
0x1400e4444  add     [r14+rcx+8], rax
0x1400e4449  cmp     r10d, edi
0x1400e444c  jb      short loc_1400E442A
0x1400e444e  inc     edx
0x1400e4450  cmp     edx, cs:g_RaidNumberProcessors
0x1400e4456  jb      short loc_1400E4412
0x1400e4458  mov     r11, [r13+968h]
0x1400e445f  xor     r10d, r10d
0x1400e4462  test    edi, edi
0x1400e4464  jz      short loc_1400E449D
0x1400e4466  xor     r9d, r9d
0x1400e4469  mov     r8, r9
0x1400e446c  inc     r10d
0x1400e446f  shl     r8, 4
0x1400e4473  inc     r9
0x1400e4476  mov     rdx, [r14+r8]
0x1400e447a  sub     rdx, [r11+r8]
0x1400e447e  mov     [r12+r8], rdx
0x1400e4482  add     rbx, rdx
0x1400e4485  mov     rcx, [r14+r8+8]
0x1400e448a  sub     rcx, [r11+r8+8]
0x1400e448f  mov     [r12+r8+8], rcx
0x1400e4494  cmp     r10d, edi
0x1400e4497  jb      short loc_1400E4469
0x1400e4499  mov     [rbp+160h+var_1D0], rbx
0x1400e449d  mov     r8d, cs:dword_14017705C; Size
0x1400e44a4  mov     rdx, r14; Src
0x1400e44a7  mov     rcx, [r13+968h]; void *
0x1400e44ae  call    memmove
0x1400e44b3  test    rbx, rbx
0x1400e44b6  jz      loc_1400E4968
0x1400e44bc  xor     esi, esi
0x1400e44be  cmp     esi, 2
0x1400e44c1  jge     loc_1400E4656
0x1400e44c7  movsxd  rax, esi
0x1400e44ca  lea     rcx, [rbp+160h+var_110]
0x1400e44ce  xor     ebx, ebx
0x1400e44d0  lea     rax, [rax+rax*8]
0x1400e44d4  lea     rcx, [rcx+rax*8]
0x1400e44d8  lea     rax, [rbp+rax*8+160h+var_1A0]
0x1400e44dd  mov     [rbp+160h+var_1C8], rcx
0x1400e44e1  mov     [rbp+160h+var_1C0], rax
0x1400e44e5  mov     [rbp+160h+var_1E0], ebx
0x1400e44e8  cmp     ebx, 9
0x1400e44eb  jge     loc_1400E464F
0x1400e44f1  mov     r9, [r13+8]
0x1400e44f5  mov     edx, 15Fh
0x1400e44fa  mov     ecx, 40h ; '@'
0x1400e44ff  mov     r8d, 65546152h
0x1400e4505  call    RaidAllocatePool
0x1400e450a  mov     r9, [r13+8]
0x1400e450e  mov     rdi, rax
0x1400e4511  movsxd  rcx, ebx
0x1400e4514  mov     edx, 15Fh
0x1400e4519  movsxd  rax, esi
0x1400e451c  mov     r8d, 65546152h
0x1400e4522  mov     [rbp+160h+var_1D8], rcx
0x1400e4526  lea     rbx, [rcx+rax*8]
0x1400e452a  mov     ecx, 40h ; '@'
0x1400e452f  add     rbx, rax
0x1400e4532  mov     [rbp+rbx*8+160h+var_110], rdi
0x1400e4537  call    RaidAllocatePool
0x1400e453c  mov     [rbp+rbx*8+160h+var_1A0], rax
0x1400e4541  test    rdi, rdi
0x1400e4544  jz      loc_1400E4391
0x1400e454a  test    rax, rax
0x1400e454d  jz      loc_1400E4391
0x1400e4553  mov     rax, [rbp+160h+var_1D8]
0x1400e4557  xor     r14d, r14d
0x1400e455a  mov     rcx, [rbp+160h+var_1C8]
0x1400e455e  mov     edi, [rbp+160h+var_1E0]
0x1400e4561  mov     rcx, [rcx+rax*8]
0x1400e4565  mov     [rbp+160h+var_1D8], rcx
0x1400e4569  mov     rcx, [rbp+160h+var_1C0]
0x1400e456d  mov     r15, [rbp+160h+var_1D8]
0x1400e4571  mov     r13, [rcx+rax*8]
0x1400e4575  movzx   ebx, word ptr cs:xmmword_140177020+2
0x1400e457c  lea     r8, aLld; "%lld"
0x1400e4583  imul    ebx, r14d
0x1400e4587  lea     rcx, [rbp+160h+pszDest]; pszDest
0x1400e458e  xor     eax, eax
0x1400e4590  xorps   xmm0, xmm0
0x1400e4593  mov     [rbp+160h+var_70], eax
0x1400e4599  xorps   xmm1, xmm1
0x1400e459c  mov     [rbp+160h+var_58], eax
0x1400e45a2  mov     edx, 14h; cchDest
0x1400e45a7  movzx   eax, word ptr cs:xmmword_140177020
0x1400e45ae  add     ebx, edi
0x1400e45b0  imul    ebx, eax
0x1400e45b3  movups  xmmword ptr [rbp+160h+pszDest], xmm0
0x1400e45ba  movups  xmmword ptr [rbp+160h+pszSrc], xmm1
0x1400e45c1  add     ebx, esi
0x1400e45c3  add     rbx, rbx
0x1400e45c6  mov     r9, [r12+rbx*8]
0x1400e45ca  call    StringCchPrintfA
0x1400e45cf  mov     r9, [r12+rbx*8+8]
0x1400e45d4  lea     r8, aLld; "%lld"
0x1400e45db  mov     edx, 14h; cchDest
0x1400e45e0  lea     rcx, [rbp+160h+pszSrc]; pszDest
0x1400e45e7  call    StringCchPrintfA
0x1400e45ec  lea     r8, [rbp+160h+pszDest]; pszSrc
0x1400e45f3  mov     rcx, r15; pszDest
0x1400e45f6  call    StringCchCatA
0x1400e45fb  lea     r8, [rbp+160h+pszSrc]; pszSrc
0x1400e4602  mov     rcx, r13; pszDest
0x1400e4605  call    StringCchCatA
0x1400e460a  cmp     r14d, 0Dh
0x1400e460e  jnb     short loc_1400E462E
0x1400e4610  lea     r8, asc_14015CCD8; ", "
0x1400e4617  mov     rcx, r15; pszDest
0x1400e461a  call    StringCchCatA
0x1400e461f  lea     r8, asc_14015CCD8; ", "
0x1400e4626  mov     rcx, r13; pszDest
0x1400e4629  call    StringCchCatA
0x1400e462e  inc     r14d
0x1400e4631  cmp     r14d, 0Eh
0x1400e4635  jl      loc_1400E4575
0x1400e463b  mov     r14, [rbp+160h+var_1B0]
0x1400e463f  lea     ebx, [rdi+1]
0x1400e4642  mov     r15d, [rbp+160h+var_1DC]
0x1400e4646  mov     r13, [rbp+160h+var_1A8]
0x1400e464a  jmp     loc_1400E44E5
0x1400e464f  inc     esi
0x1400e4651  jmp     loc_1400E44BE
0x1400e4656  mov     rdx, [r13+0A0h]
0x1400e465d  test    rdx, rdx
0x1400e4660  jz      short loc_1400E4668
0x1400e4662  add     rdx, 5Ah ; 'Z'
0x1400e4666  jmp     short loc_1400E468D
0x1400e4668  mov     r8, [r13+98h]
0x1400e466f  test    r8, r8
0x1400e4672  jz      short loc_1400E468D
0x1400e4674  mov     rax, [r13+18h]
0x1400e4678  mov     rcx, [rax+250h]
0x1400e467f  mov     eax, [rcx+0B8h]
0x1400e4685  test    al, 40h
0x1400e4687  jz      short loc_1400E468D
0x1400e4689  lea     rdx, [r8+29h]
0x1400e468d  test    cs:byte_140177434, 8
0x1400e4694  jz      loc_1400E4968
0x1400e469a  mov     rsi, [r13+18h]
0x1400e469e  lea     rdi, dword_140157D94
0x1400e46a5  movzx   ecx, byte ptr [r13+1FAh]
0x1400e46ad  lea     r9, qword_140155FE0
0x1400e46b4  test    rdx, rdx
0x1400e46b7  lea     r8, [r13+0B1h]
0x1400e46be  lea     r10, [r13+0A8h]
0x1400e46c5  mov     rax, [rsi+1418h]
0x1400e46cc  lea     r11, [rsi+1408h]
0x1400e46d3  cmovnz  rdi, rdx
0x1400e46d7  lea     rbx, [r13+838h]
0x1400e46de  test    rax, rax
0x1400e46e1  lea     rdx, [r13+0F2h]
0x1400e46e8  cmovnz  r9, rax
0x1400e46ec  mov     rax, [rbp+160h+var_118]
0x1400e46f0  mov     [rsp+3B0h+var_1F0], rax
0x1400e46f8  and     ecx, 1
0x1400e46fb  mov     rax, [rbp+160h+var_88]
0x1400e4702  mov     [rsp+3B0h+var_1F8], rax
0x1400e470a  mov     rax, [rbp+160h+var_120]
0x1400e470e  mov     [rsp+3B0h+var_200], rax
0x1400e4716  mov     rax, [rbp+160h+var_90]
0x1400e471d  mov     [rsp+3B0h+var_208], rax
0x1400e4725  mov     rax, [rbp+160h+var_128]
0x1400e4729  mov     [rsp+3B0h+var_210], rax
0x1400e4731  mov     rax, [rbp+160h+var_98]
0x1400e4738  mov     [rsp+3B0h+var_218], rax
0x1400e4740  mov     rax, [rbp+160h+var_130]
0x1400e4744  mov     [rsp+3B0h+var_220], rax
0x1400e474c  mov     rax, [rbp+160h+var_A0]
0x1400e4753  mov     [rsp+3B0h+var_228], rax
0x1400e475b  mov     rax, [rbp+160h+var_138]
0x1400e475f  mov     [rsp+3B0h+var_230], rax
0x1400e4767  mov     rax, [rbp+160h+var_A8]
0x1400e476e  mov     [rsp+3B0h+var_238], rax
0x1400e4776  mov     rax, [rbp+160h+var_140]
0x1400e477a  mov     [rsp+3B0h+var_240], rax
0x1400e4782  mov     rax, [rbp+160h+var_B0]
0x1400e4789  mov     [rsp+3B0h+var_248], rax
0x1400e4791  mov     rax, [rbp+160h+var_148]
0x1400e4795  mov     [rsp+3B0h+var_250], rax
0x1400e479d  mov     rax, [rbp+160h+var_B8]
0x1400e47a4  mov     [rsp+3B0h+var_258], rax
0x1400e47ac  mov     rax, [rbp+160h+var_150]
0x1400e47b0  mov     [rsp+3B0h+var_260], rax
0x1400e47b8  mov     rax, [rbp+160h+var_C0]
0x1400e47bf  mov     [rsp+3B0h+var_268], rax
0x1400e47c7  mov     rax, [rbp+160h+var_158]
0x1400e47cb  mov     [rsp+3B0h+var_270], rax
0x1400e47d3  mov     rax, [rbp+160h+var_C8]
0x1400e47da  mov     [rsp+3B0h+var_278], rax
0x1400e47e2  mov     rax, [rbp+160h+var_160]
0x1400e47e6  mov     [rsp+3B0h+var_280], rax
0x1400e47ee  mov     rax, [rbp+160h+var_D0]
0x1400e47f5  mov     [rsp+3B0h+var_288], rax
0x1400e47fd  mov     rax, [rbp+160h+var_168]
0x1400e4801  mov     [rsp+3B0h+var_290], rax
0x1400e4809  mov     rax, [rbp+160h+var_D8]
0x1400e4810  mov     [rsp+3B0h+var_298], rax
0x1400e4818  mov     rax, [rbp+160h+var_170]
0x1400e481c  mov     [rsp+3B0h+var_2A0], rax
0x1400e4824  mov     rax, [rbp+160h+var_E0]
0x1400e482b  mov     [rsp+3B0h+var_2A8], rax
0x1400e4833  mov     rax, [rbp+160h+var_178]
0x1400e4837  mov     [rsp+3B0h+var_2B0], rax
0x1400e483f  mov     rax, [rbp+160h+var_E8]
0x1400e4843  mov     [rsp+3B0h+var_2B8], rax
0x1400e484b  mov     rax, [rbp+160h+var_180]
0x1400e484f  mov     [rsp+3B0h+var_2C0], rax
0x1400e4857  mov     rax, [rbp+160h+var_F0]
0x1400e485b  mov     [rsp+3B0h+var_2C8], rax
0x1400e4863  mov     rax, [rbp+160h+var_188]
0x1400e4867  mov     [rsp+3B0h+var_2D0], rax
  ... truncated ...
```
