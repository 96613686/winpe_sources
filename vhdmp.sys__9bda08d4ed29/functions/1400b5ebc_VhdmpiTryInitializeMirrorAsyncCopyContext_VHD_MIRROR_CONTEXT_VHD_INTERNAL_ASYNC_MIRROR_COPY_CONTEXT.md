# VhdmpiTryInitializeMirrorAsyncCopyContext(_VHD_MIRROR_CONTEXT *,_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)

- ea: `0x1400b5ebc`
- end: `0x1400b6126`
- name: `?VhdmpiTryInitializeMirrorAsyncCopyContext@@YAXPEAU_VHD_MIRROR_CONTEXT@@PEAU_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT@@@Z`
- size: `618`
- prototype: `void(struct _VHD_MIRROR_CONTEXT *, struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b36d0`

## callees

- `0x140023980`
- `0x140026e20`
- `0x140033a58`
- `0x140036284`
- `0x1400b3110`
- `0x1400b5ebc`
- `0x1400b6ca4`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b5eea`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b5eea`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400b5f0b`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400b5f24`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400b5f0b`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400b5f24`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b6098`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b6098`
- `ntoskrnl!PsCreateSystemThread` at `0x1400b6073`
- `ntoskrnl!PsCreateSystemThread` at `0x1400b6073`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400b603c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400b603c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5f69`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5f69`
- `ntoskrnl!KeInitializeEvent` at `0x1400b5f39`
- `ntoskrnl!KeInitializeEvent` at `0x1400b5fd4`
- `ntoskrnl!KeInitializeEvent` at `0x1400b5f39`
- `ntoskrnl!KeInitializeEvent` at `0x1400b5fd4`

## string_xrefs

- `0x1400b60f8`: `VhdmpiTryInitializeMirrorAsyncCopyContext`
- `0x1400b60eb`: `Worker thread creation failed. (0x%08x) Continuing with %d of %d threads`

## pseudocode

```c
void __fastcall VhdmpiTryInitializeMirrorAsyncCopyContext(
        struct _VHD_MIRROR_CONTEXT *a1,
        struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *a2)
{
  struct _EX_RUNDOWN_REF *v2; // r14
  __int64 v5; // rax
  __int64 Pool2; // rax
  unsigned int v7; // edi
  __int64 StartContext; // rsi
  NTSTATUS v9; // ebp
  unsigned int v10; // edx
  unsigned __int8 v11; // r8
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  v2 = (struct _EX_RUNDOWN_REF *)((char *)a2 + 56);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)a2 + 7);
  VhdmpiInitializePassiveLock(a2);
  KeInitializeSemaphore((PRKSEMAPHORE)((char *)a2 + 72), Count, Count);
  KeInitializeSemaphore((PRKSEMAPHORE)((char *)a2 + 104), Limit, Limit);
  KeInitializeEvent((PRKEVENT)((char *)a2 + 16), NotificationEvent, 0);
  v5 = (unsigned int)dword_14008E384;
  *((_DWORD *)a2 + 16) = dword_14008E384;
  if ( (_DWORD)v5 != 1 )
  {
    Pool2 = ExAllocatePool2(64, 456 * v5, 1195657302);
    *((_QWORD *)a2 + 17) = Pool2;
    if ( !Pool2 )
      goto LABEL_14;
    v7 = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( !*((_DWORD *)a2 + 16) )
      return;
    do
    {
      StartContext = *((_QWORD *)a2 + 17) + 456LL * v7;
      KeInitializeEvent((PRKEVENT)(StartContext + 16), NotificationEvent, 0);
      *(_QWORD *)StartContext = a1;
      *(_QWORD *)(StartContext + 40) = *((_QWORD *)a1 + 25);
      v9 = VhdmpiInitializeInternalIoContext((void *)(StartContext + 48), *((_QWORD *)a1 + 22));
      if ( v9 < 0 )
        break;
      *(_BYTE *)(StartContext + 99) = *((_BYTE *)a1 + 187);
      *(_BYTE *)(StartContext + 100) = *((_BYTE *)a1 + 188);
      ExAcquireRundownProtection(v2);
      v9 = PsCreateSystemThread(
             (PHANDLE)(StartContext + 8),
             0x1FFFFFu,
             &ObjectAttributes,
             0,
             0,
             (PKSTART_ROUTINE)VhdmpiMirrorCopyThread,
             (PVOID)StartContext);
      if ( v9 < 0 )
      {
        ExReleaseRundownProtection(v2);
        VhdmpiCleanupInternalIoContext((void *)(StartContext + 48));
        break;
      }
      ++v7;
    }
    while ( v7 < *((_DWORD *)a2 + 16) );
    if ( v7 >= 2 )
    {
      if ( (unsigned int)dword_1400876D0 > 3 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
          TraceEvents(
            "VhdmpiTryInitializeMirrorAsyncCopyContext",
            0x33Bu,
            v11,
            v10,
            "Worker thread creation failed. (0x%08x) Continuing with %d of %d threads",
            v9,
            v7,
            *((_DWORD *)a2 + 16));
      }
      *((_DWORD *)a2 + 16) = v7;
    }
    else
    {
LABEL_14:
      VhdmpiCleanupMirrorAsyncCopyContext(a2);
    }
  }
}

```

## disassembly

```asm
0x1400b5ebc  push    rbx
0x1400b5ebe  push    rbp
0x1400b5ebf  push    rsi
0x1400b5ec0  push    rdi
0x1400b5ec1  push    r12
0x1400b5ec3  push    r14
0x1400b5ec5  push    r15
0x1400b5ec7  sub     rsp, 70h
0x1400b5ecb  xorps   xmm0, xmm0
0x1400b5ece  lea     r14, [rdx+38h]
0x1400b5ed2  mov     r15, rcx
0x1400b5ed5  mov     rbx, rdx
0x1400b5ed8  mov     rcx, r14; RunRef
0x1400b5edb  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1400b5ee0  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1400b5ee5  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b5eea  call    cs:__imp_ExInitializeRundownProtection
0x1400b5ef1  nop     dword ptr [rax+rax+00h]
0x1400b5ef6  mov     rcx, rbx
0x1400b5ef9  call    VhdmpiInitializePassiveLock
0x1400b5efe  mov     edx, cs:Count; Count
0x1400b5f04  lea     rcx, [rbx+48h]; Semaphore
0x1400b5f08  mov     r8d, edx; Limit
0x1400b5f0b  call    cs:__imp_KeInitializeSemaphore
0x1400b5f12  nop     dword ptr [rax+rax+00h]
0x1400b5f17  mov     edx, cs:Limit; Count
0x1400b5f1d  lea     rcx, [rbx+68h]; Semaphore
0x1400b5f21  mov     r8d, edx; Limit
0x1400b5f24  call    cs:__imp_KeInitializeSemaphore
0x1400b5f2b  nop     dword ptr [rax+rax+00h]
0x1400b5f30  lea     rcx, [rbx+10h]; Event
0x1400b5f34  xor     r8d, r8d; State
0x1400b5f37  xor     edx, edx; Type
0x1400b5f39  call    cs:__imp_KeInitializeEvent
0x1400b5f40  nop     dword ptr [rax+rax+00h]
0x1400b5f45  mov     eax, cs:dword_14008E384
0x1400b5f4b  mov     [rbx+40h], eax
0x1400b5f4e  cmp     eax, 1
0x1400b5f51  jz      loc_1400B6116
0x1400b5f57  imul    rdx, rax, 1C8h
0x1400b5f5e  mov     ecx, 40h ; '@'
0x1400b5f63  mov     r8d, 47444856h
0x1400b5f69  call    cs:__imp_ExAllocatePool2
0x1400b5f70  nop     dword ptr [rax+rax+00h]
0x1400b5f75  mov     [rbx+88h], rax
0x1400b5f7c  test    rax, rax
0x1400b5f7f  jz      loc_1400B610E
0x1400b5f85  xor     edi, edi
0x1400b5f87  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1400b5f8f  xorps   xmm0, xmm0
0x1400b5f92  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], 0
0x1400b5f9b  mov     [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x1400b5fa3  mov     [rsp+0A8h+ObjectAttributes.ObjectName], 0
0x1400b5fac  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b5fb2  cmp     [rbx+40h], edi
0x1400b5fb5  jbe     loc_1400B6116
0x1400b5fbb  mov     eax, edi
0x1400b5fbd  xor     r8d, r8d; State
0x1400b5fc0  imul    rsi, rax, 1C8h
0x1400b5fc7  xor     edx, edx; Type
0x1400b5fc9  add     rsi, [rbx+88h]
0x1400b5fd0  lea     rcx, [rsi+10h]; Event
0x1400b5fd4  call    cs:__imp_KeInitializeEvent
0x1400b5fdb  nop     dword ptr [rax+rax+00h]
0x1400b5fe0  mov     [rsi], r15
0x1400b5fe3  lea     rcx, [rsi+30h]; void *
0x1400b5fe7  mov     rax, [r15+0C8h]
0x1400b5fee  mov     r8b, 1
0x1400b5ff1  mov     [rsi+28h], rax
0x1400b5ff5  mov     r9, [r15+88h]
0x1400b5ffc  mov     rax, [r15+0B0h]
0x1400b6003  mov     edx, [r15+0C0h]
0x1400b600a  mov     [rsp+0A8h+ClientId], rax; __int64
0x1400b600f  mov     r9, [r9+90h]
0x1400b6016  call    VhdmpiInitializeInternalIoContext
0x1400b601b  mov     ebp, eax
0x1400b601d  test    eax, eax
0x1400b601f  js      loc_1400B60AD
0x1400b6025  mov     al, [r15+0BBh]
0x1400b602c  mov     rcx, r14; RunRef
0x1400b602f  mov     [rsi+63h], al
0x1400b6032  mov     al, [r15+0BCh]
0x1400b6039  mov     [rsi+64h], al
0x1400b603c  call    cs:__imp_ExAcquireRundownProtection
0x1400b6043  nop     dword ptr [rax+rax+00h]
0x1400b6048  lea     rax, ?VhdmpiMirrorCopyThread@@YAXPEAX@Z; VhdmpiMirrorCopyThread(void *)
0x1400b604f  mov     [rsp+0A8h+StartContext], rsi; StartContext
0x1400b6054  mov     [rsp+0A8h+StartRoutine], rax; StartRoutine
0x1400b6059  lea     rcx, [rsi+8]; ThreadHandle
0x1400b605d  xor     r9d, r9d; ProcessHandle
0x1400b6060  mov     [rsp+0A8h+ClientId], 0; ClientId
0x1400b6069  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1400b606e  mov     edx, 1FFFFFh; DesiredAccess
0x1400b6073  call    cs:__imp_PsCreateSystemThread
0x1400b607a  nop     dword ptr [rax+rax+00h]
0x1400b607f  mov     ebp, eax
0x1400b6081  test    eax, eax
0x1400b6083  js      short loc_1400B6095
0x1400b6085  inc     edi
0x1400b6087  cmp     edi, [rbx+40h]
0x1400b608a  jb      loc_1400B5FBB
0x1400b6090  jmp     loc_1400B6116
0x1400b6095  mov     rcx, r14; RunRef
0x1400b6098  call    cs:__imp_ExReleaseRundownProtection
0x1400b609f  nop     dword ptr [rax+rax+00h]
0x1400b60a4  lea     rcx, [rsi+30h]; void *
0x1400b60a8  call    VhdmpiCleanupInternalIoContext
0x1400b60ad  cmp     edi, 2
0x1400b60b0  jb      short loc_1400B610E
0x1400b60b2  mov     eax, cs:dword_1400876D0
0x1400b60b8  mov     r8d, 3
0x1400b60be  cmp     eax, r8d
0x1400b60c1  jbe     short loc_1400B6109
0x1400b60c3  mov     edx, 40000h
0x1400b60c8  lea     rcx, dword_1400876D0
0x1400b60cf  call    _tlgKeywordOn
0x1400b60d4  test    al, al
0x1400b60d6  jz      short loc_1400B6109
0x1400b60d8  mov     eax, [rbx+40h]
0x1400b60db  mov     ecx, 33Bh
0x1400b60e0  mov     [rsp+0A8h+var_70], eax
0x1400b60e4  mov     r9d, edx; int
0x1400b60e7  mov     dword ptr [rsp+0A8h+StartContext], edi
0x1400b60eb  lea     rax, aWorkerThreadCr; "Worker thread creation failed. (0x%08x)"...
0x1400b60f2  mov     edx, ecx; int
0x1400b60f4  mov     dword ptr [rsp+0A8h+StartRoutine], ebp; char
0x1400b60f8  lea     rcx, aVhdmpitryiniti; "VhdmpiTryInitializeMirrorAsyncCopyConte"...
0x1400b60ff  mov     [rsp+0A8h+ClientId], rax; char *
0x1400b6104  call    TraceEvents
0x1400b6109  mov     [rbx+40h], edi
0x1400b610c  jmp     short loc_1400B6116
0x1400b610e  mov     rcx, rbx; struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *
0x1400b6111  call    ?VhdmpiCleanupMirrorAsyncCopyContext@@YAXPEAU_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT@@@Z; VhdmpiCleanupMirrorAsyncCopyContext(_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)
0x1400b6116  add     rsp, 70h
0x1400b611a  pop     r15
0x1400b611c  pop     r14
0x1400b611e  pop     r12
0x1400b6120  pop     rdi
0x1400b6121  pop     rsi
0x1400b6122  pop     rbp
0x1400b6123  pop     rbx
0x1400b6124  retn
```
