# std::_Destroy_range<std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)

- ea: `0x18000bc6c`
- end: `0x18000bca3`
- name: `??$_Destroy_range@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAXPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a8d0`
- `0x18000dc08`
- `0x18001f0e8`

## callees

- `0x18000bc6c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc89`

## pseudocode

```c
HRESULT __fastcall std::_Destroy_range<std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>(
        HSTRING *a1,
        HSTRING *a2)
{
  HSTRING *v3; // rbx
  HRESULT result; // eax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      if ( *v3 )
        result = WindowsDeleteString(*v3);
      v3 += 3;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000bc6c  cmp     rcx, rdx
0x18000bc6f  jz      short locret_18000BCA2
0x18000bc71  mov     [rsp+arg_0], rbx
0x18000bc76  push    rdi
0x18000bc77  sub     rsp, 20h
0x18000bc7b  mov     rdi, rdx
0x18000bc7e  mov     rbx, rcx
0x18000bc81  mov     rcx, [rbx]; string
0x18000bc84  test    rcx, rcx
0x18000bc87  jz      short loc_18000BC8F
0x18000bc89  call    cs:__imp_WindowsDeleteString
0x18000bc8f  add     rbx, 18h
0x18000bc93  cmp     rbx, rdi
0x18000bc96  jnz     short loc_18000BC81
0x18000bc98  mov     rbx, [rsp+28h+arg_0]
0x18000bc9d  add     rsp, 20h
0x18000bca1  pop     rdi
0x18000bca2  retn
```
