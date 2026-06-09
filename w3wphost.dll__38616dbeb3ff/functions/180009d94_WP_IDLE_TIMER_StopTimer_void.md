# WP_IDLE_TIMER::StopTimer(void)

- ea: `0x180009d94`
- end: `0x180009e12`
- name: `?StopTimer@WP_IDLE_TIMER@@QEAAXXZ`
- size: `126`
- prototype: `void __fastcall(WP_IDLE_TIMER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007398`
- `0x1800099fc`

## callees

- `0x180009d94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009da7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009da7`
- `iisutil!PuDbgPrint` at `0x180009df7`
- `iisutil!PuDbgPrint` at `0x180009df7`

## string_xrefs

- `0x180009dde`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x180009de5`: `Failed to delete Timer queue.  Win32 = %ld\n`

## pseudocode

```c
void __fastcall WP_IDLE_TIMER::StopTimer(HANDLE *this)
{
  DWORD LastError; // eax

  if ( !DeleteTimerQueueTimer(0, this[2], (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
  {
    LastError = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
      323,
      "WP_IDLE_TIMER::StopTimer",
      "Failed to delete Timer queue.  Win32 = %ld\n",
      LastError);
  }
  this[2] = 0;
}

```

## disassembly

```asm
0x180009d94  push    rbx
0x180009d96  sub     rsp, 30h
0x180009d9a  mov     rdx, [rcx+10h]; Timer
0x180009d9e  mov     rbx, rcx
0x180009da1  xor     ecx, ecx; TimerQueue
0x180009da3  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180009da7  call    cs:__imp_DeleteTimerQueueTimer
0x180009dae  nop     dword ptr [rax+rax+00h]
0x180009db3  test    eax, eax
0x180009db5  jnz     short loc_180009E03
0x180009db7  test    byte ptr cs:g_dwDebugFlags, 3
0x180009dbe  jz      short loc_180009E03
0x180009dc0  call    cs:__imp_GetLastError
0x180009dc7  nop     dword ptr [rax+rax+00h]
0x180009dcc  mov     rcx, cs:g_pDebug
0x180009dd3  lea     r9, aWpIdleTimerSto; "WP_IDLE_TIMER::StopTimer"
0x180009dda  mov     [rsp+38h+var_10], eax
0x180009dde  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009de5  lea     rax, aFailedToDelete_1; "Failed to delete Timer queue.  Win32 = "...
0x180009dec  mov     r8d, 143h
0x180009df2  mov     [rsp+38h+var_18], rax
0x180009df7  call    cs:__imp_PuDbgPrint
0x180009dfe  nop     dword ptr [rax+rax+00h]
0x180009e03  mov     qword ptr [rbx+10h], 0
0x180009e0b  add     rsp, 30h
0x180009e0f  pop     rbx
0x180009e10  retn
```
