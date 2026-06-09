# ScheduleEventQueueWorker(ushort const *,ushort const *)

- ea: `0x180026af0`
- end: `0x180026b8a`
- name: `?ScheduleEventQueueWorker@@YAXPEBG0@Z`
- size: `154`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026630`

## callees

- `0x180026af0`
- `0x180026b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b27`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026b55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026b55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026b83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180026b6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180026b6c`

## pseudocode

```c
void __fastcall ScheduleEventQueueWorker(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  struct UPNP_EVENT_SOURCE *EventSource; // rax
  __int64 i; // rbx
  void *v6; // rcx

  EnterCriticalSection(&g_csEventApiLock);
  EventSource = PesFindEventSource(a1);
  if ( EventSource )
  {
    for ( i = *((_QWORD *)EventSource + 2); i; i = *(_QWORD *)(i + 272) )
    {
      if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(i + 40), a2) )
      {
        v6 = *(void **)(i + 184);
        if ( v6 )
        {
          if ( *(_QWORD *)(i + 200) )
            SetEvent(v6);
          SetThreadpoolWait(*(PTP_WAIT *)(i + 216), *(HANDLE *)(i + 184), 0);
        }
        break;
      }
    }
  }
  LeaveCriticalSection(&g_csEventApiLock);
}

```

## disassembly

```asm
0x180026af0  mov     [rsp+arg_0], rbx
0x180026af5  push    rdi
0x180026af6  sub     rsp, 20h
0x180026afa  mov     rbx, rcx
0x180026afd  mov     rdi, rdx
0x180026b00  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180026b07  call    cs:__imp_EnterCriticalSection
0x180026b0d  mov     rcx, rbx; unsigned __int16 *
0x180026b10  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180026b15  test    rax, rax
0x180026b18  jz      short loc_180026B72
0x180026b1a  mov     rbx, [rax+10h]
0x180026b1e  jmp     short loc_180026B38
0x180026b20  mov     rcx, [rbx+28h]
0x180026b24  mov     rdx, rdi
0x180026b27  call    cs:__imp__o__wcsicmp
0x180026b2d  test    eax, eax
0x180026b2f  jz      short loc_180026B3F
0x180026b31  mov     rbx, [rbx+110h]
0x180026b38  test    rbx, rbx
0x180026b3b  jnz     short loc_180026B20
0x180026b3d  jmp     short loc_180026B72
0x180026b3f  mov     rcx, [rbx+0B8h]; hEvent
0x180026b46  test    rcx, rcx
0x180026b49  jz      short loc_180026B72
0x180026b4b  cmp     qword ptr [rbx+0C8h], 0
0x180026b53  jz      short loc_180026B5B
0x180026b55  call    cs:__imp_SetEvent
0x180026b5b  mov     rdx, [rbx+0B8h]; h
0x180026b62  xor     r8d, r8d; pftTimeout
0x180026b65  mov     rcx, [rbx+0D8h]; pwa
0x180026b6c  call    cs:__imp_SetThreadpoolWait
0x180026b72  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventApiLock
0x180026b79  mov     rbx, [rsp+28h+arg_0]
0x180026b7e  add     rsp, 20h
0x180026b82  pop     rdi
0x180026b83  jmp     cs:__imp_LeaveCriticalSection
```
