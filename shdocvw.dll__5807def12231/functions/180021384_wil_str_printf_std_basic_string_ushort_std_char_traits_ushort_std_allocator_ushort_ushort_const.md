# wil::str_printf<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(ushort const *,...)

- ea: `0x180021384`
- end: `0x180021407`
- name: `??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180021b00`
- `0x180021e84`
- `0x1800227b8`

## callees

- `0x18001a610`
- `0x180021384`
- `0x180021410`

## string_xrefs

- `0x1800213eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 wil::str_printf<std::wstring>(__int64 a1, const wchar_t *a2, ...)
{
  int v3; // eax
  va_list v5; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  va_copy(v5, va);
  v3 = wil::details::str_vprintf_nothrow<std::wstring>(a1, a2, &v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7F0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x180021384  mov     r11, rsp
0x180021387  mov     [r11+10h], rdx
0x18002138b  mov     [r11+8], rcx
0x18002138f  mov     [r11+18h], r8
0x180021393  mov     [r11+20h], r9
0x180021397  push    rbx
0x180021398  sub     rsp, 30h
0x18002139c  mov     rbx, rcx
0x18002139f  mov     [rsp+38h+var_18], 0
0x1800213a7  xorps   xmm0, xmm0
0x1800213aa  movups  xmmword ptr [rcx], xmm0
0x1800213ad  mov     qword ptr [rcx+10h], 0
0x1800213b5  mov     qword ptr [rcx+18h], 7
0x1800213bd  xor     eax, eax
0x1800213bf  mov     [rcx], ax
0x1800213c2  mov     [rsp+38h+var_18], 1; int
0x1800213ca  mov     [r11-10h], rax
0x1800213ce  lea     rax, [r11+18h]
0x1800213d2  mov     [r11-10h], rax
0x1800213d6  lea     r8, [r11-10h]
0x1800213da  call    ??$str_vprintf_nothrow@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAPEAD@Z; wil::details::str_vprintf_nothrow<std::wstring>(std::wstring &,ushort const *,char * &)
0x1800213df  test    eax, eax
0x1800213e1  jns     short loc_1800213FD
0x1800213e3  mov     rcx, [rsp+38h]; this
0x1800213e8  mov     r9d, eax; char *
0x1800213eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800213f2  mov     edx, 7F0h; void *
0x1800213f7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800213fd  mov     rax, rbx
0x180021400  add     rsp, 30h
0x180021404  pop     rbx
0x180021405  retn
```
