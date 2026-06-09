# WP_RECYCLER::TerminateTimeBased(void)

- ea: `0x180001f14`
- end: `0x180001fcc`
- name: `?TerminateTimeBased@WP_RECYCLER@@QEAAXXZ`
- size: `184`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800094d8`
- `0x180009640`

## callees

- `0x180001f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f1d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001f3b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001f3b`
- `iisutil!PuDbgPrint` at `0x180001f97`
- `iisutil!PuDbgPrint` at `0x180001f97`

## string_xrefs

- `0x180001f7e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180001f85`: `failed to call DeleteTimerQueueTimer(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateTimeBased(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rdx
  signed int LastError; // eax

  EnterCriticalSection(this);
  OwningThread = this[3].OwningThread;
  if ( OwningThread )
  {
    if ( !DeleteTimerQueueTimer(0, OwningThread, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        1159,
        "WP_RECYCLER::TerminateTimeBased",
        "failed to call DeleteTimerQueueTimer(): hr=0x%x\n",
        LastError);
    }
    this[3].OwningThread = 0;
  }
  LODWORD(this[3].LockSemaphore) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001f14  push    rbx
0x180001f16  sub     rsp, 30h
0x180001f1a  mov     rbx, rcx
0x180001f1d  call    cs:__imp_EnterCriticalSection
0x180001f24  nop     dword ptr [rax+rax+00h]
0x180001f29  mov     rdx, [rbx+88h]; Timer
0x180001f30  test    rdx, rdx
0x180001f33  jz      short loc_180001FAE
0x180001f35  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001f39  xor     ecx, ecx; TimerQueue
0x180001f3b  call    cs:__imp_DeleteTimerQueueTimer
0x180001f42  nop     dword ptr [rax+rax+00h]
0x180001f47  test    eax, eax
0x180001f49  jnz     short loc_180001FA3
0x180001f4b  test    byte ptr cs:g_dwDebugFlags, 3
0x180001f52  jz      short loc_180001FA3
0x180001f54  call    cs:__imp_GetLastError
0x180001f5b  nop     dword ptr [rax+rax+00h]
0x180001f60  test    eax, eax
0x180001f62  jle     short loc_180001F6C
0x180001f64  movzx   eax, ax
0x180001f67  or      eax, 80070000h
0x180001f6c  mov     rcx, cs:g_pDebug
0x180001f73  lea     r9, aWpRecyclerTerm_0; "WP_RECYCLER::TerminateTimeBased"
0x180001f7a  mov     [rsp+38h+var_10], eax
0x180001f7e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001f85  lea     rax, aFailedToCallDe; "failed to call DeleteTimerQueueTimer():"...
0x180001f8c  mov     r8d, 487h
0x180001f92  mov     [rsp+38h+var_18], rax
0x180001f97  call    cs:__imp_PuDbgPrint
0x180001f9e  nop     dword ptr [rax+rax+00h]
0x180001fa3  mov     qword ptr [rbx+88h], 0
0x180001fae  mov     rcx, rbx
0x180001fb1  mov     dword ptr [rbx+90h], 0
0x180001fbb  add     rsp, 30h
0x180001fbf  pop     rbx
0x180001fc0  jmp     cs:__imp_LeaveCriticalSection
```
