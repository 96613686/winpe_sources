# XPartCreatePartition

- ea: `0x14002e0bc`
- end: `0x14002e5cc`
- name: `XPartCreatePartition`
- size: `1296`
- prototype: ``
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
- `0x14002d980`
- `0x14002e0bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e26b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e26b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e599`
- `ntoskrnl!ZwClose` at `0x14002e476`
- `ntoskrnl!ZwClose` at `0x14002e476`
- `ntoskrnl!KeSetEvent` at `0x14002e28e`
- `ntoskrnl!KeSetEvent` at `0x14002e574`
- `ntoskrnl!KeSetEvent` at `0x14002e28e`
- `ntoskrnl!KeSetEvent` at `0x14002e574`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1ca`
- `ntoskrnl!KeInitializeEvent` at `0x14002e3a6`
- `ntoskrnl!KeInitializeEvent` at `0x14002e4c7`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1ca`
- `ntoskrnl!KeInitializeEvent` at `0x14002e3a6`
- `ntoskrnl!KeInitializeEvent` at `0x14002e4c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e2ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002e2ab`
- `ntoskrnl!ExAllocatePool2` at `0x14002e115`
- `ntoskrnl!ExAllocatePool2` at `0x14002e2ed`
- `ntoskrnl!ExAllocatePool2` at `0x14002e115`
- `ntoskrnl!ExAllocatePool2` at `0x14002e2ed`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e2bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e2bb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e45c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e45c`
- `ntoskrnl!PsThreadType` at `0x14002e434`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e3d7`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e3d7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e1dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e1dd`

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
  __int64 SendMessage; // rax
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
0x14002e0bc  mov     [rsp-38h+arg_8], rbx
0x14002e0c1  push    rbp
0x14002e0c2  push    rsi
0x14002e0c3  push    rdi
0x14002e0c4  push    r12
0x14002e0c6  push    r13
0x14002e0c8  push    r14
0x14002e0ca  push    r15
0x14002e0cc  mov     rbp, rsp
0x14002e0cf  sub     rsp, 70h
0x14002e0d3  mov     rax, cs:__security_cookie
0x14002e0da  xor     rax, rsp
0x14002e0dd  mov     [rbp+var_10], rax
0x14002e0e1  xor     r13d, r13d
0x14002e0e4  mov     r15, r8
0x14002e0e7  mov     r14, rdx
0x14002e0ea  mov     rdi, rcx
0x14002e0ed  mov     dword ptr [rbp+Object], r13d
0x14002e0f1  mov     [rbp+ThreadHandle], r13
0x14002e0f5  cmp     [rcx], r13w
0x14002e0f9  jnz     short loc_14002E105
0x14002e0fb  mov     edi, 0C000000Dh
0x14002e100  jmp     loc_14002E5A5
0x14002e105  mov     edx, 4F8h
0x14002e10a  mov     ecx, 40h ; '@'
0x14002e10f  mov     r8d, 73756256h
0x14002e115  call    cs:__imp_ExAllocatePool2
0x14002e11c  nop     dword ptr [rax+rax+00h]
0x14002e121  mov     rbx, rax
0x14002e124  test    rax, rax
0x14002e127  jnz     short loc_14002E168
0x14002e129  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e130  lea     rax, WPP_GLOBAL_Control
0x14002e137  cmp     rcx, rax
0x14002e13a  jz      short loc_14002E15E
0x14002e13c  test    dword ptr [rcx+2Ch], 1000000h
0x14002e143  jz      short loc_14002E15E
0x14002e145  cmp     byte ptr [rcx+29h], 2
0x14002e149  jb      short loc_14002E15E
0x14002e14b  mov     rcx, [rcx+18h]
0x14002e14f  lea     edx, [rbx+12h]
0x14002e152  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e159  call    WPP_SF_
0x14002e15e  mov     edi, 0C000009Ah
0x14002e163  jmp     loc_14002E5A5
0x14002e168  mov     qword ptr [rax+0A0h], 1
0x14002e173  lea     rcx, [rbx+108h]; Event
0x14002e17a  mov     [rax+140h], r13b
0x14002e181  xor     r8d, r8d; State
0x14002e184  mov     dword ptr [rax+1A8h], 500000h
0x14002e18e  mov     r12b, r13b
0x14002e191  mov     [rax+1ACh], r13d
0x14002e198  add     rax, 18h
0x14002e19c  lea     edx, [r8+1]; Type
0x14002e1a0  mov     [rax+8], rax
0x14002e1a4  mov     [rax], rax
0x14002e1a7  lea     rax, [rbx+28h]
0x14002e1ab  mov     [rax+8], rax
0x14002e1af  mov     [rax], rax
0x14002e1b2  mov     dword ptr [rbx+0F0h], 1
0x14002e1bc  mov     [rbx+0F8h], r13
0x14002e1c3  mov     [rbx+100h], r13d
0x14002e1ca  call    cs:__imp_KeInitializeEvent
0x14002e1d1  nop     dword ptr [rax+rax+00h]
0x14002e1d6  lea     rcx, [rbx+128h]; SpinLock
0x14002e1dd  call    cs:__imp_KeInitializeSpinLock
0x14002e1e4  nop     dword ptr [rax+rax+00h]
0x14002e1e9  lea     rax, [rbx+130h]
0x14002e1f0  mov     r9, rbx
0x14002e1f3  lea     r8, LowResourcesMessageSent
0x14002e1fa  mov     [rax+8], rax
0x14002e1fe  mov     edx, 0F0h
0x14002e203  mov     [rax], rax
0x14002e206  mov     rcx, rbx
0x14002e209  call    XPartAllocateSendMessage
0x14002e20e  mov     [rbx+3D0h], rax
0x14002e215  test    rax, rax
0x14002e218  jnz     loc_14002E2D0
0x14002e21e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e225  lea     rax, WPP_GLOBAL_Control
0x14002e22c  cmp     rcx, rax
0x14002e22f  jz      short loc_14002E255
0x14002e231  test    dword ptr [rcx+2Ch], 1000000h
0x14002e238  jz      short loc_14002E255
0x14002e23a  cmp     byte ptr [rcx+29h], 2
0x14002e23e  jb      short loc_14002E255
0x14002e240  mov     rcx, [rcx+18h]
0x14002e244  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e24b  mov     edx, 13h
0x14002e250  call    WPP_SF_
0x14002e255  mov     edi, 0C000009Ah
0x14002e25a  mov     rcx, [rbx+98h]; P
0x14002e261  test    rcx, rcx
0x14002e264  jz      short loc_14002E277
0x14002e266  mov     edx, 73756256h; Tag
0x14002e26b  call    cs:__imp_ExFreePoolWithTag
0x14002e272  nop     dword ptr [rax+rax+00h]
0x14002e277  cmp     [rbx+50h], r13
0x14002e27b  jz      loc_14002E562
0x14002e281  lea     rcx, [rbx+58h]; Event
0x14002e285  mov     byte ptr [rbx+70h], 1
0x14002e289  xor     r8d, r8d; Wait
0x14002e28c  xor     edx, edx; Increment
0x14002e28e  call    cs:__imp_KeSetEvent
0x14002e295  nop     dword ptr [rax+rax+00h]
0x14002e29a  mov     rcx, [rbx+50h]; Object
0x14002e29e  xor     r9d, r9d; Alertable
0x14002e2a1  xor     r8d, r8d; WaitMode
0x14002e2a4  mov     [rsp+70h+Timeout], r13; Timeout
0x14002e2a9  xor     edx, edx; WaitReason
0x14002e2ab  call    cs:__imp_KeWaitForSingleObject
0x14002e2b2  nop     dword ptr [rax+rax+00h]
0x14002e2b7  mov     rcx, [rbx+50h]; Object
0x14002e2bb  call    cs:__imp_ObfDereferenceObject
0x14002e2c2  nop     dword ptr [rax+rax+00h]
0x14002e2c7  mov     [rbx+50h], r13
0x14002e2cb  jmp     loc_14002E580
0x14002e2d0  movups  xmm0, xmmword ptr [r14]
0x14002e2d4  lea     rsi, [rbx+80h]
0x14002e2db  mov     ecx, 40h ; '@'
0x14002e2e0  mov     r8d, 73756256h
0x14002e2e6  movdqu  xmmword ptr [rsi], xmm0
0x14002e2ea  movzx   edx, word ptr [rdi]
0x14002e2ed  call    cs:__imp_ExAllocatePool2
0x14002e2f4  nop     dword ptr [rax+rax+00h]
0x14002e2f9  mov     [rbx+98h], rax
0x14002e300  test    rax, rax
0x14002e303  jz      loc_14002E255
0x14002e309  movzx   r8d, word ptr [rdi]; Size
0x14002e30d  mov     rcx, rax; void *
0x14002e310  mov     rdx, [rdi+8]; Src
0x14002e314  call    memmove
0x14002e319  movzx   eax, word ptr [rdi]
0x14002e31c  lea     rcx, [rbp+var_20]
0x14002e320  mov     [rbx+90h], ax
0x14002e327  xorps   xmm0, xmm0
0x14002e32a  movzx   eax, word ptr [rdi+2]
0x14002e32e  mov     [rbx+92h], ax
0x14002e335  movups  [rbp+var_20], xmm0
0x14002e339  call    HviGetHypervisorFeatures
0x14002e33e  mov     rax, 40000000000000h
0x14002e348  test    qword ptr [rbp+var_20], rax
0x14002e34c  jz      short loc_14002E397
0x14002e34e  lea     rdx, [rbp+Object]
0x14002e352  mov     byte ptr [rbx+142h], 1
0x14002e359  lea     rcx, ValueName; ValueName
0x14002e360  call    XPartGetAllowedDevicesWhenIsolatedValue
0x14002e365  test    eax, eax
0x14002e367  js      short loc_14002E376
0x14002e369  cmp     dword ptr [rbp+Object], 1
0x14002e36d  setz    al
0x14002e370  mov     [rbx+143h], al
0x14002e376  lea     rdx, [rbp+Object]
0x14002e37a  lea     rcx, stru_14001C1F8; ValueName
0x14002e381  call    XPartGetAllowedDevicesWhenIsolatedValue
0x14002e386  test    eax, eax
0x14002e388  js      short loc_14002E397
0x14002e38a  cmp     dword ptr [rbp+Object], 1
0x14002e38e  setz    al
0x14002e391  mov     [rbx+144h], al
0x14002e397  xor     r8d, r8d; State
0x14002e39a  mov     [rbx+70h], r13b
0x14002e39e  lea     rcx, [rbx+58h]; Event
0x14002e3a2  lea     edx, [r8+1]; Type
0x14002e3a6  call    cs:__imp_KeInitializeEvent
0x14002e3ad  nop     dword ptr [rax+rax+00h]
0x14002e3b2  lea     rax, XPartReceiveMessageThread
0x14002e3b9  mov     [rsp+70h+StartContext], rbx; StartContext
0x14002e3be  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14002e3c3  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002e3c7  xor     r9d, r9d; ProcessHandle
0x14002e3ca  mov     [rsp+70h+Timeout], r13; ClientId
0x14002e3cf  xor     r8d, r8d; ObjectAttributes
0x14002e3d2  mov     edx, 1FFFFFh; DesiredAccess
0x14002e3d7  call    cs:__imp_PsCreateSystemThread
0x14002e3de  nop     dword ptr [rax+rax+00h]
0x14002e3e3  mov     edi, eax
0x14002e3e5  test    eax, eax
0x14002e3e7  jns     short loc_14002E434
0x14002e3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e3f0  lea     rax, WPP_GLOBAL_Control
0x14002e3f7  cmp     rcx, rax
0x14002e3fa  jz      loc_14002E25A
0x14002e400  test    dword ptr [rcx+2Ch], 1000000h
0x14002e407  jz      loc_14002E25A
0x14002e40d  cmp     byte ptr [rcx+29h], 2
0x14002e411  jb      loc_14002E25A
0x14002e417  mov     edx, 15h
0x14002e41c  mov     rcx, [rcx+18h]
0x14002e420  lea     r8, WPP_fbdbafadf6343d90dc2aa602a7311302_Traceguids
0x14002e427  mov     r9d, edi
0x14002e42a  call    WPP_SF_d
0x14002e42f  jmp     loc_14002E25A
0x14002e434  mov     r8, cs:__imp_PsThreadType
0x14002e43b  lea     rax, [rbp+Object]
0x14002e43f  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e443  xor     r9d, r9d; AccessMode
0x14002e446  mov     [rsp+70h+StartRoutine], r13; HandleInformation
0x14002e44b  xor     edx, edx; DesiredAccess
0x14002e44d  mov     r12b, 1
0x14002e450  mov     [rbp+Object], r13
0x14002e454  mov     r8, [r8]; ObjectType
0x14002e457  mov     [rsp+70h+Timeout], rax; Object
0x14002e45c  call    cs:__imp_ObReferenceObjectByHandle
0x14002e463  nop     dword ptr [rax+rax+00h]
0x14002e468  mov     edi, eax
0x14002e46a  mov     rax, [rbp+Object]
0x14002e46e  mov     [rbx+50h], rax
0x14002e472  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e476  call    cs:__imp_ZwClose
0x14002e47d  nop     dword ptr [rax+rax+00h]
0x14002e482  test    edi, edi
0x14002e484  jns     short loc_14002E4BE
0x14002e486  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e48d  lea     rax, WPP_GLOBAL_Control
0x14002e494  cmp     rcx, rax
0x14002e497  jz      loc_14002E25A
0x14002e49d  test    dword ptr [rcx+2Ch], 1000000h
0x14002e4a4  jz      loc_14002E25A
0x14002e4aa  cmp     byte ptr [rcx+29h], 2
0x14002e4ae  jb      loc_14002E25A
0x14002e4b4  mov     edx, 16h
0x14002e4b9  jmp     loc_14002E41C
0x14002e4be  lea     rcx, [rbx+38h]; Event
0x14002e4c2  xor     r8d, r8d; State
0x14002e4c5  xor     edx, edx; Type
0x14002e4c7  call    cs:__imp_KeInitializeEvent
0x14002e4ce  nop     dword ptr [rax+rax+00h]
0x14002e4d3  mov     rcx, rbx
0x14002e4d6  call    ChInitializePartition
0x14002e4db  mov     edi, eax
0x14002e4dd  test    eax, eax
0x14002e4df  js      loc_14002E25A
0x14002e4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4ec  lea     rax, WPP_GLOBAL_Control
0x14002e4f3  cmp     rcx, rax
0x14002e4f6  jz      short loc_14002E524
0x14002e4f8  test    dword ptr [rcx+2Ch], 10000h
0x14002e4ff  jz      short loc_14002E524
0x14002e501  cmp     byte ptr [rcx+29h], 4
0x14002e505  jb      short loc_14002E524
0x14002e507  mov     rax, cs:qword_1400207A0
0x14002e50e  mov     edx, 17h
0x14002e513  mov     rcx, [rcx+18h]
0x14002e517  mov     r9, rsi
0x14002e51a  mov     [rsp+70h+Timeout], rax
0x14002e51f  call    WPP_SF__guid_q
0x14002e524  mov     rax, cs:WdfFunctions_01033
0x14002e52b  lea     rcx, aOnecoreVmDvVmb_1; "onecore\\vm\\dv\\vmbus\\xpart\\baseclas"...
0x14002e532  mov     rdx, cs:qword_1400207A0
0x14002e539  mov     r9d, 290h
0x14002e53f  mov     [rsp+70h+Timeout], rcx
0x14002e544  xor     r8d, r8d
0x14002e547  mov     rcx, cs:WdfDriverGlobals
0x14002e54e  mov     rax, [rax+668h]
0x14002e555  call    _guard_dispatch_icall
0x14002e55a  mov     [r15], rbx
0x14002e55d  mov     edi, r13d
0x14002e560  jmp     short loc_14002E5A5
0x14002e562  test    r12b, r12b
0x14002e565  jz      short loc_14002E580
0x14002e567  lea     rcx, [rbx+58h]; Event
0x14002e56b  mov     byte ptr [rbx+70h], 1
0x14002e56f  xor     r8d, r8d; Wait
0x14002e572  xor     edx, edx; Increment
0x14002e574  call    cs:__imp_KeSetEvent
0x14002e57b  nop     dword ptr [rax+rax+00h]
0x14002e580  mov     rcx, [rbx+3D0h]
0x14002e587  test    rcx, rcx
0x14002e58a  jz      short loc_14002E591
0x14002e58c  call    XPartFreeSendMessage
0x14002e591  mov     edx, 73756256h; Tag
0x14002e596  mov     rcx, rbx; P
0x14002e599  call    cs:__imp_ExFreePoolWithTag
0x14002e5a0  nop     dword ptr [rax+rax+00h]
0x14002e5a5  mov     eax, edi
0x14002e5a7  mov     rcx, [rbp+var_10]
0x14002e5ab  xor     rcx, rsp; StackCookie
0x14002e5ae  call    __security_check_cookie
0x14002e5b3  mov     rbx, [rsp+70h+arg_8]
0x14002e5bb  add     rsp, 70h
0x14002e5bf  pop     r15
0x14002e5c1  pop     r14
0x14002e5c3  pop     r13
0x14002e5c5  pop     r12
0x14002e5c7  pop     rdi
0x14002e5c8  pop     rsi
0x14002e5c9  pop     rbp
0x14002e5ca  retn
```
