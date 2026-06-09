# CWaitItem::StartWaitEpilogue(void)

- ea: `0x1800028a8`
- end: `0x18000297b`
- name: `?StartWaitEpilogue@CWaitItem@@IEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b68`
- `0x1800026e0`

## callees

- `0x1800028a8`
- `0x180002990`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180002970`
- `ntdll!RtlCaptureStackBackTrace` at `0x180002970`
- `ntdll!NtQuerySystemTime` at `0x1800028e0`
- `ntdll!NtQuerySystemTime` at `0x1800028e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002946`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000291a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000291a`

## pseudocode

```c
signed int __fastcall CWaitItem::StartWaitEpilogue(volatile signed __int32 *Context)
{
  __int64 v2; // rdi
  HANDLE EventW; // rax
  signed int result; // eax
  ULONG BackTraceHash; // [rsp+30h] [rbp+8h] BYREF

  v2 = 20LL * (((unsigned __int8)_InterlockedExchangeAdd(Context + 51, 1u) + 1) & 0xF);
  NtQuerySystemTime((PLARGE_INTEGER)&Context[v2 + 54]);
  BackTraceHash = 0;
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 8u, (PVOID *)&Context[v2 + 56], &BackTraceHash);
  Context[v2 + 52] = *((_DWORD *)Context + 50);
  *((_DWORD *)Context + 50) = 1;
  Context[v2 + 53] = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)Context + 187) = EventW;
  if ( EventW )
    return CWaitItem::IssueWait((char *)Context, 1);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800028a8  mov     [rsp+arg_8], rbx
0x1800028ad  mov     [rsp+arg_10], rsi
0x1800028b2  push    rdi
0x1800028b3  sub     rsp, 20h
0x1800028b7  mov     esi, 1
0x1800028bc  mov     rbx, rcx
0x1800028bf  mov     eax, esi
0x1800028c1  lock xadd [rcx+0CCh], eax
0x1800028c9  add     eax, esi
0x1800028cb  add     rcx, 0D8h
0x1800028d2  and     eax, 0Fh
0x1800028d5  lea     rdi, [rax+rax*4]
0x1800028d9  shl     rdi, 4
0x1800028dd  add     rcx, rdi; SystemTime
0x1800028e0  call    cs:__imp_NtQuerySystemTime
0x1800028e6  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, esi; int g_bCaptureObjectStackTrace
0x1800028ec  mov     [rsp+28h+BackTraceHash], 0
0x1800028f4  jz      short loc_18000295A
0x1800028f6  mov     eax, [rbx+0C8h]
0x1800028fc  xor     r9d, r9d; lpName
0x1800028ff  mov     [rdi+rbx+0D0h], eax
0x180002906  xor     r8d, r8d; bInitialState
0x180002909  mov     [rbx+0C8h], esi
0x18000290f  xor     edx, edx; bManualReset
0x180002911  xor     ecx, ecx; lpEventAttributes
0x180002913  mov     [rdi+rbx+0D4h], esi
0x18000291a  call    cs:__imp_CreateEventW
0x180002920  mov     [rbx+5D8h], rax
0x180002927  test    rax, rax
0x18000292a  jz      short loc_180002946
0x18000292c  mov     edx, esi; int
0x18000292e  mov     rcx, rbx; Context
0x180002931  call    ?IssueWait@CWaitItem@@IEAAJH@Z; CWaitItem::IssueWait(int)
0x180002936  mov     rbx, [rsp+28h+arg_8]
0x18000293b  mov     rsi, [rsp+28h+arg_10]
0x180002940  add     rsp, 20h
0x180002944  pop     rdi
0x180002945  retn
0x180002946  call    cs:__imp_GetLastError
0x18000294c  test    eax, eax
0x18000294e  jle     short loc_180002936
0x180002950  movzx   eax, ax
0x180002953  or      eax, 80070000h
0x180002958  jmp     short loc_180002936
0x18000295a  lea     r8, [rbx+0E0h]
0x180002961  mov     edx, 8; FramesToCapture
0x180002966  add     r8, rdi; BackTrace
0x180002969  lea     r9, [rsp+28h+BackTraceHash]; BackTraceHash
0x18000296e  mov     ecx, esi; FramesToSkip
0x180002970  call    cs:__imp_RtlCaptureStackBackTrace
0x180002976  jmp     loc_1800028F6
```
