# VmsQsMgmtInitializeDeferredQueue

- ea: `0x1401b095c`
- end: `0x1401b0ae4`
- name: `VmsQsMgmtInitializeDeferredQueue`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1401adc74`

## callees

- `0x14003a450`
- `0x1401b095c`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x1401b0a41`
- `ntoskrnl!PsCreateSystemThread` at `0x1401b0a41`
- `ntoskrnl!InitializeSListHead` at `0x1401b099c`
- `ntoskrnl!InitializeSListHead` at `0x1401b099c`
- `ntoskrnl!KeInitializeEvent` at `0x1401b09b6`
- `ntoskrnl!KeInitializeEvent` at `0x1401b09b6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401b0a00`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401b0a00`
- `ntoskrnl!ZwClose` at `0x1401b0ac6`
- `ntoskrnl!ZwClose` at `0x1401b0ac6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b0aa9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401b0aa9`

## pseudocode

```c
__int64 VmsQsMgmtInitializeDeferredQueue()
{
  NTSTATUS v0; // eax
  int v1; // edx
  unsigned int v2; // ebx
  void *ThreadHandle; // [rsp+50h] [rbp+8h] BYREF
  PVOID Object; // [rsp+58h] [rbp+10h] BYREF

  ThreadHandle = 0;
  byte_1401FA8C1 = 0;
  byte_1401FA8C0 = 0;
  byte_1401F98F9 = 0;
  dword_1401F9948 = 0;
  qword_1401FA020 = 0;
  InitializeSListHead(&SListHead);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  memset(&Lookaside, 0, sizeof(Lookaside));
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x50u, 0x77446D56u, 0);
  byte_1401FA8C0 = 1;
  v0 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, VmsQsMgmtDeferredWorkerThread, 0);
  v2 = v0;
  if ( v0 >= 0 )
  {
    Object = 0;
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    qword_1401FA020 = Object;
    ZwClose(ThreadHandle);
    v2 = 0;
    byte_1401FA8C1 = 1;
  }
  else
  {
    LOBYTE(v1) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v1, 20, 38, (__int64)WPP_9967daa17f81308e3174d8235558202a_Traceguids, v0);
  }
  return v2;
}

```

## disassembly

```asm
0x1401b095c  push    rbx
0x1401b095e  sub     rsp, 40h
0x1401b0962  lea     rcx, SListHead; SListHead
0x1401b0969  mov     [rsp+48h+ThreadHandle], 0
0x1401b0972  mov     cs:byte_1401FA8C1, 0
0x1401b0979  mov     cs:byte_1401FA8C0, 0
0x1401b0980  mov     cs:byte_1401F98F9, 0
0x1401b0987  mov     cs:dword_1401F9948, 0
0x1401b0991  mov     cs:qword_1401FA020, 0
0x1401b099c  call    cs:__imp_InitializeSListHead
0x1401b09a3  nop     dword ptr [rax+rax+00h]
0x1401b09a8  xor     r8d, r8d; State
0x1401b09ab  lea     rcx, Event; Event
0x1401b09b2  lea     edx, [r8+1]; Type
0x1401b09b6  call    cs:__imp_KeInitializeEvent
0x1401b09bd  nop     dword ptr [rax+rax+00h]
0x1401b09c2  xor     edx, edx; Val
0x1401b09c4  lea     rcx, Lookaside; void *
0x1401b09cb  mov     r8d, 80h; Size
0x1401b09d1  call    memset
0x1401b09d6  xor     eax, eax
0x1401b09d8  lea     rcx, Lookaside; Lookaside
0x1401b09df  mov     [rsp+48h+Depth], ax; Depth
0x1401b09e4  mov     r9d, 200h; Flags
0x1401b09ea  mov     [rsp+48h+Tag], 77446D56h; Tag
0x1401b09f2  xor     r8d, r8d; Free
0x1401b09f5  xor     edx, edx; Allocate
0x1401b09f7  mov     [rsp+48h+Size], 50h ; 'P'; Size
0x1401b0a00  call    cs:__imp_ExInitializeNPagedLookasideList
0x1401b0a07  nop     dword ptr [rax+rax+00h]
0x1401b0a0c  lea     rax, VmsQsMgmtDeferredWorkerThread
0x1401b0a13  mov     qword ptr [rsp+48h+Depth], 0; StartContext
0x1401b0a1c  mov     qword ptr [rsp+48h+Tag], rax; StartRoutine
0x1401b0a21  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x1401b0a26  xor     r9d, r9d; ProcessHandle
0x1401b0a29  mov     [rsp+48h+Size], 0; ClientId
0x1401b0a32  xor     r8d, r8d; ObjectAttributes
0x1401b0a35  mov     cs:byte_1401FA8C0, 1
0x1401b0a3c  mov     edx, 1FFFFFh; DesiredAccess
0x1401b0a41  call    cs:__imp_PsCreateSystemThread
0x1401b0a48  nop     dword ptr [rax+rax+00h]
0x1401b0a4d  mov     ebx, eax
0x1401b0a4f  test    eax, eax
0x1401b0a51  jns     short loc_1401B0A7D
0x1401b0a53  mov     rcx, cs:VmsIfrLog
0x1401b0a5a  mov     r9d, 26h ; '&'
0x1401b0a60  mov     [rsp+48h+Tag], eax
0x1401b0a64  mov     dl, 2
0x1401b0a66  lea     rax, WPP_9967daa17f81308e3174d8235558202a_Traceguids
0x1401b0a6d  mov     [rsp+48h+Size], rax
0x1401b0a72  lea     r8d, [r9-12h]
0x1401b0a76  call    WPP_RECORDER_SF_d
0x1401b0a7b  jmp     short loc_1401B0ADB
0x1401b0a7d  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x1401b0a82  lea     rax, [rsp+48h+Object]
0x1401b0a87  mov     qword ptr [rsp+48h+Tag], 0; HandleInformation
0x1401b0a90  xor     r9d, r9d; AccessMode
0x1401b0a93  xor     r8d, r8d; ObjectType
0x1401b0a96  mov     [rsp+48h+Size], rax; Object
0x1401b0a9b  mov     edx, 1FFFFFh; DesiredAccess
0x1401b0aa0  mov     [rsp+48h+Object], 0
0x1401b0aa9  call    cs:__imp_ObReferenceObjectByHandle
0x1401b0ab0  nop     dword ptr [rax+rax+00h]
0x1401b0ab5  mov     rax, [rsp+48h+Object]
0x1401b0aba  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x1401b0abf  mov     cs:qword_1401FA020, rax
0x1401b0ac6  call    cs:__imp_ZwClose
0x1401b0acd  nop     dword ptr [rax+rax+00h]
0x1401b0ad2  xor     ebx, ebx
0x1401b0ad4  mov     cs:byte_1401FA8C1, 1
0x1401b0adb  mov     eax, ebx
0x1401b0add  add     rsp, 40h
0x1401b0ae1  pop     rbx
0x1401b0ae2  retn
```
