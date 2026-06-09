# CSWbemProperty::CPropertyDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x180021730`
- end: `0x1800219e8`
- name: `?HandleError@CPropertyDispatchHelp@CSWbemProperty@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `696`
- prototype: `__int64 __fastcall(CSWbemProperty::CPropertyDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180019114`
- `0x180021730`
- `0x180021b9c`
- `0x180024390`
- `0x180026008`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180021809`
- `OLEAUT32!__imp_VariantInit` at `0x18002184b`
- `OLEAUT32!__imp_VariantInit` at `0x180021891`
- `OLEAUT32!__imp_VariantInit` at `0x1800218d5`
- `OLEAUT32!__imp_VariantInit` at `0x180021809`
- `OLEAUT32!__imp_VariantInit` at `0x18002184b`
- `OLEAUT32!__imp_VariantInit` at `0x180021891`
- `OLEAUT32!__imp_VariantInit` at `0x1800218d5`
- `OLEAUT32!__imp_VariantClear` at `0x18002198f`
- `OLEAUT32!__imp_VariantClear` at `0x1800219b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800219bc`
- `OLEAUT32!__imp_VariantClear` at `0x18002198f`
- `OLEAUT32!__imp_VariantClear` at `0x1800219b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800219bc`
- `OLEAUT32!__imp_VariantCopy` at `0x1800218e2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800218e2`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021869`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002190c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021869`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002190c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800218a3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800218a3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002192e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002192e`

## pseudocode

```c
__int64 __fastcall CSWbemProperty::CPropertyDispatchHelp::HandleError(
        CSWbemProperty::CPropertyDispatchHelp *this,
        int a2,
        char a3,
        struct tagDISPPARAMS *a4,
        VARIANTARG *a5,
        unsigned int *a6,
        unsigned int a7)
{
  unsigned int Element; // edi
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  __int16 v12; // r12
  VARTYPE v13; // ax
  __int64 v14; // rbx
  int v16; // [rsp+20h] [rbp-61h] BYREF
  __int64 v17; // [rsp+28h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-51h] BYREF
  VARIANTARG pvarSrc; // [rsp+48h] [rbp-39h] BYREF
  VARIANTARG pvargDest; // [rsp+60h] [rbp-21h] BYREF
  LONG rgIndices; // [rsp+D8h] [rbp+57h] BYREF

  Element = a7;
  if ( !a2 && a7 == -2147352559 )
  {
    if ( a4->cArgs )
    {
      v11 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
      v16 = 0;
      LOWORD(a7) = 0;
      v17 = 0;
      v12 = a3 & 2;
      if ( (**v11)(v11, &IID_ISWbemProperty, &v17) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 96LL))(v17, &v16) < 0
          || (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 112LL))(v17, &a7) < 0
          || !(_WORD)a7 )
        {
          goto LABEL_30;
        }
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v17 + 56LL))(v17, &pvarg) < 0
          || (pvarg.vt & 0x2000) == 0 )
        {
LABEL_29:
          VariantClear(&pvarg);
LABEL_30:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          return Element;
        }
        memset(&pvargDest, 0, sizeof(pvargDest));
        VariantInit(&pvargDest);
        if ( VariantChangeType(&pvargDest, &a4->rgvarg[v12 == 0], 0, 3u) )
        {
          Element = -2147352571;
          if ( a6 )
            *a6 = v12 == 0;
          goto LABEL_28;
        }
        rgIndices = pvargDest.lVal;
        if ( v12 )
        {
          if ( a4->cArgs == 1 )
          {
            VariantInit(a5);
            Element = SafeArrayGetElement(pvarg.parray, &rgIndices, a5);
LABEL_28:
            VariantClear(&pvargDest);
            goto LABEL_29;
          }
          goto LABEL_25;
        }
        if ( (a3 & 4) == 0 )
          goto LABEL_28;
        if ( a4->cArgs != 2 )
        {
LABEL_25:
          Element = -2147352562;
          goto LABEL_28;
        }
        memset(&pvarSrc, 0, sizeof(pvarSrc));
        VariantInit(&pvarSrc);
        if ( VariantCopy(&pvarSrc, a4->rgvarg) < 0 )
          goto LABEL_28;
        if ( v16 == 13 || (v13 = CimTypeToVtType(v16), !VariantChangeType(&pvarSrc, &pvarSrc, 0, v13)) )
        {
          CheckArrayBounds(pvarg.parray, rgIndices);
          Element = SafeArrayPutElement(pvarg.parray, &rgIndices, &pvarSrc);
          if ( Element )
          {
LABEL_24:
            VariantClear(&pvarSrc);
            goto LABEL_28;
          }
          if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v17 + 64LL))(v17, &pvarg) >= 0 )
          {
            v14 = *((_QWORD *)this + 5);
            Element = 0;
            SetSite(
              a4->rgvarg,
              *(struct ISWbemInternalObject **)(v14 + 32),
              *(unsigned __int16 **)(v14 + 128),
              rgIndices);
            CSWbemProperty::UpdateSite((CSWbemProperty *)v14);
            goto LABEL_24;
          }
        }
        Element = -2147352571;
        if ( a6 )
          *a6 = 0;
        goto LABEL_24;
      }
    }
  }
  return Element;
}

```

## disassembly

```asm
0x180021730  push    rbp
0x180021732  push    rbx
0x180021733  push    rsi
0x180021734  push    rdi
0x180021735  push    r12
0x180021737  push    r13
0x180021739  push    r14
0x18002173b  push    r15
0x18002173d  lea     rbp, [rsp-7]
0x180021742  sub     rsp, 88h
0x180021749  mov     edi, [rbp+3Fh+arg_30]
0x18002174c  xor     r13d, r13d
0x18002174f  mov     rsi, r9
0x180021752  movzx   r14d, r8w
0x180021756  mov     r15, rcx
0x180021759  test    edx, edx
0x18002175b  jnz     loc_1800219D2
0x180021761  cmp     edi, 80020011h
0x180021767  jnz     loc_1800219D2
0x18002176d  cmp     [r9+10h], r13d
0x180021771  jbe     loc_1800219D2
0x180021777  mov     rcx, [rcx+28h]
0x18002177b  lea     rdx, IID_ISWbemProperty
0x180021782  movzx   r12d, r8w
0x180021786  mov     [rbp+3Fh+var_A0], r13d
0x18002178a  mov     word ptr [rbp+3Fh+arg_30], r13w
0x18002178f  lea     r8, [rbp+3Fh+var_98]
0x180021793  mov     [rbp+3Fh+var_98], r13
0x180021797  and     r12w, 2
0x18002179c  mov     rax, [rcx]
0x18002179f  mov     ebx, r13d
0x1800217a2  setz    bl
0x1800217a5  mov     rax, [rax]
0x1800217a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217ad  test    eax, eax
0x1800217af  js      loc_1800219D2
0x1800217b5  mov     rcx, [rbp+3Fh+var_98]
0x1800217b9  lea     rdx, [rbp+3Fh+var_A0]
0x1800217bd  mov     rax, [rcx]
0x1800217c0  mov     rax, [rax+60h]
0x1800217c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c9  test    eax, eax
0x1800217cb  js      loc_1800219C2
0x1800217d1  mov     rcx, [rbp+3Fh+var_98]
0x1800217d5  lea     rdx, [rbp+3Fh+arg_30]
0x1800217d9  mov     rax, [rcx]
0x1800217dc  mov     rax, [rax+70h]
0x1800217e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217e5  test    eax, eax
0x1800217e7  js      loc_1800219C2
0x1800217ed  cmp     word ptr [rbp+3Fh+arg_30], r13w
0x1800217f2  jz      loc_1800219C2
0x1800217f8  xorps   xmm0, xmm0
0x1800217fb  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800217ff  xor     eax, eax
0x180021801  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180021805  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180021809  call    cs:__imp_VariantInit
0x18002180f  mov     rcx, [rbp+3Fh+var_98]
0x180021813  lea     rdx, [rbp+3Fh+pvarg]
0x180021817  mov     rax, [rcx]
0x18002181a  mov     rax, [rax+38h]
0x18002181e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021823  test    eax, eax
0x180021825  js      loc_1800219B8
0x18002182b  mov     eax, 2000h
0x180021830  test    word ptr [rbp+3Fh+pvarg], ax
0x180021834  jz      loc_1800219B8
0x18002183a  xorps   xmm0, xmm0
0x18002183d  lea     rcx, [rbp+3Fh+pvargDest]; pvarg
0x180021841  xor     eax, eax
0x180021843  movups  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x180021847  mov     qword ptr [rbp+3Fh+pvargDest+10h], rax
0x18002184b  call    cs:__imp_VariantInit
0x180021851  mov     eax, ebx
0x180021853  lea     r9d, [r13+3]; vt
0x180021857  xor     r8d, r8d; wFlags
0x18002185a  lea     rcx, [rax+rax*2]
0x18002185e  mov     rax, [rsi]
0x180021861  lea     rdx, [rax+rcx*8]; pvarSrc
0x180021865  lea     rcx, [rbp+3Fh+pvargDest]; pvargDest
0x180021869  call    cs:__imp_VariantChangeType
0x18002186f  test    eax, eax
0x180021871  jnz     loc_18002199E
0x180021877  mov     eax, dword ptr [rbp+3Fh+pvargDest+8]
0x18002187a  mov     [rbp+3Fh+rgIndices], eax
0x18002187d  test    r12w, r12w
0x180021881  jz      short loc_1800218B0
0x180021883  cmp     dword ptr [rsi+10h], 1
0x180021887  jnz     loc_180021997
0x18002188d  mov     rcx, [rbp+3Fh+arg_20]; pvarg
0x180021891  call    cs:__imp_VariantInit
0x180021897  mov     r8, [rbp+3Fh+arg_20]; pv
0x18002189b  lea     rdx, [rbp+3Fh+rgIndices]; rgIndices
0x18002189f  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x1800218a3  call    cs:__imp_SafeArrayGetElement
0x1800218a9  mov     edi, eax
0x1800218ab  jmp     loc_1800219AE
0x1800218b0  test    r14b, 4
0x1800218b4  jz      loc_1800219AE
0x1800218ba  cmp     dword ptr [rsi+10h], 2
0x1800218be  jnz     loc_180021997
0x1800218c4  xorps   xmm0, xmm0
0x1800218c7  lea     rcx, [rbp+3Fh+pvarSrc]; pvarg
0x1800218cb  xor     eax, eax
0x1800218cd  movups  xmmword ptr [rbp+3Fh+pvarSrc], xmm0
0x1800218d1  mov     qword ptr [rbp+3Fh+pvarSrc+10h], rax
0x1800218d5  call    cs:__imp_VariantInit
0x1800218db  mov     rdx, [rsi]; pvargSrc
0x1800218de  lea     rcx, [rbp+3Fh+pvarSrc]; pvargDest
0x1800218e2  call    cs:__imp_VariantCopy
0x1800218e8  test    eax, eax
0x1800218ea  js      loc_1800219AE
0x1800218f0  mov     ecx, [rbp+3Fh+var_A0]; int
0x1800218f3  cmp     ecx, 0Dh
0x1800218f6  jz      short loc_180021916
0x1800218f8  call    ?CimTypeToVtType@@YAGJ@Z; CimTypeToVtType(long)
0x1800218fd  movzx   r9d, ax; vt
0x180021901  lea     rdx, [rbp+3Fh+pvarSrc]; pvarSrc
0x180021905  lea     rcx, [rbp+3Fh+pvarSrc]; pvargDest
0x180021909  xor     r8d, r8d; wFlags
0x18002190c  call    cs:__imp_VariantChangeType
0x180021912  test    eax, eax
0x180021914  jnz     short loc_18002197A
0x180021916  mov     edx, [rbp+3Fh+rgIndices]; int
0x180021919  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x18002191d  call    ?CheckArrayBounds@@YAXPEAUtagSAFEARRAY@@J@Z; CheckArrayBounds(tagSAFEARRAY *,long)
0x180021922  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x180021926  lea     r8, [rbp+3Fh+pvarSrc]; pv
0x18002192a  lea     rdx, [rbp+3Fh+rgIndices]; rgIndices
0x18002192e  call    cs:__imp_SafeArrayPutElement
0x180021934  mov     edi, eax
0x180021936  test    eax, eax
0x180021938  jnz     short loc_18002198B
0x18002193a  mov     rcx, [rbp+3Fh+var_98]
0x18002193e  lea     rdx, [rbp+3Fh+pvarg]
0x180021942  mov     rax, [rcx]
0x180021945  mov     rax, [rax+40h]
0x180021949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002194e  test    eax, eax
0x180021950  js      short loc_18002197A
0x180021952  mov     rbx, [r15+28h]
0x180021956  mov     edi, r13d
0x180021959  mov     r9d, [rbp+3Fh+rgIndices]; int
0x18002195d  mov     rcx, [rsi]; struct tagVARIANT *
0x180021960  mov     r8, [rbx+80h]; unsigned __int16 *
0x180021967  mov     rdx, [rbx+20h]; struct ISWbemInternalObject *
0x18002196b  call    ?SetSite@@YAXPEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z; SetSite(tagVARIANT *,ISWbemInternalObject *,ushort *,long)
0x180021970  mov     rcx, rbx; this
0x180021973  call    ?UpdateSite@CSWbemProperty@@QEAAXXZ; CSWbemProperty::UpdateSite(void)
0x180021978  jmp     short loc_18002198B
0x18002197a  mov     rax, [rbp+3Fh+arg_28]
0x18002197e  mov     edi, 80020005h
0x180021983  test    rax, rax
0x180021986  jz      short loc_18002198B
0x180021988  mov     [rax], r13d
0x18002198b  lea     rcx, [rbp+3Fh+pvarSrc]; pvarg
0x18002198f  call    cs:__imp_VariantClear
0x180021995  jmp     short loc_1800219AE
0x180021997  mov     edi, 8002000Eh
0x18002199c  jmp     short loc_1800219AE
0x18002199e  mov     rax, [rbp+3Fh+arg_28]
0x1800219a2  mov     edi, 80020005h
0x1800219a7  test    rax, rax
0x1800219aa  jz      short loc_1800219AE
0x1800219ac  mov     [rax], ebx
0x1800219ae  lea     rcx, [rbp+3Fh+pvargDest]; pvarg
0x1800219b2  call    cs:__imp_VariantClear
0x1800219b8  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800219bc  call    cs:__imp_VariantClear
0x1800219c2  mov     rcx, [rbp+3Fh+var_98]
0x1800219c6  mov     rax, [rcx]
0x1800219c9  mov     rax, [rax+10h]
0x1800219cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d2  mov     eax, edi
0x1800219d4  add     rsp, 88h
0x1800219db  pop     r15
0x1800219dd  pop     r14
0x1800219df  pop     r13
0x1800219e1  pop     r12
0x1800219e3  pop     rdi
0x1800219e4  pop     rsi
0x1800219e5  pop     rbx
0x1800219e6  pop     rbp
0x1800219e7  retn
```
