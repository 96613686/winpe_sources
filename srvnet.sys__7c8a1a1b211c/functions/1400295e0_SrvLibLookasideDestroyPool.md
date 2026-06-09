# SrvLibLookasideDestroyPool

- ea: `0x1400295e0`
- end: `0x14002963f`
- name: `SrvLibLookasideDestroyPool`
- size: `95`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400295e0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002960b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002960b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029629`

## pseudocode

```c
void __fastcall SrvLibLookasideDestroyPool(struct _NPAGED_LOOKASIDE_LIST *P)
{
  struct _NPAGED_LOOKASIDE_LIST *v2; // rdi
  unsigned int v3; // ebp
  unsigned int i; // esi

  if ( P )
  {
    v2 = P;
    v3 = SrvNetNumberOfActiveProcessorsAtServerStart + 1;
    if ( (unsigned int)SrvNetNumberOfActiveProcessorsAtServerStart <= 1 )
      v3 = SrvNetNumberOfActiveProcessorsAtServerStart;
    for ( i = 0; i < v3; v2 = (struct _NPAGED_LOOKASIDE_LIST *)((char *)v2 + 192) )
    {
      ExDeleteNPagedLookasideList(v2);
      ++i;
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x1400295e0  test    rcx, rcx
0x1400295e3  jz      short locret_14002963D
0x1400295e5  push    rbx
0x1400295e6  push    rbp
0x1400295e7  push    rsi
0x1400295e8  push    rdi
0x1400295e9  sub     rsp, 28h
0x1400295ed  mov     eax, cs:SrvNetNumberOfActiveProcessorsAtServerStart
0x1400295f3  mov     rbx, rcx
0x1400295f6  cmp     eax, 1
0x1400295f9  mov     rdi, rcx
0x1400295fc  lea     ebp, [rax+1]
0x1400295ff  cmovbe  ebp, eax
0x140029602  xor     esi, esi
0x140029604  test    ebp, ebp
0x140029606  jz      short loc_140029624
0x140029608  mov     rcx, rdi; Lookaside
0x14002960b  call    cs:__imp_ExDeleteNPagedLookasideList
0x140029612  nop     dword ptr [rax+rax+00h]
0x140029617  inc     esi
0x140029619  add     rdi, 0C0h
0x140029620  cmp     esi, ebp
0x140029622  jb      short loc_140029608
0x140029624  xor     edx, edx; Tag
0x140029626  mov     rcx, rbx; P
0x140029629  call    cs:__imp_ExFreePoolWithTag
0x140029630  nop     dword ptr [rax+rax+00h]
0x140029635  add     rsp, 28h
0x140029639  pop     rdi
0x14002963a  pop     rsi
0x14002963b  pop     rbp
0x14002963c  pop     rbx
0x14002963d  retn
```
