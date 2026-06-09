# std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>::_Tidy(void)

- ea: `0x180017e10`
- end: `0x180017ebe`
- name: `?_Tidy@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXXZ`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017dfc`

## callees

- `0x180017e10`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e3b`

## pseudocode

```c
__int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Tidy(__int64 a1)
{
  HSTRING *v1; // rbx
  HSTRING *i; // rsi
  void *v4; // rcx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  __int64 result; // rax
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(HSTRING **)(a1 + 8); v1 != i; v1 += 3 )
    {
      if ( *v1 )
        WindowsDeleteString(*v1);
    }
    v4 = *(void **)a1;
    v5 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    v9 = *(void **)a1;
    v6 = 24 * v5;
    v8 = 24 * v5;
    if ( 24 * v5 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v9, &v8);
      v6 = v8;
      v4 = v9;
    }
    operator delete(v4, v6);
    result = 0;
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017e10  mov     [rsp+arg_18], rbx
0x180017e15  push    rdi
0x180017e16  sub     rsp, 20h
0x180017e1a  mov     rbx, [rcx]
0x180017e1d  mov     rdi, rcx
0x180017e20  test    rbx, rbx
0x180017e23  jz      short loc_180017E98
0x180017e25  mov     [rsp+28h+arg_10], rsi
0x180017e2a  mov     rsi, [rcx+8]
0x180017e2e  cmp     rbx, rsi
0x180017e31  jz      short loc_180017E4A
0x180017e33  mov     rcx, [rbx]; string
0x180017e36  test    rcx, rcx
0x180017e39  jz      short loc_180017E41
0x180017e3b  call    cs:__imp_WindowsDeleteString
0x180017e41  add     rbx, 18h
0x180017e45  cmp     rbx, rsi
0x180017e48  jnz     short loc_180017E33
0x180017e4a  mov     rcx, [rdi]; void *
0x180017e4d  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180017e57  mov     rax, [rdi+10h]
0x180017e5b  mov     rsi, [rsp+28h+arg_10]
0x180017e60  sub     rax, rcx
0x180017e63  sar     rax, 3
0x180017e67  imul    rax, rdx
0x180017e6b  mov     [rsp+28h+arg_8], rcx
0x180017e70  lea     rdx, [rax+rax*2]
0x180017e74  shl     rdx, 3; unsigned __int64
0x180017e78  mov     [rsp+28h+arg_0], rdx
0x180017e7d  cmp     rdx, 1000h
0x180017e84  jnb     short loc_180017EA3
0x180017e86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017e8b  xor     eax, eax
0x180017e8d  mov     [rdi], rax
0x180017e90  mov     [rdi+8], rax
0x180017e94  mov     [rdi+10h], rax
0x180017e98  mov     rbx, [rsp+28h+arg_18]
0x180017e9d  add     rsp, 20h
0x180017ea1  pop     rdi
0x180017ea2  retn
0x180017ea3  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x180017ea8  lea     rcx, [rsp+28h+arg_8]; void **
0x180017ead  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180017eb2  mov     rdx, [rsp+28h+arg_0]
0x180017eb7  mov     rcx, [rsp+28h+arg_8]
0x180017ebc  jmp     short loc_180017E86
```
