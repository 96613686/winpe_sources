# WcClearDirectoryTable

- ea: `0x14001d42c`
- end: `0x14001d565`
- name: `WcClearDirectoryTable`
- size: `313`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d23c`

## callees

- `0x14001d42c`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001d478`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001d478`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001d48f`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001d48f`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001d538`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001d538`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001d518`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001d518`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d4db`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d4db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d504`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d504`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001d456`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001d456`
- `FLTMGR!FltReleaseResource` at `0x14001d548`
- `FLTMGR!FltReleaseResource` at `0x14001d548`
- `FLTMGR!FltClose` at `0x14001d4c2`
- `FLTMGR!FltClose` at `0x14001d4c2`

## pseudocode

```c
void __fastcall WcClearDirectoryTable(__int64 a1)
{
  struct _ERESOURCE *v2; // rcx
  struct _LIST_ENTRY *Blink; // rcx
  void *v4; // rcx
  void *v5; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v6; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v8; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(struct _ERESOURCE **)(a1 + 64);
  memset(&Enumerator, 0, sizeof(Enumerator));
  FltAcquireResourceExclusive(v2);
  if ( *(_DWORD *)(a1 + 92) )
  {
    RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 72), &Enumerator);
    while ( 1 )
    {
      v6 = RtlEnumerateEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 72), &Enumerator);
      v7 = v6;
      v8 = (struct _RTL_DYNAMIC_HASH_TABLE *)(a1 + 72);
      if ( !v6 )
        break;
      RtlRemoveEntryHashTable(v8, v6, 0);
      Blink = v7[1].Linkage.Blink;
      if ( Blink )
        ExFreePoolWithTag(Blink, 0x6E664357u);
      v4 = *(void **)(v7[1].Signature + 8);
      if ( v4 )
        FltClose(v4);
      v5 = *(void **)(v7[1].Signature + 16);
      if ( v5 )
        ObfDereferenceObject(v5);
      ExFreePoolWithTag((PVOID)v7[1].Signature, 0x73734357u);
      ExFreePoolWithTag(v7, 0x74644357u);
    }
    RtlEndEnumerationHashTable(v8, &Enumerator);
  }
  FltReleaseResource(*(PERESOURCE *)(a1 + 64));
}

```

## disassembly

```asm
0x14001d42c  mov     [rsp+arg_0], rbx
0x14001d431  mov     [rsp+arg_8], rsi
0x14001d436  push    rdi
0x14001d437  sub     rsp, 50h
0x14001d43b  xorps   xmm0, xmm0
0x14001d43e  mov     rsi, rcx
0x14001d441  mov     rcx, [rcx+40h]; Resource
0x14001d445  xor     eax, eax
0x14001d447  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14001d44c  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14001d451  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14001d456  call    cs:__imp_FltAcquireResourceExclusive
0x14001d45d  nop     dword ptr [rax+rax+00h]
0x14001d462  lea     rdi, [rsi+48h]
0x14001d466  cmp     dword ptr [rdi+14h], 0
0x14001d46a  jz      loc_14001D544
0x14001d470  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001d475  mov     rcx, rdi; HashTable
0x14001d478  call    cs:__imp_RtlInitEnumerationHashTable
0x14001d47f  nop     dword ptr [rax+rax+00h]
0x14001d484  jmp     loc_14001D510
0x14001d489  xor     r8d, r8d; Context
0x14001d48c  mov     rdx, rbx; Entry
0x14001d48f  call    cs:__imp_RtlRemoveEntryHashTable
0x14001d496  nop     dword ptr [rax+rax+00h]
0x14001d49b  mov     rcx, [rbx+20h]; P
0x14001d49f  test    rcx, rcx
0x14001d4a2  jz      short loc_14001D4B5
0x14001d4a4  mov     edx, 6E664357h; Tag
0x14001d4a9  call    cs:__imp_ExFreePoolWithTag
0x14001d4b0  nop     dword ptr [rax+rax+00h]
0x14001d4b5  mov     rax, [rbx+28h]
0x14001d4b9  mov     rcx, [rax+8]; FileHandle
0x14001d4bd  test    rcx, rcx
0x14001d4c0  jz      short loc_14001D4CE
0x14001d4c2  call    cs:__imp_FltClose
0x14001d4c9  nop     dword ptr [rax+rax+00h]
0x14001d4ce  mov     rax, [rbx+28h]
0x14001d4d2  mov     rcx, [rax+10h]; Object
0x14001d4d6  test    rcx, rcx
0x14001d4d9  jz      short loc_14001D4E7
0x14001d4db  call    cs:__imp_ObfDereferenceObject
0x14001d4e2  nop     dword ptr [rax+rax+00h]
0x14001d4e7  mov     rcx, [rbx+28h]; P
0x14001d4eb  mov     edx, 73734357h; Tag
0x14001d4f0  call    cs:__imp_ExFreePoolWithTag
0x14001d4f7  nop     dword ptr [rax+rax+00h]
0x14001d4fc  mov     edx, 74644357h; Tag
0x14001d501  mov     rcx, rbx; P
0x14001d504  call    cs:__imp_ExFreePoolWithTag
0x14001d50b  nop     dword ptr [rax+rax+00h]
0x14001d510  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001d515  mov     rcx, rdi; HashTable
0x14001d518  call    cs:__imp_RtlEnumerateEntryHashTable
0x14001d51f  nop     dword ptr [rax+rax+00h]
0x14001d524  mov     rbx, rax
0x14001d527  mov     rcx, rdi; HashTable
0x14001d52a  test    rax, rax
0x14001d52d  jnz     loc_14001D489
0x14001d533  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14001d538  call    cs:__imp_RtlEndEnumerationHashTable
0x14001d53f  nop     dword ptr [rax+rax+00h]
0x14001d544  mov     rcx, [rsi+40h]; Resource
0x14001d548  call    cs:__imp_FltReleaseResource
0x14001d54f  nop     dword ptr [rax+rax+00h]
0x14001d554  mov     rbx, [rsp+58h+arg_0]
0x14001d559  mov     rsi, [rsp+58h+arg_8]
0x14001d55e  add     rsp, 50h
0x14001d562  pop     rdi
0x14001d563  retn
```
