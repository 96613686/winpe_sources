# NtCommitEnlistmentExt

- ea: `0x140012d80`
- end: `0x140012e45`
- name: `NtCommitEnlistmentExt`
- size: `197`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1fc`
- `0x14000fed0`
- `0x140012d80`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012e26`
- `ntoskrnl!ObfDereferenceObject` at `0x140012e26`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012dff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012dff`

## pseudocode

```c
NTSTATUS __stdcall NtCommitEnlistmentExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  LARGE_INTEGER *p_ULong64FromUser; // rdi
  KPROCESSOR_MODE v4; // bl
  int v5; // esi
  PVOID v6; // rbx
  __int64 ULong64FromUser; // [rsp+58h] [rbp+10h] BYREF
  PVOID Object; // [rsp+60h] [rbp+18h] BYREF

  p_ULong64FromUser = TmVirtualClock;
  ULong64FromUser = 0;
  v4 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v4 && TmVirtualClock )
  {
    ULong64FromUser = RtlReadULong64FromUser(TmVirtualClock);
    p_ULong64FromUser = (LARGE_INTEGER *)&ULong64FromUser;
  }
  Object = 0;
  v5 = ObReferenceObjectByHandle(EnlistmentHandle, 0x10u, (POBJECT_TYPE)TmEnlistmentObjectType, v4, &Object, 0);
  if ( v5 >= 0 )
  {
    v6 = Object;
    v5 = TmCommitEnlistmentExt((PKENLISTMENT)Object, p_ULong64FromUser);
    ObfDereferenceObject(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140012d80  mov     [rsp+arg_0], rbx
0x140012d85  mov     [rsp+arg_18], rsi
0x140012d8a  push    rdi
0x140012d8b  sub     rsp, 40h
0x140012d8f  mov     rdi, rdx
0x140012d92  mov     rsi, rcx
0x140012d95  mov     [rsp+48h+arg_8], 0
0x140012d9e  mov     rax, gs:188h
0x140012da7  mov     bl, [rax+232h]
0x140012dad  test    bl, bl
0x140012daf  jz      short loc_140012DD1
0x140012db1  test    rdx, rdx
0x140012db4  jz      short loc_140012DCD
0x140012db6  mov     rcx, rdx
0x140012db9  call    RtlReadULong64FromUser
0x140012dbe  mov     [rsp+48h+arg_8], rax
0x140012dc3  lea     rdi, [rsp+48h+arg_8]
0x140012dc8  mov     [rsp+48h+var_18], rdi
0x140012dcd  jmp     short loc_140012DD1
0x140012dcf  jmp     short loc_140012E34
0x140012dd1  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x140012dd8  mov     [rsp+48h+arg_10], 0
0x140012de1  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x140012dea  lea     rax, [rsp+48h+arg_10]
0x140012def  mov     [rsp+48h+Object], rax; Object
0x140012df4  mov     r9b, bl; AccessMode
0x140012df7  mov     edx, 10h; DesiredAccess
0x140012dfc  mov     rcx, rsi; Handle
0x140012dff  call    cs:__imp_ObReferenceObjectByHandle
0x140012e06  nop     dword ptr [rax+rax+00h]
0x140012e0b  mov     esi, eax
0x140012e0d  test    eax, eax
0x140012e0f  js      short loc_140012E32
0x140012e11  mov     rbx, [rsp+48h+arg_10]
0x140012e16  mov     rdx, rdi; TmVirtualClock
0x140012e19  mov     rcx, rbx; Enlistment
0x140012e1c  call    TmCommitEnlistmentExt
0x140012e21  mov     esi, eax
0x140012e23  mov     rcx, rbx; Object
0x140012e26  call    cs:__imp_ObfDereferenceObject
0x140012e2d  nop     dword ptr [rax+rax+00h]
0x140012e32  mov     eax, esi
0x140012e34  mov     rbx, [rsp+48h+arg_0]
0x140012e39  mov     rsi, [rsp+48h+arg_18]
0x140012e3e  add     rsp, 40h
0x140012e42  pop     rdi
0x140012e43  retn
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
