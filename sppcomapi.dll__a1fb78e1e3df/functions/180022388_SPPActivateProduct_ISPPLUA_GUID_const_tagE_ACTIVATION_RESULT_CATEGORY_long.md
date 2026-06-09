# SPPActivateProduct(ISPPLUA *,_GUID const *,tagE_ACTIVATION_RESULT_CATEGORY *,long *)

- ea: `0x180022388`
- end: `0x180022719`
- name: `?SPPActivateProduct@@YAJPEAUISPPLUA@@PEBU_GUID@@PEAW4tagE_ACTIVATION_RESULT_CATEGORY@@PEAJ@Z`
- size: `913`
- prototype: `__int64 __fastcall(struct ISPPLUA *, const struct _GUID *, enum tagE_ACTIVATION_RESULT_CATEGORY *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021460`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004ca8`
- `0x180021e6c`
- `0x180021f9c`
- `0x180022388`
- `0x1800228d8`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180022493`
- `OLEAUT32!__imp_VariantInit` at `0x180022493`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800226a0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800226a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002252b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002252b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226d2`
- `SLC!SLOpen` at `0x180022448`
- `SLC!SLOpen` at `0x180022448`
- `SLC!SLClose` at `0x1800226ef`
- `SLC!SLClose` at `0x1800226ef`
- `SLC!SLGetLicensingStatusInformation` at `0x18002247d`
- `SLC!SLGetLicensingStatusInformation` at `0x18002247d`
- `SLC!SLGetSLIDList` at `0x180022560`
- `SLC!SLGetSLIDList` at `0x180022560`

## pseudocode

```c
__int64 __fastcall SPPActivateProduct(
        struct ISPPLUA *a1,
        const struct _GUID *a2,
        enum tagE_ACTIVATION_RESULT_CATEGORY *a3,
        int *a4)
{
  SAFEARRAY *v5; // r15
  int *v6; // r14
  int v7; // esi
  HRESULT WindowsSkuCategory; // ebx
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // r12
  SL_LICENSING_STATUS *v15; // r14
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  UINT pnStatusCount; // [rsp+38h] [rbp-49h] BYREF
  HSLC phSLC; // [rsp+40h] [rbp-41h] BYREF
  int v22; // [rsp+48h] [rbp-39h] BYREF
  int v23; // [rsp+4Ch] [rbp-35h]
  UINT pnReturnIds; // [rsp+50h] [rbp-31h] BYREF
  _tagSLLICENSINGSTATUS v25; // [rsp+54h] [rbp-2Dh] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-29h] BYREF
  SL_LICENSING_STATUS *ppLicensingStatus; // [rsp+60h] [rbp-21h] BYREF
  SAFEARRAY *v28; // [rsp+68h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-11h] BYREF
  __int128 v30; // [rsp+88h] [rbp+7h] BYREF
  IRecordInfo *pRecInfo; // [rsp+98h] [rbp+17h]
  int v32; // [rsp+F0h] [rbp+6Fh] BYREF
  int v33; // [rsp+F4h] [rbp+73h]
  enum tagE_ACTIVATION_RESULT_CATEGORY *v34; // [rsp+F8h] [rbp+77h]
  int *v35; // [rsp+100h] [rbp+7Fh]

  v35 = a4;
  v34 = a3;
  v33 = HIDWORD(a2);
  phSLC = 0;
  v23 = 0;
  v5 = 0;
  v25 = SL_LICENSING_STATUS_UNLICENSED;
  v28 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = a4;
  ppLicensingStatus = 0;
  v32 = 0;
  pnStatusCount = 0;
  v22 = 0;
  hMem = 0;
  pnReturnIds = 0;
  v7 = 1;
  WindowsSkuCategory = IsSafeMode(&v22);
  if ( WindowsSkuCategory < 0 )
    goto LABEL_2;
  if ( v22 )
  {
    WindowsSkuCategory = -2147467259;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147500037LL);
    v9 = -2147467259;
    v7 = 6;
    goto LABEL_51;
  }
  WindowsSkuCategory = SLOpen(&phSLC);
  if ( WindowsSkuCategory < 0
    || (WindowsSkuCategory = SLGetLicensingStatusInformation(
                               phSLC,
                               &WINDOWS_SLID,
                               0,
                               0,
                               &pnStatusCount,
                               &ppLicensingStatus),
        WindowsSkuCategory < 0) )
  {
LABEL_2:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)WindowsSkuCategory);
    v9 = WindowsSkuCategory;
    goto LABEL_44;
  }
  VariantInit(&pvarg);
  v12 = CSafeArrayHelperT<CEmptyType>::BuildSafeArray(v11, v10, &v28);
  WindowsSkuCategory = v12;
  if ( v12 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
    v5 = v28;
    v9 = v13;
LABEL_44:
    v18 = 0;
    while ( v9 != LODWORD(qword_180040500[v18]) )
    {
      if ( (unsigned int)++v18 >= 0x3A )
      {
        v7 = 255;
        goto LABEL_50;
      }
    }
    v7 = HIDWORD(qword_180040500[v18]);
LABEL_50:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    goto LABEL_51;
  }
  v9 = -1073418220;
  v5 = v28;
  if ( !pnStatusCount )
    v9 = -1073418219;
  v14 = 0;
  if ( pnStatusCount )
  {
    do
    {
      v15 = &ppLicensingStatus[v14];
      if ( *(_QWORD *)&v15->eStatus == 1 )
      {
        WindowsSkuCategory = CSLAggregationUtilsT<CEmptyType>::GetWindowsSkuCategory(phSLC);
        if ( WindowsSkuCategory < 0 )
          goto LABEL_48;
        if ( v23 == 1 )
          v9 = 0;
      }
      else
      {
        if ( hMem )
        {
          LocalFree(hMem);
          hMem = 0;
        }
        v16 = SLGetSLIDList(phSLC, SL_ID_PRODUCT_SKU, &v15->SkuId, SL_ID_PKEY, &pnReturnIds, (SLID **)&hMem);
        if ( v16 >= 0 )
        {
          if ( pnReturnIds )
          {
            v30 = *(_OWORD *)&pvarg.vt;
            if ( v9 == -1073418220 )
              v9 = -1073422333;
            pRecInfo = pvarg.pRecInfo;
            v17 = (*(__int64 (__fastcall **)(struct ISPPLUA *, SL_LICENSING_STATUS *, SAFEARRAY *, __int128 *))(*(_QWORD *)a1 + 24LL))(
                    a1,
                    v15,
                    v5,
                    &v30);
            if ( v17 < 0 )
            {
              if ( v9 < 0 )
                v9 = v17;
            }
            else
            {
              WindowsSkuCategory = SPPGetLicenseStatus(phSLC, &v15->SkuId, &v25, &v32);
              if ( WindowsSkuCategory < 0 )
              {
LABEL_48:
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)WindowsSkuCategory);
                v9 = WindowsSkuCategory;
                goto LABEL_43;
              }
              if ( v9 < 0 && v25 == SL_LICENSING_STATUS_LICENSED )
              {
                v9 = v32;
              }
              else if ( v9 == -1073422333
                     && (v32 == -1073418152 || v32 == -1073418141 || v32 == -1073417728 || v32 == 1074068486) )
              {
                v9 = v32;
              }
            }
          }
        }
        else if ( v16 != -1073418222 )
        {
          WindowsSkuCategory = v16;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
          v9 = WindowsSkuCategory;
          goto LABEL_43;
        }
      }
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < pnStatusCount );
    if ( WindowsSkuCategory < 0 )
      goto LABEL_41;
    v6 = v35;
  }
  if ( v9 < 0 )
  {
LABEL_41:
    if ( WindowsSkuCategory < 0 )
      v9 = WindowsSkuCategory;
LABEL_43:
    v6 = v35;
    goto LABEL_44;
  }
LABEL_51:
  *(_DWORD *)v34 = v7;
  *v6 = v9;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)WindowsSkuCategory);
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( ppLicensingStatus )
  {
    LocalFree(ppLicensingStatus);
    ppLicensingStatus = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return (unsigned int)WindowsSkuCategory;
}

```

## disassembly

```asm
0x180022388  mov     rax, rsp
0x18002238b  mov     [rax+8], rbx
0x18002238f  mov     [rax+20h], r9
0x180022393  mov     [rax+18h], r8
0x180022397  mov     [rax+10h], rdx
0x18002239b  push    rbp
0x18002239c  push    rsi
0x18002239d  push    rdi
0x18002239e  push    r12
0x1800223a0  push    r13
0x1800223a2  push    r14
0x1800223a4  push    r15
0x1800223a6  lea     rbp, [rax-5Fh]
0x1800223aa  sub     rsp, 0A0h
0x1800223b1  xor     eax, eax
0x1800223b3  mov     [rbp+57h+phSLC], 0
0x1800223bb  mov     r13, rcx
0x1800223be  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800223c2  xorps   xmm0, xmm0
0x1800223c5  mov     [rbp+57h+var_8C], eax
0x1800223c8  xor     r15d, r15d
0x1800223cb  mov     [rbp+57h+var_84], eax
0x1800223ce  lea     rcx, [rbp+57h+var_90]; int *
0x1800223d2  mov     [rbp+57h+var_70], r15
0x1800223d6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800223da  mov     r14, r9
0x1800223dd  mov     [rbp+57h+ppLicensingStatus], 0
0x1800223e5  mov     [rbp+57h+arg_8], 0
0x1800223ec  mov     [rbp+57h+var_A0], 0
0x1800223f3  mov     [rbp+57h+var_90], 0
0x1800223fa  mov     [rbp+57h+hMem], 0
0x180022402  mov     [rbp+57h+pnReturnIds], 0
0x180022409  call    ?IsSafeMode@@YAJPEAH@Z; IsSafeMode(int *)
0x18002240e  lea     esi, [r15+1]
0x180022412  mov     ebx, eax
0x180022414  test    eax, eax
0x180022416  jns     short loc_180022426
0x180022418  mov     ecx, ebx
0x18002241a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002241f  mov     edi, ebx
0x180022421  jmp     loc_180022653
0x180022426  cmp     [rbp+57h+var_90], r15d
0x18002242a  jz      short loc_180022444
0x18002242c  mov     ebx, 80004005h
0x180022431  mov     ecx, ebx
0x180022433  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022438  mov     edi, ebx
0x18002243a  mov     esi, 6
0x18002243f  jmp     loc_180022688
0x180022444  lea     rcx, [rbp+57h+phSLC]; phSLC
0x180022448  call    cs:__imp_SLOpen
0x18002244f  nop     dword ptr [rax+rax+00h]
0x180022454  mov     ebx, eax
0x180022456  test    eax, eax
0x180022458  js      short loc_180022418
0x18002245a  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18002245e  lea     rax, [rbp+57h+ppLicensingStatus]
0x180022462  mov     [rsp+28h], rax; ppLicensingStatus
0x180022467  lea     rdx, WINDOWS_SLID; pAppID
0x18002246e  lea     rax, [rbp+57h+var_A0]
0x180022472  xor     r9d, r9d; pwszRightName
0x180022475  xor     r8d, r8d; pProductSkuId
0x180022478  mov     [rsp+0D0h+pnStatusCount], rax; pnStatusCount
0x18002247d  call    cs:__imp_SLGetLicensingStatusInformation
0x180022484  nop     dword ptr [rax+rax+00h]
0x180022489  mov     ebx, eax
0x18002248b  test    eax, eax
0x18002248d  js      short loc_180022418
0x18002248f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022493  call    cs:__imp_VariantInit
0x18002249a  nop     dword ptr [rax+rax+00h]
0x18002249f  lea     r8, [rbp+57h+var_70]
0x1800224a3  call    ?BuildSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEBEKPEAPEAUtagSAFEARRAY@@@Z; CSafeArrayHelperT<CEmptyType>::BuildSafeArray(uchar const *,ulong,tagSAFEARRAY * *)
0x1800224a8  mov     ebx, eax
0x1800224aa  test    eax, eax
0x1800224ac  jns     short loc_1800224C0
0x1800224ae  mov     ecx, eax
0x1800224b0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800224b5  mov     r15, [rbp+57h+var_70]
0x1800224b9  mov     edi, ecx
0x1800224bb  jmp     loc_180022653
0x1800224c0  mov     eax, [rbp+57h+var_A0]
0x1800224c3  mov     edi, 0C004F014h
0x1800224c8  mov     r15, [rbp+57h+var_70]
0x1800224cc  test    eax, eax
0x1800224ce  lea     ecx, [rdi+1]
0x1800224d1  cmovz   edi, ecx
0x1800224d4  xor     r12d, r12d
0x1800224d7  test    eax, eax
0x1800224d9  jz      loc_180022646
0x1800224df  mov     rdx, [rbp+57h+ppLicensingStatus]
0x1800224e3  lea     rcx, [r12+r12*4]
0x1800224e7  lea     r14, [rdx+rcx*8]
0x1800224eb  cmp     [r14+10h], esi
0x1800224ef  jnz     short loc_180022522
0x1800224f1  cmp     dword ptr [r14+14h], 0
0x1800224f6  jnz     short loc_180022522
0x1800224f8  mov     rcx, [rbp+57h+phSLC]; hSLC
0x1800224fc  lea     r9, [rbp+57h+var_8C]
0x180022500  mov     r8, r14
0x180022503  call    ?GetWindowsSkuCategory@?$CSLAggregationUtilsT@VCEmptyType@@@@SAJPEAXPEBU_GUID@@1PEAW4E_LICENSE_CATEGORY@@@Z; CSLAggregationUtilsT<CEmptyType>::GetWindowsSkuCategory(void *,_GUID const *,_GUID const *,E_LICENSE_CATEGORY *)
0x180022508  mov     ebx, eax
0x18002250a  test    eax, eax
0x18002250c  js      loc_180022672
0x180022512  cmp     [rbp+57h+var_8C], esi
0x180022515  jnz     loc_18002262F
0x18002251b  xor     edi, edi
0x18002251d  jmp     loc_18002262F
0x180022522  mov     rcx, [rbp+57h+hMem]; hMem
0x180022526  test    rcx, rcx
0x180022529  jz      short loc_18002253F
0x18002252b  call    cs:__imp_LocalFree
0x180022532  nop     dword ptr [rax+rax+00h]
0x180022537  mov     [rbp+57h+hMem], 0
0x18002253f  mov     rcx, [rbp+57h+phSLC]; hSLC
0x180022543  lea     rax, [rbp+57h+hMem]
0x180022547  mov     [rsp+28h], rax; ppReturnIds
0x18002254c  mov     r9d, 4; eReturnIdType
0x180022552  lea     rax, [rbp+57h+pnReturnIds]
0x180022556  mov     r8, r14; pQueryId
0x180022559  mov     edx, esi; eQueryIdType
0x18002255b  mov     [rsp+0D0h+pnStatusCount], rax; pnReturnIds
0x180022560  call    cs:__imp_SLGetSLIDList
0x180022567  nop     dword ptr [rax+rax+00h]
0x18002256c  mov     ecx, eax
0x18002256e  test    eax, eax
0x180022570  jns     short loc_18002258B
0x180022572  cmp     eax, 0C004F012h
0x180022577  jz      loc_18002262F
0x18002257d  mov     ebx, eax
0x18002257f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022584  mov     edi, ebx
0x180022586  jmp     loc_18002264F
0x18002258b  cmp     [rbp+57h+pnReturnIds], 0
0x18002258f  jz      loc_18002262F
0x180022595  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180022599  lea     r9, [rbp+57h+var_50]
0x18002259d  mov     eax, 0C004E003h
0x1800225a2  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800225a7  cmp     edi, 0C004F014h
0x1800225ad  mov     r8, r15
0x1800225b0  movaps  [rbp+57h+var_50], xmm0
0x1800225b4  cmovz   edi, eax
0x1800225b7  movsd   [rbp+57h+var_40], xmm1
0x1800225bc  mov     rax, [r13+0]
0x1800225c0  mov     rdx, r14
0x1800225c3  mov     rcx, r13
0x1800225c6  mov     rax, [rax+18h]
0x1800225ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225cf  test    eax, eax
0x1800225d1  js      short loc_18002262A
0x1800225d3  mov     rcx, [rbp+57h+phSLC]; void *
0x1800225d7  lea     r9, [rbp+57h+arg_8]; int *
0x1800225db  lea     r8, [rbp+57h+var_84]; enum _tagSLLICENSINGSTATUS *
0x1800225df  mov     rdx, r14; struct _GUID *
0x1800225e2  call    ?SPPGetLicenseStatus@@YAJQEAXPEBU_GUID@@PEAW4_tagSLLICENSINGSTATUS@@PEAJ@Z; SPPGetLicenseStatus(void * const,_GUID const *,_tagSLLICENSINGSTATUS *,long *)
0x1800225e7  mov     ebx, eax
0x1800225e9  test    eax, eax
0x1800225eb  js      loc_180022672
0x1800225f1  test    edi, edi
0x1800225f3  jns     short loc_1800225FF
0x1800225f5  cmp     [rbp+57h+var_84], esi
0x1800225f8  jnz     short loc_1800225FF
0x1800225fa  mov     edi, [rbp+57h+arg_8]
0x1800225fd  jmp     short loc_18002262F
0x1800225ff  cmp     edi, 0C004E003h
0x180022605  jnz     short loc_18002262F
0x180022607  mov     eax, [rbp+57h+arg_8]
0x18002260a  cmp     eax, 0C004F058h
0x18002260f  jz      short loc_180022626
0x180022611  cmp     eax, 0C004F063h
0x180022616  jz      short loc_180022626
0x180022618  cmp     eax, 0C004F200h
0x18002261d  jz      short loc_180022626
0x18002261f  cmp     eax, 4004FC06h
0x180022624  jnz     short loc_18002262F
0x180022626  mov     edi, eax
0x180022628  jmp     short loc_18002262F
0x18002262a  test    edi, edi
0x18002262c  cmovs   edi, eax
0x18002262f  add     r12d, esi
0x180022632  mov     eax, ebx
0x180022634  cmp     r12d, [rbp+57h+var_A0]
0x180022638  jb      loc_1800224DF
0x18002263e  test    eax, eax
0x180022640  js      short loc_18002264A
0x180022642  mov     r14, [rbp+57h+arg_18]
0x180022646  test    edi, edi
0x180022648  jns     short loc_180022688
0x18002264a  test    ebx, ebx
0x18002264c  cmovs   edi, ebx
0x18002264f  mov     r14, [rbp+57h+arg_18]
0x180022653  xor     eax, eax
0x180022655  lea     rdx, qword_180040500
0x18002265c  movsxd  rcx, eax
0x18002265f  cmp     edi, [rdx+rcx*8]
0x180022662  jz      short loc_18002267D
0x180022664  add     eax, esi
0x180022666  cmp     eax, 3Ah ; ':'
0x180022669  jb      short loc_18002265C
0x18002266b  mov     esi, 0FFh
0x180022670  jmp     short loc_180022681
0x180022672  mov     ecx, ebx
0x180022674  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022679  mov     edi, ebx
0x18002267b  jmp     short loc_18002264F
0x18002267d  mov     esi, [rdx+rcx*8+4]
0x180022681  xor     ecx, ecx
0x180022683  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180022688  mov     rax, [rbp+57h+arg_10]
0x18002268c  mov     ecx, ebx
0x18002268e  mov     [rax], esi
0x180022690  mov     [r14], edi
0x180022693  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180022698  test    r15, r15
0x18002269b  jz      short loc_1800226AC
0x18002269d  mov     rcx, r15; psa
0x1800226a0  call    cs:__imp_SafeArrayDestroy
0x1800226a7  nop     dword ptr [rax+rax+00h]
0x1800226ac  mov     rcx, [rbp+57h+hMem]; hMem
0x1800226b0  test    rcx, rcx
0x1800226b3  jz      short loc_1800226C9
0x1800226b5  call    cs:__imp_LocalFree
0x1800226bc  nop     dword ptr [rax+rax+00h]
0x1800226c1  mov     [rbp+57h+hMem], 0
0x1800226c9  mov     rcx, [rbp+57h+ppLicensingStatus]; hMem
0x1800226cd  test    rcx, rcx
0x1800226d0  jz      short loc_1800226E6
0x1800226d2  call    cs:__imp_LocalFree
0x1800226d9  nop     dword ptr [rax+rax+00h]
0x1800226de  mov     [rbp+57h+ppLicensingStatus], 0
0x1800226e6  mov     rcx, [rbp+57h+phSLC]; hSLC
0x1800226ea  test    rcx, rcx
0x1800226ed  jz      short loc_1800226FB
0x1800226ef  call    cs:__imp_SLClose
0x1800226f6  nop     dword ptr [rax+rax+00h]
0x1800226fb  mov     eax, ebx
0x1800226fd  mov     rbx, [rsp+0D0h+arg_0]
0x180022705  add     rsp, 0A0h
0x18002270c  pop     r15
0x18002270e  pop     r14
0x180022710  pop     r13
0x180022712  pop     r12
0x180022714  pop     rdi
0x180022715  pop     rsi
0x180022716  pop     rbp
0x180022717  retn
```
