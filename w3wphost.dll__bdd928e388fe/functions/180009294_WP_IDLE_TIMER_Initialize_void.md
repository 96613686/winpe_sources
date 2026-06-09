# WP_IDLE_TIMER::Initialize(void)

- ea: `0x180009294`
- end: `0x180009322`
- name: `?Initialize@WP_IDLE_TIMER@@QEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800051dc`

## callees

- `0x180009294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092cb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800092c1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800092c1`
- `iisutil!PuDbgPrint` at `0x180009314`
- `iisutil!PuDbgPrint` at `0x180009314`

## string_xrefs

- `0x18000930d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x1800092f0`: `Failed to create idle timer.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall WP_IDLE_TIMER::Initialize(void **Parameter)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !CreateTimerQueueTimer(Parameter + 2, 0, IdleTimeCheckCallback, Parameter, 0xEA60u, 0xEA60u, 1u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
        127,
        "WP_IDLE_TIMER::Initialize",
        "Failed to create idle timer.  hr = %x\n");
  }
  return v1;
}

```

## disassembly

```asm
0x180009294  push    rbx
0x180009296  sub     rsp, 40h
0x18000929a  mov     eax, 0EA60h
0x18000929f  mov     [rsp+48h+Flags], 1; Flags
0x1800092a7  mov     r9, rcx; Parameter
0x1800092aa  mov     [rsp+48h+Period], eax; Period
0x1800092ae  add     rcx, 10h; phNewTimer
0x1800092b2  mov     [rsp+48h+DueTime], eax; DueTime
0x1800092b6  lea     r8, ?IdleTimeCheckCallback@@YAXPEAXE@Z; Callback
0x1800092bd  xor     edx, edx; TimerQueue
0x1800092bf  xor     ebx, ebx
0x1800092c1  call    cs:__imp_CreateTimerQueueTimer
0x1800092c7  test    eax, eax
0x1800092c9  jnz     short loc_18000931A
0x1800092cb  call    cs:__imp_GetLastError
0x1800092d1  mov     ebx, eax
0x1800092d3  test    eax, eax
0x1800092d5  jle     short loc_1800092E0
0x1800092d7  movzx   ebx, ax
0x1800092da  or      ebx, 80070000h
0x1800092e0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800092e7  jz      short loc_18000931A
0x1800092e9  mov     rcx, cs:g_pDebug
0x1800092f0  lea     rax, aFailedToCreate_2; "Failed to create idle timer.  hr = %x\n"
0x1800092f7  mov     [rsp+48h+Period], ebx
0x1800092fb  lea     r9, aWpIdleTimerIni; "WP_IDLE_TIMER::Initialize"
0x180009302  mov     r8d, 7Fh
0x180009308  mov     qword ptr [rsp+48h+DueTime], rax
0x18000930d  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009314  call    cs:__imp_PuDbgPrint
0x18000931a  mov     eax, ebx
0x18000931c  add     rsp, 40h
0x180009320  pop     rbx
0x180009321  retn
```
