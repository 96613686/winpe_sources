# WcFreeInMemoryTombstoneHashTable

- ea: `0x14001c5d8`
- end: `0x14001c682`
- name: `WcFreeInMemoryTombstoneHashTable`
- size: `170`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140030060`

## callees

- `0x14001c5d8`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14001c66a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001c66a`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001c603`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001c603`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001c617`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001c617`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001c65b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001c65b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001c63f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001c63f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c62b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c62b`

## pseudocode

```c
void __fastcall WcFreeInMemoryTombstoneHashTable(PRTL_DYNAMIC_HASH_TABLE HashTable)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v2; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v3; // rdi
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( HashTable->NumEntries )
  {
    RtlInitEnumerationHashTable(HashTable, &Enumerator);
    while ( 1 )
    {
      v2 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
      v3 = v2;
      if ( !v2 )
        break;
      RtlRemoveEntryHashTable(HashTable, v2, 0);
      ExFreePoolWithTag(v3, 0x74684357u);
    }
    RtlEndEnumerationHashTable(HashTable, &Enumerator);
  }
  RtlDeleteHashTable(HashTable);
}

```

## disassembly

```asm
0x14001c5d8  mov     [rsp+arg_0], rbx
0x14001c5dd  push    rdi
0x14001c5de  sub     rsp, 50h
0x14001c5e2  xor     eax, eax
0x14001c5e4  xorps   xmm0, xmm0
0x14001c5e7  mov     rbx, rcx
0x14001c5ea  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14001c5ef  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14001c5f4  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14001c5f9  cmp     [rcx+14h], eax
0x14001c5fc  jz      short loc_14001C667
0x14001c5fe  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001c603  call    cs:__imp_RtlInitEnumerationHashTable
0x14001c60a  nop     dword ptr [rax+rax+00h]
0x14001c60f  jmp     short loc_14001C637
0x14001c611  xor     r8d, r8d; Context
0x14001c614  mov     rdx, rdi; Entry
0x14001c617  call    cs:__imp_RtlRemoveEntryHashTable
0x14001c61e  nop     dword ptr [rax+rax+00h]
0x14001c623  mov     edx, 74684357h; Tag
0x14001c628  mov     rcx, rdi; P
0x14001c62b  call    cs:__imp_ExFreePoolWithTag
0x14001c632  nop     dword ptr [rax+rax+00h]
0x14001c637  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001c63c  mov     rcx, rbx; HashTable
0x14001c63f  call    cs:__imp_RtlEnumerateEntryHashTable
0x14001c646  nop     dword ptr [rax+rax+00h]
0x14001c64b  mov     rdi, rax
0x14001c64e  mov     rcx, rbx; HashTable
0x14001c651  test    rax, rax
0x14001c654  jnz     short loc_14001C611
0x14001c656  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001c65b  call    cs:__imp_RtlEndEnumerationHashTable
0x14001c662  nop     dword ptr [rax+rax+00h]
0x14001c667  mov     rcx, rbx; HashTable
0x14001c66a  call    cs:__imp_RtlDeleteHashTable
0x14001c671  nop     dword ptr [rax+rax+00h]
0x14001c676  mov     rbx, [rsp+58h+arg_0]
0x14001c67b  add     rsp, 50h
0x14001c67f  pop     rdi
0x14001c680  retn
```
