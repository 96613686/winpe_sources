# DispatchFdoPnp

- ea: `0x140028800`
- end: `0x140028cb7`
- name: `DispatchFdoPnp`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140028630`

## callees

- `0x140003388`
- `0x140003b3c`
- `0x140005940`
- `0x140006630`
- `0x140006834`
- `0x140006af8`
- `0x140006d40`
- `0x14000a6cc`
- `0x14000e660`
- `0x14000e754`
- `0x14000fa04`
- `0x1400124cc`
- `0x140013d4c`
- `0x140022008`
- `0x1400258cc`
- `0x140028800`
- `0x140028cc0`
- `0x140028f7c`
- `0x140029a38`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002888c`
- `ntoskrnl!KeInitializeEvent` at `0x14002888c`
- `ntoskrnl!IofCallDriver` at `0x1400288c1`
- `ntoskrnl!IofCallDriver` at `0x1400288c1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028911`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028c89`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028911`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028c89`
- `ntoskrnl!DbgPrint` at `0x140028c35`
- `ntoskrnl!DbgPrint` at `0x140028c35`

## string_xrefs

- `0x14002891d`: `event (waiting for sent irp to complete)`
- `0x140028c26`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n`

## pseudocode

```c
NTSTATUS __fastcall DispatchFdoPnp(__int64 a1, PIRP Irp, int a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PIRP v4; // rbp
  int MinorFunction; // edi
  _IO_STACK_LOCATION *v7; // rax
  struct _DEVICE_OBJECT *v8; // rbx
  struct _DEVICE_OBJECT *v9; // rdi
  NTSTATUS v10; // eax
  int Status; // ebx
  int v12; // ebx
  int v13; // edi
  int v14; // edx
  NTSTATUS i; // ecx
  int v16; // r8d
  int v17; // edx
  NTSTATUS result; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  NTSTATUS started; // r14d
  int v23; // eax
  unsigned __int64 v24; // rdx
  int v25; // kr00_4
  __int64 v26; // rdx
  int v27; // edx
  int v28; // r8d
  int v29; // edx
  int Timeout; // [rsp+20h] [rbp-78h]
  int Timeouta; // [rsp+20h] [rbp-78h]
  struct _KEVENT Event; // [rsp+50h] [rbp-48h] BYREF
  union _LARGE_INTEGER v33; // [rsp+A0h] [rbp+8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = Irp;
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( *(_DWORD *)(a1 + 4) != 1 )
  {
    if ( (_BYTE)MinorFunction == 7 )
    {
      if ( CurrentStackLocation->Parameters.Read.Length )
        goto LABEL_2;
    }
    else if ( (_BYTE)MinorFunction == 9 )
    {
      goto LABEL_2;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Irp) = 4;
      WPP_RECORDER_SF_qc(*(_QWORD *)(a1 + 1368), (_DWORD)Irp, a3, 10);
    }
    LOBYTE(Irp) = 1;
    v23 = ParentSetD0(a1, (_DWORD)Irp, 0, 0, 0);
    if ( v23 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Irp) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)Irp,
        8,
        11,
        (__int64)WPP_54beca300c4a353e079921b0991edb26_Traceguids,
        v23);
    }
  }
LABEL_2:
  if ( MinorFunction == 9 )
  {
    v7 = v4->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v7[-1].MajorFunction = *(_OWORD *)&v7->MajorFunction;
    *(_OWORD *)&v7[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v7->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v7[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v7->Parameters.SetQuota + 6);
    v7[-1].FileObject = v7->FileObject;
    v7[-1].Control = 0;
    v8 = *(struct _DEVICE_OBJECT **)(a1 + 32);
    v9 = *(struct _DEVICE_OBJECT **)(a1 + 40);
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    SetCompletionRoutine(g_RecorderLog, v8, v4, USBD_SyncCompletionRoutine, &Event);
    v10 = IofCallDriver(v9, v4);
    Status = v10;
    if ( v10 == 259 )
    {
      v12 = g_RecorderLog;
      v33.QuadPart = -600000000;
      v13 = 0;
      for ( i = KeWaitForSingleObject(&Event, Executive, 0, 0, &v33);
            i == 258;
            i = KeWaitForSingleObject(&Event, Executive, 0, 0, &v33) )
      {
        DbgPrint(
          "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n",
          KeGetCurrentThread(),
          ++v13,
          "event (waiting for sent irp to complete)");
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qds(
            v12,
            v27,
            v28,
            61,
            Timeouta,
            (char)KeGetCurrentThread(),
            v13,
            (__int64)"event (waiting for sent irp to complete)");
      }
      if ( i < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dqs(
          v12,
          v14,
          v16,
          62,
          Timeouta,
          i,
          (char)KeGetCurrentThread(),
          (__int64)"event (waiting for sent irp to complete)");
    }
    else if ( v10 < 0 )
    {
LABEL_7:
      if ( Status >= 0 )
        *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 4) |= 0x200u;
      v17 = Status;
LABEL_10:
      UsbcCompleteIrp(a1, v17, v4);
      return Status;
    }
    Status = v4->IoStatus.Status;
    goto LABEL_7;
  }
  if ( MinorFunction == 1 )
  {
LABEL_12:
    v4->IoStatus.Status = 0;
LABEL_13:
    result = UsbcForwardIrpWithCompletion(
               a1,
               *(struct _DEVICE_OBJECT **)(a1 + 40),
               v4,
               (IO_COMPLETION_ROUTINE *)USBC_PnpComplete,
               *(struct _DEVICE_OBJECT **)(a1 + 32),
               (PVOID)a1);
    started = result;
    if ( !(_BYTE)MinorFunction || MinorFunction == 2 || MinorFunction == 4 || (unsigned int)(MinorFunction - 5) < 2 )
    {
LABEL_34:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qcqd(
          *(_QWORD *)(a1 + 1368),
          v19,
          v20,
          v21,
          Timeout,
          *(_QWORD *)(a1 + 32),
          MinorFunction,
          (char)v4,
          started);
      return started;
    }
  }
  else
  {
    v25 = (int)Irp;
    v24 = 0x140000000uLL;
    switch ( MinorFunction )
    {
      case 0:
        started = StartParentFdo(a1);
        goto LABEL_34;
      case 2:
        started = FdoRemoveDevice(a1, v4);
        goto LABEL_34;
      case 4:
        HandleFdoStop(a1, v4);
        goto LABEL_13;
      case 5:
        *(_DWORD *)(a1 + 12) = 4;
        DisableIdleTimer(a1, 0x140000000uLL, 1347376211);
        LOBYTE(v26) = 1;
        CancelFdoIdleIrp(a1, v26);
        goto LABEL_12;
      case 6:
        if ( *(_DWORD *)(a1 + 12) == 4 )
        {
          LOBYTE(v24) = 1;
          EnableIdleTimer(a1, v24, 1347376211);
        }
        *(_DWORD *)(a1 + 12) = 2;
        goto LABEL_12;
      case 7:
        result = QueryParentDeviceRelations(a1, v4);
        break;
      case 22:
        Status = 0;
        HandleFdoDeviceUsageNotification(a1, v4);
        v17 = 0;
        goto LABEL_10;
      case 23:
        if ( *(_BYTE *)(a1 + 1361) )
          UnregisterCompositeDevice(a1);
        goto LABEL_12;
      default:
        v29 = v25;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v29) = 5;
          WPP_RECORDER_SF_qc(*(_QWORD *)(a1 + 1368), v29, a3, 12);
        }
        goto LABEL_13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140028800  mov     [rsp+arg_10], rbx
0x140028805  push    rbp
0x140028806  push    rsi
0x140028807  push    rdi
0x140028808  push    r14
0x14002880a  push    r15
0x14002880c  sub     rsp, 70h
0x140028810  cmp     dword ptr [rcx+4], 1
0x140028814  lea     r15, WPP_RECORDER_INITIALIZED
0x14002881b  mov     r14, [rdx+0B8h]
0x140028822  mov     rbp, rdx
0x140028825  mov     rsi, rcx
0x140028828  movzx   edi, byte ptr [r14+1]
0x14002882d  jnz     loc_140028A2E
0x140028833  mov     rbx, rdi
0x140028836  cmp     edi, 9
0x140028839  jnz     loc_14002895D
0x14002883f  mov     rax, [rbp+0B8h]
0x140028846  lea     rcx, [rsp+98h+Event]; Event
0x14002884b  xor     r8d, r8d; State
0x14002884e  xor     edx, edx; Type
0x140028850  movups  xmm0, xmmword ptr [rax]
0x140028853  movups  xmmword ptr [rax-48h], xmm0
0x140028857  movups  xmm1, xmmword ptr [rax+10h]
0x14002885b  movups  xmmword ptr [rax-38h], xmm1
0x14002885f  movups  xmm0, xmmword ptr [rax+20h]
0x140028863  movups  xmmword ptr [rax-28h], xmm0
0x140028867  movsd   xmm1, qword ptr [rax+30h]
0x14002886c  xorps   xmm0, xmm0
0x14002886f  movsd   qword ptr [rax-18h], xmm1
0x140028874  mov     byte ptr [rax-45h], 0
0x140028878  xor     eax, eax
0x14002887a  mov     rbx, [rsi+20h]
0x14002887e  mov     rdi, [rsi+28h]
0x140028882  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140028887  movups  xmmword ptr [rsp+98h+Event.Header.___u0], xmm0
0x14002888c  call    cs:__imp_KeInitializeEvent
0x140028893  nop     dword ptr [rax+rax+00h]
0x140028898  mov     rcx, cs:g_RecorderLog
0x14002889f  lea     rax, [rsp+98h+Event]
0x1400288a4  lea     r9, USBD_SyncCompletionRoutine
0x1400288ab  mov     [rsp+98h+Timeout], rax
0x1400288b0  mov     r8, rbp
0x1400288b3  mov     rdx, rbx
0x1400288b6  call    SetCompletionRoutine
0x1400288bb  mov     rdx, rbp; Irp
0x1400288be  mov     rcx, rdi; DeviceObject
0x1400288c1  call    cs:__imp_IofCallDriver
0x1400288c8  nop     dword ptr [rax+rax+00h]
0x1400288cd  mov     ebx, eax
0x1400288cf  cmp     eax, 103h
0x1400288d4  jnz     loc_1400289D2
0x1400288da  mov     rbx, cs:g_RecorderLog
0x1400288e1  lea     rax, [rsp+98h+arg_0]
0x1400288e9  xor     r9d, r9d; Alertable
0x1400288ec  mov     [rsp+98h+Timeout], rax; Timeout
0x1400288f1  xor     r8d, r8d; WaitMode
0x1400288f4  mov     [rsp+98h+arg_8], r12
0x1400288fc  xor     edx, edx; WaitReason
0x1400288fe  mov     qword ptr [rsp+98h+arg_0], 0FFFFFFFFDC3CBA00h
0x14002890a  lea     rcx, [rsp+98h+Event]; Object
0x14002890f  xor     edi, edi
0x140028911  call    cs:__imp_KeWaitForSingleObject
0x140028918  nop     dword ptr [rax+rax+00h]
0x14002891d  lea     r12, aEventWaitingFo; "event (waiting for sent irp to complete"...
0x140028924  mov     ecx, eax
0x140028926  cmp     eax, 102h
0x14002892b  jz      loc_140028C1D
0x140028931  test    ecx, ecx
0x140028933  js      loc_140028B33
0x140028939  mov     r12, [rsp+98h+arg_8]
0x140028941  mov     ebx, [rbp+30h]
0x140028944  test    ebx, ebx
0x140028946  jns     loc_140028CA7
0x14002894c  mov     edx, ebx
0x14002894e  mov     r8, rbp
0x140028951  mov     rcx, rsi
0x140028954  call    UsbcCompleteIrp
0x140028959  mov     eax, ebx
0x14002895b  jmp     short loc_1400289BD
0x14002895d  cmp     ebx, 1
0x140028960  jnz     short loc_1400289DF
0x140028962  mov     dword ptr [rbp+30h], 0
0x140028969  mov     rax, [rsi+20h]
0x14002896d  lea     r9, USBC_PnpComplete
0x140028974  mov     rdx, [rsi+28h]
0x140028978  mov     r8, rbp
0x14002897b  mov     [rsp+98h+var_70], rsi
0x140028980  mov     rcx, rsi
0x140028983  mov     [rsp+98h+Timeout], rax
0x140028988  call    UsbcForwardIrpWithCompletion
0x14002898d  mov     r14d, eax
0x140028990  test    dil, dil
0x140028993  jz      loc_140028B08
0x140028999  sub     ebx, 2
0x14002899c  jz      loc_140028B08
0x1400289a2  sub     ebx, 2
0x1400289a5  jz      loc_140028B08
0x1400289ab  sub     ebx, 1
0x1400289ae  jz      loc_140028B08
0x1400289b4  cmp     ebx, 1
0x1400289b7  jz      loc_140028B08
0x1400289bd  mov     rbx, [rsp+98h+arg_10]
0x1400289c5  add     rsp, 70h
0x1400289c9  pop     r15
0x1400289cb  pop     r14
0x1400289cd  pop     rdi
0x1400289ce  pop     rsi
0x1400289cf  pop     rbp
0x1400289d0  retn
0x1400289d2  test    eax, eax
0x1400289d4  jns     loc_140028941
0x1400289da  jmp     loc_140028944
0x1400289df  cmp     ebx, 17h; switch 24 cases
0x1400289e2  jbe     loc_140028AAC
0x1400289e8  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400289ef  jz      loc_140028969
0x1400289f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400289fc  cmp     word ptr [rax+48h], 0
0x140028a01  jz      loc_140028969
0x140028a07  mov     rax, [rsi+20h]
0x140028a0b  mov     r9d, 0Ch
0x140028a11  mov     rcx, [rsi+558h]
0x140028a18  mov     dl, 5
0x140028a1a  mov     byte ptr [rsp+98h+var_68], dil
0x140028a1f  mov     [rsp+98h+var_70], rax
0x140028a24  call    WPP_RECORDER_SF_qc
0x140028a29  jmp     loc_140028969
0x140028a2e  cmp     dil, 7
0x140028a32  jz      loc_140028BA3
0x140028a38  cmp     dil, 9
0x140028a3c  jz      loc_140028833
0x140028a42  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140028a49  jnz     loc_140028AD3
0x140028a4f  xor     r9d, r9d
0x140028a52  mov     [rsp+98h+Timeout], 0
0x140028a5b  xor     r8d, r8d
0x140028a5e  mov     dl, 1
0x140028a60  mov     rcx, rsi
0x140028a63  call    ParentSetD0
0x140028a68  test    eax, eax
0x140028a6a  jns     loc_140028833
0x140028a70  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140028a77  jz      loc_140028833
0x140028a7d  mov     rcx, [rsi+558h]
0x140028a84  mov     r9d, 0Bh
0x140028a8a  mov     dword ptr [rsp+98h+var_70], eax
0x140028a8e  mov     r8d, 8
0x140028a94  lea     rax, WPP_54beca300c4a353e079921b0991edb26_Traceguids
0x140028a9b  mov     dl, 2
0x140028a9d  mov     [rsp+98h+Timeout], rax
0x140028aa2  call    WPP_RECORDER_SF_d
0x140028aa7  jmp     loc_140028833
0x140028aac  lea     rdx, cs:140000000h
0x140028ab3  mov     ecx, ds:(jpt_140028ABD - 140000000h)[rdx+rdi*4]
0x140028aba  add     rcx, rdx
0x140028abd  jmp     rcx; switch jump
0x140028ac3  mov     rdx, rbp; jumptable 0000000140028ABD case 7
0x140028ac6  mov     rcx, rsi
0x140028ac9  call    QueryParentDeviceRelations
0x140028ace  jmp     loc_1400289BD
0x140028ad3  mov     rax, [rcx+20h]
0x140028ad7  mov     r9d, 0Ah
0x140028add  mov     rcx, [rcx+558h]
0x140028ae4  mov     dl, 4
0x140028ae6  mov     byte ptr [rsp+98h+var_68], dil
0x140028aeb  mov     [rsp+98h+var_70], rax
0x140028af0  call    WPP_RECORDER_SF_qc
0x140028af5  jmp     loc_140028A4F
0x140028afa  mov     rdx, rbp; jumptable 0000000140028ABD case 2
0x140028afd  mov     rcx, rsi
0x140028b00  call    FdoRemoveDevice
0x140028b05  mov     r14d, eax
0x140028b08  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140028b0f  jnz     short loc_140028B7A
0x140028b11  mov     eax, r14d
0x140028b14  jmp     loc_1400289BD
0x140028b19  cmp     byte ptr [rsi+551h], 0; jumptable 0000000140028ABD case 23
0x140028b20  jz      loc_140028962
0x140028b26  mov     rcx, rsi
0x140028b29  call    UnregisterCompositeDevice
0x140028b2e  jmp     loc_140028962
0x140028b33  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140028b3a  jz      loc_140028939
0x140028b40  mov     rax, gs:188h
0x140028b49  mov     r9d, 3Eh ; '>'
0x140028b4f  mov     [rsp+98h+var_60], r12
0x140028b54  mov     [rsp+98h+var_68], rax
0x140028b59  mov     dword ptr [rsp+98h+var_70], ecx
0x140028b5d  mov     rcx, rbx
0x140028b60  call    WPP_RECORDER_SF_dqs
0x140028b65  jmp     loc_140028939
0x140028b6a  mov     rdx, rbp; jumptable 0000000140028ABD case 0
0x140028b6d  mov     rcx, rsi; int
0x140028b70  call    StartParentFdo
0x140028b75  mov     r14d, eax
0x140028b78  jmp     short loc_140028B08
0x140028b7a  mov     rax, [rsi+20h]
0x140028b7e  mov     rcx, [rsi+558h]
0x140028b85  mov     [rsp+98h+var_58], r14d
0x140028b8a  mov     [rsp+98h+var_60], rbp
0x140028b8f  mov     byte ptr [rsp+98h+var_68], dil
0x140028b94  mov     [rsp+98h+var_70], rax
0x140028b99  call    WPP_RECORDER_SF_qcqd
0x140028b9e  jmp     loc_140028B11
0x140028ba3  cmp     dword ptr [r14+8], 0
0x140028ba8  jz      loc_140028A42
0x140028bae  jmp     loc_140028833
0x140028bb3  mov     r8d, 504F5453h; jumptable 0000000140028ABD case 5
0x140028bb9  mov     dword ptr [rsi+0Ch], 4
0x140028bc0  mov     rcx, rsi
0x140028bc3  call    DisableIdleTimer
0x140028bc8  mov     dl, 1
0x140028bca  mov     rcx, rsi
0x140028bcd  call    CancelFdoIdleIrp
0x140028bd2  jmp     loc_140028962
0x140028bd7  cmp     dword ptr [rsi+0Ch], 4; jumptable 0000000140028ABD case 6
0x140028bdb  jnz     short loc_140028BED
0x140028bdd  mov     r8d, 504F5453h
0x140028be3  mov     dl, 1
0x140028be5  mov     rcx, rsi
0x140028be8  call    EnableIdleTimer
0x140028bed  mov     dword ptr [rsi+0Ch], 2
0x140028bf4  jmp     loc_140028962
0x140028bf9  mov     rdx, rbp; jumptable 0000000140028ABD case 4
0x140028bfc  mov     rcx, rsi
0x140028bff  call    HandleFdoStop
0x140028c04  jmp     loc_140028969
0x140028c09  mov     rdx, rbp; jumptable 0000000140028ABD case 22
0x140028c0c  mov     rcx, rsi
0x140028c0f  xor     ebx, ebx
0x140028c11  call    HandleFdoDeviceUsageNotification
0x140028c16  xor     edx, edx
0x140028c18  jmp     loc_14002894E
0x140028c1d  mov     rdx, gs:188h
0x140028c26  lea     rcx, aUsbccgpWatchdo; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x140028c2d  inc     edi
0x140028c2f  mov     r9, r12
0x140028c32  mov     r8d, edi
0x140028c35  call    cs:__imp_DbgPrint
0x140028c3c  nop     dword ptr [rax+rax+00h]
0x140028c41  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140028c48  jz      short loc_140028C6F
0x140028c4a  mov     rax, gs:188h
0x140028c53  mov     r9d, 3Dh ; '='
0x140028c59  mov     [rsp+98h+var_60], r12
0x140028c5e  mov     rcx, rbx
0x140028c61  mov     dword ptr [rsp+98h+var_68], edi
0x140028c65  mov     [rsp+98h+var_70], rax
0x140028c6a  call    WPP_RECORDER_SF_qds
0x140028c6f  lea     rax, [rsp+98h+arg_0]
0x140028c77  xor     r9d, r9d; Alertable
0x140028c7a  xor     r8d, r8d; WaitMode
0x140028c7d  mov     [rsp+98h+Timeout], rax; Timeout
0x140028c82  xor     edx, edx; WaitReason
0x140028c84  lea     rcx, [rsp+98h+Event]; Object
0x140028c89  call    cs:__imp_KeWaitForSingleObject
0x140028c90  nop     dword ptr [rax+rax+00h]
0x140028c95  mov     ecx, eax
0x140028c97  cmp     eax, 102h
0x140028c9c  jz      loc_140028C1D
0x140028ca2  jmp     loc_140028931
0x140028ca7  mov     rcx, [r14+8]
0x140028cab  or      dword ptr [rcx+4], 200h
0x140028cb2  jmp     loc_14002894C
```
