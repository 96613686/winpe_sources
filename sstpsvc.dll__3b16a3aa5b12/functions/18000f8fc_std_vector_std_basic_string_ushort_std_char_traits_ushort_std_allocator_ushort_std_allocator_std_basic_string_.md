# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18000f8fc`
- end: `0x18000f96b`
- name: `??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ff74`
- `0x1800132c0`
- `0x1800138c0`
- `0x180014170`
- `0x180014490`

## callees

- `0x18000f454`
- `0x18000f8fc`
- `0x1800118ec`

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
0x18000f8fc  mov     [rsp+arg_8], rbx
0x18000f901  mov     [rsp+arg_0], rcx
0x18000f906  push    rdi
0x18000f907  sub     rsp, 30h
0x18000f90b  mov     rdi, rdx
0x18000f90e  mov     rbx, rcx
0x18000f911  mov     qword ptr [rcx], 0
0x18000f918  mov     qword ptr [rcx+8], 0
0x18000f920  mov     qword ptr [rcx+10h], 0
0x18000f928  mov     rdx, [rdx+8]
0x18000f92c  sub     rdx, [rdi]
0x18000f92f  sar     rdx, 3
0x18000f933  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000f93d  imul    rdx, rax
0x18000f941  call    ?_Buy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAA_N_K@Z; std::vector<std::wstring>::_Buy(unsigned __int64)
0x18000f946  test    al, al
0x18000f948  jz      short loc_18000F95D
0x18000f94a  mov     r8, [rbx]
0x18000f94d  mov     rdx, [rdi+8]
0x18000f951  mov     rcx, [rdi]
0x18000f954  call    ??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring>>(std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring> &,std::_Nonscalar_ptr_iterator_tag)
0x18000f959  mov     [rbx+8], rax
0x18000f95d  mov     rax, rbx
0x18000f960  mov     rbx, [rsp+38h+arg_8]
0x18000f965  add     rsp, 30h
0x18000f969  pop     rdi
0x18000f96a  retn
```
