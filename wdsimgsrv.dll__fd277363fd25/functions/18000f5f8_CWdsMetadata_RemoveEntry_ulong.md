# CWdsMetadata::RemoveEntry(ulong)

- ea: `0x18000f5f8`
- end: `0x18000f6ac`
- name: `?RemoveEntry@CWdsMetadata@@QEAAKK@Z`
- size: `180`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000dd58`
- `0x18000f784`

## callees

- `0x1800029e8`
- `0x18000d188`
- `0x18000f5f8`
- `0x18000f6b4`
- `0x18000f8a4`
- `0x18000fd28`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntry(CWdsMetadata *this, __int64 a2)
{
  unsigned int v3; // ebp
  __int64 Item; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  CWdsMetadataEntry *v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // edx
  CWdsMetadataEntry *v16; // [rsp+40h] [rbp+8h] BYREF

  v16 = 0;
  v3 = a2;
  Item = (unsigned int)CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem((char *)this + 48, a2, &v16);
  if ( !(unsigned int)ElValidateWin32_2(Item, v5, v6, 3403) )
  {
    v8 = v16;
    v9 = *((_QWORD *)v16 + 3);
    if ( !v9
      || (Item = (unsigned int)CWdsMetadata::RemoveEntryFromGroup(v7, (char *)this + 24, v9, v16),
          !(unsigned int)ElValidateWin32_2(Item, v10, v11, 3410)) )
    {
      CWdsMetadata::RemoveEntryFromGroup(v7, this, *(_QWORD *)v8, v8);
      LODWORD(Item) = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem((char *)this + 48, v3);
      if ( !(unsigned int)ElValidateWin32_2((unsigned int)Item, v12, v13, 3418) )
        CWdsMetadataEntry::`scalar deleting destructor'(v8, v14);
    }
  }
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x18000f5f8  mov     rax, rsp
0x18000f5fb  mov     [rax+10h], rbx
0x18000f5ff  mov     [rax+18h], rbp
0x18000f603  push    rsi
0x18000f604  push    rdi
0x18000f605  push    r14
0x18000f607  sub     rsp, 20h
0x18000f60b  and     qword ptr [rax+8], 0
0x18000f610  lea     r8, [rax+8]
0x18000f614  mov     rsi, rcx
0x18000f617  mov     ebp, edx
0x18000f619  add     rcx, 30h ; '0'
0x18000f61d  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f622  mov     ecx, eax
0x18000f624  mov     r9d, 0D4Bh
0x18000f62a  mov     edi, eax
0x18000f62c  call    ElValidateWin32_2
0x18000f631  test    eax, eax
0x18000f633  jnz     short loc_18000F696
0x18000f635  mov     rbx, [rsp+38h+arg_0]
0x18000f63a  mov     r8, [rbx+18h]
0x18000f63e  test    r8, r8
0x18000f641  jz      short loc_18000F662
0x18000f643  lea     rdx, [rsi+18h]
0x18000f647  mov     r9, rbx
0x18000f64a  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000f64f  mov     r9d, 0D52h
0x18000f655  mov     ecx, eax
0x18000f657  mov     edi, eax
0x18000f659  call    ElValidateWin32_2
0x18000f65e  test    eax, eax
0x18000f660  jnz     short loc_18000F696
0x18000f662  mov     r8, [rbx]
0x18000f665  mov     r9, rbx
0x18000f668  mov     rdx, rsi
0x18000f66b  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000f670  mov     edx, ebp
0x18000f672  lea     rcx, [rsi+30h]
0x18000f676  call    ?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)
0x18000f67b  mov     r9d, 0D5Ah
0x18000f681  mov     ecx, eax
0x18000f683  mov     edi, eax
0x18000f685  call    ElValidateWin32_2
0x18000f68a  test    eax, eax
0x18000f68c  jnz     short loc_18000F696
0x18000f68e  mov     rcx, rbx; this
0x18000f691  call    ??_GCWdsMetadataEntry@@QEAAPEAXI@Z; CWdsMetadataEntry::`scalar deleting destructor'(uint)
0x18000f696  mov     rbx, [rsp+38h+arg_8]
0x18000f69b  mov     eax, edi
0x18000f69d  mov     rbp, [rsp+38h+arg_10]
0x18000f6a2  add     rsp, 20h
0x18000f6a6  pop     r14
0x18000f6a8  pop     rdi
0x18000f6a9  pop     rsi
0x18000f6aa  retn
```
