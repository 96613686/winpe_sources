# VmsVmNicChannelHandlePause

- ea: `0x140194f28`
- end: `0x140195087`
- name: `VmsVmNicChannelHandlePause`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140196e30`

## callees

- `0x140027a64`
- `0x140066a1c`
- `0x14008497c`
- `0x14012c0e0`
- `0x140194f28`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140195057`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140195057`
- `ntoskrnl!ExRundownCompleted` at `0x14019506a`
- `ntoskrnl!ExRundownCompleted` at `0x14019506a`
- `ntoskrnl!KeReleaseMutex` at `0x140194fa2`
- `ntoskrnl!KeReleaseMutex` at `0x140194fa2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194f62`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194f62`
- `NDIS!NdisMSleep` at `0x140194fb7`
- `NDIS!NdisMSleep` at `0x140194fd1`
- `NDIS!NdisMSleep` at `0x140194fb7`
- `NDIS!NdisMSleep` at `0x140194fd1`

## string_xrefs

- `0x140195009`: `VmsOmNicHeaderGetIncomingPacketCount(&vmNicExt->Nic->NicHeader) == 0`

## pseudocode

```c
void __fastcall VmsVmNicChannelHandlePause(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdx
  int v4; // edx
  struct _EX_RUNDOWN_REF *v5; // rbx

  if ( !*(_WORD *)(a1 + 16) )
  {
    v1 = *(_QWORD *)(a1 + 8);
    v2 = *(_QWORD *)(v1 + 680);
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    if ( *(_DWORD *)(v2 + 1880) == 1 )
    {
      v3 = *(_QWORD *)(v2 + 1888);
      if ( *(_DWORD *)(v3 + 8916) == 1 )
        VmsPDRevokePDAccess(v2, *(_QWORD *)(v3 + 4264), 0);
    }
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    while ( *(_DWORD *)(v1 + 244) )
      NdisMSleep(0x3E8u);
    while ( *(_DWORD *)(v1 + 248) )
      NdisMSleep(0x3E8u);
    if ( (unsigned int)VmsOmpNicHeaderGetPacketCount(*(_QWORD *)(v1 + 680) + 1232LL, 2) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v4,
        19,
        62,
        (__int64)WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids,
        "VmsOmNicHeaderGetIncomingPacketCount(&vmNicExt->Nic->NicHeader) == 0");
      if ( (unsigned int)VmsOmpNicHeaderGetPacketCount(*(_QWORD *)(v1 + 680) + 1232LL, 2) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v5 = *(struct _EX_RUNDOWN_REF **)v1;
    ExWaitForRundownProtectionRelease(v5 + 500616);
    ExRundownCompleted(v5 + 500616);
  }
}

```

## disassembly

```asm
0x140194f28  mov     [rsp+arg_0], rbx
0x140194f2d  mov     [rsp+arg_8], rsi
0x140194f32  push    rdi
0x140194f33  sub     rsp, 30h
0x140194f37  xor     esi, esi
0x140194f39  cmp     [rcx+10h], si
0x140194f3d  jnz     loc_140195076
0x140194f43  mov     rbx, [rcx+8]
0x140194f47  xor     r9d, r9d; Alertable
0x140194f4a  xor     r8d, r8d; WaitMode
0x140194f4d  mov     [rsp+38h+Timeout], rsi; Timeout
0x140194f52  xor     edx, edx; WaitReason
0x140194f54  lea     rcx, VmsOmIoctlMutex; Object
0x140194f5b  mov     rdi, [rbx+2A8h]
0x140194f62  call    cs:__imp_KeWaitForSingleObject
0x140194f69  nop     dword ptr [rax+rax+00h]
0x140194f6e  cmp     dword ptr [rdi+758h], 1
0x140194f75  jnz     short loc_140194F99
0x140194f77  mov     rdx, [rdi+760h]
0x140194f7e  cmp     dword ptr [rdx+22D4h], 1
0x140194f85  jnz     short loc_140194F99
0x140194f87  mov     rdx, [rdx+10A8h]
0x140194f8e  xor     r8d, r8d
0x140194f91  mov     rcx, rdi
0x140194f94  call    VmsPDRevokePDAccess
0x140194f99  xor     edx, edx; Wait
0x140194f9b  lea     rcx, VmsOmIoctlMutex; Mutex
0x140194fa2  call    cs:__imp_KeReleaseMutex
0x140194fa9  nop     dword ptr [rax+rax+00h]
0x140194fae  mov     edi, 3E8h
0x140194fb3  jmp     short loc_140194FC3
0x140194fb5  mov     ecx, edi; MicrosecondsToSleep
0x140194fb7  call    cs:__imp_NdisMSleep
0x140194fbe  nop     dword ptr [rax+rax+00h]
0x140194fc3  mov     eax, [rbx+0F4h]
0x140194fc9  test    eax, eax
0x140194fcb  jnz     short loc_140194FB5
0x140194fcd  jmp     short loc_140194FDD
0x140194fcf  mov     ecx, edi; MicrosecondsToSleep
0x140194fd1  call    cs:__imp_NdisMSleep
0x140194fd8  nop     dword ptr [rax+rax+00h]
0x140194fdd  mov     eax, [rbx+0F8h]
0x140194fe3  test    eax, eax
0x140194fe5  jnz     short loc_140194FCF
0x140194fe7  mov     rcx, [rbx+2A8h]
0x140194fee  lea     edx, [rax+2]
0x140194ff1  mov     edi, 4D0h
0x140194ff6  add     rcx, rdi
0x140194ff9  call    VmsOmpNicHeaderGetPacketCount
0x140194ffe  test    eax, eax
0x140195000  jz      short loc_14019504D
0x140195002  mov     rcx, cs:VmsIfrLog
0x140195009  lea     rax, aVmsomnicheader_0; "VmsOmNicHeaderGetIncomingPacketCount(&v"...
0x140195010  mov     [rsp+38h+var_10], rax
0x140195015  mov     r9d, 3Eh ; '>'
0x14019501b  lea     rax, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140195022  mov     [rsp+38h+Timeout], rax
0x140195027  lea     r8d, [r9-2Bh]
0x14019502b  call    WPP_RECORDER_SF_s
0x140195030  mov     rcx, [rbx+2A8h]
0x140195037  mov     edx, 2
0x14019503c  add     rcx, rdi
0x14019503f  call    VmsOmpNicHeaderGetPacketCount
0x140195044  test    eax, eax
0x140195046  jz      short loc_14019504D
0x140195048  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsOmNicHeaderGetIncomingPacketCount(&vmNicExt->Nic->NicHeader) == 0")
0x14019504d  mov     rbx, [rbx]
0x140195050  lea     rcx, [rbx+3D1C40h]; RunRef
0x140195057  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14019505e  nop     dword ptr [rax+rax+00h]
0x140195063  lea     rcx, [rbx+3D1C40h]; RunRef
0x14019506a  call    cs:__imp_ExRundownCompleted
0x140195071  nop     dword ptr [rax+rax+00h]
0x140195076  mov     rbx, [rsp+38h+arg_0]
0x14019507b  mov     rsi, [rsp+38h+arg_8]
0x140195080  add     rsp, 30h
0x140195084  pop     rdi
0x140195085  retn
```
