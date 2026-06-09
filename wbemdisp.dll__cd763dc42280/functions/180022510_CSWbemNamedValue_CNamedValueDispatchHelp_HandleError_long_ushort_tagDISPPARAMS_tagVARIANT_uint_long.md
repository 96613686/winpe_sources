# CSWbemNamedValue::CNamedValueDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x180022510`
- end: `0x1800227a5`
- name: `?HandleError@CNamedValueDispatchHelp@CSWbemNamedValue@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `661`
- prototype: `__int64 __fastcall(CSWbemNamedValue::CNamedValueDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *, unsigned int *, LONG rgIndices)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180022510`
- `0x180024390`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002259f`
- `OLEAUT32!__imp_VariantInit` at `0x1800225e1`
- `OLEAUT32!__imp_VariantInit` at `0x180022628`
- `OLEAUT32!__imp_VariantInit` at `0x18002266c`
- `OLEAUT32!__imp_VariantInit` at `0x1800226a9`
- `OLEAUT32!__imp_VariantInit` at `0x18002259f`
- `OLEAUT32!__imp_VariantInit` at `0x1800225e1`
- `OLEAUT32!__imp_VariantInit` at `0x180022628`
- `OLEAUT32!__imp_VariantInit` at `0x18002266c`
- `OLEAUT32!__imp_VariantInit` at `0x1800226a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800226e3`
- `OLEAUT32!__imp_VariantClear` at `0x18002274c`
- `OLEAUT32!__imp_VariantClear` at `0x18002276f`
- `OLEAUT32!__imp_VariantClear` at `0x180022779`
- `OLEAUT32!__imp_VariantClear` at `0x1800226e3`
- `OLEAUT32!__imp_VariantClear` at `0x18002274c`
- `OLEAUT32!__imp_VariantClear` at `0x18002276f`
- `OLEAUT32!__imp_VariantClear` at `0x180022779`
- `OLEAUT32!__imp_VariantCopy` at `0x180022679`
- `OLEAUT32!__imp_VariantCopy` at `0x180022679`
- `OLEAUT32!__imp_VariantChangeType` at `0x180022600`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800226f8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180022600`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800226f8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800226c0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800226c0`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002263a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800226d2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002263a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800226d2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002270e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002270e`

## pseudocode

```c
__int64 __fastcall CSWbemNamedValue::CNamedValueDispatchHelp::HandleError(
        CSWbemNamedValue::CNamedValueDispatchHelp *this,
        int a2,
        char a3,
        struct tagDISPPARAMS *a4,
        VARIANTARG *a5,
        unsigned int *a6,
        LONG rgIndices)
{
  unsigned int Element; // ebx
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int16 v11; // r15
  VARTYPE vt; // bx
  __int64 v14; // [rsp+20h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-69h] BYREF
  VARIANTARG pvarSrc; // [rsp+40h] [rbp-51h] BYREF
  VARIANTARG pv; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG pvargDest; // [rsp+70h] [rbp-21h] BYREF
  LONG plLbound; // [rsp+E8h] [rbp+57h] BYREF

  Element = rgIndices;
  if ( !a2 && rgIndices == -2147352559 )
  {
    if ( a4->cArgs )
    {
      v10 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
      v14 = 0;
      v11 = a3 & 2;
      if ( (**v10)(v10, &IID_ISWbemNamedValue, &v14) >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 56LL))(v14, &pvarg) < 0
          || (pvarg.vt & 0x2000) == 0 )
        {
          goto LABEL_27;
        }
        memset(&pvargDest, 0, sizeof(pvargDest));
        VariantInit(&pvargDest);
        if ( VariantChangeType(&pvargDest, &a4->rgvarg[v11 == 0], 0, 3u) )
        {
          Element = -2147352571;
          if ( a6 )
            *a6 = v11 == 0;
          goto LABEL_26;
        }
        rgIndices = pvargDest.lVal;
        if ( v11 )
        {
          if ( a4->cArgs == 1 )
          {
            VariantInit(a5);
            Element = SafeArrayGetElement(pvarg.parray, &rgIndices, a5);
LABEL_26:
            VariantClear(&pvargDest);
LABEL_27:
            VariantClear(&pvarg);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            return Element;
          }
          goto LABEL_23;
        }
        if ( (a3 & 4) == 0 )
          goto LABEL_26;
        if ( a4->cArgs != 2 )
        {
LABEL_23:
          Element = -2147352562;
          goto LABEL_26;
        }
        memset(&pvarSrc, 0, sizeof(pvarSrc));
        VariantInit(&pvarSrc);
        if ( VariantCopy(&pvarSrc, a4->rgvarg) < 0 )
          goto LABEL_26;
        CheckArrayBounds(pvarg.parray, rgIndices);
        vt = -1;
        memset(&pv, 0, sizeof(pv));
        VariantInit(&pv);
        plLbound = 0;
        SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
        if ( SafeArrayGetElement(pvarg.parray, &plLbound, &pv) >= 0 )
          vt = pv.vt;
        VariantClear(&pv);
        if ( !VariantChangeType(&pvarSrc, &pvarSrc, 0, vt) )
        {
          Element = SafeArrayPutElement(pvarg.parray, &rgIndices, &pvarSrc);
          if ( Element )
          {
LABEL_22:
            VariantClear(&pvarSrc);
            goto LABEL_26;
          }
          if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 64LL))(v14, &pvarg) >= 0 )
          {
            Element = 0;
            goto LABEL_22;
          }
        }
        Element = -2147352571;
        if ( a6 )
          *a6 = 0;
        goto LABEL_22;
      }
    }
  }
  return Element;
}

```

## disassembly

```asm
0x180022510  push    rbp
0x180022512  push    rbx
0x180022513  push    rsi
0x180022514  push    rdi
0x180022515  push    r12
0x180022517  push    r13
0x180022519  push    r14
0x18002251b  push    r15
0x18002251d  lea     rbp, [rsp-7]
0x180022522  sub     rsp, 98h
0x180022529  mov     ebx, [rbp+3Fh+rgIndices]
0x18002252c  xor     r12d, r12d
0x18002252f  mov     rdi, r9
0x180022532  movzx   r14d, r8w
0x180022536  test    edx, edx
0x180022538  jnz     loc_18002278F
0x18002253e  cmp     ebx, 80020011h
0x180022544  jnz     loc_18002278F
0x18002254a  cmp     [r9+10h], r12d
0x18002254e  jbe     loc_18002278F
0x180022554  mov     rcx, [rcx+28h]
0x180022558  lea     r13d, [r12+2]
0x18002255d  movzx   r15d, r8w
0x180022561  mov     [rbp+3Fh+var_B0], r12
0x180022565  and     r15w, r13w
0x180022569  lea     r8, [rbp+3Fh+var_B0]
0x18002256d  mov     esi, r12d
0x180022570  lea     rdx, IID_ISWbemNamedValue
0x180022577  mov     rax, [rcx]
0x18002257a  setz    sil
0x18002257e  mov     rax, [rax]
0x180022581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022586  test    eax, eax
0x180022588  js      loc_18002278F
0x18002258e  xorps   xmm0, xmm0
0x180022591  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180022595  xor     eax, eax
0x180022597  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18002259b  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x18002259f  call    cs:__imp_VariantInit
0x1800225a5  mov     rcx, [rbp+3Fh+var_B0]
0x1800225a9  lea     rdx, [rbp+3Fh+pvarg]
0x1800225ad  mov     rax, [rcx]
0x1800225b0  mov     rax, [rax+38h]
0x1800225b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b9  test    eax, eax
0x1800225bb  js      loc_180022775
0x1800225c1  mov     eax, 2000h
0x1800225c6  test    word ptr [rbp+3Fh+pvarg], ax
0x1800225ca  jz      loc_180022775
0x1800225d0  xorps   xmm0, xmm0
0x1800225d3  lea     rcx, [rbp+3Fh+pvargDest]; pvarg
0x1800225d7  xor     eax, eax
0x1800225d9  movups  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x1800225dd  mov     qword ptr [rbp+3Fh+pvargDest+10h], rax
0x1800225e1  call    cs:__imp_VariantInit
0x1800225e7  mov     eax, esi
0x1800225e9  lea     r9d, [r12+3]; vt
0x1800225ee  xor     r8d, r8d; wFlags
0x1800225f1  lea     rcx, [rax+rax*2]
0x1800225f5  mov     rax, [rdi]
0x1800225f8  lea     rdx, [rax+rcx*8]; pvarSrc
0x1800225fc  lea     rcx, [rbp+3Fh+pvargDest]; pvargDest
0x180022600  call    cs:__imp_VariantChangeType
0x180022606  test    eax, eax
0x180022608  jnz     loc_18002275B
0x18002260e  mov     eax, dword ptr [rbp+3Fh+pvargDest+8]
0x180022611  mov     [rbp+3Fh+rgIndices], eax
0x180022614  test    r15w, r15w
0x180022618  jz      short loc_180022647
0x18002261a  cmp     dword ptr [rdi+10h], 1
0x18002261e  jnz     loc_180022754
0x180022624  mov     rcx, [rbp+3Fh+arg_20]; pvarg
0x180022628  call    cs:__imp_VariantInit
0x18002262e  mov     r8, [rbp+3Fh+arg_20]; pv
0x180022632  lea     rdx, [rbp+3Fh+rgIndices]; rgIndices
0x180022636  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x18002263a  call    cs:__imp_SafeArrayGetElement
0x180022640  mov     ebx, eax
0x180022642  jmp     loc_18002276B
0x180022647  test    r14b, 4
0x18002264b  jz      loc_18002276B
0x180022651  cmp     [rdi+10h], r13d
0x180022655  jnz     loc_180022754
0x18002265b  xorps   xmm0, xmm0
0x18002265e  lea     rcx, [rbp+3Fh+pvarSrc]; pvarg
0x180022662  xor     eax, eax
0x180022664  movups  xmmword ptr [rbp+3Fh+pvarSrc], xmm0
0x180022668  mov     qword ptr [rbp+3Fh+pvarSrc+10h], rax
0x18002266c  call    cs:__imp_VariantInit
0x180022672  mov     rdx, [rdi]; pvargSrc
0x180022675  lea     rcx, [rbp+3Fh+pvarSrc]; pvargDest
0x180022679  call    cs:__imp_VariantCopy
0x18002267f  test    eax, eax
0x180022681  js      loc_18002276B
0x180022687  mov     edx, [rbp+3Fh+rgIndices]; int
0x18002268a  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x18002268e  call    ?CheckArrayBounds@@YAXPEAUtagSAFEARRAY@@J@Z; CheckArrayBounds(tagSAFEARRAY *,long)
0x180022693  xorps   xmm0, xmm0
0x180022696  lea     rcx, [rbp+3Fh+pv]; pvarg
0x18002269a  xor     eax, eax
0x18002269c  mov     ebx, 0FFFFh
0x1800226a1  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x1800226a5  mov     qword ptr [rbp+3Fh+pv+10h], rax
0x1800226a9  call    cs:__imp_VariantInit
0x1800226af  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x1800226b3  lea     r8, [rbp+3Fh+plLbound]; plLbound
0x1800226b7  mov     edx, 1; nDim
0x1800226bc  mov     [rbp+3Fh+plLbound], r12d
0x1800226c0  call    cs:__imp_SafeArrayGetLBound
0x1800226c6  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x1800226ca  lea     r8, [rbp+3Fh+pv]; pv
0x1800226ce  lea     rdx, [rbp+3Fh+plLbound]; rgIndices
0x1800226d2  call    cs:__imp_SafeArrayGetElement
0x1800226d8  test    eax, eax
0x1800226da  lea     rcx, [rbp+3Fh+pv]; pvarg
0x1800226de  cmovns  bx, word ptr [rbp+3Fh+pv]
0x1800226e3  call    cs:__imp_VariantClear
0x1800226e9  xor     r8d, r8d; wFlags
0x1800226ec  lea     rdx, [rbp+3Fh+pvarSrc]; pvarSrc
0x1800226f0  movzx   r9d, bx; vt
0x1800226f4  lea     rcx, [rbp+3Fh+pvarSrc]; pvargDest
0x1800226f8  call    cs:__imp_VariantChangeType
0x1800226fe  test    eax, eax
0x180022700  jnz     short loc_180022737
0x180022702  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x180022706  lea     r8, [rbp+3Fh+pvarSrc]; pv
0x18002270a  lea     rdx, [rbp+3Fh+rgIndices]; rgIndices
0x18002270e  call    cs:__imp_SafeArrayPutElement
0x180022714  mov     ebx, eax
0x180022716  test    eax, eax
0x180022718  jnz     short loc_180022748
0x18002271a  mov     rcx, [rbp+3Fh+var_B0]
0x18002271e  lea     rdx, [rbp+3Fh+pvarg]
0x180022722  mov     rax, [rcx]
0x180022725  mov     rax, [rax+40h]
0x180022729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002272e  test    eax, eax
0x180022730  js      short loc_180022737
0x180022732  mov     ebx, r12d
0x180022735  jmp     short loc_180022748
0x180022737  mov     rax, [rbp+3Fh+arg_28]
0x18002273b  mov     ebx, 80020005h
0x180022740  test    rax, rax
0x180022743  jz      short loc_180022748
0x180022745  mov     [rax], r12d
0x180022748  lea     rcx, [rbp+3Fh+pvarSrc]; pvarg
0x18002274c  call    cs:__imp_VariantClear
0x180022752  jmp     short loc_18002276B
0x180022754  mov     ebx, 8002000Eh
0x180022759  jmp     short loc_18002276B
0x18002275b  mov     rax, [rbp+3Fh+arg_28]
0x18002275f  mov     ebx, 80020005h
0x180022764  test    rax, rax
0x180022767  jz      short loc_18002276B
0x180022769  mov     [rax], esi
0x18002276b  lea     rcx, [rbp+3Fh+pvargDest]; pvarg
0x18002276f  call    cs:__imp_VariantClear
0x180022775  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180022779  call    cs:__imp_VariantClear
0x18002277f  mov     rcx, [rbp+3Fh+var_B0]
0x180022783  mov     rax, [rcx]
0x180022786  mov     rax, [rax+10h]
0x18002278a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002278f  mov     eax, ebx
0x180022791  add     rsp, 98h
0x180022798  pop     r15
0x18002279a  pop     r14
0x18002279c  pop     r13
0x18002279e  pop     r12
0x1800227a0  pop     rdi
0x1800227a1  pop     rsi
0x1800227a2  pop     rbx
0x1800227a3  pop     rbp
0x1800227a4  retn
```
