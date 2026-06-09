# XPartPartitionsRemoveWorkerRoutine

- ea: `0x14002ea40`
- end: `0x14002ed23`
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
- `0x14002ea40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002eb79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eb79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecad`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002eae7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002eae7`
- `ntoskrnl!KeSetEvent` at `0x14002eb23`
- `ntoskrnl!KeSetEvent` at `0x14002ecc6`
- `ntoskrnl!KeSetEvent` at `0x14002eb23`
- `ntoskrnl!KeSetEvent` at `0x14002ecc6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002eaac`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002eaac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002eb44`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002eb44`
- `ntoskrnl!IofCompleteRequest` at `0x14002ece3`
- `ntoskrnl!IofCompleteRequest` at `0x14002ece3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eb54`
- `ntoskrnl!ObfDereferenceObject` at `0x14002eb54`

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
0x14002ea40  push    rbx
0x14002ea42  push    rbp
0x14002ea43  push    rsi
0x14002ea44  push    rdi
0x14002ea45  push    r13
0x14002ea47  sub     rsp, 30h
0x14002ea4b  lea     rcx, qword_1400206E8
0x14002ea52  call    DvRemoveWorkQueue
0x14002ea57  mov     rdi, rax
0x14002ea5a  test    rax, rax
0x14002ea5d  jz      loc_14002ED10
0x14002ea63  lea     r13, WPP_GLOBAL_Control
0x14002ea6a  lea     rbx, [rdi-10h]
0x14002ea6e  mov     rdi, [rdi]
0x14002ea71  mov     rdx, cs:WPP_GLOBAL_Control
0x14002ea78  cmp     rdx, r13
0x14002ea7b  jz      short loc_14002EAA5
0x14002ea7d  test    dword ptr [rdx+2Ch], 1000000h
0x14002ea84  jz      short loc_14002EAA5
0x14002ea86  cmp     byte ptr [rdx+29h], 4
0x14002ea8a  jb      short loc_14002EAA5
0x14002ea8c  mov     rcx, rbx
0x14002ea8f  call    XPartDbgID
0x14002ea94  mov     rcx, [rdx+18h]
0x14002ea98  mov     r9, rax
0x14002ea9b  mov     [rsp+58h+Timeout], rbx
0x14002eaa0  call    WPP_SF_iq
0x14002eaa5  lea     rcx, FastMutex; FastMutex
0x14002eaac  call    cs:__imp_ExAcquireFastMutex
0x14002eab3  nop     dword ptr [rax+rax+00h]
0x14002eab8  mov     rax, [rbx]
0x14002eabb  cmp     [rax+8], rbx
0x14002eabf  jnz     loc_14002ED1C
0x14002eac5  mov     rcx, [rbx+8]
0x14002eac9  cmp     [rcx], rbx
0x14002eacc  jnz     loc_14002ED1C
0x14002ead2  mov     [rcx], rax
0x14002ead5  mov     [rax+8], rcx
0x14002ead9  lea     rcx, FastMutex; FastMutex
0x14002eae0  mov     [rbx+8], rbx
0x14002eae4  mov     [rbx], rbx
0x14002eae7  call    cs:__imp_ExReleaseFastMutex
0x14002eaee  nop     dword ptr [rax+rax+00h]
0x14002eaf3  mov     rcx, rbx
0x14002eaf6  call    ChDestroyPartition
0x14002eafb  mov     rax, [rbx+408h]
0x14002eb02  test    rax, rax
0x14002eb05  jz      short loc_14002EB0F
0x14002eb07  mov     rcx, rbx
0x14002eb0a  call    _guard_dispatch_icall
0x14002eb0f  cmp     qword ptr [rbx+50h], 0
0x14002eb14  jz      short loc_14002EB68
0x14002eb16  lea     rcx, [rbx+58h]; Event
0x14002eb1a  mov     byte ptr [rbx+70h], 1
0x14002eb1e  xor     r8d, r8d; Wait
0x14002eb21  xor     edx, edx; Increment
0x14002eb23  call    cs:__imp_KeSetEvent
0x14002eb2a  nop     dword ptr [rax+rax+00h]
0x14002eb2f  mov     rcx, [rbx+50h]; Object
0x14002eb33  xor     r9d, r9d; Alertable
0x14002eb36  xor     r8d, r8d; WaitMode
0x14002eb39  mov     [rsp+58h+Timeout], 0; Timeout
0x14002eb42  xor     edx, edx; WaitReason
0x14002eb44  call    cs:__imp_KeWaitForSingleObject
0x14002eb4b  nop     dword ptr [rax+rax+00h]
0x14002eb50  mov     rcx, [rbx+50h]; Object
0x14002eb54  call    cs:__imp_ObfDereferenceObject
0x14002eb5b  nop     dword ptr [rax+rax+00h]
0x14002eb60  mov     qword ptr [rbx+50h], 0
0x14002eb68  mov     rcx, [rbx+0E8h]; P
0x14002eb6f  test    rcx, rcx
0x14002eb72  jz      short loc_14002EB90
0x14002eb74  mov     edx, 73756256h; Tag
0x14002eb79  call    cs:__imp_ExFreePoolWithTag
0x14002eb80  nop     dword ptr [rax+rax+00h]
0x14002eb85  mov     qword ptr [rbx+0E8h], 0
0x14002eb90  mov     rcx, [rbx+3D0h]
0x14002eb97  test    rcx, rcx
0x14002eb9a  jz      short loc_14002EBA1
0x14002eb9c  call    XPartFreeSendMessage
0x14002eba1  mov     rcx, [rbx+98h]; P
0x14002eba8  test    rcx, rcx
0x14002ebab  jz      short loc_14002EBBE
0x14002ebad  mov     edx, 73756256h; Tag
0x14002ebb2  call    cs:__imp_ExFreePoolWithTag
0x14002ebb9  nop     dword ptr [rax+rax+00h]
0x14002ebbe  mov     rcx, [rbx+190h]; P
0x14002ebc5  test    rcx, rcx
0x14002ebc8  jz      short loc_14002EBF2
0x14002ebca  lea     rax, [rbx+198h]
0x14002ebd1  cmp     rcx, rax
0x14002ebd4  jz      short loc_14002EBF2
0x14002ebd6  mov     edx, 73756256h; Tag
0x14002ebdb  call    cs:__imp_ExFreePoolWithTag
0x14002ebe2  nop     dword ptr [rax+rax+00h]
0x14002ebe7  mov     qword ptr [rbx+190h], 0
0x14002ebf2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ebf9  cmp     rcx, r13
0x14002ebfc  jz      short loc_14002EC2E
0x14002ebfe  test    dword ptr [rcx+2Ch], 10000h
0x14002ec05  jz      short loc_14002EC2E
0x14002ec07  cmp     byte ptr [rcx+29h], 4
0x14002ec0b  jb      short loc_14002EC2E
0x14002ec0d  mov     rax, cs:qword_1400207A0
0x14002ec14  lea     r9, [rbx+80h]
0x14002ec1b  mov     rcx, [rcx+18h]
0x14002ec1f  mov     edx, 1Dh
0x14002ec24  mov     [rsp+58h+Timeout], rax
0x14002ec29  call    WPP_SF__guid_q
0x14002ec2e  mov     rax, cs:WdfFunctions_01033
0x14002ec35  lea     rcx, aOnecoreVmDvVmb_1; "onecore\\vm\\dv\\vmbus\\xpart\\baseclas"...
0x14002ec3c  mov     rdx, cs:qword_1400207A0
0x14002ec43  mov     r9d, 4C8h
0x14002ec49  mov     [rsp+58h+Timeout], rcx
0x14002ec4e  xor     r8d, r8d
0x14002ec51  mov     rcx, cs:WdfDriverGlobals
0x14002ec58  mov     rax, [rax+670h]
0x14002ec5f  call    _guard_dispatch_icall
0x14002ec64  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ec6b  cmp     rcx, r13
0x14002ec6e  jz      short loc_14002EC97
0x14002ec70  test    dword ptr [rcx+2Ch], 1000000h
0x14002ec77  jz      short loc_14002EC97
0x14002ec79  cmp     byte ptr [rcx+29h], 4
0x14002ec7d  jb      short loc_14002EC97
0x14002ec7f  mov     rcx, [rcx+18h]
0x14002ec83  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002ec8a  mov     edx, 1Eh
0x14002ec8f  mov     r9, rbx
0x14002ec92  call    WPP_SF_q
0x14002ec97  mov     rbp, [rbx+0C0h]
0x14002ec9e  mov     edx, 73756256h; Tag
0x14002eca3  mov     rsi, [rbx+0C8h]
0x14002ecaa  mov     rcx, rbx; P
0x14002ecad  call    cs:__imp_ExFreePoolWithTag
0x14002ecb4  nop     dword ptr [rax+rax+00h]
0x14002ecb9  test    rbp, rbp
0x14002ecbc  jz      short loc_14002ECD2
0x14002ecbe  xor     r8d, r8d; Wait
0x14002ecc1  xor     edx, edx; Increment
0x14002ecc3  mov     rcx, rbp; Event
0x14002ecc6  call    cs:__imp_KeSetEvent
0x14002eccd  nop     dword ptr [rax+rax+00h]
0x14002ecd2  test    rsi, rsi
0x14002ecd5  jz      short loc_14002ECEF
0x14002ecd7  xor     edx, edx; PriorityBoost
0x14002ecd9  mov     dword ptr [rsi+30h], 0
0x14002ece0  mov     rcx, rsi; Irp
0x14002ece3  call    cs:__imp_IofCompleteRequest
0x14002ecea  nop     dword ptr [rax+rax+00h]
0x14002ecef  test    rdi, rdi
0x14002ecf2  jnz     loc_14002EA6A
0x14002ecf8  lea     rcx, qword_1400206E8
0x14002ecff  call    DvRemoveWorkQueue
0x14002ed04  mov     rdi, rax
0x14002ed07  test    rax, rax
0x14002ed0a  jnz     loc_14002EA6A
0x14002ed10  add     rsp, 30h
0x14002ed14  pop     r13
0x14002ed16  pop     rdi
0x14002ed17  pop     rsi
0x14002ed18  pop     rbp
0x14002ed19  pop     rbx
0x14002ed1a  retn
0x14002ed1c  mov     ecx, 3
0x14002ed21  int     29h; Win8: RtlFailFast(ecx)
```
