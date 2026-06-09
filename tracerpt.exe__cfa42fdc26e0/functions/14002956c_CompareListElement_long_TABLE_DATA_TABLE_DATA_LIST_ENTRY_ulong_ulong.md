# CompareListElement(long,_TABLE_DATA *,_TABLE_DATA *,_LIST_ENTRY *,ulong,ulong)

- ea: `0x14002956c`
- end: `0x1400295df`
- name: `?CompareListElement@@YAHJPEAU_TABLE_DATA@@0PEAU_LIST_ENTRY@@KK@Z`
- size: `115`
- prototype: `LONG __fastcall(int, struct _TABLE_DATA *, struct _TABLE_DATA *, struct _LIST_ENTRY *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002de10`

## callees

- `0x140029454`
- `0x14002956c`
- `0x14002cbbc`

## pseudocode

```c
LONG __fastcall CompareListElement(
        int a1,
        struct _TABLE_DATA *a2,
        struct _TABLE_DATA *a3,
        struct _LIST_ENTRY *a4,
        unsigned int a5,
        unsigned int a6)
{
  struct _ITEM_DATA *v10; // rbx
  struct _ITEM_DATA *v11; // rax

  v10 = ListSelectItemData(a2, a3, a4, a5, a1);
  if ( v10 && (v11 = ListSelectItemData(a2, a3, a4, a6, a1)) != 0 )
    return CompareItemData(v10, v11);
  else
    return 0;
}

```

## disassembly

```asm
0x14002956c  push    rbx
0x14002956e  push    rbp
0x14002956f  push    rsi
0x140029570  push    rdi
0x140029571  push    r14
0x140029573  sub     rsp, 30h
0x140029577  mov     rdi, r9
0x14002957a  mov     [rsp+58h+var_38], ecx; int
0x14002957e  mov     r9d, [rsp+58h+arg_20]; unsigned int
0x140029586  mov     rsi, r8
0x140029589  mov     rbp, rdx
0x14002958c  mov     r14d, ecx
0x14002958f  mov     r8, rdi; struct _LIST_ENTRY *
0x140029592  mov     rdx, rsi; struct _TABLE_DATA *
0x140029595  mov     rcx, rbp; struct _TABLE_DATA *
0x140029598  call    ?ListSelectItemData@@YAPEAU_ITEM_DATA@@PEAU_TABLE_DATA@@0PEAU_LIST_ENTRY@@KJ@Z; ListSelectItemData(_TABLE_DATA *,_TABLE_DATA *,_LIST_ENTRY *,ulong,long)
0x14002959d  mov     rbx, rax
0x1400295a0  test    rax, rax
0x1400295a3  jz      short loc_1400295D2
0x1400295a5  mov     r9d, [rsp+58h+arg_28]; unsigned int
0x1400295ad  mov     r8, rdi; struct _LIST_ENTRY *
0x1400295b0  mov     rdx, rsi; struct _TABLE_DATA *
0x1400295b3  mov     [rsp+58h+var_38], r14d; int
0x1400295b8  mov     rcx, rbp; struct _TABLE_DATA *
0x1400295bb  call    ?ListSelectItemData@@YAPEAU_ITEM_DATA@@PEAU_TABLE_DATA@@0PEAU_LIST_ENTRY@@KJ@Z; ListSelectItemData(_TABLE_DATA *,_TABLE_DATA *,_LIST_ENTRY *,ulong,long)
0x1400295c0  test    rax, rax
0x1400295c3  jz      short loc_1400295D2
0x1400295c5  mov     rdx, rax; struct _ITEM_DATA *
0x1400295c8  mov     rcx, rbx; struct _ITEM_DATA *
0x1400295cb  call    ?CompareItemData@@YAJPEAU_ITEM_DATA@@0@Z; CompareItemData(_ITEM_DATA *,_ITEM_DATA *)
0x1400295d0  jmp     short loc_1400295D4
0x1400295d2  xor     eax, eax
0x1400295d4  add     rsp, 30h
0x1400295d8  pop     r14
0x1400295da  pop     rdi
0x1400295db  pop     rsi
0x1400295dc  pop     rbp
0x1400295dd  pop     rbx
0x1400295de  retn
```
