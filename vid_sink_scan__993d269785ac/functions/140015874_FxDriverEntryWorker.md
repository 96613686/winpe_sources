# FxDriverEntryWorker

- ea: `0x140015874`
- end: `0x1400159dc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `NTSTATUS __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015840`

## callees

- `0x140015800`
- `0x140015874`
- `0x140015a24`
- `0x140015c80`
- `0x1400217a0`
- `0x14010203c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140015930`
- `ntoskrnl!DbgPrintEx` at `0x140015930`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400158b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400158b5`
- `WDFLDR!WdfVersionBind` at `0x1400158d5`
- `WDFLDR!WdfVersionBind` at `0x1400158d5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140015976`
- `WDFLDR!WdfLdrQueryInterface` at `0x140015976`

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
  DestinationString.Buffer = (wchar_t *)qword_1400643D0;
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
      if ( off_140064268 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
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
        qword_1400645D8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140015874  push    rbx
0x140015876  push    rsi
0x140015877  push    rdi
0x140015878  push    r14
0x14001587a  sub     rsp, 58h
0x14001587e  mov     rsi, rdx
0x140015881  mov     rdi, rcx
0x140015884  test    rcx, rcx
0x140015887  jnz     short loc_140015893
0x140015889  call    DriverEntry
0x14001588e  jmp     loc_1400159A5
0x140015893  lea     rax, qword_1400643D0
0x14001589a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x1400158a4  lea     r14, DestinationString
0x1400158ab  mov     cs:DestinationString.Buffer, rax
0x1400158b2  mov     rcx, r14; DestinationString
0x1400158b5  call    cs:__imp_RtlCopyUnicodeString
0x1400158bc  nop     dword ptr [rax+rax+00h]
0x1400158c1  lea     r9, WdfDriverGlobals
0x1400158c8  mov     rdx, r14
0x1400158cb  lea     r8, WdfBindInfo
0x1400158d2  mov     rcx, rdi
0x1400158d5  call    cs:__imp_WdfVersionBind
0x1400158dc  nop     dword ptr [rax+rax+00h]
0x1400158e1  test    eax, eax
0x1400158e3  js      loc_1400159A5
0x1400158e9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400158ee  mov     ebx, eax
0x1400158f0  test    eax, eax
0x1400158f2  js      loc_14001599E
0x1400158f8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400158fd  mov     ebx, eax
0x1400158ff  test    eax, eax
0x140015901  js      loc_14001599E
0x140015907  mov     rdx, rsi; RegistryPath
0x14001590a  mov     rcx, rdi; DriverObject
0x14001590d  call    DriverEntry
0x140015912  mov     ebx, eax
0x140015914  test    eax, eax
0x140015916  jns     loc_1400159B0
0x14001591c  xor     edx, edx; Level
0x14001591e  mov     [rsp+78h+var_58], r14
0x140015923  mov     r9d, eax
0x140015926  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x14001592d  lea     ecx, [rdx+4Dh]; ComponentId
0x140015930  call    cs:__imp_DbgPrintEx
0x140015937  nop     dword ptr [rax+rax+00h]
0x14001593c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140015943  cmp     cs:off_140064268, rax
0x14001594a  jz      short loc_14001599E
0x14001594c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140015953  mov     [rsp+78h+var_3C], 0
0x14001595c  lea     rcx, [rsp+78h+var_48]
0x140015961  mov     [rsp+78h+var_48], rax
0x140015966  mov     [rsp+78h+var_34], 0
0x14001596e  mov     [rsp+78h+var_40], 18h
0x140015976  call    cs:__imp_WdfLdrQueryInterface
0x14001597d  nop     dword ptr [rax+rax+00h]
0x140015982  test    eax, eax
0x140015984  js      short loc_14001599E
0x140015986  mov     rdx, cs:WdfDriverGlobals
0x14001598d  lea     rcx, WdfBindInfo
0x140015994  mov     rax, [rsp+78h+var_3C+4]
0x140015999  call    _guard_dispatch_icall
0x14001599e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400159a3  mov     eax, ebx
0x1400159a5  add     rsp, 58h
0x1400159a9  pop     r14
0x1400159ab  pop     rdi
0x1400159ac  pop     rsi
0x1400159ad  pop     rbx
0x1400159ae  retn
0x1400159b0  mov     rax, cs:WdfDriverGlobals
0x1400159b7  cmp     byte ptr [rax+30h], 0
0x1400159bb  jz      short loc_1400159D8
0x1400159bd  mov     rax, [rdi+68h]
0x1400159c1  test    rax, rax
0x1400159c4  jz      short loc_1400159CD
0x1400159c6  mov     cs:qword_1400645D8, rax
0x1400159cd  lea     rax, FxStubDriverUnload
0x1400159d4  mov     [rdi+68h], rax
0x1400159d8  xor     eax, eax
0x1400159da  jmp     short loc_1400159A5
```
