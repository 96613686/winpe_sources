# WaQueueCallback

- ea: `0x180035390`
- end: `0x1800354fe`
- name: `WaQueueCallback`
- size: `366`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033fe4`
- `0x180035350`
- `0x180035370`
- `0x180036448`
- `0x18003d1ec`

## callees

- `0x180014f30`
- `0x180035390`
- `0x180054794`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800353e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180035411`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800353e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180035411`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800353cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800353cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035477`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800354ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800354ae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035457`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180035457`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800354c1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800354c1`

## pseudocode

```c
char __fastcall WaQueueCallback(__int64 a1, void (__fastcall *a2)(__int64, _QWORD, __int64))
{
  __int64 v4; // r8
  __int64 v6; // rcx
  __int64 *v7; // rax

  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = a1;
  *(_QWORD *)(a1 + 40) = a2;
  *(_QWORD *)(a1 + 16) = -1;
  if ( TlsGetValue(WaCallbackQueueTlsIndex) || !TlsSetValue(WaCallbackQueueTlsIndex, (LPVOID)1) )
  {
    WaGetCurrentThreadToken((__int64 *)(a1 + 16));
    if ( EventActivityIdControl(1u, (LPGUID)(a1 + 24)) )
      *(_OWORD *)(a1 + 24) = 0;
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
      McTemplateU0pq_EventWriteTransfer(v6, ThreadActionQueue, a1, 2);
    EnterCriticalSection(&WaGlobalCallbackQueueLock);
    v7 = (__int64 *)qword_1800AEB38;
    if ( *(__int64 **)qword_1800AEB38 != &WaGlobalCallbackQueue )
      __fastfail(3u);
    *(_QWORD *)a1 = &WaGlobalCallbackQueue;
    *(_QWORD *)(a1 + 8) = v7;
    *v7 = a1;
    qword_1800AEB38 = a1;
    LeaveCriticalSection(&WaGlobalCallbackQueueLock);
    SubmitThreadpoolWork(pwk);
    return 1;
  }
  else
  {
    LOBYTE(v4) = 1;
    a2(a1, 0, v4);
    TlsSetValue(WaCallbackQueueTlsIndex, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180035390  mov     [rsp+arg_10], rbx
0x180035395  mov     [rsp+arg_18], rsi
0x18003539a  push    rdi
0x18003539b  sub     rsp, 40h
0x18003539f  mov     rax, cs:__security_cookie
0x1800353a6  xor     rax, rsp
0x1800353a9  mov     [rsp+48h+var_18], rax
0x1800353ae  mov     [rcx+8], rcx
0x1800353b2  mov     rbx, rcx
0x1800353b5  mov     [rcx], rcx
0x1800353b8  mov     rdi, rdx
0x1800353bb  mov     [rcx+28h], rdx
0x1800353bf  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x1800353c7  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x1800353cd  call    cs:__imp_TlsGetValue
0x1800353d4  nop     dword ptr [rax+rax+00h]
0x1800353d9  test    rax, rax
0x1800353dc  jnz     short loc_18003543D
0x1800353de  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x1800353e4  mov     edx, 1; lpTlsValue
0x1800353e9  call    cs:__imp_TlsSetValue
0x1800353f0  nop     dword ptr [rax+rax+00h]
0x1800353f5  test    eax, eax
0x1800353f7  jz      short loc_18003543D
0x1800353f9  mov     r8b, 1
0x1800353fc  xor     edx, edx
0x1800353fe  mov     rcx, rbx
0x180035401  mov     rax, rdi
0x180035404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035409  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x18003540f  xor     edx, edx; lpTlsValue
0x180035411  call    cs:__imp_TlsSetValue
0x180035418  nop     dword ptr [rax+rax+00h]
0x18003541d  xor     al, al
0x18003541f  mov     rcx, [rsp+48h+var_18]
0x180035424  xor     rcx, rsp; StackCookie
0x180035427  call    __security_check_cookie
0x18003542c  mov     rbx, [rsp+48h+arg_10]
0x180035431  mov     rsi, [rsp+48h+arg_18]
0x180035436  add     rsp, 40h
0x18003543a  pop     rdi
0x18003543b  retn
0x18003543d  lea     rcx, [rbx+10h]
0x180035441  call    WaGetCurrentThreadToken
0x180035446  xorps   xmm0, xmm0
0x180035449  lea     rdx, [rbx+18h]; ActivityId
0x18003544d  mov     ecx, 1; ControlCode
0x180035452  movups  [rsp+48h+var_28], xmm0
0x180035457  call    cs:__imp_EventActivityIdControl
0x18003545e  nop     dword ptr [rax+rax+00h]
0x180035463  test    eax, eax
0x180035465  jnz     short loc_1800354DB
0x180035467  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x18003546e  jnz     short loc_1800354E4
0x180035470  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x180035477  call    cs:__imp_EnterCriticalSection
0x18003547e  nop     dword ptr [rax+rax+00h]
0x180035483  mov     rax, cs:qword_1800AEB38
0x18003548a  lea     rcx, WaGlobalCallbackQueue
0x180035491  cmp     [rax], rcx
0x180035494  jnz     short loc_1800354D4
0x180035496  mov     [rbx], rcx
0x180035499  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x1800354a0  mov     [rbx+8], rax
0x1800354a4  mov     [rax], rbx
0x1800354a7  mov     cs:qword_1800AEB38, rbx
0x1800354ae  call    cs:__imp_LeaveCriticalSection
0x1800354b5  nop     dword ptr [rax+rax+00h]
0x1800354ba  mov     rcx, cs:pwk; pwk
0x1800354c1  call    cs:__imp_SubmitThreadpoolWork
0x1800354c8  nop     dword ptr [rax+rax+00h]
0x1800354cd  mov     al, 1
0x1800354cf  jmp     loc_18003541F
0x1800354d4  mov     ecx, 3
0x1800354d9  int     29h; Win8: RtlFailFast(ecx)
0x1800354db  xorps   xmm0, xmm0
0x1800354de  movups  xmmword ptr [rbx+18h], xmm0
0x1800354e2  jmp     short loc_180035467
0x1800354e4  mov     r9d, 2
0x1800354ea  lea     rdx, ThreadActionQueue
0x1800354f1  mov     r8, rbx
0x1800354f4  call    McTemplateU0pq_EventWriteTransfer
0x1800354f9  jmp     loc_180035470
```
