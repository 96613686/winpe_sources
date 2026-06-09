# ConvertArray(tagVARIANT *,tagVARIANT *,int,ushort)

- ea: `0x180025074`
- end: `0x18002540e`
- name: `?ConvertArray@@YAJPEAUtagVARIANT@@0HG@Z`
- size: `922`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct tagVARIANT *, int, unsigned __int16)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002df8`
- `0x180020de0`
- `0x180020ff0`
- `0x180023590`
- `0x180025c74`

## callees

- `0x180025074`
- `0x180025aa4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800251c8`
- `OLEAUT32!__imp_VariantInit` at `0x1800252fd`
- `OLEAUT32!__imp_VariantInit` at `0x180025335`
- `OLEAUT32!__imp_VariantInit` at `0x1800251c8`
- `OLEAUT32!__imp_VariantInit` at `0x1800252fd`
- `OLEAUT32!__imp_VariantInit` at `0x180025335`
- `OLEAUT32!__imp_VariantClear` at `0x1800251f2`
- `OLEAUT32!__imp_VariantClear` at `0x18002538d`
- `OLEAUT32!__imp_VariantClear` at `0x1800253c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800251f2`
- `OLEAUT32!__imp_VariantClear` at `0x18002538d`
- `OLEAUT32!__imp_VariantClear` at `0x1800253c0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800252c5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800252c5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800253d3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800253d3`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002510c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002510c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025150`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025150`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025139`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025139`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800251d9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002530e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800251d9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002530e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025380`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800253b3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025380`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800253b3`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180025356`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180025356`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18002533b`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18002533b`

## pseudocode

```c
HRESULT __fastcall ConvertArray(struct tagVARIANT *a1, struct tagVARIANT *a2, int a3, __int16 a4)
{
  unsigned __int16 vt; // di
  __int16 v5; // bx
  SAFEARRAY **pparray; // rax
  SAFEARRAY *parray; // r15
  HRESULT result; // eax
  HRESULT v10; // r14d
  LONG v11; // ecx
  LONG v12; // edx
  ULONG v13; // r12d
  VARTYPE v14; // bx
  __int16 v15; // ax
  SAFEARRAY *v16; // rsi
  LONG i; // eax
  HRESULT Element; // ebx
  LANGID SystemDefaultLangID; // ax
  void *v20; // r8
  void *bstrVal; // r8
  LONG rgIndices[2]; // [rsp+30h] [rbp-40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pv; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  LONG plUbound; // [rsp+B8h] [rbp+48h] BYREF
  LONG plLbound; // [rsp+C8h] [rbp+58h] BYREF

  vt = a4;
  v5 = 9;
  if ( a4 != 13 )
    v5 = a4;
  if ( !v5 )
    v5 = 1;
  if ( !a2 || !a1 || (a2->vt & 0xC) == 0 || (a2->vt & 0x2000) == 0 )
    return -2147217407;
  if ( (a2->vt & 0x4000) != 0 )
  {
    pparray = a2->pparray;
    if ( !pparray )
      return -2147217407;
    parray = *pparray;
  }
  else
  {
    parray = a2->parray;
  }
  if ( !parray || SafeArrayGetDim(parray) != 1 )
    return -2147217407;
  *(_QWORD *)rgIndices = 0;
  plLbound = 0;
  plUbound = 0;
  result = SafeArrayGetLBound(parray, 1u, &plLbound);
  if ( result )
    return result;
  result = SafeArrayGetUBound(parray, 1u, &plUbound);
  v10 = result;
  if ( result )
    return result;
  v11 = plUbound;
  v12 = plLbound;
  v13 = plUbound - plLbound + 1;
  if ( plUbound - plLbound != -1 )
  {
    if ( v5 != 1 )
    {
      vt = v5;
      goto LABEL_49;
    }
    while ( 1 )
    {
      rgIndices[0] = v12;
      if ( v12 > v11 )
      {
        if ( a3 )
          vt = GetAcceptableQualType(vt);
        goto LABEL_49;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      result = SafeArrayGetElement(parray, rgIndices, &pvarg);
      v10 = result;
      if ( result )
        return result;
      v14 = pvarg.vt;
      VariantClear(&pvarg);
      if ( rgIndices[0] == plLbound )
        goto LABEL_27;
      if ( vt != v14 )
      {
        switch ( vt )
        {
          case 2u:
            if ( v14 != 17 )
            {
              if ( v14 != 3 )
                return -2147217400;
              vt = 3;
            }
            break;
          case 3u:
            if ( v14 == 2 )
              break;
            v15 = 17;
            goto LABEL_37;
          case 4u:
            if ( v14 != 5 )
              return -2147217400;
            vt = 5;
            break;
          case 5u:
            v15 = 4;
LABEL_37:
            if ( v15 != v14 )
              return -2147217400;
            break;
          default:
            if ( vt != 17 || (unsigned __int16)(v14 - 2) > 1u )
              return -2147217400;
LABEL_27:
            vt = v14;
            break;
        }
      }
      v11 = plUbound;
      v12 = rgIndices[0] + 1;
    }
  }
  if ( a3 )
  {
    if ( v5 == 1 )
      vt = 3;
    else
      vt = v5;
  }
  else
  {
    vt = 12;
  }
LABEL_49:
  rgsabound.lLbound = 0;
  rgsabound.cElements = v13;
  v16 = SafeArrayCreate(vt, 1u, &rgsabound);
  for ( i = plLbound; ; i = rgIndices[0] + 1 )
  {
    rgIndices[0] = i;
    if ( i > plUbound || v10 )
      break;
    memset(&pv, 0, sizeof(pv));
    VariantInit(&pv);
    Element = SafeArrayGetElement(parray, rgIndices, &pv);
    if ( Element )
      goto LABEL_64;
    if ( pv.vt == vt )
    {
      if ( ((vt - 8) & 0xFFFA) != 0 || (bstrVal = pv.bstrVal, vt == 12) )
        bstrVal = &pv.decVal.8;
      v10 = SafeArrayPutElement(v16, rgIndices, bstrVal);
    }
    else
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      SystemDefaultLangID = GetSystemDefaultLangID();
      Element = VariantChangeTypeEx(&pvarg, &pv, SystemDefaultLangID, 0, vt);
      if ( Element )
      {
LABEL_64:
        SafeArrayDestroy(v16);
        return Element;
      }
      if ( ((vt - 8) & 0xFFFA) != 0 || (v20 = pvarg.bstrVal, vt == 12) )
        v20 = &pvarg.decVal.8;
      v10 = SafeArrayPutElement(v16, rgIndices, v20);
      VariantClear(&pvarg);
    }
    VariantClear(&pv);
  }
  a1->vt = vt | 0x2000;
  a1->llVal = (LONGLONG)v16;
  return 0;
}

```

## disassembly

```asm
0x180025074  mov     [rsp-38h+arg_10], rbx
0x180025079  mov     [rsp-38h+arg_0], rcx
0x18002507e  push    rbp
0x18002507f  push    rsi
0x180025080  push    rdi
0x180025081  push    r12
0x180025083  push    r13
0x180025085  push    r14
0x180025087  push    r15
0x180025089  mov     rbp, rsp
0x18002508c  sub     rsp, 70h
0x180025090  movzx   edi, r9w
0x180025094  mov     ebx, 9
0x180025099  mov     r13d, r8d
0x18002509c  lea     r9d, [rbx+4]
0x1800250a0  cmp     r9w, di
0x1800250a4  cmovnz  bx, di
0x1800250a8  xor     eax, eax
0x1800250aa  lea     esi, [rax+1]
0x1800250ad  cmp     ax, bx
0x1800250b0  jnz     short loc_1800250B5
0x1800250b2  movzx   ebx, si
0x1800250b5  test    rdx, rdx
0x1800250b8  jz      loc_1800253F1
0x1800250be  test    rcx, rcx
0x1800250c1  jz      loc_1800253F1
0x1800250c7  movzx   r8d, word ptr [rdx]
0x1800250cb  test    r8b, 0Ch
0x1800250cf  setnz   cl
0x1800250d2  bt      r8w, r9w
0x1800250d7  setb    al
0x1800250da  test    al, cl
0x1800250dc  jz      loc_1800253F1
0x1800250e2  bt      r8w, 0Eh
0x1800250e8  jnb     short loc_1800250FC
0x1800250ea  mov     rax, [rdx+8]
0x1800250ee  test    rax, rax
0x1800250f1  jz      loc_1800253F1
0x1800250f7  mov     r15, [rax]
0x1800250fa  jmp     short loc_180025100
0x1800250fc  mov     r15, [rdx+8]
0x180025100  test    r15, r15
0x180025103  jz      loc_1800253F1
0x180025109  mov     rcx, r15; psa
0x18002510c  call    cs:__imp_SafeArrayGetDim
0x180025112  cmp     eax, esi
0x180025114  jnz     loc_1800253F1
0x18002511a  lea     r8, [rbp+plLbound]; plLbound
0x18002511e  mov     qword ptr [rbp+rgIndices], 0
0x180025126  mov     edx, esi; nDim
0x180025128  mov     [rbp+plLbound], 0
0x18002512f  mov     rcx, r15; psa
0x180025132  mov     [rbp+plUbound], 0
0x180025139  call    cs:__imp_SafeArrayGetLBound
0x18002513f  test    eax, eax
0x180025141  jnz     loc_1800253F6
0x180025147  lea     r8, [rbp+plUbound]; plUbound
0x18002514b  mov     edx, esi; nDim
0x18002514d  mov     rcx, r15; psa
0x180025150  call    cs:__imp_SafeArrayGetUBound
0x180025156  mov     r14d, eax
0x180025159  test    eax, eax
0x18002515b  jnz     loc_1800253F6
0x180025161  mov     ecx, [rbp+plUbound]
0x180025164  mov     r12d, ecx
0x180025167  mov     edx, [rbp+plLbound]
0x18002516a  sub     r12d, edx
0x18002516d  add     r12d, esi
0x180025170  jnz     short loc_18002519A
0x180025172  test    r13d, r13d
0x180025175  lea     r13d, [rax+0Ch]
0x180025179  jnz     short loc_180025183
0x18002517b  mov     edi, r13d
0x18002517e  jmp     loc_1800252B1
0x180025183  cmp     si, bx
0x180025186  jz      short loc_180025190
0x180025188  movzx   edi, bx
0x18002518b  jmp     loc_1800252B1
0x180025190  mov     edi, 3
0x180025195  jmp     loc_1800252B1
0x18002519a  cmp     si, bx
0x18002519d  jz      short loc_1800251A7
0x18002519f  movzx   edi, bx
0x1800251a2  jmp     loc_1800252AB
0x1800251a7  mov     esi, 3
0x1800251ac  mov     [rbp+rgIndices], edx
0x1800251af  cmp     edx, ecx
0x1800251b1  jg      loc_180025296
0x1800251b7  xorps   xmm0, xmm0
0x1800251ba  lea     rcx, [rbp+pvarg]; pvarg
0x1800251be  xor     eax, eax
0x1800251c0  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800251c4  mov     qword ptr [rbp+pvarg+10h], rax
0x1800251c8  call    cs:__imp_VariantInit
0x1800251ce  lea     r8, [rbp+pvarg]; pv
0x1800251d2  mov     rcx, r15; psa
0x1800251d5  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800251d9  call    cs:__imp_SafeArrayGetElement
0x1800251df  mov     r14d, eax
0x1800251e2  test    eax, eax
0x1800251e4  jnz     loc_1800253F6
0x1800251ea  movzx   ebx, word ptr [rbp+pvarg]
0x1800251ee  lea     rcx, [rbp+pvarg]; pvarg
0x1800251f2  call    cs:__imp_VariantClear
0x1800251f8  mov     edx, [rbp+rgIndices]
0x1800251fb  cmp     edx, [rbp+plLbound]
0x1800251fe  jnz     short loc_180025208
0x180025200  movzx   edi, bx
0x180025203  jmp     loc_18002528C
0x180025208  cmp     di, bx
0x18002520b  jz      short loc_18002528C
0x18002520d  movzx   ecx, di
0x180025210  mov     r8d, 2
0x180025216  sub     ecx, r8d
0x180025219  jz      short loc_18002527A
0x18002521b  sub     ecx, 1
0x18002521e  jz      short loc_18002526D
0x180025220  sub     ecx, 1
0x180025223  jz      short loc_180025255
0x180025225  sub     ecx, 1
0x180025228  jz      short loc_180025249
0x18002522a  cmp     ecx, 0Ch
0x18002522d  jnz     short loc_18002523F
0x18002522f  movzx   eax, bx
0x180025232  lea     ecx, [r8-1]
0x180025236  sub     ax, r8w
0x18002523a  cmp     ax, cx
0x18002523d  jbe     short loc_180025200
0x18002523f  mov     eax, 80041008h
0x180025244  jmp     loc_1800253F6
0x180025249  mov     eax, 4
0x18002524e  cmp     ax, bx
0x180025251  jnz     short loc_18002523F
0x180025253  jmp     short loc_18002528C
0x180025255  mov     r8d, 5
0x18002525b  movzx   eax, bx
0x18002525e  cmp     r8w, bx
0x180025262  cmovnz  ax, di
0x180025266  jnz     short loc_18002523F
0x180025268  movzx   edi, ax
0x18002526b  jmp     short loc_18002528C
0x18002526d  cmp     r8w, bx
0x180025271  jz      short loc_18002528C
0x180025273  mov     eax, 11h
0x180025278  jmp     short loc_18002524E
0x18002527a  mov     eax, 11h
0x18002527f  cmp     ax, bx
0x180025282  jz      short loc_18002528C
0x180025284  cmp     si, bx
0x180025287  jnz     short loc_18002523F
0x180025289  movzx   edi, si
0x18002528c  mov     ecx, [rbp+plUbound]
0x18002528f  inc     edx
0x180025291  jmp     loc_1800251AC
0x180025296  test    r13d, r13d
0x180025299  jz      short loc_1800252A6
0x18002529b  movzx   ecx, di; unsigned __int16
0x18002529e  call    ?GetAcceptableQualType@@YAGG@Z; GetAcceptableQualType(ushort)
0x1800252a3  movzx   edi, ax
0x1800252a6  mov     esi, 1
0x1800252ab  mov     r13d, 0Ch
0x1800252b1  lea     r8, [rbp+rgsabound]; rgsabound
0x1800252b5  mov     [rbp+rgsabound.lLbound], 0
0x1800252bc  mov     edx, esi; cDims
0x1800252be  mov     [rbp+rgsabound.cElements], r12d
0x1800252c2  movzx   ecx, di; vt
0x1800252c5  call    cs:__imp_SafeArrayCreate
0x1800252cb  mov     rsi, rax
0x1800252ce  mov     r12d, 0FFFAh
0x1800252d4  mov     eax, [rbp+plLbound]
0x1800252d7  mov     [rbp+rgIndices], eax
0x1800252da  cmp     eax, [rbp+plUbound]
0x1800252dd  jg      loc_1800253DD
0x1800252e3  test    r14d, r14d
0x1800252e6  jnz     loc_1800253DD
0x1800252ec  xorps   xmm0, xmm0
0x1800252ef  lea     rcx, [rbp+pv]; pvarg
0x1800252f3  xor     eax, eax
0x1800252f5  movups  xmmword ptr [rbp+pv], xmm0
0x1800252f9  mov     qword ptr [rbp+pv+10h], rax
0x1800252fd  call    cs:__imp_VariantInit
0x180025303  lea     r8, [rbp+pv]; pv
0x180025307  mov     rcx, r15; psa
0x18002530a  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002530e  call    cs:__imp_SafeArrayGetElement
0x180025314  mov     ebx, eax
0x180025316  test    eax, eax
0x180025318  jnz     loc_1800253D0
0x18002531e  cmp     word ptr [rbp+pv], di
0x180025322  jz      short loc_180025395
0x180025324  xorps   xmm0, xmm0
0x180025327  lea     rcx, [rbp+pvarg]; pvarg
0x18002532b  xor     eax, eax
0x18002532d  movups  xmmword ptr [rbp+pvarg], xmm0
0x180025331  mov     qword ptr [rbp+pvarg+10h], rax
0x180025335  call    cs:__imp_VariantInit
0x18002533b  call    cs:__imp_GetSystemDefaultLangID
0x180025341  movzx   r9d, bx; wFlags
0x180025345  mov     [rsp+70h+vt], di; vt
0x18002534a  movzx   r8d, ax; lcid
0x18002534e  lea     rdx, [rbp+pv]; pvarSrc
0x180025352  lea     rcx, [rbp+pvarg]; pvargDest
0x180025356  call    cs:__imp_VariantChangeTypeEx
0x18002535c  mov     ebx, eax
0x18002535e  test    eax, eax
0x180025360  jnz     short loc_1800253D0
0x180025362  lea     eax, [rdi-8]
0x180025365  test    r12w, ax
0x180025369  jnz     short loc_180025375
0x18002536b  mov     r8, qword ptr [rbp+pvarg+8]
0x18002536f  cmp     di, r13w
0x180025373  jnz     short loc_180025379
0x180025375  lea     r8, [rbp+pvarg+8]; pv
0x180025379  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002537d  mov     rcx, rsi; psa
0x180025380  call    cs:__imp_SafeArrayPutElement
0x180025386  lea     rcx, [rbp+pvarg]; pvarg
0x18002538a  mov     r14d, eax
0x18002538d  call    cs:__imp_VariantClear
0x180025393  jmp     short loc_1800253BC
0x180025395  lea     eax, [rdi-8]
0x180025398  test    r12w, ax
0x18002539c  jnz     short loc_1800253A8
0x18002539e  mov     r8, qword ptr [rbp+pv+8]
0x1800253a2  cmp     di, r13w
0x1800253a6  jnz     short loc_1800253AC
0x1800253a8  lea     r8, [rbp+pv+8]; pv
0x1800253ac  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800253b0  mov     rcx, rsi; psa
0x1800253b3  call    cs:__imp_SafeArrayPutElement
0x1800253b9  mov     r14d, eax
0x1800253bc  lea     rcx, [rbp+pv]; pvarg
0x1800253c0  call    cs:__imp_VariantClear
0x1800253c6  mov     eax, [rbp+rgIndices]
0x1800253c9  inc     eax
0x1800253cb  jmp     loc_1800252D7
0x1800253d0  mov     rcx, rsi; psa
0x1800253d3  call    cs:__imp_SafeArrayDestroy
0x1800253d9  mov     eax, ebx
0x1800253db  jmp     short loc_1800253F6
0x1800253dd  mov     rax, [rbp+arg_0]
0x1800253e1  or      di, 2000h
0x1800253e6  mov     [rax], di
0x1800253e9  mov     [rax+8], rsi
0x1800253ed  xor     eax, eax
0x1800253ef  jmp     short loc_1800253F6
0x1800253f1  mov     eax, 80041001h
0x1800253f6  mov     rbx, [rsp+70h+arg_10]
0x1800253fe  add     rsp, 70h
0x180025402  pop     r15
0x180025404  pop     r14
0x180025406  pop     r13
0x180025408  pop     r12
0x18002540a  pop     rdi
0x18002540b  pop     rsi
0x18002540c  pop     rbp
0x18002540d  retn
```
