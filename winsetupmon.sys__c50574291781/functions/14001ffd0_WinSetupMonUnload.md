# WinSetupMonUnload

- ea: `0x14001ffd0`
- end: `0x140020126`
- name: `WinSetupMonUnload`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400022f0`
- `0x140002614`
- `0x140003554`
- `0x140003944`
- `0x140007800`
- `0x140008740`
- `0x14001f130`
- `0x14001ffd0`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x140020097`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x140020097`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002002c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002002c`
- `ntoskrnl!IoDeleteDevice` at `0x140020059`
- `ntoskrnl!IoDeleteDevice` at `0x140020059`
- `ntoskrnl!EtwUnregister` at `0x140020111`
- `ntoskrnl!EtwUnregister` at `0x140020111`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001ffdd`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001ffdd`
- `FLTMGR!FltUnregisterFilter` at `0x1400200c4`
- `FLTMGR!FltUnregisterFilter` at `0x1400200c4`
- `FLTMGR!FltCloseCommunicationPort` at `0x140020073`
- `FLTMGR!FltCloseCommunicationPort` at `0x140020073`

## string_xrefs

- `0x14002003e`: `WinSetupMonUnload: Failed IoDeleteSymbolicLink`
- `0x1400200a9`: `WinSetupMonUnload: Failed PsSetCreateProcessNotifyRoutine`

## pseudocode

```c
__int64 WinSetupMonUnload()
{
  NTSTATUS v0; // eax
  NTSTATUS ProcessNotifyRoutine; // eax
  REGHANDLE v2; // rcx
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-18h] BYREF

  ExWaitForRundownProtectionRelease(&FilterRundownRef);
  if ( IsLogFileReady() )
    WriteLogMessage(2, L"Logging stopped due to driver unload");
  StopLoggingToFile(0);
  if ( byte_1400194C1 )
  {
    *(_QWORD *)&SymbolicLinkName.Length = 3145774;
    SymbolicLinkName.Buffer = L"\\DosDevices\\WinSetupMon";
    v0 = IoDeleteSymbolicLink(&SymbolicLinkName);
    if ( v0 >= 0 )
      byte_1400194C1 = 0;
    else
      TraceError("WinSetupMonUnload: Failed IoDeleteSymbolicLink", (unsigned int)v0);
  }
  IoDeleteDevice(DeviceObject);
  DeviceObject = 0;
  FltCloseCommunicationPort(FilterPort);
  FilterPort = 0;
  if ( byte_1400194C0 )
  {
    ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(WinSetupMonCreateProcessNotificationCallback, 1u);
    if ( ProcessNotifyRoutine >= 0 )
      byte_1400194C0 = 0;
    else
      TraceError("WinSetupMonUnload: Failed PsSetCreateProcessNotifyRoutine", (unsigned int)ProcessNotifyRoutine);
  }
  FltUnregisterFilter((PFLT_FILTER)FilterHandle);
  FilterHandle = 0;
  UnloadConfig();
  ClearState();
  DriverObject = 0;
  if ( byte_1400194D0 )
    UninitializeTelemetryAssertsKM();
  if ( byte_1400194D1 )
  {
    v2 = qword_140019020;
    dword_140019000 = 0;
    qword_140019020 = 0;
    EtwUnregister(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14001ffd0  push    rbx
0x14001ffd2  sub     rsp, 30h
0x14001ffd6  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x14001ffdd  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001ffe4  nop     dword ptr [rax+rax+00h]
0x14001ffe9  call    ?IsLogFileReady@@YAEXZ; IsLogFileReady(void)
0x14001ffee  xor     ebx, ebx
0x14001fff0  test    al, al
0x14001fff2  jz      short loc_140020003
0x14001fff4  lea     rdx, aLoggingStopped_0; "Logging stopped due to driver unload"
0x14001fffb  lea     ecx, [rbx+2]
0x14001fffe  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140020003  xor     ecx, ecx; struct _FLT_INSTANCE *
0x140020005  call    ?StopLoggingToFile@@YAXPEAU_FLT_INSTANCE@@@Z; StopLoggingToFile(_FLT_INSTANCE *)
0x14002000a  cmp     cs:byte_1400194C1, bl
0x140020010  jz      short loc_140020052
0x140020012  lea     rax, aDosdevicesWins; "\\DosDevices\\WinSetupMon"
0x140020019  mov     qword ptr [rsp+38h+SymbolicLinkName.Length], 30002Eh
0x140020022  lea     rcx, [rsp+38h+SymbolicLinkName]; SymbolicLinkName
0x140020027  mov     [rsp+38h+SymbolicLinkName.Buffer], rax
0x14002002c  call    cs:__imp_IoDeleteSymbolicLink
0x140020033  nop     dword ptr [rax+rax+00h]
0x140020038  test    eax, eax
0x14002003a  jns     short loc_14002004C
0x14002003c  mov     edx, eax
0x14002003e  lea     rcx, aWinsetupmonunl_0; "WinSetupMonUnload: Failed IoDeleteSymbo"...
0x140020045  call    TraceError
0x14002004a  jmp     short loc_140020052
0x14002004c  mov     cs:byte_1400194C1, bl
0x140020052  mov     rcx, cs:DeviceObject; DeviceObject
0x140020059  call    cs:__imp_IoDeleteDevice
0x140020060  nop     dword ptr [rax+rax+00h]
0x140020065  mov     rcx, cs:?FilterPort@@3PEAU_FLT_PORT@@EA; ServerPort
0x14002006c  mov     cs:DeviceObject, rbx
0x140020073  call    cs:__imp_FltCloseCommunicationPort
0x14002007a  nop     dword ptr [rax+rax+00h]
0x14002007f  cmp     cs:byte_1400194C0, bl
0x140020085  mov     cs:?FilterPort@@3PEAU_FLT_PORT@@EA, rbx; _FLT_PORT * FilterPort
0x14002008c  jz      short loc_1400200BD
0x14002008e  mov     dl, 1; Remove
0x140020090  lea     rcx, WinSetupMonCreateProcessNotificationCallback; NotifyRoutine
0x140020097  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x14002009e  nop     dword ptr [rax+rax+00h]
0x1400200a3  test    eax, eax
0x1400200a5  jns     short loc_1400200B7
0x1400200a7  mov     edx, eax
0x1400200a9  lea     rcx, aWinsetupmonunl; "WinSetupMonUnload: Failed PsSetCreatePr"...
0x1400200b0  call    TraceError
0x1400200b5  jmp     short loc_1400200BD
0x1400200b7  mov     cs:byte_1400194C0, bl
0x1400200bd  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x1400200c4  call    cs:__imp_FltUnregisterFilter
0x1400200cb  nop     dword ptr [rax+rax+00h]
0x1400200d0  mov     cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA, rbx; _FLT_FILTER * FilterHandle
0x1400200d7  call    ?UnloadConfig@@YAXXZ; UnloadConfig(void)
0x1400200dc  call    ?ClearState@@YAXXZ; ClearState(void)
0x1400200e1  cmp     cs:byte_1400194D0, bl
0x1400200e7  mov     cs:DriverObject, rbx
0x1400200ee  jz      short loc_1400200F5
0x1400200f0  call    UninitializeTelemetryAssertsKM
0x1400200f5  cmp     cs:byte_1400194D1, bl
0x1400200fb  jz      short loc_14002011D
0x1400200fd  mov     rcx, cs:qword_140019020; RegHandle
0x140020104  mov     cs:dword_140019000, ebx
0x14002010a  mov     cs:qword_140019020, rbx
0x140020111  call    cs:__imp_EtwUnregister
0x140020118  nop     dword ptr [rax+rax+00h]
0x14002011d  xor     eax, eax
0x14002011f  add     rsp, 30h
0x140020123  pop     rbx
0x140020124  retn
```
