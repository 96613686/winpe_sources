# CancelExitWindows

- ea: `0x180005378`
- end: `0x18000546d`
- name: `CancelExitWindows`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007e90`
- `0x18000acac`

## callees

- `0x180005378`

## import_xrefs

- `ntdll!NtClearEvent` at `0x1800053d2`
- `ntdll!NtClearEvent` at `0x180005438`
- `ntdll!NtClearEvent` at `0x1800053d2`
- `ntdll!NtClearEvent` at `0x180005438`
- `ntdll!NtSetEvent` at `0x1800053e7`
- `ntdll!NtSetEvent` at `0x1800053e7`
- `ntdll!NtWaitForSingleObject` at `0x1800053ab`
- `ntdll!NtWaitForSingleObject` at `0x180005412`
- `ntdll!NtWaitForSingleObject` at `0x1800053ab`
- `ntdll!NtWaitForSingleObject` at `0x180005412`
- `ntdll!RtlLeaveCriticalSection` at `0x1800053fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180005458`
- `ntdll!RtlLeaveCriticalSection` at `0x1800053fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180005458`
- `ntdll!RtlEnterCriticalSection` at `0x18000538c`
- `ntdll!RtlEnterCriticalSection` at `0x180005425`
- `ntdll!RtlEnterCriticalSection` at `0x18000538c`
- `ntdll!RtlEnterCriticalSection` at `0x180005425`

## pseudocode

```c
__int64 CancelExitWindows()
{
  unsigned int v0; // ebx
  union _LARGE_INTEGER Timeout; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  Timeout.QuadPart = 0;
  RtlEnterCriticalSection(&gcsUserSrv);
  Timeout.QuadPart = 0;
  if ( NtWaitForSingleObject(gheventCancel, 0, &Timeout) )
  {
    if ( !gdwThreadEndSession
      || (NtClearEvent(gheventCancelled),
          NtSetEvent(gheventCancel, 0),
          RtlLeaveCriticalSection(&gcsUserSrv),
          NtWaitForSingleObject(gheventCancelled, 0, 0),
          RtlEnterCriticalSection(&gcsUserSrv),
          NtClearEvent(gheventCancel),
          !gdwThreadEndSession) )
    {
      v0 = 1;
    }
  }
  RtlLeaveCriticalSection(&gcsUserSrv);
  return v0;
}

```

## disassembly

```asm
0x180005378  push    rbx
0x18000537a  sub     rsp, 20h
0x18000537e  xor     ebx, ebx
0x180005380  lea     rcx, gcsUserSrv; CriticalSection
0x180005387  mov     qword ptr [rsp+28h+Timeout], rbx
0x18000538c  call    cs:__imp_RtlEnterCriticalSection
0x180005393  nop     dword ptr [rax+rax+00h]
0x180005398  mov     rcx, cs:gheventCancel; Handle
0x18000539f  lea     r8, [rsp+28h+Timeout]; Timeout
0x1800053a4  xor     edx, edx; Alertable
0x1800053a6  mov     qword ptr [rsp+28h+Timeout], rbx
0x1800053ab  call    cs:__imp_NtWaitForSingleObject
0x1800053b2  nop     dword ptr [rax+rax+00h]
0x1800053b7  test    eax, eax
0x1800053b9  jz      loc_180005451
0x1800053bf  cmp     cs:gdwThreadEndSession, ebx
0x1800053c5  jz      loc_18000544C
0x1800053cb  mov     rcx, cs:gheventCancelled; EventHandle
0x1800053d2  call    cs:__imp_NtClearEvent
0x1800053d9  nop     dword ptr [rax+rax+00h]
0x1800053de  mov     rcx, cs:gheventCancel; EventHandle
0x1800053e5  xor     edx, edx; PreviousState
0x1800053e7  call    cs:__imp_NtSetEvent
0x1800053ee  nop     dword ptr [rax+rax+00h]
0x1800053f3  lea     rcx, gcsUserSrv; CriticalSection
0x1800053fa  call    cs:__imp_RtlLeaveCriticalSection
0x180005401  nop     dword ptr [rax+rax+00h]
0x180005406  mov     rcx, cs:gheventCancelled; Handle
0x18000540d  xor     r8d, r8d; Timeout
0x180005410  xor     edx, edx; Alertable
0x180005412  call    cs:__imp_NtWaitForSingleObject
0x180005419  nop     dword ptr [rax+rax+00h]
0x18000541e  lea     rcx, gcsUserSrv; CriticalSection
0x180005425  call    cs:__imp_RtlEnterCriticalSection
0x18000542c  nop     dword ptr [rax+rax+00h]
0x180005431  mov     rcx, cs:gheventCancel; EventHandle
0x180005438  call    cs:__imp_NtClearEvent
0x18000543f  nop     dword ptr [rax+rax+00h]
0x180005444  cmp     cs:gdwThreadEndSession, ebx
0x18000544a  jnz     short loc_180005451
0x18000544c  mov     ebx, 1
0x180005451  lea     rcx, gcsUserSrv; CriticalSection
0x180005458  call    cs:__imp_RtlLeaveCriticalSection
0x18000545f  nop     dword ptr [rax+rax+00h]
0x180005464  mov     eax, ebx
0x180005466  add     rsp, 20h
0x18000546a  pop     rbx
0x18000546b  retn
```
