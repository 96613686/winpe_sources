# ProcessIrpsThread

- ea: `0x14003a830`
- end: `0x14003aeb3`
- name: `ProcessIrpsThread`
- size: `1667`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140001048`
- `0x140001078`
- `0x14000e6a8`
- `0x140010220`
- `0x140012cc4`
- `0x140014b20`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d0cc`
- `0x14001d120`
- `0x14003a830`
- `0x140040214`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!IoCsqInsertIrp` at `0x14003ab24`
- `ntoskrnl!IoCsqInsertIrp` at `0x14003ab24`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003a949`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003a949`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003a9c2`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003a9c2`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003a9d7`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003a9d7`
- `ntoskrnl!IofCompleteRequest` at `0x14003aab6`
- `ntoskrnl!IofCompleteRequest` at `0x14003acad`
- `ntoskrnl!IofCompleteRequest` at `0x14003aab6`
- `ntoskrnl!IofCompleteRequest` at `0x14003acad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aaa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aaa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac8c`
- `ntoskrnl!IoFreeIrp` at `0x14003ad3d`
- `ntoskrnl!IoFreeIrp` at `0x14003ad3d`
- `ntoskrnl!KeReadStateSemaphore` at `0x14003a8da`
- `ntoskrnl!KeReadStateSemaphore` at `0x14003a8ec`
- `ntoskrnl!KeReadStateSemaphore` at `0x14003a8da`
- `ntoskrnl!KeReadStateSemaphore` at `0x14003a8ec`

## pseudocode

```c
void __fastcall __noreturn ProcessIrpsThread(char *StartContext)
{
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  LONG StateSemaphore; // ebx
  LONG v4; // eax
  NTSTATUS v5; // eax
  PIRP v6; // rax
  IRP *v7; // rbx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  struct _LIST_ENTRY *Flink; // rdi
  int v11; // eax
  __int64 v12; // r14
  char v13; // bl
  __int64 v14; // rax
  int v15; // r8d
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // rax
  IRP *v20; // rbx
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24; // r8d
  int v25; // r9d
  PRKSEMAPHORE Semaphore[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v27; // [rsp+50h] [rbp-59h] BYREF
  __int64 v28[8]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-9h] BYREF

  *(_OWORD *)Semaphore = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext);
  if ( StartContext[354] )
  {
    RegisterInterruptHandler(*((_QWORD *)StartContext + 3));
    *((_DWORD *)StartContext + 377) = 1;
  }
  Semaphore[0] = (PRKSEMAPHORE)(StartContext + 608);
  Semaphore[1] = (PRKSEMAPHORE)(StartContext + 808);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    StateSemaphore = KeReadStateSemaphore((PRKSEMAPHORE)(StartContext + 808));
    v4 = KeReadStateSemaphore(Semaphore[0]);
    WPP_SF_qDD(AttachedDevice, 18, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext, v4, StateSemaphore);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v5 = KeWaitForMultipleObjects(2u, (PVOID *)Semaphore, WaitAny, Executive, 0, 0, 0, 0);
        if ( v5 )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
            StartContext);
        if ( StartContext[356] )
        {
          UnregisterInterruptHandler(StartContext);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
              StartContext);
          PsTerminateSystemThread(0);
        }
        v6 = IoCsqRemoveNextIrp((PIO_CSQ)StartContext + 8, 0);
        v7 = v6;
        if ( v6 )
        {
          Flink = v6->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
              StartContext);
          v11 = ((__int64 (__fastcall *)(IRP *, struct _LIST_ENTRY *, struct _LIST_ENTRY *))Flink[1].Blink)(
                  v7,
                  Flink[2].Flink,
                  Flink[2].Blink);
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                23,
                WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
                StartContext,
                v11);
            goto LABEL_31;
          }
          if ( v11 == 259 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
                StartContext);
            LODWORD(Flink->Flink) = 1;
            IoCsqInsertIrp((PIO_CSQ)(StartContext + 432), v7, (PIO_CSQ_IRP_CONTEXT)&Flink[3]);
          }
          else
          {
LABEL_31:
            ExFreePoolWithTag(Flink, 0x56425355u);
            IofCompleteRequest(v7, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v9 = 24;
              goto LABEL_22;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v9 = 21;
            goto LABEL_22;
          }
        }
      }
      if ( v5 == 1 )
        break;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v9 = 35;
LABEL_22:
        WPP_SF_q(v8->AttachedDevice, v9, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext);
      }
    }
    v12 = *((_QWORD *)StartContext + 81);
    v13 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
        StartContext,
        v12,
        *((_QWORD *)StartContext + 80));
    if ( !v12 )
      MicrosoftTelemetryAssertTriggeredMsgKM("We lack an interrupt context?  Impossible!");
    if ( !*((_QWORD *)StartContext + 80) )
      MicrosoftTelemetryAssertTriggeredMsgKM("We lack an interrupt IRP?  Impossible!");
    if ( v12 )
      break;
LABEL_67:
    if ( *((_QWORD *)StartContext + 80) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids,
          StartContext,
          *((_QWORD *)StartContext + 80));
      IoFreeIrp(*((PIRP *)StartContext + 80));
      *((_QWORD *)StartContext + 80) = 0;
    }
    if ( v13 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 33;
        goto LABEL_22;
      }
    }
    else if ( *((_DWORD *)StartContext + 377) > *((_DWORD *)StartContext + 379) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext);
      if ( dword_14004C1E8 && (unsigned __int8)tlgKeywordOn(&dword_14004C1E8, 0x400000000000LL) )
      {
        v23 = *((_QWORD *)StartContext + 171);
        v28[4] = (__int64)&v27;
        v27 = 16779264;
        v28[5] = 8;
        v28[6] = (__int64)(StartContext + 1348);
        v28[7] = 16;
        tlgCreate1Sz_wchar_t(v29, v23);
        tlgWriteTransfer_EtwWriteTransfer((int)&dword_14004C1E8, (int)&byte_140048E71, v24, v25, 5u, (__int64)v28);
      }
    }
    else
    {
      RegisterInterruptHandler(*((_QWORD *)StartContext + 3));
      ++*((_DWORD *)StartContext + 377);
    }
  }
  v14 = *((_QWORD *)StartContext + 80);
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext);
    goto LABEL_67;
  }
  v15 = *(_DWORD *)(v14 + 48);
  if ( v15 >= 0 )
  {
    v15 = *(_DWORD *)(*(_QWORD *)(v12 + 8) + 4LL);
    if ( v15 >= 0 )
    {
      if ( **(_BYTE **)(v12 + 16) == 1 )
      {
        v18 = *(_QWORD *)(*((_QWORD *)StartContext + 81) + 16LL);
        v19 = RemoveMatchingIrpFromQueue(v18, StartContext);
        v20 = (IRP *)v19;
        if ( v19 )
        {
          ExFreePoolWithTag(*(PVOID *)(v19 + 120), 0x56425355u);
          v20->IoStatus.Status = *(_BYTE *)(v18 + 4) != 0 ? 0xC0000001 : 0;
          IofCompleteRequest(v20, 0);
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            goto LABEL_66;
          v22 = 30;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            goto LABEL_66;
          v22 = 29;
        }
        WPP_SF_q(v21->AttachedDevice, v22, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext);
      }
LABEL_66:
      v13 = USBVideoProcessInterrupt(v12);
      goto LABEL_67;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_66;
    v17 = 28;
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_66;
    v17 = 27;
  }
  WPP_SF_qD(v16->AttachedDevice, v17, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, StartContext, v15);
  goto LABEL_66;
}

```

## disassembly

```asm
0x14003a830  push    rbp
0x14003a832  push    rbx
0x14003a833  push    rsi
0x14003a834  push    rdi
0x14003a835  push    r12
0x14003a837  push    r13
0x14003a839  push    r14
0x14003a83b  push    r15
0x14003a83d  lea     rbp, [rsp-1Fh]
0x14003a842  sub     rsp, 0C8h
0x14003a849  mov     rax, cs:__security_cookie
0x14003a850  xor     rax, rsp
0x14003a853  mov     [rbp+57h+var_50], rax
0x14003a857  xorps   xmm0, xmm0
0x14003a85a  mov     rsi, rcx
0x14003a85d  movups  xmmword ptr [rbp+57h+Semaphore], xmm0
0x14003a861  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a868  lea     r14, WPP_GLOBAL_Control
0x14003a86f  cmp     rcx, r14
0x14003a872  jz      short loc_14003A892
0x14003a874  cmp     byte ptr [rcx+29h], 4
0x14003a878  jb      short loc_14003A892
0x14003a87a  mov     rcx, [rcx+18h]
0x14003a87e  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003a885  mov     edx, 11h
0x14003a88a  mov     r9, rsi
0x14003a88d  call    WPP_SF_q
0x14003a892  cmp     byte ptr [rsi+162h], 0
0x14003a899  jz      short loc_14003A8AE
0x14003a89b  mov     rcx, [rsi+18h]
0x14003a89f  call    RegisterInterruptHandler
0x14003a8a4  mov     dword ptr [rsi+5E4h], 1
0x14003a8ae  lea     rax, [rsi+260h]
0x14003a8b5  lea     rcx, [rsi+328h]; Semaphore
0x14003a8bc  mov     [rbp+57h+Semaphore], rax
0x14003a8c0  mov     [rbp+57h+Semaphore+8], rcx
0x14003a8c4  mov     rdi, cs:WPP_GLOBAL_Control
0x14003a8cb  cmp     rdi, r14
0x14003a8ce  jz      short loc_14003A917
0x14003a8d0  cmp     byte ptr [rdi+29h], 5
0x14003a8d4  jb      short loc_14003A917
0x14003a8d6  mov     rdi, [rdi+18h]
0x14003a8da  call    cs:__imp_KeReadStateSemaphore
0x14003a8e1  nop     dword ptr [rax+rax+00h]
0x14003a8e6  mov     rcx, [rbp+57h+Semaphore]; Semaphore
0x14003a8ea  mov     ebx, eax
0x14003a8ec  call    cs:__imp_KeReadStateSemaphore
0x14003a8f3  nop     dword ptr [rax+rax+00h]
0x14003a8f8  mov     edx, 12h
0x14003a8fd  mov     dword ptr [rsp+100h+Alertable], ebx
0x14003a901  mov     r9, rsi
0x14003a904  mov     dword ptr [rsp+100h+WaitMode], eax
0x14003a908  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003a90f  mov     rcx, rdi
0x14003a912  call    WPP_SF_qDD
0x14003a917  lea     r13, [rsi+544h]
0x14003a91e  xor     r9d, r9d; WaitReason
0x14003a921  mov     [rsp+100h+WaitBlockArray], 0; WaitBlockArray
0x14003a92a  mov     [rsp+100h+Timeout], 0; Timeout
0x14003a933  lea     rdx, [rbp+57h+Semaphore]; Object
0x14003a937  mov     [rsp+100h+Alertable], 0; Alertable
0x14003a93c  mov     [rsp+100h+WaitMode], 0; WaitMode
0x14003a941  lea     r8d, [r9+1]; WaitType
0x14003a945  lea     ecx, [r9+2]; Count
0x14003a949  call    cs:__imp_KeWaitForMultipleObjects
0x14003a950  nop     dword ptr [rax+rax+00h]
0x14003a955  test    eax, eax
0x14003a957  jnz     loc_14003AB35
0x14003a95d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a964  cmp     rcx, r14
0x14003a967  jz      short loc_14003A985
0x14003a969  cmp     byte ptr [rcx+29h], 4
0x14003a96d  jb      short loc_14003A985
0x14003a96f  mov     rcx, [rcx+18h]
0x14003a973  lea     edx, [rax+13h]
0x14003a976  mov     r9, rsi
0x14003a979  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003a980  call    WPP_SF_q
0x14003a985  cmp     byte ptr [rsi+164h], 0
0x14003a98c  jz      short loc_14003A9CE
0x14003a98e  mov     rcx, rsi
0x14003a991  call    UnregisterInterruptHandler
0x14003a996  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a99d  cmp     rcx, r14
0x14003a9a0  jz      short loc_14003A9C0
0x14003a9a2  cmp     byte ptr [rcx+29h], 4
0x14003a9a6  jb      short loc_14003A9C0
0x14003a9a8  mov     rcx, [rcx+18h]
0x14003a9ac  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003a9b3  mov     edx, 14h
0x14003a9b8  mov     r9, rsi
0x14003a9bb  call    WPP_SF_q
0x14003a9c0  xor     ecx, ecx; ExitStatus
0x14003a9c2  call    cs:__imp_PsTerminateSystemThread
0x14003a9c9  nop     dword ptr [rax+rax+00h]
0x14003a9ce  xor     edx, edx; PeekContext
0x14003a9d0  lea     rcx, [rsi+200h]; Csq
0x14003a9d7  call    cs:__imp_IoCsqRemoveNextIrp
0x14003a9de  nop     dword ptr [rax+rax+00h]
0x14003a9e3  mov     rbx, rax
0x14003a9e6  test    rax, rax
0x14003a9e9  jnz     short loc_14003AA20
0x14003a9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9f2  cmp     rcx, r14
0x14003a9f5  jz      loc_14003A91E
0x14003a9fb  cmp     byte ptr [rcx+29h], 5
0x14003a9ff  jb      loc_14003A91E
0x14003aa05  lea     edx, [rax+15h]
0x14003aa08  mov     rcx, [rcx+18h]
0x14003aa0c  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003aa13  mov     r9, rsi
0x14003aa16  call    WPP_SF_q
0x14003aa1b  jmp     loc_14003A91E
0x14003aa20  mov     rdi, [rax+78h]
0x14003aa24  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa2b  cmp     rcx, r14
0x14003aa2e  jz      short loc_14003AA4E
0x14003aa30  cmp     byte ptr [rcx+29h], 5
0x14003aa34  jb      short loc_14003AA4E
0x14003aa36  mov     rcx, [rcx+18h]
0x14003aa3a  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003aa41  mov     edx, 16h
0x14003aa46  mov     r9, rsi
0x14003aa49  call    WPP_SF_q
0x14003aa4e  mov     rax, [rdi+18h]
0x14003aa52  mov     rcx, rbx
0x14003aa55  mov     r8, [rdi+28h]
0x14003aa59  mov     rdx, [rdi+20h]
0x14003aa5d  call    _guard_dispatch_icall
0x14003aa62  test    eax, eax
0x14003aa64  jns     short loc_14003AA96
0x14003aa66  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa6d  cmp     rcx, r14
0x14003aa70  jz      short loc_14003AA9D
0x14003aa72  cmp     byte ptr [rcx+29h], 5
0x14003aa76  jb      short loc_14003AA9D
0x14003aa78  mov     rcx, [rcx+18h]
0x14003aa7c  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003aa83  mov     edx, 17h
0x14003aa88  mov     dword ptr [rsp+100h+WaitMode], eax
0x14003aa8c  mov     r9, rsi
0x14003aa8f  call    WPP_SF_qD
0x14003aa94  jmp     short loc_14003AA9D
0x14003aa96  cmp     eax, 103h
0x14003aa9b  jz      short loc_14003AAE6
0x14003aa9d  mov     edx, 56425355h; Tag
0x14003aaa2  mov     rcx, rdi; P
0x14003aaa5  call    cs:__imp_ExFreePoolWithTag
0x14003aaac  nop     dword ptr [rax+rax+00h]
0x14003aab1  xor     edx, edx; PriorityBoost
0x14003aab3  mov     rcx, rbx; Irp
0x14003aab6  call    cs:__imp_IofCompleteRequest
0x14003aabd  nop     dword ptr [rax+rax+00h]
0x14003aac2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aac9  cmp     rcx, r14
0x14003aacc  jz      loc_14003A91E
0x14003aad2  cmp     byte ptr [rcx+29h], 5
0x14003aad6  jb      loc_14003A91E
0x14003aadc  mov     edx, 18h
0x14003aae1  jmp     loc_14003AA08
0x14003aae6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aaed  cmp     rcx, r14
0x14003aaf0  jz      short loc_14003AB10
0x14003aaf2  cmp     byte ptr [rcx+29h], 5
0x14003aaf6  jb      short loc_14003AB10
0x14003aaf8  mov     rcx, [rcx+18h]
0x14003aafc  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003ab03  mov     edx, 19h
0x14003ab08  mov     r9, rsi
0x14003ab0b  call    WPP_SF_q
0x14003ab10  lea     r8, [rdi+30h]; Context
0x14003ab14  mov     dword ptr [rdi], 1
0x14003ab1a  mov     rdx, rbx; Irp
0x14003ab1d  lea     rcx, [rsi+1B0h]; Csq
0x14003ab24  call    cs:__imp_IoCsqInsertIrp
0x14003ab2b  nop     dword ptr [rax+rax+00h]
0x14003ab30  jmp     loc_14003A91E
0x14003ab35  cmp     eax, 1
0x14003ab38  jnz     loc_14003AE8F
0x14003ab3e  mov     r14, [rsi+288h]
0x14003ab45  xor     bl, bl
0x14003ab47  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab4e  lea     rdi, WPP_GLOBAL_Control
0x14003ab55  cmp     rcx, rdi
0x14003ab58  jz      short loc_14003AB87
0x14003ab5a  cmp     byte ptr [rcx+29h], 4
0x14003ab5e  jb      short loc_14003AB87
0x14003ab60  mov     rcx, [rcx+18h]
0x14003ab64  lea     edx, [rax+19h]
0x14003ab67  mov     rax, [rsi+280h]
0x14003ab6e  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003ab75  mov     qword ptr [rsp+100h+Alertable], rax
0x14003ab7a  mov     r9, rsi
0x14003ab7d  mov     qword ptr [rsp+100h+WaitMode], r14
0x14003ab82  call    WPP_SF_qqq
0x14003ab87  test    r14, r14
0x14003ab8a  jnz     short loc_14003AB98
0x14003ab8c  lea     rcx, aWeLackAnInterr; "We lack an interrupt context?  Impossib"...
0x14003ab93  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003ab98  cmp     qword ptr [rsi+280h], 0
0x14003aba0  jnz     short loc_14003ABAE
0x14003aba2  lea     rcx, aWeLackAnInterr_0; "We lack an interrupt IRP?  Impossible!"
0x14003aba9  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003abae  test    r14, r14
0x14003abb1  jz      loc_14003ACF4
0x14003abb7  mov     rax, [rsi+280h]
0x14003abbe  test    rax, rax
0x14003abc1  jz      loc_14003AD7C
0x14003abc7  mov     r8d, [rax+30h]
0x14003abcb  test    r8d, r8d
0x14003abce  jns     short loc_14003ABF1
0x14003abd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003abd7  cmp     rcx, rdi
0x14003abda  jz      loc_14003ACEA
0x14003abe0  cmp     byte ptr [rcx+29h], 2
0x14003abe4  jb      loc_14003ACEA
0x14003abea  mov     edx, 1Bh
0x14003abef  jmp     short loc_14003AC1D
0x14003abf1  mov     rax, [r14+8]
0x14003abf5  mov     r8d, [rax+4]
0x14003abf9  test    r8d, r8d
0x14003abfc  jns     short loc_14003AC3A
0x14003abfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac05  cmp     rcx, rdi
0x14003ac08  jz      loc_14003ACEA
0x14003ac0e  cmp     byte ptr [rcx+29h], 2
0x14003ac12  jb      loc_14003ACEA
0x14003ac18  mov     edx, 1Ch
0x14003ac1d  mov     rcx, [rcx+18h]
0x14003ac21  mov     r9, rsi
0x14003ac24  mov     dword ptr [rsp+100h+WaitMode], r8d
0x14003ac29  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003ac30  call    WPP_SF_qD
0x14003ac35  jmp     loc_14003ACEA
0x14003ac3a  mov     rax, [r14+10h]
0x14003ac3e  cmp     byte ptr [rax], 1
0x14003ac41  jnz     loc_14003ACEA
0x14003ac47  mov     rax, [rsi+288h]
0x14003ac4e  mov     rdx, rsi
0x14003ac51  mov     rdi, [rax+10h]
0x14003ac55  mov     rcx, rdi
0x14003ac58  call    RemoveMatchingIrpFromQueue
0x14003ac5d  mov     rbx, rax
0x14003ac60  test    rax, rax
0x14003ac63  jnz     short loc_14003AC83
0x14003ac65  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac6c  lea     rax, WPP_GLOBAL_Control
0x14003ac73  cmp     rcx, rax
0x14003ac76  jz      short loc_14003ACEA
0x14003ac78  cmp     byte ptr [rcx+29h], 5
0x14003ac7c  jb      short loc_14003ACEA
0x14003ac7e  lea     edx, [rbx+1Dh]
0x14003ac81  jmp     short loc_14003ACD7
0x14003ac83  mov     rcx, [rax+78h]; P
0x14003ac87  mov     edx, 56425355h; Tag
0x14003ac8c  call    cs:__imp_ExFreePoolWithTag
0x14003ac93  nop     dword ptr [rax+rax+00h]
0x14003ac98  mov     al, [rdi+4]
0x14003ac9b  neg     al
0x14003ac9d  sbb     ecx, ecx
0x14003ac9f  xor     edx, edx; PriorityBoost
0x14003aca1  and     ecx, 0C0000001h
0x14003aca7  mov     [rbx+30h], ecx
0x14003acaa  mov     rcx, rbx; Irp
0x14003acad  call    cs:__imp_IofCompleteRequest
0x14003acb4  nop     dword ptr [rax+rax+00h]
0x14003acb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003acc0  lea     rax, WPP_GLOBAL_Control
0x14003acc7  cmp     rcx, rax
0x14003acca  jz      short loc_14003ACEA
0x14003accc  cmp     byte ptr [rcx+29h], 5
0x14003acd0  jb      short loc_14003ACEA
0x14003acd2  mov     edx, 1Eh
0x14003acd7  mov     rcx, [rcx+18h]
0x14003acdb  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003ace2  mov     r9, rsi
0x14003ace5  call    WPP_SF_q
0x14003acea  mov     rcx, r14
0x14003aced  call    USBVideoProcessInterrupt
0x14003acf2  mov     bl, al
0x14003acf4  lea     r14, WPP_GLOBAL_Control
0x14003acfb  mov     rax, [rsi+280h]
0x14003ad02  test    rax, rax
0x14003ad05  jz      short loc_14003AD54
0x14003ad07  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad0e  cmp     rcx, r14
0x14003ad11  jz      short loc_14003AD36
0x14003ad13  cmp     byte ptr [rcx+29h], 4
0x14003ad17  jb      short loc_14003AD36
0x14003ad19  mov     rcx, [rcx+18h]
0x14003ad1d  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003ad24  mov     edx, 20h ; ' '
0x14003ad29  mov     qword ptr [rsp+100h+WaitMode], rax
0x14003ad2e  mov     r9, rsi
0x14003ad31  call    WPP_SF_qq
0x14003ad36  mov     rcx, [rsi+280h]; Irp
0x14003ad3d  call    cs:__imp_IoFreeIrp
0x14003ad44  nop     dword ptr [rax+rax+00h]
0x14003ad49  mov     qword ptr [rsi+280h], 0
0x14003ad54  test    bl, bl
  ... truncated ...
```
