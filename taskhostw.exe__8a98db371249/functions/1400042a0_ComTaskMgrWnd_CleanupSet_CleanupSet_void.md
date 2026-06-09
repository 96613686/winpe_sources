# ComTaskMgrWnd::CleanupSet::~CleanupSet(void)

- ea: `0x1400042a0`
- end: `0x1400042cb`
- name: `??1CleanupSet@ComTaskMgrWnd@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(ComTaskMgrWnd::CleanupSet *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004268`

## callees

- `0x1400042d4`
- `0x140004360`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400042be`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400042be`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSet::~CleanupSet(ComTaskMgrWnd::CleanupSet *this)
{
  void **v1; // rbx

  v1 = (void **)((char *)this + 8);
  ClearList<std::set<ComTaskHost *>>((__int64)this + 8);
  std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(v1);
  operator delete(*v1);
}

```

## disassembly

```asm
0x1400042a0  push    rbx
0x1400042a2  sub     rsp, 20h
0x1400042a6  lea     rbx, [rcx+8]
0x1400042aa  mov     rcx, rbx
0x1400042ad  call    ??$ClearList@V?$set@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@@std@@@@YAXAEAV?$set@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@@std@@@Z; ClearList<std::set<ComTaskHost *>>(std::set<ComTaskHost *> &)
0x1400042b2  nop
0x1400042b3  mov     rcx, rbx
0x1400042b6  call    ?clear@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(void)
0x1400042bb  mov     rcx, [rbx]
0x1400042be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400042c4  nop
0x1400042c5  add     rsp, 20h
0x1400042c9  pop     rbx
0x1400042ca  retn
```
