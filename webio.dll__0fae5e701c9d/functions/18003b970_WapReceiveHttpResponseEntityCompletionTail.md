# WapReceiveHttpResponseEntityCompletionTail

- ea: `0x18003b970`
- end: `0x18003bf2a`
- name: `WapReceiveHttpResponseEntityCompletionTail`
- size: `1466`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036a70`
- `0x18003a7b0`
- `0x18003ad00`
- `0x18003c570`
- `0x18003d1ec`

## callees

- `0x180014f30`
- `0x1800151d0`
- `0x1800180e0`
- `0x18001b150`
- `0x18003b970`
- `0x18003c570`
- `0x18003cad0`
- `0x180054794`
- `0x18005cdf8`
- `0x1800722f0`
- `0x180081680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003bbee`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003bc17`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003bbee`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003bc17`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003bbd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003bbd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bafd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bc44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bdf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bafd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bc44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bdf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bd68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bd68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003be68`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003be41`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003be41`

## pseudocode

```c
char __fastcall WapReceiveHttpResponseEntityCompletionTail(char *lpMem, __int64 a2, __int128 *a3)
{
  __int64 v3; // rbx
  char v5; // r9
  _QWORD *v6; // rdx
  _QWORD *v7; // rax
  __int64 v9; // rcx
  _QWORD *v10; // r8
  _QWORD *v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // r14
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD v16; // ecx
  _QWORD *v17; // rbx
  __int64 v18; // r8
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  __int128 **v21; // rcx
  __int64 v22; // r10
  __int128 **v23; // rax
  __int128 **v24; // rax
  int v25; // eax
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int128 *i; // r15
  unsigned __int64 v29; // r12
  __int64 v30; // r13
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // r8
  unsigned __int64 v34; // rcx
  char v35; // [rsp+30h] [rbp-50h]
  __int128 v37; // [rsp+40h] [rbp-40h] BYREF
  char *v38; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v39[16]; // [rsp+58h] [rbp-28h] BYREF
  char **v40; // [rsp+68h] [rbp-18h]
  __int64 v41; // [rsp+70h] [rbp-10h]

  v37 = 0;
  v3 = a2;
  v35 = 0;
  while ( 1 )
  {
    if ( lpMem[3236] || lpMem[1972] < 0 )
      goto LABEL_9;
    v5 = 0;
    *((_QWORD *)&v37 + 1) = &v37;
    v6 = lpMem + 3216;
    *(_QWORD *)&v37 = &v37;
    while ( 1 )
    {
      v7 = (_QWORD *)*v6;
      if ( (_QWORD *)*v6 == v6 || !*((_BYTE *)v7 + 56) )
        break;
      v9 = *v7;
      if ( *(_QWORD **)(*v7 + 8LL) != v7 )
        goto LABEL_50;
      v10 = (_QWORD *)v7[1];
      if ( (_QWORD *)*v10 != v7 )
        goto LABEL_50;
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      v11 = (_QWORD *)*((_QWORD *)&v37 + 1);
      if ( **((__int128 ***)&v37 + 1) != &v37 )
        goto LABEL_50;
      v7[1] = *((_QWORD *)&v37 + 1);
      a3 = &v37;
      *v7 = &v37;
      *v11 = v7;
      *((_QWORD *)&v37 + 1) = v7;
      if ( *((_DWORD *)v7 + 34) == 38 )
        v5 = 1;
      *((_QWORD *)lpMem + 469) += v7[18];
    }
    if ( (lpMem[56] || !*((_DWORD *)lpMem + 12)) && v7 == v6 )
    {
      v21 = (__int128 **)(lpMem + 3200);
      while ( 1 )
      {
        a3 = *v21;
        if ( *v21 == (__int128 *)v21 )
          break;
        *((_DWORD *)a3 + 34) = *((_DWORD *)lpMem + 13);
        *((_QWORD *)a3 + 18) = 0;
        *((_BYTE *)a3 + 56) = 1;
        v22 = *(_QWORD *)a3;
        if ( *(__int128 **)(*(_QWORD *)a3 + 8LL) != a3 )
          goto LABEL_50;
        v23 = (__int128 **)*((_QWORD *)a3 + 1);
        if ( *v23 != a3 )
          goto LABEL_50;
        *v23 = (__int128 *)v22;
        *(_QWORD *)(v22 + 8) = v23;
        v24 = (__int128 **)*((_QWORD *)&v37 + 1);
        if ( **((__int128 ***)&v37 + 1) != &v37 )
          goto LABEL_50;
        *((_QWORD *)a3 + 1) = *((_QWORD *)&v37 + 1);
        *(_QWORD *)a3 = &v37;
        *v24 = a3;
        *((_QWORD *)&v37 + 1) = a3;
      }
    }
    if ( (__int128 *)v37 == &v37 )
    {
LABEL_9:
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      return v35;
    }
    if ( *((char **)lpMem + 400) != lpMem + 3200 )
      goto LABEL_20;
    if ( (_QWORD *)*v6 != v6 )
      goto LABEL_20;
    if ( !v5 )
      goto LABEL_20;
    v25 = *((_DWORD *)lpMem + 493);
    if ( (v25 & 0x10) != 0 )
      goto LABEL_20;
    *((_DWORD *)lpMem + 493) = v25 | 0x10;
    if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
    {
      v38 = lpMem;
      v40 = &v38;
      v41 = 8;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, RequestReceiveComplete, a3, 2, v39);
    }
    if ( lpMem[304] < 0 )
    {
      lpMem[3236] = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      WaFinishHttpRequest(lpMem);
      v12 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 8);
    }
    else
    {
LABEL_20:
      lpMem[3236] = 1;
      v12 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 8);
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
    }
    if ( (__int128 *)v37 != &v37 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      if ( lpMem[56] || !*((_DWORD *)lpMem + 12) )
      {
        v13 = v12;
      }
      else
      {
        if ( *((_QWORD *)lpMem + 584) && (unsigned __int8)WaHttpExtensionIsPushDataActive(lpMem) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
          for ( i = (__int128 *)v37; i != &v37; i = *(__int128 **)i )
          {
            if ( *((_DWORD *)i + 34) )
            {
              WaHttpExtensionOnReceiveDataStream(lpMem, 0, 0);
              break;
            }
            v29 = *((_QWORD *)i + 18);
            v30 = 0;
            while ( (unsigned int)v30 < *((_DWORD *)i + 6) )
            {
              if ( !v29 )
                break;
              v31 = *((_QWORD *)i + 2);
              v32 = *(_QWORD *)(v31 + 24 * v30 + 16);
              v33 = v32;
              if ( v29 <= v32 )
                v33 = v29;
              WaHttpExtensionOnReceiveDataStream(lpMem, *(_QWORD *)(v31 + 24 * v30 + 8), v33);
              v34 = v29;
              v29 -= v32;
              v30 = (unsigned int)(v30 + 1);
              if ( v34 <= v32 )
                v29 = 0;
            }
          }
          v3 = a2;
          goto LABEL_27;
        }
        v13 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 8);
      }
      LeaveCriticalSection(v13);
    }
LABEL_27:
    if ( v3 )
    {
      v19 = (_QWORD *)(v3 + 16);
      if ( *((_QWORD *)&v37 + 1) == v3 + 16 && (_QWORD)v37 == *((_QWORD *)&v37 + 1) )
      {
        if ( **((__int128 ***)&v37 + 1) != &v37 )
          goto LABEL_50;
        v20 = *(_QWORD **)(*((_QWORD *)&v37 + 1) + 8LL);
        if ( *v20 != *((_QWORD *)&v37 + 1) )
          goto LABEL_50;
        *((_QWORD *)&v37 + 1) = *(_QWORD *)(*((_QWORD *)&v37 + 1) + 8LL);
        *v20 = &v37;
        *(_QWORD *)(v3 + 24) = v19;
        *v19 = v19;
        v35 = 1;
      }
    }
    v14 = v37;
    if ( (__int128 *)v37 != &v37 )
      break;
LABEL_37:
    EnterCriticalSection(v12);
    lpMem[3236] = 0;
  }
  if ( *(__int128 **)(v37 + 8) != &v37 )
    goto LABEL_50;
  *((_QWORD *)lpMem + 411) = v37;
  *((_QWORD *)lpMem + 412) = &v37;
  *(_QWORD *)(v14 + 8) = lpMem + 3288;
  *(_QWORD *)&v37 = lpMem + 3288;
  if ( *((__int128 **)lpMem + 412) != &v37 )
    goto LABEL_50;
  v15 = *((_QWORD *)&v37 + 1);
  if ( **((__int128 ***)&v37 + 1) != &v37 )
    goto LABEL_50;
  **((_QWORD **)&v37 + 1) = lpMem + 3288;
  *((_QWORD *)lpMem + 412) = v15;
  _InterlockedIncrement((volatile signed __int32 *)lpMem + 1);
  v16 = WaCallbackQueueTlsIndex;
  v17 = lpMem + 3240;
  *((_QWORD *)lpMem + 406) = lpMem + 3240;
  *((_QWORD *)lpMem + 405) = lpMem + 3240;
  *((_QWORD *)lpMem + 410) = WapCompleteHttpResponseReceiveTrackersCallback;
  *((_QWORD *)lpMem + 407) = -1;
  if ( !TlsGetValue(v16) && TlsSetValue(WaCallbackQueueTlsIndex, (LPVOID)1) )
  {
    LOBYTE(v18) = 1;
    WapCompleteHttpResponseReceiveTrackersCallback(lpMem + 3240, 0, v18);
    TlsSetValue(WaCallbackQueueTlsIndex, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 1, 0xFFFFFFFF) == 1 )
      WapDestroyHttpRequest(lpMem);
    v3 = a2;
    goto LABEL_37;
  }
  WaGetCurrentThreadToken((__int64 *)lpMem + 407);
  WaEtwControlActivityId((LPGUID)lpMem + 204);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    McTemplateU0pq_EventWriteTransfer(v26, ThreadActionQueue, lpMem + 3240, 2);
  EnterCriticalSection(&WaGlobalCallbackQueueLock);
  v27 = (_QWORD *)qword_1800AEB38;
  if ( *(__int64 **)qword_1800AEB38 != &WaGlobalCallbackQueue )
LABEL_50:
    __fastfail(3u);
  *v17 = &WaGlobalCallbackQueue;
  *((_QWORD *)lpMem + 406) = v27;
  *v27 = v17;
  qword_1800AEB38 = (__int64)(lpMem + 3240);
  LeaveCriticalSection(&WaGlobalCallbackQueueLock);
  SubmitThreadpoolWork(pwk);
  return 0;
}

```

## disassembly

```asm
0x18003b970  push    rbp
0x18003b972  push    rbx
0x18003b973  push    rsi
0x18003b974  push    rdi
0x18003b975  push    r12
0x18003b977  push    r13
0x18003b979  push    r15
0x18003b97b  mov     rbp, rsp
0x18003b97e  sub     rsp, 80h
0x18003b985  mov     rax, cs:__security_cookie
0x18003b98c  xor     rax, rsp
0x18003b98f  mov     [rbp+var_8], rax
0x18003b993  xorps   xmm0, xmm0
0x18003b996  mov     [rbp+var_48], rdx
0x18003b99a  movups  [rbp+var_40], xmm0
0x18003b99e  mov     rbx, rdx
0x18003b9a1  mov     [rbp+var_50], 0
0x18003b9a5  mov     rdi, rcx
0x18003b9a8  mov     [rsp+80h+arg_10], r14
0x18003b9b0  mov     r12d, 1
0x18003b9b6  lea     r15, WapCompleteHttpResponseReceiveTrackersCallback
0x18003b9bd  cmp     byte ptr [rdi+0CA4h], 0
0x18003b9c4  jnz     short loc_18003BA13
0x18003b9c6  test    byte ptr [rdi+7B4h], 80h
0x18003b9cd  jnz     short loc_18003BA13
0x18003b9cf  lea     rax, [rbp+var_40]
0x18003b9d3  xor     r9b, r9b
0x18003b9d6  mov     qword ptr [rbp+var_40+8], rax
0x18003b9da  lea     rdx, [rdi+0C90h]
0x18003b9e1  lea     rax, [rbp+var_40]
0x18003b9e5  mov     qword ptr [rbp+var_40], rax
0x18003b9e9  mov     rax, [rdx]
0x18003b9ec  cmp     rax, rdx
0x18003b9ef  jnz     short loc_18003BA4E
0x18003b9f1  cmp     byte ptr [rdi+38h], 0
0x18003b9f5  jnz     loc_18003BCAC
0x18003b9fb  cmp     dword ptr [rdi+30h], 0
0x18003b9ff  jz      loc_18003BCAC
0x18003ba05  lea     rax, [rbp+var_40]
0x18003ba09  cmp     qword ptr [rbp+var_40], rax
0x18003ba0d  jnz     loc_18003BABA
0x18003ba13  lea     rcx, [rdi+8]; lpCriticalSection
0x18003ba17  call    cs:__imp_LeaveCriticalSection
0x18003ba1e  nop     dword ptr [rax+rax+00h]
0x18003ba23  movzx   eax, [rbp+var_50]
0x18003ba27  mov     r14, [rsp+80h+arg_10]
0x18003ba2f  mov     rcx, [rbp+var_8]
0x18003ba33  xor     rcx, rsp; StackCookie
0x18003ba36  call    __security_check_cookie
0x18003ba3b  add     rsp, 80h
0x18003ba42  pop     r15
0x18003ba44  pop     r13
0x18003ba46  pop     r12
0x18003ba48  pop     rdi
0x18003ba49  pop     rsi
0x18003ba4a  pop     rbx
0x18003ba4b  pop     rbp
0x18003ba4c  retn
0x18003ba4e  cmp     byte ptr [rax+38h], 0
0x18003ba52  jz      short loc_18003B9F1
0x18003ba54  mov     rcx, [rax]
0x18003ba57  cmp     [rcx+8], rax
0x18003ba5b  jnz     loc_18003BD1C
0x18003ba61  mov     r8, [rax+8]
0x18003ba65  cmp     [r8], rax
0x18003ba68  jnz     loc_18003BD1C
0x18003ba6e  mov     [r8], rcx
0x18003ba71  mov     [rcx+8], r8
0x18003ba75  lea     r8, [rbp+var_40]
0x18003ba79  mov     rcx, qword ptr [rbp+var_40+8]
0x18003ba7d  cmp     [rcx], r8
0x18003ba80  jnz     loc_18003BD1C
0x18003ba86  mov     [rax+8], rcx
0x18003ba8a  lea     r8, [rbp+var_40]
0x18003ba8e  mov     [rax], r8
0x18003ba91  mov     [rcx], rax
0x18003ba94  mov     qword ptr [rbp+var_40+8], rax
0x18003ba98  cmp     dword ptr [rax+88h], 26h ; '&'
0x18003ba9f  mov     rcx, [rax+90h]
0x18003baa6  movzx   r9d, r9b
0x18003baaa  cmovz   r9d, r12d
0x18003baae  add     [rdi+0EA8h], rcx
0x18003bab5  jmp     loc_18003B9E9
0x18003baba  lea     rax, [rdi+0C80h]
0x18003bac1  cmp     [rax], rax
0x18003bac4  jnz     short loc_18003BAD4
0x18003bac6  cmp     [rdx], rdx
0x18003bac9  jnz     short loc_18003BAD4
0x18003bacb  test    r9b, r9b
0x18003bace  jnz     loc_18003BD30
0x18003bad4  lea     rcx, [rdi+8]; lpCriticalSection
0x18003bad8  mov     byte ptr [rdi+0CA4h], 1
0x18003badf  lea     r14, [rdi+8]
0x18003bae3  call    cs:__imp_LeaveCriticalSection
0x18003baea  nop     dword ptr [rax+rax+00h]
0x18003baef  lea     rax, [rbp+var_40]
0x18003baf3  cmp     qword ptr [rbp+var_40], rax
0x18003baf7  jz      short loc_18003BB3B
0x18003baf9  lea     rcx, [rdi+8]; lpCriticalSection
0x18003bafd  call    cs:__imp_EnterCriticalSection
0x18003bb04  nop     dword ptr [rax+rax+00h]
0x18003bb09  cmp     byte ptr [rdi+38h], 0
0x18003bb0d  jnz     loc_18003BD85
0x18003bb13  cmp     dword ptr [rdi+30h], 0
0x18003bb17  jz      loc_18003BD85
0x18003bb1d  cmp     qword ptr [rdi+1240h], 0
0x18003bb25  jnz     loc_18003BE54
0x18003bb2b  lea     rcx, [rdi+8]; lpCriticalSection
0x18003bb2f  call    cs:__imp_LeaveCriticalSection
0x18003bb36  nop     dword ptr [rax+rax+00h]
0x18003bb3b  test    rbx, rbx
0x18003bb3e  jnz     loc_18003BC5C
0x18003bb44  mov     rcx, qword ptr [rbp+var_40]
0x18003bb48  lea     rax, [rbp+var_40]
0x18003bb4c  cmp     rcx, rax
0x18003bb4f  jz      loc_18003BC41
0x18003bb55  lea     rax, [rbp+var_40]
0x18003bb59  cmp     [rcx+8], rax
0x18003bb5d  jnz     loc_18003BD1C
0x18003bb63  lea     rax, [rdi+0CD8h]
0x18003bb6a  mov     [rax], rcx
0x18003bb6d  lea     rdx, [rbp+var_40]
0x18003bb71  mov     [rax+8], rdx
0x18003bb75  mov     [rcx+8], rax
0x18003bb79  lea     rcx, [rbp+var_40]
0x18003bb7d  mov     qword ptr [rbp+var_40], rax
0x18003bb81  cmp     [rax+8], rcx
0x18003bb85  jnz     loc_18003BD1C
0x18003bb8b  mov     rcx, qword ptr [rbp+var_40+8]
0x18003bb8f  lea     rdx, [rbp+var_40]
0x18003bb93  cmp     [rcx], rdx
0x18003bb96  jnz     loc_18003BD1C
0x18003bb9c  mov     [rcx], rax
0x18003bb9f  mov     [rax+8], rcx
0x18003bba3  lock inc dword ptr [rdi+4]
0x18003bba7  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x18003bbad  lea     rbx, [rdi+0CA8h]
0x18003bbb4  mov     [rdi+0CB0h], rbx
0x18003bbbb  mov     [rbx], rbx
0x18003bbbe  mov     [rdi+0CD0h], r15
0x18003bbc5  mov     qword ptr [rdi+0CB8h], 0FFFFFFFFFFFFFFFFh
0x18003bbd0  call    cs:__imp_TlsGetValue
0x18003bbd7  nop     dword ptr [rax+rax+00h]
0x18003bbdc  test    rax, rax
0x18003bbdf  jnz     loc_18003BDC5
0x18003bbe5  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x18003bbeb  mov     rdx, r12; lpTlsValue
0x18003bbee  call    cs:__imp_TlsSetValue
0x18003bbf5  nop     dword ptr [rax+rax+00h]
0x18003bbfa  test    eax, eax
0x18003bbfc  jz      loc_18003BDC5
0x18003bc02  mov     r8b, 1
0x18003bc05  xor     edx, edx
0x18003bc07  mov     rcx, rbx
0x18003bc0a  call    WapCompleteHttpResponseReceiveTrackersCallback
0x18003bc0f  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x18003bc15  xor     edx, edx; lpTlsValue
0x18003bc17  call    cs:__imp_TlsSetValue
0x18003bc1e  nop     dword ptr [rax+rax+00h]
0x18003bc23  mov     eax, 0FFFFFFFFh
0x18003bc28  lock xadd [rdi+4], eax
0x18003bc2d  cmp     eax, 1
0x18003bc30  jz      loc_18003BD23
0x18003bc36  mov     rbx, [rbp+var_48]
0x18003bc3a  lea     r15, WapCompleteHttpResponseReceiveTrackersCallback
0x18003bc41  mov     rcx, r14; lpCriticalSection
0x18003bc44  call    cs:__imp_EnterCriticalSection
0x18003bc4b  nop     dword ptr [rax+rax+00h]
0x18003bc50  mov     byte ptr [rdi+0CA4h], 0
0x18003bc57  jmp     loc_18003B9BD
0x18003bc5c  mov     rax, qword ptr [rbp+var_40+8]
0x18003bc60  lea     rcx, [rbx+10h]
0x18003bc64  cmp     rax, rcx
0x18003bc67  jnz     loc_18003BB44
0x18003bc6d  cmp     qword ptr [rbp+var_40], rax
0x18003bc71  jnz     loc_18003BB44
0x18003bc77  lea     rdx, [rbp+var_40]
0x18003bc7b  cmp     [rax], rdx
0x18003bc7e  jnz     loc_18003BD1C
0x18003bc84  mov     rdx, [rax+8]
0x18003bc88  cmp     [rdx], rax
0x18003bc8b  jnz     loc_18003BD1C
0x18003bc91  lea     rax, [rbp+var_40]
0x18003bc95  mov     qword ptr [rbp+var_40+8], rdx
0x18003bc99  mov     [rdx], rax
0x18003bc9c  mov     [rbx+18h], rcx
0x18003bca0  mov     [rcx], rcx
0x18003bca3  mov     [rbp+var_50], 1
0x18003bca7  jmp     loc_18003BB44
0x18003bcac  cmp     rax, rdx
0x18003bcaf  jnz     loc_18003BA05
0x18003bcb5  lea     rcx, [rdi+0C80h]
0x18003bcbc  mov     r8, [rcx]
0x18003bcbf  cmp     r8, rcx
0x18003bcc2  jz      loc_18003BA05
0x18003bcc8  mov     eax, [rdi+34h]
0x18003bccb  mov     [r8+88h], eax
0x18003bcd2  mov     qword ptr [r8+90h], 0
0x18003bcdd  mov     byte ptr [r8+38h], 1
0x18003bce2  mov     r10, [r8]
0x18003bce5  cmp     [r10+8], r8
0x18003bce9  jnz     short loc_18003BD1C
0x18003bceb  mov     rax, [r8+8]
0x18003bcef  cmp     [rax], r8
0x18003bcf2  jnz     short loc_18003BD1C
0x18003bcf4  mov     [rax], r10
0x18003bcf7  mov     [r10+8], rax
0x18003bcfb  lea     r10, [rbp+var_40]
0x18003bcff  mov     rax, qword ptr [rbp+var_40+8]
0x18003bd03  cmp     [rax], r10
0x18003bd06  jnz     short loc_18003BD1C
0x18003bd08  mov     [r8+8], rax
0x18003bd0c  lea     r10, [rbp+var_40]
0x18003bd10  mov     [r8], r10
0x18003bd13  mov     [rax], r8
0x18003bd16  mov     qword ptr [rbp+var_40+8], r8
0x18003bd1a  jmp     short loc_18003BCBC
0x18003bd1c  mov     ecx, 3
0x18003bd21  int     29h; Win8: RtlFailFast(ecx)
0x18003bd23  mov     rcx, rdi; lpMem
0x18003bd26  call    WapDestroyHttpRequest
0x18003bd2b  jmp     loc_18003BC36
0x18003bd30  mov     eax, [rdi+7B4h]
0x18003bd36  test    al, 10h
0x18003bd38  jnz     loc_18003BAD4
0x18003bd3e  or      eax, 10h
0x18003bd41  mov     [rdi+7B4h], eax
0x18003bd47  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x18003bd4e  jnz     short loc_18003BD8D
0x18003bd50  test    byte ptr [rdi+130h], 80h
0x18003bd57  jz      loc_18003BAD4
0x18003bd5d  lea     rcx, [rdi+8]; lpCriticalSection
0x18003bd61  mov     byte ptr [rdi+0CA4h], 1
0x18003bd68  call    cs:__imp_LeaveCriticalSection
0x18003bd6f  nop     dword ptr [rax+rax+00h]
0x18003bd74  mov     rcx, rdi
0x18003bd77  call    WaFinishHttpRequest
0x18003bd7c  lea     r14, [rdi+8]
0x18003bd80  jmp     loc_18003BAEF
0x18003bd85  mov     rcx, r14
0x18003bd88  jmp     loc_18003BB2F
0x18003bd8d  lea     rax, [rbp+var_30]
0x18003bd91  mov     [rbp+var_30], rdi
0x18003bd95  mov     [rbp+var_18], rax
0x18003bd99  lea     rdx, RequestReceiveComplete
0x18003bda0  lea     rax, [rbp+var_28]
0x18003bda4  mov     [rbp+var_10], 8
0x18003bdac  mov     r9d, 2
0x18003bdb2  mov     [rsp+80h+var_60], rax
0x18003bdb7  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18003bdbe  call    McGenEventWrite_EventWriteTransfer
0x18003bdc3  jmp     short loc_18003BD50
0x18003bdc5  lea     rcx, [rdi+0CB8h]
0x18003bdcc  call    WaGetCurrentThreadToken
0x18003bdd1  lea     rcx, [rbx+18h]; ActivityId
0x18003bdd5  mov     edx, 2
0x18003bdda  call    WaEtwControlActivityId
0x18003bddf  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x18003bde6  jnz     loc_18003BF10
0x18003bdec  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x18003bdf3  call    cs:__imp_EnterCriticalSection
0x18003bdfa  nop     dword ptr [rax+rax+00h]
0x18003bdff  mov     rax, cs:qword_1800AEB38
0x18003be06  lea     rcx, WaGlobalCallbackQueue
0x18003be0d  cmp     [rax], rcx
0x18003be10  jnz     loc_18003BD1C
0x18003be16  mov     [rbx], rcx
0x18003be19  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x18003be20  mov     [rbx+8], rax
0x18003be24  mov     [rax], rbx
0x18003be27  mov     cs:qword_1800AEB38, rbx
0x18003be2e  call    cs:__imp_LeaveCriticalSection
0x18003be35  nop     dword ptr [rax+rax+00h]
0x18003be3a  mov     rcx, cs:pwk; pwk
0x18003be41  call    cs:__imp_SubmitThreadpoolWork
0x18003be48  nop     dword ptr [rax+rax+00h]
0x18003be4d  xor     al, al
0x18003be4f  jmp     loc_18003BA27
0x18003be54  mov     rcx, rdi
0x18003be57  call    WaHttpExtensionIsPushDataActive
0x18003be5c  test    al, al
0x18003be5e  jz      loc_18003BB2B
0x18003be64  lea     rcx, [rdi+8]; lpCriticalSection
0x18003be68  call    cs:__imp_LeaveCriticalSection
0x18003be6f  nop     dword ptr [rax+rax+00h]
0x18003be74  mov     r15, qword ptr [rbp+var_40]
0x18003be78  lea     rax, [rbp+var_40]
0x18003be7c  cmp     r15, rax
0x18003be7f  jz      short loc_18003BEFA
0x18003be81  mov     r9d, [r15+88h]
0x18003be88  test    r9d, r9d
0x18003be8b  jnz     short loc_18003BEED
0x18003be8d  mov     r12, [r15+90h]
0x18003be94  xor     r13d, r13d
0x18003be97  cmp     [r15+18h], r13d
0x18003be9b  jbe     short loc_18003BEE8
0x18003be9d  test    r12, r12
0x18003bea0  jz      short loc_18003BEE8
0x18003bea2  mov     rax, [r15+10h]
0x18003bea6  lea     rcx, ds:0[r13*2]
  ... truncated ...
```
