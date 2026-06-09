# WbemVariantChangeType(tagVARIANT *,tagVARIANT *,ushort)

- ea: `0x1800073e0`
- end: `0x18000775d`
- name: `?WbemVariantChangeType@@YAJPEAUtagVARIANT@@0G@Z`
- size: `893`
- prototype: `int(struct tagVARIANT *, struct tagVARIANT *, unsigned __int16)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ff0`
- `0x180005a80`
- `0x180007300`

## callees

- `0x1800073e0`
- `0x180013564`
- `0x180014120`
- `0x18002cba0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180007566`
- `OLEAUT32!__imp_VariantClear` at `0x180007589`
- `OLEAUT32!__imp_VariantClear` at `0x1800075fd`
- `OLEAUT32!__imp_VariantClear` at `0x180007701`
- `OLEAUT32!__imp_VariantClear` at `0x180007566`
- `OLEAUT32!__imp_VariantClear` at `0x180007589`
- `OLEAUT32!__imp_VariantClear` at `0x1800075fd`
- `OLEAUT32!__imp_VariantClear` at `0x180007701`
- `OLEAUT32!__imp_VariantCopy` at `0x180007576`
- `OLEAUT32!__imp_VariantCopy` at `0x180007576`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007423`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007530`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007423`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007530`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800074b9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800074b9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007607`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007607`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180007480`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180007480`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000745f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000745f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800074fa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800074fa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007556`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007556`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall WbemVariantChangeType(struct tagVARIANT *a1, struct tagVARIANT *a2, VARTYPE a3)
{
  SAFEARRAY *parray; // r12
  HRESULT LBound; // eax
  unsigned int v9; // edi
  HRESULT UBound; // eax
  SAFEARRAY *v11; // rax
  SAFEARRAY *v12; // r14
  int i; // eax
  HRESULT Element; // eax
  HRESULT v15; // eax
  void *bstrVal; // r8
  HRESULT v17; // eax
  _QWORD *v18; // r10
  __int64 v19; // rdx
  LONG plLbound; // [rsp+20h] [rbp-40h] BYREF
  LONG plUbound; // [rsp+24h] [rbp-3Ch] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-38h] BYREF
  SAFEARRAY *v23; // [rsp+30h] [rbp-30h] BYREF
  char v24; // [rsp+38h] [rbp-28h]
  VARIANTARG pv; // [rsp+40h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+48h] BYREF
  VARIANTARG *p_pv; // [rsp+B8h] [rbp+58h]

  if ( a2->vt == 1 )
    return VariantCopy(a1, a2);
  if ( (a3 & 0x2000) == 0 )
    return VariantChangeType(a1, a2, 1u, a3);
  if ( (a2->vt & 0x2000) == 0 )
    return -2147352571;
  parray = a2->parray;
  plLbound = 0;
  LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
  v9 = LBound;
  if ( LBound < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, LBound);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v19 = 37;
LABEL_29:
    WPP_SF_D(v18[2], v19, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v9);
    return v9;
  }
  plUbound = 0;
  UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
  v9 = UBound;
  if ( UBound < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, UBound);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v19 = 38;
    goto LABEL_29;
  }
  rgsabound.cElements = plUbound - plLbound + 1;
  rgsabound.lLbound = plLbound;
  v11 = SafeArrayCreate(a3 & 0xDFFF, 1u, &rgsabound);
  v12 = v11;
  if ( !v11 )
    return -2147217402;
  v23 = v11;
  v24 = 0;
  for ( i = plLbound; ; i = rgIndices + 1 )
  {
    rgIndices = i;
    if ( i > plUbound )
    {
      if ( a1 == a2 )
        VariantClear(a2);
      a1->vt = a3;
      a1->llVal = (LONGLONG)v12;
      v24 = 1;
      return 0;
    }
    memset(&pv, 0, sizeof(pv));
    Element = SafeArrayGetElement(parray, &rgIndices, &pv.decVal.8);
    v9 = Element;
    if ( Element < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, Element);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v9);
      }
      goto LABEL_46;
    }
    pv.vt = a2->vt & 0xDFFF;
    p_pv = &pv;
    v15 = VariantChangeType(&pv, &pv, 0, a3 & 0xDFFF);
    v9 = v15;
    if ( v15 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v15);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v9);
      }
      VariantClear(&pv);
LABEL_46:
      OnDeleteIf<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *)>::~OnDeleteIf<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *)>((__int64)&v23);
      return v9;
    }
    bstrVal = pv.bstrVal;
    if ( pv.vt != 8 )
      bstrVal = &pv.decVal.8;
    v17 = SafeArrayPutElement(v12, &rgIndices, bstrVal);
    v9 = v17;
    if ( v17 < 0 )
      break;
    VariantClear(&pv);
  }
  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v17);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v9);
  }
  VariantClear(&pv);
  SafeArrayDestroy(v12);
  return v9;
}

```

## disassembly

```asm
0x1800073e0  mov     [rsp-38h+arg_0], rbx
0x1800073e5  push    rbp
0x1800073e6  push    rsi
0x1800073e7  push    rdi
0x1800073e8  push    r12
0x1800073ea  push    r13
0x1800073ec  push    r14
0x1800073ee  push    r15
0x1800073f0  mov     rbp, rsp
0x1800073f3  sub     rsp, 60h
0x1800073f7  movzx   r15d, r8w
0x1800073fb  mov     rbx, rdx
0x1800073fe  mov     rsi, rcx
0x180007401  mov     r14d, 1
0x180007407  cmp     [rdx], r14w
0x18000740b  jz      loc_180007576
0x180007411  mov     eax, 2000h
0x180007416  test    ax, r8w
0x18000741a  jnz     short loc_180007441
0x18000741c  mov     r8d, r14d; wFlags
0x18000741f  movzx   r9d, r15w; vt
0x180007423  call    cs:__imp_VariantChangeType
0x180007429  mov     rbx, [rsp+60h+arg_0]
0x180007431  add     rsp, 60h
0x180007435  pop     r15
0x180007437  pop     r14
0x180007439  pop     r13
0x18000743b  pop     r12
0x18000743d  pop     rdi
0x18000743e  pop     rsi
0x18000743f  pop     rbp
0x180007440  retn
0x180007441  test    [rdx], ax
0x180007444  jz      loc_18000760F
0x18000744a  mov     r12, [rdx+8]
0x18000744e  mov     [rbp+plLbound], 0
0x180007455  lea     r8, [rbp+plLbound]; plLbound
0x180007459  mov     edx, r14d; nDim
0x18000745c  mov     rcx, r12; psa
0x18000745f  call    cs:__imp_SafeArrayGetLBound
0x180007465  mov     edi, eax
0x180007467  test    eax, eax
0x180007469  js      loc_1800075A2
0x18000746f  mov     [rbp+plUbound], 0
0x180007476  lea     r8, [rbp+plUbound]; plUbound
0x18000747a  mov     edx, r14d; nDim
0x18000747d  mov     rcx, r12; psa
0x180007480  call    cs:__imp_SafeArrayGetUBound
0x180007486  mov     edi, eax
0x180007488  test    eax, eax
0x18000748a  js      loc_18000764A
0x180007490  mov     ecx, [rbp+plUbound]
0x180007493  mov     eax, [rbp+plLbound]
0x180007496  sub     ecx, eax
0x180007498  add     ecx, r14d
0x18000749b  mov     [rbp+rgsabound.cElements], ecx
0x18000749e  mov     [rbp+rgsabound.lLbound], eax
0x1800074a1  mov     eax, 0DFFFh
0x1800074a6  movzx   r13d, r15w
0x1800074aa  and     r13w, ax
0x1800074ae  lea     r8, [rbp+rgsabound]; rgsabound
0x1800074b2  mov     edx, r14d; cDims
0x1800074b5  movzx   ecx, r13w; vt
0x1800074b9  call    cs:__imp_SafeArrayCreate
0x1800074bf  mov     r14, rax
0x1800074c2  test    rax, rax
0x1800074c5  jz      loc_1800075CA
0x1800074cb  mov     [rbp+var_30], rax
0x1800074cf  mov     [rbp+var_28], 0
0x1800074d3  mov     eax, [rbp+plLbound]
0x1800074d6  mov     [rbp+rgIndices], eax
0x1800074d9  cmp     eax, [rbp+plUbound]
0x1800074dc  jg      loc_180007581
0x1800074e2  xorps   xmm0, xmm0
0x1800074e5  xor     eax, eax
0x1800074e7  movups  [rbp+pv], xmm0
0x1800074eb  mov     [rbp+var_10], rax
0x1800074ef  lea     r8, [rbp+pv+8]; pv
0x1800074f3  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800074f7  mov     rcx, r12; psa
0x1800074fa  call    cs:__imp_SafeArrayGetElement
0x180007500  mov     edi, eax
0x180007502  test    eax, eax
0x180007504  js      loc_180007709
0x18000750a  movzx   eax, word ptr [rbx]
0x18000750d  mov     ecx, 0DFFFh
0x180007512  and     ax, cx
0x180007515  mov     word ptr [rbp+pv], ax
0x180007519  lea     rax, [rbp+pv]
0x18000751d  mov     [rbp+arg_18], rax
0x180007521  xor     r8d, r8d; wFlags
0x180007524  movzx   r9d, r13w; vt
0x180007528  lea     rdx, [rbp+pv]; pvarSrc
0x18000752c  lea     rcx, [rbp+pv]; pvargDest
0x180007530  call    cs:__imp_VariantChangeType
0x180007536  mov     edi, eax
0x180007538  test    eax, eax
0x18000753a  js      loc_1800076B7
0x180007540  lea     rdx, [rbp+rgIndices]; rgIndices
0x180007544  mov     rcx, r14; psa
0x180007547  cmp     word ptr [rbp+pv], 8
0x18000754c  mov     r8, qword ptr [rbp+pv+8]
0x180007550  jz      short loc_180007556
0x180007552  lea     r8, [rbp+pv+8]; pv
0x180007556  call    cs:__imp_SafeArrayPutElement
0x18000755c  mov     edi, eax
0x18000755e  test    eax, eax
0x180007560  js      short loc_1800075D4
0x180007562  lea     rcx, [rbp+pv]; pvarg
0x180007566  call    cs:__imp_VariantClear
0x18000756c  mov     eax, [rbp+rgIndices]
0x18000756f  inc     eax
0x180007571  jmp     loc_1800074D6
0x180007576  call    cs:__imp_VariantCopy
0x18000757c  jmp     loc_180007429
0x180007581  cmp     rsi, rbx
0x180007584  jnz     short loc_18000758F
0x180007586  mov     rcx, rbx; pvarg
0x180007589  call    cs:__imp_VariantClear
0x18000758f  mov     [rsi], r15w
0x180007593  mov     [rsi+8], r14
0x180007597  mov     [rbp+var_28], 1
0x18000759b  xor     eax, eax
0x18000759d  jmp     loc_180007429
0x1800075a2  mov     edx, edi; int
0x1800075a4  lea     rcx, qword_18006A9C0; this
0x1800075ab  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800075b0  lea     rcx, WPP_GLOBAL_Control
0x1800075b7  mov     r10, cs:WPP_GLOBAL_Control
0x1800075be  cmp     r10, rcx
0x1800075c1  jnz     short loc_180007619
0x1800075c3  mov     eax, edi
0x1800075c5  jmp     loc_180007429
0x1800075ca  mov     eax, 80041006h
0x1800075cf  jmp     loc_180007429
0x1800075d4  mov     edx, edi; int
0x1800075d6  lea     rcx, qword_18006A9C0; this
0x1800075dd  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800075e2  lea     rcx, WPP_GLOBAL_Control
0x1800075e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800075f0  cmp     rax, rcx
0x1800075f3  jnz     loc_180007686
0x1800075f9  lea     rcx, [rbp+pv]; pvarg
0x1800075fd  call    cs:__imp_VariantClear
0x180007603  nop
0x180007604  mov     rcx, r14; psa
0x180007607  call    cs:__imp_SafeArrayDestroy
0x18000760d  jmp     short loc_1800075C3
0x18000760f  mov     eax, 80020005h
0x180007614  jmp     loc_180007429
0x180007619  test    [r10+1Ch], r14b
0x18000761d  jz      short loc_1800075C3
0x18000761f  cmp     byte ptr [r10+19h], 2
0x180007624  jb      short loc_1800075C3
0x180007626  mov     edx, 25h ; '%'
0x18000762b  jmp     short loc_180007632
0x18000762d  mov     edx, 26h ; '&'
0x180007632  mov     r9d, edi
0x180007635  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x18000763c  mov     rcx, [r10+10h]
0x180007640  call    WPP_SF_D
0x180007645  jmp     loc_1800075C3
0x18000764a  mov     edx, edi; int
0x18000764c  lea     rcx, qword_18006A9C0; this
0x180007653  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007658  lea     rcx, WPP_GLOBAL_Control
0x18000765f  mov     r10, cs:WPP_GLOBAL_Control
0x180007666  cmp     r10, rcx
0x180007669  jz      loc_1800075C3
0x18000766f  test    [r10+1Ch], r14b
0x180007673  jz      loc_1800075C3
0x180007679  cmp     byte ptr [r10+19h], 2
0x18000767e  jb      loc_1800075C3
0x180007684  jmp     short loc_18000762D
0x180007686  test    byte ptr [rax+1Ch], 1
0x18000768a  jz      loc_1800075F9
0x180007690  cmp     byte ptr [rax+19h], 2
0x180007694  jb      loc_1800075F9
0x18000769a  mov     edx, 29h ; ')'
0x18000769f  mov     r9d, edi
0x1800076a2  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x1800076a9  mov     rcx, [rax+10h]
0x1800076ad  call    WPP_SF_D
0x1800076b2  jmp     loc_1800075F9
0x1800076b7  mov     edx, edi; int
0x1800076b9  lea     rcx, qword_18006A9C0; this
0x1800076c0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800076c5  lea     rcx, WPP_GLOBAL_Control
0x1800076cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800076d3  cmp     rax, rcx
0x1800076d6  jz      short loc_1800076FD
0x1800076d8  test    byte ptr [rax+1Ch], 1
0x1800076dc  jz      short loc_1800076FD
0x1800076de  cmp     byte ptr [rax+19h], 2
0x1800076e2  jb      short loc_1800076FD
0x1800076e4  mov     edx, 28h ; '('
0x1800076e9  mov     r9d, edi
0x1800076ec  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x1800076f3  mov     rcx, [rax+10h]
0x1800076f7  call    WPP_SF_D
0x1800076fc  nop
0x1800076fd  lea     rcx, [rbp+pv]; pvarg
0x180007701  call    cs:__imp_VariantClear
0x180007707  jmp     short loc_18000774F
0x180007709  mov     edx, edi; int
0x18000770b  lea     rcx, qword_18006A9C0; this
0x180007712  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180007717  lea     rcx, WPP_GLOBAL_Control
0x18000771e  mov     rax, cs:WPP_GLOBAL_Control
0x180007725  cmp     rax, rcx
0x180007728  jz      short loc_18000774F
0x18000772a  test    byte ptr [rax+1Ch], 1
0x18000772e  jz      short loc_18000774F
0x180007730  cmp     byte ptr [rax+19h], 2
0x180007734  jb      short loc_18000774F
0x180007736  mov     edx, 27h ; '''
0x18000773b  mov     r9d, edi
0x18000773e  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180007745  mov     rcx, [rax+10h]
0x180007749  call    WPP_SF_D
0x18000774e  nop
0x18000774f  lea     rcx, [rbp+var_30]
0x180007753  call    ??1?$OnDeleteIf@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@Z@@QEAA@XZ; OnDeleteIf<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *)>::~OnDeleteIf<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *)>(void)
0x180007758  jmp     loc_1800075C3
```
