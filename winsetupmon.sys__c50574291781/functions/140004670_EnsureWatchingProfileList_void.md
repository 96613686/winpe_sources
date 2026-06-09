# EnsureWatchingProfileList(void)

- ea: `0x140004670`
- end: `0x140004902`
- name: `?EnsureWatchingProfileList@@YAJXZ`
- size: `658`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005544`

## callees

- `0x140003944`
- `0x140004670`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!PsIsSystemThread` at `0x1400046c7`
- `ntoskrnl!PsIsSystemThread` at `0x1400046c7`
- `ntoskrnl!PsCreateSystemThread` at `0x140004746`
- `ntoskrnl!PsCreateSystemThread` at `0x140004746`
- `ntoskrnl!PsThreadType` at `0x140004771`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400047ea`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400047ea`
- `ntoskrnl!ZwClose` at `0x1400048c3`
- `ntoskrnl!ZwClose` at `0x1400048c3`
- `ntoskrnl!KeClearEvent` at `0x140004849`
- `ntoskrnl!KeClearEvent` at `0x14000485c`
- `ntoskrnl!KeClearEvent` at `0x140004849`
- `ntoskrnl!KeClearEvent` at `0x14000485c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004799`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004799`
- `ntoskrnl!ObfDereferenceObject` at `0x1400048ae`
- `ntoskrnl!ObfDereferenceObject` at `0x1400048ae`
- `ntoskrnl!KeInitializeEvent` at `0x1400046e8`
- `ntoskrnl!KeInitializeEvent` at `0x140004700`
- `ntoskrnl!KeInitializeEvent` at `0x1400046e8`
- `ntoskrnl!KeInitializeEvent` at `0x140004700`
- `FLTMGR!FltReleasePushLockEx` at `0x140004892`
- `FLTMGR!FltReleasePushLockEx` at `0x1400048dd`
- `FLTMGR!FltReleasePushLockEx` at `0x140004892`
- `FLTMGR!FltReleasePushLockEx` at `0x1400048dd`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000469f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000469f`

## string_xrefs

- `0x140004758`: `Could not create profile list thread (0x%08X)`
- `0x1400047ab`: `Could not reference thread object by handle (0x%08X)`
- `0x14000482a`: `Unexpected exit from profile list watch thread: 0x%08X`

## pseudocode

```c
__int64 EnsureWatchingProfileList(void)
{
  char v0; // di
  NTSTATUS v1; // eax
  int v2; // ebx
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  PVOID v6[2]; // [rsp+40h] [rbp-10h] BYREF
  void *ThreadHandle; // [rsp+70h] [rbp+20h] BYREF
  PVOID Object; // [rsp+78h] [rbp+28h] BYREF

  ThreadHandle = 0;
  Object = 0;
  FltAcquirePushLockExclusiveEx(&qword_1400193B0, 0);
  v0 = 1;
  if ( Handle )
  {
    v2 = 0;
  }
  else
  {
    byte_1400193B8 = PsIsSystemThread(KeGetCurrentThread());
    KeInitializeEvent(&Event, NotificationEvent, 0);
    KeInitializeEvent(&stru_1400193D8, NotificationEvent, 0);
    dword_1400193F0 = 0;
    v1 = PsCreateSystemThread(
           &ThreadHandle,
           0x1FFFFFu,
           0,
           0,
           0,
           (PKSTART_ROUTINE)ProfileListWatchRoutine,
           &byte_1400193B8);
    v2 = v1;
    if ( v1 < 0 )
    {
      WriteLogMessage(3, L"Could not create profile list thread (0x%08X)", (unsigned int)v1);
      goto LABEL_14;
    }
    v3 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
    v2 = v3;
    if ( v3 < 0 )
    {
      WriteLogMessage(3, L"Could not reference thread object by handle (0x%08X)", (unsigned int)v3);
LABEL_14:
      KeClearEvent(&stru_1400193D8);
      KeClearEvent(&Event);
      memset(&byte_1400193B8, 0, 0x40u);
      goto LABEL_17;
    }
    v6[0] = &Event;
    v6[1] = Object;
    v4 = KeWaitForMultipleObjects(2u, v6, WaitAny, Executive, 0, 0, 0, 0);
    v2 = v4;
    if ( v4 < 0 )
    {
      WriteLogMessage(3, L"Could not wait for multiple events notification (0x%08X)", (unsigned int)v4);
      goto LABEL_14;
    }
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        v2 = dword_1400193F0;
        WriteLogMessage(3, L"Unexpected exit from profile list watch thread: 0x%08X", (unsigned int)dword_1400193F0);
        if ( v2 < 0 )
          goto LABEL_14;
      }
      else
      {
        WriteLogMessage(3, L"Unexpected wait status; exiting (0x%08X)", (unsigned int)v4);
      }
      v2 = -1073741823;
      goto LABEL_14;
    }
    v2 = 0;
    Handle = ThreadHandle;
    ThreadHandle = 0;
    FltReleasePushLockEx(&qword_1400193B0, 0);
    v0 = 0;
  }
LABEL_17:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  if ( v0 )
    FltReleasePushLockEx(&qword_1400193B0, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140004670  mov     [rsp-18h+arg_10], rbx
0x140004675  mov     [rsp-18h+arg_18], rdi
0x14000467a  push    rbp
0x14000467b  push    r13
0x14000467d  push    r15
0x14000467f  mov     rbp, rsp
0x140004682  sub     rsp, 50h
0x140004686  xor     edx, edx
0x140004688  mov     [rbp+ThreadHandle], 0
0x140004690  lea     rcx, qword_1400193B0
0x140004697  mov     [rbp+Object], 0
0x14000469f  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400046a6  nop     dword ptr [rax+rax+00h]
0x1400046ab  cmp     cs:Handle, 0
0x1400046b3  mov     edi, 1
0x1400046b8  jnz     loc_1400048A3
0x1400046be  mov     rcx, gs:188h; Thread
0x1400046c7  call    cs:__imp_PsIsSystemThread
0x1400046ce  nop     dword ptr [rax+rax+00h]
0x1400046d3  lea     r15, Event
0x1400046da  xor     r8d, r8d; State
0x1400046dd  mov     rcx, r15; Event
0x1400046e0  mov     cs:byte_1400193B8, al
0x1400046e6  xor     edx, edx; Type
0x1400046e8  call    cs:__imp_KeInitializeEvent
0x1400046ef  nop     dword ptr [rax+rax+00h]
0x1400046f4  xor     r8d, r8d; State
0x1400046f7  lea     rcx, stru_1400193D8; Event
0x1400046fe  xor     edx, edx; Type
0x140004700  call    cs:__imp_KeInitializeEvent
0x140004707  nop     dword ptr [rax+rax+00h]
0x14000470c  lea     rax, ?ProfileListWatchRoutine@@YAXPEAX@Z; ProfileListWatchRoutine(void *)
0x140004713  mov     cs:dword_1400193F0, 0
0x14000471d  lea     r13, byte_1400193B8
0x140004724  xor     r9d, r9d; ProcessHandle
0x140004727  mov     [rsp+50h+StartContext], r13; StartContext
0x14000472c  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140004730  mov     [rsp+50h+StartRoutine], rax; StartRoutine
0x140004735  xor     r8d, r8d; ObjectAttributes
0x140004738  mov     edx, 1FFFFFh; DesiredAccess
0x14000473d  mov     [rsp+50h+ClientId], 0; ClientId
0x140004746  call    cs:__imp_PsCreateSystemThread
0x14000474d  nop     dword ptr [rax+rax+00h]
0x140004752  mov     ebx, eax
0x140004754  test    eax, eax
0x140004756  jns     short loc_140004771
0x140004758  lea     rdx, aCouldNotCreate_0; "Could not create profile list thread (0"...
0x14000475f  mov     r8d, eax
0x140004762  mov     ecx, 3
0x140004767  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000476c  jmp     loc_140004842
0x140004771  mov     r8, cs:__imp_PsThreadType
0x140004778  lea     rax, [rbp+Object]
0x14000477c  mov     rcx, [rbp+ThreadHandle]; Handle
0x140004780  xor     r9d, r9d; AccessMode
0x140004783  mov     [rsp+50h+StartRoutine], 0; HandleInformation
0x14000478c  mov     edx, 1FFFFFh; DesiredAccess
0x140004791  mov     [rsp+50h+ClientId], rax; Object
0x140004796  mov     r8, [r8]; ObjectType
0x140004799  call    cs:__imp_ObReferenceObjectByHandle
0x1400047a0  nop     dword ptr [rax+rax+00h]
0x1400047a5  mov     ebx, eax
0x1400047a7  test    eax, eax
0x1400047a9  jns     short loc_1400047B4
0x1400047ab  lea     rdx, aCouldNotRefere; "Could not reference thread object by ha"...
0x1400047b2  jmp     short loc_14000475F
0x1400047b4  mov     rax, [rbp+Object]
0x1400047b8  lea     rdx, [rbp+var_10]; Object
0x1400047bc  mov     [rsp+50h+WaitBlockArray], 0; WaitBlockArray
0x1400047c5  xor     r9d, r9d; WaitReason
0x1400047c8  mov     [rsp+50h+StartContext], 0; Timeout
0x1400047d1  mov     r8d, edi; WaitType
0x1400047d4  mov     byte ptr [rsp+50h+StartRoutine], 0; Alertable
0x1400047d9  mov     [rbp+var_10], r15
0x1400047dd  lea     ecx, [r9+2]; Count
0x1400047e1  mov     [rbp+var_8], rax
0x1400047e5  mov     byte ptr [rsp+50h+ClientId], 0; WaitMode
0x1400047ea  call    cs:__imp_KeWaitForMultipleObjects
0x1400047f1  nop     dword ptr [rax+rax+00h]
0x1400047f6  mov     ebx, eax
0x1400047f8  test    eax, eax
0x1400047fa  jns     short loc_140004808
0x1400047fc  lea     rdx, aCouldNotWaitFo; "Could not wait for multiple events noti"...
0x140004803  jmp     loc_14000475F
0x140004808  jz      short loc_140004878
0x14000480a  mov     ecx, 3
0x14000480f  cmp     eax, edi
0x140004811  jz      short loc_140004824
0x140004813  mov     r8d, eax
0x140004816  lea     rdx, aUnexpectedWait; "Unexpected wait status; exiting (0x%08X"...
0x14000481d  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004822  jmp     short loc_14000483D
0x140004824  mov     ebx, cs:dword_1400193F0
0x14000482a  lea     rdx, aUnexpectedExit; "Unexpected exit from profile list watch"...
0x140004831  mov     r8d, ebx
0x140004834  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004839  test    ebx, ebx
0x14000483b  js      short loc_140004842
0x14000483d  mov     ebx, 0C0000001h
0x140004842  lea     rcx, stru_1400193D8; Event
0x140004849  call    cs:__imp_KeClearEvent
0x140004850  nop     dword ptr [rax+rax+00h]
0x140004855  lea     rcx, Event; Event
0x14000485c  call    cs:__imp_KeClearEvent
0x140004863  nop     dword ptr [rax+rax+00h]
0x140004868  xor     edx, edx; Val
0x14000486a  mov     rcx, r13; void *
0x14000486d  lea     r8d, [rdx+40h]; Size
0x140004871  call    memset
0x140004876  jmp     short loc_1400048A5
0x140004878  mov     rax, [rbp+ThreadHandle]
0x14000487c  lea     rcx, qword_1400193B0
0x140004883  xor     ebx, ebx
0x140004885  mov     cs:Handle, rax
0x14000488c  xor     edx, edx
0x14000488e  mov     [rbp+ThreadHandle], rbx
0x140004892  call    cs:__imp_FltReleasePushLockEx
0x140004899  nop     dword ptr [rax+rax+00h]
0x14000489e  xor     dil, dil
0x1400048a1  jmp     short loc_1400048A5
0x1400048a3  xor     ebx, ebx
0x1400048a5  mov     rcx, [rbp+Object]; Object
0x1400048a9  test    rcx, rcx
0x1400048ac  jz      short loc_1400048BA
0x1400048ae  call    cs:__imp_ObfDereferenceObject
0x1400048b5  nop     dword ptr [rax+rax+00h]
0x1400048ba  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400048be  test    rcx, rcx
0x1400048c1  jz      short loc_1400048CF
0x1400048c3  call    cs:__imp_ZwClose
0x1400048ca  nop     dword ptr [rax+rax+00h]
0x1400048cf  test    dil, dil
0x1400048d2  jz      short loc_1400048E9
0x1400048d4  xor     edx, edx
0x1400048d6  lea     rcx, qword_1400193B0
0x1400048dd  call    cs:__imp_FltReleasePushLockEx
0x1400048e4  nop     dword ptr [rax+rax+00h]
0x1400048e9  lea     r11, [rsp+50h+var_s0]
0x1400048ee  mov     eax, ebx
0x1400048f0  mov     rbx, [r11+30h]
0x1400048f4  mov     rdi, [r11+38h]
0x1400048f8  mov     rsp, r11
0x1400048fb  pop     r15
0x1400048fd  pop     r13
0x1400048ff  pop     rbp
0x140004900  retn
```
