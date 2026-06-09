# PFSubsumeContext

- ea: `0x140001628`
- end: `0x1400018ee`
- name: `PFSubsumeContext`
- size: `710`
- prototype: `__int64 __usercall@<rax>(PFLT_FILTER Filter@<rcx>, PFLT_INSTANCE Instance@<rdx>, __int64, PHANDLE TargetHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b784`

## callees

- `0x140001188`
- `0x140001628`
- `0x140009378`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140001713`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001713`
- `ntoskrnl!KeSetEvent` at `0x140001852`
- `ntoskrnl!KeSetEvent` at `0x140001852`
- `ntoskrnl!ObfDereferenceObject` at `0x1400016cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14000179e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018a7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018bc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400016cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14000179e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018a7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018bc`
- `ntoskrnl!ZwDuplicateObject` at `0x1400017dc`
- `ntoskrnl!ZwDuplicateObject` at `0x1400017dc`
- `FLTMGR!FltClose` at `0x1400016ef`
- `FLTMGR!FltClose` at `0x1400018d0`
- `FLTMGR!FltClose` at `0x1400016ef`
- `FLTMGR!FltClose` at `0x1400018d0`
- `FLTMGR!FltDeleteStreamContext` at `0x140001868`
- `FLTMGR!FltDeleteStreamContext` at `0x140001868`
- `FLTMGR!FltGetStreamContext` at `0x140001784`
- `FLTMGR!FltGetStreamContext` at `0x140001784`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400017f5`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400017f5`
- `FLTMGR!FltReleaseContext` at `0x140001877`
- `FLTMGR!FltReleaseContext` at `0x140001892`
- `FLTMGR!FltReleaseContext` at `0x140001877`
- `FLTMGR!FltReleaseContext` at `0x140001892`
- `FLTMGR!FltReleaseResource` at `0x14000182a`
- `FLTMGR!FltReleaseResource` at `0x14000182a`

## pseudocode

```c
__int64 __fastcall PFSubsumeContext(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        void *a3,
        char *a4,
        char *a5,
        PHANDLE TargetHandle)
{
  int Lock; // esi
  int v11; // eax
  struct _KEVENT *v12; // rbx
  HANDLE v13; // rdi
  NTSTATUS v14; // eax
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+48h] [rbp-28h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-20h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-18h] BYREF
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-10h] BYREF
  PVOID v21; // [rsp+68h] [rbp-8h]

  FileHandle = 0;
  Object = 0;
  FileObject = 0;
  v21 = 0;
  Context = 0;
  LOBYTE(v16) = 0;
  Lock = PFOpenById(Filter, Instance, a3, a5, 1, &Object, &FileHandle, 0);
  if ( Lock < 0 )
    goto LABEL_22;
  v11 = PFGetContextByFileObject(Filter, Instance, (PFILE_OBJECT)Object, (__int64)&v16);
  v12 = (struct _KEVENT *)v21;
  Lock = v11;
  if ( v11 < 0 )
    goto LABEL_17;
  if ( !v21 )
  {
LABEL_22:
    v13 = FileHandle;
    goto LABEL_23;
  }
  if ( !(_BYTE)v16 )
  {
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    v13 = FileHandle;
    if ( FileHandle )
    {
      FltClose(FileHandle);
      v13 = 0;
    }
    v14 = KeWaitForSingleObject(v12, UserRequest, 0, 1u, 0);
    Lock = v14;
    if ( v14 == 257 || v14 >= 0 && v12[1].Header.LockNV < 0 )
      Lock = v12[1].Header.Lock;
    goto LABEL_18;
  }
  Lock = PFOpenById(Filter, Instance, a3, a4, 0, (PVOID *)&FileObject, 0, 1);
  if ( Lock >= 0 )
  {
    Lock = FltGetStreamContext(Instance, FileObject, &Context);
    if ( Lock >= 0 )
    {
      ObfDereferenceObject(FileObject);
      v13 = FileHandle;
      FileObject = 0;
      Lock = ZwDuplicateObject(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               FileHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               TargetHandle,
               0,
               0,
               6u);
      if ( Lock >= 0 )
      {
        FltAcquireResourceExclusive(&Resource);
        v12[1].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)*((_QWORD *)Context + 5);
        *((_QWORD *)Context + 5) = v12;
        *(_QWORD *)&v12[2].Header.Lock = Object;
        v12 = 0;
        Object = 0;
        FltReleaseResource(&Resource);
      }
      goto LABEL_18;
    }
  }
LABEL_17:
  v13 = FileHandle;
LABEL_18:
  if ( v12 )
  {
    if ( (_BYTE)v16 )
    {
      v12[1].Header.LockNV = Lock;
      KeSetEvent(v12, 0, 0);
      FltDeleteStreamContext(Instance, (PFILE_OBJECT)Object, 0);
    }
    FltReleaseContext(v12);
  }
LABEL_23:
  if ( Context )
    FltReleaseContext(Context);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v13 )
    FltClose(v13);
  return (unsigned int)Lock;
}

```

## disassembly

```asm
0x140001628  push    rbp
0x14000162a  push    rbx
0x14000162b  push    rsi
0x14000162c  push    rdi
0x14000162d  push    r12
0x14000162f  push    r13
0x140001631  push    r14
0x140001633  mov     rbp, rsp
0x140001636  sub     rsp, 70h
0x14000163a  xor     ebx, ebx
0x14000163c  lea     rax, [rbp+FileHandle]
0x140001640  mov     [rsp+70h+var_38], bl; char
0x140001644  mov     r13, r9
0x140001647  mov     r9, [rbp+arg_20]
0x14000164b  mov     r12, r8
0x14000164e  mov     qword ptr [rsp+70h+Options], rax; __int64
0x140001653  mov     r14, rdx
0x140001656  lea     rax, [rbp+Object]
0x14000165a  mov     [rbp+FileHandle], rbx
0x14000165e  mov     qword ptr [rsp+70h+HandleAttributes], rax; Object
0x140001663  mov     rdi, rcx
0x140001666  mov     byte ptr [rsp+70h+Timeout], 1; char
0x14000166b  mov     [rbp+Object], rbx
0x14000166f  mov     [rbp+FileObject], rbx
0x140001673  mov     [rbp+var_8], rbx
0x140001677  mov     [rbp+Context], rbx
0x14000167b  mov     byte ptr [rbp+var_30], bl
0x14000167e  call    PFOpenById
0x140001683  mov     esi, eax
0x140001685  test    eax, eax
0x140001687  js      loc_140001885
0x14000168d  mov     r8, [rbp+Object]; FileObject
0x140001691  lea     rax, [rbp+var_30]
0x140001695  lea     r9, [rbp+var_8]
0x140001699  mov     [rsp+70h+Timeout], rax; __int64
0x14000169e  mov     rdx, r14; Instance
0x1400016a1  mov     rcx, rdi; Filter
0x1400016a4  call    PFGetContextByFileObject
0x1400016a9  mov     rbx, [rbp+var_8]
0x1400016ad  mov     esi, eax
0x1400016af  test    eax, eax
0x1400016b1  js      loc_140001838
0x1400016b7  test    rbx, rbx
0x1400016ba  jz      loc_140001885
0x1400016c0  cmp     byte ptr [rbp+var_30], 0
0x1400016c4  jnz     short loc_140001742
0x1400016c6  mov     rcx, [rbp+Object]; Object
0x1400016ca  test    rcx, rcx
0x1400016cd  jz      short loc_1400016E3
0x1400016cf  call    cs:__imp_ObfDereferenceObject
0x1400016d6  nop     dword ptr [rax+rax+00h]
0x1400016db  mov     [rbp+Object], 0
0x1400016e3  mov     rdi, [rbp+FileHandle]
0x1400016e7  test    rdi, rdi
0x1400016ea  jz      short loc_1400016FD
0x1400016ec  mov     rcx, rdi; FileHandle
0x1400016ef  call    cs:__imp_FltClose
0x1400016f6  nop     dword ptr [rax+rax+00h]
0x1400016fb  xor     edi, edi
0x1400016fd  xor     r8d, r8d; WaitMode
0x140001700  mov     [rsp+70h+Timeout], 0; Timeout
0x140001709  mov     r9b, 1; Alertable
0x14000170c  mov     rcx, rbx; Object
0x14000170f  lea     edx, [r8+6]; WaitReason
0x140001713  call    cs:__imp_KeWaitForSingleObject
0x14000171a  nop     dword ptr [rax+rax+00h]
0x14000171f  mov     esi, eax
0x140001721  cmp     eax, 101h
0x140001726  jz      short loc_14000173A
0x140001728  test    eax, eax
0x14000172a  js      loc_14000183C
0x140001730  cmp     dword ptr [rbx+18h], 0
0x140001734  jge     loc_14000183C
0x14000173a  mov     esi, [rbx+18h]
0x14000173d  jmp     loc_14000183C
0x140001742  mov     [rsp+70h+var_38], 1; char
0x140001747  lea     rax, [rbp+FileObject]
0x14000174b  mov     qword ptr [rsp+70h+Options], 0; __int64
0x140001754  mov     r9, r13
0x140001757  mov     qword ptr [rsp+70h+HandleAttributes], rax; Object
0x14000175c  mov     r8, r12
0x14000175f  mov     rdx, r14; Instance
0x140001762  mov     byte ptr [rsp+70h+Timeout], 0; char
0x140001767  mov     rcx, rdi; Filter
0x14000176a  call    PFOpenById
0x14000176f  mov     esi, eax
0x140001771  test    eax, eax
0x140001773  js      loc_140001838
0x140001779  mov     rdx, [rbp+FileObject]; FileObject
0x14000177d  lea     r8, [rbp+Context]; Context
0x140001781  mov     rcx, r14; Instance
0x140001784  call    cs:__imp_FltGetStreamContext
0x14000178b  nop     dword ptr [rax+rax+00h]
0x140001790  mov     esi, eax
0x140001792  test    eax, eax
0x140001794  js      loc_140001838
0x14000179a  mov     rcx, [rbp+FileObject]; Object
0x14000179e  call    cs:__imp_ObfDereferenceObject
0x1400017a5  nop     dword ptr [rax+rax+00h]
0x1400017aa  mov     rdi, [rbp+FileHandle]
0x1400017ae  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1400017b2  mov     r9, [rbp+TargetHandle]; TargetHandle
0x1400017b6  mov     r8, rcx; TargetProcessHandle
0x1400017b9  mov     [rsp+70h+Options], 6; Options
0x1400017c1  mov     rdx, rdi; SourceHandle
0x1400017c4  mov     [rsp+70h+HandleAttributes], 0; HandleAttributes
0x1400017cc  mov     [rbp+FileObject], 0
0x1400017d4  mov     dword ptr [rsp+70h+Timeout], 0; DesiredAccess
0x1400017dc  call    cs:__imp_ZwDuplicateObject
0x1400017e3  nop     dword ptr [rax+rax+00h]
0x1400017e8  mov     esi, eax
0x1400017ea  test    eax, eax
0x1400017ec  js      short loc_14000183C
0x1400017ee  lea     rcx, Resource; Resource
0x1400017f5  call    cs:__imp_FltAcquireResourceExclusive
0x1400017fc  nop     dword ptr [rax+rax+00h]
0x140001801  mov     rax, [rbp+Context]
0x140001805  lea     rcx, Resource; Resource
0x14000180c  mov     rdx, [rax+28h]
0x140001810  mov     [rbx+28h], rdx
0x140001814  mov     rax, [rbp+Context]
0x140001818  mov     [rax+28h], rbx
0x14000181c  mov     rax, [rbp+Object]
0x140001820  mov     [rbx+30h], rax
0x140001824  xor     ebx, ebx
0x140001826  mov     [rbp+Object], rbx
0x14000182a  call    cs:__imp_FltReleaseResource
0x140001831  nop     dword ptr [rax+rax+00h]
0x140001836  jmp     short loc_14000183C
0x140001838  mov     rdi, [rbp+FileHandle]
0x14000183c  test    rbx, rbx
0x14000183f  jz      short loc_140001889
0x140001841  cmp     byte ptr [rbp+var_30], 0
0x140001845  jz      short loc_140001874
0x140001847  xor     r8d, r8d; Wait
0x14000184a  mov     [rbx+18h], esi
0x14000184d  xor     edx, edx; Increment
0x14000184f  mov     rcx, rbx; Event
0x140001852  call    cs:__imp_KeSetEvent
0x140001859  nop     dword ptr [rax+rax+00h]
0x14000185e  mov     rdx, [rbp+Object]; FileObject
0x140001862  xor     r8d, r8d; OldContext
0x140001865  mov     rcx, r14; Instance
0x140001868  call    cs:__imp_FltDeleteStreamContext
0x14000186f  nop     dword ptr [rax+rax+00h]
0x140001874  mov     rcx, rbx; Context
0x140001877  call    cs:__imp_FltReleaseContext
0x14000187e  nop     dword ptr [rax+rax+00h]
0x140001883  jmp     short loc_140001889
0x140001885  mov     rdi, [rbp+FileHandle]
0x140001889  mov     rcx, [rbp+Context]; Context
0x14000188d  test    rcx, rcx
0x140001890  jz      short loc_14000189E
0x140001892  call    cs:__imp_FltReleaseContext
0x140001899  nop     dword ptr [rax+rax+00h]
0x14000189e  mov     rcx, [rbp+Object]; Object
0x1400018a2  test    rcx, rcx
0x1400018a5  jz      short loc_1400018B3
0x1400018a7  call    cs:__imp_ObfDereferenceObject
0x1400018ae  nop     dword ptr [rax+rax+00h]
0x1400018b3  mov     rcx, [rbp+FileObject]; Object
0x1400018b7  test    rcx, rcx
0x1400018ba  jz      short loc_1400018C8
0x1400018bc  call    cs:__imp_ObfDereferenceObject
0x1400018c3  nop     dword ptr [rax+rax+00h]
0x1400018c8  test    rdi, rdi
0x1400018cb  jz      short loc_1400018DC
0x1400018cd  mov     rcx, rdi; FileHandle
0x1400018d0  call    cs:__imp_FltClose
0x1400018d7  nop     dword ptr [rax+rax+00h]
0x1400018dc  mov     eax, esi
0x1400018de  add     rsp, 70h
0x1400018e2  pop     r14
0x1400018e4  pop     r13
0x1400018e6  pop     r12
0x1400018e8  pop     rdi
0x1400018e9  pop     rsi
0x1400018ea  pop     rbx
0x1400018eb  pop     rbp
0x1400018ec  retn
```
