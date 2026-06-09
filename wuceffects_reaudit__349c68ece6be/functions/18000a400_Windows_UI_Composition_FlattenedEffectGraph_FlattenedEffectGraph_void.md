# Windows::UI::Composition::FlattenedEffectGraph::~FlattenedEffectGraph(void)

- ea: `0x18000a400`
- end: `0x18000a617`
- name: `??1FlattenedEffectGraph@Composition@UI@Windows@@UEAA@XZ`
- size: `535`
- prototype: `void __fastcall(Windows::UI::Composition::FlattenedEffectGraph *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009f00`

## callees

- `0x18000a400`
- `0x18000a6d0`
- `0x18000a810`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a496`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a496`

## pseudocode

```c
void __fastcall Windows::UI::Composition::FlattenedEffectGraph::~FlattenedEffectGraph(
        Windows::UI::Composition::FlattenedEffectGraph *this)
{
  HSTRING *v1; // rdi
  HSTRING *i; // rsi
  void *v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  HSTRING *v7; // rdi
  HSTRING *j; // rsi
  void *v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 k; // rsi
  void *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 m; // rsi
  void *v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // [rsp+40h] [rbp+20h] BYREF
  void *v23; // [rsp+48h] [rbp+28h] BYREF

  v1 = (HSTRING *)*((_QWORD *)this + 12);
  if ( v1 )
  {
    for ( i = (HSTRING *)*((_QWORD *)this + 13); v1 != i; v1 += 2 )
    {
      if ( *v1 )
        WindowsDeleteString(*v1);
    }
    v4 = (void *)*((_QWORD *)this + 12);
    v5 = *((_QWORD *)this + 14) - (_QWORD)v4;
    v23 = v4;
    v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = v6;
    if ( v6 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v23, &v22);
      v6 = v22;
      v4 = v23;
    }
    operator delete(v4, v6);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
  }
  v7 = (HSTRING *)*((_QWORD *)this + 9);
  if ( v7 )
  {
    for ( j = (HSTRING *)*((_QWORD *)this + 10); v7 != j; v7 += 3 )
    {
      if ( *v7 )
        WindowsDeleteString(*v7);
    }
    v9 = (void *)*((_QWORD *)this + 9);
    v10 = *((_QWORD *)this + 11) - (_QWORD)v9;
    v23 = v9;
    v11 = 8 * (v10 >> 3);
    v22 = v11;
    if ( v11 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v23, &v22);
      v11 = v22;
      v9 = v23;
    }
    operator delete(v9, v11);
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  v12 = *((_QWORD *)this + 6);
  if ( v12 )
  {
    for ( k = *((_QWORD *)this + 7); v12 != k; v12 += 8 )
      std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(v12);
    v14 = (void *)*((_QWORD *)this + 6);
    v15 = *((_QWORD *)this + 8) - (_QWORD)v14;
    v23 = v14;
    v16 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
    v22 = v16;
    if ( v16 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v23, &v22);
      v16 = v22;
      v14 = v23;
    }
    operator delete(v14, v16);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
  v17 = *((_QWORD *)this + 3);
  if ( v17 )
  {
    for ( m = *((_QWORD *)this + 4); v17 != m; v17 += 8 )
      std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>(v17);
    v19 = (void *)*((_QWORD *)this + 3);
    v20 = *((_QWORD *)this + 5) - (_QWORD)v19;
    v23 = v19;
    v21 = v20 & 0xFFFFFFFFFFFFFFF8uLL;
    v22 = v21;
    if ( v21 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v23, &v22);
      v21 = v22;
      v19 = v23;
    }
    operator delete(v19, v21);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x18000a400  mov     [rsp-18h+arg_10], rbx
0x18000a405  mov     [rsp-18h+arg_18], rsi
0x18000a40a  push    rbp
0x18000a40b  push    rdi
0x18000a40c  push    r14
0x18000a40e  mov     rbp, rsp
0x18000a411  sub     rsp, 20h
0x18000a415  mov     rdi, [rcx+60h]
0x18000a419  xor     r14d, r14d
0x18000a41c  mov     rbx, rcx
0x18000a41f  test    rdi, rdi
0x18000a422  jz      short loc_18000A47C
0x18000a424  mov     rsi, [rcx+68h]
0x18000a428  cmp     rdi, rsi
0x18000a42b  jz      short loc_18000A447
0x18000a42d  nop     dword ptr [rax]
0x18000a430  mov     rcx, [rdi]; string
0x18000a433  test    rcx, rcx
0x18000a436  jz      short loc_18000A43E
0x18000a438  call    cs:__imp_WindowsDeleteString
0x18000a43e  add     rdi, 10h
0x18000a442  cmp     rdi, rsi
0x18000a445  jnz     short loc_18000A430
0x18000a447  mov     rcx, [rbx+60h]; void *
0x18000a44b  mov     rdx, [rbx+70h]
0x18000a44f  sub     rdx, rcx
0x18000a452  mov     [rbp+arg_8], rcx
0x18000a456  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18000a45a  mov     [rbp+arg_0], rdx
0x18000a45e  cmp     rdx, 1000h
0x18000a465  jnb     loc_18000A5AF
0x18000a46b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a470  mov     [rbx+60h], r14
0x18000a474  mov     [rbx+68h], r14
0x18000a478  mov     [rbx+70h], r14
0x18000a47c  mov     rdi, [rbx+48h]
0x18000a480  test    rdi, rdi
0x18000a483  jz      short loc_18000A4F0
0x18000a485  mov     rsi, [rbx+50h]
0x18000a489  cmp     rdi, rsi
0x18000a48c  jz      short loc_18000A4A5
0x18000a48e  mov     rcx, [rdi]; string
0x18000a491  test    rcx, rcx
0x18000a494  jz      short loc_18000A49C
0x18000a496  call    cs:__imp_WindowsDeleteString
0x18000a49c  add     rdi, 18h
0x18000a4a0  cmp     rdi, rsi
0x18000a4a3  jnz     short loc_18000A48E
0x18000a4a5  mov     rcx, [rbx+48h]; void *
0x18000a4a9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000a4b3  mov     rax, [rbx+58h]
0x18000a4b7  sub     rax, rcx
0x18000a4ba  mov     [rbp+arg_8], rcx
0x18000a4be  sar     rax, 3
0x18000a4c2  imul    rax, rdx
0x18000a4c6  lea     rdx, [rax+rax*2]
0x18000a4ca  shl     rdx, 3; unsigned __int64
0x18000a4ce  mov     [rbp+arg_0], rdx
0x18000a4d2  cmp     rdx, 1000h
0x18000a4d9  jnb     loc_18000A5C9
0x18000a4df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a4e4  mov     [rbx+48h], r14
0x18000a4e8  mov     [rbx+50h], r14
0x18000a4ec  mov     [rbx+58h], r14
0x18000a4f0  mov     rdi, [rbx+30h]
0x18000a4f4  test    rdi, rdi
0x18000a4f7  jz      short loc_18000A548
0x18000a4f9  mov     rsi, [rbx+38h]
0x18000a4fd  cmp     rdi, rsi
0x18000a500  jz      short loc_18000A513
0x18000a502  mov     rcx, rdi
0x18000a505  call    ??1?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(void)
0x18000a50a  add     rdi, 8
0x18000a50e  cmp     rdi, rsi
0x18000a511  jnz     short loc_18000A502
0x18000a513  mov     rcx, [rbx+30h]; void *
0x18000a517  mov     rdx, [rbx+40h]
0x18000a51b  sub     rdx, rcx
0x18000a51e  mov     [rbp+arg_8], rcx
0x18000a522  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000a526  mov     [rbp+arg_0], rdx
0x18000a52a  cmp     rdx, 1000h
0x18000a531  jnb     loc_18000A5E3
0x18000a537  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a53c  mov     [rbx+30h], r14
0x18000a540  mov     [rbx+38h], r14
0x18000a544  mov     [rbx+40h], r14
0x18000a548  mov     rdi, [rbx+18h]
0x18000a54c  test    rdi, rdi
0x18000a54f  jz      short loc_18000A59C
0x18000a551  mov     rsi, [rbx+20h]
0x18000a555  cmp     rdi, rsi
0x18000a558  jz      short loc_18000A56B
0x18000a55a  mov     rcx, rdi
0x18000a55d  call    ??1?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>(void)
0x18000a562  add     rdi, 8
0x18000a566  cmp     rdi, rsi
0x18000a569  jnz     short loc_18000A55A
0x18000a56b  mov     rcx, [rbx+18h]; void *
0x18000a56f  mov     rdx, [rbx+28h]
0x18000a573  sub     rdx, rcx
0x18000a576  mov     [rbp+arg_8], rcx
0x18000a57a  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000a57e  mov     [rbp+arg_0], rdx
0x18000a582  cmp     rdx, 1000h
0x18000a589  jnb     short loc_18000A5FD
0x18000a58b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a590  mov     [rbx+18h], r14
0x18000a594  mov     [rbx+20h], r14
0x18000a598  mov     [rbx+28h], r14
0x18000a59c  mov     rbx, [rsp+20h+arg_10]
0x18000a5a1  mov     rsi, [rsp+20h+arg_18]
0x18000a5a6  add     rsp, 20h
0x18000a5aa  pop     r14
0x18000a5ac  pop     rdi
0x18000a5ad  pop     rbp
0x18000a5ae  retn
0x18000a5af  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x18000a5b3  lea     rcx, [rbp+arg_8]; void **
0x18000a5b7  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a5bc  mov     rdx, [rbp+arg_0]
0x18000a5c0  mov     rcx, [rbp+arg_8]
0x18000a5c4  jmp     loc_18000A46B
0x18000a5c9  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x18000a5cd  lea     rcx, [rbp+arg_8]; void **
0x18000a5d1  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a5d6  mov     rdx, [rbp+arg_0]
0x18000a5da  mov     rcx, [rbp+arg_8]
0x18000a5de  jmp     loc_18000A4DF
0x18000a5e3  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x18000a5e7  lea     rcx, [rbp+arg_8]; void **
0x18000a5eb  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a5f0  mov     rdx, [rbp+arg_0]
0x18000a5f4  mov     rcx, [rbp+arg_8]
0x18000a5f8  jmp     loc_18000A537
0x18000a5fd  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x18000a601  lea     rcx, [rbp+arg_8]; void **
0x18000a605  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a60a  mov     rdx, [rbp+arg_0]
0x18000a60e  mov     rcx, [rbp+arg_8]
0x18000a612  jmp     loc_18000A58B
```
