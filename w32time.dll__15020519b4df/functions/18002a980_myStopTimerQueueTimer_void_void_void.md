# myStopTimerQueueTimer(void *,void *,void *)

- ea: `0x18002a980`
- end: `0x18002aa01`
- name: `?myStopTimerQueueTimer@@YAJPEAX00@Z`
- size: `129`
- prototype: `int(void *, void *, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010748`
- `0x18002522c`
- `0x18002a940`

## callees

- `0x18002a980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a993`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9e4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a9ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a9ad`

## pseudocode

```c
__int64 __fastcall myStopTimerQueueTimer(void *a1, struct _RTL_CRITICAL_SECTION *a2, void *a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  unsigned int v6; // edi
  signed int LastError; // eax

  EnterCriticalSection(a2);
  DebugInfo = a2[1].DebugInfo;
  if ( !DebugInfo )
    goto LABEL_4;
  if ( DeleteTimerQueueTimer(0, DebugInfo, a3) )
  {
    a2[1].DebugInfo = 0;
LABEL_4:
    v6 = 0;
    goto LABEL_5;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
  LeaveCriticalSection(a2);
  return v6;
}

```

## disassembly

```asm
0x18002a980  mov     [rsp+arg_0], rbx
0x18002a985  push    rdi
0x18002a986  sub     rsp, 20h
0x18002a98a  mov     rcx, rdx; lpCriticalSection
0x18002a98d  mov     rdi, r8
0x18002a990  mov     rbx, rdx
0x18002a993  call    cs:__imp_EnterCriticalSection
0x18002a99a  nop     dword ptr [rax+rax+00h]
0x18002a99f  mov     rdx, [rbx+28h]; Timer
0x18002a9a3  test    rdx, rdx
0x18002a9a6  jz      short loc_18002A9C5
0x18002a9a8  mov     r8, rdi; CompletionEvent
0x18002a9ab  xor     ecx, ecx; TimerQueue
0x18002a9ad  call    cs:__imp_DeleteTimerQueueTimer
0x18002a9b4  nop     dword ptr [rax+rax+00h]
0x18002a9b9  test    eax, eax
0x18002a9bb  jz      short loc_18002A9E4
0x18002a9bd  mov     qword ptr [rbx+28h], 0
0x18002a9c5  xor     edi, edi
0x18002a9c7  mov     rcx, rbx; lpCriticalSection
0x18002a9ca  call    cs:__imp_LeaveCriticalSection
0x18002a9d1  nop     dword ptr [rax+rax+00h]
0x18002a9d6  mov     rbx, [rsp+28h+arg_0]
0x18002a9db  mov     eax, edi
0x18002a9dd  add     rsp, 20h
0x18002a9e1  pop     rdi
0x18002a9e2  retn
0x18002a9e4  call    cs:__imp_GetLastError
0x18002a9eb  nop     dword ptr [rax+rax+00h]
0x18002a9f0  mov     edi, eax
0x18002a9f2  test    eax, eax
0x18002a9f4  jle     short loc_18002A9C7
0x18002a9f6  movzx   edi, ax
0x18002a9f9  or      edi, 80070000h
0x18002a9ff  jmp     short loc_18002A9C7
```
