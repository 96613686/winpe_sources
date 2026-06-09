# VmxpDeleteVolumeDeviceWorker(void *)

- ea: `0x140008f90`
- end: `0x140008fcb`
- name: `?VmxpDeleteVolumeDeviceWorker@@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(VMX_VOLUME_DEVICE *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140008e18`
- `0x140008f90`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140008fab`
- `ntoskrnl!KeDelayExecutionThread` at `0x140008fab`

## pseudocode

```c
void __fastcall VmxpDeleteVolumeDeviceWorker(VMX_VOLUME_DEVICE *this)
{
  unsigned int v2; // edx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  Interval.QuadPart = -20000000;
  KeDelayExecutionThread(0, 0, &Interval);
  if ( this )
    VMX_VOLUME_DEVICE::`scalar deleting destructor'(this, v2);
}

```

## disassembly

```asm
0x140008f90  push    rbx
0x140008f92  sub     rsp, 20h
0x140008f96  mov     rbx, rcx
0x140008f99  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFECED300h
0x140008fa2  xor     ecx, ecx; WaitMode
0x140008fa4  lea     r8, [rsp+28h+Interval]; Interval
0x140008fa9  xor     edx, edx; Alertable
0x140008fab  call    cs:__imp_KeDelayExecutionThread
0x140008fb2  nop     dword ptr [rax+rax+00h]
0x140008fb7  test    rbx, rbx
0x140008fba  jz      short loc_140008FC4
0x140008fbc  mov     rcx, rbx; this
0x140008fbf  call    ??_GVMX_VOLUME_DEVICE@@QEAAPEAXI@Z; VMX_VOLUME_DEVICE::`scalar deleting destructor'(uint)
0x140008fc4  add     rsp, 20h
0x140008fc8  pop     rbx
0x140008fc9  retn
```
