# std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,unsigned __int64,unsigned __int64)

- ea: `0x180016a90`
- end: `0x180016b42`
- name: `?_Change_array@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005c00`
- `0x180016944`

## callees

- `0x180016a90`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016ac8`

## pseudocode

```c
void __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HSTRING *v4; // rbx
  HSTRING *i; // rdi
  void *v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  void *v13; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(HSTRING **)(a1 + 8); v4 != i; v4 += 2 )
    {
      if ( *v4 )
        WindowsDeleteString(*v4);
    }
    v10 = *(void **)a1;
    v11 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = *(void **)a1;
    v12 = v11;
    if ( v11 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v13, &v12);
      v11 = v12;
      v10 = v13;
    }
    operator delete(v10, v11);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 16 * a3;
  *(_QWORD *)(a1 + 16) = a2 + 16 * a4;
}

```

## disassembly

```asm
0x180016a90  push    rbx
0x180016a92  push    rbp
0x180016a93  push    rsi
0x180016a94  push    r14
0x180016a96  push    r15
0x180016a98  sub     rsp, 20h
0x180016a9c  mov     rbx, [rcx]
0x180016a9f  mov     rbp, r9
0x180016aa2  mov     r14, r8
0x180016aa5  mov     r15, rdx
0x180016aa8  mov     rsi, rcx
0x180016aab  test    rbx, rbx
0x180016aae  jz      short loc_180016B02
0x180016ab0  mov     [rsp+48h+arg_10], rdi
0x180016ab5  mov     rdi, [rcx+8]
0x180016ab9  cmp     rbx, rdi
0x180016abc  jz      short loc_180016AD7
0x180016abe  xchg    ax, ax
0x180016ac0  mov     rcx, [rbx]; string
0x180016ac3  test    rcx, rcx
0x180016ac6  jz      short loc_180016ACE
0x180016ac8  call    cs:__imp_WindowsDeleteString
0x180016ace  add     rbx, 10h
0x180016ad2  cmp     rbx, rdi
0x180016ad5  jnz     short loc_180016AC0
0x180016ad7  mov     rcx, [rsi]; void *
0x180016ada  mov     rdx, [rsi+10h]
0x180016ade  mov     rdi, [rsp+48h+arg_10]
0x180016ae3  sub     rdx, rcx
0x180016ae6  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180016aea  mov     [rsp+48h+arg_8], rcx
0x180016aef  mov     [rsp+48h+arg_0], rdx
0x180016af4  cmp     rdx, 1000h
0x180016afb  jnb     short loc_180016B27
0x180016afd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b02  shl     r14, 4
0x180016b06  add     r14, r15
0x180016b09  mov     [rsi], r15
0x180016b0c  shl     rbp, 4
0x180016b10  add     rbp, r15
0x180016b13  mov     [rsi+8], r14
0x180016b17  mov     [rsi+10h], rbp
0x180016b1b  add     rsp, 20h
0x180016b1f  pop     r15
0x180016b21  pop     r14
0x180016b23  pop     rsi
0x180016b24  pop     rbp
0x180016b25  pop     rbx
0x180016b26  retn
0x180016b27  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x180016b2c  lea     rcx, [rsp+48h+arg_8]; void **
0x180016b31  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180016b36  mov     rdx, [rsp+48h+arg_0]
0x180016b3b  mov     rcx, [rsp+48h+arg_8]
0x180016b40  jmp     short loc_180016AFD
```
