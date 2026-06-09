# CallbackFdoDeviceSetDx

- ea: `0x14000a390`
- end: `0x14000a441`
- name: `CallbackFdoDeviceSetDx`
- size: `177`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400054a0`
- `0x1400083c8`
- `0x14000a390`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a3cf`
- `ntoskrnl!IofCompleteRequest` at `0x14000a3cf`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000a3b4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000a3b4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a3f7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a3f7`

## pseudocode

```c
void __fastcall CallbackFdoDeviceSetDx(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        IRP *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  char *DeviceExtension; // rbx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)DeviceExtension + 172),
      4,
      3,
      37,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)DeviceExtension + 5));
  PoStartNextPowerIrp(Context);
  Context->IoStatus.Status = IoStatus->Status;
  IofCompleteRequest(Context, 0);
  UsbcReleaseRemoveLock(DeviceExtension + 8, Context);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 208), Context, 0x20u);
}

```

## disassembly

```asm
0x14000a390  mov     [rsp+arg_0], rbx
0x14000a395  push    rdi
0x14000a396  sub     rsp, 30h
0x14000a39a  mov     rbx, [rcx+40h]
0x14000a39e  mov     rdi, r9
0x14000a3a1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a3a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a3af  jnz     short loc_14000A40F
0x14000a3b1  mov     rcx, rdi; Irp
0x14000a3b4  call    cs:__imp_PoStartNextPowerIrp
0x14000a3bb  nop     dword ptr [rax+rax+00h]
0x14000a3c0  mov     rax, [rsp+38h+IoStatus]
0x14000a3c5  xor     edx, edx; PriorityBoost
0x14000a3c7  mov     ecx, [rax]
0x14000a3c9  mov     [rdi+30h], ecx
0x14000a3cc  mov     rcx, rdi; Irp
0x14000a3cf  call    cs:__imp_IofCompleteRequest
0x14000a3d6  nop     dword ptr [rax+rax+00h]
0x14000a3db  mov     rdx, rdi
0x14000a3de  lea     rcx, [rbx+8]
0x14000a3e2  call    UsbcReleaseRemoveLock
0x14000a3e7  lea     rcx, [rbx+0D0h]; RemoveLock
0x14000a3ee  mov     r8d, 20h ; ' '; RemlockSize
0x14000a3f4  mov     rdx, rdi; Tag
0x14000a3f7  call    cs:__imp_IoReleaseRemoveLockEx
0x14000a3fe  nop     dword ptr [rax+rax+00h]
0x14000a403  mov     rbx, [rsp+38h+arg_0]
0x14000a408  add     rsp, 30h
0x14000a40c  pop     rdi
0x14000a40d  retn
0x14000a40f  mov     rax, [rbx+28h]
0x14000a413  mov     r9d, 25h ; '%'
0x14000a419  mov     rcx, [rbx+560h]
0x14000a420  mov     dl, 4
0x14000a422  mov     [rsp+38h+var_10], rax
0x14000a427  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000a42e  mov     [rsp+38h+var_18], rax
0x14000a433  lea     r8d, [r9-22h]
0x14000a437  call    WPP_RECORDER_SF_q
0x14000a43c  jmp     loc_14000A3B1
```
