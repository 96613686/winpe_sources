# std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(std::_Tree_node<ComTaskHost *,void *> *)

- ea: `0x140004510`
- end: `0x140004561`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z`
- size: `81`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004360`
- `0x1400043a0`
- `0x140004510`

## callees

- `0x140004510`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004542`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004542`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      operator delete(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 25) );
  }
}

```

## disassembly

```asm
0x140004510  mov     [rsp+arg_0], rbx
0x140004515  mov     [rsp+arg_8], rsi
0x14000451a  push    rdi
0x14000451b  sub     rsp, 20h
0x14000451f  cmp     byte ptr [rdx+19h], 0
0x140004523  mov     rdi, rdx
0x140004526  mov     rsi, rcx
0x140004529  mov     rbx, rdx
0x14000452c  jnz     short loc_140004551
0x14000452e  xchg    ax, ax
0x140004530  mov     rdx, [rbx+10h]
0x140004534  mov     rcx, rsi
0x140004537  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(std::_Tree_node<ComTaskHost *,void *> *)
0x14000453c  mov     rbx, [rbx]
0x14000453f  mov     rcx, rdi
0x140004542  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004548  cmp     byte ptr [rbx+19h], 0
0x14000454c  mov     rdi, rbx
0x14000454f  jz      short loc_140004530
0x140004551  mov     rbx, [rsp+28h+arg_0]
0x140004556  mov     rsi, [rsp+28h+arg_8]
0x14000455b  add     rsp, 20h
0x14000455f  pop     rdi
0x140004560  retn
```
