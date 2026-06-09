# FxDriverEntryWorker

- ea: `0x140010134`
- end: `0x14001029c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010100`

## callees

- `0x14000fffc`
- `0x140010134`
- `0x1400102e4`
- `0x140010470`
- `0x140010700`
- `0x14001e03c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400101f0`
- `ntoskrnl!DbgPrintEx` at `0x1400101f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010175`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010175`
- `WDFLDR!WdfLdrQueryInterface` at `0x140010236`
- `WDFLDR!WdfLdrQueryInterface` at `0x140010236`
- `WDFLDR!WdfVersionBind` at `0x140010195`
- `WDFLDR!WdfVersionBind` at `0x140010195`

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
  DestinationString.Buffer = (wchar_t *)qword_140015250;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind(DriverObject, &DestinationString, &WdfBindInfo, &WdfDriverGlobals);
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
      if ( off_1400151D8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&WdfBindInfo, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_140015458 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140010134  push    rbx
0x140010136  push    rsi
0x140010137  push    rdi
0x140010138  push    r14
0x14001013a  sub     rsp, 58h
0x14001013e  mov     rsi, rdx
0x140010141  mov     rdi, rcx
0x140010144  test    rcx, rcx
0x140010147  jnz     short loc_140010153
0x140010149  call    DriverEntry
0x14001014e  jmp     loc_140010265
0x140010153  lea     rax, qword_140015250
0x14001015a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140010164  lea     r14, DestinationString
0x14001016b  mov     cs:DestinationString.Buffer, rax
0x140010172  mov     rcx, r14; DestinationString
0x140010175  call    cs:__imp_RtlCopyUnicodeString
0x14001017c  nop     dword ptr [rax+rax+00h]
0x140010181  lea     r9, WdfDriverGlobals
0x140010188  mov     rdx, r14
0x14001018b  lea     r8, WdfBindInfo
0x140010192  mov     rcx, rdi
0x140010195  call    cs:__imp_WdfVersionBind
0x14001019c  nop     dword ptr [rax+rax+00h]
0x1400101a1  test    eax, eax
0x1400101a3  js      loc_140010265
0x1400101a9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400101ae  mov     ebx, eax
0x1400101b0  test    eax, eax
0x1400101b2  js      loc_14001025E
0x1400101b8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400101bd  mov     ebx, eax
0x1400101bf  test    eax, eax
0x1400101c1  js      loc_14001025E
0x1400101c7  mov     rdx, rsi; RegistryPath
0x1400101ca  mov     rcx, rdi; DriverObject
0x1400101cd  call    DriverEntry
0x1400101d2  mov     ebx, eax
0x1400101d4  test    eax, eax
0x1400101d6  jns     loc_140010270
0x1400101dc  xor     edx, edx; Level
0x1400101de  mov     [rsp+78h+var_58], r14
0x1400101e3  mov     r9d, eax
0x1400101e6  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x1400101ed  lea     ecx, [rdx+4Dh]; ComponentId
0x1400101f0  call    cs:__imp_DbgPrintEx
0x1400101f7  nop     dword ptr [rax+rax+00h]
0x1400101fc  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140010203  cmp     cs:off_1400151D8, rax
0x14001020a  jz      short loc_14001025E
0x14001020c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140010213  mov     [rsp+78h+var_3C], 0
0x14001021c  lea     rcx, [rsp+78h+var_48]
0x140010221  mov     [rsp+78h+var_48], rax
0x140010226  mov     [rsp+78h+var_34], 0
0x14001022e  mov     [rsp+78h+var_40], 18h
0x140010236  call    cs:__imp_WdfLdrQueryInterface
0x14001023d  nop     dword ptr [rax+rax+00h]
0x140010242  test    eax, eax
0x140010244  js      short loc_14001025E
0x140010246  mov     rdx, cs:WdfDriverGlobals
0x14001024d  lea     rcx, WdfBindInfo
0x140010254  mov     rax, [rsp+78h+var_3C+4]
0x140010259  call    _guard_dispatch_icall
0x14001025e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140010263  mov     eax, ebx
0x140010265  add     rsp, 58h
0x140010269  pop     r14
0x14001026b  pop     rdi
0x14001026c  pop     rsi
0x14001026d  pop     rbx
0x14001026e  retn
0x140010270  mov     rax, cs:WdfDriverGlobals
0x140010277  cmp     byte ptr [rax+30h], 0
0x14001027b  jz      short loc_140010298
0x14001027d  mov     rax, [rdi+68h]
0x140010281  test    rax, rax
0x140010284  jz      short loc_14001028D
0x140010286  mov     cs:qword_140015458, rax
0x14001028d  lea     rax, FxStubDriverUnload
0x140010294  mov     [rdi+68h], rax
0x140010298  xor     eax, eax
0x14001029a  jmp     short loc_140010265
```
