# CXVariant::ConvertToTiOneStep(CTypeInfo const *,CTypeInfo const *,uchar *,ulong,long,CDefaultCollation const *,short,uchar,EErrorHandling,bool,IBlobHandleFactory *,bool &)

- ea: `0x100403e20`
- end: `0x1004040ae`
- name: `?ConvertToTiOneStep@CXVariant@@AEAAJPEBVCTypeInfo@@0PEAEKJPEBVCDefaultCollation@@FEW4EErrorHandling@@_NPEAUIBlobHandleFactory@@AEA_N@Z`
- size: `654`
- prototype: `__int64 __fastcall(__int64, char *, const struct CTypeInfo *, unsigned __int8 *, unsigned int, int, struct CDefaultCollation *, __int16, char, char, bool, struct IBlobHandleFactory *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, registry_config`

## callers

- `0x100403a90`

## callees

- `0x100401170`
- `0x1004035b0`
- `0x100403e20`
- `0x100404f80`
- `0x1004071d0`
- `0x100407540`
- `0x100407c90`
- `0x100408840`
- `0x10040b8f0`
- `0x10040c4b0`
- `0x1004111d0`
- `0x100415620`
- `0x1004191c0`
- `0x10041d240`
- `0x100423760`
- `0x100452150`
- `0x100455450`
- `0x1004559f0`
- `0x1004568e0`
- `0x100456a90`
- `0x10045a190`
- `0x10045a660`
- `0x10045ab10`
- `0x10045acb0`
- `0x10045b3d0`
- `0x10045b690`
- `0x10045bf60`
- `0x10045c970`
- `0x10045cae0`
- `0x10045cc60`
- `0x10045cde0`
- `0x10047c300`
- `0x10047c5d0`
- `0x10047c6d0`
- `0x10047c820`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100451005`
- `sqldk!??_V@YAXPEAX@Z` at `0x10045111a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100451219`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004513a6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100451005`
- `sqldk!??_V@YAXPEAX@Z` at `0x10045111a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100451219`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004513a6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100450ff5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100451209`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100450ff5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100451209`
- `sqldk!SystemThread_TlsIndex` at `0x100450fa8`
- `sqldk!SystemThread_TlsIndex` at `0x1004511bc`
- `sqldk!SystemThread_TlsOffset` at `0x100450fb1`
- `sqldk!SystemThread_TlsOffset` at `0x1004511c5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450fcc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004511e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100450fcc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004511e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CXVariant::ConvertToTiOneStep(
        __int64 a1,
        char *a2,
        const struct CTypeInfo *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int a6,
        struct CDefaultCollation *a7,
        __int16 a8,
        char a9,
        char a10,
        bool a11,
        struct IBlobHandleFactory *a12)
{
  const struct CTypeInfo *v12; // rdx
  unsigned __int8 *v13; // rdi
  unsigned __int16 *v14; // r12
  char *v15; // r14
  struct IBlobHandleFactory *v17; // rbx
  unsigned int v18; // esi
  unsigned __int8 v19; // dl
  __int64 v20; // r8
  __int64 v21; // r10
  __int64 v22; // r9
  unsigned __int16 v23; // r13
  int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // edi
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  __int64 result; // rax
  const struct CTypeInfo *v33; // rdx
  unsigned int v34; // edi
  unsigned __int8 v35; // cl
  unsigned __int8 v36; // r8
  unsigned __int16 v37; // cx
  int v38; // ebx
  unsigned __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // r13d
  int v42; // edi
  int v43; // eax
  __int64 v44; // rdx
  int v45; // ecx
  __int64 v46; // r9
  __int64 v47; // r8
  unsigned __int16 v48; // r13
  void *v49; // rbx
  __int64 v50; // r8
  int v51; // ecx
  int v52; // eax
  unsigned __int64 v53; // rdi
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rdx
  int v58; // edi
  int v59; // ecx
  int v60; // ecx
  int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // edi
  int v64; // eax
  unsigned __int64 v65; // rdi
  __int64 v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // rax
  int v69; // ecx
  int v70; // edi
  int v71; // eax
  __int64 v72; // rax
  struct ILockBytesSS *v73; // rdi
  __int64 v74; // rdx
  unsigned __int16 v75; // bx
  unsigned int v76; // eax
  int v77; // ecx
  int v78; // edi
  unsigned int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // eax
  int v82; // edi
  int v83; // ecx
  int v84; // ebx
  int v85; // ecx
  int v86; // eax
  unsigned __int16 v87; // r13
  int v88; // ecx
  unsigned __int16 v89; // r13
  __int64 v90; // rcx
  int v91; // ecx
  int v92; // ecx
  int v93; // ecx
  unsigned __int8 v94; // al
  unsigned __int8 v95; // al
  unsigned __int8 v96; // al
  char v97; // [rsp+28h] [rbp-38h]
  __int64 v98; // [rsp+50h] [rbp-10h] BYREF
  int v99; // [rsp+60h] [rbp+0h]
  unsigned int v100; // [rsp+68h] [rbp+8h] BYREF
  unsigned __int8 *v101; // [rsp+70h] [rbp+10h]
  struct IBlobHandleFactory *v102; // [rsp+78h] [rbp+18h]
  unsigned __int64 v103; // [rsp+80h] [rbp+20h]
  unsigned __int64 v104; // [rsp+88h] [rbp+28h]
  __int64 v105; // [rsp+90h] [rbp+30h]
  unsigned __int8 *v106; // [rsp+98h] [rbp+38h] BYREF

  v105 = -2;
  v13 = a4;
  v101 = a4;
  v14 = (unsigned __int16 *)a3;
  v15 = a2;
  v17 = a12;
  v102 = a12;
  v18 = 0;
  if ( *((_BYTE *)&xsm_rgfIsDeepType + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a3)) && !a4 )
    return 100;
  v19 = *a2;
  if ( v19 == 0xBD )
  {
    v98 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = &v98;
    *(_QWORD *)(a1 + 16) = 8;
    *(_WORD *)(a1 + 2) &= ~1u;
    *(_BYTE *)(a1 + 1) = -83;
    v15 = &CTypeInfo::tiDBTSAsBinary;
    v19 = CTypeInfo::tiDBTSAsBinary;
  }
  if ( v19 == 240 )
    goto LABEL_37;
  if ( v19 == 241 )
  {
    v12 = (const struct CTypeInfo *)v15;
    if ( *(_BYTE *)a3 == 0xF1 )
      return CXVariant::PerformConvertToXml((CXVariant *)a1, (const struct CTypeInfo *)v15, a3, a4, a5, a12, a6);
    if ( *(_BYTE *)a3 != 0xF0 )
    {
      LOBYTE(v18) = a10 == 1;
      return CXVariant::PerformConvertFromXml((CXVariant *)a1, (const struct CTypeInfo *)v15, a3, a4, a5, a12, v18, a6);
    }
    return CXVariant::PerformConvertUdt((CXVariant *)a1, v12, a3, a12, v13, a5);
  }
  v20 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v19);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + v20) && *((_WORD *)v15 + 8) == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLegacyLargeObject + v20) )
  {
    LOBYTE(v21) = *(_BYTE *)v14;
  }
  else
  {
    v21 = *(unsigned __int8 *)v14;
    v22 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v21);
    if ( (!*((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + v22) || v14[8] != 0xFFFF)
      && !*((_BYTE *)&CTypeInfo::sxm_rgfIsLegacyLargeObject + v22) )
    {
      switch ( *(_BYTE *)v14 )
      {
        case 0x22:
        case 0x23:
        case 0x63:
          return v18;
        case 0x24:
          return CXVariantConvertTo<36>::Execute((CXVariant *)a1);
        case 0x28:
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString
               + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15)) )
            return CXVariant::PerformConvertStrOrWstrToVarTimeOrDate(
                     (CXVariant *)a1,
                     (const struct CTypeInfo *)v15,
                     (const struct CTypeInfo *)v14,
                     a6,
                     a8,
                     a7,
                     a9);
          return CXVariant::PerformConvertToNewDate(
                   (CXVariant *)a1,
                   (const struct CTypeInfo *)v15,
                   (const struct CTypeInfo *)v14,
                   a6);
        case 0x29:
        case 0x2A:
        case 0x2B:
          v33 = (const struct CTypeInfo *)v15;
          if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString
                + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15)) )
            goto LABEL_40;
          return CXVariant::PerformConvertStrOrWstrToVarTimeOrDate(
                   (CXVariant *)a1,
                   (const struct CTypeInfo *)v15,
                   (const struct CTypeInfo *)v14,
                   a6,
                   a8,
                   a7,
                   a9);
        case 0x30:
          return CXVariantConvertTo<48>::Execute((CXVariant *)a1);
        case 0x34:
          return CXVariantConvertTo<52>::Execute((CXVariant *)a1);
        case 0x38:
          return CXVariantConvertTo<56>::Execute((CXVariant *)a1);
        case 0x3A:
          v33 = (const struct CTypeInfo *)v15;
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15)) )
            goto LABEL_40;
          return CXVariantConvertToDatetime<58>::Execute((CXVariant *)a1, a6, a9);
        case 0x3B:
          return CXVariantConvertTo<59>::Execute((CXVariant *)a1);
        case 0x3C:
          return CXVariantConvertTo<60>::Execute((CXVariant *)a1);
        case 0x3D:
          v33 = (const struct CTypeInfo *)v15;
          if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15)) )
            return CXVariantConvertToDatetime<61>::Execute((CXVariant *)a1, a6, a9);
LABEL_40:
          LODWORD(result) = CXVariant::PerformConvertVarTime((CXVariant *)a1, v33, (const struct CTypeInfo *)v14, a6);
          return (unsigned int)result;
        case 0x3E:
          return CXVariant::PerformConvertToR8((CXVariant *)a1, (const struct CTypeInfo *)v15);
        case 0x62:
          return CXVariant::PerformConvertToSsVariant((CXVariant *)a1, v13, a5, (const struct CTypeInfo *)v15);
        case 0x68:
          return CXVariantConvertTo<104>::Execute((CXVariant *)a1);
        case 0x6A:
        case 0x6C:
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v20) )
          {
            v88 = *((_DWORD *)v15 + 5);
            if ( (v88 & 0x80) != 0 )
            {
              v34 = 65001;
            }
            else if ( HIBYTE(v88) )
            {
              v34 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v88)]);
            }
            else
            {
              v34 = qword_100856AB0[4 * (v88 & 0x7F)];
            }
          }
          else
          {
            v34 = 0;
          }
          if ( (unsigned __int8)(v21 + 16) <= 1u )
          {
            v35 = byte_10085AFF3[4 * v22];
            if ( (_BYTE)v21 == 0xF0 || (_BYTE)v21 == 0xF1 )
              v36 = byte_10085AFF2[4 * v22];
            else
              v36 = *((_BYTE *)v14 + 18);
          }
          else
          {
            v35 = *((_BYTE *)v14 + 19);
            v36 = *((_BYTE *)v14 + 18);
          }
          return CXVariant::PerformConvertToNm((CXVariant *)a1, *v15, v36, v35, a11, v34);
        case 0x7A:
          return CXVariantConvertTo<122>::Execute((CXVariant *)a1);
        case 0x7F:
          return CXVariantConvertTo<127>::Execute((CXVariant *)a1);
        case 0xA5:
        case 0xAD:
          v89 = v14[8];
          if ( v89 == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v22) )
            v89 = 8100;
          if ( a6 )
          {
            v90 = (unsigned __int8)*v15;
            if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v90)) == 1 )
            {
              v91 = v90 - 167;
              if ( v91 )
              {
                v92 = v91 - 8;
                if ( v92 )
                {
                  v93 = v92 - 56;
                  if ( v93 && v93 != 8 )
                    return 100;
                  switch ( (_DWORD)v21 )
                  {
                    case 0xA5:
                    case 0xA7:
                      if ( (*((_BYTE *)v14 + 1) & 2) != 0 || *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) != 1 )
                        return CXVariantConvertToByt<231>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                      break;
                    case 0xAD:
                    case 0xAF:
                      v94 = *((_BYTE *)v14 + 1);
                      if ( (v94 & 2) != 0
                        || *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) != 1
                        || (v94 & 4) == 0 )
                      {
                        goto LABEL_231;
                      }
                      break;
                    case 0xEF:
LABEL_231:
                      v18 = 1;
                      return CXVariantConvertToByt<231>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                    default:
                      return CXVariantConvertToByt<231>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                  }
                  v18 = 2;
                  return CXVariantConvertToByt<231>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                }
              }
              switch ( (_DWORD)v21 )
              {
                case 0xA5:
                case 0xA7:
                  if ( (*((_BYTE *)v14 + 1) & 2) != 0 || *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) != 1 )
                    return CXVariantConvertToByt<167>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                  break;
                case 0xAD:
                case 0xAF:
                  v95 = *((_BYTE *)v14 + 1);
                  if ( (v95 & 2) != 0 || *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) != 1 || (v95 & 4) == 0 )
                    goto LABEL_245;
                  break;
                case 0xEF:
LABEL_245:
                  v18 = 1;
                  return CXVariantConvertToByt<167>::Convert((CXVariant *)a1, v13, v89, v18, v97);
                default:
                  return CXVariantConvertToByt<167>::Convert((CXVariant *)a1, v13, v89, v18, v97);
              }
              v18 = 2;
              return CXVariantConvertToByt<167>::Convert((CXVariant *)a1, v13, v89, v18, v97);
            }
          }
          if ( (_DWORD)v21 != 165 && (_DWORD)v21 != 167 )
          {
            if ( (_DWORD)v21 != 173 && (_DWORD)v21 != 175 )
            {
              if ( (_DWORD)v21 != 239 )
                goto LABEL_260;
              goto LABEL_259;
            }
            v96 = *((_BYTE *)v14 + 1);
            if ( (v96 & 2) != 0 || *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) != 1 || (v96 & 4) == 0 )
            {
LABEL_259:
              v18 = 1;
              goto LABEL_260;
            }
            goto LABEL_264;
          }
          if ( (*((_BYTE *)v14 + 1) & 2) == 0 && *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrBinary + v22) == 1 )
LABEL_264:
            v18 = 2;
LABEL_260:
          result = CXVariant::PerformConvertToByt(a1, v15, v13, v89, v18, a10);
          break;
        case 0xA7:
        case 0xAF:
          v23 = v14[8];
          if ( v23 == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v22) )
            v23 = 8100;
          v24 = a6;
          if ( !a6 )
          {
            v25 = (unsigned __int8)*v15;
            if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v25))
              || (_BYTE)v25 == 40 )
            {
              v24 = 121;
            }
          }
          v26 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15);
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v26) )
            v100 = (unsigned __int8)v15[19];
          else
            v100 = 0;
          v27 = 65001;
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v22) )
          {
            v28 = *((_DWORD *)v14 + 5);
            if ( (v28 & 0x80) != 0 )
            {
              v99 = 65001;
            }
            else
            {
              if ( HIBYTE(v28) )
                v29 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v28)]);
              else
                v29 = qword_100856AB0[4 * (v28 & 0x7F)];
              v99 = v29;
            }
          }
          else
          {
            v99 = 0;
          }
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v26) )
          {
            v30 = *((_DWORD *)v15 + 5);
            if ( (v30 & 0x80) == 0 )
            {
              if ( HIBYTE(v30) )
                v27 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v30)]);
              else
                v27 = qword_100856AB0[4 * (v30 & 0x7F)];
            }
          }
          else
          {
            v27 = 0;
          }
          v31 = CTypeInfo::EpadPadding(v14);
          LODWORD(v98) = v100;
          return CXVariant::PerformConvertToStr(a1, (unsigned __int8)*v15, v101, v23, v31, a8, v27, v99, v24, a10, v98);
        case 0xBD:
          result = CXVariant::PerformConvertToByt(a1, v15, &v106, 8, 1, 0);
          if ( (_DWORD)result )
            return (unsigned int)result;
          if ( !*(_BYTE *)a1 )
            *(_QWORD *)(a1 + 8) = v106;
          *(_BYTE *)(a1 + 1) = -67;
          return result;
        case 0xE7:
        case 0xEF:
          v37 = v14[8];
          if ( v37 == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v22) )
            v100 = 8100;
          else
            LOWORD(v100) = v14[8];
          v38 = a6;
          if ( !a6 )
          {
            v44 = (unsigned __int8)*v15;
            if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v44))
              || (_BYTE)v44 == 40 )
            {
              v38 = 121;
            }
          }
          if ( (*((_DWORD *)v14 + 5) & 0x100) == 0 )
            goto LABEL_55;
          v39 = (unsigned __int8)*v15;
          v103 = v39;
          if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v39)) )
            goto LABEL_55;
          if ( v37 == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v22) )
            v37 = 8100;
          if ( (unsigned int)v37 < *(_DWORD *)(a1 + 16) )
          {
            LOBYTE(v99) = 1;
          }
          else
          {
LABEL_55:
            LOBYTE(v99) = 0;
            LOBYTE(v39) = *v15;
            v103 = (unsigned __int8)*v15;
          }
          v40 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v39);
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v40) )
            v41 = (unsigned __int8)v15[19];
          else
            v41 = 0;
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v40) )
          {
            v45 = *((_DWORD *)v15 + 5);
            if ( (v45 & 0x80) != 0 )
            {
              v42 = 65001;
            }
            else if ( HIBYTE(v45) )
            {
              v42 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v45)]);
            }
            else
            {
              v42 = qword_100856AB0[4 * (v45 & 0x7F)];
            }
          }
          else
          {
            v42 = 0;
          }
          v43 = CTypeInfo::EpadPadding(v14);
          LOBYTE(v98) = v99;
          return CXVariant::PerformConvertToWstr(
                   a1,
                   (unsigned __int8)v103,
                   v101,
                   (unsigned __int16)v100,
                   v43,
                   a8,
                   v42,
                   v38,
                   a10,
                   v41,
                   v98);
        case 0xF0:
          return CXVariant::PerformConvertUdt(
                   (CXVariant *)a1,
                   (const struct CTypeInfo *)v15,
                   (const struct CTypeInfo *)v14,
                   a12,
                   v13,
                   a5);
        case 0xF1:
          return CXVariant::PerformConvertToXml(
                   (CXVariant *)a1,
                   (const struct CTypeInfo *)v15,
                   (const struct CTypeInfo *)v14,
                   v13,
                   a5,
                   a12,
                   a6);
        default:
          return 1;
      }
      return result;
    }
  }
  if ( (_BYTE)v21 == 0xF0 )
  {
    a3 = (const struct CTypeInfo *)v14;
LABEL_37:
    v12 = (const struct CTypeInfo *)v15;
    return CXVariant::PerformConvertUdt((CXVariant *)a1, v12, a3, a12, v13, a5);
  }
  if ( (_BYTE)v21 == 0xF1 )
    return CXVariant::PerformConvertToXml(
             (CXVariant *)a1,
             (const struct CTypeInfo *)v15,
             (const struct CTypeInfo *)v14,
             v13,
             a5,
             a12,
             a6);
  v46 = (unsigned __int8)*v15;
  v47 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v46);
  if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + v47) || *((_WORD *)v15 + 8) == 0xFFFF )
  {
    v74 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v21);
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + v74) )
    {
      v75 = v14[8];
      if ( v75 != 0xFFFF )
      {
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v74) )
          v75 = 8100;
        LOWORD(v99) = v75;
        if ( a6
          && ((*((_BYTE *)&CTypeInfo::sxm_rgfIsString + v47) && *((_WORD *)v15 + 8) == 0xFFFF
            || *((_BYTE *)&CTypeInfo::sxm_rgfIsWString + v47) && *((_WORD *)v15 + 8) == 0xFFFF)
           && *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + v74)
           || *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + v47)
           && *((_WORD *)v15 + 8) == 0xFFFF
           && *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + v74)) )
        {
          switch ( (_DWORD)v46 )
          {
            case 0xA5:
              if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsString + v74) )
              {
                v80 = CTypeInfo::EpadPadding(v14);
                return CXVariantConvertFromBHToString<165,167,0,0>::Convert(a1, v101, v75, v80);
              }
              else
              {
                v81 = CTypeInfo::EpadPadding(v14);
                return CXVariantConvertFromBHToString<165,231,0,0>::Convert(a1, v13, v75, v81);
              }
            case 0xA7:
              v77 = *((_DWORD *)v15 + 5);
              if ( (v77 & 0x80) != 0 )
              {
                v78 = 65001;
              }
              else if ( HIBYTE(v77) )
              {
                v78 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v77)]);
              }
              else
              {
                v78 = qword_100856AB0[4 * (v77 & 0x7F)];
              }
              v79 = CTypeInfo::EpadPadding(v14);
              return CXVariantConvertFromBHToString<167,165,0,0>::Convert(
                       a1,
                       v101,
                       v75,
                       v79,
                       v78,
                       a6,
                       0,
                       a10,
                       v102,
                       0,
                       v98);
            case 0xE7:
              v76 = CTypeInfo::EpadPadding(v14);
              return CXVariantConvertFromBHToString<231,165,0,0>::Convert(
                       a1,
                       v13,
                       v75,
                       v76,
                       0,
                       a6,
                       0,
                       a10,
                       v102,
                       0,
                       v98);
            default:
              return v18;
          }
        }
        else
        {
          v82 = 65001;
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v74) )
          {
            v83 = *((_DWORD *)v14 + 5);
            if ( (v83 & 0x80) != 0 )
            {
              v84 = 65001;
            }
            else if ( HIBYTE(v83) )
            {
              v84 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v83)]);
            }
            else
            {
              v84 = qword_100856AB0[4 * (v83 & 0x7F)];
            }
          }
          else
          {
            v84 = 0;
          }
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v47) )
          {
            v85 = *((_DWORD *)v15 + 5);
            if ( (v85 & 0x80) == 0 )
            {
              if ( HIBYTE(v85) )
                v82 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v85)]);
              else
                v82 = qword_100856AB0[4 * (v85 & 0x7F)];
            }
          }
          else
          {
            v82 = 0;
          }
          v86 = CTypeInfo::EpadPadding(v14);
          return CXVariant::PerformConvertFromBHToString(
                   a1,
                   v15,
                   v14,
                   v101,
                   (unsigned __int16)v99,
                   v86,
                   v82,
                   a6,
                   v84,
                   a10,
                   v98);
        }
      }
      v17 = v102;
    }
    v87 = v14[8];
    if ( v87 == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v74) )
      v87 = 8100;
    return CXVariant::PerformConvertFromBHToBH(
             (CXVariant *)a1,
             (const struct CTypeInfo *)v15,
             (const struct CTypeInfo *)v14,
             v13,
             v87,
             a6,
             v17);
  }
  else
  {
    v48 = v14[8];
    if ( v48 == 0xFFFF
      || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v21)) )
    {
      v48 = 8100;
    }
    v49 = 0;
    v103 = 0;
    v50 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v14);
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + v50)
      && (v14[8] == 0xFFFF || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v50))
      && *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15))
      && *((_WORD *)v15 + 8) != 0xFFFF
      && (unsigned int)(a6 - 1) <= 1 )
    {
      v51 = *(_DWORD *)(a1 + 16);
      v52 = 0;
      if ( a6 == 1 )
        v52 = 2;
      LODWORD(v104) = v52 + 2 * v51;
      v53 = (unsigned int)v104;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsString + v50) )
      {
        v55 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v56 = *(_QWORD *)(v55 + 256);
        if ( !v56 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v56 = *(_QWORD *)(v55 + 256);
        }
        v49 = operator new[](
                v53,
                *(struct IMemObj **)(v56 + 1000),
                "sql\\ntdbms\\msql\\typesystem\\retypes.cpp",
                6700,
                6u);
        if ( v49 )
          operator delete[](0);
        v103 = (unsigned __int64)v49;
        v57 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15);
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v57) )
          v100 = (unsigned __int8)v15[19];
        else
          v100 = 0;
        v58 = 65001;
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode
             + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v14)) )
        {
          v59 = *((_DWORD *)v14 + 5);
          if ( (v59 & 0x80) != 0 )
          {
            v99 = 65001;
          }
          else
          {
            if ( HIBYTE(v59) )
              v64 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v59)]);
            else
              v64 = qword_100856AB0[4 * (v59 & 0x7F)];
            v99 = v64;
          }
        }
        else
        {
          v99 = 0;
        }
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v57) )
        {
          v60 = *((_DWORD *)v15 + 5);
          if ( (v60 & 0x80) == 0 )
          {
            if ( HIBYTE(v60) )
              v58 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v60)]);
            else
              v58 = qword_100856AB0[4 * (v60 & 0x7F)];
          }
        }
        else
        {
          v58 = 0;
        }
        v61 = CTypeInfo::EpadPadding(v14);
        LODWORD(v98) = v100;
        v62 = CXVariant::PerformConvertToStr(
                a1,
                (unsigned __int8)*v15,
                v49,
                (unsigned int)v104,
                v61,
                a8,
                v58,
                v99,
                a6,
                a10,
                v98);
      }
      else
      {
        v65 = 2LL * (unsigned int)v104;
        v104 = v65;
        v66 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v67 = *(_QWORD *)(v66 + 256);
        if ( !v67 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v67 = *(_QWORD *)(v66 + 256);
        }
        v49 = operator new[](
                v65,
                *(struct IMemObj **)(v67 + 1000),
                "sql\\ntdbms\\msql\\typesystem\\retypes.cpp",
                6718,
                6u);
        if ( v49 )
          operator delete[](0);
        v103 = (unsigned __int64)v49;
        v68 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)*v15);
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v68) )
          v100 = (unsigned __int8)v15[19];
        else
          v100 = 0;
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v68) )
        {
          v69 = *((_DWORD *)v15 + 5);
          if ( (v69 & 0x80) != 0 )
          {
            v70 = 65001;
          }
          else if ( HIBYTE(v69) )
          {
            v70 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v69)]);
          }
          else
          {
            v70 = qword_100856AB0[4 * (v69 & 0x7F)];
          }
        }
        else
        {
          v70 = 0;
        }
        v71 = CTypeInfo::EpadPadding(v14);
        LOBYTE(v98) = 0;
        v62 = CXVariant::PerformConvertToWstr(
                a1,
                (unsigned __int8)*v15,
                v49,
                (unsigned int)v104,
                v71,
                a8,
                v70,
                a6,
                a10,
                v100,
                v98);
      }
      v63 = v62;
      if ( v62 )
      {
        operator delete[](v49);
        return v63;
      }
      v13 = v101;
    }
    v72 = v48;
    v100 = v48;
    if ( *(_BYTE *)a1 != 3 )
    {
      (**(void (__fastcall ***)(struct IBlobHandleFactory *, unsigned __int8 *, unsigned int *, _QWORD))v102)(
        v102,
        v13,
        &v100,
        0);
      v106 = v13;
      v102 = 0;
      v73 = (struct ILockBytesSS *)(*(__int64 (__fastcall **)(unsigned __int8 *, _QWORD))(*(_QWORD *)v13 + 8LL))(v13, 0);
      v102 = v73;
      CopyStrToBlobHandleWithPad(
        (const struct CTypeInfo *)v15,
        (const struct CTypeInfo *)v14,
        v73,
        *(unsigned __int8 **)(a1 + 8),
        *(_DWORD *)(a1 + 16));
      (*(void (__fastcall **)(struct ILockBytesSS *))(*(_QWORD *)v73 + 160LL))(v73);
      v106 = 0;
      (*(void (__fastcall **)(struct ILockBytesSS *))(*(_QWORD *)v73 + 16LL))(v73);
      v72 = v100;
    }
    *(_QWORD *)(a1 + 8) = v101;
    *(_QWORD *)(a1 + 16) = v72;
    *(_BYTE *)(a1 + 1) = *(_BYTE *)v14;
    operator delete[](v49);
    return 0;
  }
}

```

## disassembly

```asm
0x100403e20  push    rbp
0x100403e22  push    rbx
0x100403e23  push    rsi
0x100403e24  push    rdi
0x100403e25  push    r12
0x100403e27  push    r13
0x100403e29  push    r14
0x100403e2b  push    r15
0x100403e2d  sub     rsp, 0B8h
0x100403e34  lea     rbp, [rsp+60h]
0x100403e39  mov     [rbp+90h+var_60], 0FFFFFFFFFFFFFFFEh
0x100403e41  mov     rax, cs:__security_cookie
0x100403e48  xor     rax, rbp
0x100403e4b  mov     [rbp+90h+var_50], rax
0x100403e4f  mov     rdi, r9
0x100403e52  mov     [rbp+90h+var_80], r9
0x100403e56  mov     r12, r8
0x100403e59  mov     r14, rdx
0x100403e5c  mov     r15, rcx
0x100403e5f  mov     r11, [rbp+90h+arg_30]
0x100403e66  mov     rbx, [rbp+90h+arg_58]
0x100403e6d  mov     [rbp+90h+var_78], rbx
0x100403e71  xor     esi, esi
0x100403e73  movzx   eax, byte ptr [r8]
0x100403e77  lea     r13, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100403e7e  movzx   eax, byte ptr [rax+r13+45AE60h]
0x100403e87  cmp     [rax+r13+45BE00h], sil
0x100403e8f  jnz     loc_1004035ED
0x100403e95  movzx   edx, byte ptr [rdx]
0x100403e98  cmp     dl, 0BDh
0x100403e9b  jz      loc_100450E27
0x100403ea1  movzx   ecx, dl
0x100403ea4  sub     ecx, 0F0h
0x100403eaa  jz      loc_1004038B8
0x100403eb0  cmp     ecx, 1
0x100403eb3  jz      loc_1004520DA
0x100403eb9  movzx   eax, dl
0x100403ebc  movzx   r8d, byte ptr [rax+r13+45AE60h]
0x100403ec5  mov     eax, 0FFFFh
0x100403eca  cmp     [r8+r13+45BD80h], sil
0x100403ed2  jnz     loc_100403898
0x100403ed8  cmp     [r8+r13+45BDA8h], sil
0x100403ee0  jnz     loc_1004038A3
0x100403ee6  movzx   r10d, byte ptr [r12]
0x100403eeb  movzx   r9d, byte ptr [r10+r13+45AE60h]
0x100403ef4  cmp     [r9+r13+45BD80h], sil
0x100403efc  jnz     loc_1004035FF
0x100403f02  cmp     [r9+r13+45BDA8h], sil
0x100403f0a  jnz     loc_1004038AB
0x100403f10  mov     edx, r10d
0x100403f13  lea     eax, [r10-22h]; switch 208 cases
0x100403f17  cmp     eax, 0CFh
0x100403f1c  ja      def_100403F38; jumptable 0000000100403F38 default case, cases 37-39,44-47,49-51,53-55,57,63-97,100-103,105,107,109-121,123-126,128-164,166,168-172,174,176-188,190-230,232-238
0x100403f22  cdqe
0x100403f24  movzx   eax, ds:(byte_100404110 - 100400000h)[rax+r13]
0x100403f2d  mov     ecx, ds:(jpt_100403F38 - 100400000h)[r13+rax*4]
0x100403f35  add     rcx, r13
0x100403f38  jmp     rcx; switch jump
0x100403f3b  movzx   r13d, word ptr [r12+10h]; jumptable 0000000100403F38 cases 167,175
0x100403f41  mov     r10d, 0FFFFh
0x100403f47  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100403f4e  cmp     r13w, r10w
0x100403f52  jz      loc_100451D23
0x100403f58  cmp     [r9+r8+4F3B00h], sil
0x100403f60  jnz     loc_100451D23
0x100403f66  mov     ebx, [rbp+90h+arg_28]
0x100403f6c  test    ebx, ebx
0x100403f6e  jnz     short loc_100403F94
0x100403f70  movzx   ecx, byte ptr [r14]
0x100403f74  movzx   eax, byte ptr [rcx+r8+45AE60h]
0x100403f7d  cmp     [rax+r8+45BDD0h], sil
0x100403f85  jnz     loc_100451D2F
0x100403f8b  cmp     cl, 28h ; '('
0x100403f8e  jz      loc_100451D2F
0x100403f94  movzx   eax, byte ptr [r14]
0x100403f98  movzx   edx, byte ptr [rax+r8+45AE60h]
0x100403fa1  cmp     [rdx+r8+45BDD0h], sil
0x100403fa9  jnz     loc_100451D3A
0x100403faf  mov     [rbp+90h+var_88], esi
0x100403fb2  mov     edi, 0FDE9h
0x100403fb7  cmp     [r9+r8+45BD40h], sil
0x100403fbf  jz      loc_100451D71
0x100403fc5  mov     ecx, [r12+14h]
0x100403fca  mov     eax, ecx
0x100403fcc  shr     eax, 7
0x100403fcf  test    al, 1
0x100403fd1  jnz     loc_100451D48
0x100403fd7  mov     eax, ecx
0x100403fd9  shr     eax, 18h
0x100403fdc  test    al, al
0x100403fde  jnz     loc_100451D51
0x100403fe4  movzx   eax, cl
0x100403fe7  and     eax, 7Fh
0x100403fea  shl     rax, 5
0x100403fee  mov     eax, [rax+r8+456AB0h]
0x100403ff6  mov     [rbp+90h+var_90], eax
0x100403ff9  jmp     short loc_100403FFC
0x100403ffc  cmp     [rdx+r8+45BD40h], sil
0x100404004  jz      loc_100451D7A
0x10040400a  mov     ecx, [r14+14h]
0x10040400e  mov     eax, ecx
0x100404010  shr     eax, 7
0x100404013  test    al, 1
0x100404015  jnz     short loc_10040403F
0x100404017  mov     eax, ecx
0x100404019  shr     eax, 18h
0x10040401c  test    al, al
0x10040401e  jz      loc_10041BD01
0x100404024  movzx   eax, al
0x100404027  lea     rcx, [rax+rax*4]
0x10040402b  movzx   eax, ds:rva byte_10085C9DC[r8+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100404034  mov     edi, ds:rva ?x_uiCodePage@@3QBIB[r8+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x10040403c  jmp     short loc_10040403F
0x10040403f  mov     rcx, r12
0x100404042  call    ?EpadPadding@CTypeInfo@@QEBA?AW4EPadding@@XZ; CTypeInfo::EpadPadding(void)
0x100404047  movzx   r9d, r13w
0x10040404b  mov     ecx, [rbp+90h+var_88]
0x10040404e  mov     dword ptr [rsp+0F0h+var_A0], ecx
0x100404052  movzx   ecx, [rbp+90h+arg_48]
0x100404059  mov     byte ptr [rsp+0F0h+var_A8], cl
0x10040405d  mov     [rsp+0F0h+var_B0], ebx
0x100404061  mov     ecx, [rbp+90h+var_90]
0x100404064  mov     [rsp+0F0h+var_B8], ecx
0x100404068  mov     dword ptr [rsp+0F0h+var_C0], edi
0x10040406c  movzx   ecx, word ptr [rbp+90h+arg_38]
0x100404073  mov     word ptr [rsp+0F0h+var_C8], cx
0x100404078  mov     dword ptr [rsp+0F0h+var_D0], eax
0x10040407c  mov     r8, [rbp+90h+var_80]
0x100404080  movzx   edx, byte ptr [r14]
0x100404084  mov     rcx, r15
0x100404087  call    ?PerformConvertToStr@CXVariant@@QEAAJEPEAEKW4EPadding@@FIIJW4EErrorHandling@@W4ETimeScale@@@Z; CXVariant::PerformConvertToStr(uchar,uchar *,ulong,EPadding,short,uint,uint,long,EErrorHandling,ETimeScale)
0x10040408c  mov     esi, eax
0x10040408e  jmp     short loc_100404091
0x100404091  mov     rcx, [rbp+90h+var_50]
0x100404095  xor     rcx, rbp; StackCookie
0x100404098  call    __security_check_cookie
0x10040409d  lea     rsp, [rbp+58h]
0x1004040a1  pop     r15
0x1004040a3  pop     r14
0x1004040a5  pop     r13
0x1004040a7  pop     r12
0x1004040a9  pop     rdi
0x1004040aa  pop     rsi
0x1004040ab  pop     rbx
0x1004040ac  pop     rbp
0x1004040ad  retn
0x1004035ed  test    r9, r9
0x1004035f0  jnz     loc_100403E95
0x1004035f6  lea     eax, [rsi+64h]
0x1004035f9  jmp     loc_100404091
0x1004035ff  cmp     ax, [r12+10h]
0x100403605  jnz     loc_100403F02
0x10040360b  jmp     loc_1004038AB
0x100403898  cmp     ax, [r14+10h]
0x10040389d  jnz     loc_100403ED8
0x1004038a3  movzx   r10d, byte ptr [r12]
0x1004038a8  jmp     short loc_1004038AB
0x1004038ab  cmp     r10b, 0F0h
0x1004038af  jnz     loc_100450E6B
0x1004038b5  mov     r8, r12; struct CTypeInfo *
0x1004038b8  mov     rdx, r14; struct CTypeInfo *
0x1004038bb  mov     rcx, r15; this
0x1004038be  mov     eax, [rbp+90h+arg_20]
0x1004038c4  mov     dword ptr [rsp+0F0h+var_C8], eax; unsigned int
0x1004038c8  mov     [rsp+0F0h+var_D0], rdi; unsigned __int8 *
0x1004038cd  mov     r9, rbx; struct IBlobHandleFactory *
0x1004038d0  call    ?PerformConvertUdt@CXVariant@@AEAAJPEBVCTypeInfo@@0PEAUIBlobHandleFactory@@PEAEK@Z; CXVariant::PerformConvertUdt(CTypeInfo const *,CTypeInfo const *,IBlobHandleFactory *,uchar *,ulong)
0x1004038d5  nop
0x1004038d6  jmp     loc_100404091
0x100407198  cmp     [r8+r13+45BD40h], sil; jumptable 0000000100403F38 case 56
0x1004071a0  jnz     loc_100451949
0x1004071a6  mov     edi, esi
0x1004071a8  mov     r8d, esi
0x1004071ab  movzx   edx, byte ptr [r14]
0x1004071af  mov     rcx, r15; this
0x1004071b2  call    ?Execute@?$CXVariantConvertTo@$0DI@@@SAJPEAVCXVariant@@EI@Z; CXVariantConvertTo<56>::Execute(CXVariant *,uchar,uint)
0x1004071b7  mov     esi, eax
0x1004071b9  jmp     loc_100404091
0x100407e82  movzx   eax, byte ptr [r14]; jumptable 0000000100403F38 case 61
0x100407e86  movzx   ecx, byte ptr [rax+r13+45AE60h]
0x100407e8f  mov     rdx, r14; struct CTypeInfo *
0x100407e92  cmp     [rcx+r13+45BDD0h], sil
0x100407e9a  mov     rcx, r15; this
0x100407e9d  jz      loc_10045202D
0x100407ea3  mov     r9d, [rbp+90h+arg_28]; int
0x100407eaa  mov     r8, r12; struct CTypeInfo *
0x100407ead  call    ?PerformConvertVarTime@CXVariant@@QEAAJPEBVCTypeInfo@@0J@Z; CXVariant::PerformConvertVarTime(CTypeInfo const *,CTypeInfo const *,long)
0x100407eb2  mov     esi, eax
0x100407eb4  mov     eax, esi; jumptable 0000000100403F38 cases 34,35,99
0x100407eb6  jmp     loc_100404091
0x1004087f9  movzx   eax, byte ptr [r14]; jumptable 0000000100403F38 case 40
0x1004087fd  movzx   ecx, byte ptr [rax+r13+45AE60h]
0x100408806  mov     r9d, [rbp+90h+arg_28]; int
0x10040880d  mov     r8, r12; struct CTypeInfo *
0x100408810  mov     rdx, r14; struct CTypeInfo *
0x100408813  cmp     [rcx+r13+45AFC0h], sil
0x10040881b  mov     rcx, r15; this
0x10040881e  jnz     loc_1004520A7
0x100408824  call    ?PerformConvertToNewDate@CXVariant@@QEAAJPEBVCTypeInfo@@0J@Z; CXVariant::PerformConvertToNewDate(CTypeInfo const *,CTypeInfo const *,long)
0x100408829  mov     esi, eax
0x10040882b  jmp     loc_100404091
0x1004098d4  cmp     [r8+r13+45BD40h], sil; jumptable 0000000100403F38 cases 106,108
0x1004098dc  jnz     loc_100451C2A
0x1004098e2  mov     edi, esi
0x1004098e4  movzx   edx, byte ptr [r14]; unsigned __int8
0x1004098e8  lea     eax, [r10+10h]
0x1004098ec  cmp     al, 1
0x1004098ee  jbe     loc_100451C7F
0x1004098f4  movzx   ecx, byte ptr [r12+13h]
0x1004098fa  movzx   r8d, byte ptr [r12+12h]; unsigned __int8
0x100409900  jmp     short loc_100409903
0x100409903  mov     dword ptr [rsp+0F0h+var_C8], edi; unsigned int
0x100409907  movzx   eax, [rbp+90h+arg_50]
0x10040990e  mov     byte ptr [rsp+0F0h+var_D0], al; bool
0x100409912  movzx   r9d, cl; unsigned __int8
0x100409916  mov     rcx, r15; this
0x100409919  call    ?PerformConvertToNm@CXVariant@@QEAAJEEE_NI@Z; CXVariant::PerformConvertToNm(uchar,uchar,uchar,bool,uint)
0x10040991e  mov     esi, eax
0x100409920  jmp     loc_100404091
0x10040b8c2  cmp     [r8+r13+45BD40h], sil; jumptable 0000000100403F38 case 48
0x10040b8ca  jnz     loc_100451813
0x10040b8d0  mov     edi, esi
0x10040b8d2  mov     r8d, esi
0x10040b8d5  movzx   edx, byte ptr [r14]
0x10040b8d9  mov     rcx, r15; this
0x10040b8dc  call    ?Execute@?$CXVariantConvertTo@$0DA@@@SAJPEAVCXVariant@@EI@Z; CXVariantConvertTo<48>::Execute(CXVariant *,uchar,uint)
0x10040b8e1  mov     esi, eax
0x10040b8e3  jmp     loc_100404091
0x100410a20  movzx   ecx, word ptr [r12+10h]; jumptable 0000000100403F38 cases 231,239
0x100410a26  mov     r13d, 1FA4h
0x100410a2c  mov     r10d, 0FFFFh
0x100410a32  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100410a39  cmp     cx, r10w
0x100410a3d  jz      loc_100451D82
0x100410a43  cmp     [r9+r8+4F3B00h], sil
0x100410a4b  jnz     loc_100451D82
0x100410a51  mov     word ptr [rbp+90h+var_88], cx
0x100410a55  jmp     short loc_100410A58
0x100410a58  mov     ebx, [rbp+90h+arg_28]
0x100410a5e  test    ebx, ebx
0x100410a60  jz      loc_100411708
0x100410a66  mov     eax, [r12+14h]
0x100410a6b  shr     eax, 8
0x100410a6e  test    al, 1
0x100410a70  jnz     loc_100451D8C
0x100410a76  mov     byte ptr [rbp+90h+var_90], sil
0x100410a7a  movzx   edx, byte ptr [r14]
0x100410a7e  mov     [rbp+90h+var_70], rdx
0x100410a82  movzx   eax, dl
0x100410a85  movzx   ecx, byte ptr [rax+r8+45AE60h]
0x100410a8e  cmp     [rcx+r8+45BDD0h], sil
0x100410a96  jnz     loc_100451DD5
0x100410a9c  mov     r13d, esi
0x100410a9f  cmp     [rcx+r8+45BD40h], sil
0x100410aa7  jnz     loc_1004118E0
0x100410aad  mov     edi, esi
0x100410aaf  mov     rcx, r12
0x100410ab2  call    ?EpadPadding@CTypeInfo@@QEBA?AW4EPadding@@XZ; CTypeInfo::EpadPadding(void)
0x100410ab7  movzx   r9d, word ptr [rbp+90h+var_88]
0x100410abc  movzx   ecx, byte ptr [rbp+90h+var_90]
0x100410ac0  mov     byte ptr [rsp+0F0h+var_A0], cl
0x100410ac4  mov     [rsp+0F0h+var_A8], r13d
0x100410ac9  movzx   ecx, [rbp+90h+arg_48]
0x100410ad0  mov     byte ptr [rsp+0F0h+var_B0], cl
0x100410ad4  mov     [rsp+0F0h+var_B8], ebx
0x100410ad8  mov     dword ptr [rsp+0F0h+var_C0], edi
0x100410adc  movzx   ecx, word ptr [rbp+90h+arg_38]
0x100410ae3  mov     word ptr [rsp+0F0h+var_C8], cx
0x100410ae8  mov     dword ptr [rsp+0F0h+var_D0], eax
0x100410aec  mov     r8, [rbp+90h+var_80]
0x100410af0  movzx   edx, byte ptr [rbp+90h+var_70]
0x100410af4  mov     rcx, r15
0x100410af7  call    ?PerformConvertToWstr@CXVariant@@QEAAJEPEAEKW4EPadding@@FIJW4EErrorHandling@@W4ETimeScale@@_N@Z; CXVariant::PerformConvertToWstr(uchar,uchar *,ulong,EPadding,short,uint,long,EErrorHandling,ETimeScale,bool)
0x100410afc  mov     esi, eax
0x100410afe  jmp     loc_100404091
0x100411708  movzx   edx, byte ptr [r14]
0x10041170c  movzx   eax, byte ptr [rdx+r8+45AE60h]
0x100411715  cmp     [rax+r8+45BDD0h], sil
0x10041171d  jnz     short loc_100411728
0x10041171f  cmp     dl, 28h ; '('
0x100411722  jnz     loc_100410A66
0x100411728  mov     ebx, 79h ; 'y'
0x10041172d  jmp     loc_100410A66
0x1004118e0  mov     ecx, [r14+14h]
0x1004118e4  mov     eax, ecx
0x1004118e6  shr     eax, 7
0x1004118e9  test    al, 1
0x1004118eb  jnz     loc_100451DE0
0x1004118f1  mov     eax, ecx
0x1004118f3  shr     eax, 18h
0x1004118f6  test    al, al
0x1004118f8  jnz     loc_10041D792
0x1004118fe  movzx   eax, cl
0x100411901  and     eax, 7Fh
0x100411904  shl     rax, 5
0x100411908  mov     edi, [rax+r8+456AB0h]
0x100411910  jmp     loc_100410AAF
0x1004155ee  cmp     [r8+r13+45BD40h], sil; jumptable 0000000100403F38 case 104
0x1004155f6  jnz     loc_10045178B
0x1004155fc  mov     edi, esi
  ... truncated ...
```
