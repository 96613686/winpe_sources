# DispatchPdoSetPower_SetParentD0Completion

- ea: `0x140007e70`
- end: `0x140007f86`
- name: `DispatchPdoSetPower_SetParentD0Completion`
- size: `278`
- prototype: `__int64 __fastcall(PVOID PeekContext, PVOID Tag)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054a0`
- `0x140006f58`
- `0x140007e70`
- `0x140008eac`
- `0x140009804`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140007ee5`
- `ntoskrnl!IofCompleteRequest` at `0x140007ee5`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140007ecd`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140007ecd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007f0c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007f0c`
- `ntoskrnl!PoSetPowerState` at `0x140007eab`
- `ntoskrnl!PoSetPowerState` at `0x140007eab`

## pseudocode

```c
void __fastcall DispatchPdoSetPower_SetParentD0Completion(_QWORD *PeekContext, IRP *Tag, int a3)
{
  __int64 v3; // rsi
  IRP *v4; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  struct _DEVICE_OBJECT *v7; // rcx

  v3 = PeekContext[29];
  v4 = Tag;
  CurrentStackLocation = Tag->Tail.Overlay.CurrentStackLocation;
  if ( a3 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Tag) = 4;
    WPP_RECORDER_SF_qq(
      *(_QWORD *)(v3 + 1368),
      (_DWORD)Tag,
      3,
      62,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      PeekContext[28],
      (char)v4);
  }
  v7 = (struct _DEVICE_OBJECT *)PeekContext[28];
  *((_DWORD *)PeekContext + 4) = 1;
  PoSetPowerState(v7, CurrentStackLocation->Parameters.Power.Type, CurrentStackLocation->Parameters.Power.State);
  CompleteFunctionIdleIrp((char *)PeekContext, 0);
  if ( *(_BYTE *)(v3 + 1362) )
  {
    LockSendSetFeatureControlRequestForFunctionSuspend(v3, PeekContext, v4, 2);
  }
  else
  {
    PoStartNextPowerIrp(v4);
    v4->IoStatus.Status = 0;
    IofCompleteRequest(v4, 0);
    UsbcReleaseRemoveLock(v3, v4);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 200), v4, 0x20u);
  }
}

```

## disassembly

```asm
0x140007e70  push    rbx
0x140007e72  push    rbp
0x140007e73  push    rsi
0x140007e74  push    rdi
0x140007e75  sub     rsp, 48h
0x140007e79  mov     rsi, [rcx+0E8h]
0x140007e80  mov     rbx, rdx
0x140007e83  mov     rbp, [rdx+0B8h]
0x140007e8a  mov     rdi, rcx
0x140007e8d  test    r8d, r8d
0x140007e90  js      loc_140007F38
0x140007e96  mov     rcx, [rdi+0E0h]; DeviceObject
0x140007e9d  mov     dword ptr [rdi+10h], 1
0x140007ea4  mov     r8d, [rbp+18h]; State
0x140007ea8  mov     edx, [rbp+10h]; Type
0x140007eab  call    cs:__imp_PoSetPowerState
0x140007eb2  nop     dword ptr [rax+rax+00h]
0x140007eb7  xor     edx, edx
0x140007eb9  mov     rcx, rdi; PeekContext
0x140007ebc  call    CompleteFunctionIdleIrp
0x140007ec1  cmp     byte ptr [rsi+552h], 0
0x140007ec8  jnz     short loc_140007F22
0x140007eca  mov     rcx, rbx; Irp
0x140007ecd  call    cs:__imp_PoStartNextPowerIrp
0x140007ed4  nop     dword ptr [rax+rax+00h]
0x140007ed9  xor     edx, edx; PriorityBoost
0x140007edb  mov     dword ptr [rbx+30h], 0
0x140007ee2  mov     rcx, rbx; Irp
0x140007ee5  call    cs:__imp_IofCompleteRequest
0x140007eec  nop     dword ptr [rax+rax+00h]
0x140007ef1  mov     rdx, rbx
0x140007ef4  mov     rcx, rsi
0x140007ef7  call    UsbcReleaseRemoveLock
0x140007efc  lea     rcx, [rsi+0C8h]; RemoveLock
0x140007f03  mov     r8d, 20h ; ' '; RemlockSize
0x140007f09  mov     rdx, rbx; Tag
0x140007f0c  call    cs:__imp_IoReleaseRemoveLockEx
0x140007f13  nop     dword ptr [rax+rax+00h]
0x140007f18  add     rsp, 48h
0x140007f1c  pop     rdi
0x140007f1d  pop     rsi
0x140007f1e  pop     rbp
0x140007f1f  pop     rbx
0x140007f20  retn
0x140007f22  mov     r9d, 2
0x140007f28  mov     r8, rbx
0x140007f2b  mov     rdx, rdi
0x140007f2e  mov     rcx, rsi
0x140007f31  call    LockSendSetFeatureControlRequestForFunctionSuspend
0x140007f36  jmp     short loc_140007F18
0x140007f38  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007f3f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007f46  jz      loc_140007E96
0x140007f4c  mov     rax, [rcx+0E0h]
0x140007f53  mov     r9d, 3Eh ; '>'
0x140007f59  mov     rcx, [rsi+558h]
0x140007f60  mov     dl, 4
0x140007f62  mov     [rsp+68h+var_38], rbx
0x140007f67  mov     [rsp+68h+var_40], rax
0x140007f6c  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140007f73  lea     r8d, [r9-3Bh]
0x140007f77  mov     [rsp+68h+var_48], rax
0x140007f7c  call    WPP_RECORDER_SF_qq
0x140007f81  jmp     loc_140007E96
```
