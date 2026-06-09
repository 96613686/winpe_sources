# Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(ulong,_EVENT_TRACE *)

- ea: `0x180016698`
- end: `0x180017eec`
- name: `?AddImageIdEvents@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAU_EVENT_TRACE@@@Z`
- size: `6228`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18001ad80`

## callees

- `0x180001d66`
- `0x18000a89c`
- `0x18000aadc`
- `0x18000e390`
- `0x180012a18`
- `0x180012cbc`
- `0x180015524`
- `0x180015c88`
- `0x180015e34`
- `0x18001616c`
- `0x180016248`
- `0x180016478`
- `0x180016698`
- `0x1800182e4`
- `0x18001871c`
- `0x180018de8`
- `0x180019164`
- `0x1800198f0`
- `0x180019de8`
- `0x180019f5c`
- `0x18001c398`
- `0x18002fa2c`
- `0x18002fae4`
- `0x1800319ae`
- `0x1800319c6`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180017790`
- `msvcrt!_stricmp` at `0x180017790`
- `msvcrt!wcsrchr` at `0x180016910`
- `msvcrt!wcsrchr` at `0x1800169c5`
- `msvcrt!wcsrchr` at `0x180016910`
- `msvcrt!wcsrchr` at `0x1800169c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170c1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170db`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170f5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170c1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170db`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800170f5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016f03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016f03`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016da2`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016e3a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016e89`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016da2`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016e3a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180016e89`
- `ole32!CoCreateGuid` at `0x180017bf7`
- `ole32!CoCreateGuid` at `0x180017bf7`

## string_xrefs

- `0x18001694e`: `Unable to parse image path: %s`
- `0x180016978`: `NULL path in image path.`
- `0x180016c32`: `\SystemRoot\System32\DriverStore\FileRepository\`
- `0x180016ce1`: `\\?\GLOBALROOT\DriverStores\BSPDRIVERS\System32\DriverStore\FileRepository\`
- `0x180016d2a`: `OS bug workaround - trying alternate path: %s`
- `0x180017b9f`: `CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        int a2,
        struct _EVENT_TRACE *a3)
{
  struct _EVENT_TRACE *v3; // r12
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rsi
  unsigned int v6; // ebx
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  unsigned int v9; // r14d
  wchar_t *v10; // rdi
  unsigned int *MofData; // rcx
  unsigned int MofLength; // r10d
  int v13; // r15d
  int v14; // eax
  char *v15; // rax
  __int64 v16; // r14
  wchar_t *v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 result; // rax
  __int64 v21; // rdi
  wchar_t *v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  unsigned int *v26; // rax
  int v27; // eax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v28; // r13
  int Only2; // eax
  union _CVDD *v30; // r9
  signed int v31; // r14d
  wchar_t *v32; // rdi
  WCHAR *v33; // r8
  WCHAR *v34; // rdx
  unsigned int v35; // edi
  int v36; // r14d
  DWORD FinalPathNameByHandleW; // eax
  __int64 v38; // r8
  unsigned __int64 v39; // rdi
  WCHAR *v40; // rax
  WCHAR *v41; // rdx
  int v42; // eax
  WCHAR *v43; // rdx
  __int64 v44; // r8
  DWORD v45; // eax
  Microsoft::Xbox *v46; // rcx
  unsigned int v47; // edx
  int v48; // eax
  unsigned __int16 *v49; // r14
  union _CVDD **v50; // r14
  unsigned __int16 *v51; // rdx
  struct CODEVIEW_INFORMATION_1 *v52; // r8
  struct CODEVIEW_INFORMATION_1 *v53; // rax
  unsigned int v54; // r13d
  unsigned int v55; // r14d
  int v56; // eax
  const union _CVDD *v57; // rdx
  union _CVDD *v58; // rcx
  const struct CODEVIEW_INFORMATION_1 *v59; // r8
  unsigned int v60; // edi
  unsigned int v61; // r9d
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v62; // r14
  unsigned int v63; // r14d
  int v64; // ecx
  __int64 v65; // rax
  int v66; // esp
  _DWORD *v67; // r13
  unsigned int v68; // ecx
  unsigned int i; // eax
  __int64 v70; // rdx
  unsigned int v71; // ecx
  _DWORD *v72; // rdx
  char v73; // al
  unsigned __int64 v74; // rax
  int v75; // eax
  DWORD v76; // ecx
  unsigned int v77; // ecx
  int v78; // eax
  unsigned int v79; // edx
  int EmbeddedPdb; // eax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v81; // rbx
  int v82; // edx
  unsigned int *p_pguid; // rcx
  int v84; // r13d
  int v85; // eax
  unsigned int v86; // [rsp+20h] [rbp-8E8h]
  unsigned int v87; // [rsp+20h] [rbp-8E8h]
  union _CVDD **v88; // [rsp+20h] [rbp-8E8h]
  unsigned int **v89; // [rsp+28h] [rbp-8E0h]
  struct CODEVIEW_INFORMATION_1 **v90; // [rsp+30h] [rbp-8D8h]
  struct CODEVIEW_INFORMATION_1 **v91; // [rsp+30h] [rbp-8D8h]
  union _CVDD *v92; // [rsp+38h] [rbp-8D0h]
  struct CODEVIEW_INFORMATION_1 *v93; // [rsp+40h] [rbp-8C8h]
  struct CODEVIEW_INFORMATION_1 *v94; // [rsp+48h] [rbp-8C0h]
  bool *v95; // [rsp+50h] [rbp-8B8h]
  unsigned int *v96; // [rsp+58h] [rbp-8B0h]
  unsigned int v97; // [rsp+60h] [rbp-8A8h]
  bool *v98; // [rsp+60h] [rbp-8A8h]
  bool *v99; // [rsp+60h] [rbp-8A8h]
  unsigned int v100[2]; // [rsp+68h] [rbp-8A0h]
  __int64 MappedAsImage; // [rsp+70h] [rbp-898h]
  struct EMBEDDED_PDB_INFORMATION *v102; // [rsp+78h] [rbp-890h]
  struct XPerfCore::IErrorMessage *v103; // [rsp+90h] [rbp-878h] BYREF
  int v104; // [rsp+98h] [rbp-870h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v105; // [rsp+A0h] [rbp-868h]
  DWORD Size; // [rsp+A8h] [rbp-860h]
  _BYTE Size_4[4]; // [rsp+ACh] [rbp-85Ch] BYREF
  unsigned int *v108; // [rsp+B0h] [rbp-858h] BYREF
  __int64 v109; // [rsp+B8h] [rbp-850h] BYREF
  unsigned __int64 v110; // [rsp+C0h] [rbp-848h]
  __int64 v111; // [rsp+C8h] [rbp-840h] BYREF
  wchar_t *String1; // [rsp+D0h] [rbp-838h]
  union _CVDD *v113; // [rsp+E0h] [rbp-828h] BYREF
  struct CODEVIEW_INFORMATION_1 *v114; // [rsp+E8h] [rbp-820h] BYREF
  unsigned int *v115; // [rsp+F0h] [rbp-818h]
  void *Src; // [rsp+F8h] [rbp-810h]
  unsigned __int16 *v117; // [rsp+100h] [rbp-808h]
  union _CVDD *v118; // [rsp+108h] [rbp-800h]
  __int128 v119; // [rsp+110h] [rbp-7F8h] BYREF
  __int64 v120; // [rsp+120h] [rbp-7E8h]
  union _CVDD *v121; // [rsp+128h] [rbp-7E0h]
  HANDLE hFile[2]; // [rsp+130h] [rbp-7D8h] BYREF
  unsigned __int16 *v123; // [rsp+140h] [rbp-7C8h]
  void *v124; // [rsp+148h] [rbp-7C0h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v125; // [rsp+150h] [rbp-7B8h]
  struct _EVENT_TRACE *v126; // [rsp+158h] [rbp-7B0h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v127; // [rsp+160h] [rbp-7A8h]
  __int64 v128; // [rsp+168h] [rbp-7A0h]
  ATL::CAtlException *v129; // [rsp+170h] [rbp-798h] BYREF
  __int128 v130; // [rsp+180h] [rbp-788h] BYREF
  __m256i v131; // [rsp+190h] [rbp-778h]
  __int128 v132; // [rsp+1B0h] [rbp-758h]
  __int128 v133; // [rsp+1C0h] [rbp-748h]
  DWORD v134; // [rsp+1D0h] [rbp-738h]
  int v135; // [rsp+1D4h] [rbp-734h]
  WCHAR szFilePath[4]; // [rsp+1E0h] [rbp-728h] BYREF
  unsigned __int64 v137; // [rsp+1F0h] [rbp-718h]
  unsigned __int64 v138; // [rsp+1F8h] [rbp-710h]
  GUID pguid; // [rsp+200h] [rbp-708h] BYREF
  unsigned __int64 v140; // [rsp+210h] [rbp-6F8h] BYREF
  unsigned __int64 v141; // [rsp+218h] [rbp-6F0h] BYREF
  unsigned int v142; // [rsp+220h] [rbp-6E8h] BYREF
  unsigned int v143; // [rsp+224h] [rbp-6E4h]
  unsigned __int16 v144[4]; // [rsp+228h] [rbp-6E0h] BYREF
  int v145; // [rsp+230h] [rbp-6D8h]
  wchar_t String2[56]; // [rsp+850h] [rbp-B8h] BYREF

  v128 = -2;
  v3 = a3;
  v126 = a3;
  v5 = this;
  v125 = this;
  v127 = this;
  *(_QWORD *)&pguid.Data1 = a3;
  v6 = 0;
  v7 = 0;
  v109 = 0;
  v8 = 0;
  v110 = 0;
  v9 = 0;
  v111 = 0;
  v10 = 0;
  String1 = 0;
  MofData = (unsigned int *)v3->MofData;
  MofLength = v3->MofLength;
  if ( !v3->Header.Class.Version )
  {
LABEL_211:
    if ( (**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *, __int64))v5 + 47))(
           (__int64)v5 + 376,
           L"Failed to parse image event.",
           v7) )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
    }
    return 1;
  }
  if ( v3->Header.Class.Version == 1 )
  {
    if ( a2 != 4 )
    {
      v13 = 8;
      if ( a2 != 8 )
        goto LABEL_211;
      if ( MofLength < 0x18 )
        goto LABEL_8;
      HIDWORD(v109) = MofData[2];
      v10 = (wchar_t *)(MofData + 5);
LABEL_10:
      v8 = *(_QWORD *)MofData;
      v7 = MofData[4];
      String1 = v10;
      v110 = v8;
      LODWORD(v109) = v7;
      v14 = 0;
      goto LABEL_26;
    }
    if ( MofLength >= 0x10 )
    {
      HIDWORD(v109) = MofData[1];
      v10 = (wchar_t *)(MofData + 3);
      goto LABEL_24;
    }
  }
  else
  {
    if ( (unsigned int)v3->Header.Class.Version - 2 > 1 )
      goto LABEL_211;
    if ( *((_DWORD *)v5 + 8) < 0xBu )
    {
      if ( a2 != 4 )
        goto LABEL_6;
      if ( MofLength >= 0x2C )
      {
        v10 = (wchar_t *)(MofData + 10);
        goto LABEL_13;
      }
    }
    else
    {
      if ( a2 != 4 )
      {
LABEL_6:
        v13 = 8;
        if ( a2 != 8 )
          goto LABEL_211;
        if ( MofLength < 0x40 )
        {
LABEL_8:
          v14 = -2147024883;
          goto LABEL_26;
        }
        HIDWORD(v109) = MofData[2];
        v10 = (wchar_t *)(MofData + 14);
        v9 = MofData[5];
        LODWORD(v111) = v9;
        HIDWORD(v111) = MofData[6];
        goto LABEL_10;
      }
      if ( MofLength >= 0x30 )
      {
        v10 = (wchar_t *)(MofData + 11);
LABEL_13:
        HIDWORD(v109) = MofData[1];
        v9 = MofData[3];
        LODWORD(v111) = v9;
        HIDWORD(v111) = MofData[4];
LABEL_24:
        v7 = MofData[2];
        v8 = *MofData;
        LODWORD(v109) = MofData[2];
        v110 = v8;
        String1 = v10;
        v14 = 0;
        goto LABEL_25;
      }
    }
  }
  v14 = -2147024883;
LABEL_25:
  v13 = 8;
LABEL_26:
  if ( v14 < 0 )
    goto LABEL_211;
  if ( *((_QWORD *)v5 + 5) == v3->Header.TimeStamp.QuadPart
    && *((_DWORD *)v5 + 12) == (_DWORD)v7
    && *((_QWORD *)v5 + 7) == v8 )
  {
    return 1;
  }
  v15 = (char *)v5 + 64;
  if ( !*((_BYTE *)v5 + 176) )
  {
    try
    {
      Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize((Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 64));
      v15 = (char *)v5 + 64;
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
    catch ( ATL::CAtlException *v129 )
    {
      if ( *(_DWORD *)v129 == -2147024882 )
        return (unsigned int)-2147024882;
      *((_BYTE *)v127 + 200) = 1;
      return 1;
    }
  }
  if ( !(unsigned __int8)Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
                           v15,
                           v10,
                           (char *)v5 + 192)
    && (!*((_QWORD *)v5 + 23)
     || !(unsigned __int8)Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
                            *((_QWORD *)v5 + 23),
                            v10,
                            (char *)v5 + 192)) )
  {
    if ( v10 )
    {
      v16 = 0;
      if ( !*((_BYTE *)v5 + 201) )
      {
        v17 = wcsrchr(v10, 0x5Cu);
        if ( v17 )
        {
          v18 = v17 - v10 + 1;
          v19 = -1;
          do
            ++v19;
          while ( v10[v19] );
          v16 = v18 & -(__int64)(v18 < v19);
        }
      }
      if ( !(**((unsigned __int8 (***)(__int64, const wchar_t *, ...))v5 + 47))(
              (__int64)v5 + 376,
              L"Unable to parse image path: %s",
              &v10[v16]) )
        return 1;
    }
    else if ( !(**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *))v5 + 47))(
                 (__int64)v5 + 376,
                 L"NULL path in image path.") )
    {
      return 1;
    }
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
    return 1;
  }
  try
  {
    v118 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
    if ( *((_BYTE *)v5 + 201) )
    {
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))(
        (__int64)v5 + 376,
        L"%s [%s] failure: ",
        *((_QWORD *)v5 + 24),
        v10);
    }
    else
    {
      v21 = 0;
      v22 = wcsrchr(*((const wchar_t **)v5 + 24), 0x5Cu);
      if ( v22 )
      {
        v23 = *((_QWORD *)v5 + 24);
        v24 = (((__int64)v22 - v23) >> 1) + 1;
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v23 + 2 * v25) );
        v21 = v24 & -(__int64)(v24 < v25);
      }
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))(
        (__int64)v5 + 376,
        L"%s failure: ",
        *((_QWORD *)v5 + 24) + 2 * v21);
    }
    v121 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  memset_0(&v140, 0, 0x640u);
  if ( a2 == 4 )
    v26 = &v142;
  else
    v26 = (unsigned int *)v144;
  v115 = v26;
  HIDWORD(v103) = 0;
  v113 = 0;
  v108 = 0;
  v114 = 0;
  v119 = 0;
  v120 = 0;
  BYTE1(v103) = 0;
  Src = (char *)v5 + 208;
  v27 = Microsoft::Windows::Performance::CCvDDCache::Find(
          (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 208),
          *((const unsigned __int16 **)v5 + 24),
          v9,
          (unsigned int *)&v103 + 1,
          &v113,
          (const unsigned int **)&v108,
          &v114,
          (unsigned int *)&v111 + 1,
          (unsigned int *)&v109 + 1,
          (struct EMBEDDED_PDB_INFORMATION *)&v119,
          (bool *)&v103 + 1,
          (unsigned __int16 *)v26,
          v97);
  if ( v27 >= 0 )
  {
    v54 = HIDWORD(v111);
    v63 = v109;
    v104 = HIDWORD(v103);
    v118 = (union _CVDD *)v108;
    v108 = (unsigned int *)v114;
    goto LABEL_140;
  }
  if ( v27 != -2147023728 )
  {
    if ( v27 != -2147467259 && v27 != -2147024774 )
    {
      v35 = -2147024882;
      if ( v27 != -2147024882 )
      {
        (*(void (**)(__int64, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
          (__int64)v5 + 376,
          L"unexpected caching error: %x");
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
        v35 = 1;
        *((_BYTE *)v5 + 200) = 1;
      }
      return v35;
    }
    return 1;
  }
  v104 = *((_DWORD *)v5 + 92);
  HIDWORD(v103) = v104;
  v117 = (unsigned __int16 *)((char *)v5 + 344);
  if ( !*((_QWORD *)v5 + 43) )
    return 2147549183LL;
  v108 = (unsigned int *)((char *)v5 + 352);
  if ( !*((_QWORD *)v5 + 44) )
    return 2147549183LL;
  v114 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 360);
  if ( !*((_QWORD *)v5 + 45) )
    return 2147549183LL;
  LOBYTE(v103) = Performance::COSVersionInfo::IsWin8AndUp();
  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm);
  v123 = 0;
  v124 = 0;
  v28 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)*((_QWORD *)v5 + 24);
  v105 = v28;
  v113 = v28;
  Only2 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
            (XPerfCore::CFileMapping *)hFile,
            (const unsigned __int16 *)v28,
            (bool)v103,
            (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
  v31 = Only2;
  if ( Only2 >= 0 )
  {
    v35 = 1;
    goto LABEL_102;
  }
  if ( Only2 != -2147024893
    || (wcscpy(String2, L"\\SystemRoot\\System32\\DriverStore\\FileRepository\\"),
        v32 = String1,
        wcsncmp_0(String1, String2, 0x30u)) )
  {
    v35 = 1;
    v46 = v28;
LABEL_112:
    if ( !*((_BYTE *)v5 + 202) )
    {
      v54 = HIDWORD(v111);
      goto LABEL_120;
    }
    v51 = v117;
    if ( *(_QWORD *)v117 )
    {
      if ( *(_QWORD *)v108 )
      {
        v52 = v114;
        v53 = *(struct CODEVIEW_INFORMATION_1 **)v114;
        if ( *(_QWORD *)v114 )
        {
          v104 = 1;
          v54 = HIDWORD(v111);
          *(_DWORD *)v53 = HIDWORD(v111);
          *(_WORD *)(*(_QWORD *)v52 + 4LL) = 0;
          *(_WORD *)(*(_QWORD *)v52 + 6LL) = 0;
          v31 = Microsoft::Xbox::CvDbgInfoFromVBI(
                  v46,
                  v51,
                  *(struct Microsoft::Windows::Performance::CErrorEvent **)v51,
                  v30);
          **(_DWORD **)v108 = 1576;
LABEL_120:
          if ( v31 < 0 )
          {
            Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
            Microsoft::Windows::Performance::CCvDDCache::AddFailure(
              (Microsoft::Windows::Performance::CCvDDCache *)Src,
              (const unsigned __int16 *)v105,
              v111);
            goto LABEL_130;
          }
          v55 = v104;
          goto LABEL_124;
        }
      }
    }
    v35 = -2147418113;
LABEL_130:
    XPerfCore::CFileMapping::~CFileMapping((XPerfCore::CFileMapping *)hFile);
    return v35;
  }
  try
  {
    v138 = 7;
    v137 = 0;
    szFilePath[0] = 0;
    std::wstring::assign(
      szFilePath,
      L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS\\System32\\DriverStore\\FileRepository\\");
    std::wstring::operator+=(szFilePath, v32 + 48);
    v33 = szFilePath;
    if ( v138 >= 8 )
      v33 = *(WCHAR **)szFilePath;
    (*(void (**)(__int64, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
      (__int64)v5 + 376,
      L"OS bug workaround - trying alternate path: %s",
      v33);
    v34 = szFilePath;
    if ( v138 >= 8 )
      v34 = *(WCHAR **)szFilePath;
    v31 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
            (XPerfCore::CFileMapping *)hFile,
            v34,
            (bool)v103,
            (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
    if ( v31 < 0 )
    {
      v35 = 1;
LABEL_96:
      v105 = v28;
      if ( v138 >= 8 )
        operator delete(*(void **)szFilePath);
      goto LABEL_233;
    }
    if ( hFile[0] == (HANDLE)-1LL )
    {
      v35 = 1;
      v36 = 87;
LABEL_94:
      v31 = v36 | 0x80070000;
      goto LABEL_96;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile[0], 0, 0, 0);
    Size = FinalPathNameByHandleW;
    v39 = v137;
    if ( v137 <= FinalPathNameByHandleW && v138 != FinalPathNameByHandleW )
    {
      LOBYTE(v38) = 1;
      if ( (unsigned __int8)std::wstring::_Grow(szFilePath, FinalPathNameByHandleW, v38) )
      {
        v40 = szFilePath;
        if ( v138 >= 8 )
          v40 = *(WCHAR **)szFilePath;
        v137 = v39;
        v40[v39] = 0;
      }
      FinalPathNameByHandleW = Size;
    }
    v35 = 1;
    if ( v138 < 8 )
    {
      v41 = szFilePath;
    }
    else
    {
      v41 = *(WCHAR **)szFilePath;
      if ( !*(_QWORD *)szFilePath )
        goto LABEL_81;
    }
    if ( FinalPathNameByHandleW )
    {
      v45 = GetFinalPathNameByHandleW(hFile[0], v41, FinalPathNameByHandleW, 0);
      v42 = v45 >= Size ? 0x7A : 0;
LABEL_82:
      if ( v42 )
      {
        v36 = v42;
        goto LABEL_94;
      }
      if ( v138 < 8 )
      {
        v43 = szFilePath;
      }
      else
      {
        v43 = *(WCHAR **)szFilePath;
        if ( !*(_QWORD *)szFilePath )
        {
          v44 = 0;
LABEL_92:
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v5 + 192, v43, v44);
          v28 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)*((_QWORD *)v5 + 24);
          v113 = v28;
          goto LABEL_96;
        }
      }
      v44 = -1;
      do
        ++v44;
      while ( v43[v44] );
      goto LABEL_92;
    }
LABEL_81:
    GetFinalPathNameByHandleW(hFile[0], 0, 0, 0);
    v42 = 122;
    goto LABEL_82;
  }
  catch ( std::bad_alloc )
  {
    v6 = 0;
    v35 = 1;
    v13 = 8;
    v31 = -2147024882;
    v104 = HIDWORD(v103);
    v46 = v113;
    v105 = v113;
    v3 = *(struct _EVENT_TRACE **)&pguid.Data1;
    v126 = *(struct _EVENT_TRACE **)&pguid.Data1;
    v5 = v127;
    v125 = v127;
    v118 = v121;
    goto LABEL_112;
  }
LABEL_233:
  v138 = 7;
  v137 = 0;
  szFilePath[0] = 0;
  if ( v31 < 0 )
    goto LABEL_111;
LABEL_102:
  v47 = (unsigned int)v124;
  v113 = (union _CVDD *)v124;
  if ( (unsigned __int64)v124 >= 0xFFFFFFFF )
  {
    v47 = -1;
    v113 = (union _CVDD *)0xFFFFFFFFLL;
  }
  LODWORD(v98) = 780;
  v48 = XPerf::Internal::CvDbgInfoFromImage2(
          v28,
          v123,
          (void *)v47,
          v111,
          v86,
          (unsigned int *)&v103 + 1,
          *(union _CVDD **)v117,
          *(union _CVDD **)v108,
          *(struct CODEVIEW_INFORMATION_1 **)v114,
          (struct CODEVIEW_INFORMATION_1 *)((char *)&v111 + 4),
          (unsigned int *)&v109 + 1,
          v115,
          (unsigned __int16 *)v98,
          (unsigned int)Size_4,
          (BOOLEAN)v103,
          (struct EMBEDDED_PDB_INFORMATION *)&v119,
          (struct EMBEDDED_PDB_INFORMATION *)((char *)&v103 + 1),
          (bool *)v5 + 376,
          v103);
  v31 = v48;
  if ( v48 < 0 )
  {
    if ( v48 != -2146893023 )
      goto LABEL_110;
    *((_DWORD *)v5 + 92) = 0;
    v49 = v117;
    operator delete[](*(void **)v117);
    *(_QWORD *)v49 = 0;
    v50 = (union _CVDD **)v108;
    operator delete[](*(void **)v108);
    *v50 = 0;
    operator delete[](*(void **)v114);
    *(_QWORD *)v114 = 0;
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v117, HIDWORD(v103))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v50, HIDWORD(v103))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(v114, HIDWORD(v103)) )
    {
      v35 = -2147024882;
      goto LABEL_130;
    }
    *((_DWORD *)v5 + 92) = HIDWORD(v103);
    LODWORD(v99) = 780;
    v31 = XPerf::Internal::CvDbgInfoFromImage2(
            v28,
            v123,
            (void *)(unsigned int)v113,
            v111,
            v87,
            (unsigned int *)&v103 + 1,
            *(union _CVDD **)v117,
            *v50,
            *(struct CODEVIEW_INFORMATION_1 **)v114,
            (struct CODEVIEW_INFORMATION_1 *)((char *)&v111 + 4),
            (unsigned int *)&v109 + 1,
            v115,
            (unsigned __int16 *)v99,
            (unsigned int)Size_4,
            (BOOLEAN)v103,
            (struct EMBEDDED_PDB_INFORMATION *)&v119,
            (struct EMBEDDED_PDB_INFORMATION *)((char *)&v103 + 1),
            (bool *)v5 + 376,
            v103);
    if ( v31 < 0 )
    {
LABEL_110:
      v104 = HIDWORD(v103);
LABEL_111:
      v46 = v105;
      goto LABEL_112;
    }
  }
  v54 = HIDWORD(v111);
  v55 = HIDWORD(v103);
  v104 = HIDWORD(v103);
LABEL_124:
  if ( !*(_BYTE *)v118 )
  {
    v56 = Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
            v46,
            v55,
            *(union _CVDD **)v117,
            *(unsigned int **)v108);
    if ( v56 < 0 )
      goto LABEL_129;
  }
  v57 = *(const union _CVDD **)v117;
  v113 = *(union _CVDD **)v117;
  v58 = *(union _CVDD **)v108;
  v118 = *(union _CVDD **)v108;
  v59 = *(const struct CODEVIEW_INFORMATION_1 **)v114;
  v108 = *(unsigned int **)v114;
  if ( (*((_DWORD *)v5 + 93) & 0x100) == 0 )
  {
    v119 = 0;
    v120 = 0;
  }
  LOBYTE(v103) = 0;
  v60 = HIDWORD(v109);
  v61 = v55;
  v62 = v105;
  v56 = Microsoft::Windows::Performance::CCvDDCache::Add(
          (Microsoft::Windows::Performance::CCvDDCache *)Src,
          (const unsigned __int16 *)v105,
          v111,
          v61,
          v57,
          (const unsigned int *)v58,
          v59,
          v54,
          HIDWORD(v109),
          (struct EMBEDDED_PDB_INFORMATION *)&v119,
          SBYTE1(v103),
          (const unsigned __int16 *)v115,
          (bool *)&v103);
  if ( v56 < 0 )
  {
LABEL_129:
    v35 = v56;
    goto LABEL_130;
  }
  if ( (_BYTE)v103 )
  {
    v91 = (struct CODEVIEW_INFORMATION_1 **)v62;
    v63 = v109;
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddFileVersionEvent(
      v5,
      v3,
      v109,
      v60,
      v54,
      (const unsigned __int16 *)v115,
      (const unsigned __int16 *)v91,
      (struct XPerfCore::CFileMapping *)hFile);
  }
  else
  {
    v63 = v109;
  }
  XPerfCore::CFileMapping::~CFileMapping((XPerfCore::CFileMapping *)hFile);
LABEL_140:
  if ( a2 == 4 )
  {
    v64 = v110;
    v140 = __PAIR64__(HIDWORD(v109), v110);
    v141 = __PAIR64__(v54, v63);
  }
  else
  {
    if ( a2 != 8 )
      return 2147549183LL;
    v64 = v110;
    v140 = v110;
    v141 = HIDWORD(v109);
    v142 = v63;
    v143 = v54;
  }
  HIDWORD(v103) = v64;
  v65 = -1;
  do
    ++v65;
  while ( *((_WORD *)v115 + v65) );
  v130 = *(_OWORD *)&v3->Header.Size;
  v131 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
  v132 = *(_OWORD *)&v3->InstanceId;
  v133 = *(_OWORD *)v3->ParentGuid.Data4;
  v135 = HIDWORD(*(_QWORD *)&v3->MofLength);
  *(_OWORD *)&v131.m256i_u64[1] = ImageIdGuid;
  DWORD1(v130) = 0x20000;
  HIDWORD(v130) = v63;
  *((_QWORD *)&v133 + 1) = &v140;
  v134 = (_DWORD)v115 + 2 + 2 * v65 - (v66 + 528);
  result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
             *((_QWORD *)v5 + 2),
             &v130,
             0,
             0);
  if ( (int)result < 0 )
    return result;
  v67 = 0;
  v115 = 0;
  v68 = 0;
  LODWORD(v105) = 0;
  for ( i = v104; v68 < i; LODWORD(v105) = v68 )
  {
    v70 = v68;
    v71 = *((_DWORD *)v118 + v68);
    Size = v71;
    if ( v71 >= 4 )
    {
      if ( v71 > 0x628 )
        return 2147549183LL;
      v72 = (_DWORD *)((char *)v113 + 1576 * v70);
      Src = v72;
      if ( *v72 )
      {
        switch ( *v72 )
        {
          case 1:
            v73 = 33;
            break;
          case 2:
            v73 = 34;
            break;
          case 3:
            v73 = 37;
            break;
          case 0x3031424E:
            v73 = 35;
            break;
          case 0x53445352:
            v73 = 36;
            break;
          default:
            return 1;
        }
      }
      else
      {
        v73 = 32;
      }
      LOBYTE(v103) = v73;
      if ( (_DWORD)v119 )
      {
        if ( v73 == 36 )
        {
          v74 = -1;
          do
            ++v74;
          while ( *((_BYTE *)v72 + v74 + 24) );
          if ( v74 <= 7 || (v75 = _stricmp((const char *)v72 + v74 + 17, ".ni.pdb"), v72 = Src, v75) )
          {
            v67 = v72;
            v115 = v72;
          }
        }
      }
      if ( a2 == 4 )
      {
        memcpy_0((char *)&v140 + 4, v72, Size);
        v140 = __PAIR64__(v63, HIDWORD(v103));
        v76 = Size + 4;
      }
      else
      {
        if ( a2 != 8 )
          return 2147549183LL;
        memcpy_0(&v141, v72, Size);
        v140 = v110;
        LODWORD(v141) = v63;
        v76 = Size + 8;
      }
      v130 = *(_OWORD *)&v3->Header.Size;
      v131 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
      v132 = *(_OWORD *)&v3->InstanceId;
      v133 = *(_OWORD *)v3->ParentGuid.Data4;
      v135 = HIDWORD(*(_QWORD *)&v3->MofLength);
      *(_OWORD *)&v131.m256i_u64[1] = ImageIdGuid;
      DWORD1(v130) = (unsigned __int8)v103 | 0x20000;
      HIDWORD(v130) = v63;
      *((_QWORD *)&v133 + 1) = &v140;
      v134 = v76;
      result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                 *((_QWORD *)v5 + 2),
                 &v130,
                 0,
                 0);
      if ( (int)result < 0 )
        return result;
      i = v104;
    }
    v68 = (_DWORD)v105 + 1;
  }
  v77 = 0;
  LODWORD(v105) = 0;
  if ( i )
  {
    v78 = a2;
    v79 = v104;
    do
    {
      if ( v78 == 4 )
      {
        v140 = __PAIR64__(v63, HIDWORD(v103));
      }
      else
      {
        if ( v78 != 8 )
          return 2147549183LL;
        v140 = v110;
        LODWORD(v141) = v63;
      }
      if ( v108[2 * v77] )
      {
        HIDWORD(v141) = v108[2 * v77];
        v142 = v108[2 * v77 + 1];
        *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
        *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
        *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
        *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
        *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
        *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(_OWORD *)&String2[12] = ImageIdGuid;
        *(_DWORD *)&String2[2] = 131110;
        *(_DWORD *)&String2[6] = v63;
        *(_QWORD *)&String2[36] = &v140;
        *(_DWORD *)&String2[40] = 20;
        result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   String2,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
        v78 = a2;
        v77 = (unsigned int)v105;
        v79 = v104;
      }
      LODWORD(v105) = ++v77;
    }
    while ( v77 < v79 );
  }
  if ( (_DWORD)v119 )
  {
    pguid = 0;
    if ( v67 )
    {
      try
      {
        Src = v67 + 1;
        v121 = (union _CVDD *)(v67 + 6);
        EmbeddedPdb = Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
                        v5,
                        (char *)v67 + 24,
                        (const struct _GUID *)(v67 + 1),
                        v67[5],
                        (DWORD *)&v119);
      }
      catch ( std::bad_alloc )
      {
        return 2147942414LL;
      }
      LODWORD(v105) = EmbeddedPdb;
      if ( EmbeddedPdb < 0 )
      {
        LODWORD(v102) = v115[5];
        LODWORD(MappedAsImage) = *((unsigned __int8 *)v67 + 19);
        v100[0] = *((unsigned __int8 *)v67 + 18);
        LODWORD(v98) = *((unsigned __int8 *)v67 + 17);
        LODWORD(v96) = *((unsigned __int8 *)v67 + 16);
        LODWORD(v95) = *((unsigned __int8 *)v67 + 15);
        LODWORD(v94) = *((unsigned __int8 *)v67 + 14);
        LODWORD(v93) = *((unsigned __int8 *)v67 + 13);
        LODWORD(v92) = *((unsigned __int8 *)v67 + 12);
        LODWORD(v90) = *((unsigned __int16 *)v67 + 5);
        LODWORD(v89) = *((unsigned __int16 *)v67 + 4);
        LODWORD(v88) = *(_DWORD *)Src;
        v81 = v125;
        (**((void (***)(char *, const wchar_t *, ...))v5 + 47))(
          (char *)v125 + 376,
          L"CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d",
          (unsigned int)v105,
          v121,
          v88,
          v89,
          v90,
          v92,
          v93,
          v94,
          v95,
          v96,
          v98,
          *(_QWORD *)v100,
          MappedAsImage,
          v102);
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v81, v126);
        return 1;
      }
      v82 = v67[5];
      p_pguid = (unsigned int *)Src;
      goto LABEL_194;
    }
    if ( CoCreateGuid(&pguid) >= 0 )
    {
      v82 = 1;
      p_pguid = (unsigned int *)&pguid;
LABEL_194:
      v84 = a2;
      if ( a2 == 4 )
      {
        v140 = __PAIR64__(v63, HIDWORD(v103));
LABEL_198:
        HIDWORD(v141) = v120;
        v142 = *p_pguid;
        v143 = p_pguid[1];
        *(_QWORD *)v144 = *((_QWORD *)p_pguid + 1);
        v145 = v82;
        *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
        *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
        *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
        *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
        *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
        *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(_OWORD *)&String2[12] = ImageIdGuid;
        *(_DWORD *)&String2[2] = 65575;
        *(_DWORD *)&String2[6] = v63;
        *(_QWORD *)&String2[36] = &v140;
        wcscpy(&String2[40], L"$");
        result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   String2,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
        goto LABEL_201;
      }
      if ( a2 == 8 )
      {
        v140 = v110;
        LODWORD(v141) = v63;
        goto LABEL_198;
      }
      return 2147549183LL;
    }
    return 1;
  }
  v84 = a2;
LABEL_201:
  if ( !BYTE1(v103) )
    return 0;
  if ( v84 == 4 )
  {
    v140 = __PAIR64__(v63, HIDWORD(v103));
  }
  else
  {
    if ( v84 != 8 )
      return 2147549183LL;
    v140 = v110;
    LODWORD(v141) = v63;
    v13 = 12;
  }
  *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
  *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
  *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
  *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
  *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
  *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
  *(_OWORD *)&String2[12] = ImageIdGuid;
  *(_DWORD *)&String2[2] = 65576;
  *(_DWORD *)&String2[6] = v63;
  *(_QWORD *)&String2[36] = &v140;
  *(_DWORD *)&String2[40] = v13;
  v85 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
          *((_QWORD *)v5 + 2),
          String2,
          0,
          0);
  if ( v85 < 0 )
    return (unsigned int)v85;
  return v6;
}

```

## disassembly

```asm
0x180016698  mov     [rsp+arg_8], edx
0x18001669c  mov     r11, rsp
0x18001669f  push    rbx
0x1800166a0  push    rsi
0x1800166a1  push    rdi
0x1800166a2  push    r12
0x1800166a4  push    r13
0x1800166a6  push    r14
0x1800166a8  push    r15
0x1800166aa  sub     rsp, 8D0h
0x1800166b1  mov     qword ptr [r11-7A0h], 0FFFFFFFFFFFFFFFEh
0x1800166bc  mov     rax, cs:__security_cookie
0x1800166c3  xor     rax, rsp
0x1800166c6  mov     [rsp+908h+var_48], rax
0x1800166ce  mov     r12, r8
0x1800166d1  mov     [rsp+908h+var_7B0], r8
0x1800166d9  mov     r13d, edx
0x1800166dc  mov     rsi, rcx
0x1800166df  mov     [rsp+908h+var_7B8], rcx
0x1800166e7  mov     [rsp+908h+var_7A8], rcx
0x1800166ef  mov     qword ptr [rsp+908h+pguid.Data1], r8
0x1800166f7  xor     ebx, ebx
0x1800166f9  mov     r8d, ebx
0x1800166fc  mov     [r11-850h], rbx
0x180016703  mov     edx, ebx
0x180016705  mov     [r11-848h], rbx
0x18001670c  mov     r14d, ebx
0x18001670f  mov     [r11-840h], rbx
0x180016716  mov     edi, ebx
0x180016718  mov     [r11-838h], rbx
0x18001671f  mov     rcx, [r12+48h]
0x180016724  mov     r10d, [r12+50h]
0x180016729  movzx   r9d, word ptr [r12+6]
0x18001672f  test    r9d, r9d
0x180016732  jz      loc_180017E99
0x180016738  sub     r9d, 1
0x18001673c  jz      loc_18001680D
0x180016742  sub     r9d, 1
0x180016746  jz      short loc_180016752
0x180016748  cmp     r9d, 1
0x18001674c  jnz     loc_180017E99
0x180016752  cmp     dword ptr [rsi+20h], 0Bh
0x180016756  jb      loc_1800167F7
0x18001675c  cmp     r13d, 4
0x180016760  jz      short loc_1800167CB
0x180016762  mov     r15d, 8
0x180016768  cmp     r13d, r15d
0x18001676b  jnz     loc_180017E99
0x180016771  cmp     r10d, 40h ; '@'
0x180016775  jnb     short loc_180016781
0x180016777  mov     eax, 8007000Dh
0x18001677c  jmp     loc_180016880
0x180016781  mov     eax, [rcx+8]
0x180016784  mov     [rsp+908h+var_84C], eax
0x18001678b  lea     rdi, [rcx+38h]
0x18001678f  mov     r14d, [rcx+14h]
0x180016793  mov     [rsp+908h+var_840], r14d
0x18001679b  mov     eax, [rcx+18h]
0x18001679e  mov     [rsp+908h+var_83C], eax
0x1800167a5  mov     rdx, [rcx]
0x1800167a8  mov     r8d, [rcx+10h]
0x1800167ac  mov     [rsp+908h+String1], rdi
0x1800167b4  mov     [rsp+908h+var_848], rdx
0x1800167bc  mov     [rsp+908h+var_850], r8d
0x1800167c4  mov     eax, ebx
0x1800167c6  jmp     loc_180016880
0x1800167cb  cmp     r10d, 30h ; '0'
0x1800167cf  jb      short loc_180016845
0x1800167d1  lea     rdi, [rcx+2Ch]
0x1800167d5  mov     eax, [rcx+4]
0x1800167d8  mov     [rsp+908h+var_84C], eax
0x1800167df  mov     r14d, [rcx+0Ch]
0x1800167e3  mov     [rsp+908h+var_840], r14d
0x1800167eb  mov     eax, [rcx+10h]
0x1800167ee  mov     [rsp+908h+var_83C], eax
0x1800167f5  jmp     short loc_18001685A
0x1800167f7  cmp     r13d, 4
0x1800167fb  jnz     loc_180016762
0x180016801  cmp     r10d, 2Ch ; ','
0x180016805  jb      short loc_180016845
0x180016807  lea     rdi, [rcx+28h]
0x18001680b  jmp     short loc_1800167D5
0x18001680d  cmp     r13d, 4
0x180016811  jz      short loc_18001683F
0x180016813  mov     r15d, 8
0x180016819  cmp     r13d, r15d
0x18001681c  jnz     loc_180017E99
0x180016822  cmp     r10d, 18h
0x180016826  jb      loc_180016777
0x18001682c  mov     eax, [rcx+8]
0x18001682f  mov     [rsp+908h+var_84C], eax
0x180016836  lea     rdi, [rcx+14h]
0x18001683a  jmp     loc_1800167A5
0x18001683f  cmp     r10d, 10h
0x180016843  jnb     short loc_18001684C
0x180016845  mov     eax, 8007000Dh
0x18001684a  jmp     short loc_18001687A
0x18001684c  mov     eax, [rcx+4]
0x18001684f  mov     [rsp+908h+var_84C], eax
0x180016856  lea     rdi, [rcx+0Ch]
0x18001685a  mov     r8d, [rcx+8]
0x18001685e  mov     edx, [rcx]
0x180016860  mov     [rsp+908h+var_850], r8d
0x180016868  mov     [rsp+908h+var_848], rdx
0x180016870  mov     [rsp+908h+String1], rdi
0x180016878  mov     eax, ebx
0x18001687a  mov     r15d, 8
0x180016880  test    eax, eax
0x180016882  js      loc_180017E99
0x180016888  mov     rax, [r12+10h]
0x18001688d  cmp     [rsi+28h], rax
0x180016891  jnz     short loc_1800168A3
0x180016893  cmp     [rsi+30h], r8d
0x180016897  jnz     short loc_1800168A3
0x180016899  cmp     [rsi+38h], rdx
0x18001689d  jz      loc_180017EC1
0x1800168a3  lea     rax, [rsi+40h]
0x1800168a7  cmp     [rax+70h], bl
0x1800168aa  jnz     short loc_1800168B8
0x1800168ac  mov     rcx, rax; this
0x1800168af  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x1800168b4  lea     rax, [rsi+40h]
0x1800168b8  lea     r8, [rsi+0C0h]
0x1800168bf  mov     rdx, rdi
0x1800168c2  mov     rcx, rax
0x1800168c5  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800168ca  test    al, al
0x1800168cc  jnz     loc_1800169A0
0x1800168d2  mov     rax, [rsi+0B8h]
0x1800168d9  test    rax, rax
0x1800168dc  jz      short loc_1800168F8
0x1800168de  lea     r8, [rsi+0C0h]
0x1800168e5  mov     rdx, rdi
0x1800168e8  mov     rcx, rax
0x1800168eb  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800168f0  test    al, al
0x1800168f2  jnz     loc_1800169A0
0x1800168f8  test    rdi, rdi
0x1800168fb  jz      short loc_18001696E
0x1800168fd  mov     r14, rbx
0x180016900  cmp     [rsi+0C9h], bl
0x180016906  jnz     short loc_180016940
0x180016908  mov     edx, 5Ch ; '\'; Ch
0x18001690d  mov     rcx, rdi; Str
0x180016910  call    cs:__imp_wcsrchr
0x180016917  nop     dword ptr [rax+rax+00h]
0x18001691c  test    rax, rax
0x18001691f  jz      short loc_180016940
0x180016921  sub     rax, rdi
0x180016924  sar     rax, 1
0x180016927  inc     rax
0x18001692a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001692e  inc     rcx
0x180016931  cmp     [rdi+rcx*2], bx
0x180016935  jnz     short loc_18001692E
0x180016937  cmp     rax, rcx
0x18001693a  sbb     r14, r14
0x18001693d  and     r14, rax
0x180016940  lea     rcx, [rsi+178h]
0x180016947  mov     rax, [rcx]
0x18001694a  lea     r8, [rdi+r14*2]
0x18001694e  lea     rdx, aUnableToParseI; "Unable to parse image path: %s"
0x180016955  mov     rax, [rax]
0x180016958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001695d  test    al, al
0x18001695f  jz      short loc_180016996
0x180016961  mov     rdx, r12; struct _EVENT_TRACE *
0x180016964  mov     rcx, rsi; this
0x180016967  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x18001696c  jmp     short loc_180016996
0x18001696e  lea     rcx, [rsi+178h]
0x180016975  mov     rax, [rcx]
0x180016978  lea     rdx, aNullPathInImag; "NULL path in image path."
0x18001697f  mov     rax, [rax]
0x180016982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016987  test    al, al
0x180016989  jz      short loc_180016996
0x18001698b  mov     rdx, r12; struct _EVENT_TRACE *
0x18001698e  mov     rcx, rsi; this
0x180016991  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180016996  mov     eax, 1
0x18001699b  jmp     loc_180017EC8
0x1800169a0  lea     rax, [rsi+0C9h]
0x1800169a7  mov     [rsp+908h+var_800], rax
0x1800169af  mov     r8, [rsi+0C0h]
0x1800169b6  cmp     [rax], bl
0x1800169b8  jnz     short loc_180016A23
0x1800169ba  mov     rdi, rbx
0x1800169bd  mov     edx, 5Ch ; '\'; Ch
0x1800169c2  mov     rcx, r8; Str
0x1800169c5  call    cs:__imp_wcsrchr
0x1800169cc  nop     dword ptr [rax+rax+00h]
0x1800169d1  test    rax, rax
0x1800169d4  jz      short loc_1800169FD
0x1800169d6  mov     rdx, [rsi+0C0h]
0x1800169dd  sub     rax, rdx
0x1800169e0  sar     rax, 1
0x1800169e3  lea     rcx, [rax+1]
0x1800169e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800169eb  inc     rax
0x1800169ee  cmp     [rdx+rax*2], bx
0x1800169f2  jnz     short loc_1800169EB
0x1800169f4  cmp     rcx, rax
0x1800169f7  sbb     rdi, rdi
0x1800169fa  and     rdi, rcx
0x1800169fd  lea     rcx, [rsi+178h]
0x180016a04  mov     rdx, [rcx]
0x180016a07  mov     rax, [rsi+0C0h]
0x180016a0e  lea     r8, [rax+rdi*2]
0x180016a12  mov     rax, [rdx]
0x180016a15  lea     rdx, aSFailure; "%s failure: "
0x180016a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a21  jmp     short loc_180016A3F
0x180016a23  lea     rcx, [rsi+178h]
0x180016a2a  mov     rax, [rcx]
0x180016a2d  mov     r9, rdi
0x180016a30  lea     rdx, aSSFailure; "%s [%s] failure: "
0x180016a37  mov     rax, [rax]
0x180016a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a3f  lea     rax, [rsi+0C9h]
0x180016a46  mov     [rsp+908h+var_7E0], rax
0x180016a4e  xor     edx, edx; Val
0x180016a50  mov     r8d, 640h; Size
0x180016a56  lea     rcx, [rsp+908h+var_6F8]; void *
0x180016a5e  call    memset_0
0x180016a63  cmp     r13d, 4
0x180016a67  jz      short loc_180016A7C
0x180016a69  cmp     r13d, r15d
0x180016a6c  jnz     loc_180017D8D
0x180016a72  lea     rax, [rsp+908h+var_6E0]
0x180016a7a  jmp     short loc_180016A84
0x180016a7c  lea     rax, [rsp+908h+var_6E8]
0x180016a84  mov     [rsp+908h+var_818], rax
0x180016a8c  mov     [rsp+908h+var_874], ebx
0x180016a93  mov     [rsp+908h+var_828], rbx
0x180016a9b  mov     [rsp+908h+var_858], rbx
0x180016aa3  mov     [rsp+908h+var_820], rbx
0x180016aab  xorps   xmm0, xmm0
0x180016aae  xor     ecx, ecx
0x180016ab0  movups  [rsp+908h+var_7F8], xmm0
0x180016ab8  mov     [rsp+908h+var_7E8], rcx
0x180016ac0  mov     [rsp+908h+var_877], bl
0x180016ac7  lea     rcx, [rsi+0D0h]; this
0x180016ace  mov     [rsp+908h+Src], rcx
0x180016ad6  mov     [rsp+908h+var_8B0], rax; unsigned __int16 *
0x180016adb  lea     rax, [rsp+908h+var_877]
0x180016ae3  mov     [rsp+908h+var_8B8], rax; bool *
0x180016ae8  lea     rax, [rsp+908h+var_7F8]
0x180016af0  mov     [rsp+908h+var_8C0], rax; struct EMBEDDED_PDB_INFORMATION *
0x180016af5  lea     rax, [rsp+908h+var_84C]
0x180016afd  mov     [rsp+908h+var_8C8], rax; unsigned int *
0x180016b02  lea     rax, [rsp+908h+var_83C]
0x180016b0a  mov     [rsp+908h+var_8D0], rax; unsigned int *
0x180016b0f  lea     rax, [rsp+908h+var_820]
0x180016b17  mov     [rsp+908h+var_8D8], rax; struct CODEVIEW_INFORMATION_1 **
0x180016b1c  lea     rax, [rsp+908h+var_858]
0x180016b24  mov     [rsp+908h+var_8E0], rax; unsigned int **
0x180016b29  lea     rax, [rsp+908h+var_828]
0x180016b31  mov     [rsp+908h+var_8E8], rax; unsigned int
0x180016b36  lea     r9, [rsp+908h+var_874]; unsigned int *
0x180016b3e  mov     r8d, r14d; unsigned int
0x180016b41  lea     rdi, [rsi+0C0h]
0x180016b48  mov     rdx, [rdi]; unsigned __int16 *
0x180016b4b  call    ?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z; Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)
0x180016b50  mov     r8d, eax
0x180016b53  test    eax, eax
0x180016b55  jns     loc_180017510
0x180016b5b  cmp     eax, 80070490h
0x180016b60  jnz     loc_1800174B2
0x180016b66  mov     eax, [rsi+170h]
0x180016b6c  mov     [rsp+908h+var_870], eax
0x180016b73  mov     [rsp+908h+var_874], eax
0x180016b7a  lea     rax, [rsi+158h]
0x180016b81  mov     [rsp+908h+var_808], rax
0x180016b89  cmp     [rax], rbx
0x180016b8c  jz      loc_180017D8D
0x180016b92  lea     rax, [rsi+160h]
0x180016b99  mov     [rsp+908h+var_858], rax
0x180016ba1  cmp     [rax], rbx
0x180016ba4  jz      loc_180017D8D
0x180016baa  lea     rax, [rsi+168h]
0x180016bb1  mov     [rsp+908h+var_820], rax
0x180016bb9  cmp     [rax], rbx
0x180016bbc  jz      loc_180017D8D
0x180016bc2  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x180016bc7  mov     [rsp+908h+var_878], al; struct XPerfCore::IErrorMessage *
0x180016bce  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180016bd6  movdqu  xmmword ptr [rsp+908h+hFile], xmm0
0x180016bdf  mov     [rsp+908h+var_7C8], rbx
0x180016be7  mov     [rsp+908h+var_7C0], rbx
0x180016bef  mov     r13, [rdi]
0x180016bf2  mov     [rsp+908h+var_868], r13
0x180016bfa  mov     [rsp+908h+var_828], r13
0x180016c02  lea     r9, [rsi+178h]; struct XPerfCore::IErrorMessage *
0x180016c09  mov     r8b, al; bool
0x180016c0c  mov     rdx, r13; unsigned __int16 *
0x180016c0f  lea     rcx, [rsp+908h+hFile]; this
0x180016c17  call    ?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z; XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)
0x180016c1c  mov     r14d, eax
0x180016c1f  test    eax, eax
  ... truncated ...
```
