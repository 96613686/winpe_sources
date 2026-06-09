# PgmDispatchCreate

- ea: `0x1400078e0`
- end: `0x140007aa7`
- name: `PgmDispatchCreate`
- size: `455`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001a50`
- `0x140005038`
- `0x1400052e4`
- `0x140005328`
- `0x14000738c`
- `0x140007414`
- `0x1400078e0`
- `0x140036008`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140007975`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007975`
- `ntoskrnl!ExAllocatePool2` at `0x140007956`
- `ntoskrnl!ExAllocatePool2` at `0x140007956`

## pseudocode

```c
__int64 __fastcall PgmDispatchCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IRP *MasterIrp; // rbx
  UCHAR Control; // bp
  _QWORD *Pool2; // rax
  _QWORD *v7; // rbx
  unsigned int Connection; // ebx
  __int64 EA; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  Control = CurrentStackLocation->Control;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 259;
  CurrentStackLocation->Control |= 1u;
  if ( !MasterIrp )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_a24bb4c2db3a31577af78786167edc49_Traceguids,
        CurrentStackLocation->FileObject);
    Pool2 = (_QWORD *)ExAllocatePool2(64, 40, 812476240);
    v7 = Pool2;
    if ( Pool2 )
    {
      Pool2[1] = Pool2;
      *Pool2 = Pool2;
      KeInitializeSpinLock(Pool2 + 3);
      ++*((_DWORD *)v7 + 5);
      *((_DWORD *)v7 + 4) = 1414418243;
      CurrentStackLocation->FileObject->FsContext = v7;
      Connection = 0;
      CurrentStackLocation->FileObject->FsContext2 = (PVOID)3;
    }
    else
    {
      Connection = -1073741670;
    }
    goto LABEL_23;
  }
  EA = FindEA(MasterIrp, "ConnectionContext");
  if ( EA )
  {
    Connection = PgmCreateConnection(v11, v10, CurrentStackLocation, EA);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v13 = 18;
LABEL_16:
      WPP_SF_qD(AttachedDevice, v13, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids, a2, Connection);
    }
  }
  else
  {
    v14 = FindEA(MasterIrp, "TransportAddress");
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids);
      Connection = -2147483629;
      goto LABEL_23;
    }
    Connection = PgmCreateAddress(v16, v15, CurrentStackLocation, v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v13 = 19;
      goto LABEL_16;
    }
  }
  if ( Connection != 259 )
  {
LABEL_23:
    CurrentStackLocation->Control = Control;
    CompleteDispatchIrp(a2);
  }
  return Connection;
}

```

## disassembly

```asm
0x1400078e0  push    rbx
0x1400078e2  push    rbp
0x1400078e3  push    rsi
0x1400078e4  push    rdi
0x1400078e5  sub     rsp, 38h
0x1400078e9  mov     rdi, [rdx+0B8h]
0x1400078f0  mov     rsi, rdx
0x1400078f3  mov     rbx, [rdx+18h]
0x1400078f7  mov     bpl, [rdi+3]
0x1400078fb  mov     qword ptr [rdx+38h], 0
0x140007903  mov     dword ptr [rdx+30h], 103h
0x14000790a  or      byte ptr [rdi+3], 1
0x14000790e  test    rbx, rbx
0x140007911  jnz     loc_1400079B0
0x140007917  mov     rcx, cs:WPP_GLOBAL_Control
0x14000791e  lea     rax, WPP_GLOBAL_Control
0x140007925  cmp     rcx, rax
0x140007928  jz      short loc_140007948
0x14000792a  mov     eax, [rcx+2Ch]
0x14000792d  test    al, 10h
0x14000792f  jz      short loc_140007948
0x140007931  mov     r9, [rdi+30h]
0x140007935  lea     edx, [rbx+11h]
0x140007938  mov     rcx, [rcx+18h]
0x14000793c  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x140007943  call    WPP_SF_q
0x140007948  mov     edx, 28h ; '('
0x14000794d  mov     r8d, 306D6750h
0x140007953  lea     ecx, [rdx+18h]
0x140007956  call    cs:__imp_ExAllocatePool2
0x14000795d  nop     dword ptr [rax+rax+00h]
0x140007962  mov     rbx, rax
0x140007965  test    rax, rax
0x140007968  jz      short loc_1400079A6
0x14000796a  lea     rcx, [rax+18h]; SpinLock
0x14000796e  mov     [rax+8], rax
0x140007972  mov     [rax], rax
0x140007975  call    cs:__imp_KeInitializeSpinLock
0x14000797c  nop     dword ptr [rax+rax+00h]
0x140007981  inc     dword ptr [rbx+14h]
0x140007984  mov     dword ptr [rbx+10h], 544E4F43h
0x14000798b  mov     rcx, [rdi+30h]
0x14000798f  mov     [rcx+18h], rbx
0x140007993  xor     ebx, ebx
0x140007995  mov     rax, [rdi+30h]
0x140007999  mov     qword ptr [rax+20h], 3
0x1400079a1  jmp     loc_140007A8D
0x1400079a6  mov     ebx, 0C000009Ah
0x1400079ab  jmp     loc_140007A8D
0x1400079b0  lea     rdx, aConnectioncont; "ConnectionContext"
0x1400079b7  mov     rcx, rbx
0x1400079ba  call    FindEA
0x1400079bf  test    rax, rax
0x1400079c2  jz      short loc_1400079F8
0x1400079c4  mov     r9, rax
0x1400079c7  mov     r8, rdi
0x1400079ca  call    PgmCreateConnection
0x1400079cf  mov     ebx, eax
0x1400079d1  mov     r10, cs:WPP_GLOBAL_Control
0x1400079d8  lea     rax, WPP_GLOBAL_Control
0x1400079df  cmp     r10, rax
0x1400079e2  jz      short loc_140007A4F
0x1400079e4  mov     ecx, [r10+2Ch]
0x1400079e8  test    cl, 10h
0x1400079eb  jz      short loc_140007A4F
0x1400079ed  mov     rcx, [r10+18h]
0x1400079f1  mov     edx, 12h
0x1400079f6  jmp     short loc_140007A3C
0x1400079f8  lea     rdx, aTransportaddre; "TransportAddress"
0x1400079ff  mov     rcx, rbx
0x140007a02  call    FindEA
0x140007a07  test    rax, rax
0x140007a0a  jz      short loc_140007A59
0x140007a0c  mov     r9, rax
0x140007a0f  mov     r8, rdi
0x140007a12  call    PgmCreateAddress
0x140007a17  mov     ebx, eax
0x140007a19  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a20  lea     rax, WPP_GLOBAL_Control
0x140007a27  cmp     rcx, rax
0x140007a2a  jz      short loc_140007A4F
0x140007a2c  mov     eax, [rcx+2Ch]
0x140007a2f  test    al, 10h
0x140007a31  jz      short loc_140007A4F
0x140007a33  mov     rcx, [rcx+18h]
0x140007a37  mov     edx, 13h
0x140007a3c  mov     r9, rsi
0x140007a3f  mov     [rsp+58h+var_38], ebx
0x140007a43  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x140007a4a  call    WPP_SF_qD
0x140007a4f  cmp     ebx, 103h
0x140007a55  jz      short loc_140007A9B
0x140007a57  jmp     short loc_140007A8D
0x140007a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a60  lea     rax, WPP_GLOBAL_Control
0x140007a67  cmp     rcx, rax
0x140007a6a  jz      short loc_140007A88
0x140007a6c  mov     eax, [rcx+2Ch]
0x140007a6f  test    al, 2
0x140007a71  jz      short loc_140007A88
0x140007a73  mov     rcx, [rcx+18h]
0x140007a77  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x140007a7e  mov     edx, 14h
0x140007a83  call    WPP_SF_
0x140007a88  mov     ebx, 80000013h
0x140007a8d  mov     edx, ebx
0x140007a8f  mov     [rdi+3], bpl
0x140007a93  mov     rcx, rsi; Irp
0x140007a96  call    CompleteDispatchIrp
0x140007a9b  mov     eax, ebx
0x140007a9d  add     rsp, 38h
0x140007aa1  pop     rdi
0x140007aa2  pop     rsi
0x140007aa3  pop     rbp
0x140007aa4  pop     rbx
0x140007aa5  retn
```
