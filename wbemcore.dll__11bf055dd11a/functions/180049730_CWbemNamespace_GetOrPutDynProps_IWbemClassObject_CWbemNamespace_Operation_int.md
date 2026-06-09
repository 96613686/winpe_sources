# CWbemNamespace::GetOrPutDynProps(IWbemClassObject *,CWbemNamespace::Operation,int)

- ea: `0x180049730`
- end: `0x180049d2b`
- name: `?GetOrPutDynProps@CWbemNamespace@@QEAAJPEAUIWbemClassObject@@W4Operation@1@H@Z`
- size: `1531`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035668`
- `0x180048a50`
- `0x1800495b0`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x180011700`
- `0x180020870`
- `0x18002fee4`
- `0x18003cfe0`
- `0x18003d010`
- `0x180049730`
- `0x18005fbbc`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180049a9c`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180049a9c`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x180049aeb`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180049783`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180049783`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049825`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049975`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049a7d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049d1b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049825`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049975`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049a7d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180049d1b`
- `wbemcomn!GetMemLogObject` at `0x1800498f6`
- `wbemcomn!GetMemLogObject` at `0x1800499b6`
- `wbemcomn!GetMemLogObject` at `0x180049a12`
- `wbemcomn!GetMemLogObject` at `0x180049aa8`
- `wbemcomn!GetMemLogObject` at `0x180049b0e`
- `wbemcomn!GetMemLogObject` at `0x180049baf`
- `wbemcomn!GetMemLogObject` at `0x180049c42`
- `wbemcomn!GetMemLogObject` at `0x180049c9c`
- `wbemcomn!GetMemLogObject` at `0x1800498f6`
- `wbemcomn!GetMemLogObject` at `0x1800499b6`
- `wbemcomn!GetMemLogObject` at `0x180049a12`
- `wbemcomn!GetMemLogObject` at `0x180049aa8`
- `wbemcomn!GetMemLogObject` at `0x180049b0e`
- `wbemcomn!GetMemLogObject` at `0x180049baf`
- `wbemcomn!GetMemLogObject` at `0x180049c42`
- `wbemcomn!GetMemLogObject` at `0x180049c9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049901`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800499c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049a20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049ab3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049b19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049bba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049c4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049caa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049901`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800499c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049a20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049ab3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049b19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049bba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049c4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049caa`
- `OLEAUT32!__imp_VariantInit` at `0x18004979a`
- `OLEAUT32!__imp_VariantInit` at `0x18004979a`
- `OLEAUT32!__imp_VariantClear` at `0x18004981a`
- `OLEAUT32!__imp_VariantClear` at `0x1800498be`
- `OLEAUT32!__imp_VariantClear` at `0x18004996a`
- `OLEAUT32!__imp_VariantClear` at `0x180049a72`
- `OLEAUT32!__imp_VariantClear` at `0x180049d10`
- `OLEAUT32!__imp_VariantClear` at `0x18004981a`
- `OLEAUT32!__imp_VariantClear` at `0x1800498be`
- `OLEAUT32!__imp_VariantClear` at `0x18004996a`
- `OLEAUT32!__imp_VariantClear` at `0x180049a72`
- `OLEAUT32!__imp_VariantClear` at `0x180049d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall CWbemNamespace::GetOrPutDynProps(__int64 a1, __int64 a2, int a3)
{
  unsigned __int16 *v5; // r14
  __int64 v6; // rbx
  CClientCnt *v7; // rcx
  __int64 v9; // rdx
  int ObjectW; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v12; // rdx
  const unsigned __int16 *bstrVal; // r8
  CMemoryLog *v14; // rax
  CClientCnt *v15; // rcx
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  int v18; // r8d
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  int v21; // eax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  struct IWbemClassObject *v25; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-49h] BYREF
  struct IWbemContext *NewContext; // [rsp+58h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-39h] BYREF
  struct IWbemContext *v29; // [rsp+78h] [rbp-21h] BYREF
  struct IWbemClassObject *v30; // [rsp+80h] [rbp-19h] BYREF
  __int64 v31; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v32[40]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v33[24]; // [rsp+B8h] [rbp+1Fh] BYREF
  __int64 v34; // [rsp+108h] [rbp+6Fh] BYREF

  v34 = a2;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  v5 = 0;
  CVar::CVar((CVar *)v32);
  v29 = 0;
  v31 = 0;
  v30 = 0;
  VariantInit(&pvarg);
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 24LL))(v34, &v31) < 0 )
    goto LABEL_10;
  v6 = v31;
  v24 = v31;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v31 + 24LL))(
         v31,
         L"DYNPROPS",
         0,
         &pvarg,
         0) < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 321;
      goto LABEL_16;
    }
    goto LABEL_7;
  }
  if ( pvarg.iVal != -1 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 322;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v7 + 2), v9, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
    }
LABEL_7:
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v24 = 0;
LABEL_10:
    VariantClear(&pvarg);
    CVar::~CVar((CVar *)v32);
    return 0;
  }
  VariantClear(&pvarg);
  ObjectW = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL))(
              v34,
              L"__CLASS",
              0,
              &pvarg,
              0,
              0);
  if ( ObjectW < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ObjectW);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        323,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)ObjectW);
    }
    goto LABEL_28;
  }
  bstrVal = 0;
  if ( pvarg.vt == 8 )
    bstrVal = pvarg.bstrVal;
  ObjectW = CRepository::GetObjectW(
              *(struct IWmiDbSession **)(a1 + 40),
              *(struct IWmiDbHandle **)(a1 + 56),
              bstrVal,
              0,
              &v30);
  v25 = v30;
  if ( ObjectW < 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, ObjectW);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v12 = 324;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v15 + 2), v12, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ObjectW);
LABEL_27:
    CReleaseMe::release((CReleaseMe *)&v25);
LABEL_28:
    CReleaseMe::release((CReleaseMe *)&v24);
    VariantClear(&pvarg);
    CVar::~CVar((CVar *)v32);
    return (unsigned int)ObjectW;
  }
  if ( *(_QWORD *)(a1 + 248) )
  {
    NewContext = ConfigMgr::GetNewContext();
    if ( !NewContext )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          325,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749894LL);
      }
      CReleaseMe::release((CReleaseMe *)&v25);
      CReleaseMe::release((CReleaseMe *)&v24);
      VariantClear(&pvarg);
      CVar::~CVar((CVar *)v32);
      return 2147749894LL;
    }
    v26 = 0;
    ObjectW = CMUILocaleList::GetFirst_ms_XXX_Locale((CMUILocaleList *)(a1 + 176), &v26);
    if ( ObjectW < 0 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, ObjectW);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v12 = 326;
      goto LABEL_26;
    }
    MakeGuard<int (*)(void *),unsigned short *>(v33, CMUILocale::_Free, v26);
    ObjectW = CWbemNamespace::AdjustCtx((CWbemNamespace *)a1, &NewContext, v18);
    if ( ObjectW < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, ObjectW);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          327,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)ObjectW);
      }
      ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(v33);
      goto LABEL_27;
    }
    v5 = (unsigned __int16 *)NewContext;
    ObjectW = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemContext *, _QWORD, unsigned __int16 *, GUID *, struct IWbemContext **))(**(_QWORD **)(a1 + 248) + 48LL))(
                *(_QWORD *)(a1 + 248),
                0,
                NewContext,
                *(_QWORD *)(a1 + 112),
                v26,
                &IID__IWmiDynamicPropertyResolver,
                &v29);
    ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(v33);
  }
  else
  {
    ObjectW = -2147217398;
  }
  v26 = v5;
  if ( ObjectW < 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, ObjectW);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        328,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)ObjectW);
    }
    CReleaseMe::release((CReleaseMe *)&v26);
    goto LABEL_27;
  }
  NewContext = v29;
  if ( !a3 )
  {
    v21 = ((__int64 (__fastcall *)(struct IWbemContext *, unsigned __int16 *, struct IWbemClassObject *, __int64 *))v29->lpVtbl->Clone)(
            v29,
            v5,
            v30,
            &v34);
LABEL_66:
    ObjectW = v21;
    if ( v21 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, ObjectW);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        330,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)ObjectW);
    }
    CReleaseMe::release((CReleaseMe *)&NewContext);
    CReleaseMe::release((CReleaseMe *)&v26);
    goto LABEL_27;
  }
  if ( a3 == 1 )
  {
    v21 = ((__int64 (__fastcall *)(struct IWbemContext *, unsigned __int16 *, struct IWbemClassObject *, __int64))v29->lpVtbl->GetNames)(
            v29,
            v5,
            v30,
            v34);
    goto LABEL_66;
  }
  v23 = GetMemLogObject();
  CMemoryLog::Write(v23, -2147217400);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  }
  CReleaseMe::release((CReleaseMe *)&NewContext);
  CReleaseMe::release((CReleaseMe *)&v26);
  CReleaseMe::release((CReleaseMe *)&v25);
  CReleaseMe::release((CReleaseMe *)&v24);
  VariantClear(&pvarg);
  CVar::~CVar((CVar *)v32);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180049730  mov     [rsp-8+arg_0], rbx
0x180049735  mov     [rsp-8+arg_10], rsi
0x18004973a  mov     [rsp-8+arg_8], rdx
0x18004973f  push    rbp
0x180049740  push    rdi
0x180049741  push    r12
0x180049743  push    r14
0x180049745  push    r15
0x180049747  lea     rbp, [rsp-37h]
0x18004974c  sub     rsp, 0D0h
0x180049753  mov     esi, r8d
0x180049756  mov     r9, rdx
0x180049759  mov     rdi, rcx
0x18004975c  xor     r15d, r15d
0x18004975f  lea     r12, WPP_GLOBAL_Control
0x180049766  mov     rcx, cs:WPP_GLOBAL_Control
0x18004976d  cmp     rcx, r12
0x180049770  jz      short loc_18004977C
0x180049772  test    byte ptr [rcx+1Ch], 1
0x180049776  jnz     loc_180049896
0x18004977c  mov     r14, r15
0x18004977f  lea     rcx, [rbp+57h+var_60]
0x180049783  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180049789  nop
0x18004978a  mov     [rbp+57h+var_78], r15
0x18004978e  mov     [rbp+57h+var_68], r15
0x180049792  mov     [rbp+57h+var_70], r15
0x180049796  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004979a  call    cs:__imp_VariantInit
0x1800497a0  nop
0x1800497a1  mov     rcx, [rbp+57h+arg_8]
0x1800497a5  mov     rax, [rcx]
0x1800497a8  lea     rdx, [rbp+57h+var_68]
0x1800497ac  mov     rax, [rax+18h]
0x1800497b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497b5  test    eax, eax
0x1800497b7  js      short loc_180049816
0x1800497b9  mov     rbx, [rbp+57h+var_68]
0x1800497bd  mov     [rbp+57h+var_B0], rbx
0x1800497c1  mov     rcx, [rbp+57h+var_68]
0x1800497c5  mov     rax, [rcx]
0x1800497c8  mov     [rsp+0F0h+var_D0], r15
0x1800497cd  lea     r9, [rbp+57h+pvarg]
0x1800497d1  xor     r8d, r8d
0x1800497d4  lea     rdx, aDynprops; "DYNPROPS"
0x1800497db  mov     rax, [rax+18h]
0x1800497df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497e4  test    eax, eax
0x1800497e6  jns     short loc_180049849
0x1800497e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497ef  cmp     rcx, r12
0x1800497f2  jz      short loc_1800497FE
0x1800497f4  test    byte ptr [rcx+1Ch], 1
0x1800497f8  jnz     loc_180049885
0x1800497fe  test    rbx, rbx
0x180049801  jz      short loc_180049812
0x180049803  mov     rax, [rbx]
0x180049806  mov     rcx, rbx
0x180049809  mov     rax, [rax+10h]
0x18004980d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049812  mov     [rbp+57h+var_B0], r15
0x180049816  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004981a  call    cs:__imp_VariantClear
0x180049820  nop
0x180049821  lea     rcx, [rbp+57h+var_60]
0x180049825  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004982b  xor     eax, eax
0x18004982d  lea     r11, [rsp+0F0h+var_20]
0x180049835  mov     rbx, [r11+30h]
0x180049839  mov     rsi, [r11+40h]
0x18004983d  mov     rsp, r11
0x180049840  pop     r15
0x180049842  pop     r14
0x180049844  pop     r12
0x180049846  pop     rdi
0x180049847  pop     rbp
0x180049848  retn
0x180049849  cmp     word ptr [rbp+57h+pvarg+8], 0FFFFh
0x18004984e  jz      short loc_1800498BA
0x180049850  mov     rcx, cs:WPP_GLOBAL_Control
0x180049857  cmp     rcx, r12
0x18004985a  jz      short loc_1800497FE
0x18004985c  test    byte ptr [rcx+1Ch], 1
0x180049860  jz      short loc_1800497FE
0x180049862  cmp     byte ptr [rcx+19h], 2
0x180049866  jb      short loc_1800497FE
0x180049868  mov     edx, 142h
0x18004986d  xor     r9d, r9d
0x180049870  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180049877  mov     rcx, [rcx+10h]
0x18004987b  call    WPP_SF_d
0x180049880  jmp     loc_1800497FE
0x180049885  cmp     byte ptr [rcx+19h], 2
0x180049889  jb      loc_1800497FE
0x18004988f  mov     edx, 141h
0x180049894  jmp     short loc_18004986D
0x180049896  cmp     byte ptr [rcx+19h], 5
0x18004989a  jb      loc_18004977C
0x1800498a0  mov     edx, 140h
0x1800498a5  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800498ac  mov     rcx, [rcx+10h]
0x1800498b0  call    WPP_SF_q
0x1800498b5  jmp     loc_18004977C
0x1800498ba  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800498be  call    cs:__imp_VariantClear
0x1800498c4  mov     rcx, [rbp+57h+arg_8]
0x1800498c8  mov     rax, [rcx]
0x1800498cb  mov     [rsp+0F0h+var_C8], r15
0x1800498d0  mov     [rsp+0F0h+var_D0], r15
0x1800498d5  lea     r9, [rbp+57h+pvarg]
0x1800498d9  xor     r8d, r8d
0x1800498dc  lea     rdx, aClass_0; "__CLASS"
0x1800498e3  mov     rax, [rax+20h]
0x1800498e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498ec  mov     ebx, eax
0x1800498ee  test    eax, eax
0x1800498f0  jns     loc_180049982
0x1800498f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800498fc  mov     edx, ebx
0x1800498fe  mov     rcx, rax
0x180049901  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049907  mov     rcx, cs:WPP_GLOBAL_Control
0x18004990e  cmp     rcx, r12
0x180049911  jz      short loc_18004995C
0x180049913  test    byte ptr [rcx+1Ch], 1
0x180049917  jz      short loc_18004995C
0x180049919  cmp     byte ptr [rcx+19h], 2
0x18004991d  jb      short loc_18004995C
0x18004991f  mov     edx, 143h
0x180049924  mov     r9d, ebx
0x180049927  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004992e  mov     rcx, [rcx+10h]
0x180049932  call    WPP_SF_d
0x180049937  jmp     short loc_18004995C
0x180049939  mov     edx, 144h
0x18004993e  mov     r9d, ebx
0x180049941  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180049948  mov     rcx, [rcx+10h]
0x18004994c  call    WPP_SF_d
0x180049951  nop
0x180049952  lea     rcx, [rbp+57h+var_A8]; this
0x180049956  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18004995b  nop
0x18004995c  lea     rcx, [rbp+57h+var_B0]; this
0x180049960  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180049965  nop
0x180049966  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004996a  call    cs:__imp_VariantClear
0x180049970  nop
0x180049971  lea     rcx, [rbp+57h+var_60]
0x180049975  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004997b  mov     eax, ebx
0x18004997d  jmp     loc_18004982D
0x180049982  mov     r8, r15
0x180049985  cmp     word ptr [rbp+57h+pvarg], 8
0x18004998a  cmovz   r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18004998f  lea     rax, [rbp+57h+var_70]
0x180049993  mov     [rsp+0F0h+var_D0], rax; struct IWbemClassObject **
0x180049998  xor     r9d, r9d; unsigned int
0x18004999b  mov     rdx, [rdi+38h]; struct IWmiDbHandle *
0x18004999f  mov     rcx, [rdi+28h]; struct IWmiDbSession *
0x1800499a3  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x1800499a8  mov     ebx, eax
0x1800499aa  mov     rcx, [rbp+57h+var_70]
0x1800499ae  mov     [rbp+57h+var_A8], rcx
0x1800499b2  test    eax, eax
0x1800499b4  jns     short loc_1800499F0
0x1800499b6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800499bc  mov     edx, ebx
0x1800499be  mov     rcx, rax
0x1800499c1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800499c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499ce  cmp     rcx, r12
0x1800499d1  jz      loc_180049952
0x1800499d7  test    byte ptr [rcx+1Ch], 1
0x1800499db  jz      loc_180049952
0x1800499e1  cmp     byte ptr [rcx+19h], 2
0x1800499e5  jb      loc_180049952
0x1800499eb  jmp     loc_180049939
0x1800499f0  cmp     qword ptr [rdi+0F8h], 0
0x1800499f8  jnz     short loc_180049A04
0x1800499fa  mov     ebx, 8004100Ah
0x1800499ff  jmp     loc_180049BA7
0x180049a04  call    ?GetNewContext@ConfigMgr@@SAPEAUIWbemContext@@XZ; ConfigMgr::GetNewContext(void)
0x180049a09  mov     [rbp+57h+var_98], rax
0x180049a0d  test    rax, rax
0x180049a10  jnz     short loc_180049A8D
0x180049a12  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049a18  mov     edx, 80041006h
0x180049a1d  mov     rcx, rax
0x180049a20  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a2d  cmp     rcx, r12
0x180049a30  jz      short loc_180049A5A
0x180049a32  test    byte ptr [rcx+1Ch], 1
0x180049a36  jz      short loc_180049A5A
0x180049a38  cmp     byte ptr [rcx+19h], 2
0x180049a3c  jb      short loc_180049A5A
0x180049a3e  mov     edx, 145h
0x180049a43  mov     r9d, 80041006h
0x180049a49  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180049a50  mov     rcx, [rcx+10h]
0x180049a54  call    WPP_SF_d
0x180049a59  nop
0x180049a5a  lea     rcx, [rbp+57h+var_A8]; this
0x180049a5e  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180049a63  nop
0x180049a64  lea     rcx, [rbp+57h+var_B0]; this
0x180049a68  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180049a6d  nop
0x180049a6e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180049a72  call    cs:__imp_VariantClear
0x180049a78  nop
0x180049a79  lea     rcx, [rbp+57h+var_60]
0x180049a7d  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180049a83  mov     eax, 80041006h
0x180049a88  jmp     loc_18004982D
0x180049a8d  mov     [rbp+57h+var_A0], r15
0x180049a91  lea     rcx, [rdi+0B0h]
0x180049a98  lea     rdx, [rbp+57h+var_A0]
0x180049a9c  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x180049aa2  mov     ebx, eax
0x180049aa4  test    eax, eax
0x180049aa6  jns     short loc_180049AE7
0x180049aa8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049aae  mov     edx, ebx
0x180049ab0  mov     rcx, rax
0x180049ab3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ac0  cmp     rcx, r12
0x180049ac3  jz      loc_180049952
0x180049ac9  test    byte ptr [rcx+1Ch], 1
0x180049acd  jz      loc_180049952
0x180049ad3  cmp     byte ptr [rcx+19h], 2
0x180049ad7  jb      loc_180049952
0x180049add  mov     edx, 146h
0x180049ae2  jmp     loc_18004993E
0x180049ae7  mov     r8, [rbp+57h+var_A0]
0x180049aeb  mov     rdx, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180049af2  lea     rcx, [rbp+57h+var_38]
0x180049af6  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x180049afb  nop
0x180049afc  lea     rdx, [rbp+57h+var_98]; struct IWbemContext **
0x180049b00  mov     rcx, rdi; this
0x180049b03  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x180049b08  mov     ebx, eax
0x180049b0a  test    eax, eax
0x180049b0c  jns     short loc_180049B5E
0x180049b0e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049b14  mov     edx, ebx
0x180049b16  mov     rcx, rax
0x180049b19  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b26  cmp     rcx, r12
0x180049b29  jz      short loc_180049B50
0x180049b2b  test    byte ptr [rcx+1Ch], 1
0x180049b2f  jz      short loc_180049B50
0x180049b31  cmp     byte ptr [rcx+19h], 2
0x180049b35  jb      short loc_180049B50
0x180049b37  mov     edx, 147h
0x180049b3c  mov     r9d, ebx
0x180049b3f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180049b46  mov     rcx, [rcx+10h]
0x180049b4a  call    WPP_SF_d
0x180049b4f  nop
0x180049b50  lea     rcx, [rbp+57h+var_38]
0x180049b54  call    ??1?$ScopeGuardImpl1@P6AHPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(void)
0x180049b59  jmp     loc_180049952
0x180049b5e  mov     rcx, [rdi+0F8h]
0x180049b65  mov     rax, [rcx]
0x180049b68  lea     rdx, [rbp+57h+var_78]
0x180049b6c  mov     [rsp+0F0h+var_C0], rdx
0x180049b71  lea     rdx, IID__IWmiDynamicPropertyResolver
0x180049b78  mov     [rsp+0F0h+var_C8], rdx
0x180049b7d  mov     rdx, [rbp+57h+var_A0]
0x180049b81  mov     [rsp+0F0h+var_D0], rdx
0x180049b86  mov     r9, [rdi+70h]
0x180049b8a  mov     r14, [rbp+57h+var_98]
0x180049b8e  mov     r8, r14
0x180049b91  xor     edx, edx
0x180049b93  mov     rax, [rax+30h]
0x180049b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b9c  mov     ebx, eax
0x180049b9e  lea     rcx, [rbp+57h+var_38]
0x180049ba2  call    ??1?$ScopeGuardImpl1@P6AHPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(void)
0x180049ba7  mov     [rbp+57h+var_A0], r14
0x180049bab  test    ebx, ebx
0x180049bad  jns     short loc_180049BFF
0x180049baf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049bb5  mov     edx, ebx
0x180049bb7  mov     rcx, rax
0x180049bba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bc7  cmp     rcx, r12
0x180049bca  jz      short loc_180049BF1
0x180049bcc  test    byte ptr [rcx+1Ch], 1
0x180049bd0  jz      short loc_180049BF1
0x180049bd2  cmp     byte ptr [rcx+19h], 2
0x180049bd6  jb      short loc_180049BF1
0x180049bd8  mov     edx, 148h
  ... truncated ...
```
