# CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)

- ea: `0x18000ba40`
- end: `0x18000baf8`
- name: `?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008da0`
- `0x18000b960`

## callees

- `0x180009684`
- `0x18000ba40`
- `0x18000c274`
- `0x18000cc1c`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntryFromGroup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  unsigned int GroupIndex; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  __int64 v12; // r9
  _QWORD *i; // rax
  __int64 v14; // rdx
  __int64 v15; // r8

  v6 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(a1, a2, a3);
  v10 = 0;
  if ( GroupIndex < *(_DWORD *)(a2 + 12) )
  {
    _mm_lfence();
    v6 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * GroupIndex);
  }
  else
  {
    v10 = 1413;
  }
  if ( !(unsigned int)ElValidateWin32_1(v10, v8, v9, 3361) )
  {
    v11 = *(_DWORD *)(v6 + 20);
    v12 = 0;
    if ( v11 )
    {
      for ( i = *(_QWORD **)(v6 + 8); *i != a4; ++i )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v11 )
          return v10;
      }
      v10 = 0;
      memmove_0(
        (void *)(*(_QWORD *)(v6 + 8) + 8 * v12),
        (const void *)(*(_QWORD *)(v6 + 8) + 8LL * (unsigned int)(v12 + 1)),
        8LL * (v11 + ~(_DWORD)v12));
      --*(_DWORD *)(v6 + 20);
      ElValidateWin32_1(0, v14, v15, 3369);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_0], rbx
0x18000ba45  mov     [rsp+arg_8], rbp
0x18000ba4a  mov     [rsp+arg_10], rsi
0x18000ba4f  push    rdi
0x18000ba50  sub     rsp, 20h
0x18000ba54  mov     rbp, r9
0x18000ba57  mov     rsi, rdx
0x18000ba5a  xor     edi, edi
0x18000ba5c  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000ba61  xor     ebx, ebx
0x18000ba63  cmp     eax, [rsi+0Ch]
0x18000ba66  jb      short loc_18000BA6F
0x18000ba68  mov     ebx, 585h
0x18000ba6d  jmp     short loc_18000BA7B
0x18000ba6f  lfence
0x18000ba72  mov     ecx, eax
0x18000ba74  mov     rax, [rsi]
0x18000ba77  mov     rdi, [rax+rcx*8]
0x18000ba7b  mov     r9d, 0D21h
0x18000ba81  mov     ecx, ebx
0x18000ba83  call    ElValidateWin32_1
0x18000ba88  test    eax, eax
0x18000ba8a  jnz     short loc_18000BAE0
0x18000ba8c  mov     ecx, [rdi+14h]
0x18000ba8f  xor     r9d, r9d
0x18000ba92  mov     r10, [rdi+8]
0x18000ba96  test    ecx, ecx
0x18000ba98  jz      short loc_18000BAE0
0x18000ba9a  mov     rax, r10
0x18000ba9d  cmp     [rax], rbp
0x18000baa0  jz      short loc_18000BAB0
0x18000baa2  inc     r9d
0x18000baa5  add     rax, 8
0x18000baa9  cmp     r9d, ecx
0x18000baac  jb      short loc_18000BA9D
0x18000baae  jmp     short loc_18000BAE0
0x18000bab0  mov     r8d, r9d
0x18000bab3  lea     eax, [r9+1]
0x18000bab7  not     r8d
0x18000baba  lea     rdx, [r10+rax*8]; Src
0x18000babe  add     r8d, ecx
0x18000bac1  xor     ebx, ebx
0x18000bac3  shl     r8, 3; Size
0x18000bac7  lea     rcx, [r10+r9*8]; void *
0x18000bacb  call    memmove_0
0x18000bad0  dec     dword ptr [rdi+14h]
0x18000bad3  mov     r9d, 0D29h
0x18000bad9  mov     ecx, ebx
0x18000badb  call    ElValidateWin32_1
0x18000bae0  mov     rbp, [rsp+28h+arg_8]
0x18000bae5  mov     eax, ebx
0x18000bae7  mov     rbx, [rsp+28h+arg_0]
0x18000baec  mov     rsi, [rsp+28h+arg_10]
0x18000baf1  add     rsp, 20h
0x18000baf5  pop     rdi
0x18000baf6  retn
```
