# RpcXdrDispatchCreate

- ea: `0x1400205c0`
- end: `0x1400205ec`
- name: `RpcXdrDispatchCreate`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400205d8`
- `ntoskrnl!IofCompleteRequest` at `0x1400205d8`

## pseudocode

```c
__int64 __fastcall RpcXdrDispatchCreate(__int64 a1, IRP *a2)
{
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1400205c0  sub     rsp, 28h
0x1400205c4  mov     rcx, rdx; Irp
0x1400205c7  mov     qword ptr [rdx+38h], 0
0x1400205cf  mov     dword ptr [rdx+30h], 0
0x1400205d6  xor     edx, edx; PriorityBoost
0x1400205d8  call    cs:__imp_IofCompleteRequest
0x1400205df  nop     dword ptr [rax+rax+00h]
0x1400205e4  xor     eax, eax
0x1400205e6  add     rsp, 28h
0x1400205ea  retn
```
