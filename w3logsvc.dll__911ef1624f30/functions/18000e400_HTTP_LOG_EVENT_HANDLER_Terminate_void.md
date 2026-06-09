# HTTP_LOG_EVENT_HANDLER::Terminate(void)

- ea: `0x18000e400`
- end: `0x18000e470`
- name: `?Terminate@HTTP_LOG_EVENT_HANDLER@@QEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(HTTP_LOG_EVENT_HANDLER *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000adac`
- `0x18000d180`
- `0x18000d814`

## callees

- `0x18000dd54`
- `0x18000de64`
- `0x18000e400`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e442`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e442`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e435`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e435`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e423`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e423`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::Terminate(HTTP_LOG_EVENT_HANDLER *this)
{
  __int64 result; // rax
  struct _TP_TIMER *v3; // rcx

  result = 0;
  if ( *(_DWORD *)this )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + 29);
    if ( v3 )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 29), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 29));
      *((_QWORD *)this + 29) = 0;
    }
    HTTP_LOG_EVENT_HANDLER::DeleteEtwSession(this);
    result = HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer(this);
    if ( (int)result < 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e400  push    rbx
0x18000e402  sub     rsp, 20h
0x18000e406  xor     eax, eax
0x18000e408  mov     rbx, rcx
0x18000e40b  cmp     [rcx], eax
0x18000e40d  jz      short loc_18000E46A
0x18000e40f  mov     rcx, [rcx+0E8h]; pti
0x18000e416  test    rcx, rcx
0x18000e419  jz      short loc_18000E453
0x18000e41b  xor     r9d, r9d; msWindowLength
0x18000e41e  xor     r8d, r8d; msPeriod
0x18000e421  xor     edx, edx; pftDueTime
0x18000e423  call    cs:__imp_SetThreadpoolTimer
0x18000e429  mov     rcx, [rbx+0E8h]; pti
0x18000e430  mov     edx, 1; fCancelPendingCallbacks
0x18000e435  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e43b  mov     rcx, [rbx+0E8h]; pti
0x18000e442  call    cs:__imp_CloseThreadpoolTimer
0x18000e448  mov     qword ptr [rbx+0E8h], 0
0x18000e453  mov     rcx, rbx; this
0x18000e456  call    ?DeleteEtwSession@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ; HTTP_LOG_EVENT_HANDLER::DeleteEtwSession(void)
0x18000e45b  mov     rcx, rbx; this
0x18000e45e  call    ?DeleteEtwConsumer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ; HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer(void)
0x18000e463  xor     ecx, ecx
0x18000e465  test    eax, eax
0x18000e467  cmovs   eax, ecx
0x18000e46a  add     rsp, 20h
0x18000e46e  pop     rbx
0x18000e46f  retn
```
