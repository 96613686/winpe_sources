# XPartCreatePartition

- ea: `0x14002e06c`
- end: `0x14002e57c`
- name: `XPartCreatePartition`
- size: `1296`
- prototype: `__int64 __fastcall(const void **, _OWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140013a24`

## callees

- `0x14000389c`
- `0x1400038cc`
- `0x14000c4d0`
- `0x14001240c`
- `0x14001270c`
- `0x140012c20`
- `0x140012c74`
- `0x140017000`
- `0x140017190`
- `0x140017240`
- `0x14002d930`
- `0x14002e06c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e549`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e549`
- `ntoskrnl!ZwClose` at `0x14002e426`
- `ntoskrnl!ZwClose` at `0x14002e426`
- `ntoskrnl!KeSetEvent` at `0x14002e23e`
- `ntoskrnl!KeSetEvent` at `0x14002e524`
- `ntoskrnl!KeSetEvent` at `0x14002e23e`
- `ntoskrnl!KeSetEvent` at `0x14002e524`
- `ntoskrnl!KeInitializeEvent` at `0x14002e17a`
- `ntoskrnl!KeInitializeEvent` at `0x14002e356`
- `ntoskrnl!KeInitializeEvent` at `0x14002e477`
- `ntoskrnl!KeInitializeEvent` at `0x14002e17a`
- `ntoskrnl!KeInitializeEvent` at `0x14002e356`
- `ntoskrnl!KeInitializeEvent` at `0x14002e477`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e25b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e25b`
- `ntoskrnl!ExAllocatePool2` at `0x14002e0c5`
- `ntoskrnl!ExAllocatePool2` at `0x14002e29d`
- `ntoskrnl!ExAllocatePool2` at `0x14002e0c5`
- `ntoskrnl!ExAllocatePool2` at `0x14002e29d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e26b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e26b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e40c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e40c`
- `ntoskrnl!PsThreadType` at `0x14002e3e4`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e387`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e387`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e18d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e18d`

## pseudocode

```c
__int64 __fastcall XPartCreatePartition(const void **a1, _OWORD *a2, __int64 *a3)
{
  NTSTATUS v6; // edi
  __int64 Pool2; // rax
  __int64 StartContext; // rbx
  struct _KEVENT *v9; // rcx
  char v10; // r12
  _QWORD *v11; // rax
  _QWORD *SendMessage; // rax
  void *v13; // rcx
  void *v14; // rax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  PVOID Object; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-28h] BYREF
  __int128 v21; // [rsp+50h] [rbp-20h] BYREF

  LODWORD(Object) = 0;
  ThreadHandle = 0;
  if ( !*(_WORD *)a1 )
    return (unsigned int)-1073741811;
  Pool2 = ExAllocatePool2(64, 1272, 1937072726);
  StartContext = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids);
    }
    return (unsigned int)-1073741670;
  }
  *(_QWORD *)(Pool2 + 160) = 1;
  v9 = (struct _KEVENT *)(Pool2 + 264);
  *(_BYTE *)(Pool2 + 320) = 0;
  *(_DWORD *)(Pool2 + 424) = 5242880;
  v10 = 0;
  *(_DWORD *)(Pool2 + 428) = 0;
  v11 = (_QWORD *)(Pool2 + 24);
  v11[1] = v11;
  *v11 = v11;
  *(_QWORD *)(StartContext + 48) = StartContext + 40;
  *(_QWORD *)(StartContext + 40) = StartContext + 40;
  *(_DWORD *)(StartContext + 240) = 1;
  *(_QWORD *)(StartContext + 248) = 0;
  *(_DWORD *)(StartContext + 256) = 0;
  KeInitializeEvent(v9, SynchronizationEvent, 0);
  KeInitializeSpinLock((PKSPIN_LOCK)(StartContext + 296));
  *(_QWORD *)(StartContext + 312) = StartContext + 304;
  *(_QWORD *)(StartContext + 304) = StartContext + 304;
  SendMessage = XPartAllocateSendMessage(StartContext, 240, LowResourcesMessageSent, StartContext);
  *(_QWORD *)(StartContext + 976) = SendMessage;
  if ( !SendMessage )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids);
    }
    goto LABEL_14;
  }
  *(_OWORD *)(StartContext + 128) = *a2;
  v14 = (void *)ExAllocatePool2(64, *(unsigned __int16 *)a1, 1937072726);
  *(_QWORD *)(StartContext + 152) = v14;
  if ( !v14 )
  {
LABEL_14:
    v6 = -1073741670;
LABEL_15:
    v13 = *(void **)(StartContext + 152);
    if ( v13 )
      ExFreePoolWithTag(v13, 0x73756256u);
    if ( *(_QWORD *)(StartContext + 80) )
    {
      *(_BYTE *)(StartContext + 112) = 1;
      KeSetEvent((PRKEVENT)(StartContext + 88), 0, 0);
      KeWaitForSingleObject(*(PVOID *)(StartContext + 80), Executive, 0, 0, 0);
      ObfDereferenceObject(*(PVOID *)(StartContext + 80));
      *(_QWORD *)(StartContext + 80) = 0;
    }
    else if ( v10 )
    {
      *(_BYTE *)(StartContext + 112) = 1;
      KeSetEvent((PRKEVENT)(StartContext + 88), 0, 0);
    }
    if ( *(_QWORD *)(StartContext + 976) )
      XPartFreeSendMessage();
    ExFreePoolWithTag((PVOID)StartContext, 0x73756256u);
    return (unsigned int)v6;
  }
  memmove(v14, a1[1], *(unsigned __int16 *)a1);
  *(_WORD *)(StartContext + 144) = *(_WORD *)a1;
  *(_WORD *)(StartContext + 146) = *((_WORD *)a1 + 1);
  v21 = 0;
  HviGetHypervisorFeatures(&v21);
  if ( (v21 & 0x40000000000000LL) != 0 )
  {
    *(_BYTE *)(StartContext + 322) = 1;
    if ( (int)XPartGetAllowedDevicesWhenIsolatedValue(&ValueName) >= 0 )
      *(_BYTE *)(StartContext + 323) = (_DWORD)Object == 1;
    if ( (int)XPartGetAllowedDevicesWhenIsolatedValue(&stru_14001C1F8) >= 0 )
      *(_BYTE *)(StartContext + 324) = (_DWORD)Object == 1;
  }
  *(_BYTE *)(StartContext + 112) = 0;
  KeInitializeEvent((PRKEVENT)(StartContext + 88), SynchronizationEvent, 0);
  v6 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         0,
         0,
         0,
         (PKSTART_ROUTINE)XPartReceiveMessageThread,
         (PVOID)StartContext);
  if ( v6 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_15;
    }
    v16 = 21;
    goto LABEL_30;
  }
  v10 = 1;
  Object = 0;
  v6 = ObReferenceObjectByHandle(ThreadHandle, 0, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
  *(_QWORD *)(StartContext + 80) = Object;
  ZwClose(ThreadHandle);
  if ( v6 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_15;
    }
    v16 = 22;
LABEL_30:
    WPP_SF_d(v15->AttachedDevice, v16, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids, (unsigned int)v6);
    goto LABEL_15;
  }
  KeInitializeEvent((PRKEVENT)(StartContext + 56), NotificationEvent, 0);
  v6 = ChInitializePartition(StartContext);
  if ( v6 < 0 )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF__guid_q(WPP_GLOBAL_Control->AttachedDevice, 23, v17, StartContext + 128, qword_1400207A0);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01033 + 1640))(
    WdfDriverGlobals,
    qword_1400207A0,
    0,
    656,
    "onecore\\vm\\dv\\vmbus\\xpart\\baseclass.c");
  *a3 = StartContext;
  return 0;
}

```

## disassembly

```asm
0x14002e06c  mov     [rsp-38h+arg_8], rbx
0x14002e071  push    rbp
0x14002e072  push    rsi
0x14002e073  push    rdi
0x14002e074  push    r12
0x14002e076  push    r13
0x14002e078  push    r14
0x14002e07a  push    r15
0x14002e07c  mov     rbp, rsp
0x14002e07f  sub     rsp, 70h
0x14002e083  mov     rax, cs:__security_cookie
0x14002e08a  xor     rax, rsp
0x14002e08d  mov     [rbp+var_10], rax
0x14002e091  xor     r13d, r13d
0x14002e094  mov     r15, r8
0x14002e097  mov     r14, rdx
0x14002e09a  mov     rdi, rcx
0x14002e09d  mov     dword ptr [rbp+Object], r13d
0x14002e0a1  mov     [rbp+ThreadHandle], r13
0x14002e0a5  cmp     [rcx], r13w
0x14002e0a9  jnz     short loc_14002E0B5
0x14002e0ab  mov     edi, 0C000000Dh
0x14002e0b0  jmp     loc_14002E555
0x14002e0b5  mov     edx, 4F8h
0x14002e0ba  mov     ecx, 40h ; '@'
0x14002e0bf  mov     r8d, 73756256h
0x14002e0c5  call    cs:__imp_ExAllocatePool2
0x14002e0cc  nop     dword ptr [rax+rax+00h]
0x14002e0d1  mov     rbx, rax
0x14002e0d4  test    rax, rax
0x14002e0d7  jnz     short loc_14002E118
0x14002e0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0e0  lea     rax, WPP_GLOBAL_Control
0x14002e0e7  cmp     rcx, rax
0x14002e0ea  jz      short loc_14002E10E
0x14002e0ec  test    dword ptr [rcx+2Ch], 1000000h
0x14002e0f3  jz      short loc_14002E10E
0x14002e0f5  cmp     byte ptr [rcx+29h], 2
0x14002e0f9  jb      short loc_14002E10E
0x14002e0fb  mov     rcx, [rcx+18h]
0x14002e0ff  lea     edx, [rbx+12h]
0x14002e102  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e109  call    WPP_SF_
0x14002e10e  mov     edi, 0C000009Ah
0x14002e113  jmp     loc_14002E555
0x14002e118  mov     qword ptr [rax+0A0h], 1
0x14002e123  lea     rcx, [rbx+108h]; Event
0x14002e12a  mov     [rax+140h], r13b
0x14002e131  xor     r8d, r8d; State
0x14002e134  mov     dword ptr [rax+1A8h], 500000h
0x14002e13e  mov     r12b, r13b
0x14002e141  mov     [rax+1ACh], r13d
0x14002e148  add     rax, 18h
0x14002e14c  lea     edx, [r8+1]; Type
0x14002e150  mov     [rax+8], rax
0x14002e154  mov     [rax], rax
0x14002e157  lea     rax, [rbx+28h]
0x14002e15b  mov     [rax+8], rax
0x14002e15f  mov     [rax], rax
0x14002e162  mov     dword ptr [rbx+0F0h], 1
0x14002e16c  mov     [rbx+0F8h], r13
0x14002e173  mov     [rbx+100h], r13d
0x14002e17a  call    cs:__imp_KeInitializeEvent
0x14002e181  nop     dword ptr [rax+rax+00h]
0x14002e186  lea     rcx, [rbx+128h]; SpinLock
0x14002e18d  call    cs:__imp_KeInitializeSpinLock
0x14002e194  nop     dword ptr [rax+rax+00h]
0x14002e199  lea     rax, [rbx+130h]
0x14002e1a0  mov     r9, rbx
0x14002e1a3  lea     r8, LowResourcesMessageSent
0x14002e1aa  mov     [rax+8], rax
0x14002e1ae  mov     edx, 0F0h
0x14002e1b3  mov     [rax], rax
0x14002e1b6  mov     rcx, rbx
0x14002e1b9  call    XPartAllocateSendMessage
0x14002e1be  mov     [rbx+3D0h], rax
0x14002e1c5  test    rax, rax
0x14002e1c8  jnz     loc_14002E280
0x14002e1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1d5  lea     rax, WPP_GLOBAL_Control
0x14002e1dc  cmp     rcx, rax
0x14002e1df  jz      short loc_14002E205
0x14002e1e1  test    dword ptr [rcx+2Ch], 1000000h
0x14002e1e8  jz      short loc_14002E205
0x14002e1ea  cmp     byte ptr [rcx+29h], 2
0x14002e1ee  jb      short loc_14002E205
0x14002e1f0  mov     rcx, [rcx+18h]
0x14002e1f4  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e1fb  mov     edx, 13h
0x14002e200  call    WPP_SF_
0x14002e205  mov     edi, 0C000009Ah
0x14002e20a  mov     rcx, [rbx+98h]; P
0x14002e211  test    rcx, rcx
0x14002e214  jz      short loc_14002E227
0x14002e216  mov     edx, 73756256h; Tag
0x14002e21b  call    cs:__imp_ExFreePoolWithTag
0x14002e222  nop     dword ptr [rax+rax+00h]
0x14002e227  cmp     [rbx+50h], r13
0x14002e22b  jz      loc_14002E512
0x14002e231  lea     rcx, [rbx+58h]; Event
0x14002e235  mov     byte ptr [rbx+70h], 1
0x14002e239  xor     r8d, r8d; Wait
0x14002e23c  xor     edx, edx; Increment
0x14002e23e  call    cs:__imp_KeSetEvent
0x14002e245  nop     dword ptr [rax+rax+00h]
0x14002e24a  mov     rcx, [rbx+50h]; Object
0x14002e24e  xor     r9d, r9d; Alertable
0x14002e251  xor     r8d, r8d; WaitMode
0x14002e254  mov     [rsp+70h+Timeout], r13; Timeout
0x14002e259  xor     edx, edx; WaitReason
0x14002e25b  call    cs:__imp_KeWaitForSingleObject
0x14002e262  nop     dword ptr [rax+rax+00h]
0x14002e267  mov     rcx, [rbx+50h]; Object
0x14002e26b  call    cs:__imp_ObfDereferenceObject
0x14002e272  nop     dword ptr [rax+rax+00h]
0x14002e277  mov     [rbx+50h], r13
0x14002e27b  jmp     loc_14002E530
0x14002e280  movups  xmm0, xmmword ptr [r14]
0x14002e284  lea     rsi, [rbx+80h]
0x14002e28b  mov     ecx, 40h ; '@'
0x14002e290  mov     r8d, 73756256h
0x14002e296  movdqu  xmmword ptr [rsi], xmm0
0x14002e29a  movzx   edx, word ptr [rdi]
0x14002e29d  call    cs:__imp_ExAllocatePool2
0x14002e2a4  nop     dword ptr [rax+rax+00h]
0x14002e2a9  mov     [rbx+98h], rax
0x14002e2b0  test    rax, rax
0x14002e2b3  jz      loc_14002E205
0x14002e2b9  movzx   r8d, word ptr [rdi]; Size
0x14002e2bd  mov     rcx, rax; void *
0x14002e2c0  mov     rdx, [rdi+8]; Src
0x14002e2c4  call    memmove
0x14002e2c9  movzx   eax, word ptr [rdi]
0x14002e2cc  lea     rcx, [rbp+var_20]
0x14002e2d0  mov     [rbx+90h], ax
0x14002e2d7  xorps   xmm0, xmm0
0x14002e2da  movzx   eax, word ptr [rdi+2]
0x14002e2de  mov     [rbx+92h], ax
0x14002e2e5  movups  [rbp+var_20], xmm0
0x14002e2e9  call    HviGetHypervisorFeatures
0x14002e2ee  mov     rax, 40000000000000h
0x14002e2f8  test    qword ptr [rbp+var_20], rax
0x14002e2fc  jz      short loc_14002E347
0x14002e2fe  lea     rdx, [rbp+Object]
0x14002e302  mov     byte ptr [rbx+142h], 1
0x14002e309  lea     rcx, ValueName; ValueName
0x14002e310  call    XPartGetAllowedDevicesWhenIsolatedValue
0x14002e315  test    eax, eax
0x14002e317  js      short loc_14002E326
0x14002e319  cmp     dword ptr [rbp+Object], 1
0x14002e31d  setz    al
0x14002e320  mov     [rbx+143h], al
0x14002e326  lea     rdx, [rbp+Object]
0x14002e32a  lea     rcx, stru_14001C1F8; ValueName
0x14002e331  call    XPartGetAllowedDevicesWhenIsolatedValue
0x14002e336  test    eax, eax
0x14002e338  js      short loc_14002E347
0x14002e33a  cmp     dword ptr [rbp+Object], 1
0x14002e33e  setz    al
0x14002e341  mov     [rbx+144h], al
0x14002e347  xor     r8d, r8d; State
0x14002e34a  mov     [rbx+70h], r13b
0x14002e34e  lea     rcx, [rbx+58h]; Event
0x14002e352  lea     edx, [r8+1]; Type
0x14002e356  call    cs:__imp_KeInitializeEvent
0x14002e35d  nop     dword ptr [rax+rax+00h]
0x14002e362  lea     rax, XPartReceiveMessageThread
0x14002e369  mov     [rsp+70h+StartContext], rbx; StartContext
0x14002e36e  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14002e373  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002e377  xor     r9d, r9d; ProcessHandle
0x14002e37a  mov     [rsp+70h+Timeout], r13; ClientId
0x14002e37f  xor     r8d, r8d; ObjectAttributes
0x14002e382  mov     edx, 1FFFFFh; DesiredAccess
0x14002e387  call    cs:__imp_PsCreateSystemThread
0x14002e38e  nop     dword ptr [rax+rax+00h]
0x14002e393  mov     edi, eax
0x14002e395  test    eax, eax
0x14002e397  jns     short loc_14002E3E4
0x14002e399  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e3a0  lea     rax, WPP_GLOBAL_Control
0x14002e3a7  cmp     rcx, rax
0x14002e3aa  jz      loc_14002E20A
0x14002e3b0  test    dword ptr [rcx+2Ch], 1000000h
0x14002e3b7  jz      loc_14002E20A
0x14002e3bd  cmp     byte ptr [rcx+29h], 2
0x14002e3c1  jb      loc_14002E20A
0x14002e3c7  mov     edx, 15h
0x14002e3cc  mov     rcx, [rcx+18h]
0x14002e3d0  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e3d7  mov     r9d, edi
0x14002e3da  call    WPP_SF_d
0x14002e3df  jmp     loc_14002E20A
0x14002e3e4  mov     r8, cs:__imp_PsThreadType
0x14002e3eb  lea     rax, [rbp+Object]
0x14002e3ef  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e3f3  xor     r9d, r9d; AccessMode
0x14002e3f6  mov     [rsp+70h+StartRoutine], r13; HandleInformation
0x14002e3fb  xor     edx, edx; DesiredAccess
0x14002e3fd  mov     r12b, 1
0x14002e400  mov     [rbp+Object], r13
0x14002e404  mov     r8, [r8]; ObjectType
0x14002e407  mov     [rsp+70h+Timeout], rax; Object
0x14002e40c  call    cs:__imp_ObReferenceObjectByHandle
0x14002e413  nop     dword ptr [rax+rax+00h]
0x14002e418  mov     edi, eax
0x14002e41a  mov     rax, [rbp+Object]
0x14002e41e  mov     [rbx+50h], rax
0x14002e422  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e426  call    cs:__imp_ZwClose
0x14002e42d  nop     dword ptr [rax+rax+00h]
0x14002e432  test    edi, edi
0x14002e434  jns     short loc_14002E46E
0x14002e436  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e43d  lea     rax, WPP_GLOBAL_Control
0x14002e444  cmp     rcx, rax
0x14002e447  jz      loc_14002E20A
0x14002e44d  test    dword ptr [rcx+2Ch], 1000000h
0x14002e454  jz      loc_14002E20A
0x14002e45a  cmp     byte ptr [rcx+29h], 2
0x14002e45e  jb      loc_14002E20A
0x14002e464  mov     edx, 16h
0x14002e469  jmp     loc_14002E3CC
0x14002e46e  lea     rcx, [rbx+38h]; Event
0x14002e472  xor     r8d, r8d; State
0x14002e475  xor     edx, edx; Type
0x14002e477  call    cs:__imp_KeInitializeEvent
0x14002e47e  nop     dword ptr [rax+rax+00h]
0x14002e483  mov     rcx, rbx
0x14002e486  call    ChInitializePartition
0x14002e48b  mov     edi, eax
0x14002e48d  test    eax, eax
0x14002e48f  js      loc_14002E20A
0x14002e495  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e49c  lea     rax, WPP_GLOBAL_Control
0x14002e4a3  cmp     rcx, rax
0x14002e4a6  jz      short loc_14002E4D4
0x14002e4a8  test    dword ptr [rcx+2Ch], 10000h
0x14002e4af  jz      short loc_14002E4D4
0x14002e4b1  cmp     byte ptr [rcx+29h], 4
0x14002e4b5  jb      short loc_14002E4D4
0x14002e4b7  mov     rax, cs:qword_1400207A0
0x14002e4be  mov     edx, 17h
0x14002e4c3  mov     rcx, [rcx+18h]
0x14002e4c7  mov     r9, rsi
0x14002e4ca  mov     [rsp+70h+Timeout], rax
0x14002e4cf  call    WPP_SF__guid_q
0x14002e4d4  mov     rax, cs:WdfFunctions_01033
0x14002e4db  lea     rcx, aOnecoreVmDvVmb_1; "onecore\\vm\\dv\\vmbus\\xpart\\baseclas"...
0x14002e4e2  mov     rdx, cs:qword_1400207A0
0x14002e4e9  mov     r9d, 290h
0x14002e4ef  mov     [rsp+70h+Timeout], rcx
0x14002e4f4  xor     r8d, r8d
0x14002e4f7  mov     rcx, cs:WdfDriverGlobals
0x14002e4fe  mov     rax, [rax+668h]
0x14002e505  call    _guard_dispatch_icall
0x14002e50a  mov     [r15], rbx
0x14002e50d  mov     edi, r13d
0x14002e510  jmp     short loc_14002E555
0x14002e512  test    r12b, r12b
0x14002e515  jz      short loc_14002E530
0x14002e517  lea     rcx, [rbx+58h]; Event
0x14002e51b  mov     byte ptr [rbx+70h], 1
0x14002e51f  xor     r8d, r8d; Wait
0x14002e522  xor     edx, edx; Increment
0x14002e524  call    cs:__imp_KeSetEvent
0x14002e52b  nop     dword ptr [rax+rax+00h]
0x14002e530  mov     rcx, [rbx+3D0h]
0x14002e537  test    rcx, rcx
0x14002e53a  jz      short loc_14002E541
0x14002e53c  call    XPartFreeSendMessage
0x14002e541  mov     edx, 73756256h; Tag
0x14002e546  mov     rcx, rbx; P
0x14002e549  call    cs:__imp_ExFreePoolWithTag
0x14002e550  nop     dword ptr [rax+rax+00h]
0x14002e555  mov     eax, edi
0x14002e557  mov     rcx, [rbp+var_10]
0x14002e55b  xor     rcx, rsp; StackCookie
0x14002e55e  call    __security_check_cookie
0x14002e563  mov     rbx, [rsp+70h+arg_8]
0x14002e56b  add     rsp, 70h
0x14002e56f  pop     r15
0x14002e571  pop     r14
0x14002e573  pop     r13
0x14002e575  pop     r12
0x14002e577  pop     rdi
0x14002e578  pop     rsi
0x14002e579  pop     rbp
0x14002e57a  retn
```
