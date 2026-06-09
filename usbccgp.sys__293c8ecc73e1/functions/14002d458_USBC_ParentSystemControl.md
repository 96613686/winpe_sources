# USBC_ParentSystemControl

- ea: `0x14002d458`
- end: `0x14002d51e`
- name: `USBC_ParentSystemControl`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002d418`

## callees

- `0x1400029d0`
- `0x1400054a0`
- `0x14002d458`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002d510`
- `ntoskrnl!IofCompleteRequest` at `0x14002d510`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d4ec`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d4ec`
- `WMILIB!WmiSystemControl` at `0x14002d4bb`
- `WMILIB!WmiSystemControl` at `0x14002d4bb`

## pseudocode

```c
__int64 __fastcall USBC_ParentSystemControl(__int64 a1, IRP *a2)
{
  bool v2; // zf
  __int64 v4; // rbx
  __int64 v5; // rdx
  unsigned int v6; // esi
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_BYTE *)(a1 + 1152) == 0;
  v4 = a1;
  IrpDisposition = IrpProcessed;
  if ( v2 || !wmiInit )
  {
    v5 = *(_QWORD *)(a1 + 40);
  }
  else
  {
    v6 = WmiSystemControl((PWMILIB_CONTEXT)(a1 + 1160), *(PDEVICE_OBJECT *)(a1 + 32), a2, &IrpDisposition);
    if ( IrpDisposition == IrpProcessed )
    {
LABEL_7:
      UsbcReleaseRemoveLock(v4, a2);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 200), a2, 0x20u);
      return v6;
    }
    if ( IrpDisposition == IrpNotCompleted )
    {
      IofCompleteRequest(a2, 0);
      goto LABEL_7;
    }
    v5 = *(_QWORD *)(v4 + 40);
    a1 = v4;
  }
  return (unsigned int)UsbcForwardIrp(a1, v5, a2);
}

```

## disassembly

```asm
0x14002d458  mov     [rsp+arg_8], rbx
0x14002d45d  mov     [rsp+arg_10], rsi
0x14002d462  push    rdi
0x14002d463  sub     rsp, 20h
0x14002d467  cmp     byte ptr [rcx+480h], 0
0x14002d46e  mov     rdi, rdx
0x14002d471  mov     rbx, rcx
0x14002d474  mov     [rsp+28h+IrpDisposition], 0
0x14002d47c  jnz     short loc_14002D49F
0x14002d47e  mov     rdx, [rcx+28h]
0x14002d482  mov     r8, rdi
0x14002d485  call    UsbcForwardIrp
0x14002d48a  mov     esi, eax
0x14002d48c  mov     rbx, [rsp+28h+arg_8]
0x14002d491  mov     eax, esi
0x14002d493  mov     rsi, [rsp+28h+arg_10]
0x14002d498  add     rsp, 20h
0x14002d49c  pop     rdi
0x14002d49d  retn
0x14002d49f  cmp     cs:wmiInit, 0
0x14002d4a6  jz      short loc_14002D47E
0x14002d4a8  mov     rdx, [rbx+20h]; DeviceObject
0x14002d4ac  lea     r9, [rsp+28h+IrpDisposition]; IrpDisposition
0x14002d4b1  add     rcx, 488h; WmiLibInfo
0x14002d4b8  mov     r8, rdi; Irp
0x14002d4bb  call    cs:__imp_WmiSystemControl
0x14002d4c2  nop     dword ptr [rax+rax+00h]
0x14002d4c7  mov     edx, [rsp+28h+IrpDisposition]
0x14002d4cb  mov     esi, eax
0x14002d4cd  test    edx, edx
0x14002d4cf  jnz     short loc_14002D4FA
0x14002d4d1  mov     rdx, rdi
0x14002d4d4  mov     rcx, rbx
0x14002d4d7  call    UsbcReleaseRemoveLock
0x14002d4dc  lea     rcx, [rbx+0C8h]; RemoveLock
0x14002d4e3  mov     r8d, 20h ; ' '; RemlockSize
0x14002d4e9  mov     rdx, rdi; Tag
0x14002d4ec  call    cs:__imp_IoReleaseRemoveLockEx
0x14002d4f3  nop     dword ptr [rax+rax+00h]
0x14002d4f8  jmp     short loc_14002D48C
0x14002d4fa  sub     edx, 1
0x14002d4fd  jz      short loc_14002D50B
0x14002d4ff  mov     rdx, [rbx+28h]
0x14002d503  mov     rcx, rbx
0x14002d506  jmp     loc_14002D482
0x14002d50b  xor     edx, edx; PriorityBoost
0x14002d50d  mov     rcx, rdi; Irp
0x14002d510  call    cs:__imp_IofCompleteRequest
0x14002d517  nop     dword ptr [rax+rax+00h]
0x14002d51c  jmp     short loc_14002D4D1
```
