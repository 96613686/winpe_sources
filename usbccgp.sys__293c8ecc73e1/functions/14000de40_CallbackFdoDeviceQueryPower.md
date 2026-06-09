# CallbackFdoDeviceQueryPower

- ea: `0x14000de40`
- end: `0x14000deaf`
- name: `CallbackFdoDeviceQueryPower`
- size: `111`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400054a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000de6f`
- `ntoskrnl!IofCompleteRequest` at `0x14000de6f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000de54`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000de54`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000de97`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000de97`

## pseudocode

```c
void __fastcall CallbackFdoDeviceQueryPower(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        IRP *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  char *DeviceExtension; // rbx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  PoStartNextPowerIrp(Context);
  Context->IoStatus.Status = IoStatus->Status;
  IofCompleteRequest(Context, 0);
  UsbcReleaseRemoveLock(DeviceExtension + 8, Context);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 208), Context, 0x20u);
}

```

## disassembly

```asm
0x14000de40  mov     [rsp+arg_0], rbx
0x14000de45  push    rdi
0x14000de46  sub     rsp, 20h
0x14000de4a  mov     rbx, [rcx+40h]
0x14000de4e  mov     rdi, r9
0x14000de51  mov     rcx, r9; Irp
0x14000de54  call    cs:__imp_PoStartNextPowerIrp
0x14000de5b  nop     dword ptr [rax+rax+00h]
0x14000de60  mov     rax, [rsp+28h+IoStatus]
0x14000de65  xor     edx, edx; PriorityBoost
0x14000de67  mov     ecx, [rax]
0x14000de69  mov     [rdi+30h], ecx
0x14000de6c  mov     rcx, rdi; Irp
0x14000de6f  call    cs:__imp_IofCompleteRequest
0x14000de76  nop     dword ptr [rax+rax+00h]
0x14000de7b  mov     rdx, rdi
0x14000de7e  lea     rcx, [rbx+8]
0x14000de82  call    UsbcReleaseRemoveLock
0x14000de87  lea     rcx, [rbx+0D0h]; RemoveLock
0x14000de8e  mov     r8d, 20h ; ' '; RemlockSize
0x14000de94  mov     rdx, rdi; Tag
0x14000de97  call    cs:__imp_IoReleaseRemoveLockEx
0x14000de9e  nop     dword ptr [rax+rax+00h]
0x14000dea3  mov     rbx, [rsp+28h+arg_0]
0x14000dea8  add     rsp, 20h
0x14000deac  pop     rdi
0x14000dead  retn
```
