# Windows::UI::Composition::CompositeEffectType::Validate(Windows::UI::Composition::EffectNode const &)

- ea: `0x1800180c0`
- end: `0x18001811f`
- name: `?Validate@CompositeEffectType@Composition@UI@Windows@@UEBAXAEBVEffectNode@234@@Z`
- size: `95`
- prototype: `void __fastcall(Windows::UI::Composition::CompositeEffectType *__hidden this, const struct Windows::UI::Composition::EffectNode *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004db8`
- `0x1800180c0`
- `0x18001de54`
- `0x180021060`

## string_xrefs

- `0x180018102`: `Unsupported composite mode.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::UI::Composition::CompositeEffectType::Validate(
        Windows::UI::Composition::CompositeEffectType *this,
        const struct Windows::UI::Composition::EffectNode *a2)
{
  __int64 v2; // rcx
  _BYTE v3[32]; // [rsp+20h] [rbp-38h] BYREF

  if ( **((_DWORD **)a2 + 3) >= 0xDu || !off_1800327F0[**((int **)a2 + 3)] )
  {
    std::wstring::wstring(v3, L"Unsupported composite mode.");
    Windows::UI::Composition::OriginateException(v2, v3);
  }
}

```

## disassembly

```asm
0x1800180c0  sub     rsp, 58h
0x1800180c4  mov     rax, cs:__security_cookie
0x1800180cb  xor     rax, rsp
0x1800180ce  mov     [rsp+58h+var_18], rax
0x1800180d3  mov     rax, [rdx+18h]
0x1800180d7  movsxd  rax, dword ptr [rax]
0x1800180da  cmp     eax, 0Dh
0x1800180dd  jnb     short loc_180018102
0x1800180df  mov     rcx, rax
0x1800180e2  lea     rax, off_1800327F0; "SourceOver"
0x1800180e9  cmp     qword ptr [rax+rcx*8], 0
0x1800180ee  jz      short loc_180018102
0x1800180f0  mov     rcx, [rsp+58h+var_18]
0x1800180f5  xor     rcx, rsp; StackCookie
0x1800180f8  call    __security_check_cookie
0x1800180fd  add     rsp, 58h
0x180018101  retn
0x180018102  lea     rdx, aUnsupportedCom; "Unsupported composite mode."
0x180018109  lea     rcx, [rsp+58h+var_38]
0x18001810e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180018113  nop
0x180018114  lea     rdx, [rsp+58h+var_38]
0x180018119  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
```
