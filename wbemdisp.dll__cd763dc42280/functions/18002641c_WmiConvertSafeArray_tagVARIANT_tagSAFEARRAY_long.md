# WmiConvertSafeArray(tagVARIANT &,tagSAFEARRAY *,long)

- ea: `0x18002641c`
- end: `0x1800265e8`
- name: `?WmiConvertSafeArray@@YAJAEAUtagVARIANT@@PEAUtagSAFEARRAY@@J@Z`
- size: `460`
- prototype: `int(struct tagVARIANT *, struct tagSAFEARRAY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800265f0`

## callees

- `0x180019114`
- `0x18002641c`
- `0x1800265f0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180026502`
- `OLEAUT32!__imp_VariantInit` at `0x18002652e`
- `OLEAUT32!__imp_VariantInit` at `0x180026502`
- `OLEAUT32!__imp_VariantInit` at `0x18002652e`
- `OLEAUT32!__imp_VariantClear` at `0x180026580`
- `OLEAUT32!__imp_VariantClear` at `0x18002658f`
- `OLEAUT32!__imp_VariantClear` at `0x180026580`
- `OLEAUT32!__imp_VariantClear` at `0x18002658f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800264c4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800264c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800265ae`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800265ae`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180026455`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180026455`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002648a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002648a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180026472`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180026472`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180026513`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180026513`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026570`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026570`

## pseudocode

```c
__int64 __fastcall WmiConvertSafeArray(struct tagVARIANT *a1, struct tagSAFEARRAY *a2, int a3)
{
  int v6; // esi
  VARTYPE v7; // ax
  ULONG v8; // r8d
  VARTYPE v9; // bx
  SAFEARRAY *v10; // r14
  bool v11; // di
  void *bstrVal; // r8
  LONG plLbound; // [rsp+20h] [rbp-40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pv; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+48h] BYREF
  LONG plUbound; // [rsp+B8h] [rbp+58h] BYREF

  plLbound = 0;
  plUbound = 0;
  v6 = -2147217407;
  if ( a2
    && SafeArrayGetDim(a2) == 1
    && SafeArrayGetLBound(a2, 1u, &plLbound) >= 0
    && SafeArrayGetUBound(a2, 1u, &plUbound) >= 0 )
  {
    v7 = 12;
    v8 = plUbound - plLbound + 1;
    if ( plUbound - plLbound != -1 )
      v7 = CimTypeToVtType(a3);
    rgsabound.cElements = v8;
    rgsabound.lLbound = 0;
    v9 = v7;
    v10 = SafeArrayCreate(v7, 1u, &rgsabound);
    if ( v10 )
    {
      v11 = 1;
      rgIndices = plLbound;
      if ( plLbound > plUbound )
      {
LABEL_21:
        a1->llVal = (LONGLONG)v10;
        a1->vt = v9 | 0x2000;
        return 0;
      }
      else
      {
        while ( v11 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          if ( SafeArrayGetElement(a2, &rgIndices, &pvarg) < 0 )
          {
            v11 = 0;
          }
          else
          {
            memset(&pv, 0, sizeof(pv));
            VariantInit(&pv);
            v6 = WmiVariantChangeType(&pv, &pvarg, a3);
            if ( v6 >= 0 )
            {
              if ( ((v9 - 8) & 0xFFFA) != 0 || (bstrVal = pv.bstrVal, v9 == 12) )
                bstrVal = &pv.decVal.8;
              v11 = SafeArrayPutElement(v10, &rgIndices, bstrVal) == 0;
            }
            VariantClear(&pv);
          }
          VariantClear(&pvarg);
          if ( ++rgIndices > plUbound )
          {
            if ( v11 )
              goto LABEL_21;
            break;
          }
        }
        SafeArrayDestroy(v10);
      }
    }
    else
    {
      return (unsigned int)-2147217402;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002641c  mov     [rsp-38h+arg_0], rbx
0x180026421  push    rbp
0x180026422  push    rsi
0x180026423  push    rdi
0x180026424  push    r12
0x180026426  push    r13
0x180026428  push    r14
0x18002642a  push    r15
0x18002642c  mov     rbp, rsp
0x18002642f  sub     rsp, 60h
0x180026433  xor     edi, edi
0x180026435  mov     r13d, r8d
0x180026438  mov     [rbp+plLbound], edi
0x18002643b  mov     r15, rdx
0x18002643e  mov     [rbp+plUbound], edi
0x180026441  mov     r12, rcx
0x180026444  mov     esi, 80041001h
0x180026449  test    rdx, rdx
0x18002644c  jz      loc_1800265CE
0x180026452  mov     rcx, rdx; psa
0x180026455  call    cs:__imp_SafeArrayGetDim
0x18002645b  lea     r14d, [rdi+1]
0x18002645f  cmp     eax, r14d
0x180026462  jnz     loc_1800265CE
0x180026468  lea     r8, [rbp+plLbound]; plLbound
0x18002646c  mov     edx, r14d; nDim
0x18002646f  mov     rcx, r15; psa
0x180026472  call    cs:__imp_SafeArrayGetLBound
0x180026478  test    eax, eax
0x18002647a  js      loc_1800265CE
0x180026480  lea     r8, [rbp+plUbound]; plUbound
0x180026484  mov     edx, r14d; nDim
0x180026487  mov     rcx, r15; psa
0x18002648a  call    cs:__imp_SafeArrayGetUBound
0x180026490  test    eax, eax
0x180026492  js      loc_1800265CE
0x180026498  mov     r8d, [rbp+plUbound]
0x18002649c  lea     eax, [rdi+0Ch]
0x18002649f  sub     r8d, [rbp+plLbound]
0x1800264a3  add     r8d, r14d
0x1800264a6  jz      short loc_1800264B0
0x1800264a8  mov     ecx, r13d; int
0x1800264ab  call    ?CimTypeToVtType@@YAGJ@Z; CimTypeToVtType(long)
0x1800264b0  mov     [rbp+rgsabound.cElements], r8d
0x1800264b4  mov     edx, r14d; cDims
0x1800264b7  lea     r8, [rbp+rgsabound]; rgsabound
0x1800264bb  mov     [rbp+rgsabound.lLbound], edi
0x1800264be  movzx   ecx, ax; vt
0x1800264c1  movzx   ebx, ax
0x1800264c4  call    cs:__imp_SafeArrayCreate
0x1800264ca  mov     r14, rax
0x1800264cd  test    rax, rax
0x1800264d0  jz      loc_1800265C9
0x1800264d6  mov     ecx, [rbp+plLbound]
0x1800264d9  mov     dil, 1
0x1800264dc  mov     [rbp+rgIndices], ecx
0x1800264df  cmp     ecx, [rbp+plUbound]
0x1800264e2  jg      loc_1800265B6
0x1800264e8  test    dil, dil
0x1800264eb  jz      loc_1800265AB
0x1800264f1  xorps   xmm0, xmm0
0x1800264f4  lea     rcx, [rbp+pvarg]; pvarg
0x1800264f8  xor     eax, eax
0x1800264fa  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800264fe  mov     qword ptr [rbp+pvarg+10h], rax
0x180026502  call    cs:__imp_VariantInit
0x180026508  lea     r8, [rbp+pvarg]; pv
0x18002650c  mov     rcx, r15; psa
0x18002650f  lea     rdx, [rbp+rgIndices]; rgIndices
0x180026513  call    cs:__imp_SafeArrayGetElement
0x180026519  test    eax, eax
0x18002651b  js      short loc_180026588
0x18002651d  xorps   xmm0, xmm0
0x180026520  lea     rcx, [rbp+pv]; pvarg
0x180026524  xor     eax, eax
0x180026526  movups  xmmword ptr [rbp+pv], xmm0
0x18002652a  mov     qword ptr [rbp+pv+10h], rax
0x18002652e  call    cs:__imp_VariantInit
0x180026534  mov     r8d, r13d; int
0x180026537  lea     rdx, [rbp+pvarg]; pvarSrc
0x18002653b  lea     rcx, [rbp+pv]; struct tagVARIANT *
0x18002653f  call    ?WmiVariantChangeType@@YAJAEAUtagVARIANT@@PEAU1@J@Z; WmiVariantChangeType(tagVARIANT &,tagVARIANT *,long)
0x180026544  mov     esi, eax
0x180026546  test    eax, eax
0x180026548  js      short loc_18002657C
0x18002654a  lea     ecx, [rbx-8]
0x18002654d  mov     eax, 0FFFAh
0x180026552  test    ax, cx
0x180026555  jnz     short loc_180026565
0x180026557  mov     r8, qword ptr [rbp+pv+8]
0x18002655b  mov     eax, 0Ch
0x180026560  cmp     bx, ax
0x180026563  jnz     short loc_180026569
0x180026565  lea     r8, [rbp+pv+8]; pv
0x180026569  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002656d  mov     rcx, r14; psa
0x180026570  call    cs:__imp_SafeArrayPutElement
0x180026576  test    eax, eax
0x180026578  setz    dil
0x18002657c  lea     rcx, [rbp+pv]; pvarg
0x180026580  call    cs:__imp_VariantClear
0x180026586  jmp     short loc_18002658B
0x180026588  xor     dil, dil
0x18002658b  lea     rcx, [rbp+pvarg]; pvarg
0x18002658f  call    cs:__imp_VariantClear
0x180026595  mov     eax, [rbp+rgIndices]
0x180026598  inc     eax
0x18002659a  mov     [rbp+rgIndices], eax
0x18002659d  cmp     eax, [rbp+plUbound]
0x1800265a0  jle     loc_1800264E8
0x1800265a6  test    dil, dil
0x1800265a9  jnz     short loc_1800265B6
0x1800265ab  mov     rcx, r14; psa
0x1800265ae  call    cs:__imp_SafeArrayDestroy
0x1800265b4  jmp     short loc_1800265CE
0x1800265b6  or      bx, 2000h
0x1800265bb  mov     [r12+8], r14
0x1800265c0  mov     [r12], bx
0x1800265c5  xor     esi, esi
0x1800265c7  jmp     short loc_1800265CE
0x1800265c9  mov     esi, 80041006h
0x1800265ce  mov     rbx, [rsp+60h+arg_0]
0x1800265d6  mov     eax, esi
0x1800265d8  add     rsp, 60h
0x1800265dc  pop     r15
0x1800265de  pop     r14
0x1800265e0  pop     r13
0x1800265e2  pop     r12
0x1800265e4  pop     rdi
0x1800265e5  pop     rsi
0x1800265e6  pop     rbp
0x1800265e7  retn
```
