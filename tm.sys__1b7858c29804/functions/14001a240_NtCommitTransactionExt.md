# NtCommitTransactionExt

- ea: `0x14001a240`
- end: `0x14001a2d7`
- name: `NtCommitTransactionExt`
- size: `151`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionHandle, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14001a240`
- `0x14001a2e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001a2b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a2b8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a291`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001a291`

## pseudocode

```c
NTSTATUS __stdcall NtCommitTransactionExt(HANDLE TransactionHandle, BOOLEAN Wait)
{
  int v3; // edi
  PKTRANSACTION v4; // rbx
  PKTRANSACTION Transaction; // [rsp+50h] [rbp+18h] BYREF

  Transaction = 0;
  v3 = ObReferenceObjectByHandle(
         TransactionHandle,
         Wait != 0 ? 1048584 : 8,
         (POBJECT_TYPE)TmTransactionObjectType,
         *((_BYTE *)KeGetCurrentThread() + 562),
         (PVOID *)&Transaction,
         0);
  if ( v3 >= 0 )
  {
    v4 = Transaction;
    v3 = TmCommitTransactionExt(Transaction, Wait);
    ObfDereferenceObject(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x14001a240  mov     r11, rsp
0x14001a243  mov     [r11+8], rbx
0x14001a247  mov     [r11+10h], rsi
0x14001a24b  push    rdi
0x14001a24c  sub     rsp, 30h
0x14001a250  mov     r9, gs:188h
0x14001a259  mov     al, dl
0x14001a25b  mov     r8, cs:TmTransactionObjectType; ObjectType
0x14001a262  mov     sil, dl
0x14001a265  neg     al
0x14001a267  mov     qword ptr [r11-10h], 0
0x14001a26f  lea     rax, [r11+18h]
0x14001a273  mov     qword ptr [r11+18h], 0
0x14001a27b  mov     r9b, [r9+232h]; AccessMode
0x14001a282  sbb     edx, edx
0x14001a284  and     edx, 100000h
0x14001a28a  mov     [r11-18h], rax
0x14001a28e  add     edx, 8; DesiredAccess
0x14001a291  call    cs:__imp_ObReferenceObjectByHandle
0x14001a298  nop     dword ptr [rax+rax+00h]
0x14001a29d  mov     edi, eax
0x14001a29f  test    eax, eax
0x14001a2a1  js      short loc_14001A2C4
0x14001a2a3  mov     rbx, [rsp+38h+Transaction]
0x14001a2a8  mov     dl, sil; Wait
0x14001a2ab  mov     rcx, rbx; Transaction
0x14001a2ae  call    TmCommitTransactionExt
0x14001a2b3  mov     rcx, rbx; Object
0x14001a2b6  mov     edi, eax
0x14001a2b8  call    cs:__imp_ObfDereferenceObject
0x14001a2bf  nop     dword ptr [rax+rax+00h]
0x14001a2c4  mov     rbx, [rsp+38h+arg_0]
0x14001a2c9  mov     eax, edi
0x14001a2cb  mov     rsi, [rsp+38h+arg_8]
0x14001a2d0  add     rsp, 30h
0x14001a2d4  pop     rdi
0x14001a2d5  retn
```
