# Smb2ExecuteFSIoctl

- ea: `0x140082ae0`
- end: `0x140082f58`
- name: `Smb2ExecuteFSIoctl`
- size: `1144`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140082290`
- `0x1400828f0`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x1400125d0`
- `0x140015000`
- `0x1400152a0`
- `0x1400186f0`
- `0x1400222ec`
- `0x140022958`
- `0x140082ae0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140082d63`
- `ntoskrnl!KeDelayExecutionThread` at `0x140082d63`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082b6f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082b6f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140082afc`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140082afc`
- `ntoskrnl!IofCallDriver` at `0x140082d1b`
- `ntoskrnl!IofCallDriver` at `0x140082d1b`
- `ntoskrnl!IoFreeIrp` at `0x140082e25`
- `ntoskrnl!IoFreeIrp` at `0x140082e25`
- `ntoskrnl!IoAllocateIrpEx` at `0x140082e09`
- `ntoskrnl!IoAllocateIrpEx` at `0x140082e09`
- `ntoskrnl!IoReuseIrp` at `0x140082b2d`
- `ntoskrnl!IoReuseIrp` at `0x140082b2d`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140082f47`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140082f47`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteFSIoctl(__int64 a1, struct _FILE_OBJECT *a2)
{
  __int64 v2; // rsi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  IRP *v6; // rcx
  struct _DEVICE_OBJECT *v7; // r15
  char StackSize; // r9
  bool v9; // bp
  char v10; // r13
  int v11; // r14d
  int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  char v18; // dl
  __int64 v19; // rdx
  int v21; // r14d
  int v22; // r14d
  __int64 v23; // rdx
  __int64 Irp; // rdi
  __int64 v25; // r9
  __int64 v26; // rdx
  SECURITY_STATUS v27; // edi
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  RelatedDeviceObject = IoGetRelatedDeviceObject(a2);
  v6 = *(IRP **)(a1 + 120);
  v7 = RelatedDeviceObject;
  StackSize = RelatedDeviceObject->StackSize;
  if ( v6->StackCount < StackSize || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v23 = 15;
    if ( StackSize > 15 )
      v23 = (unsigned __int8)RelatedDeviceObject->StackSize;
    Irp = IoAllocateIrpEx(-1, v23, 0);
    if ( !Irp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          98,
          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
          a1,
          -1073741670);
      }
      Smb2SetError(a1, 3221225626LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c", 2922);
      return 0;
    }
    IoFreeIrp(*(PIRP *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = Irp;
  }
  else
  {
    IoReuseIrp(v6, 0);
  }
  v9 = 0;
  v10 = 0;
  v11 = *(_DWORD *)(v2 + 192);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = a2;
  v12 = v11 & 3;
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v13 + 8LL * KeGetCurrentNodeNumber() + 8) + 224LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  v14 = *(_QWORD *)(a1 + 120);
  v15 = *(_QWORD *)(v14 + 184);
  *(_QWORD *)(a1 + 48) = Smb2ContinueIoctl;
  v16 = *(_QWORD *)(v14 + 184);
  *(_QWORD *)(v16 - 16) = Srv2PostOnCompletionAndClearCancel;
  *(_QWORD *)(v16 - 8) = a1;
  *(_BYTE *)(v16 - 69) = -32;
  *(_WORD *)(v15 - 72) = 13;
  *(_QWORD *)(v15 - 24) = a2;
  *(_QWORD *)(v15 - 32) = v7;
  *(_BYTE *)(v15 - 70) = 0;
  v17 = *(_QWORD *)(v2 + 72);
  if ( v17 )
  {
    v18 = *(_DWORD *)(v17 + 184) & 1;
    *(_BYTE *)(v15 - 70) = v18;
    *(_BYTE *)(v15 - 70) = v18 | (2 * (*(_BYTE *)(*(_QWORD *)(v2 + 72) + 184LL) & 2));
  }
  *(_DWORD *)(v15 - 64) = *(_DWORD *)(v2 + 200);
  *(_DWORD *)(v15 - 56) = *(_DWORD *)(v2 + 204);
  *(_DWORD *)(v15 - 48) = *(_DWORD *)(v2 + 192);
  if ( v12 )
  {
    v21 = v12 - 1;
    if ( v21 && (v22 = v21 - 1) != 0 )
    {
      if ( v22 == 1 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = *(_QWORD *)(v2 + 224);
        *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) = 0;
        *(_QWORD *)(v15 - 40) = *(_QWORD *)(v2 + 216);
      }
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = *(_QWORD *)(v2 + 232);
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = *(_QWORD *)(v2 + 216);
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) = 16;
    }
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
    if ( *(_DWORD *)(v2 + 204) || *(_DWORD *)(v2 + 200) )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = *(_QWORD *)(v2 + 216);
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL);
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) = 16;
      if ( *(_DWORD *)(v2 + 204) )
        *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) |= 0x40u;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 16LL) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
    }
  }
  if ( *(_DWORD *)(v15 - 48) == 589967 || *(_DWORD *)(v15 - 48) == 589988 )
  {
    v10 = 1;
  }
  else if ( *(_DWORD *)(v15 - 48) == 1163287 )
  {
    *(_DWORD *)(v15 - 48) = 1171455;
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = *(_QWORD *)(v2 + 224);
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  }
  if ( *(_QWORD *)(v2 + 168) != -1 )
    v9 = *(_BYTE *)(v2 + 2) == 0;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v9) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids, a1);
    }
    v25 = 3071;
    v26 = 3221225760LL;
    goto LABEL_36;
  }
  if ( v9 )
    Srv2ReferenceConnection(a1);
  if ( v10 )
  {
    v27 = Smb2ImpersonateWorkItem(v2);
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids, a1);
      }
      v25 = 3092;
      v26 = (unsigned int)v27;
LABEL_36:
      Smb2SetError(a1, v26, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c", v25);
      return 0;
    }
  }
  LOBYTE(v19) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v19, 3097, "Smb2ExecuteFSIoctl", 1);
  IofCallDriver(v7, *(PIRP *)(a1 + 120));
  if ( v10 )
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
  if ( v9 )
  {
    Interval.QuadPart = -10000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
      Srv2DereferenceWorkItem(a1);
    else
      Smb2GoAsync2(a1);
  }
  return 259;
}

```

## disassembly

```asm
0x140082ae0  push    rbx
0x140082ae2  push    rsi
0x140082ae3  push    rdi
0x140082ae4  push    r12
0x140082ae6  push    r15
0x140082ae8  sub     rsp, 30h
0x140082aec  mov     rsi, [rcx+230h]
0x140082af3  mov     rbx, rcx
0x140082af6  mov     rcx, rdx; FileObject
0x140082af9  mov     r12, rdx
0x140082afc  call    cs:__imp_IoGetRelatedDeviceObject
0x140082b03  nop     dword ptr [rax+rax+00h]
0x140082b08  mov     rcx, [rbx+78h]; Irp
0x140082b0c  mov     r15, rax
0x140082b0f  movzx   r9d, byte ptr [rax+4Ch]
0x140082b14  cmp     [rcx+42h], r9b
0x140082b18  jl      loc_140082DF3
0x140082b1e  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140082b25  jnz     loc_140082DF3
0x140082b2b  xor     edx, edx; Iostatus
0x140082b2d  call    cs:__imp_IoReuseIrp
0x140082b34  nop     dword ptr [rax+rax+00h]
0x140082b39  mov     rax, [rbx+78h]
0x140082b3d  mov     [rsp+58h+arg_8], rbp
0x140082b42  xor     bpl, bpl
0x140082b45  mov     [rsp+58h+arg_10], r13
0x140082b4a  xor     r13b, r13b
0x140082b4d  mov     [rsp+58h+arg_18], r14
0x140082b52  mov     r14d, [rsi+0C0h]
0x140082b59  mov     [rax+0C0h], r12
0x140082b60  and     r14d, 3
0x140082b64  mov     rax, [rbx+40h]
0x140082b68  mov     rdi, [rax+88h]
0x140082b6f  call    cs:__imp_KeGetCurrentNodeNumber
0x140082b76  nop     dword ptr [rax+rax+00h]
0x140082b7b  movzx   eax, ax
0x140082b7e  xor     r9d, r9d
0x140082b81  mov     rcx, [rdi+rax*8+8]
0x140082b86  mov     rax, [rbx+78h]
0x140082b8a  mov     rdx, [rcx+0E0h]
0x140082b91  lea     rcx, Smb2ContinueIoctl
0x140082b98  mov     [rax+98h], rdx
0x140082b9f  mov     rax, [rbx+78h]
0x140082ba3  mov     [rax+40h], bpl
0x140082ba7  mov     rax, [rbx+78h]
0x140082bab  mov     [rax+30h], r9d
0x140082baf  mov     rax, [rbx+78h]
0x140082bb3  mov     [rax+38h], r9
0x140082bb7  mov     rax, [rbx+78h]
0x140082bbb  mov     r8, [rax+0B8h]
0x140082bc2  mov     [rbx+30h], rcx
0x140082bc6  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x140082bcd  mov     rax, [rax+0B8h]
0x140082bd4  mov     [rax-10h], rcx
0x140082bd8  mov     [rax-8], rbx
0x140082bdc  mov     byte ptr [rax-45h], 0E0h
0x140082be0  mov     word ptr [r8-48h], 0Dh
0x140082be7  mov     [r8-18h], r12
0x140082beb  mov     [r8-20h], r15
0x140082bef  mov     [r8-46h], bpl
0x140082bf3  mov     rdx, [rsi+48h]
0x140082bf7  test    rdx, rdx
0x140082bfa  jz      short loc_140082C1F
0x140082bfc  mov     edx, [rdx+0B8h]
0x140082c02  and     dl, 1
0x140082c05  mov     [r8-46h], dl
0x140082c09  mov     rax, [rsi+48h]
0x140082c0d  movzx   ecx, byte ptr [rax+0B8h]
0x140082c14  and     cl, 2
0x140082c17  add     cl, cl
0x140082c19  or      cl, dl
0x140082c1b  mov     [r8-46h], cl
0x140082c1f  mov     eax, [rsi+0C8h]
0x140082c25  mov     [r8-40h], eax
0x140082c29  mov     eax, [rsi+0CCh]
0x140082c2f  mov     [r8-38h], eax
0x140082c33  mov     eax, [rsi+0C0h]
0x140082c39  mov     [r8-30h], eax
0x140082c3d  test    r14d, r14d
0x140082c40  jnz     loc_140082D9E
0x140082c46  mov     rax, [rbx+78h]
0x140082c4a  mov     [rax+8], r9
0x140082c4e  cmp     [rsi+0CCh], r9d
0x140082c55  jz      loc_140082E72
0x140082c5b  mov     rcx, [rbx+78h]
0x140082c5f  mov     rax, [rsi+0D8h]
0x140082c66  mov     [rcx+18h], rax
0x140082c6a  mov     rcx, [rbx+78h]
0x140082c6e  mov     rax, [rcx+18h]
0x140082c72  mov     [rcx+70h], rax
0x140082c76  mov     rax, [rbx+78h]
0x140082c7a  mov     dword ptr [rax+10h], 10h
0x140082c81  cmp     [rsi+0CCh], r9d
0x140082c88  jbe     short loc_140082C92
0x140082c8a  mov     rax, [rbx+78h]
0x140082c8e  or      dword ptr [rax+10h], 40h
0x140082c92  mov     ecx, [r8-30h]
0x140082c96  mov     r14, [rsp+58h+arg_18]
0x140082c9b  sub     ecx, 9008Fh
0x140082ca1  jz      loc_140082F00
0x140082ca7  sub     ecx, 15h
0x140082caa  jz      loc_140082F00
0x140082cb0  cmp     ecx, 8BF73h
0x140082cb6  jz      loc_140082EA6
0x140082cbc  cmp     qword ptr [rsi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140082cc4  jnz     loc_140082D89
0x140082cca  movzx   edx, bpl
0x140082cce  mov     rcx, rbx
0x140082cd1  call    Srv2MarkWorkItemCancellable
0x140082cd6  test    eax, eax
0x140082cd8  js      loc_140082E3A
0x140082cde  test    bpl, bpl
0x140082ce1  jz      short loc_140082CEB
0x140082ce3  mov     rcx, rbx
0x140082ce6  call    Srv2ReferenceConnection
0x140082ceb  test    r13b, r13b
0x140082cee  jnz     loc_14009923C
0x140082cf4  lea     rcx, [rbx+248h]
0x140082cfb  mov     byte ptr [rsp+58h+var_38], 1
0x140082d00  lea     r9, aSmb2executefsi; "Smb2ExecuteFSIoctl"
0x140082d07  mov     r8d, 0C19h
0x140082d0d  mov     dl, 3
0x140082d0f  call    SRV2_PERF_ENTER_EX
0x140082d14  mov     rdx, [rbx+78h]; Irp
0x140082d18  mov     rcx, r15; DeviceObject
0x140082d1b  call    cs:__imp_IofCallDriver
0x140082d22  nop     dword ptr [rax+rax+00h]
0x140082d27  test    r13b, r13b
0x140082d2a  jnz     loc_140082F3C
0x140082d30  test    bpl, bpl
0x140082d33  jnz     short loc_140082D51
0x140082d35  mov     eax, 103h
0x140082d3a  mov     rbp, [rsp+58h+arg_8]
0x140082d3f  mov     r13, [rsp+58h+arg_10]
0x140082d44  add     rsp, 30h
0x140082d48  pop     r15
0x140082d4a  pop     r12
0x140082d4c  pop     rdi
0x140082d4d  pop     rsi
0x140082d4e  pop     rbx
0x140082d4f  retn
0x140082d51  lea     r8, [rsp+58h+Interval]; Interval
0x140082d56  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x140082d5f  xor     edx, edx; Alertable
0x140082d61  xor     ecx, ecx; WaitMode
0x140082d63  call    cs:__imp_KeDelayExecutionThread
0x140082d6a  nop     dword ptr [rax+rax+00h]
0x140082d6f  mov     rcx, rbx
0x140082d72  call    Srv2MarkWorkItemPending
0x140082d77  mov     rcx, rbx
0x140082d7a  test    eax, eax
0x140082d7c  jz      loc_140082E9C
0x140082d82  call    Srv2DereferenceWorkItem
0x140082d87  jmp     short loc_140082D35
0x140082d89  cmp     [rsi+2], r9b
0x140082d8d  mov     eax, 1
0x140082d92  movzx   ebp, bpl
0x140082d96  cmovz   ebp, eax
0x140082d99  jmp     loc_140082CCA
0x140082d9e  sub     r14d, 1
0x140082da2  jz      loc_140082ECA
0x140082da8  sub     r14d, 1
0x140082dac  jz      loc_140082ECA
0x140082db2  cmp     r14d, 1
0x140082db6  jnz     loc_140082C92
0x140082dbc  mov     rax, [rbx+78h]
0x140082dc0  mov     [rax+8], r9
0x140082dc4  mov     rax, [rbx+78h]
0x140082dc8  mov     [rax+18h], r9
0x140082dcc  mov     rax, [rsi+0E0h]
0x140082dd3  mov     rcx, [rbx+78h]
0x140082dd7  mov     [rcx+70h], rax
0x140082ddb  mov     rax, [rbx+78h]
0x140082ddf  mov     [rax+10h], r9d
0x140082de3  mov     rax, [rsi+0D8h]
0x140082dea  mov     [r8-28h], rax
0x140082dee  jmp     loc_140082C92
0x140082df3  mov     edx, 0Fh
0x140082df8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140082dff  cmp     r9b, dl
0x140082e02  cmovg   edx, r9d
0x140082e06  xor     r8d, r8d
0x140082e09  call    cs:__imp_IoAllocateIrpEx
0x140082e10  nop     dword ptr [rax+rax+00h]
0x140082e15  mov     rdi, rax
0x140082e18  test    rax, rax
0x140082e1b  jz      loc_14009929C
0x140082e21  mov     rcx, [rbx+78h]; Irp
0x140082e25  call    cs:__imp_IoFreeIrp
0x140082e2c  nop     dword ptr [rax+rax+00h]
0x140082e31  mov     [rbx+78h], rdi
0x140082e35  jmp     loc_140082B39
0x140082e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e41  lea     rax, WPP_GLOBAL_Control
0x140082e48  cmp     rcx, rax
0x140082e4b  jnz     loc_140082F08
0x140082e51  mov     r9d, 0BFFh
0x140082e57  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140082e5e  mov     edx, 0C0000120h
0x140082e63  mov     rcx, rbx
0x140082e66  call    _Smb2SetError
0x140082e6b  xor     eax, eax
0x140082e6d  jmp     loc_140082D3A
0x140082e72  cmp     [rsi+0C8h], r9d
0x140082e79  jnz     loc_140082C5B
0x140082e7f  mov     rax, [rbx+78h]
0x140082e83  mov     [rax+10h], r9d
0x140082e87  mov     rax, [rbx+78h]
0x140082e8b  mov     [rax+18h], r9
0x140082e8f  mov     rax, [rbx+78h]
0x140082e93  mov     [rax+70h], r9
0x140082e97  jmp     loc_140082C92
0x140082e9c  call    Smb2GoAsync2
0x140082ea1  jmp     loc_140082D35
0x140082ea6  mov     dword ptr [r8-30h], 11DFFFh
0x140082eae  mov     rax, [rsi+0E0h]
0x140082eb5  mov     rcx, [rbx+78h]
0x140082eb9  mov     [rcx+18h], rax
0x140082ebd  mov     rax, [rbx+78h]
0x140082ec1  mov     [rax+70h], r9
0x140082ec5  jmp     loc_140082CBC
0x140082eca  mov     rcx, [rbx+78h]
0x140082ece  mov     rax, [rsi+0E8h]
0x140082ed5  mov     [rcx+8], rax
0x140082ed9  mov     rax, [rsi+0D8h]
0x140082ee0  mov     rcx, [rbx+78h]
0x140082ee4  mov     [rcx+18h], rax
0x140082ee8  mov     rax, [rbx+78h]
0x140082eec  mov     [rax+70h], r9
0x140082ef0  mov     rax, [rbx+78h]
0x140082ef4  mov     dword ptr [rax+10h], 10h
0x140082efb  jmp     loc_140082C92
0x140082f00  mov     r13b, 1
0x140082f03  jmp     loc_140082CBC
0x140082f08  test    dword ptr [rcx+2Ch], 20000000h
0x140082f0f  jz      loc_140082E51
0x140082f15  cmp     byte ptr [rcx+29h], 1
0x140082f19  jb      loc_140082E51
0x140082f1f  mov     rcx, [rcx+18h]
0x140082f23  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x140082f2a  mov     edx, 63h ; 'c'
0x140082f2f  mov     r9, rbx
0x140082f32  call    WPP_SF_q
0x140082f37  jmp     loc_140082E51
0x140082f3c  mov     rcx, gs:188h; Thread
0x140082f45  xor     edx, edx; Token
0x140082f47  call    cs:__imp_PsAssignImpersonationToken
0x140082f4e  nop     dword ptr [rax+rax+00h]
0x140082f53  jmp     loc_140082D30
0x14009923c  mov     rcx, rsi
0x14009923f  call    Smb2ImpersonateWorkItem
0x140099244  mov     edi, eax
0x140099246  test    eax, eax
0x140099248  jns     loc_140082CF4
0x14009924e  mov     rcx, cs:WPP_GLOBAL_Control
0x140099255  lea     rax, WPP_GLOBAL_Control
0x14009925c  cmp     rcx, rax
0x14009925f  jz      short loc_140099288
0x140099261  test    dword ptr [rcx+2Ch], 20000000h
0x140099268  jz      short loc_140099288
0x14009926a  cmp     byte ptr [rcx+29h], 1
0x14009926e  jb      short loc_140099288
0x140099270  mov     rcx, [rcx+18h]
0x140099274  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x14009927b  mov     edx, 64h ; 'd'
0x140099280  mov     r9, rbx
0x140099283  call    WPP_SF_q
0x140099288  mov     r9d, 0C14h
0x14009928e  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140099295  mov     edx, edi
0x140099297  jmp     loc_140082E63
0x14009929c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400992a3  lea     rax, WPP_GLOBAL_Control
0x1400992aa  cmp     rcx, rax
0x1400992ad  jz      short loc_1400992DE
0x1400992af  test    dword ptr [rcx+2Ch], 20000000h
0x1400992b6  jz      short loc_1400992DE
0x1400992b8  cmp     byte ptr [rcx+29h], 1
0x1400992bc  jb      short loc_1400992DE
0x1400992be  mov     rcx, [rcx+18h]
0x1400992c2  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x1400992c9  mov     edx, 62h ; 'b'
0x1400992ce  mov     [rsp+58h+var_38], 0C000009Ah
0x1400992d6  mov     r9, rbx
0x1400992d9  call    WPP_SF_qD
0x1400992de  mov     r9d, 0B6Ah
0x1400992e4  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400992eb  mov     edx, 0C000009Ah
0x1400992f0  mov     rcx, rbx
0x1400992f3  call    _Smb2SetError
0x1400992f8  xor     eax, eax
0x1400992fa  jmp     loc_140082D44
```
