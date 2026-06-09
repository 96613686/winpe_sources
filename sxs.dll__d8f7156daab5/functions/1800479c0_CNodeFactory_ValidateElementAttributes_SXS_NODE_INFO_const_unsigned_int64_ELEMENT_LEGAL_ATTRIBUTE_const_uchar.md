# CNodeFactory::ValidateElementAttributes(_SXS_NODE_INFO const *,unsigned __int64,_ELEMENT_LEGAL_ATTRIBUTE const *,uchar)

- ea: `0x1800479c0`
- end: `0x180048406`
- name: `?ValidateElementAttributes@CNodeFactory@@QEAAHPEBU_SXS_NODE_INFO@@_KPEBU_ELEMENT_LEGAL_ATTRIBUTE@@E@Z`
- size: `2630`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, const struct _SXS_NODE_INFO *, unsigned __int64, const struct _ELEMENT_LEGAL_ATTRIBUTE *, char)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031260`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001e5c0`
- `0x18001e5d0`
- `0x180020820`
- `0x180032350`
- `0x1800479c0`
- `0x1800515ec`
- `0x18005b8a0`
- `0x18005d2b0`
- `0x18005d428`
- `0x180067548`
- `0x180067680`
- `0x180069d70`
- `0x180069df4`
- `0x180069e80`
- `0x18006a0dd`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180047b9b`
- `ntdll!RtlCompareUnicodeString` at `0x180047c00`
- `ntdll!RtlCompareUnicodeString` at `0x180047b9b`
- `ntdll!RtlCompareUnicodeString` at `0x180047c00`
- `ntdll!RtlPopFrame` at `0x180047de1`
- `ntdll!RtlPopFrame` at `0x180047de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048163`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800481e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048163`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800481e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483b5`

## pseudocode

```c
__int64 __fastcall CNodeFactory::ValidateElementAttributes(
        CNodeFactory *this,
        const struct _SXS_NODE_INFO *a2,
        unsigned __int64 a3,
        const struct _ELEMENT_LEGAL_ATTRIBUTE *a4,
        unsigned __int8 a5)
{
  unsigned __int64 v5; // rbx
  char v6; // di
  const struct _SXS_NODE_INFO *v8; // r15
  const char *v9; // rcx
  unsigned __int8 v10; // r12
  unsigned __int64 i; // rax
  char v12; // dl
  int v13; // edx
  unsigned __int64 j; // rsi
  char *v15; // r13
  _WORD *v16; // rcx
  unsigned __int8 k; // r15
  unsigned __int64 v18; // rbx
  char *v19; // r12
  __int64 v20; // rcx
  WCHAR *v21; // rax
  WCHAR *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  WCHAR *v25; // rax
  int v26; // edx
  CNodeFactory *v27; // rbx
  bool v28; // zf
  unsigned __int64 v29; // rax
  char *v30; // rbx
  unsigned int v31; // ebx
  unsigned __int64 v33; // rdx
  const void *v34; // r10
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rbx
  unsigned __int64 v37; // rcx
  _WORD *v38; // r8
  unsigned __int64 v39; // rcx
  __int64 v40; // rbx
  unsigned __int64 v41; // rax
  __int64 v42; // rbx
  void *v43; // rax
  CNodeFactory *v44; // rdi
  const struct _SXS_NODE_INFO *v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rcx
  unsigned __int8 v48; // bl
  CNodeFactory *v49; // r13
  unsigned __int64 v50; // rdi
  __int64 v51; // rsi
  DWORD LastError; // eax
  const struct _UNICODE_STRING *v53; // [rsp+38h] [rbp-110h]
  const struct _UNICODE_STRING *v54; // [rsp+40h] [rbp-108h]
  const struct _UNICODE_STRING *v55; // [rsp+48h] [rbp-100h]
  const struct _UNICODE_STRING *v56; // [rsp+50h] [rbp-F8h]
  const struct _UNICODE_STRING *v57; // [rsp+58h] [rbp-F0h]
  const struct _UNICODE_STRING *v58; // [rsp+60h] [rbp-E8h]
  const struct _UNICODE_STRING *v59; // [rsp+68h] [rbp-E0h]
  const struct _UNICODE_STRING *v60; // [rsp+70h] [rbp-D8h]
  const struct _UNICODE_STRING *v61; // [rsp+78h] [rbp-D0h]
  const struct _UNICODE_STRING *v62; // [rsp+80h] [rbp-C8h]
  const struct _UNICODE_STRING *v63; // [rsp+88h] [rbp-C0h]
  const struct _UNICODE_STRING *v64; // [rsp+90h] [rbp-B8h]
  const struct _UNICODE_STRING *v65; // [rsp+98h] [rbp-B0h]
  const struct _UNICODE_STRING *v66; // [rsp+A0h] [rbp-A8h]
  const struct _UNICODE_STRING *v67; // [rsp+A8h] [rbp-A0h]
  const struct _UNICODE_STRING *v68; // [rsp+B0h] [rbp-98h]
  const struct _UNICODE_STRING *v69; // [rsp+B8h] [rbp-90h]
  char v70; // [rsp+C8h] [rbp-80h]
  int v71; // [rsp+CCh] [rbp-7Ch]
  __int64 v72; // [rsp+D0h] [rbp-78h]
  const struct _SXS_NODE_INFO *v73; // [rsp+D8h] [rbp-70h]
  unsigned __int64 v74; // [rsp+E0h] [rbp-68h]
  CNodeFactory *v75; // [rsp+E8h] [rbp-60h]
  unsigned __int64 v76; // [rsp+F0h] [rbp-58h]
  unsigned __int64 v77; // [rsp+F8h] [rbp-50h]
  char *v78; // [rsp+100h] [rbp-48h]
  unsigned __int64 v79; // [rsp+108h] [rbp-40h]
  unsigned __int64 v80; // [rsp+110h] [rbp-38h]
  void *v81; // [rsp+118h] [rbp-30h] BYREF
  UNICODE_STRING String2; // [rsp+120h] [rbp-28h] BYREF
  UNICODE_STRING v83; // [rsp+130h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+140h] [rbp-8h] BYREF
  char v85[4]; // [rsp+150h] [rbp+8h] BYREF
  int v86; // [rsp+154h] [rbp+Ch] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+158h] [rbp+10h] BYREF
  __int64 v88; // [rsp+170h] [rbp+28h]
  int v89; // [rsp+178h] [rbp+30h]
  unsigned int *v90; // [rsp+180h] [rbp+38h]
  struct _UNICODE_STRING v91; // [rsp+188h] [rbp+40h] BYREF
  void **v92; // [rsp+198h] [rbp+50h] BYREF
  int v93; // [rsp+1A0h] [rbp+58h]
  void *Src; // [rsp+1A8h] [rbp+60h]
  unsigned __int64 v95; // [rsp+1B0h] [rbp+68h]
  __int16 v96[4]; // [rsp+1B8h] [rbp+70h]
  __int16 v97; // [rsp+1C0h] [rbp+78h] BYREF
  _BYTE v98[16]; // [rsp+248h] [rbp+100h] BYREF
  unsigned __int16 *v99; // [rsp+258h] [rbp+110h]

  v5 = a3;
  v6 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800716B0;
  v75 = this;
  v90 = (unsigned int *)&v86;
  v8 = a2;
  v74 = a3;
  v73 = a2;
  v86 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v88 = 544438355;
  v89 = 3882;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( v5 && !v8 )
  {
    v89 = 3890;
    FusionpTraceParameterCheck(v9);
    SetLastError(0x57u);
    *v90 = 0;
  }
  else
  {
    v10 = a5;
    if ( !a5 || a4 )
    {
      for ( i = 0; i < a5; v6 = v12 )
      {
        v12 = v6 + 1;
        if ( (*((_DWORD *)a4 + 8 * i) & 2) == 0 )
          v12 = v6;
        ++i;
      }
      v13 = 0;
      v72 = 0;
      v71 = 0;
      v70 = 0;
      for ( j = 0; ; ++j )
      {
        if ( j >= v5 )
        {
          if ( v70 != v6 )
          {
            v48 = 0;
            if ( v10 )
            {
              v49 = v75;
              v50 = 0;
              do
              {
                v51 = 32 * v50;
                if ( (*((_BYTE *)a4 + 32 * v50) & 2) != 0 )
                {
                  if ( ((unsigned __int8)(1 << v48) & *((_BYTE *)&v72 + (v50 >> 5))) != 0 )
                  {
                    v13 = v71;
                  }
                  else
                  {
                    FusionpLogRequiredAttributeMissingParseError(
                      *(const unsigned __int16 **)(*((_QWORD *)v49 + 2) + 1312LL),
                      *((const unsigned __int16 **)v49 + 56),
                      *((_QWORD *)v49 + 57),
                      *((_DWORD *)v49 + 118),
                      *((const unsigned __int16 **)v8 + 22),
                      *((_QWORD *)v8 + 23),
                      *(const unsigned __int16 **)(*(_QWORD *)((char *)a4 + v51 + 8) + 16LL),
                      *(_QWORD *)(*(_QWORD *)((char *)a4 + v51 + 8) + 24LL));
                    TraceActCtxGenManifestParseError(
                      *(_DWORD *)(*((_QWORD *)v49 + 2) + 1304LL),
                      *((_DWORD *)v49 + 118),
                      *((const unsigned __int16 **)v8 + 22),
                      *(const unsigned __int16 **)(*(_QWORD *)((char *)a4 + v51 + 8) + 16LL),
                      0,
                      0x78u);
                    v13 = 1;
                    v71 = 1;
                  }
                }
                ++v48;
                ++v50;
              }
              while ( v48 < v10 );
            }
          }
          if ( v13 )
          {
            SetLastError(0x36B5u);
            *v90 = 0;
            FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078A08);
          }
          else
          {
            SetLastError(0);
            *v90 = 1;
          }
          goto LABEL_45;
        }
        v15 = (char *)v8 + 192 * j;
        if ( *((_DWORD *)v15 + 1) == 2 )
        {
          v16 = (_WORD *)*((_QWORD *)v15 + 22);
          v76 = *((_QWORD *)v15 + 23);
          v81 = v16;
          if ( (v76 < 3 || ((*v16 - 88) & 0xFFDF) != 0 || ((v16[1] - 77) & 0xFFDF) != 0 || ((v16[2] - 76) & 0xFFDF) != 0)
            && !*((_QWORD *)v15 + 5) )
          {
            break;
          }
        }
LABEL_31:
        ;
      }
      for ( k = 0; ; ++k )
      {
        if ( k >= v10 )
        {
          v27 = v75;
LABEL_28:
          v28 = k == v10;
          v8 = v73;
          if ( v28 )
          {
            FusionpLogAttributeNotAllowedParseError(
              *(const unsigned __int16 **)(*((_QWORD *)v27 + 2) + 1312LL),
              *((const unsigned __int16 **)v27 + 56),
              *((_QWORD *)v27 + 57),
              *((_DWORD *)v27 + 118),
              *((const unsigned __int16 **)v73 + 22),
              *((_QWORD *)v73 + 23),
              *((const unsigned __int16 **)v15 + 22),
              *((_QWORD *)v15 + 23));
            TraceActCtxGenManifestParseError(
              *(_DWORD *)(*((_QWORD *)v27 + 2) + 1304LL),
              *((_DWORD *)v27 + 118),
              *((const unsigned __int16 **)v8 + 22),
              *((const unsigned __int16 **)v15 + 22),
              0,
              0x7Au);
            v13 = 1;
            v71 = 1;
          }
          else
          {
LABEL_29:
            v13 = v71;
          }
          v5 = v74;
          goto LABEL_31;
        }
        v18 = k;
        v77 = k;
        v19 = (char *)a4 + 32 * k;
        v20 = *((_QWORD *)v19 + 1);
        if ( v20 )
        {
          if ( !*(_QWORD *)(v20 + 8) )
          {
            v21 = (WCHAR *)*((_QWORD *)v15 + 3);
            String2 = 0;
            *(_QWORD *)&String1.Length = 0;
            String1.Buffer = v21;
            v22 = *(WCHAR **)v20;
            String2.Length = 0;
            String2.MaximumLength = 0;
            String2.Buffer = v22;
            if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
            {
              v23 = *((_QWORD *)v19 + 1);
              v24 = *(_QWORD *)(v23 + 24);
              if ( v76 == v24 )
              {
                *(&v83.MaximumLength + 2) = 0;
                v83.Buffer = (PWSTR)v81;
                String2 = 0;
                v83.Length = 2 * v76;
                *(_DWORD *)&v83.MaximumLength = (unsigned __int16)(2 * v76);
                v25 = *(WCHAR **)(v23 + 16);
                String2.Length = 2 * v24;
                String2.MaximumLength = 2 * v24;
                String2.Buffer = v25;
                if ( !RtlCompareUnicodeString(&v83, &String2, 0) )
                  break;
              }
            }
          }
        }
        v10 = a5;
      }
      if ( !*((_QWORD *)v19 + 2) )
        goto LABEL_24;
      v93 = 0;
      Src = 0;
      v95 = 0;
      *(_QWORD *)v96 = 0;
      v92 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
      v97 = 0;
      Src = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v92);
      v95 = ((__int64 (__fastcall *)(void ***))v92[3])(&v92);
      if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
        memset_0(Src, 0, 2 * v95);
      v85[0] = 0;
      v29 = j + 1;
      *(_QWORD *)&v91.Length = 0;
      while ( 1 )
      {
        v76 = v29;
        if ( v29 >= v74 )
          break;
        v30 = (char *)v73 + 192 * v29;
        if ( *((_DWORD *)v30 + 1) != 13 )
          break;
        SetLastError(0);
        v33 = *((_QWORD *)v30 + 23);
        v80 = v33;
        *(_QWORD *)&String2.Length = v33 + 1;
        if ( v33 + 1 > 1 )
        {
          v34 = (const void *)*((_QWORD *)v30 + 22);
          v35 = *(_QWORD *)v96;
          *(_QWORD *)&v83.Length = v34;
          v36 = v33 + 1 + *(_QWORD *)v96;
          v37 = v95;
          v79 = v36;
          if ( v36 > v95 )
          {
            v81 = 0;
            if ( !((unsigned int (__fastcall *)(void ***, unsigned __int64, void **))*v92)(
                    &v92,
                    v33 + 1 + *(_QWORD *)v96,
                    &v81) )
            {
              *v90 = 0;
              FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078AA8);
LABEL_84:
              CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(&v92);
              goto LABEL_45;
            }
            if ( v36 )
            {
              v78 = (char *)v81;
              if ( Src )
              {
                v41 = *(_QWORD *)v96;
                if ( *(_QWORD *)v96 >= v36 )
                  v41 = v36 - 1;
                v42 = 2 * v41;
                memcpy_0(v81, Src, 2 * v41);
                *(_WORD *)&v78[v42] = 0;
                v36 = v79;
              }
              else
              {
                *(_WORD *)v81 = 0;
              }
            }
            if ( Src )
            {
              v43 = (void *)((__int64 (__fastcall *)(void ***))v92[2])(&v92);
              if ( Src != v43 )
                ((void (__fastcall *)(void ***))v92[1])(&v92);
            }
            v38 = v81;
            v37 = v36;
            v35 = *(_QWORD *)v96;
            v33 = v80;
            v34 = *(const void **)&v83.Length;
            Src = v81;
            v95 = v36;
          }
          else
          {
            v38 = Src;
          }
          v39 = v37 - v35;
          if ( v39 )
          {
            *(_QWORD *)&v83.Length = &v38[v35];
            if ( v34 )
            {
              if ( v33 >= v39 )
                v33 = v39 - 1;
              v40 = 2 * v33;
              memcpy_0(&v38[v35], v34, 2 * v33);
              *(_WORD *)(v40 + *(_QWORD *)&v83.Length) = 0;
            }
            else
            {
              v38[v35] = 0;
            }
            v35 = *(_QWORD *)v96;
          }
          *(_QWORD *)v96 = *(_QWORD *)&String2.Length - 1LL + v35;
        }
        v29 = v76 + 1;
      }
      SetLastError(0);
      if ( (*((unsigned int (__fastcall **)(_QWORD, void ***, char *, _QWORD, _QWORD, struct _UNICODE_STRING *))v19 + 2))(
             *((unsigned int *)v19 + 6),
             &v92,
             v85,
             0,
             0,
             &v91) )
      {
        if ( !v85[0] )
        {
          _mm_lfence();
          v44 = v75;
          v45 = v73;
          FusionpLogInvalidAttributeValueParseError(
            *(const unsigned __int16 **)(*((_QWORD *)v75 + 2) + 1312LL),
            *((const unsigned __int16 **)v75 + 56),
            *((_QWORD *)v75 + 57),
            *((_DWORD *)v75 + 118),
            *((const unsigned __int16 **)v73 + 22),
            *((_QWORD *)v73 + 23),
            *(const unsigned __int16 **)(*((_QWORD *)v19 + 1) + 16LL),
            *(_QWORD *)(*((_QWORD *)v19 + 1) + 24LL),
            (const unsigned __int16 *)Src,
            v96[0]);
          CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v98);
          SetLastError(0);
          if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(
                               v98,
                               *((_QWORD *)v45 + 22),
                               *((_QWORD *)v45 + 23)) )
          {
            _mm_lfence();
            TraceActCtxGenManifestParseError(
              *(_DWORD *)(*((_QWORD *)v44 + 2) + 1304LL),
              *((_DWORD *)v44 + 118),
              v99,
              *(const unsigned __int16 **)(*((_QWORD *)v19 + 1) + 16LL),
              (const unsigned __int16 *)Src,
              0x79u);
            SetLastError(0x36B5u);
            *v90 = 0;
            FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078A48);
          }
          else
          {
            *v90 = 0;
            FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078A68);
          }
          CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v98);
          goto LABEL_84;
        }
        v92 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
        if ( Src != &v97 )
          CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v92);
        v18 = v77;
LABEL_24:
        v26 = *(_DWORD *)v19;
        if ( (*(_DWORD *)v19 & 2) != 0 )
        {
          ++v70;
          *((_BYTE *)&v72 + (v18 >> 5)) |= 1 << (k & 0x1F);
        }
        v27 = v75;
        if ( (*(_BYTE *)(*((_QWORD *)v75 + 2) + 1204LL) & 4) == 0 )
        {
          v10 = a5;
          v8 = v73;
          goto LABEL_29;
        }
        if ( (v26 & 4) == 0 )
        {
          v10 = a5;
          goto LABEL_28;
        }
        _mm_lfence();
        String1.Buffer = (PWSTR)*((_QWORD *)v75 + 52);
        String1.Length = 2 * *((_WORD *)v75 + 212);
        String1.MaximumLength = String1.Length;
        v46 = *((_QWORD *)v19 + 1);
        v47 = *(_QWORD *)(v46 + 24);
        v91.Buffer = *(PWSTR *)(v46 + 16);
        v91.Length = 2 * v47;
        v91.MaximumLength = 2 * v47;
        CNodeFactory::LogParseError(
          v75,
          0xC1010052,
          0x9Bu,
          &v91,
          &String1,
          0,
          v53,
          v54,
          v55,
          v56,
          v57,
          v58,
          v59,
          v60,
          v61,
          v62,
          v63,
          v64,
          v65,
          v66,
          v67,
          v68,
          v69);
        SetLastError(0x36B5u);
        *v90 = 0;
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078A28);
      }
      else
      {
        *v90 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078A88);
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(&v92);
      }
    }
    else
    {
      v89 = 3891;
      FusionpTraceParameterCheck(v9);
      SetLastError(0x57u);
      *v90 = 0;
    }
  }
LABEL_45:
  v31 = *v90;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v31 )
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
  return v31;
}

```

## disassembly

```asm
0x1800479c0  mov     r11, rsp
0x1800479c3  push    rbp
0x1800479c4  push    rbx
0x1800479c5  lea     rbp, [r11-1F8h]
0x1800479cc  sub     rsp, 328h
0x1800479d3  mov     rax, cs:__security_cookie
0x1800479da  xor     rax, rsp
0x1800479dd  mov     [rbp+1F0h+var_40], rax
0x1800479e4  mov     [r11-18h], rdi
0x1800479e8  lea     rax, qword_1800716B0
0x1800479ef  mov     [r11-28h], r13
0x1800479f3  mov     rbx, r8
0x1800479f6  mov     [r11-30h], r14
0x1800479fa  xor     edi, edi
0x1800479fc  mov     [rbp+1F0h+Frame.Context], rax
0x180047a00  mov     r14, r9
0x180047a03  lea     rax, [rbp+1F0h+var_1E4]
0x180047a07  mov     [rbp+1F0h+var_250], rcx
0x180047a0b  mov     [r11-38h], r15
0x180047a0f  lea     rcx, [rbp+1F0h+Frame]; this
0x180047a13  mov     [rbp+1F0h+var_1B8], rax
0x180047a17  mov     r15, rdx
0x180047a1a  mov     [rbp+1F0h+var_258], rbx
0x180047a1e  mov     [rbp+1F0h+var_260], rdx
0x180047a22  mov     [rbp+1F0h+var_1E4], edi
0x180047a25  mov     [rbp+1F0h+Frame.Flags], 1
0x180047a2c  mov     [rbp+1F0h+Frame.Previous], rdi
0x180047a30  mov     [rbp+1F0h+var_1C8], 20737853h
0x180047a38  mov     [rbp+1F0h+var_1C0], 0F2Ah
0x180047a3f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180047a44  test    rbx, rbx
0x180047a47  jz      short loc_180047A52
0x180047a49  test    r15, r15
0x180047a4c  jz      loc_180047FDB
0x180047a52  mov     [rsp+330h+var_18], r12
0x180047a5a  movzx   r12d, [rbp+1F0h+arg_20]
0x180047a62  test    r12b, r12b
0x180047a65  jnz     loc_180047F7E
0x180047a6b  xor     eax, eax
0x180047a6d  mov     [rsp+330h+arg_10], rsi
0x180047a75  test    r12b, r12b
0x180047a78  jz      short loc_180047AA7
0x180047a7a  nop     word ptr [rax+rax+00h]
0x180047a80  mov     rcx, rax
0x180047a83  shl     rcx, 5
0x180047a87  mov     r8d, [rcx+r14]
0x180047a8b  lea     ecx, [rdi+1]
0x180047a8e  movzx   edx, cl
0x180047a91  test    r8b, 2
0x180047a95  movzx   ecx, dil
0x180047a99  cmovz   edx, ecx
0x180047a9c  inc     rax
0x180047a9f  movzx   edi, dl
0x180047aa2  cmp     rax, r12
0x180047aa5  jb      short loc_180047A80
0x180047aa7  xor     edx, edx
0x180047aa9  mov     [rbp+1F0h+var_268], 0
0x180047ab1  xor     al, al
0x180047ab3  mov     [rbp+1F0h+var_26C], edx
0x180047ab6  mov     [rbp+1F0h+var_270], al
0x180047ab9  xor     esi, esi
0x180047abb  mov     r9d, 0FFDFh
0x180047ac1  cmp     rsi, rbx
0x180047ac4  jnb     loc_180047D70
0x180047aca  lea     r13, [rsi+rsi*2]
0x180047ace  shl     r13, 6
0x180047ad2  add     r13, r15
0x180047ad5  cmp     dword ptr [r13+4], 2
0x180047ada  jnz     loc_180047C7B
0x180047ae0  mov     r8, [r13+0B8h]
0x180047ae7  mov     rcx, [r13+0B0h]
0x180047aee  mov     [rbp+1F0h+var_248], r8
0x180047af2  mov     [rbp+1F0h+var_220], rcx
0x180047af6  cmp     r8, 3
0x180047afa  jb      short loc_180047B1B
0x180047afc  movzx   eax, word ptr [rcx]
0x180047aff  sub     ax, 58h ; 'X'
0x180047b03  test    r9w, ax
0x180047b07  jnz     short loc_180047B1B
0x180047b09  movzx   eax, word ptr [rcx+2]
0x180047b0d  sub     ax, 4Dh ; 'M'
0x180047b11  test    r9w, ax
0x180047b15  jz      loc_180047FAF
0x180047b1b  cmp     qword ptr [r13+28h], 0
0x180047b20  jnz     loc_180047C7B
0x180047b26  xor     r15b, r15b
0x180047b29  nop     dword ptr [rax+00000000h]
0x180047b30  cmp     r15b, r12b
0x180047b33  jnb     loc_18004802B
0x180047b39  movzx   ebx, r15b
0x180047b3d  mov     r12d, ebx
0x180047b40  mov     [rbp+1F0h+var_240], rbx
0x180047b44  shl     r12, 5
0x180047b48  add     r12, r14
0x180047b4b  mov     rcx, [r12+8]
0x180047b50  test    rcx, rcx
0x180047b53  jnz     short loc_180047B62
0x180047b55  movzx   r12d, [rbp+1F0h+arg_20]
0x180047b5d  inc     r15b
0x180047b60  jmp     short loc_180047B30
0x180047b62  mov     rdx, [rcx+8]
0x180047b66  test    rdx, rdx
0x180047b69  jnz     short loc_180047B55
0x180047b6b  mov     rax, [r13+18h]
0x180047b6f  xorps   xmm0, xmm0
0x180047b72  movups  xmmword ptr [rbp+1F0h+String2.Length], xmm0
0x180047b76  mov     qword ptr [rbp+1F0h+String1.Length], rdx
0x180047b7a  xor     r8d, r8d; CaseInsensitive
0x180047b7d  add     dx, dx
0x180047b80  mov     [rbp+1F0h+String1.Buffer], rax
0x180047b84  mov     rax, [rcx]
0x180047b87  lea     rcx, [rbp+1F0h+String1]; String1
0x180047b8b  mov     [rbp+1F0h+String2.Length], dx
0x180047b8f  mov     [rbp+1F0h+String2.MaximumLength], dx
0x180047b93  lea     rdx, [rbp+1F0h+String2]; String2
0x180047b97  mov     [rbp+1F0h+String2.Buffer], rax
0x180047b9b  call    cs:__imp_RtlCompareUnicodeString
0x180047ba2  nop     dword ptr [rax+rax+00h]
0x180047ba7  test    eax, eax
0x180047ba9  jnz     short loc_180047B55
0x180047bab  mov     rdx, [r12+8]
0x180047bb0  mov     r8, [rbp+1F0h+var_248]
0x180047bb4  mov     rcx, [rdx+18h]
0x180047bb8  cmp     r8, rcx
0x180047bbb  jnz     short loc_180047B55
0x180047bbd  mov     rax, [rbp+1F0h+var_220]
0x180047bc1  add     cx, cx
0x180047bc4  xorps   xmm0, xmm0
0x180047bc7  xorps   xmm1, xmm1
0x180047bca  movups  xmmword ptr [rbp+1F0h+var_208.Length], xmm0
0x180047bce  mov     [rbp+1F0h+var_208.Buffer], rax
0x180047bd2  movzx   eax, r8w
0x180047bd6  add     ax, ax
0x180047bd9  xor     r8d, r8d; CaseInsensitive
0x180047bdc  movups  xmmword ptr [rbp+1F0h+String2.Length], xmm1
0x180047be0  mov     [rbp+1F0h+var_208.Length], ax
0x180047be4  mov     [rbp+1F0h+var_208.MaximumLength], ax
0x180047be8  mov     rax, [rdx+10h]
0x180047bec  lea     rdx, [rbp+1F0h+String2]; String2
0x180047bf0  mov     [rbp+1F0h+String2.Length], cx
0x180047bf4  mov     [rbp+1F0h+String2.MaximumLength], cx
0x180047bf8  lea     rcx, [rbp+1F0h+var_208]; String1
0x180047bfc  mov     [rbp+1F0h+String2.Buffer], rax
0x180047c00  call    cs:__imp_RtlCompareUnicodeString
0x180047c07  nop     dword ptr [rax+rax+00h]
0x180047c0c  test    eax, eax
0x180047c0e  jnz     loc_180047B55
0x180047c14  cmp     qword ptr [r12+10h], 0
0x180047c1a  jnz     short loc_180047C83
0x180047c1c  mov     edx, [r12]
0x180047c20  test    dl, 2
0x180047c23  jz      short loc_180047C3E
0x180047c25  shr     rbx, 5
0x180047c29  mov     eax, r15d
0x180047c2c  and     eax, 1Fh
0x180047c2f  movzx   ecx, byte ptr [rbp+rbx+1F0h+var_268]
0x180047c34  bts     ecx, eax
0x180047c37  inc     [rbp+1F0h+var_270]
0x180047c3a  mov     byte ptr [rbp+rbx+1F0h+var_268], cl
0x180047c3e  mov     rbx, [rbp+1F0h+var_250]
0x180047c42  mov     rax, [rbx+10h]
0x180047c46  test    byte ptr [rax+4B4h], 4
0x180047c4d  jnz     loc_180048015
0x180047c53  movzx   r12d, [rbp+1F0h+arg_20]
0x180047c5b  mov     r15, [rbp+1F0h+var_260]
0x180047c5f  jmp     short loc_180047C6E
0x180047c61  cmp     r15b, r12b
0x180047c64  mov     r15, [rbp+1F0h+var_260]
0x180047c68  jz      loc_180048034
0x180047c6e  mov     edx, [rbp+1F0h+var_26C]
0x180047c71  mov     rbx, [rbp+1F0h+var_258]
0x180047c75  mov     r9d, 0FFDFh
0x180047c7b  inc     rsi
0x180047c7e  jmp     loc_180047AC1
0x180047c83  xor     ebx, ebx
0x180047c85  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180047c8c  lea     rcx, [rbp+1F0h+var_1A0]
0x180047c90  mov     [rbp+1F0h+var_198], ebx
0x180047c93  mov     [rbp+1F0h+Src], rbx
0x180047c97  mov     [rbp+1F0h+var_188], rbx
0x180047c9b  mov     qword ptr [rbp+1F0h+var_180], rbx
0x180047c9f  mov     [rbp+1F0h+var_1A0], rax
0x180047ca3  mov     [rbp+1F0h+var_178], bx
0x180047ca7  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180047cac  mov     [rbp+1F0h+Src], rax
0x180047cb0  lea     rcx, [rbp+1F0h+var_1A0]
0x180047cb4  mov     rax, [rbp+1F0h+var_1A0]
0x180047cb8  mov     rax, [rax+18h]
0x180047cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cc1  mov     [rbp+1F0h+var_188], rax
0x180047cc5  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180047cca  test    eax, eax
0x180047ccc  jnz     loc_180047EAD
0x180047cd2  mov     [rbp+1F0h+var_1E8], bl
0x180047cd5  lea     rax, [rsi+1]
0x180047cd9  mov     qword ptr [rbp+1F0h+var_1B0.Length], rbx
0x180047cdd  mov     [rbp+1F0h+var_248], rax
0x180047ce1  cmp     rax, [rbp+1F0h+var_258]
0x180047ce5  jnb     short loc_180047CFD
0x180047ce7  lea     rbx, [rax+rax*2]
0x180047ceb  shl     rbx, 6
0x180047cef  add     rbx, [rbp+1F0h+var_260]
0x180047cf3  cmp     dword ptr [rbx+4], 0Dh
0x180047cf7  jz      loc_180047E09
0x180047cfd  xor     ecx, ecx; dwErrCode
0x180047cff  call    cs:__imp_SetLastError
0x180047d06  nop     dword ptr [rax+rax+00h]
0x180047d0b  mov     ecx, [r12+18h]
0x180047d10  lea     rax, [rbp+1F0h+var_1B0]
0x180047d14  mov     [rsp+330h+var_308], rax
0x180047d19  lea     r8, [rbp+1F0h+var_1E8]
0x180047d1d  mov     rax, [r12+10h]
0x180047d22  lea     rdx, [rbp+1F0h+var_1A0]
0x180047d26  xor     ebx, ebx
0x180047d28  xor     r9d, r9d
0x180047d2b  mov     [rsp+330h+var_310], rbx
0x180047d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d35  test    eax, eax
0x180047d37  jz      loc_18004821E
0x180047d3d  cmp     [rbp+1F0h+var_1E8], bl
0x180047d40  jz      loc_1800480E4
0x180047d46  mov     rdx, [rbp+1F0h+Src]
0x180047d4a  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180047d51  mov     [rbp+1F0h+var_1A0], rax
0x180047d55  lea     rax, [rbp+1F0h+var_178]
0x180047d59  cmp     rdx, rax
0x180047d5c  jz      short loc_180047D67
0x180047d5e  lea     rcx, [rbp+1F0h+var_1A0]
0x180047d62  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180047d67  mov     rbx, [rbp+1F0h+var_240]
0x180047d6b  jmp     loc_180047C1C
0x180047d70  cmp     [rbp+1F0h+var_270], dil
0x180047d74  jnz     loc_1800482C9
0x180047d7a  test    edx, edx
0x180047d7c  jnz     loc_1800483B0
0x180047d82  xor     ecx, ecx; dwErrCode
0x180047d84  call    cs:__imp_SetLastError
0x180047d8b  nop     dword ptr [rax+rax+00h]
0x180047d90  mov     rax, [rbp+1F0h+var_1B8]
0x180047d94  mov     dword ptr [rax], 1
0x180047d9a  mov     rsi, [rsp+330h+arg_10]
0x180047da2  mov     r12, [rsp+330h+var_18]
0x180047daa  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180047db1  mov     rax, [rbp+1F0h+var_1B8]
0x180047db5  mov     r15, [rsp+330h+var_30]
0x180047dbd  mov     r14, [rsp+330h+var_28]
0x180047dc5  mov     r13, [rsp+330h+var_20]
0x180047dcd  mov     ebx, [rax]
0x180047dcf  mov     rdi, [rsp+320h]
0x180047dd7  jnz     loc_1800483DC
0x180047ddd  lea     rcx, [rbp+1F0h+Frame]; Frame
0x180047de1  call    cs:__imp_RtlPopFrame
0x180047de8  nop     dword ptr [rax+rax+00h]
0x180047ded  mov     eax, ebx
0x180047def  mov     rcx, [rbp+1F0h+var_40]
0x180047df6  xor     rcx, rsp; StackCookie
0x180047df9  call    __security_check_cookie
0x180047dfe  add     rsp, 328h
0x180047e05  pop     rbx
0x180047e06  pop     rbp
0x180047e07  retn
0x180047e09  xor     ecx, ecx; dwErrCode
0x180047e0b  call    cs:__imp_SetLastError
0x180047e12  nop     dword ptr [rax+rax+00h]
0x180047e17  mov     rdx, [rbx+0B8h]
0x180047e1e  mov     [rbp+1F0h+var_228], rdx
0x180047e22  lea     rcx, [rdx+1]
0x180047e26  mov     qword ptr [rbp+1F0h+String2.Length], rcx
0x180047e2a  cmp     rcx, 1
0x180047e2e  jbe     short loc_180047EA1
0x180047e30  mov     r10, [rbx+0B0h]
0x180047e37  mov     rax, qword ptr [rbp+1F0h+var_180]
0x180047e3b  mov     qword ptr [rbp+1F0h+var_208.Length], r10
0x180047e3f  lea     rbx, [rcx+rax]
0x180047e43  mov     rcx, [rbp+1F0h+var_188]
0x180047e47  mov     [rbp+1F0h+var_230], rbx
0x180047e4b  cmp     rbx, rcx
0x180047e4e  ja      short loc_180047EC4
0x180047e50  mov     r8, [rbp+1F0h+Src]
0x180047e54  sub     rcx, rax
0x180047e57  jz      short loc_180047E93
0x180047e59  lea     r9, [r8+rax*2]
0x180047e5d  mov     qword ptr [rbp+1F0h+var_208.Length], r9
0x180047e61  test    r10, r10
0x180047e64  jz      loc_180047FC6
0x180047e6a  cmp     rdx, rcx
0x180047e6d  jnb     loc_18004800C
0x180047e73  lea     rbx, [rdx+rdx]
0x180047e77  mov     rcx, r9; void *
0x180047e7a  mov     r8, rbx; Size
0x180047e7d  mov     rdx, r10; Src
0x180047e80  call    memcpy_0
0x180047e85  mov     rcx, qword ptr [rbp+1F0h+var_208.Length]
0x180047e89  xor     eax, eax
0x180047e8b  mov     [rbx+rcx], ax
0x180047e8f  mov     rax, qword ptr [rbp+1F0h+var_180]
0x180047e93  mov     rcx, qword ptr [rbp+1F0h+String2.Length]
0x180047e97  dec     rcx
0x180047e9a  add     rax, rcx
0x180047e9d  mov     qword ptr [rbp+1F0h+var_180], rax
  ... truncated ...
```
