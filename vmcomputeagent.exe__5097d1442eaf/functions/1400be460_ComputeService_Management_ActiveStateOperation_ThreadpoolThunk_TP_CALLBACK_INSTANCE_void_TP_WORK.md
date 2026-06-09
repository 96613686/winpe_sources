# ComputeService::Management::ActiveStateOperation::ThreadpoolThunk(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1400be460`
- end: `0x1400be81f`
- name: `?ThreadpoolThunk@ActiveStateOperation@Management@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `959`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140033d28`
- `0x14003407c`
- `0x14003f850`
- `0x1400be460`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be55d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be7d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be55d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400be7d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be56b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be7de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be56b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400be7de`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400be482`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400be482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400be64d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400be64d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ComputeService::Management::ActiveStateOperation::ThreadpoolThunk(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r14
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  __int64 v10; // rdx
  void *v11; // rbx
  HANDLE v12; // rax
  void (__fastcall *v13)(__int128 *, _QWORD **); // r14
  __int64 v14; // r8
  __int64 v15; // rdx
  signed __int32 v16; // eax
  signed __int32 v17; // ett
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  void *v21; // rbx
  HANDLE v22; // rax
  _QWORD *v23; // [rsp+20h] [rbp-198h] BYREF
  __int128 v24; // [rsp+28h] [rbp-190h]
  __int64 v25; // [rsp+38h] [rbp-180h] BYREF
  _DWORD v26[2]; // [rsp+40h] [rbp-178h] BYREF
  __int128 v27; // [rsp+48h] [rbp-170h] BYREF
  __int64 v28; // [rsp+58h] [rbp-160h]
  __int64 v29; // [rsp+60h] [rbp-158h] BYREF
  _QWORD v30[2]; // [rsp+68h] [rbp-150h] BYREF
  __int64 v31; // [rsp+78h] [rbp-140h]
  _BYTE v32[32]; // [rsp+80h] [rbp-138h] BYREF
  int v33; // [rsp+A0h] [rbp-118h] BYREF
  __int16 v34; // [rsp+A8h] [rbp-110h]
  __int64 v35; // [rsp+AAh] [rbp-10Eh]
  int v36; // [rsp+B2h] [rbp-106h]
  __int16 epi16; // [rsp+B6h] [rbp-102h]
  __int64 v38; // [rsp+B8h] [rbp-100h]
  __int64 v39; // [rsp+C0h] [rbp-F8h]
  __int128 v40; // [rsp+C8h] [rbp-F0h]
  __int64 v41; // [rsp+D8h] [rbp-E0h]
  __int128 v42; // [rsp+E0h] [rbp-D8h]
  __int64 v43; // [rsp+F0h] [rbp-C8h]
  ComputeService::Reporting::ComputeException *v44; // [rsp+F8h] [rbp-C0h] BYREF
  wil::ResultException *v45; // [rsp+100h] [rbp-B8h] BYREF
  _QWORD *v46; // [rsp+108h] [rbp-B0h] BYREF
  __int128 v47; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v48; // [rsp+120h] [rbp-98h] BYREF
  LPVOID lpMem[2]; // [rsp+130h] [rbp-88h]
  _QWORD v50[3]; // [rsp+140h] [rbp-78h] BYREF
  int v51; // [rsp+158h] [rbp-60h]
  __int128 *v52; // [rsp+160h] [rbp-58h]
  char v53; // [rsp+168h] [rbp-50h]
  char v54; // [rsp+170h] [rbp-48h]

  CallbackMayRunLong(Instance);
  try
  {
    v46 = Context;
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(*Context + 320LL),
      v4);
    v54 = 0;
    v5 = *(_QWORD *)(*Context + 424LL);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v5 + 40LL))(v5, v26);
      if ( v54 )
      {
        if ( v51 )
          wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v50);
        if ( LOBYTE(lpMem[1]) )
        {
          v7 = lpMem[0];
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
        }
        lpMem[0] = 0;
        v54 = 0;
      }
      v48 = 0;
      *(_OWORD *)lpMem = 0;
      LODWORD(v48) = *(_DWORD *)v6;
      *((_QWORD *)&v48 + 1) = *(_QWORD *)(v6 + 8);
      if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) )
      {
        v9 = GetProcessHeap();
        HeapFree(v9, 0, 0);
        LOBYTE(lpMem[1]) = 0;
      }
      lpMem[0] = 0;
      lpMem[0] = *(LPVOID *)(v6 + 16);
      *(_QWORD *)(v6 + 16) = 0;
      LOBYTE(lpMem[1]) = *(_BYTE *)(v6 + 24);
      *(_BYTE *)(v6 + 24) = 0;
      v50[0] = 0;
      v50[1] = *(_QWORD *)(v6 + 40);
      v50[2] = 0;
      v51 = 0;
      v52 = *(__int128 **)(v6 + 64);
      v53 = 0;
      if ( *(_DWORD *)(v6 + 56) )
      {
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v6 + 32));
        wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v50, v10);
      }
      v52 = &v48;
      v54 = 1;
      if ( (_DWORD)v31 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v29);
      if ( (_BYTE)v28 )
      {
        v11 = (void *)*((_QWORD *)&v27 + 1);
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v11);
      }
    }
    v13 = *(void (__fastcall **)(__int128 *, _QWORD **))(*Context + 416LL);
    *(_QWORD *)(*Context + 416LL) = 0;
    *(_DWORD *)(*Context + 124LL) = GetCurrentThreadId();
    *(_BYTE *)(*Context + 120LL) = 0;
    v47 = 0;
    v14 = *Context;
    v47 = 0;
    v15 = *(_QWORD *)(v14 + 40);
    if ( v15 )
    {
      v16 = *(_DWORD *)(v15 + 8);
      while ( v16 )
      {
        v17 = v16;
        v16 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 8), v16 + 1, v16);
        if ( v17 == v16 )
        {
          v47 = *(_OWORD *)(v14 + 32);
          break;
        }
      }
    }
    if ( (_QWORD)v47 )
    {
      v24 = 0;
      v18 = Context[1];
      if ( v18 )
        _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
      *(_QWORD *)&v24 = *Context;
      v19 = (volatile signed __int32 *)Context[1];
      *((_QWORD *)&v24 + 1) = v19;
      v46 = 0;
      v25 = 0;
      v23 = Context;
      std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v25);
      try
      {
        v13(&v47, &v23);
      }
      catch ( ComputeService::Reporting::ComputeException *v44 )
      {
        ComputeService::Management::StateOperation::Complete((ComputeService::Management::StateOperation *)v24, v44);
        v19 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
      }
      catch ( wil::ResultException *v45 )
      {
        v26[0] = *((_DWORD *)v45 + 8);
        v26[1] = 0;
        v27 = 0;
        v33 = v26[0];
        v34 = 0;
        v35 = 0;
        v36 = 0;
        epi16 = _mm_extract_epi16((__m128i)0LL, 7);
        v38 = 0;
        v39 = 7;
        v28 = 0;
        v29 = 7;
        LOWORD(v27) = 0;
        v31 = 0;
        v30[1] = 0;
        v30[0] = 0;
        v40 = 0;
        v41 = 0;
        memset(v32, 0, 24);
        v42 = 0;
        v43 = 0;
        ComputeService::Management::StateOperation::Complete(v24, &v33);
        std::vector<Schema::Responses::Attribution::AttributionRecord>::_Tidy(v32);
        std::vector<Schema::Responses::Service::ErrorEvent>::_Tidy(v30);
        std::wstring::~wstring(&v27);
        v19 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
      }
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
    }
    v20 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    if ( v54 )
    {
      if ( v51 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v50);
      if ( LOBYTE(lpMem[1]) )
      {
        v21 = lpMem[0];
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v21);
        LOBYTE(lpMem[1]) = 0;
      }
      lpMem[0] = 0;
    }
    std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v46);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1400be460  push    rbx
0x1400be462  push    rsi
0x1400be463  push    rdi
0x1400be464  push    r14
0x1400be466  sub     rsp, 198h
0x1400be46d  mov     rax, cs:__security_cookie
0x1400be474  xor     rax, rsp
0x1400be477  mov     [rsp+1B8h+var_38], rax
0x1400be47f  mov     rsi, rdx
0x1400be482  call    cs:__imp_CallbackMayRunLong
0x1400be488  mov     [rsp+1B8h+var_B0], rsi
0x1400be490  mov     rcx, [rsi]
0x1400be493  add     rcx, 140h; this
0x1400be49a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400be49f  xor     edi, edi
0x1400be4a1  mov     [rsp+1B8h+var_48], dil
0x1400be4a9  mov     rax, [rsi]
0x1400be4ac  mov     rcx, [rax+1A8h]
0x1400be4b3  test    rcx, rcx
0x1400be4b6  jz      loc_1400BE63C
0x1400be4bc  mov     rax, [rcx]
0x1400be4bf  lea     rdx, [rsp+1B8h+var_178]
0x1400be4c4  mov     rax, [rax+28h]
0x1400be4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be4cd  mov     r14, rax
0x1400be4d0  cmp     [rsp+1B8h+var_48], dil
0x1400be4d8  jz      short loc_1400BE527
0x1400be4da  cmp     [rsp+1B8h+var_60], edi
0x1400be4e1  jz      short loc_1400BE4F1
0x1400be4e3  lea     rcx, [rsp+1B8h+var_78]; this
0x1400be4eb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400be4f0  nop
0x1400be4f1  cmp     byte ptr [rsp+1B8h+lpMem+8], dil
0x1400be4f9  jz      short loc_1400BE517
0x1400be4fb  mov     rbx, [rsp+1B8h+lpMem]
0x1400be503  call    cs:__imp_GetProcessHeap
0x1400be509  mov     r8, rbx; lpMem
0x1400be50c  xor     edx, edx; dwFlags
0x1400be50e  mov     rcx, rax; hHeap
0x1400be511  call    cs:__imp_HeapFree
0x1400be517  mov     [rsp+1B8h+lpMem], rdi
0x1400be51f  mov     [rsp+1B8h+var_48], dil
0x1400be527  xorps   xmm0, xmm0
0x1400be52a  movups  [rsp+1B8h+var_98], xmm0
0x1400be532  movaps  xmmword ptr [rsp+1B8h+lpMem], xmm0
0x1400be53a  mov     eax, [r14]
0x1400be53d  mov     dword ptr [rsp+1B8h+var_98], eax
0x1400be544  mov     rax, [r14+8]
0x1400be548  mov     qword ptr [rsp+1B8h+var_98+8], rax
0x1400be550  psrldq  xmm0, 8
0x1400be555  movd    eax, xmm0
0x1400be559  test    al, al
0x1400be55b  jz      short loc_1400BE579
0x1400be55d  call    cs:__imp_GetProcessHeap
0x1400be563  xor     r8d, r8d; lpMem
0x1400be566  xor     edx, edx; dwFlags
0x1400be568  mov     rcx, rax; hHeap
0x1400be56b  call    cs:__imp_HeapFree
0x1400be571  mov     byte ptr [rsp+1B8h+lpMem+8], dil
0x1400be579  mov     [rsp+1B8h+lpMem], rdi
0x1400be581  mov     rax, [r14+10h]
0x1400be585  mov     [rsp+1B8h+lpMem], rax
0x1400be58d  mov     [r14+10h], rdi
0x1400be591  mov     al, [r14+18h]
0x1400be595  mov     byte ptr [rsp+1B8h+lpMem+8], al
0x1400be59c  mov     [r14+18h], dil
0x1400be5a0  lea     rcx, [r14+20h]; this
0x1400be5a4  mov     [rsp+1B8h+var_78], rdi
0x1400be5ac  mov     rax, [rcx+8]
0x1400be5b0  mov     [rsp+1B8h+var_70], rax
0x1400be5b8  mov     [rsp+1B8h+var_68], rdi
0x1400be5c0  mov     [rsp+1B8h+var_60], edi
0x1400be5c7  mov     rax, [rcx+20h]
0x1400be5cb  mov     [rsp+1B8h+var_58], rax
0x1400be5d3  mov     [rsp+1B8h+var_50], dil
0x1400be5db  cmp     [rcx+18h], edi
0x1400be5de  jz      short loc_1400BE5F3
0x1400be5e0  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400be5e5  lea     rcx, [rsp+1B8h+var_78]; this
0x1400be5ed  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400be5f2  nop
0x1400be5f3  lea     rax, [rsp+1B8h+var_98]
0x1400be5fb  mov     [rsp+1B8h+var_58], rax
0x1400be603  mov     [rsp+1B8h+var_48], 1
0x1400be60b  cmp     dword ptr [rsp+1B8h+var_140], edi
0x1400be60f  jz      short loc_1400BE61C
0x1400be611  lea     rcx, [rsp+1B8h+var_158]; this
0x1400be616  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400be61b  nop
0x1400be61c  cmp     byte ptr [rsp+1B8h+var_160], dil
0x1400be621  jz      short loc_1400BE63C
0x1400be623  mov     rbx, [rsp+1B8h+var_168]
0x1400be628  call    cs:__imp_GetProcessHeap
0x1400be62e  mov     r8, rbx; lpMem
0x1400be631  xor     edx, edx; dwFlags
0x1400be633  mov     rcx, rax; hHeap
0x1400be636  call    cs:__imp_HeapFree
0x1400be63c  mov     rax, [rsi]
0x1400be63f  mov     r14, [rax+1A0h]
0x1400be646  mov     [rax+1A0h], rdi
0x1400be64d  call    cs:__imp_GetCurrentThreadId
0x1400be653  mov     rcx, [rsi]
0x1400be656  mov     [rcx+7Ch], eax
0x1400be659  mov     rax, [rsi]
0x1400be65c  mov     [rax+78h], dil
0x1400be660  xorps   xmm0, xmm0
0x1400be663  movups  [rsp+1B8h+var_A8], xmm0
0x1400be66b  mov     r8, [rsi]
0x1400be66e  movdqu  [rsp+1B8h+var_A8], xmm0
0x1400be677  mov     rdx, [r8+28h]
0x1400be67b  test    rdx, rdx
0x1400be67e  jz      short loc_1400BE6AD
0x1400be680  mov     eax, [rdx+8]
0x1400be683  jmp     short loc_1400BE68F
0x1400be685  lea     ecx, [rax+1]
0x1400be688  lock cmpxchg [rdx+8], ecx
0x1400be68d  jz      short loc_1400BE695
0x1400be68f  test    eax, eax
0x1400be691  jnz     short loc_1400BE685
0x1400be693  jmp     short loc_1400BE6AD
0x1400be695  mov     rax, [r8+20h]
0x1400be699  mov     qword ptr [rsp+1B8h+var_A8], rax
0x1400be6a1  mov     rax, [r8+28h]
0x1400be6a5  mov     qword ptr [rsp+1B8h+var_A8+8], rax
0x1400be6ad  cmp     qword ptr [rsp+1B8h+var_A8], rdi
0x1400be6b5  jz      loc_1400BE759
0x1400be6bb  xorps   xmm0, xmm0
0x1400be6be  movups  [rsp+1B8h+var_190], xmm0
0x1400be6c3  mov     rax, [rsi+8]
0x1400be6c7  test    rax, rax
0x1400be6ca  jz      short loc_1400BE6D0
0x1400be6cc  lock inc dword ptr [rax+8]
0x1400be6d0  mov     rax, [rsi]
0x1400be6d3  mov     qword ptr [rsp+1B8h+var_190], rax
0x1400be6d8  mov     rbx, [rsi+8]
0x1400be6dc  mov     qword ptr [rsp+1B8h+var_190+8], rbx
0x1400be6e1  mov     [rsp+1B8h+var_B0], rdi
0x1400be6e9  mov     [rsp+1B8h+var_180], rdi
0x1400be6ee  mov     [rsp+1B8h+var_198], rsi
0x1400be6f3  lea     rcx, [rsp+1B8h+var_180]
0x1400be6f8  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x1400be6fd  lea     rdx, [rsp+1B8h+var_198]
0x1400be702  lea     rcx, [rsp+1B8h+var_A8]
0x1400be70a  mov     rax, r14
0x1400be70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be712  nop
0x1400be713  jmp     short loc_1400BE71C
0x1400be715  mov     rbx, qword ptr [rsp+1B8h+var_190+8]
0x1400be71a  xor     edi, edi
0x1400be71c  or      esi, 0FFFFFFFFh
0x1400be71f  test    rbx, rbx
0x1400be722  jz      short loc_1400BE75C
0x1400be724  mov     eax, esi
0x1400be726  lock xadd [rbx+8], eax
0x1400be72b  add     eax, esi
0x1400be72d  jnz     short loc_1400BE75C
0x1400be72f  mov     rax, [rbx]
0x1400be732  mov     rcx, rbx
0x1400be735  mov     rax, [rax]
0x1400be738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be73d  mov     eax, esi
0x1400be73f  lock xadd [rbx+0Ch], eax
0x1400be744  add     eax, esi
0x1400be746  jnz     short loc_1400BE75C
0x1400be748  mov     rax, [rbx]
0x1400be74b  mov     rcx, rbx
0x1400be74e  mov     rax, [rax+8]
0x1400be752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be757  jmp     short loc_1400BE75C
0x1400be759  or      esi, 0FFFFFFFFh
0x1400be75c  mov     rbx, qword ptr [rsp+1B8h+var_A8+8]
0x1400be764  test    rbx, rbx
0x1400be767  jz      short loc_1400BE79D
0x1400be769  mov     eax, esi
0x1400be76b  lock xadd [rbx+8], eax
0x1400be770  add     eax, esi
0x1400be772  jnz     short loc_1400BE79D
0x1400be774  mov     rax, [rbx]
0x1400be777  mov     rcx, rbx
0x1400be77a  mov     rax, [rax]
0x1400be77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be782  mov     eax, esi
0x1400be784  lock xadd [rbx+0Ch], eax
0x1400be789  add     eax, esi
0x1400be78b  jnz     short loc_1400BE79D
0x1400be78d  mov     rax, [rbx]
0x1400be790  mov     rcx, rbx
0x1400be793  mov     rax, [rax+8]
0x1400be797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400be79c  nop
0x1400be79d  cmp     [rsp+1B8h+var_48], dil
0x1400be7a5  jz      short loc_1400BE7F4
0x1400be7a7  cmp     [rsp+1B8h+var_60], edi
0x1400be7ae  jz      short loc_1400BE7BE
0x1400be7b0  lea     rcx, [rsp+1B8h+var_78]; this
0x1400be7b8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400be7bd  nop
0x1400be7be  cmp     byte ptr [rsp+1B8h+lpMem+8], dil
0x1400be7c6  jz      short loc_1400BE7EC
0x1400be7c8  mov     rbx, [rsp+1B8h+lpMem]
0x1400be7d0  call    cs:__imp_GetProcessHeap
0x1400be7d6  mov     r8, rbx; lpMem
0x1400be7d9  xor     edx, edx; dwFlags
0x1400be7db  mov     rcx, rax; hHeap
0x1400be7de  call    cs:__imp_HeapFree
0x1400be7e4  mov     byte ptr [rsp+1B8h+lpMem+8], dil
0x1400be7ec  mov     [rsp+1B8h+lpMem], rdi
0x1400be7f4  lea     rcx, [rsp+1B8h+var_B0]
0x1400be7fc  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x1400be801  nop
0x1400be802  mov     rcx, [rsp+1B8h+var_38]
0x1400be80a  xor     rcx, rsp; StackCookie
0x1400be80d  call    __security_check_cookie
0x1400be812  add     rsp, 198h
0x1400be819  pop     r14
0x1400be81b  pop     rdi
0x1400be81c  pop     rsi
0x1400be81d  pop     rbx
0x1400be81e  retn
```
