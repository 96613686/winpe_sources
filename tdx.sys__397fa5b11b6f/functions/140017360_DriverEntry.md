# DriverEntry

- ea: `0x140017360`
- end: `0x14001742e`
- name: `DriverEntry`
- size: `206`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140024010`

## callees

- `0x140014184`
- `0x140017360`
- `0x1400234a8`
- `0x14002352c`
- `0x14002391c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140017369`
- `ntoskrnl!IoGetCurrentProcess` at `0x140017369`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v3; // ebx

  IoGetCurrentProcess();
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)TdxUnload;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)TdxTdiDispatchCreate;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)TdxTdiDispatchCleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)TdxTdiDispatchClose;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)TdxTdiDispatchInternalDeviceControl;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)TdxTdiDispatchDeviceControl;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NETIO;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  v3 = TdxInitializeModule(DriverObject);
  if ( v3 < 0 )
    WppCleanupKm();
  return v3;
}

```

## disassembly

```asm
0x140017360  push    rbx
0x140017362  sub     rsp, 20h
0x140017366  mov     rbx, rcx
0x140017369  call    cs:__imp_IoGetCurrentProcess
0x140017370  nop     dword ptr [rax+rax+00h]
0x140017375  lea     rax, TdxUnload
0x14001737c  mov     [rbx+68h], rax
0x140017380  lea     rax, TdxTdiDispatchCreate
0x140017387  mov     [rbx+70h], rax
0x14001738b  lea     rax, TdxTdiDispatchCleanup
0x140017392  mov     [rbx+100h], rax
0x140017399  lea     rax, TdxTdiDispatchClose
0x1400173a0  mov     [rbx+80h], rax
0x1400173a7  lea     rax, TdxTdiDispatchInternalDeviceControl
0x1400173ae  mov     [rbx+0E8h], rax
0x1400173b5  lea     rax, TdxTdiDispatchDeviceControl
0x1400173bc  mov     [rbx+0E0h], rax
0x1400173c3  lea     rax, WPP_ThisDir_CTLGUID_NETIO
0x1400173ca  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400173d1  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400173dc  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400173e7  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400173f2  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400173fd  call    WppLoadTracingSupport
0x140017402  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001740d  call    WppInitKm
0x140017412  mov     rcx, rbx
0x140017415  call    TdxInitializeModule
0x14001741a  mov     ebx, eax
0x14001741c  test    eax, eax
0x14001741e  jns     short loc_140017425
0x140017420  call    WppCleanupKm
0x140017425  mov     eax, ebx
0x140017427  add     rsp, 20h
0x14001742b  pop     rbx
0x14001742c  retn
```
