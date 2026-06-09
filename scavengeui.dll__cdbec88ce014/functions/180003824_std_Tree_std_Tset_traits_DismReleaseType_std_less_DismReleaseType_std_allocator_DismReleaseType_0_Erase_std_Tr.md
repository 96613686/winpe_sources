# std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Erase(std::_Tree_node<_DismReleaseType,void *> *)

- ea: `0x180003824`
- end: `0x180003873`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@@Z`
- size: `79`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003128`
- `0x180003824`

## callees

- `0x180003824`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003854`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003854`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Erase(
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
      std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Erase(
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
0x180003824  mov     [rsp+arg_0], rbx
0x180003829  mov     [rsp+arg_8], rsi
0x18000382e  push    rdi
0x18000382f  sub     rsp, 20h
0x180003833  cmp     byte ptr [rdx+19h], 0
0x180003837  mov     rdi, rdx
0x18000383a  mov     rsi, rcx
0x18000383d  mov     rbx, rdx
0x180003840  jnz     short loc_180003863
0x180003842  mov     rdx, [rbx+10h]
0x180003846  mov     rcx, rsi
0x180003849  call    ?_Erase@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Erase(std::_Tree_node<_DismReleaseType,void *> *)
0x18000384e  mov     rbx, [rbx]
0x180003851  mov     rcx, rdi
0x180003854  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000385a  cmp     byte ptr [rbx+19h], 0
0x18000385e  mov     rdi, rbx
0x180003861  jz      short loc_180003842
0x180003863  mov     rbx, [rsp+28h+arg_0]
0x180003868  mov     rsi, [rsp+28h+arg_8]
0x18000386d  add     rsp, 20h
0x180003871  pop     rdi
0x180003872  retn
```
