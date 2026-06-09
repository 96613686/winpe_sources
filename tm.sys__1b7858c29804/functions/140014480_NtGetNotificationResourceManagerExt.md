# NtGetNotificationResourceManagerExt

- ea: `0x140014480`
- end: `0x1400145c3`
- name: `NtGetNotificationResourceManagerExt`
- size: `323`
- prototype: `NTSTATUS __stdcall(HANDLE ResourceManagerHandle, PTRANSACTION_NOTIFICATION TransactionNotification, ULONG NotificationLength, PLARGE_INTEGER Timeout, PULONG ReturnLength, ULONG Asynchronous, ULONG_PTR AsynchronousContext)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000d1fc`
- `0x14000d238`
- `0x14000d2bc`
- `0x140012560`
- `0x14001268c`
- `0x140014480`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400145a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400145a3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014549`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014549`
- `ntoskrnl!ProbeForWrite` at `0x1400144c6`
- `ntoskrnl!ProbeForWrite` at `0x1400144c6`

## pseudocode

```c
NTSTATUS __stdcall NtGetNotificationResourceManagerExt(
        HANDLE ResourceManagerHandle,
        PTRANSACTION_NOTIFICATION TransactionNotification,
        ULONG NotificationLength,
        PLARGE_INTEGER Timeout,
        PULONG ReturnLength,
        ULONG Asynchronous,
        ULONG_PTR AsynchronousContext)
{
  LARGE_INTEGER *v11; // rdi
  KPROCESSOR_MODE v12; // r15
  PULONG v13; // rbx
  unsigned int ULongFromUser; // eax
  int v15; // r14d
  PVOID v16; // rsi
  int NotificationResourceManagerAsync; // eax
  __int64 ULong64FromUser; // [rsp+30h] [rbp-58h] BYREF
  PVOID Object[10]; // [rsp+38h] [rbp-50h] BYREF

  ULong64FromUser = 0;
  v11 = 0;
  v12 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v12 )
  {
    ProbeForWrite(TransactionNotification, NotificationLength, 8u);
    if ( Timeout )
    {
      v11 = (LARGE_INTEGER *)&ULong64FromUser;
      Object[1] = &ULong64FromUser;
      ULong64FromUser = RtlReadULong64FromUser(Timeout);
    }
    v13 = ReturnLength;
    if ( ReturnLength )
    {
      ULongFromUser = RtlReadULongFromUser(ReturnLength);
      RtlWriteULongToUser(ReturnLength, ULongFromUser);
    }
  }
  else
  {
    if ( Timeout )
      v11 = Timeout;
    v13 = ReturnLength;
  }
  Object[0] = 0;
  v15 = ObReferenceObjectByHandle(
          ResourceManagerHandle,
          0x10u,
          (POBJECT_TYPE)TmResourceManagerObjectType,
          v12,
          Object,
          0);
  if ( v15 >= 0 )
  {
    v16 = Object[0];
    if ( Asynchronous )
      NotificationResourceManagerAsync = TmpGetNotificationResourceManagerAsync(
                                           (PRKEVENT)Object[0],
                                           v12,
                                           AsynchronousContext,
                                           (__int64)TransactionNotification,
                                           NotificationLength,
                                           (__int64)v13);
    else
      NotificationResourceManagerAsync = TmpGetNotificationResourceManager((PRKEVENT)Object[0], v11, (__int64)v13);
    v15 = NotificationResourceManagerAsync;
    ObfDereferenceObject(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x140014480  push    rbx
0x140014482  push    rsi
0x140014483  push    rdi
0x140014484  push    r12
0x140014486  push    r13
0x140014488  push    r14
0x14001448a  push    r15
0x14001448c  sub     rsp, 50h
0x140014490  mov     rbx, r9
0x140014493  mov     r12d, r8d
0x140014496  mov     r13, rdx
0x140014499  mov     rsi, rcx
0x14001449c  xor     r14d, r14d
0x14001449f  mov     [rsp+88h+var_58], r14
0x1400144a4  mov     edi, r14d
0x1400144a7  mov     rax, gs:188h
0x1400144b0  mov     r15b, [rax+232h]
0x1400144b7  test    r15b, r15b
0x1400144ba  jz      short loc_140014514
0x1400144bc  mov     edx, r12d; Length
0x1400144bf  lea     r8d, [r14+8]; Alignment
0x1400144c3  mov     rcx, r13; Address
0x1400144c6  call    cs:__imp_ProbeForWrite
0x1400144cd  nop     dword ptr [rax+rax+00h]
0x1400144d2  test    rbx, rbx
0x1400144d5  jz      short loc_1400144EE
0x1400144d7  lea     rdi, [rsp+88h+var_58]
0x1400144dc  mov     [rsp+88h+var_48], rdi
0x1400144e1  mov     rcx, rbx
0x1400144e4  call    RtlReadULong64FromUser
0x1400144e9  mov     [rsp+88h+var_58], rax
0x1400144ee  mov     rbx, [rsp+88h+ReturnLength]
0x1400144f6  test    rbx, rbx
0x1400144f9  jz      short loc_14001450D
0x1400144fb  mov     rcx, rbx
0x1400144fe  call    RtlReadULongFromUser
0x140014503  mov     edx, eax
0x140014505  mov     rcx, rbx
0x140014508  call    RtlWriteULongToUser
0x14001450d  jmp     short loc_140014523
0x14001450f  jmp     loc_1400145B2
0x140014514  test    rbx, rbx
0x140014517  cmovnz  rdi, rbx
0x14001451b  mov     rbx, [rsp+88h+ReturnLength]
0x140014523  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x14001452a  mov     [rsp+88h+var_50], r14
0x14001452f  mov     [rsp+88h+HandleInformation], r14; HandleInformation
0x140014534  lea     rax, [rsp+88h+var_50]
0x140014539  mov     [rsp+88h+Object], rax; Object
0x14001453e  mov     r9b, r15b; AccessMode
0x140014541  mov     edx, 10h; DesiredAccess
0x140014546  mov     rcx, rsi; Handle
0x140014549  call    cs:__imp_ObReferenceObjectByHandle
0x140014550  nop     dword ptr [rax+rax+00h]
0x140014555  mov     r14d, eax
0x140014558  test    eax, eax
0x14001455a  js      short loc_1400145AF
0x14001455c  mov     rsi, [rsp+88h+var_50]
0x140014561  mov     [rsp+88h+HandleInformation], rbx; __int64
0x140014566  mov     dl, r15b
0x140014569  mov     rcx, rsi; Event
0x14001456c  cmp     [rsp+88h+Asynchronous], 0
0x140014574  jz      short loc_14001458D
0x140014576  mov     dword ptr [rsp+88h+Object], r12d; int
0x14001457b  mov     r9, r13
0x14001457e  mov     r8, [rsp+88h+AsynchronousContext]
0x140014586  call    TmpGetNotificationResourceManagerAsync
0x14001458b  jmp     short loc_14001459D
0x14001458d  mov     [rsp+88h+Object], rdi; Timeout
0x140014592  mov     r9d, r12d
0x140014595  mov     r8, r13
0x140014598  call    TmpGetNotificationResourceManager
0x14001459d  mov     r14d, eax
0x1400145a0  mov     rcx, rsi; Object
0x1400145a3  call    cs:__imp_ObfDereferenceObject
0x1400145aa  nop     dword ptr [rax+rax+00h]
0x1400145af  mov     eax, r14d
0x1400145b2  add     rsp, 50h
0x1400145b6  pop     r15
0x1400145b8  pop     r14
0x1400145ba  pop     r13
0x1400145bc  pop     r12
0x1400145be  pop     rdi
0x1400145bf  pop     rsi
0x1400145c0  pop     rbx
0x1400145c1  retn
0x140022033  push    rbp
0x140022035  sub     rsp, 30h
0x140022039  mov     rbp, rdx
0x14002203c  call    cs:__imp_ExSystemExceptionFilter
0x140022043  nop     dword ptr [rax+rax+00h]
0x140022048  nop
0x140022049  add     rsp, 30h
0x14002204d  pop     rbp
0x14002204e  retn
```
