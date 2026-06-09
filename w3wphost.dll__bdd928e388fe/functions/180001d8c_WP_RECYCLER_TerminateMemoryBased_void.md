# WP_RECYCLER::TerminateMemoryBased(void)

- ea: `0x180001d8c`
- end: `0x180001e1e`
- name: `?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008588`
- `0x180008c60`

## callees

- `0x180001d8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d95`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001daa`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001daa`
- `iisutil!PuDbgPrint` at `0x180001dfa`
- `iisutil!PuDbgPrint` at `0x180001dfa`

## string_xrefs

- `0x180001de1`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180001de8`: `failed to call DeleteTimerQueueTimer(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateMemoryBased(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx

  EnterCriticalSection(this);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    if ( !DeleteTimerQueueTimer(0, DebugInfo, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        728,
        "WP_RECYCLER::TerminateMemoryBased",
        "failed to call DeleteTimerQueueTimer(): hr=0x%x\n");
    }
    this[1].DebugInfo = 0;
  }
  this[1].LockCount = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001d8c  push    rbx
0x180001d8e  sub     rsp, 30h
0x180001d92  mov     rbx, rcx
0x180001d95  call    cs:__imp_EnterCriticalSection
0x180001d9b  mov     rdx, [rbx+28h]; Timer
0x180001d9f  test    rdx, rdx
0x180001da2  jz      short loc_180001E08
0x180001da4  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001da8  xor     ecx, ecx; TimerQueue
0x180001daa  call    cs:__imp_DeleteTimerQueueTimer
0x180001db0  test    eax, eax
0x180001db2  jnz     short loc_180001E00
0x180001db4  test    byte ptr cs:g_dwDebugFlags, 3
0x180001dbb  jz      short loc_180001E00
0x180001dbd  call    cs:__imp_GetLastError
0x180001dc3  test    eax, eax
0x180001dc5  jle     short loc_180001DCF
0x180001dc7  movzx   eax, ax
0x180001dca  or      eax, 80070000h
0x180001dcf  mov     rcx, cs:g_pDebug
0x180001dd6  lea     r9, aWpRecyclerTerm_1; "WP_RECYCLER::TerminateMemoryBased"
0x180001ddd  mov     [rsp+38h+var_10], eax
0x180001de1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001de8  lea     rax, aFailedToCallDe; "failed to call DeleteTimerQueueTimer():"...
0x180001def  mov     r8d, 2D8h
0x180001df5  mov     [rsp+38h+var_18], rax
0x180001dfa  call    cs:__imp_PuDbgPrint
0x180001e00  mov     qword ptr [rbx+28h], 0
0x180001e08  mov     rcx, rbx
0x180001e0b  mov     dword ptr [rbx+30h], 0
0x180001e12  add     rsp, 30h
0x180001e16  pop     rbx
0x180001e17  jmp     cs:__imp_LeaveCriticalSection
```
