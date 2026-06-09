# std::_Uninitialized_copy<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> &)

- ea: `0x1800135d0`
- end: `0x180013636`
- name: `??$_Uninitialized_copy@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV12@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@YAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013444`

## callees

- `0x18000577c`
- `0x180005884`
- `0x1800135d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Uninitialized_copy<std::wstring *,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 32 )
  {
    std::wstring::wstring(a3, i);
    a3 += 32;
  }
  std::_Destroy_range<std::allocator<std::wstring>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x1800135d0  mov     rax, rsp
0x1800135d3  mov     [rax+8], rbx
0x1800135d7  mov     [rax+10h], rsi
0x1800135db  push    rdi
0x1800135dc  sub     rsp, 40h
0x1800135e0  mov     rbx, r8
0x1800135e3  mov     rsi, rdx
0x1800135e6  mov     rdi, rcx
0x1800135e9  mov     [rax-28h], rbx
0x1800135ed  mov     [rax-20h], rbx
0x1800135f1  mov     [rax-18h], r9
0x1800135f5  cmp     rcx, rdx
0x1800135f8  jz      short loc_180013617
0x1800135fa  mov     rdx, rdi
0x1800135fd  mov     rcx, rbx
0x180013600  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013605  add     rbx, 20h ; ' '
0x180013609  mov     [rsp+48h+var_20], rbx
0x18001360e  add     rdi, 20h ; ' '
0x180013612  cmp     rdi, rsi
0x180013615  jnz     short loc_1800135FA
0x180013617  mov     rdx, rbx
0x18001361a  mov     rcx, rbx
0x18001361d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180013622  mov     rax, rbx
0x180013625  mov     rbx, [rsp+48h+arg_0]
0x18001362a  mov     rsi, [rsp+48h+arg_8]
0x18001362f  add     rsp, 40h
0x180013633  pop     rdi
0x180013634  retn
```
