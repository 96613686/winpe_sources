# myStartTimerQueueTimer(void *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)

- ea: `0x18002b7b0`
- end: `0x18002b84a`
- name: `?myStartTimerQueueTimer@@YAJPEAX0P6AX0E@Z0KKK@Z`
- size: `154`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, void *@<rdx>, void (*)(void *, unsigned __int8)@<r8>, void *@<r9>, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010748`
- `0x18002522c`
- `0x1800301f8`
- `0x180039100`

## callees

- `0x18002b7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b80c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b80c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b7c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b826`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002b7f7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002b7f7`

## pseudocode

```c
__int64 __fastcall myStartTimerQueueTimer(
        LPCRITICAL_SECTION lpCriticalSection,
        void *a2,
        void (*a3)(void *, unsigned __int8),
        void *a4,
        DWORD DueTime,
        DWORD Period)
{
  unsigned int v8; // edi
  signed int LastError; // eax

  EnterCriticalSection(lpCriticalSection);
  if ( lpCriticalSection[1].DebugInfo )
  {
    v8 = -2147023649;
  }
  else if ( CreateTimerQueueTimer((PHANDLE)&lpCriticalSection[1].DebugInfo, 0, a3, 0, DueTime, Period, 0) )
  {
    v8 = 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x18002b7b0  mov     [rsp+arg_0], rbx
0x18002b7b5  push    rdi
0x18002b7b6  sub     rsp, 40h
0x18002b7ba  mov     rdi, r8
0x18002b7bd  mov     rbx, rcx
0x18002b7c0  call    cs:__imp_EnterCriticalSection
0x18002b7c7  nop     dword ptr [rax+rax+00h]
0x18002b7cc  cmp     qword ptr [rbx+28h], 0
0x18002b7d1  lea     rcx, [rbx+28h]; phNewTimer
0x18002b7d5  jnz     short loc_18002B843
0x18002b7d7  mov     eax, [rsp+48h+arg_28]
0x18002b7db  xor     r9d, r9d; Parameter
0x18002b7de  mov     [rsp+48h+Flags], 0; Flags
0x18002b7e6  mov     r8, rdi; Callback
0x18002b7e9  mov     [rsp+48h+Period], eax; Period
0x18002b7ed  xor     edx, edx; TimerQueue
0x18002b7ef  mov     eax, [rsp+48h+arg_20]
0x18002b7f3  mov     [rsp+48h+DueTime], eax; DueTime
0x18002b7f7  call    cs:__imp_CreateTimerQueueTimer
0x18002b7fe  nop     dword ptr [rax+rax+00h]
0x18002b803  test    eax, eax
0x18002b805  jz      short loc_18002B826
0x18002b807  xor     edi, edi
0x18002b809  mov     rcx, rbx; lpCriticalSection
0x18002b80c  call    cs:__imp_LeaveCriticalSection
0x18002b813  nop     dword ptr [rax+rax+00h]
0x18002b818  mov     rbx, [rsp+48h+arg_0]
0x18002b81d  mov     eax, edi
0x18002b81f  add     rsp, 40h
0x18002b823  pop     rdi
0x18002b824  retn
0x18002b826  call    cs:__imp_GetLastError
0x18002b82d  nop     dword ptr [rax+rax+00h]
0x18002b832  mov     edi, eax
0x18002b834  test    eax, eax
0x18002b836  jle     short loc_18002B809
0x18002b838  movzx   edi, ax
0x18002b83b  or      edi, 80070000h
0x18002b841  jmp     short loc_18002B809
0x18002b843  mov     edi, 800704DFh
0x18002b848  jmp     short loc_18002B809
```
