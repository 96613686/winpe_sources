# std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>(void)

- ea: `0x180005194`
- end: `0x1800051be`
- name: `??1?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d20`
- `0x180006320`

## callees

- `0x180004060`
- `0x180004e88`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>(
        _QWORD **a1)
{
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>(
    a1,
    a1,
    (*a1)[1]);
  std::_Deallocate<16>(*a1, 0x30u);
}

```

## disassembly

```asm
0x180005194  push    rbx
0x180005196  sub     rsp, 20h
0x18000519a  mov     r8, [rcx]
0x18000519d  mov     rdx, rcx
0x1800051a0  mov     rbx, rcx
0x1800051a3  mov     r8, [r8+8]
0x1800051a7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>> &,std::_Tree_node<std::pair<_GUID const,ulong>,void *> *)
0x1800051ac  mov     rcx, [rbx]
0x1800051af  mov     edx, 30h ; '0'
0x1800051b4  add     rsp, 20h
0x1800051b8  pop     rbx
0x1800051b9  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
