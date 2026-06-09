# WP_RECYCLER::TerminateScheduleBased(void)

- ea: `0x180001fd4`
- end: `0x18000208a`
- name: `?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ`
- size: `182`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800090e4`
- `0x180009640`

## callees

- `0x180001fd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000207e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fdd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180001ff9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180001ff9`
- `iisutil!PuDbgPrint` at `0x180002055`
- `iisutil!PuDbgPrint` at `0x180002055`

## string_xrefs

- `0x18000203c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180002043`: `failed to call DeleteTimerQueueEx(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateScheduleBased(struct _RTL_CRITICAL_SECTION *this)
{
  void *SpinCount; // rcx
  signed int LastError; // eax

  EnterCriticalSection(this);
  SpinCount = (void *)this[3].SpinCount;
  if ( SpinCount )
  {
    if ( !DeleteTimerQueueEx(SpinCount, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        475,
        "WP_RECYCLER::TerminateScheduleBased",
        "failed to call DeleteTimerQueueEx(): hr=0x%x\n",
        LastError);
    }
    this[3].SpinCount = 0;
  }
  LODWORD(this[4].DebugInfo) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001fd4  push    rbx
0x180001fd6  sub     rsp, 30h
0x180001fda  mov     rbx, rcx
0x180001fdd  call    cs:__imp_EnterCriticalSection
0x180001fe4  nop     dword ptr [rax+rax+00h]
0x180001fe9  mov     rcx, [rbx+98h]; TimerQueue
0x180001ff0  test    rcx, rcx
0x180001ff3  jz      short loc_18000206C
0x180001ff5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001ff9  call    cs:__imp_DeleteTimerQueueEx
0x180002000  nop     dword ptr [rax+rax+00h]
0x180002005  test    eax, eax
0x180002007  jnz     short loc_180002061
0x180002009  test    byte ptr cs:g_dwDebugFlags, 3
0x180002010  jz      short loc_180002061
0x180002012  call    cs:__imp_GetLastError
0x180002019  nop     dword ptr [rax+rax+00h]
0x18000201e  test    eax, eax
0x180002020  jle     short loc_18000202A
0x180002022  movzx   eax, ax
0x180002025  or      eax, 80070000h
0x18000202a  mov     rcx, cs:g_pDebug
0x180002031  lea     r9, aWpRecyclerTerm; "WP_RECYCLER::TerminateScheduleBased"
0x180002038  mov     [rsp+38h+var_10], eax
0x18000203c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002043  lea     rax, aFailedToCallDe_0; "failed to call DeleteTimerQueueEx(): hr"...
0x18000204a  mov     r8d, 1DBh
0x180002050  mov     [rsp+38h+var_18], rax
0x180002055  call    cs:__imp_PuDbgPrint
0x18000205c  nop     dword ptr [rax+rax+00h]
0x180002061  mov     qword ptr [rbx+98h], 0
0x18000206c  mov     rcx, rbx
0x18000206f  mov     dword ptr [rbx+0A0h], 0
0x180002079  add     rsp, 30h
0x18000207d  pop     rbx
0x18000207e  jmp     cs:__imp_LeaveCriticalSection
```
