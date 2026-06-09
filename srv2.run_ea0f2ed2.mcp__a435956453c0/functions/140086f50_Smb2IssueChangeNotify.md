# Smb2IssueChangeNotify

- ea: `0x140086f50`
- end: `0x1400872b1`
- name: `Smb2IssueChangeNotify`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086e30`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x1400152a0`
- `0x1400157f0`
- `0x1400186f0`
- `0x1400222ec`
- `0x1400224b8`
- `0x140022958`
- `0x140086f50`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140087133`
- `ntoskrnl!KeDelayExecutionThread` at `0x140087133`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140086fbe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140086fbe`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140086f67`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140086f67`
- `ntoskrnl!IofCallDriver` at `0x1400870fe`
- `ntoskrnl!IofCallDriver` at `0x1400870fe`
- `ntoskrnl!IoFreeIrp` at `0x14008719e`
- `ntoskrnl!IoFreeIrp` at `0x14008719e`
- `ntoskrnl!IoAllocateIrpEx` at `0x140087182`
- `ntoskrnl!IoAllocateIrpEx` at `0x140087182`
- `ntoskrnl!IoReuseIrp` at `0x140086f98`
- `ntoskrnl!IoReuseIrp` at `0x140086f98`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140087115`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140087115`

## pseudocode

```c
__int64 __fastcall Smb2IssueChangeNotify(__int64 a1)
{
  __int64 v1; // rsi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  IRP *v4; // rcx
  struct _DEVICE_OBJECT *v5; // rbp
  char StackSize; // r8
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  SECURITY_STATUS v14; // edi
  __int64 v16; // rdx
  __int64 Irp; // rdi
  __int64 v18; // r9
  __int64 v19; // rdx
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v1 + 88));
  v4 = *(IRP **)(a1 + 120);
  v5 = RelatedDeviceObject;
  StackSize = RelatedDeviceObject->StackSize;
  if ( v4->StackCount < StackSize || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v16 = 15;
    if ( StackSize > 15 )
      v16 = (unsigned __int8)RelatedDeviceObject->StackSize;
    Irp = IoAllocateIrpEx(-1, v16, 0);
    if ( !Irp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
          a1,
          -1073741670);
      }
      v18 = 905;
      v19 = 3221225626LL;
      goto LABEL_31;
    }
    IoFreeIrp(*(PIRP *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = Irp;
  }
  else
  {
    IoReuseIrp(v4, 0);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 192LL) = *(_QWORD *)(v1 + 88);
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 152LL) = *(_QWORD *)(*(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8) + 224LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 120) + 64LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  v8 = *(_QWORD *)(a1 + 120);
  v9 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(a1 + 48) = Smb2ContinueChangeNotify;
  v10 = *(_QWORD *)(v8 + 184);
  *(_QWORD *)(v10 - 16) = Srv2PostOnCompletionAndClearCancel;
  *(_QWORD *)(v10 - 8) = a1;
  *(_BYTE *)(v10 - 69) = -32;
  *(_WORD *)(v9 - 72) = 524;
  *(_QWORD *)(v9 - 24) = *(_QWORD *)(v1 + 88);
  *(_QWORD *)(v9 - 32) = v5;
  *(_BYTE *)(v9 - 70) = *(_BYTE *)(v1 + 200);
  *(_DWORD *)(v9 - 64) = *(_DWORD *)(v1 + 196);
  *(_DWORD *)(v9 - 56) = *(_DWORD *)(v1 + 192);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 112LL) = 0;
  v11 = *(_QWORD *)(v1 + 160);
  v12 = *(_QWORD *)(a1 + 120);
  if ( (v5->Flags & 0x10) != 0 )
    *(_QWORD *)(v12 + 8) = *(_QWORD *)(v11 + 56);
  else
    *(_QWORD *)(v12 + 24) = *(_QWORD *)(v11 + 24);
  LOBYTE(v12) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v12, 965, "Smb2IssueChangeNotify", 1);
  LOBYTE(v13) = 1;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v13) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids, a1);
    }
    v18 = 973;
    v19 = 3221225760LL;
    goto LABEL_31;
  }
  v14 = Smb2ImpersonateWorkItem(v1);
  if ( v14 < 0 )
  {
    Srv2UnmarkWorkItemCancellable(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        (unsigned int)v14);
    }
    v18 = 986;
    v19 = (unsigned int)v14;
LABEL_31:
    Smb2SetError(a1, v19, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", v18);
    return Srv2CompleteWorkItem(a1, 0);
  }
  Srv2ReferenceConnection(a1);
  IofCallDriver(v5, *(PIRP *)(a1 + 120));
  PsAssignImpersonationToken(KeGetCurrentThread(), 0);
  Interval.QuadPart = -5000;
  KeDelayExecutionThread(0, 0, &Interval);
  if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
    return Srv2DereferenceWorkItem(a1);
  else
    return Smb2GoAsync2(a1);
}

```

## disassembly

```asm
0x140086f50  push    rbx
0x140086f52  push    rbp
0x140086f53  push    rsi
0x140086f54  push    rdi
0x140086f55  sub     rsp, 38h
0x140086f59  mov     rsi, [rcx+230h]
0x140086f60  mov     rbx, rcx
0x140086f63  mov     rcx, [rsi+58h]; FileObject
0x140086f67  call    cs:__imp_IoGetRelatedDeviceObject
0x140086f6e  nop     dword ptr [rax+rax+00h]
0x140086f73  mov     rcx, [rbx+78h]; Irp
0x140086f77  mov     rbp, rax
0x140086f7a  movzx   r8d, byte ptr [rax+4Ch]
0x140086f7f  cmp     [rcx+42h], r8b
0x140086f83  jl      loc_14008716C
0x140086f89  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140086f90  jnz     loc_14008716C
0x140086f96  xor     edx, edx; Iostatus
0x140086f98  call    cs:__imp_IoReuseIrp
0x140086f9f  nop     dword ptr [rax+rax+00h]
0x140086fa4  mov     rax, [rsi+58h]
0x140086fa8  mov     rcx, [rbx+78h]
0x140086fac  mov     [rcx+0C0h], rax
0x140086fb3  mov     rax, [rbx+40h]
0x140086fb7  mov     rdi, [rax+88h]
0x140086fbe  call    cs:__imp_KeGetCurrentNodeNumber
0x140086fc5  nop     dword ptr [rax+rax+00h]
0x140086fca  movzx   eax, ax
0x140086fcd  xor     r8d, r8d
0x140086fd0  mov     rcx, [rdi+rax*8+8]
0x140086fd5  mov     rax, [rbx+78h]
0x140086fd9  mov     rdx, [rcx+0E0h]
0x140086fe0  mov     [rax+98h], rdx
0x140086fe7  lea     rdx, Smb2ContinueChangeNotify
0x140086fee  mov     rax, [rbx+78h]
0x140086ff2  mov     byte ptr [rax+40h], 0
0x140086ff6  mov     rax, [rbx+78h]
0x140086ffa  mov     [rax+8], r8
0x140086ffe  mov     rax, [rbx+78h]
0x140087002  mov     [rax+18h], r8
0x140087006  mov     rax, [rbx+78h]
0x14008700a  mov     [rax+70h], r8
0x14008700e  mov     rax, [rbx+78h]
0x140087012  mov     [rax+30h], r8d
0x140087016  mov     rax, [rbx+78h]
0x14008701a  mov     [rax+38h], r8
0x14008701e  mov     rax, [rbx+78h]
0x140087022  mov     rcx, [rax+0B8h]
0x140087029  mov     [rbx+30h], rdx
0x14008702d  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x140087034  mov     rax, [rax+0B8h]
0x14008703b  mov     [rax-10h], rdx
0x14008703f  mov     [rax-8], rbx
0x140087043  mov     byte ptr [rax-45h], 0E0h
0x140087047  mov     word ptr [rcx-48h], 20Ch
0x14008704d  mov     rax, [rsi+58h]
0x140087051  mov     [rcx-18h], rax
0x140087055  mov     [rcx-20h], rbp
0x140087059  movzx   eax, byte ptr [rsi+0C8h]
0x140087060  mov     [rcx-46h], al
0x140087063  mov     eax, [rsi+0C4h]
0x140087069  mov     [rcx-40h], eax
0x14008706c  mov     eax, [rsi+0C0h]
0x140087072  mov     [rcx-38h], eax
0x140087075  mov     rax, [rbx+78h]
0x140087079  mov     [rax+18h], r8
0x14008707d  mov     rax, [rbx+78h]
0x140087081  mov     [rax+8], r8
0x140087085  mov     rax, [rbx+78h]
0x140087089  mov     [rax+70h], r8
0x14008708d  mov     eax, [rbp+30h]
0x140087090  mov     rcx, [rsi+0A0h]
0x140087097  mov     rdx, [rbx+78h]
0x14008709b  test    al, 10h
0x14008709d  jnz     loc_1400871B3
0x1400870a3  mov     rax, [rcx+18h]
0x1400870a7  mov     [rdx+18h], rax
0x1400870ab  lea     rcx, [rbx+248h]
0x1400870b2  mov     byte ptr [rsp+58h+var_38], 1
0x1400870b7  lea     r9, aSmb2issuechang; "Smb2IssueChangeNotify"
0x1400870be  mov     r8d, 3C5h
0x1400870c4  mov     dl, 3
0x1400870c6  call    SRV2_PERF_ENTER_EX
0x1400870cb  mov     dl, 1
0x1400870cd  mov     rcx, rbx
0x1400870d0  call    Srv2MarkWorkItemCancellable
0x1400870d5  test    eax, eax
0x1400870d7  js      loc_1400871C0
0x1400870dd  mov     rcx, rsi
0x1400870e0  call    Smb2ImpersonateWorkItem
0x1400870e5  mov     edi, eax
0x1400870e7  mov     rcx, rbx
0x1400870ea  test    eax, eax
0x1400870ec  js      loc_14008720C
0x1400870f2  call    Srv2ReferenceConnection
0x1400870f7  mov     rdx, [rbx+78h]; Irp
0x1400870fb  mov     rcx, rbp; DeviceObject
0x1400870fe  call    cs:__imp_IofCallDriver
0x140087105  nop     dword ptr [rax+rax+00h]
0x14008710a  mov     rcx, gs:188h; Thread
0x140087113  xor     edx, edx; Token
0x140087115  call    cs:__imp_PsAssignImpersonationToken
0x14008711c  nop     dword ptr [rax+rax+00h]
0x140087121  lea     r8, [rsp+58h+Interval]; Interval
0x140087126  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFEC78h
0x14008712f  xor     edx, edx; Alertable
0x140087131  xor     ecx, ecx; WaitMode
0x140087133  call    cs:__imp_KeDelayExecutionThread
0x14008713a  nop     dword ptr [rax+rax+00h]
0x14008713f  mov     rcx, rbx
0x140087142  call    Srv2MarkWorkItemPending
0x140087147  mov     rcx, rbx
0x14008714a  test    eax, eax
0x14008714c  jz      short loc_14008715D
0x14008714e  call    Srv2DereferenceWorkItem
0x140087153  add     rsp, 38h
0x140087157  pop     rdi
0x140087158  pop     rsi
0x140087159  pop     rbp
0x14008715a  pop     rbx
0x14008715b  retn
0x14008715d  call    Smb2GoAsync2
0x140087162  add     rsp, 38h
0x140087166  pop     rdi
0x140087167  pop     rsi
0x140087168  pop     rbp
0x140087169  pop     rbx
0x14008716a  retn
0x14008716c  mov     edx, 0Fh
0x140087171  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140087178  cmp     r8b, dl
0x14008717b  cmovg   edx, r8d
0x14008717f  xor     r8d, r8d
0x140087182  call    cs:__imp_IoAllocateIrpEx
0x140087189  nop     dword ptr [rax+rax+00h]
0x14008718e  mov     rdi, rax
0x140087191  test    rax, rax
0x140087194  jz      loc_14008725D
0x14008719a  mov     rcx, [rbx+78h]; Irp
0x14008719e  call    cs:__imp_IoFreeIrp
0x1400871a5  nop     dword ptr [rax+rax+00h]
0x1400871aa  mov     [rbx+78h], rdi
0x1400871ae  jmp     loc_140086FA4
0x1400871b3  mov     rax, [rcx+38h]
0x1400871b7  mov     [rdx+8], rax
0x1400871bb  jmp     loc_1400870AB
0x1400871c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400871c7  lea     rax, WPP_GLOBAL_Control
0x1400871ce  cmp     rcx, rax
0x1400871d1  jz      loc_14009AF1A
0x1400871d7  test    dword ptr [rcx+2Ch], 4000000h
0x1400871de  jz      loc_14009AF1A
0x1400871e4  cmp     byte ptr [rcx+29h], 1
0x1400871e8  jb      loc_14009AF1A
0x1400871ee  mov     rcx, [rcx+18h]
0x1400871f2  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x1400871f9  mov     edx, 18h
0x1400871fe  mov     r9, rbx
0x140087201  call    WPP_SF_q
0x140087206  nop
0x140087207  jmp     loc_14009AF1A
0x14008720c  call    Srv2UnmarkWorkItemCancellable
0x140087211  mov     rcx, cs:WPP_GLOBAL_Control
0x140087218  lea     rax, WPP_GLOBAL_Control
0x14008721f  cmp     rcx, rax
0x140087222  jz      loc_14009AF27
0x140087228  test    dword ptr [rcx+2Ch], 4000000h
0x14008722f  jz      loc_14009AF27
0x140087235  cmp     byte ptr [rcx+29h], 1
0x140087239  jb      loc_14009AF27
0x14008723f  mov     rcx, [rcx+18h]
0x140087243  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14008724a  mov     edx, 19h
0x14008724f  mov     r9d, edi
0x140087252  call    WPP_SF_d
0x140087257  nop
0x140087258  jmp     loc_14009AF27
0x14008725d  mov     rcx, cs:WPP_GLOBAL_Control
0x140087264  lea     rax, WPP_GLOBAL_Control
0x14008726b  cmp     rcx, rax
0x14008726e  jz      loc_14009AF31
0x140087274  test    dword ptr [rcx+2Ch], 4000000h
0x14008727b  jz      loc_14009AF31
0x140087281  cmp     byte ptr [rcx+29h], 1
0x140087285  jb      loc_14009AF31
0x14008728b  mov     rcx, [rcx+18h]
0x14008728f  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x140087296  mov     edx, 17h
0x14008729b  mov     [rsp+58h+var_38], 0C000009Ah
0x1400872a3  mov     r9, rbx
0x1400872a6  call    WPP_SF_qD
0x1400872ab  nop
0x1400872ac  jmp     loc_14009AF31
0x14009af1a  mov     r9d, 3CDh
0x14009af20  mov     edx, 0C0000120h
0x14009af25  jmp     short loc_14009AF3C
0x14009af27  mov     r9d, 3DAh
0x14009af2d  mov     edx, edi
0x14009af2f  jmp     short loc_14009AF3C
0x14009af31  mov     r9d, 389h
0x14009af37  mov     edx, 0C000009Ah
0x14009af3c  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14009af43  mov     rcx, rbx
0x14009af46  call    _Smb2SetError
0x14009af4b  xor     edx, edx
0x14009af4d  mov     rcx, rbx
0x14009af50  call    Srv2CompleteWorkItem
0x14009af55  nop
0x14009af56  jmp     loc_140087153
```
