# NtRollbackEnlistmentExt

- ea: `0x140013b80`
- end: `0x140013c45`
- name: `NtRollbackEnlistmentExt`
- size: `197`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000d1fc`
- `0x140013b80`
- `0x140020250`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013c26`
- `ntoskrnl!ObfDereferenceObject` at `0x140013c26`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013bff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013bff`

## pseudocode

```c
NTSTATUS __stdcall NtRollbackEnlistmentExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
    v5 = TmRollbackEnlistmentExt((PKENLISTMENT)Object, p_ULong64FromUser);
    ObfDereferenceObject(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140013b80  mov     [rsp+arg_0], rbx
0x140013b85  mov     [rsp+arg_18], rsi
0x140013b8a  push    rdi
0x140013b8b  sub     rsp, 40h
0x140013b8f  mov     rdi, rdx
0x140013b92  mov     rsi, rcx
0x140013b95  mov     [rsp+48h+arg_8], 0
0x140013b9e  mov     rax, gs:188h
0x140013ba7  mov     bl, [rax+232h]
0x140013bad  test    bl, bl
0x140013baf  jz      short loc_140013BD1
0x140013bb1  test    rdx, rdx
0x140013bb4  jz      short loc_140013BCD
0x140013bb6  mov     rcx, rdx
0x140013bb9  call    RtlReadULong64FromUser
0x140013bbe  mov     [rsp+48h+arg_8], rax
0x140013bc3  lea     rdi, [rsp+48h+arg_8]
0x140013bc8  mov     [rsp+48h+var_18], rdi
0x140013bcd  jmp     short loc_140013BD1
0x140013bcf  jmp     short loc_140013C34
0x140013bd1  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x140013bd8  mov     [rsp+48h+arg_10], 0
0x140013be1  mov     [rsp+48h+HandleInformation], 0; HandleInformation
0x140013bea  lea     rax, [rsp+48h+arg_10]
0x140013bef  mov     [rsp+48h+Object], rax; Object
0x140013bf4  mov     r9b, bl; AccessMode
0x140013bf7  mov     edx, 8; DesiredAccess
0x140013bfc  mov     rcx, rsi; Handle
0x140013bff  call    cs:__imp_ObReferenceObjectByHandle
0x140013c06  nop     dword ptr [rax+rax+00h]
0x140013c0b  mov     esi, eax
0x140013c0d  test    eax, eax
0x140013c0f  js      short loc_140013C32
0x140013c11  mov     rbx, [rsp+48h+arg_10]
0x140013c16  mov     rdx, rdi; TmVirtualClock
0x140013c19  mov     rcx, rbx; Enlistment
0x140013c1c  call    TmRollbackEnlistmentExt
0x140013c21  mov     esi, eax
0x140013c23  mov     rcx, rbx; Object
0x140013c26  call    cs:__imp_ObfDereferenceObject
0x140013c2d  nop     dword ptr [rax+rax+00h]
0x140013c32  mov     eax, esi
0x140013c34  mov     rbx, [rsp+48h+arg_0]
0x140013c39  mov     rsi, [rsp+48h+arg_18]
0x140013c3e  add     rsp, 40h
0x140013c42  pop     rdi
0x140013c43  retn
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
