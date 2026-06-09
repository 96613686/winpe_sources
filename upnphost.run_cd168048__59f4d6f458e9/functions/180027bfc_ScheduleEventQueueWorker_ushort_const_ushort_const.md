# ScheduleEventQueueWorker(ushort const *,ushort const *)

- ea: `0x180027bfc`
- end: `0x180027c9b`
- name: `?ScheduleEventQueueWorker@@YAXPEBG0@Z`
- size: `159`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027700`

## callees

- `0x180027bfc`
- `0x180027ca4`
- `0x180027fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027c55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027c55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027c72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027c72`

## pseudocode

```c
void __fastcall ScheduleEventQueueWorker(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  struct UPNP_EVENT_SOURCE *EventSource; // rax
  struct UPNP_SUBSCRIBER *Subscriber; // rax
  struct UPNP_SUBSCRIBER *v6; // rbx
  void *v7; // rcx

  EnterCriticalSection(&g_csEventApiLock);
  EventSource = PesFindEventSource(a1);
  if ( EventSource )
  {
    Subscriber = PsubFindSubscriber(EventSource, a2);
    v6 = Subscriber;
    if ( Subscriber )
    {
      v7 = (void *)*((_QWORD *)Subscriber + 23);
      if ( v7 )
      {
        if ( *((_QWORD *)Subscriber + 25) )
          SetEvent(v7);
        SetThreadpoolWait(*((PTP_WAIT *)v6 + 27), *((HANDLE *)v6 + 23), 0);
      }
    }
  }
  LeaveCriticalSection(&g_csEventApiLock);
}

```

## disassembly

```asm
0x180027bfc  mov     [rsp+arg_0], rbx
0x180027c01  push    rdi
0x180027c02  sub     rsp, 20h
0x180027c06  mov     rbx, rcx
0x180027c09  mov     rdi, rdx
0x180027c0c  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180027c13  call    cs:__imp_EnterCriticalSection
0x180027c1a  nop     dword ptr [rax+rax+00h]
0x180027c1f  mov     rcx, rbx; unsigned __int16 *
0x180027c22  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180027c27  test    rax, rax
0x180027c2a  jz      short loc_180027C7E
0x180027c2c  mov     rdx, rdi; unsigned __int16 *
0x180027c2f  mov     rcx, rax; struct UPNP_EVENT_SOURCE *
0x180027c32  call    ?PsubFindSubscriber@@YAPEAUUPNP_SUBSCRIBER@@PEAUUPNP_EVENT_SOURCE@@PEBG@Z; PsubFindSubscriber(UPNP_EVENT_SOURCE *,ushort const *)
0x180027c37  mov     rbx, rax
0x180027c3a  test    rax, rax
0x180027c3d  jz      short loc_180027C7E
0x180027c3f  mov     rcx, [rax+0B8h]; hEvent
0x180027c46  test    rcx, rcx
0x180027c49  jz      short loc_180027C7E
0x180027c4b  cmp     qword ptr [rax+0C8h], 0
0x180027c53  jz      short loc_180027C61
0x180027c55  call    cs:__imp_SetEvent
0x180027c5c  nop     dword ptr [rax+rax+00h]
0x180027c61  mov     rdx, [rbx+0B8h]; h
0x180027c68  xor     r8d, r8d; pftTimeout
0x180027c6b  mov     rcx, [rbx+0D8h]; pwa
0x180027c72  call    cs:__imp_SetThreadpoolWait
0x180027c79  nop     dword ptr [rax+rax+00h]
0x180027c7e  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventApiLock
0x180027c85  mov     rbx, [rsp+28h+arg_0]
0x180027c8a  add     rsp, 20h
0x180027c8e  pop     rdi
0x180027c8f  jmp     cs:__imp_LeaveCriticalSection
```
