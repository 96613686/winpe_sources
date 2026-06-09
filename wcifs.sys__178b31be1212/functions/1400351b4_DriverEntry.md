# DriverEntry

- ea: `0x1400351b4`
- end: `0x1400357fe`
- name: `DriverEntry`
- size: `1610`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140035010`

## callees

- `0x1400020c4`
- `0x140002e08`
- `0x140003274`
- `0x14000672c`
- `0x14001b088`
- `0x14002248c`
- `0x140035078`
- `0x1400351b4`
- `0x140035804`
- `0x140035ed0`
- `0x1400360a4`

## import_xrefs

- `ntoskrnl!PsAllocSiloContextSlot` at `0x140035696`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400356d2`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x140035696`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400356d2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140035646`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140035681`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140035646`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140035681`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140035579`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400355ab`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400355dd`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003560f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140035579`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400355ab`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400355dd`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003560f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140035297`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140035297`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400353ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400353ac`
- `ntoskrnl!KeInitializeEvent` at `0x14003523e`
- `ntoskrnl!KeInitializeEvent` at `0x14003523e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400357b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400357b1`
- `ntoskrnl!ExAllocatePool2` at `0x14003535c`
- `ntoskrnl!ExAllocatePool2` at `0x14003535c`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140035524`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14003554b`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140035524`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14003554b`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14003548b`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14003548b`
- `FLTMGR!FltCloseCommunicationPort` at `0x14003577c`
- `FLTMGR!FltCloseCommunicationPort` at `0x14003577c`
- `FLTMGR!FltStartFiltering` at `0x14003570f`
- `FLTMGR!FltStartFiltering` at `0x14003570f`
- `FLTMGR!FltCreateCommunicationPort` at `0x140035475`
- `FLTMGR!FltCreateCommunicationPort` at `0x140035475`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400353c5`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400353c5`
- `FLTMGR!FltRegisterFilter` at `0x14003530d`
- `FLTMGR!FltRegisterFilter` at `0x14003530d`
- `FLTMGR!FltUnregisterFilter` at `0x140035794`
- `FLTMGR!FltUnregisterFilter` at `0x140035794`

## string_xrefs

- `0x1400351df`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // eax
  int v5; // edx
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ebx
  int v11; // r9d
  NTSTATUS v12; // eax
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // eax
  NTSTATUS started; // eax
  char MessageNotifyCallback; // [rsp+30h] [rbp-88h]
  char MaxConnections; // [rsp+38h] [rbp-80h]
  _QWORD v21[2]; // [rsp+40h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+D0h] [rbp+18h] BYREF

  v21[0] = 6684772;
  SecurityDescriptor = 0;
  v21[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  wil_InitializeFeatureStaging();
  WcTelemetryAndTracingInit(DriverObject, RegistryPath);
  FastMutex.Owner = 0;
  FastMutex.Count = 1;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  qword_14000E6A2 = 0;
  ::DestinationString.Buffer = (PWSTR)qword_14000E6C8;
  word_14000E6A0 = 0;
  byte_14000E680 = 0;
  P = 0;
  dword_14000E6AC = -2147483624;
  *(_DWORD *)&::DestinationString.Length = 6553600;
  RtlCopyUnicodeString(&::DestinationString, &SourceString);
  v4 = WcSetConfiguration(DriverObject);
  if ( v4 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v5,
      1,
      44,
      (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      25,
      v4);
  }
  v6 = FltRegisterFilter(DriverObject, &FilterRegistration, &Globals);
  v10 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = v6;
      v11 = 45;
      MessageNotifyCallback = 37;
LABEL_31:
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v7,
        1,
        v11,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        MessageNotifyCallback,
        MaxConnections);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( byte_14000E680 )
  {
    P = (PVOID)ExAllocatePool2(256, 40, 1701593943);
    if ( !P )
    {
      v10 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        MaxConnections = -102;
        v11 = 46;
        MessageNotifyCallback = 50;
        goto LABEL_31;
      }
LABEL_32:
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(v8, v7, v9, (unsigned int)v10);
      if ( ServerPort )
        FltCloseCommunicationPort(ServerPort);
      if ( Globals )
        FltUnregisterFilter(Globals);
      if ( P )
        ExFreePoolWithTag(P, 0x656C4357u);
      WcTelemetryAndTracingCleanup();
      wil_UninitializeFeatureStaging();
      return v10;
    }
  }
  McGenEventRegister_EtwRegister();
  RtlInitUnicodeString(&DestinationString, L"\\WcifsPort");
  v12 = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = v12;
      v11 = 47;
      MessageNotifyCallback = 66;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v10 = FltCreateCommunicationPort(
          Globals,
          &ServerPort,
          &ObjectAttributes,
          0,
          (PFLT_CONNECT_NOTIFY)WcPortConnect,
          WcPortDisconnect,
          (PFLT_MESSAGE_NOTIFY)WcPortMessage,
          1000);
  FltFreeSecurityDescriptor(SecurityDescriptor);
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = v10;
      v11 = 48;
      MessageNotifyCallback = 88;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v13 = WcSetBootConfiguration(v21);
  if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 4;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v14,
      1,
      49,
      (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      104,
      v13);
  }
  FltInitExtraCreateParameterLookasideList(Globals, qword_14000E300, 0, 0x10u, 0x6F724357u);
  FltInitExtraCreateParameterLookasideList(Globals, qword_14000E280, 0, 0x58u, 0x6F724357u);
  ExInitializePagedLookasideList(&stru_14000E380, 0, 0, 0, 0x30u, 0x62724357u, 0);
  ExInitializePagedLookasideList(&stru_14000E400, 0, 0, 0, 0x48u, 0x65634357u, 0);
  ExInitializePagedLookasideList(&stru_14000E500, 0, 0, 0, 0x20u, 0x63634357u, 0);
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0x50u, 0x6E654357u, 0);
  ExInitializeNPagedLookasideList(&stru_14000E580, 0, 0, 0x200u, 0x108u, 0x63654357u, 0);
  if ( HIBYTE(qword_14000E6A2) )
    ExInitializeNPagedLookasideList(&stru_14000E600, 0, 0, 0x200u, 0x68u, 0x70634357u, 0);
  v15 = PsAllocSiloContextSlot(0, &dword_14000E250);
  v10 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = v15;
      v11 = 50;
      MessageNotifyCallback = -78;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v16 = PsAllocSiloContextSlot(0, &dword_14000E254);
  v10 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = v16;
      v11 = 51;
      MessageNotifyCallback = -67;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  Context = 0;
  started = FltStartFiltering(Globals);
  v10 = started;
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v11 = 52;
      MessageNotifyCallback = -54;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
    McTemplateK0_EtwWriteTransfer(v8, WcifsDriverEntrySuccess);
  return v10;
}

```

## disassembly

```asm
0x1400351b4  mov     r11, rsp
0x1400351b7  mov     [r11+8], rbx
0x1400351bb  mov     [r11+10h], rsi
0x1400351bf  push    rdi
0x1400351c0  push    r12
0x1400351c2  push    r13
0x1400351c4  push    r14
0x1400351c6  push    r15
0x1400351c8  sub     rsp, 90h
0x1400351cf  xorps   xmm0, xmm0
0x1400351d2  mov     qword ptr [r11-78h], 660064h
0x1400351da  xor     eax, eax
0x1400351dc  xor     r14d, r14d
0x1400351df  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400351e6  mov     [r11+18h], r14
0x1400351ea  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x1400351ef  mov     [r11-70h], rax
0x1400351f3  mov     rbx, rdx
0x1400351f6  mov     rdi, rcx
0x1400351f9  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x1400351fe  movups  xmmword ptr [rsp+0B8h+ObjectAttributes+1Ch], xmm0
0x140035203  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x140035208  call    wil_InitializeFeatureStaging
0x14003520d  mov     rdx, rbx
0x140035210  mov     rcx, rdi
0x140035213  call    WcTelemetryAndTracingInit
0x140035218  lea     r15d, [r14+1]
0x14003521c  mov     cs:FastMutex.Owner, r14
0x140035223  mov     edx, r15d; Type
0x140035226  mov     cs:FastMutex.Count, r15d
0x14003522d  xor     r8d, r8d; State
0x140035230  mov     cs:FastMutex.Contention, r14d
0x140035237  lea     rcx, FastMutex.Event; Event
0x14003523e  call    cs:__imp_KeInitializeEvent
0x140035245  nop     dword ptr [rax+rax+00h]
0x14003524a  lea     rax, qword_14000E6C8
0x140035251  mov     cs:qword_14000E6A2, r14
0x140035258  lea     rdx, SourceString; SourceString
0x14003525f  mov     cs:DestinationString.Buffer, rax
0x140035266  lea     rcx, DestinationString; DestinationString
0x14003526d  mov     cs:word_14000E6A0, r14w
0x140035275  mov     cs:byte_14000E680, r14b
0x14003527c  mov     cs:P, r14
0x140035283  mov     cs:dword_14000E6AC, 80000018h
0x14003528d  mov     dword ptr cs:DestinationString.Length, 640000h
0x140035297  call    cs:__imp_RtlCopyUnicodeString
0x14003529e  nop     dword ptr [rax+rax+00h]
0x1400352a3  mov     rcx, rdi
0x1400352a6  call    WcSetConfiguration
0x1400352ab  lea     r12, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400352b2  lea     r13, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400352b9  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400352c0  test    eax, eax
0x1400352c2  jns     short loc_1400352FC
0x1400352c4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400352cb  jz      short loc_1400352FC
0x1400352cd  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400352d4  lea     r9d, [r14+2Ch]
0x1400352d8  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x1400352dc  mov     r8d, r15d
0x1400352df  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 719h
0x1400352e7  mov     dl, 2
0x1400352e9  mov     [rsp+0B8h+DisconnectNotifyCallback], r12
0x1400352ee  mov     rcx, [rcx+40h]
0x1400352f2  mov     [rsp+0B8h+ConnectNotifyCallback], r13
0x1400352f7  call    WPP_RECORDER_SF_sDd
0x1400352fc  lea     r8, Globals; RetFilter
0x140035303  mov     rcx, rdi; Driver
0x140035306  lea     rdx, FilterRegistration; Registration
0x14003530d  call    cs:__imp_FltRegisterFilter
0x140035314  nop     dword ptr [rax+rax+00h]
0x140035319  mov     ebx, eax
0x14003531b  test    eax, eax
0x14003531d  jns     short loc_140035343
0x14003531f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140035326  jz      loc_14003575F
0x14003532c  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x140035330  mov     r9d, 2Dh ; '-'
0x140035336  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 725h
0x14003533e  jmp     loc_140035740
0x140035343  cmp     cs:byte_14000E680, r14b
0x14003534a  jz      short loc_14003539B
0x14003534c  mov     edx, 28h ; '('
0x140035351  mov     ecx, 100h
0x140035356  mov     r8d, 656C4357h
0x14003535c  call    cs:__imp_ExAllocatePool2
0x140035363  nop     dword ptr [rax+rax+00h]
0x140035368  mov     cs:P, rax
0x14003536f  test    rax, rax
0x140035372  jnz     short loc_14003539B
0x140035374  mov     ebx, 0C000009Ah
0x140035379  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140035380  jz      loc_14003575F
0x140035386  mov     dword ptr [rsp+0B8h+MaxConnections], ebx
0x14003538a  lea     r9d, [rax+2Eh]
0x14003538e  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 732h
0x140035396  jmp     loc_140035740
0x14003539b  call    McGenEventRegister_EtwRegister
0x1400353a0  lea     rdx, aWcifsport; "\\WcifsPort"
0x1400353a7  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1400353ac  call    cs:__imp_RtlInitUnicodeString
0x1400353b3  nop     dword ptr [rax+rax+00h]
0x1400353b8  mov     edx, 1F0001h; DesiredAccess
0x1400353bd  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x1400353c5  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x1400353cc  nop     dword ptr [rax+rax+00h]
0x1400353d1  mov     ebx, eax
0x1400353d3  test    eax, eax
0x1400353d5  jns     short loc_1400353FB
0x1400353d7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400353de  jz      loc_14003575F
0x1400353e4  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x1400353e8  mov     r9d, 2Fh ; '/'
0x1400353ee  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 742h
0x1400353f6  jmp     loc_140035740
0x1400353fb  mov     rcx, cs:Globals; Filter
0x140035402  lea     rax, [rsp+0B8h+DestinationString]
0x140035407  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x14003540c  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x140035411  mov     rax, [rsp+0B8h+SecurityDescriptor]
0x140035419  lea     rdx, ServerPort; ServerPort
0x140035420  mov     [rsp+0B8h+ObjectAttributes.SecurityDescriptor], rax
0x140035428  mov     edi, 30h ; '0'
0x14003542d  mov     dword ptr [rsp+0B8h+MaxConnections], 3E8h; MaxConnections
0x140035435  lea     rax, WcPortMessage
0x14003543c  mov     [rsp+0B8h+MessageNotifyCallback], rax; MessageNotifyCallback
0x140035441  xor     r9d, r9d; ServerPortCookie
0x140035444  lea     rax, WcPortDisconnect
0x14003544b  mov     [rsp+0B8h+ObjectAttributes.Length], edi
0x14003544f  mov     [rsp+0B8h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x140035454  lea     rax, WcPortConnect
0x14003545b  mov     [rsp+0B8h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x140035460  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], r14
0x140035465  mov     [rsp+0B8h+ObjectAttributes.Attributes], 240h
0x14003546d  mov     [rsp+0B8h+ObjectAttributes.SecurityQualityOfService], r14
0x140035475  call    cs:__imp_FltCreateCommunicationPort
0x14003547c  nop     dword ptr [rax+rax+00h]
0x140035481  mov     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x140035489  mov     ebx, eax
0x14003548b  call    cs:__imp_FltFreeSecurityDescriptor
0x140035492  nop     dword ptr [rax+rax+00h]
0x140035497  test    ebx, ebx
0x140035499  jns     short loc_1400354BC
0x14003549b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400354a2  jz      loc_14003575F
0x1400354a8  mov     dword ptr [rsp+0B8h+MaxConnections], ebx
0x1400354ac  mov     r9d, edi
0x1400354af  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 758h
0x1400354b7  jmp     loc_140035740
0x1400354bc  lea     rcx, [rsp+0B8h+var_78]
0x1400354c1  call    WcSetBootConfiguration
0x1400354c6  test    eax, eax
0x1400354c8  jns     short loc_140035504
0x1400354ca  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400354d1  jz      short loc_140035504
0x1400354d3  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400354da  mov     r9d, 31h ; '1'
0x1400354e0  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x1400354e4  mov     r8d, r15d
0x1400354e7  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 768h
0x1400354ef  mov     dl, 4
0x1400354f1  mov     [rsp+0B8h+DisconnectNotifyCallback], r12
0x1400354f6  mov     rcx, [rcx+40h]
0x1400354fa  mov     [rsp+0B8h+ConnectNotifyCallback], r13
0x1400354ff  call    WPP_RECORDER_SF_sDd
0x140035504  mov     rcx, cs:Globals; Filter
0x14003550b  lea     rdx, qword_14000E300; Lookaside
0x140035512  mov     ebx, 6F724357h
0x140035517  mov     r9d, 10h; Size
0x14003551d  xor     r8d, r8d; Flags
0x140035520  mov     dword ptr [rsp+0B8h+ConnectNotifyCallback], ebx; Tag
0x140035524  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x14003552b  nop     dword ptr [rax+rax+00h]
0x140035530  mov     rcx, cs:Globals; Filter
0x140035537  lea     rdx, qword_14000E280; Lookaside
0x14003553e  mov     r9d, 58h ; 'X'; Size
0x140035544  mov     dword ptr [rsp+0B8h+ConnectNotifyCallback], ebx; Tag
0x140035548  xor     r8d, r8d; Flags
0x14003554b  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x140035552  nop     dword ptr [rax+rax+00h]
0x140035557  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x14003555d  lea     rcx, stru_14000E380; Lookaside
0x140035564  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 62724357h; Tag
0x14003556c  xor     r9d, r9d; Flags
0x14003556f  xor     r8d, r8d; Free
0x140035572  mov     [rsp+0B8h+ConnectNotifyCallback], rdi; Size
0x140035577  xor     edx, edx; Allocate
0x140035579  call    cs:__imp_ExInitializePagedLookasideList
0x140035580  nop     dword ptr [rax+rax+00h]
0x140035585  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x14003558b  lea     rcx, stru_14000E400; Lookaside
0x140035592  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 65634357h; Tag
0x14003559a  xor     r9d, r9d; Flags
0x14003559d  xor     r8d, r8d; Free
0x1400355a0  mov     [rsp+0B8h+ConnectNotifyCallback], 48h ; 'H'; Size
0x1400355a9  xor     edx, edx; Allocate
0x1400355ab  call    cs:__imp_ExInitializePagedLookasideList
0x1400355b2  nop     dword ptr [rax+rax+00h]
0x1400355b7  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x1400355bd  lea     rcx, stru_14000E500; Lookaside
0x1400355c4  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 63634357h; Tag
0x1400355cc  xor     r9d, r9d; Flags
0x1400355cf  xor     r8d, r8d; Free
0x1400355d2  mov     [rsp+0B8h+ConnectNotifyCallback], 20h ; ' '; Size
0x1400355db  xor     edx, edx; Allocate
0x1400355dd  call    cs:__imp_ExInitializePagedLookasideList
0x1400355e4  nop     dword ptr [rax+rax+00h]
0x1400355e9  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x1400355ef  lea     rcx, Lookaside; Lookaside
0x1400355f6  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 6E654357h; Tag
0x1400355fe  xor     r9d, r9d; Flags
0x140035601  xor     r8d, r8d; Free
0x140035604  mov     [rsp+0B8h+ConnectNotifyCallback], 50h ; 'P'; Size
0x14003560d  xor     edx, edx; Allocate
0x14003560f  call    cs:__imp_ExInitializePagedLookasideList
0x140035616  nop     dword ptr [rax+rax+00h]
0x14003561b  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x140035621  lea     rcx, stru_14000E580; Lookaside
0x140035628  mov     ebx, 200h
0x14003562d  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 63654357h; Tag
0x140035635  mov     r9d, ebx; Flags
0x140035638  mov     [rsp+0B8h+ConnectNotifyCallback], 108h; Size
0x140035641  xor     r8d, r8d; Free
0x140035644  xor     edx, edx; Allocate
0x140035646  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003564d  nop     dword ptr [rax+rax+00h]
0x140035652  cmp     byte ptr cs:qword_14000E6A2+7, r14b
0x140035659  jz      short loc_14003568D
0x14003565b  mov     word ptr [rsp+0B8h+MessageNotifyCallback], r14w; Depth
0x140035661  lea     rcx, stru_14000E600; Lookaside
0x140035668  mov     dword ptr [rsp+0B8h+DisconnectNotifyCallback], 70634357h; Tag
0x140035670  mov     r9d, ebx; Flags
0x140035673  xor     r8d, r8d; Free
0x140035676  mov     [rsp+0B8h+ConnectNotifyCallback], 68h ; 'h'; Size
0x14003567f  xor     edx, edx; Allocate
0x140035681  call    cs:__imp_ExInitializeNPagedLookasideList
0x140035688  nop     dword ptr [rax+rax+00h]
0x14003568d  lea     rdx, dword_14000E250
0x140035694  xor     ecx, ecx
0x140035696  call    cs:__imp_PsAllocSiloContextSlot
0x14003569d  nop     dword ptr [rax+rax+00h]
0x1400356a2  mov     ebx, eax
0x1400356a4  test    eax, eax
0x1400356a6  jns     short loc_1400356C9
0x1400356a8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400356af  jz      loc_14003575F
0x1400356b5  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x1400356b9  mov     r9d, 32h ; '2'
0x1400356bf  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 7B2h
0x1400356c7  jmp     short loc_140035740
0x1400356c9  lea     rdx, dword_14000E254
0x1400356d0  xor     ecx, ecx
0x1400356d2  call    cs:__imp_PsAllocSiloContextSlot
0x1400356d9  nop     dword ptr [rax+rax+00h]
0x1400356de  mov     ebx, eax
0x1400356e0  test    eax, eax
0x1400356e2  jns     short loc_140035701
0x1400356e4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400356eb  jz      short loc_14003575F
0x1400356ed  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x1400356f1  mov     r9d, 33h ; '3'
0x1400356f7  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 7BDh
0x1400356ff  jmp     short loc_140035740
0x140035701  mov     rcx, cs:Globals; Filter
0x140035708  mov     cs:Context, r14
0x14003570f  call    cs:__imp_FltStartFiltering
0x140035716  nop     dword ptr [rax+rax+00h]
0x14003571b  mov     ebx, eax
0x14003571d  test    eax, eax
0x14003571f  jns     loc_1400357C9
0x140035725  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14003572c  jz      short loc_14003575F
0x14003572e  mov     dword ptr [rsp+0B8h+MaxConnections], eax
0x140035732  mov     r9d, 34h ; '4'
0x140035738  mov     dword ptr [rsp+0B8h+MessageNotifyCallback], 7CAh
0x140035740  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035747  mov     r8d, r15d
0x14003574a  mov     [rsp+0B8h+DisconnectNotifyCallback], r12
0x14003574f  mov     dl, 2
0x140035751  mov     [rsp+0B8h+ConnectNotifyCallback], r13
0x140035756  mov     rcx, [rcx+40h]
0x14003575a  call    WPP_RECORDER_SF_sDd
0x14003575f  test    byte ptr cs:WPP_MAIN_CB.Queue, r15b
0x140035766  jz      short loc_140035770
0x140035768  mov     r9d, ebx
0x14003576b  call    McTemplateK0d_EtwWriteTransfer
0x140035770  mov     rcx, cs:ServerPort; ServerPort
0x140035777  test    rcx, rcx
0x14003577a  jz      short loc_140035788
0x14003577c  call    cs:__imp_FltCloseCommunicationPort
0x140035783  nop     dword ptr [rax+rax+00h]
0x140035788  mov     rcx, cs:Globals; Filter
0x14003578f  test    rcx, rcx
0x140035792  jz      short loc_1400357A0
0x140035794  call    cs:__imp_FltUnregisterFilter
0x14003579b  nop     dword ptr [rax+rax+00h]
0x1400357a0  mov     rcx, cs:P; P
0x1400357a7  test    rcx, rcx
0x1400357aa  jz      short loc_1400357BD
0x1400357ac  mov     edx, 656C4357h; Tag
  ... truncated ...
```
