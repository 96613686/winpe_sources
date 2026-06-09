# VmsVrssPvtCreateWorkerThread

- ea: `0x1401b1394`
- end: `0x1401b1534`
- name: `VmsVrssPvtCreateWorkerThread`
- size: `416`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401b108c`

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x14008497c`
- `0x1401b1394`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x1401b1405`
- `ntoskrnl!PsCreateSystemThread` at `0x1401b1405`
- `ntoskrnl!ZwSetInformationThread` at `0x1401b1465`
- `ntoskrnl!ZwSetInformationThread` at `0x1401b1465`
- `ntoskrnl!KeInitializeEvent` at `0x1401b13cf`
- `ntoskrnl!KeInitializeEvent` at `0x1401b13cf`
- `ntoskrnl!ZwClose` at `0x1401b14f3`
- `ntoskrnl!ZwClose` at `0x1401b14f3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b14d6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b14d6`

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
0x1401b1394  push    rbx
0x1401b1396  push    rsi
0x1401b1397  push    rdi
0x1401b1398  sub     rsp, 40h
0x1401b139c  lea     rsi, [rcx+240h]
0x1401b13a3  mov     [rsp+58h+ThreadHandle], 0
0x1401b13ac  xor     r8d, r8d; State
0x1401b13af  mov     [rsp+58h+ThreadInformation], 0
0x1401b13b7  mov     rbx, rcx
0x1401b13ba  mov     dword ptr [rsi+0DCh], 0
0x1401b13c4  lea     rcx, [rsi+0C0h]; Event
0x1401b13cb  lea     edx, [r8+1]; Type
0x1401b13cf  call    cs:__imp_KeInitializeEvent
0x1401b13d6  nop     dword ptr [rax+rax+00h]
0x1401b13db  lea     rax, VmsVrssWorkerThread
0x1401b13e2  mov     [rsp+58h+StartContext], rbx; StartContext
0x1401b13e7  mov     [rsp+58h+StartRoutine], rax; StartRoutine
0x1401b13ec  lea     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x1401b13f1  xor     r9d, r9d; ProcessHandle
0x1401b13f4  mov     [rsp+58h+ClientId], 0; ClientId
0x1401b13fd  xor     r8d, r8d; ObjectAttributes
0x1401b1400  mov     edx, 1FFFFFh; DesiredAccess
0x1401b1405  call    cs:__imp_PsCreateSystemThread
0x1401b140c  nop     dword ptr [rax+rax+00h]
0x1401b1411  mov     ebx, eax
0x1401b1413  test    eax, eax
0x1401b1415  jns     short loc_1401B1449
0x1401b1417  mov     rcx, cs:VmsIfrLog
0x1401b141e  lea     rdi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1425  mov     dword ptr [rsp+58h+StartContext], eax
0x1401b1429  mov     r9d, 11h
0x1401b142f  mov     [rsp+58h+StartRoutine], rsi
0x1401b1434  mov     dl, 2
0x1401b1436  mov     [rsp+58h+ClientId], rdi
0x1401b143b  lea     r8d, [r9+3]
0x1401b143f  call    WPP_RECORDER_SF_id
0x1401b1444  jmp     loc_1401B1503
0x1401b1449  mov     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x1401b144e  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x1401b1453  mov     r9d, 4; ThreadInformationLength
0x1401b1459  mov     [rsp+58h+ThreadInformation], 0Fh
0x1401b1461  lea     edx, [r9-2]; ThreadInformationClass
0x1401b1465  call    cs:__imp_ZwSetInformationThread
0x1401b146c  nop     dword ptr [rax+rax+00h]
0x1401b1471  lea     rdi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1478  mov     ebx, eax
0x1401b147a  test    eax, eax
0x1401b147c  jns     short loc_1401B14AA
0x1401b147e  mov     rcx, cs:VmsIfrLog
0x1401b1485  lea     rax, aNtSuccessStatu_0; "NT_SUCCESS(status)"
0x1401b148c  mov     r9d, 12h
0x1401b1492  mov     [rsp+58h+StartRoutine], rax
0x1401b1497  mov     [rsp+58h+ClientId], rdi
0x1401b149c  lea     r8d, [r9+1]
0x1401b14a0  call    WPP_RECORDER_SF_s
0x1401b14a5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1401b14aa  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x1401b14af  lea     rax, [rsp+58h+Object]
0x1401b14b4  mov     [rsp+58h+StartRoutine], 0; HandleInformation
0x1401b14bd  xor     r9d, r9d; AccessMode
0x1401b14c0  xor     r8d, r8d; ObjectType
0x1401b14c3  mov     [rsp+58h+ClientId], rax; Object
0x1401b14c8  mov     edx, 1FFFFFh; DesiredAccess
0x1401b14cd  mov     [rsp+58h+Object], 0
0x1401b14d6  call    cs:__imp_ObReferenceObjectByHandle
0x1401b14dd  nop     dword ptr [rax+rax+00h]
0x1401b14e2  mov     rax, [rsp+58h+Object]
0x1401b14e7  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x1401b14ec  mov     [rsi+0F0h], rax
0x1401b14f3  call    cs:__imp_ZwClose
0x1401b14fa  nop     dword ptr [rax+rax+00h]
0x1401b14ff  test    ebx, ebx
0x1401b1501  jns     short loc_1401B1529
0x1401b1503  mov     rcx, cs:VmsIfrLog
0x1401b150a  mov     r9d, 13h
0x1401b1510  mov     dword ptr [rsp+58h+StartContext], ebx
0x1401b1514  mov     dl, 2
0x1401b1516  mov     [rsp+58h+StartRoutine], rsi
0x1401b151b  mov     [rsp+58h+ClientId], rdi
0x1401b1520  lea     r8d, [r9+1]
0x1401b1524  call    WPP_RECORDER_SF_id
0x1401b1529  mov     eax, ebx
0x1401b152b  add     rsp, 40h
0x1401b152f  pop     rdi
0x1401b1530  pop     rsi
0x1401b1531  pop     rbx
0x1401b1532  retn
```
