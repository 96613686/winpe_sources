# Smb2ExecuteFSIoctl

- ea: `0x140082b30`
- end: `0x140082fa8`
- name: `Smb2ExecuteFSIoctl`
- size: `1144`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400822e0`
- `0x140082940`

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
- `0x140082b30`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140082db3`
- `ntoskrnl!KeDelayExecutionThread` at `0x140082db3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082bbf`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082bbf`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140082b4c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140082b4c`
- `ntoskrnl!IofCallDriver` at `0x140082d6b`
- `ntoskrnl!IofCallDriver` at `0x140082d6b`
- `ntoskrnl!IoFreeIrp` at `0x140082e75`
- `ntoskrnl!IoFreeIrp` at `0x140082e75`
- `ntoskrnl!IoAllocateIrpEx` at `0x140082e59`
- `ntoskrnl!IoAllocateIrpEx` at `0x140082e59`
- `ntoskrnl!IoReuseIrp` at `0x140082b7d`
- `ntoskrnl!IoReuseIrp` at `0x140082b7d`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140082f97`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140082f97`

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
          &WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
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
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 99, &WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids, a1);
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
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, &WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids, a1);
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
0x140082b30  push    rbx
0x140082b32  push    rsi
0x140082b33  push    rdi
0x140082b34  push    r12
0x140082b36  push    r15
0x140082b38  sub     rsp, 30h
0x140082b3c  mov     rsi, [rcx+230h]
0x140082b43  mov     rbx, rcx
0x140082b46  mov     rcx, rdx; FileObject
0x140082b49  mov     r12, rdx
0x140082b4c  call    cs:__imp_IoGetRelatedDeviceObject
0x140082b53  nop     dword ptr [rax+rax+00h]
0x140082b58  mov     rcx, [rbx+78h]; Irp
0x140082b5c  mov     r15, rax
0x140082b5f  movzx   r9d, byte ptr [rax+4Ch]
0x140082b64  cmp     [rcx+42h], r9b
0x140082b68  jl      loc_140082E43
0x140082b6e  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140082b75  jnz     loc_140082E43
0x140082b7b  xor     edx, edx; Iostatus
0x140082b7d  call    cs:__imp_IoReuseIrp
0x140082b84  nop     dword ptr [rax+rax+00h]
0x140082b89  mov     rax, [rbx+78h]
0x140082b8d  mov     [rsp+58h+arg_8], rbp
0x140082b92  xor     bpl, bpl
0x140082b95  mov     [rsp+58h+arg_10], r13
0x140082b9a  xor     r13b, r13b
0x140082b9d  mov     [rsp+58h+arg_18], r14
0x140082ba2  mov     r14d, [rsi+0C0h]
0x140082ba9  mov     [rax+0C0h], r12
0x140082bb0  and     r14d, 3
0x140082bb4  mov     rax, [rbx+40h]
0x140082bb8  mov     rdi, [rax+88h]
0x140082bbf  call    cs:__imp_KeGetCurrentNodeNumber
0x140082bc6  nop     dword ptr [rax+rax+00h]
0x140082bcb  movzx   eax, ax
0x140082bce  xor     r9d, r9d
0x140082bd1  mov     rcx, [rdi+rax*8+8]
0x140082bd6  mov     rax, [rbx+78h]
0x140082bda  mov     rdx, [rcx+0E0h]
0x140082be1  lea     rcx, Smb2ContinueIoctl
0x140082be8  mov     [rax+98h], rdx
0x140082bef  mov     rax, [rbx+78h]
0x140082bf3  mov     [rax+40h], bpl
0x140082bf7  mov     rax, [rbx+78h]
0x140082bfb  mov     [rax+30h], r9d
0x140082bff  mov     rax, [rbx+78h]
0x140082c03  mov     [rax+38h], r9
0x140082c07  mov     rax, [rbx+78h]
0x140082c0b  mov     r8, [rax+0B8h]
0x140082c12  mov     [rbx+30h], rcx
0x140082c16  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x140082c1d  mov     rax, [rax+0B8h]
0x140082c24  mov     [rax-10h], rcx
0x140082c28  mov     [rax-8], rbx
0x140082c2c  mov     byte ptr [rax-45h], 0E0h
0x140082c30  mov     word ptr [r8-48h], 0Dh
0x140082c37  mov     [r8-18h], r12
0x140082c3b  mov     [r8-20h], r15
0x140082c3f  mov     [r8-46h], bpl
0x140082c43  mov     rdx, [rsi+48h]
0x140082c47  test    rdx, rdx
0x140082c4a  jz      short loc_140082C6F
0x140082c4c  mov     edx, [rdx+0B8h]
0x140082c52  and     dl, 1
0x140082c55  mov     [r8-46h], dl
0x140082c59  mov     rax, [rsi+48h]
0x140082c5d  movzx   ecx, byte ptr [rax+0B8h]
0x140082c64  and     cl, 2
0x140082c67  add     cl, cl
0x140082c69  or      cl, dl
0x140082c6b  mov     [r8-46h], cl
0x140082c6f  mov     eax, [rsi+0C8h]
0x140082c75  mov     [r8-40h], eax
0x140082c79  mov     eax, [rsi+0CCh]
0x140082c7f  mov     [r8-38h], eax
0x140082c83  mov     eax, [rsi+0C0h]
0x140082c89  mov     [r8-30h], eax
0x140082c8d  test    r14d, r14d
0x140082c90  jnz     loc_140082DEE
0x140082c96  mov     rax, [rbx+78h]
0x140082c9a  mov     [rax+8], r9
0x140082c9e  cmp     [rsi+0CCh], r9d
0x140082ca5  jz      loc_140082EC2
0x140082cab  mov     rcx, [rbx+78h]
0x140082caf  mov     rax, [rsi+0D8h]
0x140082cb6  mov     [rcx+18h], rax
0x140082cba  mov     rcx, [rbx+78h]
0x140082cbe  mov     rax, [rcx+18h]
0x140082cc2  mov     [rcx+70h], rax
0x140082cc6  mov     rax, [rbx+78h]
0x140082cca  mov     dword ptr [rax+10h], 10h
0x140082cd1  cmp     [rsi+0CCh], r9d
0x140082cd8  jbe     short loc_140082CE2
0x140082cda  mov     rax, [rbx+78h]
0x140082cde  or      dword ptr [rax+10h], 40h
0x140082ce2  mov     ecx, [r8-30h]
0x140082ce6  mov     r14, [rsp+58h+arg_18]
0x140082ceb  sub     ecx, 9008Fh
0x140082cf1  jz      loc_140082F50
0x140082cf7  sub     ecx, 15h
0x140082cfa  jz      loc_140082F50
0x140082d00  cmp     ecx, 8BF73h
0x140082d06  jz      loc_140082EF6
0x140082d0c  cmp     qword ptr [rsi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140082d14  jnz     loc_140082DD9
0x140082d1a  movzx   edx, bpl
0x140082d1e  mov     rcx, rbx
0x140082d21  call    Srv2MarkWorkItemCancellable
0x140082d26  test    eax, eax
0x140082d28  js      loc_140082E8A
0x140082d2e  test    bpl, bpl
0x140082d31  jz      short loc_140082D3B
0x140082d33  mov     rcx, rbx
0x140082d36  call    Srv2ReferenceConnection
0x140082d3b  test    r13b, r13b
0x140082d3e  jnz     loc_14009928C
0x140082d44  lea     rcx, [rbx+248h]
0x140082d4b  mov     byte ptr [rsp+58h+var_38], 1
0x140082d50  lea     r9, aSmb2executefsi; "Smb2ExecuteFSIoctl"
0x140082d57  mov     r8d, 0C19h
0x140082d5d  mov     dl, 3
0x140082d5f  call    SRV2_PERF_ENTER_EX
0x140082d64  mov     rdx, [rbx+78h]; Irp
0x140082d68  mov     rcx, r15; DeviceObject
0x140082d6b  call    cs:__imp_IofCallDriver
0x140082d72  nop     dword ptr [rax+rax+00h]
0x140082d77  test    r13b, r13b
0x140082d7a  jnz     loc_140082F8C
0x140082d80  test    bpl, bpl
0x140082d83  jnz     short loc_140082DA1
0x140082d85  mov     eax, 103h
0x140082d8a  mov     rbp, [rsp+58h+arg_8]
0x140082d8f  mov     r13, [rsp+58h+arg_10]
0x140082d94  add     rsp, 30h
0x140082d98  pop     r15
0x140082d9a  pop     r12
0x140082d9c  pop     rdi
0x140082d9d  pop     rsi
0x140082d9e  pop     rbx
0x140082d9f  retn
0x140082da1  lea     r8, [rsp+58h+Interval]; Interval
0x140082da6  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x140082daf  xor     edx, edx; Alertable
0x140082db1  xor     ecx, ecx; WaitMode
0x140082db3  call    cs:__imp_KeDelayExecutionThread
0x140082dba  nop     dword ptr [rax+rax+00h]
0x140082dbf  mov     rcx, rbx
0x140082dc2  call    Srv2MarkWorkItemPending
0x140082dc7  mov     rcx, rbx
0x140082dca  test    eax, eax
0x140082dcc  jz      loc_140082EEC
0x140082dd2  call    Srv2DereferenceWorkItem
0x140082dd7  jmp     short loc_140082D85
0x140082dd9  cmp     [rsi+2], r9b
0x140082ddd  mov     eax, 1
0x140082de2  movzx   ebp, bpl
0x140082de6  cmovz   ebp, eax
0x140082de9  jmp     loc_140082D1A
0x140082dee  sub     r14d, 1
0x140082df2  jz      loc_140082F1A
0x140082df8  sub     r14d, 1
0x140082dfc  jz      loc_140082F1A
0x140082e02  cmp     r14d, 1
0x140082e06  jnz     loc_140082CE2
0x140082e0c  mov     rax, [rbx+78h]
0x140082e10  mov     [rax+8], r9
0x140082e14  mov     rax, [rbx+78h]
0x140082e18  mov     [rax+18h], r9
0x140082e1c  mov     rax, [rsi+0E0h]
0x140082e23  mov     rcx, [rbx+78h]
0x140082e27  mov     [rcx+70h], rax
0x140082e2b  mov     rax, [rbx+78h]
0x140082e2f  mov     [rax+10h], r9d
0x140082e33  mov     rax, [rsi+0D8h]
0x140082e3a  mov     [r8-28h], rax
0x140082e3e  jmp     loc_140082CE2
0x140082e43  mov     edx, 0Fh
0x140082e48  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140082e4f  cmp     r9b, dl
0x140082e52  cmovg   edx, r9d
0x140082e56  xor     r8d, r8d
0x140082e59  call    cs:__imp_IoAllocateIrpEx
0x140082e60  nop     dword ptr [rax+rax+00h]
0x140082e65  mov     rdi, rax
0x140082e68  test    rax, rax
0x140082e6b  jz      loc_1400992EC
0x140082e71  mov     rcx, [rbx+78h]; Irp
0x140082e75  call    cs:__imp_IoFreeIrp
0x140082e7c  nop     dword ptr [rax+rax+00h]
0x140082e81  mov     [rbx+78h], rdi
0x140082e85  jmp     loc_140082B89
0x140082e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e91  lea     rax, WPP_GLOBAL_Control
0x140082e98  cmp     rcx, rax
0x140082e9b  jnz     loc_140082F58
0x140082ea1  mov     r9d, 0BFFh
0x140082ea7  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140082eae  mov     edx, 0C0000120h
0x140082eb3  mov     rcx, rbx
0x140082eb6  call    _Smb2SetError
0x140082ebb  xor     eax, eax
0x140082ebd  jmp     loc_140082D8A
0x140082ec2  cmp     [rsi+0C8h], r9d
0x140082ec9  jnz     loc_140082CAB
0x140082ecf  mov     rax, [rbx+78h]
0x140082ed3  mov     [rax+10h], r9d
0x140082ed7  mov     rax, [rbx+78h]
0x140082edb  mov     [rax+18h], r9
0x140082edf  mov     rax, [rbx+78h]
0x140082ee3  mov     [rax+70h], r9
0x140082ee7  jmp     loc_140082CE2
0x140082eec  call    Smb2GoAsync2
0x140082ef1  jmp     loc_140082D85
0x140082ef6  mov     dword ptr [r8-30h], 11DFFFh
0x140082efe  mov     rax, [rsi+0E0h]
0x140082f05  mov     rcx, [rbx+78h]
0x140082f09  mov     [rcx+18h], rax
0x140082f0d  mov     rax, [rbx+78h]
0x140082f11  mov     [rax+70h], r9
0x140082f15  jmp     loc_140082D0C
0x140082f1a  mov     rcx, [rbx+78h]
0x140082f1e  mov     rax, [rsi+0E8h]
0x140082f25  mov     [rcx+8], rax
0x140082f29  mov     rax, [rsi+0D8h]
0x140082f30  mov     rcx, [rbx+78h]
0x140082f34  mov     [rcx+18h], rax
0x140082f38  mov     rax, [rbx+78h]
0x140082f3c  mov     [rax+70h], r9
0x140082f40  mov     rax, [rbx+78h]
0x140082f44  mov     dword ptr [rax+10h], 10h
0x140082f4b  jmp     loc_140082CE2
0x140082f50  mov     r13b, 1
0x140082f53  jmp     loc_140082D0C
0x140082f58  test    dword ptr [rcx+2Ch], 20000000h
0x140082f5f  jz      loc_140082EA1
0x140082f65  cmp     byte ptr [rcx+29h], 1
0x140082f69  jb      loc_140082EA1
0x140082f6f  mov     rcx, [rcx+18h]
0x140082f73  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x140082f7a  mov     edx, 63h ; 'c'
0x140082f7f  mov     r9, rbx
0x140082f82  call    WPP_SF_q
0x140082f87  jmp     loc_140082EA1
0x140082f8c  mov     rcx, gs:188h; Thread
0x140082f95  xor     edx, edx; Token
0x140082f97  call    cs:__imp_PsAssignImpersonationToken
0x140082f9e  nop     dword ptr [rax+rax+00h]
0x140082fa3  jmp     loc_140082D80
0x14009928c  mov     rcx, rsi
0x14009928f  call    Smb2ImpersonateWorkItem
0x140099294  mov     edi, eax
0x140099296  test    eax, eax
0x140099298  jns     loc_140082D44
0x14009929e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400992a5  lea     rax, WPP_GLOBAL_Control
0x1400992ac  cmp     rcx, rax
0x1400992af  jz      short loc_1400992D8
0x1400992b1  test    dword ptr [rcx+2Ch], 20000000h
0x1400992b8  jz      short loc_1400992D8
0x1400992ba  cmp     byte ptr [rcx+29h], 1
0x1400992be  jb      short loc_1400992D8
0x1400992c0  mov     rcx, [rcx+18h]
0x1400992c4  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x1400992cb  mov     edx, 64h ; 'd'
0x1400992d0  mov     r9, rbx
0x1400992d3  call    WPP_SF_q
0x1400992d8  mov     r9d, 0C14h
0x1400992de  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400992e5  mov     edx, edi
0x1400992e7  jmp     loc_140082EB3
0x1400992ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400992f3  lea     rax, WPP_GLOBAL_Control
0x1400992fa  cmp     rcx, rax
0x1400992fd  jz      short loc_14009932E
0x1400992ff  test    dword ptr [rcx+2Ch], 20000000h
0x140099306  jz      short loc_14009932E
0x140099308  cmp     byte ptr [rcx+29h], 1
0x14009930c  jb      short loc_14009932E
0x14009930e  mov     rcx, [rcx+18h]
0x140099312  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x140099319  mov     edx, 62h ; 'b'
0x14009931e  mov     [rsp+58h+var_38], 0C000009Ah
0x140099326  mov     r9, rbx
0x140099329  call    WPP_SF_qD
0x14009932e  mov     r9d, 0B6Ah
0x140099334  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14009933b  mov     edx, 0C000009Ah
0x140099340  mov     rcx, rbx
0x140099343  call    _Smb2SetError
0x140099348  xor     eax, eax
0x14009934a  jmp     loc_140082D94
```
