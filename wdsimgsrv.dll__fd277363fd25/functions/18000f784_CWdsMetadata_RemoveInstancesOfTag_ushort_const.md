# CWdsMetadata::RemoveInstancesOfTag(ushort const *)

- ea: `0x18000f784`
- end: `0x18000f89b`
- name: `?RemoveInstancesOfTag@CWdsMetadata@@QEAAKPEBG@Z`
- size: `279`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006020`

## callees

- `0x1800029e8`
- `0x18000de94`
- `0x18000f5f8`
- `0x18000f784`
- `0x18000fd28`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveInstancesOfTag(CWdsMetadata *this, const unsigned __int16 *a2)
{
  unsigned int Item; // ebx
  int GroupIndex; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rbp
  unsigned int v8; // r14d
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r15
  unsigned int i; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v18; // [rsp+40h] [rbp+8h] BYREF

  Item = 0;
  v18 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(this, this, a2);
  if ( GroupIndex >= 0 )
  {
    Item = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(this, (unsigned int)GroupIndex, &v18);
    if ( !(unsigned int)ElValidateWin32_2(Item, v5, v6, 5165) )
    {
      v7 = v18;
      do
      {
        if ( !*(_DWORD *)(v7 + 20) )
          break;
        v18 = 0;
        v8 = -1;
        Item = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(v7 + 8, 0, &v18);
        if ( (unsigned int)ElValidateWin32_2(Item, v9, v10, 5173) )
          break;
        v11 = v18;
        for ( i = 0; i < *((_DWORD *)this + 15); ++i )
        {
          v18 = 0;
          Item = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem((char *)this + 48, i, &v18);
          if ( (unsigned int)ElValidateWin32_2(Item, v13, v14, 5180) )
            return Item;
          if ( v18 == v11 )
          {
            v8 = i;
            break;
          }
        }
        Item = CWdsMetadata::RemoveEntry(this, v8);
      }
      while ( !(unsigned int)ElValidateWin32_2(Item, v15, v16, 5190) );
    }
  }
  return Item;
}

```

## disassembly

```asm
0x18000f784  mov     rax, rsp
0x18000f787  mov     [rax+10h], rbx
0x18000f78b  mov     [rax+18h], rbp
0x18000f78f  mov     [rax+20h], rsi
0x18000f793  push    rdi
0x18000f794  push    r14
0x18000f796  push    r15
0x18000f798  sub     rsp, 20h
0x18000f79c  mov     r8, rdx
0x18000f79f  xor     ebx, ebx
0x18000f7a1  and     [rax+8], rbx
0x18000f7a5  mov     rdx, rcx
0x18000f7a8  mov     rsi, rcx
0x18000f7ab  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000f7b0  test    eax, eax
0x18000f7b2  js      loc_18000F87F
0x18000f7b8  lea     r8, [rsp+38h+arg_0]
0x18000f7bd  mov     edx, eax
0x18000f7bf  mov     rcx, rsi
0x18000f7c2  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f7c7  mov     ecx, eax
0x18000f7c9  mov     r9d, 142Dh
0x18000f7cf  mov     ebx, eax
0x18000f7d1  call    ElValidateWin32_2
0x18000f7d6  test    eax, eax
0x18000f7d8  jnz     loc_18000F87F
0x18000f7de  mov     rbp, [rsp+38h+arg_0]
0x18000f7e3  cmp     dword ptr [rbp+14h], 0
0x18000f7e7  jz      loc_18000F87F
0x18000f7ed  and     [rsp+38h+arg_0], 0
0x18000f7f3  lea     rcx, [rbp+8]
0x18000f7f7  lea     r8, [rsp+38h+arg_0]
0x18000f7fc  xor     edx, edx
0x18000f7fe  or      r14d, 0FFFFFFFFh
0x18000f802  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f807  mov     ecx, eax
0x18000f809  mov     r9d, 1435h
0x18000f80f  mov     ebx, eax
0x18000f811  call    ElValidateWin32_2
0x18000f816  test    eax, eax
0x18000f818  jnz     short loc_18000F87F
0x18000f81a  mov     r15, [rsp+38h+arg_0]
0x18000f81f  xor     edi, edi
0x18000f821  cmp     edi, [rsi+3Ch]
0x18000f824  jnb     short loc_18000F85D
0x18000f826  and     [rsp+38h+arg_0], 0
0x18000f82c  lea     rcx, [rsi+30h]
0x18000f830  lea     r8, [rsp+38h+arg_0]
0x18000f835  mov     edx, edi
0x18000f837  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f83c  mov     ecx, eax
0x18000f83e  mov     r9d, 143Ch
0x18000f844  mov     ebx, eax
0x18000f846  call    ElValidateWin32_2
0x18000f84b  test    eax, eax
0x18000f84d  jnz     short loc_18000F87F
0x18000f84f  cmp     [rsp+38h+arg_0], r15
0x18000f854  jz      short loc_18000F85A
0x18000f856  inc     edi
0x18000f858  jmp     short loc_18000F821
0x18000f85a  mov     r14d, edi
0x18000f85d  mov     edx, r14d; unsigned int
0x18000f860  mov     rcx, rsi; this
0x18000f863  call    ?RemoveEntry@CWdsMetadata@@QEAAKK@Z; CWdsMetadata::RemoveEntry(ulong)
0x18000f868  mov     r9d, 1446h
0x18000f86e  mov     ecx, eax
0x18000f870  mov     ebx, eax
0x18000f872  call    ElValidateWin32_2
0x18000f877  test    eax, eax
0x18000f879  jz      loc_18000F7E3
0x18000f87f  mov     rbp, [rsp+38h+arg_10]
0x18000f884  mov     eax, ebx
0x18000f886  mov     rbx, [rsp+38h+arg_8]
0x18000f88b  mov     rsi, [rsp+38h+arg_18]
0x18000f890  add     rsp, 20h
0x18000f894  pop     r15
0x18000f896  pop     r14
0x18000f898  pop     rdi
0x18000f899  retn
```
