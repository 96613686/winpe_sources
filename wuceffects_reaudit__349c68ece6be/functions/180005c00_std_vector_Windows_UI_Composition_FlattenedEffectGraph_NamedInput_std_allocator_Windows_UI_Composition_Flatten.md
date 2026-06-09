# std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput &&)

- ea: `0x180005c00`
- end: `0x180005cd7`
- name: `??$_Emplace_reallocate@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@$$QEAU23456@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005440`

## callees

- `0x180005c00`
- `0x18000ad40`
- `0x18000adc0`
- `0x180016a10`
- `0x180016a48`
- `0x180016a90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005c3a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005c3a`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v6; // rax
  __int64 v8; // rbp
  __int64 v9; // r15
  SIZE_T size_of; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r11

  v3 = *a1;
  v6 = (a1[1] - *a1) >> 4;
  if ( v6 == 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<16>(v9);
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = ((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL) + v11;
  *(_QWORD *)v12 = *(_QWORD *)a3;
  *(_QWORD *)a3 = 0;
  *(_DWORD *)(v12 + 8) = *(_DWORD *)(a3 + 8);
  *(_BYTE *)(v12 + 12) = *(_BYTE *)(a3 + 12);
  v13 = a1[1];
  v14 = *a1;
  if ( a2 != v13 )
  {
    std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(v14, a2, v11);
    v13 = a1[1];
    v11 = v12 + 16;
    v14 = a2;
  }
  std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(v14, v13, v11);
  std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Change_array((__int64)a1, v15, v8, v9);
  return v12;
}

```

## disassembly

```asm
0x180005c00  push    rbx
0x180005c02  push    rbp
0x180005c03  push    rsi
0x180005c04  push    rdi
0x180005c05  push    r14
0x180005c07  push    r15
0x180005c09  sub     rsp, 28h
0x180005c0d  mov     rsi, [rcx]
0x180005c10  mov     rbx, rcx
0x180005c13  mov     rax, [rcx+8]
0x180005c17  mov     r14, r8
0x180005c1a  sub     rax, rsi
0x180005c1d  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180005c27  sar     rax, 4
0x180005c2b  mov     rdi, rdx
0x180005c2e  cmp     rax, rcx
0x180005c31  jnz     short loc_180005C41
0x180005c33  lea     rcx, aVectorTooLong; "vector too long"
0x180005c3a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180005c41  lea     rbp, [rax+1]
0x180005c45  mov     rcx, rbx
0x180005c48  mov     rdx, rbp
0x180005c4b  call    ?_Calculate_growth@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEBA_K_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Calculate_growth(unsigned __int64)
0x180005c50  mov     rcx, rax
0x180005c53  mov     r15, rax
0x180005c56  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180005c5b  mov     rcx, rax; dwBytes
0x180005c5e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180005c63  mov     rcx, rdi
0x180005c66  mov     r11, rax
0x180005c69  sub     rcx, rsi
0x180005c6c  mov     r8, rax
0x180005c6f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180005c73  lea     rsi, [rcx+rax]
0x180005c77  mov     rcx, [r14]
0x180005c7a  mov     [rsi], rcx
0x180005c7d  mov     qword ptr [r14], 0
0x180005c84  mov     ecx, [r14+8]
0x180005c88  mov     [rsi+8], ecx
0x180005c8b  mov     cl, [r14+0Ch]
0x180005c8f  mov     [rsi+0Ch], cl
0x180005c92  mov     rdx, [rbx+8]
0x180005c96  mov     rcx, [rbx]
0x180005c99  cmp     rdi, rdx
0x180005c9c  jz      short loc_180005CB1
0x180005c9e  mov     rdx, rdi
0x180005ca1  call    ??$_Uninitialized_move@PEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput> &)
0x180005ca6  mov     rdx, [rbx+8]
0x180005caa  lea     r8, [rsi+10h]
0x180005cae  mov     rcx, rdi
0x180005cb1  call    ??$_Uninitialized_move@PEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput> &)
0x180005cb6  mov     r9, r15
0x180005cb9  mov     r8, rbp
0x180005cbc  mov     rdx, r11
0x180005cbf  mov     rcx, rbx
0x180005cc2  call    ?_Change_array@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,unsigned __int64,unsigned __int64)
0x180005cc7  mov     rax, rsi
0x180005cca  add     rsp, 28h
0x180005cce  pop     r15
0x180005cd0  pop     r14
0x180005cd2  pop     rdi
0x180005cd3  pop     rsi
0x180005cd4  pop     rbp
0x180005cd5  pop     rbx
0x180005cd6  retn
```
