# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)

- ea: `0x1800150fc`
- end: `0x180015189`
- name: `??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013d7c`
- `0x180015060`
- `0x180015230`
- `0x18001523c`
- `0x1800154a8`
- `0x180015590`
- `0x180015950`
- `0x18001ce0c`
- `0x18001ce50`
- `0x18001df44`
- `0x180024384`
- `0x180029c74`
- `0x18002d644`

## callees

- `0x1800150fc`
- `0x18001ceb8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001513a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001513a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001517d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(
        void **a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Erase(
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
0x1800150fc  push    rdi
0x1800150fe  sub     rsp, 30h
0x180015102  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001510b  mov     [rsp+38h+arg_0], rbx
0x180015110  mov     [rsp+38h+arg_8], rsi
0x180015115  mov     rbx, rcx
0x180015118  mov     rax, [rcx]
0x18001511b  mov     rsi, [rax+8]
0x18001511f  mov     rdi, rsi
0x180015122  cmp     byte ptr [rsi+19h], 0
0x180015126  jnz     short loc_18001514F
0x180015128  mov     rdx, [rdi+10h]
0x18001512c  mov     rcx, rbx
0x18001512f  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Erase(std::_Tree_node<ushort const *,void *> *)
0x180015134  mov     rdi, [rdi]
0x180015137  mov     rcx, rsi
0x18001513a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015141  nop     dword ptr [rax+rax+00h]
0x180015146  mov     rsi, rdi
0x180015149  cmp     byte ptr [rdi+19h], 0
0x18001514d  jz      short loc_180015128
0x18001514f  mov     rax, [rbx]
0x180015152  mov     [rax+8], rax
0x180015156  mov     rax, [rbx]
0x180015159  mov     [rax], rax
0x18001515c  mov     rax, [rbx]
0x18001515f  mov     [rax+10h], rax
0x180015163  mov     qword ptr [rbx+8], 0
0x18001516b  mov     rcx, [rbx]
0x18001516e  mov     rbx, [rsp+38h+arg_0]
0x180015173  mov     rsi, [rsp+38h+arg_8]
0x180015178  add     rsp, 30h
0x18001517c  pop     rdi
0x18001517d  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
