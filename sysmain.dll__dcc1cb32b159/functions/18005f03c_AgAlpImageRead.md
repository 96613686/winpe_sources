# AgAlpImageRead

- ea: `0x18005f03c`
- end: `0x18005f445`
- name: `AgAlpImageRead`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005ee60`

## callees

- `0x18002341c`
- `0x18004e068`
- `0x18005f03c`
- `0x180067398`
- `0x180067740`
- `0x180078746`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18005f07b`
- `ntdll!NtQueryInformationThread` at `0x18005f07b`
- `ntdll!RtlNtStatusToDosError` at `0x18005f087`
- `ntdll!RtlNtStatusToDosError` at `0x18005f087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f05d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f098`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f0f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f05d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f098`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f0f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f421`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f29e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f29e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f189`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f189`

## pseudocode

```c
__int64 __fastcall AgAlpImageRead(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  _QWORD *v5; // rbx
  HANDLE CurrentThread; // rax
  int v10; // eax
  int v11; // r12d
  HANDLE v12; // rax
  unsigned int v13; // edi
  __int64 v14; // r15
  unsigned int v15; // edi
  HANDLE v16; // rax
  unsigned int v17; // edi
  _OWORD *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // r11
  int v21; // r8d
  __int64 v22; // r9
  _QWORD *v23; // rdi
  __int64 v24; // r10
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // r12d
  __int64 v31; // rbp
  __int64 v32; // rdi
  _DWORD *v33; // rdx
  void *v34; // r8
  HANDLE v35; // rax
  int ThreadInformation; // [rsp+30h] [rbp-58h] BYREF
  __int64 v38; // [rsp+38h] [rbp-50h]

  v5 = 0;
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v10 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v10 >= 0 )
  {
    v11 = ThreadInformation;
  }
  else
  {
    RtlNtStatusToDosError(v10);
    v11 = 8;
  }
  v12 = GetCurrentThread();
  PfSetPagePriorityThread(v12);
  if ( (unsigned int)AgAlpImageVerify(a3, a4, a2) )
  {
    v13 = 0;
    if ( *(_DWORD *)(a2 + 8) )
    {
      v14 = a1 + 3472;
      do
        AgAlpTpEmpty(v14 + 33944LL * v13++, 1);
      while ( v13 < *(_DWORD *)(a2 + 8) );
    }
    v15 = 11;
    goto LABEL_31;
  }
  if ( v11 != 8 )
  {
    v16 = GetCurrentThread();
    PfSetPagePriorityThread(v16);
    v11 = 8;
  }
  ThreadInformation = v11;
  if ( !*(_DWORD *)(a2 + 12) )
    goto LABEL_26;
  v17 = 0;
  *(_OWORD *)(a1 + 2816) = *(_OWORD *)(a3 + 12);
  *(_OWORD *)(a1 + 2832) = *(_OWORD *)(a3 + 28);
  *(_OWORD *)(a1 + 2848) = *(_OWORD *)(a3 + 44);
  *(_OWORD *)(a1 + 2864) = *(_OWORD *)(a3 + 60);
  *(_OWORD *)(a1 + 2880) = *(_OWORD *)(a3 + 76);
  *(_QWORD *)(a1 + 2896) = *(_QWORD *)(a3 + 92);
  if ( !*(_WORD *)(a3 + 8) )
  {
LABEL_15:
    while ( v5 )
    {
      v20 = v5;
      v21 = *(_DWORD *)(a1 + 2908) >> 5;
      v22 = -1LL << (*(_BYTE *)(a1 + 2908) & 0x1F);
      v23 = v5;
      v5 = (_QWORD *)*v5;
      v24 = v20[1] & v22;
      if ( v21 )
      {
        v38 = v20[1] & (-1LL << (*(_BYTE *)(a1 + 2908) & 0x1F));
        v25 = *(_QWORD *)(a1 + 2912)
            + 8LL
            * ((v21 - 1)
             & (HIBYTE(v24)
              + 37
              * (BYTE6(v24)
               + 37
               * (BYTE5(v24)
                + 37
                * (BYTE4(v24)
                 + 37
                 * (BYTE3(v24)
                  + 37 * (BYTE2(v24) + 37 * (BYTE1(v24) + 37 * ((unsigned int)(unsigned __int8)v24 + 11623883)))))))));
        while ( 1 )
        {
          v25 = *(_QWORD *)v25;
          if ( (v25 & 1) != 0 )
            break;
          if ( v24 == (v22 & *(_QWORD *)(v25 + 8)) )
          {
            if ( !v25 )
              break;
            HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v20);
            goto LABEL_15;
          }
        }
      }
      v38 = v24;
      v26 = (v21 - 1)
          & (HIBYTE(v24)
           + 37
           * (BYTE6(v24)
            + 37
            * (BYTE5(v24)
             + 37
             * (BYTE4(v24)
              + 37
              * (BYTE3(v24)
               + 37 * (BYTE2(v24) + 37 * (BYTE1(v24) + 37 * ((unsigned int)(unsigned __int8)v24 + 11623883))))))));
      v27 = *(_QWORD *)(a1 + 2912);
      *v23 = *(_QWORD *)(v27 + 8 * v26);
      *(_QWORD *)(v27 + 8 * v26) = v20;
      v28 = (_QWORD *)(a1 + 2920);
      ++*(_DWORD *)(a1 + 2904);
      v29 = *(_QWORD *)(a1 + 2920);
      if ( *(_QWORD *)(v29 + 8) != a1 + 2920 )
        __fastfail(3u);
      v20[2] = v29;
      v20[3] = v28;
      *(_QWORD *)(v29 + 8) = v20 + 2;
      *v28 = v20 + 2;
    }
LABEL_26:
    AgAlpForegroundCalculateAvgSize(a1);
    if ( *(_DWORD *)(a2 + 8) )
    {
      v30 = 0;
      do
      {
        v31 = 33944LL * v30;
        v32 = *(unsigned int *)(*(_QWORD *)a2 + 4LL * v30);
        AgAlpTpEmpty(a1 + v31 + 3472, 0);
        v33 = (_DWORD *)(a3 + 32772 * v32 + 6448);
        *(_DWORD *)(a1 + v31 + 4624) = *v33;
        memcpy_0((void *)(v31 + a1 + 4640), v33, 0x8004u);
        ++v30;
        *(_OWORD *)(a1 + v31 + 4600) = *(_OWORD *)(a3 + 20 * v32 + 100);
        *(_DWORD *)(a1 + v31 + 4616) = *(_DWORD *)(a3 + 20 * v32 + 116);
      }
      while ( v30 < *(_DWORD *)(a2 + 8) );
      v11 = ThreadInformation;
    }
    v15 = 0;
    goto LABEL_31;
  }
  while ( 1 )
  {
    v18 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x30u);
    if ( !v18 )
      break;
    v19 = v17++;
    *v18 = *(_OWORD *)(a3 + 48 * v19 + 304);
    v18[1] = *(_OWORD *)(a3 + 48 * v19 + 320);
    v18[2] = *(_OWORD *)(a3 + 48 * v19 + 336);
    *(_QWORD *)v18 = v5;
    v5 = v18;
    if ( v17 >= *(unsigned __int16 *)(a3 + 8) )
      goto LABEL_15;
  }
  v15 = 8;
LABEL_31:
  while ( v5 )
  {
    v34 = v5;
    v5 = (_QWORD *)*v5;
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v34);
  }
  if ( v11 != 8 )
  {
    v35 = GetCurrentThread();
    PfSetPagePriorityThread(v35);
  }
  return v15;
}

```

## disassembly

```asm
0x18005f03c  push    rbx
0x18005f03e  push    rbp
0x18005f03f  push    rsi
0x18005f040  push    rdi
0x18005f041  push    r12
0x18005f043  push    r13
0x18005f045  push    r14
0x18005f047  push    r15
0x18005f049  sub     rsp, 48h
0x18005f04d  xor     ebp, ebp
0x18005f04f  mov     edi, r9d
0x18005f052  mov     ebx, ebp
0x18005f054  mov     r14, r8
0x18005f057  mov     r13, rdx
0x18005f05a  mov     r15, rcx
0x18005f05d  call    cs:__imp_GetCurrentThread
0x18005f063  lea     r9d, [rbp+4]; ThreadInformationLength
0x18005f067  mov     [rsp+88h+ThreadInformation], ebp
0x18005f06b  mov     rcx, rax; ThreadHandle
0x18005f06e  mov     [rsp+88h+ReturnLength], rbp; ReturnLength
0x18005f073  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x18005f078  lea     edx, [rbp+18h]; ThreadInformationClass
0x18005f07b  call    cs:__imp_NtQueryInformationThread
0x18005f081  test    eax, eax
0x18005f083  jns     short loc_18005F093
0x18005f085  mov     ecx, eax; Status
0x18005f087  call    cs:__imp_RtlNtStatusToDosError
0x18005f08d  lea     r12d, [rbp+8]
0x18005f091  jmp     short loc_18005F098
0x18005f093  mov     r12d, [rsp+88h+ThreadInformation]
0x18005f098  call    cs:__imp_GetCurrentThread
0x18005f09e  mov     rcx, rax; ThreadHandle
0x18005f0a1  mov     edx, 1
0x18005f0a6  call    PfSetPagePriorityThread
0x18005f0ab  mov     r8, r13
0x18005f0ae  mov     edx, edi
0x18005f0b0  mov     rcx, r14
0x18005f0b3  call    AgAlpImageVerify
0x18005f0b8  test    eax, eax
0x18005f0ba  jz      short loc_18005F0F3
0x18005f0bc  mov     edi, ebp
0x18005f0be  cmp     [r13+8], ebp
0x18005f0c2  jbe     short loc_18005F0E9
0x18005f0c4  add     r15, 0D90h
0x18005f0cb  mov     eax, edi
0x18005f0cd  mov     edx, 1
0x18005f0d2  imul    rcx, rax, 8498h
0x18005f0d9  add     rcx, r15
0x18005f0dc  call    AgAlpTpEmpty
0x18005f0e1  inc     edi
0x18005f0e3  cmp     edi, [r13+8]
0x18005f0e7  jb      short loc_18005F0CB
0x18005f0e9  mov     edi, 0Bh
0x18005f0ee  jmp     loc_18005F3FB
0x18005f0f3  cmp     r12d, 8
0x18005f0f7  jz      short loc_18005F110
0x18005f0f9  call    cs:__imp_GetCurrentThread
0x18005f0ff  mov     rcx, rax; ThreadHandle
0x18005f102  mov     edx, r12d
0x18005f105  call    PfSetPagePriorityThread
0x18005f10a  mov     r12d, 8
0x18005f110  mov     [rsp+88h+ThreadInformation], r12d
0x18005f115  cmp     [r13+0Ch], ebp
0x18005f119  jz      loc_18005F363
0x18005f11f  movups  xmm0, xmmword ptr [r14+0Ch]
0x18005f124  mov     edi, ebp
0x18005f126  movups  xmmword ptr [r15+0B00h], xmm0
0x18005f12e  movups  xmm1, xmmword ptr [r14+1Ch]
0x18005f133  movups  xmmword ptr [r15+0B10h], xmm1
0x18005f13b  movups  xmm0, xmmword ptr [r14+2Ch]
0x18005f140  movups  xmmword ptr [r15+0B20h], xmm0
0x18005f148  movups  xmm1, xmmword ptr [r14+3Ch]
0x18005f14d  movups  xmmword ptr [r15+0B30h], xmm1
0x18005f155  movups  xmm0, xmmword ptr [r14+4Ch]
0x18005f15a  movups  xmmword ptr [r15+0B40h], xmm0
0x18005f162  movsd   xmm1, qword ptr [r14+5Ch]
0x18005f168  movsd   qword ptr [r15+0B50h], xmm1
0x18005f171  cmp     bp, [r14+8]
0x18005f176  jnb     short loc_18005F1D8
0x18005f178  mov     rcx, cs:PfSvcGlobals
0x18005f17f  xor     edx, edx; dwFlags
0x18005f181  mov     rcx, [rcx+58h]; hHeap
0x18005f185  lea     r8d, [rdx+30h]; dwBytes
0x18005f189  call    cs:__imp_HeapAlloc
0x18005f18f  test    rax, rax
0x18005f192  jz      loc_18005F2A9
0x18005f198  mov     ecx, edi
0x18005f19a  inc     edi
0x18005f19c  lea     rdx, [rcx+rcx*2]
0x18005f1a0  add     rdx, rdx
0x18005f1a3  movups  xmm0, xmmword ptr [r14+rdx*8+130h]
0x18005f1ac  movups  xmmword ptr [rax], xmm0
0x18005f1af  movups  xmm1, xmmword ptr [r14+rdx*8+140h]
0x18005f1b8  movups  xmmword ptr [rax+10h], xmm1
0x18005f1bc  movups  xmm0, xmmword ptr [r14+rdx*8+150h]
0x18005f1c5  movups  xmmword ptr [rax+20h], xmm0
0x18005f1c9  mov     [rax], rbx
0x18005f1cc  mov     rbx, rax
0x18005f1cf  movzx   eax, word ptr [r14+8]
0x18005f1d4  cmp     edi, eax
0x18005f1d6  jb      short loc_18005F178
0x18005f1d8  test    rbx, rbx
0x18005f1db  jz      loc_18005F363
0x18005f1e1  mov     r8d, [r15+0B5Ch]
0x18005f1e8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18005f1ec  mov     ecx, r8d
0x18005f1ef  mov     r11, rbx
0x18005f1f2  and     ecx, 1Fh
0x18005f1f5  shr     r8d, 5
0x18005f1f9  shl     r9, cl
0x18005f1fc  mov     rdi, rbx
0x18005f1ff  mov     rbx, [rbx]
0x18005f202  mov     r10, r9
0x18005f205  and     r10, [r11+8]
0x18005f209  test    r8d, r8d
0x18005f20c  jz      loc_18005F2B3
0x18005f212  lea     rsi, [rsp+88h+var_50]
0x18005f217  mov     [rsp+88h+var_50], r10
0x18005f21c  movzx   eax, byte ptr [rsi]
0x18005f21f  add     eax, 0B15DCBh
0x18005f224  imul    ecx, eax, 25h ; '%'
0x18005f227  movzx   eax, byte ptr [rsi+1]
0x18005f22b  add     ecx, eax
0x18005f22d  movzx   eax, byte ptr [rsi+2]
0x18005f231  imul    edx, ecx, 25h ; '%'
0x18005f234  add     edx, eax
0x18005f236  movzx   eax, byte ptr [rsi+3]
0x18005f23a  imul    ecx, edx, 25h ; '%'
0x18005f23d  add     ecx, eax
0x18005f23f  movzx   eax, byte ptr [rsi+4]
0x18005f243  imul    edx, ecx, 25h ; '%'
0x18005f246  add     edx, eax
0x18005f248  movzx   eax, byte ptr [rsi+5]
0x18005f24c  imul    ecx, edx, 25h ; '%'
0x18005f24f  add     ecx, eax
0x18005f251  movzx   eax, byte ptr [rsi+6]
0x18005f255  imul    edx, ecx, 25h ; '%'
0x18005f258  lea     ecx, [r8-1]
0x18005f25c  add     edx, eax
0x18005f25e  movzx   eax, byte ptr [rsi+7]
0x18005f262  imul    edx, 25h ; '%'
0x18005f265  add     edx, eax
0x18005f267  mov     rax, [r15+0B60h]
0x18005f26e  and     rdx, rcx
0x18005f271  lea     rcx, [rax+rdx*8]
0x18005f275  mov     rcx, [rcx]
0x18005f278  test    cl, 1
0x18005f27b  jnz     short loc_18005F2B3
0x18005f27d  mov     rax, [rcx+8]
0x18005f281  and     rax, r9
0x18005f284  cmp     r10, rax
0x18005f287  jnz     short loc_18005F275
0x18005f289  test    rcx, rcx
0x18005f28c  jz      short loc_18005F2B3
0x18005f28e  mov     rcx, cs:PfSvcGlobals
0x18005f295  mov     r8, r11; lpMem
0x18005f298  xor     edx, edx; dwFlags
0x18005f29a  mov     rcx, [rcx+58h]; hHeap
0x18005f29e  call    cs:__imp_HeapFree
0x18005f2a4  jmp     loc_18005F1D8
0x18005f2a9  mov     edi, 8
0x18005f2ae  jmp     loc_18005F3FB
0x18005f2b3  lea     r9, [rsp+88h+var_50]
0x18005f2b8  mov     [rsp+88h+var_50], r10
0x18005f2bd  movzx   eax, byte ptr [r9]
0x18005f2c1  add     eax, 0B15DCBh
0x18005f2c6  imul    ecx, eax, 25h ; '%'
0x18005f2c9  movzx   eax, byte ptr [r9+1]
0x18005f2ce  add     ecx, eax
0x18005f2d0  movzx   eax, byte ptr [r9+2]
0x18005f2d5  imul    edx, ecx, 25h ; '%'
0x18005f2d8  add     edx, eax
0x18005f2da  movzx   eax, byte ptr [r9+3]
0x18005f2df  imul    ecx, edx, 25h ; '%'
0x18005f2e2  add     ecx, eax
0x18005f2e4  movzx   eax, byte ptr [r9+4]
0x18005f2e9  imul    edx, ecx, 25h ; '%'
0x18005f2ec  add     edx, eax
0x18005f2ee  movzx   eax, byte ptr [r9+5]
0x18005f2f3  imul    ecx, edx, 25h ; '%'
0x18005f2f6  add     ecx, eax
0x18005f2f8  movzx   eax, byte ptr [r9+6]
0x18005f2fd  imul    edx, ecx, 25h ; '%'
0x18005f300  lea     ecx, [r8-1]
0x18005f304  add     edx, eax
0x18005f306  movzx   eax, byte ptr [r9+7]
0x18005f30b  imul    edx, 25h ; '%'
0x18005f30e  add     edx, eax
0x18005f310  and     rdx, rcx
0x18005f313  mov     rcx, [r15+0B60h]
0x18005f31a  mov     rax, [rcx+rdx*8]
0x18005f31e  mov     [rdi], rax
0x18005f321  mov     [rcx+rdx*8], r11
0x18005f325  lea     rcx, [r15+0B68h]
0x18005f32c  mov     eax, [r15+0B58h]
0x18005f333  inc     eax
0x18005f335  mov     [r15+0B58h], eax
0x18005f33c  mov     rdx, [rcx]
0x18005f33f  cmp     [rdx+8], rcx
0x18005f343  jnz     short loc_18005F35C
0x18005f345  lea     rax, [r11+10h]
0x18005f349  mov     [rax], rdx
0x18005f34c  mov     [rax+8], rcx
0x18005f350  mov     [rdx+8], rax
0x18005f354  mov     [rcx], rax
0x18005f357  jmp     loc_18005F1D8
0x18005f35c  mov     ecx, 3
0x18005f361  int     29h; Win8: RtlFailFast(ecx)
0x18005f363  mov     rcx, r15
0x18005f366  call    AgAlpForegroundCalculateAvgSize
0x18005f36b  cmp     [r13+8], ebp
0x18005f36f  jbe     loc_18005F3F9
0x18005f375  mov     r12d, ebp
0x18005f378  mov     rax, [r13+0]
0x18005f37c  xor     edx, edx
0x18005f37e  mov     ecx, r12d
0x18005f381  imul    rbp, rcx, 8498h
0x18005f388  mov     edi, [rax+rcx*4]
0x18005f38b  lea     rsi, [r15+rbp]
0x18005f38f  lea     rcx, [rsi+0D90h]
0x18005f396  call    AgAlpTpEmpty
0x18005f39b  imul    rdx, rdi, 8004h
0x18005f3a2  lea     rcx, [r15+1220h]
0x18005f3a9  mov     r8d, 8004h; Size
0x18005f3af  add     rdx, 1930h
0x18005f3b6  add     rcx, rbp; void *
0x18005f3b9  add     rdx, r14; Src
0x18005f3bc  mov     eax, [rdx]
0x18005f3be  mov     [rsi+1210h], eax
0x18005f3c4  call    memcpy_0
0x18005f3c9  lea     rax, [rdi+rdi*4]
0x18005f3cd  inc     r12d
0x18005f3d0  movups  xmm0, xmmword ptr [r14+rax*4+64h]
0x18005f3d6  movups  xmmword ptr [r15+rbp+11F8h], xmm0
0x18005f3df  mov     eax, [r14+rax*4+74h]
0x18005f3e4  mov     [r15+rbp+1208h], eax
0x18005f3ec  cmp     r12d, [r13+8]
0x18005f3f0  jb      short loc_18005F378
0x18005f3f2  mov     r12d, [rsp+88h+ThreadInformation]
0x18005f3f7  xor     ebp, ebp
0x18005f3f9  mov     edi, ebp
0x18005f3fb  test    rbx, rbx
0x18005f3fe  jz      short loc_18005F41B
0x18005f400  mov     rcx, cs:PfSvcGlobals
0x18005f407  mov     r8, rbx; lpMem
0x18005f40a  mov     rbx, [rbx]
0x18005f40d  xor     edx, edx; dwFlags
0x18005f40f  mov     rcx, [rcx+58h]; hHeap
0x18005f413  call    cs:__imp_HeapFree
0x18005f419  jmp     short loc_18005F3FB
0x18005f41b  cmp     r12d, 8
0x18005f41f  jz      short loc_18005F432
0x18005f421  call    cs:__imp_GetCurrentThread
0x18005f427  mov     rcx, rax; ThreadHandle
0x18005f42a  mov     edx, r12d
0x18005f42d  call    PfSetPagePriorityThread
0x18005f432  mov     eax, edi
0x18005f434  add     rsp, 48h
0x18005f438  pop     r15
0x18005f43a  pop     r14
0x18005f43c  pop     r13
0x18005f43e  pop     r12
0x18005f440  pop     rdi
0x18005f441  pop     rsi
0x18005f442  pop     rbp
0x18005f443  pop     rbx
0x18005f444  retn
```
