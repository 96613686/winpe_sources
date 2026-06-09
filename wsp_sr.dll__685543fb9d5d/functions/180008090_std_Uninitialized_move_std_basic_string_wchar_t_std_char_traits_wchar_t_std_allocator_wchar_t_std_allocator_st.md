# std::_Uninitialized_move<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> &)

- ea: `0x180008090`
- end: `0x1800080ce`
- name: `??$_Uninitialized_move@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@YAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000784c`
- `0x18000795c`
- `0x180007b98`

## callees

- `0x18000577c`
- `0x180008090`
- `0x180008440`

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
0x180008090  push    rbx
0x180008092  sub     rsp, 20h
0x180008096  mov     rbx, r8
0x180008099  mov     r8, rdx
0x18000809c  mov     rdx, rcx
0x18000809f  cmp     rcx, r8
0x1800080a2  jz      short loc_1800080B9
0x1800080a4  mov     rcx, rbx
0x1800080a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800080ac  add     rbx, 20h ; ' '
0x1800080b0  add     rdx, 20h ; ' '
0x1800080b4  cmp     rdx, r8
0x1800080b7  jnz     short loc_1800080A4
0x1800080b9  mov     rdx, rbx
0x1800080bc  mov     rcx, rbx
0x1800080bf  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800080c4  mov     rax, rbx
0x1800080c7  add     rsp, 20h
0x1800080cb  pop     rbx
0x1800080cc  retn
```
