# DispatchPdoPower

- ea: `0x140003d08`
- end: `0x140003e80`
- name: `DispatchPdoPower`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003c28`

## callees

- `0x140003d08`
- `0x1400054a0`
- `0x140005fc4`
- `0x140008b00`
- `0x14000b4bc`
- `0x14000b8cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003d8b`
- `ntoskrnl!IofCompleteRequest` at `0x140003d8b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003d44`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003d44`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003db2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003db2`

## pseudocode

```c
__int64 __fastcall DispatchPdoPower(_QWORD *a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 v4; // rsi
  unsigned int Status; // ebx
  int v7; // edx
  unsigned int Options; // eax
  int v9; // r9d

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = a1[29];
  if ( !CurrentStackLocation->MinorFunction )
  {
    Status = DispatchPdoWaitWake(a1, a2);
    goto LABEL_5;
  }
  if ( CurrentStackLocation->MinorFunction == 1 )
  {
LABEL_3:
    Status = a2->IoStatus.Status;
LABEL_4:
    PoStartNextPowerIrp(a2);
    goto LABEL_5;
  }
  v7 = CurrentStackLocation->MinorFunction - 2;
  if ( CurrentStackLocation->MinorFunction != 2 )
  {
    if ( CurrentStackLocation->MinorFunction != 3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 4;
        WPP_RECORDER_SF_qD(
          *(_QWORD *)(v4 + 1368),
          v7,
          3,
          40,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          (char)a2,
          CurrentStackLocation->MinorFunction);
      }
      goto LABEL_3;
    }
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( Options )
    {
      if ( Options != 1 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_16;
      v9 = 39;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_16:
        Status = 0;
        goto LABEL_4;
      }
      v9 = 38;
    }
    WPP_RECORDER_SF_qqL(a1[49], 1, (_DWORD)CurrentStackLocation, v9);
    goto LABEL_16;
  }
  Status = DispatchPdoSetPower(a1);
  if ( Status != 259 )
    goto LABEL_4;
LABEL_5:
  if ( Status != 259 )
  {
    a2->IoStatus.Status = Status;
    IofCompleteRequest(a2, 0);
    UsbcReleaseRemoveLock(v4, a2);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 200), a2, 0x20u);
  }
  return Status;
}

```

## disassembly

```asm
0x140003d08  mov     [rsp+arg_0], rbx
0x140003d0d  mov     [rsp+arg_8], rsi
0x140003d12  push    rdi
0x140003d13  sub     rsp, 40h
0x140003d17  mov     r8, [rdx+0B8h]
0x140003d1e  mov     rdi, rdx
0x140003d21  mov     rsi, [rcx+0E8h]
0x140003d28  movzx   r10d, byte ptr [r8+1]
0x140003d2d  mov     edx, r10d
0x140003d30  test    r10d, r10d
0x140003d33  jz      loc_140003E71
0x140003d39  sub     edx, 1
0x140003d3c  jnz     short loc_140003D6B
0x140003d3e  mov     ebx, [rdi+30h]
0x140003d41  mov     rcx, rdi; Irp
0x140003d44  call    cs:__imp_PoStartNextPowerIrp
0x140003d4b  nop     dword ptr [rax+rax+00h]
0x140003d50  cmp     ebx, 103h
0x140003d56  jnz     short loc_140003D83
0x140003d58  mov     rsi, [rsp+48h+arg_8]
0x140003d5d  mov     eax, ebx
0x140003d5f  mov     rbx, [rsp+48h+arg_0]
0x140003d64  add     rsp, 40h
0x140003d68  pop     rdi
0x140003d69  retn
0x140003d6b  sub     edx, 1
0x140003d6e  jnz     short loc_140003DC0
0x140003d70  mov     rdx, rdi
0x140003d73  call    DispatchPdoSetPower
0x140003d78  mov     ebx, eax
0x140003d7a  cmp     eax, 103h
0x140003d7f  jnz     short loc_140003D41
0x140003d81  jmp     short loc_140003D50
0x140003d83  xor     edx, edx; PriorityBoost
0x140003d85  mov     [rdi+30h], ebx
0x140003d88  mov     rcx, rdi; Irp
0x140003d8b  call    cs:__imp_IofCompleteRequest
0x140003d92  nop     dword ptr [rax+rax+00h]
0x140003d97  mov     rdx, rdi
0x140003d9a  mov     rcx, rsi
0x140003d9d  call    UsbcReleaseRemoveLock
0x140003da2  lea     rcx, [rsi+0C8h]; RemoveLock
0x140003da9  mov     r8d, 20h ; ' '; RemlockSize
0x140003daf  mov     rdx, rdi; Tag
0x140003db2  call    cs:__imp_IoReleaseRemoveLockEx
0x140003db9  nop     dword ptr [rax+rax+00h]
0x140003dbe  jmp     short loc_140003D58
0x140003dc0  cmp     edx, 1
0x140003dc3  jnz     short loc_140003E2A
0x140003dc5  mov     eax, [r8+10h]
0x140003dc9  test    eax, eax
0x140003dcb  jnz     short loc_140003E0D
0x140003dcd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003dd4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003ddb  jz      short loc_140003E06
0x140003ddd  lea     r9d, [rdx+25h]
0x140003de1  mov     eax, [r8+18h]
0x140003de5  mov     [rsp+48h+var_10], eax
0x140003de9  mov     rax, [rcx+0E0h]
0x140003df0  mov     rcx, [rcx+188h]
0x140003df7  mov     [rsp+48h+var_18], rdi
0x140003dfc  mov     [rsp+48h+var_20], rax
0x140003e01  call    WPP_RECORDER_SF_qqL
0x140003e06  xor     ebx, ebx
0x140003e08  jmp     loc_140003D41
0x140003e0d  cmp     eax, 1
0x140003e10  jnz     short loc_140003E06
0x140003e12  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003e19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003e20  jz      short loc_140003E06
0x140003e22  mov     r9d, 27h ; '''
0x140003e28  jmp     short loc_140003DE1
0x140003e2a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003e31  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003e38  jz      loc_140003D3E
0x140003e3e  mov     rcx, [rsi+558h]
0x140003e45  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140003e4c  mov     dword ptr [rsp+48h+var_18], r10d
0x140003e51  mov     r9d, 28h ; '('
0x140003e57  mov     [rsp+48h+var_20], rdi
0x140003e5c  mov     dl, 4
0x140003e5e  mov     [rsp+48h+var_28], rax
0x140003e63  lea     r8d, [r9-25h]
0x140003e67  call    WPP_RECORDER_SF_qD
0x140003e6c  jmp     loc_140003D3E
0x140003e71  mov     rdx, rdi
0x140003e74  call    DispatchPdoWaitWake
0x140003e79  mov     ebx, eax
0x140003e7b  jmp     loc_140003D50
```
