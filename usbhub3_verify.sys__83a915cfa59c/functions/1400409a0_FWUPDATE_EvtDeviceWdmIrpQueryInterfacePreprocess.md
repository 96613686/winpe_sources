# FWUPDATE_EvtDeviceWdmIrpQueryInterfacePreprocess

- ea: `0x1400409a0`
- end: `0x140040aed`
- name: `FWUPDATE_EvtDeviceWdmIrpQueryInterfacePreprocess`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400409a0`
- `0x140045570`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140040a77`
- `ntoskrnl!IofCallDriver` at `0x140040a77`
- `ntoskrnl!RtlCompareMemory` at `0x140040a0b`
- `ntoskrnl!RtlCompareMemory` at `0x140040a96`
- `ntoskrnl!RtlCompareMemory` at `0x140040a0b`
- `ntoskrnl!RtlCompareMemory` at `0x140040a96`

## pseudocode

```c
NTSTATUS __fastcall FWUPDATE_EvtDeviceWdmIrpQueryInterfacePreprocess(__int64 a1, IRP *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  struct _DEVICE_OBJECT *v9; // rax

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1768))(WdfDriverGlobals, a1);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v4,
         off_14006B270);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v7 = v5;
  if ( RtlCompareMemory(CurrentStackLocation->Parameters.Create.SecurityContext, &USB_BUS_INTERFACE_USBDI_GUID, 0x10u) == 16 )
  {
    CurrentStackLocation->Parameters.CreatePipe.Parameters = *(_NAMED_PIPE_CREATE_PARAMETERS **)(v7 + 248);
LABEL_3:
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
           WdfDriverGlobals,
           *(_QWORD *)(v7 + 16));
    v9 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1424))(
                                    WdfDriverGlobals,
                                    v8);
    return IofCallDriver(v9, a2);
  }
  if ( RtlCompareMemory(CurrentStackLocation->Parameters.Create.SecurityContext, &GUID_USBD_INTERFACE, 0x10u) == 16 )
  {
    CurrentStackLocation->Parameters.CreatePipe.Parameters = *(_NAMED_PIPE_CREATE_PARAMETERS **)(v7 + 248);
    goto LABEL_3;
  }
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01015 + 272))(
           WdfDriverGlobals,
           a1,
           a2);
}

```

## disassembly

```asm
0x1400409a0  push    rbx
0x1400409a2  push    rbp
0x1400409a3  push    rsi
0x1400409a4  push    rdi
0x1400409a5  sub     rsp, 28h
0x1400409a9  mov     rax, cs:WdfFunctions_01015
0x1400409b0  mov     rbx, rdx
0x1400409b3  mov     rbp, rcx
0x1400409b6  mov     rdx, rcx
0x1400409b9  mov     rcx, cs:WdfDriverGlobals
0x1400409c0  mov     rax, [rax+6E8h]
0x1400409c7  call    _guard_dispatch_icall
0x1400409cc  mov     r9, cs:WdfFunctions_01015
0x1400409d3  mov     rdx, rax
0x1400409d6  mov     r8, cs:off_14006B270
0x1400409dd  mov     rcx, cs:WdfDriverGlobals
0x1400409e4  mov     rax, [r9+650h]
0x1400409eb  call    _guard_dispatch_icall
0x1400409f0  mov     rdi, [rbx+0B8h]
0x1400409f7  lea     rdx, USB_BUS_INTERFACE_USBDI_GUID; Source2
0x1400409fe  mov     r8d, 10h; Length
0x140040a04  mov     rsi, rax
0x140040a07  mov     rcx, [rdi+8]; Source1
0x140040a0b  call    cs:__imp_RtlCompareMemory
0x140040a12  nop     dword ptr [rax+rax+00h]
0x140040a17  cmp     rax, 10h
0x140040a1b  jnz     short loc_140040A85
0x140040a1d  mov     rcx, [rsi+0F8h]
0x140040a24  mov     [rdi+20h], rcx
0x140040a28  inc     byte ptr [rbx+43h]
0x140040a2b  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140040a33  mov     rax, cs:WdfFunctions_01015
0x140040a3a  mov     rdx, [rsi+10h]
0x140040a3e  mov     rcx, cs:WdfDriverGlobals
0x140040a45  mov     rax, [rax+150h]
0x140040a4c  call    _guard_dispatch_icall
0x140040a51  mov     rcx, cs:WdfFunctions_01015
0x140040a58  mov     rdx, rax
0x140040a5b  mov     r8, [rcx+590h]
0x140040a62  mov     rcx, cs:WdfDriverGlobals
0x140040a69  mov     rax, r8
0x140040a6c  call    _guard_dispatch_icall
0x140040a71  mov     rdx, rbx; Irp
0x140040a74  mov     rcx, rax; DeviceObject
0x140040a77  call    cs:__imp_IofCallDriver
0x140040a7e  nop     dword ptr [rax+rax+00h]
0x140040a83  jmp     short loc_140040AE3
0x140040a85  mov     rcx, [rdi+8]; Source1
0x140040a89  lea     rdx, GUID_USBD_INTERFACE; Source2
0x140040a90  mov     r8d, 10h; Length
0x140040a96  call    cs:__imp_RtlCompareMemory
0x140040a9d  nop     dword ptr [rax+rax+00h]
0x140040aa2  cmp     rax, 10h
0x140040aa6  jnz     short loc_140040AB8
0x140040aa8  mov     rax, [rsi+0F8h]
0x140040aaf  mov     [rdi+20h], rax
0x140040ab3  jmp     loc_140040A28
0x140040ab8  inc     byte ptr [rbx+43h]
0x140040abb  mov     r8, rbx
0x140040abe  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140040ac6  mov     rdx, rbp
0x140040ac9  mov     rax, cs:WdfFunctions_01015
0x140040ad0  mov     rcx, cs:WdfDriverGlobals
0x140040ad7  mov     rax, [rax+110h]
0x140040ade  call    _guard_dispatch_icall
0x140040ae3  add     rsp, 28h
0x140040ae7  pop     rdi
0x140040ae8  pop     rsi
0x140040ae9  pop     rbp
0x140040aea  pop     rbx
0x140040aeb  retn
```
