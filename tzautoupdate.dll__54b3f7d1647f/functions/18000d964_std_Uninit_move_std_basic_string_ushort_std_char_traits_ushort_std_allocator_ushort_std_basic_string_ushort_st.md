# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000d964`
- end: `0x18000d9bf`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d33c`
- `0x180010320`

## callees

- `0x18000d964`
- `0x18000da10`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
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
  return a3;
}

```

## disassembly

```asm
0x18000d964  mov     rax, rsp
0x18000d967  mov     [rax+8], rbx
0x18000d96b  mov     [rax+10h], rsi
0x18000d96f  mov     [rax+20h], r9
0x18000d973  mov     [rax+18h], r8
0x18000d977  push    rdi
0x18000d978  sub     rsp, 20h
0x18000d97c  mov     rbx, r8
0x18000d97f  mov     rsi, rdx
0x18000d982  mov     rdi, rcx
0x18000d985  mov     [rsp+28h+arg_18], rbx
0x18000d98a  cmp     rcx, rdx
0x18000d98d  jz      short loc_18000D9AC
0x18000d98f  mov     rdx, rdi
0x18000d992  mov     rcx, rbx
0x18000d995  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000d99a  add     rbx, 20h ; ' '
0x18000d99e  mov     [rsp+28h+arg_10], rbx
0x18000d9a3  add     rdi, 20h ; ' '
0x18000d9a7  cmp     rdi, rsi
0x18000d9aa  jnz     short loc_18000D98F
0x18000d9ac  mov     rax, rbx
0x18000d9af  mov     rbx, [rsp+28h+arg_0]
0x18000d9b4  mov     rsi, [rsp+28h+arg_8]
0x18000d9b9  add     rsp, 20h
0x18000d9bd  pop     rdi
0x18000d9be  retn
```
