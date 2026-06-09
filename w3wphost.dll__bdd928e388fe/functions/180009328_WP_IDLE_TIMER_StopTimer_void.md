# WP_IDLE_TIMER::StopTimer(void)

- ea: `0x180009328`
- end: `0x180009393`
- name: `?StopTimer@WP_IDLE_TIMER@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(WP_IDLE_TIMER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006cd8`
- `0x180008fd4`

## callees

- `0x180009328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000934e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000934e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000933b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000933b`
- `iisutil!PuDbgPrint` at `0x18000937f`
- `iisutil!PuDbgPrint` at `0x18000937f`

## string_xrefs

- `0x180009366`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x18000936d`: `Failed to delete Timer queue.  Win32 = %ld\n`

## pseudocode

```c
void __fastcall WP_IDLE_TIMER::StopTimer(HANDLE *this)
{
  if ( !DeleteTimerQueueTimer(0, this[2], (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
  {
    GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
      323,
      "WP_IDLE_TIMER::StopTimer",
      "Failed to delete Timer queue.  Win32 = %ld\n");
  }
  this[2] = 0;
}

```

## disassembly

```asm
0x180009328  push    rbx
0x18000932a  sub     rsp, 30h
0x18000932e  mov     rdx, [rcx+10h]; Timer
0x180009332  mov     rbx, rcx
0x180009335  xor     ecx, ecx; TimerQueue
0x180009337  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000933b  call    cs:__imp_DeleteTimerQueueTimer
0x180009341  test    eax, eax
0x180009343  jnz     short loc_180009385
0x180009345  test    byte ptr cs:g_dwDebugFlags, 3
0x18000934c  jz      short loc_180009385
0x18000934e  call    cs:__imp_GetLastError
0x180009354  mov     rcx, cs:g_pDebug
0x18000935b  lea     r9, aWpIdleTimerSto; "WP_IDLE_TIMER::StopTimer"
0x180009362  mov     [rsp+38h+var_10], eax
0x180009366  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000936d  lea     rax, aFailedToDelete_1; "Failed to delete Timer queue.  Win32 = "...
0x180009374  mov     r8d, 143h
0x18000937a  mov     [rsp+38h+var_18], rax
0x18000937f  call    cs:__imp_PuDbgPrint
0x180009385  mov     qword ptr [rbx+10h], 0
0x18000938d  add     rsp, 30h
0x180009391  pop     rbx
0x180009392  retn
```
