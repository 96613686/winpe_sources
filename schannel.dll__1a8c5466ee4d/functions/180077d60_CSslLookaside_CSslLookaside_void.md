# CSslLookaside::~CSslLookaside(void)

- ea: `0x180077d60`
- end: `0x180077db9`
- name: `??1CSslLookaside@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CSslLookaside *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180077dc0`
- `0x180077e00`

## callees

- `0x180014240`
- `0x180077d60`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180077d8f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180077d8f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180077d9e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180077d9e`

## pseudocode

```c
void __fastcall CSslLookaside::~CSslLookaside(CSslLookaside *this)
{
  bool v1; // zf
  union _SLIST_HEADER *i; // rcx
  PSLIST_ENTRY v4; // rax

  v1 = *((_BYTE *)this + 32) == 0;
  *(_QWORD *)this = &CSslLookaside::`vftable';
  if ( !v1 )
  {
    for ( i = (union _SLIST_HEADER *)((char *)this + 16); ; i = (union _SLIST_HEADER *)((char *)this + 16) )
    {
      v4 = InterlockedPopEntrySList(i);
      if ( !v4 )
        break;
      SPExternalFree(v4);
    }
  }
  InterlockedFlushSList((PSLIST_HEADER)this + 1);
  *(_QWORD *)this = &IAllocate::`vftable';
}

```

## disassembly

```asm
0x180077d60  mov     [rsp+arg_0], rbx
0x180077d65  push    rdi
0x180077d66  sub     rsp, 20h
0x180077d6a  cmp     byte ptr [rcx+20h], 0
0x180077d6e  lea     rax, ??_7CSslLookaside@@6B@; const CSslLookaside::`vftable'
0x180077d75  mov     [rcx], rax
0x180077d78  mov     rbx, rcx
0x180077d7b  jz      short loc_180077D9A
0x180077d7d  add     rcx, 10h
0x180077d81  jmp     short loc_180077D8F
0x180077d83  mov     rcx, rax; void *
0x180077d86  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180077d8b  lea     rcx, [rbx+10h]; ListHead
0x180077d8f  call    cs:__imp_InterlockedPopEntrySList
0x180077d95  test    rax, rax
0x180077d98  jnz     short loc_180077D83
0x180077d9a  lea     rcx, [rbx+10h]; ListHead
0x180077d9e  call    cs:__imp_InterlockedFlushSList
0x180077da4  lea     rax, ??_7IAllocate@@6B@; const IAllocate::`vftable'
0x180077dab  mov     [rbx], rax
0x180077dae  mov     rbx, [rsp+28h+arg_0]
0x180077db3  add     rsp, 20h
0x180077db7  pop     rdi
0x180077db8  retn
```
