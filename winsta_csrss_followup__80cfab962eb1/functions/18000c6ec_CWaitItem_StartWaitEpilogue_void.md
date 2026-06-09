# CWaitItem::StartWaitEpilogue(void)

- ea: `0x18000c6ec`
- end: `0x18000c7d8`
- name: `?StartWaitEpilogue@CWaitItem@@IEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b8d4`
- `0x18000c510`

## callees

- `0x18000c6ec`
- `0x18000c7e0`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000c7c7`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000c7c7`
- `ntdll!NtQuerySystemTime` at `0x18000c724`
- `ntdll!NtQuerySystemTime` at `0x18000c724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c797`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c764`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c764`

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
0x18000c6ec  mov     [rsp+arg_8], rbx
0x18000c6f1  mov     [rsp+arg_10], rsi
0x18000c6f6  push    rdi
0x18000c6f7  sub     rsp, 20h
0x18000c6fb  mov     esi, 1
0x18000c700  mov     rbx, rcx
0x18000c703  mov     eax, esi
0x18000c705  lock xadd [rcx+0CCh], eax
0x18000c70d  add     eax, esi
0x18000c70f  add     rcx, 0D8h
0x18000c716  and     eax, 0Fh
0x18000c719  lea     rdi, [rax+rax*4]
0x18000c71d  shl     rdi, 4
0x18000c721  add     rcx, rdi; SystemTime
0x18000c724  call    cs:__imp_NtQuerySystemTime
0x18000c72b  nop     dword ptr [rax+rax+00h]
0x18000c730  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, esi; int g_bCaptureObjectStackTrace
0x18000c736  mov     [rsp+28h+BackTraceHash], 0
0x18000c73e  jz      short loc_18000C7B1
0x18000c740  mov     eax, [rbx+0C8h]
0x18000c746  xor     r9d, r9d; lpName
0x18000c749  mov     [rdi+rbx+0D0h], eax
0x18000c750  xor     r8d, r8d; bInitialState
0x18000c753  mov     [rbx+0C8h], esi
0x18000c759  xor     edx, edx; bManualReset
0x18000c75b  xor     ecx, ecx; lpEventAttributes
0x18000c75d  mov     [rdi+rbx+0D4h], esi
0x18000c764  call    cs:__imp_CreateEventW
0x18000c76b  nop     dword ptr [rax+rax+00h]
0x18000c770  mov     [rbx+5D8h], rax
0x18000c777  test    rax, rax
0x18000c77a  jz      short loc_18000C797
0x18000c77c  mov     edx, esi; int
0x18000c77e  mov     rcx, rbx; Context
0x18000c781  call    ?IssueWait@CWaitItem@@IEAAJH@Z; CWaitItem::IssueWait(int)
0x18000c786  mov     rbx, [rsp+28h+arg_8]
0x18000c78b  mov     rsi, [rsp+28h+arg_10]
0x18000c790  add     rsp, 20h
0x18000c794  pop     rdi
0x18000c795  retn
0x18000c797  call    cs:__imp_GetLastError
0x18000c79e  nop     dword ptr [rax+rax+00h]
0x18000c7a3  test    eax, eax
0x18000c7a5  jle     short loc_18000C786
0x18000c7a7  movzx   eax, ax
0x18000c7aa  or      eax, 80070000h
0x18000c7af  jmp     short loc_18000C786
0x18000c7b1  lea     r8, [rbx+0E0h]
0x18000c7b8  mov     edx, 8; FramesToCapture
0x18000c7bd  add     r8, rdi; BackTrace
0x18000c7c0  lea     r9, [rsp+28h+BackTraceHash]; BackTraceHash
0x18000c7c5  mov     ecx, esi; FramesToSkip
0x18000c7c7  call    cs:__imp_RtlCaptureStackBackTrace
0x18000c7ce  nop     dword ptr [rax+rax+00h]
0x18000c7d3  jmp     loc_18000C740
```
