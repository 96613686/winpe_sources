# Windows::UI::Composition::EffectGenerator::InitializeSamplerData(Windows::UI::Composition::EffectSubgraph const &)

- ea: `0x18000bfb0`
- end: `0x18000c2f0`
- name: `?InitializeSamplerData@EffectGenerator@Composition@UI@Windows@@AEAAXAEBUEffectSubgraph@234@@Z`
- size: `832`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *__hidden this, const struct Windows::UI::Composition::EffectSubgraph *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008320`

## callees

- `0x18000a88c`
- `0x18000ad10`
- `0x18000ad40`
- `0x18000bfb0`
- `0x18000c330`
- `0x18000c75c`
- `0x18000c7a0`
- `0x18001a8b0`
- `0x180021ce0`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000c22c`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000c22c`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectGenerator::InitializeSamplerData(
        Windows::UI::Composition::EffectGenerator *this,
        const struct Windows::UI::Composition::EffectSubgraph *a2)
{
  _QWORD *v4; // r14
  int v5; // ebx
  int v6; // eax
  _DWORD *v7; // rdx
  __int64 v8; // r10
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  unsigned __int64 i; // r8
  __int64 v12; // r12
  __int64 v13; // rdi
  __int64 v14; // r12
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rcx
  __int64 v18; // rbp
  unsigned __int64 v19; // rdx
  SIZE_T size_of; // rax
  char *v21; // r15
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // rax
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  __int64 v27; // rbp
  unsigned __int64 v28; // rdx
  SIZE_T v29; // rax
  char *v30; // r15
  __int64 v31; // rcx
  __int64 j; // rbx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rcx
  int v36; // edi
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax

  v4 = (_QWORD *)((char *)this + 24);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 32LL))(*(_QWORD *)this + 16LL);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 24LL))(*(_QWORD *)this + 16LL);
  v7 = (_DWORD *)*((_QWORD *)this + 4);
  v8 = *((_QWORD *)this + 3);
  v9 = (unsigned int)(v6 + v5 - 1);
  v10 = ((__int64)v7 - v8) >> 3;
  if ( v9 < v10 )
  {
    *((_QWORD *)this + 4) = v8 + 8 * v9;
  }
  else if ( v9 > v10 )
  {
    if ( v9 > (*((_QWORD *)this + 5) - v8) >> 3 )
    {
      std::vector<Windows::UI::Composition::EffectGenerator::SurfaceData>::_Resize_reallocate<std::_Value_init_tag>(
        (char *)this + 24,
        v9);
    }
    else
    {
      for ( i = v9 - v10; i; --i )
      {
        *v7 = -1;
        v7[1] = 0;
        v7 += 2;
      }
      *((_QWORD *)this + 4) = v7;
    }
  }
  v12 = *((_QWORD *)a2 + 4) - *((_QWORD *)a2 + 3);
  v13 = *((_QWORD *)this + 1);
  v14 = v12 >> 3;
  v15 = *(_QWORD *)(v13 + 88);
  v16 = (*(_QWORD *)(v13 + 96) - v15) >> 2;
  if ( (unsigned int)v14 < v16 )
  {
    v38 = v15 + 4LL * (unsigned int)v14;
LABEL_36:
    *(_QWORD *)(v13 + 96) = v38;
    goto LABEL_16;
  }
  if ( (unsigned int)v14 <= v16 )
    goto LABEL_16;
  v17 = (*(_QWORD *)(v13 + 104) - v15) >> 2;
  if ( (unsigned int)v14 <= v17 )
  {
    v38 = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(
            *(_QWORD *)(v13 + 96),
            (unsigned int)v14 - v16);
    goto LABEL_36;
  }
  v18 = 0x3FFFFFFFFFFFFFFFLL;
  v19 = v17 >> 1;
  if ( v17 <= 0x3FFFFFFFFFFFFFFFLL - (v17 >> 1) )
  {
    v18 = v17 + v19;
    if ( v17 + v19 < (unsigned int)v14 )
      v18 = (unsigned int)v14;
  }
  size_of = std::_Get_size_of_n<4>(v18);
  v21 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(
    &v21[4 * v16],
    (unsigned int)v14 - v16);
  memmove_0(v21, *(const void **)(v13 + 88), *(_QWORD *)(v13 + 96) - *(_QWORD *)(v13 + 88));
  v22 = *(_QWORD *)(v13 + 88);
  if ( v22 )
    std::_Deallocate<16>(v22, (*(_QWORD *)(v13 + 104) - v22) & 0xFFFFFFFFFFFFFFFCuLL);
  *(_QWORD *)(v13 + 88) = v21;
  *(_QWORD *)(v13 + 96) = &v21[4 * (unsigned int)v14];
  *(_QWORD *)(v13 + 104) = &v21[4 * v18];
LABEL_16:
  v23 = *((_QWORD *)this + 1);
  v24 = *(_QWORD *)(v23 + 112);
  v25 = (*(_QWORD *)(v23 + 120) - v24) >> 3;
  if ( (unsigned int)v14 < v25 )
  {
    v39 = v24 + 8LL * (unsigned int)v14;
LABEL_38:
    *(_QWORD *)(v23 + 120) = v39;
    goto LABEL_25;
  }
  if ( (unsigned int)v14 <= v25 )
    goto LABEL_25;
  v26 = (*(_QWORD *)(v23 + 128) - v24) >> 3;
  if ( (unsigned int)v14 <= v26 )
  {
    v39 = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(
            *(_QWORD *)(v23 + 120),
            (unsigned int)v14 - v25);
    goto LABEL_38;
  }
  v27 = 0x1FFFFFFFFFFFFFFFLL;
  v28 = v26 >> 1;
  if ( v26 <= 0x1FFFFFFFFFFFFFFFLL - (v26 >> 1) )
  {
    v27 = v26 + v28;
    if ( v26 + v28 < (unsigned int)v14 )
      v27 = (unsigned int)v14;
  }
  v29 = std::_Get_size_of_n<8>(v27);
  v30 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v29);
  std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(
    &v30[8 * v25],
    (unsigned int)v14 - v25);
  memmove_0(v30, *(const void **)(v23 + 112), *(_QWORD *)(v23 + 120) - *(_QWORD *)(v23 + 112));
  v31 = *(_QWORD *)(v23 + 112);
  if ( v31 )
    std::_Deallocate<16>(v31, (*(_QWORD *)(v23 + 128) - v31) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_QWORD *)(v23 + 112) = v30;
  *(_QWORD *)(v23 + 120) = &v30[8 * (unsigned int)v14];
  *(_QWORD *)(v23 + 128) = &v30[8 * v27];
LABEL_25:
  for ( j = 0; (unsigned int)j < (unsigned int)v14; j = (unsigned int)(j + 1) )
  {
    v33 = *((_QWORD *)this + 1);
    v34 = *(_QWORD *)(v33 + 112);
    if ( (*(_QWORD *)(v33 + 120) - v34) >> 3 <= (unsigned __int64)(unsigned int)j
      || ((v35 = *((_QWORD *)a2 + 3),
           *(_DWORD *)(v34 + 8 * j) = *(_DWORD *)(v35 + 8 * j + 4),
           (*(_BYTE *)(v34 + 8 * j + 4) = *(_BYTE *)(v35 + 8 * j)) != 0)
        ? (v36 = *(_DWORD *)(v35 + 8 * j + 4),
           v37 = v36
               + (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 24LL))(*(_QWORD *)this + 16LL))
        : (v37 = *(_DWORD *)(v35 + 8 * j + 4)),
          (__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) >> 3 <= (unsigned __int64)v37) )
    {
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    *(_DWORD *)(*v4 + 8LL * v37) = j;
  }
}

```

## disassembly

```asm
0x18000bfb0  mov     [rsp+arg_8], rdx
0x18000bfb5  push    rbx
0x18000bfb6  push    rbp
0x18000bfb7  push    rsi
0x18000bfb8  push    rdi
0x18000bfb9  push    r12
0x18000bfbb  push    r13
0x18000bfbd  push    r14
0x18000bfbf  push    r15
0x18000bfc1  sub     rsp, 28h
0x18000bfc5  mov     r13, rcx
0x18000bfc8  mov     rdi, rdx
0x18000bfcb  mov     rcx, [rcx]
0x18000bfce  add     rcx, 10h
0x18000bfd2  mov     rax, [rcx]
0x18000bfd5  mov     rax, [rax+20h]
0x18000bfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfde  mov     rcx, [r13+0]
0x18000bfe2  lea     r14, [r13+18h]
0x18000bfe6  add     rcx, 10h
0x18000bfea  mov     ebx, eax
0x18000bfec  mov     rdx, [rcx]
0x18000bfef  mov     rax, [rdx+18h]
0x18000bff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff8  mov     rdx, [r14+8]
0x18000bffc  lea     r8d, [rbx-1]
0x18000c000  mov     r10, [r14]
0x18000c003  mov     r9, rdx
0x18000c006  sub     r9, r10
0x18000c009  add     r8d, eax
0x18000c00c  sar     r9, 3
0x18000c010  xor     ecx, ecx
0x18000c012  cmp     r8, r9
0x18000c015  jb      loc_18000C294
0x18000c01b  jbe     short loc_18000C04D
0x18000c01d  mov     rax, [r14+10h]
0x18000c021  sub     rax, r10
0x18000c024  sar     rax, 3
0x18000c028  cmp     r8, rax
0x18000c02b  ja      loc_18000C24B
0x18000c031  sub     r8, r9
0x18000c034  jz      short loc_18000C049
0x18000c036  mov     dword ptr [rdx], 0FFFFFFFFh
0x18000c03c  mov     [rdx+4], ecx
0x18000c03f  add     rdx, 8
0x18000c043  sub     r8, 1
0x18000c047  jnz     short loc_18000C036
0x18000c049  mov     [r14+8], rdx
0x18000c04d  mov     r12, [rdi+20h]
0x18000c051  sub     r12, [rdi+18h]
0x18000c055  mov     rdi, [r13+8]
0x18000c059  sar     r12, 3
0x18000c05d  mov     ebx, r12d
0x18000c060  mov     rax, [rdi+58h]
0x18000c064  mov     rsi, [rdi+60h]
0x18000c068  sub     rsi, rax
0x18000c06b  sar     rsi, 2
0x18000c06f  cmp     rbx, rsi
0x18000c072  jb      loc_18000C27A
0x18000c078  jbe     loc_18000C10E
0x18000c07e  mov     rcx, [rdi+68h]
0x18000c082  sub     rcx, rax
0x18000c085  sar     rcx, 2
0x18000c089  cmp     rbx, rcx
0x18000c08c  jbe     loc_18000C2B6
0x18000c092  mov     rdx, rcx
0x18000c095  mov     rbp, 3FFFFFFFFFFFFFFFh
0x18000c09f  shr     rdx, 1
0x18000c0a2  mov     rax, rbp
0x18000c0a5  sub     rax, rdx
0x18000c0a8  cmp     rcx, rax
0x18000c0ab  ja      short loc_18000C0B8
0x18000c0ad  lea     rbp, [rcx+rdx]
0x18000c0b1  cmp     rbp, rbx
0x18000c0b4  cmovb   rbp, rbx
0x18000c0b8  mov     rcx, rbp
0x18000c0bb  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x18000c0c0  mov     rcx, rax; dwBytes
0x18000c0c3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000c0c8  mov     rdx, rbx
0x18000c0cb  mov     r15, rax
0x18000c0ce  sub     rdx, rsi
0x18000c0d1  lea     rcx, [rax+rsi*4]
0x18000c0d5  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData> &)
0x18000c0da  mov     rdx, [rdi+58h]; Src
0x18000c0de  mov     rcx, r15; void *
0x18000c0e1  mov     r8, [rdi+60h]
0x18000c0e5  sub     r8, rdx; Size
0x18000c0e8  call    memmove_0
0x18000c0ed  mov     rcx, [rdi+58h]
0x18000c0f1  test    rcx, rcx
0x18000c0f4  jnz     loc_18000C2A1
0x18000c0fa  lea     rax, [r15+rbx*4]
0x18000c0fe  mov     [rdi+58h], r15
0x18000c102  mov     [rdi+60h], rax
0x18000c106  lea     rax, [r15+rbp*4]
0x18000c10a  mov     [rdi+68h], rax
0x18000c10e  mov     rdi, [r13+8]
0x18000c112  mov     rax, [rdi+70h]
0x18000c116  mov     rsi, [rdi+78h]
0x18000c11a  sub     rsi, rax
0x18000c11d  sar     rsi, 3
0x18000c121  cmp     rbx, rsi
0x18000c124  jb      loc_18000C287
0x18000c12a  jbe     loc_18000C1C6
0x18000c130  mov     rcx, [rdi+80h]
0x18000c137  sub     rcx, rax
0x18000c13a  sar     rcx, 3
0x18000c13e  cmp     rbx, rcx
0x18000c141  jbe     loc_18000C2DF
0x18000c147  mov     rdx, rcx
0x18000c14a  mov     rbp, 1FFFFFFFFFFFFFFFh
0x18000c154  shr     rdx, 1
0x18000c157  mov     rax, rbp
0x18000c15a  sub     rax, rdx
0x18000c15d  cmp     rcx, rax
0x18000c160  ja      short loc_18000C16D
0x18000c162  lea     rbp, [rcx+rdx]
0x18000c166  cmp     rbp, rbx
0x18000c169  cmovb   rbp, rbx
0x18000c16d  mov     rcx, rbp
0x18000c170  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000c175  mov     rcx, rax; dwBytes
0x18000c178  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000c17d  mov     rdx, rbx
0x18000c180  mov     r15, rax
0x18000c183  sub     rdx, rsi
0x18000c186  lea     rcx, [rax+rsi*8]
0x18000c18a  call    ??$_Uninitialized_value_construct_n@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(Windows::UI::Composition::CompiledEffectSubgraph::InputBindings *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings> &)
0x18000c18f  mov     rdx, [rdi+70h]; Src
0x18000c193  mov     rcx, r15; void *
0x18000c196  mov     r8, [rdi+78h]
0x18000c19a  sub     r8, rdx; Size
0x18000c19d  call    memmove_0
0x18000c1a2  mov     rcx, [rdi+70h]
0x18000c1a6  test    rcx, rcx
0x18000c1a9  jnz     loc_18000C2C7
0x18000c1af  lea     rax, [r15+rbx*8]
0x18000c1b3  mov     [rdi+70h], r15
0x18000c1b7  mov     [rdi+78h], rax
0x18000c1bb  lea     rax, [r15+rbp*8]
0x18000c1bf  mov     [rdi+80h], rax
0x18000c1c6  xor     ebx, ebx
0x18000c1c8  test    r12d, r12d
0x18000c1cb  jz      loc_18000C269
0x18000c1d1  mov     rsi, [rsp+68h+arg_8]
0x18000c1d6  mov     rax, [r13+8]
0x18000c1da  mov     edx, ebx
0x18000c1dc  mov     r8, [rax+70h]
0x18000c1e0  mov     rcx, [rax+78h]
0x18000c1e4  sub     rcx, r8
0x18000c1e7  sar     rcx, 3
0x18000c1eb  cmp     rcx, rdx
0x18000c1ee  jbe     short loc_18000C225
0x18000c1f0  mov     rcx, [rsi+18h]
0x18000c1f4  mov     eax, [rcx+rbx*8+4]
0x18000c1f8  mov     [r8+rbx*8], eax
0x18000c1fc  mov     al, [rcx+rbx*8]
0x18000c1ff  mov     [r8+rbx*8+4], al
0x18000c204  cmp     byte ptr [rcx+rbx*8], 0
0x18000c208  mov     edi, [rcx+rbx*8+4]
0x18000c20c  jnz     short loc_18000C233
0x18000c20e  mov     eax, edi
0x18000c210  mov     rcx, [r14]
0x18000c213  mov     edx, eax
0x18000c215  mov     rax, [r14+8]
0x18000c219  sub     rax, rcx
0x18000c21c  sar     rax, 3
0x18000c220  cmp     rax, rdx
0x18000c223  ja      short loc_18000C25B
0x18000c225  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000c22c  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000c232  int     3; Trap to Debugger
0x18000c233  mov     rcx, [r13+0]
0x18000c237  add     rcx, 10h
0x18000c23b  mov     rax, [rcx]
0x18000c23e  mov     rax, [rax+18h]
0x18000c242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c247  add     eax, edi
0x18000c249  jmp     short loc_18000C210
0x18000c24b  mov     rdx, r8
0x18000c24e  mov     rcx, r14
0x18000c251  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USurfaceData@EffectGenerator@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectGenerator@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Windows::UI::Composition::EffectGenerator::SurfaceData>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c256  jmp     loc_18000C04D
0x18000c25b  mov     [rcx+rdx*8], ebx
0x18000c25e  inc     ebx
0x18000c260  cmp     ebx, r12d
0x18000c263  jb      loc_18000C1D6
0x18000c269  add     rsp, 28h
0x18000c26d  pop     r15
0x18000c26f  pop     r14
0x18000c271  pop     r13
0x18000c273  pop     r12
0x18000c275  pop     rdi
0x18000c276  pop     rsi
0x18000c277  pop     rbp
0x18000c278  pop     rbx
0x18000c279  retn
0x18000c27a  lea     rax, [rax+rbx*4]
0x18000c27e  mov     [rdi+60h], rax
0x18000c282  jmp     loc_18000C10E
0x18000c287  lea     rax, [rax+rbx*8]
0x18000c28b  mov     [rdi+78h], rax
0x18000c28f  jmp     loc_18000C1C6
0x18000c294  lea     rax, [r10+r8*8]
0x18000c298  mov     [r14+8], rax
0x18000c29c  jmp     loc_18000C04D
0x18000c2a1  mov     rdx, [rdi+68h]
0x18000c2a5  sub     rdx, rcx
0x18000c2a8  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000c2ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c2b1  jmp     loc_18000C0FA
0x18000c2b6  mov     rcx, [rdi+60h]
0x18000c2ba  mov     rdx, rbx
0x18000c2bd  sub     rdx, rsi
0x18000c2c0  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData> &)
0x18000c2c5  jmp     short loc_18000C27E
0x18000c2c7  mov     rdx, [rdi+80h]
0x18000c2ce  sub     rdx, rcx
0x18000c2d1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c2d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c2da  jmp     loc_18000C1AF
0x18000c2df  mov     rcx, [rdi+78h]
0x18000c2e3  sub     rbx, rsi
0x18000c2e6  mov     rdx, rbx
0x18000c2e9  call    ??$_Uninitialized_value_construct_n@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(Windows::UI::Composition::CompiledEffectSubgraph::InputBindings *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings> &)
0x18000c2ee  jmp     short loc_18000C28B
```
