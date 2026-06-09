# NtReadOnlyEnlistmentExt

- ea: `0x140013950`
- end: `0x140013a15`
- name: `NtReadOnlyEnlistmentExt`
- size: `197`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000d1fc`
- `0x140013950`
- `0x140019e50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400139f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400139f6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400139d1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400139d1`

## pseudocode

```c
NTSTATUS __stdcall NtReadOnlyEnlistmentExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  LARGE_INTEGER *p_ULong64FromUser; // rbx
  KPROCESSOR_MODE v4; // di
  NTSTATUS result; // eax
  PVOID v6; // rdi
  NTSTATUS OnlyEnlistmentExt; // ebx
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
    OnlyEnlistmentExt = TmReadOnlyEnlistmentExt((PKENLISTMENT)Object, p_ULong64FromUser);
    ObfDereferenceObject(v6);
    return OnlyEnlistmentExt;
  }
  return result;
}

```

## disassembly

```asm
0x140013950  mov     [rsp+arg_0], rbx
0x140013955  mov     [rsp+arg_18], rsi
0x14001395a  push    rdi
0x14001395b  sub     rsp, 40h
0x14001395f  mov     rbx, rdx
0x140013962  mov     rsi, rcx
0x140013965  mov     [rsp+48h+arg_8], 0
0x14001396e  mov     rax, gs:188h
0x140013977  mov     dil, [rax+232h]
0x14001397e  test    dil, dil
0x140013981  jz      short loc_1400139A3
0x140013983  test    rdx, rdx
0x140013986  jz      short loc_14001399F
0x140013988  mov     rcx, rdx
0x14001398b  call    RtlReadULong64FromUser
0x140013990  mov     [rsp+48h+arg_8], rax
0x140013995  lea     rbx, [rsp+48h+arg_8]
0x14001399a  mov     [rsp+48h+var_18], rbx
0x14001399f  jmp     short loc_1400139A3
0x1400139a1  jmp     short loc_140013A04
0x1400139a3  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x1400139aa  mov     [rsp+48h+arg_10], 0
0x1400139b3  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x1400139bc  lea     rax, [rsp+48h+arg_10]
0x1400139c1  mov     [rsp+48h+Object], rax; Object
0x1400139c6  mov     r9b, dil; AccessMode
0x1400139c9  mov     edx, 8; DesiredAccess
0x1400139ce  mov     rcx, rsi; Handle
0x1400139d1  call    cs:__imp_ObReferenceObjectByHandle
0x1400139d8  nop     dword ptr [rax+rax+00h]
0x1400139dd  test    eax, eax
0x1400139df  js      short loc_140013A04
0x1400139e1  mov     rdi, [rsp+48h+arg_10]
0x1400139e6  mov     rdx, rbx; TmVirtualClock
0x1400139e9  mov     rcx, rdi; Enlistment
0x1400139ec  call    TmReadOnlyEnlistmentExt
0x1400139f1  mov     ebx, eax
0x1400139f3  mov     rcx, rdi; Object
0x1400139f6  call    cs:__imp_ObfDereferenceObject
0x1400139fd  nop     dword ptr [rax+rax+00h]
0x140013a02  mov     eax, ebx
0x140013a04  mov     rbx, [rsp+48h+arg_0]
0x140013a09  mov     rsi, [rsp+48h+arg_18]
0x140013a0e  add     rsp, 40h
0x140013a12  pop     rdi
0x140013a13  retn
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
