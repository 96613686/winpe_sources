# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x1800106b4`
- end: `0x180010724`
- name: `??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `112`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180010d80`
- `0x1800142b8`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`

## callees

- `0x1800101fc`
- `0x1800106b4`
- `0x18001286c`

## pseudocode

```c
__int64 *__fastcall std::vector<std::wstring>::vector<std::wstring>(__int64 *a1, __int64 *a2)
{
  char v4; // al
  __int64 *result; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = std::vector<std::wstring>::_Buy(a1, 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3));
  try
  {
    if ( v4 )
      a1[1] = std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring>>(
                *a2,
                a2[1],
                *a1);
    result = a1;
  }
  catch ( ... )
  {
    std::vector<std::wstring>::_Tidy((void **)a1);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800106b4  mov     [rsp+arg_8], rbx
0x1800106b9  mov     [rsp+arg_0], rcx
0x1800106be  push    rdi
0x1800106bf  sub     rsp, 30h
0x1800106c3  mov     rdi, rdx
0x1800106c6  mov     rbx, rcx
0x1800106c9  mov     qword ptr [rcx], 0
0x1800106d0  mov     qword ptr [rcx+8], 0
0x1800106d8  mov     qword ptr [rcx+10h], 0
0x1800106e0  mov     rdx, [rdx+8]
0x1800106e4  sub     rdx, [rdi]
0x1800106e7  sar     rdx, 3
0x1800106eb  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800106f5  imul    rdx, rax
0x1800106f9  call    ?_Buy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAA_N_K@Z; std::vector<std::wstring>::_Buy(unsigned __int64)
0x1800106fe  test    al, al
0x180010700  jz      short loc_180010715
0x180010702  mov     r8, [rbx]
0x180010705  mov     rdx, [rdi+8]
0x180010709  mov     rcx, [rdi]
0x18001070c  call    ??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring>>(std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring> &,std::_Nonscalar_ptr_iterator_tag)
0x180010711  mov     [rbx+8], rax
0x180010715  mov     rax, rbx
0x180010718  mov     rbx, [rsp+38h+arg_8]
0x18001071d  add     rsp, 30h
0x180010721  pop     rdi
0x180010722  retn
```
