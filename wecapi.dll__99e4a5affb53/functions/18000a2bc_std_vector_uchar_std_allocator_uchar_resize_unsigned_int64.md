# std::vector<uchar,std::allocator<uchar>>::resize(unsigned __int64)

- ea: `0x18000a2bc`
- end: `0x18000a379`
- name: `?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000632c`
- `0x18000908c`

## callees

- `0x180009cb8`
- `0x180009fd8`
- `0x18000a2bc`
- `0x18000ba33`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::resize(__int64 *a1, unsigned __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // rax
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rdx

  v4 = *a1;
  v5 = a1[1] - *a1;
  if ( a2 >= v5 )
  {
    if ( a2 > v5 )
    {
      if ( a1[2] - a1[1] < a2 - v5 )
      {
        if ( ~v5 < a2 - v5 )
          std::vector<std::wstring>::_Xlen();
        v7 = a1[2] - v4;
        v8 = 0;
        if ( ~(v7 >> 1) >= v7 )
          v8 = v7 + (v7 >> 1);
        if ( v8 < a2 )
          v8 = a2;
        std::vector<unsigned char>::_Reallocate(a1, v8);
      }
      memset_0((void *)a1[1], 0, a2 + *a1 - a1[1]);
      a1[1] = a2 + *a1;
    }
  }
  else
  {
    v6 = v4 + a2;
    if ( v4 + a2 == v4 )
    {
      a1[1] = v4;
    }
    else if ( v6 != a1[1] )
    {
      a1[1] = v6;
    }
  }
}

```

## disassembly

```asm
0x18000a2bc  mov     [rsp+arg_8], rbx
0x18000a2c1  mov     [rsp+arg_0], rcx
0x18000a2c6  push    rdi
0x18000a2c7  sub     rsp, 20h
0x18000a2cb  mov     rdi, rdx
0x18000a2ce  mov     rbx, rcx
0x18000a2d1  mov     rdx, [rcx]
0x18000a2d4  mov     rcx, [rcx+8]
0x18000a2d8  sub     rcx, rdx
0x18000a2db  cmp     rdi, rcx
0x18000a2de  jnb     short loc_18000A304
0x18000a2e0  lea     rax, [rdx+rdi]
0x18000a2e4  cmp     rax, rdx
0x18000a2e7  jnz     short loc_18000A2F8
0x18000a2e9  mov     [rbx+8], rdx
0x18000a2ed  mov     rbx, [rsp+28h+arg_8]
0x18000a2f2  add     rsp, 20h
0x18000a2f6  pop     rdi
0x18000a2f7  retn
0x18000a2f8  cmp     rax, [rbx+8]
0x18000a2fc  jz      short loc_18000A2ED
0x18000a2fe  mov     [rbx+8], rax
0x18000a302  jmp     short loc_18000A2ED
0x18000a304  jbe     short loc_18000A2ED
0x18000a306  mov     r8, rdi
0x18000a309  sub     r8, rcx
0x18000a30c  mov     r9, [rbx+10h]
0x18000a310  mov     rax, r9
0x18000a313  sub     rax, [rbx+8]
0x18000a317  cmp     rax, r8
0x18000a31a  jnb     short loc_18000A34F
0x18000a31c  not     rcx
0x18000a31f  cmp     rcx, r8
0x18000a322  jb      short loc_18000A373
0x18000a324  sub     r9, rdx
0x18000a327  mov     rax, r9
0x18000a32a  shr     rax, 1
0x18000a32d  mov     rcx, rax
0x18000a330  not     rcx
0x18000a333  add     rax, r9
0x18000a336  xor     edx, edx
0x18000a338  cmp     rcx, r9
0x18000a33b  cmovnb  rdx, rax
0x18000a33f  cmp     rdx, rdi
0x18000a342  cmovb   rdx, rdi
0x18000a346  mov     rcx, rbx
0x18000a349  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18000a34e  nop
0x18000a34f  mov     rcx, [rbx+8]; void *
0x18000a353  mov     r8, [rbx]
0x18000a356  sub     r8, rcx
0x18000a359  add     r8, rdi; Size
0x18000a35c  xor     edx, edx; Val
0x18000a35e  call    memset_0
0x18000a363  nop
0x18000a364  mov     rcx, [rbx]
0x18000a367  add     rcx, rdi
0x18000a36a  mov     [rbx+8], rcx
0x18000a36e  jmp     loc_18000A2ED
0x18000a373  call    ?_Xlen@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEBAXXZ; std::vector<std::wstring>::_Xlen(void)
```
