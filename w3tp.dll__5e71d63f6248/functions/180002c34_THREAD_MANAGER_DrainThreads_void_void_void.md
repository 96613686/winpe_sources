# THREAD_MANAGER::DrainThreads(void (*)(void *),void *)

- ea: `0x180002c34`
- end: `0x180002d4e`
- name: `?DrainThreads@THREAD_MANAGER@@AEAAXP6AXPEAX@Z0@Z`
- size: `282`
- prototype: `void(THREAD_MANAGER *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003418`

## callees

- `0x180001770`
- `0x180002c34`
- `0x180003ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c72`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002cfc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002cfc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002c9b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002c9b`
- `iisutil!PuDbgPrint` at `0x180002cf1`
- `iisutil!PuDbgPrint` at `0x180002d38`
- `iisutil!PuDbgPrint` at `0x180002cf1`
- `iisutil!PuDbgPrint` at `0x180002d38`

## string_xrefs

- `0x180002cea`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180002d31`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180002cd1`: `W3TP: Waiting for threads to drain, sleep 1000\n`
- `0x180002cd8`: `THREAD_MANAGER::DrainThreads`
- `0x180002d1f`: `THREAD_MANAGER::DrainThreads`
- `0x180002d18`: `W3TP: All threads drained\n`

## pseudocode

```c
void __fastcall THREAD_MANAGER::DrainThreads(THREAD_MANAGER *this, void (*a2)(void *), void *a3)
{
  int i; // ebx
  void *v6; // rdx
  unsigned int v7; // edx
  THREAD_MANAGER::THREAD_PARAM *v8; // rcx

  if ( !*((_DWORD *)this + 12) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *((_DWORD *)this + 12) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    SetEvent(*((HANDLE *)this + 12));
    for ( i = *((_DWORD *)this + 19); i >= 0; --i )
      THREAD_POOL_DATA::ThreadPoolStop(a3);
    v6 = (void *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v8 = (THREAD_MANAGER::THREAD_PARAM *)*((_QWORD *)this + 8);
      *((_QWORD *)this + 7) = 0;
      if ( v8 )
      {
        THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(v8, v7);
        *((_QWORD *)this + 8) = 0;
      }
    }
    while ( *((int *)this + 19) > 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          1766,
          "THREAD_MANAGER::DrainThreads",
          "W3TP: Waiting for threads to drain, sleep 1000\n");
      Sleep(0x3E8u);
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1770,
        "THREAD_MANAGER::DrainThreads",
        "W3TP: All threads drained\n");
  }
}

```

## disassembly

```asm
0x180002c34  mov     [rsp+arg_0], rbx
0x180002c39  mov     [rsp+arg_8], rsi
0x180002c3e  push    rdi
0x180002c3f  sub     rsp, 30h
0x180002c43  cmp     dword ptr [rcx+30h], 0
0x180002c47  mov     rsi, r8
0x180002c4a  mov     rdi, rcx
0x180002c4d  jnz     loc_180002D3E
0x180002c53  add     rcx, 8; lpCriticalSection
0x180002c57  call    cs:__imp_EnterCriticalSection
0x180002c5d  lea     rcx, [rdi+8]; lpCriticalSection
0x180002c61  mov     dword ptr [rdi+30h], 1
0x180002c68  call    cs:__imp_LeaveCriticalSection
0x180002c6e  mov     rcx, [rdi+60h]; hEvent
0x180002c72  call    cs:__imp_SetEvent
0x180002c78  mov     ebx, [rdi+4Ch]
0x180002c7b  test    ebx, ebx
0x180002c7d  js      short loc_180002C8C
0x180002c7f  mov     rcx, rsi; void *
0x180002c82  call    ?ThreadPoolStop@THREAD_POOL_DATA@@SAXPEAX@Z; THREAD_POOL_DATA::ThreadPoolStop(void *)
0x180002c87  sub     ebx, 1
0x180002c8a  jns     short loc_180002C7F
0x180002c8c  mov     rdx, [rdi+38h]; Timer
0x180002c90  test    rdx, rdx
0x180002c93  jz      short loc_180002D02
0x180002c95  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180002c99  xor     ecx, ecx; TimerQueue
0x180002c9b  call    cs:__imp_DeleteTimerQueueTimer
0x180002ca1  mov     rcx, [rdi+40h]; this
0x180002ca5  mov     qword ptr [rdi+38h], 0
0x180002cad  test    rcx, rcx
0x180002cb0  jz      short loc_180002D02
0x180002cb2  call    ??_GTHREAD_PARAM@THREAD_MANAGER@@QEAAPEAXI@Z; THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(uint)
0x180002cb7  mov     qword ptr [rdi+40h], 0
0x180002cbf  jmp     short loc_180002D02
0x180002cc1  test    cs:g_dwDebugFlags, 3
0x180002cc8  jz      short loc_180002CF7
0x180002cca  mov     rcx, cs:g_pDebug
0x180002cd1  lea     rax, aW3tpWaitingFor; "W3TP: Waiting for threads to drain, sle"...
0x180002cd8  lea     r9, aThreadManagerD; "THREAD_MANAGER::DrainThreads"
0x180002cdf  mov     [rsp+38h+var_18], rax
0x180002ce4  mov     r8d, 6E6h
0x180002cea  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002cf1  call    cs:__imp_PuDbgPrint
0x180002cf7  mov     ecx, 3E8h; dwMilliseconds
0x180002cfc  call    cs:__imp_Sleep
0x180002d02  cmp     dword ptr [rdi+4Ch], 0
0x180002d06  jg      short loc_180002CC1
0x180002d08  test    cs:g_dwDebugFlags, 3
0x180002d0f  jz      short loc_180002D3E
0x180002d11  mov     rcx, cs:g_pDebug
0x180002d18  lea     rax, aW3tpAllThreads; "W3TP: All threads drained\n"
0x180002d1f  lea     r9, aThreadManagerD; "THREAD_MANAGER::DrainThreads"
0x180002d26  mov     [rsp+38h+var_18], rax
0x180002d2b  mov     r8d, 6EAh
0x180002d31  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002d38  call    cs:__imp_PuDbgPrint
0x180002d3e  mov     rbx, [rsp+38h+arg_0]
0x180002d43  mov     rsi, [rsp+38h+arg_8]
0x180002d48  add     rsp, 30h
0x180002d4c  pop     rdi
0x180002d4d  retn
```
