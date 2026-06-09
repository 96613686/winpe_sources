# CWshCollection::Item(tagVARIANT *,tagVARIANT *)

- ea: `0x180007390`
- end: `0x18000750f`
- name: `?Item@CWshCollection@@UEAAJPEAUtagVARIANT@@0@Z`
- size: `383`
- prototype: `int(CWshCollection *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005938`
- `0x180007390`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007469`
- `msvcrt!_wcsicmp` at `0x180007469`
- `OLEAUT32!__imp_VariantInit` at `0x1800073c3`
- `OLEAUT32!__imp_VariantInit` at `0x1800073c3`
- `OLEAUT32!__imp_VariantClear` at `0x180007477`
- `OLEAUT32!__imp_VariantClear` at `0x180007484`
- `OLEAUT32!__imp_VariantClear` at `0x1800074e6`
- `OLEAUT32!__imp_VariantClear` at `0x180007477`
- `OLEAUT32!__imp_VariantClear` at `0x180007484`
- `OLEAUT32!__imp_VariantClear` at `0x1800074e6`
- `OLEAUT32!__imp_VariantCopy` at `0x1800074a2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800074a2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000741d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000741d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180007403`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180007403`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180007453`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800074d3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180007453`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800074d3`

## pseudocode

```c
int __fastcall CWshCollection::Item(const VARIANTARG *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  SAFEARRAY *parray; // rcx
  int result; // eax
  int v8; // eax
  LONG v9; // ecx
  LONG v10; // eax
  SAFEARRAY *v11; // rcx
  LONG plLbound; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pv; // [rsp+28h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+68h] [rbp+28h] BYREF
  LONG plUbound; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 || !a3 )
    return -2147467261;
  VariantInit(a3);
  parray = this[3].parray;
  rgIndices = 0;
  if ( parray && a2->vt == 8 )
  {
    plLbound = 0;
    plUbound = 0;
    result = SafeArrayGetLBound(parray, 1u, &plLbound);
    if ( result < 0 )
      return result;
    result = SafeArrayGetUBound(this[3].parray, 1u, &plUbound);
    if ( result < 0 )
      return result;
    v8 = plLbound;
    memset(&pv, 0, sizeof(pv));
    while ( 1 )
    {
      v9 = plUbound;
      rgIndices = v8;
      if ( v8 > plUbound )
        break;
      result = SafeArrayGetElement(this[3].parray, &rgIndices, &pv);
      if ( result < 0 )
        return result;
      if ( !_wcsicmp(a2->bstrVal, pv.bstrVal) )
      {
        VariantClear(&pv);
        v8 = rgIndices;
        v9 = plUbound;
        break;
      }
      VariantClear(&pv);
      v8 = rgIndices + 1;
    }
    if ( v8 > v9 )
    {
      result = *((_DWORD *)&this[3].decVal + 4);
      if ( result >= 0 )
        return VariantCopy(a3, this + 4);
      return result;
    }
    v10 = v8 - plLbound;
  }
  else
  {
    plUbound = 0;
    Variant_I4(a2, (unsigned int *)&plUbound);
    v10 = plUbound;
  }
  v11 = *(SAFEARRAY **)&this[3].vt;
  rgIndices = v10;
  result = SafeArrayGetElement(v11, &rgIndices, a3);
  if ( result >= 0 )
  {
    if ( a3->vt == 8 )
    {
      return 0;
    }
    else
    {
      VariantClear(a3);
      return -2147418113;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007390  mov     [rsp-18h+arg_0], rbx
0x180007395  mov     [rsp-18h+arg_10], rsi
0x18000739a  push    rbp
0x18000739b  push    rdi
0x18000739c  push    r15
0x18000739e  mov     rbp, rsp
0x1800073a1  sub     rsp, 40h
0x1800073a5  mov     rbx, r8
0x1800073a8  mov     rsi, rdx
0x1800073ab  mov     rdi, rcx
0x1800073ae  test    rdx, rdx
0x1800073b1  jz      loc_1800074F7
0x1800073b7  test    rbx, rbx
0x1800073ba  jz      loc_1800074F7
0x1800073c0  mov     rcx, rbx; pvarg
0x1800073c3  call    cs:__imp_VariantInit
0x1800073c9  mov     rcx, [rdi+50h]; psa
0x1800073cd  mov     r15d, 8
0x1800073d3  mov     [rbp+rgIndices], 0
0x1800073da  test    rcx, rcx
0x1800073dd  jz      loc_1800074AF
0x1800073e3  cmp     r15w, [rsi]
0x1800073e7  jnz     loc_1800074AF
0x1800073ed  lea     r8, [rbp+plLbound]; plLbound
0x1800073f1  mov     [rbp+plLbound], 0
0x1800073f8  lea     edx, [r15-7]; nDim
0x1800073fc  mov     [rbp+plUbound], 0
0x180007403  call    cs:__imp_SafeArrayGetLBound
0x180007409  test    eax, eax
0x18000740b  js      loc_1800074FC
0x180007411  mov     rcx, [rdi+50h]; psa
0x180007415  lea     r8, [rbp+plUbound]; plUbound
0x180007419  lea     edx, [r15-7]; nDim
0x18000741d  call    cs:__imp_SafeArrayGetUBound
0x180007423  test    eax, eax
0x180007425  js      loc_1800074FC
0x18000742b  xor     eax, eax
0x18000742d  xorps   xmm0, xmm0
0x180007430  mov     [rbp+var_8], rax
0x180007434  mov     eax, [rbp+plLbound]
0x180007437  movups  [rbp+pv], xmm0
0x18000743b  mov     ecx, [rbp+plUbound]
0x18000743e  mov     edx, eax
0x180007440  mov     [rbp+rgIndices], eax
0x180007443  cmp     eax, ecx
0x180007445  jg      short loc_180007490
0x180007447  mov     rcx, [rdi+50h]; psa
0x18000744b  lea     r8, [rbp+pv]; pv
0x18000744f  lea     rdx, [rbp+rgIndices]; rgIndices
0x180007453  call    cs:__imp_SafeArrayGetElement
0x180007459  test    eax, eax
0x18000745b  js      loc_1800074FC
0x180007461  mov     rdx, qword ptr [rbp+pv+8]; String2
0x180007465  mov     rcx, [rsi+8]; String1
0x180007469  call    cs:__imp__wcsicmp
0x18000746f  lea     rcx, [rbp+pv]; pvarg
0x180007473  test    eax, eax
0x180007475  jz      short loc_180007484
0x180007477  call    cs:__imp_VariantClear
0x18000747d  mov     eax, [rbp+rgIndices]
0x180007480  inc     eax
0x180007482  jmp     short loc_18000743B
0x180007484  call    cs:__imp_VariantClear
0x18000748a  mov     eax, [rbp+rgIndices]
0x18000748d  mov     ecx, [rbp+plUbound]
0x180007490  cmp     eax, ecx
0x180007492  jle     short loc_1800074AA
0x180007494  mov     eax, [rdi+58h]
0x180007497  test    eax, eax
0x180007499  js      short loc_1800074FC
0x18000749b  lea     rdx, [rdi+60h]; pvargSrc
0x18000749f  mov     rcx, rbx; pvargDest
0x1800074a2  call    cs:__imp_VariantCopy
0x1800074a8  jmp     short loc_1800074FC
0x1800074aa  sub     eax, [rbp+plLbound]
0x1800074ad  jmp     short loc_1800074C5
0x1800074af  lea     rdx, [rbp+plUbound]; unsigned int *
0x1800074b3  mov     [rbp+plUbound], 0
0x1800074ba  mov     rcx, rsi; pvarSrc
0x1800074bd  call    ?Variant_I4@@YAJPEAUtagVARIANT@@PEAK@Z; Variant_I4(tagVARIANT *,ulong *)
0x1800074c2  mov     eax, [rbp+plUbound]
0x1800074c5  mov     rcx, [rdi+48h]; psa
0x1800074c9  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800074cd  mov     r8, rbx; pv
0x1800074d0  mov     [rbp+rgIndices], eax
0x1800074d3  call    cs:__imp_SafeArrayGetElement
0x1800074d9  test    eax, eax
0x1800074db  js      short loc_1800074FC
0x1800074dd  cmp     r15w, [rbx]
0x1800074e1  jz      short loc_1800074F3
0x1800074e3  mov     rcx, rbx; pvarg
0x1800074e6  call    cs:__imp_VariantClear
0x1800074ec  mov     eax, 8000FFFFh
0x1800074f1  jmp     short loc_1800074FC
0x1800074f3  xor     eax, eax
0x1800074f5  jmp     short loc_1800074FC
0x1800074f7  mov     eax, 80004003h
0x1800074fc  mov     rbx, [rsp+40h+arg_0]
0x180007501  mov     rsi, [rsp+40h+arg_10]
0x180007506  add     rsp, 40h
0x18000750a  pop     r15
0x18000750c  pop     rdi
0x18000750d  pop     rbp
0x18000750e  retn
```
