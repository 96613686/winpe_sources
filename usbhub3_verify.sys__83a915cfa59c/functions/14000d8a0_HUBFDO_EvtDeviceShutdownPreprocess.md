# HUBFDO_EvtDeviceShutdownPreprocess

- ea: `0x14000d8a0`
- end: `0x14000d8f6`
- name: `HUBFDO_EvtDeviceShutdownPreprocess`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140045570`
- `0x14008af98`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d8e1`
- `ntoskrnl!IofCompleteRequest` at `0x14000d8e1`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceShutdownPreprocess(__int64 a1, IRP *a2)
{
  __int64 v3; // rax

  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B270);
  HUBREG_UxdShutdown(v3);
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000d8a0  push    rbx
0x14000d8a2  sub     rsp, 20h
0x14000d8a6  mov     rax, cs:WdfFunctions_01015
0x14000d8ad  mov     rbx, rdx
0x14000d8b0  mov     r8, cs:off_14006B270
0x14000d8b7  mov     rdx, rcx
0x14000d8ba  mov     rcx, cs:WdfDriverGlobals
0x14000d8c1  mov     rax, [rax+650h]
0x14000d8c8  call    _guard_dispatch_icall
0x14000d8cd  mov     rcx, rax
0x14000d8d0  call    HUBREG_UxdShutdown
0x14000d8d5  xor     edx, edx; PriorityBoost
0x14000d8d7  mov     dword ptr [rbx+30h], 0
0x14000d8de  mov     rcx, rbx; Irp
0x14000d8e1  call    cs:__imp_IofCompleteRequest
0x14000d8e8  nop     dword ptr [rax+rax+00h]
0x14000d8ed  xor     eax, eax
0x14000d8ef  add     rsp, 20h
0x14000d8f3  pop     rbx
0x14000d8f4  retn
```
