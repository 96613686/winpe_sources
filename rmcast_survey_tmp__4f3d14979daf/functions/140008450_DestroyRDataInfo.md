# DestroyRDataInfo

- ea: `0x140008450`
- end: `0x1400084b6`
- name: `DestroyRDataInfo`
- size: `102`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140036d5c`
- `0x1400373f8`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000846c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000846c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000847e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000848f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000847e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000848f`

## pseudocode

```c
__int64 __fastcall DestroyRDataInfo(__int64 a1)
{
  __int64 v2; // rbx
  __int64 result; // rax

  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 264LL);
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v2 + 64));
  ExFreePoolWithTag(*(PVOID *)(v2 + 56), 0);
  ExFreePoolWithTag((PVOID)v2, 0);
  result = *(_QWORD *)(a1 + 40);
  *(_QWORD *)(result + 264) = 0;
  return result;
}

```

## disassembly

```asm
0x140008450  mov     [rsp+arg_0], rbx
0x140008455  push    rdi
0x140008456  sub     rsp, 20h
0x14000845a  mov     rax, [rcx+28h]
0x14000845e  mov     rdi, rcx
0x140008461  mov     rbx, [rax+108h]
0x140008468  lea     rcx, [rbx+40h]; Lookaside
0x14000846c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140008473  nop     dword ptr [rax+rax+00h]
0x140008478  mov     rcx, [rbx+38h]; P
0x14000847c  xor     edx, edx; Tag
0x14000847e  call    cs:__imp_ExFreePoolWithTag
0x140008485  nop     dword ptr [rax+rax+00h]
0x14000848a  xor     edx, edx; Tag
0x14000848c  mov     rcx, rbx; P
0x14000848f  call    cs:__imp_ExFreePoolWithTag
0x140008496  nop     dword ptr [rax+rax+00h]
0x14000849b  mov     rax, [rdi+28h]
0x14000849f  mov     rbx, [rsp+28h+arg_0]
0x1400084a4  mov     qword ptr [rax+108h], 0
0x1400084af  add     rsp, 20h
0x1400084b3  pop     rdi
0x1400084b4  retn
```
