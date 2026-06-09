# RpcXdrDispatchDeviceControl

- ea: `0x140020600`
- end: `0x14002062f`
- name: `RpcXdrDispatchDeviceControl`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020618`
- `ntoskrnl!IofCompleteRequest` at `0x140020618`

## pseudocode

```c
__int64 __fastcall RpcXdrDispatchDeviceControl(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = -1073741808;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x140020600  sub     rsp, 28h
0x140020604  mov     rcx, rdx; Irp
0x140020607  mov     dword ptr [rdx+30h], 0C0000010h
0x14002060e  mov     qword ptr [rdx+38h], 0
0x140020616  xor     edx, edx; PriorityBoost
0x140020618  call    cs:__imp_IofCompleteRequest
0x14002061f  nop     dword ptr [rax+rax+00h]
0x140020624  mov     eax, 0C0000010h
0x140020629  add     rsp, 28h
0x14002062d  retn
```
