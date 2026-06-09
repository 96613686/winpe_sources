# CSdBackupImpl::_BuildVolumePathsForSnapshot(ISdAsyncPriv *,ulong *,ushort * * *)

- ea: `0x1800178cc`
- end: `0x180018106`
- name: `?_BuildVolumePathsForSnapshot@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAKPEAPEAPEAG@Z`
- size: `2106`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct ISdAsyncPriv *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task`

## callers

- `0x180018874`

## callees

- `0x180008370`
- `0x1800083e4`
- `0x18000b894`
- `0x18000b97c`
- `0x18000dd9c`
- `0x18001316c`
- `0x1800131f0`
- `0x180014c30`
- `0x1800154f4`
- `0x180016014`
- `0x18001637c`
- `0x1800163f0`
- `0x18001649c`
- `0x1800166d0`
- `0x1800178cc`
- `0x180072e08`
- `0x180072f14`
- `0x1800739f8`
- `0x180095fd4`
- `0x18009e904`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180017d87`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180017d87`
- `ole32!CoTaskMemFree` at `0x180017ff0`
- `ole32!CoTaskMemFree` at `0x180018016`
- `ole32!CoTaskMemFree` at `0x18001803f`
- `ole32!CoTaskMemFree` at `0x18001805d`
- `ole32!CoTaskMemFree` at `0x180017ff0`
- `ole32!CoTaskMemFree` at `0x180018016`
- `ole32!CoTaskMemFree` at `0x18001803f`
- `ole32!CoTaskMemFree` at `0x18001805d`
- `ole32!CoTaskMemAlloc` at `0x180017e03`
- `ole32!CoTaskMemAlloc` at `0x180017e03`

## string_xrefs

- `0x180017917`: `CSdBackupImpl::_BuildVolumePathsForSnapshot`

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
    0x41Eu,
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
0x1800178cc  push    rbp
0x1800178ce  push    rbx
0x1800178cf  push    rsi
0x1800178d0  push    rdi
0x1800178d1  push    r12
0x1800178d3  push    r13
0x1800178d5  push    r14
0x1800178d7  push    r15
0x1800178d9  lea     rbp, [rsp-208h]
0x1800178e1  sub     rsp, 308h
0x1800178e8  mov     rax, cs:__security_cookie
0x1800178ef  xor     rax, rsp
0x1800178f2  mov     [rbp+240h+var_50], rax
0x1800178f9  mov     rsi, r9
0x1800178fc  mov     [rbp+240h+var_288], r9
0x180017900  mov     rbx, r8
0x180017903  mov     [rbp+240h+var_280], rbx
0x180017907  mov     [rbp+240h+var_290], rdx
0x18001790b  mov     r13, rcx
0x18001790e  xor     r9d, r9d; unsigned __int16
0x180017911  mov     r8d, 41Eh; unsigned __int16
0x180017917  lea     rdx, aCsdbackupimplB; "CSdBackupImpl::_BuildVolumePathsForSnap"...
0x18001791e  lea     rcx, [rsp+340h+var_308]; this
0x180017923  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017928  xor     eax, eax
0x18001792a  mov     [rbp+240h+var_2B8], rax
0x18001792e  mov     [rbp+240h+var_278], eax
0x180017931  xorps   xmm0, xmm0
0x180017934  movdqu  xmmword ptr [rbp+240h+var_270], xmm0
0x180017939  mov     edi, eax
0x18001793b  mov     [rbp+240h+var_2C0], rax
0x18001793f  mov     r14d, eax
0x180017942  mov     [rsp+340h+var_310], rax
0x180017947  mov     [rbp+240h+var_2A8], eax
0x18001794a  movdqu  xmmword ptr [rbp+240h+var_2A0], xmm0
0x18001794f  mov     r12d, eax
0x180017952  mov     r15d, eax
0x180017955  mov     [rbp+240h+szVolumeName], ax
0x180017959  xor     edx, edx; Val
0x18001795b  mov     r8d, 208h; Size
0x180017961  lea     rcx, [rbp+240h+var_25E]; void *
0x180017965  call    memset_0
0x18001796a  xor     ecx, ecx
0x18001796c  mov     [rsp+340h+var_2CC], ecx
0x180017970  mov     [rsp+340h+pv], rcx
0x180017975  mov     [rbp+240h+var_2B0], ecx
0x180017978  test    rsi, rsi
0x18001797b  jz      short loc_180017980
0x18001797d  mov     [rsi], rcx
0x180017980  test    rbx, rbx
0x180017983  jz      short loc_180017987
0x180017985  mov     [rbx], ecx
0x180017987  mov     eax, 435h
0x18001798c  cmp     [rbp+240h+var_290], rcx
0x180017990  jnz     short loc_1800179A1
0x180017992  mov     ebx, 80070057h
0x180017997  mov     [rsp+340h+var_302], ax
0x18001799c  jmp     loc_180017FD3
0x1800179a1  mov     [rsp+340h+var_304], ax
0x1800179a6  mov     eax, 436h
0x1800179ab  test    rbx, rbx
0x1800179ae  jz      short loc_180017992
0x1800179b0  mov     [rsp+340h+var_304], ax
0x1800179b5  mov     eax, 437h
0x1800179ba  test    rsi, rsi
0x1800179bd  jz      short loc_180017992
0x1800179bf  mov     [rsp+340h+var_308], ecx
0x1800179c3  mov     [rsp+340h+var_304], ax
0x1800179c8  lea     rcx, [rsp+340h+var_310]; struct CSxStringMap **
0x1800179cd  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x1800179d2  mov     ebx, eax
0x1800179d4  mov     [rsp+340h+var_308], eax
0x1800179d8  mov     r14, [rsp+340h+var_310]
0x1800179dd  test    eax, eax
0x1800179df  mov     eax, 439h
0x1800179e4  jns     short loc_1800179F0
0x1800179e6  mov     [rsp+340h+var_302], ax
0x1800179eb  jmp     loc_180017FD7
0x1800179f0  mov     [rsp+340h+var_304], ax
0x1800179f5  test    byte ptr [r13+0BCh], 1
0x1800179fd  jz      short loc_180017A55
0x1800179ff  mov     rdx, [r13+140h]
0x180017a06  lea     rcx, [rbp+240h+var_278]
0x180017a0a  call    ?Attach@CSxIter@?$CSxList@VCSdLCList@@VCSdLCEntry@@@@QEAAJPEAVCSdLCList@@@Z; CSxList<CSdLCList,CSdLCEntry>::CSxIter::Attach(CSdLCList *)
0x180017a0f  mov     ebx, eax
0x180017a11  mov     [rsp+340h+var_308], eax
0x180017a15  test    eax, eax
0x180017a17  mov     eax, 43Dh
0x180017a1c  js      short loc_1800179E6
0x180017a1e  mov     [rsp+340h+var_304], ax
0x180017a23  lea     rdx, [rbp+240h+var_2B8]
0x180017a27  lea     rcx, [rbp+240h+var_278]
0x180017a2b  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x180017a30  mov     ebx, eax
0x180017a32  mov     [rsp+340h+var_308], eax
0x180017a36  test    eax, eax
0x180017a38  mov     eax, 43Eh
0x180017a3d  js      short loc_1800179E6
0x180017a3f  mov     [rsp+340h+var_304], ax
0x180017a44  cmp     ebx, 1
0x180017a47  jnz     loc_180017B30
0x180017a4d  and     dword ptr [r13+0BCh], 0FFFFFFFEh
0x180017a55  test    byte ptr [r13+0BCh], 2
0x180017a5d  jz      loc_180017D84
0x180017a63  mov     rcx, [r13+2C0h]
0x180017a6a  mov     rax, [rcx]
0x180017a6d  lea     r9, [rsp+340h+pv]
0x180017a72  lea     r8, [rsp+340h+var_2CC]
0x180017a77  xor     edx, edx
0x180017a79  mov     rax, [rax+88h]
0x180017a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a85  mov     ebx, eax
0x180017a87  mov     [rsp+340h+var_308], eax
0x180017a8b  test    eax, eax
0x180017a8d  mov     eax, 470h
0x180017a92  js      loc_1800179E6
0x180017a98  mov     [rsp+340h+var_304], ax
0x180017a9d  xor     esi, esi
0x180017a9f  cmp     esi, [rsp+340h+var_2CC]
0x180017aa3  jnb     loc_180017D84
0x180017aa9  mov     rcx, [r13+2C0h]
0x180017ab0  mov     rax, [rcx]
0x180017ab3  lea     r8, [rbp+240h+var_2B0]
0x180017ab7  mov     rdx, [rsp+340h+pv]
0x180017abc  mov     rdx, [rdx+rsi*8]
0x180017ac0  mov     rax, [rax+50h]
0x180017ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ac9  mov     ebx, eax
0x180017acb  mov     [rsp+340h+var_308], eax
0x180017acf  test    eax, eax
0x180017ad1  mov     eax, 475h
0x180017ad6  js      loc_1800179E6
0x180017adc  mov     [rsp+340h+var_304], ax
0x180017ae1  cmp     ebx, 1
0x180017ae4  jnz     loc_180017CB9
0x180017aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180017af1  lea     rax, WPP_GLOBAL_Control
0x180017af8  cmp     rcx, rax
0x180017afb  jz      short loc_180017B26
0x180017afd  test    byte ptr [rcx+1Ch], 40h
0x180017b01  jz      short loc_180017B26
0x180017b03  lea     edx, [rbx+19h]
0x180017b06  mov     eax, [rbp+240h+var_2B0]
0x180017b09  mov     [rsp+340h+var_320], eax
0x180017b0d  mov     r9, [rsp+340h+pv]
0x180017b12  mov     r9, [r9+rsi*8]
0x180017b16  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x180017b1d  mov     rcx, [rcx+10h]
0x180017b21  call    WPP_SF_Sd
0x180017b26  mov     [rsp+340h+var_308], r12d
0x180017b2b  jmp     loc_180017D7D
0x180017b30  mov     esi, 460h
0x180017b35  test    ebx, ebx
0x180017b37  jnz     loc_180017A55
0x180017b3d  mov     rbx, [rbp+240h+var_2B8]
0x180017b41  lea     rdx, [rbp+240h+szVolumeName]; lpszVolumeName
0x180017b45  mov     rcx, [rbx+40h]; unsigned __int16 *
0x180017b49  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180017b4e  test    eax, eax
0x180017b50  jns     short loc_180017B95
0x180017b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b59  lea     rdx, WPP_GLOBAL_Control
0x180017b60  cmp     rcx, rdx
0x180017b63  jz      loc_180017C4B
0x180017b69  test    byte ptr [rcx+1Ch], 40h
0x180017b6d  jz      loc_180017C4B
0x180017b73  mov     edx, 19h
0x180017b78  mov     [rsp+340h+var_320], eax
0x180017b7c  mov     r9, [rbx+40h]
0x180017b80  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x180017b87  mov     rcx, [rcx+10h]
0x180017b8b  call    WPP_SF_Sd
0x180017b90  jmp     loc_180017C4B
0x180017b95  test    rdi, rdi
0x180017b98  jz      short loc_180017BA2
0x180017b9a  mov     rcx, rdi; this
0x180017b9d  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017ba2  mov     [rsp+340h+var_310], r12
0x180017ba7  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x180017bac  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x180017bb1  mov     ebx, eax
0x180017bb3  mov     [rsp+340h+var_308], eax
0x180017bb7  mov     rdi, [rsp+340h+var_310]
0x180017bbc  test    eax, eax
0x180017bbe  mov     eax, 459h
0x180017bc3  js      loc_1800179E6
0x180017bc9  mov     [rsp+340h+var_304], ax
0x180017bce  lea     rcx, [rdi+8]; this
0x180017bd2  lea     rdx, [rbp+240h+szVolumeName]; unsigned __int16 *
0x180017bd6  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180017bdb  mov     ebx, eax
0x180017bdd  mov     [rsp+340h+var_308], eax
0x180017be1  test    eax, eax
0x180017be3  mov     eax, 45Ah
0x180017be8  js      loc_1800179E6
0x180017bee  mov     [rsp+340h+var_304], ax
0x180017bf3  mov     rcx, [rbp+240h+var_2C0]; this
0x180017bf7  test    rcx, rcx
0x180017bfa  jz      short loc_180017C01
0x180017bfc  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017c01  mov     [rbp+240h+var_2C0], r12
0x180017c05  lea     r8, [rbp+240h+var_2C0]
0x180017c09  mov     rdx, rdi
0x180017c0c  mov     rcx, r14
0x180017c0f  call    ?Find@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@QEAAJPEAVCSxRuleTree@@PEAPEAV2@@Z; CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(CSxRuleTree *,CSxRuleTree * *)
0x180017c14  mov     ebx, eax
0x180017c16  mov     [rsp+340h+var_308], eax
0x180017c1a  test    eax, eax
0x180017c1c  mov     eax, 45Dh
0x180017c21  js      loc_1800179E6
0x180017c27  mov     [rsp+340h+var_304], ax
0x180017c2c  cmp     ebx, 1
0x180017c2f  jnz     short loc_180017C4B
0x180017c31  mov     rdx, rdi
0x180017c34  mov     rcx, r14
0x180017c37  call    ?Insert@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAVCSxStringEntry@@PEAPEAV2@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(CSxStringEntry *,CSxStringEntry * *)
0x180017c3c  mov     ebx, eax
0x180017c3e  mov     [rsp+340h+var_308], eax
0x180017c42  test    eax, eax
0x180017c44  js      short loc_180017CAF
0x180017c46  mov     [rsp+340h+var_304], si
0x180017c4b  mov     rcx, [rbp+240h+var_290]
0x180017c4f  mov     rax, [rcx]
0x180017c52  mov     rax, [rax+78h]
0x180017c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c5b  mov     ebx, eax
0x180017c5d  mov     [rsp+340h+var_308], eax
0x180017c61  test    eax, eax
0x180017c63  mov     eax, 464h
0x180017c68  js      loc_1800179E6
0x180017c6e  mov     [rsp+340h+var_304], ax
0x180017c73  mov     rcx, [rbp+240h+var_2B8]; this
0x180017c77  test    rcx, rcx
0x180017c7a  jz      short loc_180017C85
0x180017c7c  mov     [rbp+240h+var_2B8], r12
0x180017c80  call    ?Release@CSdBackupRoot@@QEAAKXZ; CSdBackupRoot::Release(void)
0x180017c85  lea     rdx, [rbp+240h+var_2B8]
0x180017c89  lea     rcx, [rbp+240h+var_278]
0x180017c8d  call    ?Next@CSxIter@?$CSxList@VCSdSubstitutePathList@@VCSdSubstitutePath@@@@QEAAJPEAPEAVCSdSubstitutePath@@@Z; CSxList<CSdSubstitutePathList,CSdSubstitutePath>::CSxIter::Next(CSdSubstitutePath * *)
0x180017c92  mov     ebx, eax
0x180017c94  mov     [rsp+340h+var_308], eax
0x180017c98  test    eax, eax
0x180017c9a  mov     eax, 467h
0x180017c9f  js      loc_1800179E6
0x180017ca5  mov     [rsp+340h+var_304], ax
0x180017caa  jmp     loc_180017B35
0x180017caf  mov     [rsp+340h+var_302], si
0x180017cb4  jmp     loc_180017FD7
0x180017cb9  test    rdi, rdi
0x180017cbc  jz      short loc_180017CC6
0x180017cbe  mov     rcx, rdi; this
0x180017cc1  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017cc6  mov     [rsp+340h+var_310], r12
0x180017ccb  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x180017cd0  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x180017cd5  mov     ebx, eax
0x180017cd7  mov     [rsp+340h+var_308], eax
0x180017cdb  mov     rdi, [rsp+340h+var_310]
0x180017ce0  test    eax, eax
0x180017ce2  mov     eax, 47Fh
0x180017ce7  js      loc_1800179E6
0x180017ced  mov     [rsp+340h+var_304], ax
0x180017cf2  lea     rcx, [rdi+8]; this
0x180017cf6  mov     rdx, [rsp+340h+pv]
0x180017cfb  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x180017cff  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180017d04  mov     ebx, eax
0x180017d06  mov     [rsp+340h+var_308], eax
0x180017d0a  test    eax, eax
0x180017d0c  mov     eax, 480h
0x180017d11  js      loc_1800179E6
0x180017d17  mov     [rsp+340h+var_304], ax
0x180017d1c  mov     rcx, [rbp+240h+var_2C0]; this
0x180017d20  test    rcx, rcx
0x180017d23  jz      short loc_180017D2A
0x180017d25  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x180017d2a  mov     [rbp+240h+var_2C0], r12
0x180017d2e  lea     r8, [rbp+240h+var_2C0]
0x180017d32  mov     rdx, rdi
0x180017d35  mov     rcx, r14
0x180017d38  call    ?Find@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@QEAAJPEAVCSxRuleTree@@PEAPEAV2@@Z; CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::Find(CSxRuleTree *,CSxRuleTree * *)
0x180017d3d  mov     ebx, eax
0x180017d3f  mov     [rsp+340h+var_308], eax
0x180017d43  test    eax, eax
0x180017d45  mov     eax, 483h
0x180017d4a  js      loc_1800179E6
0x180017d50  mov     [rsp+340h+var_304], ax
0x180017d55  cmp     ebx, 1
0x180017d58  jnz     short loc_180017D7D
0x180017d5a  mov     rdx, rdi
0x180017d5d  mov     rcx, r14
0x180017d60  call    ?Insert@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAVCSxStringEntry@@PEAPEAV2@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::Insert(CSxStringEntry *,CSxStringEntry * *)
0x180017d65  mov     ebx, eax
0x180017d67  mov     [rsp+340h+var_308], eax
0x180017d6b  test    eax, eax
0x180017d6d  mov     eax, 486h
0x180017d72  js      loc_1800179E6
0x180017d78  mov     [rsp+340h+var_304], ax
0x180017d7d  inc     esi
0x180017d7f  jmp     loc_180017A9F
  ... truncated ...
```
