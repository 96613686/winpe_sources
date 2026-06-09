# ShutdownResolverContextStart

- ea: `0x180011a70`
- end: `0x180011b54`
- name: `ShutdownResolverContextStart`
- size: `228`
- prototype: `__int64 __fastcall(PVOID Reserved6)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a1c0`

## callees

- `0x180011a70`

## import_xrefs

- `ntdll!RtlCreateUserThread` at `0x180011b36`
- `ntdll!RtlCreateUserThread` at `0x180011b36`
- `ntdll!NtCreateEvent` at `0x180011a90`
- `ntdll!NtCreateEvent` at `0x180011aba`
- `ntdll!NtCreateEvent` at `0x180011ae3`
- `ntdll!NtCreateEvent` at `0x180011a90`
- `ntdll!NtCreateEvent` at `0x180011aba`
- `ntdll!NtCreateEvent` at `0x180011ae3`

## pseudocode

```c
__int64 __fastcall ShutdownResolverContextStart(void **Reserved6)
{
  NTSTATUS Event; // edx

  Event = NtCreateEvent(Reserved6 + 8, 0x1F0003u, 0, SynchronizationEvent, 0);
  if ( Event >= 0 )
  {
    Event = NtCreateEvent(Reserved6 + 10, 0x1F0003u, 0, NotificationEvent, 0);
    if ( Event >= 0 )
    {
      Event = NtCreateEvent(Reserved6 + 9, 0x1F0003u, 0, SynchronizationEvent, 0);
      if ( Event >= 0 )
      {
        Event = RtlCreateUserThread(
                  (PVOID)0xFFFFFFFFFFFFFFFFLL,
                  0,
                  0,
                  0,
                  0,
                  0,
                  ResolverContextThread,
                  Reserved6,
                  Reserved6 + 11,
                  0);
        if ( Event >= 0 )
          return 0;
      }
    }
  }
  return (unsigned int)Event;
}

```

## disassembly

```asm
0x180011a70  push    rbx
0x180011a72  sub     rsp, 50h
0x180011a76  mov     rbx, rcx
0x180011a79  mov     [rsp+58h+InitialState], 0; InitialState
0x180011a7e  add     rcx, 40h ; '@'; EventHandle
0x180011a82  mov     r9d, 1; EventType
0x180011a88  xor     r8d, r8d; ObjectAttributes
0x180011a8b  mov     edx, 1F0003h; DesiredAccess
0x180011a90  call    cs:__imp_NtCreateEvent
0x180011a97  nop     dword ptr [rax+rax+00h]
0x180011a9c  mov     edx, eax
0x180011a9e  test    eax, eax
0x180011aa0  js      loc_180011B4B
0x180011aa6  lea     rcx, [rbx+50h]; EventHandle
0x180011aaa  mov     [rsp+58h+InitialState], 0; InitialState
0x180011aaf  xor     r9d, r9d; EventType
0x180011ab2  xor     r8d, r8d; ObjectAttributes
0x180011ab5  mov     edx, 1F0003h; DesiredAccess
0x180011aba  call    cs:__imp_NtCreateEvent
0x180011ac1  nop     dword ptr [rax+rax+00h]
0x180011ac6  mov     edx, eax
0x180011ac8  test    eax, eax
0x180011aca  js      short loc_180011B4B
0x180011acc  lea     rcx, [rbx+48h]; EventHandle
0x180011ad0  mov     [rsp+58h+InitialState], 0; InitialState
0x180011ad5  mov     r9d, 1; EventType
0x180011adb  xor     r8d, r8d; ObjectAttributes
0x180011ade  mov     edx, 1F0003h; DesiredAccess
0x180011ae3  call    cs:__imp_NtCreateEvent
0x180011aea  nop     dword ptr [rax+rax+00h]
0x180011aef  mov     edx, eax
0x180011af1  test    eax, eax
0x180011af3  js      short loc_180011B4B
0x180011af5  mov     [rsp+58h+Reserved8], 0; Reserved8
0x180011afe  lea     rax, [rbx+58h]
0x180011b02  mov     [rsp+58h+Reserved7], rax; Reserved7
0x180011b07  xor     r9d, r9d; Reserved2
0x180011b0a  mov     [rsp+58h+Reserved6], rbx; Reserved6
0x180011b0f  lea     rax, ResolverContextThread
0x180011b16  mov     [rsp+58h+Reserved5], rax; Reserved5
0x180011b1b  xor     r8d, r8d; Reserved1
0x180011b1e  mov     [rsp+58h+Reserved4], 0; Reserved4
0x180011b27  xor     edx, edx; OutThreadHandle
0x180011b29  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180011b2d  mov     qword ptr [rsp+58h+InitialState], 0; Reserved3
0x180011b36  call    cs:__imp_RtlCreateUserThread
0x180011b3d  nop     dword ptr [rax+rax+00h]
0x180011b42  mov     edx, eax
0x180011b44  xor     eax, eax
0x180011b46  test    edx, edx
0x180011b48  cmovns  edx, eax
0x180011b4b  mov     eax, edx
0x180011b4d  add     rsp, 50h
0x180011b51  pop     rbx
0x180011b52  retn
```
