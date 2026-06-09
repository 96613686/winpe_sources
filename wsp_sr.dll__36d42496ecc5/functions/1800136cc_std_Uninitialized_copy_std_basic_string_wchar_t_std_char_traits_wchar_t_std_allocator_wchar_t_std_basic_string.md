# std::_Uninitialized_copy<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> &)

- ea: `0x1800136cc`
- end: `0x180013731`
- name: `??$_Uninitialized_copy@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV12@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@YAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001356c`

## callees

- `0x18000574c`
- `0x18000584c`
- `0x1800136cc`

## pseudocode

```c
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
0x1800136cc  mov     rax, rsp
0x1800136cf  mov     [rax+8], rbx
0x1800136d3  mov     [rax+10h], rsi
0x1800136d7  push    rdi
0x1800136d8  sub     rsp, 40h
0x1800136dc  mov     rbx, r8
0x1800136df  mov     rsi, rdx
0x1800136e2  mov     rdi, rcx
0x1800136e5  mov     [rax-28h], rbx
0x1800136e9  mov     [rax-20h], rbx
0x1800136ed  mov     [rax-18h], r9
0x1800136f1  cmp     rcx, rdx
0x1800136f4  jz      short loc_180013713
0x1800136f6  mov     rdx, rdi
0x1800136f9  mov     rcx, rbx
0x1800136fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013701  add     rbx, 20h ; ' '
0x180013705  mov     [rsp+48h+var_20], rbx
0x18001370a  add     rdi, 20h ; ' '
0x18001370e  cmp     rdi, rsi
0x180013711  jnz     short loc_1800136F6
0x180013713  mov     rdx, rbx
0x180013716  mov     rcx, rbx
0x180013719  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001371e  mov     rax, rbx
0x180013721  mov     rbx, [rsp+48h+arg_0]
0x180013726  mov     rsi, [rsp+48h+arg_8]
0x18001372b  add     rsp, 40h
0x18001372f  pop     rdi
0x180013730  retn
```
