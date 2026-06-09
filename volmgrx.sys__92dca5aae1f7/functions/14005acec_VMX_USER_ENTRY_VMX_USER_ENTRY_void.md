# VMX_USER_ENTRY::~VMX_USER_ENTRY(void)

- ea: `0x14005acec`
- end: `0x14005ad18`
- name: `??1VMX_USER_ENTRY@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(VMX_USER_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001b334`

## callees

- `0x14001b35c`
- `0x14005acec`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005ad06`
- `ntoskrnl!IofCompleteRequest` at `0x14005ad06`

## pseudocode

```c
void __fastcall VMX_USER_ENTRY::~VMX_USER_ENTRY(VMX_USER_ENTRY *this)
{
  struct _IRP *NotificationsIrp; // rax

  NotificationsIrp = VmxpDequeueGetNotificationsIrp(this);
  if ( NotificationsIrp )
  {
    NotificationsIrp->IoStatus.Status = -1073741536;
    IofCompleteRequest(NotificationsIrp, 0);
  }
}

```

## disassembly

```asm
0x14005acec  sub     rsp, 28h
0x14005acf0  call    ?VmxpDequeueGetNotificationsIrp@@YAPEAU_IRP@@PEAVVMX_USER_ENTRY@@@Z; VmxpDequeueGetNotificationsIrp(VMX_USER_ENTRY *)
0x14005acf5  test    rax, rax
0x14005acf8  jz      short loc_14005AD12
0x14005acfa  xor     edx, edx; PriorityBoost
0x14005acfc  mov     dword ptr [rax+30h], 0C0000120h
0x14005ad03  mov     rcx, rax; Irp
0x14005ad06  call    cs:__imp_IofCompleteRequest
0x14005ad0d  nop     dword ptr [rax+rax+00h]
0x14005ad12  add     rsp, 28h
0x14005ad16  retn
```
