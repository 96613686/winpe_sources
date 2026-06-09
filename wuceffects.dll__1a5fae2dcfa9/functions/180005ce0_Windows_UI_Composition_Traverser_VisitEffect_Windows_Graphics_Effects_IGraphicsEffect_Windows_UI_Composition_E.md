# Windows::UI::Composition::Traverser::VisitEffect(Windows::Graphics::Effects::IGraphicsEffect *,Windows::UI::Composition::EffectSubgraph *)

- ea: `0x180005ce0`
- end: `0x180006103`
- name: `?VisitEffect@Traverser@Composition@UI@Windows@@AEAAIPEAUIGraphicsEffect@Effects@Graphics@4@PEAUEffectSubgraph@234@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Traverser *this, struct Windows::Graphics::Effects::IGraphicsEffect *, unsigned int **)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005440`
- `0x18000b520`

## callees

- `0x180004db8`
- `0x180004ed0`
- `0x180004ffc`
- `0x1800050d0`
- `0x180005440`
- `0x180005ce0`
- `0x180006410`
- `0x180008b90`
- `0x18000a6d0`
- `0x18000badc`
- `0x18000d710`
- `0x180016240`
- `0x1800168d0`
- `0x18001b950`
- `0x18001bee8`
- `0x18001de54`
- `0x18001eaa0`
- `0x180021060`
- `0x18002699c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800060ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800060ee`

## string_xrefs

- `0x180005d38`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180005d70`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180005da8`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180005f22`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Traverser::VisitEffect(
        Windows::UI::Composition::Traverser *this,
        struct Windows::Graphics::Effects::IGraphicsEffect *a2,
        unsigned int **a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // ebx
  Windows::UI::Composition::EffectNode *v10; // rax
  Windows::UI::Composition::EffectNode *v11; // rsi
  Windows::UI::Composition::Traverser *v12; // rcx
  __int64 v13; // rdi
  _QWORD *v14; // rbx
  Windows::UI::Composition::EffectNode **v15; // rdx
  unsigned int v16; // edi
  unsigned int *v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  HSTRING v21; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v22; // rcx
  __int64 v24; // rsi
  HSTRING *v25; // rbx
  HSTRING v26; // r15
  HSTRING v27; // r14
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v34; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  Windows::UI::Composition::EffectNode *v36; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v38; // [rsp+3Ch] [rbp-44h] BYREF
  struct _GUID v39; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v40[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v34 = 0;
  v6 = (**(__int64 (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffect *, GUID *, struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop **))a2)(
         a2,
         &GUID_2fc57384_a068_44d7_a331_30982fcf7177,
         &v34);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v6,
      (int)v34);
  v39 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, struct _GUID *))(*(_QWORD *)v34 + 24LL))(
         v34,
         &v39);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v7,
      (int)v34);
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, unsigned int *))(*(_QWORD *)v34 + 64LL))(
         v34,
         &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v8,
      (int)v34);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 32LL))(*(_QWORD *)this + 16LL);
  v10 = (Windows::UI::Composition::EffectNode *)operator new(0x28u);
  v36 = v10;
  if ( v10 )
    v11 = Windows::UI::Composition::EffectNode::EffectNode(v10, &v39, v9, v37);
  else
    v11 = 0;
  v36 = v11;
  Windows::UI::Composition::Traverser::VisitEffectInputs(
    this,
    v34,
    (struct Windows::UI::Composition::EffectSubgraph *)a3,
    v11);
  Windows::UI::Composition::Traverser::VisitEffectProperties(v12, v34, v11);
  v13 = *(_QWORD *)this;
  v14 = (_QWORD *)(*(_QWORD *)this + 48LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 56LL) - *v14 == 200 )
    Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 80LL))(*(_QWORD *)v11)
    && (unsigned __int64)((__int64)(*(_QWORD *)(v13 + 104) - *(_QWORD *)(v13 + 96)) >> 4) > 3 )
  {
    std::wstring::wstring(v40, L"No more than three graph source parameters with white noise effect are supported.");
    Windows::UI::Composition::OriginateException(v30, v40);
  }
  v15 = (Windows::UI::Composition::EffectNode **)v14[1];
  if ( v15 == (Windows::UI::Composition::EffectNode **)v14[2] )
  {
    std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectNode>>(
      v14,
      v15,
      &v36);
  }
  else
  {
    v36 = 0;
    *v15 = v11;
    v14[1] += 8LL;
  }
  v16 = ((__int64)(v14[1] - *v14) >> 3) - 1;
  v38 = v16;
  v17 = a3[1];
  if ( v17 == a3[2] )
  {
    std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a3, v17, &v38);
  }
  else
  {
    *v17 = v16;
    ++a3[1];
  }
  std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(&v36);
  (*(void (__fastcall **)(_QWORD, Windows::UI::Composition::EffectNode *))(**(_QWORD **)v11 + 152LL))(
    *(_QWORD *)v11,
    v11);
  v18 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  v19 = *v18 - *(_QWORD *)&CLSID_D2D1GaussianBlur.Data1;
  if ( *v18 == *(_QWORD *)&CLSID_D2D1GaussianBlur.Data1 )
    v19 = v18[1] - *(_QWORD *)CLSID_D2D1GaussianBlur.Data4;
  if ( !v19 )
    *((_BYTE *)a3 + 48) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v11 + 48LL))(*(_QWORD *)v11, 0) )
  {
    v31 = **((_QWORD **)v11 + 1);
    if ( (_DWORD)v31 == 2 )
      *(_DWORD *)(std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::at(
                    *(_QWORD *)this + 96LL,
                    HIDWORD(v31))
                + 8) = v16;
  }
  string = 0;
  v20 = (*(__int64 (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect *, HSTRING *))(*(_QWORD *)a2 + 48LL))(
          a2,
          &string);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v20,
      (int)v34);
  v21 = string;
  if ( string )
  {
    if ( !Windows::UI::Composition::Traverser::IsValidNameFormat(string) )
    {
      std::wstring::wstring(v40, L"Malformed effect name.");
      Windows::UI::Composition::OriginateException(v32, v40);
    }
    if ( Windows::UI::Composition::Traverser::FindNamedEffect(this, string) )
    {
      std::wstring::wstring(v40, L"Duplicate effect name.");
      Windows::UI::Composition::OriginateException(v33, v40);
    }
    std::vector<Windows::UI::Composition::Traverser::NamedEffect>::_Emplace_one_at_back<>((char *)this + 72);
    v24 = *((_QWORD *)this + 10);
    v25 = (HSTRING *)(v24 - 16);
    if ( (HSTRING *)(v24 - 16) != &string )
    {
      v26 = string;
      v27 = *v25;
      if ( *v25 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
        WindowsDeleteString(v27);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
      }
      *v25 = v26;
      string = 0;
    }
    v28 = v34;
    if ( *(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop **)(v24 - 24) != v34 )
    {
      if ( v34 )
        (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *))(*(_QWORD *)v34 + 8LL))(v34);
      v29 = *(_QWORD *)(v24 - 24);
      *(_QWORD *)(v24 - 24) = v28;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    *(_DWORD *)(v24 - 8) = v16;
    v21 = string;
  }
  if ( v21 )
    WindowsDeleteString(v21);
  v22 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return v16;
}

```

## disassembly

```asm
0x180005ce0  push    rbp
0x180005ce2  push    rbx
0x180005ce3  push    rsi
0x180005ce4  push    rdi
0x180005ce5  push    r12
0x180005ce7  push    r14
0x180005ce9  push    r15
0x180005ceb  mov     rbp, rsp
0x180005cee  sub     rsp, 80h
0x180005cf5  mov     rax, cs:__security_cookie
0x180005cfc  xor     rax, rsp
0x180005cff  mov     [rbp+var_10], rax
0x180005d03  mov     r14, r8
0x180005d06  mov     r12, rdx
0x180005d09  mov     r15, rcx
0x180005d0c  mov     [rbp+var_60], 0
0x180005d14  mov     rax, [rdx]
0x180005d17  lea     r8, [rbp+var_60]
0x180005d1b  lea     rdx, _GUID_2fc57384_a068_44d7_a331_30982fcf7177
0x180005d22  mov     rcx, r12
0x180005d25  mov     rax, [rax]
0x180005d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d2d  mov     rcx, [rbp+38h]; this
0x180005d31  test    eax, eax
0x180005d33  jns     short loc_180005D4A
0x180005d35  mov     r9d, eax; char *
0x180005d38  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005d3f  mov     edx, 19Dh; void *
0x180005d44  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005d4a  xorps   xmm0, xmm0
0x180005d4d  movups  xmmword ptr [rbp+var_40.Data1], xmm0
0x180005d51  mov     rcx, [rbp+var_60]
0x180005d55  mov     rax, [rcx]
0x180005d58  lea     rdx, [rbp+var_40]
0x180005d5c  mov     rax, [rax+18h]
0x180005d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d65  mov     rcx, [rbp+38h]; this
0x180005d69  test    eax, eax
0x180005d6b  jns     short loc_180005D82
0x180005d6d  mov     r9d, eax; char *
0x180005d70  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005d77  mov     edx, 1A0h; void *
0x180005d7c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005d82  mov     [rbp+var_48], 0
0x180005d89  mov     rcx, [rbp+var_60]
0x180005d8d  mov     rax, [rcx]
0x180005d90  lea     rdx, [rbp+var_48]
0x180005d94  mov     rax, [rax+40h]
0x180005d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9d  mov     rcx, [rbp+38h]; this
0x180005da1  test    eax, eax
0x180005da3  jns     short loc_180005DBA
0x180005da5  mov     r9d, eax; char *
0x180005da8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005daf  mov     edx, 1A3h; void *
0x180005db4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005dba  mov     rcx, [r15]
0x180005dbd  add     rcx, 10h
0x180005dc1  mov     rax, [rcx]
0x180005dc4  mov     rax, [rax+20h]
0x180005dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dcd  mov     ebx, eax
0x180005dcf  mov     ecx, 28h ; '('; dwBytes
0x180005dd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005dd9  mov     [rbp+var_50], rax
0x180005ddd  test    rax, rax
0x180005de0  jz      loc_180006046
0x180005de6  mov     r9d, [rbp+var_48]; unsigned int
0x180005dea  mov     r8d, ebx; unsigned int
0x180005ded  lea     rdx, [rbp+var_40]; struct _GUID *
0x180005df1  mov     rcx, rax; this
0x180005df4  call    ??0EffectNode@Composition@UI@Windows@@QEAA@AEBU_GUID@@II@Z; Windows::UI::Composition::EffectNode::EffectNode(_GUID const &,uint,uint)
0x180005df9  mov     rsi, rax
0x180005dfc  mov     [rbp+var_50], rsi
0x180005e00  mov     r9, rsi; struct Windows::UI::Composition::EffectNode *
0x180005e03  mov     r8, r14; struct Windows::UI::Composition::EffectSubgraph *
0x180005e06  mov     rdx, [rbp+var_60]; struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *
0x180005e0a  mov     rcx, r15; this
0x180005e0d  call    ?VisitEffectInputs@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffectD2D1Interop@Effects@Graphics@4@PEAUEffectSubgraph@234@PEAVEffectNode@234@@Z; Windows::UI::Composition::Traverser::VisitEffectInputs(Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *,Windows::UI::Composition::EffectSubgraph *,Windows::UI::Composition::EffectNode *)
0x180005e12  mov     r8, rsi; struct Windows::UI::Composition::EffectNode *
0x180005e15  mov     rdx, [rbp+var_60]; struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *
0x180005e19  call    ?VisitEffectProperties@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffectD2D1Interop@Effects@Graphics@4@PEAVEffectNode@234@@Z; Windows::UI::Composition::Traverser::VisitEffectProperties(Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *,Windows::UI::Composition::EffectNode *)
0x180005e1e  mov     rdi, [r15]
0x180005e21  lea     rbx, [rdi+30h]
0x180005e25  mov     rax, [rbx+8]
0x180005e29  sub     rax, [rbx]
0x180005e2c  cmp     rax, 0C8h
0x180005e32  jz      loc_18000604D
0x180005e38  mov     rcx, [rsi]
0x180005e3b  mov     rax, [rcx]
0x180005e3e  mov     rax, [rax+50h]
0x180005e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e47  test    al, al
0x180005e49  jnz     loc_180006053
0x180005e4f  mov     rdx, [rbx+8]
0x180005e53  cmp     rdx, [rbx+10h]
0x180005e57  jnz     loc_180006025
0x180005e5d  lea     r8, [rbp+var_50]
0x180005e61  mov     rcx, rbx
0x180005e64  call    ??$_Emplace_reallocate@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectNode>>(std::unique_ptr<Windows::UI::Composition::EffectNode> * const,std::unique_ptr<Windows::UI::Composition::EffectNode> &&)
0x180005e69  mov     rdi, [rbx+8]
0x180005e6d  sub     rdi, [rbx]
0x180005e70  sar     rdi, 3
0x180005e74  dec     edi
0x180005e76  mov     [rbp+var_44], edi
0x180005e79  mov     rdx, [r14+8]
0x180005e7d  cmp     rdx, [r14+10h]
0x180005e81  jnz     loc_18000603A
0x180005e87  lea     r8, [rbp+var_44]
0x180005e8b  mov     rcx, r14
0x180005e8e  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x180005e93  nop
0x180005e94  lea     rcx, [rbp+var_50]
0x180005e98  call    ??1?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(void)
0x180005e9d  mov     rcx, [rsi]
0x180005ea0  mov     rax, [rcx]
0x180005ea3  mov     rdx, rsi
0x180005ea6  mov     rax, [rax+98h]
0x180005ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb2  mov     rcx, [rsi]
0x180005eb5  mov     rax, [rcx]
0x180005eb8  mov     rax, [rax+8]
0x180005ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec1  mov     rcx, [rax]
0x180005ec4  sub     rcx, qword ptr cs:CLSID_D2D1GaussianBlur.Data1
0x180005ecb  jnz     short loc_180005ED8
0x180005ecd  mov     rcx, [rax+8]
0x180005ed1  sub     rcx, qword ptr cs:CLSID_D2D1GaussianBlur.Data4
0x180005ed8  test    rcx, rcx
0x180005edb  jnz     short loc_180005EE2
0x180005edd  mov     byte ptr [r14+30h], 1
0x180005ee2  mov     rcx, [rsi]
0x180005ee5  mov     rax, [rcx]
0x180005ee8  xor     edx, edx
0x180005eea  mov     rax, [rax+30h]
0x180005eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef3  test    al, al
0x180005ef5  jnz     loc_180006084
0x180005efb  mov     [rbp+string], 0
0x180005f03  mov     rax, [r12]
0x180005f07  lea     rdx, [rbp+string]
0x180005f0b  mov     rcx, r12
0x180005f0e  mov     rax, [rax+30h]
0x180005f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f17  mov     rcx, [rbp+38h]; this
0x180005f1b  test    eax, eax
0x180005f1d  jns     short loc_180005F34
0x180005f1f  mov     r9d, eax; char *
0x180005f22  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005f29  mov     edx, 1D5h; void *
0x180005f2e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005f34  mov     rcx, [rbp+string]; HSTRING
0x180005f38  test    rcx, rcx
0x180005f3b  jnz     short loc_180005F89
0x180005f3d  test    rcx, rcx
0x180005f40  jnz     short loc_180005F80
0x180005f42  mov     rcx, [rbp+var_60]
0x180005f46  test    rcx, rcx
0x180005f49  jz      short loc_180005F60
0x180005f4b  mov     [rbp+var_60], 0
0x180005f53  mov     rdx, [rcx]
0x180005f56  mov     rax, [rdx+10h]
0x180005f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5f  nop
0x180005f60  mov     eax, edi
0x180005f62  mov     rcx, [rbp+var_10]
0x180005f66  xor     rcx, rsp; StackCookie
0x180005f69  call    __security_check_cookie
0x180005f6e  add     rsp, 80h
0x180005f75  pop     r15
0x180005f77  pop     r14
0x180005f79  pop     r12
0x180005f7b  pop     rdi
0x180005f7c  pop     rsi
0x180005f7d  pop     rbx
0x180005f7e  pop     rbp
0x180005f7f  retn
0x180005f80  call    cs:__imp_WindowsDeleteString
0x180005f86  nop
0x180005f87  jmp     short loc_180005F42
0x180005f89  call    ?IsValidNameFormat@Traverser@Composition@UI@Windows@@CA_NPEAUHSTRING__@@@Z; Windows::UI::Composition::Traverser::IsValidNameFormat(HSTRING__ *)
0x180005f8e  test    al, al
0x180005f90  jz      loc_1800060AC
0x180005f96  mov     rdx, [rbp+string]; HSTRING
0x180005f9a  mov     rcx, r15; this
0x180005f9d  call    ?FindNamedEffect@Traverser@Composition@UI@Windows@@AEAAPEBUNamedEffect@1234@PEAUHSTRING__@@@Z; Windows::UI::Composition::Traverser::FindNamedEffect(HSTRING__ *)
0x180005fa2  test    rax, rax
0x180005fa5  jnz     loc_1800060C7
0x180005fab  lea     rcx, [r15+48h]
0x180005faf  call    ??$_Emplace_one_at_back@$$V@?$vector@UNamedEffect@Traverser@Composition@UI@Windows@@V?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@std@@@std@@AEAAAEAUNamedEffect@Traverser@Composition@UI@Windows@@XZ; std::vector<Windows::UI::Composition::Traverser::NamedEffect>::_Emplace_one_at_back<>(void)
0x180005fb4  mov     rsi, [r15+50h]
0x180005fb8  lea     rbx, [rsi-10h]
0x180005fbc  lea     rax, [rbp+string]
0x180005fc0  cmp     rbx, rax
0x180005fc3  jz      short loc_180005FE0
0x180005fc5  mov     r15, [rbp+string]
0x180005fc9  mov     r14, [rbx]
0x180005fcc  test    r14, r14
0x180005fcf  jnz     loc_1800060E2
0x180005fd5  mov     [rbx], r15
0x180005fd8  mov     [rbp+string], 0
0x180005fe0  mov     rbx, [rbp+var_60]
0x180005fe4  cmp     [rsi-18h], rbx
0x180005fe8  jz      short loc_180006019
0x180005fea  test    rbx, rbx
0x180005fed  jz      short loc_180005FFF
0x180005fef  mov     rax, [rbx]
0x180005ff2  mov     rcx, rbx
0x180005ff5  mov     rax, [rax+8]
0x180005ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffe  nop
0x180005fff  mov     rcx, [rsi-18h]
0x180006003  mov     [rsi-18h], rbx
0x180006007  test    rcx, rcx
0x18000600a  jz      short loc_180006019
0x18000600c  mov     rax, [rcx]
0x18000600f  mov     rax, [rax+10h]
0x180006013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006018  nop
0x180006019  mov     [rsi-8], edi
0x18000601c  mov     rcx, [rbp+string]
0x180006020  jmp     loc_180005F3D
0x180006025  mov     [rbp+var_50], 0
0x18000602d  mov     [rdx], rsi
0x180006030  add     qword ptr [rbx+8], 8
0x180006035  jmp     loc_180005E69
0x18000603a  mov     [rdx], edi
0x18000603c  add     qword ptr [r14+8], 4
0x180006041  jmp     loc_180005E94
0x180006046  xor     esi, esi
0x180006048  jmp     loc_180005DFC
0x18000604d  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
0x180006053  mov     rax, [rdi+68h]
0x180006057  sub     rax, [rdi+60h]
0x18000605b  sar     rax, 4
0x18000605f  cmp     rax, 3
0x180006063  jbe     loc_180005E4F
0x180006069  lea     rdx, aNoMoreThanThre; "No more than three graph source paramet"...
0x180006070  lea     rcx, [rbp+var_30]
0x180006074  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006079  nop
0x18000607a  lea     rdx, [rbp+var_30]
0x18000607e  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180006084  mov     rdx, [rsi+8]
0x180006088  mov     rdx, [rdx]
0x18000608b  cmp     edx, 2
0x18000608e  jnz     loc_180005EFB
0x180006094  shr     rdx, 20h
0x180006098  mov     rcx, [r15]
0x18000609b  add     rcx, 60h ; '`'
0x18000609f  call    ?at@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEBAAEBUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::at(unsigned __int64)
0x1800060a4  mov     [rax+8], edi
0x1800060a7  jmp     loc_180005EFB
0x1800060ac  lea     rdx, aMalformedEffec; "Malformed effect name."
0x1800060b3  lea     rcx, [rbp+var_30]
0x1800060b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800060bc  nop
0x1800060bd  lea     rdx, [rbp+var_30]
0x1800060c1  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x1800060c7  lea     rdx, aDuplicateEffec; "Duplicate effect name."
0x1800060ce  lea     rcx, [rbp+var_30]
0x1800060d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800060d7  nop
0x1800060d8  lea     rdx, [rbp+var_30]
0x1800060dc  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x1800060e2  lea     rcx, [rbp+var_50]; this
0x1800060e6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800060eb  mov     rcx, r14; string
0x1800060ee  call    cs:__imp_WindowsDeleteString
0x1800060f4  lea     rcx, [rbp+var_50]; this
0x1800060f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800060fd  jmp     loc_180005FD5
```
