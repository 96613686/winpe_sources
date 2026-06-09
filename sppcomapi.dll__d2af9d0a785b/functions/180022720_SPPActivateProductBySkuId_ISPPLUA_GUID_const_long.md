# SPPActivateProductBySkuId(ISPPLUA *,_GUID const *,long *)

- ea: `0x180022720`
- end: `0x1800228d2`
- name: `?SPPActivateProductBySkuId@@YAJPEAUISPPLUA@@PEBU_GUID@@PEAJ@Z`
- size: `434`
- prototype: `int(struct ISPPLUA *, const struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021530`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004ca8`
- `0x180021f9c`
- `0x18002214c`
- `0x180022720`
- `0x1800228d8`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800227a7`
- `OLEAUT32!__imp_VariantInit` at `0x1800227a7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180022897`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180022897`
- `SLC!SLOpen` at `0x180022808`
- `SLC!SLOpen` at `0x180022808`
- `SLC!SLClose` at `0x1800228ac`
- `SLC!SLClose` at `0x1800228ac`
- `SLC!SLSetGenuineInformation` at `0x180022868`
- `SLC!SLSetGenuineInformation` at `0x180022868`

## string_xrefs

- `0x180022855`: `SL_LAST_ACT_ATTEMPT_HRESULT`

## pseudocode

```c
__int64 __fastcall SPPActivateProductBySkuId(struct ISPPLUA *a1, const struct _GUID *a2, int *a3)
{
  SAFEARRAY *v3; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 (__fastcall *v13)(struct ISPPLUA *, const struct _GUID *, SAFEARRAY *, VARIANTARG *); // rax
  int v14; // r14d
  HRESULT v15; // eax
  __int64 v16; // rcx
  enum _tagSLLICENSINGSTATUS v18; // [rsp+30h] [rbp-50h] BYREF
  SAFEARRAY *v19; // [rsp+38h] [rbp-48h] BYREF
  HSLC phSLC; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v22; // [rsp+60h] [rbp-20h] BYREF
  int pbValue; // [rsp+B0h] [rbp+30h] BYREF
  int v24; // [rsp+C8h] [rbp+48h] BYREF

  phSLC = 0;
  v3 = 0;
  v24 = 0;
  v19 = 0;
  pbValue = 0;
  v18 = SL_LICENSING_STATUS_UNLICENSED;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !a1 || !a2 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_18;
  }
  v9 = IsSafeMode(&v24);
  v8 = v9;
  if ( v9 < 0 )
  {
LABEL_6:
    v7 = (unsigned int)v9;
    goto LABEL_3;
  }
  if ( v24 )
  {
    v8 = -2147467259;
    v7 = 2147500037LL;
    goto LABEL_3;
  }
  VariantInit(&pvarg);
  v12 = CSafeArrayHelperT<CEmptyType>::BuildSafeArray(v11, v10, &v19);
  v8 = v12;
  if ( v12 >= 0 )
  {
    v3 = v19;
    v13 = *(__int64 (__fastcall **)(struct ISPPLUA *, const struct _GUID *, SAFEARRAY *, VARIANTARG *))(*(_QWORD *)a1 + 24LL);
    v22 = pvarg;
    v14 = v13(a1, a2, v19, &v22);
    v9 = SLOpen(&phSLC);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_6;
    v9 = SPPGetLicenseStatus(phSLC, a2, &v18, &pbValue);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_6;
    if ( v14 >= 0 )
    {
      v14 = pbValue;
      if ( v18 != SL_LICENSING_STATUS_LICENSED )
      {
        v15 = SLSetGenuineInformation(a2, L"SL_LAST_ACT_ATTEMPT_HRESULT", SL_DATA_BINARY, 4u, (const BYTE *)&pbValue);
        if ( v15 < 0 )
          CSLEventLogT<CEmptyType>::LogEventHR(v16, 3221233667LL, (unsigned int)v15);
      }
    }
    *a3 = v14;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
    v3 = v19;
  }
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v3 )
    SafeArrayDestroy(v3);
  if ( phSLC )
    SLClose(phSLC);
  return v8;
}

```

## disassembly

```asm
0x180022720  mov     [rsp-28h+arg_8], rbx
0x180022725  push    rbp
0x180022726  push    rsi
0x180022727  push    rdi
0x180022728  push    r14
0x18002272a  push    r15
0x18002272c  mov     rbp, rsp
0x18002272f  sub     rsp, 80h
0x180022736  xor     eax, eax
0x180022738  mov     [rbp+phSLC], 0
0x180022740  xor     edi, edi
0x180022742  mov     [rbp+arg_18], 0
0x180022749  mov     qword ptr [rbp+pvarg+10h], rax
0x18002274d  xorps   xmm0, xmm0
0x180022750  mov     [rbp+var_48], rdi
0x180022754  mov     r15, r8
0x180022757  mov     [rbp+arg_0], eax
0x18002275a  mov     rsi, rdx
0x18002275d  mov     [rbp+var_50], eax
0x180022760  mov     r14, rcx
0x180022763  movups  xmmword ptr [rbp+pvarg], xmm0
0x180022767  test    rcx, rcx
0x18002276a  jnz     short loc_18002277D
0x18002276c  mov     ecx, 80070057h
0x180022771  mov     ebx, ecx
0x180022773  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022778  jmp     loc_180022888
0x18002277d  test    rsi, rsi
0x180022780  jz      short loc_18002276C
0x180022782  lea     rcx, [rbp+arg_18]; int *
0x180022786  call    ?IsSafeMode@@YAJPEAH@Z; IsSafeMode(int *)
0x18002278b  mov     ebx, eax
0x18002278d  test    eax, eax
0x18002278f  jns     short loc_180022795
0x180022791  mov     ecx, eax
0x180022793  jmp     short loc_180022773
0x180022795  cmp     [rbp+arg_18], edi
0x180022798  jz      short loc_1800227A3
0x18002279a  mov     ebx, 80004005h
0x18002279f  mov     ecx, ebx
0x1800227a1  jmp     short loc_180022773
0x1800227a3  lea     rcx, [rbp+pvarg]; pvarg
0x1800227a7  call    cs:__imp_VariantInit
0x1800227ae  nop     dword ptr [rax+rax+00h]
0x1800227b3  lea     r8, [rbp+var_48]
0x1800227b7  call    ?BuildSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEBEKPEAPEAUtagSAFEARRAY@@@Z; CSafeArrayHelperT<CEmptyType>::BuildSafeArray(uchar const *,ulong,tagSAFEARRAY * *)
0x1800227bc  mov     ebx, eax
0x1800227be  test    eax, eax
0x1800227c0  jns     short loc_1800227D2
0x1800227c2  mov     ecx, eax
0x1800227c4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800227c9  mov     rdi, [rbp+var_48]
0x1800227cd  jmp     loc_180022888
0x1800227d2  mov     rax, [r14]
0x1800227d5  lea     r9, [rbp+var_20]
0x1800227d9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800227dd  mov     rdx, rsi
0x1800227e0  mov     rdi, [rbp+var_48]
0x1800227e4  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800227e9  mov     r8, rdi
0x1800227ec  mov     rax, [rax+18h]
0x1800227f0  mov     rcx, r14
0x1800227f3  movaps  [rbp+var_20], xmm0
0x1800227f7  movsd   [rbp+var_10], xmm1
0x1800227fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022801  lea     rcx, [rbp+phSLC]; phSLC
0x180022805  mov     r14d, eax
0x180022808  call    cs:__imp_SLOpen
0x18002280f  nop     dword ptr [rax+rax+00h]
0x180022814  mov     ebx, eax
0x180022816  test    eax, eax
0x180022818  js      loc_180022791
0x18002281e  mov     rcx, [rbp+phSLC]; void *
0x180022822  lea     r9, [rbp+arg_0]; int *
0x180022826  lea     r8, [rbp+var_50]; enum _tagSLLICENSINGSTATUS *
0x18002282a  mov     rdx, rsi; struct _GUID *
0x18002282d  call    ?SPPGetLicenseStatus@@YAJQEAXPEBU_GUID@@PEAW4_tagSLLICENSINGSTATUS@@PEAJ@Z; SPPGetLicenseStatus(void * const,_GUID const *,_tagSLLICENSINGSTATUS *,long *)
0x180022832  mov     ebx, eax
0x180022834  test    eax, eax
0x180022836  js      loc_180022791
0x18002283c  test    r14d, r14d
0x18002283f  js      short loc_180022885
0x180022841  cmp     [rbp+var_50], 1
0x180022845  mov     r14d, [rbp+arg_0]
0x180022849  jz      short loc_180022885
0x18002284b  mov     r9d, 4; cbValue
0x180022851  lea     rax, [rbp+arg_0]
0x180022855  lea     rdx, aSlLastActAttem; "SL_LAST_ACT_ATTEMPT_HRESULT"
0x18002285c  mov     [rsp+80h+pbValue], rax; pbValue
0x180022861  mov     rcx, rsi; pQueryId
0x180022864  lea     r8d, [r9-1]; eDataType
0x180022868  call    cs:__imp_SLSetGenuineInformation
0x18002286f  nop     dword ptr [rax+rax+00h]
0x180022874  test    eax, eax
0x180022876  jns     short loc_180022885
0x180022878  mov     r8d, eax
0x18002287b  mov     edx, 0C0002003h
0x180022880  call    ?LogEventHR@?$CSLEventLogT@VCEmptyType@@@@SAXGIJPEBG00@Z; CSLEventLogT<CEmptyType>::LogEventHR(ushort,uint,long,ushort const *,ushort const *,ushort const *)
0x180022885  mov     [r15], r14d
0x180022888  mov     ecx, ebx
0x18002288a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002288f  test    rdi, rdi
0x180022892  jz      short loc_1800228A3
0x180022894  mov     rcx, rdi; psa
0x180022897  call    cs:__imp_SafeArrayDestroy
0x18002289e  nop     dword ptr [rax+rax+00h]
0x1800228a3  mov     rcx, [rbp+phSLC]; hSLC
0x1800228a7  test    rcx, rcx
0x1800228aa  jz      short loc_1800228B8
0x1800228ac  call    cs:__imp_SLClose
0x1800228b3  nop     dword ptr [rax+rax+00h]
0x1800228b8  mov     eax, ebx
0x1800228ba  mov     rbx, [rsp+80h+arg_8]
0x1800228c2  add     rsp, 80h
0x1800228c9  pop     r15
0x1800228cb  pop     r14
0x1800228cd  pop     rdi
0x1800228ce  pop     rsi
0x1800228cf  pop     rbp
0x1800228d0  retn
```
