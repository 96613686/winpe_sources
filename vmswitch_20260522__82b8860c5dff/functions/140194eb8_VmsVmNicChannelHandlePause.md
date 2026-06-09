# VmsVmNicChannelHandlePause

- ea: `0x140194eb8`
- end: `0x140195017`
- name: `VmsVmNicChannelHandlePause`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140196dc0`

## callees

- `0x140027a64`
- `0x140066a1c`
- `0x14008497c`
- `0x14012c070`
- `0x140194eb8`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194fe7`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194fe7`
- `ntoskrnl!ExRundownCompleted` at `0x140194ffa`
- `ntoskrnl!ExRundownCompleted` at `0x140194ffa`
- `ntoskrnl!KeReleaseMutex` at `0x140194f32`
- `ntoskrnl!KeReleaseMutex` at `0x140194f32`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194ef2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194ef2`
- `NDIS!NdisMSleep` at `0x140194f47`
- `NDIS!NdisMSleep` at `0x140194f61`
- `NDIS!NdisMSleep` at `0x140194f47`
- `NDIS!NdisMSleep` at `0x140194f61`

## string_xrefs

- `0x140194f99`: `VmsOmNicHeaderGetIncomingPacketCount(&vmNicExt->Nic->NicHeader) == 0`

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
0x140194eb8  mov     [rsp+arg_0], rbx
0x140194ebd  mov     [rsp+arg_8], rsi
0x140194ec2  push    rdi
0x140194ec3  sub     rsp, 30h
0x140194ec7  xor     esi, esi
0x140194ec9  cmp     [rcx+10h], si
0x140194ecd  jnz     loc_140195006
0x140194ed3  mov     rbx, [rcx+8]
0x140194ed7  xor     r9d, r9d; Alertable
0x140194eda  xor     r8d, r8d; WaitMode
0x140194edd  mov     [rsp+38h+Timeout], rsi; Timeout
0x140194ee2  xor     edx, edx; WaitReason
0x140194ee4  lea     rcx, VmsOmIoctlMutex; Object
0x140194eeb  mov     rdi, [rbx+2A8h]
0x140194ef2  call    cs:__imp_KeWaitForSingleObject
0x140194ef9  nop     dword ptr [rax+rax+00h]
0x140194efe  cmp     dword ptr [rdi+758h], 1
0x140194f05  jnz     short loc_140194F29
0x140194f07  mov     rdx, [rdi+760h]
0x140194f0e  cmp     dword ptr [rdx+22D4h], 1
0x140194f15  jnz     short loc_140194F29
0x140194f17  mov     rdx, [rdx+10A8h]
0x140194f1e  xor     r8d, r8d
0x140194f21  mov     rcx, rdi
0x140194f24  call    VmsPDRevokePDAccess
0x140194f29  xor     edx, edx; Wait
0x140194f2b  lea     rcx, VmsOmIoctlMutex; Mutex
0x140194f32  call    cs:__imp_KeReleaseMutex
0x140194f39  nop     dword ptr [rax+rax+00h]
0x140194f3e  mov     edi, 3E8h
0x140194f43  jmp     short loc_140194F53
0x140194f45  mov     ecx, edi; MicrosecondsToSleep
0x140194f47  call    cs:__imp_NdisMSleep
0x140194f4e  nop     dword ptr [rax+rax+00h]
0x140194f53  mov     eax, [rbx+0F4h]
0x140194f59  test    eax, eax
0x140194f5b  jnz     short loc_140194F45
0x140194f5d  jmp     short loc_140194F6D
0x140194f5f  mov     ecx, edi; MicrosecondsToSleep
0x140194f61  call    cs:__imp_NdisMSleep
0x140194f68  nop     dword ptr [rax+rax+00h]
0x140194f6d  mov     eax, [rbx+0F8h]
0x140194f73  test    eax, eax
0x140194f75  jnz     short loc_140194F5F
0x140194f77  mov     rcx, [rbx+2A8h]
0x140194f7e  lea     edx, [rax+2]
0x140194f81  mov     edi, 4D0h
0x140194f86  add     rcx, rdi
0x140194f89  call    VmsOmpNicHeaderGetPacketCount
0x140194f8e  test    eax, eax
0x140194f90  jz      short loc_140194FDD
0x140194f92  mov     rcx, cs:VmsIfrLog
0x140194f99  lea     rax, aVmsomnicheader_0; "VmsOmNicHeaderGetIncomingPacketCount(&v"...
0x140194fa0  mov     [rsp+38h+var_10], rax
0x140194fa5  mov     r9d, 3Eh ; '>'
0x140194fab  lea     rax, WPP_d47d8eaa39f234e41d9f14a0f3ab9b90_Traceguids
0x140194fb2  mov     [rsp+38h+Timeout], rax
0x140194fb7  lea     r8d, [r9-2Bh]
0x140194fbb  call    WPP_RECORDER_SF_s
0x140194fc0  mov     rcx, [rbx+2A8h]
0x140194fc7  mov     edx, 2
0x140194fcc  add     rcx, rdi
0x140194fcf  call    VmsOmpNicHeaderGetPacketCount
0x140194fd4  test    eax, eax
0x140194fd6  jz      short loc_140194FDD
0x140194fd8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsOmNicHeaderGetIncomingPacketCount(&vmNicExt->Nic->NicHeader) == 0")
0x140194fdd  mov     rbx, [rbx]
0x140194fe0  lea     rcx, [rbx+3D1C40h]; RunRef
0x140194fe7  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140194fee  nop     dword ptr [rax+rax+00h]
0x140194ff3  lea     rcx, [rbx+3D1C40h]; RunRef
0x140194ffa  call    cs:__imp_ExRundownCompleted
0x140195001  nop     dword ptr [rax+rax+00h]
0x140195006  mov     rbx, [rsp+38h+arg_0]
0x14019500b  mov     rsi, [rsp+38h+arg_8]
0x140195010  add     rsp, 30h
0x140195014  pop     rdi
0x140195015  retn
```
