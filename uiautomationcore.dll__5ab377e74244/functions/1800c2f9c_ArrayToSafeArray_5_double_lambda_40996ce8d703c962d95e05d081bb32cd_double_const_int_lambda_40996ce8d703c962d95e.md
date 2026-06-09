# ArrayToSafeArray<5,double,_lambda_40996ce8d703c962d95e05d081bb32cd_>(double const *,int,_lambda_40996ce8d703c962d95e05d081bb32cd_ &&)

- ea: `0x1800c2f9c`
- end: `0x1800c3185`
- name: `??$ArrayToSafeArray@$04NV_lambda_40996ce8d703c962d95e05d081bb32cd_@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBNH$$QEAV_lambda_40996ce8d703c962d95e05d081bb32cd_@@@Z`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c27cc`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800c2f9c`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c3019`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c3019`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c3087`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c3087`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c306b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c306b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c30aa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c30aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c30da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c30da`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c3036`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c3036`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c2fe6`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c2fe6`

## string_xrefs

- `0x1800c30f4`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c3112`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c3125`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c313d`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SAFEARRAY **ArrayToSafeArray<5,double,_lambda_40996ce8d703c962d95e05d081bb32cd_>(
        SAFEARRAY **a1,
        __int64 a2,
        signed int a3,
        ...)
{
  SAFEARRAY *Vector; // rax
  const char *v7; // r9
  HRESULT Vartype; // eax
  unsigned int v9; // ebx
  __int64 i; // r8
  __int64 v12; // rdx
  __int64 v13; // r9
  LONG plLbound; // [rsp+20h] [rbp-20h] BYREF
  int v15; // [rsp+24h] [rbp-1Ch]
  SAFEARRAY *psa; // [rsp+28h] [rbp-18h]
  int v17; // [rsp+30h] [rbp-10h]
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  VARTYPE pvt; // [rsp+80h] [rbp+40h] BYREF
  __int64 plUbound; // [rsp+88h] [rbp+48h] BYREF
  va_list plUbounda; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(plUbounda, a3);
  plUbound = va_arg(va1, _QWORD);
  v15 = 0;
  if ( a3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      plLbound);
  Vector = SafeArrayCreateVector(5u, 0, a3);
  *a1 = Vector;
  v15 = 1;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      v7);
  v17 = 0;
  ppvData = 0;
  psa = Vector;
  if ( SafeArrayGetDim(Vector) != 1 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 92;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v13,
      plLbound);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v9,
      plLbound);
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 95;
    goto LABEL_16;
  }
  if ( pvt != 5 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 106;
    goto LABEL_17;
  }
  plLbound = 0;
  LODWORD(plUbound) = 0;
  Vartype = SafeArrayGetLBound(psa, 1u, &plLbound);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 111;
    goto LABEL_16;
  }
  Vartype = SafeArrayGetUBound(psa, 1u, (LONG *)plUbounda);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 112;
    goto LABEL_16;
  }
  v17 = plUbound - plLbound + 1;
  Vartype = SafeArrayAccessData(psa, &ppvData);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 115;
LABEL_16:
    v13 = (unsigned int)Vartype;
    goto LABEL_17;
  }
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    *((_QWORD *)ppvData + i) = *(_QWORD *)(a2 + 8 * i);
  if ( psa )
    SafeArrayUnaccessData(psa);
  return a1;
}

```

## disassembly

```asm
0x1800c2f9c  mov     [rsp-28h+arg_8], rbx
0x1800c2fa1  mov     [rsp-28h+plUbound], r9
0x1800c2fa6  mov     [rsp-28h+arg_0], rcx
0x1800c2fab  push    rbp
0x1800c2fac  push    rsi
0x1800c2fad  push    rdi
0x1800c2fae  push    r13
0x1800c2fb0  push    r14
0x1800c2fb2  mov     rbp, rsp
0x1800c2fb5  sub     rsp, 40h
0x1800c2fb9  mov     edi, r8d
0x1800c2fbc  mov     r14, rdx
0x1800c2fbf  mov     rsi, rcx
0x1800c2fc2  mov     [rbp+var_1C], 0
0x1800c2fc9  mov     rcx, [rbp+28h]; this
0x1800c2fcd  mov     eax, r8d
0x1800c2fd0  shr     eax, 1Fh
0x1800c2fd3  test    al, al
0x1800c2fd5  jnz     loc_1800C3137
0x1800c2fdb  mov     r13d, 5
0x1800c2fe1  mov     ecx, r13d; vt
0x1800c2fe4  xor     edx, edx; lLbound
0x1800c2fe6  call    cs:__imp_SafeArrayCreateVector
0x1800c2fec  mov     [rsi], rax
0x1800c2fef  mov     [rbp+var_1C], 1
0x1800c2ff6  mov     rcx, [rbp+28h]; this
0x1800c2ffa  test    rax, rax
0x1800c2ffd  jz      loc_1800C30F4
0x1800c3003  mov     [rbp+var_10], 0
0x1800c300a  mov     [rbp+ppvData], 0
0x1800c3012  mov     [rbp+psa], rax
0x1800c3016  mov     rcx, rax; psa
0x1800c3019  call    cs:__imp_SafeArrayGetDim
0x1800c301f  cmp     eax, 1
0x1800c3022  jnz     loc_1800C3174
0x1800c3028  xor     eax, eax
0x1800c302a  mov     [rbp+pvt], ax
0x1800c302e  lea     rdx, [rbp+pvt]; pvt
0x1800c3032  mov     rcx, [rbp+psa]; psa
0x1800c3036  call    cs:__imp_SafeArrayGetVartype
0x1800c303c  mov     ebx, eax
0x1800c303e  test    eax, eax
0x1800c3040  js      loc_1800C3156
0x1800c3046  cmp     [rbp+pvt], r13w
0x1800c304b  jnz     loc_1800C315D
0x1800c3051  mov     [rbp+plLbound], 0
0x1800c3058  mov     dword ptr [rbp+plUbound], 0
0x1800c305f  lea     r8, [rbp+plLbound]; plLbound
0x1800c3063  lea     edx, [r13-4]; nDim
0x1800c3067  mov     rcx, [rbp+psa]; psa
0x1800c306b  call    cs:__imp_SafeArrayGetLBound
0x1800c3071  mov     ebx, eax
0x1800c3073  test    eax, eax
0x1800c3075  js      loc_1800C314F
0x1800c307b  lea     r8, [rbp+plUbound]; plUbound
0x1800c307f  lea     edx, [r13-4]; nDim
0x1800c3083  mov     rcx, [rbp+psa]; psa
0x1800c3087  call    cs:__imp_SafeArrayGetUBound
0x1800c308d  mov     ebx, eax
0x1800c308f  test    eax, eax
0x1800c3091  js      loc_1800C316D
0x1800c3097  mov     eax, dword ptr [rbp+plUbound]
0x1800c309a  sub     eax, [rbp+plLbound]
0x1800c309d  inc     eax
0x1800c309f  mov     [rbp+var_10], eax
0x1800c30a2  lea     rdx, [rbp+ppvData]; ppvData
0x1800c30a6  mov     rcx, [rbp+psa]; psa
0x1800c30aa  call    cs:__imp_SafeArrayAccessData
0x1800c30b0  mov     ebx, eax
0x1800c30b2  test    eax, eax
0x1800c30b4  js      short loc_1800C3106
0x1800c30b6  xor     r8d, r8d
0x1800c30b9  test    edi, edi
0x1800c30bb  jz      short loc_1800C30D1
0x1800c30bd  mov     rcx, [r14+r8*8]
0x1800c30c1  mov     rax, [rbp+ppvData]
0x1800c30c5  mov     [rax+r8*8], rcx
0x1800c30c9  inc     r8d
0x1800c30cc  cmp     r8d, edi
0x1800c30cf  jb      short loc_1800C30BD
0x1800c30d1  mov     rcx, [rbp+psa]; psa
0x1800c30d5  test    rcx, rcx
0x1800c30d8  jz      short loc_1800C30E0
0x1800c30da  call    cs:__imp_SafeArrayUnaccessData
0x1800c30e0  mov     rax, rsi
0x1800c30e3  mov     rbx, [rsp+40h+arg_8]
0x1800c30e8  add     rsp, 40h
0x1800c30ec  pop     r14
0x1800c30ee  pop     r13
0x1800c30f0  pop     rdi
0x1800c30f1  pop     rsi
0x1800c30f2  pop     rbp
0x1800c30f3  retn
0x1800c30f4  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c30fb  mov     edx, 132h; void *
0x1800c3100  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800c3106  mov     edx, 73h ; 's'; void *
0x1800c310b  mov     r9d, eax; char *
0x1800c310e  mov     rcx, [rbp+28h]; this
0x1800c3112  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c3119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c311e  mov     rcx, [rbp+28h]; this
0x1800c3122  mov     r9d, ebx; char *
0x1800c3125  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c312c  mov     edx, 43h ; 'C'; void *
0x1800c3131  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c3137  mov     r9d, 80070057h; char *
0x1800c313d  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c3144  mov     edx, 130h; void *
0x1800c3149  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c314f  mov     edx, 6Fh ; 'o'
0x1800c3154  jmp     short loc_1800C310B
0x1800c3156  mov     edx, 5Fh ; '_'
0x1800c315b  jmp     short loc_1800C310B
0x1800c315d  mov     r9d, 80070057h
0x1800c3163  mov     ebx, r9d
0x1800c3166  mov     edx, 6Ah ; 'j'
0x1800c316b  jmp     short loc_1800C310E
0x1800c316d  mov     edx, 70h ; 'p'
0x1800c3172  jmp     short loc_1800C310B
0x1800c3174  mov     r9d, 80070057h
0x1800c317a  mov     ebx, r9d
0x1800c317d  mov     edx, 5Ch ; '\'
0x1800c3182  jmp     short loc_1800C310E
```
