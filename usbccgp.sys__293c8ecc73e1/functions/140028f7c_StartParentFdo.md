# StartParentFdo

- ea: `0x140028f7c`
- end: `0x140029774`
- name: `StartParentFdo`
- size: `2040`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028800`

## callees

- `0x140003388`
- `0x140006834`
- `0x1400088b4`
- `0x14000a6cc`
- `0x14000a7bc`
- `0x14000ba3c`
- `0x14000c2bc`
- `0x14000e8a4`
- `0x14000f664`
- `0x140010d14`
- `0x140011280`
- `0x1400116a4`
- `0x14001399c`
- `0x140015100`
- `0x140022ee4`
- `0x140022fe8`
- `0x140023214`
- `0x140023414`
- `0x140023588`
- `0x140023938`
- `0x140026294`
- `0x1400265cc`
- `0x140028f7c`
- `0x14002977c`
- `0x140029b50`
- `0x14002aec4`
- `0x14002baf4`
- `0x14002c2cc`
- `0x14002c430`
- `0x14002c604`
- `0x14002c8e4`
- `0x14002d524`
- `0x14002d86c`
- `0x14002dab0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029064`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029190`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029215`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029718`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029064`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029190`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029215`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029718`
- `ntoskrnl!KeSetTimer` at `0x1400296bf`
- `ntoskrnl!KeSetTimer` at `0x1400296bf`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140028fbc`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029082`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002919c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029252`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400292d7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400292e8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002932f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400293ff`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029643`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029724`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140028fbc`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029082`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002919c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029252`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400292d7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400292e8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002932f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400293ff`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029643`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029724`
- `ntoskrnl!swscanf_s` at `0x140029128`
- `ntoskrnl!swscanf_s` at `0x140029128`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140029035`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140029035`
- `ntoskrnl!DbgPrint` at `0x140029637`
- `ntoskrnl!DbgPrint` at `0x140029637`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14002969e`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14002969e`
- `ntoskrnl!ExAllocatePool2` at `0x140028fe3`
- `ntoskrnl!ExAllocatePool2` at `0x140028fe3`

## string_xrefs

- `0x140029630`: `USBCCGP: ERROR: All enumeration attempts failed!! status 0x%x\n`

## pseudocode

```c
__int64 __fastcall StartParentFdo(__int64 a1, IRP *a2)
{
  int v2; // r13d
  unsigned int v3; // r15d
  ULONG v5; // r12d
  void *Pool2; // rax
  int v7; // edx
  void *Data; // r14
  NTSTATUS DevicePropertyData; // eax
  int v10; // edx
  int DeviceDescriptor; // edi
  IRP *v12; // r12
  ULONGLONG v13; // r14
  int v14; // edx
  ULONGLONG v15; // rcx
  int v16; // r15d
  _WORD *i; // rdi
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONGLONG v23; // r14
  int v24; // eax
  int v25; // edx
  ULONGLONG v26; // rax
  int v27; // edx
  int v28; // eax
  __int64 v29; // rdx
  int OriginalConfiguration; // eax
  char v31; // r14
  int v32; // edx
  _QWORD *InterfaceList; // rax
  int AltConfiguration; // eax
  int v35; // r8d
  int v36; // edx
  int Size; // [rsp+20h] [rbp-48h]
  PULONG RequiredSize; // [rsp+30h] [rbp-38h]
  int v39; // [rsp+40h] [rbp-28h] BYREF
  ULONGLONG UnbiasedInterruptTime; // [rsp+48h] [rbp-20h]
  __int64 v41; // [rsp+50h] [rbp-18h] BYREF
  __int64 v42; // [rsp+58h] [rbp-10h] BYREF
  char v43; // [rsp+B0h] [rbp+48h] BYREF
  PIRP Irp; // [rsp+B8h] [rbp+50h]
  ULONG v45; // [rsp+C0h] [rbp+58h] BYREF
  ULONG Type; // [rsp+C8h] [rbp+60h] BYREF

  Irp = a2;
  v2 = *(_DWORD *)(a1 + 12);
  v43 = 0;
  v3 = 0;
  v42 = 0;
  v41 = 0;
  v45 = 0;
  v39 = 0;
  Type = 0;
  *(_DWORD *)(a1 + 12) = 1;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  v5 = 128;
  while ( 1 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v5, 1130525525);
    Data = Pool2;
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v7, 8, 40, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
      }
      DeviceDescriptor = -1073741670;
      goto LABEL_79;
    }
    memset(Pool2, 0, v5);
    DevicePropertyData = IoGetDevicePropertyData(
                           *(PDEVICE_OBJECT *)(a1 + 24),
                           &DEVPKEY_Device_HardwareIds,
                           0,
                           0,
                           v5,
                           Data,
                           &v45,
                           &Type);
    DeviceDescriptor = DevicePropertyData;
    if ( DevicePropertyData != -1073741789 )
      break;
    v5 = v45;
    ++v3;
    ExFreePoolWithTag(Data, 0x43627355u);
    if ( v3 >= 2 )
    {
      v12 = Irp;
      goto LABEL_6;
    }
  }
  v16 = 0;
  if ( DevicePropertyData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v10,
        8,
        41,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        DevicePropertyData);
    }
    ExFreePoolWithTag(Data, 0x43627355u);
LABEL_79:
    KeQueryUnbiasedInterruptTime();
    v12 = Irp;
    goto LABEL_24;
  }
  for ( i = Data; *i; i += v20 + 1 )
  {
    v18 = -1;
    do
      ++v18;
    while ( i[v18] );
    if ( (unsigned int)v18 >= 6 && swscanf_s(&i[(unsigned int)v18 - 6], L"&MI_%02x", &v39) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v19, 8, 42, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
      }
      DeviceDescriptor = -1073741823;
      ExFreePoolWithTag(Data, 0x43627355u);
      KeQueryUnbiasedInterruptTime();
      v12 = Irp;
      goto LABEL_24;
    }
    v20 = -1;
    do
      ++v20;
    while ( i[v20] );
  }
  ExFreePoolWithTag(Data, 0x43627355u);
  v12 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v23 = KeQueryUnbiasedInterruptTime();
  v24 = CallDriverSync(*(PDEVICE_OBJECT *)(a1 + 40), v12, 0, *(struct _DEVICE_OBJECT **)(a1 + 32));
  DeviceDescriptor = v24;
  if ( v24 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v25,
        8,
        43,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        v24);
    }
    LODWORD(RequiredSize) = 0;
    RecordStartFailData(a1, DeviceDescriptor, 0, -1610612732, 1179865158, 0, (size_t)RequiredSize);
LABEL_69:
    KeQueryUnbiasedInterruptTime();
    goto LABEL_24;
  }
  v26 = KeQueryUnbiasedInterruptTime();
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_i(*(_QWORD *)(a1 + 1368), (v26 - v23) / 0x2710, 2, 44, Size, (v26 - v23) / 0x2710);
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  v13 = UnbiasedInterruptTime;
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      v15 = KeQueryUnbiasedInterruptTime();
      goto LABEL_8;
    }
    if ( v2 == 6 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v27, 2, 45, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
      }
      v28 = ParentSelectConfiguration(a1, *(unsigned __int8 *)(*(_QWORD *)(a1 + 56) + 4LL));
      *(_DWORD *)(a1 + 392) = 0;
      LOBYTE(v29) = 1;
      DeviceDescriptor = v28;
      EnableIdleTimer(a1, v29, 1347376211);
      goto LABEL_7;
    }
    DeviceDescriptor = -1073741436;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v27) = 2;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(a1 + 1368),
        v27,
        8,
        50,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        v2);
    }
    goto LABEL_69;
  }
  QueryUSBStackAndDeviceCapabilities(a1);
  ParentGetD3ColdInterface(a1);
  ParentQueryForInterface(a1);
  OriginalConfiguration = ParentFindOriginalConfiguration(a1, &v43);
  v31 = v43;
  if ( OriginalConfiguration < 0 )
    v31 = 0;
  v43 = v31;
  while ( 2 )
  {
    *(_BYTE *)(a1 + 64) = v31;
    DeviceDescriptor = GetDeviceDescriptor(a1);
    if ( DeviceDescriptor < 0 )
      goto LABEL_62;
    SetRecorderLogIdentifier(*(_QWORD *)(a1 + 1368), *(unsigned __int16 *)(a1 + 104), *(unsigned __int16 *)(a1 + 106));
    DeviceDescriptor = GetConfigDescriptor(a1);
    if ( DeviceDescriptor < 0 )
      goto LABEL_62;
    DeviceDescriptor = GetParentFdoCapabilities(a1);
    if ( DeviceDescriptor < 0 )
      goto LABEL_62;
    USBC_QueryKseDeviceFlags(
      *(unsigned __int16 *)(a1 + 104),
      *(unsigned __int16 *)(a1 + 106),
      *(unsigned __int16 *)(a1 + 108),
      (unsigned int)&v41,
      (__int64)&v42,
      *(_QWORD *)(a1 + 1368));
    if ( (v41 & 0x200000) != 0 || (v42 & 0x200000) != 0 )
      *(_DWORD *)(a1 + 1224) |= 0x20u;
    InterfaceList = GetInterfaceList(a1, *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 56));
    *(_QWORD *)(a1 + 88) = InterfaceList;
    if ( !InterfaceList )
    {
      DeviceDescriptor = -1073741668;
      goto LABEL_62;
    }
    DeviceDescriptor = ParentSelectConfiguration(a1, *(unsigned __int8 *)(*(_QWORD *)(a1 + 56) + 4LL));
    if ( DeviceDescriptor < 0 )
    {
      AltConfiguration = ParentFindAltConfiguration(a1, &v43);
      if ( AltConfiguration < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_61;
        v31 = v43;
        WPP_RECORDER_SF_ddd(
          *(_QWORD *)(a1 + 1368),
          v32,
          v35,
          47,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v43,
          DeviceDescriptor,
          AltConfiguration);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v31 = v43;
          LOBYTE(v32) = 4;
          WPP_RECORDER_SF_dd(
            *(_QWORD *)(a1 + 1368),
            v32,
            1,
            46,
            (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
            DeviceDescriptor,
            v43);
          goto LABEL_62;
        }
LABEL_61:
        v31 = v43;
      }
LABEL_62:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v32) = 2;
        WPP_RECORDER_SF_dd(
          *(_QWORD *)(a1 + 1368),
          v32,
          8,
          48,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v16,
          DeviceDescriptor);
      }
      StartCleanup(a1);
      ResetDevice(a1);
      if ( (unsigned int)++v16 >= 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v36) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(a1 + 1368),
            v36,
            8,
            49,
            (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
            DeviceDescriptor);
        }
        DbgPrint("USBCCGP: ERROR: All enumeration attempts failed!! status 0x%x\n", DeviceDescriptor);
        goto LABEL_69;
      }
      continue;
    }
    break;
  }
  DeviceDescriptor = CreateFunctionList(a1);
  if ( DeviceDescriptor >= 0 )
  {
    GetMsOs20DescriptorSet(a1);
    GetMsExtendedConfigDescriptor((_QWORD *)a1);
    if ( *(_BYTE *)(a1 + 1360) )
      RegisterCompositeDevice(a1);
    DeviceDescriptor = CreateStaticFunctionPDOs(a1);
    if ( DeviceDescriptor >= 0 )
    {
      IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(a1 + 24), BusRelations);
      KeSetTimer((PKTIMER)(a1 + 992), (LARGE_INTEGER)-50000000LL, (PKDPC)(a1 + 1056));
    }
    CheckParentIdle(a1);
  }
LABEL_6:
  v13 = UnbiasedInterruptTime;
LABEL_7:
  v15 = KeQueryUnbiasedInterruptTime();
  if ( DeviceDescriptor >= 0 )
  {
LABEL_8:
    *(_DWORD *)(a1 + 12) = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_i(*(_QWORD *)(a1 + 1368), (v15 - v13) / 0x2710, 1, 52, Size, (v15 - v13) / 0x2710);
    USBC_RegisterWmi(a1);
    goto LABEL_27;
  }
LABEL_24:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1368),
      v14,
      8,
      51,
      (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
      DeviceDescriptor);
  }
  *(_DWORD *)(a1 + 12) = 3;
  ReportStartFailData(a1);
LABEL_27:
  UsbcCompleteIrp(a1, DeviceDescriptor, v12);
  return (unsigned int)DeviceDescriptor;
}

```

## disassembly

```asm
0x140028f7c  mov     [rsp-40h+Irp], rdx
0x140028f81  push    rbp
0x140028f82  push    rbx
0x140028f83  push    rsi
0x140028f84  push    rdi
0x140028f85  push    r12
0x140028f87  push    r13
0x140028f89  push    r14
0x140028f8b  push    r15
0x140028f8d  mov     rbp, rsp
0x140028f90  sub     rsp, 68h
0x140028f94  mov     r13d, [rcx+0Ch]
0x140028f98  xor     esi, esi
0x140028f9a  mov     [rbp+arg_0], sil
0x140028f9e  mov     r15d, esi
0x140028fa1  mov     [rbp+var_10], rsi
0x140028fa5  mov     rbx, rcx
0x140028fa8  mov     [rbp+var_18], rsi
0x140028fac  mov     [rbp+arg_10], esi
0x140028faf  mov     [rbp+var_28], esi
0x140028fb2  mov     [rbp+arg_18], esi
0x140028fb5  mov     dword ptr [rcx+0Ch], 1
0x140028fbc  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140028fc3  nop     dword ptr [rax+rax+00h]
0x140028fc8  mov     [rbp+var_20], rax
0x140028fcc  mov     r12d, 80h
0x140028fd2  mov     r8d, 43627355h
0x140028fd8  mov     edx, r12d
0x140028fdb  mov     ecx, 40h ; '@'
0x140028fe0  mov     edi, r12d
0x140028fe3  call    cs:__imp_ExAllocatePool2
0x140028fea  nop     dword ptr [rax+rax+00h]
0x140028fef  mov     r14, rax
0x140028ff2  test    rax, rax
0x140028ff5  jz      loc_140029739
0x140028ffb  mov     r8d, edi; Size
0x140028ffe  xor     edx, edx; Val
0x140029000  mov     rcx, rax; void *
0x140029003  call    memset
0x140029008  mov     rcx, [rbx+18h]; Pdo
0x14002900c  lea     rax, [rbp+arg_18]
0x140029010  mov     [rsp+68h+Type], rax; Type
0x140029015  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x14002901c  lea     rax, [rbp+arg_10]
0x140029020  xor     r9d, r9d; Flags
0x140029023  mov     [rsp+68h+RequiredSize], rax; RequiredSize
0x140029028  xor     r8d, r8d; Lcid
0x14002902b  mov     [rsp+68h+Data], r14; Data
0x140029030  mov     [rsp+68h+Size], r12d; Size
0x140029035  call    cs:__imp_IoGetDevicePropertyData
0x14002903c  nop     dword ptr [rax+rax+00h]
0x140029041  lea     rsi, WPP_RECORDER_INITIALIZED
0x140029048  mov     edi, eax
0x14002904a  cmp     eax, 0C0000023h
0x14002904f  jnz     loc_1400290E5
0x140029055  mov     r12d, [rbp+arg_10]
0x140029059  mov     edx, 43627355h; Tag
0x14002905e  mov     rcx, r14; P
0x140029061  inc     r15d
0x140029064  call    cs:__imp_ExFreePoolWithTag
0x14002906b  nop     dword ptr [rax+rax+00h]
0x140029070  cmp     r15d, 2
0x140029074  jb      loc_140028FD2
0x14002907a  mov     r12, [rbp+Irp]
0x14002907e  mov     r14, [rbp+var_20]
0x140029082  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140029089  nop     dword ptr [rax+rax+00h]
0x14002908e  mov     rcx, rax
0x140029091  test    edi, edi
0x140029093  js      loc_1400291AC
0x140029099  mov     dword ptr [rbx+0Ch], 2
0x1400290a0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400290a7  jz      short loc_1400290D8
0x1400290a9  sub     rcx, r14
0x1400290ac  mov     r9d, 34h ; '4'
0x1400290b2  mov     rax, 346DC5D63886594Bh
0x1400290bc  mul     rcx
0x1400290bf  mov     rcx, [rbx+558h]
0x1400290c6  lea     r8d, [r9-33h]
0x1400290ca  shr     rdx, 0Bh
0x1400290ce  mov     [rsp+68h+Data], rdx
0x1400290d3  call    WPP_RECORDER_SF_i
0x1400290d8  mov     rcx, rbx
0x1400290db  call    USBC_RegisterWmi
0x1400290e0  jmp     loc_1400291EC
0x1400290e5  xor     r15d, r15d
0x1400290e8  test    eax, eax
0x1400290ea  js      loc_1400296D8
0x1400290f0  mov     rdi, r14
0x1400290f3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400290f7  cmp     [rdi], r15w
0x1400290fb  jz      loc_14002920D
0x140029101  mov     rax, r12
0x140029104  inc     rax
0x140029107  cmp     [rdi+rax*2], r15w
0x14002910c  jnz     short loc_140029104
0x14002910e  cmp     eax, 6
0x140029111  jb      short loc_140029138
0x140029113  mov     eax, eax
0x140029115  lea     r8, [rbp+var_28]
0x140029119  add     rax, 0FFFFFFFFFFFFFFFAh
0x14002911d  lea     rdx, aMi02x; "&MI_%02x"
0x140029124  lea     rcx, [rdi+rax*2]; Src
0x140029128  call    cs:__imp_swscanf_s
0x14002912f  nop     dword ptr [rax+rax+00h]
0x140029134  test    eax, eax
0x140029136  jnz     short loc_14002914F
0x140029138  mov     rax, r12
0x14002913b  inc     rax
0x14002913e  cmp     [rdi+rax*2], r15w
0x140029143  jnz     short loc_14002913B
0x140029145  lea     rdi, [rdi+rax*2]
0x140029149  add     rdi, 2
0x14002914d  jmp     short loc_1400290F7
0x14002914f  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029156  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002915d  jz      short loc_140029183
0x14002915f  mov     rcx, [rbx+558h]
0x140029166  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002916d  mov     r9d, 2Ah ; '*'
0x140029173  mov     qword ptr [rsp+68h+Size], rax
0x140029178  mov     dl, 2
0x14002917a  lea     r8d, [r9-22h]
0x14002917e  call    WPP_RECORDER_SF_
0x140029183  mov     edx, 43627355h; Tag
0x140029188  mov     rcx, r14; P
0x14002918b  mov     edi, 0C0000001h
0x140029190  call    cs:__imp_ExFreePoolWithTag
0x140029197  nop     dword ptr [rax+rax+00h]
0x14002919c  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400291a3  nop     dword ptr [rax+rax+00h]
0x1400291a8  mov     r12, [rbp+Irp]
0x1400291ac  lea     r13, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400291b3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400291ba  jz      short loc_1400291DD
0x1400291bc  mov     rcx, [rbx+558h]
0x1400291c3  mov     r9d, 33h ; '3'
0x1400291c9  mov     dword ptr [rsp+68h+Data], edi
0x1400291cd  mov     dl, 2
0x1400291cf  mov     qword ptr [rsp+68h+Size], r13
0x1400291d4  lea     r8d, [r9-2Bh]
0x1400291d8  call    WPP_RECORDER_SF_d
0x1400291dd  mov     rcx, rbx
0x1400291e0  mov     dword ptr [rbx+0Ch], 3
0x1400291e7  call    ReportStartFailData
0x1400291ec  mov     r8, r12
0x1400291ef  mov     edx, edi
0x1400291f1  mov     rcx, rbx
0x1400291f4  call    UsbcCompleteIrp
0x1400291f9  mov     eax, edi
0x1400291fb  add     rsp, 68h
0x1400291ff  pop     r15
0x140029201  pop     r14
0x140029203  pop     r13
0x140029205  pop     r12
0x140029207  pop     rdi
0x140029208  pop     rsi
0x140029209  pop     rbx
0x14002920a  pop     rbp
0x14002920b  retn
0x14002920d  mov     edx, 43627355h; Tag
0x140029212  mov     rcx, r14; P
0x140029215  call    cs:__imp_ExFreePoolWithTag
0x14002921c  nop     dword ptr [rax+rax+00h]
0x140029221  mov     r12, [rbp+Irp]
0x140029225  mov     rax, [r12+0B8h]
0x14002922d  movups  xmm0, xmmword ptr [rax]
0x140029230  movups  xmmword ptr [rax-48h], xmm0
0x140029234  movups  xmm1, xmmword ptr [rax+10h]
0x140029238  movups  xmmword ptr [rax-38h], xmm1
0x14002923c  movups  xmm0, xmmword ptr [rax+20h]
0x140029240  movups  xmmword ptr [rax-28h], xmm0
0x140029244  movsd   xmm1, qword ptr [rax+30h]
0x140029249  movsd   qword ptr [rax-18h], xmm1
0x14002924e  mov     [rax-45h], r15b
0x140029252  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140029259  nop     dword ptr [rax+rax+00h]
0x14002925e  mov     r9, [rbx+20h]
0x140029262  xor     r8d, r8d
0x140029265  mov     rcx, [rbx+28h]; DeviceObject
0x140029269  mov     rdx, r12; Irp
0x14002926c  mov     r14, rax
0x14002926f  call    CallDriverSync
0x140029274  mov     edi, eax
0x140029276  test    eax, eax
0x140029278  jns     short loc_1400292E8
0x14002927a  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029281  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029288  jz      short loc_1400292B2
0x14002928a  mov     rcx, [rbx+558h]
0x140029291  mov     r9d, 2Bh ; '+'
0x140029297  mov     dword ptr [rsp+68h+Data], eax
0x14002929b  mov     dl, 2
0x14002929d  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400292a4  mov     qword ptr [rsp+68h+Size], rax
0x1400292a9  lea     r8d, [r9-23h]
0x1400292ad  call    WPP_RECORDER_SF_d
0x1400292b2  mov     dword ptr [rsp+68h+RequiredSize], r15d; Size
0x1400292b7  mov     r9d, 0A0000004h; int
0x1400292bd  mov     [rsp+68h+Data], r15; Src
0x1400292c2  xor     r8d, r8d; int
0x1400292c5  mov     edx, edi; int
0x1400292c7  mov     [rsp+68h+Size], 46535046h; int
0x1400292cf  mov     rcx, rbx; int
0x1400292d2  call    RecordStartFailData
0x1400292d7  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400292de  nop     dword ptr [rax+rax+00h]
0x1400292e3  jmp     loc_1400291AC
0x1400292e8  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400292ef  nop     dword ptr [rax+rax+00h]
0x1400292f4  mov     rcx, rax
0x1400292f7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400292fe  jz      short loc_14002932F
0x140029300  sub     rcx, r14
0x140029303  mov     r9d, 2Ch ; ','
0x140029309  mov     rax, 346DC5D63886594Bh
0x140029313  mul     rcx
0x140029316  mov     rcx, [rbx+558h]
0x14002931d  lea     r8d, [r9-2Ah]
0x140029321  shr     rdx, 0Bh
0x140029325  mov     [rsp+68h+Data], rdx
0x14002932a  call    WPP_RECORDER_SF_i
0x14002932f  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140029336  nop     dword ptr [rax+rax+00h]
0x14002933b  mov     [rbp+var_20], rax
0x14002933f  mov     r14, rax
0x140029342  test    r13d, r13d
0x140029345  jz      loc_140029413
0x14002934b  cmp     r13d, 2
0x14002934f  jz      loc_1400293FF
0x140029355  cmp     r13d, 6
0x140029359  jz      short loc_14002939B
0x14002935b  mov     edi, 0C0000184h
0x140029360  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029367  jz      loc_1400292D7
0x14002936d  mov     rcx, [rbx+558h]
0x140029374  mov     r9d, 32h ; '2'
0x14002937a  mov     dword ptr [rsp+68h+Data], r13d
0x14002937f  mov     dl, 2
0x140029381  lea     r13, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140029388  mov     qword ptr [rsp+68h+Size], r13
0x14002938d  lea     r8d, [r9-2Ah]
0x140029391  call    WPP_RECORDER_SF_D
0x140029396  jmp     loc_140029643
0x14002939b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400293a2  jz      short loc_1400293C8
0x1400293a4  mov     rcx, [rbx+558h]
0x1400293ab  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400293b2  mov     r9d, 2Dh ; '-'
0x1400293b8  mov     qword ptr [rsp+68h+Size], rax
0x1400293bd  mov     dl, 4
0x1400293bf  lea     r8d, [r9-2Bh]
0x1400293c3  call    WPP_RECORDER_SF_
0x1400293c8  mov     rdx, [rbx+38h]
0x1400293cc  mov     rcx, rbx; int
0x1400293cf  mov     r9, [rbx+58h]
0x1400293d3  movzx   eax, byte ptr [rdx+4]
0x1400293d7  mov     word ptr [rsp+68h+Size], ax; __int16
0x1400293dc  call    ParentSelectConfiguration
0x1400293e1  mov     r8d, 504F5453h
0x1400293e7  mov     [rbx+188h], r15d
0x1400293ee  mov     dl, 1
0x1400293f0  mov     rcx, rbx
0x1400293f3  mov     edi, eax
0x1400293f5  call    EnableIdleTimer
0x1400293fa  jmp     loc_140029082
0x1400293ff  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140029406  nop     dword ptr [rax+rax+00h]
0x14002940b  mov     rcx, rax
0x14002940e  jmp     loc_140029099
0x140029413  mov     rcx, rbx
0x140029416  call    QueryUSBStackAndDeviceCapabilities
0x14002941b  mov     rcx, rbx
0x14002941e  call    ParentGetD3ColdInterface
0x140029423  mov     rcx, rbx
0x140029426  call    ParentQueryForInterface
0x14002942b  lea     rdx, [rbp+arg_0]
0x14002942f  mov     rcx, rbx
0x140029432  call    ParentFindOriginalConfiguration
0x140029437  movzx   r14d, [rbp+arg_0]
0x14002943c  xor     ecx, ecx
0x14002943e  test    eax, eax
0x140029440  cmovs   r14d, ecx
0x140029444  mov     [rbp+arg_0], r14b
0x140029448  mov     rcx, rbx; int
0x14002944b  mov     [rbx+40h], r14b
0x14002944f  call    GetDeviceDescriptor
0x140029454  mov     edi, eax
0x140029456  test    eax, eax
0x140029458  js      loc_1400295AD
0x14002945e  movzx   r8d, word ptr [rbx+6Ah]
0x140029463  movzx   edx, word ptr [rbx+68h]
0x140029467  mov     rcx, [rbx+558h]
0x14002946e  call    SetRecorderLogIdentifier
0x140029473  mov     dl, r14b
0x140029476  mov     rcx, rbx; int
0x140029479  call    GetConfigDescriptor
0x14002947e  mov     edi, eax
0x140029480  test    eax, eax
0x140029482  js      loc_1400295AD
  ... truncated ...
```
