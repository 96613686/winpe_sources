# ImpInitializeWork

- ea: `0x14014b324`
- end: `0x14014b61c`
- name: `ImpInitializeWork`
- size: `760`
- prototype: `__int64 __fastcall(PVOID Object, struct _KEVENT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1401a6070`

## callees

- `0x140111520`
- `0x14014b324`
- `0x14014b624`
- `0x14014b674`
- `0x14014b724`
- `0x14014b7b8`
- `0x14014b8d0`
- `0x14014b928`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14014b573`
- `ntoskrnl!ZwClose` at `0x14014b588`
- `ntoskrnl!ZwClose` at `0x14014b573`
- `ntoskrnl!ZwClose` at `0x14014b588`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014b5b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014b5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014b5b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014b5c7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14014b42a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14014b42a`
- `ntoskrnl!KeInitializeEvent` at `0x14014b3e6`
- `ntoskrnl!KeInitializeEvent` at `0x14014b3fb`
- `ntoskrnl!KeInitializeEvent` at `0x14014b3e6`
- `ntoskrnl!KeInitializeEvent` at `0x14014b3fb`
- `ntoskrnl!ExAllocatePool2` at `0x14014b39f`
- `ntoskrnl!ExAllocatePool2` at `0x14014b3c1`
- `ntoskrnl!ExAllocatePool2` at `0x14014b39f`
- `ntoskrnl!ExAllocatePool2` at `0x14014b3c1`
- `ntoskrnl!PsCreateSystemThread` at `0x14014b4c4`
- `ntoskrnl!PsCreateSystemThread` at `0x14014b4c4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14014b50a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14014b50a`
- `ntoskrnl!ObfDereferenceObject` at `0x14014b55b`
- `ntoskrnl!ObfDereferenceObject` at `0x14014b55b`
- `ntoskrnl!PsThreadType` at `0x14014b4da`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014b35e`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014b35e`

## pseudocode

```c
__int64 __fastcall ImpInitializeWork(PVOID Object, struct _KEVENT **a2)
{
  char v3; // r14
  char v4; // r12
  __int64 InputMonitorSessionState; // rdi
  struct _KEVENT *Pool2; // r15
  struct _KEVENT *v7; // rsi
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  PVOID v10; // r12
  struct _KEVENT **v11; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+C0h] [rbp+48h] BYREF
  struct _KEVENT **v15; // [rsp+C8h] [rbp+50h]
  HANDLE ProcessHandle; // [rsp+D0h] [rbp+58h] BYREF
  PVOID Objecta; // [rsp+D8h] [rbp+60h] BYREF

  v15 = a2;
  v3 = 0;
  v4 = 0;
  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ThreadHandle = 0;
  InputMonitorSessionState = W32GetInputMonitorSessionState();
  if ( !InputMonitorSessionState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  *(_QWORD *)(InputMonitorSessionState + 64) = InputMonitorSessionState + 56;
  *(_QWORD *)(InputMonitorSessionState + 56) = InputMonitorSessionState + 56;
  if ( !Object )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1836084809);
  if ( !Pool2 )
  {
    v7 = 0;
    goto LABEL_32;
  }
  v7 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1836084809);
  if ( !v7 )
  {
LABEL_32:
    v8 = -1073741670;
    goto LABEL_16;
  }
  KeInitializeEvent(Pool2, SynchronizationEvent, 0);
  KeInitializeEvent(v7, SynchronizationEvent, 0);
  v8 = ObOpenObjectByPointer(Object, 0, 0, 2u, 0, 0, &ProcessHandle);
  if ( v8 >= 0 )
  {
    v8 = ImpInitializeLock(InputMonitorSessionState + 72);
    if ( v8 >= 0 )
    {
      v4 = 1;
      v8 = ImpRpcAsyncInit();
      if ( v8 >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = 1;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        ImpAcquireLock(InputMonitorSessionState + 72);
        v8 = PsCreateSystemThread(
               &ThreadHandle,
               0x1FFFFFu,
               &ObjectAttributes,
               ProcessHandle,
               0,
               ImpWorkerRoutine,
               Pool2);
        if ( v8 >= 0 )
        {
          Objecta = 0;
          v9 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, &Objecta, 0);
          v10 = Objecta;
          v8 = v9;
          if ( v9 >= 0 )
          {
            *(_QWORD *)(InputMonitorSessionState + 24) = v7;
            *(_BYTE *)(InputMonitorSessionState + 48) = 1;
            v7 = 0;
            v3 = 0;
            *(_QWORD *)(InputMonitorSessionState + 32) = ThreadHandle;
            v11 = v15;
            *(_QWORD *)(InputMonitorSessionState + 40) = v10;
            ThreadHandle = 0;
            *v11 = Pool2;
            ImpReleaseLock(InputMonitorSessionState + 72);
            Pool2 = 0;
          }
          if ( v10 )
            ObfDereferenceObject(v10);
          v4 = v3;
        }
      }
    }
  }
LABEL_16:
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( v3 )
    ImpReleaseLock(InputMonitorSessionState + 72);
  if ( v4 )
    ImpCleanupLock(InputMonitorSessionState + 72);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  if ( v3 )
    ImpRpcAsyncUnInit();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14014b324  mov     [rsp-40h+arg_8], rdx
0x14014b329  push    rbp
0x14014b32a  push    rbx
0x14014b32b  push    rsi
0x14014b32c  push    rdi
0x14014b32d  push    r12
0x14014b32f  push    r13
0x14014b331  push    r14
0x14014b333  push    r15
0x14014b335  mov     rbp, rsp
0x14014b338  sub     rsp, 78h
0x14014b33c  xorps   xmm0, xmm0
0x14014b33f  xor     eax, eax
0x14014b341  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14014b345  mov     rbx, rcx
0x14014b348  xor     r14b, r14b
0x14014b34b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14014b34f  xor     r12b, r12b
0x14014b352  mov     [rbp+ProcessHandle], rax
0x14014b356  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14014b35a  mov     [rbp+ThreadHandle], rax
0x14014b35e  call    cs:__imp_W32GetInputMonitorSessionState
0x14014b365  nop     dword ptr [rax+rax+00h]
0x14014b36a  mov     rdi, rax
0x14014b36d  test    rax, rax
0x14014b370  jz      loc_14014B5FC
0x14014b376  lea     rcx, [rdi+38h]
0x14014b37a  mov     [rcx+8], rcx
0x14014b37e  mov     [rcx], rcx
0x14014b381  test    rbx, rbx
0x14014b384  jz      loc_14014B606
0x14014b38a  mov     r13d, 18h
0x14014b390  mov     esi, 6D706E49h
0x14014b395  mov     r8d, esi
0x14014b398  mov     edx, r13d
0x14014b39b  lea     ecx, [r13+28h]
0x14014b39f  call    cs:__imp_ExAllocatePool2
0x14014b3a6  nop     dword ptr [rax+rax+00h]
0x14014b3ab  mov     r15, rax
0x14014b3ae  test    rax, rax
0x14014b3b1  jz      loc_14014B610
0x14014b3b7  mov     r8d, esi
0x14014b3ba  lea     ecx, [r13+28h]
0x14014b3be  mov     edx, r13d
0x14014b3c1  call    cs:__imp_ExAllocatePool2
0x14014b3c8  nop     dword ptr [rax+rax+00h]
0x14014b3cd  mov     rsi, rax
0x14014b3d0  test    rax, rax
0x14014b3d3  jz      loc_14014B612
0x14014b3d9  xor     r8d, r8d; State
0x14014b3dc  mov     rcx, r15; Event
0x14014b3df  lea     r13d, [r8+1]
0x14014b3e3  mov     edx, r13d; Type
0x14014b3e6  call    cs:__imp_KeInitializeEvent
0x14014b3ed  nop     dword ptr [rax+rax+00h]
0x14014b3f2  xor     r8d, r8d; State
0x14014b3f5  mov     edx, r13d; Type
0x14014b3f8  mov     rcx, rsi; Event
0x14014b3fb  call    cs:__imp_KeInitializeEvent
0x14014b402  nop     dword ptr [rax+rax+00h]
0x14014b407  lea     rax, [rbp+ProcessHandle]
0x14014b40b  xor     r8d, r8d; PassedAccessState
0x14014b40e  mov     [rsp+78h+Handle], rax; Handle
0x14014b413  lea     r9d, [r13+1]; DesiredAccess
0x14014b417  mov     [rsp+78h+AccessMode], r12b; AccessMode
0x14014b41c  xor     edx, edx; HandleAttributes
0x14014b41e  mov     rcx, rbx; Object
0x14014b421  mov     [rsp+78h+ObjectType], 0; ObjectType
0x14014b42a  call    cs:__imp_ObOpenObjectByPointer
0x14014b431  nop     dword ptr [rax+rax+00h]
0x14014b436  mov     ebx, eax
0x14014b438  test    eax, eax
0x14014b43a  js      loc_14014B56A
0x14014b440  lea     r13, [rdi+48h]
0x14014b444  mov     rcx, r13
0x14014b447  call    ImpInitializeLock
0x14014b44c  mov     ebx, eax
0x14014b44e  test    eax, eax
0x14014b450  js      loc_14014B56A
0x14014b456  mov     r12b, 1
0x14014b459  call    ImpRpcAsyncInit
0x14014b45e  mov     ebx, eax
0x14014b460  test    eax, eax
0x14014b462  js      loc_14014B56A
0x14014b468  xorps   xmm0, xmm0
0x14014b46b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14014b472  mov     rcx, r13
0x14014b475  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14014b47d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14014b482  mov     r14b, r12b
0x14014b485  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14014b48c  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14014b494  call    ImpAcquireLock
0x14014b499  mov     r9, [rbp+ProcessHandle]; ProcessHandle
0x14014b49d  lea     rax, ImpWorkerRoutine
0x14014b4a4  mov     [rsp+78h+Handle], r15; StartContext
0x14014b4a9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14014b4ad  mov     qword ptr [rsp+78h+AccessMode], rax; StartRoutine
0x14014b4b2  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14014b4b6  mov     edx, 1FFFFFh; DesiredAccess
0x14014b4bb  mov     [rsp+78h+ObjectType], 0; ClientId
0x14014b4c4  call    cs:__imp_PsCreateSystemThread
0x14014b4cb  nop     dword ptr [rax+rax+00h]
0x14014b4d0  mov     ebx, eax
0x14014b4d2  test    eax, eax
0x14014b4d4  js      loc_14014B56A
0x14014b4da  mov     r8, cs:__imp_PsThreadType
0x14014b4e1  lea     rax, [rbp+Object]
0x14014b4e5  mov     rcx, [rbp+ThreadHandle]; Handle
0x14014b4e9  xor     r9d, r9d; AccessMode
0x14014b4ec  mov     qword ptr [rsp+78h+AccessMode], 0; HandleInformation
0x14014b4f5  mov     edx, 1FFFFFh; DesiredAccess
0x14014b4fa  mov     [rbp+Object], 0
0x14014b502  mov     r8, [r8]; ObjectType
0x14014b505  mov     [rsp+78h+ObjectType], rax; Object
0x14014b50a  call    cs:__imp_ObReferenceObjectByHandle
0x14014b511  nop     dword ptr [rax+rax+00h]
0x14014b516  mov     r12, [rbp+Object]
0x14014b51a  mov     ebx, eax
0x14014b51c  test    eax, eax
0x14014b51e  js      short loc_14014B553
0x14014b520  mov     [rdi+18h], rsi
0x14014b524  mov     rcx, r13
0x14014b527  mov     [rdi+30h], r14b
0x14014b52b  xor     esi, esi
0x14014b52d  mov     rax, [rbp+ThreadHandle]
0x14014b531  xor     r14b, r14b
0x14014b534  mov     [rdi+20h], rax
0x14014b538  mov     rax, [rbp+arg_8]
0x14014b53c  mov     [rdi+28h], r12
0x14014b540  mov     [rbp+ThreadHandle], 0
0x14014b548  mov     [rax], r15
0x14014b54b  call    ImpReleaseLock
0x14014b550  xor     r15d, r15d
0x14014b553  test    r12, r12
0x14014b556  jz      short loc_14014B567
0x14014b558  mov     rcx, r12; Object
0x14014b55b  call    cs:__imp_ObfDereferenceObject
0x14014b562  nop     dword ptr [rax+rax+00h]
0x14014b567  mov     r12b, r14b
0x14014b56a  mov     rcx, [rbp+ThreadHandle]; Handle
0x14014b56e  test    rcx, rcx
0x14014b571  jz      short loc_14014B57F
0x14014b573  call    cs:__imp_ZwClose
0x14014b57a  nop     dword ptr [rax+rax+00h]
0x14014b57f  mov     rcx, [rbp+ProcessHandle]; Handle
0x14014b583  test    rcx, rcx
0x14014b586  jz      short loc_14014B594
0x14014b588  call    cs:__imp_ZwClose
0x14014b58f  nop     dword ptr [rax+rax+00h]
0x14014b594  test    r14b, r14b
0x14014b597  jz      short loc_14014B5A2
0x14014b599  lea     rcx, [rdi+48h]
0x14014b59d  call    ImpReleaseLock
0x14014b5a2  test    r12b, r12b
0x14014b5a5  jnz     short loc_14014B5F1
0x14014b5a7  test    rsi, rsi
0x14014b5aa  jz      short loc_14014B5BD
0x14014b5ac  xor     edx, edx; Tag
0x14014b5ae  mov     rcx, rsi; P
0x14014b5b1  call    cs:__imp_ExFreePoolWithTag
0x14014b5b8  nop     dword ptr [rax+rax+00h]
0x14014b5bd  test    r15, r15
0x14014b5c0  jz      short loc_14014B5D3
0x14014b5c2  xor     edx, edx; Tag
0x14014b5c4  mov     rcx, r15; P
0x14014b5c7  call    cs:__imp_ExFreePoolWithTag
0x14014b5ce  nop     dword ptr [rax+rax+00h]
0x14014b5d3  test    r14b, r14b
0x14014b5d6  jz      short loc_14014B5DD
0x14014b5d8  call    ImpRpcAsyncUnInit
0x14014b5dd  mov     eax, ebx
0x14014b5df  add     rsp, 78h
0x14014b5e3  pop     r15
0x14014b5e5  pop     r14
0x14014b5e7  pop     r13
0x14014b5e9  pop     r12
0x14014b5eb  pop     rdi
0x14014b5ec  pop     rsi
0x14014b5ed  pop     rbx
0x14014b5ee  pop     rbp
0x14014b5ef  retn
0x14014b5f1  lea     rcx, [rdi+48h]
0x14014b5f5  call    ImpCleanupLock
0x14014b5fa  jmp     short loc_14014B5A7
0x14014b5fc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14014b601  jmp     loc_14014B376
0x14014b606  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14014b60b  jmp     loc_14014B38A
0x14014b610  xor     esi, esi
0x14014b612  mov     ebx, 0C000009Ah
0x14014b617  jmp     loc_14014B56A
```
