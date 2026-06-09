# Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs(Windows::Graphics::Effects::IGraphicsEffect *,bool,bool)

- ea: `0x180004550`
- end: `0x180004d53`
- name: `?EnumerateEffectSubgraphs@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffect@Effects@Graphics@4@_N1@Z`
- size: `2051`
- prototype: `void __fastcall(Windows::UI::Composition::Traverser *this, struct Windows::Graphics::Effects::IGraphicsEffect *, char, char)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180004550`
- `0x18000b520`

## callees

- `0x180003ef0`
- `0x180003f94`
- `0x180004378`
- `0x180004550`
- `0x180004d5c`
- `0x180004db8`
- `0x180004df4`
- `0x180006138`
- `0x18000b900`
- `0x180019d18`
- `0x18001de54`
- `0x18001eaa0`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004cf1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004cf1`

## string_xrefs

- `0x1800045bc`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800045f4`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180004820`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800048f1`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180004bf1`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs(
        Windows::UI::Composition::Traverser *this,
        struct Windows::Graphics::Effects::IGraphicsEffect *a2,
        char a3,
        char a4)
{
  int v7; // eax
  int v8; // eax
  __int64 i; // rbx
  void ***v10; // rdi
  _QWORD *v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // r15
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rsi
  __int64 v21; // rdx
  float v22; // xmm0_4
  __int64 v23; // rcx
  float v24; // xmm1_4
  _QWORD *v25; // r8
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  _QWORD *v30; // rdx
  int v31; // eax
  bool v32; // r14
  unsigned int j; // esi
  _QWORD *v34; // rdx
  __int64 v35; // rcx
  int v36; // eax
  struct Windows::Graphics::Effects::IGraphicsEffect *v37; // rcx
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v38; // rcx
  bool v39; // r9
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v40; // r15
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v41; // rbx
  __int64 v42; // rcx
  struct Windows::UI::Composition::CSingleInputCompositeEffect **v43; // rdx
  struct Windows::Graphics::Effects::IGraphicsEffect *v44; // rbx
  struct Windows::Graphics::Effects::IGraphicsEffect *v45; // rcx
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v46; // rcx
  __int64 v47; // rcx
  struct Windows::UI::Composition::CSingleInputCompositeEffect **v48; // rbx
  struct Windows::UI::Composition::CSingleInputCompositeEffect **v49; // r15
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v50; // rbx
  __int64 v51; // rax
  __int64 v52; // r9
  _QWORD *v53; // rdx
  int v54; // eax
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rcx
  int v59; // [rsp+20h] [rbp-59h]
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v60; // [rsp+28h] [rbp-51h] BYREF
  char v61; // [rsp+30h] [rbp-49h]
  struct Windows::Graphics::Effects::IGraphicsEffect *v62; // [rsp+38h] [rbp-41h] BYREF
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v63; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::Graphics::Effects::IGraphicsEffect *v64; // [rsp+48h] [rbp-31h] BYREF
  __int64 v65; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v66; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::UI::Composition::CSingleInputCompositeEffect *v67; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v68; // [rsp+68h] [rbp-11h]
  __int128 v69; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v61 = a4;
  LOBYTE(v59) = a3;
  v64 = a2;
  v65 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffect *, GUID *, __int64 *))a2)(
         a2,
         &GUID_2fc57384_a068_44d7_a331_30982fcf7177,
         &v65);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v7,
      v59);
  v69 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v65 + 24LL))(v65, &v69);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v8,
      v59);
  for ( i = 0; (unsigned int)i < 0x1F; i = (unsigned int)(i + 1) )
  {
    v10 = off_18003E110[i];
    v11 = (_QWORD *)((__int64 (__fastcall *)(void ***))(*v10)[1])(v10);
    v12 = v69 - *v11;
    if ( (_QWORD)v69 == *v11 )
      v12 = *((_QWORD *)&v69 + 1) - v11[1];
    if ( !v12 )
      goto LABEL_12;
  }
  v10 = 0;
LABEL_12:
  if ( !v10 )
  {
    std::wstring::wstring(&v67, L"Unsupported effect type.");
    Windows::UI::Composition::OriginateException(v57, &v67);
  }
  if ( a4 && ((unsigned __int8 (__fastcall *)(void ***))(*v10)[9])(v10) )
  {
    std::wstring::wstring(&v67, L"SceneLightingEffect cannot be a source to GaussianBlurEffect.");
    Windows::UI::Composition::OriginateException(v47, &v67);
  }
  _mm_lfence();
  v13 = 0x100000001B3LL
      * (HIBYTE(v64)
       ^ (0x100000001B3LL
        * (BYTE6(v64)
         ^ (0x100000001B3LL
          * (BYTE5(v64)
           ^ (0x100000001B3LL
            * (BYTE4(v64)
             ^ (0x100000001B3LL
              * (BYTE3(v64)
               ^ (0x100000001B3LL
                * (BYTE2(v64)
                 ^ (0x100000001B3LL * (BYTE1(v64) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL)))))))))))))));
  v14 = *((_QWORD *)this + 4);
  v15 = *(_QWORD *)(v14 + 16 * (v13 & *((_QWORD *)this + 7)) + 8);
  v16 = (_QWORD *)*((_QWORD *)this + 2);
  if ( (_QWORD *)v15 == v16 )
  {
LABEL_15:
    v15 = 0;
  }
  else
  {
    while ( a2 != *(struct Windows::Graphics::Effects::IGraphicsEffect **)(v15 + 16) )
    {
      if ( v15 == *(_QWORD *)(v14 + 16 * (v13 & *((_QWORD *)this + 7))) )
        goto LABEL_15;
      v15 = *(_QWORD *)(v15 + 8);
    }
  }
  if ( v15 && (_QWORD *)v15 != v16 )
  {
    std::wstring::wstring(&v67, L"Non-tree shaped effect graph.");
    Windows::UI::Composition::OriginateException(v17, &v67);
  }
  _mm_lfence();
  v18 = *((_QWORD *)this + 4);
  v19 = *(_QWORD *)(v18 + 16 * (v13 & *((_QWORD *)this + 7)) + 8);
  if ( (_QWORD *)v19 != v16 )
  {
    while ( a2 != *(struct Windows::Graphics::Effects::IGraphicsEffect **)(v19 + 16) )
    {
      if ( v19 == *(_QWORD *)(v18 + 16 * (v13 & *((_QWORD *)this + 7))) )
      {
        v16 = (_QWORD *)v19;
        goto LABEL_20;
      }
      v19 = *(_QWORD *)(v19 + 8);
    }
    goto LABEL_30;
  }
LABEL_20:
  if ( *((_QWORD *)this + 3) == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("unordered_map/set too long");
  v67 = (Windows::UI::Composition::Traverser *)((char *)this + 16);
  v68 = 0;
  v20 = (_QWORD *)std::allocator<std::_List_node<Windows::Graphics::Effects::IGraphicsEffect *,void *>>::allocate();
  v68 = v20;
  v20[2] = a2;
  v21 = *((_QWORD *)this + 3) + 1LL;
  if ( v21 < 0 )
    v22 = (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1))
        + (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1));
  else
    v22 = (float)(int)v21;
  v23 = *((_QWORD *)this + 8);
  if ( v23 < 0 )
  {
    v56 = *((_QWORD *)this + 8) & 1LL | ((unsigned __int64)v23 >> 1);
    v24 = (float)(int)v56 + (float)(int)v56;
  }
  else
  {
    v24 = (float)(int)v23;
  }
  if ( (float)(v22 / v24) > *((float *)this + 2) )
  {
    v51 = std::_Hash<std::_Uset_traits<Windows::Graphics::Effects::IGraphicsEffect *,std::_Uhash_compare<Windows::Graphics::Effects::IGraphicsEffect *,std::hash<Windows::Graphics::Effects::IGraphicsEffect *>,std::equal_to<Windows::Graphics::Effects::IGraphicsEffect *>>,std::allocator<Windows::Graphics::Effects::IGraphicsEffect *>,0>>::_Desired_grow_bucket_count((char *)this + 8);
    std::_Hash<std::_Uset_traits<Windows::Graphics::Effects::IGraphicsEffect *,std::_Uhash_compare<Windows::Graphics::Effects::IGraphicsEffect *,std::hash<Windows::Graphics::Effects::IGraphicsEffect *>,std::equal_to<Windows::Graphics::Effects::IGraphicsEffect *>>,std::allocator<Windows::Graphics::Effects::IGraphicsEffect *>,0>>::_Forced_rehash(
      (char *)this + 8,
      v51);
    v26 = (_QWORD *)((char *)this + 56);
    v52 = *((_QWORD *)this + 4);
    v53 = *(_QWORD **)(v52 + 16 * (*((_QWORD *)this + 7) & v13) + 8);
    v25 = (_QWORD *)((char *)this + 16);
    v16 = (_QWORD *)*((_QWORD *)this + 2);
    if ( v53 != v16 )
    {
      while ( v20[2] != v53[2] )
      {
        if ( v53 == *(_QWORD **)(v52 + 16 * (*((_QWORD *)this + 7) & v13)) )
        {
          v16 = v53;
          goto LABEL_27;
        }
        v53 = (_QWORD *)v53[1];
      }
      v16 = (_QWORD *)*v53;
    }
  }
  else
  {
    v25 = (_QWORD *)((char *)this + 16);
    v26 = (_QWORD *)((char *)this + 56);
  }
LABEL_27:
  v27 = (_QWORD *)v16[1];
  ++*((_QWORD *)this + 3);
  *v20 = v16;
  v20[1] = v27;
  *v27 = v20;
  v16[1] = v20;
  v28 = 2 * (*v26 & v13);
  v29 = *((_QWORD *)this + 4);
  v30 = *(_QWORD **)(v29 + 8 * v28);
  if ( v30 == (_QWORD *)*v25 )
  {
    *(_QWORD *)(v29 + 8 * v28) = v20;
LABEL_29:
    *(_QWORD *)(v29 + 8 * v28 + 8) = v20;
    goto LABEL_30;
  }
  if ( v30 == v16 )
  {
    *(_QWORD *)(v29 + 8 * v28) = v20;
  }
  else if ( *(_QWORD **)(v29 + 8 * v28 + 8) == v27 )
  {
    goto LABEL_29;
  }
LABEL_30:
  if ( ((unsigned __int8 (__fastcall *)(void ***))(*v10)[5])(v10)
    || ((unsigned __int8 (__fastcall *)(void ***))(*v10)[11])(v10) )
  {
    LOBYTE(v59) = 0;
  }
  v66 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 64LL))(v65, &v66);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v31,
      v59);
  v32 = !((unsigned int (__fastcall *)(void ***))(*v10)[2])(v10)
     && !((unsigned __int8 (__fastcall *)(void ***))(*v10)[5])(v10);
  for ( j = 0; j < v66; ++j )
  {
    v63 = 0;
    v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::UI::Composition::CSingleInputCompositeEffect **))(*(_QWORD *)v65 + 56LL))(
            v65,
            j,
            &v63);
    if ( v36 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v36,
        v59);
    if ( v63 )
    {
      v62 = 0;
      if ( (**(int (__fastcall ***)(struct Windows::UI::Composition::CSingleInputCompositeEffect *, GUID *, struct Windows::Graphics::Effects::IGraphicsEffect **))v63)(
             v63,
             &GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3,
             &v62) >= 0
        && v62 )
      {
        if ( !v61 && !((unsigned __int8 (__fastcall *)(void ***))(*v10)[5])(v10) )
        {
          v39 = 0;
          goto LABEL_60;
        }
LABEL_83:
        v39 = 1;
LABEL_60:
        Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs(this, v62, v32, v39);
      }
      else if ( ((unsigned __int8 (__fastcall *)(void ***))(*v10)[5])(v10) )
      {
        v67 = v63;
        v48 = (struct Windows::UI::Composition::CSingleInputCompositeEffect **)*((_QWORD *)this + 15);
        v49 = (struct Windows::UI::Composition::CSingleInputCompositeEffect **)*((_QWORD *)this + 16);
        while ( 1 )
        {
          if ( v48 == v49 )
          {
            v50 = 0;
            goto LABEL_90;
          }
          v60 = 0;
          v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::UI::Composition::CSingleInputCompositeEffect **))(*((_QWORD *)*v48 + 2) + 56LL))(
                  (__int64)*v48 + 16,
                  0,
                  &v60);
          if ( v54 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x181,
              (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
              (const char *)(unsigned int)v54,
              v59);
          v55 = v60;
          if ( v60 == v67 )
            break;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v55 + 16LL))(v55);
          }
          ++v48;
        }
        v50 = *v48;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v55 + 16LL))(v55);
        }
LABEL_90:
        if ( v62 != v50 )
        {
          v60 = v50;
          Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffect>::InternalAddRef(&v60);
          v60 = v62;
          v62 = v50;
          Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v60);
        }
        if ( !v62 )
        {
          v60 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v60);
          Windows::UI::Composition::CSingleInputCompositeEffect::Create(&v60);
          v40 = v63;
          v41 = v60;
          if ( *((struct Windows::UI::Composition::CSingleInputCompositeEffect **)v60 + 3) != v63 )
          {
            if ( v63 )
              (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v63 + 8LL))(v63);
            v42 = *((_QWORD *)v41 + 3);
            *((_QWORD *)v41 + 3) = v40;
            if ( v42 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            v41 = v60;
          }
          v43 = (struct Windows::UI::Composition::CSingleInputCompositeEffect **)*((_QWORD *)this + 16);
          if ( v43 == *((struct Windows::UI::Composition::CSingleInputCompositeEffect ***)this + 17) )
          {
            std::vector<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> &>(
              (char *)this + 120,
              v43,
              &v60);
          }
          else
          {
            *v43 = v41;
            Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffect>::InternalAddRef(v43);
            *((_QWORD *)this + 16) += 8LL;
          }
          v44 = v60;
          if ( v60 )
            (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v60 + 8LL))(v60);
          v45 = v62;
          v62 = v44;
          if ( v45 )
            (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect *))(*(_QWORD *)v45 + 16LL))(v45);
          v46 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v46 + 16LL))(v46);
          }
        }
        goto LABEL_83;
      }
      v37 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect *))(*(_QWORD *)v37 + 16LL))(v37);
      }
      goto LABEL_53;
    }
    if ( !((unsigned __int8 (__fastcall *)(void ***, _QWORD))(*v10)[4])(v10, 0) )
    {
      std::wstring::wstring(&v67, L"Null effect input.");
      Windows::UI::Composition::OriginateException(v58, &v67);
    }
LABEL_53:
    v38 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Composition::CSingleInputCompositeEffect *))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  if ( !(_BYTE)v59 )
  {
    v34 = (_QWORD *)*((_QWORD *)this + 13);
    if ( v34 == *((_QWORD **)this + 14) )
    {
      std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(
        (char *)this + 96,
        v34,
        &v64);
    }
    else
    {
      *v34 = a2;
      *((_QWORD *)this + 13) += 8LL;
    }
  }
  v35 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
}

```

## disassembly

```asm
0x180004550  mov     [rsp-8+arg_10], rbx
0x180004555  push    rbp
0x180004556  push    rsi
0x180004557  push    rdi
0x180004558  push    r12
0x18000455a  push    r13
0x18000455c  push    r14
0x18000455e  push    r15
0x180004560  lea     rbp, [rsp-27h]
0x180004565  sub     rsp, 0A0h
0x18000456c  mov     rax, cs:__security_cookie
0x180004573  xor     rax, rsp
0x180004576  mov     [rbp+57h+var_40], rax
0x18000457a  movzx   esi, r9b
0x18000457e  mov     [rbp+57h+var_A0], r9b
0x180004582  mov     [rbp+57h+var_B0], r8b
0x180004586  mov     r12, rdx
0x180004589  mov     r13, rcx
0x18000458c  mov     [rbp+57h+var_88], rdx
0x180004590  mov     [rbp+57h+var_80], 0
0x180004598  mov     rax, [rdx]
0x18000459b  lea     r8, [rbp+57h+var_80]
0x18000459f  lea     rdx, _GUID_2fc57384_a068_44d7_a331_30982fcf7177
0x1800045a6  mov     rcx, r12
0x1800045a9  mov     rax, [rax]
0x1800045ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b1  mov     rcx, [rbp+5Fh]; this
0x1800045b5  test    eax, eax
0x1800045b7  jns     short loc_1800045CE
0x1800045b9  mov     r9d, eax; char *
0x1800045bc  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800045c3  mov     edx, 0D8h; void *
0x1800045c8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800045ce  xorps   xmm0, xmm0
0x1800045d1  movups  [rbp+57h+var_50], xmm0
0x1800045d5  mov     rcx, [rbp+57h+var_80]
0x1800045d9  mov     rax, [rcx]
0x1800045dc  lea     rdx, [rbp+57h+var_50]
0x1800045e0  mov     rax, [rax+18h]
0x1800045e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e9  mov     rcx, [rbp+5Fh]; this
0x1800045ed  test    eax, eax
0x1800045ef  jns     short loc_180004606
0x1800045f1  mov     r9d, eax; char *
0x1800045f4  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800045fb  mov     edx, 0DBh; void *
0x180004600  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180004606  xor     ebx, ebx
0x180004608  lea     r14, off_18003E110
0x18000460f  nop
0x180004610  cmp     ebx, 1Fh
0x180004613  jnb     short loc_180004642
0x180004615  mov     rdi, [r14+rbx*8]
0x180004619  mov     rax, [rdi]
0x18000461c  mov     rcx, rdi
0x18000461f  mov     rax, [rax+8]
0x180004623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004628  mov     rcx, qword ptr [rbp+57h+var_50]
0x18000462c  sub     rcx, [rax]
0x18000462f  jnz     short loc_180004639
0x180004631  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x180004635  sub     rcx, [rax+8]
0x180004639  test    rcx, rcx
0x18000463c  jz      short loc_180004644
0x18000463e  inc     ebx
0x180004640  jmp     short loc_180004610
0x180004642  xor     edi, edi
0x180004644  test    rdi, rdi
0x180004647  jz      loc_180004CCF
0x18000464d  test    sil, sil
0x180004650  jnz     loc_180004AEC
0x180004656  lfence
0x180004659  movzx   ebx, r12b
0x18000465d  mov     rax, 0CBF29CE484222325h
0x180004667  xor     rbx, rax
0x18000466a  mov     rcx, 100000001B3h
0x180004674  imul    rbx, rcx
0x180004678  movzx   eax, byte ptr [rbp+57h+var_88+1]
0x18000467c  xor     rbx, rax
0x18000467f  imul    rbx, rcx
0x180004683  movzx   eax, byte ptr [rbp+57h+var_88+2]
0x180004687  xor     rbx, rax
0x18000468a  imul    rbx, rcx
0x18000468e  movzx   eax, byte ptr [rbp+57h+var_88+3]
0x180004692  xor     rbx, rax
0x180004695  imul    rbx, rcx
0x180004699  movzx   eax, byte ptr [rbp+57h+var_88+4]
0x18000469d  xor     rbx, rax
0x1800046a0  imul    rbx, rcx
0x1800046a4  movzx   eax, byte ptr [rbp+57h+var_88+5]
0x1800046a8  xor     rbx, rax
0x1800046ab  imul    rbx, rcx
0x1800046af  movzx   eax, byte ptr [rbp+57h+var_88+6]
0x1800046b3  xor     rbx, rax
0x1800046b6  imul    rbx, rcx
0x1800046ba  movzx   eax, byte ptr [rbp+57h+var_88+7]
0x1800046be  xor     rbx, rax
0x1800046c1  imul    rbx, rcx
0x1800046c5  mov     rdx, [r13+38h]
0x1800046c9  and     rdx, rbx
0x1800046cc  add     rdx, rdx
0x1800046cf  mov     rcx, [r13+20h]
0x1800046d3  mov     rax, [rcx+rdx*8+8]
0x1800046d8  lea     r8, [r13+10h]
0x1800046dc  mov     r15, [r8]
0x1800046df  cmp     rax, r15
0x1800046e2  jnz     loc_1800049F0
0x1800046e8  xor     eax, eax
0x1800046ea  test    rax, rax
0x1800046ed  jz      short loc_18000470F
0x1800046ef  cmp     rax, r15
0x1800046f2  jz      short loc_18000470F
0x1800046f4  lea     rdx, aNonTreeShapedE; "Non-tree shaped effect graph."
0x1800046fb  lea     rcx, [rbp+57h+var_70]
0x1800046ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004704  nop
0x180004705  lea     rdx, [rbp+57h+var_70]
0x180004709  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000470f  lfence
0x180004712  mov     rcx, [r13+20h]
0x180004716  mov     rax, [rcx+rdx*8+8]
0x18000471b  cmp     rax, r15
0x18000471e  jnz     loc_1800049CC
0x180004724  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000472e  cmp     [r13+18h], rax
0x180004732  jz      loc_180004CEA
0x180004738  mov     [rbp+57h+var_70], r8
0x18000473c  mov     [rbp+57h+var_68], 0
0x180004744  call    ?allocate@?$allocator@U?$_List_node@PEAUIGraphicsEffect@Effects@Graphics@Windows@@PEAX@std@@@std@@QEAAPEAU?$_List_node@PEAUIGraphicsEffect@Effects@Graphics@Windows@@PEAX@2@_K@Z; std::allocator<std::_List_node<Windows::Graphics::Effects::IGraphicsEffect *,void *>>::allocate(unsigned __int64)
0x180004749  mov     rsi, rax
0x18000474c  mov     [rbp+57h+var_68], rax
0x180004750  mov     [rax+10h], r12
0x180004754  mov     rdx, [r13+18h]
0x180004758  add     rdx, 1
0x18000475c  xorps   xmm0, xmm0
0x18000475f  js      loc_180004C98
0x180004765  cvtsi2ss xmm0, rdx
0x18000476a  mov     rcx, [r13+40h]
0x18000476e  xorps   xmm1, xmm1
0x180004771  test    rcx, rcx
0x180004774  js      loc_180004CB5
0x18000477a  cvtsi2ss xmm1, rcx
0x18000477f  divss   xmm0, xmm1
0x180004783  comiss  xmm0, dword ptr [r13+8]
0x180004788  ja      loc_180004B5F
0x18000478e  lea     r8, [r13+10h]
0x180004792  lea     rax, [r13+38h]
0x180004796  mov     rcx, [r15+8]
0x18000479a  inc     qword ptr [r13+18h]
0x18000479e  mov     [rsi], r15
0x1800047a1  mov     [rsi+8], rcx
0x1800047a5  mov     [rcx], rsi
0x1800047a8  mov     [r15+8], rsi
0x1800047ac  and     rbx, [rax]
0x1800047af  add     rbx, rbx
0x1800047b2  mov     rax, [r13+20h]
0x1800047b6  mov     rdx, [rax+rbx*8]
0x1800047ba  cmp     rdx, [r8]
0x1800047bd  jnz     loc_180004A0A
0x1800047c3  mov     [rax+rbx*8], rsi
0x1800047c7  mov     [rax+rbx*8+8], rsi
0x1800047cc  mov     rax, [rdi]
0x1800047cf  mov     rcx, rdi
0x1800047d2  mov     rax, [rax+28h]
0x1800047d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047db  test    al, al
0x1800047dd  jnz     loc_180004D08
0x1800047e3  mov     rax, [rdi]
0x1800047e6  mov     rcx, rdi
0x1800047e9  mov     rax, [rax+58h]
0x1800047ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f2  test    al, al
0x1800047f4  jnz     loc_180004D08
0x1800047fa  xor     r15d, r15d
0x1800047fd  mov     [rbp+57h+var_78], r15d
0x180004801  mov     rcx, [rbp+57h+var_80]
0x180004805  mov     rax, [rcx]
0x180004808  lea     rdx, [rbp+57h+var_78]
0x18000480c  mov     rax, [rax+40h]
0x180004810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004815  mov     rcx, [rbp+5Fh]; this
0x180004819  test    eax, eax
0x18000481b  jns     short loc_180004832
0x18000481d  mov     r9d, eax; char *
0x180004820  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180004827  mov     edx, 100h; void *
0x18000482c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180004832  mov     rax, [rdi]
0x180004835  mov     rcx, rdi
0x180004838  mov     rax, [rax+10h]
0x18000483c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004841  test    eax, eax
0x180004843  jnz     loc_180004BBD
0x180004849  mov     rax, [rdi]
0x18000484c  mov     rcx, rdi
0x18000484f  mov     rax, [rax+28h]
0x180004853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004858  test    al, al
0x18000485a  jnz     loc_180004BBD
0x180004860  mov     r14b, 1
0x180004863  mov     esi, r15d
0x180004866  cmp     esi, [rbp+57h+var_78]
0x180004869  jb      short loc_1800048CC
0x18000486b  cmp     [rbp+57h+var_B0], 0
0x18000486f  jnz     short loc_18000488B
0x180004871  lea     rcx, [r13+60h]
0x180004875  mov     rdx, [rcx+8]
0x180004879  cmp     rdx, [rcx+10h]
0x18000487d  jz      loc_180004903
0x180004883  mov     [rdx], r12
0x180004886  add     qword ptr [rcx+8], 8
0x18000488b  mov     rcx, [rbp+57h+var_80]
0x18000488f  test    rcx, rcx
0x180004892  jz      short loc_1800048A5
0x180004894  mov     [rbp+57h+var_80], r15
0x180004898  mov     rax, [rcx]
0x18000489b  mov     rax, [rax+10h]
0x18000489f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a4  nop
0x1800048a5  mov     rcx, [rbp+57h+var_40]
0x1800048a9  xor     rcx, rsp; StackCookie
0x1800048ac  call    __security_check_cookie
0x1800048b1  mov     rbx, [rsp+0D0h+arg_10]
0x1800048b9  add     rsp, 0A0h
0x1800048c0  pop     r15
0x1800048c2  pop     r14
0x1800048c4  pop     r13
0x1800048c6  pop     r12
0x1800048c8  pop     rdi
0x1800048c9  pop     rsi
0x1800048ca  pop     rbp
0x1800048cb  retn
0x1800048cc  mov     [rbp+57h+var_90], r15
0x1800048d0  mov     rcx, [rbp+57h+var_80]
0x1800048d4  mov     rax, [rcx]
0x1800048d7  lea     r8, [rbp+57h+var_90]
0x1800048db  mov     edx, esi
0x1800048dd  mov     rax, [rax+38h]
0x1800048e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e6  mov     rcx, [rbp+5Fh]; this
0x1800048ea  test    eax, eax
0x1800048ec  jns     short loc_180004911
0x1800048ee  mov     r9d, eax; char *
0x1800048f1  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800048f8  mov     edx, 110h; void *
0x1800048fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180004903  lea     r8, [rbp+57h+var_88]
0x180004907  call    ??$_Emplace_reallocate@UEffectSubgraphInput@Composition@UI@Windows@@@?$vector@UEffectSubgraphInput@Composition@UI@Windows@@V?$allocator@UEffectSubgraphInput@Composition@UI@Windows@@@std@@@std@@AEAAPEAUEffectSubgraphInput@Composition@UI@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(Windows::UI::Composition::EffectSubgraphInput * const,Windows::UI::Composition::EffectSubgraphInput &&)
0x18000490c  jmp     loc_18000488B
0x180004911  mov     rcx, [rbp+57h+var_90]
0x180004915  test    rcx, rcx
0x180004918  jz      loc_180004C3F
0x18000491e  mov     [rbp+57h+var_98], r15
0x180004922  mov     rax, [rcx]
0x180004925  lea     r8, [rbp+57h+var_98]
0x180004929  lea     rdx, _GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3
0x180004930  mov     rax, [rax]
0x180004933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004938  nop
0x180004939  test    eax, eax
0x18000493b  jns     short loc_18000498F
0x18000493d  mov     rax, [rdi]
0x180004940  mov     rcx, rdi
0x180004943  mov     rax, [rax+28h]
0x180004947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494c  test    al, al
0x18000494e  jnz     loc_180004B27
0x180004954  mov     rcx, [rbp+57h+var_98]
0x180004958  test    rcx, rcx
0x18000495b  jz      short loc_18000496E
0x18000495d  mov     [rbp+57h+var_98], r15
0x180004961  mov     rax, [rcx]
0x180004964  mov     rax, [rax+10h]
0x180004968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496d  nop
0x18000496e  mov     rcx, [rbp+57h+var_90]
0x180004972  test    rcx, rcx
0x180004975  jz      short loc_180004988
0x180004977  mov     [rbp+57h+var_90], r15
0x18000497b  mov     rax, [rcx]
0x18000497e  mov     rax, [rax+10h]
0x180004982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004987  nop
0x180004988  inc     esi
0x18000498a  jmp     loc_180004866
0x18000498f  cmp     [rbp+57h+var_98], 0
0x180004994  jz      short loc_18000493D
0x180004996  cmp     [rbp+57h+var_A0], 0
0x18000499a  jnz     loc_180004AE4
0x1800049a0  mov     rax, [rdi]
0x1800049a3  mov     rcx, rdi
0x1800049a6  mov     rax, [rax+28h]
0x1800049aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049af  test    al, al
0x1800049b1  jnz     loc_180004AE4
0x1800049b7  xor     r9d, r9d; bool
0x1800049ba  movzx   r8d, r14b; bool
0x1800049be  mov     rdx, [rbp+57h+var_98]; struct Windows::Graphics::Effects::IGraphicsEffect *
0x1800049c2  mov     rcx, r13; this
0x1800049c5  call    ?EnumerateEffectSubgraphs@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffect@Effects@Graphics@4@_N1@Z; Windows::UI::Composition::Traverser::EnumerateEffectSubgraphs(Windows::Graphics::Effects::IGraphicsEffect *,bool,bool)
  ... truncated ...
```
