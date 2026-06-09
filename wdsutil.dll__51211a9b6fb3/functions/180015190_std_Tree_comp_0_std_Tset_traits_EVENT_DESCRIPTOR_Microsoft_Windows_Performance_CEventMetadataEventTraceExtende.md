# std::_Tree_comp<0,std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::~_Tree_comp<0,std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(void)

- ea: `0x180015190`
- end: `0x18001519a`
- name: `??1?$_Tree_comp@$0A@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800322b3`
- `0x1800327f3`
- `0x1800334a1`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015193`

## pseudocode

```c
void __fastcall std::_Tree_comp<0,std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::~_Tree_comp<0,std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(
        void **a1)
{
  operator delete(*a1);
}

```

## disassembly

```asm
0x180015190  mov     rcx, [rcx]
0x180015193  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
