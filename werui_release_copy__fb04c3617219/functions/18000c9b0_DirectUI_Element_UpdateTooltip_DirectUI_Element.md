# DirectUI::Element::UpdateTooltip(DirectUI::Element *)

- ea: `0x18000c9b0`
- end: `0x18000c9da`
- name: `?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z`
- size: `42`
- prototype: `void __fastcall(DirectUI::Element *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000c9b0`
- `0x180018010`

## pseudocode

```c
void __fastcall DirectUI::Element::UpdateTooltip(DirectUI::Element *this, struct DirectUI::Element *a2)
{
  __int64 v2; // rcx

  if ( (*((_BYTE *)this + 151) & 8) != 0 )
  {
    v2 = *((_QWORD *)this + 10);
    if ( v2 )
      (*(void (__fastcall **)(__int64, struct DirectUI::Element *))(*(_QWORD *)v2 + 248LL))(v2, a2);
  }
}

```

## disassembly

```asm
0x18000c9b0  sub     rsp, 28h
0x18000c9b4  test    byte ptr [rcx+97h], 8
0x18000c9bb  jz      short loc_18000C9D5
0x18000c9bd  mov     rcx, [rcx+50h]
0x18000c9c1  test    rcx, rcx
0x18000c9c4  jz      short loc_18000C9D5
0x18000c9c6  mov     rax, [rcx]
0x18000c9c9  mov     rax, [rax+0F8h]
0x18000c9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d5  add     rsp, 28h
0x18000c9d9  retn
```
