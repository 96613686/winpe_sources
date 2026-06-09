# VmsTmFreeAllVMSPortsAndMacs

- ea: `0x14015bd78`
- end: `0x14015bf08`
- name: `VmsTmFreeAllVMSPortsAndMacs`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14015ba7c`

## callees

- `0x14015bd78`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015bdc4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015be4c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015bdc4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14015be4c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be19`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be8d`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be19`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14015be8d`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015bdfd`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015be71`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015bdfd`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14015be71`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015bdac`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015be34`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015bdac`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14015be34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bde9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015be5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bec2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bde9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015be5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bec2`

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
0x14015bd78  mov     r11, rsp
0x14015bd7b  mov     [r11+8], rbx
0x14015bd7f  mov     [r11+10h], rsi
0x14015bd83  push    rdi
0x14015bd84  sub     rsp, 50h
0x14015bd88  xorps   xmm0, xmm0
0x14015bd8b  lea     rsi, [rcx+648h]
0x14015bd92  mov     rbx, rcx
0x14015bd95  lea     rdx, [r11-38h]; Enumerator
0x14015bd99  xor     eax, eax
0x14015bd9b  mov     rcx, rsi; HashTable
0x14015bd9e  movups  xmmword ptr [rsp+58h+Enumerator.___u0], xmm0
0x14015bda3  movups  xmmword ptr [rsp+58h+Enumerator.___u0+10h], xmm0
0x14015bda8  mov     [r11-18h], rax
0x14015bdac  call    cs:__imp_RtlInitEnumerationHashTable
0x14015bdb3  nop     dword ptr [rax+rax+00h]
0x14015bdb8  test    al, al
0x14015bdba  jz      short loc_14015BE25
0x14015bdbc  jmp     short loc_14015BDF5
0x14015bdbe  xor     r8d, r8d; Context
0x14015bdc1  mov     rdx, rdi; Entry
0x14015bdc4  call    cs:__imp_RtlRemoveEntryHashTable
0x14015bdcb  nop     dword ptr [rax+rax+00h]
0x14015bdd0  mov     rax, [rdi+50h]
0x14015bdd4  test    rax, rax
0x14015bdd7  jz      short loc_14015BDE4
0x14015bdd9  mov     qword ptr [rax+2A50h], 0
0x14015bde4  xor     edx, edx; Tag
0x14015bde6  mov     rcx, rdi; P
0x14015bde9  call    cs:__imp_ExFreePoolWithTag
0x14015bdf0  nop     dword ptr [rax+rax+00h]
0x14015bdf5  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015bdfa  mov     rcx, rsi; HashTable
0x14015bdfd  call    cs:__imp_RtlEnumerateEntryHashTable
0x14015be04  nop     dword ptr [rax+rax+00h]
0x14015be09  mov     rdi, rax
0x14015be0c  mov     rcx, rsi; HashTable
0x14015be0f  test    rax, rax
0x14015be12  jnz     short loc_14015BDBE
0x14015be14  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be19  call    cs:__imp_RtlEndEnumerationHashTable
0x14015be20  nop     dword ptr [rax+rax+00h]
0x14015be25  lea     rdi, [rbx+670h]
0x14015be2c  mov     rcx, rdi; HashTable
0x14015be2f  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be34  call    cs:__imp_RtlInitEnumerationHashTable
0x14015be3b  nop     dword ptr [rax+rax+00h]
0x14015be40  test    al, al
0x14015be42  jz      short loc_14015BE99
0x14015be44  jmp     short loc_14015BE69
0x14015be46  xor     r8d, r8d; Context
0x14015be49  mov     rdx, rsi; Entry
0x14015be4c  call    cs:__imp_RtlRemoveEntryHashTable
0x14015be53  nop     dword ptr [rax+rax+00h]
0x14015be58  xor     edx, edx; Tag
0x14015be5a  mov     rcx, rsi; P
0x14015be5d  call    cs:__imp_ExFreePoolWithTag
0x14015be64  nop     dword ptr [rax+rax+00h]
0x14015be69  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be6e  mov     rcx, rdi; HashTable
0x14015be71  call    cs:__imp_RtlEnumerateEntryHashTable
0x14015be78  nop     dword ptr [rax+rax+00h]
0x14015be7d  mov     rsi, rax
0x14015be80  mov     rcx, rdi; HashTable
0x14015be83  test    rax, rax
0x14015be86  jnz     short loc_14015BE46
0x14015be88  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14015be8d  call    cs:__imp_RtlEndEnumerationHashTable
0x14015be94  nop     dword ptr [rax+rax+00h]
0x14015be99  mov     rax, [rbx+698h]
0x14015bea0  test    rax, rax
0x14015bea3  jz      short loc_14015BED9
0x14015bea5  mov     rcx, [rax+50h]
0x14015bea9  test    rcx, rcx
0x14015beac  jz      short loc_14015BEB9
0x14015beae  mov     qword ptr [rcx+2A50h], 0
0x14015beb9  mov     rcx, [rbx+698h]; P
0x14015bec0  xor     edx, edx; Tag
0x14015bec2  call    cs:__imp_ExFreePoolWithTag
0x14015bec9  nop     dword ptr [rax+rax+00h]
0x14015bece  mov     qword ptr [rbx+698h], 0
0x14015bed9  mov     rsi, [rsp+58h+arg_8]
0x14015bede  lea     rax, [rbx+908h]
0x14015bee5  mov     [rax+8], rax
0x14015bee9  mov     [rax], rax
0x14015beec  xor     eax, eax
0x14015beee  mov     [rbx+906h], ax
0x14015bef5  mov     [rbx+640h], ax
0x14015befc  mov     rbx, [rsp+58h+arg_0]
0x14015bf01  add     rsp, 50h
0x14015bf05  pop     rdi
0x14015bf06  retn
```
