# DispatchFdoPower

- ea: `0x140003e88`
- end: `0x140004071`
- name: `DispatchFdoPower`
- size: `489`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140003c28`

## callees

- `0x140003e88`
- `0x140004078`
- `0x1400054a0`
- `0x140008eac`
- `0x14000a1b4`
- `0x14000b4bc`
- `0x14000b670`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x140003f3a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004009`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003f3a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004009`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003f81`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004050`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003f81`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004050`
- `ntoskrnl!PoCallDriver` at `0x140003f58`
- `ntoskrnl!PoCallDriver` at `0x140004027`
- `ntoskrnl!PoCallDriver` at `0x140003f58`
- `ntoskrnl!PoCallDriver` at `0x140004027`

## pseudocode

```c
__int64 __fastcall DispatchFdoPower(char *Context, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PIRP v3; // rbx
  int MinorFunction; // edx
  unsigned int v7; // esi
  int v9; // edx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = Irp;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)Context + 171),
      (_DWORD)Irp,
      3,
      10,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)Context + 4),
      (char)v3);
  }
  if ( *((_DWORD *)Context + 3) )
  {
    MinorFunction = CurrentStackLocation->MinorFunction;
    switch ( CurrentStackLocation->MinorFunction )
    {
      case 0u:
        return (unsigned int)DispatchFdoWaitWake(Context, v3);
      case 2u:
        return (unsigned int)DispatchFdoSetPower(Context, v3);
      case 3u:
        return (unsigned int)DispatchFdoQueryPower(Context, v3);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(MinorFunction) = 4;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)Context + 171),
        MinorFunction,
        3,
        12,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *((_QWORD *)Context + 4),
        CurrentStackLocation->MinorFunction);
    }
    PoStartNextPowerIrp(v3);
    ++v3->CurrentLocation;
    ++v3->Tail.Overlay.CurrentStackLocation;
    v7 = PoCallDriver(*((PDEVICE_OBJECT *)Context + 5), v3);
    UsbcReleaseRemoveLock(Context, v3);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v3, 0x20u);
  }
  else
  {
    PoStartNextPowerIrp(v3);
    ++v3->CurrentLocation;
    ++v3->Tail.Overlay.CurrentStackLocation;
    v7 = PoCallDriver(*((PDEVICE_OBJECT *)Context + 5), v3);
    UsbcReleaseRemoveLock(Context, v3);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v3, 0x20u);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)Context + 171),
        v9,
        3,
        11,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *((_QWORD *)Context + 4),
        (char)v3);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140003e88  push    rbx
0x140003e8a  push    rbp
0x140003e8b  push    rsi
0x140003e8c  push    rdi
0x140003e8d  push    r12
0x140003e8f  push    r14
0x140003e91  sub     rsp, 48h
0x140003e95  mov     rsi, [rdx+0B8h]
0x140003e9c  mov     rbx, rdx
0x140003e9f  mov     rdi, rcx
0x140003ea2  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003ea9  xor     ebp, ebp
0x140003eab  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003eb2  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140003eb9  jz      short loc_140003EC8
0x140003ebb  mov     rax, cs:WPP_GLOBAL_Control
0x140003ec2  cmp     [rax+48h], bp
0x140003ec6  jnz     short loc_140003F0A
0x140003ec8  cmp     [rdi+0Ch], ebp
0x140003ecb  jz      short loc_140003F37
0x140003ecd  movzx   edx, byte ptr [rsi+1]
0x140003ed1  mov     ecx, edx
0x140003ed3  test    edx, edx
0x140003ed5  jz      short loc_140003EFD
0x140003ed7  sub     ecx, 2
0x140003eda  jnz     loc_140003FCA
0x140003ee0  mov     rdx, rbx; Irp
0x140003ee3  mov     rcx, rdi; Context
0x140003ee6  call    DispatchFdoSetPower
0x140003eeb  mov     esi, eax
0x140003eed  mov     eax, esi
0x140003eef  add     rsp, 48h
0x140003ef3  pop     r14
0x140003ef5  pop     r12
0x140003ef7  pop     rdi
0x140003ef8  pop     rsi
0x140003ef9  pop     rbp
0x140003efa  pop     rbx
0x140003efb  retn
0x140003efd  mov     rdx, rbx
0x140003f00  mov     rcx, rdi
0x140003f03  call    DispatchFdoWaitWake
0x140003f08  jmp     short loc_140003EEB
0x140003f0a  mov     rax, [rcx+20h]
0x140003f0e  mov     r9d, 0Ah
0x140003f14  mov     rcx, [rcx+558h]
0x140003f1b  mov     dl, 5
0x140003f1d  mov     [rsp+78h+var_48], rbx
0x140003f22  mov     [rsp+78h+var_50], rax
0x140003f27  lea     r8d, [r9-7]
0x140003f2b  mov     [rsp+78h+var_58], r12
0x140003f30  call    WPP_RECORDER_SF_qq
0x140003f35  jmp     short loc_140003EC8
0x140003f37  mov     rcx, rbx; Irp
0x140003f3a  call    cs:__imp_PoStartNextPowerIrp
0x140003f41  nop     dword ptr [rax+rax+00h]
0x140003f46  inc     byte ptr [rbx+43h]
0x140003f49  mov     rdx, rbx; Irp
0x140003f4c  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140003f54  mov     rcx, [rdi+28h]; DeviceObject
0x140003f58  call    cs:__imp_PoCallDriver
0x140003f5f  nop     dword ptr [rax+rax+00h]
0x140003f64  mov     rdx, rbx
0x140003f67  mov     rcx, rdi
0x140003f6a  mov     esi, eax
0x140003f6c  call    UsbcReleaseRemoveLock
0x140003f71  lea     rcx, [rdi+0C8h]; RemoveLock
0x140003f78  mov     r8d, 20h ; ' '; RemlockSize
0x140003f7e  mov     rdx, rbx; Tag
0x140003f81  call    cs:__imp_IoReleaseRemoveLockEx
0x140003f88  nop     dword ptr [rax+rax+00h]
0x140003f8d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140003f94  jz      loc_140003EED
0x140003f9a  mov     rax, [rdi+20h]
0x140003f9e  mov     r9d, 0Bh
0x140003fa4  mov     rcx, [rdi+558h]
0x140003fab  mov     dl, 4
0x140003fad  mov     [rsp+78h+var_48], rbx
0x140003fb2  mov     [rsp+78h+var_50], rax
0x140003fb7  lea     r8d, [r9-8]
0x140003fbb  mov     [rsp+78h+var_58], r12
0x140003fc0  call    WPP_RECORDER_SF_qq
0x140003fc5  jmp     loc_140003EED
0x140003fca  cmp     ecx, 1
0x140003fcd  jz      loc_140004061
0x140003fd3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140003fda  jz      short loc_140004006
0x140003fdc  mov     rax, [rdi+20h]
0x140003fe0  mov     r9d, 0Ch
0x140003fe6  mov     rcx, [rdi+558h]
0x140003fed  mov     dword ptr [rsp+78h+var_48], edx
0x140003ff1  mov     dl, 4
0x140003ff3  mov     [rsp+78h+var_50], rax
0x140003ff8  lea     r8d, [r9-9]
0x140003ffc  mov     [rsp+78h+var_58], r12
0x140004001  call    WPP_RECORDER_SF_qD
0x140004006  mov     rcx, rbx; Irp
0x140004009  call    cs:__imp_PoStartNextPowerIrp
0x140004010  nop     dword ptr [rax+rax+00h]
0x140004015  inc     byte ptr [rbx+43h]
0x140004018  mov     rdx, rbx; Irp
0x14000401b  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140004023  mov     rcx, [rdi+28h]; DeviceObject
0x140004027  call    cs:__imp_PoCallDriver
0x14000402e  nop     dword ptr [rax+rax+00h]
0x140004033  mov     rdx, rbx
0x140004036  mov     rcx, rdi
0x140004039  mov     esi, eax
0x14000403b  call    UsbcReleaseRemoveLock
0x140004040  lea     rcx, [rdi+0C8h]; RemoveLock
0x140004047  mov     r8d, 20h ; ' '; RemlockSize
0x14000404d  mov     rdx, rbx; Tag
0x140004050  call    cs:__imp_IoReleaseRemoveLockEx
0x140004057  nop     dword ptr [rax+rax+00h]
0x14000405c  jmp     loc_140003EED
0x140004061  mov     rdx, rbx
0x140004064  mov     rcx, rdi
0x140004067  call    DispatchFdoQueryPower
0x14000406c  jmp     loc_140003EEB
```
