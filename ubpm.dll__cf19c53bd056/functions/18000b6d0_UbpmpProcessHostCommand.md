# UbpmpProcessHostCommand

- ea: `0x18000b6d0`
- end: `0x18000c240`
- name: `UbpmpProcessHostCommand`
- size: `2928`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b440`

## callees

- `0x180009750`
- `0x18000a4c8`
- `0x18000a570`
- `0x18000b6d0`
- `0x18000c248`
- `0x18000e660`
- `0x180019d90`
- `0x180029a0c`
- `0x180030cec`
- `0x180032e38`
- `0x18003c764`
- `0x18003c7c4`
- `0x18003c89c`
- `0x18003c90c`
- `0x18003cab8`
- `0x18003cb3c`
- `0x18003cbc0`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b743`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b759`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b824`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b743`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b759`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b824`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b7c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba2e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba3c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b7c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba2e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ba3c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000c1b6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000c1b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b75f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b82a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b75f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b82a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1e1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b807`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000bcba`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b807`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000bcba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b8f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b8f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0bf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0bf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b8b9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b8b9`

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
  unsigned int v27; // ebx
  unsigned __int16 *v28; // r15
  __int64 v30; // r8
  int v31; // eax
  char v32; // al
  __int64 *i; // rax
  DWORD v34; // eax
  DWORD v35; // eax
  __int64 v36; // rcx
  char v37; // al
  __int16 v38; // ax
  __int64 v39; // rdx
  __int64 v40; // rax
  __int16 v41; // ax
  DWORD v42; // eax
  __int64 v43; // [rsp+28h] [rbp-71h]
  unsigned int Reply; // [rsp+50h] [rbp-49h] BYREF
  char v45; // [rsp+54h] [rbp-45h]
  BOOL v46; // [rsp+58h] [rbp-41h]
  unsigned int v47; // [rsp+5Ch] [rbp-3Dh]
  __int64 v48; // [rsp+60h] [rbp-39h]
  __int64 v49; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v50; // [rsp+70h] [rbp-29h]
  __int64 v51; // [rsp+78h] [rbp-21h]
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v52; // [rsp+80h] [rbp-19h] BYREF
  HANDLE Handles[2]; // [rsp+88h] [rbp-11h] BYREF
  HANDLE v54; // [rsp+98h] [rbp-1h]

  v3 = *a2;
  Reply = 0;
  v4 = 0;
  v47 = 0;
  v5 = 0;
  v46 = 0;
  v6 = a1;
  v7 = *((_QWORD *)a2 + 4);
  v8.m128i_i64[0] = 0;
  v52 = a1;
  v51 = v7;
  v48 = a3;
  v50 = a2;
  v49 = a3;
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
    for ( i = (__int64 *)*((_QWORD *)v6 + 25); i != (__int64 *)((char *)v6 + 200); i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 10) == *(_DWORD *)(a3 + 56) )
      {
        if ( *(_QWORD *)(a3 + 96) )
        {
          if ( (*(_BYTE *)(a3 + 104) & 1) == 0 )
          {
            if ( *(_WORD *)(a3 + 106) != 1 )
            {
              *(_WORD *)(a3 + 106) = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 160);
            }
            *((_QWORD *)a2 + 5) = *(_QWORD *)(a3 + 96);
            *((_DWORD *)a2 + 14) = *(_DWORD *)(a3 + 56);
            goto LABEL_5;
          }
          Reply = 4320;
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
            WPP_SF_dd(v13[2], 159, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v6 + 8), 4320);
LABEL_31:
          v26 = 0;
          if ( !*((_WORD *)v6 + 98) )
            v26 = *((_QWORD *)v6 + 27) == (_QWORD)v6 + 216;
          v4 = v47;
          goto LABEL_34;
        }
        Reply = 1235;
        if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
          goto LABEL_31;
        v39 = 158;
LABEL_114:
        WPP_SF_dd(v13[2], v39, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v6 + 8), 1235);
        goto LABEL_31;
      }
    }
    Reply = 1235;
    if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
      goto LABEL_31;
    v39 = 157;
    goto LABEL_114;
  }
  if ( v3 != 1 )
  {
    if ( v3 == 2 )
    {
      v32 = *((_BYTE *)v6 + 104);
      if ( v32 < 0 || (v32 & 4) != 0 )
      {
        Reply = 4320;
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        {
          WPP_SF_dd(v13[2], 163, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *((unsigned int *)v6 + 8), 4320);
LABEL_27:
          if ( !Reply )
            goto LABEL_31;
        }
        v25 = *((_WORD *)v6 + 98);
        if ( v25 )
          *((_WORD *)v6 + 98) = v25 - 1;
LABEL_102:
        UbpmpDecrementTaskRefAndDelete(&v49);
        goto LABEL_31;
      }
    }
LABEL_5:
    v45 = 0;
    v15 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    for ( j = 0; j < 2u; ++j )
    {
      *((_DWORD *)v11 + 2) = 0;
      RtlReleaseSRWLockExclusive(v11);
      v17 = *((_BYTE *)v6 + 432);
      Handles[0] = *((HANDLE *)v6 + 6);
      Handles[1] = *((HANDLE *)v6 + 3);
      v54 = g_hLowPowerEpochExited;
      while ( 1 )
      {
        LastError = WaitForMultipleObjectsEx(2u, Handles, 0, g_dwTaskhostResponseTimeoutMsec, 0);
        if ( LastError != 258 || v17 || g_fLowPowerEpoch != 1 || !g_hLowPowerEpochExited )
          break;
        v34 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
        LastError = v34;
        if ( v34 != 2 )
        {
          if ( v34 >= 2 )
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
                LODWORD(v43) = v30;
                WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, v30, *((unsigned int *)v6 + 8), j, v43);
              }
              v31 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                LODWORD(v43) = v30;
                WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, v30, *((unsigned int *)v6 + 8), j, v43);
              }
              v31 = 1067;
            }
            Reply = v31;
            break;
          case 0x102u:
            Reply = 1460;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                164,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                j,
                1460);
            if ( g_fBreakOnTaskhostTimeout && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
              __debugbreak();
            break;
          case 0xFFFFFFFF:
            v35 = GetLastError();
            Reply = v35;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v35);
            break;
          default:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                168,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                j,
                Reply);
            Reply = 1235;
            break;
        }
        goto LABEL_49;
      }
      if ( (*((_BYTE *)v6 + 104) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(v43) = Reply;
          WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, Reply, *((unsigned int *)v6 + 8), j, v43);
        }
        Reply = 1067;
        goto LABEL_49;
      }
      if ( j )
      {
        SetEvent(*((HANDLE *)v6 + 6));
        v22 = *((__m128i *)v6 + 7);
        v23 = v51;
        v8 = *((__m128i *)v6 + 8);
        *((_OWORD *)v6 + 7) = 0;
        *((_OWORD *)v6 + 8) = 0;
        v24 = _mm_srli_si128(v22, 8).m128i_u64[0];
        if ( v23 != v24 )
        {
          Reply = 776;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LODWORD(v43) = *((_DWORD *)v6 + 8);
            WPP_SF_iiddd(*((_QWORD *)WPP_GLOBAL_Control + 2), WPP_GLOBAL_Control, v23, v23, v24, v43, j, 776);
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
          HIDWORD(v43) = HIDWORD(v23);
          WPP_SF_ddiL(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
      }
      else
      {
        v20 = (_QWORD *)*((_QWORD *)v6 + 21);
        v21 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)v6 + 7);
        v45 = 1;
        *v20 = v50;
        *((_QWORD *)v6 + 21) = 0;
        *((_QWORD *)v6 + 7) = 0;
        *((_OWORD *)v6 + 7) = 0;
        v50 = 0;
        *((_OWORD *)v6 + 8) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          if ( v48 )
            v40 = *(_QWORD *)(v48 + 96);
          else
            v40 = 0;
          WPP_SF_ddiqqi(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, v19, v3, *((_DWORD *)v6 + 8), v51, v6, v48, v40);
        }
        _InterlockedExchange((volatile __int32 *)v6 + 81, GetCurrentThreadId());
        Reply = RpcAsyncCompleteCall(v21, &Reply);
        if ( Reply )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              171,
              WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              0,
              Reply);
          goto LABEL_49;
        }
        v11 = (char *)v6 + 64;
        _InterlockedExchange((volatile __int32 *)v6 + 81, 0);
        v47 = *((_DWORD *)v6 + 82);
        *((_DWORD *)v6 + 82) = 0;
      }
    }
    if ( !Reply && v3 == 2 )
    {
      if ( (v15 & 1) != 0 )
      {
        v41 = *((_WORD *)v6 + 98);
        if ( v41 )
          *((_WORD *)v6 + 98) = v41 - 1;
        UbpmpDecrementTaskRefAndDelete(&v49);
      }
      else
      {
        *(_QWORD *)(v48 + 96) = v8.m128i_i64[0];
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
        v4 = v47;
        goto LABEL_53;
      }
      goto LABEL_31;
    }
    if ( v45 != 1 )
      goto LABEL_31;
    if ( Reply == 15501 )
      goto LABEL_31;
    v36 = v48;
    v37 = *(_BYTE *)(v48 + 104);
    if ( (v37 & 1) != 0 )
      goto LABEL_31;
    *(_BYTE *)(v48 + 104) = v37 | 1;
    v38 = *((_WORD *)v6 + 98);
    if ( v38 )
      *((_WORD *)v6 + 98) = v38 - 1;
    UbpmpTaskPostStopActions(v36, v6);
    goto LABEL_102;
  }
  if ( *((struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)v6 + 27) == (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)v6 + 216)
    && (unsigned int)UbpmpAllTasksStopped(v6) )
  {
    if ( v13 != v14 && *((char *)v13 + 28) < 0 )
      WPP_SF_qd(v13[2], 162);
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
        v26 = v46;
        Reply = 0;
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v42 = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          175,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)v6 + 8),
          v42);
      }
    }
    v26 = v46;
    goto LABEL_34;
  }
  v26 = 0;
LABEL_34:
  *((_DWORD *)v6 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)v6 + 64);
  *((_DWORD *)v6 + 22) = 0;
  RtlReleaseSRWLockExclusive((char *)v6 + 80);
  v27 = 0;
  if ( v4 )
  {
    do
    {
      UbpmpDecrementRefAndDelete(&v52, 1);
      ++v27;
    }
    while ( v27 < v4 );
    v6 = v52;
  }
  if ( v5 )
    UbpmpTaskHostTerminationCleanup(v6, v5);
  if ( v26 )
    UbpmpSendCommandGetResponse((__int64)v6, 0, 0, 1u);
  v28 = v50;
  if ( v50 )
  {
    UBPM_MIDL_user_free(*((_QWORD *)v50 + 2));
    UBPM_MIDL_user_free(*((_QWORD *)v28 + 3));
    UBPM_MIDL_user_free(*((_QWORD *)v28 + 1));
    UBPM_MIDL_user_free(v28);
  }
  return Reply;
}

```

## disassembly

```asm
0x18000b6d0  mov     [rsp-8+arg_18], rbx
0x18000b6d5  push    rbp
0x18000b6d6  push    rsi
0x18000b6d7  push    rdi
0x18000b6d8  push    r12
0x18000b6da  push    r13
0x18000b6dc  push    r14
0x18000b6de  push    r15
0x18000b6e0  lea     rbp, [rsp-27h]
0x18000b6e5  sub     rsp, 0C0h
0x18000b6ec  movaps  [rsp+0F0h+var_40], xmm6
0x18000b6f4  mov     rax, cs:__security_cookie
0x18000b6fb  xor     rax, rsp
0x18000b6fe  mov     [rbp+57h+var_48], rax
0x18000b702  movzx   r14d, word ptr [rdx]
0x18000b706  xor     eax, eax
0x18000b708  mov     [rbp+57h+Reply], eax
0x18000b70b  mov     r12d, eax
0x18000b70e  mov     [rbp+57h+var_94], eax
0x18000b711  mov     r13d, eax
0x18000b714  mov     [rbp+57h+var_98], eax
0x18000b717  mov     rdi, rcx
0x18000b71a  mov     rax, [rdx+20h]
0x18000b71e  xorps   xmm6, xmm6
0x18000b721  mov     [rbp+57h+var_70], rcx
0x18000b725  mov     rsi, r8
0x18000b728  add     rcx, 50h ; 'P'
0x18000b72c  mov     [rbp+57h+var_78], rax
0x18000b730  mov     [rbp+57h+var_90], r8
0x18000b734  mov     r15, rdx
0x18000b737  mov     [rbp+57h+var_80], rdx
0x18000b73b  mov     [rbp+57h+var_88], r8
0x18000b73f  movups  xmmword ptr [rbp+57h+Handles], xmm6
0x18000b743  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b749  call    cs:__imp_GetCurrentThreadId
0x18000b74f  lea     rbx, [rdi+40h]
0x18000b753  mov     [rdi+58h], eax
0x18000b756  mov     rcx, rbx
0x18000b759  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b75f  call    cs:__imp_GetCurrentThreadId
0x18000b765  mov     [rbx+8], eax
0x18000b768  mov     r10, cs:WPP_GLOBAL_Control
0x18000b76f  lea     r8, WPP_GLOBAL_Control
0x18000b776  cmp     r10, r8
0x18000b779  jnz     loc_18000B966
0x18000b77f  cmp     r14d, 3
0x18000b783  jz      loc_18000BB64
0x18000b789  cmp     r14d, 1
0x18000b78d  jz      loc_18000BC11
0x18000b793  cmp     r14d, 2
0x18000b797  jz      loc_18000BB13
0x18000b79d  movdqa  xmm0, xmm6
0x18000b7a1  mov     [rbp+57h+var_9C], r12b
0x18000b7a5  psrldq  xmm0, 8
0x18000b7aa  xor     r15d, r15d
0x18000b7ad  movd    r12d, xmm0
0x18000b7b2  mov     esi, r15d
0x18000b7b5  cmp     si, 2
0x18000b7b9  jnb     loc_18000B9AC
0x18000b7bf  mov     rcx, rbx
0x18000b7c2  mov     [rbx+8], r15d
0x18000b7c6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b7cc  mov     rax, [rdi+30h]
0x18000b7d0  movzx   r15d, byte ptr [rdi+1B0h]
0x18000b7d8  mov     [rbp+57h+Handles], rax
0x18000b7dc  mov     rax, [rdi+18h]
0x18000b7e0  mov     [rbp+57h+Handles+8], rax
0x18000b7e4  mov     rax, cs:?g_hLowPowerEpochExited@@3PEAXEA; void * g_hLowPowerEpochExited
0x18000b7eb  mov     [rbp+57h+var_58], rax
0x18000b7ef  mov     r9d, cs:?g_dwTaskhostResponseTimeoutMsec@@3KA; dwMilliseconds
0x18000b7f6  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000b7fa  xor     r8d, r8d; bWaitAll
0x18000b7fd  mov     [rsp+0F0h+bAlertable], r13d; bAlertable
0x18000b802  mov     ecx, 2; nCount
0x18000b807  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b80d  mov     ebx, eax
0x18000b80f  cmp     eax, 102h
0x18000b814  jz      loc_18000BC80
0x18000b81a  mov     [rbp+57h+Reply], ebx
0x18000b81d  lea     rbx, [rdi+40h]
0x18000b821  mov     rcx, rbx
0x18000b824  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b82a  call    cs:__imp_GetCurrentThreadId
0x18000b830  mov     [rbx+8], eax
0x18000b833  mov     r8d, [rbp+57h+Reply]
0x18000b837  test    r8d, r8d
0x18000b83a  jnz     loc_18000BAA5
0x18000b840  test    byte ptr [rdi+68h], 4
0x18000b844  jnz     loc_18000C009
0x18000b84a  test    si, si
0x18000b84d  jnz     loc_18000B8EF
0x18000b853  mov     rax, [rdi+0A8h]
0x18000b85a  xorps   xmm0, xmm0
0x18000b85d  mov     rbx, [rdi+38h]
0x18000b861  mov     r15, [rbp+57h+var_80]
0x18000b865  mov     [rbp+57h+var_9C], 1
0x18000b869  mov     [rax], r15
0x18000b86c  xor     r15d, r15d
0x18000b86f  mov     [rdi+0A8h], r15
0x18000b876  mov     [rdi+38h], r15
0x18000b87a  movups  xmmword ptr [rdi+70h], xmm0
0x18000b87e  mov     [rbp+57h+var_80], r15
0x18000b882  movups  xmmword ptr [rdi+80h], xmm0
0x18000b889  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b890  lea     rax, WPP_GLOBAL_Control
0x18000b897  cmp     rcx, rax
0x18000b89a  jz      short loc_18000B8A6
0x18000b89c  test    byte ptr [rcx+1Ch], 80h
0x18000b8a0  jnz     loc_18000BF43
0x18000b8a6  call    cs:__imp_GetCurrentThreadId
0x18000b8ac  lea     rdx, [rbp+57h+Reply]; Reply
0x18000b8b0  mov     rcx, rbx; pAsync
0x18000b8b3  xchg    eax, [rdi+144h]
0x18000b8b9  call    cs:__imp_RpcAsyncCompleteCall
0x18000b8bf  mov     [rbp+57h+Reply], eax
0x18000b8c2  test    eax, eax
0x18000b8c4  jnz     loc_18000BBCC
0x18000b8ca  mov     eax, r15d
0x18000b8cd  lea     rbx, [rdi+40h]
0x18000b8d1  xchg    eax, [rdi+144h]
0x18000b8d7  mov     eax, [rdi+148h]
0x18000b8dd  mov     [rbp+57h+var_94], eax
0x18000b8e0  mov     [rdi+148h], r15d
0x18000b8e7  inc     si
0x18000b8ea  jmp     loc_18000B7B5
0x18000b8ef  mov     rcx, [rdi+30h]; hEvent
0x18000b8f3  call    cs:__imp_SetEvent
0x18000b8f9  movups  xmm1, xmmword ptr [rdi+70h]
0x18000b8fd  mov     r8, [rbp+57h+var_78]
0x18000b901  movups  xmm6, xmmword ptr [rdi+80h]
0x18000b908  xorps   xmm0, xmm0
0x18000b90b  movups  xmmword ptr [rdi+70h], xmm0
0x18000b90f  movups  xmmword ptr [rdi+80h], xmm0
0x18000b916  movdqa  xmm0, xmm1
0x18000b91a  psrldq  xmm0, 8
0x18000b91f  movq    rcx, xmm0
0x18000b924  cmp     r8, rcx
0x18000b927  jnz     loc_18000BFB5
0x18000b92d  movd    r9d, xmm1
0x18000b932  mov     [rbp+57h+Reply], r9d
0x18000b936  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b93d  lea     rax, WPP_GLOBAL_Control
0x18000b944  cmp     rcx, rax
0x18000b947  jz      short loc_18000B953
0x18000b949  test    byte ptr [rcx+1Ch], 80h
0x18000b94d  jnz     loc_18000BF85
0x18000b953  movdqa  xmm0, xmm6
0x18000b957  psrldq  xmm0, 8
0x18000b95c  movd    r12d, xmm0
0x18000b961  xor     r15d, r15d
0x18000b964  jmp     short loc_18000B8E7
0x18000b966  test    byte ptr [r10+1Ch], 80h
0x18000b96b  jz      loc_18000B77F
0x18000b971  movzx   eax, word ptr [rdi+0C4h]
0x18000b978  mov     r9d, r14d
0x18000b97b  mov     rcx, [r10+10h]
0x18000b97f  mov     dword ptr [rsp+0F0h+var_B8], eax
0x18000b983  mov     eax, [rdi+20h]
0x18000b986  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18000b98a  mov     [rsp+0F0h+var_C8], rsi
0x18000b98f  mov     qword ptr [rsp+0F0h+bAlertable], rdi
0x18000b994  call    WPP_SF_dqqdd
0x18000b999  mov     r10, cs:WPP_GLOBAL_Control
0x18000b9a0  lea     r8, WPP_GLOBAL_Control
0x18000b9a7  jmp     loc_18000B77F
0x18000b9ac  cmp     [rbp+57h+Reply], r13d
0x18000b9b0  jnz     loc_18000BAE5
0x18000b9b6  cmp     r14d, 2
0x18000b9ba  jnz     loc_18000BAE5
0x18000b9c0  test    r12b, 1
0x18000b9c4  jnz     loc_18000C144
0x18000b9ca  mov     rcx, [rbp+57h+var_90]
0x18000b9ce  movsd   qword ptr [rcx+60h], xmm6
0x18000b9d3  cmp     [rbp+57h+Reply], r13d
0x18000b9d7  jz      short loc_18000BA08
0x18000b9d9  movzx   eax, word ptr [rdi+0C4h]
0x18000b9e0  test    ax, ax
0x18000b9e3  jz      loc_18000BE23
0x18000b9e9  dec     ax
0x18000b9ec  mov     [rdi+0C4h], ax
0x18000b9f3  jmp     loc_18000BE23
0x18000b9f8  mov     [rbp+57h+Reply], 4D3h
0x18000b9ff  cmp     r10, r8
0x18000ba02  jnz     loc_18000BEBA
0x18000ba08  mov     esi, r13d
0x18000ba0b  mov     r14d, 1
0x18000ba11  cmp     [rdi+0C4h], r13w
0x18000ba19  jz      loc_18000BD22
0x18000ba1f  mov     r12d, [rbp+57h+var_94]
0x18000ba23  xor     r15d, r15d
0x18000ba26  lea     rcx, [rdi+40h]
0x18000ba2a  mov     [rcx+8], r15d
0x18000ba2e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ba34  lea     rcx, [rdi+50h]
0x18000ba38  mov     [rcx+8], r15d
0x18000ba3c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ba42  mov     ebx, r15d
0x18000ba45  test    r12d, r12d
0x18000ba48  jnz     loc_18000C224
0x18000ba4e  test    r13, r13
0x18000ba51  jz      short loc_18000BA5E
0x18000ba53  mov     rdx, r13; WaitHandle
0x18000ba56  mov     rcx, rdi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x18000ba59  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x18000ba5e  test    esi, esi
0x18000ba60  jnz     loc_18000BB84
0x18000ba66  mov     r15, [rbp+57h+var_80]
0x18000ba6a  test    r15, r15
0x18000ba6d  jnz     loc_18000BD71
0x18000ba73  mov     eax, [rbp+57h+Reply]
0x18000ba76  mov     rcx, [rbp+57h+var_48]
0x18000ba7a  xor     rcx, rsp; StackCookie
0x18000ba7d  call    __security_check_cookie
0x18000ba82  mov     rbx, [rsp+0F0h+arg_18]
0x18000ba8a  movaps  xmm6, [rsp+0F0h+var_40]
0x18000ba92  add     rsp, 0C0h
0x18000ba99  pop     r15
0x18000ba9b  pop     r14
0x18000ba9d  pop     r13
0x18000ba9f  pop     r12
0x18000baa1  pop     rdi
0x18000baa2  pop     rsi
0x18000baa3  pop     rbp
0x18000baa4  retn
0x18000baa5  cmp     r8d, 1
0x18000baa9  jnz     loc_18000BD35
0x18000baaf  mov     rcx, rdi
0x18000bab2  call    UbpmpAllTasksStopped
0x18000bab7  test    eax, eax
0x18000bab9  jz      loc_18000C0DD
0x18000babf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bac6  lea     rax, WPP_GLOBAL_Control
0x18000bacd  cmp     rcx, rax
0x18000bad0  jz      short loc_18000BADC
0x18000bad2  test    byte ptr [rcx+1Ch], 80h
0x18000bad6  jnz     loc_18000C121
0x18000badc  xor     r15d, r15d
0x18000badf  mov     eax, r15d
0x18000bae2  mov     [rbp+57h+Reply], eax
0x18000bae5  cmp     r14d, 3
0x18000bae9  jz      loc_18000BDDF
0x18000baef  cmp     r14d, 2
0x18000baf3  jz      loc_18000B9D3
0x18000baf9  cmp     r14d, 1
0x18000bafd  jnz     loc_18000BA08
0x18000bb03  mov     r12d, [rbp+57h+var_94]
0x18000bb07  lea     r8, WPP_GLOBAL_Control
0x18000bb0e  jmp     loc_18000BC30
0x18000bb13  movzx   eax, byte ptr [rdi+68h]
0x18000bb17  test    al, al
0x18000bb19  js      short loc_18000BB23
0x18000bb1b  test    al, 4
0x18000bb1d  jz      loc_18000B79D
0x18000bb23  mov     [rbp+57h+Reply], 10E0h
0x18000bb2a  cmp     r10, r8
0x18000bb2d  jz      loc_18000B9D9
0x18000bb33  test    byte ptr [r10+1Ch], 1
0x18000bb38  jz      loc_18000B9D9
0x18000bb3e  mov     r9d, [rdi+20h]
0x18000bb42  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000bb49  mov     rcx, [r10+10h]
0x18000bb4d  mov     edx, 0A3h
0x18000bb52  mov     [rsp+0F0h+bAlertable], 10E0h
0x18000bb5a  call    WPP_SF_dd
0x18000bb5f  jmp     loc_18000B9D3
0x18000bb64  lea     rdx, [rdi+0C8h]
0x18000bb6b  mov     rax, [rdx]
0x18000bb6e  cmp     rax, rdx
0x18000bb71  jz      loc_18000B9F8
0x18000bb77  mov     ecx, [rsi+38h]
0x18000bb7a  cmp     [rax+28h], ecx
0x18000bb7d  jz      short loc_18000BB99
0x18000bb7f  mov     rax, [rax]
0x18000bb82  jmp     short loc_18000BB6E
0x18000bb84  mov     r9d, r14d
0x18000bb87  xor     r8d, r8d
0x18000bb8a  xor     edx, edx
0x18000bb8c  mov     rcx, rdi
0x18000bb8f  call    UbpmpSendCommandGetResponse
0x18000bb94  jmp     loc_18000BA66
0x18000bb99  cmp     [rsi+60h], r12
0x18000bb9d  jz      loc_18000BE31
0x18000bba3  test    byte ptr [rsi+68h], 1
0x18000bba7  jnz     loc_18000BE53
0x18000bbad  cmp     word ptr [rsi+6Ah], 1
0x18000bbb2  jnz     loc_18000BE7D
0x18000bbb8  mov     rax, [rsi+60h]
0x18000bbbc  mov     [r15+28h], rax
0x18000bbc0  mov     eax, [rsi+38h]
0x18000bbc3  mov     [r15+38h], eax
0x18000bbc7  jmp     loc_18000B79D
0x18000bbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbd3  lea     rax, WPP_GLOBAL_Control
0x18000bbda  cmp     rcx, rax
0x18000bbdd  jz      loc_18000BAE5
0x18000bbe3  test    byte ptr [rcx+1Ch], 1
0x18000bbe7  jz      loc_18000BAE5
0x18000bbed  mov     eax, [rbp+57h+Reply]
0x18000bbf0  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000bbf7  mov     rcx, [rcx+10h]
  ... truncated ...
```
