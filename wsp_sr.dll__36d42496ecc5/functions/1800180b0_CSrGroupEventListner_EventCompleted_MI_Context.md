# CSrGroupEventListner::EventCompleted(_MI_Context *)

- ea: `0x1800180b0`
- end: `0x1800180ce`
- name: `?EventCompleted@CSrGroupEventListner@@UEAAXPEAU_MI_Context@@@Z`
- size: `30`
- prototype: `void __fastcall(CSrGroupEventListner *__hidden this, struct _MI_Context *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001c318`
- `0x18001c588`
- `0x18001c7f8`

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
0x1800180b0  mov     eax, [rcx+8]
0x1800180b3  add     rcx, 10h
0x1800180b7  cmp     eax, 1
0x1800180ba  jz      ?SrSmapiPostReplicationGroupArrivalEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupArrivalEvent(std::wstring const &,_MI_Context *)
0x1800180c0  cmp     eax, 2
0x1800180c3  jz      ?SrSmapiPostReplicationGroupDepartureEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupDepartureEvent(std::wstring const &,_MI_Context *)
0x1800180c9  jmp     ?SrSmapiPostReplicationGroupModificationEvent@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_MI_Context@@@Z; SrSmapiPostReplicationGroupModificationEvent(std::wstring const &,_MI_Context *)
```
