# CImageCache::RegisterImageMetadata(void *,CImageCache::Image *)

- ea: `0x1800096e8`
- end: `0x18000a93b`
- name: `?RegisterImageMetadata@CImageCache@@AEAAKPEAXPEAUImage@1@@Z`
- size: `4691`
- prototype: `__int64 __fastcall(CImageCache *this, void *, struct Image *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180008494`

## callees

- `0x1800029c8`
- `0x1800096e8`
- `0x18000aa2c`
- `0x18000ab00`
- `0x18000ad88`
- `0x18000aeac`
- `0x18000d100`
- `0x18000d57c`
- `0x18000d638`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x18000dda0`
- `0x18000de94`
- `0x18000df74`
- `0x18000f9b8`
- `0x18000f9f8`
- `0x18000fd28`
- `0x180012890`
- `0x180012a18`
- `0x180012d80`
- `0x180013170`
- `0x180015ff9`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180009f1b`
- `msvcrt!wcsrchr` at `0x180009f1b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a8d1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a8d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a224`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a2f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a305`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a489`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a556`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a56a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a224`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a2f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a305`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a489`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a556`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a56a`
- `RPCRT4!UuidCreate` at `0x18000a658`
- `RPCRT4!UuidCreate` at `0x18000a6a0`
- `RPCRT4!UuidCreate` at `0x18000a658`
- `RPCRT4!UuidCreate` at `0x18000a6a0`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000988f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000a3a9`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000988f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000a3a9`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180009eee`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180009eee`
- `WdsImage!WdsImgGetVersion` at `0x180009e91`
- `WdsImage!WdsImgGetVersion` at `0x180009e91`
- `WdsImage!WdsImgGetCreationTime` at `0x180009b64`
- `WdsImage!WdsImgGetCreationTime` at `0x180009b64`
- `WdsImage!WdsImgGetServicePackLevel` at `0x180009ec0`
- `WdsImage!WdsImgGetServicePackLevel` at `0x180009ec0`
- `WdsImage!WdsImgGetPath` at `0x180009a05`
- `WdsImage!WdsImgGetPath` at `0x180009a05`
- `WdsImage!WdsImgGetHalName` at `0x180009ccd`
- `WdsImage!WdsImgGetHalName` at `0x180009ccd`
- `WdsImage!WdsImgGetProductFamily` at `0x180009c88`
- `WdsImage!WdsImgGetProductFamily` at `0x180009c88`
- `WdsImage!WdsImgGetImageIdentifierPresent` at `0x18000986e`
- `WdsImage!WdsImgGetImageIdentifierPresent` at `0x18000986e`
- `WdsImage!WdsImgGetArchitecture` at `0x180009a84`
- `WdsImage!WdsImgGetArchitecture` at `0x180009a84`
- `WdsImage!WdsImgGetImageIdentifier` at `0x1800098c7`
- `WdsImage!WdsImgGetImageIdentifier` at `0x1800098c7`
- `WdsImage!WdsImgGetDescription` at `0x180009b1f`
- `WdsImage!WdsImgGetDescription` at `0x180009b1f`
- `WdsImage!WdsImgGetLastModifiedTime` at `0x180009bca`
- `WdsImage!WdsImgGetLastModifiedTime` at `0x180009bca`
- `WdsImage!WdsImgGetLanguage` at `0x180009d12`
- `WdsImage!WdsImgGetLanguage` at `0x180009d12`
- `WdsImage!WdsImgGetLanguages` at `0x180009d6e`
- `WdsImage!WdsImgGetLanguages` at `0x180009d6e`
- `WdsImage!WdsImgGetProductName` at `0x180009c30`
- `WdsImage!WdsImgGetProductName` at `0x180009c30`

## string_xrefs

- `0x180009a2c`: `WDS.Image.Path`
- `0x1800098fe`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a097`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a319`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a33f`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a578`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a6e6`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000a860`: `InstallImage`

## pseudocode

```c
__int64 __fastcall CImageCache::RegisterImageMetadata(CImageCache *this, void *a2, struct Image *a3)
{
  unsigned int v3; // esi
  __int64 ImageIdentifierPresent; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ecx
  __int64 Metadata; // rdi
  struct _GUID *v12; // r12
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned int appended; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  unsigned int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  unsigned int ServicePackLevel; // ebx
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rdx
  wchar_t *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rbx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  CWdsMetadataStoreManagementClient *v73; // r13
  __int64 v74; // rdx
  struct _GUID v75; // xmm0
  __int64 v76; // rdx
  __int64 v77; // rcx
  int GroupIndex; // eax
  __int64 v79; // rdx
  const wchar_t *v80; // r12
  __int64 v81; // r8
  unsigned int v82; // eax
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rbx
  unsigned __int16 *v90; // rsi
  unsigned int v91; // eax
  __int64 v92; // r8
  const wchar_t *v93; // rdx
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // rcx
  unsigned __int64 v98; // rbx
  __int64 v99; // rdx
  __int64 v100; // r8
  int Data1; // eax
  unsigned int v102; // ebx
  int v103; // eax
  __int64 v104; // rdx
  __int64 v105; // r8
  unsigned int v106; // eax
  __int64 v107; // r9
  __int64 v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // rdx
  __int64 v112; // r8
  __int64 v113; // rbx
  unsigned __int16 *v114; // rsi
  unsigned int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // rdx
  __int64 v121; // r9
  __int64 v122; // rcx
  __int64 v123; // rdx
  const struct CWdsMetadata *v124; // r9
  __int64 v125; // rdx
  __int64 v126; // rdx
  __int64 v127; // rdx
  __int64 v128; // rdx
  __int64 v129; // rdx
  __int64 v130; // r8
  __int64 v131; // rdx
  __int64 v132; // rdx
  __int64 v133; // r8
  __int64 v134; // rdx
  unsigned int i; // ebx
  __int64 v136; // rdx
  __int64 v137; // rdx
  struct _GUID *v139; // [rsp+20h] [rbp-E0h]
  struct CWdsMetadata *v140; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v141[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v142; // [rsp+60h] [rbp-A0h] BYREF
  int v143; // [rsp+70h] [rbp-90h] BYREF
  UUID v144; // [rsp+78h] [rbp-88h]
  void *v145; // [rsp+88h] [rbp-78h] BYREF
  __int64 v146; // [rsp+90h] [rbp-70h]
  int v147; // [rsp+A0h] [rbp-60h] BYREF
  int v148; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v149; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *Str; // [rsp+B0h] [rbp-50h] BYREF
  int v151; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v152; // [rsp+C0h] [rbp-40h]
  _QWORD v153[10]; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v154; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v155; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v156; // [rsp+138h] [rbp+38h] BYREF
  struct _GUID *v157; // [rsp+140h] [rbp+40h] BYREF
  struct _GUID *v158; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v159; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v160; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 *v161; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 *v162; // [rsp+168h] [rbp+68h] BYREF
  __int64 v163; // [rsp+170h] [rbp+70h] BYREF
  const unsigned __int16 *v164; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 *v165; // [rsp+180h] [rbp+80h] BYREF
  struct _GUID v166; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v167[10]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v168[10]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v169[10]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v170[10]; // [rsp+290h] [rbp+190h] BYREF
  UUID Uuid; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v172[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v173; // [rsp+300h] [rbp+200h]
  __int128 v174; // [rsp+310h] [rbp+210h]
  int v175; // [rsp+320h] [rbp+220h]
  wchar_t v176; // [rsp+324h] [rbp+224h]
  _BYTE v177[202]; // [rsp+326h] [rbp+226h] BYREF
  unsigned __int16 v178; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v179[526]; // [rsp+3F2h] [rbp+2F2h] BYREF

  v3 = 0;
  v175 = *(_DWORD *)L"n=";
  Uuid = 0;
  *(_QWORD *)&v166.Data1 = this;
  v153[0] = 0;
  *(_OWORD *)v172 = *(_OWORD *)L"WDS.Image.Windows.Version=";
  v153[1] = 0;
  v153[3] = 0;
  v174 = *(_OWORD *)L"s.Version=";
  v153[4] = 0;
  v153[6] = 0;
  v153[7] = 0;
  v170[0] = 0;
  v170[1] = 0;
  v170[3] = 0;
  v170[4] = 0;
  v170[6] = 0;
  v170[7] = 0;
  v168[0] = 0;
  v168[1] = 0;
  v168[3] = 0;
  v168[4] = 0;
  v168[6] = 0;
  v168[7] = 0;
  v169[0] = 0;
  v169[1] = 0;
  v169[3] = 0;
  v169[4] = 0;
  v169[6] = 0;
  v169[7] = 0;
  *(_QWORD *)&v142.Data1 = 0;
  LODWORD(v141[0]) = 0;
  v147 = 0;
  v148 = 0;
  v157 = 0;
  v158 = 0;
  Str = 0;
  v173 = *(_OWORD *)L"e.Windows.Version=";
  v176 = aWdsImageWindow_5[26];
  memset_0(v177, 0, sizeof(v177));
  v155 = 0;
  v156 = 0;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  v149 = 0;
  v164 = 0;
  v165 = 0;
  ImageIdentifierPresent = (unsigned int)WdsImgGetImageIdentifierPresent(a2, &v147);
  if ( (int)ElValidateHr_0(ImageIdentifierPresent, v8, v9, 570) < 0 )
    goto LABEL_2;
  if ( !v147 )
  {
    LODWORD(Metadata) = 0;
    *((_DWORD *)a3 + 16) = *((_DWORD *)this + 38);
    goto LABEL_150;
  }
  v12 = (struct _GUID *)((char *)a3 + 48);
  *(_QWORD *)&v154.Data1 = (char *)a3 + 48;
  LODWORD(ImageIdentifierPresent) = WdsImgGetImageIdentifier(a2, (char *)a3 + 48);
  if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v13, v14, 587) < 0 )
    goto LABEL_2;
  *((_DWORD *)a3 + 11) = 1;
  LODWORD(Metadata) = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Object.Type='Image'");
  if ( (unsigned int)ElValidateWin32_0(
                       (unsigned int)Metadata,
                       v15,
                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                       597) )
    goto LABEL_150;
  v142 = *v12;
  LODWORD(Metadata) = CWdsMetadata::AppendGuidEntry((CWdsMetadata *)v153, L"WDS.Object.ID", &v142);
  if ( (unsigned int)ElValidateWin32_0(
                       (unsigned int)Metadata,
                       v16,
                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                       600) )
    goto LABEL_150;
  v142 = *v12;
  LODWORD(Metadata) = CWdsMetadata::AppendGuidEntry((CWdsMetadata *)v153, L"WDS.Image.ID", &v142);
  if ( (unsigned int)ElValidateWin32_0(
                       (unsigned int)Metadata,
                       v17,
                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                       603) )
    goto LABEL_150;
  LODWORD(Metadata) = CWdsMetadata::AppendStringEntry(
                        (CWdsMetadata *)v153,
                        L"WDS.Image.Group",
                        *(const unsigned __int16 **)a3);
  if ( (unsigned int)ElValidateWin32_0(
                       (unsigned int)Metadata,
                       v18,
                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                       607) )
    goto LABEL_150;
  appended = 13;
  switch ( *((_DWORD *)a3 + 8) )
  {
    case 1:
      appended = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Type='VHD'");
      v21 = 613;
      break;
    case 2:
      appended = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Type='WIM'");
      v21 = 623;
      break;
    case 3:
      appended = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Type='VHDX'");
      v21 = 618;
      break;
    default:
      v21 = 628;
      break;
  }
  LODWORD(Metadata) = appended;
  if ( (unsigned int)ElValidateWin32_0(appended, v19, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", v21) )
    goto LABEL_150;
  LODWORD(ImageIdentifierPresent) = WdsImgGetPath(a2, &v155);
  if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v22, v23, 633) < 0 )
    goto LABEL_2;
  LODWORD(Metadata) = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Path", v155);
  if ( (unsigned int)ElValidateWin32_0(
                       (unsigned int)Metadata,
                       v24,
                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                       637) )
    goto LABEL_150;
  Metadata = CWdsMetadata::AppendIntegerEntry(
               (CWdsMetadata *)v153,
               v25,
               (union _LARGE_INTEGER)*((unsigned int *)a3 + 9));
  if ( (unsigned int)ElValidateWin32_0(Metadata, v26, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 642) )
    goto LABEL_150;
  LODWORD(ImageIdentifierPresent) = WdsImgGetArchitecture(a2, &v148);
  if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v27, v28, 645) < 0 )
    goto LABEL_2;
  if ( v148 )
  {
    switch ( v148 )
    {
      case 5:
        v51 = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Architecture='ARM'");
        v31 = 666;
        break;
      case 9:
        v51 = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Architecture='X64'");
        v31 = 656;
        break;
      case 12:
        v51 = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Architecture='ARM64'");
        v31 = 661;
        break;
      default:
        v30 = 13;
        v31 = 671;
        LODWORD(Metadata) = 13;
        goto LABEL_25;
    }
  }
  else
  {
    v51 = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, L"WDS.Image.Architecture='X86'");
    v31 = 651;
  }
  LODWORD(Metadata) = v51;
  v30 = v51;
LABEL_25:
  if ( (unsigned int)ElValidateWin32_0(v30, v29, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", v31) )
    goto LABEL_150;
  Metadata = CWdsMetadata::AppendStringEntry(
               (CWdsMetadata *)v153,
               L"WDS.Image.Name",
               *((const unsigned __int16 **)a3 + 2));
  if ( (unsigned int)ElValidateWin32_0(Metadata, v32, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 675) )
    goto LABEL_150;
  if ( (int)WdsImgGetDescription(a2, &v156) >= 0 )
  {
    Metadata = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Description", v156);
    if ( (unsigned int)ElValidateWin32_0(Metadata, v33, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 688) )
      goto LABEL_150;
  }
  LODWORD(ImageIdentifierPresent) = WdsImgGetCreationTime(a2, &v157);
  if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v34, v35, 692) < 0 )
    goto LABEL_2;
  v142 = *v157;
  Metadata = CWdsMetadata::AppendTimeEntry((CWdsMetadata *)v153, L"WDS.Image.CreationTime", (struct _SYSTEMTIME *)&v142);
  if ( (unsigned int)ElValidateWin32_0(Metadata, v36, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 696) )
    goto LABEL_150;
  LODWORD(ImageIdentifierPresent) = WdsImgGetLastModifiedTime(a2, &v158);
  if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v37, v38, 699) < 0 )
    goto LABEL_2;
  v142 = *v158;
  Metadata = CWdsMetadata::AppendTimeEntry(
               (CWdsMetadata *)v153,
               L"WDS.Image.ModificationTime",
               (struct _SYSTEMTIME *)&v142);
  if ( !(unsigned int)ElValidateWin32_0(Metadata, v39, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 703) )
  {
    LODWORD(ImageIdentifierPresent) = WdsImgGetProductName(a2, &v159);
    if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v40, v41, 706) < 0 )
      goto LABEL_2;
    Metadata = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Windows.ProductName", v159);
    if ( (unsigned int)ElValidateWin32_0(Metadata, v42, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 710) )
      goto LABEL_150;
    if ( (int)WdsImgGetProductFamily(a2, &v160) >= 0 )
    {
      Metadata = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Windows.ProductFamily", v160);
      if ( (unsigned int)ElValidateWin32_0(Metadata, v43, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 717) )
        goto LABEL_150;
    }
    if ( (int)WdsImgGetHalName(a2, &v161) >= 0 )
    {
      Metadata = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Windows.HAL", v161);
      if ( (unsigned int)ElValidateWin32_0(Metadata, v44, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 725) )
        goto LABEL_150;
    }
    LODWORD(ImageIdentifierPresent) = WdsImgGetLanguage(a2, &v162);
    if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v45, v46, 729) < 0 )
      goto LABEL_2;
    Metadata = CWdsMetadata::AppendStringEntry((CWdsMetadata *)v153, L"WDS.Image.Windows.Language.Default", v162);
    if ( !(unsigned int)ElValidateWin32_0(Metadata, v47, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 733) )
    {
      ImageIdentifierPresent = (unsigned int)WdsImgGetLanguages(a2, &v163, &v149);
      if ( (int)ElValidateHr_0(ImageIdentifierPresent, v48, v49, 736) < 0 )
        goto LABEL_2;
      while ( v3 < v149 )
      {
        Metadata = CWdsMetadata::AppendStringEntry(
                     (CWdsMetadata *)v153,
                     L"WDS.Image.Windows.Language",
                     *(const unsigned __int16 **)(v163 + 8LL * v3));
        if ( (unsigned int)ElValidateWin32_0(
                             Metadata,
                             v50,
                             "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                             742) )
          goto LABEL_150;
        ++v3;
      }
      ImageIdentifierPresent = (unsigned int)WdsImgGetVersion(a2, &v164);
      if ( (int)ElValidateHr_0(ImageIdentifierPresent, v52, v53, 754) < 0 )
        goto LABEL_2;
      ServicePackLevel = WdsImgGetServicePackLevel(a2, &v165);
      if ( (int)ElValidateHr_0(ServicePackLevel, v55, v56, 757) < 0 )
        goto LABEL_55;
      LODWORD(Metadata) = DuplicateStringW(v164, &Str);
      if ( (unsigned int)ElValidateWin32_0(
                           (unsigned int)Metadata,
                           v57,
                           "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                           760) )
        goto LABEL_150;
      v58 = wcsrchr(Str, 0x2Eu);
      v60 = v58;
      if ( !v58 )
        goto LABEL_155;
      v61 = -1;
      do
        ++v61;
      while ( v58[v61] );
      if ( v61 == 1 )
      {
LABEL_155:
        LODWORD(Metadata) = 13;
        if ( (unsigned int)ElValidateWin32_0(13, v59, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 767) )
          goto LABEL_150;
      }
      *v60 = 0;
      LODWORD(ImageIdentifierPresent) = StringCchCatW(v172, 0x80u, Str);
      if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v62, v63, 776) < 0 )
        goto LABEL_2;
      LODWORD(ImageIdentifierPresent) = StringCchCatW(v172, 0x80u, L".");
      if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v64, v65, 781) < 0 )
        goto LABEL_2;
      LODWORD(ImageIdentifierPresent) = StringCchCatW(v172, 0x80u, v165);
      if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v66, v67, 786) < 0 )
        goto LABEL_2;
      LODWORD(ImageIdentifierPresent) = StringCchCatW(v172, 0x80u, L".");
      if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v68, v69, 791) < 0 )
        goto LABEL_2;
      ServicePackLevel = StringCchCatW(v172, 0x80u, v60 + 1);
      if ( (int)ElValidateHr_0(ServicePackLevel, v70, v71, 796) < 0 )
        goto LABEL_55;
      LODWORD(Metadata) = CWdsMetadata::AppendEntry((CWdsMetadata *)v153, v172);
      if ( !(unsigned int)ElValidateWin32_0(
                            (unsigned int)Metadata,
                            v72,
                            "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                            799) )
      {
        v73 = (CImageCache *)((char *)this + 160);
        v142 = *v12;
        LODWORD(Metadata) = CWdsMetadataStoreManagementClient::CheckRegistration(
                              (CImageCache *)((char *)this + 160),
                              &v142,
                              (int *)v141);
        if ( !(unsigned int)ElValidateWin32_0(
                              (unsigned int)Metadata,
                              v74,
                              "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                              808) )
        {
          if ( LODWORD(v141[0]) )
          {
            v167[0] = 0;
            v144 = 0;
            v75 = *v12;
            v167[1] = 0;
            v167[3] = 0;
            v142 = v75;
            v167[4] = 0;
            v167[6] = 0;
            v167[7] = 0;
            v143 = 0;
            v151 = 0;
            v152 = 0;
            Metadata = CWdsMetadataStoreManagementClient::GetMetadata(
                         (CImageCache *)((char *)this + 160),
                         &v142,
                         (struct CWdsMetadata *)v167);
            if ( (unsigned int)ElValidateWin32_0(
                                 Metadata,
                                 v76,
                                 "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                 822) )
            {
LABEL_71:
              CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v151);
              CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v143);
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v167);
              goto LABEL_150;
            }
            v141[0] = 0;
            GroupIndex = CWdsMetadata::FindGroupIndex(v77, v167, L"WDS.Image.Priority");
            v80 = L"<error>";
            if ( GroupIndex < 0
              || (_mm_lfence(), v81 = *(unsigned int *)(*(_QWORD *)(v167[0] + 8LL * GroupIndex) + 20LL), !(_DWORD)v81) )
            {
              v82 = CWdsMetadataValue::Copy((CWdsMetadataValue *)&v143, (const struct CWdsMetadataValue *)&v151);
              v83 = 3768;
LABEL_78:
              LODWORD(Metadata) = v82;
              ElValidateWin32_2(v82, v79, v81, v83);
              goto LABEL_96;
            }
            if ( (unsigned int)v81 > 1 )
            {
              if ( g_ErrLibTraceFunction )
                g_ErrLibTraceFunction(
                  L"Expected 0 or 1 instances of Tag [%s]; received %u instances",
                  L"WDS.Image.Priority");
              v82 = 13;
              v83 = 3775;
              goto LABEL_78;
            }
            *(_QWORD *)&v142.Data1 = 0;
            v145 = 0;
            v146 = 0;
            Metadata = (unsigned int)CWdsMetadata::GetInstancesOfTag(v167, L"WDS.Image.Priority", &v145);
            if ( (unsigned int)ElValidateWin32_2(Metadata, v85, v86, 3785)
              || (Metadata = (unsigned int)CDynArray<unsigned short *,CDeallocateString>::GetItem(&v145, v84, &v142),
                  (unsigned int)ElValidateWin32_2(Metadata, v87, v88, 3788)) )
            {
              if ( v145 )
                operator delete(v145);
LABEL_96:
              if ( (unsigned int)ElValidateWin32_0(
                                   (unsigned int)Metadata,
                                   v84,
                                   "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                   828) )
                goto LABEL_71;
              if ( v143 == 4 )
              {
                v98 = *(_QWORD *)&v144.Data1;
                *(_QWORD *)&v142.Data1 = *(_QWORD *)&v144.Data1;
                LODWORD(Metadata) = 0;
                if ( (unsigned int)ElValidateWin32_0(
                                     0,
                                     v96,
                                     "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                     833) )
                  goto LABEL_71;
                Data1 = -1;
                if ( v98 > 0xFFFFFFFF )
                {
                  v102 = -2147024362;
                }
                else
                {
                  Data1 = v144.Data1;
                  v102 = 0;
                }
                *((_DWORD *)a3 + 16) = Data1;
                if ( (int)ElValidateHr_0(v102, v99, v100, 836) < 0 )
                {
                  LODWORD(Metadata) = WIN32_FROM_HRESULT(v102);
                  goto LABEL_71;
                }
              }
              else
              {
                *((_DWORD *)a3 + 16) = *(_DWORD *)(*(_QWORD *)&v166.Data1 + 152LL);
              }
              v141[0] = 0;
              v103 = CWdsMetadata::FindGroupIndex(v97, v167, L"WDS.Image.AssessmentID");
              if ( v103 < 0
                || (_mm_lfence(), v105 = *(unsigned int *)(*(_QWORD *)(v167[0] + 8LL * v103) + 20LL), !(_DWORD)v105) )
              {
                v106 = CWdsMetadataValue::Copy((CWdsMetadataValue *)&v143, (const struct CWdsMetadataValue *)&v151);
                v107 = 3768;
LABEL_112:
                LODWORD(Metadata) = v106;
                ElValidateWin32_2(v106, v104, v105, v107);
LABEL_130:
                if ( !(unsigned int)ElValidateWin32_0(
                                      (unsigned int)Metadata,
                                      v108,
                                      "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                      857) )
                {
                  if ( v143 == 6 )
                  {
                    LODWORD(Metadata) = 0;
                    v121 = 862;
                    v122 = 0;
                    Uuid = v144;
                  }
                  else
                  {
                    LODWORD(Metadata) = UuidCreate(&Uuid);
                    v122 = (unsigned int)Metadata;
                    v121 = 871;
                  }
                  if ( !(unsigned int)ElValidateWin32_0(
                                        v122,
                                        v120,
                                        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                        v121) )
                  {
                    v166 = Uuid;
                    LODWORD(Metadata) = CWdsMetadata::AppendGuidEntry(
                                          (CWdsMetadata *)v153,
                                          L"WDS.Image.AssessmentID",
                                          &v166);
                    if ( !(unsigned int)ElValidateWin32_0(
                                          (unsigned int)Metadata,
                                          v123,
                                          "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                          876) )
                    {
                      v154 = *(struct _GUID *)*(_QWORD *)&v154.Data1;
                      LODWORD(Metadata) = CWdsMetadataStoreManagementClient::SetMetadata(
                                            v73,
                                            &v154,
                                            (const struct CWdsMetadata *)v153,
                                            v124,
                                            (const struct CWdsMetadata *)v139,
                                            v140);
                      ElValidateWin32_0(
                        (unsigned int)Metadata,
                        v125,
                        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                        888);
                    }
                  }
                }
                goto LABEL_71;
              }
              if ( (unsigned int)v105 > 1 )
              {
                if ( g_ErrLibTraceFunction )
                  g_ErrLibTraceFunction(
                    L"Expected 0 or 1 instances of Tag [%s]; received %u instances",
                    L"WDS.Image.AssessmentID");
                v106 = 13;
                v107 = 3775;
                goto LABEL_112;
              }
              v146 = 0;
              *(_QWORD *)&v142.Data1 = 0;
              v145 = 0;
              Metadata = (unsigned int)CWdsMetadata::GetInstancesOfTag(v167, L"WDS.Image.AssessmentID", &v145);
              if ( (unsigned int)ElValidateWin32_2(Metadata, v109, v110, 3785)
                || (Metadata = (unsigned int)CDynArray<unsigned short *,CDeallocateString>::GetItem(&v145, v108, &v142),
                    (unsigned int)ElValidateWin32_2(Metadata, v111, v112, 3788)) )
              {
                if ( v145 )
                  operator delete(v145);
                goto LABEL_130;
              }
              v113 = *(_QWORD *)&v142.Data1;
              if ( *(_DWORD *)(*(_QWORD *)&v142.Data1 + 32LL) || *(_DWORD *)(*(_QWORD *)&v142.Data1 + 40LL) != 6 )
              {
                v115 = CWdsMetadataEntry::ToString(*(CWdsMetadataEntry **)&v142.Data1, v141);
                v114 = v141[0];
                if ( !v115 )
                  v80 = v141[0];
                if ( g_ErrLibTraceFunction )
                  g_ErrLibTraceFunction(
                    L"Entry %s is of type %s; expected %s",
                    v80,
                    off_180018DB0[*(int *)(v113 + 40)],
                    L"GUID");
                LODWORD(Metadata) = 13;
                if ( (unsigned int)ElValidateWin32_2(13, v116, v117, 3807) )
                  goto LABEL_126;
              }
              else
              {
                v114 = v141[0];
              }
              Metadata = CWdsMetadataValue::Copy(
                           (CWdsMetadataValue *)&v143,
                           (const struct CWdsMetadataValue *)(v113 + 40));
              ElValidateWin32_2(Metadata, v118, v119, 3811);
LABEL_126:
              if ( v145 )
                operator delete(v145);
              if ( v114 )
                operator delete(v114);
              goto LABEL_130;
            }
            v89 = *(_QWORD *)&v142.Data1;
            if ( *(_DWORD *)(*(_QWORD *)&v142.Data1 + 32LL) || *(_DWORD *)(*(_QWORD *)&v142.Data1 + 40LL) != 4 )
            {
              v91 = CWdsMetadataEntry::ToString(*(CWdsMetadataEntry **)&v142.Data1, v141);
              v90 = v141[0];
              v93 = L"<error>";
              if ( !v91 )
                v93 = v141[0];
              if ( g_ErrLibTraceFunction )
                g_ErrLibTraceFunction(
                  L"Entry %s is of type %s; expected %s",
                  v93,
                  off_180018DB0[*(int *)(v89 + 40)],
                  L"Integer");
              LODWORD(Metadata) = 13;
              if ( (unsigned int)ElValidateWin32_2(13, v93, v92, 3807) )
                goto LABEL_92;
            }
            else
            {
              v90 = v141[0];
            }
            Metadata = CWdsMetadataValue::Copy((CWdsMetadataValue *)&v143, (const struct CWdsMetadataValue *)(v89 + 40));
            ElValidateWin32_2(Metadata, v94, v95, 3811);
LABEL_92:
            if ( v145 )
              operator delete(v145);
            if ( v90 )
              operator delete(v90);
            goto LABEL_96;
          }
          v178 = 0;
          memset_0(v179, 0, 0x206u);
          *((_DWORD *)a3 + 16) = *((_DWORD *)this + 38);
          LODWORD(Metadata) = UuidCreate(&Uuid);
          if ( !(unsigned int)ElValidateWin32_0(
                                (unsigned int)Metadata,
                                v126,
                                "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                905) )
          {
            v154 = Uuid;
            LODWORD(Metadata) = CWdsMetadata::AppendGuidEntry((CWdsMetadata *)v153, L"WDS.Image.AssessmentID", &v154);
            if ( !(unsigned int)ElValidateWin32_0(
                                  (unsigned int)Metadata,
                                  v127,
                                  "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                  909) )
            {
              Metadata = CWdsMetadata::AppendEntry((CWdsMetadata *)v168, L"WDS.Object.Type='Image'");
              if ( !(unsigned int)ElValidateWin32_0(
                                    Metadata,
                                    v128,
                                    "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                    918) )
              {
                LODWORD(ImageIdentifierPresent) = StringCchPrintfW(
                                                    &v178,
                                                    0x104u,
                                                    L"%s[GreaterThanOrEqual;MatchGroup=%s]=0",
                                                    L"WDS.Image.Priority",
                                                    L"WDS.Image.Priority");
                if ( (int)ElValidateHr_0((unsigned int)ImageIdentifierPresent, v129, v130, 925) >= 0 )
                {
                  Metadata = CWdsMetadata::AppendEntry((CWdsMetadata *)v168, &v178);
                  if ( (unsigned int)ElValidateWin32_0(
                                       Metadata,
                                       v131,
                                       "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                       928) )
                    goto LABEL_150;
                  ServicePackLevel = StringCchPrintfW(
                                       &v178,
                                       0x104u,
                                       L"%s[LessThan;MatchGroup=%s]=1000000",
                                       L"WDS.Image.Priority",
                                       L"WDS.Image.Priority");
                  if ( (int)ElValidateHr_0(ServicePackLevel, v132, v133, 935) >= 0 )
                  {
                    LODWORD(Metadata) = CWdsMetadata::AppendEntry((CWdsMetadata *)v168, &v178);
                    if ( !(unsigned int)ElValidateWin32_0(
                                          (unsigned int)Metadata,
                                          v134,
                                          "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                          938) )
                    {
                      for ( i = 0; i < 0x13; ++i )
                      {
                        LODWORD(Metadata) = CWdsMetadata::AppendExclusionFilter((CWdsMetadata *)v169, off_180018D10[i]);
                        if ( (unsigned int)ElValidateWin32_0(
                                             (unsigned int)Metadata,
                                             v136,
                                             "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                             948) )
                          goto LABEL_150;
                      }
                      v154 = (struct _GUID)xmmword_18001CD10;
                      v166 = *v12;
                      LODWORD(Metadata) = CWdsMetadataStoreManagementClient::Register(
                                            v73,
                                            &v166,
                                            L"InstallImage",
                                            1,
                                            &v154,
                                            (const struct CWdsMetadata *)v153,
                                            (const struct CWdsMetadata *)v170,
                                            (const struct CWdsMetadata *)v168,
                                            (const struct CWdsMetadata *)v169);
                      ElValidateWin32_0(
                        (unsigned int)Metadata,
                        v137,
                        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                        964);
                    }
                    goto LABEL_150;
                  }
LABEL_55:
                  v10 = ServicePackLevel;
                  goto LABEL_3;
                }
LABEL_2:
                v10 = ImageIdentifierPresent;
LABEL_3:
                LODWORD(Metadata) = WIN32_FROM_HRESULT(v10);
              }
            }
          }
        }
      }
    }
  }
LABEL_150:
  if ( Str )
  {
    operator delete[](Str);
    Str = 0;
  }
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v169);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v168);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v170);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v153);
  return (unsigned int)Metadata;
}

```

## disassembly

```asm
0x1800096e8  mov     [rsp-8+arg_18], rbx
0x1800096ed  push    rbp
0x1800096ee  push    rsi
0x1800096ef  push    rdi
0x1800096f0  push    r12
0x1800096f2  push    r13
0x1800096f4  push    r14
0x1800096f6  push    r15
0x1800096f8  lea     rbp, [rsp-510h]
0x180009700  sub     rsp, 610h
0x180009707  mov     rax, cs:__security_cookie
0x18000970e  xor     rax, rsp
0x180009711  mov     [rbp+540h+var_40], rax
0x180009718  mov     eax, dword ptr cs:aWdsImageWindow_5+30h; "n="
0x18000971e  xor     esi, esi
0x180009720  movups  xmm1, xmmword ptr cs:aWdsImageWindow_5+10h; "e.Windows.Version="
0x180009727  mov     [rbp+540h+var_320], eax
0x18000972d  mov     r14, r8
0x180009730  movzx   eax, word ptr cs:aWdsImageWindow_5+34h; ""
0x180009737  xorps   xmm0, xmm0
0x18000973a  movups  xmmword ptr [rbp+540h+Uuid.Data1], xmm0
0x180009741  mov     rbx, rdx
0x180009744  mov     r15, rcx
0x180009747  movups  xmm0, xmmword ptr cs:aWdsImageWindow_5; "WDS.Image.Windows.Version="
0x18000974e  mov     qword ptr [rbp+540h+var_4B0.Data1], rcx
0x180009755  xor     edx, edx; Val
0x180009757  mov     r8d, 0CAh; Size
0x18000975d  mov     [rbp+540h+var_570], rsi
0x180009761  movaps  xmmword ptr [rbp+540h+var_350], xmm0
0x180009768  lea     rcx, [rbp+540h+var_31A]; void *
0x18000976f  movups  xmm0, xmmword ptr cs:aWdsImageWindow_5+20h; "s.Version="
0x180009776  mov     [rbp+540h+var_568], rsi
0x18000977a  mov     [rbp+540h+var_558], rsi
0x18000977e  movaps  [rbp+540h+var_330], xmm0
0x180009785  mov     [rbp+540h+var_550], rsi
0x180009789  mov     [rbp+540h+var_540], rsi
0x18000978d  mov     [rbp+540h+var_538], rsi
0x180009791  mov     [rbp+540h+var_3B0], rsi
0x180009798  mov     [rbp+540h+var_3A8], rsi
0x18000979f  mov     [rbp+540h+var_398], rsi
0x1800097a6  mov     [rbp+540h+var_390], rsi
0x1800097ad  mov     [rbp+540h+var_380], rsi
0x1800097b4  mov     [rbp+540h+var_378], rsi
0x1800097bb  mov     [rbp+540h+var_450], rsi
0x1800097c2  mov     [rbp+540h+var_448], rsi
0x1800097c9  mov     [rbp+540h+var_438], rsi
0x1800097d0  mov     [rbp+540h+var_430], rsi
0x1800097d7  mov     [rbp+540h+var_420], rsi
0x1800097de  mov     [rbp+540h+var_418], rsi
0x1800097e5  mov     [rbp+540h+var_400], rsi
0x1800097ec  mov     [rbp+540h+var_3F8], rsi
0x1800097f3  mov     [rbp+540h+var_3E8], rsi
0x1800097fa  mov     [rbp+540h+var_3E0], rsi
0x180009801  mov     [rbp+540h+var_3D0], rsi
0x180009808  mov     [rbp+540h+var_3C8], rsi
0x18000980f  mov     qword ptr [rsp+640h+var_5E0.Data1], rsi
0x180009814  mov     dword ptr [rsp+640h+var_5F0], esi
0x180009818  mov     [rbp+540h+var_5A0], esi
0x18000981b  mov     [rbp+540h+var_59C], esi
0x18000981e  mov     [rbp+540h+var_500], rsi
0x180009822  mov     [rbp+540h+var_4F8], rsi
0x180009826  mov     [rbp+540h+Str], rsi
0x18000982a  movaps  [rbp+540h+var_340], xmm1
0x180009831  mov     [rbp+540h+var_31C], ax
0x180009838  call    memset_0
0x18000983d  lea     rdx, [rbp+540h+var_5A0]
0x180009841  mov     [rbp+540h+var_510], rsi
0x180009845  mov     rcx, rbx
0x180009848  mov     [rbp+540h+var_508], rsi
0x18000984c  mov     [rbp+540h+var_4F0], rsi
0x180009850  mov     [rbp+540h+var_4E8], rsi
0x180009854  mov     [rbp+540h+var_4E0], rsi
0x180009858  mov     [rbp+540h+var_4D8], rsi
0x18000985c  mov     [rbp+540h+var_4D0], rsi
0x180009860  mov     [rbp+540h+var_598], esi
0x180009863  mov     [rbp+540h+var_4C8], rsi
0x180009867  mov     [rbp+540h+var_4C0], rsi
0x18000986e  call    cs:__imp_WdsImgGetImageIdentifierPresent
0x180009875  nop     dword ptr [rax+rax+00h]
0x18000987a  mov     ecx, eax
0x18000987c  mov     r9d, 23Ah
0x180009882  mov     edi, eax
0x180009884  call    ElValidateHr_0
0x180009889  test    eax, eax
0x18000988b  jns     short loc_1800098A2
0x18000988d  mov     ecx, edi
0x18000988f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180009896  nop     dword ptr [rax+rax+00h]
0x18000989b  mov     edi, eax
0x18000989d  jmp     loc_18000A8C8
0x1800098a2  cmp     [rbp+540h+var_5A0], esi
0x1800098a5  jnz     short loc_1800098B9
0x1800098a7  mov     eax, [r15+98h]
0x1800098ae  mov     edi, esi
0x1800098b0  mov     [r14+40h], eax
0x1800098b4  jmp     loc_18000A8C8
0x1800098b9  lea     r12, [r14+30h]
0x1800098bd  mov     rcx, rbx
0x1800098c0  mov     rdx, r12
0x1800098c3  mov     qword ptr [rbp+540h+var_520.Data1], r12
0x1800098c7  call    cs:__imp_WdsImgGetImageIdentifier
0x1800098ce  nop     dword ptr [rax+rax+00h]
0x1800098d3  mov     ecx, eax
0x1800098d5  mov     r9d, 24Bh
0x1800098db  mov     edi, eax
0x1800098dd  call    ElValidateHr_0
0x1800098e2  test    eax, eax
0x1800098e4  js      short loc_18000988D
0x1800098e6  lea     rdx, aWdsObjectTypeI; "WDS.Object.Type='Image'"
0x1800098ed  mov     dword ptr [r14+2Ch], 1
0x1800098f5  lea     rcx, [rbp+540h+var_570]; this
0x1800098f9  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x1800098fe  lea     r13, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180009905  mov     r9d, 255h
0x18000990b  mov     r8, r13
0x18000990e  mov     ecx, eax
0x180009910  mov     edi, eax
0x180009912  call    ElValidateWin32_0
0x180009917  test    eax, eax
0x180009919  jnz     loc_18000A8C8
0x18000991f  movups  xmm0, xmmword ptr [r12]
0x180009924  lea     r8, [rsp+640h+var_5E0]; struct _GUID
0x180009929  lea     rdx, aWdsObjectId; "WDS.Object.ID"
0x180009930  lea     rcx, [rbp+540h+var_570]; this
0x180009934  movdqu  xmmword ptr [rsp+640h+var_5E0.Data1], xmm0
0x18000993a  call    ?AppendGuidEntry@CWdsMetadata@@QEAAKPEBGU_GUID@@@Z; CWdsMetadata::AppendGuidEntry(ushort const *,_GUID)
0x18000993f  mov     r9d, 258h
0x180009945  mov     r8, r13
0x180009948  mov     ecx, eax
0x18000994a  mov     edi, eax
0x18000994c  call    ElValidateWin32_0
0x180009951  test    eax, eax
0x180009953  jnz     loc_18000A8C8
0x180009959  movups  xmm0, xmmword ptr [r12]
0x18000995e  lea     r8, [rsp+640h+var_5E0]; struct _GUID
0x180009963  lea     rdx, aWdsImageId; "WDS.Image.ID"
0x18000996a  lea     rcx, [rbp+540h+var_570]; this
0x18000996e  movdqu  xmmword ptr [rsp+640h+var_5E0.Data1], xmm0
0x180009974  call    ?AppendGuidEntry@CWdsMetadata@@QEAAKPEBGU_GUID@@@Z; CWdsMetadata::AppendGuidEntry(ushort const *,_GUID)
0x180009979  mov     r9d, 25Bh
0x18000997f  mov     r8, r13
0x180009982  mov     ecx, eax
0x180009984  mov     edi, eax
0x180009986  call    ElValidateWin32_0
0x18000998b  test    eax, eax
0x18000998d  jnz     loc_18000A8C8
0x180009993  mov     r8, [r14]; unsigned __int16 *
0x180009996  lea     rdx, aWdsImageGroup; "WDS.Image.Group"
0x18000999d  lea     rcx, [rbp+540h+var_570]; this
0x1800099a1  call    ?AppendStringEntry@CWdsMetadata@@QEAAKPEBG0@Z; CWdsMetadata::AppendStringEntry(ushort const *,ushort const *)
0x1800099a6  mov     r9d, 25Fh
0x1800099ac  mov     r8, r13
0x1800099af  mov     ecx, eax
0x1800099b1  mov     edi, eax
0x1800099b3  call    ElValidateWin32_0
0x1800099b8  test    eax, eax
0x1800099ba  jnz     loc_18000A8C8
0x1800099c0  mov     ecx, [r14+20h]
0x1800099c4  mov     eax, 0Dh
0x1800099c9  sub     ecx, 1
0x1800099cc  jz      loc_180009E08
0x1800099d2  sub     ecx, 1
0x1800099d5  jz      loc_180009DED
0x1800099db  cmp     ecx, 1
0x1800099de  jz      loc_180009DD2
0x1800099e4  mov     r9d, 274h
0x1800099ea  mov     r8, r13
0x1800099ed  mov     ecx, eax
0x1800099ef  mov     edi, eax
0x1800099f1  call    ElValidateWin32_0
0x1800099f6  test    eax, eax
0x1800099f8  jnz     loc_18000A8C8
0x1800099fe  lea     rdx, [rbp+540h+var_510]
0x180009a02  mov     rcx, rbx
0x180009a05  call    cs:__imp_WdsImgGetPath
0x180009a0c  nop     dword ptr [rax+rax+00h]
0x180009a11  mov     ecx, eax
0x180009a13  mov     r9d, 279h
0x180009a19  mov     edi, eax
0x180009a1b  call    ElValidateHr_0
0x180009a20  test    eax, eax
0x180009a22  js      loc_18000988D
0x180009a28  mov     r8, [rbp+540h+var_510]; unsigned __int16 *
0x180009a2c  lea     rdx, aWdsImagePath; "WDS.Image.Path"
0x180009a33  lea     rcx, [rbp+540h+var_570]; this
0x180009a37  call    ?AppendStringEntry@CWdsMetadata@@QEAAKPEBG0@Z; CWdsMetadata::AppendStringEntry(ushort const *,ushort const *)
0x180009a3c  mov     r9d, 27Dh
0x180009a42  mov     r8, r13
0x180009a45  mov     ecx, eax
0x180009a47  mov     edi, eax
0x180009a49  call    ElValidateWin32_0
0x180009a4e  test    eax, eax
0x180009a50  jnz     loc_18000A8C8
0x180009a56  mov     r8d, [r14+24h]; union _LARGE_INTEGER
0x180009a5a  lea     rcx, [rbp+540h+var_570]; this
0x180009a5e  call    ?AppendIntegerEntry@CWdsMetadata@@QEAAKPEBGT_LARGE_INTEGER@@@Z; CWdsMetadata::AppendIntegerEntry(ushort const *,_LARGE_INTEGER)
0x180009a63  mov     r9d, 282h
0x180009a69  mov     r8, r13
0x180009a6c  mov     ecx, eax
0x180009a6e  mov     edi, eax
0x180009a70  call    ElValidateWin32_0
0x180009a75  test    eax, eax
0x180009a77  jnz     loc_18000A8C8
0x180009a7d  lea     rdx, [rbp+540h+var_59C]
0x180009a81  mov     rcx, rbx
0x180009a84  call    cs:__imp_WdsImgGetArchitecture
0x180009a8b  nop     dword ptr [rax+rax+00h]
0x180009a90  mov     ecx, eax
0x180009a92  mov     r9d, 285h
0x180009a98  mov     edi, eax
0x180009a9a  call    ElValidateHr_0
0x180009a9f  test    eax, eax
0x180009aa1  js      loc_18000988D
0x180009aa7  mov     eax, [rbp+540h+var_59C]
0x180009aaa  test    eax, eax
0x180009aac  jz      loc_180009E6B
0x180009ab2  cmp     eax, 5
0x180009ab5  jz      loc_180009E53
0x180009abb  cmp     eax, 9
0x180009abe  jz      loc_180009E3B
0x180009ac4  cmp     eax, 0Ch
0x180009ac7  jz      loc_180009E23
0x180009acd  mov     ecx, 0Dh
0x180009ad2  mov     r9d, 29Fh
0x180009ad8  mov     edi, ecx
0x180009ada  mov     r8, r13
0x180009add  call    ElValidateWin32_0
0x180009ae2  test    eax, eax
0x180009ae4  jnz     loc_18000A8C8
0x180009aea  mov     r8, [r14+10h]; unsigned __int16 *
0x180009aee  lea     rdx, aWdsImageName; "WDS.Image.Name"
0x180009af5  lea     rcx, [rbp+540h+var_570]; this
0x180009af9  call    ?AppendStringEntry@CWdsMetadata@@QEAAKPEBG0@Z; CWdsMetadata::AppendStringEntry(ushort const *,ushort const *)
0x180009afe  mov     r9d, 2A3h
0x180009b04  mov     r8, r13
0x180009b07  mov     ecx, eax
0x180009b09  mov     edi, eax
0x180009b0b  call    ElValidateWin32_0
0x180009b10  test    eax, eax
0x180009b12  jnz     loc_18000A8C8
0x180009b18  lea     rdx, [rbp+540h+var_508]
0x180009b1c  mov     rcx, rbx
0x180009b1f  call    cs:__imp_WdsImgGetDescription
0x180009b26  nop     dword ptr [rax+rax+00h]
0x180009b2b  test    eax, eax
0x180009b2d  js      short loc_180009B5D
0x180009b2f  mov     r8, [rbp+540h+var_508]; unsigned __int16 *
0x180009b33  lea     rdx, aWdsImageDescri; "WDS.Image.Description"
0x180009b3a  lea     rcx, [rbp+540h+var_570]; this
0x180009b3e  call    ?AppendStringEntry@CWdsMetadata@@QEAAKPEBG0@Z; CWdsMetadata::AppendStringEntry(ushort const *,ushort const *)
0x180009b43  mov     r9d, 2B0h
0x180009b49  mov     r8, r13
0x180009b4c  mov     ecx, eax
0x180009b4e  mov     edi, eax
0x180009b50  call    ElValidateWin32_0
0x180009b55  test    eax, eax
0x180009b57  jnz     loc_18000A8C8
0x180009b5d  lea     rdx, [rbp+540h+var_500]
0x180009b61  mov     rcx, rbx
0x180009b64  call    cs:__imp_WdsImgGetCreationTime
0x180009b6b  nop     dword ptr [rax+rax+00h]
0x180009b70  mov     ecx, eax
0x180009b72  mov     r9d, 2B4h
0x180009b78  mov     edi, eax
0x180009b7a  call    ElValidateHr_0
0x180009b7f  test    eax, eax
0x180009b81  js      loc_18000988D
0x180009b87  mov     rax, [rbp+540h+var_500]
0x180009b8b  lea     r8, [rsp+640h+var_5E0]; struct _SYSTEMTIME
0x180009b90  lea     rdx, aWdsImageCreati; "WDS.Image.CreationTime"
0x180009b97  lea     rcx, [rbp+540h+var_570]; this
0x180009b9b  movups  xmm0, xmmword ptr [rax]
0x180009b9e  movdqu  xmmword ptr [rsp+640h+var_5E0.Data1], xmm0
0x180009ba4  call    ?AppendTimeEntry@CWdsMetadata@@QEAAKPEBGU_SYSTEMTIME@@@Z; CWdsMetadata::AppendTimeEntry(ushort const *,_SYSTEMTIME)
0x180009ba9  mov     r9d, 2B8h
0x180009baf  mov     r8, r13
0x180009bb2  mov     ecx, eax
0x180009bb4  mov     edi, eax
0x180009bb6  call    ElValidateWin32_0
0x180009bbb  test    eax, eax
0x180009bbd  jnz     loc_18000A8C8
0x180009bc3  lea     rdx, [rbp+540h+var_4F8]
0x180009bc7  mov     rcx, rbx
0x180009bca  call    cs:__imp_WdsImgGetLastModifiedTime
0x180009bd1  nop     dword ptr [rax+rax+00h]
0x180009bd6  mov     ecx, eax
0x180009bd8  mov     r9d, 2BBh
0x180009bde  mov     edi, eax
0x180009be0  call    ElValidateHr_0
0x180009be5  test    eax, eax
0x180009be7  js      loc_18000988D
0x180009bed  mov     rax, [rbp+540h+var_4F8]
0x180009bf1  lea     r8, [rsp+640h+var_5E0]; struct _SYSTEMTIME
0x180009bf6  lea     rdx, aWdsImageModifi; "WDS.Image.ModificationTime"
0x180009bfd  lea     rcx, [rbp+540h+var_570]; this
0x180009c01  movups  xmm0, xmmword ptr [rax]
0x180009c04  movdqu  xmmword ptr [rsp+640h+var_5E0.Data1], xmm0
0x180009c0a  call    ?AppendTimeEntry@CWdsMetadata@@QEAAKPEBGU_SYSTEMTIME@@@Z; CWdsMetadata::AppendTimeEntry(ushort const *,_SYSTEMTIME)
0x180009c0f  mov     r9d, 2BFh
0x180009c15  mov     r8, r13
  ... truncated ...
```
