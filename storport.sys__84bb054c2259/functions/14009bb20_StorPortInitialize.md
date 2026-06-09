# StorPortInitialize

- ea: `0x14009bb20`
- end: `0x14009c319`
- name: `StorPortInitialize`
- size: `2041`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140197da0`

## callees

- `0x14003c170`
- `0x14009a9b0`
- `0x14009aa7c`
- `0x14009bb20`
- `0x14009d384`
- `0x14014b440`
- `0x140187cac`
- `0x14019089c`
- `0x140190900`
- `0x140190a30`
- `0x140190ad0`
- `0x140190dc0`
- `0x140190e54`
- `0x1401c8044`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009c249`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c2af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c249`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c2af`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14009c05b`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14009c05b`
- `ntoskrnl!IoCreateDevice` at `0x14009c27c`
- `ntoskrnl!IoCreateDevice` at `0x14009c27c`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14009c308`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14009c308`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14009c086`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14009c086`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14009c2c3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14009c2c3`
- `ntoskrnl!PcwRegister` at `0x14009bcbe`
- `ntoskrnl!PcwRegister` at `0x14009bd19`
- `ntoskrnl!PcwRegister` at `0x14009bd74`
- `ntoskrnl!PcwRegister` at `0x14009bdcf`
- `ntoskrnl!PcwRegister` at `0x14009be2a`
- `ntoskrnl!PcwRegister` at `0x14009be85`
- `ntoskrnl!PcwRegister` at `0x14009bee0`
- `ntoskrnl!PcwRegister` at `0x14009bf3b`
- `ntoskrnl!PcwRegister` at `0x14009bcbe`
- `ntoskrnl!PcwRegister` at `0x14009bd19`
- `ntoskrnl!PcwRegister` at `0x14009bd74`
- `ntoskrnl!PcwRegister` at `0x14009bdcf`
- `ntoskrnl!PcwRegister` at `0x14009be2a`
- `ntoskrnl!PcwRegister` at `0x14009be85`
- `ntoskrnl!PcwRegister` at `0x14009bee0`
- `ntoskrnl!PcwRegister` at `0x14009bf3b`

## pseudocode

```c
__int64 __fastcall StorPortInitialize(PDRIVER_OBJECT DriverObject, __int64 a2, unsigned int *a3, __int64 a4)
{
  char v8; // r13
  __int64 v9; // rcx
  NTSTATUS v10; // ebx
  _DWORD *v11; // rdx
  char v12; // r12
  PDEVICE_OBJECT v13; // rcx
  void (__fastcall *v14)(PDRIVER_OBJECT, __int64); // rax
  __int64 PortData; // rsi
  void (__fastcall *v16)(PDRIVER_OBJECT); // rax
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int inited; // eax
  NTSTATUS v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-39h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+90h] [rbp-29h] BYREF
  struct _PCW_REGISTRATION_INFORMATION Info; // [rsp+A0h] [rbp-19h] BYREF
  PVOID DriverObjectExtension; // [rsp+120h] [rbp+67h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+128h] [rbp+6Fh] BYREF

  DeviceObject = 0;
  DriverObjectExtension = 0;
  v8 = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  memset(&Info, 0, 52);
  if ( !InitSecurityCookie )
  {
    _security_init_cookie();
    InitSecurityCookie = 1;
  }
  if ( !DriverObject || !a2 || !a3 )
    goto LABEL_21;
  v9 = *a3;
  if ( (_DWORD)v9 != 208 && (_DWORD)v9 != 176 && (_DWORD)v9 != 136
    || !*((_QWORD *)a3 + 1)
    || !*((_QWORD *)a3 + 4)
    || !*((_QWORD *)a3 + 5) )
  {
    goto LABEL_9;
  }
  v11 = a3 + 46;
  if ( (_DWORD)v9 == 208 && (*v11 & 0x40000) != 0 )
  {
    if ( *((_QWORD *)a3 + 2) )
      goto LABEL_9;
  }
  else
  {
    if ( !*((_QWORD *)a3 + 2) )
    {
LABEL_9:
      v10 = -1073741735;
      goto LABEL_52;
    }
    if ( (_DWORD)v9 != 208 )
      goto LABEL_22;
  }
  if ( (*v11 & 0x4000) != 0 && (a3[47] & 2) == 0 )
  {
LABEL_21:
    v10 = -1073741811;
    goto LABEL_52;
  }
LABEL_22:
  v12 = 0;
  if ( _InterlockedIncrement(&InitializeCount) == 1 )
  {
    v12 = 1;
    if ( !IsWppInitialized )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = 0;
      WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_wppCtlGuid;
      WPP_MAIN_CB.NextDevice = 0;
      WPP_MAIN_CB.CurrentIrp = 0;
      WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
      WppLoadTracingSupport(v9, v11);
      WPP_MAIN_CB.CurrentIrp = 0;
      WppInitKm();
      IsWppInitialized = 1;
    }
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L"&(";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationUnitReadCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))RaUnitReadIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfUnitReadCounterSet, &Info) < 0 )
      SpPerfUnitReadCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L"(*";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationUnitWriteCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))RaUnitWriteIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfUnitWriteCounterSet, &Info) < 0 )
      SpPerfUnitWriteCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L".0";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationUnitTransferCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))RaUnitTransferIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfUnitTransferCounterSet, &Info) < 0 )
      SpPerfUnitTransferCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L"&(";
    *(_QWORD *)&Info.CounterCount = 2;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationUnitQueueCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))RaUnitQueueCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfUnitQueueCounterSet, &Info) < 0 )
      SpPerfUnitQueueCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L":<";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationNamespaceReadCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))NvmeNamespaceReadIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfNamespaceReadCounterSet, &Info) < 0 )
      SpPerfNamespaceReadCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L"<>";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationNamespaceWriteCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))NvmeNamespaceWriteIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfNamespaceWriteCounterSet, &Info) < 0 )
      SpPerfNamespaceWriteCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L"BD";
    *(_QWORD *)&Info.CounterCount = 56;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationNamespaceTransferCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))NvmeNamespaceTransferIoCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfNamespaceTransferCounterSet, &Info) < 0 )
      SpPerfNamespaceTransferCounterSet = 0;
    *(_QWORD *)&Info.Version = 256;
    Info.Name = (const _UNICODE_STRING *)L":<";
    *(_QWORD *)&Info.CounterCount = 2;
    Info.Counters = (_PCW_COUNTER_DESCRIPTOR *)`SpPerfInitRegistrationInformationNamespaceQueueCounterSet'::`2'::Descriptors;
    *(_QWORD *)&Info.Flags = 0;
    Info.Callback = (int (__fastcall *)(_PCW_CALLBACK_TYPE, _PCW_CALLBACK_INFORMATION *, void *))NvmeNamespaceQueueCounterSetCallback;
    Info.CallbackContext = 0;
    if ( PcwRegister(&SpPerfNamespaceQueueCounterSet, &Info) < 0 )
      SpPerfNamespaceQueueCounterSet = 0;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqq(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_3cacd4df8bbd375787950e28c3d16483_Traceguids,
      DriverObject,
      a2,
      a3,
      a4);
  }
  if ( *a3 == 176 || *a3 == 208 && (a3[46] & 1) != 0 )
  {
    v14 = (void (__fastcall *)(PDRIVER_OBJECT, __int64))*((_QWORD *)a3 + 20);
    if ( v14 )
    {
      v14(DriverObject, a2);
      v8 = 1;
    }
  }
  PortData = RaidGetPortData(v13, v11);
  if ( !PortData )
  {
    v10 = -1073741801;
    goto LABEL_52;
  }
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, DriverEntry);
  if ( !DriverObjectExtension )
  {
    v10 = IoAllocateDriverObjectExtension(DriverObject, DriverEntry, 0x70u, &DriverObjectExtension);
    if ( v10 < 0 )
      goto LABEL_52;
    RaCreateDriver(DriverObjectExtension);
    v10 = RaInitializeDriver(DriverObjectExtension, DriverObject, PortData, a2);
    if ( v10 < 0 )
      goto LABEL_52;
  }
  v21 = *a3;
  if ( *a3 == 208 )
  {
    if ( (Microsoft_Windows_StorPortEnableBits & 0x10) != 0 )
      McTemplateK0dqddddddiiiii_EtwWriteTransfer(
        v19,
        v18,
        v20,
        208,
        a3[1],
        a3[16],
        a3[17],
        a3[18],
        a3[46],
        a3[47],
        a3[48],
        *((_QWORD *)a3 + 17),
        *((_QWORD *)a3 + 18),
        *((_QWORD *)a3 + 19),
        *((_QWORD *)a3 + 20),
        *((_QWORD *)a3 + 21));
  }
  else if ( v21 == 176 )
  {
    if ( (Microsoft_Windows_StorPortEnableBits & 0x10) != 0 )
      McTemplateK0dqddddddiiiii_EtwWriteTransfer(
        v19,
        v18,
        v20,
        176,
        a3[1],
        a3[16],
        a3[17],
        a3[18],
        0,
        0,
        0,
        *((_QWORD *)a3 + 17),
        *((_QWORD *)a3 + 18),
        *((_QWORD *)a3 + 19),
        *((_QWORD *)a3 + 20),
        *((_QWORD *)a3 + 21));
  }
  else if ( (Microsoft_Windows_StorPortEnableBits & 0x10) != 0 )
  {
    McTemplateK0dqddddddiiiii_EtwWriteTransfer(
      v19,
      v18,
      v20,
      v21,
      a3[1],
      a3[16],
      a3[17],
      a3[18],
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0);
  }
  inited = RaSaveDriverInitData(DriverObjectExtension, a3);
  v10 = inited;
  if ( inited >= 0 )
    v8 = 0;
  *((_WORD *)a3 + 52) |= 0x10u;
  if ( CreateControlObject && *a3 == 208 && (a3[46] & 0x8000) != 0 && !StorpControl )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\StorportControl");
    v23 = IoCreateDevice(DriverObject, 4u, &DestinationString, 0x15u, 0x100u, 0, &DeviceObject);
    if ( v23 < 0 )
    {
      if ( (byte_140177437 & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(v24, EventStorportControlCreationFailed, v25, (unsigned int)v23);
    }
    else
    {
      StorpControl = DeviceObject;
      *(_DWORD *)DeviceObject->DeviceExtension = 1146246738;
      RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\StorportControl");
      IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
    }
    v10 = 0;
  }
  else if ( inited < 0 )
  {
LABEL_52:
    if ( _InterlockedExchangeAdd(&InitializeCount, 0xFFFFFFFF) == 1 && IsWppInitialized )
    {
      WppCleanupKm();
      IsWppInitialized = 0;
    }
    if ( DriverObjectExtension )
      RaDeleteDriver();
    DriverObjectExtension = 0;
    if ( v8 )
    {
      v16 = (void (__fastcall *)(PDRIVER_OBJECT))*((_QWORD *)a3 + 21);
      if ( v16 )
        v16(DriverObject);
    }
    return (unsigned int)v10;
  }
  if ( v12 )
    IoRegisterDriverReinitialization(DriverObject, RaDriverReinitialization, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14009bb20  mov     [rsp-8+arg_10], rbx
0x14009bb25  push    rbp
0x14009bb26  push    rsi
0x14009bb27  push    rdi
0x14009bb28  push    r12
0x14009bb2a  push    r13
0x14009bb2c  push    r14
0x14009bb2e  push    r15
0x14009bb30  lea     rbp, [rsp-27h]
0x14009bb35  sub     rsp, 0E0h
0x14009bb3c  xorps   xmm0, xmm0
0x14009bb3f  xor     esi, esi
0x14009bb41  xor     eax, eax
0x14009bb43  mov     [rbp+57h+arg_8], rsi
0x14009bb47  cmp     cs:InitSecurityCookie, sil
0x14009bb4e  mov     rbx, r9
0x14009bb51  mov     rdi, r8
0x14009bb54  mov     [rbp+57h+DriverObjectExtension], rsi
0x14009bb58  mov     r15, rdx
0x14009bb5b  mov     [rbp+57h+Info.Flags], eax
0x14009bb5e  mov     r14, rcx
0x14009bb61  mov     r13b, sil
0x14009bb64  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14009bb68  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm0
0x14009bb6c  movups  xmmword ptr [rbp+57h+Info.Version], xmm0
0x14009bb70  movups  xmmword ptr [rbp+57h+Info.CounterCount], xmm0
0x14009bb74  movups  xmmword ptr [rbp+57h+Info.Callback], xmm0
0x14009bb78  jnz     short loc_14009BB86
0x14009bb7a  call    __security_init_cookie
0x14009bb7f  mov     cs:InitSecurityCookie, 1
0x14009bb86  test    r14, r14
0x14009bb89  jz      short loc_14009BC03
0x14009bb8b  test    r15, r15
0x14009bb8e  jz      short loc_14009BC03
0x14009bb90  test    rdi, rdi
0x14009bb93  jz      short loc_14009BC03
0x14009bb95  mov     ecx, [rdi]
0x14009bb97  mov     eax, 0D0h
0x14009bb9c  cmp     ecx, eax
0x14009bb9e  jz      short loc_14009BBBA
0x14009bba0  cmp     ecx, 0B0h
0x14009bba6  jz      short loc_14009BBBA
0x14009bba8  cmp     ecx, 88h
0x14009bbae  jz      short loc_14009BBBA
0x14009bbb0  mov     ebx, 0C0000059h
0x14009bbb5  jmp     loc_14009BFE3
0x14009bbba  cmp     [rdi+8], rsi
0x14009bbbe  jz      short loc_14009BBB0
0x14009bbc0  cmp     [rdi+20h], rsi
0x14009bbc4  jz      short loc_14009BBB0
0x14009bbc6  cmp     [rdi+28h], rsi
0x14009bbca  jz      short loc_14009BBB0
0x14009bbcc  lea     rdx, [rdi+0B8h]
0x14009bbd3  cmp     ecx, eax
0x14009bbd5  jnz     short loc_14009BBE7
0x14009bbd7  test    dword ptr [rdx], 40000h
0x14009bbdd  jz      short loc_14009BBE7
0x14009bbdf  cmp     [rdi+10h], rsi
0x14009bbe3  jz      short loc_14009BBF1
0x14009bbe5  jmp     short loc_14009BBB0
0x14009bbe7  cmp     [rdi+10h], rsi
0x14009bbeb  jz      short loc_14009BBB0
0x14009bbed  cmp     ecx, eax
0x14009bbef  jnz     short loc_14009BC0D
0x14009bbf1  test    dword ptr [rdx], 4000h
0x14009bbf7  jz      short loc_14009BC0D
0x14009bbf9  mov     eax, [rdi+0BCh]
0x14009bbff  test    al, 2
0x14009bc01  jnz     short loc_14009BC0D
0x14009bc03  mov     ebx, 0C000000Dh
0x14009bc08  jmp     loc_14009BFE3
0x14009bc0d  mov     r12b, sil
0x14009bc10  mov     eax, 1
0x14009bc15  lock xadd cs:InitializeCount, eax
0x14009bc1d  inc     eax
0x14009bc1f  cmp     eax, 1
0x14009bc22  jnz     loc_14009BF52
0x14009bc28  cmp     cs:IsWppInitialized, sil
0x14009bc2f  mov     r12b, al
0x14009bc32  jnz     short loc_14009BC7A
0x14009bc34  lea     rax, WPP_ThisDir_CTLGUID_wppCtlGuid
0x14009bc3b  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14009bc42  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14009bc49  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14009bc50  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14009bc57  mov     cs:WPP_MAIN_CB.Timer, 1
0x14009bc62  call    WppLoadTracingSupport
0x14009bc67  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14009bc6e  call    WppInitKm
0x14009bc73  mov     cs:IsWppInitialized, r12b
0x14009bc7a  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationUnitReadCounterSet@@9@9; "&("
0x14009bc81  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bc89  mov     [rbp+57h+Info.Name], rax
0x14009bc8d  lea     rdx, [rbp+57h+Info]; Info
0x14009bc91  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationUnitReadCounterSet@@9@9; `SpPerfInitRegistrationInformationUnitReadCounterSet'::`2'::Descriptors
0x14009bc98  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009bca0  mov     [rbp+57h+Info.Counters], rax
0x14009bca4  lea     rcx, SpPerfUnitReadCounterSet; Registration
0x14009bcab  lea     rax, RaUnitReadIoCounterSetCallback
0x14009bcb2  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bcb6  mov     [rbp+57h+Info.Callback], rax
0x14009bcba  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bcbe  call    cs:__imp_PcwRegister
0x14009bcc5  nop     dword ptr [rax+rax+00h]
0x14009bcca  test    eax, eax
0x14009bccc  jns     short loc_14009BCD5
0x14009bcce  mov     cs:SpPerfUnitReadCounterSet, rsi
0x14009bcd5  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationUnitWriteCounterSet@@9@9; "(*"
0x14009bcdc  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bce4  mov     [rbp+57h+Info.Name], rax
0x14009bce8  lea     rdx, [rbp+57h+Info]; Info
0x14009bcec  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationUnitWriteCounterSet@@9@9; `SpPerfInitRegistrationInformationUnitWriteCounterSet'::`2'::Descriptors
0x14009bcf3  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009bcfb  mov     [rbp+57h+Info.Counters], rax
0x14009bcff  lea     rcx, SpPerfUnitWriteCounterSet; Registration
0x14009bd06  lea     rax, RaUnitWriteIoCounterSetCallback
0x14009bd0d  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bd11  mov     [rbp+57h+Info.Callback], rax
0x14009bd15  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bd19  call    cs:__imp_PcwRegister
0x14009bd20  nop     dword ptr [rax+rax+00h]
0x14009bd25  test    eax, eax
0x14009bd27  jns     short loc_14009BD30
0x14009bd29  mov     cs:SpPerfUnitWriteCounterSet, rsi
0x14009bd30  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationUnitTransferCounterSet@@9@9; ".0"
0x14009bd37  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bd3f  mov     [rbp+57h+Info.Name], rax
0x14009bd43  lea     rdx, [rbp+57h+Info]; Info
0x14009bd47  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationUnitTransferCounterSet@@9@9; `SpPerfInitRegistrationInformationUnitTransferCounterSet'::`2'::Descriptors
0x14009bd4e  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009bd56  mov     [rbp+57h+Info.Counters], rax
0x14009bd5a  lea     rcx, SpPerfUnitTransferCounterSet; Registration
0x14009bd61  lea     rax, RaUnitTransferIoCounterSetCallback
0x14009bd68  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bd6c  mov     [rbp+57h+Info.Callback], rax
0x14009bd70  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bd74  call    cs:__imp_PcwRegister
0x14009bd7b  nop     dword ptr [rax+rax+00h]
0x14009bd80  test    eax, eax
0x14009bd82  jns     short loc_14009BD8B
0x14009bd84  mov     cs:SpPerfUnitTransferCounterSet, rsi
0x14009bd8b  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationUnitQueueCounterSet@@9@9; "&("
0x14009bd92  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bd9a  mov     [rbp+57h+Info.Name], rax
0x14009bd9e  lea     rdx, [rbp+57h+Info]; Info
0x14009bda2  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationUnitQueueCounterSet@@9@9; `SpPerfInitRegistrationInformationUnitQueueCounterSet'::`2'::Descriptors
0x14009bda9  mov     qword ptr [rbp+57h+Info.CounterCount], 2
0x14009bdb1  mov     [rbp+57h+Info.Counters], rax
0x14009bdb5  lea     rcx, SpPerfUnitQueueCounterSet; Registration
0x14009bdbc  lea     rax, RaUnitQueueCounterSetCallback
0x14009bdc3  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bdc7  mov     [rbp+57h+Info.Callback], rax
0x14009bdcb  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bdcf  call    cs:__imp_PcwRegister
0x14009bdd6  nop     dword ptr [rax+rax+00h]
0x14009bddb  test    eax, eax
0x14009bddd  jns     short loc_14009BDE6
0x14009bddf  mov     cs:SpPerfUnitQueueCounterSet, rsi
0x14009bde6  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationNamespaceReadCounterSet@@9@9; ":<"
0x14009bded  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bdf5  mov     [rbp+57h+Info.Name], rax
0x14009bdf9  lea     rdx, [rbp+57h+Info]; Info
0x14009bdfd  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationNamespaceReadCounterSet@@9@9; `SpPerfInitRegistrationInformationNamespaceReadCounterSet'::`2'::Descriptors
0x14009be04  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009be0c  mov     [rbp+57h+Info.Counters], rax
0x14009be10  lea     rcx, SpPerfNamespaceReadCounterSet; Registration
0x14009be17  lea     rax, NvmeNamespaceReadIoCounterSetCallback
0x14009be1e  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009be22  mov     [rbp+57h+Info.Callback], rax
0x14009be26  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009be2a  call    cs:__imp_PcwRegister
0x14009be31  nop     dword ptr [rax+rax+00h]
0x14009be36  test    eax, eax
0x14009be38  jns     short loc_14009BE41
0x14009be3a  mov     cs:SpPerfNamespaceReadCounterSet, rsi
0x14009be41  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationNamespaceWriteCounterSet@@9@9; "<>"
0x14009be48  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009be50  mov     [rbp+57h+Info.Name], rax
0x14009be54  lea     rdx, [rbp+57h+Info]; Info
0x14009be58  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationNamespaceWriteCounterSet@@9@9; `SpPerfInitRegistrationInformationNamespaceWriteCounterSet'::`2'::Descriptors
0x14009be5f  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009be67  mov     [rbp+57h+Info.Counters], rax
0x14009be6b  lea     rcx, SpPerfNamespaceWriteCounterSet; Registration
0x14009be72  lea     rax, NvmeNamespaceWriteIoCounterSetCallback
0x14009be79  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009be7d  mov     [rbp+57h+Info.Callback], rax
0x14009be81  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009be85  call    cs:__imp_PcwRegister
0x14009be8c  nop     dword ptr [rax+rax+00h]
0x14009be91  test    eax, eax
0x14009be93  jns     short loc_14009BE9C
0x14009be95  mov     cs:SpPerfNamespaceWriteCounterSet, rsi
0x14009be9c  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationNamespaceTransferCounterSet@@9@9; "BD"
0x14009bea3  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009beab  mov     [rbp+57h+Info.Name], rax
0x14009beaf  lea     rdx, [rbp+57h+Info]; Info
0x14009beb3  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationNamespaceTransferCounterSet@@9@9; `SpPerfInitRegistrationInformationNamespaceTransferCounterSet'::`2'::Descriptors
0x14009beba  mov     qword ptr [rbp+57h+Info.CounterCount], 38h ; '8'
0x14009bec2  mov     [rbp+57h+Info.Counters], rax
0x14009bec6  lea     rcx, SpPerfNamespaceTransferCounterSet; Registration
0x14009becd  lea     rax, NvmeNamespaceTransferIoCounterSetCallback
0x14009bed4  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bed8  mov     [rbp+57h+Info.Callback], rax
0x14009bedc  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bee0  call    cs:__imp_PcwRegister
0x14009bee7  nop     dword ptr [rax+rax+00h]
0x14009beec  test    eax, eax
0x14009beee  jns     short loc_14009BEF7
0x14009bef0  mov     cs:SpPerfNamespaceTransferCounterSet, rsi
0x14009bef7  lea     rax, ?Name@?1??SpPerfInitRegistrationInformationNamespaceQueueCounterSet@@9@9; ":<"
0x14009befe  mov     qword ptr [rbp+57h+Info.Version], 100h
0x14009bf06  mov     [rbp+57h+Info.Name], rax
0x14009bf0a  lea     rdx, [rbp+57h+Info]; Info
0x14009bf0e  lea     rax, ?Descriptors@?1??SpPerfInitRegistrationInformationNamespaceQueueCounterSet@@9@9; `SpPerfInitRegistrationInformationNamespaceQueueCounterSet'::`2'::Descriptors
0x14009bf15  mov     qword ptr [rbp+57h+Info.CounterCount], 2
0x14009bf1d  mov     [rbp+57h+Info.Counters], rax
0x14009bf21  lea     rcx, SpPerfNamespaceQueueCounterSet; Registration
0x14009bf28  lea     rax, NvmeNamespaceQueueCounterSetCallback
0x14009bf2f  mov     qword ptr [rbp+57h+Info.Flags], rsi
0x14009bf33  mov     [rbp+57h+Info.Callback], rax
0x14009bf37  mov     [rbp+57h+Info.CallbackContext], rsi
0x14009bf3b  call    cs:__imp_PcwRegister
0x14009bf42  nop     dword ptr [rax+rax+00h]
0x14009bf47  test    eax, eax
0x14009bf49  jns     short loc_14009BF52
0x14009bf4b  mov     cs:SpPerfNamespaceQueueCounterSet, rsi
0x14009bf52  mov     rcx, cs:WPP_GLOBAL_Control
0x14009bf59  lea     rax, WPP_GLOBAL_Control
0x14009bf60  cmp     rcx, rax
0x14009bf63  jz      short loc_14009BF99
0x14009bf65  mov     eax, [rcx+2Ch]
0x14009bf68  test    al, 2
0x14009bf6a  jz      short loc_14009BF99
0x14009bf6c  cmp     byte ptr [rcx+29h], 4
0x14009bf70  jb      short loc_14009BF99
0x14009bf72  mov     rcx, [rcx+18h]
0x14009bf76  lea     r8, WPP_3cacd4df8bbd375787950e28c3d16483_Traceguids
0x14009bf7d  mov     [rsp+110h+DeviceObject], rbx
0x14009bf82  mov     edx, 0Ah
0x14009bf87  mov     qword ptr [rsp+110h+Exclusive], rdi
0x14009bf8c  mov     r9, r14
0x14009bf8f  mov     qword ptr [rsp+110h+DeviceCharacteristics], r15
0x14009bf94  call    WPP_SF_qqqq
0x14009bf99  mov     eax, [rdi]
0x14009bf9b  mov     ebx, 0B0h
0x14009bfa0  cmp     eax, ebx
0x14009bfa2  jz      short loc_14009BFB5
0x14009bfa4  cmp     eax, 0D0h
0x14009bfa9  jnz     short loc_14009BFCF
0x14009bfab  mov     eax, [rdi+0B8h]
0x14009bfb1  test    al, 1
0x14009bfb3  jz      short loc_14009BFCF
0x14009bfb5  mov     rax, [rdi+0A0h]
0x14009bfbc  test    rax, rax
0x14009bfbf  jz      short loc_14009BFCF
0x14009bfc1  mov     rdx, r15
0x14009bfc4  mov     rcx, r14
0x14009bfc7  call    _guard_dispatch_icall
0x14009bfcc  mov     r13b, 1
0x14009bfcf  call    RaidGetPortData
0x14009bfd4  mov     rsi, rax
0x14009bfd7  test    rax, rax
0x14009bfda  jnz     short loc_14009C051
0x14009bfdc  mov     ebx, 0C0000017h
0x14009bfe1  xor     esi, esi
0x14009bfe3  or      eax, 0FFFFFFFFh
0x14009bfe6  lock xadd cs:InitializeCount, eax
0x14009bfee  cmp     eax, 1
0x14009bff1  jnz     short loc_14009C008
0x14009bff3  cmp     cs:IsWppInitialized, sil
0x14009bffa  jz      short loc_14009C008
0x14009bffc  call    WppCleanupKm
0x14009c001  mov     cs:IsWppInitialized, sil
0x14009c008  mov     rcx, [rbp+57h+DriverObjectExtension]
0x14009c00c  test    rcx, rcx
0x14009c00f  jz      short loc_14009C016
0x14009c011  call    RaDeleteDriver
0x14009c016  mov     [rbp+57h+DriverObjectExtension], rsi
0x14009c01a  test    r13b, r13b
0x14009c01d  jz      short loc_14009C033
0x14009c01f  mov     rax, [rdi+0A8h]
0x14009c026  test    rax, rax
0x14009c029  jz      short loc_14009C033
0x14009c02b  mov     rcx, r14
0x14009c02e  call    _guard_dispatch_icall
0x14009c033  mov     eax, ebx
0x14009c035  mov     rbx, [rsp+110h+arg_10]
0x14009c03d  add     rsp, 0E0h
0x14009c044  pop     r15
0x14009c046  pop     r14
0x14009c048  pop     r13
0x14009c04a  pop     r12
0x14009c04c  pop     rdi
0x14009c04d  pop     rsi
0x14009c04e  pop     rbp
0x14009c04f  retn
0x14009c051  lea     rdx, DriverEntry; ClientIdentificationAddress
0x14009c058  mov     rcx, r14; DriverObject
0x14009c05b  call    cs:__imp_IoGetDriverObjectExtension
0x14009c062  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
