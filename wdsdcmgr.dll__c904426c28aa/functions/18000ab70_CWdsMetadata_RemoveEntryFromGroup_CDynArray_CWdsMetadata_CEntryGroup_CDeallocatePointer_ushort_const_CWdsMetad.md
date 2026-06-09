# CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)

- ea: `0x18000ab70`
- end: `0x18000ac49`
- name: `?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a970`
- `0x18000ac50`

## callees

- `0x18000a7ec`
- `0x18000ab70`
- `0x180014d58`
- `0x180015c91`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntryFromGroup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  unsigned int GroupIndex; // eax
  const char *v8; // rdx
  unsigned int v9; // ebx
  const char *v10; // rdx
  _QWORD *v11; // rax
  __int64 v12; // r10
  unsigned int v13; // eax

  v6 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(a1, a2, a3);
  v9 = 0;
  if ( GroupIndex < *(_DWORD *)(a2 + 12) )
  {
    _mm_lfence();
    v6 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * GroupIndex);
  }
  else
  {
    v9 = 1413;
  }
  if ( !ElValidateWin32(v9, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xD21u) )
  {
    v11 = *(_QWORD **)(v6 + 8);
    v12 = 0;
    if ( *(_DWORD *)(v6 + 20) )
    {
      while ( *v11 != a4 )
      {
        v12 = (unsigned int)(v12 + 1);
        ++v11;
        if ( (unsigned int)v12 >= *(_DWORD *)(v6 + 20) )
          return v9;
      }
      v13 = *(_DWORD *)(v6 + 20);
      v9 = (unsigned int)v12 >= v13 ? 0x585 : 0;
      if ( (unsigned int)v12 < v13 )
      {
        memmove_0(
          (void *)(*(_QWORD *)(v6 + 8) + 8 * v12),
          (const void *)(*(_QWORD *)(v6 + 8) + 8LL * (unsigned int)(v12 + 1)),
          8LL * (v13 - (unsigned int)v12 - 1));
        --*(_DWORD *)(v6 + 20);
        v9 = 0;
      }
      ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xD29u);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000ab70  mov     [rsp+arg_0], rbx
0x18000ab75  mov     [rsp+arg_8], rbp
0x18000ab7a  mov     [rsp+arg_10], rsi
0x18000ab7f  push    rdi
0x18000ab80  sub     rsp, 20h
0x18000ab84  mov     rbp, r9
0x18000ab87  mov     rsi, rdx
0x18000ab8a  xor     edi, edi
0x18000ab8c  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000ab91  xor     ebx, ebx
0x18000ab93  cmp     eax, [rsi+0Ch]
0x18000ab96  jb      short loc_18000AB9F
0x18000ab98  mov     ebx, 585h
0x18000ab9d  jmp     short loc_18000ABAB
0x18000ab9f  lfence
0x18000aba2  mov     ecx, eax
0x18000aba4  mov     rax, [rsi]
0x18000aba7  mov     rdi, [rax+rcx*8]
0x18000abab  mov     r9d, 0D21h; unsigned int
0x18000abb1  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000abb8  mov     ecx, ebx; unsigned int
0x18000abba  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000abbf  test    eax, eax
0x18000abc1  jnz     short loc_18000AC32
0x18000abc3  mov     rax, [rdi+8]
0x18000abc7  xor     r10d, r10d
0x18000abca  cmp     [rdi+14h], r10d
0x18000abce  jbe     short loc_18000AC32
0x18000abd0  cmp     [rax], rbp
0x18000abd3  jz      short loc_18000ABE4
0x18000abd5  inc     r10d
0x18000abd8  add     rax, 8
0x18000abdc  cmp     r10d, [rdi+14h]
0x18000abe0  jb      short loc_18000ABD0
0x18000abe2  jmp     short loc_18000AC32
0x18000abe4  mov     eax, [rdi+14h]
0x18000abe7  cmp     r10d, eax
0x18000abea  sbb     ebx, ebx
0x18000abec  not     ebx
0x18000abee  and     ebx, 585h
0x18000abf4  cmp     r10d, eax
0x18000abf7  jnb     short loc_18000AC1E
0x18000abf9  mov     r9, [rdi+8]
0x18000abfd  sub     eax, r10d
0x18000ac00  lea     r8d, [rax-1]
0x18000ac04  lea     eax, [r10+1]
0x18000ac08  shl     r8, 3; Size
0x18000ac0c  lea     rdx, [r9+rax*8]; Src
0x18000ac10  lea     rcx, [r9+r10*8]; void *
0x18000ac14  call    memmove_0
0x18000ac19  dec     dword ptr [rdi+14h]
0x18000ac1c  xor     ebx, ebx
0x18000ac1e  mov     r9d, 0D29h; unsigned int
0x18000ac24  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ac2b  mov     ecx, ebx; unsigned int
0x18000ac2d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ac32  mov     rbp, [rsp+28h+arg_8]
0x18000ac37  mov     eax, ebx
0x18000ac39  mov     rbx, [rsp+28h+arg_0]
0x18000ac3e  mov     rsi, [rsp+28h+arg_10]
0x18000ac43  add     rsp, 20h
0x18000ac47  pop     rdi
0x18000ac48  retn
```
