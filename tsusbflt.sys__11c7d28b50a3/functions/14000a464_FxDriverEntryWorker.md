# FxDriverEntryWorker

- ea: `0x14000a464`
- end: `0x14000a5cc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000a430`

## callees

- `0x14000a330`
- `0x14000a464`
- `0x14000a614`
- `0x14000a7a0`
- `0x14000aa30`
- `0x14001303c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000a520`
- `ntoskrnl!DbgPrintEx` at `0x14000a520`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a4a5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a4a5`
- `WDFLDR!WdfVersionBind` at `0x14000a4c5`
- `WDFLDR!WdfVersionBind` at `0x14000a4c5`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000a566`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000a566`

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
      if ( off_14000F328 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
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
        qword_14000F668 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a464  push    rbx
0x14000a466  push    rsi
0x14000a467  push    rdi
0x14000a468  push    r14
0x14000a46a  sub     rsp, 58h
0x14000a46e  mov     rsi, rdx
0x14000a471  mov     rdi, rcx
0x14000a474  test    rcx, rcx
0x14000a477  jnz     short loc_14000A483
0x14000a479  call    DriverEntry
0x14000a47e  jmp     loc_14000A595
0x14000a483  lea     rax, WPP_MAIN_CB.Queue+10h
0x14000a48a  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 2080000h
0x14000a494  lea     r14, WPP_MAIN_CB.DeviceExtension
0x14000a49b  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14000a4a2  mov     rcx, r14; DestinationString
0x14000a4a5  call    cs:__imp_RtlCopyUnicodeString
0x14000a4ac  nop     dword ptr [rax+rax+00h]
0x14000a4b1  lea     r9, WPP_MAIN_CB.Queue+8
0x14000a4b8  mov     rdx, r14
0x14000a4bb  lea     r8, WdfBindInfo
0x14000a4c2  mov     rcx, rdi
0x14000a4c5  call    cs:__imp_WdfVersionBind
0x14000a4cc  nop     dword ptr [rax+rax+00h]
0x14000a4d1  test    eax, eax
0x14000a4d3  js      loc_14000A595
0x14000a4d9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14000a4de  mov     ebx, eax
0x14000a4e0  test    eax, eax
0x14000a4e2  js      loc_14000A58E
0x14000a4e8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x14000a4ed  mov     ebx, eax
0x14000a4ef  test    eax, eax
0x14000a4f1  js      loc_14000A58E
0x14000a4f7  mov     rdx, rsi; RegistryPath
0x14000a4fa  mov     rcx, rdi; DriverObject
0x14000a4fd  call    DriverEntry
0x14000a502  mov     ebx, eax
0x14000a504  test    eax, eax
0x14000a506  jns     loc_14000A5A0
0x14000a50c  xor     edx, edx; Level
0x14000a50e  mov     [rsp+78h+var_58], r14
0x14000a513  mov     r9d, eax
0x14000a516  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x14000a51d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000a520  call    cs:__imp_DbgPrintEx
0x14000a527  nop     dword ptr [rax+rax+00h]
0x14000a52c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000a533  cmp     cs:off_14000F328, rax
0x14000a53a  jz      short loc_14000A58E
0x14000a53c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x14000a543  mov     [rsp+78h+var_3C], 0
0x14000a54c  lea     rcx, [rsp+78h+var_48]
0x14000a551  mov     [rsp+78h+var_48], rax
0x14000a556  mov     [rsp+78h+var_34], 0
0x14000a55e  mov     [rsp+78h+var_40], 18h
0x14000a566  call    cs:__imp_WdfLdrQueryInterface
0x14000a56d  nop     dword ptr [rax+rax+00h]
0x14000a572  test    eax, eax
0x14000a574  js      short loc_14000A58E
0x14000a576  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000a57d  lea     rcx, WdfBindInfo
0x14000a584  mov     rax, [rsp+78h+var_3C+4]
0x14000a589  call    _guard_dispatch_icall
0x14000a58e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x14000a593  mov     eax, ebx
0x14000a595  add     rsp, 58h
0x14000a599  pop     r14
0x14000a59b  pop     rdi
0x14000a59c  pop     rsi
0x14000a59d  pop     rbx
0x14000a59e  retn
0x14000a5a0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000a5a7  cmp     byte ptr [rax+30h], 0
0x14000a5ab  jz      short loc_14000A5C8
0x14000a5ad  mov     rax, [rdi+68h]
0x14000a5b1  test    rax, rax
0x14000a5b4  jz      short loc_14000A5BD
0x14000a5b6  mov     cs:qword_14000F668, rax
0x14000a5bd  lea     rax, FxStubDriverUnload
0x14000a5c4  mov     [rdi+68h], rax
0x14000a5c8  xor     eax, eax
0x14000a5ca  jmp     short loc_14000A595
```
