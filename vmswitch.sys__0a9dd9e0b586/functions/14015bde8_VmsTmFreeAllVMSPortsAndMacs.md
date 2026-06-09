# VmsTmFreeAllVMSPortsAndMacs

- ea: `0x14015bde8`
- end: `0x14015bf78`
- name: `VmsTmFreeAllVMSPortsAndMacs`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14015baec`

## callees

- `0x14015bde8`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015be34`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015bebc`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015be34`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015bebc`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be89`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015befd`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be89`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015befd`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015be6d`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015bee1`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015be6d`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015bee1`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015be1c`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015bea4`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015be1c`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015bea4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015be59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015becd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bf32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015be59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015becd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bf32`

## pseudocode

```c
__int64 __fastcall VmsTmFreeAllVMSPortsAndMacs(__int64 a1)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v1; // rsi
  _LIST_ENTRY *Blink; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v4; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v5; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v6; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 result; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  v1 = (struct _RTL_DYNAMIC_HASH_TABLE *)(a1 + 1608);
  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1608), &Enumerator) )
  {
    while ( 1 )
    {
      v4 = RtlEnumerateEntryHashTable(v1, &Enumerator);
      v5 = v4;
      if ( !v4 )
        break;
      RtlRemoveEntryHashTable(v1, v4, 0);
      Blink = v5[3].Linkage.Blink;
      if ( Blink )
        Blink[677].Flink = 0;
      ExFreePoolWithTag(v5, 0);
    }
    RtlEndEnumerationHashTable(v1, &Enumerator);
  }
  if ( RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1648), &Enumerator) )
  {
    while ( 1 )
    {
      v6 = RtlEnumerateEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 1648), &Enumerator);
      v7 = v6;
      v8 = (struct _RTL_DYNAMIC_HASH_TABLE *)(a1 + 1648);
      if ( !v6 )
        break;
      RtlRemoveEntryHashTable(v8, v6, 0);
      ExFreePoolWithTag(v7, 0);
    }
    RtlEndEnumerationHashTable(v8, &Enumerator);
  }
  v9 = *(_QWORD *)(a1 + 1688);
  if ( v9 )
  {
    v10 = *(_QWORD *)(v9 + 80);
    if ( v10 )
      *(_QWORD *)(v10 + 10832) = 0;
    ExFreePoolWithTag(*(PVOID *)(a1 + 1688), 0);
    *(_QWORD *)(a1 + 1688) = 0;
  }
  *(_QWORD *)(a1 + 2320) = a1 + 2312;
  *(_QWORD *)(a1 + 2312) = a1 + 2312;
  result = 0;
  *(_WORD *)(a1 + 2310) = 0;
  *(_WORD *)(a1 + 1600) = 0;
  return result;
}

```

## disassembly

```asm
0x14015bde8  mov     r11, rsp
0x14015bdeb  mov     [r11+8], rbx
0x14015bdef  mov     [r11+10h], rsi
0x14015bdf3  push    rdi
0x14015bdf4  sub     rsp, 50h
0x14015bdf8  xorps   xmm0, xmm0
0x14015bdfb  lea     rsi, [rcx+648h]
0x14015be02  mov     rbx, rcx
0x14015be05  lea     rdx, [r11-38h]; Enumerator
0x14015be09  xor     eax, eax
0x14015be0b  mov     rcx, rsi; HashTable
0x14015be0e  movups  xmmword ptr [rsp+58h+Enumerator.___u0], xmm0
0x14015be13  movups  xmmword ptr [rsp+58h+Enumerator.___u0+10h], xmm0
0x14015be18  mov     [r11-18h], rax
0x14015be1c  call    cs:__imp_RtlInitEnumerationHashTable
0x14015be23  nop     dword ptr [rax+rax+00h]
0x14015be28  test    al, al
0x14015be2a  jz      short loc_14015BE95
0x14015be2c  jmp     short loc_14015BE65
0x14015be2e  xor     r8d, r8d; Context
0x14015be31  mov     rdx, rdi; Entry
0x14015be34  call    cs:__imp_RtlRemoveEntryHashTable
0x14015be3b  nop     dword ptr [rax+rax+00h]
0x14015be40  mov     rax, [rdi+50h]
0x14015be44  test    rax, rax
0x14015be47  jz      short loc_14015BE54
0x14015be49  mov     qword ptr [rax+2A50h], 0
0x14015be54  xor     edx, edx; Tag
0x14015be56  mov     rcx, rdi; P
0x14015be59  call    cs:__imp_ExFreePoolWithTag
0x14015be60  nop     dword ptr [rax+rax+00h]
0x14015be65  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be6a  mov     rcx, rsi; HashTable
0x14015be6d  call    cs:__imp_RtlEnumerateEntryHashTable
0x14015be74  nop     dword ptr [rax+rax+00h]
0x14015be79  mov     rdi, rax
0x14015be7c  mov     rcx, rsi; HashTable
0x14015be7f  test    rax, rax
0x14015be82  jnz     short loc_14015BE2E
0x14015be84  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be89  call    cs:__imp_RtlEndEnumerationHashTable
0x14015be90  nop     dword ptr [rax+rax+00h]
0x14015be95  lea     rdi, [rbx+670h]
0x14015be9c  mov     rcx, rdi; HashTable
0x14015be9f  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015bea4  call    cs:__imp_RtlInitEnumerationHashTable
0x14015beab  nop     dword ptr [rax+rax+00h]
0x14015beb0  test    al, al
0x14015beb2  jz      short loc_14015BF09
0x14015beb4  jmp     short loc_14015BED9
0x14015beb6  xor     r8d, r8d; Context
0x14015beb9  mov     rdx, rsi; Entry
0x14015bebc  call    cs:__imp_RtlRemoveEntryHashTable
0x14015bec3  nop     dword ptr [rax+rax+00h]
0x14015bec8  xor     edx, edx; Tag
0x14015beca  mov     rcx, rsi; P
0x14015becd  call    cs:__imp_ExFreePoolWithTag
0x14015bed4  nop     dword ptr [rax+rax+00h]
0x14015bed9  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015bede  mov     rcx, rdi; HashTable
0x14015bee1  call    cs:__imp_RtlEnumerateEntryHashTable
0x14015bee8  nop     dword ptr [rax+rax+00h]
0x14015beed  mov     rsi, rax
0x14015bef0  mov     rcx, rdi; HashTable
0x14015bef3  test    rax, rax
0x14015bef6  jnz     short loc_14015BEB6
0x14015bef8  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015befd  call    cs:__imp_RtlEndEnumerationHashTable
0x14015bf04  nop     dword ptr [rax+rax+00h]
0x14015bf09  mov     rax, [rbx+698h]
0x14015bf10  test    rax, rax
0x14015bf13  jz      short loc_14015BF49
0x14015bf15  mov     rcx, [rax+50h]
0x14015bf19  test    rcx, rcx
0x14015bf1c  jz      short loc_14015BF29
0x14015bf1e  mov     qword ptr [rcx+2A50h], 0
0x14015bf29  mov     rcx, [rbx+698h]; P
0x14015bf30  xor     edx, edx; Tag
0x14015bf32  call    cs:__imp_ExFreePoolWithTag
0x14015bf39  nop     dword ptr [rax+rax+00h]
0x14015bf3e  mov     qword ptr [rbx+698h], 0
0x14015bf49  mov     rsi, [rsp+58h+arg_8]
0x14015bf4e  lea     rax, [rbx+908h]
0x14015bf55  mov     [rax+8], rax
0x14015bf59  mov     [rax], rax
0x14015bf5c  xor     eax, eax
0x14015bf5e  mov     [rbx+906h], ax
0x14015bf65  mov     [rbx+640h], ax
0x14015bf6c  mov     rbx, [rsp+58h+arg_0]
0x14015bf71  add     rsp, 50h
0x14015bf75  pop     rdi
0x14015bf76  retn
```
