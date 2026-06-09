# FxDriverEntryWorker

- ea: `0x140030574`
- end: `0x1400306dc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140030540`

## callees

- `0x140030500`
- `0x140030574`
- `0x140030724`
- `0x140030980`
- `0x140039780`
- `0x14005003c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140030630`
- `ntoskrnl!DbgPrintEx` at `0x140030630`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400305b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400305b5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140030676`
- `WDFLDR!WdfLdrQueryInterface` at `0x140030676`
- `WDFLDR!WdfVersionBind` at `0x1400305d5`
- `WDFLDR!WdfVersionBind` at `0x1400305d5`

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
  WPP_MAIN_CB.DeviceType = 34078720;
  WPP_MAIN_CB.Queue.ListEntry.Flink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.DeviceType, RegistryPath);
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.DeviceType, &WdfBindInfo, &WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
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
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &WPP_MAIN_CB.DeviceType);
      if ( off_140047C88 != &__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(void *, PKDPC))((char *)v10 + 4))(
            &WdfBindInfo,
            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
      }
      goto LABEL_10;
    }
    if ( LOBYTE(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc->SystemArgument2) )
    {
      if ( DriverObject->DriverUnload )
        qword_140048078 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140030574  push    rbx
0x140030576  push    rsi
0x140030577  push    rdi
0x140030578  push    r14
0x14003057a  sub     rsp, 58h
0x14003057e  mov     rsi, rdx
0x140030581  mov     rdi, rcx
0x140030584  test    rcx, rcx
0x140030587  jnz     short loc_140030593
0x140030589  call    DriverEntry
0x14003058e  jmp     loc_1400306A5
0x140030593  lea     rax, WPP_MAIN_CB.DeviceQueue
0x14003059a  mov     cs:WPP_MAIN_CB.DeviceType, 2080000h
0x1400305a4  lea     r14, WPP_MAIN_CB.DeviceType
0x1400305ab  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x1400305b2  mov     rcx, r14; DestinationString
0x1400305b5  call    cs:__imp_RtlCopyUnicodeString
0x1400305bc  nop     dword ptr [rax+rax+00h]
0x1400305c1  lea     r9, WPP_MAIN_CB.Queue+40h
0x1400305c8  mov     rdx, r14
0x1400305cb  lea     r8, WdfBindInfo
0x1400305d2  mov     rcx, rdi
0x1400305d5  call    cs:__imp_WdfVersionBind
0x1400305dc  nop     dword ptr [rax+rax+00h]
0x1400305e1  test    eax, eax
0x1400305e3  js      loc_1400306A5
0x1400305e9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400305ee  mov     ebx, eax
0x1400305f0  test    eax, eax
0x1400305f2  js      loc_14003069E
0x1400305f8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400305fd  mov     ebx, eax
0x1400305ff  test    eax, eax
0x140030601  js      loc_14003069E
0x140030607  mov     rdx, rsi; RegistryPath
0x14003060a  mov     rcx, rdi; DriverObject
0x14003060d  call    DriverEntry
0x140030612  mov     ebx, eax
0x140030614  test    eax, eax
0x140030616  jns     loc_1400306B0
0x14003061c  xor     edx, edx; Level
0x14003061e  mov     [rsp+78h+var_58], r14
0x140030623  mov     r9d, eax
0x140030626  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x14003062d  lea     ecx, [rdx+4Dh]; ComponentId
0x140030630  call    cs:__imp_DbgPrintEx
0x140030637  nop     dword ptr [rax+rax+00h]
0x14003063c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140030643  cmp     cs:off_140047C88, rax
0x14003064a  jz      short loc_14003069E
0x14003064c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140030653  mov     [rsp+78h+var_3C], 0
0x14003065c  lea     rcx, [rsp+78h+var_48]
0x140030661  mov     [rsp+78h+var_48], rax
0x140030666  mov     [rsp+78h+var_34], 0
0x14003066e  mov     [rsp+78h+var_40], 18h
0x140030676  call    cs:__imp_WdfLdrQueryInterface
0x14003067d  nop     dword ptr [rax+rax+00h]
0x140030682  test    eax, eax
0x140030684  js      short loc_14003069E
0x140030686  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14003068d  lea     rcx, WdfBindInfo
0x140030694  mov     rax, [rsp+78h+var_3C+4]
0x140030699  call    _guard_dispatch_icall
0x14003069e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400306a3  mov     eax, ebx
0x1400306a5  add     rsp, 58h
0x1400306a9  pop     r14
0x1400306ab  pop     rdi
0x1400306ac  pop     rsi
0x1400306ad  pop     rbx
0x1400306ae  retn
0x1400306b0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400306b7  cmp     byte ptr [rax+30h], 0
0x1400306bb  jz      short loc_1400306D8
0x1400306bd  mov     rax, [rdi+68h]
0x1400306c1  test    rax, rax
0x1400306c4  jz      short loc_1400306CD
0x1400306c6  mov     cs:qword_140048078, rax
0x1400306cd  lea     rax, FxStubDriverUnload
0x1400306d4  mov     [rdi+68h], rax
0x1400306d8  xor     eax, eax
0x1400306da  jmp     short loc_1400306A5
```
