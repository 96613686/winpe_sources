# CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)

- ea: `0x18000f6b4`
- end: `0x18000f77d`
- name: `?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e5f8`
- `0x18000f5f8`

## callees

- `0x1800025e4`
- `0x1800029e8`
- `0x18000de94`
- `0x18000f6b4`
- `0x18000fd28`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntryFromGroup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int GroupIndex; // eax
  unsigned int Item; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 i; // r10
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r10
  int v15; // r11d
  __int64 v17; // [rsp+30h] [rbp+8h] BYREF

  v17 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(a1, a2, a3);
  Item = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(a2, GroupIndex, &v17);
  if ( !(unsigned int)ElValidateWin32_2(Item, v8, v9, 3361) )
  {
    v10 = v17;
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v17 + 20); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v17 + 8) + 8 * i) == a4 )
      {
        Item = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(v17 + 8, (unsigned int)i, &v17);
        if ( !Item )
        {
          memmove_0(
            (void *)(*(_QWORD *)(v10 + 8) + 8 * v14),
            (const void *)(*(_QWORD *)(v10 + 8) + 8LL * (unsigned int)(v14 + 1)),
            8LL * (unsigned int)(v15 - v14 - 1));
          --*(_DWORD *)(v10 + 20);
        }
        ElValidateWin32_2(Item, v12, v13, 3369);
        return Item;
      }
    }
  }
  return Item;
}

```

## disassembly

```asm
0x18000f6b4  mov     rax, rsp
0x18000f6b7  mov     [rax+10h], rbx
0x18000f6bb  mov     [rax+18h], rbp
0x18000f6bf  mov     [rax+20h], rsi
0x18000f6c3  mov     [rax+8], rcx
0x18000f6c7  push    rdi
0x18000f6c8  sub     rsp, 20h
0x18000f6cc  and     qword ptr [rax+8], 0
0x18000f6d1  mov     rbp, r9
0x18000f6d4  mov     rbx, rdx
0x18000f6d7  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000f6dc  lea     r8, [rsp+28h+arg_0]
0x18000f6e1  mov     edx, eax
0x18000f6e3  mov     rcx, rbx
0x18000f6e6  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f6eb  mov     ecx, eax
0x18000f6ed  mov     r9d, 0D21h
0x18000f6f3  mov     ebx, eax
0x18000f6f5  call    ElValidateWin32_2
0x18000f6fa  test    eax, eax
0x18000f6fc  jnz     short loc_18000F765
0x18000f6fe  mov     rdi, [rsp+28h+arg_0]
0x18000f703  xor     r10d, r10d
0x18000f706  mov     rax, [rdi+8]
0x18000f70a  mov     r11d, [rdi+14h]
0x18000f70e  cmp     r10d, r11d
0x18000f711  jnb     short loc_18000F765
0x18000f713  cmp     [rax+r10*8], rbp
0x18000f717  jz      short loc_18000F71E
0x18000f719  inc     r10d
0x18000f71c  jmp     short loc_18000F70E
0x18000f71e  lea     r8, [rsp+28h+arg_0]
0x18000f723  mov     edx, r10d
0x18000f726  lea     rcx, [rdi+8]
0x18000f72a  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000f72f  mov     ebx, eax
0x18000f731  test    eax, eax
0x18000f733  jnz     short loc_18000F758
0x18000f735  mov     r9, [rdi+8]
0x18000f739  lea     eax, [r10+1]
0x18000f73d  sub     r11d, r10d
0x18000f740  lea     rdx, [r9+rax*8]; Src
0x18000f744  lea     r8d, [r11-1]
0x18000f748  shl     r8, 3; Size
0x18000f74c  lea     rcx, [r9+r10*8]; void *
0x18000f750  call    memmove_0
0x18000f755  dec     dword ptr [rdi+14h]
0x18000f758  mov     r9d, 0D29h
0x18000f75e  mov     ecx, ebx
0x18000f760  call    ElValidateWin32_2
0x18000f765  mov     rbp, [rsp+28h+arg_10]
0x18000f76a  mov     eax, ebx
0x18000f76c  mov     rbx, [rsp+28h+arg_8]
0x18000f771  mov     rsi, [rsp+28h+arg_18]
0x18000f776  add     rsp, 20h
0x18000f77a  pop     rdi
0x18000f77b  retn
```
