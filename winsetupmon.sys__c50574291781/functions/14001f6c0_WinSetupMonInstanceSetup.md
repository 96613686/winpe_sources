# WinSetupMonInstanceSetup

- ea: `0x14001f6c0`
- end: `0x14001fa95`
- name: `WinSetupMonInstanceSetup`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001a94`
- `0x140002614`
- `0x140002644`
- `0x1400034f4`
- `0x140003554`
- `0x1400041ac`
- `0x140004260`
- `0x140006578`
- `0x140008138`
- `0x14000d874`
- `0x14000df1c`
- `0x14000f900`
- `0x14000fd40`
- `0x14001f130`
- `0x14001f288`
- `0x14001f6c0`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001f93e`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001f93e`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14001f98d`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14001f98d`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001fa1e`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001fa1e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f8f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f8f0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fa4c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fa4c`
- `FLTMGR!FltReleaseContext` at `0x14001f9f2`
- `FLTMGR!FltReleaseContext` at `0x14001fa08`
- `FLTMGR!FltReleaseContext` at `0x14001f9f2`
- `FLTMGR!FltReleaseContext` at `0x14001fa08`
- `FLTMGR!FltSetVolumeContext` at `0x14001f90c`
- `FLTMGR!FltSetVolumeContext` at `0x14001f90c`
- `FLTMGR!FltAllocateContext` at `0x14001f86b`
- `FLTMGR!FltAllocateContext` at `0x14001f86b`
- `FLTMGR!FltGetVolumeName` at `0x14001f73b`
- `FLTMGR!FltGetVolumeName` at `0x14001f73b`

## string_xrefs

- `0x14001f778`: `WinSetupMonInstanceSetup: SetupConfig failed`

## pseudocode

```c
__int64 __fastcall WinSetupMonInstanceSetup(__int64 a1)
{
  struct _FLT_VOLUME *v2; // rcx
  char v3; // r14
  NTSTATUS v4; // eax
  int v5; // ebx
  int started; // ebx
  const char *v7; // rcx
  int DriveLetter; // eax
  NTSTATUS DeviceObjectPointer; // eax
  const char *v10; // rcx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rdi
  __int64 v13; // rax
  NTSTATUS v14; // eax
  unsigned __int16 v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+58h] [rbp-A8h] BYREF
  PVOID NotificationEntry; // [rsp+60h] [rbp-A0h] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp-98h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+70h] [rbp-90h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v23[128]; // [rsp+80h] [rbp-80h] BYREF

  memset(v23, 0, sizeof(v23));
  v2 = *(struct _FLT_VOLUME **)(a1 + 16);
  VolumeName.Buffer = (wchar_t *)v23;
  *(_QWORD *)&VolumeName.Length = 0x800000;
  v16 = 0;
  FileObject = 0;
  v3 = 0;
  DeviceObject = 0;
  NotificationEntry = 0;
  NewContext = 0;
  OldContext = 0;
  v4 = FltGetVolumeName(v2, &VolumeName, 0);
  if ( v4 < 0 )
  {
    TraceError("WinSetupMonInstanceSetup: FltGetVolumeName failed", (unsigned int)v4);
LABEL_3:
    v5 = -1071906801;
    goto LABEL_32;
  }
  started = SetupConfig(&VolumeName);
  if ( started < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v7 = "WinSetupMonInstanceSetup: SetupConfig failed";
LABEL_6:
    TraceErrorVolume(v7, &VolumeName, (unsigned int)started);
    goto LABEL_3;
  }
  if ( IsLogFileReady() )
  {
    if ( IsLogPathUnderPath(&VolumeName) )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( !IsLogPathUnderPath(&VolumeName) )
  {
LABEL_13:
    if ( !HasTrackedPath(&VolumeName) )
      goto LABEL_3;
    goto LABEL_14;
  }
  started = StartLoggingToFile(*(struct _FLT_INSTANCE **)(a1 + 24));
  if ( started < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v7 = "WinSetupMonInstanceSetup: StartLoggingToFile failed";
    goto LABEL_6;
  }
  v3 = 1;
LABEL_14:
  DriveLetter = GetDriveLetter(*(PFLT_VOLUME *)(a1 + 16), &v16);
  if ( DriveLetter < 0 )
  {
    if ( DriveLetter == -1073741275 )
      UnmapDosDrive(&VolumeName);
    else
      TraceErrorVolume("WinSetupMonInstanceSetup: Failed GetDriveLetter", &VolumeName, (unsigned int)DriveLetter);
  }
  else
  {
    DeviceObjectPointer = MapDosDrive(&VolumeName, v16);
    v5 = DeviceObjectPointer;
    if ( DeviceObjectPointer < 0 )
    {
      v10 = "WinSetupMonInstanceSetup: MapDosDrive failed";
LABEL_17:
      TraceErrorVolume(v10, &VolumeName, (unsigned int)DeviceObjectPointer);
      goto LABEL_32;
    }
  }
  DeviceObjectPointer = FltAllocateContext((PFLT_FILTER)FilterHandle, 1u, 0xA8u, (POOL_TYPE)512, &NewContext);
  v5 = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    v10 = "WinSetupMonInstanceSetup: Failed FltAllocateContext";
    goto LABEL_17;
  }
  v12 = operator new(v11, NewContext);
  *v12 = 0;
  memset(v12 + 1, 0, 0x80u);
  v12[17] = 0x800000;
  v12[18] = v12 + 1;
  v12[19] = 0;
  v12[20] = 0;
  v13 = *(_QWORD *)(a1 + 16);
  NewContext = v12;
  *v12 = v13;
  RtlCopyUnicodeString((PUNICODE_STRING)((char *)NewContext + 136), &VolumeName);
  DeviceObjectPointer = FltSetVolumeContext(
                          *(PFLT_VOLUME *)(a1 + 16),
                          FLT_SET_CONTEXT_REPLACE_IF_EXISTS,
                          NewContext,
                          &OldContext);
  v5 = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    v10 = "WinSetupMonInstanceSetup: Failed FltSetVolumeContext";
    goto LABEL_17;
  }
  DeviceObjectPointer = IoGetDeviceObjectPointer(&VolumeName, 0x100000u, &FileObject, &DeviceObject);
  v5 = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    v10 = "WinSetupMonInstanceSetup: Failed IoGetDeviceObjectPointer";
    goto LABEL_17;
  }
  DeviceObjectPointer = IoRegisterPlugPlayNotification(
                          EventCategoryTargetDeviceChange,
                          0,
                          FileObject,
                          DriverObject,
                          WinSetupMonPnpNotificationCallback,
                          NewContext,
                          &NotificationEntry);
  v5 = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    if ( DeviceObjectPointer != -1073741808 )
    {
      v10 = "WinSetupMonInstanceSetup: Failed IoRegisterPlugPlayNotification";
      goto LABEL_17;
    }
    v5 = 0;
  }
  if ( NotificationEntry )
  {
    *((_QWORD *)NewContext + 19) = FileObject;
    FileObject = 0;
    *((_QWORD *)NewContext + 20) = NotificationEntry;
    NotificationEntry = 0;
  }
LABEL_32:
  if ( OldContext )
    FltReleaseContext(OldContext);
  if ( NewContext )
    FltReleaseContext(NewContext);
  if ( NotificationEntry )
  {
    v14 = IoUnregisterPlugPlayNotification(NotificationEntry);
    if ( v14 < 0 )
      TraceErrorVolume(
        "WinSetupMonInstanceSetup: Failed IoUnregisterPlugPlayNotification",
        &VolumeName,
        (unsigned int)v14);
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v5 < 0 && v3 )
    StopLoggingToFile(*(struct _FLT_INSTANCE **)(a1 + 24));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001f6c0  push    rbp
0x14001f6c2  push    rbx
0x14001f6c3  push    rsi
0x14001f6c4  push    rdi
0x14001f6c5  push    r12
0x14001f6c7  push    r14
0x14001f6c9  lea     rbp, [rsp-18h]
0x14001f6ce  sub     rsp, 118h
0x14001f6d5  mov     rax, cs:__security_cookie
0x14001f6dc  xor     rax, rsp
0x14001f6df  mov     [rbp+40h+var_40], rax
0x14001f6e3  mov     rsi, rcx
0x14001f6e6  mov     r12d, 80h
0x14001f6ec  mov     r8d, r12d; Size
0x14001f6ef  lea     rcx, [rbp+40h+var_C0]; void *
0x14001f6f3  xor     edx, edx; Val
0x14001f6f5  call    memset
0x14001f6fa  mov     rcx, [rsi+10h]; Volume
0x14001f6fe  lea     rax, [rbp+40h+var_C0]
0x14001f702  mov     [rsp+140h+VolumeName.Buffer], rax
0x14001f707  lea     rdx, [rsp+140h+VolumeName]; VolumeName
0x14001f70c  xor     eax, eax
0x14001f70e  mov     qword ptr [rsp+140h+VolumeName.Length], 800000h
0x14001f717  xor     r8d, r8d; BufferSizeNeeded
0x14001f71a  mov     [rsp+140h+var_100], ax
0x14001f71f  mov     [rsp+140h+FileObject], rax
0x14001f724  xor     r14b, r14b
0x14001f727  mov     [rsp+140h+DeviceObject], rax
0x14001f72c  mov     [rsp+140h+var_E0], rax
0x14001f731  mov     [rsp+140h+NewContext], rax
0x14001f736  mov     [rsp+140h+OldContext], rax
0x14001f73b  call    cs:__imp_FltGetVolumeName
0x14001f742  nop     dword ptr [rax+rax+00h]
0x14001f747  test    eax, eax
0x14001f749  jns     short loc_14001F763
0x14001f74b  mov     edx, eax
0x14001f74d  lea     rcx, aWinsetupmonins; "WinSetupMonInstanceSetup: FltGetVolumeN"...
0x14001f754  call    TraceError
0x14001f759  mov     ebx, 0C01C000Fh
0x14001f75e  jmp     loc_14001F9E8
0x14001f763  lea     rcx, [rsp+140h+VolumeName]; String2
0x14001f768  call    ?SetupConfig@@YAJPEBU_UNICODE_STRING@@@Z; SetupConfig(_UNICODE_STRING const *)
0x14001f76d  mov     ebx, eax
0x14001f76f  test    eax, eax
0x14001f771  jns     short loc_14001F78E
0x14001f773  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001f778  lea     rcx, aWinsetupmonins_3; "WinSetupMonInstanceSetup: SetupConfig f"...
0x14001f77f  lea     rdx, [rsp+140h+VolumeName]
0x14001f784  mov     r8d, ebx
0x14001f787  call    TraceErrorVolume
0x14001f78c  jmp     short loc_14001F759
0x14001f78e  call    ?IsLogFileReady@@YAEXZ; IsLogFileReady(void)
0x14001f793  lea     rcx, [rsp+140h+VolumeName]; struct _UNICODE_STRING *
0x14001f798  test    al, al
0x14001f79a  jnz     short loc_14001F7C7
0x14001f79c  call    ?IsLogPathUnderPath@@YAEPEBU_UNICODE_STRING@@@Z; IsLogPathUnderPath(_UNICODE_STRING const *)
0x14001f7a1  test    al, al
0x14001f7a3  jz      short loc_14001F7D0
0x14001f7a5  mov     rcx, [rsi+18h]; struct _FLT_INSTANCE *
0x14001f7a9  call    ?StartLoggingToFile@@YAJPEAU_FLT_INSTANCE@@@Z; StartLoggingToFile(_FLT_INSTANCE *)
0x14001f7ae  mov     ebx, eax
0x14001f7b0  test    eax, eax
0x14001f7b2  jns     short loc_14001F7C2
0x14001f7b4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001f7b9  lea     rcx, aWinsetupmonins_8; "WinSetupMonInstanceSetup: StartLoggingT"...
0x14001f7c0  jmp     short loc_14001F77F
0x14001f7c2  mov     r14b, 1
0x14001f7c5  jmp     short loc_14001F7E2
0x14001f7c7  call    ?IsLogPathUnderPath@@YAEPEBU_UNICODE_STRING@@@Z; IsLogPathUnderPath(_UNICODE_STRING const *)
0x14001f7cc  test    al, al
0x14001f7ce  jnz     short loc_14001F7E2
0x14001f7d0  lea     rcx, [rsp+140h+VolumeName]; String2
0x14001f7d5  call    ?HasTrackedPath@@YAEPEBU_UNICODE_STRING@@@Z; HasTrackedPath(_UNICODE_STRING const *)
0x14001f7da  test    al, al
0x14001f7dc  jz      loc_14001F759
0x14001f7e2  mov     rcx, [rsi+10h]; Volume
0x14001f7e6  lea     rdx, [rsp+140h+var_100]; unsigned __int16 *
0x14001f7eb  call    ?GetDriveLetter@@YAJPEAU_FLT_VOLUME@@PEAG@Z; GetDriveLetter(_FLT_VOLUME *,ushort *)
0x14001f7f0  test    eax, eax
0x14001f7f2  js      short loc_14001F822
0x14001f7f4  movzx   edx, [rsp+140h+var_100]; unsigned __int16
0x14001f7f9  lea     rcx, [rsp+140h+VolumeName]; SourceString
0x14001f7fe  call    ?MapDosDrive@@YAJPEBU_UNICODE_STRING@@G@Z; MapDosDrive(_UNICODE_STRING const *,ushort)
0x14001f803  mov     ebx, eax
0x14001f805  test    eax, eax
0x14001f807  jns     short loc_14001F849
0x14001f809  lea     rcx, aWinsetupmonins_9; "WinSetupMonInstanceSetup: MapDosDrive f"...
0x14001f810  mov     r8d, eax
0x14001f813  lea     rdx, [rsp+140h+VolumeName]
0x14001f818  call    TraceErrorVolume
0x14001f81d  jmp     loc_14001F9E8
0x14001f822  cmp     eax, 0C0000225h
0x14001f827  jnz     short loc_14001F835
0x14001f829  lea     rcx, [rsp+140h+VolumeName]; String1
0x14001f82e  call    ?UnmapDosDrive@@YAXPEBU_UNICODE_STRING@@@Z; UnmapDosDrive(_UNICODE_STRING const *)
0x14001f833  jmp     short loc_14001F849
0x14001f835  mov     r8d, eax
0x14001f838  lea     rdx, [rsp+140h+VolumeName]
0x14001f83d  lea     rcx, aWinsetupmonins_7; "WinSetupMonInstanceSetup: Failed GetDri"...
0x14001f844  call    TraceErrorVolume
0x14001f849  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x14001f850  lea     rax, [rsp+140h+NewContext]
0x14001f855  mov     edx, 1; ContextType
0x14001f85a  mov     [rsp+140h+ReturnedContext], rax; ReturnedContext
0x14001f85f  mov     r9d, 200h; PoolType
0x14001f865  mov     r8d, 0A8h; ContextSize
0x14001f86b  call    cs:__imp_FltAllocateContext
0x14001f872  nop     dword ptr [rax+rax+00h]
0x14001f877  mov     ebx, eax
0x14001f879  test    eax, eax
0x14001f87b  jns     short loc_14001F886
0x14001f87d  lea     rcx, aWinsetupmonins_10; "WinSetupMonInstanceSetup: Failed FltAll"...
0x14001f884  jmp     short loc_14001F810
0x14001f886  mov     rdx, [rsp+140h+NewContext]; void *
0x14001f88b  call    ??2@YAPEAX_KPEAX@Z; operator new(unsigned __int64,void *)
0x14001f890  mov     r8, r12; Size
0x14001f893  xor     edx, edx; Val
0x14001f895  mov     rdi, rax
0x14001f898  lea     rbx, [rax+8]
0x14001f89c  mov     qword ptr [rax], 0
0x14001f8a3  mov     rcx, rbx; void *
0x14001f8a6  call    memset
0x14001f8ab  mov     qword ptr [rdi+88h], 800000h
0x14001f8b6  lea     rdx, [rsp+140h+VolumeName]; SourceString
0x14001f8bb  mov     [rdi+90h], rbx
0x14001f8c2  mov     qword ptr [rdi+98h], 0
0x14001f8cd  mov     qword ptr [rdi+0A0h], 0
0x14001f8d8  mov     rax, [rsi+10h]
0x14001f8dc  mov     [rsp+140h+NewContext], rdi
0x14001f8e1  mov     [rdi], rax
0x14001f8e4  mov     rcx, [rsp+140h+NewContext]
0x14001f8e9  add     rcx, 88h; DestinationString
0x14001f8f0  call    cs:__imp_RtlCopyUnicodeString
0x14001f8f7  nop     dword ptr [rax+rax+00h]
0x14001f8fc  mov     r8, [rsp+140h+NewContext]; NewContext
0x14001f901  lea     r9, [rsp+140h+OldContext]; OldContext
0x14001f906  mov     rcx, [rsi+10h]; Volume
0x14001f90a  xor     edx, edx; Operation
0x14001f90c  call    cs:__imp_FltSetVolumeContext
0x14001f913  nop     dword ptr [rax+rax+00h]
0x14001f918  mov     ebx, eax
0x14001f91a  test    eax, eax
0x14001f91c  jns     short loc_14001F92A
0x14001f91e  lea     rcx, aWinsetupmonins_6; "WinSetupMonInstanceSetup: Failed FltSet"...
0x14001f925  jmp     loc_14001F810
0x14001f92a  lea     r9, [rsp+140h+DeviceObject]; DeviceObject
0x14001f92f  mov     edx, 100000h; DesiredAccess
0x14001f934  lea     r8, [rsp+140h+FileObject]; FileObject
0x14001f939  lea     rcx, [rsp+140h+VolumeName]; ObjectName
0x14001f93e  call    cs:__imp_IoGetDeviceObjectPointer
0x14001f945  nop     dword ptr [rax+rax+00h]
0x14001f94a  mov     ebx, eax
0x14001f94c  test    eax, eax
0x14001f94e  jns     short loc_14001F95C
0x14001f950  lea     rcx, aWinsetupmonins_0; "WinSetupMonInstanceSetup: Failed IoGetD"...
0x14001f957  jmp     loc_14001F810
0x14001f95c  mov     r9, cs:DriverObject; DriverObject
0x14001f963  lea     rax, [rsp+140h+var_E0]
0x14001f968  mov     r8, [rsp+140h+FileObject]; EventCategoryData
0x14001f96d  xor     edx, edx; EventCategoryFlags
0x14001f96f  mov     [rsp+140h+NotificationEntry], rax; NotificationEntry
0x14001f974  mov     rax, [rsp+140h+NewContext]
0x14001f979  mov     [rsp+140h+Context], rax; Context
0x14001f97e  lea     rax, WinSetupMonPnpNotificationCallback
0x14001f985  lea     ecx, [rdx+3]; EventCategory
0x14001f988  mov     [rsp+140h+ReturnedContext], rax; CallbackRoutine
0x14001f98d  call    cs:__imp_IoRegisterPlugPlayNotification
0x14001f994  nop     dword ptr [rax+rax+00h]
0x14001f999  mov     ebx, eax
0x14001f99b  test    eax, eax
0x14001f99d  jns     short loc_14001F9AC
0x14001f99f  cmp     eax, 0C0000010h
0x14001f9a4  jnz     loc_14001FA89
0x14001f9aa  xor     ebx, ebx
0x14001f9ac  cmp     [rsp+140h+var_E0], 0
0x14001f9b2  jz      short loc_14001F9E8
0x14001f9b4  mov     rcx, [rsp+140h+FileObject]
0x14001f9b9  mov     rax, [rsp+140h+NewContext]
0x14001f9be  mov     [rax+98h], rcx
0x14001f9c5  mov     rcx, [rsp+140h+var_E0]
0x14001f9ca  mov     rax, [rsp+140h+NewContext]
0x14001f9cf  mov     [rsp+140h+FileObject], 0
0x14001f9d8  mov     [rax+0A0h], rcx
0x14001f9df  mov     [rsp+140h+var_E0], 0
0x14001f9e8  mov     rcx, [rsp+140h+OldContext]; Context
0x14001f9ed  test    rcx, rcx
0x14001f9f0  jz      short loc_14001F9FE
0x14001f9f2  call    cs:__imp_FltReleaseContext
0x14001f9f9  nop     dword ptr [rax+rax+00h]
0x14001f9fe  mov     rcx, [rsp+140h+NewContext]; Context
0x14001fa03  test    rcx, rcx
0x14001fa06  jz      short loc_14001FA14
0x14001fa08  call    cs:__imp_FltReleaseContext
0x14001fa0f  nop     dword ptr [rax+rax+00h]
0x14001fa14  mov     rcx, [rsp+140h+var_E0]; NotificationEntry
0x14001fa19  test    rcx, rcx
0x14001fa1c  jz      short loc_14001FA42
0x14001fa1e  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14001fa25  nop     dword ptr [rax+rax+00h]
0x14001fa2a  test    eax, eax
0x14001fa2c  jns     short loc_14001FA42
0x14001fa2e  mov     r8d, eax
0x14001fa31  lea     rdx, [rsp+140h+VolumeName]
0x14001fa36  lea     rcx, aWinsetupmonins_5; "WinSetupMonInstanceSetup: Failed IoUnre"...
0x14001fa3d  call    TraceErrorVolume
0x14001fa42  mov     rcx, [rsp+140h+FileObject]; Object
0x14001fa47  test    rcx, rcx
0x14001fa4a  jz      short loc_14001FA58
0x14001fa4c  call    cs:__imp_ObfDereferenceObject
0x14001fa53  nop     dword ptr [rax+rax+00h]
0x14001fa58  test    ebx, ebx
0x14001fa5a  jns     short loc_14001FA6A
0x14001fa5c  test    r14b, r14b
0x14001fa5f  jz      short loc_14001FA6A
0x14001fa61  mov     rcx, [rsi+18h]; struct _FLT_INSTANCE *
0x14001fa65  call    ?StopLoggingToFile@@YAXPEAU_FLT_INSTANCE@@@Z; StopLoggingToFile(_FLT_INSTANCE *)
0x14001fa6a  mov     eax, ebx
0x14001fa6c  mov     rcx, [rbp+40h+var_40]
0x14001fa70  xor     rcx, rsp; StackCookie
0x14001fa73  call    __security_check_cookie
0x14001fa78  add     rsp, 118h
0x14001fa7f  pop     r14
0x14001fa81  pop     r12
0x14001fa83  pop     rdi
0x14001fa84  pop     rsi
0x14001fa85  pop     rbx
0x14001fa86  pop     rbp
0x14001fa87  retn
0x14001fa89  lea     rcx, aWinsetupmonins_2; "WinSetupMonInstanceSetup: Failed IoRegi"...
0x14001fa90  jmp     loc_14001F810
```
