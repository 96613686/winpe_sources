# ImpInitializeWork

- ea: `0x1401498c4`
- end: `0x140149bbc`
- name: `ImpInitializeWork`
- size: `760`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1401a54e0`

## callees

- `0x140110520`
- `0x1401498c4`
- `0x140149bc4`
- `0x140149c14`
- `0x140149cc4`
- `0x140149d58`
- `0x140149e70`
- `0x140149ec8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140149b13`
- `ntoskrnl!ZwClose` at `0x140149b28`
- `ntoskrnl!ZwClose` at `0x140149b13`
- `ntoskrnl!ZwClose` at `0x140149b28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149b67`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401499ca`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401499ca`
- `ntoskrnl!KeInitializeEvent` at `0x140149986`
- `ntoskrnl!KeInitializeEvent` at `0x14014999b`
- `ntoskrnl!KeInitializeEvent` at `0x140149986`
- `ntoskrnl!KeInitializeEvent` at `0x14014999b`
- `ntoskrnl!ExAllocatePool2` at `0x14014993f`
- `ntoskrnl!ExAllocatePool2` at `0x140149961`
- `ntoskrnl!ExAllocatePool2` at `0x14014993f`
- `ntoskrnl!ExAllocatePool2` at `0x140149961`
- `ntoskrnl!PsCreateSystemThread` at `0x140149a64`
- `ntoskrnl!PsCreateSystemThread` at `0x140149a64`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140149aaa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140149aaa`
- `ntoskrnl!ObfDereferenceObject` at `0x140149afb`
- `ntoskrnl!ObfDereferenceObject` at `0x140149afb`
- `ntoskrnl!PsThreadType` at `0x140149a7a`
- `WIN32K!W32GetInputMonitorSessionState` at `0x1401498fe`
- `WIN32K!W32GetInputMonitorSessionState` at `0x1401498fe`

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
0x1401498c4  mov     [rsp-40h+arg_8], rdx
0x1401498c9  push    rbp
0x1401498ca  push    rbx
0x1401498cb  push    rsi
0x1401498cc  push    rdi
0x1401498cd  push    r12
0x1401498cf  push    r13
0x1401498d1  push    r14
0x1401498d3  push    r15
0x1401498d5  mov     rbp, rsp
0x1401498d8  sub     rsp, 78h
0x1401498dc  xorps   xmm0, xmm0
0x1401498df  xor     eax, eax
0x1401498e1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1401498e5  mov     rbx, rcx
0x1401498e8  xor     r14b, r14b
0x1401498eb  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1401498ef  xor     r12b, r12b
0x1401498f2  mov     [rbp+ProcessHandle], rax
0x1401498f6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1401498fa  mov     [rbp+ThreadHandle], rax
0x1401498fe  call    cs:__imp_W32GetInputMonitorSessionState
0x140149905  nop     dword ptr [rax+rax+00h]
0x14014990a  mov     rdi, rax
0x14014990d  test    rax, rax
0x140149910  jz      loc_140149B9C
0x140149916  lea     rcx, [rdi+38h]
0x14014991a  mov     [rcx+8], rcx
0x14014991e  mov     [rcx], rcx
0x140149921  test    rbx, rbx
0x140149924  jz      loc_140149BA6
0x14014992a  mov     r13d, 18h
0x140149930  mov     esi, 6D706E49h
0x140149935  mov     r8d, esi
0x140149938  mov     edx, r13d
0x14014993b  lea     ecx, [r13+28h]
0x14014993f  call    cs:__imp_ExAllocatePool2
0x140149946  nop     dword ptr [rax+rax+00h]
0x14014994b  mov     r15, rax
0x14014994e  test    rax, rax
0x140149951  jz      loc_140149BB0
0x140149957  mov     r8d, esi
0x14014995a  lea     ecx, [r13+28h]
0x14014995e  mov     edx, r13d
0x140149961  call    cs:__imp_ExAllocatePool2
0x140149968  nop     dword ptr [rax+rax+00h]
0x14014996d  mov     rsi, rax
0x140149970  test    rax, rax
0x140149973  jz      loc_140149BB2
0x140149979  xor     r8d, r8d; State
0x14014997c  mov     rcx, r15; Event
0x14014997f  lea     r13d, [r8+1]
0x140149983  mov     edx, r13d; Type
0x140149986  call    cs:__imp_KeInitializeEvent
0x14014998d  nop     dword ptr [rax+rax+00h]
0x140149992  xor     r8d, r8d; State
0x140149995  mov     edx, r13d; Type
0x140149998  mov     rcx, rsi; Event
0x14014999b  call    cs:__imp_KeInitializeEvent
0x1401499a2  nop     dword ptr [rax+rax+00h]
0x1401499a7  lea     rax, [rbp+ProcessHandle]
0x1401499ab  xor     r8d, r8d; PassedAccessState
0x1401499ae  mov     [rsp+78h+Handle], rax; Handle
0x1401499b3  lea     r9d, [r13+1]; DesiredAccess
0x1401499b7  mov     [rsp+78h+AccessMode], r12b; AccessMode
0x1401499bc  xor     edx, edx; HandleAttributes
0x1401499be  mov     rcx, rbx; Object
0x1401499c1  mov     [rsp+78h+ObjectType], 0; ObjectType
0x1401499ca  call    cs:__imp_ObOpenObjectByPointer
0x1401499d1  nop     dword ptr [rax+rax+00h]
0x1401499d6  mov     ebx, eax
0x1401499d8  test    eax, eax
0x1401499da  js      loc_140149B0A
0x1401499e0  lea     r13, [rdi+48h]
0x1401499e4  mov     rcx, r13
0x1401499e7  call    ImpInitializeLock
0x1401499ec  mov     ebx, eax
0x1401499ee  test    eax, eax
0x1401499f0  js      loc_140149B0A
0x1401499f6  mov     r12b, 1
0x1401499f9  call    ImpRpcAsyncInit
0x1401499fe  mov     ebx, eax
0x140149a00  test    eax, eax
0x140149a02  js      loc_140149B0A
0x140149a08  xorps   xmm0, xmm0
0x140149a0b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140149a12  mov     rcx, r13
0x140149a15  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140149a1d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140149a22  mov     r14b, r12b
0x140149a25  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140149a2c  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140149a34  call    ImpAcquireLock
0x140149a39  mov     r9, [rbp+ProcessHandle]; ProcessHandle
0x140149a3d  lea     rax, ImpWorkerRoutine
0x140149a44  mov     [rsp+78h+Handle], r15; StartContext
0x140149a49  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140149a4d  mov     qword ptr [rsp+78h+AccessMode], rax; StartRoutine
0x140149a52  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140149a56  mov     edx, 1FFFFFh; DesiredAccess
0x140149a5b  mov     [rsp+78h+ObjectType], 0; ClientId
0x140149a64  call    cs:__imp_PsCreateSystemThread
0x140149a6b  nop     dword ptr [rax+rax+00h]
0x140149a70  mov     ebx, eax
0x140149a72  test    eax, eax
0x140149a74  js      loc_140149B0A
0x140149a7a  mov     r8, cs:__imp_PsThreadType
0x140149a81  lea     rax, [rbp+Object]
0x140149a85  mov     rcx, [rbp+ThreadHandle]; Handle
0x140149a89  xor     r9d, r9d; AccessMode
0x140149a8c  mov     qword ptr [rsp+78h+AccessMode], 0; HandleInformation
0x140149a95  mov     edx, 1FFFFFh; DesiredAccess
0x140149a9a  mov     [rbp+Object], 0
0x140149aa2  mov     r8, [r8]; ObjectType
0x140149aa5  mov     [rsp+78h+ObjectType], rax; Object
0x140149aaa  call    cs:__imp_ObReferenceObjectByHandle
0x140149ab1  nop     dword ptr [rax+rax+00h]
0x140149ab6  mov     r12, [rbp+Object]
0x140149aba  mov     ebx, eax
0x140149abc  test    eax, eax
0x140149abe  js      short loc_140149AF3
0x140149ac0  mov     [rdi+18h], rsi
0x140149ac4  mov     rcx, r13
0x140149ac7  mov     [rdi+30h], r14b
0x140149acb  xor     esi, esi
0x140149acd  mov     rax, [rbp+ThreadHandle]
0x140149ad1  xor     r14b, r14b
0x140149ad4  mov     [rdi+20h], rax
0x140149ad8  mov     rax, [rbp+arg_8]
0x140149adc  mov     [rdi+28h], r12
0x140149ae0  mov     [rbp+ThreadHandle], 0
0x140149ae8  mov     [rax], r15
0x140149aeb  call    ImpReleaseLock
0x140149af0  xor     r15d, r15d
0x140149af3  test    r12, r12
0x140149af6  jz      short loc_140149B07
0x140149af8  mov     rcx, r12; Object
0x140149afb  call    cs:__imp_ObfDereferenceObject
0x140149b02  nop     dword ptr [rax+rax+00h]
0x140149b07  mov     r12b, r14b
0x140149b0a  mov     rcx, [rbp+ThreadHandle]; Handle
0x140149b0e  test    rcx, rcx
0x140149b11  jz      short loc_140149B1F
0x140149b13  call    cs:__imp_ZwClose
0x140149b1a  nop     dword ptr [rax+rax+00h]
0x140149b1f  mov     rcx, [rbp+ProcessHandle]; Handle
0x140149b23  test    rcx, rcx
0x140149b26  jz      short loc_140149B34
0x140149b28  call    cs:__imp_ZwClose
0x140149b2f  nop     dword ptr [rax+rax+00h]
0x140149b34  test    r14b, r14b
0x140149b37  jz      short loc_140149B42
0x140149b39  lea     rcx, [rdi+48h]
0x140149b3d  call    ImpReleaseLock
0x140149b42  test    r12b, r12b
0x140149b45  jnz     short loc_140149B91
0x140149b47  test    rsi, rsi
0x140149b4a  jz      short loc_140149B5D
0x140149b4c  xor     edx, edx; Tag
0x140149b4e  mov     rcx, rsi; P
0x140149b51  call    cs:__imp_ExFreePoolWithTag
0x140149b58  nop     dword ptr [rax+rax+00h]
0x140149b5d  test    r15, r15
0x140149b60  jz      short loc_140149B73
0x140149b62  xor     edx, edx; Tag
0x140149b64  mov     rcx, r15; P
0x140149b67  call    cs:__imp_ExFreePoolWithTag
0x140149b6e  nop     dword ptr [rax+rax+00h]
0x140149b73  test    r14b, r14b
0x140149b76  jz      short loc_140149B7D
0x140149b78  call    ImpRpcAsyncUnInit
0x140149b7d  mov     eax, ebx
0x140149b7f  add     rsp, 78h
0x140149b83  pop     r15
0x140149b85  pop     r14
0x140149b87  pop     r13
0x140149b89  pop     r12
0x140149b8b  pop     rdi
0x140149b8c  pop     rsi
0x140149b8d  pop     rbx
0x140149b8e  pop     rbp
0x140149b8f  retn
0x140149b91  lea     rcx, [rdi+48h]
0x140149b95  call    ImpCleanupLock
0x140149b9a  jmp     short loc_140149B47
0x140149b9c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140149ba1  jmp     loc_140149916
0x140149ba6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140149bab  jmp     loc_14014992A
0x140149bb0  xor     esi, esi
0x140149bb2  mov     ebx, 0C000009Ah
0x140149bb7  jmp     loc_140149B0A
```
