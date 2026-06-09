# SafeArrayToArray<double>(tagSAFEARRAY *,double * *,int *,ushort)

- ea: `0x1800eb490`
- end: `0x1800eb66f`
- name: `??$SafeArrayToArray@N@@YAJPEAUtagSAFEARRAY@@PEAPEANPEAHG@Z`
- size: `479`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800239fc`
- `0x1800eb3f4`

## callees

- `0x18002f580`
- `0x1800eb490`
- `0x1801e88a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800eb4cb`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800eb4cb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800eb53b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800eb53b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800eb51e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800eb51e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800eb55e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800eb55e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb5be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb5f7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb5be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800eb5f7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800eb4e8`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800eb4e8`

## string_xrefs

- `0x1800eb5a6`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800eb614`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
__int64 __fastcall SafeArrayToArray<double>(SAFEARRAY *a1, _QWORD *a2, unsigned int *a3, VARTYPE a4)
{
  HRESULT Vartype; // eax
  unsigned int v7; // ebx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  unsigned int v12; // ecx
  __int64 i; // r9
  SAFEARRAY *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  LONG plUbound; // [rsp+20h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-24h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-20h]
  unsigned int v20; // [rsp+30h] [rbp-18h]
  void *ppvData; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  VARTYPE pvt; // [rsp+88h] [rbp+40h] BYREF

  pvt = a4;
  psa = 0;
  v20 = 0;
  ppvData = 0;
  if ( !a1 )
  {
    v16 = 2147942487LL;
    v15 = 87;
    v7 = -2147024809;
    goto LABEL_22;
  }
  psa = a1;
  if ( SafeArrayGetDim(a1) != 1 )
  {
    v16 = 2147942487LL;
    v15 = 92;
    v7 = -2147024809;
    goto LABEL_22;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v7 = Vartype;
  if ( Vartype < 0 )
  {
    v15 = 95;
    goto LABEL_21;
  }
  if ( pvt != 5 )
  {
    v16 = 2147942487LL;
    v15 = 106;
    v7 = -2147024809;
    goto LABEL_22;
  }
  plLbound = 0;
  plUbound = 0;
  Vartype = SafeArrayGetLBound(psa, 1u, &plLbound);
  v7 = Vartype;
  if ( Vartype < 0 )
  {
    v15 = 111;
    goto LABEL_21;
  }
  Vartype = SafeArrayGetUBound(psa, 1u, &plUbound);
  v7 = Vartype;
  if ( Vartype < 0 )
  {
    v15 = 112;
    goto LABEL_21;
  }
  v20 = plUbound - plLbound + 1;
  Vartype = SafeArrayAccessData(psa, &ppvData);
  v7 = Vartype;
  if ( Vartype < 0 )
  {
    v15 = 115;
LABEL_21:
    v16 = (unsigned int)Vartype;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v16,
      plUbound);
    v10 = 159;
    goto LABEL_12;
  }
  v8 = 8LL * v20;
  if ( !is_mul_ok(v20, 8u) )
    v8 = -1;
  v9 = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
  if ( !v9 )
  {
    v7 = -2147024882;
    v10 = 162;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v7,
      plUbound);
    if ( psa )
      SafeArrayUnaccessData(psa);
    return v7;
  }
  v12 = v20;
  for ( i = 0; (unsigned int)i < v20; v12 = v20 )
  {
    v9[i] = *((_QWORD *)ppvData + i);
    i = (unsigned int)(i + 1);
  }
  *a3 = v12;
  v14 = psa;
  *a2 = v9;
  if ( v14 )
    SafeArrayUnaccessData(v14);
  return 0;
}

```

## disassembly

```asm
0x1800eb490  mov     [rsp-20h+pvt], r9w
0x1800eb496  push    rbp
0x1800eb497  push    rbx
0x1800eb498  push    rsi
0x1800eb499  push    rdi
0x1800eb49a  mov     rbp, rsp
0x1800eb49d  sub     rsp, 48h
0x1800eb4a1  mov     [rbp+psa], 0
0x1800eb4a9  mov     rdi, r8
0x1800eb4ac  mov     [rbp+var_18], 0
0x1800eb4b3  mov     rsi, rdx
0x1800eb4b6  mov     [rbp+ppvData], 0
0x1800eb4be  test    rcx, rcx
0x1800eb4c1  jz      loc_1800EB62A
0x1800eb4c7  mov     [rbp+psa], rcx
0x1800eb4cb  call    cs:__imp_SafeArrayGetDim
0x1800eb4d1  cmp     eax, 1
0x1800eb4d4  jnz     loc_1800EB65F
0x1800eb4da  mov     rcx, [rbp+psa]; psa
0x1800eb4de  lea     rdx, [rbp+pvt]; pvt
0x1800eb4e2  xor     eax, eax
0x1800eb4e4  mov     [rbp+pvt], ax
0x1800eb4e8  call    cs:__imp_SafeArrayGetVartype
0x1800eb4ee  mov     ebx, eax
0x1800eb4f0  test    eax, eax
0x1800eb4f2  js      loc_1800EB641
0x1800eb4f8  cmp     [rbp+pvt], 5
0x1800eb4fd  jnz     loc_1800EB648
0x1800eb503  mov     rcx, [rbp+psa]; psa
0x1800eb507  lea     r8, [rbp+plLbound]; plLbound
0x1800eb50b  mov     edx, 1; nDim
0x1800eb510  mov     [rbp+plLbound], 0
0x1800eb517  mov     [rbp+plUbound], 0
0x1800eb51e  call    cs:__imp_SafeArrayGetLBound
0x1800eb524  mov     ebx, eax
0x1800eb526  test    eax, eax
0x1800eb528  js      loc_1800EB63A
0x1800eb52e  mov     rcx, [rbp+psa]; psa
0x1800eb532  lea     r8, [rbp+plUbound]; plUbound
0x1800eb536  mov     edx, 1; nDim
0x1800eb53b  call    cs:__imp_SafeArrayGetUBound
0x1800eb541  mov     ebx, eax
0x1800eb543  test    eax, eax
0x1800eb545  js      loc_1800EB658
0x1800eb54b  mov     eax, [rbp+plUbound]
0x1800eb54e  lea     rdx, [rbp+ppvData]; ppvData
0x1800eb552  sub     eax, [rbp+plLbound]
0x1800eb555  mov     rcx, [rbp+psa]; psa
0x1800eb559  inc     eax
0x1800eb55b  mov     [rbp+var_18], eax
0x1800eb55e  call    cs:__imp_SafeArrayAccessData
0x1800eb564  mov     ebx, eax
0x1800eb566  test    eax, eax
0x1800eb568  js      loc_1800EB608
0x1800eb56e  mov     ecx, [rbp+var_18]
0x1800eb571  mov     eax, 8
0x1800eb576  mul     rcx
0x1800eb579  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800eb580  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eb587  cmovb   rax, rcx
0x1800eb58b  mov     rcx, rax; unsigned __int64
0x1800eb58e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800eb593  test    rax, rax
0x1800eb596  jnz     short loc_1800EB5C8
0x1800eb598  mov     ebx, 8007000Eh
0x1800eb59d  mov     edx, 0A2h; void *
0x1800eb5a2  mov     rcx, [rbp+20h]; this
0x1800eb5a6  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800eb5ad  mov     r9d, ebx; char *
0x1800eb5b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb5b5  mov     rcx, [rbp+psa]; psa
0x1800eb5b9  test    rcx, rcx
0x1800eb5bc  jz      short loc_1800EB5C4
0x1800eb5be  call    cs:__imp_SafeArrayUnaccessData
0x1800eb5c4  mov     eax, ebx
0x1800eb5c6  jmp     short loc_1800EB5FF
0x1800eb5c8  mov     ecx, [rbp+var_18]
0x1800eb5cb  xor     r9d, r9d
0x1800eb5ce  test    ecx, ecx
0x1800eb5d0  jz      short loc_1800EB5E9
0x1800eb5d2  mov     rcx, [rbp+ppvData]
0x1800eb5d6  mov     rdx, [rcx+r9*8]
0x1800eb5da  mov     [rax+r9*8], rdx
0x1800eb5de  inc     r9d
0x1800eb5e1  mov     ecx, [rbp+var_18]
0x1800eb5e4  cmp     r9d, ecx
0x1800eb5e7  jb      short loc_1800EB5D2
0x1800eb5e9  mov     [rdi], ecx
0x1800eb5eb  mov     rcx, [rbp+psa]; psa
0x1800eb5ef  mov     [rsi], rax
0x1800eb5f2  test    rcx, rcx
0x1800eb5f5  jz      short loc_1800EB5FD
0x1800eb5f7  call    cs:__imp_SafeArrayUnaccessData
0x1800eb5fd  xor     eax, eax
0x1800eb5ff  add     rsp, 48h
0x1800eb603  pop     rdi
0x1800eb604  pop     rsi
0x1800eb605  pop     rbx
0x1800eb606  pop     rbp
0x1800eb607  retn
0x1800eb608  mov     edx, 73h ; 's'; void *
0x1800eb60d  mov     r9d, eax; char *
0x1800eb610  mov     rcx, [rbp+20h]; this
0x1800eb614  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800eb61b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb620  mov     edx, 9Fh
0x1800eb625  jmp     loc_1800EB5A2
0x1800eb62a  mov     r9d, 80070057h
0x1800eb630  mov     edx, 57h ; 'W'
0x1800eb635  mov     ebx, r9d
0x1800eb638  jmp     short loc_1800EB610
0x1800eb63a  mov     edx, 6Fh ; 'o'
0x1800eb63f  jmp     short loc_1800EB60D
0x1800eb641  mov     edx, 5Fh ; '_'
0x1800eb646  jmp     short loc_1800EB60D
0x1800eb648  mov     r9d, 80070057h
0x1800eb64e  mov     edx, 6Ah ; 'j'
0x1800eb653  mov     ebx, r9d
0x1800eb656  jmp     short loc_1800EB610
0x1800eb658  mov     edx, 70h ; 'p'
0x1800eb65d  jmp     short loc_1800EB60D
0x1800eb65f  mov     r9d, 80070057h
0x1800eb665  mov     edx, 5Ch ; '\'
0x1800eb66a  mov     ebx, r9d
0x1800eb66d  jmp     short loc_1800EB610
```
