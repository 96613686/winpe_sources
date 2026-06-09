# ArrayToSafeArray<3,uint,_lambda_08ce7e0006d56236c8a28b10a775ceb7_>(uint const *,int,_lambda_08ce7e0006d56236c8a28b10a775ceb7_ &&)

- ea: `0x1800613bc`
- end: `0x1800615b6`
- name: `??$ArrayToSafeArray@$02IV_lambda_08ce7e0006d56236c8a28b10a775ceb7_@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBIH$$QEAV_lambda_08ce7e0006d56236c8a28b10a775ceb7_@@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180061368`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800613bc`
- `0x1801a4e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180061439`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180061439`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800614a9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800614a9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18006148c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18006148c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800614cc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800614cc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061500`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061500`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180061456`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180061456`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180061406`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180061406`

## string_xrefs

- `0x180061550`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180061563`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18006151a`: `onecore\windows\accessibletech\Common\SafeArray.h`
- `0x180061532`: `onecore\windows\accessibletech\Common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SAFEARRAY **ArrayToSafeArray<3,unsigned int,_lambda_08ce7e0006d56236c8a28b10a775ceb7_>(
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
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      (const char *)0x80070057LL,
      plLbound);
  Vector = SafeArrayCreateVector(3u, 0, a3);
  *a1 = Vector;
  v15 = 1;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      v7);
  v17 = 0;
  ppvData = 0;
  psa = Vector;
  if ( SafeArrayGetDim(Vector) != 1 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 92;
    goto LABEL_18;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 95;
    goto LABEL_17;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v13 = 2147942487LL;
    v9 = -2147024809;
    v12 = 106;
LABEL_18:
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
  plLbound = 0;
  LODWORD(plUbound) = 0;
  Vartype = SafeArrayGetLBound(psa, 1u, &plLbound);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 111;
LABEL_17:
    v13 = (unsigned int)Vartype;
    goto LABEL_18;
  }
  Vartype = SafeArrayGetUBound(psa, 1u, (LONG *)plUbounda);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 112;
    goto LABEL_17;
  }
  v17 = plUbound - plLbound + 1;
  Vartype = SafeArrayAccessData(psa, &ppvData);
  v9 = Vartype;
  if ( Vartype < 0 )
  {
    v12 = 115;
    goto LABEL_17;
  }
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    *((_DWORD *)ppvData + i) = *(_DWORD *)(a2 + 4 * i);
  if ( psa )
    SafeArrayUnaccessData(psa);
  return a1;
}

```

## disassembly

```asm
0x1800613bc  mov     [rsp-28h+arg_8], rbx
0x1800613c1  mov     [rsp-28h+plUbound], r9
0x1800613c6  mov     [rsp-28h+arg_0], rcx
0x1800613cb  push    rbp
0x1800613cc  push    rsi
0x1800613cd  push    rdi
0x1800613ce  push    r13
0x1800613d0  push    r14
0x1800613d2  mov     rbp, rsp
0x1800613d5  sub     rsp, 40h
0x1800613d9  mov     edi, r8d
0x1800613dc  mov     r14, rdx
0x1800613df  mov     rsi, rcx
0x1800613e2  mov     [rbp+var_1C], 0
0x1800613e9  mov     rcx, [rbp+28h]; this
0x1800613ed  mov     eax, r8d
0x1800613f0  shr     eax, 1Fh
0x1800613f3  test    al, al
0x1800613f5  jnz     loc_18006152C
0x1800613fb  mov     r13d, 3
0x180061401  mov     ecx, r13d; vt
0x180061404  xor     edx, edx; lLbound
0x180061406  call    cs:__imp_SafeArrayCreateVector
0x18006140c  mov     [rsi], rax
0x18006140f  mov     [rbp+var_1C], 1
0x180061416  mov     rcx, [rbp+28h]; this
0x18006141a  test    rax, rax
0x18006141d  jz      loc_18006151A
0x180061423  mov     [rbp+var_10], 0
0x18006142a  mov     [rbp+ppvData], 0
0x180061432  mov     [rbp+psa], rax
0x180061436  mov     rcx, rax; psa
0x180061439  call    cs:__imp_SafeArrayGetDim
0x18006143f  cmp     eax, 1
0x180061442  jnz     loc_18006157C
0x180061448  xor     eax, eax
0x18006144a  mov     [rbp+pvt], ax
0x18006144e  lea     rdx, [rbp+pvt]; pvt
0x180061452  mov     rcx, [rbp+psa]; psa
0x180061456  call    cs:__imp_SafeArrayGetVartype
0x18006145c  mov     ebx, eax
0x18006145e  test    eax, eax
0x180061460  js      loc_18006158C
0x180061466  cmp     [rbp+pvt], r13w
0x18006146b  jnz     loc_18006159A
0x180061471  mov     [rbp+plLbound], 0
0x180061478  mov     dword ptr [rbp+plUbound], 0
0x18006147f  lea     r8, [rbp+plLbound]; plLbound
0x180061483  mov     edx, 1; nDim
0x180061488  mov     rcx, [rbp+psa]; psa
0x18006148c  call    cs:__imp_SafeArrayGetLBound
0x180061492  mov     ebx, eax
0x180061494  test    eax, eax
0x180061496  js      loc_180061544
0x18006149c  lea     r8, [rbp+plUbound]; plUbound
0x1800614a0  mov     edx, 1; nDim
0x1800614a5  mov     rcx, [rbp+psa]; psa
0x1800614a9  call    cs:__imp_SafeArrayGetUBound
0x1800614af  mov     ebx, eax
0x1800614b1  test    eax, eax
0x1800614b3  js      loc_180061575
0x1800614b9  mov     eax, dword ptr [rbp+plUbound]
0x1800614bc  sub     eax, [rbp+plLbound]
0x1800614bf  inc     eax
0x1800614c1  mov     [rbp+var_10], eax
0x1800614c4  lea     rdx, [rbp+ppvData]; ppvData
0x1800614c8  mov     rcx, [rbp+psa]; psa
0x1800614cc  call    cs:__imp_SafeArrayAccessData
0x1800614d2  mov     ebx, eax
0x1800614d4  test    eax, eax
0x1800614d6  js      loc_180061593
0x1800614dc  xor     r8d, r8d
0x1800614df  test    edi, edi
0x1800614e1  jz      short loc_1800614F7
0x1800614e3  mov     ecx, [r14+r8*4]
0x1800614e7  mov     rax, [rbp+ppvData]
0x1800614eb  mov     [rax+r8*4], ecx
0x1800614ef  inc     r8d
0x1800614f2  cmp     r8d, edi
0x1800614f5  jb      short loc_1800614E3
0x1800614f7  mov     rcx, [rbp+psa]; psa
0x1800614fb  test    rcx, rcx
0x1800614fe  jz      short loc_180061506
0x180061500  call    cs:__imp_SafeArrayUnaccessData
0x180061506  mov     rax, rsi
0x180061509  mov     rbx, [rsp+40h+arg_8]
0x18006150e  add     rsp, 40h
0x180061512  pop     r14
0x180061514  pop     r13
0x180061516  pop     rdi
0x180061517  pop     rsi
0x180061518  pop     rbp
0x180061519  retn
0x18006151a  lea     r8, aOnecoreWindows_120; "onecore\\windows\\accessibletech\\Commo"...
0x180061521  mov     edx, 132h; void *
0x180061526  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006152c  mov     r9d, 80070057h; char *
0x180061532  lea     r8, aOnecoreWindows_120; "onecore\\windows\\accessibletech\\Commo"...
0x180061539  mov     edx, 130h; void *
0x18006153e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061544  mov     edx, 6Fh ; 'o'; void *
0x180061549  mov     r9d, eax; char *
0x18006154c  mov     rcx, [rbp+28h]; this
0x180061550  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x180061557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006155c  mov     rcx, [rbp+28h]; this
0x180061560  mov     r9d, ebx; char *
0x180061563  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18006156a  mov     edx, 43h ; 'C'; void *
0x18006156f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061575  mov     edx, 70h ; 'p'
0x18006157a  jmp     short loc_180061549
0x18006157c  mov     r9d, 80070057h
0x180061582  mov     ebx, r9d
0x180061585  mov     edx, 5Ch ; '\'
0x18006158a  jmp     short loc_18006154C
0x18006158c  mov     edx, 5Fh ; '_'
0x180061591  jmp     short loc_180061549
0x180061593  mov     edx, 73h ; 's'
0x180061598  jmp     short loc_180061549
0x18006159a  cmp     [rbp+pvt], 16h
0x18006159f  jz      loc_180061471
0x1800615a5  mov     r9d, 80070057h
0x1800615ab  mov     ebx, r9d
0x1800615ae  mov     edx, 6Ah ; 'j'
0x1800615b3  jmp     short loc_18006154C
```
