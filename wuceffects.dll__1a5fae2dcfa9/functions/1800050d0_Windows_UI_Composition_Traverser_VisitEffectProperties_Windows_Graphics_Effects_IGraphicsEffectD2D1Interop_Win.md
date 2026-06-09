# Windows::UI::Composition::Traverser::VisitEffectProperties(Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *,Windows::UI::Composition::EffectNode *)

- ea: `0x1800050d0`
- end: `0x180005432`
- name: `?VisitEffectProperties@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffectD2D1Interop@Effects@Graphics@4@PEAVEffectNode@234@@Z`
- size: `866`
- prototype: `void __fastcall(Windows::UI::Composition::Traverser *__hidden this, struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, struct Windows::UI::Composition::EffectNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x180004db8`
- `0x1800050d0`
- `0x18001de54`
- `0x18001eaa0`
- `0x180021060`
- `0x180021cd4`
- `0x18002584c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005290`

## string_xrefs

- `0x180005162`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000519e`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800051e8`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180005232`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000532d`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x180005361`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800053ea`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Composition::Traverser::VisitEffectProperties(
        Windows::UI::Composition::Traverser *this,
        struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *a2,
        struct Windows::UI::Composition::EffectNode *a3)
{
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r14
  int v7; // eax
  __int64 v8; // r12
  __int64 v9; // rsi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  int v13; // r15d
  int v14; // eax
  int *v15; // rsi
  int *p_Src; // rdx
  void *v17; // rdi
  unsigned __int8 (__fastcall *v18)(void *); // rax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int Src; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v27; // [rsp+24h] [rbp-5Ch] BYREF
  int v28; // [rsp+28h] [rbp-58h] BYREF
  int v29; // [rsp+2Ch] [rbp-54h] BYREF
  __int64 v30; // [rsp+30h] [rbp-50h] BYREF
  __int64 v31; // [rsp+38h] [rbp-48h] BYREF
  int *v32; // [rsp+40h] [rbp-40h] BYREF
  int *v33; // [rsp+48h] [rbp-38h]
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v34; // [rsp+50h] [rbp-30h]
  _OWORD v35[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v4 = a2;
  v34 = a2;
  v27 = 0;
  v31 = 0;
  (*(void (__fastcall **)(_QWORD, unsigned int *, __int64 *))(**(_QWORD **)a3 + 144LL))(*(_QWORD *)a3, &v27, &v31);
  v5 = 0;
  if ( v27 )
  {
    while ( 1 )
    {
      v6 = v31 + 32LL * v5;
      v30 = 0;
      v7 = (*(__int64 (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, _QWORD, __int64 *))(*(_QWORD *)v4 + 48LL))(
             v4,
             v5,
             &v30);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x285,
          (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
          (const char *)(unsigned int)v7,
          Src);
      v8 = *((_QWORD *)a3 + 3);
      v9 = v30;
      v28 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 48LL))(v30, &v28);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
          (const char *)(unsigned int)v10,
          Src);
      v11 = v28;
      v29 = 1;
      Src = 0;
      v33 = 0;
      if ( v28 == 11 )
        break;
      v13 = 4;
      switch ( v28 )
      {
        case 4:
          v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 88LL))(v9, &Src);
          if ( v23 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x2C3,
              (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
              (const char *)(unsigned int)v23,
              Src);
          goto LABEL_14;
        case 5:
          v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 96LL))(v9, &Src);
          if ( v14 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x2BE,
              (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
              (const char *)(unsigned int)v14,
              Src);
          goto LABEL_14;
        case 8:
          v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 120LL))(v9, &Src);
          if ( v21 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x2B9,
              (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
              (const char *)(unsigned int)v21,
              Src);
          goto LABEL_14;
      }
      if ( v28 != 1032 )
      {
        std::wstring::wstring(v35, L"Unsupported effect property type.");
        Windows::UI::Composition::OriginateException(v24, v35);
      }
      v32 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, int *, int **))(*(_QWORD *)v9 + 264LL))(v9, &v29, &v32);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
          (const char *)(unsigned int)v20,
          Src);
      v11 = 8;
      p_Src = v32;
      v33 = v32;
      v15 = v32;
LABEL_15:
      if ( v11 != *(_DWORD *)(v6 + 16) || v29 != *(_DWORD *)(v6 + 20) )
      {
        std::wstring::wstring(v35, L"Unexpected property type.");
        Windows::UI::Composition::OriginateException(v25, v35);
      }
      v17 = (void *)(v8 + *(unsigned int *)(v6 + 8));
      memcpy_0(v17, p_Src, (unsigned int)(v13 * v29));
      v18 = *(unsigned __int8 (__fastcall **)(void *))(v6 + 24);
      if ( v18 && v18(v17) )
      {
        memset(v35, 0, sizeof(v35));
        std::wstring::_Construct<1,unsigned short const *>(v35, L"Property value out of bounds", 28);
        Windows::UI::Composition::OriginateException(v22, v35);
      }
      if ( v15 )
        CoTaskMemFree(v15);
      v19 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( ++v5 >= v27 )
        return;
      v4 = v34;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 144LL))(v9, &Src);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2B3,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v12,
        Src);
    v13 = 1;
LABEL_14:
    v15 = 0;
    p_Src = &Src;
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x1800050d0  mov     [rsp-38h+arg_0], rbx
0x1800050d5  push    rbp
0x1800050d6  push    rsi
0x1800050d7  push    rdi
0x1800050d8  push    r12
0x1800050da  push    r13
0x1800050dc  push    r14
0x1800050de  push    r15
0x1800050e0  mov     rbp, rsp
0x1800050e3  sub     rsp, 80h
0x1800050ea  mov     rax, cs:__security_cookie
0x1800050f1  xor     rax, rsp
0x1800050f4  mov     [rbp+var_8], rax
0x1800050f8  mov     r13, r8
0x1800050fb  mov     rdi, rdx
0x1800050fe  mov     [rbp+var_30], rdx
0x180005102  xor     r15d, r15d
0x180005105  mov     [rbp+var_5C], r15d
0x180005109  mov     [rbp+var_48], r15
0x18000510d  mov     rcx, [r8]
0x180005110  mov     rax, [rcx]
0x180005113  lea     r8, [rbp+var_48]
0x180005117  lea     rdx, [rbp+var_5C]
0x18000511b  mov     rax, [rax+90h]
0x180005122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005127  mov     ebx, r15d
0x18000512a  cmp     [rbp+var_5C], ebx
0x18000512d  jbe     loc_1800052C4
0x180005133  mov     r14d, ebx
0x180005136  shl     r14, 5
0x18000513a  add     r14, [rbp+var_48]
0x18000513e  mov     [rbp+var_50], r15
0x180005142  mov     rax, [rdi]
0x180005145  lea     r8, [rbp+var_50]
0x180005149  mov     edx, ebx
0x18000514b  mov     rcx, rdi
0x18000514e  mov     rax, [rax+30h]
0x180005152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005157  mov     rcx, [rbp+38h]; this
0x18000515b  test    eax, eax
0x18000515d  jns     short loc_180005174
0x18000515f  mov     r9d, eax; char *
0x180005162  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005169  mov     edx, 285h; void *
0x18000516e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005174  mov     r12, [r13+18h]
0x180005178  mov     rsi, [rbp+var_50]
0x18000517c  mov     [rbp+var_58], r15d
0x180005180  mov     rax, [rsi]
0x180005183  lea     rdx, [rbp+var_58]
0x180005187  mov     rcx, rsi
0x18000518a  mov     rax, [rax+30h]
0x18000518e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005193  mov     rcx, [rbp+38h]; this
0x180005197  test    eax, eax
0x180005199  jns     short loc_1800051B0
0x18000519b  mov     r9d, eax; char *
0x18000519e  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800051a5  mov     edx, 2A0h; void *
0x1800051aa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800051b0  mov     edi, [rbp+var_58]
0x1800051b3  mov     [rbp+var_54], 1
0x1800051ba  mov     [rbp+Src], r15d
0x1800051be  mov     [rbp+var_38], r15
0x1800051c2  cmp     edi, 0Bh
0x1800051c5  jnz     short loc_1800051FA
0x1800051c7  mov     rax, [rsi]
0x1800051ca  lea     rdx, [rbp+Src]
0x1800051ce  mov     rcx, rsi
0x1800051d1  mov     rax, [rax+90h]
0x1800051d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051dd  mov     rcx, [rbp+38h]; this
0x1800051e1  test    eax, eax
0x1800051e3  jns     short loc_180005244
0x1800051e5  mov     r9d, eax; char *
0x1800051e8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800051ef  mov     edx, 2B3h; void *
0x1800051f4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800051fa  mov     r15d, 4
0x180005200  mov     ecx, edi
0x180005202  sub     ecx, r15d
0x180005205  jz      loc_1800053C8
0x18000520b  sub     ecx, 1
0x18000520e  jnz     loc_1800052EB
0x180005214  mov     rax, [rsi]
0x180005217  lea     rdx, [rbp+Src]
0x18000521b  mov     rcx, rsi
0x18000521e  mov     rax, [rax+60h]
0x180005222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005227  mov     rcx, [rbp+38h]; this
0x18000522b  test    eax, eax
0x18000522d  jns     short loc_18000524A
0x18000522f  mov     r9d, eax; char *
0x180005232  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005239  mov     edx, 2BEh; void *
0x18000523e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005244  mov     r15d, 1
0x18000524a  xor     esi, esi
0x18000524c  lea     rdx, [rbp+Src]; Src
0x180005250  cmp     edi, [r14+10h]
0x180005254  jnz     loc_180005417
0x18000525a  mov     r8d, [rbp+var_54]
0x18000525e  cmp     r8d, [r14+14h]
0x180005262  jnz     loc_180005417
0x180005268  mov     edi, [r14+8]
0x18000526c  add     rdi, r12
0x18000526f  imul    r8d, r15d; Size
0x180005273  mov     rcx, rdi; void *
0x180005276  call    memcpy_0
0x18000527b  mov     rax, [r14+18h]
0x18000527f  test    rax, rax
0x180005282  jnz     loc_180005373
0x180005288  test    rsi, rsi
0x18000528b  jz      short loc_180005297
0x18000528d  mov     rcx, rsi; pv
0x180005290  call    cs:__imp_CoTaskMemFree
0x180005296  nop
0x180005297  mov     rcx, [rbp+var_50]
0x18000529b  xor     r15d, r15d
0x18000529e  test    rcx, rcx
0x1800052a1  jz      short loc_1800052B4
0x1800052a3  mov     [rbp+var_50], r15
0x1800052a7  mov     rax, [rcx]
0x1800052aa  mov     rax, [rax+10h]
0x1800052ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b3  nop
0x1800052b4  inc     ebx
0x1800052b6  cmp     ebx, [rbp+var_5C]
0x1800052b9  jnb     short loc_1800052C4
0x1800052bb  mov     rdi, [rbp+var_30]
0x1800052bf  jmp     loc_180005133
0x1800052c4  mov     rcx, [rbp+var_8]
0x1800052c8  xor     rcx, rsp; StackCookie
0x1800052cb  call    __security_check_cookie
0x1800052d0  mov     rbx, [rsp+80h+arg_0]
0x1800052d8  add     rsp, 80h
0x1800052df  pop     r15
0x1800052e1  pop     r14
0x1800052e3  pop     r13
0x1800052e5  pop     r12
0x1800052e7  pop     rdi
0x1800052e8  pop     rsi
0x1800052e9  pop     rbp
0x1800052ea  retn
0x1800052eb  sub     ecx, 3
0x1800052ee  jz      short loc_18000533F
0x1800052f0  cmp     ecx, 400h
0x1800052f6  jnz     loc_1800053FC
0x1800052fc  mov     [rbp+var_40], 0
0x180005304  mov     rax, [rsi]
0x180005307  lea     r8, [rbp+var_40]
0x18000530b  lea     rdx, [rbp+var_54]
0x18000530f  mov     rcx, rsi
0x180005312  mov     rax, [rax+108h]
0x180005319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531e  mov     rcx, [rbp+38h]; this
0x180005322  test    eax, eax
0x180005324  jns     loc_1800053B3
0x18000532a  mov     r9d, eax; char *
0x18000532d  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005334  mov     edx, 2CCh; void *
0x180005339  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000533f  mov     rax, [rsi]
0x180005342  lea     rdx, [rbp+Src]
0x180005346  mov     rcx, rsi
0x180005349  mov     rax, [rax+78h]
0x18000534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005352  mov     rcx, [rbp+38h]; this
0x180005356  test    eax, eax
0x180005358  jns     loc_18000524A
0x18000535e  mov     r9d, eax; char *
0x180005361  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180005368  mov     edx, 2B9h; void *
0x18000536d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005373  mov     rcx, rdi
0x180005376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000537b  test    al, al
0x18000537d  jz      loc_180005288
0x180005383  xorps   xmm0, xmm0
0x180005386  movups  [rbp+var_28], xmm0
0x18000538a  xorps   xmm1, xmm1
0x18000538d  movdqu  [rbp+var_18], xmm1
0x180005392  mov     r8d, 1Ch
0x180005398  lea     rdx, aPropertyValueO; "Property value out of bounds"
0x18000539f  lea     rcx, [rbp+var_28]
0x1800053a3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800053a8  nop
0x1800053a9  lea     rdx, [rbp+var_28]
0x1800053ad  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x1800053b3  mov     edi, 8
0x1800053b8  mov     rdx, [rbp+var_40]
0x1800053bc  mov     [rbp+var_38], rdx
0x1800053c0  mov     rsi, rdx
0x1800053c3  jmp     loc_180005250
0x1800053c8  mov     rax, [rsi]
0x1800053cb  lea     rdx, [rbp+Src]
0x1800053cf  mov     rcx, rsi
0x1800053d2  mov     rax, [rax+58h]
0x1800053d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053db  mov     rcx, [rbp+38h]; this
0x1800053df  test    eax, eax
0x1800053e1  jns     loc_18000524A
0x1800053e7  mov     r9d, eax; char *
0x1800053ea  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800053f1  mov     edx, 2C3h; void *
0x1800053f6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800053fc  lea     rdx, aUnsupportedEff_0; "Unsupported effect property type."
0x180005403  lea     rcx, [rbp+var_28]
0x180005407  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000540c  nop
0x18000540d  lea     rdx, [rbp+var_28]
0x180005411  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180005417  lea     rdx, aUnexpectedProp; "Unexpected property type."
0x18000541e  lea     rcx, [rbp+var_28]
0x180005422  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180005427  nop
0x180005428  lea     rdx, [rbp+var_28]
0x18000542c  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
```
