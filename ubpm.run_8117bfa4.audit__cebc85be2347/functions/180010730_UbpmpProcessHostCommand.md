# UbpmpProcessHostCommand

- ea: `0x180010730`
- end: `0x180011316`
- name: `UbpmpProcessHostCommand`
- size: `3046`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010450`

## callees

- `0x1800032ac`
- `0x180004c30`
- `0x18000fbf0`
- `0x180010164`
- `0x180010220`
- `0x180010730`
- `0x18001131c`
- `0x180013c90`
- `0x180032f78`
- `0x1800351ec`
- `0x18003f110`
- `0x18003f178`
- `0x18003f260`
- `0x18003f2d8`
- `0x18003f4a0`
- `0x18003f528`
- `0x18003f5b4`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800107a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800107c5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800108a8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800107a3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800107c5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800108a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001083e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ad3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ae7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001083e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ad3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ae7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180011280`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180011280`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112b1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010885`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010d6c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010885`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010d6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001098f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001098f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011183`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011183`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001094f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001094f`

## pseudocode

```c
__int64 __fastcall UbpmpProcessHostCommand(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned int v3; // r14d
  unsigned int v4; // r12d
  void *v5; // r13
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v6; // rdi
  __int64 v7; // rax
  __m128i v8; // xmm6
  char *v11; // rbx
  __int64 v12; // rdx
  PVOID *v13; // r10
  PVOID *v14; // r8
  char v15; // r12
  unsigned __int16 j; // si
  char v17; // r15
  DWORD LastError; // ebx
  __int64 v19; // r8
  _QWORD *v20; // rax
  struct _RPC_ASYNC_STATE *v21; // rbx
  __m128i v22; // xmm1
  __int64 v23; // r8
  unsigned __int64 v24; // xmm0_8
  __int16 v25; // ax
  BOOL v26; // esi
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int v30; // ebx
  unsigned __int16 *v31; // r15
  __int64 v33; // r8
  int v34; // eax
  char v35; // al
  __int64 *i; // rax
  DWORD v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  DWORD v47; // eax
  __int64 v48; // rcx
  char v49; // al
  __int16 v50; // ax
  __int64 v51; // rdx
  __int64 v52; // rax
  __int16 v53; // ax
  __int64 v54; // [rsp+28h] [rbp-71h]
  unsigned int Reply; // [rsp+50h] [rbp-49h] BYREF
  char v56; // [rsp+54h] [rbp-45h]
  BOOL v57; // [rsp+58h] [rbp-41h]
  unsigned int v58; // [rsp+5Ch] [rbp-3Dh]
  __int64 v59; // [rsp+60h] [rbp-39h]
  __int64 v60; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v61; // [rsp+70h] [rbp-29h]
  __int64 v62; // [rsp+78h] [rbp-21h]
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v63; // [rsp+80h] [rbp-19h] BYREF
  HANDLE Handles[2]; // [rsp+88h] [rbp-11h] BYREF
  HANDLE v65; // [rsp+98h] [rbp-1h]

  v3 = *a2;
  Reply = 0;
  v4 = 0;
  v58 = 0;
  v5 = 0;
  v57 = 0;
  v6 = a1;
  v7 = *((_QWORD *)a2 + 4);
  v8.m128i_i64[0] = 0;
  v63 = a1;
  v62 = v7;
  v59 = a3;
  v61 = a2;
  v60 = a3;
  *(_OWORD *)Handles = 0;
  RtlAcquireSRWLockExclusive((char *)a1 + 80);
  v11 = (char *)v6 + 64;
  *((_DWORD *)v6 + 22) = GetCurrentThreadId();
  RtlAcquireSRWLockExclusive((char *)v6 + 64);
  *((_DWORD *)v6 + 18) = GetCurrentThreadId();
  v13 = (PVOID *)WPP_GLOBAL_Control;
  v14 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_dqqdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_GLOBAL_Control,
      v3,
      v6,
      a3,
      *((_DWORD *)v6 + 8),
      *((unsigned __int16 *)v6 + 98));
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v14 = &WPP_GLOBAL_Control;
  }
  if ( v3 == 3 )
  {
    for ( i = (__int64 *)*((_QWORD *)v6 + 25); ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)((char *)v6 + 200) )
      {
        Reply = 1235;
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        {
          v51 = 157;
          goto LABEL_114;
        }
        goto LABEL_31;
      }
      if ( *((_DWORD *)i + 10) == *(_DWORD *)(a3 + 56) )
        break;
    }
    if ( *(_QWORD *)(a3 + 96) )
    {
      if ( (*(_BYTE *)(a3 + 104) & 1) == 0 )
      {
        if ( *(_WORD *)(a3 + 106) != 1 )
        {
          *(_WORD *)(a3 + 106) = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_GLOBAL_Control, a3, *((_DWORD *)v6 + 8));
        }
        *((_QWORD *)a2 + 5) = *(_QWORD *)(a3 + 96);
        *((_DWORD *)a2 + 14) = *(_DWORD *)(a3 + 56);
        goto LABEL_5;
      }
      Reply = 4320;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      {
        v51 = 159;
        goto LABEL_114;
      }
    }
    else
    {
      Reply = 1235;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      {
        v51 = 158;
LABEL_114:
        WPP_SF_dd(v13[2], v51, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v6 + 8));
        goto LABEL_31;
      }
    }
    goto LABEL_31;
  }
  if ( v3 != 1 )
  {
    if ( v3 == 2 )
    {
      v35 = *((_BYTE *)v6 + 104);
      if ( v35 < 0 || (v35 & 4) != 0 )
      {
        Reply = 4320;
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        {
          WPP_SF_dd(v13[2], 163, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v6 + 8));
LABEL_27:
          if ( !Reply )
            goto LABEL_31;
        }
        v25 = *((_WORD *)v6 + 98);
        if ( v25 )
          *((_WORD *)v6 + 98) = v25 - 1;
        goto LABEL_102;
      }
    }
LABEL_5:
    v56 = 0;
    v15 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    for ( j = 0; j < 2u; ++j )
    {
      *((_DWORD *)v11 + 2) = 0;
      RtlReleaseSRWLockExclusive(v11);
      v17 = *((_BYTE *)v6 + 432);
      Handles[0] = *((HANDLE *)v6 + 6);
      Handles[1] = *((HANDLE *)v6 + 3);
      v65 = g_hLowPowerEpochExited;
      while ( 1 )
      {
        LastError = WaitForMultipleObjectsEx(2u, Handles, 0, g_dwTaskhostResponseTimeoutMsec, 0);
        if ( LastError != 258 || v17 || g_fLowPowerEpoch != 1 || !g_hLowPowerEpochExited )
          break;
        v37 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
        LastError = v37;
        if ( v37 != 2 )
        {
          if ( v37 >= 2 )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                LastError);
          }
          break;
        }
      }
      Reply = LastError;
      v11 = (char *)v6 + 64;
      RtlAcquireSRWLockExclusive((char *)v6 + 64);
      *((_DWORD *)v6 + 18) = GetCurrentThreadId();
      v19 = Reply;
      if ( Reply )
      {
        switch ( Reply )
        {
          case 1u:
            if ( (unsigned int)UbpmpAllTasksStopped(v6) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                LODWORD(v54) = v33;
                WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, v33, *((unsigned int *)v6 + 8), j, v54);
              }
              v34 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                LODWORD(v54) = v33;
                WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, v33, *((unsigned int *)v6 + 8), j, v54);
              }
              v34 = 1067;
            }
            Reply = v34;
            break;
          case 0x102u:
            Reply = 1460;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, j);
            if ( g_fBreakOnTaskhostTimeout && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
              __debugbreak();
            break;
          case 0xFFFFFFFF:
            v47 = GetLastError();
            Reply = v47;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v47);
            break;
          default:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, j);
            Reply = 1235;
            break;
        }
        goto LABEL_49;
      }
      if ( (*((_BYTE *)v6 + 104) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(v54) = Reply;
          WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, Reply, *((unsigned int *)v6 + 8), j, v54);
        }
        Reply = 1067;
        goto LABEL_49;
      }
      if ( j )
      {
        SetEvent(*((HANDLE *)v6 + 6));
        v22 = *((__m128i *)v6 + 7);
        v23 = v62;
        v8 = *((__m128i *)v6 + 8);
        *((_OWORD *)v6 + 7) = 0;
        *((_OWORD *)v6 + 8) = 0;
        v24 = _mm_srli_si128(v22, 8).m128i_u64[0];
        if ( v23 != v24 )
        {
          Reply = 776;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LODWORD(v54) = *((_DWORD *)v6 + 8);
            WPP_SF_iiddd(*((_QWORD *)WPP_GLOBAL_Control + 2), WPP_GLOBAL_Control, v23, v23, v24, v54, j, 776);
          }
          goto LABEL_49;
        }
        Reply = _mm_cvtsi128_si32(v22);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        {
          v15 = _mm_cvtsi128_si32(_mm_srli_si128(v8, 8));
        }
        else
        {
          v15 = _mm_cvtsi128_si32(_mm_srli_si128(v8, 8));
          HIDWORD(v54) = HIDWORD(v23);
          WPP_SF_ddiL(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
      }
      else
      {
        v20 = (_QWORD *)*((_QWORD *)v6 + 21);
        v21 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)v6 + 7);
        v56 = 1;
        *v20 = v61;
        *((_QWORD *)v6 + 21) = 0;
        *((_QWORD *)v6 + 7) = 0;
        *((_OWORD *)v6 + 7) = 0;
        v61 = 0;
        *((_OWORD *)v6 + 8) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          if ( v59 )
            v52 = *(_QWORD *)(v59 + 96);
          else
            v52 = 0;
          WPP_SF_ddiqqi(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, v19, v3, *((_DWORD *)v6 + 8), v62, v6, v59, v52);
        }
        _InterlockedExchange((volatile __int32 *)v6 + 81, GetCurrentThreadId());
        Reply = RpcAsyncCompleteCall(v21, &Reply);
        if ( Reply )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 0);
          goto LABEL_49;
        }
        v11 = (char *)v6 + 64;
        _InterlockedExchange((volatile __int32 *)v6 + 81, 0);
        v58 = *((_DWORD *)v6 + 82);
        *((_DWORD *)v6 + 82) = 0;
      }
    }
    if ( !Reply && v3 == 2 )
    {
      if ( (v15 & 1) != 0 )
      {
        v53 = *((_WORD *)v6 + 98);
        if ( v53 )
          *((_WORD *)v6 + 98) = v53 - 1;
        UbpmpDecrementTaskRefAndDelete(&v60);
      }
      else
      {
        *(_QWORD *)(v59 + 96) = v8.m128i_i64[0];
      }
      goto LABEL_27;
    }
LABEL_49:
    if ( v3 != 3 )
    {
      if ( v3 == 2 )
        goto LABEL_27;
      if ( v3 == 1 )
      {
        v4 = v58;
        goto LABEL_53;
      }
      goto LABEL_31;
    }
    if ( v56 != 1 )
      goto LABEL_31;
    if ( Reply == 15501 )
      goto LABEL_31;
    v48 = v59;
    v49 = *(_BYTE *)(v59 + 104);
    if ( (v49 & 1) != 0 )
      goto LABEL_31;
    *(_BYTE *)(v59 + 104) = v49 | 1;
    v50 = *((_WORD *)v6 + 98);
    if ( v50 )
      *((_WORD *)v6 + 98) = v50 - 1;
    UbpmpTaskPostStopActions(v48, v6);
LABEL_102:
    UbpmpDecrementTaskRefAndDelete(&v60);
LABEL_31:
    v26 = 0;
    if ( !*((_WORD *)v6 + 98) )
      v26 = *((_QWORD *)v6 + 27) == (_QWORD)v6 + 216;
    v4 = v58;
    goto LABEL_34;
  }
  if ( *((struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)v6 + 27) == (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)v6 + 216)
    && (unsigned int)UbpmpAllTasksStopped(v6) )
  {
    if ( v13 != v14 && *((char *)v13 + 28) < 0 )
      WPP_SF_qd(v13[2], 162, v14, v6, *((_DWORD *)v6 + 8));
    *((_BYTE *)v6 + 104) |= 0x80u;
    goto LABEL_5;
  }
  Reply = 4320;
  if ( v13 != v14 && (*((_BYTE *)v13 + 28) & 1) != 0 )
  {
    WPP_SF_ddLd(
      v13[2],
      v12,
      v14,
      *((unsigned int *)v6 + 8),
      *((unsigned __int16 *)v6 + 98),
      *((unsigned __int8 *)v6 + 104),
      4320);
LABEL_53:
    v14 = &WPP_GLOBAL_Control;
  }
  if ( *((char *)v6 + 104) < 0 )
  {
    v5 = (void *)*((_QWORD *)v6 + 5);
    *((_QWORD *)v6 + 5) = 0;
    if ( Reply && Reply != 1067 )
    {
      if ( WPP_GLOBAL_Control != v14 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          174,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)v6 + 8));
      if ( TerminateProcess(*((HANDLE *)v6 + 3), 0x42Bu) )
      {
        v26 = v57;
        Reply = 0;
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          175,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)v6 + 8));
      }
    }
    v26 = v57;
    goto LABEL_34;
  }
  v26 = 0;
LABEL_34:
  *((_DWORD *)v6 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)v6 + 64);
  *((_DWORD *)v6 + 22) = 0;
  RtlReleaseSRWLockExclusive((char *)v6 + 80);
  v30 = 0;
  if ( v4 )
  {
    do
    {
      UbpmpDecrementRefAndDelete(&v63, 1);
      ++v30;
    }
    while ( v30 < v4 );
    v6 = v63;
  }
  if ( v5 )
    UbpmpTaskHostTerminationCleanup(v6, v5);
  if ( v26 )
    UbpmpSendCommandGetResponse(v6, 0, 0, 1);
  v31 = v61;
  if ( v61 )
  {
    UBPM_MIDL_user_free(*((_QWORD *)v61 + 2), v27, v28, v29);
    UBPM_MIDL_user_free(*((_QWORD *)v31 + 3), v38, v39, v40);
    UBPM_MIDL_user_free(*((_QWORD *)v31 + 1), v41, v42, v43);
    UBPM_MIDL_user_free(v31, v44, v45, v46);
  }
  return Reply;
}

```

## disassembly

```asm
0x180010730  mov     [rsp-8+arg_18], rbx
0x180010735  push    rbp
0x180010736  push    rsi
0x180010737  push    rdi
0x180010738  push    r12
0x18001073a  push    r13
0x18001073c  push    r14
0x18001073e  push    r15
0x180010740  lea     rbp, [rsp-27h]
0x180010745  sub     rsp, 0C0h
0x18001074c  movaps  [rsp+0F0h+var_40], xmm6
0x180010754  mov     rax, cs:__security_cookie
0x18001075b  xor     rax, rsp
0x18001075e  mov     [rbp+57h+var_48], rax
0x180010762  movzx   r14d, word ptr [rdx]
0x180010766  xor     eax, eax
0x180010768  mov     [rbp+57h+Reply], eax
0x18001076b  mov     r12d, eax
0x18001076e  mov     [rbp+57h+var_94], eax
0x180010771  mov     r13d, eax
0x180010774  mov     [rbp+57h+var_98], eax
0x180010777  mov     rdi, rcx
0x18001077a  mov     rax, [rdx+20h]
0x18001077e  xorps   xmm6, xmm6
0x180010781  mov     [rbp+57h+var_70], rcx
0x180010785  mov     rsi, r8
0x180010788  add     rcx, 50h ; 'P'
0x18001078c  mov     [rbp+57h+var_78], rax
0x180010790  mov     [rbp+57h+var_90], r8
0x180010794  mov     r15, rdx
0x180010797  mov     [rbp+57h+var_80], rdx
0x18001079b  mov     [rbp+57h+var_88], r8
0x18001079f  movups  xmmword ptr [rbp+57h+Handles], xmm6
0x1800107a3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800107aa  nop     dword ptr [rax+rax+00h]
0x1800107af  call    cs:__imp_GetCurrentThreadId
0x1800107b6  nop     dword ptr [rax+rax+00h]
0x1800107bb  lea     rbx, [rdi+40h]
0x1800107bf  mov     [rdi+58h], eax
0x1800107c2  mov     rcx, rbx
0x1800107c5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800107cc  nop     dword ptr [rax+rax+00h]
0x1800107d1  call    cs:__imp_GetCurrentThreadId
0x1800107d8  nop     dword ptr [rax+rax+00h]
0x1800107dd  mov     [rbx+8], eax
0x1800107e0  mov     r10, cs:WPP_GLOBAL_Control
0x1800107e7  lea     r8, WPP_GLOBAL_Control
0x1800107ee  cmp     r10, r8
0x1800107f1  jnz     loc_180010A0B
0x1800107f7  cmp     r14d, 3
0x1800107fb  jz      loc_180010C16
0x180010801  cmp     r14d, 1
0x180010805  jz      loc_180010CC3
0x18001080b  cmp     r14d, 2
0x18001080f  jz      loc_180010BC5
0x180010815  movdqa  xmm0, xmm6
0x180010819  mov     [rbp+57h+var_9C], r12b
0x18001081d  psrldq  xmm0, 8
0x180010822  xor     r15d, r15d
0x180010825  movd    r12d, xmm0
0x18001082a  mov     esi, r15d
0x18001082d  cmp     si, 2
0x180010831  jnb     loc_180010A51
0x180010837  mov     rcx, rbx
0x18001083a  mov     [rbx+8], r15d
0x18001083e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010845  nop     dword ptr [rax+rax+00h]
0x18001084a  mov     rax, [rdi+30h]
0x18001084e  movzx   r15d, byte ptr [rdi+1B0h]
0x180010856  mov     [rbp+57h+Handles], rax
0x18001085a  mov     rax, [rdi+18h]
0x18001085e  mov     [rbp+57h+Handles+8], rax
0x180010862  mov     rax, cs:?g_hLowPowerEpochExited@@3PEAXEA; void * g_hLowPowerEpochExited
0x180010869  mov     [rbp+57h+var_58], rax
0x18001086d  mov     r9d, cs:?g_dwTaskhostResponseTimeoutMsec@@3KA; dwMilliseconds
0x180010874  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180010878  xor     r8d, r8d; bWaitAll
0x18001087b  mov     [rsp+0F0h+bAlertable], r13d; bAlertable
0x180010880  mov     ecx, 2; nCount
0x180010885  call    cs:__imp_WaitForMultipleObjectsEx
0x18001088c  nop     dword ptr [rax+rax+00h]
0x180010891  mov     ebx, eax
0x180010893  cmp     eax, 102h
0x180010898  jz      loc_180010D32
0x18001089e  mov     [rbp+57h+Reply], ebx
0x1800108a1  lea     rbx, [rdi+40h]
0x1800108a5  mov     rcx, rbx
0x1800108a8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800108af  nop     dword ptr [rax+rax+00h]
0x1800108b4  call    cs:__imp_GetCurrentThreadId
0x1800108bb  nop     dword ptr [rax+rax+00h]
0x1800108c0  mov     [rbx+8], eax
0x1800108c3  mov     r8d, [rbp+57h+Reply]
0x1800108c7  test    r8d, r8d
0x1800108ca  jnz     loc_180010B57
0x1800108d0  test    byte ptr [rdi+68h], 4
0x1800108d4  jnz     loc_1800110CD
0x1800108da  test    si, si
0x1800108dd  jnz     loc_18001098B
0x1800108e3  mov     rax, [rdi+0A8h]
0x1800108ea  xorps   xmm0, xmm0
0x1800108ed  mov     rbx, [rdi+38h]
0x1800108f1  mov     r15, [rbp+57h+var_80]
0x1800108f5  mov     [rbp+57h+var_9C], 1
0x1800108f9  mov     [rax], r15
0x1800108fc  xor     r15d, r15d
0x1800108ff  mov     [rdi+0A8h], r15
0x180010906  mov     [rdi+38h], r15
0x18001090a  movups  xmmword ptr [rdi+70h], xmm0
0x18001090e  mov     [rbp+57h+var_80], r15
0x180010912  movups  xmmword ptr [rdi+80h], xmm0
0x180010919  mov     rcx, cs:WPP_GLOBAL_Control
0x180010920  lea     rax, WPP_GLOBAL_Control
0x180010927  cmp     rcx, rax
0x18001092a  jz      short loc_180010936
0x18001092c  test    byte ptr [rcx+1Ch], 80h
0x180010930  jnz     loc_180011007
0x180010936  call    cs:__imp_GetCurrentThreadId
0x18001093d  nop     dword ptr [rax+rax+00h]
0x180010942  lea     rdx, [rbp+57h+Reply]; Reply
0x180010946  mov     rcx, rbx; pAsync
0x180010949  xchg    eax, [rdi+144h]
0x18001094f  call    cs:__imp_RpcAsyncCompleteCall
0x180010956  nop     dword ptr [rax+rax+00h]
0x18001095b  mov     [rbp+57h+Reply], eax
0x18001095e  test    eax, eax
0x180010960  jnz     loc_180010C7E
0x180010966  mov     eax, r15d
0x180010969  lea     rbx, [rdi+40h]
0x18001096d  xchg    eax, [rdi+144h]
0x180010973  mov     eax, [rdi+148h]
0x180010979  mov     [rbp+57h+var_94], eax
0x18001097c  mov     [rdi+148h], r15d
0x180010983  inc     si
0x180010986  jmp     loc_18001082D
0x18001098b  mov     rcx, [rdi+30h]; hEvent
0x18001098f  call    cs:__imp_SetEvent
0x180010996  nop     dword ptr [rax+rax+00h]
0x18001099b  movups  xmm1, xmmword ptr [rdi+70h]
0x18001099f  mov     r8, [rbp+57h+var_78]
0x1800109a3  movups  xmm6, xmmword ptr [rdi+80h]
0x1800109aa  xorps   xmm0, xmm0
0x1800109ad  movups  xmmword ptr [rdi+70h], xmm0
0x1800109b1  movups  xmmword ptr [rdi+80h], xmm0
0x1800109b8  movdqa  xmm0, xmm1
0x1800109bc  psrldq  xmm0, 8
0x1800109c1  movq    rcx, xmm0
0x1800109c6  cmp     r8, rcx
0x1800109c9  jnz     loc_180011079
0x1800109cf  movd    r9d, xmm1
0x1800109d4  mov     [rbp+57h+Reply], r9d
0x1800109d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109df  lea     rax, WPP_GLOBAL_Control
0x1800109e6  cmp     rcx, rax
0x1800109e9  jz      short loc_1800109F5
0x1800109eb  test    byte ptr [rcx+1Ch], 80h
0x1800109ef  jnz     loc_180011049
0x1800109f5  movdqa  xmm0, xmm6
0x1800109f9  psrldq  xmm0, 8
0x1800109fe  movd    r12d, xmm0
0x180010a03  xor     r15d, r15d
0x180010a06  jmp     loc_180010983
0x180010a0b  test    byte ptr [r10+1Ch], 80h
0x180010a10  jz      loc_1800107F7
0x180010a16  movzx   eax, word ptr [rdi+0C4h]
0x180010a1d  mov     r9d, r14d
0x180010a20  mov     rcx, [r10+10h]
0x180010a24  mov     dword ptr [rsp+0F0h+var_B8], eax
0x180010a28  mov     eax, [rdi+20h]
0x180010a2b  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180010a2f  mov     [rsp+0F0h+var_C8], rsi
0x180010a34  mov     qword ptr [rsp+0F0h+bAlertable], rdi
0x180010a39  call    WPP_SF_dqqdd
0x180010a3e  mov     r10, cs:WPP_GLOBAL_Control
0x180010a45  lea     r8, WPP_GLOBAL_Control
0x180010a4c  jmp     loc_1800107F7
0x180010a51  cmp     [rbp+57h+Reply], r13d
0x180010a55  jnz     loc_180010B97
0x180010a5b  cmp     r14d, 2
0x180010a5f  jnz     loc_180010B97
0x180010a65  test    r12b, 1
0x180010a69  jnz     loc_18001120E
0x180010a6f  mov     rcx, [rbp+57h+var_90]
0x180010a73  movsd   qword ptr [rcx+60h], xmm6
0x180010a78  cmp     [rbp+57h+Reply], r13d
0x180010a7c  jz      short loc_180010AAD
0x180010a7e  movzx   eax, word ptr [rdi+0C4h]
0x180010a85  test    ax, ax
0x180010a88  jz      loc_180010EE7
0x180010a8e  dec     ax
0x180010a91  mov     [rdi+0C4h], ax
0x180010a98  jmp     loc_180010EE7
0x180010a9d  mov     [rbp+57h+Reply], 4D3h
0x180010aa4  cmp     r10, r8
0x180010aa7  jnz     loc_180010F7E
0x180010aad  mov     esi, r13d
0x180010ab0  mov     r14d, 1
0x180010ab6  cmp     [rdi+0C4h], r13w
0x180010abe  jz      loc_180010DE0
0x180010ac4  mov     r12d, [rbp+57h+var_94]
0x180010ac8  xor     r15d, r15d
0x180010acb  lea     rcx, [rdi+40h]
0x180010acf  mov     [rcx+8], r15d
0x180010ad3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010ada  nop     dword ptr [rax+rax+00h]
0x180010adf  lea     rcx, [rdi+50h]
0x180010ae3  mov     [rcx+8], r15d
0x180010ae7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010aee  nop     dword ptr [rax+rax+00h]
0x180010af3  mov     ebx, r15d
0x180010af6  test    r12d, r12d
0x180010af9  jnz     loc_1800112FA
0x180010aff  test    r13, r13
0x180010b02  jz      short loc_180010B0F
0x180010b04  mov     rdx, r13; WaitHandle
0x180010b07  mov     rcx, rdi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x180010b0a  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x180010b0f  test    esi, esi
0x180010b11  jnz     loc_180010C36
0x180010b17  mov     r15, [rbp+57h+var_80]
0x180010b1b  test    r15, r15
0x180010b1e  jnz     loc_180010E2F
0x180010b24  mov     eax, [rbp+57h+Reply]
0x180010b27  mov     rcx, [rbp+57h+var_48]
0x180010b2b  xor     rcx, rsp; StackCookie
0x180010b2e  call    __security_check_cookie
0x180010b33  mov     rbx, [rsp+0F0h+arg_18]
0x180010b3b  movaps  xmm6, [rsp+0F0h+var_40]
0x180010b43  add     rsp, 0C0h
0x180010b4a  pop     r15
0x180010b4c  pop     r14
0x180010b4e  pop     r13
0x180010b50  pop     r12
0x180010b52  pop     rdi
0x180010b53  pop     rsi
0x180010b54  pop     rbp
0x180010b55  retn
0x180010b57  cmp     r8d, 1
0x180010b5b  jnz     loc_180010DF3
0x180010b61  mov     rcx, rdi
0x180010b64  call    UbpmpAllTasksStopped
0x180010b69  test    eax, eax
0x180010b6b  jz      loc_1800111A7
0x180010b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b78  lea     rax, WPP_GLOBAL_Control
0x180010b7f  cmp     rcx, rax
0x180010b82  jz      short loc_180010B8E
0x180010b84  test    byte ptr [rcx+1Ch], 80h
0x180010b88  jnz     loc_1800111EB
0x180010b8e  xor     r15d, r15d
0x180010b91  mov     eax, r15d
0x180010b94  mov     [rbp+57h+Reply], eax
0x180010b97  cmp     r14d, 3
0x180010b9b  jz      loc_180010EA3
0x180010ba1  cmp     r14d, 2
0x180010ba5  jz      loc_180010A78
0x180010bab  cmp     r14d, 1
0x180010baf  jnz     loc_180010AAD
0x180010bb5  mov     r12d, [rbp+57h+var_94]
0x180010bb9  lea     r8, WPP_GLOBAL_Control
0x180010bc0  jmp     loc_180010CE2
0x180010bc5  movzx   eax, byte ptr [rdi+68h]
0x180010bc9  test    al, al
0x180010bcb  js      short loc_180010BD5
0x180010bcd  test    al, 4
0x180010bcf  jz      loc_180010815
0x180010bd5  mov     [rbp+57h+Reply], 10E0h
0x180010bdc  cmp     r10, r8
0x180010bdf  jz      loc_180010A7E
0x180010be5  test    byte ptr [r10+1Ch], 1
0x180010bea  jz      loc_180010A7E
0x180010bf0  mov     r9d, [rdi+20h]
0x180010bf4  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180010bfb  mov     rcx, [r10+10h]
0x180010bff  mov     edx, 0A3h
0x180010c04  mov     [rsp+0F0h+bAlertable], 10E0h
0x180010c0c  call    WPP_SF_dd
0x180010c11  jmp     loc_180010A78
0x180010c16  lea     rdx, [rdi+0C8h]
0x180010c1d  mov     rax, [rdx]
0x180010c20  cmp     rax, rdx
0x180010c23  jz      loc_180010A9D
0x180010c29  mov     ecx, [rsi+38h]
0x180010c2c  cmp     [rax+28h], ecx
0x180010c2f  jz      short loc_180010C4B
0x180010c31  mov     rax, [rax]
0x180010c34  jmp     short loc_180010C20
0x180010c36  mov     r9d, r14d
0x180010c39  xor     r8d, r8d
0x180010c3c  xor     edx, edx
0x180010c3e  mov     rcx, rdi
0x180010c41  call    UbpmpSendCommandGetResponse
0x180010c46  jmp     loc_180010B17
0x180010c4b  cmp     [rsi+60h], r12
0x180010c4f  jz      loc_180010EF5
0x180010c55  test    byte ptr [rsi+68h], 1
0x180010c59  jnz     loc_180010F17
0x180010c5f  cmp     word ptr [rsi+6Ah], 1
0x180010c64  jnz     loc_180010F41
0x180010c6a  mov     rax, [rsi+60h]
  ... truncated ...
```
