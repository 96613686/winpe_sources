# NtRecoverTransactionManagerExt

- ea: `0x14001a580`
- end: `0x14001a626`
- name: `NtRecoverTransactionManagerExt`
- size: `166`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionManagerHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14001a580`
- `0x14001a630`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001a618`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a618`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a5ee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a5ee`
- `ntoskrnl!PsIsComponentEnabled` at `0x14001a592`
- `ntoskrnl!PsIsComponentEnabled` at `0x14001a592`

## pseudocode

```c
NTSTATUS __stdcall NtRecoverTransactionManagerExt(HANDLE TransactionManagerHandle)
{
  int v3; // edi
  PVOID v4; // rbx
  PVOID Object; // [rsp+48h] [rbp+10h] BYREF

  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  Object = 0;
  v3 = ObReferenceObjectByHandle(
         TransactionManagerHandle,
         4u,
         (POBJECT_TYPE)TmTransactionManagerObjectType,
         *((_BYTE *)KeGetCurrentThread() + 562),
         &Object,
         0);
  if ( v3 >= 0 )
  {
    v4 = Object;
    v3 = TmRecoverTransactionManagerExt((PKTM)Object, 0);
    ObfDereferenceObject(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x14001a580  mov     [rsp+arg_0], rbx
0x14001a585  push    rdi
0x14001a586  sub     rsp, 30h
0x14001a58a  mov     rbx, rcx
0x14001a58d  mov     ecx, 1
0x14001a592  call    cs:__imp_PsIsComponentEnabled
0x14001a599  nop     dword ptr [rax+rax+00h]
0x14001a59e  test    al, al
0x14001a5a0  jnz     short loc_14001A5B3
0x14001a5a2  mov     eax, 0C0000022h
0x14001a5a7  mov     rbx, [rsp+38h+arg_0]
0x14001a5ac  add     rsp, 30h
0x14001a5b0  pop     rdi
0x14001a5b1  retn
0x14001a5b3  mov     r9, gs:188h
0x14001a5bc  lea     rax, [rsp+38h+arg_8]
0x14001a5c1  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x14001a5c8  mov     edx, 4; DesiredAccess
0x14001a5cd  mov     [rsp+38h+HandleInformation], 0; HandleInformation
0x14001a5d6  mov     rcx, rbx; Handle
0x14001a5d9  mov     [rsp+38h+arg_8], 0
0x14001a5e2  mov     r9b, [r9+232h]; AccessMode
0x14001a5e9  mov     [rsp+38h+Object], rax; Object
0x14001a5ee  call    cs:__imp_ObReferenceObjectByHandle
0x14001a5f5  nop     dword ptr [rax+rax+00h]
0x14001a5fa  mov     edi, eax
0x14001a5fc  test    eax, eax
0x14001a5fe  jns     short loc_14001A604
0x14001a600  mov     eax, edi
0x14001a602  jmp     short loc_14001A5A7
0x14001a604  mov     rbx, [rsp+38h+arg_8]
0x14001a609  xor     edx, edx; TargetVirtualClock
0x14001a60b  mov     rcx, rbx; Tm
0x14001a60e  call    TmRecoverTransactionManagerExt
0x14001a613  mov     rcx, rbx; Object
0x14001a616  mov     edi, eax
0x14001a618  call    cs:__imp_ObfDereferenceObject
0x14001a61f  nop     dword ptr [rax+rax+00h]
0x14001a624  jmp     short loc_14001A600
```
