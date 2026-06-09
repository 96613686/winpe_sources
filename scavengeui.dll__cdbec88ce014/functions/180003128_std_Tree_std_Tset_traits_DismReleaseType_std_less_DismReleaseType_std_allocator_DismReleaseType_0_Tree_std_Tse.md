# std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::~_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>(void)

- ea: `0x180003128`
- end: `0x1800031a0`
- name: `??1?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800031a8`
- `0x180003300`

## callees

- `0x180003128`
- `0x180003824`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000315c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000315c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003199`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::~_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>(
        void **a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    operator delete(v2);
  }
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x180003128  mov     [rsp+arg_0], rbx
0x18000312d  mov     [rsp+arg_8], rsi
0x180003132  push    rdi
0x180003133  sub     rsp, 20h
0x180003137  mov     rbx, rcx
0x18000313a  mov     rax, [rcx]
0x18000313d  mov     rsi, [rax+8]
0x180003141  mov     rdi, rsi
0x180003144  cmp     byte ptr [rsi+19h], 0
0x180003148  jnz     short loc_18000316B
0x18000314a  mov     rdx, [rdi+10h]
0x18000314e  mov     rcx, rbx
0x180003151  call    ?_Erase@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Erase(std::_Tree_node<_DismReleaseType,void *> *)
0x180003156  mov     rdi, [rdi]
0x180003159  mov     rcx, rsi
0x18000315c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003162  mov     rsi, rdi
0x180003165  cmp     byte ptr [rdi+19h], 0
0x180003169  jz      short loc_18000314A
0x18000316b  mov     rax, [rbx]
0x18000316e  mov     [rax+8], rax
0x180003172  mov     rax, [rbx]
0x180003175  mov     [rax], rax
0x180003178  mov     rax, [rbx]
0x18000317b  mov     [rax+10h], rax
0x18000317f  mov     qword ptr [rbx+8], 0
0x180003187  mov     rcx, [rbx]
0x18000318a  mov     rbx, [rsp+28h+arg_0]
0x18000318f  mov     rsi, [rsp+28h+arg_8]
0x180003194  add     rsp, 20h
0x180003198  pop     rdi
0x180003199  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
