# NtCommitCompleteExt

- ea: `0x140012cb0`
- end: `0x140012d75`
- name: `NtCommitCompleteExt`
- size: `197`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1fc`
- `0x140012cb0`
- `0x140019f00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012d56`
- `ntoskrnl!ObfDereferenceObject` at `0x140012d56`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012d2f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012d2f`

## pseudocode

```c
NTSTATUS __stdcall NtCommitCompleteExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  v5 = ObReferenceObjectByHandle(EnlistmentHandle, 8u, (POBJECT_TYPE)TmEnlistmentObjectType, v4, &Object, 0);
  if ( v5 >= 0 )
  {
    v6 = Object;
    v5 = TmCommitCompleteExt((PKENLISTMENT)Object, p_ULong64FromUser);
    ObfDereferenceObject(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140012cb0  mov     [rsp+arg_0], rbx
0x140012cb5  mov     [rsp+arg_18], rsi
0x140012cba  push    rdi
0x140012cbb  sub     rsp, 40h
0x140012cbf  mov     rdi, rdx
0x140012cc2  mov     rsi, rcx
0x140012cc5  mov     [rsp+48h+arg_8], 0
0x140012cce  mov     rax, gs:188h
0x140012cd7  mov     bl, [rax+232h]
0x140012cdd  test    bl, bl
0x140012cdf  jz      short loc_140012D01
0x140012ce1  test    rdx, rdx
0x140012ce4  jz      short loc_140012CFD
0x140012ce6  mov     rcx, rdx
0x140012ce9  call    RtlReadULong64FromUser
0x140012cee  mov     [rsp+48h+arg_8], rax
0x140012cf3  lea     rdi, [rsp+48h+arg_8]
0x140012cf8  mov     [rsp+48h+var_18], rdi
0x140012cfd  jmp     short loc_140012D01
0x140012cff  jmp     short loc_140012D64
0x140012d01  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x140012d08  mov     [rsp+48h+arg_10], 0
0x140012d11  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x140012d1a  lea     rax, [rsp+48h+arg_10]
0x140012d1f  mov     [rsp+48h+Object], rax; Object
0x140012d24  mov     r9b, bl; AccessMode
0x140012d27  mov     edx, 8; DesiredAccess
0x140012d2c  mov     rcx, rsi; Handle
0x140012d2f  call    cs:__imp_ObReferenceObjectByHandle
0x140012d36  nop     dword ptr [rax+rax+00h]
0x140012d3b  mov     esi, eax
0x140012d3d  test    eax, eax
0x140012d3f  js      short loc_140012D62
0x140012d41  mov     rbx, [rsp+48h+arg_10]
0x140012d46  mov     rdx, rdi; TmVirtualClock
0x140012d49  mov     rcx, rbx; Enlistment
0x140012d4c  call    TmCommitCompleteExt
0x140012d51  mov     esi, eax
0x140012d53  mov     rcx, rbx; Object
0x140012d56  call    cs:__imp_ObfDereferenceObject
0x140012d5d  nop     dword ptr [rax+rax+00h]
0x140012d62  mov     eax, esi
0x140012d64  mov     rbx, [rsp+48h+arg_0]
0x140012d69  mov     rsi, [rsp+48h+arg_18]
0x140012d6e  add     rsp, 40h
0x140012d72  pop     rdi
0x140012d73  retn
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
