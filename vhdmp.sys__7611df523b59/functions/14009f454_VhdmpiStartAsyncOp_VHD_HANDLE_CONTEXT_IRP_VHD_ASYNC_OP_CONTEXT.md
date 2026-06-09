# VhdmpiStartAsyncOp(_VHD_HANDLE_CONTEXT *,_IRP *,_VHD_ASYNC_OP_CONTEXT *)

- ea: `0x14009f454`
- end: `0x14009f6c3`
- name: `?VhdmpiStartAsyncOp@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@PEAU_VHD_ASYNC_OP_CONTEXT@@@Z`
- size: `623`
- prototype: `int(struct _VHD_HANDLE_CONTEXT *, struct _IRP *, struct _VHD_ASYNC_OP_CONTEXT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14009f6cc`
- `0x1400c8208`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140023560`
- `0x140028f78`
- `0x14002f3fc`
- `0x140035e94`
- `0x14005d840`
- `0x14009f364`
- `0x14009f454`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14009f6a3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14009f6a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009f5fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009f5fc`
- `ntoskrnl!KeSetEvent` at `0x14009f654`
- `ntoskrnl!KeSetEvent` at `0x14009f654`
- `ntoskrnl!PsCreateSystemThread` at `0x14009f597`
- `ntoskrnl!PsCreateSystemThread` at `0x14009f597`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14009f494`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14009f494`
- `ntoskrnl!ExAllocatePool2` at `0x14009f502`
- `ntoskrnl!ExAllocatePool2` at `0x14009f502`
- `ntoskrnl!KeInitializeEvent` at `0x14009f55c`
- `ntoskrnl!KeInitializeEvent` at `0x14009f55c`

## string_xrefs

- `0x14009f5da`: `Failed to create the meta-op thread: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiStartAsyncOp(struct _EX_RUNDOWN_REF *a1, struct _IRP *a2, struct _VHD_ASYNC_OP_CONTEXT *a3)
{
  __int64 v3; // rsi
  struct _EX_RUNDOWN_REF *v4; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  NTSTATUS v14; // ebx
  struct _EX_RUNDOWN_REF **Pool2; // rax
  struct _EX_RUNDOWN_REF **StartContext; // rsi
  struct _EX_RUNDOWN_REF *v17; // rax
  unsigned int v18; // edx
  unsigned __int8 v19; // r8
  void (__fastcall *v20)(struct _VHD_ASYNC_OP_CONTEXT *); // rax
  void (__fastcall *v21)(struct _VHD_ASYNC_OP_CONTEXT *); // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF

  v3 = *(_QWORD *)a3;
  v4 = a1 + 33;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ExAcquireRundownProtection(a1 + 33);
  VhdmpiAcquirePassiveLock(&a1[13], v9, v10);
  a1[15].Count = (ULONG_PTR)a3;
  VhdmpiReleasePassiveLock(&a1[13]);
  v11 = (*(__int64 (__fastcall **)(struct _EX_RUNDOWN_REF *, struct _VHD_ASYNC_OP_CONTEXT *, struct _IRP *, _QWORD))(v3 + 24))(
          a1,
          a3,
          a2->AssociatedIrp.MasterIrp,
          CurrentStackLocation->Parameters.Create.Options);
  *((_BYTE *)a3 + 8) = 1;
  v14 = v11;
  if ( v11 < 0 || *((_BYTE *)a3 + 9) || !*(_QWORD *)(v3 + 40) )
  {
    if ( v11 == 259 )
      goto LABEL_23;
    goto LABEL_19;
  }
  Pool2 = (struct _EX_RUNDOWN_REF **)ExAllocatePool2(64, 48, 1900300374);
  StartContext = Pool2;
  if ( !Pool2 )
  {
    v14 = -1073741801;
LABEL_19:
    if ( *((_BYTE *)a3 + 8) )
    {
      v21 = *(void (__fastcall **)(struct _VHD_ASYNC_OP_CONTEXT *))(*(_QWORD *)a3 + 32LL);
      if ( v21 )
        v21(a3);
    }
    VhdmpiAcquirePassiveLock(&a1[13], v12, v13);
    a1[15].Count = 0;
    VhdmpiReleasePassiveLock(&a1[13]);
    goto LABEL_23;
  }
  *Pool2 = a1;
  v17 = *(struct _EX_RUNDOWN_REF **)a3;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  StartContext[1] = v17;
  KeInitializeEvent((PRKEVENT)(StartContext + 2), SynchronizationEvent, 0);
  *((_BYTE *)StartContext + 40) = 0;
  v14 = PsCreateSystemThread(
          (PHANDLE)a3 + 15,
          0x1FFFFFu,
          &ObjectAttributes,
          0,
          0,
          (PKSTART_ROUTINE)VhdmpiAsyncOpThread,
          StartContext);
  if ( v14 < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
      TraceEvents("VhdmpiStartAsyncOp", 0x28Fu, v19, v18, "Failed to create the meta-op thread: 0x%08x", v14);
    ExFreePoolWithTag(StartContext, 0x71444856u);
    goto LABEL_19;
  }
  if ( (unsigned __int8)VhdmpiEnqueueControlDeviceIoctl(a2) )
  {
    *((_BYTE *)StartContext + 40) = 1;
  }
  else
  {
    if ( *((_BYTE *)a3 + 8) )
    {
      v20 = *(void (__fastcall **)(struct _VHD_ASYNC_OP_CONTEXT *))(*(_QWORD *)a3 + 32LL);
      if ( v20 )
        v20(a3);
    }
    VhdmpiDisconnectAsyncOp(a3, -1073741528);
    VhdmpiFreeAsyncContext(a3);
  }
  KeSetEvent((PRKEVENT)(StartContext + 2), 0, 0);
  v14 = 259;
LABEL_23:
  ExReleaseRundownProtection(v4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14009f454  push    rbx
0x14009f456  push    rbp
0x14009f457  push    rsi
0x14009f458  push    rdi
0x14009f459  push    r12
0x14009f45b  push    r13
0x14009f45d  push    r14
0x14009f45f  push    r15
0x14009f461  sub     rsp, 78h
0x14009f465  mov     rsi, [r8]
0x14009f468  lea     r12, [rcx+108h]
0x14009f46f  mov     rbx, [rdx+0B8h]
0x14009f476  xorps   xmm0, xmm0
0x14009f479  mov     r14, rcx
0x14009f47c  mov     rdi, r8
0x14009f47f  mov     rcx, r12; RunRef
0x14009f482  mov     r13, rdx
0x14009f485  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x14009f48a  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x14009f48f  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009f494  call    cs:__imp_ExAcquireRundownProtection
0x14009f49b  nop     dword ptr [rax+rax+00h]
0x14009f4a0  lea     rbp, [r14+68h]
0x14009f4a4  mov     rcx, rbp
0x14009f4a7  call    VhdmpiAcquirePassiveLock
0x14009f4ac  mov     rcx, rbp
0x14009f4af  mov     [r14+78h], rdi
0x14009f4b3  call    VhdmpiReleasePassiveLock
0x14009f4b8  mov     rax, [rsi+18h]
0x14009f4bc  mov     rdx, rdi
0x14009f4bf  mov     r9d, [rbx+10h]
0x14009f4c3  mov     rcx, r14
0x14009f4c6  mov     r8, [r13+18h]
0x14009f4ca  call    _guard_dispatch_icall
0x14009f4cf  mov     byte ptr [rdi+8], 1
0x14009f4d3  mov     ebx, eax
0x14009f4d5  test    eax, eax
0x14009f4d7  js      loc_14009F667
0x14009f4dd  cmp     byte ptr [rdi+9], 0
0x14009f4e1  jnz     loc_14009F667
0x14009f4e7  cmp     qword ptr [rsi+28h], 0
0x14009f4ec  jz      loc_14009F667
0x14009f4f2  mov     ebx, 30h ; '0'
0x14009f4f7  mov     r8d, 71444856h
0x14009f4fd  mov     edx, ebx
0x14009f4ff  lea     ecx, [rbx+10h]
0x14009f502  call    cs:__imp_ExAllocatePool2
0x14009f509  nop     dword ptr [rax+rax+00h]
0x14009f50e  mov     rsi, rax
0x14009f511  test    rax, rax
0x14009f514  jnz     short loc_14009F520
0x14009f516  mov     ebx, 0C0000017h
0x14009f51b  jmp     loc_14009F66E
0x14009f520  xor     r8d, r8d; State
0x14009f523  mov     [rax], r14
0x14009f526  mov     rax, [rdi]
0x14009f529  lea     rcx, [rsi+10h]; Event
0x14009f52d  xorps   xmm0, xmm0
0x14009f530  mov     [rsp+0B8h+ObjectAttributes.Length], ebx
0x14009f534  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], 0
0x14009f53d  lea     edx, [r8+1]; Type
0x14009f541  mov     [rsp+0B8h+ObjectAttributes.Attributes], 200h
0x14009f549  mov     [rsp+0B8h+ObjectAttributes.ObjectName], 0
0x14009f552  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009f558  mov     [rsi+8], rax
0x14009f55c  call    cs:__imp_KeInitializeEvent
0x14009f563  nop     dword ptr [rax+rax+00h]
0x14009f568  lea     rax, ?VhdmpiAsyncOpThread@@YAXPEAX@Z; VhdmpiAsyncOpThread(void *)
0x14009f56f  mov     [rsp+0B8h+StartContext], rsi; StartContext
0x14009f574  mov     [rsp+0B8h+StartRoutine], rax; StartRoutine
0x14009f579  lea     rcx, [rdi+78h]; ThreadHandle
0x14009f57d  xor     r9d, r9d; ProcessHandle
0x14009f580  mov     [rsp+0B8h+ClientId], 0; ClientId
0x14009f589  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14009f58e  mov     byte ptr [rsi+28h], 0
0x14009f592  mov     edx, 1FFFFFh; DesiredAccess
0x14009f597  call    cs:__imp_PsCreateSystemThread
0x14009f59e  nop     dword ptr [rax+rax+00h]
0x14009f5a3  mov     ebx, eax
0x14009f5a5  test    eax, eax
0x14009f5a7  jns     short loc_14009F60A
0x14009f5a9  mov     eax, cs:dword_140087708
0x14009f5af  mov     r8d, 2
0x14009f5b5  cmp     eax, r8d
0x14009f5b8  jbe     short loc_14009F5F4
0x14009f5ba  lea     edx, [r8-1]
0x14009f5be  lea     rcx, dword_140087708
0x14009f5c5  call    _tlgKeywordOn
0x14009f5ca  test    al, al
0x14009f5cc  jz      short loc_14009F5F4
0x14009f5ce  mov     ecx, 28Fh
0x14009f5d3  mov     dword ptr [rsp+0B8h+StartRoutine], ebx; char
0x14009f5d7  mov     r9d, edx; int
0x14009f5da  lea     rax, aFailedToCreate_0; "Failed to create the meta-op thread: 0x"...
0x14009f5e1  mov     edx, ecx; int
0x14009f5e3  mov     [rsp+0B8h+ClientId], rax; char *
0x14009f5e8  lea     rcx, aVhdmpistartasy; "VhdmpiStartAsyncOp"
0x14009f5ef  call    TraceEvents
0x14009f5f4  mov     edx, 71444856h; Tag
0x14009f5f9  mov     rcx, rsi; P
0x14009f5fc  call    cs:__imp_ExFreePoolWithTag
0x14009f603  nop     dword ptr [rax+rax+00h]
0x14009f608  jmp     short loc_14009F66E
0x14009f60a  mov     rcx, r13; Irp
0x14009f60d  call    VhdmpiEnqueueControlDeviceIoctl
0x14009f612  test    al, al
0x14009f614  jz      short loc_14009F61C
0x14009f616  mov     byte ptr [rsi+28h], 1
0x14009f61a  jmp     short loc_14009F64B
0x14009f61c  cmp     byte ptr [rdi+8], 0
0x14009f620  jz      short loc_14009F636
0x14009f622  mov     rax, [rdi]
0x14009f625  mov     rax, [rax+20h]
0x14009f629  test    rax, rax
0x14009f62c  jz      short loc_14009F636
0x14009f62e  mov     rcx, rdi
0x14009f631  call    _guard_dispatch_icall
0x14009f636  mov     edx, 0C0000128h; int
0x14009f63b  mov     rcx, rdi; struct _VHD_ASYNC_OP_CONTEXT *
0x14009f63e  call    ?VhdmpiDisconnectAsyncOp@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@J@Z; VhdmpiDisconnectAsyncOp(_VHD_ASYNC_OP_CONTEXT *,long)
0x14009f643  mov     rcx, rdi; P
0x14009f646  call    ?VhdmpiFreeAsyncContext@@YAXPEAU_VHD_ASYNC_OP_CONTEXT@@@Z; VhdmpiFreeAsyncContext(_VHD_ASYNC_OP_CONTEXT *)
0x14009f64b  xor     r8d, r8d; Wait
0x14009f64e  lea     rcx, [rsi+10h]; Event
0x14009f652  xor     edx, edx; Increment
0x14009f654  call    cs:__imp_KeSetEvent
0x14009f65b  nop     dword ptr [rax+rax+00h]
0x14009f660  mov     ebx, 103h
0x14009f665  jmp     short loc_14009F6A0
0x14009f667  cmp     eax, 103h
0x14009f66c  jz      short loc_14009F6A0
0x14009f66e  cmp     byte ptr [rdi+8], 0
0x14009f672  jz      short loc_14009F688
0x14009f674  mov     rax, [rdi]
0x14009f677  mov     rax, [rax+20h]
0x14009f67b  test    rax, rax
0x14009f67e  jz      short loc_14009F688
0x14009f680  mov     rcx, rdi
0x14009f683  call    _guard_dispatch_icall
0x14009f688  mov     rcx, rbp
0x14009f68b  call    VhdmpiAcquirePassiveLock
0x14009f690  mov     rcx, rbp
0x14009f693  mov     qword ptr [r14+78h], 0
0x14009f69b  call    VhdmpiReleasePassiveLock
0x14009f6a0  mov     rcx, r12; RunRef
0x14009f6a3  call    cs:__imp_ExReleaseRundownProtection
0x14009f6aa  nop     dword ptr [rax+rax+00h]
0x14009f6af  mov     eax, ebx
0x14009f6b1  add     rsp, 78h
0x14009f6b5  pop     r15
0x14009f6b7  pop     r14
0x14009f6b9  pop     r13
0x14009f6bb  pop     r12
0x14009f6bd  pop     rdi
0x14009f6be  pop     rsi
0x14009f6bf  pop     rbp
0x14009f6c0  pop     rbx
0x14009f6c1  retn
```
