# Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)

- ea: `0x18002699c`
- end: `0x1800269cc`
- name: `?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ`
- size: `48`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`
- `0x180009730`
- `0x18000b520`
- `0x18000c9b8`

## callees

- `0x180004db8`
- `0x18001de54`

## string_xrefs

- `0x1800269af`: `Effect is too complex.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
{
  __int64 v0; // rcx
  _BYTE v1[32]; // [rsp+20h] [rbp-38h] BYREF

  std::wstring::wstring(v1, L"Effect is too complex.");
  Windows::UI::Composition::OriginateException(v0, v1);
}

```

## disassembly

```asm
0x18002699c  sub     rsp, 58h
0x1800269a0  mov     rax, cs:__security_cookie
0x1800269a7  xor     rax, rsp
0x1800269aa  mov     [rsp+58h+var_18], rax
0x1800269af  lea     rdx, aEffectIsTooCom; "Effect is too complex."
0x1800269b6  lea     rcx, [rsp+58h+var_38]
0x1800269bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800269c0  nop
0x1800269c1  lea     rdx, [rsp+58h+var_38]
0x1800269c6  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
```
