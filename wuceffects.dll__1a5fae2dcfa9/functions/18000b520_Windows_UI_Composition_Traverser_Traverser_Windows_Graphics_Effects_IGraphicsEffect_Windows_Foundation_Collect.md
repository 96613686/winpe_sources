# Windows::UI::Composition::Traverser::Traverser(Windows::Graphics::Effects::IGraphicsEffect *,Windows::Foundation::Collections::IIterable<HSTRING__ *> *)

- ea: `0x18000b520`
- end: `0x18000b859`
- name: `??0Traverser@Composition@UI@Windows@@QEAA@PEAUIGraphicsEffect@Effects@Graphics@3@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@3@@Z`
- size: `825`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Traverser *this, struct Windows::Graphics::Effects::IGraphicsEffect *)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x18000b170`

## callees

- `0x180004550`
- `0x180004df4`
- `0x180005ce0`
- `0x180006138`
- `0x180006410`
- `0x180009110`
- `0x180009df0`
- `0x180009ee8`
- `0x18000a810`
- `0x18000b520`
- `0x18000b900`
- `0x18000b958`
- `0x18000c7f0`
- `0x18000c868`
- `0x180017910`
- `0x180019b84`
- `0x18001a3bc`
- `0x18001eaa0`
- `0x180021060`
- `0x18002699c`
- `0x18002e010`

## string_xrefs

- `0x18000b617`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000b64f`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000b7b6`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
Windows::UI::Composition::Traverser *__fastcall Windows::UI::Composition::Traverser::Traverser(
        struct Windows::Graphics::Effects::IGraphicsEffect ***this,
        struct Windows::Graphics::Effects::IGraphicsEffect *a2,
        __int64 a3)
{
  Windows::UI::Composition::FlattenedEffectGraph *v6; // rax
  struct Windows::Graphics::Effects::IGraphicsEffect **v7; // rdi
  struct Windows::Graphics::Effects::IGraphicsEffect **v8; // rcx
  int v9; // eax
  int v10; // eax
  struct Windows::UI::Composition::EffectType *v11; // rax
  unsigned int **v12; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffect **v13; // rdi
  struct Windows::Graphics::Effects::IGraphicsEffect **v14; // r14
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v15; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffect *v17; // r15
  _OWORD *v18; // rax
  unsigned int **v19; // rsi
  unsigned int ***v20; // rdx
  _QWORD *v21; // rcx
  int v22; // eax
  struct Windows::UI::Composition::CSingleInputCompositeEffect **v23; // rdx
  __int64 v24; // rcx
  unsigned int **v25; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v26; // [rsp+28h] [rbp-48h] BYREF
  __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v28[3]; // [rsp+38h] [rbp-38h] BYREF
  struct _GUID v29; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v28[1] = this;
  *this = 0;
  std::unordered_set<Windows::Graphics::Effects::IGraphicsEffect *>::unordered_set<Windows::Graphics::Effects::IGraphicsEffect *>(this + 1);
  std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(this + 9);
  std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(this + 12);
  std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(this + 15);
  v6 = (Windows::UI::Composition::FlattenedEffectGraph *)operator new(0x80u);
  v28[0] = v6;
  if ( v6 )
    v7 = (struct Windows::Graphics::Effects::IGraphicsEffect **)Windows::UI::Composition::FlattenedEffectGraph::FlattenedEffectGraph(v6);
  else
    v7 = 0;
  if ( *this != v7 )
  {
    if ( v7 )
      (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect **))*v7)(v7);
    v8 = *this;
    *this = v7;
    if ( v8 )
      (*((void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect **))*v8 + 1))(v8);
  }
  v26 = 0;
  Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs((Windows::UI::Composition::Traverser *)this, a2, 0, 0);
  v25 = 0;
  v9 = (**(__int64 (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffect *, GUID *, unsigned int ***))a2)(
         a2,
         &GUID_2fc57384_a068_44d7_a331_30982fcf7177,
         &v25);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v9,
      (int)v25);
  v29 = 0;
  v10 = (*((__int64 (__fastcall **)(unsigned int **, struct _GUID *))*v25 + 3))(v25, &v29);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v10,
      (int)v25);
  v11 = Windows::UI::Composition::EffectType::FromGuid(&v29);
  if ( (*(unsigned __int8 (__fastcall **)(struct Windows::UI::Composition::EffectType *))(*(_QWORD *)v11 + 40LL))(v11) )
  {
    v27 = 0;
    v22 = (**(__int64 (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffect *, GUID *, __int64 *))a2)(
            a2,
            &GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2,
            &v27);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v22,
        (int)v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v26);
    Windows::UI::Composition::CSingleInputCompositeEffect::Create(&v26);
    Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffectSource>::operator=((char *)v26 + 24, v27);
    v28[0] = v26;
    v23 = this[13];
    if ( v23 == this[14] )
    {
      std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(
        this + 12,
        v23,
        v28);
    }
    else
    {
      *v23 = v26;
      ++this[13];
    }
    v24 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  v12 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*((void (__fastcall **)(unsigned int **))*v12 + 2))(v12);
  }
  v13 = this[12];
  v14 = this[13];
  while ( v13 != v14 )
  {
    v17 = *v13;
    v18 = operator new(0x38u);
    if ( v18 )
    {
      *v18 = 0;
      v18[1] = 0;
      v18[2] = 0;
      *((_QWORD *)v18 + 6) = 0;
      v19 = (unsigned int **)Windows::UI::Composition::EffectSubgraph::EffectSubgraph((Windows::UI::Composition::EffectSubgraph *)v18);
    }
    else
    {
      v19 = 0;
    }
    v25 = v19;
    Windows::UI::Composition::Traverser::VisitEffect((Windows::UI::Composition::Traverser *)this, v17, v19);
    v20 = (unsigned int ***)(*this)[4];
    v21 = *this + 3;
    if ( (unsigned int ***)((char *)v20 - *v21) == (unsigned int ***)40 )
      Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
    if ( v20 == (unsigned int ***)(*this)[5] )
    {
      std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>(
        v21,
        v20,
        &v25);
    }
    else
    {
      v25 = 0;
      *v20 = v19;
      v21[1] += 8LL;
    }
    std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>(&v25);
    ++v13;
  }
  Windows::UI::Composition::Traverser::VisitAnimatableProperties(
    (Windows::UI::Composition::FlattenedEffectGraph **)this,
    a3);
  Windows::UI::Composition::FlattenedEffectGraph::Finalize((Windows::UI::Composition::FlattenedEffectGraph *)*this);
  v15 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (Windows::UI::Composition::Traverser *)this;
}

```

## disassembly

```asm
0x18000b520  push    rbp
0x18000b522  push    rbx
0x18000b523  push    rsi
0x18000b524  push    rdi
0x18000b525  push    r12
0x18000b527  push    r14
0x18000b529  push    r15
0x18000b52b  mov     rbp, rsp
0x18000b52e  sub     rsp, 70h
0x18000b532  mov     rax, cs:__security_cookie
0x18000b539  xor     rax, rsp
0x18000b53c  mov     [rbp+var_10], rax
0x18000b540  mov     r12, r8
0x18000b543  mov     r14, rdx
0x18000b546  mov     rbx, rcx
0x18000b549  mov     [rbp+var_30], rcx
0x18000b54d  mov     qword ptr [rcx], 0
0x18000b554  add     rcx, 8
0x18000b558  call    ??0?$unordered_set@PEAUIGraphicsEffect@Effects@Graphics@Windows@@U?$hash@PEAUIGraphicsEffect@Effects@Graphics@Windows@@@std@@U?$equal_to@PEAUIGraphicsEffect@Effects@Graphics@Windows@@@6@V?$allocator@PEAUIGraphicsEffect@Effects@Graphics@Windows@@@6@@std@@QEAA@XZ; std::unordered_set<Windows::Graphics::Effects::IGraphicsEffect *>::unordered_set<Windows::Graphics::Effects::IGraphicsEffect *>(void)
0x18000b55d  nop
0x18000b55e  lea     rcx, [rbx+48h]
0x18000b562  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000b567  nop
0x18000b568  lea     rsi, [rbx+60h]
0x18000b56c  mov     rcx, rsi
0x18000b56f  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000b574  nop
0x18000b575  lea     rcx, [rbx+78h]
0x18000b579  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000b57e  nop
0x18000b57f  mov     ecx, 80h; dwBytes
0x18000b584  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b589  mov     [rbp+var_38], rax
0x18000b58d  test    rax, rax
0x18000b590  jz      loc_18000B783
0x18000b596  mov     rcx, rax; this
0x18000b599  call    ??0FlattenedEffectGraph@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::FlattenedEffectGraph::FlattenedEffectGraph(void)
0x18000b59e  mov     rdi, rax
0x18000b5a1  cmp     [rbx], rdi
0x18000b5a4  jz      short loc_18000B5D2
0x18000b5a6  test    rdi, rdi
0x18000b5a9  jz      short loc_18000B5BA
0x18000b5ab  mov     rax, [rdi]
0x18000b5ae  mov     rcx, rdi
0x18000b5b1  mov     rax, [rax]
0x18000b5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b9  nop
0x18000b5ba  mov     rcx, [rbx]
0x18000b5bd  mov     [rbx], rdi
0x18000b5c0  test    rcx, rcx
0x18000b5c3  jz      short loc_18000B5D2
0x18000b5c5  mov     rax, [rcx]
0x18000b5c8  mov     rax, [rax+8]
0x18000b5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d1  nop
0x18000b5d2  mov     [rbp+var_48], 0
0x18000b5da  xor     r9d, r9d; bool
0x18000b5dd  xor     r8d, r8d; bool
0x18000b5e0  mov     rdx, r14; struct Windows::Graphics::Effects::IGraphicsEffect *
0x18000b5e3  mov     rcx, rbx; this
0x18000b5e6  call    ?EnumerateEffectSubgraphs@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffect@Effects@Graphics@4@_N1@Z; Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs(Windows::Graphics::Effects::IGraphicsEffect *,bool,bool)
0x18000b5eb  mov     [rbp+var_50], 0
0x18000b5f3  mov     rax, [r14]
0x18000b5f6  lea     r8, [rbp+var_50]
0x18000b5fa  lea     rdx, _GUID_2fc57384_a068_44d7_a331_30982fcf7177
0x18000b601  mov     rcx, r14
0x18000b604  mov     rax, [rax]
0x18000b607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60c  mov     rcx, [rbp+38h]; this
0x18000b610  test    eax, eax
0x18000b612  jns     short loc_18000B629
0x18000b614  mov     r9d, eax; char *
0x18000b617  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000b61e  mov     edx, 9Fh; void *
0x18000b623  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b629  xorps   xmm0, xmm0
0x18000b62c  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000b630  mov     rcx, [rbp+var_50]
0x18000b634  mov     rax, [rcx]
0x18000b637  lea     rdx, [rbp+var_20]
0x18000b63b  mov     rax, [rax+18h]
0x18000b63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b644  mov     rcx, [rbp+38h]; this
0x18000b648  test    eax, eax
0x18000b64a  jns     short loc_18000B661
0x18000b64c  mov     r9d, eax; char *
0x18000b64f  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000b656  mov     edx, 0A2h; void *
0x18000b65b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b661  lea     rcx, [rbp+var_20]; struct _GUID *
0x18000b665  call    ?FromGuid@EffectType@Composition@UI@Windows@@SAPEAV1234@AEBU_GUID@@@Z; Windows::UI::Composition::EffectType::FromGuid(_GUID const &)
0x18000b66a  mov     rcx, rax
0x18000b66d  mov     rax, [rax]
0x18000b670  mov     rax, [rax+28h]
0x18000b674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b679  test    al, al
0x18000b67b  jnz     loc_18000B78A
0x18000b681  mov     rcx, [rbp+var_50]
0x18000b685  test    rcx, rcx
0x18000b688  jz      short loc_18000B69F
0x18000b68a  mov     [rbp+var_50], 0
0x18000b692  mov     rax, [rcx]
0x18000b695  mov     rax, [rax+10h]
0x18000b699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b69e  nop
0x18000b69f  mov     rdi, [rsi]
0x18000b6a2  mov     r14, [rsi+8]
0x18000b6a6  cmp     rdi, r14
0x18000b6a9  jnz     short loc_18000B6FB
0x18000b6ab  mov     rdx, r12
0x18000b6ae  mov     rcx, rbx
0x18000b6b1  call    ?VisitAnimatableProperties@Traverser@Composition@UI@Windows@@AEAAXPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@4@@Z; Windows::UI::Composition::Traverser::VisitAnimatableProperties(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)
0x18000b6b6  mov     rcx, [rbx]; this
0x18000b6b9  call    ?Finalize@FlattenedEffectGraph@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::FlattenedEffectGraph::Finalize(void)
0x18000b6be  nop
0x18000b6bf  mov     rcx, [rbp+var_48]
0x18000b6c3  test    rcx, rcx
0x18000b6c6  jz      short loc_18000B6DD
0x18000b6c8  mov     [rbp+var_48], 0
0x18000b6d0  mov     rdx, [rcx]
0x18000b6d3  mov     rax, [rdx+10h]
0x18000b6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6dc  nop
0x18000b6dd  mov     rax, rbx
0x18000b6e0  mov     rcx, [rbp+var_10]
0x18000b6e4  xor     rcx, rsp; StackCookie
0x18000b6e7  call    __security_check_cookie
0x18000b6ec  add     rsp, 70h
0x18000b6f0  pop     r15
0x18000b6f2  pop     r14
0x18000b6f4  pop     r12
0x18000b6f6  pop     rdi
0x18000b6f7  pop     rsi
0x18000b6f8  pop     rbx
0x18000b6f9  pop     rbp
0x18000b6fa  retn
0x18000b6fb  mov     r15, [rdi]
0x18000b6fe  mov     ecx, 38h ; '8'; dwBytes
0x18000b703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b708  test    rax, rax
0x18000b70b  jz      loc_18000B7C8
0x18000b711  xorps   xmm0, xmm0
0x18000b714  xor     ecx, ecx
0x18000b716  movups  xmmword ptr [rax], xmm0
0x18000b719  movups  xmmword ptr [rax+10h], xmm0
0x18000b71d  movups  xmmword ptr [rax+20h], xmm0
0x18000b721  mov     [rax+30h], rcx
0x18000b725  mov     rcx, rax; this
0x18000b728  call    ??0EffectSubgraph@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::EffectSubgraph::EffectSubgraph(void)
0x18000b72d  mov     rsi, rax
0x18000b730  mov     [rbp+var_50], rsi
0x18000b734  mov     r8, rsi; struct Windows::UI::Composition::EffectSubgraph *
0x18000b737  mov     rdx, r15; struct Windows::Graphics::Effects::IGraphicsEffect *
0x18000b73a  mov     rcx, rbx; this
0x18000b73d  call    ?VisitEffect@Traverser@Composition@UI@Windows@@AEAAIPEAUIGraphicsEffect@Effects@Graphics@4@PEAUEffectSubgraph@234@@Z; Windows::UI::Composition::Traverser::VisitEffect(Windows::Graphics::Effects::IGraphicsEffect *,Windows::UI::Composition::EffectSubgraph *)
0x18000b742  mov     rax, [rbx]
0x18000b745  mov     rdx, [rax+20h]
0x18000b749  lea     rcx, [rax+18h]
0x18000b74d  mov     rax, rdx
0x18000b750  sub     rax, [rcx]
0x18000b753  cmp     rax, 28h ; '('
0x18000b757  jz      loc_18000B853
0x18000b75d  cmp     rdx, [rcx+10h]
0x18000b761  jnz     loc_18000B83E
0x18000b767  lea     r8, [rbp+var_50]
0x18000b76b  call    ??$_Emplace_reallocate@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const,std::unique_ptr<Windows::UI::Composition::EffectSubgraph> &&)
0x18000b770  nop
0x18000b771  lea     rcx, [rbp+var_50]
0x18000b775  call    ??1?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectSubgraph>::~unique_ptr<Windows::UI::Composition::EffectSubgraph>(void)
0x18000b77a  add     rdi, 8
0x18000b77e  jmp     loc_18000B6A6
0x18000b783  xor     edi, edi
0x18000b785  jmp     loc_18000B5A1
0x18000b78a  mov     [rbp+var_40], 0
0x18000b792  mov     rax, [r14]
0x18000b795  lea     r8, [rbp+var_40]
0x18000b799  lea     rdx, _GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2
0x18000b7a0  mov     rcx, r14
0x18000b7a3  mov     rax, [rax]
0x18000b7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ab  mov     rcx, [rbp+38h]; this
0x18000b7af  test    eax, eax
0x18000b7b1  jns     short loc_18000B7CF
0x18000b7b3  mov     r9d, eax; char *
0x18000b7b6  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000b7bd  mov     edx, 0A8h; void *
0x18000b7c2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b7c8  xor     esi, esi
0x18000b7ca  jmp     loc_18000B730
0x18000b7cf  lea     rcx, [rbp+var_48]
0x18000b7d3  call    ?InternalRelease@?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(void)
0x18000b7d8  lea     rcx, [rbp+var_48]; struct Windows::UI::Composition::CSingleInputCompositeEffect **
0x18000b7dc  call    ?Create@CSingleInputCompositeEffect@Composition@UI@Windows@@SAXPEAPEAV1234@@Z; Windows::UI::Composition::CSingleInputCompositeEffect::Create(Windows::UI::Composition::CSingleInputCompositeEffect * *)
0x18000b7e1  mov     rcx, [rbp+var_48]
0x18000b7e5  add     rcx, 18h
0x18000b7e9  mov     rdx, [rbp+var_40]
0x18000b7ed  call    ??4?$ComPtr@UIGraphicsEffectSource@Effects@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIGraphicsEffectSource@Effects@Graphics@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffectSource>::operator=(Windows::Graphics::Effects::IGraphicsEffectSource *)
0x18000b7f2  mov     rax, [rbp+var_48]
0x18000b7f6  mov     [rbp+var_38], rax
0x18000b7fa  mov     rdx, [rsi+8]
0x18000b7fe  cmp     rdx, [rsi+10h]
0x18000b802  jnz     short loc_18000B834
0x18000b804  lea     r8, [rbp+var_38]
0x18000b808  mov     rcx, rsi
0x18000b80b  call    ??$_Emplace_reallocate@UEffectSubgraphInput@Composition@UI@Windows@@@?$vector@UEffectSubgraphInput@Composition@UI@Windows@@V?$allocator@UEffectSubgraphInput@Composition@UI@Windows@@@std@@@std@@AEAAPEAUEffectSubgraphInput@Composition@UI@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(Windows::UI::Composition::EffectSubgraphInput * const,Windows::UI::Composition::EffectSubgraphInput &&)
0x18000b810  nop
0x18000b811  mov     rcx, [rbp+var_40]
0x18000b815  test    rcx, rcx
0x18000b818  jz      short loc_18000B82F
0x18000b81a  mov     [rbp+var_40], 0
0x18000b822  mov     rax, [rcx]
0x18000b825  mov     rax, [rax+10h]
0x18000b829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82e  nop
0x18000b82f  jmp     loc_18000B681
0x18000b834  mov     [rdx], rax
0x18000b837  add     qword ptr [rsi+8], 8
0x18000b83c  jmp     short loc_18000B811
0x18000b83e  mov     [rbp+var_50], 0
0x18000b846  mov     [rdx], rsi
0x18000b849  add     qword ptr [rcx+8], 8
0x18000b84e  jmp     loc_18000B771
0x18000b853  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
```
