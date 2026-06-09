# ComTaskMgrWnd::ComTaskMgrWnd(void)

- ea: `0x140006b50`
- end: `0x140006bbe`
- name: `??0ComTaskMgrWnd@@QEAA@XZ`
- size: `110`
- prototype: `ComTaskMgrWnd *__fastcall(ComTaskMgrWnd *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001968`

## callees

- `0x140006bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006b85`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140006b85`

## pseudocode

```c
ComTaskMgrWnd *__fastcall ComTaskMgrWnd::ComTaskMgrWnd(ComTaskMgrWnd *this)
{
  *(_QWORD *)this = &ComTaskMgrWnd::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 10) = std::_Tree_alloc<0,std::_Tree_base_types<ComTaskHost *>>::_Buyheadnode();
  InitializeSRWLock((PSRWLOCK)this + 9);
  *((_QWORD *)this + 1) = 0;
  *((_WORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = -2147467263;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  return this;
}

```

## disassembly

```asm
0x140006b50  mov     [rsp+arg_10], rbx
0x140006b55  mov     [rsp+arg_0], rcx
0x140006b5a  push    rbp
0x140006b5b  push    rsi
0x140006b5c  push    rdi
0x140006b5d  sub     rsp, 20h
0x140006b61  mov     rsi, rcx
0x140006b64  lea     rax, ??_7ComTaskMgrWnd@@6B@; const ComTaskMgrWnd::`vftable'
0x140006b6b  mov     [rcx], rax
0x140006b6e  xor     ebp, ebp
0x140006b70  mov     [rcx+50h], rbp
0x140006b74  mov     [rcx+58h], rbp
0x140006b78  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<ComTaskHost *>>::_Buyheadnode(void)
0x140006b7d  mov     [rsi+50h], rax
0x140006b81  lea     rcx, [rsi+48h]; SRWLock
0x140006b85  call    cs:__imp_InitializeSRWLock
0x140006b8b  mov     [rsi+8], rbp
0x140006b8f  mov     [rsi+10h], bp
0x140006b93  mov     [rsi+18h], rbp
0x140006b97  mov     dword ptr [rsi+20h], 80004001h
0x140006b9e  mov     [rsi+28h], rbp
0x140006ba2  mov     [rsi+30h], rbp
0x140006ba6  mov     [rsi+38h], rbp
0x140006baa  mov     [rsi+40h], rbp
0x140006bae  mov     rax, rsi
0x140006bb1  mov     rbx, [rsp+38h+arg_10]
0x140006bb6  add     rsp, 20h
0x140006bba  pop     rdi
0x140006bbb  pop     rsi
0x140006bbc  pop     rbp
0x140006bbd  retn
```
