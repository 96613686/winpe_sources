# WinStationAPIInit

- ea: `0x180010c30`
- end: `0x180010d66`
- name: `WinStationAPIInit`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800046b0`

## callees

- `0x18000ef7c`
- `0x180010c30`

## import_xrefs

- `KERNELBASE!WTSGetServiceSessionId` at `0x180010c70`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180010c70`
- `ntdll!NtSetInformationThread` at `0x180010d31`
- `ntdll!NtSetInformationThread` at `0x180010d31`
- `ntdll!NtResumeThread` at `0x180010d49`
- `ntdll!NtResumeThread` at `0x180010d49`
- `ntdll!RtlCreateUserThread` at `0x180010cef`
- `ntdll!RtlCreateUserThread` at `0x180010cef`
- `CSRSRV!CsrAddStaticServerThread` at `0x180010d0c`
- `CSRSRV!CsrAddStaticServerThread` at `0x180010d0c`

## pseudocode

```c
__int64 WinStationAPIInit()
{
  int v0; // eax
  NTSTATUS ready; // ebx
  void *v2; // r8
  __int128 Reserved8; // [rsp+50h] [rbp-10h] BYREF
  int ThreadInformation; // [rsp+70h] [rbp+10h] BYREF
  HANDLE ThreadHandle; // [rsp+78h] [rbp+18h] BYREF
  PVOID EventHandle; // [rsp+80h] [rbp+20h] BYREF

  ThreadHandle = 0;
  Reserved8 = 0;
  EventHandle = 0;
  ThreadInformation = 0;
  gSessionId = NtCurrentPeb()->SessionId;
  v0 = WTSGetServiceSessionId();
  ghSwDevice = 0;
  gServiceSessionId = v0;
  gRelatedActivityId = 0;
  ready = CreateTermSrvReadyEvent(&EventHandle);
  if ( ready >= 0 )
  {
    LOBYTE(v2) = 1;
    ready = RtlCreateUserThread(
              (PVOID)0xFFFFFFFFFFFFFFFFLL,
              0,
              v2,
              0,
              0,
              0,
              TerminalServerRequestThread,
              EventHandle,
              &ThreadHandle,
              &Reserved8);
    if ( ready >= 0 )
    {
      CsrAddStaticServerThread(ThreadHandle, &Reserved8, 0);
      ThreadInformation = 2;
      ready = NtSetInformationThread(ThreadHandle, ThreadBasePriority, &ThreadInformation, 4u);
      if ( ready >= 0 )
        NtResumeThread(ThreadHandle, 0);
    }
  }
  return (unsigned int)ready;
}

```

## disassembly

```asm
0x180010c30  mov     [rsp-8+arg_18], rbx
0x180010c35  push    rbp
0x180010c36  mov     rbp, rsp
0x180010c39  sub     rsp, 60h
0x180010c3d  mov     [rbp+ThreadHandle], 0
0x180010c45  xorps   xmm0, xmm0
0x180010c48  movups  [rbp+var_10], xmm0
0x180010c4c  mov     [rbp+EventHandle], 0
0x180010c54  mov     [rbp+ThreadInformation], 0
0x180010c5b  mov     rax, gs:60h
0x180010c64  mov     ecx, [rax+2C0h]
0x180010c6a  mov     cs:gSessionId, ecx
0x180010c70  call    cs:__imp_WTSGetServiceSessionId
0x180010c77  nop     dword ptr [rax+rax+00h]
0x180010c7c  xorps   xmm0, xmm0
0x180010c7f  mov     cs:ghSwDevice, 0
0x180010c8a  lea     rcx, [rbp+EventHandle]; EventHandle
0x180010c8e  mov     cs:gServiceSessionId, eax
0x180010c94  movups  cs:gRelatedActivityId, xmm0
0x180010c9b  call    CreateTermSrvReadyEvent
0x180010ca0  mov     ebx, eax
0x180010ca2  test    eax, eax
0x180010ca4  js      loc_180010D55
0x180010caa  lea     rax, [rbp+var_10]
0x180010cae  xor     r9d, r9d; Reserved2
0x180010cb1  mov     [rsp+60h+Reserved8], rax; Reserved8
0x180010cb6  mov     r8b, 1; Reserved1
0x180010cb9  lea     rax, [rbp+ThreadHandle]
0x180010cbd  xor     edx, edx; OutThreadHandle
0x180010cbf  mov     [rsp+60h+Reserved7], rax; Reserved7
0x180010cc4  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180010cc8  mov     rax, [rbp+EventHandle]
0x180010ccc  mov     [rsp+60h+Reserved6], rax; Reserved6
0x180010cd1  lea     rax, TerminalServerRequestThread
0x180010cd8  mov     [rsp+60h+Reserved5], rax; Reserved5
0x180010cdd  mov     [rsp+60h+Reserved4], 0; Reserved4
0x180010ce6  mov     [rsp+60h+Reserved3], 0; Reserved3
0x180010cef  call    cs:__imp_RtlCreateUserThread
0x180010cf6  nop     dword ptr [rax+rax+00h]
0x180010cfb  mov     ebx, eax
0x180010cfd  test    eax, eax
0x180010cff  js      short loc_180010D55
0x180010d01  mov     rcx, [rbp+ThreadHandle]
0x180010d05  lea     rdx, [rbp+var_10]
0x180010d09  xor     r8d, r8d
0x180010d0c  call    cs:__imp_CsrAddStaticServerThread
0x180010d13  nop     dword ptr [rax+rax+00h]
0x180010d18  mov     rcx, [rbp+ThreadHandle]; ThreadHandle
0x180010d1c  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180010d20  mov     r9d, 4; ThreadInformationLength
0x180010d26  mov     [rbp+ThreadInformation], 2
0x180010d2d  lea     edx, [r9-1]; ThreadInformationClass
0x180010d31  call    cs:__imp_NtSetInformationThread
0x180010d38  nop     dword ptr [rax+rax+00h]
0x180010d3d  mov     ebx, eax
0x180010d3f  test    eax, eax
0x180010d41  js      short loc_180010D55
0x180010d43  mov     rcx, [rbp+ThreadHandle]; ThreadHandle
0x180010d47  xor     edx, edx; SuspendCount
0x180010d49  call    cs:__imp_NtResumeThread
0x180010d50  nop     dword ptr [rax+rax+00h]
0x180010d55  mov     eax, ebx
0x180010d57  mov     rbx, [rsp+60h+arg_18]
0x180010d5f  add     rsp, 60h
0x180010d63  pop     rbp
0x180010d64  retn
```
