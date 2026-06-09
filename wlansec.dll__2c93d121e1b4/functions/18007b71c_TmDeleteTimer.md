# TmDeleteTimer

- ea: `0x18007b71c`
- end: `0x18007b7ef`
- name: `TmDeleteTimer`
- size: `211`
- prototype: `__int64 __fastcall(HANDLE Timer)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18007c5d0`
- `0x18007c7c4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b71c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b77a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b77a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007b76a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007b76a`

## pseudocode

```c
__int64 __fastcall TmDeleteTimer(HANDLE Timer)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  PVOID *v4; // rcx

  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids);
  if ( DeleteTimerQueueTimer(g_hTimerQueue, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    goto LABEL_8;
  LastError = GetLastError();
  v2 = LastError;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, LastError);
LABEL_8:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 27, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18007b71c  mov     [rsp+arg_0], rbx
0x18007b721  mov     [rsp+arg_8], rsi
0x18007b726  push    rdi
0x18007b727  sub     rsp, 20h
0x18007b72b  mov     rdi, rcx
0x18007b72e  xor     ebx, ebx
0x18007b730  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b737  lea     rsi, WPP_GLOBAL_Control
0x18007b73e  cmp     rcx, rsi
0x18007b741  jz      short loc_18007B75C
0x18007b743  test    byte ptr [rcx+1Ch], 1
0x18007b747  jz      short loc_18007B75C
0x18007b749  mov     rcx, [rcx+10h]
0x18007b74d  lea     edx, [rbx+19h]
0x18007b750  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b757  call    WPP_SF_
0x18007b75c  mov     rcx, cs:g_hTimerQueue; TimerQueue
0x18007b763  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18007b767  mov     rdx, rdi; Timer
0x18007b76a  call    cs:__imp_DeleteTimerQueueTimer
0x18007b771  nop     dword ptr [rax+rax+00h]
0x18007b776  test    eax, eax
0x18007b778  jnz     short loc_18007B7B2
0x18007b77a  call    cs:__imp_GetLastError
0x18007b781  nop     dword ptr [rax+rax+00h]
0x18007b786  mov     ebx, eax
0x18007b788  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b78f  cmp     rcx, rsi
0x18007b792  jz      short loc_18007B7DC
0x18007b794  test    byte ptr [rcx+1Ch], 2
0x18007b798  jz      short loc_18007B7B9
0x18007b79a  mov     rcx, [rcx+10h]
0x18007b79e  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b7a5  mov     edx, 1Ah
0x18007b7aa  mov     r9d, eax
0x18007b7ad  call    WPP_SF_d
0x18007b7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7b9  cmp     rcx, rsi
0x18007b7bc  jz      short loc_18007B7DC
0x18007b7be  test    byte ptr [rcx+1Ch], 1
0x18007b7c2  jz      short loc_18007B7DC
0x18007b7c4  mov     rcx, [rcx+10h]
0x18007b7c8  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b7cf  mov     edx, 1Bh
0x18007b7d4  mov     r9d, ebx
0x18007b7d7  call    WPP_SF_d
0x18007b7dc  mov     rsi, [rsp+28h+arg_8]
0x18007b7e1  mov     eax, ebx
0x18007b7e3  mov     rbx, [rsp+28h+arg_0]
0x18007b7e8  add     rsp, 20h
0x18007b7ec  pop     rdi
0x18007b7ed  retn
```
