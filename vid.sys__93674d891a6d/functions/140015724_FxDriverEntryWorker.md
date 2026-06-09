# FxDriverEntryWorker

- ea: `0x140015724`
- end: `0x14001588c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400156f0`

## callees

- `0x1400156b0`
- `0x140015724`
- `0x1400158d4`
- `0x140015b30`
- `0x140021db0`
- `0x14010503c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400157e0`
- `ntoskrnl!DbgPrintEx` at `0x1400157e0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140015765`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140015765`
- `WDFLDR!WdfVersionBind` at `0x140015785`
- `WDFLDR!WdfVersionBind` at `0x140015785`
- `WDFLDR!WdfLdrQueryInterface` at `0x140015826`
- `WDFLDR!WdfLdrQueryInterface` at `0x140015826`

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
  DestinationString.Buffer = (wchar_t *)qword_1400653D0;
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
      if ( off_140065278 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
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
        qword_1400655D8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140015724  push    rbx
0x140015726  push    rsi
0x140015727  push    rdi
0x140015728  push    r14
0x14001572a  sub     rsp, 58h
0x14001572e  mov     rsi, rdx
0x140015731  mov     rdi, rcx
0x140015734  test    rcx, rcx
0x140015737  jnz     short loc_140015743
0x140015739  call    DriverEntry
0x14001573e  jmp     loc_140015855
0x140015743  lea     rax, qword_1400653D0
0x14001574a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140015754  lea     r14, DestinationString
0x14001575b  mov     cs:DestinationString.Buffer, rax
0x140015762  mov     rcx, r14; DestinationString
0x140015765  call    cs:__imp_RtlCopyUnicodeString
0x14001576c  nop     dword ptr [rax+rax+00h]
0x140015771  lea     r9, WdfDriverGlobals
0x140015778  mov     rdx, r14
0x14001577b  lea     r8, WdfBindInfo
0x140015782  mov     rcx, rdi
0x140015785  call    cs:__imp_WdfVersionBind
0x14001578c  nop     dword ptr [rax+rax+00h]
0x140015791  test    eax, eax
0x140015793  js      loc_140015855
0x140015799  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14001579e  mov     ebx, eax
0x1400157a0  test    eax, eax
0x1400157a2  js      loc_14001584E
0x1400157a8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400157ad  mov     ebx, eax
0x1400157af  test    eax, eax
0x1400157b1  js      loc_14001584E
0x1400157b7  mov     rdx, rsi; RegistryPath
0x1400157ba  mov     rcx, rdi; DriverObject
0x1400157bd  call    DriverEntry
0x1400157c2  mov     ebx, eax
0x1400157c4  test    eax, eax
0x1400157c6  jns     loc_140015860
0x1400157cc  xor     edx, edx; Level
0x1400157ce  mov     [rsp+78h+var_58], r14
0x1400157d3  mov     r9d, eax
0x1400157d6  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x1400157dd  lea     ecx, [rdx+4Dh]; ComponentId
0x1400157e0  call    cs:__imp_DbgPrintEx
0x1400157e7  nop     dword ptr [rax+rax+00h]
0x1400157ec  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x1400157f3  cmp     cs:off_140065278, rax
0x1400157fa  jz      short loc_14001584E
0x1400157fc  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140015803  mov     [rsp+78h+var_3C], 0
0x14001580c  lea     rcx, [rsp+78h+var_48]
0x140015811  mov     [rsp+78h+var_48], rax
0x140015816  mov     [rsp+78h+var_34], 0
0x14001581e  mov     [rsp+78h+var_40], 18h
0x140015826  call    cs:__imp_WdfLdrQueryInterface
0x14001582d  nop     dword ptr [rax+rax+00h]
0x140015832  test    eax, eax
0x140015834  js      short loc_14001584E
0x140015836  mov     rdx, cs:WdfDriverGlobals
0x14001583d  lea     rcx, WdfBindInfo
0x140015844  mov     rax, [rsp+78h+var_3C+4]
0x140015849  call    _guard_dispatch_icall
0x14001584e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140015853  mov     eax, ebx
0x140015855  add     rsp, 58h
0x140015859  pop     r14
0x14001585b  pop     rdi
0x14001585c  pop     rsi
0x14001585d  pop     rbx
0x14001585e  retn
0x140015860  mov     rax, cs:WdfDriverGlobals
0x140015867  cmp     byte ptr [rax+30h], 0
0x14001586b  jz      short loc_140015888
0x14001586d  mov     rax, [rdi+68h]
0x140015871  test    rax, rax
0x140015874  jz      short loc_14001587D
0x140015876  mov     cs:qword_1400655D8, rax
0x14001587d  lea     rax, FxStubDriverUnload
0x140015884  mov     [rdi+68h], rax
0x140015888  xor     eax, eax
0x14001588a  jmp     short loc_140015855
```
