# StorpTelemetryNvmeSendNamespacePerfData

- ea: `0x1400e11c4`
- end: `0x1400e1a3b`
- name: `StorpTelemetryNvmeSendNamespacePerfData`
- size: `2167`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400d891c`

## callees

- `0x1400290b0`
- `0x1400d39a0`
- `0x1400dff50`
- `0x1400e0298`
- `0x1400e0968`
- `0x1400e11c4`
- `0x1400e1bc4`
- `0x14014b400`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400e12d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400e12d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e19e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e19fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e19e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e19fb`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e1274`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e1282`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e1274`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400e1282`
- `HAL!KeQueryPerformanceCounter` at `0x1400e12c5`
- `HAL!KeQueryPerformanceCounter` at `0x1400e12c5`

## pseudocode

```c
__int64 __fastcall StorpTelemetryNvmeSendNamespacePerfData(__int64 a1)
{
  __int64 v2; // rax
  __int128 v3; // xmm6
  __int128 v4; // xmm7
  _QWORD *v5; // r13
  char *Pool; // r12
  unsigned int v7; // ebx
  unsigned int v8; // edi
  ULONG RecommendedSharedDataAlignment; // ebx
  ULONG v10; // eax
  LARGE_INTEGER v11; // rax
  __int64 v12; // rdx
  LARGE_INTEGER v13; // rcx
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r9
  LARGE_INTEGER *v17; // rax
  unsigned int i; // r8d
  unsigned int v19; // r10d
  char *v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // esi
  __int64 v26; // r11
  __int64 v27; // r10
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // rdx
  unsigned __int64 v32; // r8
  __int64 j; // r9
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // ebx
  unsigned __int16 v38; // r11
  __int64 v39; // r9
  unsigned __int64 v40; // r10
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  __int64 v44; // rax
  unsigned __int64 v45; // r10
  __int64 v46; // r14
  const int *v47; // rdi
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+228h] [rbp-80h] BYREF
  __int128 v50; // [rsp+230h] [rbp-78h]
  __int128 v51; // [rsp+240h] [rbp-68h]
  unsigned __int64 v52; // [rsp+258h] [rbp-50h] BYREF
  char v53[8]; // [rsp+260h] [rbp-48h] BYREF
  const wchar_t *v54; // [rsp+268h] [rbp-40h]
  _QWORD v55[3]; // [rsp+270h] [rbp-38h]
  __int64 v56; // [rsp+3C0h] [rbp+118h]
  _QWORD *v57; // [rsp+3C8h] [rbp+120h]
  unsigned __int64 v58; // [rsp+3D0h] [rbp+128h]
  unsigned __int64 v59; // [rsp+3D8h] [rbp+130h]
  __int64 v60; // [rsp+3E0h] [rbp+138h]

  PerformanceFrequency.QuadPart = 0;
  memset_0(v53, 0, 0x190u);
  v2 = *(_QWORD *)(a1 + 624);
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v50 = 0;
  v51 = 0;
  if ( *(_QWORD *)(v2 + 8) )
  {
    v8 = qword_140177050;
    Pool = (char *)RaidAllocatePool(72, (unsigned int)Size, 1700028754, *(_QWORD *)(a1 + 8));
    if ( Pool
      && (RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment(),
          v10 = KeGetRecommendedSharedDataAlignment(),
          (v5 = (_QWORD *)RaidAllocatePool(
                            72,
                            -RecommendedSharedDataAlignment & (v10 + 24 * v8 - 1),
                            1700028754,
                            *(_QWORD *)(a1 + 8))) != 0) )
    {
      if ( UseQPCTime )
        v11 = KeQueryPerformanceCounter(&PerformanceFrequency);
      else
        v11.QuadPart = KeQueryUnbiasedInterruptTime();
      v12 = *(_QWORD *)(a1 + 624);
      v13 = v11;
      if ( v11.QuadPart <= 0 || (v14 = *(_QWORD *)(v12 + 24), v11.QuadPart >= v14) )
        v15 = v11.QuadPart - *(_QWORD *)(v12 + 24);
      else
        v15 = v11.QuadPart - v14 - 1;
      if ( UseQPCTime )
      {
        v16 = 0;
        if ( PerformanceFrequency.QuadPart && v15 )
          v16 = 10000
              * (1000 * (v15 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart)
              / PerformanceFrequency.QuadPart
              + 10000
              * (1000 * (v15 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart
               + 1000 * (v15 / PerformanceFrequency.QuadPart));
      }
      else
      {
        v16 = v15;
      }
      qword_140177068 = v13.QuadPart;
      v17 = *(LARGE_INTEGER **)(a1 + 624);
      v52 = v16;
      v17[3] = v13;
      memmove(Pool, *(const void **)(*(_QWORD *)(a1 + 624) + 8LL), (unsigned int)Size);
      for ( i = 1; i < g_RaidNumberProcessors; ++i )
      {
        v19 = 0;
        v20 = &Pool[(unsigned int)dword_140177058 * i];
        if ( v8 )
        {
          v21 = 0;
          do
          {
            v22 = 3 * v21;
            ++v19;
            v23 = *(_QWORD *)&v20[24 * v21++];
            *(_QWORD *)&Pool[8 * v22] += v23;
            *(_QWORD *)&Pool[8 * v22 + 8] += *(_QWORD *)&v20[8 * v22 + 8];
            *(_QWORD *)&Pool[8 * v22 + 16] += *(_QWORD *)&v20[8 * v22 + 16];
          }
          while ( v19 < v8 );
        }
      }
      v24 = 0;
      v25 = 0;
      v26 = *(_QWORD *)(*(_QWORD *)(a1 + 624) + 32LL);
      if ( v8 )
      {
        v27 = 0;
        do
        {
          v28 = 3 * v27;
          ++v25;
          v29 = *(_QWORD *)&Pool[24 * v27++];
          v30 = v29 - *(_QWORD *)(v26 + 8 * v28);
          v5[v28] = v30;
          v31 = *(_QWORD *)&Pool[8 * v28 + 8] - *(_QWORD *)(v26 + 8 * v28 + 8);
          v5[v28 + 1] = v31;
          v5[v28 + 2] = *(_QWORD *)&Pool[8 * v28 + 16] - *(_QWORD *)(v26 + 8 * v28 + 16);
          v24 += v31 + v30;
        }
        while ( v25 < v8 );
      }
      memmove(*(void **)(*(_QWORD *)(a1 + 624) + 32LL), Pool, (unsigned int)dword_140177058);
      if ( v24 )
      {
        v56 = 0;
        if ( (_WORD)TelemetryPerfContext )
        {
          if ( WORD1(TelemetryPerfContext) )
          {
            for ( j = 0; (unsigned int)j < v8; j = (unsigned int)(j + 1) )
            {
              if ( (unsigned int)j >= dword_140176FEC && (unsigned int)j < *((_DWORD *)&xmmword_140177010 + 3) )
              {
                v34 = (unsigned int)j / (unsigned __int16)TelemetryPerfContext;
                if ( (unsigned int)v34 >= 0xE )
                  v34 = 13;
                v32 = 3 * v34;
                v35 = v5[3 * (unsigned int)j];
                v36 = v5[3 * (unsigned int)j + 1];
                v55[v32 + 2] += v5[3 * (unsigned int)j + 2];
                v55[v32] += v35;
                v55[v32 + 1] += v36;
                v56 += v36 + v35;
              }
            }
          }
        }
        if ( *(_QWORD *)(*(_QWORD *)(a1 + 624) + 48LL) )
        {
          v37 = g_RaidNumberProcessors;
          v38 = 0;
          if ( g_RaidNumberProcessors )
          {
            v39 = v51;
            v40 = *((_QWORD *)&v50 + 1);
            v32 = v50;
            do
            {
              v41 = dword_140177070 * (unsigned int)v38;
              v42 = *(_QWORD *)(*(_QWORD *)(a1 + 624) + 48LL);
              v43 = *(_QWORD *)(v41 + v42);
              *(_QWORD *)(v41 + v42) = 0;
              if ( v43 > v32 )
                v32 = v43;
              v40 += *(_QWORD *)(v41 + v42 + 8);
              v39 += *(_QWORD *)(v41 + v42 + 16);
              ++v38;
            }
            while ( v38 < v37 );
            *(_QWORD *)&v50 = v32;
            *(_QWORD *)&v51 = v39;
            v4 = v51;
            *((_QWORD *)&v50 + 1) = v40;
            v3 = v50;
          }
          else
          {
            v39 = 0;
            v32 = 0;
            v40 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          }
          v44 = *(_QWORD *)(a1 + 624);
          v58 = v32;
          v45 = v40 - *(_QWORD *)(v44 + 64);
          j = v39 - *(_QWORD *)(v44 + 72);
          *(_OWORD *)(v44 + 56) = v3;
          v60 = j;
          *(_OWORD *)(v44 + 72) = v4;
          v59 = v45;
        }
        v54 = L"128us, 256us, 512us, 1ms, 4ms, 16ms, 64ms, 128ms, 256ms, 512ms, 1000ms, 2000ms, 10000ms, 10000+ms";
        v57 = v5;
        v53[0] = 12;
        if ( (g_StorpTraceLoggingCriticalEventEnabledSetByRegistry != 1 || g_StorpTraceLoggingCriticalEventEnabled)
          && g_StorpTraceLoggingCriticalEventsLogged < (unsigned int)g_StorpTraceLoggingCriticalEventMaximum
          && g_StorpTraceLoggingCriticalEventEnabled )
        {
          StorpTelemetryNvmeLogNamespacePerfDataCriticalData(a1, &v52, v32, j);
        }
        else
        {
          StorpTelemetryNvmeLogNamespacePerfDataMeasures(a1, &v52, v32, j);
        }
        if ( (byte_14017743A & 0x40) != 0 )
        {
          v46 = *(_QWORD *)(a1 + 16);
          v47 = &dword_140157D94;
          if ( *(_QWORD *)(v46 + 752) )
            v47 = *(const int **)(v46 + 752);
          McTemplateK0qjzshqusssjqxuxxqqqzxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx_EtwWriteTransfer(
            *(_QWORD *)(a1 + 624),
            *(unsigned __int16 *)(a1 + 424),
            a1 + 160,
            *(unsigned int *)(*(_QWORD *)(v46 + 128) + 56LL),
            *(_QWORD *)(v46 + 128) + 1048LL,
            *(_QWORD *)(*(_QWORD *)(v46 + 128) + 1032LL),
            *(_QWORD *)(v46 + 792),
            *(_WORD *)(v46 + 4),
            *(_DWORD *)(a1 + 56),
            *(_BYTE *)(v46 + 744),
            v47,
            v46 + 800,
            v46 + 841,
            a1 + 160,
            (*(_BYTE *)(v46 + 136) & 2) != 0 ? 20 : 17);
        }
      }
      if ( g_StorpTraceLoggingIoSizeDistributionEnabled && (*(_DWORD *)(a1 + 112) & 0x100LL) != 0 )
        StorpTelemetryNvmeSendNamespaceIoSizeDistributionData(a1);
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 128LL) + 1336LL) )
        StorpTelemetrySendAdapterDlrmStatistics();
      v7 = 0;
    }
    else
    {
      v7 = -1073741801;
    }
  }
  else
  {
    Pool = 0;
    v7 = -1073741823;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 624) + 88LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 624) + 96LL) = 0;
  **(_DWORD **)(a1 + 624) = 0;
  if ( Pool )
    ExFreePoolWithTag(Pool, 0x65546152u);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x65546152u);
  return v7;
}

```

## disassembly

```asm
0x1400e11c4  mov     rax, rsp
0x1400e11c7  push    rbp
0x1400e11c8  push    rbx
0x1400e11c9  push    rsi
0x1400e11ca  push    rdi
0x1400e11cb  push    r12
0x1400e11cd  push    r13
0x1400e11cf  push    r14
0x1400e11d1  push    r15
0x1400e11d3  lea     rbp, [rax-1C8h]
0x1400e11da  sub     rsp, 428h
0x1400e11e1  movaps  xmmword ptr [rax-58h], xmm6
0x1400e11e5  movaps  xmmword ptr [rax-68h], xmm7
0x1400e11e9  mov     rax, cs:__security_cookie
0x1400e11f0  xor     rax, rsp
0x1400e11f3  mov     [rbp+1C0h+var_70], rax
0x1400e11fa  mov     r15, rcx
0x1400e11fd  xor     r14d, r14d
0x1400e1200  lea     rcx, [rbp+1C0h+var_208]; void *
0x1400e1204  mov     qword ptr [rbp+1C0h+PerformanceFrequency], r14
0x1400e1208  xor     edx, edx; Val
0x1400e120a  mov     r8d, 190h; Size
0x1400e1210  call    memset_0
0x1400e1215  mov     rax, [r15+270h]
0x1400e121c  xorps   xmm6, xmm6
0x1400e121f  xorps   xmm7, xmm7
0x1400e1222  mov     r13d, r14d
0x1400e1225  movups  [rbp+1C0h+var_238], xmm6
0x1400e1229  mov     esi, 65546152h
0x1400e122e  movups  [rbp+1C0h+var_228], xmm7
0x1400e1232  cmp     [rax+8], r14
0x1400e1236  jnz     short loc_1400E1245
0x1400e1238  mov     r12d, r14d
0x1400e123b  mov     ebx, 0C0000001h
0x1400e1240  jmp     loc_1400E19BB
0x1400e1245  mov     edx, cs:Size
0x1400e124b  mov     r8d, esi
0x1400e124e  mov     r9, [r15+8]
0x1400e1252  mov     ecx, 48h ; 'H'
0x1400e1257  mov     edi, dword ptr cs:qword_140177050
0x1400e125d  call    RaidAllocatePool
0x1400e1262  mov     r12, rax
0x1400e1265  test    rax, rax
0x1400e1268  jnz     short loc_1400E1274
0x1400e126a  mov     ebx, 0C0000017h
0x1400e126f  jmp     loc_1400E19BB
0x1400e1274  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e127b  nop     dword ptr [rax+rax+00h]
0x1400e1280  mov     ebx, eax
0x1400e1282  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400e1289  nop     dword ptr [rax+rax+00h]
0x1400e128e  mov     r9, [r15+8]
0x1400e1292  neg     ebx
0x1400e1294  mov     edx, eax
0x1400e1296  mov     r8d, esi
0x1400e1299  lea     eax, [rdi+rdi*2]
0x1400e129c  mov     ecx, 48h ; 'H'
0x1400e12a1  lea     edx, [rdx+rax*8]
0x1400e12a4  mov     eax, ebx
0x1400e12a6  dec     edx
0x1400e12a8  and     rdx, rax
0x1400e12ab  call    RaidAllocatePool
0x1400e12b0  mov     r13, rax
0x1400e12b3  test    rax, rax
0x1400e12b6  jz      short loc_1400E126A
0x1400e12b8  cmp     cs:UseQPCTime, r14b
0x1400e12bf  jz      short loc_1400E12D3
0x1400e12c1  lea     rcx, [rbp+1C0h+PerformanceFrequency]; PerformanceFrequency
0x1400e12c5  call    cs:__imp_KeQueryPerformanceCounter
0x1400e12cc  nop     dword ptr [rax+rax+00h]
0x1400e12d1  jmp     short loc_1400E12DF
0x1400e12d3  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400e12da  nop     dword ptr [rax+rax+00h]
0x1400e12df  mov     rdx, [r15+270h]
0x1400e12e6  mov     rcx, rax
0x1400e12e9  mov     ebx, 1
0x1400e12ee  test    rax, rax
0x1400e12f1  jle     short loc_1400E1304
0x1400e12f3  mov     r8, [rdx+18h]
0x1400e12f7  cmp     rax, r8
0x1400e12fa  jge     short loc_1400E1304
0x1400e12fc  sub     rax, r8
0x1400e12ff  sub     rax, rbx
0x1400e1302  jmp     short loc_1400E130B
0x1400e1304  mov     rax, rcx
0x1400e1307  sub     rax, [rdx+18h]
0x1400e130b  cmp     cs:UseQPCTime, r14b
0x1400e1312  jz      short loc_1400E135E
0x1400e1314  mov     r10, qword ptr [rbp+1C0h+PerformanceFrequency]
0x1400e1318  mov     r9, r14
0x1400e131b  test    r10, r10
0x1400e131e  jz      short loc_1400E1361
0x1400e1320  test    rax, rax
0x1400e1323  jz      short loc_1400E1361
0x1400e1325  xor     edx, edx
0x1400e1327  div     r10
0x1400e132a  mov     r9, rax
0x1400e132d  imul    rax, rdx, 3E8h
0x1400e1334  xor     edx, edx
0x1400e1336  div     r10
0x1400e1339  mov     r8, rdx
0x1400e133c  imul    rdx, r9, 3E8h
0x1400e1343  add     rdx, rax
0x1400e1346  imul    r9, rdx, 2710h
0x1400e134d  imul    rax, r8, 2710h
0x1400e1354  xor     edx, edx
0x1400e1356  div     r10
0x1400e1359  add     r9, rax
0x1400e135c  jmp     short loc_1400E1361
0x1400e135e  mov     r9, rax
0x1400e1361  mov     cs:qword_140177068, rcx
0x1400e1368  mov     rax, [r15+270h]
0x1400e136f  mov     [rbp+1C0h+var_210], r9
0x1400e1373  mov     [rax+18h], rcx
0x1400e1377  mov     rcx, r12; void *
0x1400e137a  mov     rdx, [r15+270h]
0x1400e1381  mov     r8d, cs:Size; Size
0x1400e1388  mov     rdx, [rdx+8]; Src
0x1400e138c  call    memmove
0x1400e1391  cmp     cs:g_RaidNumberProcessors, ebx
0x1400e1397  mov     r8d, ebx
0x1400e139a  jbe     short loc_1400E13EA
0x1400e139c  mov     edx, r8d
0x1400e139f  mov     r10d, r14d
0x1400e13a2  imul    edx, cs:dword_140177058
0x1400e13a9  add     rdx, r12
0x1400e13ac  test    edi, edi
0x1400e13ae  jz      short loc_1400E13DE
0x1400e13b0  mov     r9, r14
0x1400e13b3  lea     rcx, [r9+r9*2]
0x1400e13b7  add     r10d, ebx
0x1400e13ba  mov     rax, [rdx+rcx*8]
0x1400e13be  add     r9, rbx
0x1400e13c1  add     [r12+rcx*8], rax
0x1400e13c5  mov     rax, [rdx+rcx*8+8]
0x1400e13ca  add     [r12+rcx*8+8], rax
0x1400e13cf  mov     rax, [rdx+rcx*8+10h]
0x1400e13d4  add     [r12+rcx*8+10h], rax
0x1400e13d9  cmp     r10d, edi
0x1400e13dc  jb      short loc_1400E13B3
0x1400e13de  add     r8d, ebx
0x1400e13e1  cmp     r8d, cs:g_RaidNumberProcessors
0x1400e13e8  jb      short loc_1400E139C
0x1400e13ea  mov     rax, [r15+270h]
0x1400e13f1  mov     rbx, r14
0x1400e13f4  mov     esi, r14d
0x1400e13f7  mov     r11, [rax+20h]
0x1400e13fb  test    edi, edi
0x1400e13fd  jz      short loc_1400E1441
0x1400e13ff  mov     r10, r14
0x1400e1402  lea     r9, [r10+r10*2]
0x1400e1406  inc     esi
0x1400e1408  mov     r8, [r12+r9*8]
0x1400e140c  inc     r10
0x1400e140f  sub     r8, [r11+r9*8]
0x1400e1413  mov     [r13+r9*8+0], r8
0x1400e1418  mov     rdx, [r12+r9*8+8]
0x1400e141d  sub     rdx, [r11+r9*8+8]
0x1400e1422  mov     [r13+r9*8+8], rdx
0x1400e1427  mov     rcx, [r12+r9*8+10h]
0x1400e142c  sub     rcx, [r11+r9*8+10h]
0x1400e1431  lea     rax, [rdx+r8]
0x1400e1435  mov     [r13+r9*8+10h], rcx
0x1400e143a  add     rbx, rax
0x1400e143d  cmp     esi, edi
0x1400e143f  jb      short loc_1400E1402
0x1400e1441  mov     rcx, [r15+270h]
0x1400e1448  mov     rdx, r12; Src
0x1400e144b  mov     r8d, cs:dword_140177058; Size
0x1400e1452  mov     rcx, [rcx+20h]; void *
0x1400e1456  call    memmove
0x1400e145b  test    rbx, rbx
0x1400e145e  jz      loc_1400E197E
0x1400e1464  cmp     word ptr cs:TelemetryPerfContext, r14w
0x1400e146c  mov     esi, 1
0x1400e1471  mov     [rbp+1C0h+var_A8], r14
0x1400e1478  jz      short loc_1400E14F2
0x1400e147a  cmp     word ptr cs:TelemetryPerfContext+2, r14w
0x1400e1482  jz      short loc_1400E14F2
0x1400e1484  mov     r9d, r14d
0x1400e1487  test    edi, edi
0x1400e1489  jz      short loc_1400E14F2
0x1400e148b  cmp     r9d, cs:dword_140176FEC
0x1400e1492  jb      short loc_1400E14EA
0x1400e1494  cmp     r9d, dword ptr cs:xmmword_140177010+0Ch
0x1400e149b  jnb     short loc_1400E14EA
0x1400e149d  movzx   ecx, word ptr cs:TelemetryPerfContext
0x1400e14a4  xor     edx, edx
0x1400e14a6  mov     eax, r9d
0x1400e14a9  div     ecx
0x1400e14ab  mov     ecx, 0Dh
0x1400e14b0  cmp     eax, 0Eh
0x1400e14b3  cmovnb  eax, ecx
0x1400e14b6  lea     r8, [rax+rax*2]
0x1400e14ba  mov     eax, r9d
0x1400e14bd  lea     rax, [rax+rax*2]
0x1400e14c1  mov     rdx, [r13+rax*8+0]
0x1400e14c6  mov     rcx, [r13+rax*8+8]
0x1400e14cb  mov     rax, [r13+rax*8+10h]
0x1400e14d0  add     [rbp+r8*8+1C0h+var_1E8], rax
0x1400e14d5  add     [rbp+r8*8+1C0h+var_1F8], rdx
0x1400e14da  add     [rbp+r8*8+1C0h+var_1F0], rcx
0x1400e14df  lea     rax, [rcx+rdx]
0x1400e14e3  add     [rbp+1C0h+var_A8], rax
0x1400e14ea  add     r9d, esi
0x1400e14ed  cmp     r9d, edi
0x1400e14f0  jb      short loc_1400E148B
0x1400e14f2  mov     rax, [r15+270h]
0x1400e14f9  cmp     [rax+30h], r14
0x1400e14fd  jz      loc_1400E15B1
0x1400e1503  mov     ebx, cs:g_RaidNumberProcessors
0x1400e1509  mov     r11d, r14d
0x1400e150c  test    ebx, ebx
0x1400e150e  jz      short loc_1400E156D
0x1400e1510  mov     r9, qword ptr [rbp+1C0h+var_228]
0x1400e1514  mov     r10, qword ptr [rbp+1C0h+var_238+8]
0x1400e1518  mov     r8, qword ptr [rbp+1C0h+var_238]
0x1400e151c  mov     rax, [r15+270h]
0x1400e1523  movzx   edx, r11w
0x1400e1527  imul    edx, cs:dword_140177070
0x1400e152e  mov     rcx, [rax+30h]
0x1400e1532  mov     rax, [rdx+rcx]
0x1400e1536  cmp     rax, r8
0x1400e1539  mov     [rdx+rcx], r14
0x1400e153d  cmova   r8, rax
0x1400e1541  add     r10, [rdx+rcx+8]
0x1400e1546  add     r9, [rdx+rcx+10h]
0x1400e154b  add     r11w, si
0x1400e154f  movzx   eax, r11w
0x1400e1553  cmp     eax, ebx
0x1400e1555  jb      short loc_1400E151C
0x1400e1557  mov     qword ptr [rbp+1C0h+var_238], r8
0x1400e155b  mov     qword ptr [rbp+1C0h+var_228], r9
0x1400e155f  movups  xmm7, [rbp+1C0h+var_228]
0x1400e1563  mov     qword ptr [rbp+1C0h+var_238+8], r10
0x1400e1567  movups  xmm6, [rbp+1C0h+var_238]
0x1400e156b  jmp     short loc_1400E1585
0x1400e156d  movdqa  xmm0, xmm6
0x1400e1571  movq    r9, xmm7
0x1400e1576  psrldq  xmm0, 8
0x1400e157b  movq    r8, xmm6
0x1400e1580  movq    r10, xmm0
0x1400e1585  mov     rax, [r15+270h]
0x1400e158c  mov     [rbp+1C0h+var_98], r8
0x1400e1593  sub     r10, [rax+40h]
0x1400e1597  sub     r9, [rax+48h]
0x1400e159b  movups  xmmword ptr [rax+38h], xmm6
0x1400e159f  mov     [rbp+1C0h+var_88], r9
0x1400e15a6  movups  xmmword ptr [rax+48h], xmm7
0x1400e15aa  mov     [rbp+1C0h+var_90], r10
0x1400e15b1  cmp     cs:g_StorpTraceLoggingCriticalEventEnabledSetByRegistry, sil
0x1400e15b8  lea     rax, a128us256us512u; "128us, 256us, 512us, 1ms, 4ms, 16ms, 64"...
0x1400e15bf  mov     [rbp+1C0h+var_200], rax
0x1400e15c3  mov     [rbp+1C0h+var_A0], r13
0x1400e15ca  mov     [rbp+1C0h+var_208], 0Ch
0x1400e15ce  jnz     short loc_1400E15D9
0x1400e15d0  cmp     cs:g_StorpTraceLoggingCriticalEventEnabled, r14d
0x1400e15d7  jz      short loc_1400E15FE
0x1400e15d9  mov     eax, cs:g_StorpTraceLoggingCriticalEventMaximum
0x1400e15df  cmp     cs:g_StorpTraceLoggingCriticalEventsLogged, eax
0x1400e15e5  jnb     short loc_1400E15FE
0x1400e15e7  cmp     cs:g_StorpTraceLoggingCriticalEventEnabled, r14d
0x1400e15ee  jz      short loc_1400E15FE
0x1400e15f0  lea     rdx, [rbp+1C0h+var_210]
0x1400e15f4  mov     rcx, r15
0x1400e15f7  call    StorpTelemetryNvmeLogNamespacePerfDataCriticalData
0x1400e15fc  jmp     short loc_1400E160A
0x1400e15fe  lea     rdx, [rbp+1C0h+var_210]
0x1400e1602  mov     rcx, r15
0x1400e1605  call    StorpTelemetryNvmeLogNamespacePerfDataMeasures
0x1400e160a  test    cs:byte_14017743A, 40h
0x1400e1611  jz      loc_1400E197E
0x1400e1617  mov     r14, [r15+10h]
0x1400e161b  lea     rdi, dword_140157D94
0x1400e1622  mov     rcx, [r15+270h]
0x1400e1629  lea     r8, [r15+0A0h]
0x1400e1630  movzx   edx, word ptr [r15+1A8h]
0x1400e1638  mov     al, [r14+88h]
0x1400e163f  lea     r10, [r14+349h]
0x1400e1646  and     al, 2
0x1400e1648  mov     rsi, [r14+80h]
0x1400e164f  neg     al
0x1400e1651  lea     r11, [r14+320h]
0x1400e1658  mov     rax, [r14+2F0h]
0x1400e165f  sbb     r9d, r9d
0x1400e1662  and     r9d, 3
0x1400e1666  lea     rbx, [rsi+418h]
0x1400e166d  add     r9d, 11h
0x1400e1671  test    rax, rax
0x1400e1674  cmovnz  rdi, rax
0x1400e1678  mov     eax, [rcx]
0x1400e167a  mov     [rsp+460h+var_248], rax
0x1400e1682  mov     rax, [rbp+1C0h+var_88]
0x1400e1689  mov     [rsp+460h+var_250], rax
0x1400e1691  mov     rax, [rbp+1C0h+var_90]
0x1400e1698  mov     [rsp+460h+var_258], rax
0x1400e16a0  mov     rax, [rbp+1C0h+var_B0]
0x1400e16a7  mov     [rsp+460h+var_260], rax
0x1400e16af  mov     rax, [rbp+1C0h+var_C8]
0x1400e16b6  mov     [rsp+460h+var_268], rax
  ... truncated ...
```
