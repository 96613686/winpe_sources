# std::_List_buy<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>,std::allocator<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>>::_Buynode<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>(std::_List_node<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>,void *> *,std::_List_node<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>,void *> *,std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>> &&)

- ea: `0x18000bfcc`
- end: `0x18000bff7`
- name: `??$_Buynode@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@?$_List_buy@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@PEAX@1@PEAU21@0$$QEAV?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@1@@Z`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c334`

## callees

- `0x18000c610`

## pseudocode

```c
__int64 __fastcall std::_List_buy<std::unique_ptr<ProcessWatcherDesc>>::_Buynode<std::unique_ptr<ProcessWatcherDesc>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx

  result = std::_List_alloc<0,std::_List_base_types<unsigned long const>>::_Buynode0(a1, a2, a3);
  v6 = *a4;
  *a4 = 0;
  *(_QWORD *)(result + 16) = v6;
  return result;
}

```

## disassembly

```asm
0x18000bfcc  mov     [rsp+arg_0], rcx
0x18000bfd1  push    rbx
0x18000bfd2  sub     rsp, 20h
0x18000bfd6  mov     rbx, r9
0x18000bfd9  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@$$CBKV?$allocator@$$CBK@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong const>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x18000bfde  mov     [rsp+28h+arg_0], rax
0x18000bfe3  mov     rcx, [rbx]
0x18000bfe6  mov     qword ptr [rbx], 0
0x18000bfed  mov     [rax+10h], rcx
0x18000bff1  add     rsp, 20h
0x18000bff5  pop     rbx
0x18000bff6  retn
```
