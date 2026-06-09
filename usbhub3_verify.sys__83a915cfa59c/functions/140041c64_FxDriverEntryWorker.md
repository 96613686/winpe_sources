# FxDriverEntryWorker

- ea: `0x140041c64`
- end: `0x140041dcc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140041c30`

## callees

- `0x140041b24`
- `0x140041c64`
- `0x140041e14`
- `0x140041fa0`
- `0x140045570`
- `0x14009403c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140041ca5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140041ca5`
- `ntoskrnl!DbgPrintEx` at `0x140041d20`
- `ntoskrnl!DbgPrintEx` at `0x140041d20`
- `WDFLDR!WdfLdrQueryInterface` at `0x140041d66`
- `WDFLDR!WdfLdrQueryInterface` at `0x140041d66`
- `WDFLDR!WdfVersionBind` at `0x140041cc5`
- `WDFLDR!WdfVersionBind` at `0x140041cc5`

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
  DestinationString.Buffer = (wchar_t *)qword_14006EAC0;
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
      if ( off_14006E9B8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
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
        qword_14006ECC8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140041c64  push    rbx
0x140041c66  push    rsi
0x140041c67  push    rdi
0x140041c68  push    r14
0x140041c6a  sub     rsp, 58h
0x140041c6e  mov     rsi, rdx
0x140041c71  mov     rdi, rcx
0x140041c74  test    rcx, rcx
0x140041c77  jnz     short loc_140041C83
0x140041c79  call    DriverEntry
0x140041c7e  jmp     loc_140041D95
0x140041c83  lea     rax, qword_14006EAC0
0x140041c8a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140041c94  lea     r14, DestinationString
0x140041c9b  mov     cs:DestinationString.Buffer, rax
0x140041ca2  mov     rcx, r14; DestinationString
0x140041ca5  call    cs:__imp_RtlCopyUnicodeString
0x140041cac  nop     dword ptr [rax+rax+00h]
0x140041cb1  lea     r9, WdfDriverGlobals
0x140041cb8  mov     rdx, r14
0x140041cbb  lea     r8, WdfBindInfo
0x140041cc2  mov     rcx, rdi
0x140041cc5  call    cs:__imp_WdfVersionBind
0x140041ccc  nop     dword ptr [rax+rax+00h]
0x140041cd1  test    eax, eax
0x140041cd3  js      loc_140041D95
0x140041cd9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x140041cde  mov     ebx, eax
0x140041ce0  test    eax, eax
0x140041ce2  js      loc_140041D8E
0x140041ce8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x140041ced  mov     ebx, eax
0x140041cef  test    eax, eax
0x140041cf1  js      loc_140041D8E
0x140041cf7  mov     rdx, rsi; RegistryPath
0x140041cfa  mov     rcx, rdi; DriverObject
0x140041cfd  call    DriverEntry
0x140041d02  mov     ebx, eax
0x140041d04  test    eax, eax
0x140041d06  jns     loc_140041DA0
0x140041d0c  xor     edx, edx; Level
0x140041d0e  mov     [rsp+78h+var_58], r14
0x140041d13  mov     r9d, eax
0x140041d16  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x140041d1d  lea     ecx, [rdx+4Dh]; ComponentId
0x140041d20  call    cs:__imp_DbgPrintEx
0x140041d27  nop     dword ptr [rax+rax+00h]
0x140041d2c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140041d33  cmp     cs:off_14006E9B8, rax
0x140041d3a  jz      short loc_140041D8E
0x140041d3c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140041d43  mov     [rsp+78h+var_3C], 0
0x140041d4c  lea     rcx, [rsp+78h+var_48]
0x140041d51  mov     [rsp+78h+var_48], rax
0x140041d56  mov     [rsp+78h+var_34], 0
0x140041d5e  mov     [rsp+78h+var_40], 18h
0x140041d66  call    cs:__imp_WdfLdrQueryInterface
0x140041d6d  nop     dword ptr [rax+rax+00h]
0x140041d72  test    eax, eax
0x140041d74  js      short loc_140041D8E
0x140041d76  mov     rdx, cs:WdfDriverGlobals
0x140041d7d  lea     rcx, WdfBindInfo
0x140041d84  mov     rax, [rsp+78h+var_3C+4]
0x140041d89  call    _guard_dispatch_icall
0x140041d8e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140041d93  mov     eax, ebx
0x140041d95  add     rsp, 58h
0x140041d99  pop     r14
0x140041d9b  pop     rdi
0x140041d9c  pop     rsi
0x140041d9d  pop     rbx
0x140041d9e  retn
0x140041da0  mov     rax, cs:WdfDriverGlobals
0x140041da7  cmp     byte ptr [rax+30h], 0
0x140041dab  jz      short loc_140041DC8
0x140041dad  mov     rax, [rdi+68h]
0x140041db1  test    rax, rax
0x140041db4  jz      short loc_140041DBD
0x140041db6  mov     cs:qword_14006ECC8, rax
0x140041dbd  lea     rax, FxStubDriverUnload
0x140041dc4  mov     [rdi+68h], rax
0x140041dc8  xor     eax, eax
0x140041dca  jmp     short loc_140041D95
```
