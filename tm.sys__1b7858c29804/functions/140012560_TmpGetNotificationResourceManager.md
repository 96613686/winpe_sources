# TmpGetNotificationResourceManager

- ea: `0x140012560`
- end: `0x140012686`
- name: `TmpGetNotificationResourceManager`
- size: `294`
- prototype: `__int64 __usercall@<rax>(PRKEVENT Event@<rcx>, PLARGE_INTEGER Timeout, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014480`

## callees

- `0x140012154`
- `0x140012560`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400125b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400125b9`
- `ntoskrnl!KeReleaseMutex` at `0x140012633`
- `ntoskrnl!KeReleaseMutex` at `0x140012633`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012666`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012666`
- `ntoskrnl!ObfDereferenceObject` at `0x14001264d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001264d`
- `ntoskrnl!KeResetEvent` at `0x1400125d4`
- `ntoskrnl!KeResetEvent` at `0x1400125d4`
- `ntoskrnl!KeRemoveQueue` at `0x14001258f`
- `ntoskrnl!KeRemoveQueue` at `0x14001258f`

## pseudocode

```c
__int64 __fastcall TmpGetNotificationResourceManager(
        PRKEVENT Event,
        KPROCESSOR_MODE a2,
        __int64 a3,
        int a4,
        PLARGE_INTEGER Timeout,
        __int64 a6)
{
  char v8; // bp
  PLIST_ENTRY v9; // rbx
  _QWORD *p_Flink; // rdi
  void *v11; // rcx

  v8 = 0;
  v9 = KeRemoveQueue((PRKQUEUE)&Event[6].Header.WaitListHead, a2, Timeout);
  KeWaitForSingleObject(&Event[9], Executive, 0, 0, 0);
  if ( Event[7].Header.WaitListHead.Flink == &Event[7].Header.WaitListHead )
    KeResetEvent(Event);
  if ( v9 == (PLIST_ENTRY)258 || v9 == (PLIST_ENTRY)192 || v9 == (PLIST_ENTRY)128 )
  {
    p_Flink = 0;
  }
  else
  {
    p_Flink = &v9->Flink;
    LODWORD(v9) = TmpCaptureOrRequeueNotification(Event, a4, a6);
    if ( (int)v9 >= 0 )
      v8 = 1;
  }
  KeReleaseMutex((PRKMUTEX)&Event[9], 0);
  if ( v8 )
  {
    v11 = (void *)p_Flink[2];
    if ( v11 )
    {
      ObfDereferenceObject(v11);
      p_Flink[2] = 0;
    }
    ExFreePoolWithTag(p_Flink, 0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012560  push    rbx
0x140012562  push    rbp
0x140012563  push    rsi
0x140012564  push    rdi
0x140012565  push    r12
0x140012567  push    r13
0x140012569  push    r14
0x14001256b  push    r15
0x14001256d  sub     rsp, 38h
0x140012571  mov     r13, r8
0x140012574  mov     rsi, rcx
0x140012577  mov     r8, [rsp+78h+Timeout]; Timeout
0x14001257f  add     rcx, 98h; Queue
0x140012586  mov     r12d, r9d
0x140012589  mov     r15b, dl
0x14001258c  xor     bpl, bpl
0x14001258f  call    cs:__imp_KeRemoveQueue
0x140012596  nop     dword ptr [rax+rax+00h]
0x14001259b  lea     r14, [rsi+0D8h]
0x1400125a2  mov     [rsp+78h+var_58], 0; Timeout
0x1400125ab  mov     rcx, r14; Object
0x1400125ae  xor     r9d, r9d; Alertable
0x1400125b1  xor     r8d, r8d; WaitMode
0x1400125b4  xor     edx, edx; WaitReason
0x1400125b6  mov     rbx, rax
0x1400125b9  call    cs:__imp_KeWaitForSingleObject
0x1400125c0  nop     dword ptr [rax+rax+00h]
0x1400125c5  lea     rcx, [rsi+0B0h]
0x1400125cc  cmp     [rcx], rcx
0x1400125cf  jnz     short loc_1400125E0
0x1400125d1  mov     rcx, rsi; Event
0x1400125d4  call    cs:__imp_KeResetEvent
0x1400125db  nop     dword ptr [rax+rax+00h]
0x1400125e0  cmp     rbx, 102h
0x1400125e7  jz      short loc_14001262C
0x1400125e9  cmp     rbx, 0C0h
0x1400125f0  jz      short loc_14001262C
0x1400125f2  cmp     rbx, 80h
0x1400125f9  jz      short loc_14001262C
0x1400125fb  mov     rax, [rsp+78h+arg_28]
0x140012603  mov     r9, r13
0x140012606  mov     [rsp+78h+var_50], rax; __int64
0x14001260b  mov     r8, rbx
0x14001260e  mov     dl, r15b
0x140012611  mov     dword ptr [rsp+78h+var_58], r12d; int
0x140012616  mov     rcx, rsi; Event
0x140012619  mov     rdi, rbx
0x14001261c  call    TmpCaptureOrRequeueNotification
0x140012621  mov     ebx, eax
0x140012623  test    eax, eax
0x140012625  js      short loc_14001262E
0x140012627  mov     bpl, 1
0x14001262a  jmp     short loc_14001262E
0x14001262c  xor     edi, edi
0x14001262e  xor     edx, edx; Wait
0x140012630  mov     rcx, r14; Mutex
0x140012633  call    cs:__imp_KeReleaseMutex
0x14001263a  nop     dword ptr [rax+rax+00h]
0x14001263f  test    bpl, bpl
0x140012642  jz      short loc_140012672
0x140012644  mov     rcx, [rdi+10h]; Object
0x140012648  test    rcx, rcx
0x14001264b  jz      short loc_140012661
0x14001264d  call    cs:__imp_ObfDereferenceObject
0x140012654  nop     dword ptr [rax+rax+00h]
0x140012659  mov     qword ptr [rdi+10h], 0
0x140012661  xor     edx, edx; Tag
0x140012663  mov     rcx, rdi; P
0x140012666  call    cs:__imp_ExFreePoolWithTag
0x14001266d  nop     dword ptr [rax+rax+00h]
0x140012672  mov     eax, ebx
0x140012674  add     rsp, 38h
0x140012678  pop     r15
0x14001267a  pop     r14
0x14001267c  pop     r13
0x14001267e  pop     r12
0x140012680  pop     rdi
0x140012681  pop     rsi
0x140012682  pop     rbp
0x140012683  pop     rbx
0x140012684  retn
```
