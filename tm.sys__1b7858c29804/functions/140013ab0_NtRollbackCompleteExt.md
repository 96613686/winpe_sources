# NtRollbackCompleteExt

- ea: `0x140013ab0`
- end: `0x140013b75`
- name: `NtRollbackCompleteExt`
- size: `197`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000d1fc`
- `0x140013ab0`
- `0x140019da0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013b56`
- `ntoskrnl!ObfDereferenceObject` at `0x140013b56`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013b31`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013b31`

## pseudocode

```c
NTSTATUS __stdcall NtRollbackCompleteExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  LARGE_INTEGER *p_ULong64FromUser; // rbx
  KPROCESSOR_MODE v4; // di
  NTSTATUS result; // eax
  PVOID v6; // rdi
  NTSTATUS v7; // ebx
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
  result = ObReferenceObjectByHandle(EnlistmentHandle, 8u, (POBJECT_TYPE)TmEnlistmentObjectType, v4, &Object, 0);
  if ( result >= 0 )
  {
    v6 = Object;
    v7 = TmRollbackCompleteExt((PKENLISTMENT)Object, p_ULong64FromUser);
    ObfDereferenceObject(v6);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140013ab0  mov     [rsp+arg_0], rbx
0x140013ab5  mov     [rsp+arg_18], rsi
0x140013aba  push    rdi
0x140013abb  sub     rsp, 40h
0x140013abf  mov     rbx, rdx
0x140013ac2  mov     rsi, rcx
0x140013ac5  mov     [rsp+48h+arg_8], 0
0x140013ace  mov     rax, gs:188h
0x140013ad7  mov     dil, [rax+232h]
0x140013ade  test    dil, dil
0x140013ae1  jz      short loc_140013B03
0x140013ae3  test    rdx, rdx
0x140013ae6  jz      short loc_140013AFF
0x140013ae8  mov     rcx, rdx
0x140013aeb  call    RtlReadULong64FromUser
0x140013af0  mov     [rsp+48h+arg_8], rax
0x140013af5  lea     rbx, [rsp+48h+arg_8]
0x140013afa  mov     [rsp+48h+var_18], rbx
0x140013aff  jmp     short loc_140013B03
0x140013b01  jmp     short loc_140013B64
0x140013b03  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x140013b0a  mov     [rsp+48h+arg_10], 0
0x140013b13  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x140013b1c  lea     rax, [rsp+48h+arg_10]
0x140013b21  mov     [rsp+48h+Object], rax; Object
0x140013b26  mov     r9b, dil; AccessMode
0x140013b29  mov     edx, 8; DesiredAccess
0x140013b2e  mov     rcx, rsi; Handle
0x140013b31  call    cs:__imp_ObReferenceObjectByHandle
0x140013b38  nop     dword ptr [rax+rax+00h]
0x140013b3d  test    eax, eax
0x140013b3f  js      short loc_140013B64
0x140013b41  mov     rdi, [rsp+48h+arg_10]
0x140013b46  mov     rdx, rbx; TmVirtualClock
0x140013b49  mov     rcx, rdi; Enlistment
0x140013b4c  call    TmRollbackCompleteExt
0x140013b51  mov     ebx, eax
0x140013b53  mov     rcx, rdi; Object
0x140013b56  call    cs:__imp_ObfDereferenceObject
0x140013b5d  nop     dword ptr [rax+rax+00h]
0x140013b62  mov     eax, ebx
0x140013b64  mov     rbx, [rsp+48h+arg_0]
0x140013b69  mov     rsi, [rsp+48h+arg_18]
0x140013b6e  add     rsp, 40h
0x140013b72  pop     rdi
0x140013b73  retn
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
