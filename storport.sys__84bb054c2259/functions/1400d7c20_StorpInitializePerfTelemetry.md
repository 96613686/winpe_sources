# StorpInitializePerfTelemetry

- ea: `0x1400d7c20`
- end: `0x1400d8913`
- name: `StorpInitializePerfTelemetry`
- size: `3315`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140198540`

## callees

- `0x1400290b0`
- `0x1400d7c20`
- `0x1400e61b4`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400d7d8f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400d7d8f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400d7d48`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400d7d48`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7cd8`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7cf6`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7d11`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7d28`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d87de`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d87ed`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d8810`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d882b`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7cd8`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7cf6`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7d11`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d7d28`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d87de`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d87ed`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d8810`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d882b`
- `HAL!KeQueryPerformanceCounter` at `0x1400d7d81`
- `HAL!KeQueryPerformanceCounter` at `0x1400d80b5`
- `HAL!KeQueryPerformanceCounter` at `0x1400d7d81`
- `HAL!KeQueryPerformanceCounter` at `0x1400d80b5`

## pseudocode

```c
__int64 StorpInitializePerfTelemetry()
{
  ULONG RecommendedSharedDataAlignment; // edi
  int v1; // ebx
  ULONG v2; // edi
  int v3; // ebx
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned int v5; // ebx
  bool v6; // zf
  ULONG v7; // ebx
  ULONG v8; // edi
  int v9; // ebx
  __int64 v10; // rbx
  unsigned int v11; // r9d
  unsigned int i; // r8d
  __int64 v13; // rdx
  int v14; // ecx
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp+38h] BYREF

  PerformanceFrequency.QuadPart = 0;
  memset_0(&TelemetryPerfContext, 0, 0xD0u);
  TelemetryPerfContext = 917506;
  *(_QWORD *)byte_140176FE8 = 28;
  *(_OWORD *)&xmmword_140177010 = 0;
  *(&xmmword_140177010 + 1) = (PVOID)0x1C0000000ALL;
  xmmword_140177020 = 0;
  qword_140177050 = 0xFC00000026LL;
  xmmword_140176FF0 = 0;
  *(_QWORD *)&xmmword_140176FF0 = 327682;
  *(_OWORD *)&xmmword_140177040 = 0;
  *(_QWORD *)&xmmword_140177020 = 0xE00090002LL;
  *(_OWORD *)&xmmword_140177000 = 0;
  *(_OWORD *)&xmmword_140177030 = 0;
  *(&xmmword_140177040 + 1) = (PVOID)252;
  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  v1 = 24 * qword_140177050;
  LODWORD(dword_140177058) = -RecommendedSharedDataAlignment & (KeGetRecommendedSharedDataAlignment() + v1 - 1);
  v2 = KeGetRecommendedSharedDataAlignment();
  v3 = 16 * HIDWORD(qword_140177050);
  LODWORD(dword_14017705C) = -v2 & (KeGetRecommendedSharedDataAlignment() + v3 - 1);
  g_RaidNumberProcessors = KeQueryMaximumProcessorCountEx(0xFFFFu);
  LODWORD(Size) = dword_140177058 * g_RaidNumberProcessors;
  LODWORD(dword_140177064) = dword_14017705C * g_RaidNumberProcessors;
  if ( UseQPCTime )
    PerformanceCounter = KeQueryPerformanceCounter(0);
  else
    PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
  qword_140177068 = PerformanceCounter.QuadPart;
  if ( (_WORD)TelemetryPerfContext )
  {
    P = (PVOID)RaidAllocatePool(72, 8LL * (unsigned __int16)TelemetryPerfContext, 1700028754, 0);
    if ( !P )
    {
LABEL_6:
      v5 = -1073741801;
LABEL_60:
      StorpUninitializePerfTelemetry();
      g_StorpTraceLoggingPerformanceEnabled = 0;
      return v5;
    }
  }
  else
  {
    P = 0;
  }
  if ( WORD1(TelemetryPerfContext) )
  {
    qword_140176FD0 = (PVOID)RaidAllocatePool(72, 8LL * WORD1(TelemetryPerfContext), 1700028754, 0);
    if ( !qword_140176FD0 )
      goto LABEL_6;
  }
  else
  {
    qword_140176FD0 = 0;
  }
  if ( WORD2(TelemetryPerfContext) )
  {
    qword_140176FD8 = (PVOID)RaidAllocatePool(72, 8LL * WORD2(TelemetryPerfContext), 1700028754, 0);
    if ( !qword_140176FD8 )
      goto LABEL_6;
  }
  else
  {
    qword_140176FD8 = 0;
  }
  if ( HIWORD(TelemetryPerfContext) )
  {
    qword_140176FE0 = (PVOID)RaidAllocatePool(72, 8LL * HIWORD(TelemetryPerfContext), 1700028754, 0);
    if ( !qword_140176FE0 )
      goto LABEL_6;
  }
  else
  {
    qword_140176FE0 = 0;
  }
  if ( (_WORD)xmmword_140176FF0 )
  {
    *((_QWORD *)&xmmword_140176FF0 + 1) = RaidAllocatePool(72, 8LL * (unsigned __int16)xmmword_140176FF0, 1700028754, 0);
    if ( !*((_QWORD *)&xmmword_140176FF0 + 1) )
      goto LABEL_6;
  }
  else
  {
    *((_QWORD *)&xmmword_140176FF0 + 1) = 0;
  }
  if ( WORD1(xmmword_140176FF0) )
  {
    xmmword_140177000 = (PVOID)RaidAllocatePool(72, 8LL * WORD1(xmmword_140176FF0), 1700028754, 0);
    if ( !xmmword_140177000 )
      goto LABEL_6;
  }
  else
  {
    xmmword_140177000 = 0;
  }
  if ( WORD2(xmmword_140176FF0) )
  {
    *(&xmmword_140177000 + 1) = (PVOID)RaidAllocatePool(72, 8LL * WORD2(xmmword_140176FF0), 1700028754, 0);
    if ( !*(&xmmword_140177000 + 1) )
      goto LABEL_6;
  }
  else
  {
    *(&xmmword_140177000 + 1) = 0;
  }
  if ( WORD3(xmmword_140176FF0) )
  {
    xmmword_140177010 = (PVOID)RaidAllocatePool(72, 8LL * WORD3(xmmword_140176FF0), 1700028754, 0);
    if ( !xmmword_140177010 )
      goto LABEL_6;
  }
  else
  {
    xmmword_140177010 = 0;
  }
  if ( (_WORD)xmmword_140177020 )
  {
    *((_QWORD *)&xmmword_140177020 + 1) = RaidAllocatePool(72, 8LL * (unsigned __int16)xmmword_140177020, 1700028754, 0);
    if ( !*((_QWORD *)&xmmword_140177020 + 1) )
      goto LABEL_6;
  }
  else
  {
    *((_QWORD *)&xmmword_140177020 + 1) = 0;
  }
  if ( WORD1(xmmword_140177020) )
  {
    xmmword_140177030 = (PVOID)RaidAllocatePool(72, 8LL * WORD1(xmmword_140177020), 1700028754, 0);
    if ( !xmmword_140177030 )
      goto LABEL_6;
  }
  else
  {
    xmmword_140177030 = 0;
  }
  if ( WORD2(xmmword_140177020) )
  {
    *(&xmmword_140177030 + 1) = (PVOID)RaidAllocatePool(72, 8LL * WORD2(xmmword_140177020), 1700028754, 0);
    if ( !*(&xmmword_140177030 + 1) )
      goto LABEL_6;
  }
  else
  {
    *(&xmmword_140177030 + 1) = 0;
  }
  if ( WORD3(xmmword_140177020) )
  {
    xmmword_140177040 = (PVOID)RaidAllocatePool(72, 8LL * WORD3(xmmword_140177020), 1700028754, 0);
    if ( !xmmword_140177040 )
      goto LABEL_6;
  }
  else
  {
    xmmword_140177040 = 0;
  }
  v6 = UseQPCTime == 0;
  *(_QWORD *)P = 0;
  *((_QWORD *)P + 1) = 1;
  **((_QWORD **)&xmmword_140176FF0 + 1) = 0;
  *(_QWORD *)(*((_QWORD *)&xmmword_140176FF0 + 1) + 8LL) = 1;
  **((_QWORD **)&xmmword_140177020 + 1) = 0;
  *(_QWORD *)(*((_QWORD *)&xmmword_140177020 + 1) + 8LL) = 1;
  if ( v6 || !g_StorpTraceLoggingPerformanceHighResolutionTimer )
  {
    *(_QWORD *)qword_140176FD0 = 1280;
    *((_QWORD *)qword_140176FD0 + 1) = 2560;
    *((_QWORD *)qword_140176FD0 + 2) = 5120;
    *((_QWORD *)qword_140176FD0 + 3) = 10000;
    *((_QWORD *)qword_140176FD0 + 4) = 40000;
    *((_QWORD *)qword_140176FD0 + 5) = 160000;
    *((_QWORD *)qword_140176FD0 + 6) = 640000;
    *((_QWORD *)qword_140176FD0 + 7) = 1280000;
    *((_QWORD *)qword_140176FD0 + 8) = 2560000;
    *((_QWORD *)qword_140176FD0 + 9) = 5120000;
    *((_QWORD *)qword_140176FD0 + 10) = 10000000;
    *((_QWORD *)qword_140176FD0 + 11) = 20000000;
    *((_QWORD *)qword_140176FD0 + 12) = 100000000;
    *((_QWORD *)qword_140176FD0 + 13) = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)xmmword_140177000 = 640000;
    *((_QWORD *)xmmword_140177000 + 1) = 2560000;
    *((_QWORD *)xmmword_140177000 + 2) = 10240000;
    *((_QWORD *)xmmword_140177000 + 3) = 51200000;
    *((_QWORD *)xmmword_140177000 + 4) = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)*(&xmmword_140177030 + 1) = 1280;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 1) = 2560;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 2) = 5120;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 3) = 10000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 4) = 40000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 5) = 160000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 6) = 640000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 7) = 1280000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 8) = 2560000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 9) = 5120000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 10) = 10000000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 11) = 20000000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 12) = 100000000;
  }
  else
  {
    KeQueryPerformanceCounter(&PerformanceFrequency);
    *(_QWORD *)qword_140176FD0 = (PerformanceFrequency.QuadPart << 7) / 1000000;
    *((_QWORD *)qword_140176FD0 + 1) = (PerformanceFrequency.QuadPart << 8) / 1000000;
    *((_QWORD *)qword_140176FD0 + 2) = (PerformanceFrequency.QuadPart << 9) / 1000000;
    *((_QWORD *)qword_140176FD0 + 3) = PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 4) = 4 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 5) = 16 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 6) = (PerformanceFrequency.QuadPart << 6) / 1000;
    *((_QWORD *)qword_140176FD0 + 7) = (PerformanceFrequency.QuadPart << 7) / 1000;
    *((_QWORD *)qword_140176FD0 + 8) = (PerformanceFrequency.QuadPart << 8) / 1000;
    *((_QWORD *)qword_140176FD0 + 9) = (PerformanceFrequency.QuadPart << 9) / 1000;
    *((_QWORD *)qword_140176FD0 + 10) = 1000 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 11) = 2000 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 12) = 10000 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)qword_140176FD0 + 13) = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)xmmword_140177000 = (PerformanceFrequency.QuadPart << 6) / 1000;
    *((_QWORD *)xmmword_140177000 + 1) = (PerformanceFrequency.QuadPart << 8) / 1000;
    *((_QWORD *)xmmword_140177000 + 2) = (PerformanceFrequency.QuadPart << 10) / 1000;
    *((_QWORD *)xmmword_140177000 + 3) = 5120 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)xmmword_140177000 + 4) = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)*(&xmmword_140177030 + 1) = (PerformanceFrequency.QuadPart << 7) / 1000000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 1) = (PerformanceFrequency.QuadPart << 8) / 1000000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 2) = (PerformanceFrequency.QuadPart << 9) / 1000000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 3) = PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 4) = 4 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 5) = 16 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 6) = (PerformanceFrequency.QuadPart << 6) / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 7) = (PerformanceFrequency.QuadPart << 7) / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 8) = (PerformanceFrequency.QuadPart << 8) / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 9) = (PerformanceFrequency.QuadPart << 9) / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 10) = 1000 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 11) = 2000 * PerformanceFrequency.QuadPart / 1000;
    *((_QWORD *)*(&xmmword_140177030 + 1) + 12) = 10000 * PerformanceFrequency.QuadPart / 1000;
  }
  *((_QWORD *)*(&xmmword_140177030 + 1) + 13) = 0x7FFFFFFFFFFFFFFFLL;
  *(_QWORD *)xmmword_140177030 = 4096;
  *((_QWORD *)xmmword_140177030 + 1) = 0x2000;
  *((_QWORD *)xmmword_140177030 + 2) = 0x4000;
  *((_QWORD *)xmmword_140177030 + 3) = 0x8000;
  *((_QWORD *)xmmword_140177030 + 4) = 0x10000;
  *((_QWORD *)xmmword_140177030 + 5) = 0x20000;
  *((_QWORD *)xmmword_140177030 + 6) = 0x40000;
  *((_QWORD *)xmmword_140177030 + 7) = 0x100000;
  *((_QWORD *)xmmword_140177030 + 8) = 0x7FFFFFFFFFFFFFFFLL;
  v7 = KeGetRecommendedSharedDataAlignment() + 31;
  dword_140177070 = v7 & -KeGetRecommendedSharedDataAlignment();
  LODWORD(dword_140177074) = g_RaidNumberProcessors * dword_140177070;
  v8 = KeGetRecommendedSharedDataAlignment();
  v9 = 4 * g_RaidNumberProcessors;
  v10 = -v8 & (KeGetRecommendedSharedDataAlignment() + v9 - 1);
  qword_140177078 = (PVOID)RaidAllocatePool(72, v10, 1700028754, 0);
  if ( !qword_140177078
    || (qword_140177080 = (PVOID)RaidAllocatePool(72, v10, 1700028754, 0)) == 0
    || (qword_140177088 = (PVOID)RaidAllocatePool(72, v10, 1700028754, 0)) == 0 )
  {
    v5 = -1073741670;
    goto LABEL_60;
  }
  v11 = g_RaidNumberProcessors;
  for ( i = 0; i < v11; *((_DWORD *)qword_140177088 + v13) = v14 )
  {
    v13 = i;
    *((_DWORD *)qword_140177078 + i) = dword_140177058 * i;
    *((_DWORD *)qword_140177080 + i) = dword_14017705C * i;
    v14 = dword_140177070 * i++;
  }
  return 0;
}

```

## disassembly

```asm
0x1400d7c20  push    rbp
0x1400d7c22  push    rbx
0x1400d7c23  push    rsi
0x1400d7c24  push    rdi
0x1400d7c25  push    r14
0x1400d7c27  push    r15
0x1400d7c29  mov     rbp, rsp
0x1400d7c2c  sub     rsp, 28h
0x1400d7c30  xor     esi, esi
0x1400d7c32  lea     rcx, TelemetryPerfContext; void *
0x1400d7c39  xor     edx, edx; Val
0x1400d7c3b  mov     qword ptr [rbp+PerformanceFrequency], rsi
0x1400d7c3f  mov     r8d, 0D0h; Size
0x1400d7c45  call    memset_0
0x1400d7c4a  xorps   xmm0, xmm0
0x1400d7c4d  mov     cs:TelemetryPerfContext, 0E0002h
0x1400d7c58  lea     r9d, [rsi+1Ch]
0x1400d7c5c  mov     ecx, 0FCh
0x1400d7c61  lea     edx, [rsi+0Ah]
0x1400d7c64  mov     qword ptr cs:byte_140176FE8, r9
0x1400d7c6b  movups  cs:xmmword_140177010, xmm0
0x1400d7c72  lea     eax, [r9+rdx]
0x1400d7c76  mov     dword ptr cs:xmmword_140177010+8, edx
0x1400d7c7c  movups  cs:xmmword_140177020, xmm0
0x1400d7c83  mov     dword ptr cs:qword_140177050, eax
0x1400d7c89  movups  cs:xmmword_140176FF0, xmm0
0x1400d7c90  mov     qword ptr cs:xmmword_140176FF0, 50002h
0x1400d7c9b  movups  cs:xmmword_140177040, xmm0
0x1400d7ca2  mov     dword ptr cs:xmmword_140177020, 90002h
0x1400d7cac  movups  cs:xmmword_140177000, xmm0
0x1400d7cb3  mov     dword ptr cs:xmmword_140177020+4, 0Eh
0x1400d7cbd  movups  cs:xmmword_140177030, xmm0
0x1400d7cc4  mov     qword ptr cs:xmmword_140177040+8, rcx
0x1400d7ccb  mov     dword ptr cs:xmmword_140177010+0Ch, r9d
0x1400d7cd2  mov     dword ptr cs:qword_140177050+4, ecx
0x1400d7cd8  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400d7cdf  nop     dword ptr [rax+rax+00h]
0x1400d7ce4  mov     edi, eax
0x1400d7ce6  mov     eax, dword ptr cs:qword_140177050
0x1400d7cec  lea     ecx, [rax+rax*2]
0x1400d7cef  lea     ebx, ds:0[rcx*8]
0x1400d7cf6  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400d7cfd  nop     dword ptr [rax+rax+00h]
0x1400d7d02  lea     ecx, [rbx-1]
0x1400d7d05  neg     edi
0x1400d7d07  add     ecx, eax
0x1400d7d09  and     ecx, edi
0x1400d7d0b  mov     cs:dword_140177058, ecx
0x1400d7d11  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400d7d18  nop     dword ptr [rax+rax+00h]
0x1400d7d1d  mov     ebx, dword ptr cs:qword_140177050+4
0x1400d7d23  mov     edi, eax
0x1400d7d25  shl     ebx, 4
0x1400d7d28  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400d7d2f  nop     dword ptr [rax+rax+00h]
0x1400d7d34  lea     ecx, [rbx-1]
0x1400d7d37  neg     edi
0x1400d7d39  add     ecx, eax
0x1400d7d3b  and     ecx, edi
0x1400d7d3d  mov     cs:dword_14017705C, ecx
0x1400d7d43  mov     ecx, 0FFFFh; GroupNumber
0x1400d7d48  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400d7d4f  nop     dword ptr [rax+rax+00h]
0x1400d7d54  mov     ecx, eax
0x1400d7d56  mov     cs:g_RaidNumberProcessors, eax
0x1400d7d5c  imul    ecx, cs:dword_140177058
0x1400d7d63  imul    eax, cs:dword_14017705C
0x1400d7d6a  cmp     cs:UseQPCTime, sil
0x1400d7d71  mov     cs:Size, ecx
0x1400d7d77  mov     cs:dword_140177064, eax
0x1400d7d7d  jz      short loc_1400D7D8F
0x1400d7d7f  xor     ecx, ecx; PerformanceFrequency
0x1400d7d81  call    cs:__imp_KeQueryPerformanceCounter
0x1400d7d88  nop     dword ptr [rax+rax+00h]
0x1400d7d8d  jmp     short loc_1400D7D9B
0x1400d7d8f  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400d7d96  nop     dword ptr [rax+rax+00h]
0x1400d7d9b  mov     cs:qword_140177068, rax
0x1400d7da2  mov     r14d, 65546152h
0x1400d7da8  movzx   eax, word ptr cs:TelemetryPerfContext
0x1400d7daf  mov     r15d, 48h ; 'H'
0x1400d7db5  test    ax, ax
0x1400d7db8  jz      short loc_1400D7DE4
0x1400d7dba  mov     edx, eax
0x1400d7dbc  xor     r9d, r9d
0x1400d7dbf  shl     rdx, 3
0x1400d7dc3  mov     r8d, r14d
0x1400d7dc6  mov     ecx, r15d
0x1400d7dc9  call    RaidAllocatePool
0x1400d7dce  mov     cs:P, rax
0x1400d7dd5  test    rax, rax
0x1400d7dd8  jnz     short loc_1400D7DEB
0x1400d7dda  mov     ebx, 0C0000017h
0x1400d7ddf  jmp     loc_1400D889E
0x1400d7de4  mov     cs:P, rsi
0x1400d7deb  movzx   eax, word ptr cs:TelemetryPerfContext+2
0x1400d7df2  test    ax, ax
0x1400d7df5  jz      short loc_1400D7E19
0x1400d7df7  mov     edx, eax
0x1400d7df9  xor     r9d, r9d
0x1400d7dfc  shl     rdx, 3
0x1400d7e00  mov     r8d, r14d
0x1400d7e03  mov     rcx, r15
0x1400d7e06  call    RaidAllocatePool
0x1400d7e0b  mov     cs:qword_140176FD0, rax
0x1400d7e12  test    rax, rax
0x1400d7e15  jnz     short loc_1400D7E20
0x1400d7e17  jmp     short loc_1400D7DDA
0x1400d7e19  mov     cs:qword_140176FD0, rsi
0x1400d7e20  movzx   eax, word ptr cs:TelemetryPerfContext+4
0x1400d7e27  test    ax, ax
0x1400d7e2a  jz      short loc_1400D7E4E
0x1400d7e2c  mov     edx, eax
0x1400d7e2e  xor     r9d, r9d
0x1400d7e31  shl     rdx, 3
0x1400d7e35  mov     r8d, r14d
0x1400d7e38  mov     rcx, r15
0x1400d7e3b  call    RaidAllocatePool
0x1400d7e40  mov     cs:qword_140176FD8, rax
0x1400d7e47  test    rax, rax
0x1400d7e4a  jnz     short loc_1400D7E55
0x1400d7e4c  jmp     short loc_1400D7DDA
0x1400d7e4e  mov     cs:qword_140176FD8, rsi
0x1400d7e55  movzx   eax, word ptr cs:TelemetryPerfContext+6
0x1400d7e5c  test    ax, ax
0x1400d7e5f  jz      short loc_1400D7E86
0x1400d7e61  mov     edx, eax
0x1400d7e63  xor     r9d, r9d
0x1400d7e66  shl     rdx, 3
0x1400d7e6a  mov     r8d, r14d
0x1400d7e6d  mov     rcx, r15
0x1400d7e70  call    RaidAllocatePool
0x1400d7e75  mov     cs:qword_140176FE0, rax
0x1400d7e7c  test    rax, rax
0x1400d7e7f  jnz     short loc_1400D7E8D
0x1400d7e81  jmp     loc_1400D7DDA
0x1400d7e86  mov     cs:qword_140176FE0, rsi
0x1400d7e8d  movzx   eax, word ptr cs:xmmword_140176FF0
0x1400d7e94  test    ax, ax
0x1400d7e97  jz      short loc_1400D7EBE
0x1400d7e99  mov     edx, eax
0x1400d7e9b  xor     r9d, r9d
0x1400d7e9e  shl     rdx, 3
0x1400d7ea2  mov     r8d, r14d
0x1400d7ea5  mov     rcx, r15
0x1400d7ea8  call    RaidAllocatePool
0x1400d7ead  mov     qword ptr cs:xmmword_140176FF0+8, rax
0x1400d7eb4  test    rax, rax
0x1400d7eb7  jnz     short loc_1400D7EC5
0x1400d7eb9  jmp     loc_1400D7DDA
0x1400d7ebe  mov     qword ptr cs:xmmword_140176FF0+8, rsi
0x1400d7ec5  movzx   eax, word ptr cs:xmmword_140176FF0+2
0x1400d7ecc  test    ax, ax
0x1400d7ecf  jz      short loc_1400D7EF6
0x1400d7ed1  mov     edx, eax
0x1400d7ed3  xor     r9d, r9d
0x1400d7ed6  shl     rdx, 3
0x1400d7eda  mov     r8d, r14d
0x1400d7edd  mov     rcx, r15
0x1400d7ee0  call    RaidAllocatePool
0x1400d7ee5  mov     qword ptr cs:xmmword_140177000, rax
0x1400d7eec  test    rax, rax
0x1400d7eef  jnz     short loc_1400D7EFD
0x1400d7ef1  jmp     loc_1400D7DDA
0x1400d7ef6  mov     qword ptr cs:xmmword_140177000, rsi
0x1400d7efd  movzx   eax, word ptr cs:xmmword_140176FF0+4
0x1400d7f04  test    ax, ax
0x1400d7f07  jz      short loc_1400D7F2E
0x1400d7f09  mov     edx, eax
0x1400d7f0b  xor     r9d, r9d
0x1400d7f0e  shl     rdx, 3
0x1400d7f12  mov     r8d, r14d
0x1400d7f15  mov     rcx, r15
0x1400d7f18  call    RaidAllocatePool
0x1400d7f1d  mov     qword ptr cs:xmmword_140177000+8, rax
0x1400d7f24  test    rax, rax
0x1400d7f27  jnz     short loc_1400D7F35
0x1400d7f29  jmp     loc_1400D7DDA
0x1400d7f2e  mov     qword ptr cs:xmmword_140177000+8, rsi
0x1400d7f35  movzx   eax, word ptr cs:xmmword_140176FF0+6
0x1400d7f3c  test    ax, ax
0x1400d7f3f  jz      short loc_1400D7F66
0x1400d7f41  mov     edx, eax
0x1400d7f43  xor     r9d, r9d
0x1400d7f46  shl     rdx, 3
0x1400d7f4a  mov     r8d, r14d
0x1400d7f4d  mov     rcx, r15
0x1400d7f50  call    RaidAllocatePool
0x1400d7f55  mov     qword ptr cs:xmmword_140177010, rax
0x1400d7f5c  test    rax, rax
0x1400d7f5f  jnz     short loc_1400D7F6D
0x1400d7f61  jmp     loc_1400D7DDA
0x1400d7f66  mov     qword ptr cs:xmmword_140177010, rsi
0x1400d7f6d  movzx   eax, word ptr cs:xmmword_140177020
0x1400d7f74  test    ax, ax
0x1400d7f77  jz      short loc_1400D7F9E
0x1400d7f79  mov     edx, eax
0x1400d7f7b  xor     r9d, r9d
0x1400d7f7e  shl     rdx, 3
0x1400d7f82  mov     r8d, r14d
0x1400d7f85  mov     rcx, r15
0x1400d7f88  call    RaidAllocatePool
0x1400d7f8d  mov     qword ptr cs:xmmword_140177020+8, rax
0x1400d7f94  test    rax, rax
0x1400d7f97  jnz     short loc_1400D7FA5
0x1400d7f99  jmp     loc_1400D7DDA
0x1400d7f9e  mov     qword ptr cs:xmmword_140177020+8, rsi
0x1400d7fa5  movzx   eax, word ptr cs:xmmword_140177020+2
0x1400d7fac  test    ax, ax
0x1400d7faf  jz      short loc_1400D7FD6
0x1400d7fb1  mov     edx, eax
0x1400d7fb3  xor     r9d, r9d
0x1400d7fb6  shl     rdx, 3
0x1400d7fba  mov     r8d, r14d
0x1400d7fbd  mov     rcx, r15
0x1400d7fc0  call    RaidAllocatePool
0x1400d7fc5  mov     qword ptr cs:xmmword_140177030, rax
0x1400d7fcc  test    rax, rax
0x1400d7fcf  jnz     short loc_1400D7FDD
0x1400d7fd1  jmp     loc_1400D7DDA
0x1400d7fd6  mov     qword ptr cs:xmmword_140177030, rsi
0x1400d7fdd  movzx   eax, word ptr cs:xmmword_140177020+4
0x1400d7fe4  test    ax, ax
0x1400d7fe7  jz      short loc_1400D800E
0x1400d7fe9  mov     edx, eax
0x1400d7feb  xor     r9d, r9d
0x1400d7fee  shl     rdx, 3
0x1400d7ff2  mov     r8d, r14d
0x1400d7ff5  mov     rcx, r15
0x1400d7ff8  call    RaidAllocatePool
0x1400d7ffd  mov     qword ptr cs:xmmword_140177030+8, rax
0x1400d8004  test    rax, rax
0x1400d8007  jnz     short loc_1400D8015
0x1400d8009  jmp     loc_1400D7DDA
0x1400d800e  mov     qword ptr cs:xmmword_140177030+8, rsi
0x1400d8015  movzx   eax, word ptr cs:xmmword_140177020+6
0x1400d801c  test    ax, ax
0x1400d801f  jz      short loc_1400D8046
0x1400d8021  mov     edx, eax
0x1400d8023  xor     r9d, r9d
0x1400d8026  shl     rdx, 3
0x1400d802a  mov     r8d, r14d
0x1400d802d  mov     rcx, r15
0x1400d8030  call    RaidAllocatePool
0x1400d8035  mov     qword ptr cs:xmmword_140177040, rax
0x1400d803c  test    rax, rax
0x1400d803f  jnz     short loc_1400D804D
0x1400d8041  jmp     loc_1400D7DDA
0x1400d8046  mov     qword ptr cs:xmmword_140177040, rsi
0x1400d804d  cmp     cs:UseQPCTime, sil
0x1400d8054  mov     rax, cs:P
0x1400d805b  mov     [rax], rsi
0x1400d805e  mov     rax, cs:P
0x1400d8065  mov     qword ptr [rax+8], 1
0x1400d806d  mov     rax, qword ptr cs:xmmword_140176FF0+8
0x1400d8074  mov     [rax], rsi
0x1400d8077  mov     rax, qword ptr cs:xmmword_140176FF0+8
0x1400d807e  mov     qword ptr [rax+8], 1
0x1400d8086  mov     rax, qword ptr cs:xmmword_140177020+8
0x1400d808d  mov     [rax], rsi
0x1400d8090  mov     rax, qword ptr cs:xmmword_140177020+8
0x1400d8097  mov     qword ptr [rax+8], 1
0x1400d809f  jz      loc_1400D8587
0x1400d80a5  cmp     cs:g_StorpTraceLoggingPerformanceHighResolutionTimer, esi
0x1400d80ab  jz      loc_1400D8587
0x1400d80b1  lea     rcx, [rbp+PerformanceFrequency]; PerformanceFrequency
0x1400d80b5  call    cs:__imp_KeQueryPerformanceCounter
0x1400d80bc  nop     dword ptr [rax+rax+00h]
0x1400d80c1  mov     rcx, qword ptr [rbp+PerformanceFrequency]
0x1400d80c5  mov     r9, 431BDE82D7B634DBh
0x1400d80cf  shl     rcx, 7
0x1400d80d3  mov     r10, 20C49BA5E353F7CFh
0x1400d80dd  mov     rax, r9
0x1400d80e0  imul    rcx
0x1400d80e3  sar     rdx, 12h
0x1400d80e7  mov     rax, rdx
0x1400d80ea  shr     rax, 3Fh
0x1400d80ee  add     rdx, rax
0x1400d80f1  mov     rax, cs:qword_140176FD0
0x1400d80f8  mov     [rax], rdx
0x1400d80fb  mov     rax, r9
0x1400d80fe  mov     rcx, qword ptr [rbp+PerformanceFrequency]
0x1400d8102  shl     rcx, 8
0x1400d8106  imul    rcx
0x1400d8109  sar     rdx, 12h
0x1400d810d  mov     rax, rdx
0x1400d8110  shr     rax, 3Fh
0x1400d8114  add     rdx, rax
0x1400d8117  mov     rax, cs:qword_140176FD0
0x1400d811e  mov     [rax+8], rdx
0x1400d8122  mov     rax, r9
0x1400d8125  mov     rcx, qword ptr [rbp+PerformanceFrequency]
0x1400d8129  shl     rcx, 9
0x1400d812d  imul    rcx
0x1400d8130  sar     rdx, 12h
0x1400d8134  mov     rax, rdx
0x1400d8137  shr     rax, 3Fh
0x1400d813b  add     rdx, rax
0x1400d813e  mov     rax, cs:qword_140176FD0
0x1400d8145  mov     [rax+10h], rdx
  ... truncated ...
```
