# WP_IDLE_TIMER::Initialize(void)

- ea: `0x180009cec`
- end: `0x180009d8d`
- name: `?Initialize@WP_IDLE_TIMER@@QEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000561c`

## callees

- `0x180009cec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009d19`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009d19`
- `iisutil!PuDbgPrint` at `0x180009d78`
- `iisutil!PuDbgPrint` at `0x180009d78`

## string_xrefs

- `0x180009d71`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`
- `0x180009d54`: `Failed to create idle timer.  hr = %x\n`

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
        "Failed to create idle timer.  hr = %x\n",
        v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180009cec  push    rbx
0x180009cee  sub     rsp, 40h
0x180009cf2  mov     eax, 0EA60h
0x180009cf7  mov     [rsp+48h+Flags], 1; Flags
0x180009cff  mov     r9, rcx; Parameter
0x180009d02  mov     [rsp+48h+Period], eax; Period
0x180009d06  add     rcx, 10h; phNewTimer
0x180009d0a  mov     [rsp+48h+DueTime], eax; DueTime
0x180009d0e  lea     r8, ?IdleTimeCheckCallback@@YAXPEAXE@Z; Callback
0x180009d15  xor     edx, edx; TimerQueue
0x180009d17  xor     ebx, ebx
0x180009d19  call    cs:__imp_CreateTimerQueueTimer
0x180009d20  nop     dword ptr [rax+rax+00h]
0x180009d25  test    eax, eax
0x180009d27  jnz     short loc_180009D84
0x180009d29  call    cs:__imp_GetLastError
0x180009d30  nop     dword ptr [rax+rax+00h]
0x180009d35  mov     ebx, eax
0x180009d37  test    eax, eax
0x180009d39  jle     short loc_180009D44
0x180009d3b  movzx   ebx, ax
0x180009d3e  or      ebx, 80070000h
0x180009d44  test    byte ptr cs:g_dwDebugFlags, 3
0x180009d4b  jz      short loc_180009D84
0x180009d4d  mov     rcx, cs:g_pDebug
0x180009d54  lea     rax, aFailedToCreate_2; "Failed to create idle timer.  hr = %x\n"
0x180009d5b  mov     [rsp+48h+Period], ebx
0x180009d5f  lea     r9, aWpIdleTimerIni; "WP_IDLE_TIMER::Initialize"
0x180009d66  mov     r8d, 7Fh
0x180009d6c  mov     qword ptr [rsp+48h+DueTime], rax
0x180009d71  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009d78  call    cs:__imp_PuDbgPrint
0x180009d7f  nop     dword ptr [rax+rax+00h]
0x180009d84  mov     eax, ebx
0x180009d86  add     rsp, 40h
0x180009d8a  pop     rbx
0x180009d8b  retn
```
