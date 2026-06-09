# D2DImageConverterBase::EnsureInitialized(IWICComponentFactory *)

- ea: `0x18003d420`
- end: `0x18003d6b8`
- name: `?EnsureInitialized@D2DImageConverterBase@@IEAAJPEAUIWICComponentFactory@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(D2DImageConverterBase *__hidden this, struct IWICComponentFactory *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003b7b0`

## callees

- `0x180035e50`
- `0x18003d420`
- `0x180044010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003d4a4`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003d4a4`
- `d3d11!D3D11CreateDevice` at `0x18003d55d`
- `d3d11!D3D11CreateDevice` at `0x18003d55d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall D2DImageConverterBase::EnsureInitialized(
        D2DImageConverterBase *this,
        struct IWICComponentFactory *a2)
{
  int v4; // esi
  struct IWICComponentFactory *v5; // rcx
  HRESULT result; // eax
  __int64 *v7; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, char *); // rbp
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rsi
  __int64 v18; // rcx
  int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  D2D1_FACTORY_OPTIONS pFactoryOptions[2]; // [rsp+50h] [rbp-58h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+58h] [rbp-50h] BYREF
  int v24; // [rsp+68h] [rbp-40h]
  int v25; // [rsp+6Ch] [rbp-3Ch]
  int v26; // [rsp+70h] [rbp-38h]

  v4 = 0;
  if ( *(struct IWICComponentFactory **)this != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IWICComponentFactory *))a2->lpVtbl->AddRef)(a2);
    v5 = *(struct IWICComponentFactory **)this;
    *(_QWORD *)this = a2;
    if ( v5 )
      ((void (__fastcall *)(struct IWICComponentFactory *))v5->lpVtbl->Release)(v5);
  }
  if ( *((_QWORD *)this + 2)
    || (pFactoryOptions[0].debugLevel = D2D1_DEBUG_LEVEL_NONE,
        result = D2D1CreateFactory(
                   D2D1_FACTORY_TYPE_SINGLE_THREADED,
                   &GUID_f9976f46_f642_44c1_97ca_da32ea2a2635,
                   pFactoryOptions,
                   (void **)this + 2),
        v4 = result,
        result >= 0) )
  {
    v7 = (__int64 *)((char *)this + 40);
    if ( *((_QWORD *)this + 5) )
      return v4;
    *(__m128i *)pFeatureLevels = _mm_load_si128((const __m128i *)&_xmm);
    v24 = 37632;
    v25 = 37376;
    v26 = 37120;
    v8 = *((_QWORD *)this + 6);
    if ( v8 )
    {
      *((_QWORD *)this + 6) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = (_QWORD *)((char *)this + 32);
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      *v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    result = D3D11CreateDevice(
               0,
               D3D_DRIVER_TYPE_WARP,
               0,
               0x20u,
               pFeatureLevels,
               7u,
               7u,
               (ID3D11Device **)this + 4,
               (D3D_FEATURE_LEVEL *)this + 20,
               (ID3D11DeviceContext **)this + 6);
    if ( result >= 0 )
    {
      *(_QWORD *)&pFactoryOptions[0].debugLevel = 0;
      v4 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, D2D1_FACTORY_OPTIONS *))*v9)(
             *v9,
             &GUID_6007896c_3244_4afd_bf18_a6d3beda5023,
             pFactoryOptions);
      if ( v4 < 0 )
      {
        v11 = *(_QWORD *)&pFactoryOptions[0].debugLevel;
        if ( *(_QWORD *)&pFactoryOptions[0].debugLevel )
        {
          *(_QWORD *)&pFactoryOptions[0].debugLevel = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        return v4;
      }
      v12 = *((_QWORD *)this + 2);
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v12 + 248LL);
      v14 = *((_QWORD *)this + 3);
      if ( v14 )
      {
        *((_QWORD *)this + 3) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v4 = v13(v12, *(_QWORD *)&pFactoryOptions[0].debugLevel, (char *)this + 24);
      if ( v4 < 0 )
      {
        v15 = *(_QWORD *)&pFactoryOptions[0].debugLevel;
        if ( *(_QWORD *)&pFactoryOptions[0].debugLevel )
        {
          *(_QWORD *)&pFactoryOptions[0].debugLevel = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        return v4;
      }
      v16 = *((_QWORD *)this + 3);
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 152LL);
      v18 = *v7;
      if ( *v7 )
      {
        *v7 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v17(v16, 0, v7);
      if ( v19 >= 0 )
      {
        v21 = *(_QWORD *)&pFactoryOptions[0].debugLevel;
        if ( *(_QWORD *)&pFactoryOptions[0].debugLevel )
        {
          *(_QWORD *)&pFactoryOptions[0].debugLevel = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        return v19;
      }
      else
      {
        v20 = *(_QWORD *)&pFactoryOptions[0].debugLevel;
        if ( *(_QWORD *)&pFactoryOptions[0].debugLevel )
        {
          *(_QWORD *)&pFactoryOptions[0].debugLevel = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        return v19;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003d420  mov     [rsp+arg_8], rbx
0x18003d425  mov     [rsp+arg_10], rbp
0x18003d42a  push    rsi
0x18003d42b  push    rdi
0x18003d42c  push    r12
0x18003d42e  push    r14
0x18003d430  push    r15
0x18003d432  sub     rsp, 80h
0x18003d439  mov     rax, cs:__security_cookie
0x18003d440  xor     rax, rsp
0x18003d443  mov     [rsp+0A8h+var_30], rax
0x18003d448  mov     rdi, rdx
0x18003d44b  mov     rbx, rcx
0x18003d44e  xor     r12d, r12d
0x18003d451  mov     esi, r12d
0x18003d454  cmp     [rcx], rdx
0x18003d457  jz      short loc_18003D486
0x18003d459  test    rdx, rdx
0x18003d45c  jz      short loc_18003D46E
0x18003d45e  mov     rax, [rdx]
0x18003d461  mov     rcx, rdx
0x18003d464  mov     rax, [rax+8]
0x18003d468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d46d  nop
0x18003d46e  mov     rcx, [rbx]
0x18003d471  mov     [rbx], rdi
0x18003d474  test    rcx, rcx
0x18003d477  jz      short loc_18003D486
0x18003d479  mov     rax, [rcx]
0x18003d47c  mov     rax, [rax+10h]
0x18003d480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d485  nop
0x18003d486  cmp     qword ptr [rbx+10h], 0
0x18003d48b  jnz     short loc_18003D4B4
0x18003d48d  mov     [rsp+0A8h+pFactoryOptions.debugLevel], r12d
0x18003d492  lea     r9, [rbx+10h]; ppIFactory
0x18003d496  lea     r8, [rsp+0A8h+pFactoryOptions]; pFactoryOptions
0x18003d49b  lea     rdx, _GUID_f9976f46_f642_44c1_97ca_da32ea2a2635; riid
0x18003d4a2  xor     ecx, ecx; factoryType
0x18003d4a4  call    cs:__imp_D2D1CreateFactory
0x18003d4aa  mov     esi, eax
0x18003d4ac  test    eax, eax
0x18003d4ae  js      loc_18003D5AA
0x18003d4b4  lea     rdi, [rbx+28h]
0x18003d4b8  cmp     qword ptr [rdi], 0
0x18003d4bc  jnz     loc_18003D5A8
0x18003d4c2  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x18003d4ca  movdqu  xmmword ptr [rsp+0A8h+var_50], xmm0
0x18003d4d0  mov     [rsp+0A8h+var_40], 9300h
0x18003d4d8  mov     [rsp+0A8h+var_3C], 9200h
0x18003d4e0  mov     [rsp+0A8h+var_38], 9100h
0x18003d4e8  lea     r15, [rbx+30h]
0x18003d4ec  mov     rcx, [r15]
0x18003d4ef  test    rcx, rcx
0x18003d4f2  jz      short loc_18003D504
0x18003d4f4  mov     [r15], r12
0x18003d4f7  mov     rax, [rcx]
0x18003d4fa  mov     rax, [rax+10h]
0x18003d4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d503  nop
0x18003d504  lea     rsi, [rbx+20h]
0x18003d508  mov     rcx, [rsi]
0x18003d50b  test    rcx, rcx
0x18003d50e  jz      short loc_18003D520
0x18003d510  mov     [rsi], r12
0x18003d513  mov     rax, [rcx]
0x18003d516  mov     rax, [rax+10h]
0x18003d51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d51f  nop
0x18003d520  lea     rax, [rbx+50h]
0x18003d524  mov     [rsp+0A8h+ppImmediateContext], r15; ppImmediateContext
0x18003d529  mov     [rsp+0A8h+pFeatureLevel], rax; pFeatureLevel
0x18003d52e  mov     [rsp+0A8h+ppDevice], rsi; ppDevice
0x18003d533  mov     [rsp+0A8h+SDKVersion], 7; SDKVersion
0x18003d53b  mov     [rsp+0A8h+FeatureLevels], 7; FeatureLevels
0x18003d543  lea     rax, [rsp+0A8h+var_50]
0x18003d548  mov     [rsp+0A8h+pFeatureLevels], rax; pFeatureLevels
0x18003d54d  mov     r9d, 20h ; ' '; Flags
0x18003d553  xor     r8d, r8d; Software
0x18003d556  mov     edx, 5; DriverType
0x18003d55b  xor     ecx, ecx; pAdapter
0x18003d55d  call    cs:__imp_D3D11CreateDevice
0x18003d563  test    eax, eax
0x18003d565  js      short loc_18003D5AA
0x18003d567  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003d56c  mov     rcx, [rsi]
0x18003d56f  mov     rax, [rcx]
0x18003d572  lea     r8, [rsp+0A8h+pFactoryOptions]
0x18003d577  lea     rdx, _GUID_6007896c_3244_4afd_bf18_a6d3beda5023
0x18003d57e  mov     rax, [rax]
0x18003d581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d586  mov     esi, eax
0x18003d588  test    eax, eax
0x18003d58a  jns     short loc_18003D5D3
0x18003d58c  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003d591  test    rcx, rcx
0x18003d594  jz      short loc_18003D5A8
0x18003d596  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003d59b  mov     rdx, [rcx]
0x18003d59e  mov     rax, [rdx+10h]
0x18003d5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5a7  nop
0x18003d5a8  mov     eax, esi
0x18003d5aa  mov     rcx, [rsp+0A8h+var_30]
0x18003d5af  xor     rcx, rsp; StackCookie
0x18003d5b2  call    __security_check_cookie
0x18003d5b7  lea     r11, [rsp+0A8h+var_28]
0x18003d5bf  mov     rbx, [r11+38h]
0x18003d5c3  mov     rbp, [r11+40h]
0x18003d5c7  mov     rsp, r11
0x18003d5ca  pop     r15
0x18003d5cc  pop     r14
0x18003d5ce  pop     r12
0x18003d5d0  pop     rdi
0x18003d5d1  pop     rsi
0x18003d5d2  retn
0x18003d5d3  mov     rsi, [rbx+10h]
0x18003d5d7  mov     rax, [rsi]
0x18003d5da  mov     rbp, [rax+0F8h]
0x18003d5e1  mov     rcx, [rbx+18h]
0x18003d5e5  test    rcx, rcx
0x18003d5e8  jz      short loc_18003D5FB
0x18003d5ea  mov     [rbx+18h], r12
0x18003d5ee  mov     rdx, [rcx]
0x18003d5f1  mov     rax, [rdx+10h]
0x18003d5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5fa  nop
0x18003d5fb  lea     r8, [rbx+18h]
0x18003d5ff  mov     rdx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003d604  mov     rcx, rsi
0x18003d607  mov     rax, rbp
0x18003d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d60f  mov     esi, eax
0x18003d611  test    eax, eax
0x18003d613  jns     short loc_18003D636
0x18003d615  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003d61a  test    rcx, rcx
0x18003d61d  jz      short loc_18003D631
0x18003d61f  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003d624  mov     rdx, [rcx]
0x18003d627  mov     rax, [rdx+10h]
0x18003d62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d630  nop
0x18003d631  jmp     loc_18003D5A8
0x18003d636  mov     rbx, [rbx+18h]
0x18003d63a  mov     rax, [rbx]
0x18003d63d  mov     rsi, [rax+98h]
0x18003d644  mov     rcx, [rdi]
0x18003d647  test    rcx, rcx
0x18003d64a  jz      short loc_18003D65C
0x18003d64c  mov     [rdi], r12
0x18003d64f  mov     rdx, [rcx]
0x18003d652  mov     rax, [rdx+10h]
0x18003d656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d65b  nop
0x18003d65c  mov     r8, rdi
0x18003d65f  xor     edx, edx
0x18003d661  mov     rcx, rbx
0x18003d664  mov     rax, rsi
0x18003d667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d66c  mov     ebx, eax
0x18003d66e  test    eax, eax
0x18003d670  jns     short loc_18003D695
0x18003d672  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003d677  test    rcx, rcx
0x18003d67a  jz      short loc_18003D68E
0x18003d67c  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003d681  mov     rdx, [rcx]
0x18003d684  mov     rax, [rdx+10h]
0x18003d688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d68d  nop
0x18003d68e  mov     eax, ebx
0x18003d690  jmp     loc_18003D5AA
0x18003d695  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003d69a  test    rcx, rcx
0x18003d69d  jz      short loc_18003D6B1
0x18003d69f  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003d6a4  mov     rax, [rcx]
0x18003d6a7  mov     rax, [rax+10h]
0x18003d6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6b0  nop
0x18003d6b1  mov     eax, ebx
0x18003d6b3  jmp     loc_18003D5AA
```
