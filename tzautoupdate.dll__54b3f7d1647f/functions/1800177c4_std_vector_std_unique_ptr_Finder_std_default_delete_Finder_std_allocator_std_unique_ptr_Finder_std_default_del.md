# std::vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>>::_Reserve(unsigned __int64)

- ea: `0x1800177c4`
- end: `0x180017840`
- name: `?_Reserve@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800175d0`

## callees

- `0x180002220`
- `0x180017718`
- `0x1800177c4`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<Finder>>::_Reserve(__int64 a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  result = (*(_QWORD *)(a1 + 16) - v2) >> 3;
  if ( !result )
  {
    v4 = (v2 - *(_QWORD *)a1) >> 3;
    if ( v4 == 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector<T> too long");
    v5 = v4 + 1;
    v6 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
    v7 = 0;
    if ( 0x1FFFFFFFFFFFFFFFLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return (__int64)std::vector<std::unique_ptr<Finder>>::_Reallocate((__int64 **)a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800177c4  sub     rsp, 28h
0x1800177c8  mov     r9, [rcx+10h]
0x1800177cc  mov     r8, rcx
0x1800177cf  mov     rdx, [rcx+8]
0x1800177d3  mov     rax, r9
0x1800177d6  sub     rax, rdx
0x1800177d9  sar     rax, 3
0x1800177dd  cmp     rax, 1
0x1800177e1  jnb     short loc_18001783B
0x1800177e3  sub     rdx, [rcx]
0x1800177e6  mov     r10, 1FFFFFFFFFFFFFFFh
0x1800177f0  sar     rdx, 3
0x1800177f4  mov     rax, r10
0x1800177f7  sub     rax, rdx
0x1800177fa  cmp     rax, 1
0x1800177fe  jnb     short loc_18001780D
0x180017800  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180017807  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001780d  sub     r9, [rcx]
0x180017810  inc     rdx
0x180017813  sar     r9, 3
0x180017817  xor     ecx, ecx
0x180017819  mov     rax, r9
0x18001781c  shr     rax, 1
0x18001781f  sub     r10, rax
0x180017822  add     rax, r9
0x180017825  cmp     r10, r9
0x180017828  cmovnb  rcx, rax
0x18001782c  cmp     rcx, rdx
0x18001782f  cmovnb  rdx, rcx
0x180017833  mov     rcx, r8
0x180017836  call    ?_Reallocate@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<Finder>>::_Reallocate(unsigned __int64)
0x18001783b  add     rsp, 28h
0x18001783f  retn
```
