# XPartPartitionsRemoveWorkerRoutine

- ea: `0x14002ea90`
- end: `0x14002ed73`
- name: `XPartPartitionsRemoveWorkerRoutine`
- size: `739`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400055cc`
- `0x140010070`
- `0x14001240c`
- `0x140012644`
- `0x140012a24`
- `0x140012c20`
- `0x140016e8c`
- `0x140017190`
- `0x14002ea90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecfd`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002eb37`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002eb37`
- `ntoskrnl!KeSetEvent` at `0x14002eb73`
- `ntoskrnl!KeSetEvent` at `0x14002ed16`
- `ntoskrnl!KeSetEvent` at `0x14002eb73`
- `ntoskrnl!KeSetEvent` at `0x14002ed16`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002eafc`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002eafc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002eb94`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002eb94`
- `ntoskrnl!IofCompleteRequest` at `0x14002ed33`
- `ntoskrnl!IofCompleteRequest` at `0x14002ed33`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eba4`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eba4`

## pseudocode

```c
void __fastcall XPartPartitionsRemoveWorkerRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  _QWORD *v2; // rdi
  void ***v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  void **v7; // rax
  void **v8; // rcx
  __int64 v9; // r8
  void **v10; // rax
  void **v11; // rcx
  void **v12; // rcx
  char *v13; // rcx
  struct _KEVENT *v14; // rbp
  IRP *v15; // rsi
  __int64 v16; // rdx

  v2 = (_QWORD *)DvRemoveWorkQueue(&qword_1400206E8, Context);
  if ( v2 )
  {
    while ( 1 )
    {
      v3 = (void ***)(v2 - 2);
      v2 = (_QWORD *)*v2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v4 = XPartDbgID(v3);
        WPP_SF_iq(*(_QWORD *)(v5 + 24), v5, v6, v4, v3);
      }
      ExAcquireFastMutex(&FastMutex);
      v7 = *v3;
      if ( (*v3)[1] != v3 || (v8 = v3[1], *v8 != v3) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = v8;
      v3[1] = (void **)v3;
      *v3 = (void **)v3;
      ExReleaseFastMutex(&FastMutex);
      ChDestroyPartition(v3);
      v10 = v3[129];
      if ( v10 )
        ((void (__fastcall *)(void ***))v10)(v3);
      if ( v3[10] )
      {
        *((_BYTE *)v3 + 112) = 1;
        KeSetEvent((PRKEVENT)(v3 + 11), 0, 0);
        KeWaitForSingleObject(v3[10], Executive, 0, 0, 0);
        ObfDereferenceObject(v3[10]);
        v3[10] = 0;
      }
      v11 = v3[29];
      if ( v11 )
      {
        ExFreePoolWithTag(v11, 0x73756256u);
        v3[29] = 0;
      }
      if ( v3[122] )
        XPartFreeSendMessage();
      v12 = v3[19];
      if ( v12 )
        ExFreePoolWithTag(v12, 0x73756256u);
      v13 = (char *)v3[50];
      if ( v13 && v13 != (char *)(v3 + 51) )
      {
        ExFreePoolWithTag(v13, 0x73756256u);
        v3[50] = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF__guid_q(WPP_GLOBAL_Control->AttachedDevice, 29, v9, v3 + 16, qword_1400207A0);
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01033 + 1648))(
        WdfDriverGlobals,
        qword_1400207A0,
        0,
        1224,
        "onecore\\vm\\dv\\vmbus\\xpart\\baseclass.c");
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids, v3);
      }
      v14 = (struct _KEVENT *)v3[24];
      v15 = (IRP *)v3[25];
      ExFreePoolWithTag(v3, 0x73756256u);
      if ( v14 )
        KeSetEvent(v14, 0, 0);
      if ( v15 )
      {
        v15->IoStatus.Status = 0;
        IofCompleteRequest(v15, 0);
      }
      if ( !v2 )
      {
        v2 = (_QWORD *)DvRemoveWorkQueue(&qword_1400206E8, v16);
        if ( !v2 )
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x14002ea90  push    rbx
0x14002ea92  push    rbp
0x14002ea93  push    rsi
0x14002ea94  push    rdi
0x14002ea95  push    r13
0x14002ea97  sub     rsp, 30h
0x14002ea9b  lea     rcx, qword_1400206E8
0x14002eaa2  call    DvRemoveWorkQueue
0x14002eaa7  mov     rdi, rax
0x14002eaaa  test    rax, rax
0x14002eaad  jz      loc_14002ED60
0x14002eab3  lea     r13, WPP_GLOBAL_Control
0x14002eaba  lea     rbx, [rdi-10h]
0x14002eabe  mov     rdi, [rdi]
0x14002eac1  mov     rdx, cs:WPP_GLOBAL_Control
0x14002eac8  cmp     rdx, r13
0x14002eacb  jz      short loc_14002EAF5
0x14002eacd  test    dword ptr [rdx+2Ch], 1000000h
0x14002ead4  jz      short loc_14002EAF5
0x14002ead6  cmp     byte ptr [rdx+29h], 4
0x14002eada  jb      short loc_14002EAF5
0x14002eadc  mov     rcx, rbx
0x14002eadf  call    XPartDbgID
0x14002eae4  mov     rcx, [rdx+18h]
0x14002eae8  mov     r9, rax
0x14002eaeb  mov     [rsp+58h+Timeout], rbx
0x14002eaf0  call    WPP_SF_iq
0x14002eaf5  lea     rcx, FastMutex; FastMutex
0x14002eafc  call    cs:__imp_ExAcquireFastMutex
0x14002eb03  nop     dword ptr [rax+rax+00h]
0x14002eb08  mov     rax, [rbx]
0x14002eb0b  cmp     [rax+8], rbx
0x14002eb0f  jnz     loc_14002ED6C
0x14002eb15  mov     rcx, [rbx+8]
0x14002eb19  cmp     [rcx], rbx
0x14002eb1c  jnz     loc_14002ED6C
0x14002eb22  mov     [rcx], rax
0x14002eb25  mov     [rax+8], rcx
0x14002eb29  lea     rcx, FastMutex; FastMutex
0x14002eb30  mov     [rbx+8], rbx
0x14002eb34  mov     [rbx], rbx
0x14002eb37  call    cs:__imp_ExReleaseFastMutex
0x14002eb3e  nop     dword ptr [rax+rax+00h]
0x14002eb43  mov     rcx, rbx
0x14002eb46  call    ChDestroyPartition
0x14002eb4b  mov     rax, [rbx+408h]
0x14002eb52  test    rax, rax
0x14002eb55  jz      short loc_14002EB5F
0x14002eb57  mov     rcx, rbx
0x14002eb5a  call    _guard_dispatch_icall
0x14002eb5f  cmp     qword ptr [rbx+50h], 0
0x14002eb64  jz      short loc_14002EBB8
0x14002eb66  lea     rcx, [rbx+58h]; Event
0x14002eb6a  mov     byte ptr [rbx+70h], 1
0x14002eb6e  xor     r8d, r8d; Wait
0x14002eb71  xor     edx, edx; Increment
0x14002eb73  call    cs:__imp_KeSetEvent
0x14002eb7a  nop     dword ptr [rax+rax+00h]
0x14002eb7f  mov     rcx, [rbx+50h]; Object
0x14002eb83  xor     r9d, r9d; Alertable
0x14002eb86  xor     r8d, r8d; WaitMode
0x14002eb89  mov     [rsp+58h+Timeout], 0; Timeout
0x14002eb92  xor     edx, edx; WaitReason
0x14002eb94  call    cs:__imp_KeWaitForSingleObject
0x14002eb9b  nop     dword ptr [rax+rax+00h]
0x14002eba0  mov     rcx, [rbx+50h]; Object
0x14002eba4  call    cs:__imp_ObfDereferenceObject
0x14002ebab  nop     dword ptr [rax+rax+00h]
0x14002ebb0  mov     qword ptr [rbx+50h], 0
0x14002ebb8  mov     rcx, [rbx+0E8h]; P
0x14002ebbf  test    rcx, rcx
0x14002ebc2  jz      short loc_14002EBE0
0x14002ebc4  mov     edx, 73756256h; Tag
0x14002ebc9  call    cs:__imp_ExFreePoolWithTag
0x14002ebd0  nop     dword ptr [rax+rax+00h]
0x14002ebd5  mov     qword ptr [rbx+0E8h], 0
0x14002ebe0  mov     rcx, [rbx+3D0h]
0x14002ebe7  test    rcx, rcx
0x14002ebea  jz      short loc_14002EBF1
0x14002ebec  call    XPartFreeSendMessage
0x14002ebf1  mov     rcx, [rbx+98h]; P
0x14002ebf8  test    rcx, rcx
0x14002ebfb  jz      short loc_14002EC0E
0x14002ebfd  mov     edx, 73756256h; Tag
0x14002ec02  call    cs:__imp_ExFreePoolWithTag
0x14002ec09  nop     dword ptr [rax+rax+00h]
0x14002ec0e  mov     rcx, [rbx+190h]; P
0x14002ec15  test    rcx, rcx
0x14002ec18  jz      short loc_14002EC42
0x14002ec1a  lea     rax, [rbx+198h]
0x14002ec21  cmp     rcx, rax
0x14002ec24  jz      short loc_14002EC42
0x14002ec26  mov     edx, 73756256h; Tag
0x14002ec2b  call    cs:__imp_ExFreePoolWithTag
0x14002ec32  nop     dword ptr [rax+rax+00h]
0x14002ec37  mov     qword ptr [rbx+190h], 0
0x14002ec42  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ec49  cmp     rcx, r13
0x14002ec4c  jz      short loc_14002EC7E
0x14002ec4e  test    dword ptr [rcx+2Ch], 10000h
0x14002ec55  jz      short loc_14002EC7E
0x14002ec57  cmp     byte ptr [rcx+29h], 4
0x14002ec5b  jb      short loc_14002EC7E
0x14002ec5d  mov     rax, cs:qword_1400207A0
0x14002ec64  lea     r9, [rbx+80h]
0x14002ec6b  mov     rcx, [rcx+18h]
0x14002ec6f  mov     edx, 1Dh
0x14002ec74  mov     [rsp+58h+Timeout], rax
0x14002ec79  call    WPP_SF__guid_q
0x14002ec7e  mov     rax, cs:WdfFunctions_01033
0x14002ec85  lea     rcx, aOnecoreVmDvVmb_1; "onecore\\vm\\dv\\vmbus\\xpart\\baseclas"...
0x14002ec8c  mov     rdx, cs:qword_1400207A0
0x14002ec93  mov     r9d, 4C8h
0x14002ec99  mov     [rsp+58h+Timeout], rcx
0x14002ec9e  xor     r8d, r8d
0x14002eca1  mov     rcx, cs:WdfDriverGlobals
0x14002eca8  mov     rax, [rax+670h]
0x14002ecaf  call    _guard_dispatch_icall
0x14002ecb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ecbb  cmp     rcx, r13
0x14002ecbe  jz      short loc_14002ECE7
0x14002ecc0  test    dword ptr [rcx+2Ch], 1000000h
0x14002ecc7  jz      short loc_14002ECE7
0x14002ecc9  cmp     byte ptr [rcx+29h], 4
0x14002eccd  jb      short loc_14002ECE7
0x14002eccf  mov     rcx, [rcx+18h]
0x14002ecd3  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002ecda  mov     edx, 1Eh
0x14002ecdf  mov     r9, rbx
0x14002ece2  call    WPP_SF_q
0x14002ece7  mov     rbp, [rbx+0C0h]
0x14002ecee  mov     edx, 73756256h; Tag
0x14002ecf3  mov     rsi, [rbx+0C8h]
0x14002ecfa  mov     rcx, rbx; P
0x14002ecfd  call    cs:__imp_ExFreePoolWithTag
0x14002ed04  nop     dword ptr [rax+rax+00h]
0x14002ed09  test    rbp, rbp
0x14002ed0c  jz      short loc_14002ED22
0x14002ed0e  xor     r8d, r8d; Wait
0x14002ed11  xor     edx, edx; Increment
0x14002ed13  mov     rcx, rbp; Event
0x14002ed16  call    cs:__imp_KeSetEvent
0x14002ed1d  nop     dword ptr [rax+rax+00h]
0x14002ed22  test    rsi, rsi
0x14002ed25  jz      short loc_14002ED3F
0x14002ed27  xor     edx, edx; PriorityBoost
0x14002ed29  mov     dword ptr [rsi+30h], 0
0x14002ed30  mov     rcx, rsi; Irp
0x14002ed33  call    cs:__imp_IofCompleteRequest
0x14002ed3a  nop     dword ptr [rax+rax+00h]
0x14002ed3f  test    rdi, rdi
0x14002ed42  jnz     loc_14002EABA
0x14002ed48  lea     rcx, qword_1400206E8
0x14002ed4f  call    DvRemoveWorkQueue
0x14002ed54  mov     rdi, rax
0x14002ed57  test    rax, rax
0x14002ed5a  jnz     loc_14002EABA
0x14002ed60  add     rsp, 30h
0x14002ed64  pop     r13
0x14002ed66  pop     rdi
0x14002ed67  pop     rsi
0x14002ed68  pop     rbp
0x14002ed69  pop     rbx
0x14002ed6a  retn
0x14002ed6c  mov     ecx, 3
0x14002ed71  int     29h; Win8: RtlFailFast(ecx)
```
