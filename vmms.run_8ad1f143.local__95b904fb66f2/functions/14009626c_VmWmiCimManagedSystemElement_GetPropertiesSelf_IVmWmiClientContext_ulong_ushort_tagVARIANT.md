# VmWmiCimManagedSystemElement::GetPropertiesSelf(IVmWmiClientContext *,ulong,ushort * *,tagVARIANT *)

- ea: `0x14009626c`
- end: `0x1400968f5`
- name: `?GetPropertiesSelf@VmWmiCimManagedSystemElement@@MEAAXPEAUIVmWmiClientContext@@KPEAPEAGPEAUtagVARIANT@@@Z`
- size: `1673`
- prototype: `void __fastcall(VmWmiCimManagedSystemElement *__hidden this, struct IVmWmiClientContext *, unsigned int, unsigned __int16 **, struct tagVARIANT *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140094a80`
- `0x140095d10`
- `0x140342c90`
- `0x14074b440`
- `0x14074e510`

## callees

- `0x140063794`
- `0x14009626c`
- `0x140188e18`
- `0x1404828e0`
- `0x140498a40`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400962c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009636d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096415`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400964b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096545`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009668a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096739`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400962c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009636d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096415`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400964b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096545`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009668a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140096739`
- `OLEAUT32!__imp_VariantClear` at `0x14009630f`
- `OLEAUT32!__imp_VariantClear` at `0x1400963b7`
- `OLEAUT32!__imp_VariantClear` at `0x14009645b`
- `OLEAUT32!__imp_VariantClear` at `0x1400964ea`
- `OLEAUT32!__imp_VariantClear` at `0x14009660a`
- `OLEAUT32!__imp_VariantClear` at `0x1400966d0`
- `OLEAUT32!__imp_VariantClear` at `0x1400967fc`
- `OLEAUT32!__imp_VariantClear` at `0x14009630f`
- `OLEAUT32!__imp_VariantClear` at `0x1400963b7`
- `OLEAUT32!__imp_VariantClear` at `0x14009645b`
- `OLEAUT32!__imp_VariantClear` at `0x1400964ea`
- `OLEAUT32!__imp_VariantClear` at `0x14009660a`
- `OLEAUT32!__imp_VariantClear` at `0x1400966d0`
- `OLEAUT32!__imp_VariantClear` at `0x1400967fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14009664b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14009683d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14009664b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14009683d`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14009658c`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14009677e`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14009658c`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14009677e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400965de`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400967d0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400965de`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1400967d0`

## string_xrefs

- `0x140096326`: `onecore\vm\common\vml\VmVariant.h`
- `0x1400963ce`: `onecore\vm\common\vml\VmVariant.h`
- `0x140096472`: `onecore\vm\common\vml\VmVariant.h`
- `0x140096501`: `onecore\vm\common\vml\VmVariant.h`
- `0x1400965f5`: `onecore\vm\common\vml\VmVariant.h`
- `0x140096621`: `onecore\vm\common\vml\VmVariant.h`
- `0x1400966e7`: `onecore\vm\common\vml\VmVariant.h`
- `0x1400967e7`: `onecore\vm\common\vml\VmVariant.h`
- `0x140096813`: `onecore\vm\common\vml\VmVariant.h`
- `0x140096899`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400968ae`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400968ca`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400968e3`: `onecore\vm\common\vml\VmAutomation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VmWmiCimManagedSystemElement::GetPropertiesSelf(
        VmWmiCimManagedSystemElement *this,
        struct IVmWmiClientContext *a2,
        int a3,
        unsigned __int16 **a4,
        struct tagVARIANT *a5)
{
  int v5; // edi
  int v7; // ebx
  int v8; // esi
  __int64 v9; // r15
  int v10; // eax
  int v11; // ecx
  struct tagVARIANT *v12; // rbx
  __int64 v13; // rsi
  HRESULT v14; // eax
  int v15; // ebx
  int v16; // esi
  __int64 v17; // r15
  int v18; // eax
  struct tagVARIANT *v19; // rbx
  __int64 v20; // rsi
  HRESULT v21; // eax
  int v22; // ebx
  int i; // esi
  __int64 v24; // r15
  int v25; // eax
  struct tagVARIANT *v26; // rbx
  __int64 v27; // rsi
  HRESULT v28; // eax
  int v29; // ebx
  int v30; // esi
  __int64 v31; // r15
  int v32; // eax
  int v33; // ecx
  struct tagVARIANT *v34; // rbx
  HRESULT v35; // eax
  int v36; // ebx
  int j; // esi
  __int64 v38; // r15
  int v39; // eax
  struct tagVARIANT *v40; // rbx
  SAFEARRAY *v41; // rsi
  HRESULT Vartype; // eax
  HRESULT v43; // eax
  HRESULT v44; // eax
  int v45; // ebx
  int k; // esi
  __int64 v47; // r15
  int v48; // eax
  struct tagVARIANT *v49; // rbx
  __int64 v50; // rsi
  HRESULT v51; // eax
  int v52; // ebx
  __int64 v53; // r14
  int v54; // eax
  struct tagVARIANT *v55; // rbx
  SAFEARRAY *v56; // rdi
  HRESULT v57; // eax
  HRESULT v58; // eax
  HRESULT v59; // eax
  unsigned __int16 **v60; // [rsp+20h] [rbp-28h]
  VARTYPE pvt; // [rsp+28h] [rbp-20h] BYREF
  SAFEARRAY *psa; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v60 = a4;
  v5 = a3;
  v7 = 0;
  v8 = a3;
  while ( v7 != v8 )
  {
    v9 = v7 + ((unsigned int)(v8 - v7) >> 1);
    v10 = _o__wcsicmp(L"Caption", a4[v9]);
    if ( !v10 )
    {
      v12 = &a5[v9];
      if ( v12 )
      {
        v13 = (*(__int64 (__fastcall **)(VmWmiCimManagedSystemElement *))(*(_QWORD *)this + 128LL))(this);
        v14 = VariantClear(&a5[v9]);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
            (const char *)(unsigned int)v14,
            (int)v60);
        a4 = v60;
        if ( v13 )
        {
          v12->vt = 8;
          v12->llVal = v13;
        }
      }
      else
      {
        a4 = v60;
      }
      break;
    }
    v11 = v7 + ((unsigned int)(v8 - v7) >> 1);
    if ( v10 >= 0 )
      v11 = v8;
    v8 = v11;
    if ( v10 >= 0 )
      v7 = v9 + 1;
    a4 = v60;
  }
  v15 = 0;
  v16 = v5;
  while ( v15 != v16 )
  {
    v17 = v15 + ((unsigned int)(v16 - v15) >> 1);
    v18 = _o__wcsicmp(L"Description", a4[v17]);
    if ( !v18 )
    {
      v19 = &a5[v17];
      if ( v19 )
      {
        v20 = (*(__int64 (__fastcall **)(VmWmiCimManagedSystemElement *))(*(_QWORD *)this + 136LL))(this);
        v21 = VariantClear(&a5[v17]);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
            (const char *)(unsigned int)v21,
            (int)v60);
        if ( v20 )
        {
          v19->vt = 8;
          v19->llVal = v20;
        }
      }
      break;
    }
    if ( v18 >= 0 )
    {
      v15 = v17 + 1;
      LODWORD(v17) = v16;
    }
    v16 = v17;
    a4 = v60;
  }
  v22 = 0;
  for ( i = v5; v22 != i; i = v24 )
  {
    v24 = v22 + ((unsigned int)(i - v22) >> 1);
    v25 = _o__wcsicmp(L"ElementName", v60[v24]);
    if ( !v25 )
    {
      v26 = &a5[v24];
      if ( v26 )
      {
        v27 = (*(__int64 (__fastcall **)(VmWmiCimManagedSystemElement *))(*(_QWORD *)this + 144LL))(this);
        v28 = VariantClear(&a5[v24]);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
            (const char *)(unsigned int)v28,
            (int)v60);
        if ( v27 )
        {
          v26->vt = 8;
          v26->llVal = v27;
        }
      }
      break;
    }
    if ( v25 >= 0 )
    {
      v22 = v24 + 1;
      LODWORD(v24) = i;
    }
  }
  v29 = 0;
  v30 = v5;
  while ( v29 != v30 )
  {
    v31 = v29 + ((unsigned int)(v30 - v29) >> 1);
    v32 = _o__wcsicmp(L"HealthState", v60[v31]);
    if ( !v32 )
    {
      v34 = &a5[v31];
      if ( v34 )
      {
        v35 = VariantClear(&a5[v31]);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
            (const char *)(unsigned int)v35,
            (int)v60);
        v34->vt = 18;
        v34->iVal = 5;
      }
      break;
    }
    v33 = v29 + ((unsigned int)(v30 - v29) >> 1);
    if ( v32 >= 0 )
      v33 = v30;
    v30 = v33;
    if ( v32 >= 0 )
      v29 = v31 + 1;
  }
  v36 = 0;
  for ( j = v5; v36 != j; j = v38 )
  {
    v38 = v36 + ((unsigned int)(j - v36) >> 1);
    v39 = _o__wcsicmp(L"OperationalStatus", v60[v38]);
    if ( !v39 )
    {
      v40 = &a5[v38];
      if ( v40 )
      {
        psa = SafeArrayCreateVectorEx(0x12u, 0, 1u, 0);
        if ( !psa )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D9,
            (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
            (const char *)0x8007000ELL,
            (int)v60);
        (*(void (__fastcall **)(VmWmiCimManagedSystemElement *, SAFEARRAY **))(*(_QWORD *)this + 152LL))(this, &psa);
        v41 = psa;
        psa = 0;
        if ( v41 )
        {
          pvt = 0;
          Vartype = SafeArrayGetVartype(v41, &pvt);
          if ( Vartype < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6ED,
              (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
              (const char *)(unsigned int)Vartype,
              (int)v60);
          v43 = VariantClear(&a5[v38]);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x723,
              (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
              (const char *)(unsigned int)v43,
              (int)v60);
          v40->vt = pvt | 0x2000;
          v40->llVal = (LONGLONG)v41;
        }
        else
        {
          Vml::VmVariant::Clear((Vml::VmVariant *)&a5[v38]);
        }
        if ( psa )
        {
          v44 = SafeArrayDestroy(psa);
          if ( v44 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x330,
              (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
              (const char *)(unsigned int)v44,
              (int)v60);
        }
      }
      break;
    }
    if ( v39 >= 0 )
    {
      v36 = v38 + 1;
      LODWORD(v38) = j;
    }
  }
  v45 = 0;
  for ( k = v5; v45 != k; k = v47 )
  {
    v47 = v45 + ((unsigned int)(k - v45) >> 1);
    v48 = _o__wcsicmp(L"Status", v60[v47]);
    if ( !v48 )
    {
      v49 = &a5[v47];
      if ( v49 )
      {
        v50 = (*(__int64 (__fastcall **)(VmWmiCimManagedSystemElement *))(*(_QWORD *)this + 160LL))(this);
        v51 = VariantClear(&a5[v47]);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
            (const char *)(unsigned int)v51,
            (int)v60);
        if ( v50 )
        {
          v49->vt = 8;
          v49->llVal = v50;
        }
      }
      break;
    }
    if ( v48 >= 0 )
    {
      v45 = v47 + 1;
      LODWORD(v47) = k;
    }
  }
  v52 = 0;
  while ( v52 != v5 )
  {
    v53 = v52 + ((unsigned int)(v5 - v52) >> 1);
    v54 = _o__wcsicmp(L"StatusDescriptions", v60[v53]);
    if ( !v54 )
    {
      v55 = &a5[v53];
      if ( v55 )
      {
        psa = 0;
        psa = SafeArrayCreateVectorEx(8u, 0, 1u, 0);
        if ( !psa )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D9,
            (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
            (const char *)0x8007000ELL,
            (int)v60);
        (*(void (__fastcall **)(VmWmiCimManagedSystemElement *, SAFEARRAY **))(*(_QWORD *)this + 168LL))(this, &psa);
        v56 = psa;
        psa = 0;
        if ( v56 )
        {
          pvt = 0;
          v57 = SafeArrayGetVartype(v56, &pvt);
          if ( v57 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6ED,
              (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
              (const char *)(unsigned int)v57,
              (int)v60);
          v58 = VariantClear(&a5[v53]);
          if ( v58 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x723,
              (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
              (const char *)(unsigned int)v58,
              (int)v60);
          v55->vt = pvt | 0x2000;
          v55->llVal = (LONGLONG)v56;
        }
        else
        {
          Vml::VmVariant::Clear((Vml::VmVariant *)&a5[v53]);
        }
        if ( psa )
        {
          v59 = SafeArrayDestroy(psa);
          if ( v59 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x330,
              (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
              (const char *)(unsigned int)v59,
              (int)v60);
        }
      }
      return;
    }
    if ( v54 >= 0 )
    {
      v52 = v53 + 1;
      LODWORD(v53) = v5;
    }
    v5 = v53;
  }
}

```

## disassembly

```asm
0x14009626c  push    rbp
0x14009626e  push    rbx
0x14009626f  push    rsi
0x140096270  push    rdi
0x140096271  push    r12
0x140096273  push    r13
0x140096275  push    r14
0x140096277  push    r15
0x140096279  mov     rbp, rsp
0x14009627c  sub     rsp, 48h
0x140096280  mov     rax, cs:__security_cookie
0x140096287  xor     rax, rsp
0x14009628a  mov     [rbp+var_10], rax
0x14009628e  mov     [rbp+var_28], r9
0x140096292  mov     edi, r8d
0x140096295  mov     r13, rcx
0x140096298  xor     ebx, ebx
0x14009629a  mov     esi, r8d
0x14009629d  mov     r12, [rbp+arg_20]
0x1400962a1  cmp     ebx, esi
0x1400962a3  jz      loc_14009634A
0x1400962a9  mov     r15d, esi
0x1400962ac  sub     r15d, ebx
0x1400962af  shr     r15d, 1
0x1400962b2  add     r15d, ebx
0x1400962b5  mov     rdx, [r9+r15*8]
0x1400962b9  lea     rcx, aCaption; "Caption"
0x1400962c0  call    cs:__imp__o__wcsicmp
0x1400962c7  nop     dword ptr [rax+rax+00h]
0x1400962cc  test    eax, eax
0x1400962ce  jz      short loc_1400962E5
0x1400962d0  mov     ecx, r15d
0x1400962d3  cmovns  ecx, esi
0x1400962d6  mov     esi, ecx
0x1400962d8  lea     ecx, [r15+1]
0x1400962dc  cmovns  ebx, ecx
0x1400962df  mov     r9, [rbp+var_28]
0x1400962e3  jmp     short loc_14009629D
0x1400962e5  lea     rax, [r15+r15*2]
0x1400962e9  lea     rbx, [r12+rax*8]
0x1400962ed  test    rbx, rbx
0x1400962f0  jz      loc_140096886
0x1400962f6  mov     rax, [r13+0]
0x1400962fa  mov     rcx, r13
0x1400962fd  mov     rax, [rax+80h]
0x140096304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096309  mov     rsi, rax
0x14009630c  mov     rcx, rbx; pvarg
0x14009630f  call    cs:__imp_VariantClear
0x140096316  nop     dword ptr [rax+rax+00h]
0x14009631b  mov     rcx, [rbp+40h]; this
0x14009631f  test    eax, eax
0x140096321  jns     short loc_140096338
0x140096323  mov     r9d, eax; char *
0x140096326  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x14009632d  mov     edx, 723h; void *
0x140096332  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140096338  mov     r9, [rbp+var_28]
0x14009633c  test    rsi, rsi
0x14009633f  jz      short loc_14009634A
0x140096341  mov     word ptr [rbx], 8
0x140096346  mov     [rbx+8], rsi
0x14009634a  xor     ebx, ebx
0x14009634c  mov     esi, edi
0x14009634e  cmp     ebx, esi
0x140096350  jz      loc_1400963EE
0x140096356  mov     r15d, esi
0x140096359  sub     r15d, ebx
0x14009635c  shr     r15d, 1
0x14009635f  add     r15d, ebx
0x140096362  mov     rdx, [r9+r15*8]
0x140096366  lea     rcx, aDescription; "Description"
0x14009636d  call    cs:__imp__o__wcsicmp
0x140096374  nop     dword ptr [rax+rax+00h]
0x140096379  test    eax, eax
0x14009637b  jz      short loc_140096391
0x14009637d  lea     ecx, [r15+1]
0x140096381  cmovns  ebx, ecx
0x140096384  cmovns  r15d, esi
0x140096388  mov     esi, r15d
0x14009638b  mov     r9, [rbp+var_28]
0x14009638f  jmp     short loc_14009634E
0x140096391  lea     rax, [r15+r15*2]
0x140096395  lea     rbx, [r12+rax*8]
0x140096399  test    rbx, rbx
0x14009639c  jz      short loc_1400963EE
0x14009639e  mov     rax, [r13+0]
0x1400963a2  mov     rcx, r13
0x1400963a5  mov     rax, [rax+88h]
0x1400963ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963b1  mov     rsi, rax
0x1400963b4  mov     rcx, rbx; pvarg
0x1400963b7  call    cs:__imp_VariantClear
0x1400963be  nop     dword ptr [rax+rax+00h]
0x1400963c3  mov     rcx, [rbp+40h]; this
0x1400963c7  test    eax, eax
0x1400963c9  jns     short loc_1400963E0
0x1400963cb  mov     r9d, eax; char *
0x1400963ce  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x1400963d5  mov     edx, 723h; void *
0x1400963da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400963e0  test    rsi, rsi
0x1400963e3  jz      short loc_1400963EE
0x1400963e5  mov     word ptr [rbx], 8
0x1400963ea  mov     [rbx+8], rsi
0x1400963ee  xor     ebx, ebx
0x1400963f0  mov     esi, edi
0x1400963f2  cmp     ebx, esi
0x1400963f4  jz      loc_140096492
0x1400963fa  mov     r15d, esi
0x1400963fd  sub     r15d, ebx
0x140096400  shr     r15d, 1
0x140096403  add     r15d, ebx
0x140096406  mov     rax, [rbp+var_28]
0x14009640a  mov     rdx, [rax+r15*8]
0x14009640e  lea     rcx, aElementname; "ElementName"
0x140096415  call    cs:__imp__o__wcsicmp
0x14009641c  nop     dword ptr [rax+rax+00h]
0x140096421  test    eax, eax
0x140096423  jz      short loc_140096435
0x140096425  lea     ecx, [r15+1]
0x140096429  cmovns  ebx, ecx
0x14009642c  cmovns  r15d, esi
0x140096430  mov     esi, r15d
0x140096433  jmp     short loc_1400963F2
0x140096435  lea     rax, [r15+r15*2]
0x140096439  lea     rbx, [r12+rax*8]
0x14009643d  test    rbx, rbx
0x140096440  jz      short loc_140096492
0x140096442  mov     rax, [r13+0]
0x140096446  mov     rcx, r13
0x140096449  mov     rax, [rax+90h]
0x140096450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096455  mov     rsi, rax
0x140096458  mov     rcx, rbx; pvarg
0x14009645b  call    cs:__imp_VariantClear
0x140096462  nop     dword ptr [rax+rax+00h]
0x140096467  mov     rcx, [rbp+40h]; this
0x14009646b  test    eax, eax
0x14009646d  jns     short loc_140096484
0x14009646f  mov     r9d, eax; char *
0x140096472  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140096479  mov     edx, 723h; void *
0x14009647e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140096484  test    rsi, rsi
0x140096487  jz      short loc_140096492
0x140096489  mov     word ptr [rbx], 8
0x14009648e  mov     [rbx+8], rsi
0x140096492  xor     ebx, ebx
0x140096494  mov     esi, edi
0x140096496  cmp     ebx, esi
0x140096498  jz      loc_14009651E
0x14009649e  mov     r15d, esi
0x1400964a1  sub     r15d, ebx
0x1400964a4  shr     r15d, 1
0x1400964a7  add     r15d, ebx
0x1400964aa  mov     rax, [rbp+var_28]
0x1400964ae  mov     rdx, [rax+r15*8]
0x1400964b2  lea     rcx, aHealthstate; "HealthState"
0x1400964b9  call    cs:__imp__o__wcsicmp
0x1400964c0  nop     dword ptr [rax+rax+00h]
0x1400964c5  test    eax, eax
0x1400964c7  jz      short loc_1400964DA
0x1400964c9  mov     ecx, r15d
0x1400964cc  cmovns  ecx, esi
0x1400964cf  mov     esi, ecx
0x1400964d1  lea     ecx, [r15+1]
0x1400964d5  cmovns  ebx, ecx
0x1400964d8  jmp     short loc_140096496
0x1400964da  lea     rax, [r15+r15*2]
0x1400964de  lea     rbx, [r12+rax*8]
0x1400964e2  test    rbx, rbx
0x1400964e5  jz      short loc_14009651E
0x1400964e7  mov     rcx, rbx; pvarg
0x1400964ea  call    cs:__imp_VariantClear
0x1400964f1  nop     dword ptr [rax+rax+00h]
0x1400964f6  mov     rcx, [rbp+40h]; this
0x1400964fa  test    eax, eax
0x1400964fc  jns     short loc_140096513
0x1400964fe  mov     r9d, eax; char *
0x140096501  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140096508  mov     edx, 723h; void *
0x14009650d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140096513  mov     word ptr [rbx], 12h
0x140096518  mov     word ptr [rbx+8], 5
0x14009651e  xor     ebx, ebx
0x140096520  mov     esi, edi
0x140096522  cmp     ebx, esi
0x140096524  jz      loc_140096663
0x14009652a  mov     r15d, esi
0x14009652d  sub     r15d, ebx
0x140096530  shr     r15d, 1
0x140096533  add     r15d, ebx
0x140096536  mov     rax, [rbp+var_28]
0x14009653a  mov     rdx, [rax+r15*8]
0x14009653e  lea     rcx, aOperationalsta; "OperationalStatus"
0x140096545  call    cs:__imp__o__wcsicmp
0x14009654c  nop     dword ptr [rax+rax+00h]
0x140096551  test    eax, eax
0x140096553  jz      short loc_140096565
0x140096555  lea     ecx, [r15+1]
0x140096559  cmovns  ebx, ecx
0x14009655c  cmovns  r15d, esi
0x140096560  mov     esi, r15d
0x140096563  jmp     short loc_140096522
0x140096565  lea     rax, [r15+r15*2]
0x140096569  lea     rbx, [r12+rax*8]
0x14009656d  test    rbx, rbx
0x140096570  jz      loc_140096663
0x140096576  mov     [rbp+psa], 0
0x14009657e  mov     ecx, 12h; vt
0x140096583  xor     r9d, r9d; pvExtra
0x140096586  xor     edx, edx; lLbound
0x140096588  lea     r8d, [rcx-11h]; cElements
0x14009658c  call    cs:__imp_SafeArrayCreateVectorEx
0x140096593  nop     dword ptr [rax+rax+00h]
0x140096598  mov     [rbp+psa], rax
0x14009659c  test    rax, rax
0x14009659f  jz      loc_14009688F
0x1400965a5  mov     rax, [r13+0]
0x1400965a9  lea     rdx, [rbp+psa]
0x1400965ad  mov     rcx, r13
0x1400965b0  mov     rax, [rax+98h]
0x1400965b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400965bc  mov     rsi, [rbp+psa]
0x1400965c0  mov     [rbp+psa], 0
0x1400965c8  test    rsi, rsi
0x1400965cb  jz      loc_14009686F
0x1400965d1  xor     eax, eax
0x1400965d3  mov     [rbp+pvt], ax
0x1400965d7  lea     rdx, [rbp+pvt]; pvt
0x1400965db  mov     rcx, rsi; psa
0x1400965de  call    cs:__imp_SafeArrayGetVartype
0x1400965e5  nop     dword ptr [rax+rax+00h]
0x1400965ea  mov     rcx, [rbp+40h]; this
0x1400965ee  test    eax, eax
0x1400965f0  jns     short loc_140096607
0x1400965f2  mov     r9d, eax; char *
0x1400965f5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x1400965fc  mov     edx, 6EDh; void *
0x140096601  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140096607  mov     rcx, rbx; pvarg
0x14009660a  call    cs:__imp_VariantClear
0x140096611  nop     dword ptr [rax+rax+00h]
0x140096616  mov     rcx, [rbp+40h]; this
0x14009661a  test    eax, eax
0x14009661c  jns     short loc_140096633
0x14009661e  mov     r9d, eax; char *
0x140096621  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140096628  mov     edx, 723h; void *
0x14009662d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140096633  movzx   eax, [rbp+pvt]
0x140096637  or      ax, 2000h
0x14009663b  mov     [rbx], ax
0x14009663e  mov     [rbx+8], rsi
0x140096642  mov     rcx, [rbp+psa]; psa
0x140096646  test    rcx, rcx
0x140096649  jz      short loc_140096663
0x14009664b  call    cs:__imp_SafeArrayDestroy
0x140096652  nop     dword ptr [rax+rax+00h]
0x140096657  mov     rcx, [rbp+40h]; this
0x14009665b  test    eax, eax
0x14009665d  js      loc_1400968AB
0x140096663  xor     ebx, ebx
0x140096665  mov     esi, edi
0x140096667  cmp     ebx, esi
0x140096669  jz      loc_1400966F9
0x14009666f  mov     r15d, esi
0x140096672  sub     r15d, ebx
0x140096675  shr     r15d, 1
0x140096678  add     r15d, ebx
0x14009667b  mov     rax, [rbp+var_28]
0x14009667f  mov     rdx, [rax+r15*8]
0x140096683  lea     rcx, aStatus; "Status"
0x14009668a  call    cs:__imp__o__wcsicmp
0x140096691  nop     dword ptr [rax+rax+00h]
0x140096696  test    eax, eax
0x140096698  jz      short loc_1400966AA
0x14009669a  lea     ecx, [r15+1]
0x14009669e  cmovns  ebx, ecx
0x1400966a1  cmovns  r15d, esi
0x1400966a5  mov     esi, r15d
0x1400966a8  jmp     short loc_140096667
0x1400966aa  lea     rax, [r15+r15*2]
0x1400966ae  lea     rbx, [r12+rax*8]
0x1400966b2  test    rbx, rbx
0x1400966b5  jz      short loc_1400966F9
0x1400966b7  mov     rax, [r13+0]
0x1400966bb  mov     rcx, r13
0x1400966be  mov     rax, [rax+0A0h]
0x1400966c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400966ca  mov     rsi, rax
0x1400966cd  mov     rcx, rbx; pvarg
0x1400966d0  call    cs:__imp_VariantClear
0x1400966d7  nop     dword ptr [rax+rax+00h]
0x1400966dc  mov     rcx, [rbp+40h]; this
0x1400966e0  test    eax, eax
0x1400966e2  jns     short loc_140096701
0x1400966e4  mov     r9d, eax; char *
0x1400966e7  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\vml\\VmVariant.h"
  ... truncated ...
```
