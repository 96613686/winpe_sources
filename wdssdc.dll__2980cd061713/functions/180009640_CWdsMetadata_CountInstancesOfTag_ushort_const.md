# CWdsMetadata::CountInstancesOfTag(ushort const *)

- ea: `0x180009640`
- end: `0x18000967c`
- name: `?CountInstancesOfTag@CWdsMetadata@@QEBAKPEBG@Z`
- size: `60`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055b0`
- `0x1800068d0`
- `0x18000b6d4`

## callees

- `0x180009640`
- `0x180009684`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::CountInstancesOfTag(CWdsMetadata *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  int GroupIndex; // eax

  v3 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex((__int64)this, (__int64 *)this, (__int64)a2);
  if ( GroupIndex >= 0 )
  {
    _mm_lfence();
    return *(unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 8LL * GroupIndex) + 20LL);
  }
  return v3;
}

```

## disassembly

```asm
0x180009640  mov     [rsp+arg_0], rbx
0x180009645  push    rdi
0x180009646  sub     rsp, 20h
0x18000964a  mov     r8, rdx
0x18000964d  mov     rdi, rcx
0x180009650  mov     rdx, rcx
0x180009653  xor     ebx, ebx
0x180009655  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000965a  test    eax, eax
0x18000965c  js      short loc_18000966E
0x18000965e  lfence
0x180009661  movsxd  rcx, eax
0x180009664  mov     rax, [rdi]
0x180009667  mov     rcx, [rax+rcx*8]
0x18000966b  mov     ebx, [rcx+14h]
0x18000966e  mov     eax, ebx
0x180009670  mov     rbx, [rsp+28h+arg_0]
0x180009675  add     rsp, 20h
0x180009679  pop     rdi
0x18000967a  retn
```
