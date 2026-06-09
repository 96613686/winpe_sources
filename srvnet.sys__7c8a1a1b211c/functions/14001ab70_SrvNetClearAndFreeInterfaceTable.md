# SrvNetClearAndFreeInterfaceTable

- ea: `0x14001ab70`
- end: `0x14001ac06`
- name: `SrvNetClearAndFreeInterfaceTable`
- size: `150`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400105e0`

## callees

- `0x14001ab70`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14001abee`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001abee`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001abd7`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001abd7`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001abb2`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001abb2`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001ab9b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001ab9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abc3`

## pseudocode

```c
void __fastcall SrvNetClearAndFreeInterfaceTable(PRTL_DYNAMIC_HASH_TABLE HashTable)
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
      ExFreePoolWithTag(v3, 0);
    }
  }
  RtlDeleteHashTable(HashTable);
}

```

## disassembly

```asm
0x14001ab70  mov     [rsp+arg_0], rbx
0x14001ab75  push    rdi
0x14001ab76  sub     rsp, 50h
0x14001ab7a  xor     eax, eax
0x14001ab7c  xorps   xmm0, xmm0
0x14001ab7f  mov     rbx, rcx
0x14001ab82  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14001ab87  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14001ab8c  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14001ab91  cmp     [rcx+14h], eax
0x14001ab94  jz      short loc_14001ABEB
0x14001ab96  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001ab9b  call    cs:__imp_RtlInitEnumerationHashTable
0x14001aba2  nop     dword ptr [rax+rax+00h]
0x14001aba7  jmp     short loc_14001ABCF
0x14001aba9  xor     r8d, r8d; Context
0x14001abac  mov     rdx, rdi; Entry
0x14001abaf  mov     rcx, rbx; HashTable
0x14001abb2  call    cs:__imp_RtlRemoveEntryHashTable
0x14001abb9  nop     dword ptr [rax+rax+00h]
0x14001abbe  xor     edx, edx; Tag
0x14001abc0  mov     rcx, rdi; P
0x14001abc3  call    cs:__imp_ExFreePoolWithTag
0x14001abca  nop     dword ptr [rax+rax+00h]
0x14001abcf  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001abd4  mov     rcx, rbx; HashTable
0x14001abd7  call    cs:__imp_RtlEnumerateEntryHashTable
0x14001abde  nop     dword ptr [rax+rax+00h]
0x14001abe3  mov     rdi, rax
0x14001abe6  test    rax, rax
0x14001abe9  jnz     short loc_14001ABA9
0x14001abeb  mov     rcx, rbx; HashTable
0x14001abee  call    cs:__imp_RtlDeleteHashTable
0x14001abf5  nop     dword ptr [rax+rax+00h]
0x14001abfa  mov     rbx, [rsp+58h+arg_0]
0x14001abff  add     rsp, 50h
0x14001ac03  pop     rdi
0x14001ac04  retn
```
