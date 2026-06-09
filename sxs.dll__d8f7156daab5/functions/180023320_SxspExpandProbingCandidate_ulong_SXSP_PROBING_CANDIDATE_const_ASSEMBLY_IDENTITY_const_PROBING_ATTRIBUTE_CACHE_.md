# SxspExpandProbingCandidate(ulong,SXSP_PROBING_CANDIDATE const &,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,StringAndCch const &,StringAndCch const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &,int *)

- ea: `0x180023320`
- end: `0x180023ed1`
- name: `?SxspExpandProbingCandidate@@YAHKAEBUSXSP_PROBING_CANDIDATE@@PEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEBVStringAndCch@@3AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAH@Z`
- size: `2993`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c820`

## callees

- `0x18000dffc`
- `0x180019740`
- `0x18001c2c8`
- `0x18001e5d0`
- `0x180020820`
- `0x180023320`
- `0x180023ee0`
- `0x18002f290`
- `0x180032350`
- `0x180034060`
- `0x18005feac`
- `0x180060008`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180023593`
- `ntdll!RtlPopFrame` at `0x180023593`
- `ntdll!RtlPushFrame` at `0x1800233cf`
- `ntdll!RtlPushFrame` at `0x1800233cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023536`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002369e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002394a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023990`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023baf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023e2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023536`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002369e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002394a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023990`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023baf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023e2e`

## pseudocode

```c
__int64 __fastcall SxspExpandProbingCandidate(
        unsigned int a1,
        unsigned __int16 **a2,
        struct _ASSEMBLY_IDENTITY *a3,
        __int64 a4,
        __int64 *a5,
        unsigned __int64 *a6,
        _QWORD *a7,
        _DWORD *a8)
{
  __int64 v9; // rsi
  unsigned __int16 *v10; // rdi
  __int64 *v11; // r12
  _QWORD *v12; // r13
  __int16 v14; // ax
  int v15; // eax
  _WORD *v16; // rbx
  __int64 v17; // rcx
  unsigned int v18; // ebx
  __int64 v20; // rbx
  unsigned __int64 v21; // r13
  unsigned __int64 v22; // r12
  _QWORD *v23; // r9
  _WORD *v24; // rcx
  _WORD *v25; // rbx
  __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  _WORD *v28; // r9
  unsigned __int64 v29; // rcx
  unsigned __int64 *v30; // rbx
  unsigned __int64 v31; // r13
  unsigned __int64 v32; // r12
  _QWORD *v33; // r9
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  __int64 v36; // rdx
  unsigned __int64 v37; // rcx
  _WORD *v38; // r9
  unsigned int (__fastcall **v39)(_QWORD *, _WORD *, void **); // rax
  const void *v40; // rdx
  unsigned __int64 v41; // rax
  __int64 v42; // rbx
  void *v43; // rax
  unsigned int (__fastcall **v44)(_QWORD *, unsigned __int64, void **); // rax
  const void *v45; // rdx
  unsigned __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rdx
  unsigned __int64 v51; // rcx
  __int64 v52; // rbx
  char *v53; // r12
  size_t v54; // rbx
  __int64 v55; // rbx
  __int64 v56; // rbx
  DWORD LastError; // eax
  __int64 v58; // [rsp+50h] [rbp-B8h] BYREF
  _WORD *v59; // [rsp+58h] [rbp-B0h]
  void *v60; // [rsp+60h] [rbp-A8h]
  __int64 v61; // [rsp+68h] [rbp-A0h]
  struct _ASSEMBLY_IDENTITY *v62; // [rsp+70h] [rbp-98h]
  void *Src; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v64; // [rsp+80h] [rbp-88h]
  _DWORD *v65; // [rsp+88h] [rbp-80h]
  __int64 v66; // [rsp+90h] [rbp-78h]
  void *v67; // [rsp+98h] [rbp-70h] BYREF
  int v68; // [rsp+A0h] [rbp-68h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-48h]
  int v71; // [rsp+C8h] [rbp-40h]
  int *v72; // [rsp+D0h] [rbp-38h]
  _BYTE v73[16]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v74; // [rsp+E8h] [rbp-20h]
  __int64 v75; // [rsp+F8h] [rbp-10h]

  v9 = 0;
  v10 = *a2;
  v64 = a6;
  v11 = a5;
  v65 = a8;
  v12 = a7;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D3C0;
  v72 = &v68;
  v61 = a4;
  v62 = a3;
  v66 = (__int64)a5;
  v68 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v70 = 544438355;
  v71 = 1629;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( (a1 & 0x10) != 0 && ((_BYTE)a2[1] & 4) == 0
    || (a1 & 2) != 0 && ((_BYTE)a2[1] & 1) != 0
    || (a1 & 4) != 0 && ((_BYTE)a2[1] & 2) != 0
    || (a1 & 8) != 0 && ((_BYTE)a2[1] & 2) == 0
    || (a1 & 0x40) != 0 && ((_BYTE)a2[1] & 8) != 0
    || (a1 & 0x80u) != 0 && ((_BYTE)a2[1] & 0x10) != 0 )
  {
    v68 = 1;
    goto LABEL_21;
  }
  while ( 1 )
  {
    while ( 1 )
    {
LABEL_10:
      v14 = *v10;
      LOWORD(v58) = v14;
      if ( !v14 )
      {
        SetLastError(0);
        *v72 = 1;
        goto LABEL_21;
      }
      ++v10;
      if ( v14 == 36 )
        break;
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBufferPreserveContentsInternal(
                            v12,
                            v12[4] + 2LL) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075930);
        goto LABEL_21;
      }
      v50 = v12[4];
      v51 = v12[3] - v50;
      if ( v51 )
      {
        v52 = 1;
        v53 = (char *)(v12[2] + 2 * v50);
        if ( v51 <= 1 )
          v52 = v51 - 1;
        v54 = 2 * v52;
        memcpy_0(v53, &v58, v54);
        *(_WORD *)&v53[v54] = 0;
      }
      ++v12[4];
      v11 = (__int64 *)v66;
      ++v9;
    }
    v15 = *v10;
    v16 = ++v10;
    if ( v15 != 77 )
      break;
    if ( v9 )
      goto LABEL_125;
    SetLastError(0);
    if ( !(unsigned int)SxspGetInstalledPath((a1 >> 2) & 8, 1u, v11[1], *v11, v62, v61, (__int64)v12) )
    {
      *v72 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075910);
      goto LABEL_21;
    }
    if ( *v16 )
      goto LABEL_125;
LABEL_16:
    v11 = (__int64 *)v66;
    ++v9;
  }
  switch ( v15 )
  {
    case '.':
      if ( v9 )
        goto LABEL_125;
      v30 = v64;
      if ( !*v64 )
        goto LABEL_125;
      SetLastError(0);
      v31 = *v30;
      v32 = *v30 + 1;
      if ( v32 <= 1 )
      {
        v12 = a7;
      }
      else
      {
        v33 = a7;
        v60 = (void *)v30[1];
        v34 = a7[3];
        v35 = v32 + a7[4];
        v59 = (_WORD *)v35;
        if ( v35 > v34 )
        {
          v44 = (unsigned int (__fastcall **)(_QWORD *, unsigned __int64, void **))*a7;
          v67 = 0;
          if ( !(*v44)(a7, v35, &v67) )
          {
            *v72 = 0;
            FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800758D0);
            goto LABEL_21;
          }
          v33 = a7;
          if ( v35 )
          {
            v45 = (const void *)a7[2];
            Src = v67;
            if ( v45 )
            {
              v46 = a7[4];
              if ( v46 >= v35 )
                v46 = v35 - 1;
              v47 = 2 * v46;
              memcpy_0(v67, v45, 2 * v46);
              v33 = a7;
              *(_WORD *)((char *)Src + v47) = 0;
              v35 = (unsigned __int64)v59;
            }
            else
            {
              *(_WORD *)v67 = 0;
            }
          }
          v59 = (_WORD *)v33[2];
          if ( v59 )
          {
            v48 = (*(__int64 (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
            if ( v59 != (_WORD *)v48 )
              (*(void (__fastcall **)(_QWORD *))(*a7 + 8LL))(a7);
            v33 = a7;
          }
          v34 = v35;
          v33[2] = v67;
          v33[3] = v35;
        }
        v36 = v33[4];
        v37 = v34 - v36;
        if ( v37 )
        {
          v38 = (_WORD *)(v33[2] + 2 * v36);
          v59 = v38;
          if ( v60 )
          {
            if ( v31 >= v37 )
              v31 = v37 - 1;
            memcpy_0(v38, v60, 2 * v31);
            v59[v31] = 0;
          }
          else
          {
            *v38 = 0;
          }
        }
        v12 = a7;
        a7[4] = v32 + a7[4] - 1LL;
      }
      v9 = 1;
      v11 = (__int64 *)v66;
      *v65 = 1;
      goto LABEL_10;
    case 'G':
      SetLastError(0);
      if ( (unsigned int)SxspGenerateNdpGACPath(v17, v62, (int *)v61, (__int64)v12) )
        goto LABEL_16;
      *v72 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800758F0);
      goto LABEL_21;
    case 'L':
      if ( (a1 & 2) != 0 )
        goto LABEL_125;
      v49 = v61;
      if ( (*(_BYTE *)v61 & 0x10) != 0 )
        goto LABEL_72;
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            v62,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                            (const unsigned __int16 **)(v49 + 72),
                            (unsigned __int64 *)(v49 + 80)) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800758B0);
        goto LABEL_21;
      }
      *(_DWORD *)v49 |= 0x10u;
LABEL_72:
      if ( !*(_QWORD *)(v49 + 80) )
        goto LABEL_16;
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(
                            v12,
                            *(_QWORD *)(v49 + 72),
                            *(_QWORD *)(v49 + 80)) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075890);
        goto LABEL_21;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v12, "\\", 1) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075870);
        goto LABEL_21;
      }
      goto LABEL_16;
    case 'N':
      v20 = v61;
      if ( (*(_BYTE *)v61 & 1) != 0 )
        goto LABEL_24;
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            0,
                            v62,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                            (const unsigned __int16 **)(v20 + 8),
                            (unsigned __int64 *)(v20 + 16)) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075850);
        goto LABEL_21;
      }
      *(_DWORD *)v20 |= 1u;
LABEL_24:
      if ( !*(_QWORD *)(v20 + 16) )
        goto LABEL_125;
      SetLastError(0);
      v21 = *(_QWORD *)(v20 + 16);
      v22 = v21 + 1;
      if ( v21 + 1 <= 1 )
      {
        v12 = a7;
        goto LABEL_16;
      }
      v23 = a7;
      Src = *(void **)(v20 + 8);
      v24 = (_WORD *)a7[3];
      v25 = (_WORD *)(v22 + a7[4]);
      v59 = v25;
      if ( v25 > v24 )
      {
        v39 = (unsigned int (__fastcall **)(_QWORD *, _WORD *, void **))*a7;
        v67 = 0;
        if ( !(*v39)(a7, v25, &v67) )
        {
          *v72 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075830);
          goto LABEL_21;
        }
        v23 = a7;
        if ( v25 )
        {
          v40 = (const void *)a7[2];
          v60 = v67;
          if ( v40 )
          {
            v41 = a7[4];
            if ( v41 >= (unsigned __int64)v25 )
              v41 = (unsigned __int64)v25 - 1;
            v42 = 2 * v41;
            memcpy_0(v67, v40, 2 * v41);
            v23 = a7;
            *(_WORD *)((char *)v60 + v42) = 0;
            v25 = v59;
          }
          else
          {
            *(_WORD *)v67 = 0;
          }
        }
        v60 = (void *)v23[2];
        if ( v60 )
        {
          v43 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          if ( v60 != v43 )
            (*(void (__fastcall **)(_QWORD *))(*a7 + 8LL))(a7);
          v23 = a7;
        }
        v24 = v25;
        v23[2] = v67;
        v23[3] = v25;
      }
      v26 = v23[4];
      v27 = (unsigned __int64)v24 - v26;
      if ( v27 )
      {
        v28 = (_WORD *)(v23[2] + 2 * v26);
        v60 = v28;
        if ( Src )
        {
          if ( v21 >= v27 )
            v21 = v27 - 1;
          memcpy_0(v28, Src, 2 * v21);
          *((_WORD *)v60 + v21) = 0;
        }
        else
        {
          *v28 = 0;
        }
      }
      v12 = a7;
      v29 = v22 + a7[4] - 1LL;
      v11 = (__int64 *)v66;
      a7[4] = v29;
      ++v9;
      goto LABEL_10;
    case 'P':
      CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
      v56 = v61;
      if ( (*(_BYTE *)v61 & 1) != 0 )
        goto LABEL_108;
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            0,
                            v62,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                            (const unsigned __int16 **)(v56 + 8),
                            (unsigned __int64 *)(v56 + 16)) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800757B0);
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
        goto LABEL_21;
      }
      *(_DWORD *)v56 |= 1u;
LABEL_108:
      if ( !*(_QWORD *)(v56 + 16) )
      {
        SetLastError(0x54Fu);
        *v72 = 0;
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
        goto LABEL_21;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspGenerateAssemblyNamePrimeFromName(*(_QWORD *)(v56 + 8), *(_QWORD *)(v56 + 16), v73) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075790);
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
        goto LABEL_21;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v12, v74, v75) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075770);
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
        goto LABEL_21;
      }
      CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v73);
      goto LABEL_16;
    case 'n':
      v55 = v61;
      Src = 0;
      v67 = 0;
      if ( (*(_BYTE *)v61 & 1) != 0 )
        goto LABEL_101;
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            0,
                            v62,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                            (const unsigned __int16 **)(v55 + 8),
                            (unsigned __int64 *)(v55 + 16)) )
      {
        *v72 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075810);
        goto LABEL_21;
      }
      *(_DWORD *)v55 |= 1u;
LABEL_101:
      if ( *(_QWORD *)(v55 + 16) )
      {
        SetLastError(0);
        if ( !(unsigned int)SxspFindLastSegmentOfAssemblyName(
                              *(const unsigned __int16 **)(v55 + 8),
                              *(_QWORD *)(v55 + 16),
                              (const unsigned __int16 **)&Src,
                              (unsigned __int64 *)&v67) )
        {
          *v72 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800757F0);
          goto LABEL_21;
        }
        SetLastError(0);
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v12, Src, v67) )
        {
          *v72 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800757D0);
          goto LABEL_21;
        }
        goto LABEL_16;
      }
LABEL_125:
      SetLastError(0x54Fu);
      *v72 = 0;
LABEL_21:
      v18 = *v72;
      if ( g_FusionEnterExitTracingEnabled )
      {
        if ( v18 )
        {
          FusionpTraceCallSuccessfulExit(0);
        }
        else
        {
          LastError = GetLastError();
          FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
        }
      }
      RtlPopFrame(&Frame);
      return v18;
    default:
      goto LABEL_125;
  }
}

```

## disassembly

```asm
0x180023320  mov     r11, rsp
0x180023323  push    rbp
0x180023324  push    rbx
0x180023325  lea     rbp, [r11-0C8h]
0x18002332c  sub     rsp, 1B8h
0x180023333  mov     rax, cs:__security_cookie
0x18002333a  xor     rax, rsp
0x18002333d  mov     [rbp+0C0h+var_40], rax
0x180023344  mov     rax, [rbp+0C0h+arg_28]
0x18002334b  mov     rbx, rdx
0x18002334e  mov     [r11+8], rsi
0x180023352  xor     esi, esi
0x180023354  mov     [r11-18h], rdi
0x180023358  mov     rdi, [rdx]
0x18002335b  mov     [rsp+1C0h+var_148], rax
0x180023360  mov     rax, [rbp+0C0h+arg_38]
0x180023367  mov     [r11-20h], r12
0x18002336b  mov     r12, [rbp+0C0h+arg_20]
0x180023372  mov     [rbp+0C0h+var_140], rax
0x180023376  lea     rax, qword_18006D3C0
0x18002337d  mov     [r11-28h], r13
0x180023381  mov     r13, [rbp+0C0h+arg_30]
0x180023388  mov     [rbp+0C0h+Frame.Context], rax
0x18002338c  lea     rax, [rbp+0C0h+var_128]
0x180023390  mov     [r11-30h], r14
0x180023394  mov     r14d, ecx
0x180023397  lea     rcx, [rbp+0C0h+Frame]; Frame
0x18002339b  mov     [rbp+0C0h+var_F8], rax
0x18002339f  mov     [rsp+1C0h+var_160], r9
0x1800233a4  mov     [rsp+1C0h+var_158], r8
0x1800233a9  mov     [rbp+0C0h+var_138], r12
0x1800233ad  mov     qword ptr [rsp+1C0h+var_180], r13
0x1800233b2  mov     [rbp+0C0h+var_128], esi
0x1800233b5  mov     [rbp+0C0h+Frame.Flags], 1
0x1800233bc  mov     [rbp+0C0h+Frame.Previous], rsi
0x1800233c0  mov     [rbp+0C0h+var_108], 20737853h
0x1800233c8  mov     [rbp+0C0h+var_100], 65Dh
0x1800233cf  call    cs:__imp_RtlPushFrame
0x1800233d6  nop     dword ptr [rax+rax+00h]
0x1800233db  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x1800233e2  jnz     loc_180023A01
0x1800233e8  mov     [rsp+1C0h+var_30], r15
0x1800233f0  test    r14b, 10h
0x1800233f4  jnz     loc_180023A99
0x1800233fa  mov     r15d, r14d
0x1800233fd  and     r15d, 2
0x180023401  jz      short loc_18002340D
0x180023403  test    byte ptr [rbx+8], 1
0x180023407  jnz     loc_18002376C
0x18002340d  test    r14b, 4
0x180023411  jnz     loc_180023756
0x180023417  test    r14b, 8
0x18002341b  jnz     loc_180023A16
0x180023421  test    r14b, 40h
0x180023425  jnz     loc_180023AA8
0x18002342b  test    r14b, r14b
0x18002342e  js      loc_180023762
0x180023434  movzx   eax, word ptr [rdi]
0x180023437  lea     rdx, __ImageBase
0x18002343e  mov     word ptr [rsp+1C0h+var_178], ax
0x180023443  test    ax, ax
0x180023446  jz      loc_180023534
0x18002344c  add     rdi, 2
0x180023450  cmp     ax, 24h ; '$'
0x180023454  jnz     loc_18002398E
0x18002345a  movzx   eax, word ptr [rdi]
0x18002345d  lea     rbx, [rdi+2]
0x180023461  mov     rdi, rbx
0x180023464  cmp     eax, 4Dh ; 'M'
0x180023467  jnz     short loc_1800234D2
0x180023469  test    rsi, rsi
0x18002346c  jnz     def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x180023472  xor     ecx, ecx; dwErrCode
0x180023474  call    cs:__imp_SetLastError
0x18002347b  nop     dword ptr [rax+rax+00h]
0x180023480  mov     rax, [rsp+1C0h+var_160]
0x180023485  mov     ecx, r14d
0x180023488  mov     r9, [r12]; int
0x18002348c  mov     edx, 1; int
0x180023491  mov     r8, [r12+8]; int
0x180023496  mov     [rsp+30h], r13; __int64
0x18002349b  mov     [rsp+1C0h+var_198], rax; __int64
0x1800234a0  mov     rax, [rsp+1C0h+var_158]
0x1800234a5  shr     ecx, 2
0x1800234a8  and     ecx, 8; int
0x1800234ab  mov     [rsp+1C0h+var_1A0], rax; struct _ASSEMBLY_IDENTITY *
0x1800234b0  call    ?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x1800234b5  test    eax, eax
0x1800234b7  jz      loc_180023E0E
0x1800234bd  cmp     [rbx], si
0x1800234c0  jnz     def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x1800234c6  mov     r12, [rbp+0C0h+var_138]
0x1800234ca  inc     rsi
0x1800234cd  jmp     loc_180023434
0x1800234d2  add     eax, 0FFFFFFD2h; switch 65 cases
0x1800234d5  cmp     eax, 40h
0x1800234d8  ja      def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x1800234de  cdqe
0x1800234e0  movzx   eax, ds:(byte_180023E90 - 180000000h)[rdx+rax]
0x1800234e8  mov     ecx, ds:(jpt_1800234F2 - 180000000h)[rdx+rax*4]
0x1800234ef  add     rcx, rdx
0x1800234f2  jmp     rcx; switch jump
0x1800234f8  xor     ecx, ecx; jumptable 00000001800234F2 case 71
0x1800234fa  call    cs:__imp_SetLastError
0x180023501  nop     dword ptr [rax+rax+00h]
0x180023506  mov     r8, [rsp+1C0h+var_160]
0x18002350b  mov     r9, r13
0x18002350e  mov     rdx, [rsp+1C0h+var_158]
0x180023513  call    ?SxspGenerateNdpGACPath@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGenerateNdpGACPath(ulong,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x180023518  test    eax, eax
0x18002351a  jnz     short loc_1800234C6
0x18002351c  mov     rax, [rbp+0C0h+var_F8]
0x180023520  lea     rcx, off_1800758F0; struct _CALL_SITE_INFO *
0x180023527  mov     dword ptr [rax], 0
0x18002352d  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180023532  jmp     short loc_18002354C
0x180023534  xor     ecx, ecx; dwErrCode
0x180023536  call    cs:__imp_SetLastError
0x18002353d  nop     dword ptr [rax+rax+00h]
0x180023542  mov     rax, [rbp+0C0h+var_F8]
0x180023546  mov     dword ptr [rax], 1
0x18002354c  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180023553  mov     rax, [rbp+0C0h+var_F8]
0x180023557  mov     r15, [rsp+1C0h+var_30]
0x18002355f  mov     r14, [rsp+1C0h+var_28]
0x180023567  mov     r13, [rsp+1C0h+var_20]
0x18002356f  mov     ebx, [rax]
0x180023571  mov     r12, [rsp+1C0h+var_18]
0x180023579  mov     rdi, [rsp+1B0h]
0x180023581  mov     rsi, [rsp+1C0h+arg_0]
0x180023589  jnz     loc_180023E49
0x18002358f  lea     rcx, [rbp+0C0h+Frame]; Frame
0x180023593  call    cs:__imp_RtlPopFrame
0x18002359a  nop     dword ptr [rax+rax+00h]
0x18002359f  mov     eax, ebx
0x1800235a1  mov     rcx, [rbp+0C0h+var_40]
0x1800235a8  xor     rcx, rsp; StackCookie
0x1800235ab  call    __security_check_cookie
0x1800235b0  add     rsp, 1B8h
0x1800235b7  pop     rbx
0x1800235b8  pop     rbp
0x1800235b9  retn
0x1800235bb  mov     rbx, [rsp+1C0h+var_160]; jumptable 00000001800234F2 case 78
0x1800235c0  test    byte ptr [rbx], 1
0x1800235c3  jz      loc_180023AD2
0x1800235c9  cmp     qword ptr [rbx+10h], 0
0x1800235ce  jz      def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x1800235d4  xor     ecx, ecx; dwErrCode
0x1800235d6  call    cs:__imp_SetLastError
0x1800235dd  nop     dword ptr [rax+rax+00h]
0x1800235e2  mov     r13, [rbx+10h]
0x1800235e6  lea     r12, [r13+1]
0x1800235ea  cmp     r12, 1
0x1800235ee  jbe     loc_180023A85
0x1800235f4  mov     rax, [rbx+8]
0x1800235f8  mov     r9, qword ptr [rsp+1C0h+var_180]
0x1800235fd  mov     [rsp+1C0h+Src], rax
0x180023602  mov     rbx, [r9+20h]
0x180023606  mov     rcx, [r9+18h]
0x18002360a  add     rbx, r12
0x18002360d  mov     [rsp+1C0h+var_170], rbx
0x180023612  cmp     rbx, rcx
0x180023615  ja      loc_180023778
0x18002361b  mov     rdx, [r9+20h]
0x18002361f  sub     rcx, rdx
0x180023622  jz      short loc_180023666
0x180023624  mov     rax, [r9+10h]
0x180023628  lea     r9, [rax+rdx*2]
0x18002362c  mov     rdx, [rsp+1C0h+Src]; Src
0x180023631  mov     [rsp+1C0h+var_168], r9
0x180023636  test    rdx, rdx
0x180023639  jz      loc_180023A0B
0x18002363f  cmp     r13, rcx
0x180023642  jnb     loc_180023B19
0x180023648  lea     rbx, ds:0[r13*2]
0x180023650  mov     rcx, r9; void *
0x180023653  mov     r8, rbx; Size
0x180023656  call    memcpy_0
0x18002365b  mov     rcx, [rsp+1C0h+var_168]
0x180023660  xor     eax, eax
0x180023662  mov     [rcx+rbx], ax
0x180023666  mov     r13, qword ptr [rsp+1C0h+var_180]
0x18002366b  mov     rcx, [r13+20h]
0x18002366f  dec     rcx
0x180023672  add     rcx, r12
0x180023675  mov     r12, [rbp+0C0h+var_138]
0x180023679  mov     [r13+20h], rcx
0x18002367d  inc     rsi
0x180023680  jmp     loc_180023434
0x180023685  test    rsi, rsi; jumptable 00000001800234F2 case 46
0x180023688  jnz     def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x18002368e  mov     rbx, [rsp+1C0h+var_148]
0x180023693  cmp     [rbx], rsi
0x180023696  jbe     def_1800234F2; jumptable 00000001800234F2 default case, cases 47-70,72-75,77,79,81-109
0x18002369c  xor     ecx, ecx; dwErrCode
0x18002369e  call    cs:__imp_SetLastError
0x1800236a5  nop     dword ptr [rax+rax+00h]
0x1800236aa  mov     r13, [rbx]
0x1800236ad  lea     r12, [r13+1]
0x1800236b1  cmp     r12, 1
0x1800236b5  jbe     loc_180023A8F
0x1800236bb  mov     rax, [rbx+8]
0x1800236bf  mov     r9, qword ptr [rsp+1C0h+var_180]
0x1800236c4  mov     [rsp+1C0h+var_168], rax
0x1800236c9  mov     rbx, [r9+20h]
0x1800236cd  mov     rcx, [r9+18h]
0x1800236d1  add     rbx, r12
0x1800236d4  mov     [rsp+1C0h+var_170], rbx
0x1800236d9  cmp     rbx, rcx
0x1800236dc  ja      loc_18002383C
0x1800236e2  mov     rdx, [r9+20h]
0x1800236e6  sub     rcx, rdx
0x1800236e9  jz      short loc_18002372D
0x1800236eb  mov     rax, [r9+10h]
0x1800236ef  lea     r9, [rax+rdx*2]
0x1800236f3  mov     rdx, [rsp+1C0h+var_168]; Src
0x1800236f8  mov     [rsp+1C0h+var_170], r9
0x1800236fd  test    rdx, rdx
0x180023700  jz      loc_180023A25
0x180023706  cmp     r13, rcx
0x180023709  jnb     loc_180023AC9
0x18002370f  lea     rbx, ds:0[r13*2]
0x180023717  mov     rcx, r9; void *
0x18002371a  mov     r8, rbx; Size
0x18002371d  call    memcpy_0
0x180023722  mov     rcx, [rsp+1C0h+var_170]
0x180023727  xor     eax, eax
0x180023729  mov     [rcx+rbx], ax
0x18002372d  mov     r13, qword ptr [rsp+1C0h+var_180]
0x180023732  mov     rcx, [r13+20h]
0x180023736  dec     rcx
0x180023739  add     rcx, r12
0x18002373c  mov     [r13+20h], rcx
0x180023740  mov     rax, [rbp+0C0h+var_140]
0x180023744  inc     rsi
0x180023747  mov     r12, [rbp+0C0h+var_138]
0x18002374b  mov     dword ptr [rax], 1
0x180023751  jmp     loc_180023434
0x180023756  test    byte ptr [rbx+8], 2
0x18002375a  jz      loc_180023417
0x180023760  jmp     short loc_18002376C
0x180023762  test    byte ptr [rbx+8], 10h
0x180023766  jz      loc_180023434
0x18002376c  mov     [rbp+0C0h+var_128], 1
0x180023773  jmp     loc_18002354C
0x180023778  mov     rax, [r9]
0x18002377b  lea     r8, [rbp+0C0h+var_130]
0x18002377f  mov     rdx, rbx
0x180023782  mov     [rbp+0C0h+var_130], 0
0x18002378a  mov     rcx, r9
0x18002378d  mov     rax, [rax]
0x180023790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023795  test    eax, eax
0x180023797  jz      loc_180023D28
0x18002379d  mov     r9, qword ptr [rsp+1C0h+var_180]
0x1800237a2  test    rbx, rbx
0x1800237a5  jz      short loc_1800237EB
0x1800237a7  mov     rdx, [r9+10h]; Src
0x1800237ab  mov     rcx, [rbp+0C0h+var_130]; void *
0x1800237af  mov     [rsp+1C0h+var_168], rcx
0x1800237b4  test    rdx, rdx
0x1800237b7  jz      loc_180023A30
0x1800237bd  mov     rax, [r9+20h]
0x1800237c1  cmp     rax, rbx
0x1800237c4  jnb     loc_180023B10
0x1800237ca  lea     rbx, [rax+rax]
0x1800237ce  mov     r8, rbx; Size
0x1800237d1  call    memcpy_0
0x1800237d6  mov     rcx, [rsp+1C0h+var_168]
0x1800237db  xor     eax, eax
0x1800237dd  mov     r9, qword ptr [rsp+1C0h+var_180]
0x1800237e2  mov     [rcx+rbx], ax
0x1800237e6  mov     rbx, [rsp+1C0h+var_170]
0x1800237eb  mov     rax, [r9+10h]
0x1800237ef  mov     [rsp+1C0h+var_168], rax
0x1800237f4  test    rax, rax
0x1800237f7  jz      short loc_180023828
0x1800237f9  mov     rax, [r9]
0x1800237fc  mov     rcx, r9
0x1800237ff  mov     rax, [rax+10h]
0x180023803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023808  mov     rdx, [rsp+1C0h+var_168]
0x18002380d  cmp     rdx, rax
0x180023810  jz      short loc_180023823
0x180023812  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x180023817  mov     rax, [rcx]
0x18002381a  mov     rax, [rax+8]
0x18002381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023823  mov     r9, qword ptr [rsp+1C0h+var_180]
0x180023828  mov     rax, [rbp+0C0h+var_130]
0x18002382c  mov     rcx, rbx
0x18002382f  mov     [r9+10h], rax
0x180023833  mov     [r9+18h], rbx
0x180023837  jmp     loc_18002361B
0x18002383c  mov     rax, [r9]
0x18002383f  lea     r8, [rbp+0C0h+var_130]
0x180023843  mov     rdx, rbx
0x180023846  mov     [rbp+0C0h+var_130], 0
0x18002384e  mov     rcx, r9
0x180023851  mov     rax, [rax]
  ... truncated ...
```
