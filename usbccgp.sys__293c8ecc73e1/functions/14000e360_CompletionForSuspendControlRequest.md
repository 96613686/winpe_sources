# CompletionForSuspendControlRequest

- ea: `0x14000e360`
- end: `0x14000e57d`
- name: `CompletionForSuspendControlRequest`
- size: `541`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x140006430`
- `0x140007b3c`
- `0x140008eac`
- `0x14000b4bc`
- `0x14000e360`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000e481`
- `ntoskrnl!IofCompleteRequest` at `0x14000e481`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000e469`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000e469`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e406`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e4a4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e406`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e4a4`
- `ntoskrnl!KeSetEvent` at `0x14000e45a`
- `ntoskrnl!KeSetEvent` at `0x14000e45a`
- `ntoskrnl!IoReuseIrp` at `0x14000e3d4`
- `ntoskrnl!IoReuseIrp` at `0x14000e3d4`
- `ntoskrnl!IoCancelIrp` at `0x14000e557`
- `ntoskrnl!IoCancelIrp` at `0x14000e557`

## pseudocode

```c
__int64 __fastcall CompletionForSuspendControlRequest(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  IRP *v6; // r12
  _QWORD *v7; // rbx
  _QWORD *v8; // r14
  IRP *v9; // rbp
  _IO_STACK_LOCATION *CurrentStackLocation; // r13
  char v11; // r14
  bool v12; // bl
  int Status; // [rsp+30h] [rbp-58h]

  v3 = *(_QWORD *)(a3 + 384);
  v5 = *(_QWORD *)(a3 + 232);
  v6 = a2;
  *(_BYTE *)(v3 + 58) = 0;
  *(_DWORD *)(v3 + 88) = a2->IoStatus.Status;
  v7 = (_QWORD *)(a3 + 224);
  v8 = (_QWORD *)(a3 + 392);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    Status = a2->IoStatus.Status;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qD(*v8, (_DWORD)a2, 3, 83, (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids, *v7, Status);
  }
  v9 = *(IRP **)(v3 + 96);
  CurrentStackLocation = v9->Tail.Overlay.CurrentStackLocation;
  if ( v6->IoStatus.Status < 0 && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qq(
        *v8,
        (_DWORD)a2,
        3,
        84,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *v7,
        *(_QWORD *)(v3 + 40));
    }
    IoCancelIrp(*(PIRP *)(v3 + 40));
  }
  IoReuseIrp(v6, 0);
  UsbcReleaseRemoveLock(v5, SendSetFeatureControlRequestForFunctionSuspend);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 200), SendSetFeatureControlRequestForFunctionSuspend, 0x20u);
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
  {
    v11 = 0;
    v12 = 0;
  }
  else
  {
    v11 = SetPdoIdle(v5, a3, 2, 1u, 1);
    v12 = CurrentStackLocation->Parameters.Create.EaLength - 2 <= 4;
  }
  *(_QWORD *)(v3 + 96) = 0;
  KeSetEvent((PRKEVENT)(a3 + 432), 0, 0);
  PoStartNextPowerIrp(v9);
  v9->IoStatus.Status = 0;
  IofCompleteRequest(v9, 0);
  UsbcReleaseRemoveLock(v5, v9);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 200), v9, 0x20u);
  if ( v11 && !v12 )
    ResumeIdleTimer(v5);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000e360  push    rbx
0x14000e362  push    rbp
0x14000e363  push    rsi
0x14000e364  push    rdi
0x14000e365  push    r12
0x14000e367  push    r13
0x14000e369  push    r14
0x14000e36b  push    r15
0x14000e36d  sub     rsp, 48h
0x14000e371  mov     rdi, [r8+180h]
0x14000e378  mov     r15, r8
0x14000e37b  mov     rsi, [r8+0E8h]
0x14000e382  mov     r12, rdx
0x14000e385  mov     byte ptr [rdi+3Ah], 0
0x14000e389  mov     eax, [rdx+30h]
0x14000e38c  mov     [rdi+58h], eax
0x14000e38f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e396  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000e39d  lea     rbx, [r8+0E0h]
0x14000e3a4  lea     r14, [r8+188h]
0x14000e3ab  lea     rcx, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000e3b2  jnz     loc_14000E4DA
0x14000e3b8  cmp     dword ptr [r12+30h], 0
0x14000e3be  mov     rbp, [rdi+60h]
0x14000e3c2  mov     r13, [rbp+0B8h]
0x14000e3c9  jl      loc_14000E515
0x14000e3cf  xor     edx, edx; Iostatus
0x14000e3d1  mov     rcx, r12; Irp
0x14000e3d4  call    cs:__imp_IoReuseIrp
0x14000e3db  nop     dword ptr [rax+rax+00h]
0x14000e3e0  lea     rdx, SendSetFeatureControlRequestForFunctionSuspend
0x14000e3e7  mov     rcx, rsi
0x14000e3ea  call    UsbcReleaseRemoveLock
0x14000e3ef  lea     r12, [rsi+0C8h]
0x14000e3f6  mov     r8d, 20h ; ' '; RemlockSize
0x14000e3fc  mov     rcx, r12; RemoveLock
0x14000e3ff  lea     rdx, SendSetFeatureControlRequestForFunctionSuspend; Tag
0x14000e406  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e40d  nop     dword ptr [rax+rax+00h]
0x14000e412  cmp     dword ptr [r13+18h], 1
0x14000e417  jz      loc_14000E4D0
0x14000e41d  mov     r9b, 1
0x14000e420  mov     byte ptr [rsp+88h+var_68], 1
0x14000e425  mov     r8d, 2
0x14000e42b  mov     rdx, r15
0x14000e42e  mov     rcx, rsi
0x14000e431  call    SetPdoIdle
0x14000e436  mov     ecx, [r13+20h]
0x14000e43a  mov     r14b, al
0x14000e43d  sub     ecx, 2
0x14000e440  cmp     ecx, 4
0x14000e443  setbe   bl
0x14000e446  lea     rcx, [r15+1B0h]; Event
0x14000e44d  mov     qword ptr [rdi+60h], 0
0x14000e455  xor     r8d, r8d; Wait
0x14000e458  xor     edx, edx; Increment
0x14000e45a  call    cs:__imp_KeSetEvent
0x14000e461  nop     dword ptr [rax+rax+00h]
0x14000e466  mov     rcx, rbp; Irp
0x14000e469  call    cs:__imp_PoStartNextPowerIrp
0x14000e470  nop     dword ptr [rax+rax+00h]
0x14000e475  xor     edx, edx; PriorityBoost
0x14000e477  mov     dword ptr [rbp+30h], 0
0x14000e47e  mov     rcx, rbp; Irp
0x14000e481  call    cs:__imp_IofCompleteRequest
0x14000e488  nop     dword ptr [rax+rax+00h]
0x14000e48d  mov     rdx, rbp
0x14000e490  mov     rcx, rsi
0x14000e493  call    UsbcReleaseRemoveLock
0x14000e498  mov     r8d, 20h ; ' '; RemlockSize
0x14000e49e  mov     rdx, rbp; Tag
0x14000e4a1  mov     rcx, r12; RemoveLock
0x14000e4a4  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e4ab  nop     dword ptr [rax+rax+00h]
0x14000e4b0  test    r14b, r14b
0x14000e4b3  jnz     loc_14000E568
0x14000e4b9  mov     eax, 0C0000016h
0x14000e4be  add     rsp, 48h
0x14000e4c2  pop     r15
0x14000e4c4  pop     r14
0x14000e4c6  pop     r13
0x14000e4c8  pop     r12
0x14000e4ca  pop     rdi
0x14000e4cb  pop     rsi
0x14000e4cc  pop     rbp
0x14000e4cd  pop     rbx
0x14000e4ce  retn
0x14000e4d0  xor     r14b, r14b
0x14000e4d3  xor     bl, bl
0x14000e4d5  jmp     loc_14000E446
0x14000e4da  mov     eax, [rdx+30h]
0x14000e4dd  mov     r9d, 53h ; 'S'
0x14000e4e3  mov     [rsp+88h+var_58], eax
0x14000e4e7  mov     dl, 4
0x14000e4e9  mov     rax, [rbx]
0x14000e4ec  mov     [rsp+88h+var_60], rax
0x14000e4f1  mov     [rsp+88h+var_68], rcx
0x14000e4f6  lea     r8d, [r9-50h]
0x14000e4fa  mov     rcx, [r14]
0x14000e4fd  call    WPP_RECORDER_SF_qD
0x14000e502  lea     rax, WPP_RECORDER_INITIALIZED
0x14000e509  lea     rcx, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000e510  jmp     loc_14000E3B8
0x14000e515  cmp     dword ptr [r13+18h], 1
0x14000e51a  jz      loc_14000E3CF
0x14000e520  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14000e527  jz      short loc_14000E553
0x14000e529  mov     rax, [rdi+28h]
0x14000e52d  mov     r9d, 54h ; 'T'
0x14000e533  mov     qword ptr [rsp+88h+var_58], rax
0x14000e538  mov     dl, 2
0x14000e53a  mov     rax, [rbx]
0x14000e53d  mov     [rsp+88h+var_60], rax
0x14000e542  mov     [rsp+88h+var_68], rcx
0x14000e547  lea     r8d, [r9-51h]
0x14000e54b  mov     rcx, [r14]
0x14000e54e  call    WPP_RECORDER_SF_qq
0x14000e553  mov     rcx, [rdi+28h]; Irp
0x14000e557  call    cs:__imp_IoCancelIrp
0x14000e55e  nop     dword ptr [rax+rax+00h]
0x14000e563  jmp     loc_14000E3CF
0x14000e568  test    bl, bl
0x14000e56a  jnz     loc_14000E4B9
0x14000e570  mov     rcx, rsi
0x14000e573  call    ResumeIdleTimer
0x14000e578  jmp     loc_14000E4B9
```
