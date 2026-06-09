# std::_Uninitialized_move<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> &)

- ea: `0x180007f54`
- end: `0x180007f91`
- name: `??$_Uninitialized_move@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@YAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z`
- size: `61`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007770`
- `0x18000787c`
- `0x180007ab8`

## callees

- `0x18000574c`
- `0x180007f54`
- `0x180008304`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::wstring *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8

  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::wstring::wstring(a3, v5);
      a3 += 32;
      v5 = v6 + 32;
    }
    while ( v5 != v7 );
  }
  std::_Destroy_range<std::allocator<std::wstring>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180007f54  push    rbx
0x180007f56  sub     rsp, 20h
0x180007f5a  mov     rbx, r8
0x180007f5d  mov     r8, rdx
0x180007f60  mov     rdx, rcx
0x180007f63  cmp     rcx, r8
0x180007f66  jz      short loc_180007F7D
0x180007f68  mov     rcx, rbx
0x180007f6b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180007f70  add     rbx, 20h ; ' '
0x180007f74  add     rdx, 20h ; ' '
0x180007f78  cmp     rdx, r8
0x180007f7b  jnz     short loc_180007F68
0x180007f7d  mov     rdx, rbx
0x180007f80  mov     rcx, rbx
0x180007f83  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180007f88  mov     rax, rbx
0x180007f8b  add     rsp, 20h
0x180007f8f  pop     rbx
0x180007f90  retn
```
