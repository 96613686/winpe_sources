# WP_RECYCLER::TerminateTimeBased(void)

- ea: `0x180001e24`
- end: `0x180001ebf`
- name: `?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008b1c`
- `0x180008c60`

## callees

- `0x180001e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001eb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e2d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e45`
- `iisutil!PuDbgPrint` at `0x180001e95`
- `iisutil!PuDbgPrint` at `0x180001e95`

## string_xrefs

- `0x180001e7c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180001e83`: `failed to call DeleteTimerQueueTimer(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateTimeBased(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rdx

  EnterCriticalSection(this);
  OwningThread = this[3].OwningThread;
  if ( OwningThread )
  {
    if ( !DeleteTimerQueueTimer(0, OwningThread, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        1159,
        "WP_RECYCLER::TerminateTimeBased",
        "failed to call DeleteTimerQueueTimer(): hr=0x%x\n");
    }
    this[3].OwningThread = 0;
  }
  LODWORD(this[3].LockSemaphore) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001e24  push    rbx
0x180001e26  sub     rsp, 30h
0x180001e2a  mov     rbx, rcx
0x180001e2d  call    cs:__imp_EnterCriticalSection
0x180001e33  mov     rdx, [rbx+88h]; Timer
0x180001e3a  test    rdx, rdx
0x180001e3d  jz      short loc_180001EA6
0x180001e3f  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001e43  xor     ecx, ecx; TimerQueue
0x180001e45  call    cs:__imp_DeleteTimerQueueTimer
0x180001e4b  test    eax, eax
0x180001e4d  jnz     short loc_180001E9B
0x180001e4f  test    byte ptr cs:g_dwDebugFlags, 3
0x180001e56  jz      short loc_180001E9B
0x180001e58  call    cs:__imp_GetLastError
0x180001e5e  test    eax, eax
0x180001e60  jle     short loc_180001E6A
0x180001e62  movzx   eax, ax
0x180001e65  or      eax, 80070000h
0x180001e6a  mov     rcx, cs:g_pDebug
0x180001e71  lea     r9, aWpRecyclerTerm_0; "WP_RECYCLER::TerminateTimeBased"
0x180001e78  mov     [rsp+38h+var_10], eax
0x180001e7c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001e83  lea     rax, aFailedToCallDe; "failed to call DeleteTimerQueueTimer():"...
0x180001e8a  mov     r8d, 487h
0x180001e90  mov     [rsp+38h+var_18], rax
0x180001e95  call    cs:__imp_PuDbgPrint
0x180001e9b  mov     qword ptr [rbx+88h], 0
0x180001ea6  mov     rcx, rbx
0x180001ea9  mov     dword ptr [rbx+90h], 0
0x180001eb3  add     rsp, 30h
0x180001eb7  pop     rbx
0x180001eb8  jmp     cs:__imp_LeaveCriticalSection
```
