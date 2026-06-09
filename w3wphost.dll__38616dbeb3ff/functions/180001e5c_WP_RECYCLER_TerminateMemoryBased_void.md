# WP_RECYCLER::TerminateMemoryBased(void)

- ea: `0x180001e5c`
- end: `0x180001f0b`
- name: `?TerminateMemoryBased@WP_RECYCLER@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e9c`
- `0x180009640`

## callees

- `0x180001e5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001eff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e65`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e80`
- `iisutil!PuDbgPrint` at `0x180001edc`
- `iisutil!PuDbgPrint` at `0x180001edc`

## string_xrefs

- `0x180001ec3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180001eca`: `failed to call DeleteTimerQueueTimer(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateMemoryBased(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  signed int LastError; // eax

  EnterCriticalSection(this);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    if ( !DeleteTimerQueueTimer(0, DebugInfo, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        728,
        "WP_RECYCLER::TerminateMemoryBased",
        "failed to call DeleteTimerQueueTimer(): hr=0x%x\n",
        LastError);
    }
    this[1].DebugInfo = 0;
  }
  this[1].LockCount = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001e5c  push    rbx
0x180001e5e  sub     rsp, 30h
0x180001e62  mov     rbx, rcx
0x180001e65  call    cs:__imp_EnterCriticalSection
0x180001e6c  nop     dword ptr [rax+rax+00h]
0x180001e71  mov     rdx, [rbx+28h]; Timer
0x180001e75  test    rdx, rdx
0x180001e78  jz      short loc_180001EF0
0x180001e7a  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001e7e  xor     ecx, ecx; TimerQueue
0x180001e80  call    cs:__imp_DeleteTimerQueueTimer
0x180001e87  nop     dword ptr [rax+rax+00h]
0x180001e8c  test    eax, eax
0x180001e8e  jnz     short loc_180001EE8
0x180001e90  test    byte ptr cs:g_dwDebugFlags, 3
0x180001e97  jz      short loc_180001EE8
0x180001e99  call    cs:__imp_GetLastError
0x180001ea0  nop     dword ptr [rax+rax+00h]
0x180001ea5  test    eax, eax
0x180001ea7  jle     short loc_180001EB1
0x180001ea9  movzx   eax, ax
0x180001eac  or      eax, 80070000h
0x180001eb1  mov     rcx, cs:g_pDebug
0x180001eb8  lea     r9, aWpRecyclerTerm_1; "WP_RECYCLER::TerminateMemoryBased"
0x180001ebf  mov     [rsp+38h+var_10], eax
0x180001ec3  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001eca  lea     rax, aFailedToCallDe; "failed to call DeleteTimerQueueTimer():"...
0x180001ed1  mov     r8d, 2D8h
0x180001ed7  mov     [rsp+38h+var_18], rax
0x180001edc  call    cs:__imp_PuDbgPrint
0x180001ee3  nop     dword ptr [rax+rax+00h]
0x180001ee8  mov     qword ptr [rbx+28h], 0
0x180001ef0  mov     rcx, rbx
0x180001ef3  mov     dword ptr [rbx+30h], 0
0x180001efa  add     rsp, 30h
0x180001efe  pop     rbx
0x180001eff  jmp     cs:__imp_LeaveCriticalSection
```
