# HUBPDO_EvtDeviceWdmIrpQueryInterfacePreprocess

- ea: `0x140017d84`
- end: `0x140017ff4`
- name: `HUBPDO_EvtDeviceWdmIrpQueryInterfacePreprocess`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140016160`

## callees

- `0x140017d84`
- `0x140045570`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140017e3c`
- `ntoskrnl!IofCallDriver` at `0x140017e3c`
- `ntoskrnl!IofCompleteRequest` at `0x140017dd4`
- `ntoskrnl!IofCompleteRequest` at `0x140017dd4`
- `ntoskrnl!RtlCompareMemory` at `0x140017e06`
- `ntoskrnl!RtlCompareMemory` at `0x140017e5b`
- `ntoskrnl!RtlCompareMemory` at `0x140017eab`
- `ntoskrnl!RtlCompareMemory` at `0x140017ece`
- `ntoskrnl!RtlCompareMemory` at `0x140017e06`
- `ntoskrnl!RtlCompareMemory` at `0x140017e5b`
- `ntoskrnl!RtlCompareMemory` at `0x140017eab`
- `ntoskrnl!RtlCompareMemory` at `0x140017ece`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceWdmIrpQueryInterfacePreprocess(__int64 a1, IRP *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int Status; // edi
  _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  _LARGE_INTEGER ByteOffset; // rax

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  v5 = v4;
  if ( (*(_DWORD *)(*(_QWORD *)(v4 + 24) + 1644LL) & 2) != 0 )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->Parameters.CreatePipe.Parameters != (_NAMED_PIPE_CREATE_PARAMETERS *)v4 )
    {
      if ( RtlCompareMemory(
             CurrentStackLocation->Parameters.Create.SecurityContext,
             &USB_BUS_INTERFACE_USBDI_GUID,
             0x10u) == 16 )
      {
        CurrentStackLocation->Parameters.CreatePipe.Parameters = *(_NAMED_PIPE_CREATE_PARAMETERS **)(*(_QWORD *)(v5 + 24) + 24LL);
        goto LABEL_7;
      }
      if ( RtlCompareMemory(CurrentStackLocation->Parameters.Create.SecurityContext, &GUID_USBD_INTERFACE, 0x10u) == 16 )
      {
        CurrentStackLocation->Parameters.CreatePipe.Parameters = *(_NAMED_PIPE_CREATE_PARAMETERS **)(*(_QWORD *)(v5 + 24) + 24LL);
        if ( CurrentStackLocation->Parameters.QueryInterface.Size >= 0x98u
          || CurrentStackLocation->Parameters.QueryInterface.Version >= 0x602u )
        {
          *(_DWORD *)(v5 + 388) = *(_DWORD *)(CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart + 32);
        }
        goto LABEL_7;
      }
      if ( RtlCompareMemory(
             CurrentStackLocation->Parameters.Create.SecurityContext,
             &GUID_HUB_CONTROLLERSTACK_INTERFACE,
             0x10u) == 16 )
      {
LABEL_7:
        ++a2->CurrentLocation;
        ++a2->Tail.Overlay.CurrentStackLocation;
        return (unsigned int)IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 8), a2);
      }
      if ( RtlCompareMemory(
             CurrentStackLocation->Parameters.Create.SecurityContext,
             &GUID_D3COLD_SUPPORT_INTERFACE,
             0x10u) != 16 )
      {
        ++a2->Tail.Overlay.CurrentStackLocation;
        ++a2->CurrentLocation;
        return (unsigned int)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01015 + 272))(
                               WdfDriverGlobals,
                               a1,
                               a2);
      }
      if ( CurrentStackLocation->Parameters.QueryInterface.Size == 72
        && CurrentStackLocation->Parameters.QueryInterface.Version == 1 )
      {
        ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
        Status = 0;
        if ( a2->IoStatus.Status )
        {
          *(_DWORD *)ByteOffset.QuadPart = 65608;
        }
        else
        {
          if ( *(_WORD *)ByteOffset.QuadPart != 72 || *(_WORD *)(ByteOffset.QuadPart + 2) != 1 )
          {
            Status = -1073741637;
LABEL_21:
            a2->IoStatus.Status = Status;
            goto LABEL_3;
          }
          *(_OWORD *)(v5 + 312) = *(_OWORD *)ByteOffset.QuadPart;
          *(_OWORD *)(v5 + 328) = *(_OWORD *)(ByteOffset.QuadPart + 16);
          *(_OWORD *)(v5 + 344) = *(_OWORD *)(ByteOffset.QuadPart + 32);
          *(_OWORD *)(v5 + 360) = *(_OWORD *)(ByteOffset.QuadPart + 48);
          *(_QWORD *)(v5 + 376) = *(_QWORD *)(ByteOffset.QuadPart + 64);
        }
        *(_QWORD *)(ByteOffset.QuadPart + 8) = v5;
        *(_QWORD *)(ByteOffset.QuadPart + 32) = HUBPDO_D3ColdSupportInterfaceSetD3ColdSupport;
        *(_QWORD *)(ByteOffset.QuadPart + 40) = HUBPDO_D3ColdSupportInterfaceGetIdleWakeInfo;
        *(_QWORD *)(ByteOffset.QuadPart + 24) = HUBPDO_D3ColdSupportInterfaceDereference;
        *(_QWORD *)(ByteOffset.QuadPart + 16) = HUBPDO_D3ColdSupportInterfaceReference;
        *(_QWORD *)(ByteOffset.QuadPart + 48) = HUBPDO_D3ColdSupportInterfaceGetD3ColdCapability;
        *(_QWORD *)(ByteOffset.QuadPart + 56) = HUBPDO_D3ColdSupportInterfaceGetD3ColdBusDriverSupport;
        *(_QWORD *)(ByteOffset.QuadPart + 64) = HUBPDO_D3ColdSupportInterfaceGetLastTransitionStatus;
        goto LABEL_21;
      }
    }
  }
  Status = a2->IoStatus.Status;
LABEL_3:
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x140017d84  push    rbx
0x140017d86  push    rbp
0x140017d87  push    rsi
0x140017d88  push    rdi
0x140017d89  push    r14
0x140017d8b  sub     rsp, 20h
0x140017d8f  mov     rax, cs:WdfFunctions_01015
0x140017d96  mov     rbx, rdx
0x140017d99  mov     r8, cs:off_14006B1D0
0x140017da0  mov     rbp, rcx
0x140017da3  mov     rdx, rcx
0x140017da6  mov     rcx, cs:WdfDriverGlobals
0x140017dad  mov     rax, [rax+650h]
0x140017db4  call    _guard_dispatch_icall
0x140017db9  mov     rsi, rax
0x140017dbc  mov     r8, [rax+18h]
0x140017dc0  mov     edx, [r8+66Ch]
0x140017dc7  test    dl, 2
0x140017dca  jnz     short loc_140017DE5
0x140017dcc  mov     edi, [rbx+30h]
0x140017dcf  xor     edx, edx; PriorityBoost
0x140017dd1  mov     rcx, rbx; Irp
0x140017dd4  call    cs:__imp_IofCompleteRequest
0x140017ddb  nop     dword ptr [rax+rax+00h]
0x140017de0  jmp     loc_140017FE6
0x140017de5  mov     rdi, [rbx+0B8h]
0x140017dec  cmp     [rdi+20h], rsi
0x140017df0  jz      short loc_140017DCC
0x140017df2  mov     rcx, [rdi+8]; Source1
0x140017df6  lea     rdx, USB_BUS_INTERFACE_USBDI_GUID; Source2
0x140017dfd  mov     r14d, 10h
0x140017e03  mov     r8d, r14d; Length
0x140017e06  call    cs:__imp_RtlCompareMemory
0x140017e0d  nop     dword ptr [rax+rax+00h]
0x140017e12  cmp     rax, r14
0x140017e15  jnz     short loc_140017E4D
0x140017e17  mov     rax, [rsi+18h]
0x140017e1b  mov     rcx, [rax+18h]
0x140017e1f  mov     [rdi+20h], rcx
0x140017e23  mov     edx, 1
0x140017e28  add     [rbx+43h], dl
0x140017e2b  lea     ecx, [rdx+47h]
0x140017e2e  mov     rdx, rbx; Irp
0x140017e31  add     [rbx+0B8h], rcx
0x140017e38  mov     rcx, [rsi+8]; DeviceObject
0x140017e3c  call    cs:__imp_IofCallDriver
0x140017e43  nop     dword ptr [rax+rax+00h]
0x140017e48  jmp     loc_140017FE4
0x140017e4d  mov     rcx, [rdi+8]; Source1
0x140017e51  lea     rdx, GUID_USBD_INTERFACE; Source2
0x140017e58  mov     r8, r14; Length
0x140017e5b  call    cs:__imp_RtlCompareMemory
0x140017e62  nop     dword ptr [rax+rax+00h]
0x140017e67  cmp     rax, r14
0x140017e6a  jnz     short loc_140017E9D
0x140017e6c  mov     rax, [rsi+18h]
0x140017e70  mov     rcx, [rax+18h]
0x140017e74  mov     eax, 98h
0x140017e79  mov     [rdi+20h], rcx
0x140017e7d  cmp     [rdi+10h], ax
0x140017e81  jnb     short loc_140017E8E
0x140017e83  mov     eax, 602h
0x140017e88  cmp     [rdi+12h], ax
0x140017e8c  jb      short loc_140017E23
0x140017e8e  mov     rax, [rdi+18h]
0x140017e92  mov     ecx, [rax+20h]
0x140017e95  mov     [rsi+184h], ecx
0x140017e9b  jmp     short loc_140017E23
0x140017e9d  mov     rcx, [rdi+8]; Source1
0x140017ea1  lea     rdx, GUID_HUB_CONTROLLERSTACK_INTERFACE; Source2
0x140017ea8  mov     r8, r14; Length
0x140017eab  call    cs:__imp_RtlCompareMemory
0x140017eb2  nop     dword ptr [rax+rax+00h]
0x140017eb7  cmp     rax, r14
0x140017eba  jz      loc_140017E23
0x140017ec0  mov     rcx, [rdi+8]; Source1
0x140017ec4  lea     rdx, GUID_D3COLD_SUPPORT_INTERFACE; Source2
0x140017ecb  mov     r8, r14; Length
0x140017ece  call    cs:__imp_RtlCompareMemory
0x140017ed5  nop     dword ptr [rax+rax+00h]
0x140017eda  mov     ecx, 48h ; 'H'
0x140017edf  cmp     rax, r14
0x140017ee2  jnz     loc_140017FB5
0x140017ee8  cmp     [rdi+10h], cx
0x140017eec  jnz     loc_140017DCC
0x140017ef2  lea     edx, [rcx-47h]
0x140017ef5  cmp     [rdi+12h], dx
0x140017ef9  jnz     loc_140017DCC
0x140017eff  mov     rax, [rdi+18h]
0x140017f03  xor     edi, edi
0x140017f05  cmp     [rbx+30h], edi
0x140017f08  jnz     short loc_140017F5C
0x140017f0a  cmp     [rax], cx
0x140017f0d  jnz     short loc_140017F4F
0x140017f0f  cmp     [rax+2], dx
0x140017f13  jnz     short loc_140017F4F
0x140017f15  movups  xmm0, xmmword ptr [rax]
0x140017f18  movups  xmmword ptr [rsi+138h], xmm0
0x140017f1f  movups  xmm1, xmmword ptr [rax+10h]
0x140017f23  movups  xmmword ptr [rsi+148h], xmm1
0x140017f2a  movups  xmm0, xmmword ptr [rax+20h]
0x140017f2e  movups  xmmword ptr [rsi+158h], xmm0
0x140017f35  movups  xmm1, xmmword ptr [rax+30h]
0x140017f39  movups  xmmword ptr [rsi+168h], xmm1
0x140017f40  movsd   xmm0, qword ptr [rax+40h]
0x140017f45  movsd   qword ptr [rsi+178h], xmm0
0x140017f4d  jmp     short loc_140017F62
0x140017f4f  mov     edi, 0C00000BBh
0x140017f54  mov     [rbx+30h], edi
0x140017f57  jmp     loc_140017DCF
0x140017f5c  mov     dword ptr [rax], 10048h
0x140017f62  lea     rcx, HUBPDO_D3ColdSupportInterfaceSetD3ColdSupport
0x140017f69  mov     [rax+8], rsi
0x140017f6d  mov     [rax+20h], rcx
0x140017f71  lea     rcx, HUBPDO_D3ColdSupportInterfaceGetIdleWakeInfo
0x140017f78  mov     [rax+28h], rcx
0x140017f7c  lea     rcx, HUBPDO_D3ColdSupportInterfaceDereference
0x140017f83  mov     [rax+18h], rcx
0x140017f87  lea     rcx, HUBPDO_D3ColdSupportInterfaceReference
0x140017f8e  mov     [rax+10h], rcx
0x140017f92  lea     rcx, HUBPDO_D3ColdSupportInterfaceGetD3ColdCapability
0x140017f99  mov     [rax+30h], rcx
0x140017f9d  lea     rcx, HUBPDO_D3ColdSupportInterfaceGetD3ColdBusDriverSupport
0x140017fa4  mov     [rax+38h], rcx
0x140017fa8  lea     rcx, HUBPDO_D3ColdSupportInterfaceGetLastTransitionStatus
0x140017faf  mov     [rax+40h], rcx
0x140017fb3  jmp     short loc_140017F54
0x140017fb5  add     [rbx+0B8h], rcx
0x140017fbc  mov     edx, 1
0x140017fc1  add     [rbx+43h], dl
0x140017fc4  mov     r8, rbx
0x140017fc7  mov     rax, cs:WdfFunctions_01015
0x140017fce  mov     rdx, rbp
0x140017fd1  mov     rcx, cs:WdfDriverGlobals
0x140017fd8  mov     rax, [rax+110h]
0x140017fdf  call    _guard_dispatch_icall
0x140017fe4  mov     edi, eax
0x140017fe6  mov     eax, edi
0x140017fe8  add     rsp, 20h
0x140017fec  pop     r14
0x140017fee  pop     rdi
0x140017fef  pop     rsi
0x140017ff0  pop     rbp
0x140017ff1  pop     rbx
0x140017ff2  retn
```
