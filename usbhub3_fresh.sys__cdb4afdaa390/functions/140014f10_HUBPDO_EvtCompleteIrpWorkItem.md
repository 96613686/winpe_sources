# HUBPDO_EvtCompleteIrpWorkItem

- ea: `0x140014f10`
- end: `0x140014f72`
- name: `HUBPDO_EvtCompleteIrpWorkItem`
- size: `98`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140045570`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014f42`
- `ntoskrnl!IofCompleteRequest` at `0x140014f42`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtCompleteIrpWorkItem(__int64 a1)
{
  PIRP *v2; // rax

  v2 = (PIRP *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                 WdfDriverGlobals,
                 a1,
                 off_14006B220);
  IofCompleteRequest(*v2, 0);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x140014f10  push    rbx
0x140014f12  sub     rsp, 20h
0x140014f16  mov     rax, cs:WdfFunctions_01015
0x140014f1d  mov     rbx, rcx
0x140014f20  mov     r8, cs:off_14006B220
0x140014f27  mov     rdx, rcx
0x140014f2a  mov     rcx, cs:WdfDriverGlobals
0x140014f31  mov     rax, [rax+650h]
0x140014f38  call    _guard_dispatch_icall
0x140014f3d  xor     edx, edx; PriorityBoost
0x140014f3f  mov     rcx, [rax]; Irp
0x140014f42  call    cs:__imp_IofCompleteRequest
0x140014f49  nop     dword ptr [rax+rax+00h]
0x140014f4e  mov     rax, cs:WdfFunctions_01015
0x140014f55  mov     rdx, rbx
0x140014f58  mov     rcx, cs:WdfDriverGlobals
0x140014f5f  mov     rax, [rax+680h]
0x140014f66  call    _guard_dispatch_icall
0x140014f6b  add     rsp, 20h
0x140014f6f  pop     rbx
0x140014f70  retn
```
