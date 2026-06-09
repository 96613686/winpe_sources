# FxDriverEntryWorker

- ea: `0x14000bf74`
- end: `0x14000c0dc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bf40`

## callees

- `0x14000bf04`
- `0x14000bf74`
- `0x14000c124`
- `0x14000c394`
- `0x140017190`
- `0x14003003c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bfb5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bfb5`
- `ntoskrnl!DbgPrintEx` at `0x14000c030`
- `ntoskrnl!DbgPrintEx` at `0x14000c030`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000c076`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000c076`
- `WDFLDR!WdfVersionBind` at `0x14000bfd5`
- `WDFLDR!WdfVersionBind` at `0x14000bfd5`

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
  *(_DWORD *)&DestinationString.Length = 34078720;
  DestinationString.Buffer = (wchar_t *)qword_14001C3F0;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind(DriverObject, &DestinationString, &qword_14001C1A0, &WdfDriverGlobals);
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
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &DestinationString);
      if ( off_14001C348 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&qword_14001C1A0, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_14001C5F8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000bf74  push    rbx
0x14000bf76  push    rsi
0x14000bf77  push    rdi
0x14000bf78  push    r14
0x14000bf7a  sub     rsp, 58h
0x14000bf7e  mov     rsi, rdx
0x14000bf81  mov     rdi, rcx
0x14000bf84  test    rcx, rcx
0x14000bf87  jnz     short loc_14000BF93
0x14000bf89  call    DriverEntry
0x14000bf8e  jmp     loc_14000C0A5
0x14000bf93  lea     rax, qword_14001C3F0
0x14000bf9a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x14000bfa4  lea     r14, DestinationString
0x14000bfab  mov     cs:DestinationString.Buffer, rax
0x14000bfb2  mov     rcx, r14; DestinationString
0x14000bfb5  call    cs:__imp_RtlCopyUnicodeString
0x14000bfbc  nop     dword ptr [rax+rax+00h]
0x14000bfc1  lea     r9, WdfDriverGlobals
0x14000bfc8  mov     rdx, r14
0x14000bfcb  lea     r8, qword_14001C1A0
0x14000bfd2  mov     rcx, rdi
0x14000bfd5  call    cs:__imp_WdfVersionBind
0x14000bfdc  nop     dword ptr [rax+rax+00h]
0x14000bfe1  test    eax, eax
0x14000bfe3  js      loc_14000C0A5
0x14000bfe9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14000bfee  mov     ebx, eax
0x14000bff0  test    eax, eax
0x14000bff2  js      loc_14000C09E
0x14000bff8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x14000bffd  mov     ebx, eax
0x14000bfff  test    eax, eax
0x14000c001  js      loc_14000C09E
0x14000c007  mov     rdx, rsi; RegistryPath
0x14000c00a  mov     rcx, rdi; DriverObject
0x14000c00d  call    DriverEntry
0x14000c012  mov     ebx, eax
0x14000c014  test    eax, eax
0x14000c016  jns     loc_14000C0B0
0x14000c01c  xor     edx, edx; Level
0x14000c01e  mov     [rsp+78h+var_58], r14
0x14000c023  mov     r9d, eax
0x14000c026  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x14000c02d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c030  call    cs:__imp_DbgPrintEx
0x14000c037  nop     dword ptr [rax+rax+00h]
0x14000c03c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000c043  cmp     cs:off_14001C348, rax
0x14000c04a  jz      short loc_14000C09E
0x14000c04c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x14000c053  mov     [rsp+78h+var_3C], 0
0x14000c05c  lea     rcx, [rsp+78h+var_48]
0x14000c061  mov     [rsp+78h+var_48], rax
0x14000c066  mov     [rsp+78h+var_34], 0
0x14000c06e  mov     [rsp+78h+var_40], 18h
0x14000c076  call    cs:__imp_WdfLdrQueryInterface
0x14000c07d  nop     dword ptr [rax+rax+00h]
0x14000c082  test    eax, eax
0x14000c084  js      short loc_14000C09E
0x14000c086  mov     rdx, cs:WdfDriverGlobals
0x14000c08d  lea     rcx, qword_14001C1A0
0x14000c094  mov     rax, [rsp+78h+var_3C+4]
0x14000c099  call    _guard_dispatch_icall
0x14000c09e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x14000c0a3  mov     eax, ebx
0x14000c0a5  add     rsp, 58h
0x14000c0a9  pop     r14
0x14000c0ab  pop     rdi
0x14000c0ac  pop     rsi
0x14000c0ad  pop     rbx
0x14000c0ae  retn
0x14000c0b0  mov     rax, cs:WdfDriverGlobals
0x14000c0b7  cmp     byte ptr [rax+30h], 0
0x14000c0bb  jz      short loc_14000C0D8
0x14000c0bd  mov     rax, [rdi+68h]
0x14000c0c1  test    rax, rax
0x14000c0c4  jz      short loc_14000C0CD
0x14000c0c6  mov     cs:qword_14001C5F8, rax
0x14000c0cd  lea     rax, FxStubDriverUnload
0x14000c0d4  mov     [rdi+68h], rax
0x14000c0d8  xor     eax, eax
0x14000c0da  jmp     short loc_14000C0A5
```
