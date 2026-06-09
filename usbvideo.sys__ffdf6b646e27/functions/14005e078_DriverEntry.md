# DriverEntry

- ea: `0x14005e078`
- end: `0x14005e184`
- name: `DriverEntry`
- size: `268`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14005e010`

## callees

- `0x140013134`
- `0x140013174`
- `0x14001d0cc`
- `0x14005499c`
- `0x140054af4`
- `0x140054b60`
- `0x140054e8c`
- `0x14005cf38`
- `0x14005cfec`
- `0x14005e078`
- `0x14005e18c`

## import_xrefs

- `ks!KsInitializeDriver` at `0x14005e143`
- `ks!KsInitializeDriver` at `0x14005e143`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // ebx

  wil_InitializeFeatureStaging();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_UsbVideo;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  McGenEventRegister_EtwRegister();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14004C1E8);
  InitializeTelemetryAssertsKMByDriverObject((__int64)DriverObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_43c45135fec032a35977ce741109f83e_Traceguids,
      &Descriptor,
      &off_1400432E0);
  v4 = KsInitializeDriver(DriverObject, RegistryPath, &Descriptor);
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)Uvc_Unload;
  if ( v4 < 0 )
  {
    TraceLoggingUnregister_EtwUnregister(&dword_14004C1E8);
    WppCleanupKm();
    wil_UninitializeFeatureStaging();
  }
  return v4;
}

```

## disassembly

```asm
0x14005e078  mov     [rsp+arg_0], rbx
0x14005e07d  push    rdi
0x14005e07e  sub     rsp, 30h
0x14005e082  mov     rbx, rdx
0x14005e085  mov     rdi, rcx
0x14005e088  call    wil_InitializeFeatureStaging
0x14005e08d  lea     rax, WPP_ThisDir_CTLGUID_UsbVideo
0x14005e094  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14005e09f  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14005e0a6  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14005e0b1  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14005e0bc  mov     cs:WPP_MAIN_CB.Timer, 1
0x14005e0c7  call    WppLoadTracingSupport
0x14005e0cc  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14005e0d7  call    WppInitKm
0x14005e0dc  call    McGenEventRegister_EtwRegister
0x14005e0e1  lea     rcx, dword_14004C1E8; CallbackContext
0x14005e0e8  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14005e0ed  mov     rcx, rdi
0x14005e0f0  call    InitializeTelemetryAssertsKMByDriverObject
0x14005e0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e0fc  lea     rax, WPP_GLOBAL_Control
0x14005e103  cmp     rcx, rax
0x14005e106  jz      short loc_14005E136
0x14005e108  cmp     byte ptr [rcx+29h], 3
0x14005e10c  jb      short loc_14005E136
0x14005e10e  mov     rcx, [rcx+18h]
0x14005e112  lea     rax, off_1400432E0
0x14005e119  mov     edx, 0Ah
0x14005e11e  mov     [rsp+38h+var_18], rax
0x14005e123  lea     r9, Descriptor
0x14005e12a  lea     r8, WPP_43c45135fec032a35977ce741109f83e_Traceguids
0x14005e131  call    WPP_SF_qq
0x14005e136  lea     r8, Descriptor; Descriptor
0x14005e13d  mov     rdx, rbx; RegistryPathName
0x14005e140  mov     rcx, rdi; DriverObject
0x14005e143  call    cs:__imp_KsInitializeDriver
0x14005e14a  nop     dword ptr [rax+rax+00h]
0x14005e14f  mov     ebx, eax
0x14005e151  lea     rax, Uvc_Unload
0x14005e158  mov     [rdi+68h], rax
0x14005e15c  test    ebx, ebx
0x14005e15e  jns     short loc_14005E176
0x14005e160  lea     rcx, dword_14004C1E8
0x14005e167  call    TraceLoggingUnregister_EtwUnregister
0x14005e16c  call    WppCleanupKm
0x14005e171  call    wil_UninitializeFeatureStaging
0x14005e176  mov     eax, ebx
0x14005e178  mov     rbx, [rsp+38h+arg_0]
0x14005e17d  add     rsp, 30h
0x14005e181  pop     rdi
0x14005e182  retn
```
