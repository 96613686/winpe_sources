# VmsVrssPvtCreateWorkerThread

- ea: `0x1401b1404`
- end: `0x1401b15a4`
- name: `VmsVrssPvtCreateWorkerThread`
- size: `416`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401b10fc`

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x14008497c`
- `0x1401b1404`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x1401b1475`
- `ntoskrnl!PsCreateSystemThread` at `0x1401b1475`
- `ntoskrnl!ZwSetInformationThread` at `0x1401b14d5`
- `ntoskrnl!ZwSetInformationThread` at `0x1401b14d5`
- `ntoskrnl!KeInitializeEvent` at `0x1401b143f`
- `ntoskrnl!KeInitializeEvent` at `0x1401b143f`
- `ntoskrnl!ZwClose` at `0x1401b1563`
- `ntoskrnl!ZwClose` at `0x1401b1563`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b1546`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b1546`

## pseudocode

```c
__int64 __fastcall VmsVrssPvtCreateWorkerThread(struct _KEVENT *StartContext)
{
  struct _KEVENT *v1; // rsi
  NTSTATUS v3; // eax
  int v4; // edx
  NTSTATUS v5; // ebx
  int v6; // edx
  int v7; // edx
  void *v8; // rcx
  int ThreadInformation; // [rsp+60h] [rbp+8h] BYREF
  void *ThreadHandle; // [rsp+68h] [rbp+10h] BYREF
  PVOID Object; // [rsp+70h] [rbp+18h] BYREF

  v1 = StartContext + 24;
  ThreadHandle = 0;
  ThreadInformation = 0;
  StartContext[33].Header.SignalState = 0;
  KeInitializeEvent(StartContext + 32, SynchronizationEvent, 0);
  v3 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, (PKSTART_ROUTINE)VmsVrssWorkerThread, StartContext);
  v5 = v3;
  if ( v3 < 0 )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v4, 20, 17, (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids, (char)v1, v3);
LABEL_6:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v6, 20, 19, (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids, (char)v1, v5);
    return (unsigned int)v5;
  }
  ThreadInformation = 15;
  v5 = ZwSetInformationThread(ThreadHandle, ThreadPriority, &ThreadInformation, 4u);
  if ( v5 < 0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      18,
      (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
      (__int64)"NT_SUCCESS(status)");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  Object = 0;
  ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
  v8 = ThreadHandle;
  *(_QWORD *)&v1[10].Header.Lock = Object;
  ZwClose(v8);
  if ( v5 < 0 )
    goto LABEL_6;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1401b1404  push    rbx
0x1401b1406  push    rsi
0x1401b1407  push    rdi
0x1401b1408  sub     rsp, 40h
0x1401b140c  lea     rsi, [rcx+240h]
0x1401b1413  mov     [rsp+58h+ThreadHandle], 0
0x1401b141c  xor     r8d, r8d; State
0x1401b141f  mov     [rsp+58h+ThreadInformation], 0
0x1401b1427  mov     rbx, rcx
0x1401b142a  mov     dword ptr [rsi+0DCh], 0
0x1401b1434  lea     rcx, [rsi+0C0h]; Event
0x1401b143b  lea     edx, [r8+1]; Type
0x1401b143f  call    cs:__imp_KeInitializeEvent
0x1401b1446  nop     dword ptr [rax+rax+00h]
0x1401b144b  lea     rax, VmsVrssWorkerThread
0x1401b1452  mov     [rsp+58h+StartContext], rbx; StartContext
0x1401b1457  mov     [rsp+58h+StartRoutine], rax; StartRoutine
0x1401b145c  lea     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x1401b1461  xor     r9d, r9d; ProcessHandle
0x1401b1464  mov     [rsp+58h+ClientId], 0; ClientId
0x1401b146d  xor     r8d, r8d; ObjectAttributes
0x1401b1470  mov     edx, 1FFFFFh; DesiredAccess
0x1401b1475  call    cs:__imp_PsCreateSystemThread
0x1401b147c  nop     dword ptr [rax+rax+00h]
0x1401b1481  mov     ebx, eax
0x1401b1483  test    eax, eax
0x1401b1485  jns     short loc_1401B14B9
0x1401b1487  mov     rcx, cs:VmsIfrLog
0x1401b148e  lea     rdi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1495  mov     dword ptr [rsp+58h+StartContext], eax
0x1401b1499  mov     r9d, 11h
0x1401b149f  mov     [rsp+58h+StartRoutine], rsi
0x1401b14a4  mov     dl, 2
0x1401b14a6  mov     [rsp+58h+ClientId], rdi
0x1401b14ab  lea     r8d, [r9+3]
0x1401b14af  call    WPP_RECORDER_SF_id
0x1401b14b4  jmp     loc_1401B1573
0x1401b14b9  mov     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x1401b14be  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x1401b14c3  mov     r9d, 4; ThreadInformationLength
0x1401b14c9  mov     [rsp+58h+ThreadInformation], 0Fh
0x1401b14d1  lea     edx, [r9-2]; ThreadInformationClass
0x1401b14d5  call    cs:__imp_ZwSetInformationThread
0x1401b14dc  nop     dword ptr [rax+rax+00h]
0x1401b14e1  lea     rdi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b14e8  mov     ebx, eax
0x1401b14ea  test    eax, eax
0x1401b14ec  jns     short loc_1401B151A
0x1401b14ee  mov     rcx, cs:VmsIfrLog
0x1401b14f5  lea     rax, aNtSuccessStatu_0; "NT_SUCCESS(status)"
0x1401b14fc  mov     r9d, 12h
0x1401b1502  mov     [rsp+58h+StartRoutine], rax
0x1401b1507  mov     [rsp+58h+ClientId], rdi
0x1401b150c  lea     r8d, [r9+1]
0x1401b1510  call    WPP_RECORDER_SF_s
0x1401b1515  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1401b151a  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x1401b151f  lea     rax, [rsp+58h+Object]
0x1401b1524  mov     [rsp+58h+StartRoutine], 0; HandleInformation
0x1401b152d  xor     r9d, r9d; AccessMode
0x1401b1530  xor     r8d, r8d; ObjectType
0x1401b1533  mov     [rsp+58h+ClientId], rax; Object
0x1401b1538  mov     edx, 1FFFFFh; DesiredAccess
0x1401b153d  mov     [rsp+58h+Object], 0
0x1401b1546  call    cs:__imp_ObReferenceObjectByHandle
0x1401b154d  nop     dword ptr [rax+rax+00h]
0x1401b1552  mov     rax, [rsp+58h+Object]
0x1401b1557  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x1401b155c  mov     [rsi+0F0h], rax
0x1401b1563  call    cs:__imp_ZwClose
0x1401b156a  nop     dword ptr [rax+rax+00h]
0x1401b156f  test    ebx, ebx
0x1401b1571  jns     short loc_1401B1599
0x1401b1573  mov     rcx, cs:VmsIfrLog
0x1401b157a  mov     r9d, 13h
0x1401b1580  mov     dword ptr [rsp+58h+StartContext], ebx
0x1401b1584  mov     dl, 2
0x1401b1586  mov     [rsp+58h+StartRoutine], rsi
0x1401b158b  mov     [rsp+58h+ClientId], rdi
0x1401b1590  lea     r8d, [r9+1]
0x1401b1594  call    WPP_RECORDER_SF_id
0x1401b1599  mov     eax, ebx
0x1401b159b  add     rsp, 40h
0x1401b159f  pop     rdi
0x1401b15a0  pop     rsi
0x1401b15a1  pop     rbx
0x1401b15a2  retn
```
