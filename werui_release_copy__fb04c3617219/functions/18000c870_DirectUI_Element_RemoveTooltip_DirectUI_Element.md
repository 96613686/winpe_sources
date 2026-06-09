# DirectUI::Element::RemoveTooltip(DirectUI::Element *)

- ea: `0x18000c870`
- end: `0x18000c89a`
- name: `?RemoveTooltip@Element@DirectUI@@MEAAXPEAV12@@Z`
- size: `42`
- prototype: `void __fastcall(DirectUI::Element *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c870`
- `0x180018010`

## pseudocode

```c
void __fastcall DirectUI::Element::RemoveTooltip(DirectUI::Element *this, struct DirectUI::Element *a2)
{
  __int64 v2; // rcx

  if ( (*((_BYTE *)this + 151) & 8) != 0 )
  {
    v2 = *((_QWORD *)this + 10);
    if ( v2 )
      (*(void (__fastcall **)(__int64, struct DirectUI::Element *))(*(_QWORD *)v2 + 264LL))(v2, a2);
  }
}

```

## disassembly

```asm
0x18000c870  sub     rsp, 28h
0x18000c874  test    byte ptr [rcx+97h], 8
0x18000c87b  jz      short loc_18000C895
0x18000c87d  mov     rcx, [rcx+50h]
0x18000c881  test    rcx, rcx
0x18000c884  jz      short loc_18000C895
0x18000c886  mov     rax, [rcx]
0x18000c889  mov     rax, [rax+108h]
0x18000c890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c895  add     rsp, 28h
0x18000c899  retn
```
