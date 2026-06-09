# std::vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>>::_Reallocate(unsigned __int64)

- ea: `0x180017718`
- end: `0x1800177bc`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `164`
- prototype: `__int64 *__fastcall(__int64 **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800177c4`

## callees

- `0x180002050`
- `0x1800021f8`
- `0x18000ad08`
- `0x180017558`
- `0x180017718`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180017799`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017799`

## pseudocode

```c
__int64 *__fastcall std::vector<std::unique_ptr<Finder>>::_Reallocate(__int64 **a1, unsigned __int64 a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 *result; // rax
  void *v8; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v8 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = a2, v3 = operator new(8 * a2), (v8 = v3) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  try
  {
    std::_Uninit_move<std::unique_ptr<Finder> *,std::unique_ptr<Finder> *,std::allocator<std::unique_ptr<Finder>>,std::unique_ptr<Finder>>(
      *a1,
      a1[1],
      v3);
  }
  catch ( ... )
  {
    operator delete(v8);
    throw;
  }
  v6 = a1[1] - *a1;
  if ( *a1 )
  {
    std::vector<std::unique_ptr<Finder>>::_Destroy(v5, *a1, a1[1]);
    operator delete(*a1);
  }
  a1[2] = &v3[v4];
  result = &v3[v6];
  a1[1] = result;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180017718  push    rbx
0x18001771a  push    rsi
0x18001771b  push    rdi
0x18001771c  push    r14
0x18001771e  sub     rsp, 38h
0x180017722  mov     rdi, rcx
0x180017725  xor     ebx, ebx
0x180017727  mov     [rsp+58h+arg_8], rbx
0x18001772c  test    rdx, rdx
0x18001772f  jz      short loc_180017763
0x180017731  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001773b  cmp     rdx, rax
0x18001773e  ja      short loc_18001775D
0x180017740  lea     r14, ds:0[rdx*8]
0x180017748  mov     rcx, r14; Size
0x18001774b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017750  mov     rbx, rax
0x180017753  mov     [rsp+58h+arg_8], rax
0x180017758  test    rax, rax
0x18001775b  jnz     short loc_18001776B
0x18001775d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180017763  lea     r14, ds:0[rdx*8]
0x18001776b  mov     r8, rbx
0x18001776e  mov     rdx, [rdi+8]
0x180017772  mov     rcx, [rdi]
0x180017775  call    ??$_Uninit_move@PEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<Finder> *,std::unique_ptr<Finder> *,std::allocator<std::unique_ptr<Finder>>,std::unique_ptr<Finder>>(std::unique_ptr<Finder> *,std::unique_ptr<Finder> *,std::unique_ptr<Finder> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<Finder>>> &,std::unique_ptr<Finder> *,std::_Nonscalar_ptr_iterator_tag)
0x18001777a  nop
0x18001777b  mov     rdx, [rdi]
0x18001777e  mov     r8, [rdi+8]
0x180017782  mov     rsi, r8
0x180017785  sub     rsi, rdx
0x180017788  sar     rsi, 3
0x18001778c  test    rdx, rdx
0x18001778f  jz      short loc_18001779F
0x180017791  call    ?_Destroy@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@2@0@Z; std::vector<std::unique_ptr<Finder>>::_Destroy(std::unique_ptr<Finder> *,std::unique_ptr<Finder> *)
0x180017796  mov     rcx, [rdi]
0x180017799  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001779f  lea     rax, [r14+rbx]
0x1800177a3  mov     [rdi+10h], rax
0x1800177a7  lea     rax, [rbx+rsi*8]
0x1800177ab  mov     [rdi+8], rax
0x1800177af  mov     [rdi], rbx
0x1800177b2  add     rsp, 38h
0x1800177b6  pop     r14
0x1800177b8  pop     rdi
0x1800177b9  pop     rsi
0x1800177ba  pop     rbx
0x1800177bb  retn
```
