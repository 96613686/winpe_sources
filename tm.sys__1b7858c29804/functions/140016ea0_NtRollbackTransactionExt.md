# NtRollbackTransactionExt

- ea: `0x140016ea0`
- end: `0x140016f37`
- name: `NtRollbackTransactionExt`
- size: `151`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionHandle, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140010c70`
- `0x140016ea0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140016f18`
- `ntoskrnl!ObfDereferenceObject` at `0x140016f18`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016ef1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016ef1`

## pseudocode

```c
NTSTATUS __stdcall NtRollbackTransactionExt(HANDLE TransactionHandle, BOOLEAN Wait)
{
  int v3; // edi
  PKTRANSACTION v4; // rbx
  PKTRANSACTION Transaction; // [rsp+50h] [rbp+18h] BYREF

  Transaction = 0;
  v3 = ObReferenceObjectByHandle(
         TransactionHandle,
         Wait != 0 ? 1048592 : 16,
         (POBJECT_TYPE)TmTransactionObjectType,
         *((_BYTE *)KeGetCurrentThread() + 562),
         (PVOID *)&Transaction,
         0);
  if ( v3 >= 0 )
  {
    v4 = Transaction;
    v3 = TmRollbackTransactionExt(Transaction, Wait);
    ObfDereferenceObject(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140016ea0  mov     r11, rsp
0x140016ea3  mov     [r11+8], rbx
0x140016ea7  mov     [r11+10h], rsi
0x140016eab  push    rdi
0x140016eac  sub     rsp, 30h
0x140016eb0  mov     r9, gs:188h
0x140016eb9  mov     al, dl
0x140016ebb  mov     r8, cs:TmTransactionObjectType; ObjectType
0x140016ec2  mov     sil, dl
0x140016ec5  neg     al
0x140016ec7  mov     qword ptr [r11-10h], 0
0x140016ecf  lea     rax, [r11+18h]
0x140016ed3  mov     qword ptr [r11+18h], 0
0x140016edb  mov     r9b, [r9+232h]; AccessMode
0x140016ee2  sbb     edx, edx
0x140016ee4  and     edx, 100000h
0x140016eea  mov     [r11-18h], rax
0x140016eee  add     edx, 10h; DesiredAccess
0x140016ef1  call    cs:__imp_ObReferenceObjectByHandle
0x140016ef8  nop     dword ptr [rax+rax+00h]
0x140016efd  mov     edi, eax
0x140016eff  test    eax, eax
0x140016f01  js      short loc_140016F24
0x140016f03  mov     rbx, [rsp+38h+Transaction]
0x140016f08  mov     dl, sil; Wait
0x140016f0b  mov     rcx, rbx; Transaction
0x140016f0e  call    TmRollbackTransactionExt
0x140016f13  mov     rcx, rbx; Object
0x140016f16  mov     edi, eax
0x140016f18  call    cs:__imp_ObfDereferenceObject
0x140016f1f  nop     dword ptr [rax+rax+00h]
0x140016f24  mov     rbx, [rsp+38h+arg_0]
0x140016f29  mov     eax, edi
0x140016f2b  mov     rsi, [rsp+38h+arg_8]
0x140016f30  add     rsp, 30h
0x140016f34  pop     rdi
0x140016f35  retn
```
