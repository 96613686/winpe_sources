# FreeDataBuffer

- ea: `0x14000ef98`
- end: `0x14000f099`
- name: `FreeDataBuffer`
- size: `257`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000c624`
- `0x14000f0a0`
- `0x1400138b0`
- `0x1400142e8`

## callees

- `0x14000ef98`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000f05e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000f05e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000efcd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000efcd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000f01d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000f01d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f075`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f075`

## pseudocode

```c
__int64 __fastcall FreeDataBuffer(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v6; // rcx
  __int64 result; // rax

  if ( *(_QWORD *)a2 )
  {
    if ( (*(_DWORD *)(a2 + 36) & 1) != 0 )
    {
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 48) + 320LL), *(PVOID *)a2);
      v4 = *(_QWORD *)(a1 + 48);
      if ( (*(_DWORD *)(v4 + 284))-- == 1 && (*(_DWORD *)(a1 + 32) & 0x8000) == 0 )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 48) + 276LL) += 100;
        *(_DWORD *)(*(_QWORD *)(a1 + 48) + 280LL) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 276LL);
        v6 = *(_QWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 32) |= 0x8000u;
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v6 + 320));
        ExInitializeNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 48) + 320LL),
          0,
          0,
          0x200u,
          *(unsigned int *)(*(_QWORD *)(a1 + 48) + 280LL),
          0x446D6750u,
          *(_WORD *)(*(_QWORD *)(a1 + 48) + 288LL));
      }
      *(_DWORD *)(a2 + 36) &= ~1u;
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)a2, 0);
    }
    result = 0;
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000ef98  mov     [rsp+arg_0], rbx
0x14000ef9d  push    rdi
0x14000ef9e  sub     rsp, 40h
0x14000efa2  mov     r8, [rdx]
0x14000efa5  mov     rbx, rdx
0x14000efa8  mov     rdi, rcx
0x14000efab  test    r8, r8
0x14000efae  jz      loc_14000F08D
0x14000efb4  mov     eax, [rdx+24h]
0x14000efb7  test    al, 1
0x14000efb9  jz      loc_14000F070
0x14000efbf  mov     rcx, [rcx+30h]
0x14000efc3  mov     rdx, r8; Entry
0x14000efc6  add     rcx, 140h; Lookaside
0x14000efcd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000efd4  nop     dword ptr [rax+rax+00h]
0x14000efd9  mov     rax, [rdi+30h]
0x14000efdd  add     dword ptr [rax+11Ch], 0FFFFFFFFh
0x14000efe4  jnz     loc_14000F06A
0x14000efea  mov     edx, 8000h
0x14000efef  test    [rdi+20h], edx
0x14000eff2  jnz     short loc_14000F06A
0x14000eff4  mov     rax, [rdi+30h]
0x14000eff8  add     dword ptr [rax+114h], 64h ; 'd'
0x14000efff  mov     rcx, [rdi+30h]
0x14000f003  mov     eax, [rcx+114h]
0x14000f009  mov     [rcx+118h], eax
0x14000f00f  mov     rcx, [rdi+30h]
0x14000f013  or      [rdi+20h], edx
0x14000f016  add     rcx, 140h; Lookaside
0x14000f01d  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000f024  nop     dword ptr [rax+rax+00h]
0x14000f029  mov     rax, [rdi+30h]
0x14000f02d  mov     r9d, 200h; Flags
0x14000f033  xor     r8d, r8d; Free
0x14000f036  mov     edx, [rax+118h]
0x14000f03c  lea     rcx, [rax+140h]; Lookaside
0x14000f043  movzx   eax, word ptr [rax+120h]
0x14000f04a  mov     [rsp+48h+Depth], ax; Depth
0x14000f04f  mov     [rsp+48h+Tag], 446D6750h; Tag
0x14000f057  mov     [rsp+48h+Size], rdx; Size
0x14000f05c  xor     edx, edx; Allocate
0x14000f05e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000f065  nop     dword ptr [rax+rax+00h]
0x14000f06a  and     dword ptr [rbx+24h], 0FFFFFFFEh
0x14000f06e  jmp     short loc_14000F081
0x14000f070  xor     edx, edx; Tag
0x14000f072  mov     rcx, r8; P
0x14000f075  call    cs:__imp_ExFreePoolWithTag
0x14000f07c  nop     dword ptr [rax+rax+00h]
0x14000f081  xor     eax, eax
0x14000f083  mov     qword ptr [rbx], 0
0x14000f08a  mov     [rbx+10h], eax
0x14000f08d  mov     rbx, [rsp+48h+arg_0]
0x14000f092  add     rsp, 40h
0x14000f096  pop     rdi
0x14000f097  retn
```
