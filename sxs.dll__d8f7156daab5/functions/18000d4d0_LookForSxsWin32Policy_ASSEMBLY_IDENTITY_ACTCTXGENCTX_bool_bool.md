# LookForSxsWin32Policy(_ASSEMBLY_IDENTITY *,_ACTCTXGENCTX *,bool,bool &)

- ea: `0x18000d4d0`
- end: `0x18000df36`
- name: `?LookForSxsWin32Policy@@YAHPEAU_ASSEMBLY_IDENTITY@@PEAU_ACTCTXGENCTX@@_NAEA_N@Z`
- size: `2662`
- prototype: `int(struct _ASSEMBLY_IDENTITY *, struct _ACTCTXGENCTX *, bool, bool *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e160`

## callees

- `0x1800075c0`
- `0x18000bb90`
- `0x18000d4d0`
- `0x18000df40`
- `0x18000dffc`
- `0x18000f170`
- `0x180016798`
- `0x18001c2c8`
- `0x180020e20`
- `0x180022d40`
- `0x180023260`
- `0x180023ee0`
- `0x180025e00`
- `0x18002de10`
- `0x18003e424`
- `0x18003eb88`
- `0x18004063c`
- `0x1800408d4`
- `0x180057858`
- `0x180058fc4`
- `0x180059980`
- `0x18005cf40`
- `0x18005d2b0`
- `0x1800665f4`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000d9a7`
- `ntdll!EtwEventWrite` at `0x18000d9a7`
- `ntdll!RtlPopFrame` at `0x18000d736`
- `ntdll!RtlPopFrame` at `0x18000d75e`
- `ntdll!RtlPopFrame` at `0x18000d803`
- `ntdll!RtlPopFrame` at `0x18000d839`
- `ntdll!RtlPopFrame` at `0x18000d8be`
- `ntdll!RtlPopFrame` at `0x18000da17`
- `ntdll!RtlPopFrame` at `0x18000d736`
- `ntdll!RtlPopFrame` at `0x18000d75e`
- `ntdll!RtlPopFrame` at `0x18000d803`
- `ntdll!RtlPopFrame` at `0x18000d839`
- `ntdll!RtlPopFrame` at `0x18000d8be`
- `ntdll!RtlPopFrame` at `0x18000da17`
- `ntdll!RtlPushFrame` at `0x18000d556`
- `ntdll!RtlPushFrame` at `0x18000d63a`
- `ntdll!RtlPushFrame` at `0x18000d886`
- `ntdll!RtlPushFrame` at `0x18000d556`
- `ntdll!RtlPushFrame` at `0x18000d63a`
- `ntdll!RtlPushFrame` at `0x18000d886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d594`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d65d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d704`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d779`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d594`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d65d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d704`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d779`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd68`

## pseudocode

```c
__int64 __fastcall LookForSxsWin32Policy(struct _ASSEMBLY_IDENTITY *a1, struct _ACTCTXGENCTX *a2, char a3, bool *a4)
{
  const char *v8; // rcx
  struct _ASSEMBLY_IDENTITY *v9; // rdi
  const unsigned __int16 *v10; // rdi
  unsigned __int64 v11; // rbx
  CPolicyStatement *v12; // r15
  unsigned int v13; // r12d
  __int64 v14; // rbx
  __int64 v15; // rax
  struct CPolicyStatement **v16; // r14
  _QWORD **v17; // rdi
  _QWORD *v18; // rbx
  int v19; // ebx
  int v20; // ebx
  char v21; // dl
  _WORD *v22; // rcx
  int *v23; // rax
  unsigned int v24; // esi
  DWORD v26; // ebx
  const unsigned __int16 *v27; // r9
  unsigned int v28; // ecx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  DWORD LastError; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  DWORD v35; // eax
  struct _ASSEMBLY_IDENTITY *v36; // [rsp+28h] [rbp-E0h]
  bool v37[8]; // [rsp+48h] [rbp-C0h] BYREF
  struct _ASSEMBLY_IDENTITY *v38; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+58h] [rbp-B0h]
  struct CPolicyStatement *v40; // [rsp+60h] [rbp-A8h] BYREF
  const unsigned __int16 *v41; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v42; // [rsp+70h] [rbp-98h]
  bool *v43; // [rsp+78h] [rbp-90h]
  int v44; // [rsp+80h] [rbp-88h] BYREF
  int v45; // [rsp+88h] [rbp-80h] BYREF
  int v46; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v47; // [rsp+90h] [rbp-78h] BYREF
  struct _ASSEMBLY_IDENTITY *v48[2]; // [rsp+98h] [rbp-70h] BYREF
  int v49; // [rsp+A8h] [rbp-60h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-40h]
  int v52; // [rsp+D0h] [rbp-38h]
  int *v53; // [rsp+D8h] [rbp-30h]
  struct _TEB_ACTIVE_FRAME v54; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v55; // [rsp+F8h] [rbp-10h]
  int v56; // [rsp+100h] [rbp-8h]
  int *v57; // [rsp+108h] [rbp+0h]
  struct _TEB_ACTIVE_FRAME v58; // [rsp+110h] [rbp+8h] BYREF
  __int64 v59; // [rsp+128h] [rbp+20h]
  int v60; // [rsp+130h] [rbp+28h]
  int *v61; // [rsp+138h] [rbp+30h]
  struct _TEB_ACTIVE_FRAME v62; // [rsp+140h] [rbp+38h] BYREF
  __int64 v63; // [rsp+158h] [rbp+50h]
  int v64; // [rsp+160h] [rbp+58h]
  int *v65; // [rsp+168h] [rbp+60h]
  _BYTE v66[832]; // [rsp+178h] [rbp+70h] BYREF
  struct _TEB_ACTIVE_FRAME v67; // [rsp+4B8h] [rbp+3B0h] BYREF
  __int64 v68; // [rsp+4D0h] [rbp+3C8h]
  int v69; // [rsp+4D8h] [rbp+3D0h]
  int *v70; // [rsp+4E0h] [rbp+3D8h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C800;
  v48[0] = a1;
  v43 = a4;
  v49 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v51 = 544438355;
  v52 = 350;
  v53 = &v49;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v37[2] = 0;
  v9 = 0;
  LOBYTE(v39) = 0;
  *a4 = 0;
  v37[1] = 0;
  v38 = 0;
  if ( !a2 )
  {
    v52 = 362;
    FusionpTraceParameterCheck(v8);
    SetLastError(0x57u);
    *v53 = 0;
    goto LABEL_39;
  }
  SetLastError(0);
  LOBYTE(v39) = 1;
  if ( !SxspMapAssemblyIdentityToPolicyIdentity(0, a1, &v38) )
  {
    *v53 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077020);
    v9 = v38;
    goto LABEL_39;
  }
  if ( a3 )
  {
    CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear((char *)a2 + 2432);
    SetLastError(0);
    if ( !(unsigned int)SxspGenerateTextuallyEncodedPolicyIdentityFromAssemblyIdentity(v30, a1, (char *)a2 + 2432) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077000);
      v9 = v38;
      goto LABEL_39;
    }
  }
  SetLastError(0);
  v10 = (const unsigned __int16 *)*((_QWORD *)a2 + 306);
  v41 = v10;
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
  }
  else
  {
    v11 = 0;
  }
  v42 = v11;
  v58.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringPtrTable<CPolicyStatement,CUnicodeCharTraits,1,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>>::Find'::`2'::__stc;
  v46 = 0;
  v61 = &v46;
  v58.Flags = 1;
  v58.Previous = 0;
  v59 = 544438355;
  v60 = 1461;
  RtlPushFrame(&v58);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v40 = 0;
  v12 = 0;
  SetLastError(0);
  v44 = 0;
  v67.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringTableHelper<CPolicyStatement *,CPolicyStatement *,CUnicodeCharTraits,1>::HashKey'::`2'::__stc;
  v67.Flags = 1;
  v70 = &v44;
  v67.Previous = 0;
  v68 = 544438355;
  v69 = 1287;
  CFrame::BaseEnter((CFrame *)&v67);
  SetLastError(0);
  v47 = 0;
  v62.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CCharTraitsBase<unsigned short,char>::Win32HashString'::`2'::__stc;
  v62.Flags = 1;
  v65 = &v47;
  v62.Previous = 0;
  v63 = 544438355;
  v64 = 156;
  CFrame::BaseEnter((CFrame *)&v62);
  SetLastError(0);
  v13 = FusionpHashUnicodeStringCaseInsensitive(v10, v11);
  v47 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v65 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v62);
  v44 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v70 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v32 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v32, 0);
    }
  }
  RtlPopFrame(&v67);
  v14 = v13 % *((_DWORD *)a2 + 496);
  SetLastError(0);
  v15 = *((_QWORD *)a2 + 249);
  v16 = 0;
  v54.Flags = 1;
  v45 = 0;
  v54.Previous = 0;
  v17 = (_QWORD **)(v15 + 40 * v14);
  v55 = 544438355;
  v56 = 802;
  v54.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::CBucketChain::Find'::`2'::__stc;
  v57 = &v45;
  CFrame::BaseEnter((CFrame *)&v54);
  v18 = *v17;
  v37[0] = 0;
  while ( 1 )
  {
    if ( !v18 || v18 == v17 )
      goto LABEL_16;
    SetLastError(0);
    if ( !(unsigned int)CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::CBucket::Matches(
                          v18 - 72,
                          &v41,
                          v13,
                          v37) )
      break;
    if ( v37[0] )
    {
      v16 = (struct CPolicyStatement **)(v18 - 2);
LABEL_16:
      v19 = 1;
      v45 = 1;
      goto LABEL_17;
    }
    v18 = (_QWORD *)*v18;
  }
  *v57 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::CBucketChain::Find'::`17'::__callsite);
  v19 = v45;
LABEL_17:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v57 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v33 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v33, 0);
    }
  }
  RtlPopFrame(&v54);
  if ( v19 )
  {
    if ( v16 )
    {
      v12 = *v16;
      v40 = *v16;
    }
    v20 = 1;
    v46 = 1;
  }
  else
  {
    *v61 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CStringPtrTable<CPolicyStatement,CUnicodeCharTraits,1,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>>::Find'::`28'::__callsite);
    v20 = v46;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v61 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v34 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v34, 0);
    }
  }
  RtlPopFrame(&v58);
  if ( !v20 )
  {
    *v53 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006FD90);
    v9 = v38;
    goto LABEL_39;
  }
  if ( v12 )
  {
    v9 = v38;
LABEL_54:
    SetLastError(0);
    if ( !CPolicyStatement::ApplyPolicy(v12, v48[0], v43) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076F20);
      goto LABEL_39;
    }
    goto LABEL_38;
  }
  v54.Flags = 1;
  v54.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear'::`2'::__stc;
  v54.Previous = 0;
  v55 = 544438355;
  v56 = 579;
  RtlPushFrame(&v54);
  v21 = g_FusionEnterExitTracingEnabled;
  if ( g_FusionEnterExitTracingEnabled )
  {
    FusionpTraceCallEntry();
    v21 = g_FusionEnterExitTracingEnabled;
  }
  v22 = (_WORD *)*((_QWORD *)a2 + 376);
  if ( v22 )
    *v22 = 0;
  *((_QWORD *)a2 + 378) = 0;
  if ( v21 )
    FusionpTraceCallExit();
  RtlPopFrame(&v54);
  SetLastError(0);
  v9 = v38;
  if ( !SxspGetAutoServicingVersion(
          0,
          *((const unsigned __int16 **)a2 + 11),
          *((_QWORD *)a2 + 13),
          v38,
          &v37[2],
          &v37[1]) )
  {
    *v53 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076FE0);
    goto LABEL_39;
  }
  if ( v37[1] )
  {
    SetLastError(0);
    if ( !(unsigned int)SxspGetInstalledPath(
                          0,
                          1u,
                          *((_QWORD *)a2 + 11),
                          *((_QWORD *)a2 + 13),
                          v9,
                          0,
                          (__int64)a2 + 2992) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076FC0);
      goto LABEL_39;
    }
    TraceActCtxGenEvents(
      *((_DWORD *)a2 + 326),
      *((const unsigned __int16 **)a2 + 376),
      0,
      v27,
      (const unsigned __int16 *)v36,
      0xE6u,
      4,
      0x66u);
    CProbedAssemblyInformation::CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
    SetLastError(0);
    if ( !(unsigned int)CProbedAssemblyInformation::Initialize((CProbedAssemblyInformation *)v66, a2) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076FA0);
      CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
      goto LABEL_39;
    }
    SetLastError(0);
    if ( !(unsigned int)CProbedAssemblyInformation::SetManifestPath((CProbedAssemblyInformation *)v66) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076F80);
      CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
      goto LABEL_39;
    }
    SetLastError(0);
    if ( !(unsigned int)CProbedAssemblyInformation::SetProbedIdentity((CProbedAssemblyInformation *)v66, v9) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076F60);
      CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
      goto LABEL_39;
    }
    SetLastError(0);
    if ( !SxspParseComponentPolicy(v28, a2, (const struct CProbedAssemblyInformation *)v66, &v40) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076F40);
      CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
      goto LABEL_39;
    }
    SetLastError(0);
    v41 = (const unsigned __int16 *)*((_QWORD *)a2 + 306);
    v29 = CUnicodeCharTraits::Cch(v41);
    v12 = v40;
    v42 = v29;
    if ( !(unsigned int)CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::Insert(
                          (char *)a2 + 1984,
                          &v41,
                          v40,
                          14027) )
    {
      *v53 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800701F0);
      CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
      goto LABEL_39;
    }
    CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v66);
    if ( v12 )
      goto LABEL_54;
  }
  v44 = *((_DWORD *)a2 + 326);
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    *(_QWORD *)&v67.Flags = &v44;
    v48[0] = (struct _ASSEMBLY_IDENTITY *)0x660004000000E9LL;
    v48[1] = (struct _ASSEMBLY_IDENTITY *)256;
    v67.Previous = (struct _TEB_ACTIVE_FRAME *)4;
    EtwEventWrite(g_hTraceHandle, v48, 1, &v67);
  }
LABEL_38:
  SetLastError(0);
  *v53 = 1;
LABEL_39:
  v23 = v53;
  v24 = *v53;
  if ( v9 && (_BYTE)v39 )
  {
    v26 = GetLastError();
    SxsDestroyAssemblyIdentity(v9);
    SetLastError(v26);
    v23 = v53;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v23 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v35 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v35, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v24;
}

```

## disassembly

```asm
0x18000d4d0  mov     r11, rsp
0x18000d4d3  push    rbp
0x18000d4d4  push    rsi
0x18000d4d5  lea     rbp, [r11-448h]
0x18000d4dc  sub     rsp, 538h
0x18000d4e3  mov     rax, cs:__security_cookie
0x18000d4ea  xor     rax, rsp
0x18000d4ed  mov     [rbp+440h+var_40], rax
0x18000d4f4  mov     [r11+18h], rbx
0x18000d4f8  lea     rax, qword_18006C800
0x18000d4ff  mov     [r11-18h], rdi
0x18000d503  movzx   ebx, r8b
0x18000d507  mov     [r11-20h], r12
0x18000d50b  mov     rsi, rdx
0x18000d50e  mov     [r11-30h], r14
0x18000d512  xor     r12d, r12d
0x18000d515  mov     [r11-38h], r15
0x18000d519  mov     r14, r9
0x18000d51c  mov     [rbp+440h+Frame.Context], rax
0x18000d520  mov     r15, rcx
0x18000d523  mov     [rbp+440h+var_4B0], rcx
0x18000d527  lea     rax, [rbp+440h+var_4A0]
0x18000d52b  lea     rcx, [rbp+440h+Frame]; Frame
0x18000d52f  mov     [rsp+540h+var_4D0], r9
0x18000d534  mov     [rbp+440h+var_4A0], r12d
0x18000d538  mov     [rbp+440h+Frame.Flags], 1
0x18000d53f  mov     [rbp+440h+Frame.Previous], r12
0x18000d543  mov     [rbp+440h+var_480], 20737853h
0x18000d54b  mov     [rbp+440h+var_478], 15Eh
0x18000d552  mov     [rbp+440h+var_470], rax
0x18000d556  call    cs:__imp_RtlPushFrame
0x18000d55d  nop     dword ptr [rax+rax+00h]
0x18000d562  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x18000d569  jnz     loc_18000DA70
0x18000d56f  mov     [rsp+540h+var_500+2], r12b
0x18000d574  mov     rdi, r12
0x18000d577  mov     byte ptr [rsp+540h+var_4F0], dil
0x18000d57c  mov     [r14], dil
0x18000d57f  mov     [rsp+540h+var_500+1], r12b
0x18000d584  mov     [rsp+540h+var_4F8], r12
0x18000d589  test    rsi, rsi
0x18000d58c  jz      loc_18000DC71
0x18000d592  xor     ecx, ecx; dwErrCode
0x18000d594  call    cs:__imp_SetLastError
0x18000d59b  nop     dword ptr [rax+rax+00h]
0x18000d5a0  lea     r8, [rsp+540h+var_4F8]; struct _ASSEMBLY_IDENTITY **
0x18000d5a5  mov     byte ptr [rsp+540h+var_4F0], 1
0x18000d5aa  mov     rdx, r15; struct _ASSEMBLY_IDENTITY *
0x18000d5ad  xor     ecx, ecx; unsigned int
0x18000d5af  call    ?SxspMapAssemblyIdentityToPolicyIdentity@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAPEAU1@@Z; SxspMapAssemblyIdentityToPolicyIdentity(ulong,_ASSEMBLY_IDENTITY const *,_ASSEMBLY_IDENTITY * *)
0x18000d5b4  test    eax, eax
0x18000d5b6  jz      loc_18000DC9A
0x18000d5bc  mov     [rsp+540h+var_20], r13
0x18000d5c4  test    bl, bl
0x18000d5c6  jnz     loc_18000DCB7
0x18000d5cc  xor     ecx, ecx; dwErrCode
0x18000d5ce  call    cs:__imp_SetLastError
0x18000d5d5  nop     dword ptr [rax+rax+00h]
0x18000d5da  mov     rdi, [rsi+990h]
0x18000d5e1  mov     [rsp+540h+var_4E0], rdi
0x18000d5e6  test    rdi, rdi
0x18000d5e9  jz      loc_18000DA95
0x18000d5ef  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d5f6  inc     rbx
0x18000d5f9  cmp     [rdi+rbx*2], r12w
0x18000d5fe  jnz     short loc_18000D5F6
0x18000d600  lea     rax, ?__stc@?1??Find@?$CStringPtrTable@VCPolicyStatement@@VCUnicodeCharTraits@@$00V?$CCaseInsensitiveUnicodeStringPtrTableHelper@VCPolicyStatement@@@@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAPEAVCPolicyStatement@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringPtrTable<CPolicyStatement,CUnicodeCharTraits,1,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>>::Find(CCountedStringHolder<CUnicodeCharTraits> const &,CPolicyStatement * &)'::`2'::__stc
0x18000d607  mov     [rsp+540h+var_4D8], rbx
0x18000d60c  mov     [rbp+440h+var_438.Context], rax
0x18000d610  lea     rcx, [rbp+440h+var_438]; Frame
0x18000d614  lea     rax, [rbp+440h+var_4BC]
0x18000d618  mov     [rbp+440h+var_4BC], r12d
0x18000d61c  mov     [rbp+440h+var_410], rax
0x18000d620  mov     [rbp+440h+var_438.Flags], 1
0x18000d627  mov     [rbp+440h+var_438.Previous], r12
0x18000d62b  mov     [rbp+440h+var_420], 20737853h
0x18000d633  mov     [rbp+440h+var_418], 5B5h
0x18000d63a  call    cs:__imp_RtlPushFrame
0x18000d641  nop     dword ptr [rax+rax+00h]
0x18000d646  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x18000d64d  jnz     loc_18000DA7A
0x18000d653  xor     ecx, ecx; dwErrCode
0x18000d655  mov     [rsp+540h+var_4E8], r12
0x18000d65a  mov     r15, r12
0x18000d65d  call    cs:__imp_SetLastError
0x18000d664  nop     dword ptr [rax+rax+00h]
0x18000d669  lea     rax, ?__stc@?1??HashKey@?$CStringTableHelper@PEAVCPolicyStatement@@PEAV1@VCUnicodeCharTraits@@$00@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAK@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CPolicyStatement *,CPolicyStatement *,CUnicodeCharTraits,1>::HashKey(CCountedStringHolder<CUnicodeCharTraits> const &,ulong &)'::`2'::__stc
0x18000d670  mov     [rsp+540h+var_4C8], r12d
0x18000d675  mov     [rbp+440h+var_90.Context], rax
0x18000d67c  lea     rcx, [rbp+440h+var_90]; this
0x18000d683  lea     rax, [rsp+540h+var_4C8]
0x18000d688  mov     [rbp+440h+var_90.Flags], 1
0x18000d692  mov     [rbp+440h+var_68], rax
0x18000d699  mov     [rbp+440h+var_90.Previous], r12
0x18000d6a0  mov     [rbp+440h+var_78], 20737853h
0x18000d6ab  mov     [rbp+440h+var_70], 507h
0x18000d6b5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18000d6ba  xor     ecx, ecx; dwErrCode
0x18000d6bc  call    cs:__imp_SetLastError
0x18000d6c3  nop     dword ptr [rax+rax+00h]
0x18000d6c8  lea     rax, ?__stc@?1??Win32HashString@?$CCharTraitsBase@GD@@SAHPEBG_KAEAK_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CCharTraitsBase<ushort,char>::Win32HashString(ushort const *,unsigned __int64,ulong &,bool)'::`2'::__stc
0x18000d6cf  mov     [rbp+440h+var_4B8], r12d
0x18000d6d3  mov     [rbp+440h+var_408.Context], rax
0x18000d6d7  lea     rcx, [rbp+440h+var_408]; this
0x18000d6db  lea     rax, [rbp+440h+var_4B8]
0x18000d6df  mov     [rbp+440h+var_408.Flags], 1
0x18000d6e6  mov     [rbp+440h+var_3E0], rax
0x18000d6ea  mov     [rbp+440h+var_408.Previous], r12
0x18000d6ee  mov     [rbp+440h+var_3F0], 20737853h
0x18000d6f6  mov     [rbp+440h+var_3E8], 9Ch
0x18000d6fd  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18000d702  xor     ecx, ecx; dwErrCode
0x18000d704  call    cs:__imp_SetLastError
0x18000d70b  nop     dword ptr [rax+rax+00h]
0x18000d710  mov     rdx, rbx; unsigned __int64
0x18000d713  mov     rcx, rdi; unsigned __int16 *
0x18000d716  call    ?FusionpHashUnicodeStringCaseInsensitive@@YAKPEBG_K@Z; FusionpHashUnicodeStringCaseInsensitive(ushort const *,unsigned __int64)
0x18000d71b  mov     r12d, eax
0x18000d71e  mov     [rbp+440h+var_4B8], 1
0x18000d725  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18000d72c  jnz     loc_18000DD05
0x18000d732  lea     rcx, [rbp+440h+var_408]; Frame
0x18000d736  call    cs:__imp_RtlPopFrame
0x18000d73d  nop     dword ptr [rax+rax+00h]
0x18000d742  mov     [rsp+540h+var_4C8], 1
0x18000d74a  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18000d751  jnz     loc_18000DD34
0x18000d757  lea     rcx, [rbp+440h+var_90]; Frame
0x18000d75e  call    cs:__imp_RtlPopFrame
0x18000d765  nop     dword ptr [rax+rax+00h]
0x18000d76a  xor     edx, edx
0x18000d76c  mov     eax, r12d
0x18000d76f  div     dword ptr [rsi+7C0h]
0x18000d775  xor     ecx, ecx; dwErrCode
0x18000d777  mov     ebx, edx
0x18000d779  call    cs:__imp_SetLastError
0x18000d780  nop     dword ptr [rax+rax+00h]
0x18000d785  mov     rax, [rsi+7C8h]
0x18000d78c  lea     rcx, [rbx+rbx*4]
0x18000d790  xor     r14d, r14d
0x18000d793  mov     [rbp+440h+var_468.Flags], 1
0x18000d79a  mov     [rbp+440h+var_4C0], r14d
0x18000d79e  mov     [rbp+440h+var_468.Previous], r14
0x18000d7a2  lea     rdi, [rax+rcx*8]
0x18000d7a6  mov     [rbp+440h+var_450], 20737853h
0x18000d7ae  lea     rax, ?__stc@?1??Find@CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCPolicyStatement@@PEAV3@V?$CCaseInsensitiveUnicodeStringPtrTableHelper@VCPolicyStatement@@@@$06$0A@@@QEAAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@KAEAPEAPEAVCPolicyStatement@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CPolicyStatement *,CPolicyStatement *,CCaseInsensitiveUnicodeStringPtrTableHelper<CPolicyStatement>,7,0>::CBucketChain::Find(CCountedStringHolder<CUnicodeCharTraits> const &,ulong,CPolicyStatement * * &)'::`2'::__stc
0x18000d7b5  mov     [rbp+440h+var_448], 322h
0x18000d7bc  mov     [rbp+440h+var_468.Context], rax
0x18000d7c0  lea     rcx, [rbp+440h+var_468]; this
0x18000d7c4  lea     rax, [rbp+440h+var_4C0]
0x18000d7c8  mov     [rbp+440h+var_440], rax
0x18000d7cc  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18000d7d1  mov     rbx, [rdi]
0x18000d7d4  mov     [rsp+540h+var_500], r14b
0x18000d7d9  test    rbx, rbx
0x18000d7dc  jz      short loc_18000D7E7
0x18000d7de  cmp     rbx, rdi
0x18000d7e1  jnz     loc_18000DD66
0x18000d7e7  mov     ebx, 1
0x18000d7ec  xor     r12d, r12d
0x18000d7ef  mov     [rbp+440h+var_4C0], ebx
0x18000d7f2  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x18000d7f9  jnz     loc_18000DDC7
0x18000d7ff  lea     rcx, [rbp+440h+var_468]; Frame
0x18000d803  call    cs:__imp_RtlPopFrame
0x18000d80a  nop     dword ptr [rax+rax+00h]
0x18000d80f  test    ebx, ebx
0x18000d811  jz      loc_18000DDF6
0x18000d817  test    r14, r14
0x18000d81a  jnz     loc_18000DE11
0x18000d820  mov     ebx, 1
0x18000d825  mov     [rbp+440h+var_4BC], ebx
0x18000d828  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18000d82f  jnz     loc_18000DE1E
0x18000d835  lea     rcx, [rbp+440h+var_438]; Frame
0x18000d839  call    cs:__imp_RtlPopFrame
0x18000d840  nop     dword ptr [rax+rax+00h]
0x18000d845  test    ebx, ebx
0x18000d847  jz      loc_18000DBFC
0x18000d84d  test    r15, r15
0x18000d850  jnz     loc_18000DC19
0x18000d856  lea     rax, ?__stc@?1??Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)'::`2'::__stc
0x18000d85d  mov     [rbp+440h+var_468.Flags], 1
0x18000d864  lea     rcx, [rbp+440h+var_468]; Frame
0x18000d868  mov     [rbp+440h+var_468.Context], rax
0x18000d86c  lea     rbx, [rsi+0BB0h]
0x18000d873  mov     [rbp+440h+var_468.Previous], r12
0x18000d877  mov     [rbp+440h+var_450], 20737853h
0x18000d87f  mov     [rbp+440h+var_448], 243h
0x18000d886  call    cs:__imp_RtlPushFrame
0x18000d88d  nop     dword ptr [rax+rax+00h]
0x18000d892  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000d899  test    dl, dl
0x18000d89b  jnz     loc_18000DA84
0x18000d8a1  mov     rcx, [rbx+10h]
0x18000d8a5  test    rcx, rcx
0x18000d8a8  jz      short loc_18000D8AE
0x18000d8aa  mov     [rcx], r12w
0x18000d8ae  mov     [rbx+20h], r12
0x18000d8b2  test    dl, dl
0x18000d8b4  jnz     loc_18000DE4D
0x18000d8ba  lea     rcx, [rbp+440h+var_468]; Frame
0x18000d8be  call    cs:__imp_RtlPopFrame
0x18000d8c5  nop     dword ptr [rax+rax+00h]
0x18000d8ca  xor     ecx, ecx; dwErrCode
0x18000d8cc  call    cs:__imp_SetLastError
0x18000d8d3  nop     dword ptr [rax+rax+00h]
0x18000d8d8  mov     rdi, [rsp+540h+var_4F8]
0x18000d8dd  lea     rax, [rsp+540h+var_500+1]
0x18000d8e2  mov     r8, [rsi+68h]; unsigned __int64
0x18000d8e6  mov     r9, rdi; struct _ASSEMBLY_IDENTITY *
0x18000d8e9  mov     rdx, [rsi+58h]; unsigned __int16 *
0x18000d8ed  xor     ecx, ecx; bool
0x18000d8ef  mov     [rsp+540h+var_518], rax; bool *
0x18000d8f4  lea     rax, [rsp+540h+var_500+2]
0x18000d8f9  mov     [rsp+540h+var_520], rax; bool *
0x18000d8fe  call    ?SxspGetAutoServicingVersion@@YAH_NPEBG_KPEAU_ASSEMBLY_IDENTITY@@AEA_N4@Z; SxspGetAutoServicingVersion(bool,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY *,bool &,bool &)
0x18000d903  test    eax, eax
0x18000d905  jz      loc_18000DE57
0x18000d90b  cmp     [rsp+540h+var_500+1], 0
0x18000d910  mov     r14d, 66h ; 'f'
0x18000d916  jnz     loc_18000DA9D
0x18000d91c  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x18000d923  mov     eax, [rsi+518h]
0x18000d929  mov     [rsp+540h+var_4C8], eax
0x18000d92d  jz      loc_18000D9B3
0x18000d933  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18000d93a  dec     al
0x18000d93c  cmp     al, 2
0x18000d93e  jbe     short loc_18000D9B3
0x18000d940  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18000d94b  jz      short loc_18000D9B3
0x18000d94d  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000d954  and     eax, 100h
0x18000d959  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18000d960  jnz     short loc_18000D9B3
0x18000d962  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18000d969  lea     rax, [rsp+540h+var_4C8]
0x18000d96e  lea     r9, [rbp+440h+var_90]
0x18000d975  mov     qword ptr [rbp+440h+var_90.Flags], rax
0x18000d97c  mov     r8d, 1
0x18000d982  mov     dword ptr [rbp+440h+var_4B0], 0E9h
0x18000d989  lea     rdx, [rbp+440h+var_4B0]
0x18000d98d  mov     dword ptr [rbp+440h+var_4B0+4], 660004h
0x18000d994  mov     [rbp+440h+var_4A8], 100h
0x18000d99c  mov     [rbp+440h+var_90.Previous], 4
0x18000d9a7  call    cs:__imp_EtwEventWrite
0x18000d9ae  nop     dword ptr [rax+rax+00h]
0x18000d9b3  xor     ecx, ecx; dwErrCode
0x18000d9b5  call    cs:__imp_SetLastError
0x18000d9bc  nop     dword ptr [rax+rax+00h]
0x18000d9c1  mov     rax, [rbp+440h+var_470]
0x18000d9c5  mov     dword ptr [rax], 1
0x18000d9cb  mov     r13, [rsp+540h+var_20]
0x18000d9d3  mov     rax, [rbp+440h+var_470]
0x18000d9d7  mov     r15, [rsp+540h+var_30]
0x18000d9df  mov     r14, [rsp+540h+var_28]
0x18000d9e7  mov     r12, [rsp+540h+var_18]
0x18000d9ef  mov     esi, [rax]
0x18000d9f1  test    rdi, rdi
0x18000d9f4  jnz     short loc_18000DA3F
0x18000d9f6  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18000d9fd  mov     rdi, [rsp+530h]
0x18000da05  mov     rbx, [rsp+540h+arg_10]
0x18000da0d  jnz     loc_18000DF0B
0x18000da13  lea     rcx, [rbp+440h+Frame]; Frame
0x18000da17  call    cs:__imp_RtlPopFrame
0x18000da1e  nop     dword ptr [rax+rax+00h]
0x18000da23  mov     eax, esi
0x18000da25  mov     rcx, [rbp+440h+var_40]
0x18000da2c  xor     rcx, rsp; StackCookie
0x18000da2f  call    __security_check_cookie
0x18000da34  add     rsp, 538h
0x18000da3b  pop     rsi
0x18000da3c  pop     rbp
0x18000da3d  retn
0x18000da3f  cmp     byte ptr [rsp+540h+var_4F0], 0
0x18000da44  jz      short loc_18000D9F6
0x18000da46  call    cs:__imp_GetLastError
0x18000da4d  nop     dword ptr [rax+rax+00h]
0x18000da52  mov     rcx, rdi; lpMem
0x18000da55  mov     ebx, eax
0x18000da57  call    SxsDestroyAssemblyIdentity
0x18000da5c  mov     ecx, ebx; dwErrCode
0x18000da5e  call    cs:__imp_SetLastError
0x18000da65  nop     dword ptr [rax+rax+00h]
0x18000da6a  mov     rax, [rbp+440h+var_470]
0x18000da6e  jmp     short loc_18000D9F6
0x18000da70  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000da75  jmp     loc_18000D56F
0x18000da7a  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000da7f  jmp     loc_18000D653
0x18000da84  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000da89  movzx   edx, cs:g_FusionEnterExitTracingEnabled
0x18000da90  jmp     loc_18000D8A1
0x18000da95  mov     rbx, r12
0x18000da98  jmp     loc_18000D600
0x18000da9d  xor     ecx, ecx; dwErrCode
0x18000da9f  call    cs:__imp_SetLastError
0x18000daa6  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
