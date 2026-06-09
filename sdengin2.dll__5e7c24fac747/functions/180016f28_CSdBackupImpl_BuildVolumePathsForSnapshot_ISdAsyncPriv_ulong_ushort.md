# CSdBackupImpl::_BuildVolumePathsForSnapshot(ISdAsyncPriv *,ulong *,ushort * * *)

- ea: `0x180016f28`
- end: `0x18001773d`
- name: `?_BuildVolumePathsForSnapshot@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAKPEAPEAPEAG@Z`
- size: `2069`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct ISdAsyncPriv *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task`

## callers

- `0x180017e74`

## callees

- `0x1800081d8`
- `0x180008240`
- `0x18000b56c`
- `0x18000b654`
- `0x18000d914`
- `0x180012914`
- `0x180012998`
- `0x180014394`
- `0x180014c00`
- `0x1800156d4`
- `0x180015a24`
- `0x180015a94`
- `0x180015b38`
- `0x180015d6c`
- `0x180016f28`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800709ec`
- `0x180091e04`
- `0x18009a24c`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800173e3`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800173e3`
- `ole32!CoTaskMemFree` at `0x180017640`
- `ole32!CoTaskMemFree` at `0x180017660`
- `ole32!CoTaskMemFree` at `0x180017683`
- `ole32!CoTaskMemFree` at `0x18001769b`
- `ole32!CoTaskMemFree` at `0x180017640`
- `ole32!CoTaskMemFree` at `0x180017660`
- `ole32!CoTaskMemFree` at `0x180017683`
- `ole32!CoTaskMemFree` at `0x18001769b`
- `ole32!CoTaskMemAlloc` at `0x180017459`
- `ole32!CoTaskMemAlloc` at `0x180017459`

## string_xrefs

- `0x180016f73`: `CSdBackupImpl::_BuildVolumePathsForSnapshot`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_BuildVolumePathsForSnapshot(
        CSdBackupImpl *this,
        struct ISdAsyncPriv *a2,
        unsigned int *a3,
        unsigned __int16 ***a4)
{
  const unsigned __int16 **v7; // rdi
  struct CSxStringEntry *v8; // r14
  __int64 v9; // r12
  unsigned __int16 **v10; // r15
  __int16 v11; // ax
  int v12; // ebx
  __int16 v13; // ax
  unsigned int v14; // r8d
  __int64 i; // rsi
  CSdBackupRoot *v16; // rbx
  int UniqueVolumeForPath; // eax
  CSdBackupRoot *v18; // rcx
  ULONG v19; // eax
  unsigned __int16 **v20; // rax
  __int64 v21; // rsi
  __int64 j; // rsi
  __int64 k; // rsi
  struct CSxStringEntry *v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v27; // [rsp+3Ch] [rbp-C4h]
  __int16 v28; // [rsp+3Eh] [rbp-C2h]
  unsigned int v29; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  CSxStringEntry *v31; // [rsp+80h] [rbp-80h] BYREF
  CSdBackupRoot *v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+90h] [rbp-70h] BYREF
  int v34; // [rsp+98h] [rbp-68h] BYREF
  CSxStringMap *v35[2]; // [rsp+A0h] [rbp-60h]
  struct ISdAsyncPriv *v36; // [rsp+B0h] [rbp-50h]
  unsigned __int16 ***v37; // [rsp+B8h] [rbp-48h]
  unsigned int *v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+C8h] [rbp-38h] BYREF
  CSdRootTable *v40[2]; // [rsp+D0h] [rbp-30h]
  WCHAR szVolumeName; // [rsp+E0h] [rbp-20h] BYREF
  char v42[526]; // [rsp+E2h] [rbp-1Eh] BYREF

  v37 = a4;
  v38 = a3;
  v36 = a2;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v26,
    "CSdBackupImpl::_BuildVolumePathsForSnapshot",
    1054,
    0);
  v32 = 0;
  v39 = 0;
  *(_OWORD *)v40 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v25 = 0;
  v34 = 0;
  *(_OWORD *)v35 = 0;
  LODWORD(v9) = 0;
  v10 = 0;
  szVolumeName = 0;
  memset_0(v42, 0, 0x208u);
  v29 = 0;
  pv = 0;
  v33 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v11 = 1077;
  if ( !v36 || (v27 = 1077, v11 = 1078, !a3) || (v27 = 1078, v11 = 1079, !a4) )
  {
    v12 = -2147024809;
LABEL_7:
    v28 = v11;
LABEL_92:
    v26 = v12;
    goto LABEL_93;
  }
  v26 = 0;
  v27 = 1079;
  v12 = CSxStringMap::CreateInstance(&v25);
  v26 = v12;
  v8 = v25;
  v13 = 1081;
  if ( v12 < 0 )
  {
LABEL_11:
    v28 = v13;
    goto LABEL_93;
  }
  v27 = 1081;
  if ( (*((_BYTE *)this + 188) & 1) != 0 )
  {
    v12 = CSxList<CSdLCList,CSdLCEntry>::CSxIter::Attach(&v39, *((_QWORD *)this + 40));
    v26 = v12;
    v13 = 1085;
    if ( v12 < 0 )
      goto LABEL_11;
    v27 = 1085;
    v12 = CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(&v39, &v32);
    v26 = v12;
    v13 = 1086;
    if ( v12 < 0 )
      goto LABEL_11;
    v27 = 1086;
    if ( v12 == 1 )
    {
      *((_DWORD *)this + 47) &= ~1u;
    }
    else
    {
      while ( !v12 )
      {
        v16 = v32;
        UniqueVolumeForPath = SxGetUniqueVolumeForPath(*((const unsigned __int16 **)v32 + 8), &szVolumeName, v14);
        if ( UniqueVolumeForPath >= 0 )
        {
          if ( v7 )
            CSxStringEntry::Release((CSxStringEntry *)v7);
          v25 = 0;
          v12 = CSxStringEntry::CreateInstance(&v25);
          v26 = v12;
          v7 = (const unsigned __int16 **)v25;
          v13 = 1113;
          if ( v12 < 0 )
            goto LABEL_11;
          v27 = 1113;
          v12 = CBsString::Set((struct CSxStringEntry *)((char *)v25 + 8), &szVolumeName);
          v26 = v12;
          v13 = 1114;
          if ( v12 < 0 )
            goto LABEL_11;
          v27 = 1114;
          if ( v31 )
            CSxStringEntry::Release(v31);
          v31 = 0;
          v12 = CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(v8, v7, &v31);
          v26 = v12;
          v13 = 1117;
          if ( v12 < 0 )
            goto LABEL_11;
          v27 = 1117;
          if ( v12 == 1 )
          {
            v12 = CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(v8, v7);
            v26 = v12;
            if ( v12 < 0 )
            {
              v28 = 1120;
              goto LABEL_93;
            }
            v27 = 1120;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids,
            *((_QWORD *)v16 + 8),
            UniqueVolumeForPath);
        }
        v12 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)v36 + 120LL))(v36);
        v26 = v12;
        v13 = 1124;
        if ( v12 < 0 )
          goto LABEL_11;
        v27 = 1124;
        v18 = v32;
        if ( v32 )
        {
          v32 = 0;
          CSdBackupRoot::Release(v18);
        }
        v12 = CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(&v39, &v32);
        v26 = v12;
        v13 = 1127;
        if ( v12 < 0 )
          goto LABEL_11;
        v27 = 1127;
      }
    }
  }
  if ( (*((_BYTE *)this + 188) & 2) != 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, LPVOID *))(**((_QWORD **)this + 88) + 136LL))(
            *((_QWORD *)this + 88),
            0,
            &v29,
            &pv);
    v26 = v12;
    v13 = 1136;
    if ( v12 < 0 )
      goto LABEL_11;
    v27 = 1136;
    for ( i = 0; (unsigned int)i < v29; i = (unsigned int)(i + 1) )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 88) + 80LL))(
              *((_QWORD *)this + 88),
              *((_QWORD *)pv + i),
              &v33);
      v26 = v12;
      v13 = 1141;
      if ( v12 < 0 )
        goto LABEL_11;
      v27 = 1141;
      if ( v12 == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)&WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids,
            *((_QWORD *)pv + i),
            v33);
        v26 = 0;
      }
      else
      {
        if ( v7 )
          CSxStringEntry::Release((CSxStringEntry *)v7);
        v25 = 0;
        v12 = CSxStringEntry::CreateInstance(&v25);
        v26 = v12;
        v7 = (const unsigned __int16 **)v25;
        v13 = 1151;
        if ( v12 < 0 )
          goto LABEL_11;
        v27 = 1151;
        v12 = CBsString::Set((struct CSxStringEntry *)((char *)v25 + 8), *((const unsigned __int16 **)pv + i));
        v26 = v12;
        v13 = 1152;
        if ( v12 < 0 )
          goto LABEL_11;
        v27 = 1152;
        if ( v31 )
          CSxStringEntry::Release(v31);
        v31 = 0;
        v12 = CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(v8, v7, &v31);
        v26 = v12;
        v13 = 1155;
        if ( v12 < 0 )
          goto LABEL_11;
        v27 = 1155;
        if ( v12 == 1 )
        {
          v12 = CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(v8, v7);
          v26 = v12;
          v13 = 1158;
          if ( v12 < 0 )
            goto LABEL_11;
          v27 = 1158;
        }
      }
    }
  }
  v19 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v8);
  v9 = v19;
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids);
    v12 = -2130706177;
    v11 = 1170;
    goto LABEL_7;
  }
  v11 = 1174;
  if ( (unsigned int)v9 >= 0xFFFF )
  {
    v12 = -2130706378;
    goto LABEL_7;
  }
  v26 = 0;
  v27 = 1174;
  v20 = (unsigned __int16 **)CoTaskMemAlloc(8 * v9);
  v10 = v20;
  if ( !v20 )
  {
    v12 = -2147024882;
    v28 = 1176;
    goto LABEL_92;
  }
  v26 = 0;
  v27 = 1176;
  memset_0(v20, 0, 8 * v9);
  if ( v7 )
    CSxStringEntry::Release((CSxStringEntry *)v7);
  v7 = 0;
  v25 = 0;
  if ( !v8 )
  {
    v12 = -2147024809;
LABEL_74:
    v11 = 1182;
    goto LABEL_7;
  }
  if ( v35[0] )
  {
    v12 = -2147418113;
    goto LABEL_74;
  }
  v35[0] = v8;
  _InterlockedIncrement((volatile signed __int32 *)v8 + 4);
  v34 = *((_DWORD *)v35[0] + 2);
  v35[1] = 0;
  v26 = 0;
  v27 = 1182;
  v12 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v34, &v25);
  v26 = v12;
  if ( v12 >= 0 )
  {
    v27 = 1183;
    v21 = 0;
    while ( !v12 && (unsigned int)v21 < (unsigned int)v9 )
    {
      v7 = (const unsigned __int16 **)v25;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids,
          *((_QWORD *)v25 + 1));
      v12 = SdSafeDuplicateStr(&v10[v21], v7[1]);
      v26 = v12;
      v13 = 1192;
      if ( v12 < 0 )
        goto LABEL_11;
      v27 = 1192;
      v12 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)v36 + 120LL))(v36);
      v26 = v12;
      v13 = 1194;
      if ( v12 < 0 )
        goto LABEL_11;
      v27 = 1194;
      if ( v7 )
      {
        v25 = 0;
        CSxStringEntry::Release((CSxStringEntry *)v7);
      }
      v12 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v34, &v25);
      v26 = v12;
      if ( v12 < 0 )
      {
        v28 = 1197;
        goto LABEL_77;
      }
      v21 = (unsigned int)(v21 + 1);
      v27 = 1197;
    }
    *v37 = v10;
    v10 = 0;
    *v38 = v9;
    v12 = 0;
    v27 = 1205;
    v7 = (const unsigned __int16 **)v25;
    goto LABEL_92;
  }
  v28 = 1183;
LABEL_77:
  v7 = (const unsigned __int16 **)v25;
LABEL_93:
  if ( pv )
  {
    for ( j = 0; (unsigned int)j < v29; j = (unsigned int)(j + 1) )
    {
      CoTaskMemFree(*((LPVOID *)pv + j));
      *((_QWORD *)pv + j) = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    v12 = v26;
  }
  if ( v10 )
  {
    for ( k = 0; (unsigned int)k < (unsigned int)v9; k = (unsigned int)(k + 1) )
    {
      CoTaskMemFree(v10[k]);
      v10[k] = 0;
    }
    CoTaskMemFree(v10);
    v12 = v26;
  }
  if ( v35[0] )
  {
    CSxStringMap::Release(v35[0]);
    v35[0] = 0;
  }
  v34 = 0;
  v35[1] = 0;
  if ( v8 )
    CSxStringMap::Release(v8);
  if ( v31 )
    CSxStringEntry::Release(v31);
  if ( v7 )
    CSxStringEntry::Release((CSxStringEntry *)v7);
  if ( v40[1] )
    CSdRootTable::Release(v40[1]);
  if ( v32 )
    CSdBackupRoot::Release(v32);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180016f28  push    rbp
0x180016f2a  push    rbx
0x180016f2b  push    rsi
0x180016f2c  push    rdi
0x180016f2d  push    r12
0x180016f2f  push    r13
0x180016f31  push    r14
0x180016f33  push    r15
0x180016f35  lea     rbp, [rsp-208h]
0x180016f3d  sub     rsp, 308h
0x180016f44  mov     rax, cs:__security_cookie
0x180016f4b  xor     rax, rsp
0x180016f4e  mov     [rbp+240h+var_50], rax
0x180016f55  mov     rsi, r9
0x180016f58  mov     [rbp+240h+var_288], r9
0x180016f5c  mov     rbx, r8
0x180016f5f  mov     [rbp+240h+var_280], rbx
0x180016f63  mov     [rbp+240h+var_290], rdx
0x180016f67  mov     r13, rcx
0x180016f6a  xor     r9d, r9d; unsigned __int16
0x180016f6d  mov     r8d, 41Eh; unsigned __int16
0x180016f73  lea     rdx, aCsdbackupimplB; "CSdBackupImpl::_BuildVolumePathsForSnap"...
0x180016f7a  lea     rcx, [rsp+340h+var_308]; this
0x180016f7f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016f84  xor     eax, eax
0x180016f86  mov     [rbp+240h+var_2B8], rax
0x180016f8a  mov     [rbp+240h+var_278], eax
0x180016f8d  xorps   xmm0, xmm0
0x180016f90  movdqu  xmmword ptr [rbp+240h+var_270], xmm0
0x180016f95  mov     edi, eax
0x180016f97  mov     [rbp+240h+var_2C0], rax
0x180016f9b  mov     r14d, eax
0x180016f9e  mov     [rsp+340h+var_310], rax
0x180016fa3  mov     [rbp+240h+var_2A8], eax
0x180016fa6  movdqu  xmmword ptr [rbp+240h+var_2A0], xmm0
0x180016fab  mov     r12d, eax
0x180016fae  mov     r15d, eax
0x180016fb1  mov     [rbp+240h+szVolumeName], ax
0x180016fb5  xor     edx, edx; Val
0x180016fb7  mov     r8d, 208h; Size
0x180016fbd  lea     rcx, [rbp+240h+var_25E]; void *
0x180016fc1  call    memset_0
0x180016fc6  xor     ecx, ecx
0x180016fc8  mov     [rsp+340h+var_2CC], ecx
0x180016fcc  mov     [rsp+340h+pv], rcx
0x180016fd1  mov     [rbp+240h+var_2B0], ecx
0x180016fd4  test    rsi, rsi
0x180016fd7  jz      short loc_180016FDC
0x180016fd9  mov     [rsi], rcx
0x180016fdc  test    rbx, rbx
0x180016fdf  jz      short loc_180016FE3
0x180016fe1  mov     [rbx], ecx
0x180016fe3  mov     eax, 435h
0x180016fe8  cmp     [rbp+240h+var_290], rcx
0x180016fec  jnz     short loc_180016FFD
0x180016fee  mov     ebx, 80070057h
0x180016ff3  mov     [rsp+340h+var_302], ax
0x180016ff8  jmp     loc_180017623
0x180016ffd  mov     [rsp+340h+var_304], ax
0x180017002  mov     eax, 436h
0x180017007  test    rbx, rbx
0x18001700a  jz      short loc_180016FEE
0x18001700c  mov     [rsp+340h+var_304], ax
0x180017011  mov     eax, 437h
0x180017016  test    rsi, rsi
0x180017019  jz      short loc_180016FEE
0x18001701b  mov     [rsp+340h+var_308], ecx
0x18001701f  mov     [rsp+340h+var_304], ax
0x180017024  lea     rcx, [rsp+340h+var_310]; struct CSxStringMap **
0x180017029  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001702e  mov     ebx, eax
0x180017030  mov     [rsp+340h+var_308], eax
0x180017034  mov     r14, [rsp+340h+var_310]
0x180017039  test    eax, eax
0x18001703b  mov     eax, 439h
0x180017040  jns     short loc_18001704C
0x180017042  mov     [rsp+340h+var_302], ax
0x180017047  jmp     loc_180017627
0x18001704c  mov     [rsp+340h+var_304], ax
0x180017051  test    byte ptr [r13+0BCh], 1
0x180017059  jz      short loc_1800170B1
0x18001705b  mov     rdx, [r13+140h]
0x180017062  lea     rcx, [rbp+240h+var_278]
0x180017066  call    ?Attach@CSxIter@?$CSxList@VCSdLCList@@VCSdLCEntry@@@@QEAAJPEAVCSdLCList@@@Z; CSxList<CSdLCList,CSdLCEntry>::CSxIter::Attach(CSdLCList *)
0x18001706b  mov     ebx, eax
0x18001706d  mov     [rsp+340h+var_308], eax
0x180017071  test    eax, eax
0x180017073  mov     eax, 43Dh
0x180017078  js      short loc_180017042
0x18001707a  mov     [rsp+340h+var_304], ax
0x18001707f  lea     rdx, [rbp+240h+var_2B8]
0x180017083  lea     rcx, [rbp+240h+var_278]
0x180017087  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x18001708c  mov     ebx, eax
0x18001708e  mov     [rsp+340h+var_308], eax
0x180017092  test    eax, eax
0x180017094  mov     eax, 43Eh
0x180017099  js      short loc_180017042
0x18001709b  mov     [rsp+340h+var_304], ax
0x1800170a0  cmp     ebx, 1
0x1800170a3  jnz     loc_18001718C
0x1800170a9  and     dword ptr [r13+0BCh], 0FFFFFFFEh
0x1800170b1  test    byte ptr [r13+0BCh], 2
0x1800170b9  jz      loc_1800173E0
0x1800170bf  mov     rcx, [r13+2C0h]
0x1800170c6  mov     rax, [rcx]
0x1800170c9  lea     r9, [rsp+340h+pv]
0x1800170ce  lea     r8, [rsp+340h+var_2CC]
0x1800170d3  xor     edx, edx
0x1800170d5  mov     rax, [rax+88h]
0x1800170dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e1  mov     ebx, eax
0x1800170e3  mov     [rsp+340h+var_308], eax
0x1800170e7  test    eax, eax
0x1800170e9  mov     eax, 470h
0x1800170ee  js      loc_180017042
0x1800170f4  mov     [rsp+340h+var_304], ax
0x1800170f9  xor     esi, esi
0x1800170fb  cmp     esi, [rsp+340h+var_2CC]
0x1800170ff  jnb     loc_1800173E0
0x180017105  mov     rcx, [r13+2C0h]
0x18001710c  mov     rax, [rcx]
0x18001710f  lea     r8, [rbp+240h+var_2B0]
0x180017113  mov     rdx, [rsp+340h+pv]
0x180017118  mov     rdx, [rdx+rsi*8]
0x18001711c  mov     rax, [rax+50h]
0x180017120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017125  mov     ebx, eax
0x180017127  mov     [rsp+340h+var_308], eax
0x18001712b  test    eax, eax
0x18001712d  mov     eax, 475h
0x180017132  js      loc_180017042
0x180017138  mov     [rsp+340h+var_304], ax
0x18001713d  cmp     ebx, 1
0x180017140  jnz     loc_180017315
0x180017146  mov     rcx, cs:WPP_GLOBAL_Control
0x18001714d  lea     rax, WPP_GLOBAL_Control
0x180017154  cmp     rcx, rax
0x180017157  jz      short loc_180017182
0x180017159  test    byte ptr [rcx+1Ch], 40h
0x18001715d  jz      short loc_180017182
0x18001715f  lea     edx, [rbx+19h]
0x180017162  mov     eax, [rbp+240h+var_2B0]
0x180017165  mov     [rsp+340h+var_320], eax
0x180017169  mov     r9, [rsp+340h+pv]
0x18001716e  mov     r9, [r9+rsi*8]
0x180017172  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x180017179  mov     rcx, [rcx+10h]
0x18001717d  call    WPP_SF_Sd
0x180017182  mov     [rsp+340h+var_308], r12d
0x180017187  jmp     loc_1800173D9
0x18001718c  mov     esi, 460h
0x180017191  test    ebx, ebx
0x180017193  jnz     loc_1800170B1
0x180017199  mov     rbx, [rbp+240h+var_2B8]
0x18001719d  lea     rdx, [rbp+240h+szVolumeName]; lpszVolumeName
0x1800171a1  mov     rcx, [rbx+40h]; unsigned __int16 *
0x1800171a5  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x1800171aa  test    eax, eax
0x1800171ac  jns     short loc_1800171F1
0x1800171ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171b5  lea     rdx, WPP_GLOBAL_Control
0x1800171bc  cmp     rcx, rdx
0x1800171bf  jz      loc_1800172A7
0x1800171c5  test    byte ptr [rcx+1Ch], 40h
0x1800171c9  jz      loc_1800172A7
0x1800171cf  mov     edx, 19h
0x1800171d4  mov     [rsp+340h+var_320], eax
0x1800171d8  mov     r9, [rbx+40h]
0x1800171dc  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x1800171e3  mov     rcx, [rcx+10h]
0x1800171e7  call    WPP_SF_Sd
0x1800171ec  jmp     loc_1800172A7
0x1800171f1  test    rdi, rdi
0x1800171f4  jz      short loc_1800171FE
0x1800171f6  mov     rcx, rdi; this
0x1800171f9  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x1800171fe  mov     [rsp+340h+var_310], r12
0x180017203  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x180017208  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x18001720d  mov     ebx, eax
0x18001720f  mov     [rsp+340h+var_308], eax
0x180017213  mov     rdi, [rsp+340h+var_310]
0x180017218  test    eax, eax
0x18001721a  mov     eax, 459h
0x18001721f  js      loc_180017042
0x180017225  mov     [rsp+340h+var_304], ax
0x18001722a  lea     rcx, [rdi+8]; this
0x18001722e  lea     rdx, [rbp+240h+szVolumeName]; unsigned __int16 *
0x180017232  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180017237  mov     ebx, eax
0x180017239  mov     [rsp+340h+var_308], eax
0x18001723d  test    eax, eax
0x18001723f  mov     eax, 45Ah
0x180017244  js      loc_180017042
0x18001724a  mov     [rsp+340h+var_304], ax
0x18001724f  mov     rcx, [rbp+240h+var_2C0]; this
0x180017253  test    rcx, rcx
0x180017256  jz      short loc_18001725D
0x180017258  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x18001725d  mov     [rbp+240h+var_2C0], r12
0x180017261  lea     r8, [rbp+240h+var_2C0]
0x180017265  mov     rdx, rdi
0x180017268  mov     rcx, r14
0x18001726b  call    ?Find@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@QEAAJPEAVCSxRuleTree@@PEAPEAV2@@Z; CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(CSxRuleTree *,CSxRuleTree * *)
0x180017270  mov     ebx, eax
0x180017272  mov     [rsp+340h+var_308], eax
0x180017276  test    eax, eax
0x180017278  mov     eax, 45Dh
0x18001727d  js      loc_180017042
0x180017283  mov     [rsp+340h+var_304], ax
0x180017288  cmp     ebx, 1
0x18001728b  jnz     short loc_1800172A7
0x18001728d  mov     rdx, rdi
0x180017290  mov     rcx, r14
0x180017293  call    ?Insert@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAVCSxStringEntry@@PEAPEAV2@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(CSxStringEntry *,CSxStringEntry * *)
0x180017298  mov     ebx, eax
0x18001729a  mov     [rsp+340h+var_308], eax
0x18001729e  test    eax, eax
0x1800172a0  js      short loc_18001730B
0x1800172a2  mov     [rsp+340h+var_304], si
0x1800172a7  mov     rcx, [rbp+240h+var_290]
0x1800172ab  mov     rax, [rcx]
0x1800172ae  mov     rax, [rax+78h]
0x1800172b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172b7  mov     ebx, eax
0x1800172b9  mov     [rsp+340h+var_308], eax
0x1800172bd  test    eax, eax
0x1800172bf  mov     eax, 464h
0x1800172c4  js      loc_180017042
0x1800172ca  mov     [rsp+340h+var_304], ax
0x1800172cf  mov     rcx, [rbp+240h+var_2B8]; this
0x1800172d3  test    rcx, rcx
0x1800172d6  jz      short loc_1800172E1
0x1800172d8  mov     [rbp+240h+var_2B8], r12
0x1800172dc  call    ?Release@CSdBackupRoot@@QEAAKXZ; CSdBackupRoot::Release(void)
0x1800172e1  lea     rdx, [rbp+240h+var_2B8]
0x1800172e5  lea     rcx, [rbp+240h+var_278]
0x1800172e9  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x1800172ee  mov     ebx, eax
0x1800172f0  mov     [rsp+340h+var_308], eax
0x1800172f4  test    eax, eax
0x1800172f6  mov     eax, 467h
0x1800172fb  js      loc_180017042
0x180017301  mov     [rsp+340h+var_304], ax
0x180017306  jmp     loc_180017191
0x18001730b  mov     [rsp+340h+var_302], si
0x180017310  jmp     loc_180017627
0x180017315  test    rdi, rdi
0x180017318  jz      short loc_180017322
0x18001731a  mov     rcx, rdi; this
0x18001731d  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017322  mov     [rsp+340h+var_310], r12
0x180017327  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x18001732c  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x180017331  mov     ebx, eax
0x180017333  mov     [rsp+340h+var_308], eax
0x180017337  mov     rdi, [rsp+340h+var_310]
0x18001733c  test    eax, eax
0x18001733e  mov     eax, 47Fh
0x180017343  js      loc_180017042
0x180017349  mov     [rsp+340h+var_304], ax
0x18001734e  lea     rcx, [rdi+8]; this
0x180017352  mov     rdx, [rsp+340h+pv]
0x180017357  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x18001735b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180017360  mov     ebx, eax
0x180017362  mov     [rsp+340h+var_308], eax
0x180017366  test    eax, eax
0x180017368  mov     eax, 480h
0x18001736d  js      loc_180017042
0x180017373  mov     [rsp+340h+var_304], ax
0x180017378  mov     rcx, [rbp+240h+var_2C0]; this
0x18001737c  test    rcx, rcx
0x18001737f  jz      short loc_180017386
0x180017381  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017386  mov     [rbp+240h+var_2C0], r12
0x18001738a  lea     r8, [rbp+240h+var_2C0]
0x18001738e  mov     rdx, rdi
0x180017391  mov     rcx, r14
0x180017394  call    ?Find@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@QEAAJPEAVCSxRuleTree@@PEAPEAV2@@Z; CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(CSxRuleTree *,CSxRuleTree * *)
0x180017399  mov     ebx, eax
0x18001739b  mov     [rsp+340h+var_308], eax
0x18001739f  test    eax, eax
0x1800173a1  mov     eax, 483h
0x1800173a6  js      loc_180017042
0x1800173ac  mov     [rsp+340h+var_304], ax
0x1800173b1  cmp     ebx, 1
0x1800173b4  jnz     short loc_1800173D9
0x1800173b6  mov     rdx, rdi
0x1800173b9  mov     rcx, r14
0x1800173bc  call    ?Insert@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAVCSxStringEntry@@PEAPEAV2@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(CSxStringEntry *,CSxStringEntry * *)
0x1800173c1  mov     ebx, eax
0x1800173c3  mov     [rsp+340h+var_308], eax
0x1800173c7  test    eax, eax
0x1800173c9  mov     eax, 486h
0x1800173ce  js      loc_180017042
0x1800173d4  mov     [rsp+340h+var_304], ax
0x1800173d9  inc     esi
0x1800173db  jmp     loc_1800170FB
  ... truncated ...
```
