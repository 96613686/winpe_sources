# USBC_AddDevice

- ea: `0x14002a2e0`
- end: `0x14002a825`
- name: `USBC_AddDevice`
- size: `1349`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x1400083c8`
- `0x1400088b4`
- `0x14000a6cc`
- `0x14000b4bc`
- `0x14000c7e8`
- `0x14000e584`
- `0x140015100`
- `0x140028d78`
- `0x14002a2e0`
- `0x14002a82c`
- `0x14002a9b0`
- `0x14002ab6c`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14002a328`
- `ntoskrnl!IoCreateDevice` at `0x14002a328`
- `ntoskrnl!KeInitializeEvent` at `0x14002a471`
- `ntoskrnl!KeInitializeEvent` at `0x14002a489`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4a1`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4b9`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4d1`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4e9`
- `ntoskrnl!KeInitializeEvent` at `0x14002a471`
- `ntoskrnl!KeInitializeEvent` at `0x14002a489`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4a1`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4b9`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4d1`
- `ntoskrnl!KeInitializeEvent` at `0x14002a4e9`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14002a5a4`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14002a5a4`
- `ntoskrnl!KeInitializeTimer` at `0x14002a4fc`
- `ntoskrnl!KeInitializeTimer` at `0x14002a530`
- `ntoskrnl!KeInitializeTimer` at `0x14002a4fc`
- `ntoskrnl!KeInitializeTimer` at `0x14002a530`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14002a570`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14002a570`
- `ntoskrnl!IoDeleteDevice` at `0x14002a76a`
- `ntoskrnl!IoDeleteDevice` at `0x14002a76a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a394`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3a7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3ca`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a444`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a591`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a394`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3a7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3ca`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a3dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a444`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a591`
- `ntoskrnl!KeInitializeMutex` at `0x14002a3f2`
- `ntoskrnl!KeInitializeMutex` at `0x14002a407`
- `ntoskrnl!KeInitializeMutex` at `0x14002a3f2`
- `ntoskrnl!KeInitializeMutex` at `0x14002a407`
- `ntoskrnl!IoDetachDevice` at `0x14002a653`
- `ntoskrnl!IoDetachDevice` at `0x14002a653`
- `ntoskrnl!KeInitializeDpc` at `0x14002a519`
- `ntoskrnl!KeInitializeDpc` at `0x14002a54d`
- `ntoskrnl!KeInitializeDpc` at `0x14002a519`
- `ntoskrnl!KeInitializeDpc` at `0x14002a54d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002a5e2`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002a5e2`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14002a6f8`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14002a6f8`

## pseudocode

```c
__int64 __fastcall USBC_AddDevice(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2)
{
  NTSTATUS IdleIrp; // eax
  int v5; // edx
  unsigned int v6; // edi
  _DWORD *DeviceExtension; // rbx
  _DWORD *v8; // rbx
  PDEVICE_OBJECT v9; // rax
  PIO_WORKITEM WorkItem; // rax
  int v11; // edx
  struct _DEVICE_OBJECT *v12; // rcx
  __int64 v13; // rcx
  int v14; // r9d
  ULONG v15; // r8d
  ULONG v16; // r9d
  int v17; // edx
  int v18; // eax
  int v19; // edx
  PDEVICE_OBJECT SourceDevice; // [rsp+A0h] [rbp+58h] BYREF

  SourceDevice = 0;
  IdleIrp = IoCreateDevice(a1, 0x570u, 0, 0x22u, 0x80u, 0, &SourceDevice);
  v6 = IdleIrp;
  if ( IdleIrp < 0 )
  {
    v8 = 0;
    SourceDevice = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v13) = g_RecorderLog;
      v14 = 15;
LABEL_14:
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(v13, v5, 8, v14, (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids, IdleIrp);
    }
LABEL_7:
    if ( SourceDevice )
    {
      if ( v8 )
      {
        v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)v8 + 5);
        if ( v12 )
          IoDetachDevice(v12);
        FreeParentFDOResources(v8);
      }
      else
      {
        IoDeleteDevice(SourceDevice);
      }
    }
    return v6;
  }
  DeviceExtension = SourceDevice->DeviceExtension;
  memset(DeviceExtension, 0, 0x570u);
  *((_QWORD *)DeviceExtension + 3) = a1;
  *((_BYTE *)DeviceExtension + 4) = 1;
  *DeviceExtension = 1130525525;
  v8 = DeviceExtension + 2;
  *v8 = 1131373638;
  *((_QWORD *)v8 + 3) = a2;
  *((_QWORD *)v8 + 4) = SourceDevice;
  *((_QWORD *)v8 + 1) = 1;
  v8[1] = 1;
  AllocateDeviceIFRLog(v8);
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 73);
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 50);
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 87);
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 10);
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 32);
  KeInitializeMutex((PRKMUTEX)(v8 + 226), 0);
  KeInitializeMutex((PRKMUTEX)(v8 + 130), 0);
  *((_QWORD *)v8 + 77) = v8 + 152;
  *((_QWORD *)v8 + 76) = v8 + 152;
  *((_QWORD *)v8 + 80) = v8 + 158;
  *((_QWORD *)v8 + 79) = v8 + 158;
  *((_QWORD *)v8 + 34) = v8 + 66;
  *((_QWORD *)v8 + 33) = v8 + 66;
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 43);
  *((_BYTE *)v8 + 352) = 0;
  *((_QWORD *)v8 + 46) = v8 + 90;
  *((_QWORD *)v8 + 45) = v8 + 90;
  KeInitializeEvent((PRKEVENT)v8 + 13, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)(v8 + 104), NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)v8 + 40, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)v8 + 12, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)v8 + 32, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)(v8 + 218), NotificationEvent, 1u);
  KeInitializeTimer((PKTIMER)v8 + 11);
  KeInitializeDpc((PRKDPC)(v8 + 198), CheckParentIdleDpc, v8);
  v8[1] = 1;
  KeInitializeTimer((PKTIMER)(v8 + 248));
  KeInitializeDpc((PRKDPC)(v8 + 264), PdoStartTimeoutDpc, v8);
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 50), 0x43627355u, 0, 0, 0x20u);
  *((_QWORD *)v8 + 30) = v8 + 58;
  *((_QWORD *)v8 + 29) = v8 + 58;
  KeInitializeSpinLock((PKSPIN_LOCK)v8 + 31);
  v9 = IoAttachDeviceToDeviceStack(SourceDevice, a2);
  *((_QWORD *)v8 + 5) = v9;
  if ( !v9 )
  {
    v6 = -1073741810;
    goto LABEL_7;
  }
  SourceDevice->Flags |= v9->Flags & 0x2000;
  IdleIrp = AllocateIdleIrp(v8);
  v6 = IdleIrp;
  if ( IdleIrp < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_7;
    v13 = *((_QWORD *)v8 + 171);
    v14 = 16;
    goto LABEL_14;
  }
  WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)v8 + 4));
  *((_QWORD *)v8 + 81) = WorkItem;
  if ( !WorkItem )
  {
    v6 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_(*((_QWORD *)v8 + 171), v11, 8, 17, (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids);
    }
    goto LABEL_7;
  }
  GetCapabilitiesFromRegistry(v8);
  GetIdleTimeoutPeriodFromRegistry(v8);
  if ( USBD_CreateHandle(SourceDevice, *((PDEVICE_OBJECT *)v8 + 5), v15, v16, (USBD_HANDLE *)v8 + 168) < 0
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_q(
      *((_QWORD *)v8 + 171),
      v17,
      1,
      18,
      (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids,
      (char)SourceDevice);
  }
  SourceDevice->Flags &= ~0x80u;
  v18 = PoDirectedDripsSetDeviceFlags(a2, 6);
  v6 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)v8 + 171),
        v19,
        1,
        19,
        (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids,
        (char)SourceDevice,
        v18);
    }
    v6 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)v8 + 171),
      v19,
      1,
      20,
      (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids,
      (char)SourceDevice);
  }
  return v6;
}

```

## disassembly

```asm
0x14002a2e0  push    rbp
0x14002a2e2  push    rbx
0x14002a2e3  push    rsi
0x14002a2e4  push    rdi
0x14002a2e5  push    r12
0x14002a2e7  push    r13
0x14002a2e9  push    r14
0x14002a2eb  push    r15
0x14002a2ed  mov     rbp, rsp
0x14002a2f0  sub     rsp, 48h
0x14002a2f4  xor     r12d, r12d
0x14002a2f7  lea     rax, [rbp+SourceDevice]
0x14002a2fb  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14002a300  mov     r15, rdx
0x14002a303  mov     r14d, 570h
0x14002a309  mov     [rsp+48h+Exclusive], r12b; Exclusive
0x14002a30e  xor     r8d, r8d; DeviceName
0x14002a311  mov     [rbp+SourceDevice], r12
0x14002a315  lea     r9d, [r12+22h]; DeviceType
0x14002a31a  mov     [rsp+48h+DeviceCharacteristics], 80h; DeviceCharacteristics
0x14002a322  mov     edx, r14d; DeviceExtensionSize
0x14002a325  mov     rsi, rcx
0x14002a328  call    cs:__imp_IoCreateDevice
0x14002a32f  nop     dword ptr [rax+rax+00h]
0x14002a334  mov     edi, eax
0x14002a336  test    eax, eax
0x14002a338  js      loc_14002A72F
0x14002a33e  mov     rax, [rbp+SourceDevice]
0x14002a342  mov     r8d, r14d; Size
0x14002a345  xor     edx, edx; Val
0x14002a347  mov     rbx, [rax+40h]
0x14002a34b  mov     rcx, rbx; void *
0x14002a34e  call    memset
0x14002a353  lea     r13d, [r12+1]
0x14002a358  mov     [rbx+18h], rsi
0x14002a35c  mov     [rbx+4], r13b
0x14002a360  mov     edi, 43627355h
0x14002a365  mov     [rbx], edi
0x14002a367  add     rbx, 8
0x14002a36b  mov     rcx, rbx
0x14002a36e  mov     dword ptr [rbx], 436F6446h
0x14002a374  mov     [rbx+18h], r15
0x14002a378  mov     rax, [rbp+SourceDevice]
0x14002a37c  mov     [rbx+20h], rax
0x14002a380  mov     [rbx+8], r13
0x14002a384  mov     [rbx+4], r13d
0x14002a388  call    AllocateDeviceIFRLog
0x14002a38d  lea     rcx, [rbx+248h]; SpinLock
0x14002a394  call    cs:__imp_KeInitializeSpinLock
0x14002a39b  nop     dword ptr [rax+rax+00h]
0x14002a3a0  lea     rcx, [rbx+190h]; SpinLock
0x14002a3a7  call    cs:__imp_KeInitializeSpinLock
0x14002a3ae  nop     dword ptr [rax+rax+00h]
0x14002a3b3  lea     rcx, [rbx+2B8h]; SpinLock
0x14002a3ba  call    cs:__imp_KeInitializeSpinLock
0x14002a3c1  nop     dword ptr [rax+rax+00h]
0x14002a3c6  lea     rcx, [rbx+50h]; SpinLock
0x14002a3ca  call    cs:__imp_KeInitializeSpinLock
0x14002a3d1  nop     dword ptr [rax+rax+00h]
0x14002a3d6  lea     rcx, [rbx+100h]; SpinLock
0x14002a3dd  call    cs:__imp_KeInitializeSpinLock
0x14002a3e4  nop     dword ptr [rax+rax+00h]
0x14002a3e9  lea     rcx, [rbx+388h]; Mutex
0x14002a3f0  xor     edx, edx; Level
0x14002a3f2  call    cs:__imp_KeInitializeMutex
0x14002a3f9  nop     dword ptr [rax+rax+00h]
0x14002a3fe  lea     rcx, [rbx+208h]; Mutex
0x14002a405  xor     edx, edx; Level
0x14002a407  call    cs:__imp_KeInitializeMutex
0x14002a40e  nop     dword ptr [rax+rax+00h]
0x14002a413  lea     rax, [rbx+260h]
0x14002a41a  mov     [rax+8], rax
0x14002a41e  lea     rcx, [rbx+158h]; SpinLock
0x14002a425  mov     [rax], rax
0x14002a428  lea     rax, [rbx+278h]
0x14002a42f  mov     [rax+8], rax
0x14002a433  mov     [rax], rax
0x14002a436  lea     rax, [rbx+108h]
0x14002a43d  mov     [rax+8], rax
0x14002a441  mov     [rax], rax
0x14002a444  call    cs:__imp_KeInitializeSpinLock
0x14002a44b  nop     dword ptr [rax+rax+00h]
0x14002a450  lea     rax, [rbx+168h]
0x14002a457  mov     [rbx+160h], r12b
0x14002a45e  lea     rcx, [rbx+138h]; Event
0x14002a465  mov     [rax+8], rax
0x14002a469  mov     r8b, r13b; State
0x14002a46c  mov     [rax], rax
0x14002a46f  xor     edx, edx; Type
0x14002a471  call    cs:__imp_KeInitializeEvent
0x14002a478  nop     dword ptr [rax+rax+00h]
0x14002a47d  lea     rcx, [rbx+1A0h]; Event
0x14002a484  mov     r8b, r13b; State
0x14002a487  xor     edx, edx; Type
0x14002a489  call    cs:__imp_KeInitializeEvent
0x14002a490  nop     dword ptr [rax+rax+00h]
0x14002a495  lea     rcx, [rbx+3C0h]; Event
0x14002a49c  mov     r8b, r13b; State
0x14002a49f  xor     edx, edx; Type
0x14002a4a1  call    cs:__imp_KeInitializeEvent
0x14002a4a8  nop     dword ptr [rax+rax+00h]
0x14002a4ad  lea     rcx, [rbx+120h]; Event
0x14002a4b4  mov     r8b, r13b; State
0x14002a4b7  xor     edx, edx; Type
0x14002a4b9  call    cs:__imp_KeInitializeEvent
0x14002a4c0  nop     dword ptr [rax+rax+00h]
0x14002a4c5  lea     rcx, [rbx+300h]; Event
0x14002a4cc  mov     r8b, r13b; State
0x14002a4cf  xor     edx, edx; Type
0x14002a4d1  call    cs:__imp_KeInitializeEvent
0x14002a4d8  nop     dword ptr [rax+rax+00h]
0x14002a4dd  lea     rcx, [rbx+368h]; Event
0x14002a4e4  mov     r8b, r13b; State
0x14002a4e7  xor     edx, edx; Type
0x14002a4e9  call    cs:__imp_KeInitializeEvent
0x14002a4f0  nop     dword ptr [rax+rax+00h]
0x14002a4f5  lea     rcx, [rbx+2C0h]; Timer
0x14002a4fc  call    cs:__imp_KeInitializeTimer
0x14002a503  nop     dword ptr [rax+rax+00h]
0x14002a508  lea     rcx, [rbx+318h]; Dpc
0x14002a50f  mov     r8, rbx; DeferredContext
0x14002a512  lea     rdx, CheckParentIdleDpc; DeferredRoutine
0x14002a519  call    cs:__imp_KeInitializeDpc
0x14002a520  nop     dword ptr [rax+rax+00h]
0x14002a525  lea     rcx, [rbx+3E0h]; Timer
0x14002a52c  mov     [rbx+4], r13d
0x14002a530  call    cs:__imp_KeInitializeTimer
0x14002a537  nop     dword ptr [rax+rax+00h]
0x14002a53c  lea     rcx, [rbx+420h]; Dpc
0x14002a543  mov     r8, rbx; DeferredContext
0x14002a546  lea     rdx, PdoStartTimeoutDpc; DeferredRoutine
0x14002a54d  call    cs:__imp_KeInitializeDpc
0x14002a554  nop     dword ptr [rax+rax+00h]
0x14002a559  lea     rcx, [rbx+0C8h]; Lock
0x14002a560  mov     [rsp+48h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x14002a568  xor     r9d, r9d; HighWatermark
0x14002a56b  xor     r8d, r8d; MaxLockedMinutes
0x14002a56e  mov     edx, edi; AllocateTag
0x14002a570  call    cs:__imp_IoInitializeRemoveLockEx
0x14002a577  nop     dword ptr [rax+rax+00h]
0x14002a57c  lea     rax, [rbx+0E8h]
0x14002a583  lea     rcx, [rbx+0F8h]; SpinLock
0x14002a58a  mov     [rax+8], rax
0x14002a58e  mov     [rax], rax
0x14002a591  call    cs:__imp_KeInitializeSpinLock
0x14002a598  nop     dword ptr [rax+rax+00h]
0x14002a59d  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x14002a5a1  mov     rdx, r15; TargetDevice
0x14002a5a4  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14002a5ab  nop     dword ptr [rax+rax+00h]
0x14002a5b0  mov     [rbx+28h], rax
0x14002a5b4  test    rax, rax
0x14002a5b7  jz      loc_14002A75C
0x14002a5bd  mov     rcx, [rbp+SourceDevice]
0x14002a5c1  mov     eax, [rax+30h]
0x14002a5c4  and     eax, 2000h
0x14002a5c9  or      [rcx+30h], eax
0x14002a5cc  mov     rcx, rbx
0x14002a5cf  call    AllocateIdleIrp
0x14002a5d4  mov     edi, eax
0x14002a5d6  test    eax, eax
0x14002a5d8  js      loc_14002A66C
0x14002a5de  mov     rcx, [rbx+20h]; DeviceObject
0x14002a5e2  call    cs:__imp_IoAllocateWorkItem
0x14002a5e9  nop     dword ptr [rax+rax+00h]
0x14002a5ee  mov     [rbx+288h], rax
0x14002a5f5  test    rax, rax
0x14002a5f8  jnz     loc_14002A6A8
0x14002a5fe  mov     edi, 0C000009Ah
0x14002a603  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a60a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002a611  jz      short loc_14002A637
0x14002a613  mov     rcx, [rbx+558h]
0x14002a61a  lea     r14, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002a621  lea     r9d, [r12+11h]
0x14002a626  mov     qword ptr [rsp+48h+DeviceCharacteristics], r14
0x14002a62b  lea     r8d, [r12+8]
0x14002a630  mov     dl, 2
0x14002a632  call    WPP_RECORDER_SF_
0x14002a637  cmp     [rbp+SourceDevice], r12
0x14002a63b  jz      loc_14002A71B
0x14002a641  test    rbx, rbx
0x14002a644  jz      loc_14002A766
0x14002a64a  mov     rcx, [rbx+28h]; TargetDevice
0x14002a64e  test    rcx, rcx
0x14002a651  jz      short loc_14002A65F
0x14002a653  call    cs:__imp_IoDetachDevice
0x14002a65a  nop     dword ptr [rax+rax+00h]
0x14002a65f  mov     rcx, rbx
0x14002a662  call    FreeParentFDOResources
0x14002a667  jmp     loc_14002A71B
0x14002a66c  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a673  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002a67a  jz      short loc_14002A637
0x14002a67c  mov     rcx, [rbx+558h]
0x14002a683  mov     r9d, 10h
0x14002a689  mov     dword ptr [rsp+48h+Exclusive], eax
0x14002a68d  lea     r14, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002a694  mov     dl, 2
0x14002a696  mov     qword ptr [rsp+48h+DeviceCharacteristics], r14
0x14002a69b  mov     r8d, 8
0x14002a6a1  call    WPP_RECORDER_SF_d
0x14002a6a6  jmp     short loc_14002A637
0x14002a6a8  mov     rcx, rbx
0x14002a6ab  call    GetCapabilitiesFromRegistry
0x14002a6b0  mov     rcx, rbx
0x14002a6b3  call    GetIdleTimeoutPeriodFromRegistry
0x14002a6b8  mov     rdx, [rbx+28h]; TargetDeviceObject
0x14002a6bc  lea     rax, [rbx+540h]
0x14002a6c3  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14002a6c7  mov     qword ptr [rsp+48h+DeviceCharacteristics], rax; USBDHandle
0x14002a6cc  call    USBD_CreateHandle
0x14002a6d1  lea     r14, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002a6d8  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002a6df  test    eax, eax
0x14002a6e1  js      loc_14002A778
0x14002a6e7  mov     rax, [rbp+SourceDevice]
0x14002a6eb  mov     edx, 6
0x14002a6f0  mov     rcx, r15
0x14002a6f3  btr     dword ptr [rax+30h], 7
0x14002a6f8  call    cs:__imp_PoDirectedDripsSetDeviceFlags
0x14002a6ff  nop     dword ptr [rax+rax+00h]
0x14002a704  mov     edi, eax
0x14002a706  test    eax, eax
0x14002a708  js      loc_14002A7C1
0x14002a70e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002a715  jnz     loc_14002A7FB
0x14002a71b  mov     eax, edi
0x14002a71d  add     rsp, 48h
0x14002a721  pop     r15
0x14002a723  pop     r14
0x14002a725  pop     r13
0x14002a727  pop     r12
0x14002a729  pop     rdi
0x14002a72a  pop     rsi
0x14002a72b  pop     rbx
0x14002a72c  pop     rbp
0x14002a72d  retn
0x14002a72f  mov     rbx, r12
0x14002a732  mov     [rbp+SourceDevice], r12
0x14002a736  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a73d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002a744  jz      loc_14002A637
0x14002a74a  mov     rcx, cs:g_RecorderLog
0x14002a751  mov     r9d, 0Fh
0x14002a757  jmp     loc_14002A689
0x14002a75c  mov     edi, 0C000000Eh
0x14002a761  jmp     loc_14002A637
0x14002a766  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14002a76a  call    cs:__imp_IoDeleteDevice
0x14002a771  nop     dword ptr [rax+rax+00h]
0x14002a776  jmp     short loc_14002A71B
0x14002a778  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002a77f  jz      loc_14002A6E7
0x14002a785  mov     rax, cs:WPP_GLOBAL_Control
0x14002a78c  cmp     [rax+48h], r12w
0x14002a791  jz      loc_14002A6E7
0x14002a797  mov     rax, [rbp+SourceDevice]
0x14002a79b  mov     r9d, 12h
0x14002a7a1  mov     rcx, [rbx+558h]
0x14002a7a8  mov     r8d, r13d
0x14002a7ab  mov     qword ptr [rsp+48h+Exclusive], rax
0x14002a7b0  mov     dl, 5
0x14002a7b2  mov     qword ptr [rsp+48h+DeviceCharacteristics], r14
0x14002a7b7  call    WPP_RECORDER_SF_q
0x14002a7bc  jmp     loc_14002A6E7
0x14002a7c1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002a7c8  jz      short loc_14002A7F3
0x14002a7ca  mov     rcx, [rbx+558h]
0x14002a7d1  mov     r9d, 13h
0x14002a7d7  mov     dword ptr [rsp+48h+DeviceObject], eax
0x14002a7db  mov     r8d, r13d
0x14002a7de  mov     rax, [rbp+SourceDevice]
0x14002a7e2  mov     dl, 2
0x14002a7e4  mov     qword ptr [rsp+48h+Exclusive], rax
0x14002a7e9  mov     qword ptr [rsp+48h+DeviceCharacteristics], r14
0x14002a7ee  call    WPP_RECORDER_SF_qD
0x14002a7f3  mov     edi, r12d
0x14002a7f6  jmp     loc_14002A70E
0x14002a7fb  mov     rax, [rbp+SourceDevice]
0x14002a7ff  mov     r9d, 14h
0x14002a805  mov     rcx, [rbx+558h]
0x14002a80c  mov     r8d, r13d
0x14002a80f  mov     qword ptr [rsp+48h+Exclusive], rax
0x14002a814  mov     dl, 4
0x14002a816  mov     qword ptr [rsp+48h+DeviceCharacteristics], r14
0x14002a81b  call    WPP_RECORDER_SF_q
0x14002a820  jmp     loc_14002A71B
```
