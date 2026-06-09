# NtRollforwardTransactionManagerExt

- ea: `0x140017fd0`
- end: `0x1400180b4`
- name: `NtRollforwardTransactionManagerExt`
- size: `228`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionManagerHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1fc`
- `0x140017fd0`
- `0x14001a630`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140018095`
- `ntoskrnl!ObfDereferenceObject` at `0x140018095`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001806e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001806e`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017ff3`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017ff3`

## pseudocode

```c
NTSTATUS __stdcall NtRollforwardTransactionManagerExt(HANDLE TransactionManagerHandle, PLARGE_INTEGER TmVirtualClock)
{
  KPROCESSOR_MODE v5; // bl
  int v6; // esi
  PVOID v7; // rbx
  __int64 ULong64FromUser; // [rsp+58h] [rbp+10h] BYREF
  PVOID Object; // [rsp+60h] [rbp+18h] BYREF

  ULong64FromUser = 0;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  v5 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v5 && TmVirtualClock )
  {
    ULong64FromUser = RtlReadULong64FromUser(TmVirtualClock);
    TmVirtualClock = (PLARGE_INTEGER)&ULong64FromUser;
  }
  Object = 0;
  v6 = ObReferenceObjectByHandle(
         TransactionManagerHandle,
         4u,
         (POBJECT_TYPE)TmTransactionManagerObjectType,
         v5,
         &Object,
         0);
  if ( v6 >= 0 )
  {
    v7 = Object;
    v6 = TmRecoverTransactionManagerExt((PKTM)Object, TmVirtualClock);
    ObfDereferenceObject(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x140017fd0  mov     [rsp+arg_0], rbx
0x140017fd5  mov     [rsp+arg_18], rsi
0x140017fda  push    rdi
0x140017fdb  sub     rsp, 40h
0x140017fdf  mov     rdi, rdx
0x140017fe2  mov     rsi, rcx
0x140017fe5  mov     [rsp+48h+arg_8], 0
0x140017fee  mov     ecx, 1
0x140017ff3  call    cs:__imp_PsIsComponentEnabled
0x140017ffa  nop     dword ptr [rax+rax+00h]
0x140017fff  test    al, al
0x140018001  jnz     short loc_14001800D
0x140018003  mov     eax, 0C0000022h
0x140018008  jmp     loc_1400180A3
0x14001800d  mov     rax, gs:188h
0x140018016  mov     bl, [rax+232h]
0x14001801c  test    bl, bl
0x14001801e  jz      short loc_140018040
0x140018020  test    rdi, rdi
0x140018023  jz      short loc_14001803C
0x140018025  mov     rcx, rdi
0x140018028  call    RtlReadULong64FromUser
0x14001802d  mov     [rsp+48h+arg_8], rax
0x140018032  lea     rdi, [rsp+48h+arg_8]
0x140018037  mov     [rsp+48h+var_18], rdi
0x14001803c  jmp     short loc_140018040
0x14001803e  jmp     short loc_1400180A3
0x140018040  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x140018047  mov     [rsp+48h+arg_10], 0
0x140018050  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x140018059  lea     rax, [rsp+48h+arg_10]
0x14001805e  mov     [rsp+48h+Object], rax; Object
0x140018063  mov     r9b, bl; AccessMode
0x140018066  mov     edx, 4; DesiredAccess
0x14001806b  mov     rcx, rsi; Handle
0x14001806e  call    cs:__imp_ObReferenceObjectByHandle
0x140018075  nop     dword ptr [rax+rax+00h]
0x14001807a  mov     esi, eax
0x14001807c  test    eax, eax
0x14001807e  js      short loc_1400180A1
0x140018080  mov     rbx, [rsp+48h+arg_10]
0x140018085  mov     rdx, rdi; TargetVirtualClock
0x140018088  mov     rcx, rbx; Tm
0x14001808b  call    TmRecoverTransactionManagerExt
0x140018090  mov     esi, eax
0x140018092  mov     rcx, rbx; Object
0x140018095  call    cs:__imp_ObfDereferenceObject
0x14001809c  nop     dword ptr [rax+rax+00h]
0x1400180a1  mov     eax, esi
0x1400180a3  mov     rbx, [rsp+48h+arg_0]
0x1400180a8  mov     rsi, [rsp+48h+arg_18]
0x1400180ad  add     rsp, 40h
0x1400180b1  pop     rdi
0x1400180b2  retn
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
