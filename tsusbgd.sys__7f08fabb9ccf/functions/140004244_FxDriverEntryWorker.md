# FxDriverEntryWorker

- ea: `0x140004244`
- end: `0x1400043ac`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004210`

## callees

- `0x14000410c`
- `0x140004244`
- `0x1400043f4`
- `0x140004580`
- `0x140006370`
- `0x14000d03c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140004300`
- `ntoskrnl!DbgPrintEx` at `0x140004300`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004285`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004285`
- `WDFLDR!WdfVersionBind` at `0x1400042a5`
- `WDFLDR!WdfVersionBind` at `0x1400042a5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140004346`
- `WDFLDR!WdfLdrQueryInterface` at `0x140004346`

## pseudocode

```c
NTSTATUS __fastcall FxDriverEntryWorker(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  struct _WDF_BIND_INFO *v5; // rcx
  int inited; // ebx
  NTSTATUS v7; // eax
  GUID *v8; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  _QWORD v10[7]; // [rsp+3Ch] [rbp-3Ch] BYREF

  if ( !DriverObject )
    return DriverEntry(0, RegistryPath);
  LODWORD(WPP_MAIN_CB.DeviceExtension) = 34078720;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.DeviceExtension, RegistryPath);
  result = WdfVersionBind(
             DriverObject,
             &WPP_MAIN_CB.DeviceExtension,
             &WdfBindInfo,
             &WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink);
  if ( result >= 0 )
  {
    inited = FxStubBindClasses(v5);
    if ( inited < 0 || (inited = FxStubInitTypes(), inited < 0) )
    {
LABEL_10:
      FxStubDriverUnloadCommon();
      return inited;
    }
    v7 = DriverEntry(DriverObject, RegistryPath);
    inited = v7;
    if ( v7 < 0 )
    {
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &WPP_MAIN_CB.DeviceExtension);
      if ( off_140009158 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, struct _LIST_ENTRY *))((char *)v10 + 4))(
            &WdfBindInfo,
            WPP_MAIN_CB.Queue.ListEntry.Blink);
      }
      goto LABEL_10;
    }
    if ( LOBYTE(WPP_MAIN_CB.Queue.ListEntry.Blink[3].Flink) )
    {
      if ( DriverObject->DriverUnload )
        qword_140009418 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004244  push    rbx
0x140004246  push    rsi
0x140004247  push    rdi
0x140004248  push    r14
0x14000424a  sub     rsp, 58h
0x14000424e  mov     rsi, rdx
0x140004251  mov     rdi, rcx
0x140004254  test    rcx, rcx
0x140004257  jnz     short loc_140004263
0x140004259  call    DriverEntry
0x14000425e  jmp     loc_140004375
0x140004263  lea     rax, WPP_MAIN_CB.Queue+10h
0x14000426a  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 2080000h
0x140004274  lea     r14, WPP_MAIN_CB.DeviceExtension
0x14000427b  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140004282  mov     rcx, r14; DestinationString
0x140004285  call    cs:__imp_RtlCopyUnicodeString
0x14000428c  nop     dword ptr [rax+rax+00h]
0x140004291  lea     r9, WPP_MAIN_CB.Queue+8
0x140004298  mov     rdx, r14
0x14000429b  lea     r8, WdfBindInfo
0x1400042a2  mov     rcx, rdi
0x1400042a5  call    cs:__imp_WdfVersionBind
0x1400042ac  nop     dword ptr [rax+rax+00h]
0x1400042b1  test    eax, eax
0x1400042b3  js      loc_140004375
0x1400042b9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400042be  mov     ebx, eax
0x1400042c0  test    eax, eax
0x1400042c2  js      loc_14000436E
0x1400042c8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400042cd  mov     ebx, eax
0x1400042cf  test    eax, eax
0x1400042d1  js      loc_14000436E
0x1400042d7  mov     rdx, rsi; RegistryPath
0x1400042da  mov     rcx, rdi; DriverObject
0x1400042dd  call    DriverEntry
0x1400042e2  mov     ebx, eax
0x1400042e4  test    eax, eax
0x1400042e6  jns     loc_140004380
0x1400042ec  xor     edx, edx; Level
0x1400042ee  mov     [rsp+78h+var_58], r14
0x1400042f3  mov     r9d, eax
0x1400042f6  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x1400042fd  lea     ecx, [rdx+4Dh]; ComponentId
0x140004300  call    cs:__imp_DbgPrintEx
0x140004307  nop     dword ptr [rax+rax+00h]
0x14000430c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140004313  cmp     cs:off_140009158, rax
0x14000431a  jz      short loc_14000436E
0x14000431c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140004323  mov     [rsp+78h+var_3C], 0
0x14000432c  lea     rcx, [rsp+78h+var_48]
0x140004331  mov     [rsp+78h+var_48], rax
0x140004336  mov     [rsp+78h+var_34], 0
0x14000433e  mov     [rsp+78h+var_40], 18h
0x140004346  call    cs:__imp_WdfLdrQueryInterface
0x14000434d  nop     dword ptr [rax+rax+00h]
0x140004352  test    eax, eax
0x140004354  js      short loc_14000436E
0x140004356  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000435d  lea     rcx, WdfBindInfo
0x140004364  mov     rax, [rsp+78h+var_3C+4]
0x140004369  call    _guard_dispatch_icall
0x14000436e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140004373  mov     eax, ebx
0x140004375  add     rsp, 58h
0x140004379  pop     r14
0x14000437b  pop     rdi
0x14000437c  pop     rsi
0x14000437d  pop     rbx
0x14000437e  retn
0x140004380  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004387  cmp     byte ptr [rax+30h], 0
0x14000438b  jz      short loc_1400043A8
0x14000438d  mov     rax, [rdi+68h]
0x140004391  test    rax, rax
0x140004394  jz      short loc_14000439D
0x140004396  mov     cs:qword_140009418, rax
0x14000439d  lea     rax, FxStubDriverUnload
0x1400043a4  mov     [rdi+68h], rax
0x1400043a8  xor     eax, eax
0x1400043aa  jmp     short loc_140004375
```
