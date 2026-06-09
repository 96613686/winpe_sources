# UnionFs::UfsUnionCtx::EnsureParentPathInScratch(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,bool,UnionFs::UfsPathName const &,bool,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsLayerCtx const &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x1400605e4`
- end: `0x140060ed1`
- name: `?EnsureParentPathInScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBVUfsPathName@2@_N23AEBVUfsStreamHandleCtx@2@AEBVUfsLayerCtx@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `2285`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_INSTANCE *, const struct UnionFs::UfsPathName *, bool, const struct UnionFs::UfsPathName *, bool, const struct UnionFs::UfsStreamHandleCtx *, const struct UnionFs::UfsLayerCtx *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140060ed8`
- `0x140061f2c`

## callees

- `0x14000efd0`
- `0x14000f7fc`
- `0x14000fdc8`
- `0x140028d54`
- `0x140036128`
- `0x1400438e4`
- `0x14004452c`
- `0x140044bac`
- `0x140044cd4`
- `0x140056ac4`
- `0x140056afc`
- `0x1400605e4`
- `0x14006bca8`
- `0x140077774`
- `0x14007843c`
- `0x140079c48`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400607e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060962`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006098d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060e87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400607e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060962`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006098d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060c7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060e87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060eb1`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140060ae4`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140060ae4`
- `ntoskrnl!PsGetHostSilo` at `0x140060ac9`
- `ntoskrnl!PsGetHostSilo` at `0x140060ac9`

## string_xrefs

- `0x1400606be`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`
- `0x14006072b`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`
- `0x1400607af`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x14006082e`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x140060938`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x140060be2`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x140060c56`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x140060e3a`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x14006079e`: `PUSH: Creating layer path`
- `0x140060d62`: `(scratchSearchPath.Length + nextComponentLength) <= scratchSearchPath.MaximumLength`
- `0x140060d35`: `(fullLayerName->PathLength() + nextComponentLength) <= fullLayerName->PathMaximumLength()`
- `0x140060e29`: `PUSH: Copying item from layer`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
        UnionFs::UfsUnionCtx *this,
        struct _UNICODE_STRING *a2,
        const struct _FLT_INSTANCE *a3,
        const struct UnionFs::UfsPathName *a4,
        bool a5,
        const struct UnionFs::UfsPathName *a6,
        bool a7,
        const struct UnionFs::UfsStreamHandleCtx *a8,
        const struct UnionFs::UfsLayerCtx *a9,
        struct _FILE_OBJECT *a10,
        const struct UnionFs::UfsSiloCtx *a11)
{
  const struct UnionFs::UfsPathName *v11; // r12
  __int64 v12; // r9
  __int64 v13; // r8
  utl::_RefCountBase *v14; // rsi
  signed __int32 v15; // edx
  signed __int32 v16; // eax
  int OpenedScratchRootPath; // ebx
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned __int16 NormalizedLayerRootPath; // ax
  int v21; // esi
  const unsigned __int16 *v22; // r8
  struct _UNICODE_STRING *v23; // rdx
  struct _UNICODE_STRING *v24; // rbx
  __int128 v25; // xmm0
  char *v26; // rdx
  __int16 v27; // cx
  unsigned __int16 *v28; // rbx
  unsigned __int16 v29; // r14
  __int64 v30; // r13
  _WORD *v31; // r15
  __int64 v32; // r8
  __int64 v33; // rsi
  __int16 v34; // dx
  struct _UNICODE_STRING *v35; // rdx
  __int16 v37; // r12
  PVOID v38; // rsi
  unsigned __int64 v39; // r13
  unsigned __int64 v40; // rdx
  _WORD *v41; // rsi
  __int64 v42; // rdx
  __int64 HostSilo; // r14
  struct _TXN_PARAMETER_BLOCK *TransactionParameterBlock; // rax
  int v45; // r14d
  __int16 FinalStatus_high; // ax
  unsigned __int16 v47; // ax
  __int64 v48; // rcx
  bool v49; // zf
  __int64 *v50; // r13
  int v51; // r12d
  int v52; // r14d
  __int16 v53; // dx
  int v54; // eax
  __int64 v55; // r11
  struct _UNICODE_STRING *v56; // rdx
  struct _UNICODE_STRING *v57; // rdx
  char *v58; // [rsp+28h] [rbp-D8h]
  char *v59; // [rsp+28h] [rbp-D8h]
  char *v60; // [rsp+28h] [rbp-D8h]
  char v61; // [rsp+50h] [rbp-B0h]
  _BYTE v62[28]; // [rsp+54h] [rbp-ACh] BYREF
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  ULONG v65; // [rsp+88h] [rbp-78h]
  PVOID v66[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h]
  __int64 *v68; // [rsp+A8h] [rbp-58h]
  struct _FLT_INSTANCE *v69; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING *v70; // [rsp+B8h] [rbp-48h]
  const struct UnionFs::UfsLayerCtx *v71; // [rsp+C0h] [rbp-40h]
  UnionFs::UfsUnionCtx *v72; // [rsp+C8h] [rbp-38h]
  const struct UnionFs::UfsPathName *v73; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING v74; // [rsp+E0h] [rbp-20h] BYREF
  char v75[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v76; // [rsp+F8h] [rbp-8h]
  utl::_RefCountBase *v77[2]; // [rsp+100h] [rbp+0h]
  __int128 v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+120h] [rbp+20h]
  struct _UNICODE_STRING v80; // [rsp+130h] [rbp+30h] BYREF
  char v81; // [rsp+140h] [rbp+40h]
  PWSTR *p_Buffer; // [rsp+1A0h] [rbp+A0h]
  char v83[80]; // [rsp+1B0h] [rbp+B0h] BYREF

  v11 = a4;
  v68 = (__int64 *)a11;
  v73 = a4;
  v69 = a3;
  v70 = a2;
  v72 = this;
  v71 = a9;
  UnicodeString = 0;
  *(_WORD *)&v62[4] = 0;
  if ( a5 )
  {
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, a2);
    v13 = *((_QWORD *)a8 + 2);
    v14 = 0;
    UnicodeString = 0;
    if ( !v13 )
      goto LABEL_6;
    v15 = *(_DWORD *)(v13 + 8);
    if ( !v15 )
      goto LABEL_6;
    while ( 1 )
    {
      v16 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 8), v15 + 1, v15);
      if ( v15 == v16 )
        break;
      v15 = v16;
      if ( !v16 )
        goto LABEL_6;
    }
    v19 = *((_QWORD *)a8 + 1);
    v14 = (utl::_RefCountBase *)*((_QWORD *)a8 + 2);
    if ( !v19 )
    {
LABEL_6:
      OpenedScratchRootPath = -1058209784;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED0008LL,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x3D6000A06FELL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath",
        "ORIGIN: No scratch layer in streamhandle ctx",
        v58);
LABEL_7:
      if ( v14 )
        utl::_RefCountBase::_DecStrong(v14);
      v18 = 0x123002004C7LL;
      goto LABEL_23;
    }
    LOBYTE(v12) = 1;
    OpenedScratchRootPath = UnionFs::UfsPathName::AsUnicodeString(*(_QWORD *)(v19 + 16), &UnicodeString, a10, v12);
    if ( OpenedScratchRootPath < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)OpenedScratchRootPath,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x1B5000A0706LL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath",
        "PUSH: AsUnicodeString",
        v58);
      goto LABEL_7;
    }
    if ( v14 )
      utl::_RefCountBase::_DecStrong(v14);
  }
  else
  {
    OpenedScratchRootPath = UnionFs::UfsStreamHandleCtx::GetOpenedScratchRootPath(a8, &UnicodeString, a10, &v62[4]);
    if ( OpenedScratchRootPath < 0 )
    {
      v18 = 0x1B6002004D0LL;
LABEL_23:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)OpenedScratchRootPath,
        (int)a10,
        (struct UnionFs::StackEventTracer *)v18,
        (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
        "PUSH: Getting scratch root",
        v58);
      goto LABEL_112;
    }
  }
  v74 = 0;
  NormalizedLayerRootPath = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(a9, &v74, 1);
  P = 0;
  v21 = UnionFs::UfsPathName::ReplacePathPrefix(
          (_DWORD)a6,
          (unsigned int)&UnicodeString,
          (unsigned int)&v74,
          NormalizedLayerRootPath,
          (__int64)&P,
          (_DWORD)a10);
  if ( v21 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v21,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x105002004E0LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
      "PUSH: Creating layer path",
      v59);
    v24 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v24, v23);
      ExFreePoolWithTag(v24, 0);
    }
    OpenedScratchRootPath = v21;
    goto LABEL_112;
  }
  v25 = *(_OWORD *)v11;
  v65 = (!a7 + 8) << 6;
  *(_WORD *)&v62[4] = *((_WORD *)v11 + 12);
  *(_WORD *)v62 = *(_WORD *)&v62[4];
  *(_OWORD *)&v62[12] = v25;
  UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&v62[12], (struct _UNICODE_STRING *)v62, v22);
  v27 = *(_WORD *)&v62[12];
  v28 = (unsigned __int16 *)P;
  v29 = *(_WORD *)&v62[12] - 2;
  v67 = -1;
  v30 = -1;
  *(__m128i *)v66 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v31 = v66[1];
  LOBYTE(v32) = 0;
  v61 = 0;
  while ( 1 )
  {
    *(_WORD *)v62 = v29;
    if ( *(_WORD *)v11 < 2u || (v33 = *(_QWORD *)&v62[20]) == 0 )
    {
LABEL_32:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000003ALL,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x107002004FFLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
        "ORIGIN: FindCharReverse",
        v59);
      if ( v66[0] != (PVOID)-1LL && v66[0] )
        ExFreePoolWithTag(v66[0], 0);
      if ( v28 )
      {
        if ( !*((_BYTE *)v28 + 16) )
          *(_OWORD *)v28 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v28, v35);
        ExFreePoolWithTag(v28, 0);
      }
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v35);
      return 3221225530LL;
    }
    if ( (v29 & 1) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("*StartPos % sizeof(WCHAR) == 0", v26);
      v27 = *(_WORD *)&v62[12];
      LOBYTE(v32) = v61;
    }
    v34 = v29 >> 1;
    while ( *(_WORD *)(v33 + 2LL * v34) != 92 )
    {
      if ( --v34 < 0 )
        goto LABEL_32;
    }
    v37 = v27 - 2 * v34;
    if ( (_BYTE)v32 )
      break;
LABEL_48:
    *(_WORD *)&v62[12] = v27 - v37;
    UnionFs::UfsPathName::PathLength((UnionFs::UfsPathName *)v28, *v28 - v37);
    v27 = *(_WORD *)&v62[12];
    v41 = v66[0];
    if ( *(_WORD *)&v62[12] == *(_WORD *)&v62[4] )
    {
      *(_WORD *)&v62[12] += 2;
      UnionFs::UfsPathName::PathLength((UnionFs::UfsPathName *)v28, *v28 + 2);
      goto LABEL_86;
    }
    if ( v37 == 2 )
    {
      LOBYTE(v32) = v61;
      goto LABEL_61;
    }
    v80.Buffer = (PWSTR)off_14007E740;
    p_Buffer = &v80.Buffer;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a10, &v80);
    memset(v83, 0, 0x48u);
    LODWORD(P) = !a7;
    if ( v68 )
      HostSilo = *v68;
    else
      HostSilo = PsGetHostSilo(!a7, v42);
    TransactionParameterBlock = IoGetTransactionParameterBlock(*(PFILE_OBJECT *)(*(_QWORD *)&v70[1].Length + 8LL));
    v45 = UnionFs::Utils::StatItem(
            (struct _UNICODE_STRING *)&v62[12],
            v69,
            v65,
            HostSilo,
            (char)P,
            v83,
            (int)a10,
            TransactionParameterBlock,
            0);
    FinalStatus_high = HIWORD(a10[2].FinalStatus);
    v32 = 1;
    if ( FinalStatus_high )
    {
      v47 = FinalStatus_high - 1;
      HIWORD(a10[2].FinalStatus) = v47;
      v26 = (char *)(120 * (v47 + 1LL));
      v48 = *(_QWORD *)((char *)&a10->Type + (_QWORD)v26);
      *(_QWORD *)((char *)&a10->Type + (_QWORD)v26) = 0;
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v48 + 24LL))(v48, v26, 1);
        v32 = 1;
      }
    }
    if ( v45 >= 0 )
    {
      if ( !v61 )
      {
LABEL_77:
        if ( v41 != (_WORD *)-1LL && v41 )
          ExFreePoolWithTag(v41, 0);
        if ( v28 )
        {
          if ( !*((_BYTE *)v28 + 16) )
            *(_OWORD *)v28 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v28, (struct _UNICODE_STRING *)v26);
          ExFreePoolWithTag(v28, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, (struct _UNICODE_STRING *)v26);
        return 0;
      }
LABEL_86:
      v50 = v68;
      v51 = (int)v71;
      while ( v41 != v31 )
      {
        v52 = (unsigned __int16)*--v31;
        if ( v52 + (unsigned int)*v28 > v28[1] )
          MicrosoftTelemetryAssertTriggeredMsgKM(
            "(fullLayerName->PathLength() + nextComponentLength) <= fullLayerName->PathMaximumLength()",
            v26,
            v32);
        UnionFs::UfsPathName::PathLength((UnionFs::UfsPathName *)v28, *v28 + v52);
        v53 = *(_WORD *)&v62[12];
        if ( v52 + (unsigned int)*(unsigned __int16 *)&v62[12] > *(unsigned __int16 *)&v62[14] )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("(scratchSearchPath.Length + nextComponentLength) <= scratchSearchPath.MaximumLength");
          v53 = *(_WORD *)&v62[12];
        }
        *(_QWORD *)v75 = v72;
        v54 = 2;
        *(_WORD *)&v62[12] = v52 + v53;
        v76 = v50;
        *(_OWORD *)v77 = 0;
        if ( a7 )
          v54 = 3;
        v79 = v54;
        v78 = 0;
        UnionFs::UfsPathName::UfsPathName(
          (UnionFs::UfsPathName *)&v80,
          (const struct _UNICODE_STRING *)&v62[12],
          *(unsigned __int16 *)&v62[4]);
        v45 = UnionFs::Utils::CopyItem((_DWORD)v70, v51, (_DWORD)v28, (_DWORD)v69, &v80, (__int64)v75, a10, v55);
        if ( v45 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v45,
            (int)a10,
            (struct UnionFs::StackEventTracer *)0x255002005A5LL,
            (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
            "PUSH: Copying item from layer",
            v60);
          if ( !v81 )
            v80 = 0;
          FsFltWil::Details::FreeUnicodeString(&v80, v57);
          if ( v77[1] )
            utl::_RefCountBase::_DecStrong(v77[1]);
          if ( v41 != (_WORD *)-1LL && v41 )
            ExFreePoolWithTag(v41, 0);
          if ( v28 )
          {
            v49 = *((_BYTE *)v28 + 16) == 0;
            goto LABEL_108;
          }
          goto LABEL_111;
        }
        if ( !v81 )
          v80 = 0;
        FsFltWil::Details::FreeUnicodeString(&v80, v56);
        if ( v77[1] )
          utl::_RefCountBase::_DecStrong(v77[1]);
      }
      goto LABEL_77;
    }
    if ( v45 != -1073741766 && v45 != -1073741772 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v45,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x1060020054DLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
        "PUSH: Stat on scratch",
        v59);
      if ( v66[0] != (PVOID)-1LL && v66[0] )
        ExFreePoolWithTag(v66[0], 0);
      if ( v28 )
      {
        v49 = *((_BYTE *)v28 + 16) == 0;
LABEL_108:
        if ( v49 )
          *(_OWORD *)v28 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v28, v23);
        ExFreePoolWithTag(v28, 0);
      }
LABEL_111:
      OpenedScratchRootPath = v45;
      goto LABEL_112;
    }
    v27 = *(_WORD *)&v62[12];
    v29 = *(_WORD *)v62;
    v61 = 1;
LABEL_61:
    v29 -= v37;
    v11 = v73;
  }
  if ( v31 != (_WORD *)v30 )
  {
LABEL_47:
    *v31++ = v37;
    v27 = *(_WORD *)&v62[12];
    v66[1] = v31;
    goto LABEL_48;
  }
  v38 = v66[0];
  v39 = (signed __int64)(v30 - (unsigned __int64)v66[0]) >> 1;
  v40 = 7 * (v39 >> 2) + 8;
  if ( v40 > 0x3FFFFFFFFFFFFFFFLL )
    v40 = 0x3FFFFFFFFFFFFFFFLL;
  if ( v39 >= v40 )
    goto LABEL_63;
  if ( (unsigned __int8)utl::vector<unsigned short,utl::allocator<unsigned short>>::_SetCapacity(v66) )
  {
    v30 = v67;
    v31 = v66[1];
    goto LABEL_47;
  }
  v38 = v66[0];
LABEL_63:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    (int)a10,
    (struct UnionFs::StackEventTracer *)0x10800200510LL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
    "ORIGIN: Tracking lengthDiff",
    v59);
  if ( v38 != (PVOID)-1LL && v38 )
    ExFreePoolWithTag(v38, 0);
  if ( v28 )
  {
    if ( !*((_BYTE *)v28 + 16) )
      *(_OWORD *)v28 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v28, v23);
    ExFreePoolWithTag(v28, 0);
  }
  OpenedScratchRootPath = -1073741670;
LABEL_112:
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v23);
  return (unsigned int)OpenedScratchRootPath;
}

```

## disassembly

```asm
0x1400605e4  mov     [rsp-8+arg_0], rbx
0x1400605e9  push    rbp
0x1400605ea  push    rsi
0x1400605eb  push    rdi
0x1400605ec  push    r12
0x1400605ee  push    r13
0x1400605f0  push    r14
0x1400605f2  push    r15
0x1400605f4  lea     rbp, [rsp-110h]
0x1400605fc  sub     rsp, 210h
0x140060603  mov     rax, cs:__security_cookie
0x14006060a  xor     rax, rsp
0x14006060d  mov     [rbp+140h+var_40], rax
0x140060614  mov     r13, [rbp+140h+arg_50]
0x14006061b  xorps   xmm0, xmm0
0x14006061e  mov     r15, [rbp+140h+arg_40]
0x140060625  mov     r12, r9
0x140060628  mov     r14, [rbp+140h+arg_28]
0x14006062f  mov     rbx, [rbp+140h+arg_38]
0x140060636  mov     rdi, [rbp+140h+arg_48]
0x14006063d  mov     [rbp+140h+var_198], r13
0x140060641  xor     r13d, r13d
0x140060644  mov     [rbp+140h+var_170], r9
0x140060648  mov     [rbp+140h+var_190], r8
0x14006064c  mov     [rbp+140h+var_188], rdx
0x140060650  mov     [rbp+140h+var_178], rcx
0x140060654  mov     [rbp+140h+var_180], r15
0x140060658  movups  xmmword ptr [rsp+240h+UnicodeString.Length], xmm0
0x14006065d  mov     word ptr [rsp+240h+var_1EC+4], r13w
0x140060663  cmp     [rbp+140h+arg_20], r13b
0x14006066a  jz      loc_1400607FB
0x140060670  lea     rcx, [rsp+240h+UnicodeString]; UnicodeString
0x140060675  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006067a  mov     r8, [rbx+10h]
0x14006067e  xorps   xmm0, xmm0
0x140060681  mov     esi, r13d
0x140060684  movups  xmmword ptr [rsp+240h+UnicodeString.Length], xmm0
0x140060689  test    r8, r8
0x14006068c  jz      short loc_1400606AB
0x14006068e  mov     edx, [r8+8]
0x140060692  test    edx, edx
0x140060694  jz      short loc_1400606AB
0x140060696  lea     ecx, [rdx+1]
0x140060699  mov     eax, edx
0x14006069b  lock cmpxchg [r8+8], ecx
0x1400606a1  cmp     edx, eax
0x1400606a3  jz      short loc_1400606F3
0x1400606a5  mov     edx, eax
0x1400606a7  test    eax, eax
0x1400606a9  jnz     short loc_140060696
0x1400606ab  lea     rax, aOriginNoScratc; "ORIGIN: No scratch layer in streamhandl"...
0x1400606b2  mov     ebx, 0C0ED0008h
0x1400606b7  mov     ecx, ebx; this
0x1400606b9  mov     [rsp+240h+var_220], rax; char *
0x1400606be  lea     r9, aUnionfsUfsstre_21; "UnionFs::UfsStreamHandleCtx::GetNormali"...
0x1400606c5  mov     r8, 3D6000A06FEh; struct UnionFs::StackEventTracer *
0x1400606cf  mov     rdx, rdi; int
0x1400606d2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400606d7  test    rsi, rsi
0x1400606da  jz      short loc_1400606E4
0x1400606dc  mov     rcx, rsi; this
0x1400606df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400606e4  mov     r8, 123002004C7h
0x1400606ee  jmp     loc_140060824
0x1400606f3  mov     rcx, [rbx+8]
0x1400606f7  mov     rsi, [rbx+10h]
0x1400606fb  test    rcx, rcx
0x1400606fe  jz      short loc_1400606AB
0x140060700  mov     rcx, [rcx+10h]
0x140060704  lea     rdx, [rsp+240h+UnicodeString]
0x140060709  mov     r9b, 1
0x14006070c  mov     r8, rdi
0x14006070f  call    ?AsUnicodeString@UfsPathName@UnionFs@@QEBAJAEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathName::AsUnicodeString(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)
0x140060714  mov     ebx, eax
0x140060716  test    eax, eax
0x140060718  jns     short loc_140060743
0x14006071a  lea     rax, aPushAsunicodes; "PUSH: AsUnicodeString"
0x140060721  mov     r8, 1B5000A0706h; struct UnionFs::StackEventTracer *
0x14006072b  lea     r9, aUnionfsUfsstre_21; "UnionFs::UfsStreamHandleCtx::GetNormali"...
0x140060732  mov     [rsp+240h+var_220], rax; char *
0x140060737  mov     rdx, rdi; int
0x14006073a  mov     ecx, ebx; this
0x14006073c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140060741  jmp     short loc_1400606D7
0x140060743  test    rsi, rsi
0x140060746  jz      short loc_140060750
0x140060748  mov     rcx, rsi; this
0x14006074b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140060750  xorps   xmm0, xmm0
0x140060753  lea     rdx, [rbp+140h+var_160]; struct _UNICODE_STRING *
0x140060757  mov     ebx, 1
0x14006075c  mov     rcx, r15; this
0x14006075f  mov     r8b, bl; bool
0x140060762  movups  xmmword ptr [rbp+140h+var_160.Length], xmm0
0x140060766  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14006076b  lea     rcx, [rsp+240h+P]
0x140060770  mov     [rsp+240h+var_218], rdi; char *
0x140060775  mov     [rsp+240h+var_220], rcx
0x14006077a  lea     r8, [rbp+140h+var_160]
0x14006077e  mov     rcx, r14
0x140060781  mov     [rsp+240h+P], r13
0x140060786  movzx   r9d, ax
0x14006078a  lea     rdx, [rsp+240h+UnicodeString]
0x14006078f  call    ?ReplacePathPrefix@UfsPathName@UnionFs@@QEBAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::ReplacePathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140060794  mov     esi, eax
0x140060796  test    eax, eax
0x140060798  jns     loc_140060846
0x14006079e  lea     rax, aPushCreatingLa_0; "PUSH: Creating layer path"
0x1400607a5  mov     r8, 105002004E0h; struct UnionFs::StackEventTracer *
0x1400607af  lea     r9, aUnionfsUfsunio_27; "UnionFs::UfsUnionCtx::EnsureParentPathI"...
0x1400607b6  mov     [rsp+240h+var_220], rax; char *
0x1400607bb  mov     rdx, rdi; int
0x1400607be  mov     ecx, esi; this
0x1400607c0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400607c5  mov     rbx, [rsp+240h+P]
0x1400607ca  test    rbx, rbx
0x1400607cd  jz      short loc_1400607F4
0x1400607cf  cmp     [rbx+10h], r13b
0x1400607d3  jnz     short loc_1400607DB
0x1400607d5  xorps   xmm0, xmm0
0x1400607d8  movups  xmmword ptr [rbx], xmm0
0x1400607db  mov     rcx, rbx; UnicodeString
0x1400607de  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400607e3  xor     edx, edx; Tag
0x1400607e5  mov     rcx, rbx; P
0x1400607e8  call    cs:__imp_ExFreePoolWithTag
0x1400607ef  nop     dword ptr [rax+rax+00h]
0x1400607f4  mov     ebx, esi
0x1400607f6  jmp     loc_140060EC0
0x1400607fb  lea     r9, [rsp+240h+var_1EC+4]
0x140060800  mov     r8, rdi
0x140060803  lea     rdx, [rsp+240h+UnicodeString]
0x140060808  mov     rcx, rbx
0x14006080b  call    ?GetOpenedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAG@Z; UnionFs::UfsStreamHandleCtx::GetOpenedScratchRootPath(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort *)
0x140060810  mov     ebx, eax
0x140060812  test    eax, eax
0x140060814  jns     loc_140060750
0x14006081a  mov     r8, 1B6002004D0h; struct UnionFs::StackEventTracer *
0x140060824  lea     rax, aPushGettingScr_0; "PUSH: Getting scratch root"
0x14006082b  mov     rdx, rdi; int
0x14006082e  lea     r9, aUnionfsUfsunio_27; "UnionFs::UfsUnionCtx::EnsureParentPathI"...
0x140060835  mov     [rsp+240h+var_220], rax; char *
0x14006083a  mov     ecx, ebx; this
0x14006083c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140060841  jmp     loc_140060EC0
0x140060846  movzx   eax, [rbp+140h+arg_30]
0x14006084d  lea     rdx, [rsp+240h+var_1EC]; struct _UNICODE_STRING *
0x140060852  movups  xmm0, xmmword ptr [r12]
0x140060857  xor     eax, ebx
0x140060859  lea     rcx, [rsp+240h+var_1EC+0Ch]; this
0x14006085e  add     eax, 8
0x140060861  shl     eax, 6
0x140060864  mov     [rbp+140h+var_1B8], eax
0x140060867  movzx   eax, word ptr [r12+18h]
0x14006086d  mov     word ptr [rsp+240h+var_1EC+4], ax
0x140060872  mov     word ptr [rsp+240h+var_1EC], ax
0x140060877  movdqu  xmmword ptr [rsp+240h+var_1EC+0Ch], xmm0
0x14006087d  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140060882  movzx   ecx, word ptr [rsp+240h+var_1EC+0Ch]
0x140060887  or      r10, 0FFFFFFFFFFFFFFFFh
0x14006088b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140060893  movzx   r14d, cx
0x140060897  mov     rbx, [rsp+240h+P]
0x14006089c  mov     eax, 2
0x1400608a1  sub     r14w, ax
0x1400608a5  mov     [rbp+140h+var_1A0], r10
0x1400608a9  xor     r9d, r9d
0x1400608ac  mov     r13, r10
0x1400608af  movdqu  xmmword ptr [rbp+140h+var_1B0], xmm0
0x1400608b4  mov     r15, [rbp+140h+var_1B0+8]
0x1400608b8  mov     r8b, r9b
0x1400608bb  mov     [rsp+240h+var_1F0], r9b
0x1400608c0  mov     r11, 3FFFFFFFFFFFFFFFh
0x1400608ca  mov     word ptr [rsp+240h+var_1EC], r14w
0x1400608d0  cmp     [r12], ax
0x1400608d5  jb      short loc_140060927
0x1400608d7  mov     rsi, qword ptr [rsp+240h+var_1EC+14h]
0x1400608dc  test    rsi, rsi
0x1400608df  jz      short loc_140060927
0x1400608e1  test    r14b, 1
0x1400608e5  jz      short loc_14006090B
0x1400608e7  lea     rcx, aStartposSizeof; "*StartPos % sizeof(WCHAR) == 0"
0x1400608ee  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400608f3  movzx   ecx, word ptr [rsp+240h+var_1EC+0Ch]
0x1400608f8  or      r10, 0FFFFFFFFFFFFFFFFh
0x1400608fc  mov     r8b, [rsp+240h+var_1F0]
0x140060901  mov     r11, 3FFFFFFFFFFFFFFFh
0x14006090b  movzx   edx, r14w
0x14006090f  shr     dx, 1
0x140060912  movsx   rax, dx
0x140060916  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x14006091b  jz      loc_1400609D3
0x140060921  add     dx, r10w
0x140060925  jns     short loc_140060912
0x140060927  lea     rax, aOriginFindchar; "ORIGIN: FindCharReverse"
0x14006092e  mov     r8, 107002004FFh; struct UnionFs::StackEventTracer *
0x140060938  lea     r9, aUnionfsUfsunio_27; "UnionFs::UfsUnionCtx::EnsureParentPathI"...
0x14006093f  mov     [rsp+240h+var_220], rax; char *
0x140060944  mov     rdx, rdi; int
0x140060947  mov     ecx, 0C000003Ah; this
0x14006094c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140060951  mov     rcx, [rbp+140h+var_1B0]; P
0x140060955  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140060959  jz      short loc_14006096E
0x14006095b  test    rcx, rcx
0x14006095e  jz      short loc_14006096E
0x140060960  xor     edx, edx; Tag
0x140060962  call    cs:__imp_ExFreePoolWithTag
0x140060969  nop     dword ptr [rax+rax+00h]
0x14006096e  xor     ecx, ecx
0x140060970  test    rbx, rbx
0x140060973  jz      short loc_140060999
0x140060975  cmp     [rbx+10h], cl
0x140060978  jnz     short loc_140060980
0x14006097a  xorps   xmm0, xmm0
0x14006097d  movups  xmmword ptr [rbx], xmm0
0x140060980  mov     rcx, rbx; UnicodeString
0x140060983  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140060988  xor     edx, edx; Tag
0x14006098a  mov     rcx, rbx; P
0x14006098d  call    cs:__imp_ExFreePoolWithTag
0x140060994  nop     dword ptr [rax+rax+00h]
0x140060999  lea     rcx, [rsp+240h+UnicodeString]; UnicodeString
0x14006099e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400609a3  mov     eax, 0C000003Ah
0x1400609a8  mov     rcx, [rbp+140h+var_40]
0x1400609af  xor     rcx, rsp; StackCookie
0x1400609b2  call    __security_check_cookie
0x1400609b7  mov     rbx, [rsp+240h+arg_0]
0x1400609bf  add     rsp, 210h
0x1400609c6  pop     r15
0x1400609c8  pop     r14
0x1400609ca  pop     r13
0x1400609cc  pop     r12
0x1400609ce  pop     rdi
0x1400609cf  pop     rsi
0x1400609d0  pop     rbp
0x1400609d1  retn
0x1400609d3  add     dx, dx
0x1400609d6  movzx   r12d, cx
0x1400609da  sub     r12w, dx
0x1400609de  test    r8b, r8b
0x1400609e1  jz      short loc_140060A3E
0x1400609e3  cmp     r15, r13
0x1400609e6  jnz     short loc_140060A2D
0x1400609e8  mov     rsi, [rbp+140h+var_1B0]
0x1400609ec  sub     r13, rsi
0x1400609ef  sar     r13, 1
0x1400609f2  mov     rax, r13
0x1400609f5  shr     rax, 2
0x1400609f9  imul    rdx, rax, 7
0x1400609fd  add     rdx, 8
0x140060a01  cmp     rdx, r11
0x140060a04  cmova   rdx, r11
0x140060a08  cmp     r13, rdx
0x140060a0b  jnb     loc_140060BC9
0x140060a11  lea     rcx, [rbp+140h+var_1B0]
0x140060a15  call    ?_SetCapacity@?$vector@GV?$allocator@G@utl@@@utl@@AEAA_N_K@Z; utl::vector<ushort,utl::allocator<ushort>>::_SetCapacity(unsigned __int64)
0x140060a1a  xor     r15d, r15d
0x140060a1d  test    al, al
0x140060a1f  jz      loc_140060BC3
0x140060a25  mov     r13, [rbp+140h+var_1A0]
0x140060a29  mov     r15, [rbp+140h+var_1B0+8]
0x140060a2d  mov     [r15], r12w
0x140060a31  add     r15, 2
0x140060a35  movzx   ecx, word ptr [rsp+240h+var_1EC+0Ch]
0x140060a3a  mov     [rbp+140h+var_1B0+8], r15
0x140060a3e  sub     cx, r12w
0x140060a42  mov     word ptr [rsp+240h+var_1EC+0Ch], cx
0x140060a47  mov     rcx, rbx; this
0x140060a4a  movzx   edx, word ptr [rbx]
0x140060a4d  sub     dx, r12w; unsigned __int16
0x140060a51  call    ?PathLength@UfsPathName@UnionFs@@QEAAXG@Z; UnionFs::UfsPathName::PathLength(ushort)
0x140060a56  movzx   ecx, word ptr [rsp+240h+var_1EC+0Ch]
0x140060a5b  mov     eax, 2
0x140060a60  mov     rsi, [rbp+140h+var_1B0]
0x140060a64  cmp     cx, word ptr [rsp+240h+var_1EC+4]
0x140060a69  jz      loc_140060CFC
0x140060a6f  cmp     r12w, ax
0x140060a73  jz      loc_140060BAD
0x140060a79  lea     rax, off_14007E740
0x140060a80  mov     rcx, rdi
0x140060a83  mov     [rbp+140h+var_110.Buffer], rax
0x140060a87  lea     rdx, [rbp+140h+var_110]
0x140060a8b  lea     rax, [rbp+140h+var_110.Buffer]
0x140060a8f  mov     [rbp+140h+var_A0], rax
0x140060a96  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x140060a9b  xor     edx, edx; Val
0x140060a9d  lea     rcx, [rbp+140h+var_90]; void *
0x140060aa4  lea     r8d, [rdx+48h]; Size
0x140060aa8  call    memset
0x140060aad  movzx   ecx, [rbp+140h+arg_30]
0x140060ab4  mov     rax, [rbp+140h+var_198]
0x140060ab8  xor     ecx, 1
0x140060abb  mov     dword ptr [rsp+240h+P], ecx
0x140060abf  test    rax, rax
0x140060ac2  jz      short loc_140060AC9
0x140060ac4  mov     r14, [rax]
0x140060ac7  jmp     short loc_140060AD8
0x140060ac9  call    cs:__imp_PsGetHostSilo
  ... truncated ...
```
