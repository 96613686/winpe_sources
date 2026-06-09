# WP_RECYCLER::TerminateScheduleBased(void)

- ea: `0x180001ec8`
- end: `0x180001f61`
- name: `?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ`
- size: `153`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008798`
- `0x180008c60`

## callees

- `0x180001ec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ed1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ed1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180001ee7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180001ee7`
- `iisutil!PuDbgPrint` at `0x180001f37`
- `iisutil!PuDbgPrint` at `0x180001f37`

## string_xrefs

- `0x180001f1e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180001f25`: `failed to call DeleteTimerQueueEx(): hr=0x%x\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TerminateScheduleBased(struct _RTL_CRITICAL_SECTION *this)
{
  void *SpinCount; // rcx

  EnterCriticalSection(this);
  SpinCount = (void *)this[3].SpinCount;
  if ( SpinCount )
  {
    if ( !DeleteTimerQueueEx(SpinCount, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
        475,
        "WP_RECYCLER::TerminateScheduleBased",
        "failed to call DeleteTimerQueueEx(): hr=0x%x\n");
    }
    this[3].SpinCount = 0;
  }
  LODWORD(this[4].DebugInfo) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180001ec8  push    rbx
0x180001eca  sub     rsp, 30h
0x180001ece  mov     rbx, rcx
0x180001ed1  call    cs:__imp_EnterCriticalSection
0x180001ed7  mov     rcx, [rbx+98h]; TimerQueue
0x180001ede  test    rcx, rcx
0x180001ee1  jz      short loc_180001F48
0x180001ee3  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001ee7  call    cs:__imp_DeleteTimerQueueEx
0x180001eed  test    eax, eax
0x180001eef  jnz     short loc_180001F3D
0x180001ef1  test    byte ptr cs:g_dwDebugFlags, 3
0x180001ef8  jz      short loc_180001F3D
0x180001efa  call    cs:__imp_GetLastError
0x180001f00  test    eax, eax
0x180001f02  jle     short loc_180001F0C
0x180001f04  movzx   eax, ax
0x180001f07  or      eax, 80070000h
0x180001f0c  mov     rcx, cs:g_pDebug
0x180001f13  lea     r9, aWpRecyclerTerm; "WP_RECYCLER::TerminateScheduleBased"
0x180001f1a  mov     [rsp+38h+var_10], eax
0x180001f1e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001f25  lea     rax, aFailedToCallDe_0; "failed to call DeleteTimerQueueEx(): hr"...
0x180001f2c  mov     r8d, 1DBh
0x180001f32  mov     [rsp+38h+var_18], rax
0x180001f37  call    cs:__imp_PuDbgPrint
0x180001f3d  mov     qword ptr [rbx+98h], 0
0x180001f48  mov     rcx, rbx
0x180001f4b  mov     dword ptr [rbx+0A0h], 0
0x180001f55  add     rsp, 30h
0x180001f59  pop     rbx
0x180001f5a  jmp     cs:__imp_LeaveCriticalSection
```
