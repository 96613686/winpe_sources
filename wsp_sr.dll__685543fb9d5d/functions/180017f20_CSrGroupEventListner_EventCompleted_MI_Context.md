# CSrGroupEventListner::EventCompleted(_MI_Context *)

- ea: `0x180017f20`
- end: `0x180017f3e`
- name: `?EventCompleted@CSrGroupEventListner@@UEAAXPEAU_MI_Context@@@Z`
- size: `30`
- prototype: `void __fastcall(CSrGroupEventListner *__hidden this, struct _MI_Context *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001c410`
- `0x18001c684`
- `0x18001c8f8`

## pseudocode

```c
void __fastcall CSrGroupEventListner::EventCompleted(CSrGroupEventListner *this, struct _MI_Context *a2)
{
  int v2; // eax
  char *v3; // rcx

  v2 = *((_DWORD *)this + 2);
  v3 = (char *)this + 16;
  if ( v2 == 1 )
  {
    SrSmapiPostReplicationGroupArrivalEvent(v3, a2);
  }
  else if ( v2 == 2 )
  {
    SrSmapiPostReplicationGroupDepartureEvent(v3, a2);
  }
  else
  {
    SrSmapiPostReplicationGroupModificationEvent(v3, a2);
  }
}

```

## disassembly

```asm
0x180017f20  mov     eax, [rcx+8]
0x180017f23  add     rcx, 10h
0x180017f27  cmp     eax, 1
0x180017f2a  jz      ?SrSmapiPostReplicationGroupArrivalEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupArrivalEvent(std::wstring const &,_MI_Context *)
0x180017f30  cmp     eax, 2
0x180017f33  jz      ?SrSmapiPostReplicationGroupDepartureEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupDepartureEvent(std::wstring const &,_MI_Context *)
0x180017f39  jmp     ?SrSmapiPostReplicationGroupModificationEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupModificationEvent(std::wstring const &,_MI_Context *)
```
