# CompletionFdoDeviceSetPower

- ea: `0x140005350`
- end: `0x140005493`
- name: `CompletionFdoDeviceSetPower`
- size: `323`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005350`
- `0x1400054a0`
- `0x14000554c`
- `0x1400083c8`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x1400053c4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400053c4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400053fc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400053fc`
- `ntoskrnl!PoSetPowerState` at `0x1400053b5`
- `ntoskrnl!PoSetPowerState` at `0x1400053b5`

## pseudocode

```c
__int64 __fastcall CompletionFdoDeviceSetPower(PDEVICE_OBJECT DeviceObject, PIRP Irp, char *Context)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PIRP v5; // rdi
  int Status; // ecx
  struct _DEVICE_OBJECT *v7; // rcx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = Irp;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
  {
    if ( Context[441] )
      GetD3ColdLastTransitionStatus(Context);
    Status = v5->IoStatus.Status;
    if ( Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(Irp) = 2;
        WPP_RECORDER_SF_qD(
          *((_QWORD *)Context + 171),
          (_DWORD)Irp,
          3,
          14,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *((_QWORD *)Context + 4),
          Status);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(Irp) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)Context + 171),
          (_DWORD)Irp,
          3,
          13,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *((_QWORD *)Context + 4));
      }
      v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)Context + 4);
      *((_DWORD *)Context + 1) = 1;
      PoSetPowerState(v7, CurrentStackLocation->Parameters.Power.Type, CurrentStackLocation->Parameters.Power.State);
    }
  }
  PoStartNextPowerIrp(v5);
  if ( v5->PendingReturned )
    v5->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  UsbcReleaseRemoveLock(Context, v5);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v5, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x140005350  mov     [rsp+arg_0], rbx
0x140005355  mov     [rsp+arg_8], rsi
0x14000535a  push    rdi
0x14000535b  sub     rsp, 40h
0x14000535f  mov     rsi, [rdx+0B8h]
0x140005366  mov     rbx, r8
0x140005369  mov     rdi, rdx
0x14000536c  cmp     dword ptr [rsi+18h], 1
0x140005370  jnz     short loc_1400053C1
0x140005372  cmp     byte ptr [r8+1B9h], 0
0x14000537a  jz      short loc_140005384
0x14000537c  mov     rcx, rbx
0x14000537f  call    GetD3ColdLastTransitionStatus
0x140005384  mov     ecx, [rdi+30h]
0x140005387  test    ecx, ecx
0x140005389  js      loc_14000541B
0x14000538f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005396  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000539d  jnz     loc_140005461
0x1400053a3  mov     rcx, [rbx+20h]; DeviceObject
0x1400053a7  mov     dword ptr [rbx+4], 1
0x1400053ae  mov     r8d, [rsi+18h]; State
0x1400053b2  mov     edx, [rsi+10h]; Type
0x1400053b5  call    cs:__imp_PoSetPowerState
0x1400053bc  nop     dword ptr [rax+rax+00h]
0x1400053c1  mov     rcx, rdi; Irp
0x1400053c4  call    cs:__imp_PoStartNextPowerIrp
0x1400053cb  nop     dword ptr [rax+rax+00h]
0x1400053d0  cmp     byte ptr [rdi+41h], 0
0x1400053d4  jz      short loc_1400053E1
0x1400053d6  mov     rax, [rdi+0B8h]
0x1400053dd  or      byte ptr [rax+3], 1
0x1400053e1  mov     rdx, rdi
0x1400053e4  mov     rcx, rbx
0x1400053e7  call    UsbcReleaseRemoveLock
0x1400053ec  lea     rcx, [rbx+0C8h]; RemoveLock
0x1400053f3  mov     r8d, 20h ; ' '; RemlockSize
0x1400053f9  mov     rdx, rdi; Tag
0x1400053fc  call    cs:__imp_IoReleaseRemoveLockEx
0x140005403  nop     dword ptr [rax+rax+00h]
0x140005408  mov     rbx, [rsp+48h+arg_0]
0x14000540d  xor     eax, eax
0x14000540f  mov     rsi, [rsp+48h+arg_8]
0x140005414  add     rsp, 40h
0x140005418  pop     rdi
0x140005419  retn
0x14000541b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005422  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005429  jz      short loc_1400053C1
0x14000542b  mov     rax, [rbx+20h]
0x14000542f  mov     r9d, 0Eh
0x140005435  mov     [rsp+48h+var_18], ecx
0x140005439  mov     dl, 2
0x14000543b  mov     rcx, [rbx+558h]
0x140005442  mov     [rsp+48h+var_20], rax
0x140005447  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000544e  lea     r8d, [r9-0Bh]
0x140005452  mov     [rsp+48h+var_28], rax
0x140005457  call    WPP_RECORDER_SF_qD
0x14000545c  jmp     loc_1400053C1
0x140005461  mov     rax, [rbx+20h]
0x140005465  mov     r9d, 0Dh
0x14000546b  mov     rcx, [rbx+558h]
0x140005472  mov     dl, 4
0x140005474  mov     [rsp+48h+var_20], rax
0x140005479  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140005480  mov     [rsp+48h+var_28], rax
0x140005485  lea     r8d, [r9-0Ah]
0x140005489  call    WPP_RECORDER_SF_q
0x14000548e  jmp     loc_1400053A3
```
