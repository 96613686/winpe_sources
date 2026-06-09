# FreeConnection

- ea: `0x1400032dc`
- end: `0x14000333b`
- name: `FreeConnection`
- size: `95`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000d2e0`
- `0x14000f57c`
- `0x1400124bc`
- `0x140015db0`
- `0x140015f60`

## callees

- `0x140002d40`
- `0x1400032dc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003328`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003328`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f0`

## pseudocode

```c
void __fastcall FreeConnection(_QWORD *Entry)
{
  void *v2; // rcx

  v2 = (void *)Entry[7];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    Entry[7] = 0;
  }
  if ( *((_BYTE *)Entry + 248) )
  {
    DereferenceAdapterContext(Entry[1]);
    Entry[1] = 0;
  }
  ExFreeToNPagedLookasideList(&g_llConnBlocks, Entry);
}

```

## disassembly

```asm
0x1400032dc  push    rbx
0x1400032de  sub     rsp, 20h
0x1400032e2  mov     rbx, rcx
0x1400032e5  mov     rcx, [rcx+38h]; P
0x1400032e9  test    rcx, rcx
0x1400032ec  jz      short loc_140003304
0x1400032ee  xor     edx, edx; Tag
0x1400032f0  call    cs:__imp_ExFreePoolWithTag
0x1400032f7  nop     dword ptr [rax+rax+00h]
0x1400032fc  mov     qword ptr [rbx+38h], 0
0x140003304  cmp     byte ptr [rbx+0F8h], 0
0x14000330b  jz      short loc_14000331E
0x14000330d  mov     rcx, [rbx+8]
0x140003311  call    DereferenceAdapterContext
0x140003316  mov     qword ptr [rbx+8], 0
0x14000331e  mov     rdx, rbx; Entry
0x140003321  lea     rcx, g_llConnBlocks; Lookaside
0x140003328  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000332f  nop     dword ptr [rax+rax+00h]
0x140003334  add     rsp, 20h
0x140003338  pop     rbx
0x140003339  retn
```
