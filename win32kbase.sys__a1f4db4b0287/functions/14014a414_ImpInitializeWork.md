# ImpInitializeWork

- ea: `0x14014a414`
- end: `0x14014a70c`
- name: `ImpInitializeWork`
- size: `760`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1401a5a40`

## callees

- `0x14010f2b0`
- `0x14014a414`
- `0x14014a714`
- `0x14014a764`
- `0x14014a814`
- `0x14014a8a8`
- `0x14014a9c0`
- `0x14014aa18`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14014a663`
- `ntoskrnl!ZwClose` at `0x14014a678`
- `ntoskrnl!ZwClose` at `0x14014a663`
- `ntoskrnl!ZwClose` at `0x14014a678`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6b7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14014a51a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14014a51a`
- `ntoskrnl!KeInitializeEvent` at `0x14014a4d6`
- `ntoskrnl!KeInitializeEvent` at `0x14014a4eb`
- `ntoskrnl!KeInitializeEvent` at `0x14014a4d6`
- `ntoskrnl!KeInitializeEvent` at `0x14014a4eb`
- `ntoskrnl!ExAllocatePool2` at `0x14014a48f`
- `ntoskrnl!ExAllocatePool2` at `0x14014a4b1`
- `ntoskrnl!ExAllocatePool2` at `0x14014a48f`
- `ntoskrnl!ExAllocatePool2` at `0x14014a4b1`
- `ntoskrnl!PsCreateSystemThread` at `0x14014a5b4`
- `ntoskrnl!PsCreateSystemThread` at `0x14014a5b4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14014a5fa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14014a5fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14014a64b`
- `ntoskrnl!ObfDereferenceObject` at `0x14014a64b`
- `ntoskrnl!PsThreadType` at `0x14014a5ca`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014a44e`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014a44e`

## pseudocode

```c
__int64 __fastcall ImpInitializeWork(PVOID Object, struct _KEVENT **a2)
{
  char v3; // r14
  char v4; // r12
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 InputMonitorSessionState; // rdi
  struct _KEVENT *Pool2; // r15
  struct _KEVENT *v9; // rsi
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  PVOID v12; // r12
  struct _KEVENT **v13; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+C0h] [rbp+48h] BYREF
  struct _KEVENT **v17; // [rsp+C8h] [rbp+50h]
  HANDLE ProcessHandle; // [rsp+D0h] [rbp+58h] BYREF
  PVOID Objecta; // [rsp+D8h] [rbp+60h] BYREF

  v17 = a2;
  v3 = 0;
  v4 = 0;
  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ThreadHandle = 0;
  InputMonitorSessionState = W32GetInputMonitorSessionState();
  if ( !InputMonitorSessionState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5);
  *(_QWORD *)(InputMonitorSessionState + 64) = InputMonitorSessionState + 56;
  *(_QWORD *)(InputMonitorSessionState + 56) = InputMonitorSessionState + 56;
  if ( !Object )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(InputMonitorSessionState + 56, v5);
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1836084809);
  if ( !Pool2 )
  {
    v9 = 0;
    goto LABEL_32;
  }
  v9 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1836084809);
  if ( !v9 )
  {
LABEL_32:
    v10 = -1073741670;
    goto LABEL_16;
  }
  KeInitializeEvent(Pool2, SynchronizationEvent, 0);
  KeInitializeEvent(v9, SynchronizationEvent, 0);
  v10 = ObOpenObjectByPointer(Object, 0, 0, 2u, 0, 0, &ProcessHandle);
  if ( v10 >= 0 )
  {
    v10 = ImpInitializeLock(InputMonitorSessionState + 72);
    if ( v10 >= 0 )
    {
      v4 = 1;
      v10 = ImpRpcAsyncInit();
      if ( v10 >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = 1;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        ImpAcquireLock(InputMonitorSessionState + 72);
        v10 = PsCreateSystemThread(
                &ThreadHandle,
                0x1FFFFFu,
                &ObjectAttributes,
                ProcessHandle,
                0,
                ImpWorkerRoutine,
                Pool2);
        if ( v10 >= 0 )
        {
          Objecta = 0;
          v11 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, &Objecta, 0);
          v12 = Objecta;
          v10 = v11;
          if ( v11 >= 0 )
          {
            *(_QWORD *)(InputMonitorSessionState + 24) = v9;
            *(_BYTE *)(InputMonitorSessionState + 48) = 1;
            v9 = 0;
            v3 = 0;
            *(_QWORD *)(InputMonitorSessionState + 32) = ThreadHandle;
            v13 = v17;
            *(_QWORD *)(InputMonitorSessionState + 40) = v12;
            ThreadHandle = 0;
            *v13 = Pool2;
            ImpReleaseLock(InputMonitorSessionState + 72);
            Pool2 = 0;
          }
          if ( v12 )
            ObfDereferenceObject(v12);
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
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  if ( v3 )
    ImpRpcAsyncUnInit();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14014a414  mov     [rsp-40h+arg_8], rdx
0x14014a419  push    rbp
0x14014a41a  push    rbx
0x14014a41b  push    rsi
0x14014a41c  push    rdi
0x14014a41d  push    r12
0x14014a41f  push    r13
0x14014a421  push    r14
0x14014a423  push    r15
0x14014a425  mov     rbp, rsp
0x14014a428  sub     rsp, 78h
0x14014a42c  xorps   xmm0, xmm0
0x14014a42f  xor     eax, eax
0x14014a431  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14014a435  mov     rbx, rcx
0x14014a438  xor     r14b, r14b
0x14014a43b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14014a43f  xor     r12b, r12b
0x14014a442  mov     [rbp+ProcessHandle], rax
0x14014a446  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14014a44a  mov     [rbp+ThreadHandle], rax
0x14014a44e  call    cs:__imp_W32GetInputMonitorSessionState
0x14014a455  nop     dword ptr [rax+rax+00h]
0x14014a45a  mov     rdi, rax
0x14014a45d  test    rax, rax
0x14014a460  jz      loc_14014A6EC
0x14014a466  lea     rcx, [rdi+38h]
0x14014a46a  mov     [rcx+8], rcx
0x14014a46e  mov     [rcx], rcx
0x14014a471  test    rbx, rbx
0x14014a474  jz      loc_14014A6F6
0x14014a47a  mov     r13d, 18h
0x14014a480  mov     esi, 6D706E49h
0x14014a485  mov     r8d, esi
0x14014a488  mov     edx, r13d
0x14014a48b  lea     ecx, [r13+28h]
0x14014a48f  call    cs:__imp_ExAllocatePool2
0x14014a496  nop     dword ptr [rax+rax+00h]
0x14014a49b  mov     r15, rax
0x14014a49e  test    rax, rax
0x14014a4a1  jz      loc_14014A700
0x14014a4a7  mov     r8d, esi
0x14014a4aa  lea     ecx, [r13+28h]
0x14014a4ae  mov     edx, r13d
0x14014a4b1  call    cs:__imp_ExAllocatePool2
0x14014a4b8  nop     dword ptr [rax+rax+00h]
0x14014a4bd  mov     rsi, rax
0x14014a4c0  test    rax, rax
0x14014a4c3  jz      loc_14014A702
0x14014a4c9  xor     r8d, r8d; State
0x14014a4cc  mov     rcx, r15; Event
0x14014a4cf  lea     r13d, [r8+1]
0x14014a4d3  mov     edx, r13d; Type
0x14014a4d6  call    cs:__imp_KeInitializeEvent
0x14014a4dd  nop     dword ptr [rax+rax+00h]
0x14014a4e2  xor     r8d, r8d; State
0x14014a4e5  mov     edx, r13d; Type
0x14014a4e8  mov     rcx, rsi; Event
0x14014a4eb  call    cs:__imp_KeInitializeEvent
0x14014a4f2  nop     dword ptr [rax+rax+00h]
0x14014a4f7  lea     rax, [rbp+ProcessHandle]
0x14014a4fb  xor     r8d, r8d; PassedAccessState
0x14014a4fe  mov     [rsp+78h+Handle], rax; Handle
0x14014a503  lea     r9d, [r13+1]; DesiredAccess
0x14014a507  mov     [rsp+78h+AccessMode], r12b; AccessMode
0x14014a50c  xor     edx, edx; HandleAttributes
0x14014a50e  mov     rcx, rbx; Object
0x14014a511  mov     [rsp+78h+ObjectType], 0; ObjectType
0x14014a51a  call    cs:__imp_ObOpenObjectByPointer
0x14014a521  nop     dword ptr [rax+rax+00h]
0x14014a526  mov     ebx, eax
0x14014a528  test    eax, eax
0x14014a52a  js      loc_14014A65A
0x14014a530  lea     r13, [rdi+48h]
0x14014a534  mov     rcx, r13
0x14014a537  call    ImpInitializeLock
0x14014a53c  mov     ebx, eax
0x14014a53e  test    eax, eax
0x14014a540  js      loc_14014A65A
0x14014a546  mov     r12b, 1
0x14014a549  call    ImpRpcAsyncInit
0x14014a54e  mov     ebx, eax
0x14014a550  test    eax, eax
0x14014a552  js      loc_14014A65A
0x14014a558  xorps   xmm0, xmm0
0x14014a55b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14014a562  mov     rcx, r13
0x14014a565  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14014a56d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14014a572  mov     r14b, r12b
0x14014a575  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14014a57c  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14014a584  call    ImpAcquireLock
0x14014a589  mov     r9, [rbp+ProcessHandle]; ProcessHandle
0x14014a58d  lea     rax, ImpWorkerRoutine
0x14014a594  mov     [rsp+78h+Handle], r15; StartContext
0x14014a599  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14014a59d  mov     qword ptr [rsp+78h+AccessMode], rax; StartRoutine
0x14014a5a2  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14014a5a6  mov     edx, 1FFFFFh; DesiredAccess
0x14014a5ab  mov     [rsp+78h+ObjectType], 0; ClientId
0x14014a5b4  call    cs:__imp_PsCreateSystemThread
0x14014a5bb  nop     dword ptr [rax+rax+00h]
0x14014a5c0  mov     ebx, eax
0x14014a5c2  test    eax, eax
0x14014a5c4  js      loc_14014A65A
0x14014a5ca  mov     r8, cs:__imp_PsThreadType
0x14014a5d1  lea     rax, [rbp+Object]
0x14014a5d5  mov     rcx, [rbp+ThreadHandle]; Handle
0x14014a5d9  xor     r9d, r9d; AccessMode
0x14014a5dc  mov     qword ptr [rsp+78h+AccessMode], 0; HandleInformation
0x14014a5e5  mov     edx, 1FFFFFh; DesiredAccess
0x14014a5ea  mov     [rbp+Object], 0
0x14014a5f2  mov     r8, [r8]; ObjectType
0x14014a5f5  mov     [rsp+78h+ObjectType], rax; Object
0x14014a5fa  call    cs:__imp_ObReferenceObjectByHandle
0x14014a601  nop     dword ptr [rax+rax+00h]
0x14014a606  mov     r12, [rbp+Object]
0x14014a60a  mov     ebx, eax
0x14014a60c  test    eax, eax
0x14014a60e  js      short loc_14014A643
0x14014a610  mov     [rdi+18h], rsi
0x14014a614  mov     rcx, r13
0x14014a617  mov     [rdi+30h], r14b
0x14014a61b  xor     esi, esi
0x14014a61d  mov     rax, [rbp+ThreadHandle]
0x14014a621  xor     r14b, r14b
0x14014a624  mov     [rdi+20h], rax
0x14014a628  mov     rax, [rbp+arg_8]
0x14014a62c  mov     [rdi+28h], r12
0x14014a630  mov     [rbp+ThreadHandle], 0
0x14014a638  mov     [rax], r15
0x14014a63b  call    ImpReleaseLock
0x14014a640  xor     r15d, r15d
0x14014a643  test    r12, r12
0x14014a646  jz      short loc_14014A657
0x14014a648  mov     rcx, r12; Object
0x14014a64b  call    cs:__imp_ObfDereferenceObject
0x14014a652  nop     dword ptr [rax+rax+00h]
0x14014a657  mov     r12b, r14b
0x14014a65a  mov     rcx, [rbp+ThreadHandle]; Handle
0x14014a65e  test    rcx, rcx
0x14014a661  jz      short loc_14014A66F
0x14014a663  call    cs:__imp_ZwClose
0x14014a66a  nop     dword ptr [rax+rax+00h]
0x14014a66f  mov     rcx, [rbp+ProcessHandle]; Handle
0x14014a673  test    rcx, rcx
0x14014a676  jz      short loc_14014A684
0x14014a678  call    cs:__imp_ZwClose
0x14014a67f  nop     dword ptr [rax+rax+00h]
0x14014a684  test    r14b, r14b
0x14014a687  jz      short loc_14014A692
0x14014a689  lea     rcx, [rdi+48h]
0x14014a68d  call    ImpReleaseLock
0x14014a692  test    r12b, r12b
0x14014a695  jnz     short loc_14014A6E1
0x14014a697  test    rsi, rsi
0x14014a69a  jz      short loc_14014A6AD
0x14014a69c  xor     edx, edx; Tag
0x14014a69e  mov     rcx, rsi; P
0x14014a6a1  call    cs:__imp_ExFreePoolWithTag
0x14014a6a8  nop     dword ptr [rax+rax+00h]
0x14014a6ad  test    r15, r15
0x14014a6b0  jz      short loc_14014A6C3
0x14014a6b2  xor     edx, edx; Tag
0x14014a6b4  mov     rcx, r15; P
0x14014a6b7  call    cs:__imp_ExFreePoolWithTag
0x14014a6be  nop     dword ptr [rax+rax+00h]
0x14014a6c3  test    r14b, r14b
0x14014a6c6  jz      short loc_14014A6CD
0x14014a6c8  call    ImpRpcAsyncUnInit
0x14014a6cd  mov     eax, ebx
0x14014a6cf  add     rsp, 78h
0x14014a6d3  pop     r15
0x14014a6d5  pop     r14
0x14014a6d7  pop     r13
0x14014a6d9  pop     r12
0x14014a6db  pop     rdi
0x14014a6dc  pop     rsi
0x14014a6dd  pop     rbx
0x14014a6de  pop     rbp
0x14014a6df  retn
0x14014a6e1  lea     rcx, [rdi+48h]
0x14014a6e5  call    ImpCleanupLock
0x14014a6ea  jmp     short loc_14014A697
0x14014a6ec  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14014a6f1  jmp     loc_14014A466
0x14014a6f6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14014a6fb  jmp     loc_14014A47A
0x14014a700  xor     esi, esi
0x14014a702  mov     ebx, 0C000009Ah
0x14014a707  jmp     loc_14014A65A
```
