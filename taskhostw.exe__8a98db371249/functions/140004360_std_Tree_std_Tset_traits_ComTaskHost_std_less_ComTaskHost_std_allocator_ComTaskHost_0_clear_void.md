# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(void)

- ea: `0x140004360`
- end: `0x140004397`
- name: `?clear@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@QEAAXXZ`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400042a0`
- `0x1400042d4`

## callees

- `0x140004510`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(
        _QWORD *a1)
{
  __int64 result; // rax

  std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(
    (__int64)a1,
    *(void **)(*a1 + 8LL));
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  result = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x140004360  push    rbx
0x140004362  sub     rsp, 20h
0x140004366  mov     rbx, rcx
0x140004369  mov     rdx, [rcx]
0x14000436c  mov     rdx, [rdx+8]
0x140004370  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(std::_Tree_node<ComTaskHost *,void *> *)
0x140004375  mov     rax, [rbx]
0x140004378  mov     [rax+8], rax
0x14000437c  mov     rax, [rbx]
0x14000437f  mov     [rax], rax
0x140004382  mov     rax, [rbx]
0x140004385  mov     [rax+10h], rax
0x140004389  mov     qword ptr [rbx+8], 0
0x140004391  add     rsp, 20h
0x140004395  pop     rbx
0x140004396  retn
```
