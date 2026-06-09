# StorpTelemetryNvmeSendNamespaceIoSizeDistributionData

- ea: `0x1400e0968`
- end: `0x1400e11bb`
- name: `StorpTelemetryNvmeSendNamespaceIoSizeDistributionData`
- size: `2131`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400e11c4`

## callees

- `0x1400290b0`
- `0x1400d40f0`
- `0x1400e0968`
- `0x1400e6374`
- `0x1400e6414`
- `0x14014b400`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400e10fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e112d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e116f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1188`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e10fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e112d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e116f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1188`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e0a65`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e0a73`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e0a65`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e0a73`

## pseudocode

```c
__int64 __fastcall StorpTelemetryNvmeSendNamespaceIoSizeDistributionData(__int64 a1)
{
  __int64 v1; // r15
  _QWORD *v2; // r12
  __int64 v3; // rax
  void *v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // edi
  ULONG RecommendedSharedDataAlignment; // ebx
  ULONG v8; // eax
  __int64 v9; // rbx
  unsigned int i; // edx
  unsigned int v11; // r10d
  char *v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v15; // r10d
  __int64 v16; // r11
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rdx
  int j; // r13d
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // esi
  char *v28; // r14
  char *v29; // r15
  __int64 v30; // rbx
  size_t v31; // rdx
  size_t v32; // rdx
  size_t v33; // rdx
  size_t v34; // rdx
  __int64 v35; // r11
  _WORD *v36; // rax
  __int16 v37; // ax
  char v38; // al
  unsigned __int8 v39; // cl
  char v40; // cl
  unsigned __int8 v41; // cl
  char v42; // cl
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // cl
  __int64 v45; // rax
  const int *v46; // r8
  __int64 v47; // rdi
  __int64 v48; // r15
  __int64 v49; // rbx
  __int64 *v50; // rax
  void *v51; // rcx
  void *v52; // rcx
  int v54; // [rsp+1C0h] [rbp-80h]
  STRSAFE_LPSTR v55; // [rsp+1C8h] [rbp-78h]
  char v56; // [rsp+1D0h] [rbp-70h]
  char *Pool; // [rsp+1F0h] [rbp-50h]
  __int64 v59[18]; // [rsp+200h] [rbp-40h] BYREF
  __int64 v60[18]; // [rsp+290h] [rbp+50h] BYREF
  char v61[13]; // [rsp+320h] [rbp+E0h] BYREF
  int v62; // [rsp+32Dh] [rbp+EDh]
  __int64 v63; // [rsp+338h] [rbp+F8h] BYREF
  char v64; // [rsp+340h] [rbp+100h]
  char pszDest[16]; // [rsp+348h] [rbp+108h] BYREF
  int v66; // [rsp+358h] [rbp+118h]
  char pszSrc[16]; // [rsp+360h] [rbp+120h] BYREF
  int v68; // [rsp+370h] [rbp+130h]
  _OWORD v69[3]; // [rsp+378h] [rbp+138h] BYREF

  v1 = a1;
  v2 = 0;
  memset_0(v60, 0, sizeof(v60));
  memset_0(v59, 0, sizeof(v59));
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v3 = *(_QWORD *)(v1 + 624);
  strcpy(v61, "PCI vendor: ");
  memset(v69, 0, 41);
  if ( *(_QWORD *)(v3 + 16) )
  {
    v6 = HIDWORD(qword_140177050);
    Pool = (char *)RaidAllocatePool(72, (unsigned int)dword_140177064, 1700028754, *(_QWORD *)(v1 + 8));
    v4 = Pool;
    if ( Pool
      && (RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment(),
          v8 = KeGetRecommendedSharedDataAlignment(),
          (v2 = (_QWORD *)RaidAllocatePool(
                            72,
                            -RecommendedSharedDataAlignment & (16 * v6 + v8 - 1),
                            1700028754,
                            *(_QWORD *)(v1 + 8))) != 0) )
    {
      v5 = -1073741823;
      v9 = 0;
      v56 = 0;
      memmove(Pool, *(const void **)(*(_QWORD *)(v1 + 624) + 16LL), (unsigned int)dword_140177064);
      for ( i = 1; i < g_RaidNumberProcessors; ++i )
      {
        v11 = 0;
        v12 = &Pool[(unsigned int)dword_14017705C * i];
        if ( v6 )
        {
          v13 = 0;
          do
          {
            ++v11;
            v14 = 16 * v13++;
            *(_QWORD *)&Pool[v14] += *(_QWORD *)&v12[v14];
            *(_QWORD *)&Pool[v14 + 8] += *(_QWORD *)&v12[v14 + 8];
          }
          while ( v11 < v6 );
        }
      }
      v15 = 0;
      v16 = *(_QWORD *)(*(_QWORD *)(v1 + 624) + 40LL);
      if ( v6 )
      {
        v17 = 0;
        do
        {
          ++v15;
          v18 = 16 * v17++;
          v19 = *(_QWORD *)&Pool[v18] - *(_QWORD *)(v18 + v16);
          v2[(unsigned __int64)v18 / 8] = v19;
          v9 += v19;
          v2[(unsigned __int64)v18 / 8 + 1] = *(_QWORD *)&Pool[v18 + 8] - *(_QWORD *)(v18 + v16 + 8);
        }
        while ( v15 < v6 );
        v56 = v9;
      }
      memmove(*(void **)(*(_QWORD *)(v1 + 624) + 40LL), Pool, (unsigned int)dword_14017705C);
      if ( v9 )
      {
        for ( j = 0; j < 2; ++j )
        {
          v21 = 0;
          while ( 1 )
          {
            v54 = v21;
            if ( v21 >= 9 )
              break;
            v22 = RaidAllocatePool(64, 351, 1700028754, *(_QWORD *)(v1 + 8));
            v23 = *(_QWORD *)(v1 + 8);
            v24 = v22;
            v55 = (STRSAFE_LPSTR)v21;
            v25 = j + v21 + 8LL * j;
            v60[v25] = v22;
            v26 = RaidAllocatePool(64, 351, 1700028754, v23);
            v59[v25] = v26;
            if ( !v24 || !v26 )
              goto LABEL_4;
            v27 = 0;
            v28 = (char *)v60[9 * j + (_QWORD)v55];
            v29 = (char *)v59[9 * j + (_QWORD)v55];
            do
            {
              v66 = 0;
              v68 = 0;
              *(_OWORD *)pszDest = 0;
              *(_OWORD *)pszSrc = 0;
              v30 = 2LL
                  * (j + (unsigned __int16)xmmword_140177020 * (v54 + v27 * (unsigned int)WORD1(xmmword_140177020)));
              StringCchPrintfA(
                pszDest,
                0x14u,
                "%lld",
                v2[2 * j
                 + 2 * (unsigned __int16)xmmword_140177020 * (v54 + v27 * (unsigned int)WORD1(xmmword_140177020))]);
              StringCchPrintfA(pszSrc, 0x14u, "%lld", v2[v30 + 1]);
              StringCchCatA(v28, v31, pszDest);
              StringCchCatA(v29, v32, pszSrc);
              if ( (unsigned int)v27 < 0xD )
              {
                StringCchCatA(v28, v33, ", ");
                StringCchCatA(v29, v34, ", ");
              }
              ++v27;
            }
            while ( v27 < 14 );
            v4 = Pool;
            v21 = v54 + 1;
            v5 = -1073741823;
            v1 = a1;
          }
        }
        v35 = *(_QWORD *)(v1 + 16);
        if ( v35 )
        {
          v36 = *(_WORD **)(v35 + 592);
          if ( v36 )
          {
            v37 = *v36 >> 12;
            if ( (unsigned __int8)v37 > 9u )
              v38 = v37 + 55;
            else
              v38 = v37 + 48;
            v61[12] = v38;
            v39 = *(_BYTE *)(*(_QWORD *)(v35 + 592) + 1LL) & 0xF;
            if ( v39 > 9u )
              v40 = v39 + 55;
            else
              v40 = v39 + 48;
            LOBYTE(v62) = v40;
            v41 = (**(_BYTE **)(v35 + 592) >> 4) & 0xF;
            if ( v41 > 9u )
              v42 = v41 + 55;
            else
              v42 = v41 + 48;
            BYTE1(v62) = v42;
            v43 = **(_BYTE **)(v35 + 592) & 0xF;
            if ( v43 > 9u )
              v44 = v43 + 55;
            else
              v44 = v43 + 48;
            HIWORD(v62) = v44;
            v45 = *(_QWORD *)(v35 + 592);
            v69[0] = *(_OWORD *)(v45 + 24);
            v69[1] = *(_OWORD *)(v45 + 40);
            *(_QWORD *)&v69[2] = *(_QWORD *)(v45 + 56);
            v63 = *(_QWORD *)(*(_QWORD *)(v35 + 592) + 64LL);
          }
        }
        if ( (byte_14017743A & 0x40) != 0 )
        {
          v46 = &dword_140157D94;
          if ( *(_QWORD *)(v35 + 752) )
            v46 = *(const int **)(v35 + 752);
          McTemplateK0qjzshqussssjqzzxssssssssssssssssssssssssssssssssssss_EtwWriteTransfer(
            (unsigned int)&StorPortEventProvider_Context,
            (unsigned int)NVMeNamespaceIoSizeDistribution,
            0,
            *(_DWORD *)(*(_QWORD *)(v35 + 128) + 56LL),
            *(_QWORD *)(v35 + 128) + 1048LL,
            *(_QWORD *)(*(_QWORD *)(v35 + 128) + 1032LL),
            *(_QWORD *)(v35 + 792),
            *(_WORD *)(v35 + 4),
            *(_DWORD *)(v1 + 56),
            *(_BYTE *)(v35 + 744),
            (__int64)v46,
            (__int64)v61,
            (__int64)v69,
            (__int64)&v63,
            v1 + 160,
            (*(_BYTE *)(v35 + 136) & 2) != 0 ? 20 : 17,
            (unsigned int)L"4K, 8K, 16K, 32K, 64K, 128K, 256K, 1M, 1M+",
            (unsigned int)L"128us, 256us, 512us, 1ms, 4ms, 16ms, 64ms, 128ms, 256ms, 512ms, 1000ms, 2000ms, 10000ms, 10000+ms",
            v56,
            v60[0],
            v59[0],
            v60[1],
            v59[1],
            v60[2],
            v59[2],
            v60[3],
            v59[3],
            v60[4],
            v59[4],
            v60[5],
            v59[5],
            v60[6],
            v59[6],
            v60[7],
            v59[7],
            v60[8],
            v59[8],
            v60[9],
            v59[9],
            v60[10],
            v59[10],
            v60[11],
            v59[11],
            v60[12],
            v59[12],
            v60[13],
            v59[13],
            v60[14],
            v59[14],
            v60[15],
            v59[15],
            v60[16],
            v59[16],
            v60[17],
            v59[17]);
        }
      }
    }
    else
    {
LABEL_4:
      v5 = -1073741801;
    }
  }
  else
  {
    v4 = 0;
    v5 = -1073741823;
  }
  v47 = 0;
  do
  {
    v48 = 9 * v47;
    v49 = 0;
    v50 = &v59[9 * v47];
    do
    {
      v51 = (void *)v60[9 * v47 + v49];
      if ( v51 )
      {
        ExFreePoolWithTag(v51, 0x65546152u);
        v60[v48 + v49] = 0;
        v50 = &v59[9 * v47];
      }
      v52 = (void *)v50[v49];
      if ( v52 )
      {
        ExFreePoolWithTag(v52, 0x65546152u);
        v59[v48 + v49] = 0;
        v50 = &v59[9 * v47];
      }
      ++v49;
    }
    while ( v49 != 9 );
    v47 = (unsigned int)(v47 + 1);
  }
  while ( (int)v47 < 2 );
  if ( v2 )
    ExFreePoolWithTag(v2, 0x65546152u);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x65546152u);
  return v5;
}

```

## disassembly

```asm
0x1400e0968  push    rbp
0x1400e096a  push    rbx
0x1400e096b  push    rsi
0x1400e096c  push    rdi
0x1400e096d  push    r12
0x1400e096f  push    r13
0x1400e0971  push    r14
0x1400e0973  push    r15
0x1400e0975  lea     rbp, [rsp-178h]
0x1400e097d  sub     rsp, 3B8h
0x1400e0984  mov     rax, cs:__security_cookie
0x1400e098b  xor     rax, rsp
0x1400e098e  mov     [rbp+1B0h+var_48], rax
0x1400e0995  mov     r15, rcx
0x1400e0998  mov     [rbp+1B0h+var_1F8], rcx
0x1400e099c  mov     ebx, 90h
0x1400e09a1  lea     rcx, [rbp+1B0h+var_160]; void *
0x1400e09a5  mov     r8d, ebx; Size
0x1400e09a8  xor     edx, edx; Val
0x1400e09aa  xor     r12d, r12d
0x1400e09ad  call    memset_0
0x1400e09b2  mov     r8d, ebx; Size
0x1400e09b5  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x1400e09b9  xor     edx, edx; Val
0x1400e09bb  call    memset_0
0x1400e09c0  mov     eax, dword ptr cs:aPciVendor+8; "or: "
0x1400e09c6  movsd   xmm0, qword ptr cs:aPciVendor; "PCI vendor: "
0x1400e09ce  mov     dword ptr [rbp+1B0h+var_D0+8], eax
0x1400e09d4  xor     eax, eax
0x1400e09d6  mov     [rbp+1B0h+var_C3], eax
0x1400e09dc  mov     [rbp+1B0h+var_B8], rax
0x1400e09e3  mov     [rbp+1B0h+var_B0], al
0x1400e09e9  mov     rax, [r15+270h]
0x1400e09f0  movsd   qword ptr [rbp+1B0h+var_D0], xmm0
0x1400e09f8  xorps   xmm0, xmm0
0x1400e09fb  movups  [rbp+1B0h+var_68], xmm0
0x1400e0a02  mov     [rbp+1B0h+var_D0+0Ch], r12b
0x1400e0a09  movups  [rbp+1B0h+var_78], xmm0
0x1400e0a10  movups  [rbp+1B0h+var_68+9], xmm0
0x1400e0a17  cmp     [rax+10h], r12
0x1400e0a1b  jnz     short loc_1400E0A2A
0x1400e0a1d  xor     esi, esi
0x1400e0a1f  mov     r14d, 0C0000001h
0x1400e0a25  jmp     loc_1400E10D6
0x1400e0a2a  mov     edx, cs:dword_140177064
0x1400e0a30  mov     r14d, 48h ; 'H'
0x1400e0a36  mov     r9, [r15+8]
0x1400e0a3a  mov     ecx, r14d
0x1400e0a3d  mov     edi, dword ptr cs:qword_140177050+4
0x1400e0a43  mov     r8d, 65546152h
0x1400e0a49  call    RaidAllocatePool
0x1400e0a4e  mov     [rbp+1B0h+var_200], rax
0x1400e0a52  mov     rsi, rax
0x1400e0a55  test    rax, rax
0x1400e0a58  jnz     short loc_1400E0A65
0x1400e0a5a  mov     r14d, 0C0000017h
0x1400e0a60  jmp     loc_1400E10D6
0x1400e0a65  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e0a6c  nop     dword ptr [rax+rax+00h]
0x1400e0a71  mov     ebx, eax
0x1400e0a73  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e0a7a  nop     dword ptr [rax+rax+00h]
0x1400e0a7f  mov     r9, [r15+8]
0x1400e0a83  neg     ebx
0x1400e0a85  mov     r8d, 65546152h
0x1400e0a8b  mov     rcx, r14
0x1400e0a8e  lea     edx, [rax-1]
0x1400e0a91  mov     eax, edi
0x1400e0a93  shl     eax, 4
0x1400e0a96  add     edx, eax
0x1400e0a98  mov     eax, ebx
0x1400e0a9a  and     rdx, rax
0x1400e0a9d  call    RaidAllocatePool
0x1400e0aa2  mov     r12, rax
0x1400e0aa5  test    rax, rax
0x1400e0aa8  jz      short loc_1400E0A5A
0x1400e0aaa  mov     rdx, [r15+270h]
0x1400e0ab1  mov     r14d, 0C0000001h
0x1400e0ab7  mov     r8d, cs:dword_140177064; Size
0x1400e0abe  xor     ebx, ebx
0x1400e0ac0  mov     rcx, rsi; void *
0x1400e0ac3  mov     [rbp+1B0h+var_22C], r14d
0x1400e0ac7  mov     [rbp+1B0h+var_220], rbx
0x1400e0acb  mov     rdx, [rdx+10h]; Src
0x1400e0acf  call    memmove
0x1400e0ad4  lea     edx, [rbx+1]
0x1400e0ad7  cmp     cs:g_RaidNumberProcessors, edx
0x1400e0add  jbe     short loc_1400E0B25
0x1400e0adf  mov     r8d, edx
0x1400e0ae2  xor     r10d, r10d
0x1400e0ae5  imul    r8d, cs:dword_14017705C
0x1400e0aed  add     r8, rsi
0x1400e0af0  test    edi, edi
0x1400e0af2  jz      short loc_1400E0B1B
0x1400e0af4  xor     r9d, r9d
0x1400e0af7  mov     rcx, r9
0x1400e0afa  inc     r10d
0x1400e0afd  shl     rcx, 4
0x1400e0b01  inc     r9
0x1400e0b04  mov     rax, [rcx+r8]
0x1400e0b08  add     [rcx+rsi], rax
0x1400e0b0c  mov     rax, [rcx+r8+8]
0x1400e0b11  add     [rcx+rsi+8], rax
0x1400e0b16  cmp     r10d, edi
0x1400e0b19  jb      short loc_1400E0AF7
0x1400e0b1b  inc     edx
0x1400e0b1d  cmp     edx, cs:g_RaidNumberProcessors
0x1400e0b23  jb      short loc_1400E0ADF
0x1400e0b25  mov     rax, [r15+270h]
0x1400e0b2c  xor     r10d, r10d
0x1400e0b2f  mov     r11, [rax+28h]
0x1400e0b33  test    edi, edi
0x1400e0b35  jz      short loc_1400E0B6E
0x1400e0b37  xor     r9d, r9d
0x1400e0b3a  mov     r8, r9
0x1400e0b3d  inc     r10d
0x1400e0b40  shl     r8, 4
0x1400e0b44  inc     r9
0x1400e0b47  mov     rdx, [r8+rsi]
0x1400e0b4b  sub     rdx, [r8+r11]
0x1400e0b4f  mov     [r12+r8], rdx
0x1400e0b53  add     rbx, rdx
0x1400e0b56  mov     rcx, [r8+rsi+8]
0x1400e0b5b  sub     rcx, [r8+r11+8]
0x1400e0b60  mov     [r12+r8+8], rcx
0x1400e0b65  cmp     r10d, edi
0x1400e0b68  jb      short loc_1400E0B3A
0x1400e0b6a  mov     [rbp+1B0h+var_220], rbx
0x1400e0b6e  mov     rcx, [r15+270h]
0x1400e0b75  mov     rdx, rsi; Src
0x1400e0b78  mov     r8d, cs:dword_14017705C; Size
0x1400e0b7f  mov     rcx, [rcx+28h]; void *
0x1400e0b83  call    memmove
0x1400e0b88  test    rbx, rbx
0x1400e0b8b  jz      loc_1400E10D6
0x1400e0b91  xor     r13d, r13d
0x1400e0b94  cmp     r13d, 2
0x1400e0b98  jge     loc_1400E0D2A
0x1400e0b9e  movsxd  rax, r13d
0x1400e0ba1  lea     rcx, [rbp+1B0h+var_160]
0x1400e0ba5  xor     ebx, ebx
0x1400e0ba7  lea     rax, [rax+rax*8]
0x1400e0bab  lea     rcx, [rcx+rax*8]
0x1400e0baf  lea     rax, [rbp+rax*8+1B0h+var_1F0]
0x1400e0bb4  mov     [rbp+1B0h+var_218], rcx
0x1400e0bb8  mov     [rbp+1B0h+var_210], rax
0x1400e0bbc  mov     [rbp+1B0h+var_230], ebx
0x1400e0bbf  cmp     ebx, 9
0x1400e0bc2  jge     loc_1400E0D22
0x1400e0bc8  mov     r9, [r15+8]
0x1400e0bcc  mov     edx, 15Fh
0x1400e0bd1  mov     ecx, 40h ; '@'
0x1400e0bd6  mov     r8d, 65546152h
0x1400e0bdc  call    RaidAllocatePool
0x1400e0be1  mov     r9, [r15+8]
0x1400e0be5  mov     rdi, rax
0x1400e0be8  movsxd  rcx, ebx
0x1400e0beb  mov     edx, 15Fh
0x1400e0bf0  movsxd  rax, r13d
0x1400e0bf3  mov     r8d, 65546152h
0x1400e0bf9  mov     [rbp+1B0h+var_228], rcx
0x1400e0bfd  lea     rbx, [rcx+rax*8]
0x1400e0c01  mov     ecx, 40h ; '@'
0x1400e0c06  add     rbx, rax
0x1400e0c09  mov     [rbp+rbx*8+1B0h+var_160], rdi
0x1400e0c0e  call    RaidAllocatePool
0x1400e0c13  mov     [rbp+rbx*8+1B0h+var_1F0], rax
0x1400e0c18  test    rdi, rdi
0x1400e0c1b  jz      loc_1400E0A5A
0x1400e0c21  test    rax, rax
0x1400e0c24  jz      loc_1400E0A5A
0x1400e0c2a  mov     rax, [rbp+1B0h+var_228]
0x1400e0c2e  xor     esi, esi
0x1400e0c30  mov     rcx, [rbp+1B0h+var_218]
0x1400e0c34  mov     edi, [rbp+1B0h+var_230]
0x1400e0c37  mov     rcx, [rcx+rax*8]
0x1400e0c3b  mov     [rbp+1B0h+var_228], rcx
0x1400e0c3f  mov     rcx, [rbp+1B0h+var_210]
0x1400e0c43  mov     r14, [rbp+1B0h+var_228]
0x1400e0c47  mov     r15, [rcx+rax*8]
0x1400e0c4b  movzx   ebx, word ptr cs:xmmword_140177020+2
0x1400e0c52  lea     r8, aLld; "%lld"
0x1400e0c59  imul    ebx, esi
0x1400e0c5c  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x1400e0c63  xor     eax, eax
0x1400e0c65  xorps   xmm0, xmm0
0x1400e0c68  mov     [rbp+1B0h+var_98], eax
0x1400e0c6e  xorps   xmm1, xmm1
0x1400e0c71  mov     [rbp+1B0h+var_80], eax
0x1400e0c77  mov     edx, 14h; cchDest
0x1400e0c7c  movzx   eax, word ptr cs:xmmword_140177020
0x1400e0c83  add     ebx, edi
0x1400e0c85  imul    ebx, eax
0x1400e0c88  movups  xmmword ptr [rbp+1B0h+pszDest], xmm0
0x1400e0c8f  movups  xmmword ptr [rbp+1B0h+pszSrc], xmm1
0x1400e0c96  add     ebx, r13d
0x1400e0c99  add     rbx, rbx
0x1400e0c9c  mov     r9, [r12+rbx*8]
0x1400e0ca0  call    StringCchPrintfA
0x1400e0ca5  mov     r9, [r12+rbx*8+8]
0x1400e0caa  lea     r8, aLld; "%lld"
0x1400e0cb1  mov     edx, 14h; cchDest
0x1400e0cb6  lea     rcx, [rbp+1B0h+pszSrc]; pszDest
0x1400e0cbd  call    StringCchPrintfA
0x1400e0cc2  lea     r8, [rbp+1B0h+pszDest]; pszSrc
0x1400e0cc9  mov     rcx, r14; pszDest
0x1400e0ccc  call    StringCchCatA
0x1400e0cd1  lea     r8, [rbp+1B0h+pszSrc]; pszSrc
0x1400e0cd8  mov     rcx, r15; pszDest
0x1400e0cdb  call    StringCchCatA
0x1400e0ce0  cmp     esi, 0Dh
0x1400e0ce3  jnb     short loc_1400E0D03
0x1400e0ce5  lea     r8, asc_14015CCD8; ", "
0x1400e0cec  mov     rcx, r14; pszDest
0x1400e0cef  call    StringCchCatA
0x1400e0cf4  lea     r8, asc_14015CCD8; ", "
0x1400e0cfb  mov     rcx, r15; pszDest
0x1400e0cfe  call    StringCchCatA
0x1400e0d03  inc     esi
0x1400e0d05  cmp     esi, 0Eh
0x1400e0d08  jl      loc_1400E0C4B
0x1400e0d0e  mov     rsi, [rbp+1B0h+var_200]
0x1400e0d12  lea     ebx, [rdi+1]
0x1400e0d15  mov     r14d, [rbp+1B0h+var_22C]
0x1400e0d19  mov     r15, [rbp+1B0h+var_1F8]
0x1400e0d1d  jmp     loc_1400E0BBC
0x1400e0d22  inc     r13d
0x1400e0d25  jmp     loc_1400E0B94
0x1400e0d2a  mov     r11, [r15+10h]
0x1400e0d2e  test    r11, r11
0x1400e0d31  jz      loc_1400E0E08
0x1400e0d37  mov     rax, [r11+250h]
0x1400e0d3e  test    rax, rax
0x1400e0d41  jz      loc_1400E0E08
0x1400e0d47  movzx   eax, word ptr [rax]
0x1400e0d4a  mov     dl, 37h ; '7'
0x1400e0d4c  shr     ax, 0Ch
0x1400e0d50  mov     r8b, 30h ; '0'
0x1400e0d53  cmp     al, 9
0x1400e0d55  ja      short loc_1400E0D5C
0x1400e0d57  add     al, r8b
0x1400e0d5a  jmp     short loc_1400E0D5E
0x1400e0d5c  add     al, dl
0x1400e0d5e  mov     [rbp+1B0h+var_D0+0Ch], al
0x1400e0d64  mov     r9b, 0Fh
0x1400e0d67  mov     rax, [r11+250h]
0x1400e0d6e  mov     cl, [rax+1]
0x1400e0d71  and     cl, r9b
0x1400e0d74  cmp     cl, 9
0x1400e0d77  ja      short loc_1400E0D7E
0x1400e0d79  add     cl, r8b
0x1400e0d7c  jmp     short loc_1400E0D80
0x1400e0d7e  add     cl, dl
0x1400e0d80  mov     byte ptr [rbp+1B0h+var_C3], cl
0x1400e0d86  mov     rax, [r11+250h]
0x1400e0d8d  mov     cl, [rax]
0x1400e0d8f  shr     cl, 4
0x1400e0d92  and     cl, r9b
0x1400e0d95  cmp     cl, 9
0x1400e0d98  ja      short loc_1400E0D9F
0x1400e0d9a  add     cl, r8b
0x1400e0d9d  jmp     short loc_1400E0DA1
0x1400e0d9f  add     cl, dl
0x1400e0da1  mov     byte ptr [rbp+1B0h+var_C3+1], cl
0x1400e0da7  mov     rax, [r11+250h]
0x1400e0dae  mov     cl, [rax]
0x1400e0db0  and     cl, r9b
0x1400e0db3  cmp     cl, 9
0x1400e0db6  ja      short loc_1400E0DBD
0x1400e0db8  add     cl, r8b
0x1400e0dbb  jmp     short loc_1400E0DBF
0x1400e0dbd  add     cl, dl
0x1400e0dbf  mov     byte ptr [rbp+1B0h+var_C3+2], cl
0x1400e0dc5  mov     byte ptr [rbp+1B0h+var_C3+3], 0
0x1400e0dcc  mov     rax, [r11+250h]
0x1400e0dd3  movups  xmm0, xmmword ptr [rax+18h]
0x1400e0dd7  movups  [rbp+1B0h+var_78], xmm0
0x1400e0dde  movups  xmm1, xmmword ptr [rax+28h]
0x1400e0de2  movups  [rbp+1B0h+var_68], xmm1
0x1400e0de9  movsd   xmm0, qword ptr [rax+38h]
0x1400e0dee  movsd   [rbp+1B0h+var_58], xmm0
0x1400e0df6  mov     rax, [r11+250h]
0x1400e0dfd  mov     rcx, [rax+40h]
0x1400e0e01  mov     [rbp+1B0h+var_B8], rcx
0x1400e0e08  test    cs:byte_14017743A, 40h
0x1400e0e0f  jz      loc_1400E10D6
0x1400e0e15  mov     al, [r11+88h]
0x1400e0e1c  lea     r8, dword_140157D94
0x1400e0e23  and     al, 2
0x1400e0e25  mov     r9, [r11+80h]
0x1400e0e2c  neg     al
0x1400e0e2e  lea     rcx, [r15+0A0h]
0x1400e0e35  mov     rax, [r11+2F0h]
0x1400e0e3c  sbb     edx, edx
0x1400e0e3e  and     edx, 3
0x1400e0e41  lea     r10, [r9+418h]
0x1400e0e48  add     edx, 11h
0x1400e0e4b  test    rax, rax
0x1400e0e4e  cmovnz  r8, rax
0x1400e0e52  mov     rax, [rbp+1B0h+var_168]
  ... truncated ...
```
