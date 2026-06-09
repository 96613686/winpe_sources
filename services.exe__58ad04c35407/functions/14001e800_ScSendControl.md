# ScSendControl

- ea: `0x14001e800`
- end: `0x14001f517`
- name: `ScSendControl`
- size: `3351`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000d900`
- `0x14001e4d4`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000cee0`
- `0x140013b0c`
- `0x1400188fc`
- `0x140019014`
- `0x14001e800`
- `0x14001ff44`
- `0x140021a88`
- `0x140021ef4`
- `0x14002309c`
- `0x140024864`
- `0x14002dad4`
- `0x14002f840`
- `0x140032be0`
- `0x140035f80`
- `0x140038698`
- `0x140043284`
- `0x14006cbac`
- `0x14006d030`
- `0x14006dd4c`
- `0x14006dde8`
- `0x14006de94`
- `0x140081b6c`
- `0x140092420`
- `0x140092ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001f058`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001f058`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14001ed25`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14001ed25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f266`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001f38f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001f3e5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001f38f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001f3e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001ec18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001ec18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ef6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ef6b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14001ee62`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14001ee62`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14001e85a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14001e85a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001e8a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001e96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001eaa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001e8a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001e96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001eaa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001ef8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001ef98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001f4d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001ef8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001ef98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001f4d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001ef5a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001ef5a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001ec12`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001ec12`
- `ntdll!RtlFreeHeap` at `0x14001ee49`
- `ntdll!RtlFreeHeap` at `0x14001ef84`
- `ntdll!RtlFreeHeap` at `0x14001f4ee`
- `ntdll!RtlFreeHeap` at `0x14001ee49`
- `ntdll!RtlFreeHeap` at `0x14001ef84`
- `ntdll!RtlFreeHeap` at `0x14001f4ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001f48f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001f48f`

## pseudocode

```c
__int64 __fastcall ScSendControl(
        __int64 a1,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        PRPC_ASYNC_STATE pAsync,
        unsigned int a7,
        int a8,
        __int64 *a9,
        unsigned int a10,
        LPWSTR StringSid,
        int a12,
        int a13,
        unsigned int a14,
        unsigned __int16 *a15,
        PVOID *a16,
        int *a17,
        int a18)
{
  signed __int64 v18; // r12
  const unsigned __int16 *v23; // rsi
  __int64 v24; // rax
  SIZE_T v25; // r14
  HLOCAL v26; // rax
  unsigned int v27; // r15d
  PRPC_ASYNC_STATE v28; // rcx
  int v29; // edx
  __int64 v30; // r8
  __int64 *v31; // r14
  unsigned int v32; // r13d
  _DWORD *v33; // rax
  _DWORD *v34; // r12
  int v35; // eax
  PRPC_ASYNC_STATE v36; // rcx
  int v37; // edx
  __int64 v38; // rdx
  unsigned int i; // ecx
  __int64 v40; // rax
  __int64 v41; // r12
  _DWORD *v42; // rax
  _DWORD *v43; // r11
  unsigned __int16 *v44; // r15
  __int64 v45; // r12
  __int64 v46; // rax
  __int64 v47; // r10
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  unsigned int v51; // eax
  unsigned int v52; // r13d
  DWORD v53; // r9d
  DWORD v54; // eax
  int v55; // r8d
  unsigned __int128 v56; // rax
  _QWORD *v57; // rax
  HLOCAL v58; // rcx
  __int64 v59; // rax
  HLOCAL v60; // rcx
  struct _RPC_ASYNC_STATE *v61; // rcx
  RPC_STATUS v62; // eax
  __int64 v63; // rax
  unsigned int v64; // eax
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v66; // rcx
  int v67; // edx
  int v68; // r8d
  __m128i v69; // xmm6
  __m128i v70; // xmm1
  __int64 v71; // r13
  void *v72; // xmm0_8
  unsigned __int64 v73; // xmm0_8
  int v74; // eax
  PRPC_ASYNC_STATE v75; // rcx
  int v76; // r9d
  unsigned __int8 v77; // al
  char v78; // al
  unsigned __int16 *v79; // rdx
  char v80; // r12
  __int64 v81; // rdx
  char v82; // al
  char ProcessId; // al
  HANDLE v84; // rbx
  int v85; // edx
  int v86; // r8d
  const unsigned __int16 *v88; // [rsp+48h] [rbp-79h] BYREF
  DWORD dwMilliseconds; // [rsp+50h] [rbp-71h]
  unsigned int Pid; // [rsp+54h] [rbp-6Dh] BYREF
  int v91; // [rsp+58h] [rbp-69h]
  int v92; // [rsp+5Ch] [rbp-65h]
  HLOCAL hMem; // [rsp+60h] [rbp-61h]
  BOOL v94; // [rsp+68h] [rbp-59h]
  HLOCAL v95; // [rsp+70h] [rbp-51h]
  HANDLE Handles[2]; // [rsp+78h] [rbp-49h] BYREF
  __int64 v97; // [rsp+88h] [rbp-39h]
  PVOID P[2]; // [rsp+A0h] [rbp-21h]
  unsigned int Reply; // [rsp+108h] [rbp+47h] BYREF
  HANDLE hObject; // [rsp+110h] [rbp+4Fh] BYREF

  hObject = a2;
  v18 = 0;
  Reply = 0;
  hMem = 0;
  dwMilliseconds = *(_DWORD *)&g_ControlMessageTimeout;
  Pid = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)Handles = 0;
  I_RpcBindingInqLocalClientPID(0, &Pid);
  Handles[0] = *(HANDLE *)(a1 + 80);
  Handles[1] = a2;
  if ( StringSid )
    *(_DWORD *)StringSid = 1235;
  v23 = (const unsigned __int16 *)pAsync;
  if ( !pAsync )
    v23 = a4;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  v25 = (unsigned int)(2 * v24 + 2);
  v26 = LocalAlloc(0x40u, v25);
  v27 = a7;
  v95 = v26;
  if ( !v26 )
  {
    Reply = 8;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v29 = 110;
LABEL_11:
      WPP_SF_Sd(v28->StubInfo, v29, (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, (_DWORD)a3, 8);
      goto LABEL_102;
    }
    goto LABEL_102;
  }
  StringCbCopyW((unsigned __int16 *)v26, v25, v23);
  v31 = a9;
  v94 = a12 != 0;
  if ( !a9 || (v30 = *a9) == 0 || (v32 = a10) == 0 )
  {
    v91 = 0;
    if ( v27 != 32 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
      {
        v37 = 115;
        goto LABEL_32;
      }
    }
    goto LABEL_49;
  }
  if ( v27 - 80 <= 1 )
  {
    LODWORD(v38) = 0;
    for ( i = 0; i < a10; ++i )
    {
      v40 = -1;
      do
        ++v40;
      while ( *(_WORD *)(*(_QWORD *)(v30 + 8LL * i) + 2 * v40) );
      v38 = (unsigned int)(v38 + 2 * v40 + 2);
    }
    v41 = 8LL * (a10 - 1) + 16;
    v42 = LocalAlloc(0x40u, v41 + v38);
    v43 = v42;
    if ( !v42 )
    {
      Reply = 8;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v29 = 111;
        goto LABEL_11;
      }
      goto LABEL_102;
    }
    v44 = (unsigned __int16 *)((char *)v42 + v41);
    v91 = 1;
    v45 = 0;
    hMem = v42;
    *v42 = v32;
    LODWORD(pAsync) = 0;
    do
    {
      v46 = -1;
      do
        ++v46;
      while ( *(_WORD *)(*(_QWORD *)(*v31 + 8 * v45) + 2 * v46) );
      *(_QWORD *)&v43[2 * v45 + 2] = v44;
      StringCbCopyW(v44, (unsigned int)(2 * v46 + 2), *(const unsigned __int16 **)(*v31 + 8 * v45));
      v44 = (unsigned __int16 *)((char *)v44 + v47);
      ++v45;
      LODWORD(pAsync) = (_DWORD)pAsync + 1;
    }
    while ( (unsigned int)pAsync < v32 );
    v27 = a7;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
    {
      WPP_SF_LSLqi(WPP_GLOBAL_Control->StubInfo, 112, v30, a7, (__int64)a3, Pid, a1, *(_QWORD *)(a1 + 112));
    }
    goto LABEL_48;
  }
  v33 = LocalAlloc(0x40u, *((unsigned int *)a9 + 1) + 16LL);
  v34 = v33;
  if ( v33 )
  {
    *v33 = *(_DWORD *)v31;
    v35 = *((_DWORD *)v31 + 1);
    v91 = 2;
    v34[1] = v35;
    if ( v35 )
    {
      *((_QWORD *)v34 + 1) = v34 + 4;
      memmove(v34 + 4, (const void *)v31[1], *((unsigned int *)v31 + 1));
    }
    hMem = v34;
    if ( v27 != 16 )
    {
      if ( v27 == 13 && *(_DWORD *)v31 == 32787 && *((_DWORD *)v31 + 1) >= 0x18u )
      {
        v18 = 0;
        if ( !memcmp((const void *)v31[1], &GUID_IDLE_BACKGROUND_TASK, 0x10u) )
          goto LABEL_49;
      }
      else
      {
        v18 = 0;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
      {
        v37 = 114;
LABEL_32:
        WPP_SF_LSLqi(v36->StubInfo, v37, v30, v27, (__int64)a3, Pid, a1, *(_QWORD *)(a1 + 112));
      }
LABEL_49:
      v92 = 0;
      if ( v27 == 1 || v27 == 15 )
      {
        if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v30) )
        {
          LODWORD(pAsync) = v27;
          v88 = a3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v48,
            (__int64)&dword_1400AE784,
            v49,
            v50,
            &v88);
        }
        if ( (unsigned int)IsEventEnabled(&ServiceSendControlStop) )
          EventWriteServiceSendControlStop(a3, a5, v27);
      }
      RtlAcquireSRWLockExclusive(a1 + 128);
      *(_DWORD *)(a1 + 136) = GetCurrentThreadId();
      if ( a13 )
      {
        v51 = ScPushProcessOntoPoBlameStack(*(_DWORD *)(a1 + 96), *(_DWORD *)(a1 + 104));
        Reply = v51;
        if ( v51 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 116, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v51);
          }
        }
        else
        {
          v92 = 1;
        }
      }
      v52 = 0;
      LODWORD(v88) = 0;
      v97 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      while ( 1 )
      {
        if ( (*(_BYTE *)(a1 + 141) & 4) != 0 )
        {
          LOBYTE(LastError) = 43;
          Reply = 1067;
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_89;
          }
          v67 = 117;
          goto LABEL_115;
        }
        if ( g_fDefaultControlMessageTimeout == 1 && *(_BYTE *)(a1 + 140) == 10 )
        {
          LOBYTE(pAsync) = 1;
          v53 = 1000;
        }
        else
        {
          v53 = dwMilliseconds;
          LOBYTE(pAsync) = 0;
        }
        v54 = WaitForMultipleObjectsEx((Handles[1] != 0) + 1, Handles, 0, v53, 0);
        if ( v54 )
          break;
        *(_BYTE *)(a1 + 140) = 0;
        if ( v52 == 1 )
        {
          SetEvent(*(HANDLE *)(a1 + 80));
          v69 = *(__m128i *)(a1 + 48);
          v70 = *(__m128i *)(a1 + 32);
          v71 = *(_QWORD *)(a1 + 48);
          *(_OWORD *)(a1 + 32) = 0;
          *(_OWORD *)(a1 + 48) = 0;
          v72 = (void *)_mm_srli_si128(v69, 8).m128i_u64[0];
          P[1] = v72;
          if ( HIDWORD(v71) && !v72 )
          {
            Reply = 8;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                122,
                (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                (_DWORD)a3,
                8);
LABEL_121:
              v52 = (unsigned int)v88;
              goto LABEL_89;
            }
            goto LABEL_179;
          }
          v73 = _mm_srli_si128(v70, 8).m128i_u64[0];
          if ( v73 != v18 )
          {
            Reply = 776;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sdii(WPP_GLOBAL_Control->StubInfo, v73, v68, (_DWORD)a3, 8, v18, v73);
              goto LABEL_121;
            }
LABEL_179:
            v52 = (unsigned int)v88;
            goto LABEL_89;
          }
          v74 = _mm_cvtsi128_si32(v70);
          Reply = v74;
          if ( v74 )
          {
            v75 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sddi(WPP_GLOBAL_Control->StubInfo, v73, v68, (_DWORD)a3, v74, v27, v73);
              goto LABEL_130;
            }
          }
          else
          {
LABEL_130:
            v75 = WPP_GLOBAL_Control;
          }
          if ( StringSid )
          {
            *(_DWORD *)StringSid = v71;
            if ( !(_DWORD)v71 )
              goto LABEL_136;
            v75 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_dS(
                WPP_GLOBAL_Control->StubInfo,
                125,
                (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                v71,
                (__int64)a3);
LABEL_136:
              v75 = WPP_GLOBAL_Control;
            }
          }
          if ( !Reply && a16 )
          {
            v76 = _mm_cvtsi128_si32(_mm_srli_si128(v69, 4));
            if ( (unsigned int)(v76 - 1) <= 0x7F )
            {
              v52 = (unsigned int)v88;
              *a16 = P[1];
              P[1] = 0;
              if ( a17 )
                *a17 = v76;
              goto LABEL_89;
            }
            Reply = 13;
            if ( v75 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v75->UserInfo) & 1) != 0 )
            {
              WPP_SF_dSd(
                v75->StubInfo,
                126,
                (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                v76,
                (__int64)a3,
                13);
              goto LABEL_121;
            }
          }
          goto LABEL_179;
        }
        v56 = ((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8);
        if ( *((_QWORD *)&v56 + 1) - v97 >= (unsigned __int64)dwMilliseconds )
          dwMilliseconds = 1000;
        else
          dwMilliseconds += v97 - DWORD2(v56);
        for ( ; !v18; v18 = _InterlockedIncrement64((volatile signed __int64 *)&s_ullControlSequence) )
          ;
        if ( v27 - 80 <= 1 )
          _InterlockedExchange64((volatile __int64 *)(a1 + 120), v18);
        pAsync = (PRPC_ASYNC_STATE)_InterlockedExchange64((volatile __int64 *)(a1 + 24), 0);
        if ( !pAsync )
        {
          LOBYTE(LastError) = 43;
          Reply = 1067;
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v67 = 127;
            goto LABEL_115;
          }
          goto LABEL_89;
        }
        v57 = *(_QWORD **)(a1 + 72);
        v58 = v95;
        v95 = 0;
        *v57 = v58;
        LODWORD(v58) = a8;
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) = v18;
        **(_DWORD **)(a1 + 64) = v27;
        *(_DWORD *)(*(_QWORD *)(a1 + 64) + 20LL) = (_DWORD)v58;
        *(_DWORD *)(*(_QWORD *)(a1 + 64) + 24LL) = *(_DWORD *)&g_dwHandlerTimeout;
        *(_DWORD *)(*(_QWORD *)(a1 + 64) + 16LL) = v94;
        *(_DWORD *)(*(_QWORD *)(a1 + 64) + 28LL) = a14;
        *(_DWORD *)(*(_QWORD *)(a1 + 64) + 32LL) = v91;
        v59 = *(_QWORD *)(a1 + 64);
        v60 = hMem;
        hMem = 0;
        *(_QWORD *)(v59 + 40) = v60;
        *(_QWORD *)(a1 + 64) = 0;
        *(_QWORD *)(a1 + 72) = 0;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(a1 + 56));
        v61 = pAsync;
        *(_OWORD *)(a1 + 32) = 0;
        *(_OWORD *)(a1 + 48) = 0;
        v62 = RpcAsyncCompleteCall(v61, &Reply);
        if ( v62 )
        {
          Reply = v62;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              128,
              (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
              (_DWORD)a3,
              v62);
          }
          goto LABEL_89;
        }
        if ( !a18 )
        {
          LODWORD(v88) = ++v52;
          if ( v52 < 2 )
            continue;
        }
        goto LABEL_89;
      }
      if ( v54 != 1 )
      {
        if ( v54 == 258 )
        {
          v77 = *(_BYTE *)(a1 + 140);
          Reply = 1053;
          if ( v77 < 0xAu )
          {
            v78 = v77 + 1;
            *(_BYTE *)(a1 + 140) = v78;
            if ( v78 == 10 )
            {
              v79 = a5;
              if ( !a5 )
                v79 = (unsigned __int16 *)a3;
              ScLogEvent(0x2Eu, v79);
            }
          }
          if ( *(_BYTE *)(a1 + 140) < 0xAu && a3 )
          {
            v80 = (char)pAsync;
            if ( *a3 )
            {
              v81 = *(unsigned int *)&g_ControlMessageTimeout;
              if ( (_BYTE)pAsync )
                v81 = 1000;
              ScLogEvent(0xBu, v81, a3);
            }
          }
          else
          {
            v80 = (char)pAsync;
          }
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v82 = dwMilliseconds;
            if ( v80 )
              v82 = -24;
            WPP_SF_Sdddd(
              WPP_GLOBAL_Control->StubInfo,
              *(unsigned __int8 *)(a1 + 140),
              v55,
              (_DWORD)a3,
              *(_BYTE *)(a1 + 140),
              v52,
              Reply,
              v82);
          }
          goto LABEL_89;
        }
        if ( v54 != -1 )
        {
          Reply = 1235;
          goto LABEL_89;
        }
        LastError = GetLastError();
        Reply = LastError;
        v66 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
LABEL_89:
          if ( v27 - 80 <= 1 )
          {
            v63 = _InterlockedExchange64((volatile __int64 *)(a1 + 120), 0);
            if ( v52 == 1 && Reply == 1053 && !v63 )
            {
              Reply = 0;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
              {
                WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 129, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, a3);
              }
            }
          }
          goto LABEL_96;
        }
        v67 = 121;
LABEL_115:
        WPP_SF_SLd(
          v66->StubInfo,
          v67,
          (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
          (_DWORD)a3,
          v52,
          LastError);
        goto LABEL_89;
      }
      if ( v27 != 32 )
      {
        Reply = 109;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          ProcessId = GetProcessId(Handles[1]);
          WPP_SF_Sddd(
            WPP_GLOBAL_Control->StubInfo,
            119,
            (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
            (_DWORD)a3,
            ProcessId,
            v52,
            109);
        }
        goto LABEL_89;
      }
      Reply = 0;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      {
        GetProcessId(Handles[1]);
        WPP_SF_LLL(WPP_GLOBAL_Control->StubInfo, 120, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
      }
LABEL_96:
      if ( v92 )
      {
        v64 = ScPopFromPoBlameStack();
        Reply = v64;
        if ( v64 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 130, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v64);
          }
        }
      }
      *(_DWORD *)(a1 + 136) = 0;
      RtlReleaseSRWLockExclusive(a1 + 128);
      goto LABEL_102;
    }
LABEL_48:
    v18 = 0;
    goto LABEL_49;
  }
  Reply = 8;
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v29 = 113;
    goto LABEL_11;
  }
LABEL_102:
  if ( hObject )
    CloseHandle(hObject);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  LocalFree(hMem);
  LocalFree(v95);
  if ( !Reply && (v27 - 1 <= 2 || v27 == 15) && a5 && *a5 )
  {
    if ( v27 == 1 && a14 )
    {
      ScLogServiceEvent(0x2Au, a5, 1u, a14, a15, a3);
    }
    else
    {
      hObject = 0;
      StringSid = 0;
      ScLogServiceEvent(0x23u, a5, v27, 0, 0, 0);
      if ( !ScGetClientSid((struct _TOKEN_USER **)&hObject) )
      {
        v84 = hObject;
        if ( ConvertSidToStringSidW(*(PSID *)hObject, &StringSid) )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_SdSL(WPP_GLOBAL_Control->StubInfo, v85, v86, (_DWORD)a3, v27, (__int64)StringSid, Pid);
          }
          LocalFree(StringSid);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v84);
      }
    }
  }
  return Reply;
}

```

## disassembly

```asm
0x14001e800  mov     rax, rsp
0x14001e803  mov     [rax+18h], rbx
0x14001e807  mov     [rax+10h], rdx
0x14001e80b  push    rbp
0x14001e80c  push    rsi
0x14001e80d  push    rdi
0x14001e80e  push    r12
0x14001e810  push    r13
0x14001e812  push    r14
0x14001e814  push    r15
0x14001e816  lea     rbp, [rax-3Fh]
0x14001e81a  sub     rsp, 0C0h
0x14001e821  xor     r12d, r12d
0x14001e824  movaps  xmmword ptr [rax-48h], xmm6
0x14001e828  mov     eax, cs:?g_ControlMessageTimeout@@3KA; ulong g_ControlMessageTimeout
0x14001e82e  xorps   xmm0, xmm0
0x14001e831  mov     rsi, rdx
0x14001e834  mov     [rbp+37h+Reply], r12d
0x14001e838  mov     rbx, rcx
0x14001e83b  mov     [rbp+37h+hMem], r12
0x14001e83f  lea     rdx, [rbp+37h+Pid]; Pid
0x14001e843  mov     [rbp+37h+dwMilliseconds], eax
0x14001e846  xor     ecx, ecx; Binding
0x14001e848  mov     [rbp+37h+Pid], r12d
0x14001e84c  movups  xmmword ptr [rbp+37h+P], xmm0
0x14001e850  mov     r14, r9
0x14001e853  mov     rdi, r8
0x14001e856  movups  xmmword ptr [rbp+37h+Handles], xmm0
0x14001e85a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14001e860  mov     rax, [rbx+50h]
0x14001e864  mov     [rbp+37h+Handles], rax
0x14001e868  mov     rax, [rbp+37h+StringSid]
0x14001e86f  mov     [rbp+37h+Handles+8], rsi
0x14001e873  test    rax, rax
0x14001e876  jz      short loc_14001E87E
0x14001e878  mov     dword ptr [rax], 4D3h
0x14001e87e  mov     rsi, [rbp+37h+pAsync]
0x14001e882  test    rsi, rsi
0x14001e885  cmovz   rsi, r14
0x14001e889  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e88d  inc     rax
0x14001e890  cmp     [rsi+rax*2], r12w
0x14001e895  jnz     short loc_14001E88D
0x14001e897  lea     eax, ds:2[rax*2]
0x14001e89e  mov     ecx, 40h ; '@'; uFlags
0x14001e8a3  mov     edx, eax; uBytes
0x14001e8a5  mov     r14d, eax
0x14001e8a8  call    cs:__imp_LocalAlloc
0x14001e8ae  mov     r15d, [rbp+37h+arg_30]
0x14001e8b2  mov     [rbp+37h+var_88], rax
0x14001e8b6  test    rax, rax
0x14001e8b9  jnz     short loc_14001E904
0x14001e8bb  lea     r8d, [rax+8]
0x14001e8bf  mov     [rbp+37h+Reply], r8d
0x14001e8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e8ca  lea     rsi, WPP_GLOBAL_Control
0x14001e8d1  cmp     rcx, rsi
0x14001e8d4  jz      loc_14001EF60
0x14001e8da  test    byte ptr [rcx+1Ch], 1
0x14001e8de  jz      loc_14001EF60
0x14001e8e4  lea     edx, [rax+6Eh]
0x14001e8e7  mov     rcx, [rcx+10h]
0x14001e8eb  mov     r9, rdi
0x14001e8ee  mov     [rsp+0F0h+bAlertable], r8d
0x14001e8f3  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14001e8fa  call    WPP_SF_Sd
0x14001e8ff  jmp     loc_14001EF60
0x14001e904  mov     r8, rsi; unsigned __int16 *
0x14001e907  mov     rdx, r14; unsigned __int64
0x14001e90a  mov     rcx, rax; unsigned __int16 *
0x14001e90d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14001e912  cmp     [rbp+37h+arg_58], r12d
0x14001e919  lea     rsi, WPP_GLOBAL_Control
0x14001e920  mov     r14, [rbp+37h+arg_40]
0x14001e927  mov     eax, r12d
0x14001e92a  setnz   al
0x14001e92d  mov     [rbp+37h+var_90], eax
0x14001e930  test    r14, r14
0x14001e933  jz      loc_14001EC76
0x14001e939  mov     r8, [r14]
0x14001e93c  test    r8, r8
0x14001e93f  jz      loc_14001EC76
0x14001e945  mov     r13d, [rbp+37h+arg_48]
0x14001e94c  test    r13d, r13d
0x14001e94f  jz      loc_14001EC76
0x14001e955  lea     eax, [r15-50h]
0x14001e959  cmp     eax, 1
0x14001e95c  jbe     loc_14001EA6E
0x14001e962  mov     edx, [r14+4]
0x14001e966  mov     ecx, 40h ; '@'; uFlags
0x14001e96b  add     rdx, 10h; uBytes
0x14001e96f  call    cs:__imp_LocalAlloc
0x14001e975  mov     r12, rax
0x14001e978  test    rax, rax
0x14001e97b  jnz     short loc_14001E9A7
0x14001e97d  lea     r8d, [rax+8]
0x14001e981  mov     [rbp+37h+Reply], r8d
0x14001e985  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e98c  cmp     rcx, rsi
0x14001e98f  jz      loc_14001EF60
0x14001e995  test    byte ptr [rcx+1Ch], 1
0x14001e999  jz      loc_14001EF60
0x14001e99f  lea     edx, [rax+71h]
0x14001e9a2  jmp     loc_14001E8E7
0x14001e9a7  mov     eax, [r14]
0x14001e9aa  mov     [r12], eax
0x14001e9ae  mov     eax, [r14+4]
0x14001e9b2  mov     [rbp+37h+var_A0], 2
0x14001e9b9  mov     [r12+4], eax
0x14001e9be  test    eax, eax
0x14001e9c0  jz      short loc_14001E9D9
0x14001e9c2  lea     rcx, [r12+10h]; void *
0x14001e9c7  mov     [r12+8], rcx
0x14001e9cc  mov     r8d, [r14+4]; Size
0x14001e9d0  mov     rdx, [r14+8]; Src
0x14001e9d4  call    memmove
0x14001e9d9  mov     [rbp+37h+hMem], r12
0x14001e9dd  cmp     r15d, 10h
0x14001e9e1  jz      loc_14001EB8B
0x14001e9e7  cmp     r15d, 0Dh
0x14001e9eb  jnz     short loc_14001EA1E
0x14001e9ed  cmp     dword ptr [r14], 8013h
0x14001e9f4  jnz     short loc_14001EA1E
0x14001e9f6  cmp     dword ptr [r14+4], 18h
0x14001e9fb  jb      short loc_14001EA1E
0x14001e9fd  mov     rcx, [r14+8]; Buf1
0x14001ea01  lea     r8d, [r15+3]; Size
0x14001ea05  lea     rdx, GUID_IDLE_BACKGROUND_TASK; Buf2
0x14001ea0c  call    memcmp
0x14001ea11  xor     r12d, r12d
0x14001ea14  test    eax, eax
0x14001ea16  jz      loc_14001EB8E
0x14001ea1c  jmp     short loc_14001EA21
0x14001ea1e  xor     r12d, r12d
0x14001ea21  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea28  cmp     rcx, rsi
0x14001ea2b  jz      loc_14001EB8E
0x14001ea31  test    dword ptr [rcx+1Ch], 100000h
0x14001ea38  jz      loc_14001EB8E
0x14001ea3e  mov     edx, 72h ; 'r'
0x14001ea43  mov     rax, [rbx+70h]
0x14001ea47  mov     r9d, r15d
0x14001ea4a  mov     rcx, [rcx+10h]
0x14001ea4e  mov     [rsp+0F0h+var_B8], rax
0x14001ea53  mov     eax, [rbp+37h+Pid]
0x14001ea56  mov     [rsp+0F0h+var_C0], rbx
0x14001ea5b  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14001ea5f  mov     qword ptr [rsp+0F0h+bAlertable], rdi
0x14001ea64  call    WPP_SF_LSLqi
0x14001ea69  jmp     loc_14001EB8E
0x14001ea6e  mov     edx, r12d
0x14001ea71  mov     ecx, r12d
0x14001ea74  mov     eax, ecx
0x14001ea76  mov     r9, [r8+rax*8]
0x14001ea7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ea7e  inc     rax
0x14001ea81  cmp     [r9+rax*2], r12w
0x14001ea86  jnz     short loc_14001EA7E
0x14001ea88  lea     edx, [rdx+rax*2]
0x14001ea8b  inc     ecx
0x14001ea8d  add     edx, 2
0x14001ea90  cmp     ecx, r13d
0x14001ea93  jb      short loc_14001EA74
0x14001ea95  lea     eax, [r13-1]
0x14001ea99  mov     ecx, 40h ; '@'; uFlags
0x14001ea9e  lea     r12, ds:10h[rax*8]
0x14001eaa6  add     rdx, r12; uBytes
0x14001eaa9  call    cs:__imp_LocalAlloc
0x14001eaaf  xor     edx, edx
0x14001eab1  mov     r11, rax
0x14001eab4  test    rax, rax
0x14001eab7  jnz     short loc_14001EAE3
0x14001eab9  lea     r8d, [rax+8]
0x14001eabd  mov     [rbp+37h+Reply], r8d
0x14001eac1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eac8  cmp     rcx, rsi
0x14001eacb  jz      loc_14001EF60
0x14001ead1  test    byte ptr [rcx+1Ch], 1
0x14001ead5  jz      loc_14001EF60
0x14001eadb  lea     edx, [rax+6Fh]
0x14001eade  jmp     loc_14001E8E7
0x14001eae3  lea     r15, [rax+r12]
0x14001eae7  mov     [rbp+37h+var_A0], 1
0x14001eaee  mov     r12, rdx
0x14001eaf1  mov     [rbp+37h+hMem], r11
0x14001eaf5  mov     [rax], r13d
0x14001eaf8  mov     dword ptr [rbp+37h+pAsync], edx
0x14001eafb  mov     rax, [r14]
0x14001eafe  mov     rcx, [rax+r12*8]
0x14001eb02  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001eb06  inc     rax
0x14001eb09  cmp     [rcx+rax*2], dx
0x14001eb0d  jnz     short loc_14001EB06
0x14001eb0f  mov     [r11+r12*8+8], r15
0x14001eb14  lea     eax, ds:2[rax*2]
0x14001eb1b  mov     r8, [r14]
0x14001eb1e  mov     rcx, r15; unsigned __int16 *
0x14001eb21  mov     edx, eax; unsigned __int64
0x14001eb23  mov     r10d, eax
0x14001eb26  mov     r8, [r8+r12*8]; unsigned __int16 *
0x14001eb2a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14001eb2f  mov     ecx, dword ptr [rbp+37h+pAsync]
0x14001eb32  add     r15, r10
0x14001eb35  inc     ecx
0x14001eb37  inc     r12
0x14001eb3a  mov     dword ptr [rbp+37h+pAsync], ecx
0x14001eb3d  mov     edx, 0
0x14001eb42  cmp     ecx, r13d
0x14001eb45  jb      short loc_14001EAFB
0x14001eb47  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb4e  mov     r15d, [rbp+37h+arg_30]
0x14001eb52  cmp     rcx, rsi
0x14001eb55  jz      short loc_14001EB8B
0x14001eb57  test    dword ptr [rcx+1Ch], 100000h
0x14001eb5e  jz      short loc_14001EB8B
0x14001eb60  mov     rax, [rbx+70h]
0x14001eb64  mov     edx, 70h ; 'p'
0x14001eb69  mov     rcx, [rcx+10h]
0x14001eb6d  mov     r9d, r15d
0x14001eb70  mov     [rsp+0F0h+var_B8], rax
0x14001eb75  mov     eax, [rbp+37h+Pid]
0x14001eb78  mov     [rsp+0F0h+var_C0], rbx
0x14001eb7d  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14001eb81  mov     qword ptr [rsp+0F0h+bAlertable], rdi
0x14001eb86  call    WPP_SF_LSLqi
0x14001eb8b  xor     r12d, r12d
0x14001eb8e  xor     r14d, r14d
0x14001eb91  mov     [rbp+37h+var_9C], r14d
0x14001eb95  cmp     r15d, 1
0x14001eb99  jz      short loc_14001EBA1
0x14001eb9b  cmp     r15d, 0Fh
0x14001eb9f  jnz     short loc_14001EC0B
0x14001eba1  mov     eax, cs:dword_1400BA2A0
0x14001eba7  cmp     eax, 5
0x14001ebaa  jbe     short loc_14001EBEC
0x14001ebac  mov     rdx, 200000000000h
0x14001ebb6  lea     rcx, dword_1400BA2A0
0x14001ebbd  call    _tlgKeywordOn
0x14001ebc2  test    al, al
0x14001ebc4  jz      short loc_14001EBEC
0x14001ebc6  lea     rax, [rbp+37h+pAsync]
0x14001ebca  mov     dword ptr [rbp+37h+pAsync], r15d
0x14001ebce  mov     [rsp+0F0h+var_C8], rax
0x14001ebd3  lea     rdx, dword_1400AE784
0x14001ebda  lea     rax, [rbp+37h+var_B0]
0x14001ebde  mov     [rbp+37h+var_B0], rdi
0x14001ebe2  mov     qword ptr [rsp+0F0h+bAlertable], rax
0x14001ebe7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001ebec  lea     rcx, ServiceSendControlStop; struct _EVENT_DESCRIPTOR *
0x14001ebf3  call    ?IsEventEnabled@@YAHPEBU_EVENT_DESCRIPTOR@@@Z; IsEventEnabled(_EVENT_DESCRIPTOR const *)
0x14001ebf8  test    eax, eax
0x14001ebfa  jz      short loc_14001EC0B
0x14001ebfc  mov     rdx, [rbp+37h+arg_20]; unsigned __int16 *
0x14001ec00  mov     r8d, r15d; unsigned int
0x14001ec03  mov     rcx, rdi; unsigned __int16 *
0x14001ec06  call    ?EventWriteServiceSendControlStop@@YAXPEBG0K@Z; EventWriteServiceSendControlStop(ushort const *,ushort const *,ulong)
0x14001ec0b  lea     rcx, [rbx+80h]
0x14001ec12  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001ec18  call    cs:__imp_GetCurrentThreadId
0x14001ec1e  xor     r10d, r10d
0x14001ec21  mov     [rbx+88h], eax
0x14001ec27  lea     r14, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14001ec2e  cmp     [rbp+37h+arg_60], r10d
0x14001ec35  jz      short loc_14001ECB2
0x14001ec37  mov     edx, [rbx+68h]; unsigned int
0x14001ec3a  mov     ecx, [rbx+60h]; unsigned int
0x14001ec3d  call    ?ScPushProcessOntoPoBlameStack@@YAKKK@Z; ScPushProcessOntoPoBlameStack(ulong,ulong)
0x14001ec42  xor     r10d, r10d
0x14001ec45  mov     [rbp+37h+Reply], eax
0x14001ec48  test    eax, eax
0x14001ec4a  jz      short loc_14001ECAB
0x14001ec4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec53  cmp     rcx, rsi
0x14001ec56  jz      short loc_14001ECB2
0x14001ec58  test    byte ptr [rcx+1Ch], 1
0x14001ec5c  jz      short loc_14001ECB2
0x14001ec5e  mov     rcx, [rcx+10h]
0x14001ec62  lea     edx, [r10+74h]
0x14001ec66  mov     r9d, eax
0x14001ec69  mov     r8, r14
0x14001ec6c  call    WPP_SF_d
0x14001ec71  xor     r10d, r10d
0x14001ec74  jmp     short loc_14001ECB2
0x14001ec76  mov     [rbp+37h+var_A0], r12d
0x14001ec7a  cmp     r15d, 20h ; ' '
0x14001ec7e  jz      loc_14001EB8E
0x14001ec84  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec8b  cmp     rcx, rsi
0x14001ec8e  jz      loc_14001EB8E
0x14001ec94  test    dword ptr [rcx+1Ch], 100000h
0x14001ec9b  jz      loc_14001EB8E
0x14001eca1  mov     edx, 73h ; 's'
0x14001eca6  jmp     loc_14001EA43
0x14001ecab  mov     [rbp+37h+var_9C], 1
0x14001ecb2  mov     ecx, ds:7FFE0004h
0x14001ecb9  mov     eax, 7FFE0320h
0x14001ecbe  shl     rcx, 20h
0x14001ecc2  mov     r13d, r10d
0x14001ecc5  mov     dword ptr [rbp+37h+var_B0], r10d
0x14001ecc9  mov     rax, [rax]
  ... truncated ...
```
