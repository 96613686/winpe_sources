# D2DImageConverterBase::EnsureInitialized(IWICComponentFactory *)

- ea: `0x18003db90`
- end: `0x18003de35`
- name: `?EnsureInitialized@D2DImageConverterBase@@IEAAJPEAUIWICComponentFactory@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(D2DImageConverterBase *__hidden this, struct IWICComponentFactory *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003c0a0`

## callees

- `0x180036420`
- `0x18003db90`
- `0x180045010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003dc14`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003dc14`
- `d3d11!D3D11CreateDevice` at `0x18003dcd3`
- `d3d11!D3D11CreateDevice` at `0x18003dcd3`

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
0x18003db90  mov     [rsp+arg_8], rbx
0x18003db95  mov     [rsp+arg_10], rbp
0x18003db9a  push    rsi
0x18003db9b  push    rdi
0x18003db9c  push    r12
0x18003db9e  push    r14
0x18003dba0  push    r15
0x18003dba2  sub     rsp, 80h
0x18003dba9  mov     rax, cs:__security_cookie
0x18003dbb0  xor     rax, rsp
0x18003dbb3  mov     [rsp+0A8h+var_30], rax
0x18003dbb8  mov     rdi, rdx
0x18003dbbb  mov     rbx, rcx
0x18003dbbe  xor     r12d, r12d
0x18003dbc1  mov     esi, r12d
0x18003dbc4  cmp     [rcx], rdx
0x18003dbc7  jz      short loc_18003DBF6
0x18003dbc9  test    rdx, rdx
0x18003dbcc  jz      short loc_18003DBDE
0x18003dbce  mov     rax, [rdx]
0x18003dbd1  mov     rcx, rdx
0x18003dbd4  mov     rax, [rax+8]
0x18003dbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbdd  nop
0x18003dbde  mov     rcx, [rbx]
0x18003dbe1  mov     [rbx], rdi
0x18003dbe4  test    rcx, rcx
0x18003dbe7  jz      short loc_18003DBF6
0x18003dbe9  mov     rax, [rcx]
0x18003dbec  mov     rax, [rax+10h]
0x18003dbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbf5  nop
0x18003dbf6  cmp     qword ptr [rbx+10h], 0
0x18003dbfb  jnz     short loc_18003DC2A
0x18003dbfd  mov     [rsp+0A8h+pFactoryOptions.debugLevel], r12d
0x18003dc02  lea     r9, [rbx+10h]; ppIFactory
0x18003dc06  lea     r8, [rsp+0A8h+pFactoryOptions]; pFactoryOptions
0x18003dc0b  lea     rdx, _GUID_f9976f46_f642_44c1_97ca_da32ea2a2635; riid
0x18003dc12  xor     ecx, ecx; factoryType
0x18003dc14  call    cs:__imp_D2D1CreateFactory
0x18003dc1b  nop     dword ptr [rax+rax+00h]
0x18003dc20  mov     esi, eax
0x18003dc22  test    eax, eax
0x18003dc24  js      loc_18003DD26
0x18003dc2a  lea     rdi, [rbx+28h]
0x18003dc2e  cmp     qword ptr [rdi], 0
0x18003dc32  jnz     loc_18003DD24
0x18003dc38  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x18003dc40  movdqu  xmmword ptr [rsp+0A8h+var_50], xmm0
0x18003dc46  mov     [rsp+0A8h+var_40], 9300h
0x18003dc4e  mov     [rsp+0A8h+var_3C], 9200h
0x18003dc56  mov     [rsp+0A8h+var_38], 9100h
0x18003dc5e  lea     r15, [rbx+30h]
0x18003dc62  mov     rcx, [r15]
0x18003dc65  test    rcx, rcx
0x18003dc68  jz      short loc_18003DC7A
0x18003dc6a  mov     [r15], r12
0x18003dc6d  mov     rax, [rcx]
0x18003dc70  mov     rax, [rax+10h]
0x18003dc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc79  nop
0x18003dc7a  lea     rsi, [rbx+20h]
0x18003dc7e  mov     rcx, [rsi]
0x18003dc81  test    rcx, rcx
0x18003dc84  jz      short loc_18003DC96
0x18003dc86  mov     [rsi], r12
0x18003dc89  mov     rax, [rcx]
0x18003dc8c  mov     rax, [rax+10h]
0x18003dc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc95  nop
0x18003dc96  lea     rax, [rbx+50h]
0x18003dc9a  mov     [rsp+0A8h+ppImmediateContext], r15; ppImmediateContext
0x18003dc9f  mov     [rsp+0A8h+pFeatureLevel], rax; pFeatureLevel
0x18003dca4  mov     [rsp+0A8h+ppDevice], rsi; ppDevice
0x18003dca9  mov     [rsp+0A8h+SDKVersion], 7; SDKVersion
0x18003dcb1  mov     [rsp+0A8h+FeatureLevels], 7; FeatureLevels
0x18003dcb9  lea     rax, [rsp+0A8h+var_50]
0x18003dcbe  mov     [rsp+0A8h+pFeatureLevels], rax; pFeatureLevels
0x18003dcc3  mov     r9d, 20h ; ' '; Flags
0x18003dcc9  xor     r8d, r8d; Software
0x18003dccc  mov     edx, 5; DriverType
0x18003dcd1  xor     ecx, ecx; pAdapter
0x18003dcd3  call    cs:__imp_D3D11CreateDevice
0x18003dcda  nop     dword ptr [rax+rax+00h]
0x18003dcdf  test    eax, eax
0x18003dce1  js      short loc_18003DD26
0x18003dce3  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003dce8  mov     rcx, [rsi]
0x18003dceb  mov     rax, [rcx]
0x18003dcee  lea     r8, [rsp+0A8h+pFactoryOptions]
0x18003dcf3  lea     rdx, _GUID_6007896c_3244_4afd_bf18_a6d3beda5023
0x18003dcfa  mov     rax, [rax]
0x18003dcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd02  mov     esi, eax
0x18003dd04  test    eax, eax
0x18003dd06  jns     short loc_18003DD50
0x18003dd08  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003dd0d  test    rcx, rcx
0x18003dd10  jz      short loc_18003DD24
0x18003dd12  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003dd17  mov     rdx, [rcx]
0x18003dd1a  mov     rax, [rdx+10h]
0x18003dd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd23  nop
0x18003dd24  mov     eax, esi
0x18003dd26  mov     rcx, [rsp+0A8h+var_30]
0x18003dd2b  xor     rcx, rsp; StackCookie
0x18003dd2e  call    __security_check_cookie
0x18003dd33  lea     r11, [rsp+0A8h+var_28]
0x18003dd3b  mov     rbx, [r11+38h]
0x18003dd3f  mov     rbp, [r11+40h]
0x18003dd43  mov     rsp, r11
0x18003dd46  pop     r15
0x18003dd48  pop     r14
0x18003dd4a  pop     r12
0x18003dd4c  pop     rdi
0x18003dd4d  pop     rsi
0x18003dd4e  retn
0x18003dd50  mov     rsi, [rbx+10h]
0x18003dd54  mov     rax, [rsi]
0x18003dd57  mov     rbp, [rax+0F8h]
0x18003dd5e  mov     rcx, [rbx+18h]
0x18003dd62  test    rcx, rcx
0x18003dd65  jz      short loc_18003DD78
0x18003dd67  mov     [rbx+18h], r12
0x18003dd6b  mov     rdx, [rcx]
0x18003dd6e  mov     rax, [rdx+10h]
0x18003dd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd77  nop
0x18003dd78  lea     r8, [rbx+18h]
0x18003dd7c  mov     rdx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003dd81  mov     rcx, rsi
0x18003dd84  mov     rax, rbp
0x18003dd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd8c  mov     esi, eax
0x18003dd8e  test    eax, eax
0x18003dd90  jns     short loc_18003DDB3
0x18003dd92  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003dd97  test    rcx, rcx
0x18003dd9a  jz      short loc_18003DDAE
0x18003dd9c  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003dda1  mov     rdx, [rcx]
0x18003dda4  mov     rax, [rdx+10h]
0x18003dda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddad  nop
0x18003ddae  jmp     loc_18003DD24
0x18003ddb3  mov     rbx, [rbx+18h]
0x18003ddb7  mov     rax, [rbx]
0x18003ddba  mov     rsi, [rax+98h]
0x18003ddc1  mov     rcx, [rdi]
0x18003ddc4  test    rcx, rcx
0x18003ddc7  jz      short loc_18003DDD9
0x18003ddc9  mov     [rdi], r12
0x18003ddcc  mov     rdx, [rcx]
0x18003ddcf  mov     rax, [rdx+10h]
0x18003ddd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddd8  nop
0x18003ddd9  mov     r8, rdi
0x18003dddc  xor     edx, edx
0x18003ddde  mov     rcx, rbx
0x18003dde1  mov     rax, rsi
0x18003dde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dde9  mov     ebx, eax
0x18003ddeb  test    eax, eax
0x18003dded  jns     short loc_18003DE12
0x18003ddef  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003ddf4  test    rcx, rcx
0x18003ddf7  jz      short loc_18003DE0B
0x18003ddf9  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003ddfe  mov     rdx, [rcx]
0x18003de01  mov     rax, [rdx+10h]
0x18003de05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de0a  nop
0x18003de0b  mov     eax, ebx
0x18003de0d  jmp     loc_18003DD26
0x18003de12  mov     rcx, qword ptr [rsp+0A8h+pFactoryOptions.debugLevel]
0x18003de17  test    rcx, rcx
0x18003de1a  jz      short loc_18003DE2E
0x18003de1c  mov     qword ptr [rsp+0A8h+pFactoryOptions.debugLevel], r12
0x18003de21  mov     rax, [rcx]
0x18003de24  mov     rax, [rax+10h]
0x18003de28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de2d  nop
0x18003de2e  mov     eax, ebx
0x18003de30  jmp     loc_18003DD26
```
