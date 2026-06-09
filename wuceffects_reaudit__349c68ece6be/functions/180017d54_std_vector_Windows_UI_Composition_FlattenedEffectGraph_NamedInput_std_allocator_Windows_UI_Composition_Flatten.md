# std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>::~vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>(void)

- ea: `0x180017d54`
- end: `0x180017df5`
- name: `??1?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAA@XZ`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c0e0`

## callees

- `0x180017d54`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017d74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017d74`

## pseudocode

```c
void __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::~vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>(
        __int64 a1)
{
  HSTRING *v1; // rbx
  HSTRING *v3; // rsi
  void *v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  void *v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(HSTRING **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        WindowsDeleteString(*v1);
      v1 += 2;
    }
    v4 = *(void **)a1;
    v5 = *(_QWORD *)(a1 + 16) - *(_QWORD *)a1;
    v8 = *(void **)a1;
    v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
    v7 = v6;
    if ( v6 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v8, &v7);
      v6 = v7;
      v4 = v8;
    }
    operator delete(v4, v6);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180017d54  mov     [rsp+arg_10], rbx
0x180017d59  mov     [rsp+arg_18], rsi
0x180017d5e  push    rdi
0x180017d5f  sub     rsp, 20h
0x180017d63  mov     rbx, [rcx]
0x180017d66  mov     rdi, rcx
0x180017d69  test    rbx, rbx
0x180017d6c  jz      short loc_180017DCA
0x180017d6e  mov     rsi, [rcx+8]
0x180017d72  jmp     short loc_180017D7E
0x180017d74  call    cs:__imp_WindowsDeleteString
0x180017d7a  add     rbx, 10h
0x180017d7e  cmp     rbx, rsi
0x180017d81  jz      short loc_180017D8D
0x180017d83  mov     rcx, [rbx]; string
0x180017d86  test    rcx, rcx
0x180017d89  jz      short loc_180017D7A
0x180017d8b  jmp     short loc_180017D74
0x180017d8d  mov     rcx, [rdi]; void *
0x180017d90  mov     rdx, [rdi+10h]
0x180017d94  sub     rdx, rcx
0x180017d97  mov     [rsp+28h+arg_8], rcx
0x180017d9c  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180017da0  mov     [rsp+28h+arg_0], rdx
0x180017da5  cmp     rdx, 1000h
0x180017dac  jnb     short loc_180017DDA
0x180017dae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017db3  mov     qword ptr [rdi], 0
0x180017dba  mov     qword ptr [rdi+8], 0
0x180017dc2  mov     qword ptr [rdi+10h], 0
0x180017dca  mov     rbx, [rsp+28h+arg_10]
0x180017dcf  mov     rsi, [rsp+28h+arg_18]
0x180017dd4  add     rsp, 20h
0x180017dd8  pop     rdi
0x180017dd9  retn
0x180017dda  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x180017ddf  lea     rcx, [rsp+28h+arg_8]; void **
0x180017de4  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180017de9  mov     rdx, [rsp+28h+arg_0]
0x180017dee  mov     rcx, [rsp+28h+arg_8]
0x180017df3  jmp     short loc_180017DAE
```
