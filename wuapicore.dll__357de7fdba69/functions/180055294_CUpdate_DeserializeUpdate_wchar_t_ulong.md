# CUpdate::DeserializeUpdate(wchar_t *,ulong)

- ea: `0x180055294`
- end: `0x180056566`
- name: `?DeserializeUpdate@CUpdate@@QEAAJPEA_WK@Z`
- size: `4818`
- prototype: `__int64 __fastcall(CUpdate *__hidden this, BSTR bstr, unsigned int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180057148`

## callees

- `0x18000588c`
- `0x180006ac4`
- `0x180039ccc`
- `0x180039e50`
- `0x180052d44`
- `0x18005335c`
- `0x1800537b4`
- `0x180053afc`
- `0x180053e14`
- `0x180054074`
- `0x18005499c`
- `0x180054e84`
- `0x180055294`
- `0x180056b3c`
- `0x1800588b8`
- `0x18005ddf8`
- `0x18005e748`
- `0x1800602e4`
- `0x180062328`
- `0x180081a38`
- `0x180081adc`
- `0x180082720`
- `0x18008428c`
- `0x1800842cc`
- `0x180084398`
- `0x1800847e4`
- `0x180084a8c`
- `0x180084b94`
- `0x18008505c`
- `0x18008512c`
- `0x180090bc8`
- `0x180091568`
- `0x180091a94`
- `0x18009ae75`
- `0x18009b050`
- `0x18009b0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800560cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800560cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005532b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005532b`
- `OLEAUT32!__imp_SysFreeString` at `0x180056068`
- `OLEAUT32!__imp_SysFreeString` at `0x180056102`
- `OLEAUT32!__imp_SysFreeString` at `0x180056181`
- `OLEAUT32!__imp_SysFreeString` at `0x180056249`
- `OLEAUT32!__imp_SysFreeString` at `0x18005628b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800562f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800562ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800563b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800563bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005643a`
- `OLEAUT32!__imp_SysFreeString` at `0x180056482`
- `OLEAUT32!__imp_SysFreeString` at `0x180056068`
- `OLEAUT32!__imp_SysFreeString` at `0x180056102`
- `OLEAUT32!__imp_SysFreeString` at `0x180056181`
- `OLEAUT32!__imp_SysFreeString` at `0x180056249`
- `OLEAUT32!__imp_SysFreeString` at `0x18005628b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800562f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800562ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800563b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800563bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005643a`
- `OLEAUT32!__imp_SysFreeString` at `0x180056482`
- `OLEAUT32!__imp_SysStringLen` at `0x180056475`
- `OLEAUT32!__imp_SysStringLen` at `0x180056475`
- `OLEAUT32!__imp_VariantClear` at `0x1800559a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800559a9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180055428`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800554df`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180055428`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800554df`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180055375`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180055375`

## string_xrefs

- `0x18005534c`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800553a3`: `Deserializing update from serialized BSTR.`
- `0x1800564d7`: `installed`
- `0x1800564de`: `installable`
- `0x180056508`: `Deserialized %ws update %ws, UpdateID = {%ws}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdate::DeserializeUpdate(CUpdate *this, BSTR bstr, unsigned int a3)
{
  int v5; // eax
  INT v6; // eax
  signed int inited; // r15d
  __int64 v8; // rdx
  __int64 v9; // rdx
  UINT v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdi
  __int64 v18; // rbx
  unsigned int v19; // r8d
  unsigned int v20; // esi
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  CUpdate *v27; // rcx
  CUpdate *v28; // rcx
  CUpdate *v29; // rcx
  CUpdate *v30; // rcx
  CUpdate *v31; // rcx
  CUpdate *v32; // rcx
  CUpdate *v33; // rcx
  __int64 v34; // r9
  int v35; // eax
  __int16 v36; // ax
  int v37; // eax
  _DWORD *v38; // rdi
  unsigned int v39; // ebx
  void *v40; // rax
  OLECHAR *v41; // rdi
  unsigned int v42; // r8d
  unsigned int v43; // r8d
  unsigned int v44; // r8d
  bool v45; // dl
  struct TraceLoggingCorrelationVector *v46; // rbx
  void *v47; // rcx
  bool v48; // dl
  struct TraceLoggingCorrelationVector *v49; // rbx
  unsigned int v50; // r8d
  void *v51; // rcx
  unsigned int v52; // r8d
  unsigned int v53; // r8d
  unsigned int v54; // r8d
  unsigned int v55; // r14d
  void *v56; // rbx
  unsigned int v57; // r8d
  OLECHAR *v58; // rdi
  int v59; // eax
  __int64 v60; // rdx
  OLECHAR *v61; // rcx
  void *v62; // rbx
  unsigned int v63; // r8d
  OLECHAR *v64; // r14
  unsigned int v65; // r8d
  __int64 v66; // rdx
  BSTR *v67; // rbx
  unsigned int v68; // r8d
  __int64 updated; // rax
  const wchar_t *v70; // rcx
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  BSTR v74; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v75; // [rsp+58h] [rbp-A8h]
  void *v76; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v77[112]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v78; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v79; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v80; // [rsp+E8h] [rbp-18h] BYREF
  void *lpMem; // [rsp+F0h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+F8h] [rbp-8h] BYREF
  BSTR v83[2]; // [rsp+100h] [rbp+0h] BYREF
  void **v84; // [rsp+110h] [rbp+10h] BYREF
  __int64 v85; // [rsp+118h] [rbp+18h]
  __int64 v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  __m128i si128; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+148h] [rbp+48h]
  __int64 v90; // [rsp+150h] [rbp+50h]
  int v91; // [rsp+168h] [rbp+68h]
  struct _SYSTEMTIME SystemTime; // [rsp+170h] [rbp+70h] BYREF
  char Str[144]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t Buffer[24]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v75 = a3;
  memset_0(&v84, 0, 0x60u);
  v84 = &CSusArrayList<unsigned char,CSusArrayListItemOpNoop<unsigned char>>::`vftable';
  v85 = 0;
  v86 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
  v90 = 0;
  CSerializationHelper::Clear((CSerializationHelper *)&v84);
  v80 = 0;
  v79 = 0;
  bstrString = 0;
  SystemTime = 0;
  v78 = 0;
  GetSystemTime(&SystemTime);
  v5 = SystemTimeToString(Buffer);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBC1,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v5,
      v72);
  v6 = SystemTimeToVariantTime(&SystemTime, (DOUBLE *)this + 50);
  if ( v6 != 1 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBC3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      v6 != 1 ? (const char *)0x80240FFFLL : 0,
      v72);
  WUTrace(0, 0, 0x10000, 5, 0, L"Deserializing update from serialized BSTR.");
  inited = CSerializationHelper::InitDeserializeFromString((CSerializationHelper *)&v84);
  if ( inited < 0 )
  {
    v8 = 3015;
LABEL_82:
    v34 = (unsigned int)inited;
LABEL_251:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v34,
      v73);
    goto LABEL_255;
  }
  LODWORD(lpMem) = 0;
  if ( !v89 )
  {
    inited = -2147418113;
    v9 = 1097;
LABEL_22:
    v12 = (unsigned int)inited;
    goto LABEL_23;
  }
  if ( v87 != 1 )
  {
    inited = -2147418113;
    v9 = 1098;
    goto LABEL_22;
  }
  if ( v91 != 1 )
  {
    inited = -2147418113;
    v9 = 1099;
    goto LABEL_22;
  }
  v10 = SysStringByteLen(bstr);
  if ( v10 )
  {
    v11 = CSusArrayList<unsigned char,CSusArrayListItemOpNoop<unsigned char>>::Add(&v84, bstr, v10);
    inited = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v9 = 1105;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SerializationUtil.cpp",
        (const char *)v12,
        v73);
      v8 = 3016;
      goto LABEL_82;
    }
  }
  v13 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &lpMem, 4u);
  inited = v13;
  if ( v13 < 0 )
  {
    v12 = (unsigned int)v13;
    v9 = 1108;
    goto LABEL_23;
  }
  v14 = v85;
  v15 = HIDWORD(v86);
  v16 = (unsigned int)v86;
  v85 = 0;
  v86 = 0;
  v17 = v15 - 4;
  v18 = (unsigned int)lpMem;
  inited = v15 - 4 != (unsigned int)lpMem ? 0x8000FFFF : 0;
  if ( v14 )
    CSusArrayList<unsigned char,CSusArrayListItemOpNoop<unsigned char>>::Attach(&v84, v14, v15, v16);
  if ( v18 != v17 )
  {
    v9 = 1122;
    goto LABEL_22;
  }
  SysStringByteLen(bstr);
  WUTrace(0, 0, 0x10000, v75, 0, L"Byte length of the input buffer for deserialization: %d");
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &v80, 4u);
  if ( inited < 0 )
  {
    v8 = 3023;
    goto LABEL_82;
  }
  v20 = v80;
  if ( v80 <= 7 )
  {
    inited = -2145124264;
    v8 = 3025;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 42, v19);
  if ( inited < 0 )
  {
    v8 = 3026;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 43, v21);
  if ( inited < 0 )
  {
    v8 = 3027;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 44, v22);
  if ( inited < 0 )
  {
    v8 = 3028;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 45, v23);
  if ( inited < 0 )
  {
    v8 = 3029;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 46, v24);
  if ( inited < 0 )
  {
    v8 = 3030;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 47, v25);
  if ( inited < 0 )
  {
    v8 = 3031;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 48, v26);
  if ( inited < 0 )
  {
    v8 = 3032;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 392, 8u);
  if ( inited < 0 )
  {
    v8 = 3033;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 408, 4u);
  if ( inited < 0 )
  {
    v8 = 3034;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 412, 4u);
  if ( inited < 0 )
  {
    v8 = 3035;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 416, 4u);
  if ( inited < 0 )
  {
    v8 = 3036;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 420, 4u);
  if ( inited < 0 )
  {
    v8 = 3037;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 424, 4u);
  if ( inited < 0 )
  {
    v8 = 3038;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 428, 4u);
  if ( inited < 0 )
  {
    v8 = 3039;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 432, 8u);
  if ( inited < 0 )
  {
    v8 = 3040;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 440, 8u);
  if ( inited < 0 )
  {
    v8 = 3041;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 448, 8u);
  if ( inited < 0 )
  {
    v8 = 3042;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v27,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 65));
  if ( inited < 0 )
  {
    v8 = 3048;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v28,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 66));
  if ( inited < 0 )
  {
    v8 = 3049;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v29,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 67));
  if ( inited < 0 )
  {
    v8 = 3050;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v30,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 68));
  if ( inited < 0 )
  {
    v8 = 3051;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v31,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 69));
  if ( inited < 0 )
  {
    v8 = 3052;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v32,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 70));
  if ( inited < 0 )
  {
    v8 = 3053;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeStringCollectionUtil(
             v33,
             (struct CSerializationHelper *)&v84,
             *((struct CStringCollection **)this + 71));
  if ( inited < 0 )
  {
    v8 = 3054;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeCategoryCollection(this, (struct CSerializationHelper *)&v84);
  if ( inited < 0 )
  {
    v8 = 3055;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeUpdateIdentity(this, (struct CSerializationHelper *)&v84);
  if ( inited < 0 )
  {
    v8 = 3056;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeInstallationBehavior(this, (struct CSerializationHelper *)&v84);
  if ( inited < 0 )
  {
    v8 = 3057;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeUninstallationBehavior(this, (struct CSerializationHelper *)&v84);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3058;
    goto LABEL_251;
  }
  inited = CUpdate::DeserializeImageInformation(this, (struct CSerializationHelper *)&v84);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3059;
    goto LABEL_251;
  }
  v35 = CUpdateDownloadContentCollection::InitializeFromSerializer(
          *((CUpdateDownloadContentCollection **)this + 64),
          (struct CSerializationHelper *)&v84,
          v20);
  inited = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x948,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v35,
      v73);
    v8 = 3061;
    goto LABEL_82;
  }
  inited = CUpdate::DeserializeBundledUpdateCollection(this, (struct CSerializationHelper *)&v84);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3063;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 576, 4u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3064;
    goto LABEL_251;
  }
  VariantClear((VARIANTARG *)((char *)this + 584));
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &v79, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3068;
    goto LABEL_251;
  }
  v36 = v79;
  *((_WORD *)this + 292) = v79;
  if ( v36 == 7 )
  {
    inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &bstrString, 8u);
    v34 = (unsigned int)inited;
    if ( inited < 0 )
    {
      v8 = 3075;
      goto LABEL_251;
    }
    *((_QWORD *)this + 74) = bstrString;
  }
  else if ( v36 )
  {
    inited = -2145124297;
    v8 = 3071;
    goto LABEL_82;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 608, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3079;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 610, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3080;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 612, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3081;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 614, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3082;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 616, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3083;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 618, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3084;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 620, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3085;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 622, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3086;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 624, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3087;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 626, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3088;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 628, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3089;
    goto LABEL_251;
  }
  inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 630, 2u);
  v34 = (unsigned int)inited;
  if ( inited < 0 )
  {
    v8 = 3090;
    goto LABEL_251;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 632, 2u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3091;
LABEL_250:
    v34 = (unsigned int)v37;
    goto LABEL_251;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 634, 2u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3092;
    goto LABEL_250;
  }
  v37 = CUpdate::DeserializeWindowsDriverInfo(this, (struct CSerializationHelper *)&v84);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3093;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 656, 0x10u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3094;
    goto LABEL_250;
  }
  v38 = (_DWORD *)((char *)this + 680);
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 680, 4u);
  inited = v37;
  v39 = 0;
  if ( v37 < 0 )
  {
    v8 = 3095;
    goto LABEL_250;
  }
  if ( *v38 )
  {
    v40 = SafeSusAllocArray((unsigned int)*v38, 0x10u);
    *((_QWORD *)this + 84) = v40;
    if ( !v40 )
    {
      inited = -2147024882;
      v34 = 2147942414LL;
      v8 = 3099;
      goto LABEL_251;
    }
    if ( *v38 )
    {
      while ( 1 )
      {
        inited = CSerializationHelper::RawDeserializeData(
                   (CSerializationHelper *)&v84,
                   (void *)(*((_QWORD *)this + 84) + 16LL * v39),
                   0x10u);
        if ( inited < 0 )
          break;
        if ( ++v39 >= *v38 )
          goto LABEL_142;
      }
      v34 = (unsigned int)inited;
      v8 = 3103;
      goto LABEL_251;
    }
  }
LABEL_142:
  inited = CUpdate::DeserializeMatchingUpdateInternal(this, (struct CSerializationHelper *)&v84);
  v41 = 0;
  if ( inited < 0 )
  {
    CUpdate::ClearInner(this);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD22,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)inited,
      v73);
    v34 = (unsigned int)inited;
    v8 = 3107;
    goto LABEL_251;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 920, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3108;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 924, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3109;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 928, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3110;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 932, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3111;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 936, 0x10u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3112;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 119, v42);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3113;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 960, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3114;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 976, 4u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3115;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 123, v43);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3116;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 124, v44);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3117;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 1000, 1u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3118;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, Str, 0x81u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3120;
    goto LABEL_250;
  }
  v46 = TraceLoggingCorrelationVector::Set(Str, v45);
  v47 = (void *)*((_QWORD *)this + 130);
  if ( v47 )
    operator delete(v47);
  *((_QWORD *)this + 130) = v46;
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, Str, 0x81u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3123;
    goto LABEL_250;
  }
  v49 = TraceLoggingCorrelationVector::Set(Str, v48);
  v51 = (void *)*((_QWORD *)this + 131);
  if ( v51 )
    operator delete(v51);
  *((_QWORD *)this + 131) = v49;
  v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 126, v50);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3126;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 1016, 8u);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3127;
    goto LABEL_250;
  }
  v37 = CSerializationHelper::RawDeserializeBinaryBSTR((CSerializationHelper *)&v84, (wchar_t **)this + 128, v52);
  inited = v37;
  if ( v37 < 0 )
  {
    v8 = 3128;
    goto LABEL_250;
  }
  if ( v20 >= 0xA )
  {
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 400, 8u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3132;
      goto LABEL_250;
    }
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 1056, 4u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3138;
      goto LABEL_250;
    }
    SysFreeString(*((BSTR *)this + 134));
    *((_QWORD *)this + 134) = 0;
    v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 134, v54);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3140;
      goto LABEL_250;
    }
  }
  if ( v20 >= 0xB )
  {
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &v78, 4u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3146;
      goto LABEL_250;
    }
    if ( this != (CUpdate *)-1096LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1104));
    CSusArrayList<CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::_tagMapEntry,CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::CMapEntryOps>::RemoveArraySection(
      (char *)this + 1144,
      0,
      0xFFFFFFFFLL,
      1);
    v55 = 0;
    if ( v78 )
    {
      while ( 1 )
      {
        v56 = 0;
        lpMem = 0;
        v83[0] = 0;
        SysFreeString(0);
        bstrString = 0;
        inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, &bstrString, v57);
        v58 = bstrString;
        if ( inited < 0 )
          break;
        inited = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, v83, 8u);
        if ( inited < 0 )
        {
          v60 = 3161;
          goto LABEL_205;
        }
        inited = DuplicateString<wchar_t *,wchar_t *>(v58, &lpMem);
        v56 = lpMem;
        if ( inited < 0 )
        {
          v60 = 3164;
          goto LABEL_205;
        }
        v74 = (BSTR)lpMem;
        inited = CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::Add(
                   (char *)this + 1144,
                   &v74,
                   v83);
        if ( inited < 0 )
        {
          v60 = 3165;
          goto LABEL_205;
        }
        SysFreeString(v58);
        ++v55;
        v41 = 0;
        if ( v55 >= v78 )
          goto LABEL_199;
      }
      v60 = 3160;
LABEL_205:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v60,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)inited,
        v73);
      if ( v56 )
        SusFree(v56);
      v61 = v58;
      goto LABEL_231;
    }
LABEL_199:
    v59 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, &v78, 4u);
    inited = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC63,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)v59,
        v73);
      goto LABEL_232;
    }
    CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::RemoveArraySection(
      (char *)this + 1176,
      0,
      0xFFFFFFFFLL,
      1);
    LODWORD(lpMem) = 0;
    if ( v78 )
    {
      while ( 1 )
      {
        v83[0] = 0;
        bstrString = 0;
        v62 = 0;
        v76 = 0;
        SysFreeString(0);
        v74 = 0;
        inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, &v74, v63);
        v64 = v74;
        if ( inited < 0 )
          break;
        inited = DuplicateString<wchar_t *,wchar_t *>(v74, &bstrString);
        if ( inited < 0 )
        {
          v66 = 3184;
          goto LABEL_226;
        }
        SysFreeString(0);
        inited = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, v83, v65);
        v41 = v83[0];
        if ( inited < 0 )
        {
          v66 = 3187;
          goto LABEL_226;
        }
        inited = DuplicateString<wchar_t *,wchar_t *>(v83[0], &v76);
        v62 = v76;
        if ( inited < 0 )
        {
          v66 = 3188;
          goto LABEL_226;
        }
        v74 = (BSTR)v76;
        v83[0] = bstrString;
        inited = CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::Add(
                   (char *)this + 1176,
                   v83,
                   &v74);
        if ( inited < 0 )
        {
          v66 = 3191;
          goto LABEL_226;
        }
        SysFreeString(v41);
        SysFreeString(v64);
        LODWORD(lpMem) = (_DWORD)lpMem + 1;
        v41 = 0;
        if ( (unsigned int)lpMem >= v78 )
          goto LABEL_215;
      }
      v66 = 3183;
LABEL_226:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v66,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)inited,
        v73);
      if ( v62 )
        SusFree(v62);
      if ( bstrString )
        SusFree(bstrString);
      SysFreeString(v41);
      v61 = v64;
LABEL_231:
      SysFreeString(v61);
LABEL_232:
      if ( this != (CUpdate *)-1096LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1104));
      goto LABEL_255;
    }
LABEL_215:
    if ( this != (CUpdate *)-1096LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1104));
    v20 = v80;
  }
  if ( v20 >= 0xC )
  {
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 636, 2u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3202;
      goto LABEL_250;
    }
  }
  if ( v20 >= 0xD )
  {
    v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 121, v53);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3208;
      goto LABEL_250;
    }
  }
  if ( v20 >= 0xE )
  {
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 638, 2u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3214;
      goto LABEL_250;
    }
  }
  if ( v20 >= 0x10 )
  {
    v67 = (BSTR *)((char *)this + 1088);
    SysFreeString(*((BSTR *)this + 136));
    *((_QWORD *)this + 136) = 0;
    v37 = CSerializationHelper::RawDeserializeBSTRString((CSerializationHelper *)&v84, (wchar_t **)this + 136, v68);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3224;
      goto LABEL_250;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_DeserializationSessionData_58587042>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_DeserializationSessionData_58587042>::GetImpl'::`2'::impl)
      && (!*v67 || !SysStringLen(*v67)) )
    {
      SysFreeString(*v67);
      *v67 = 0;
    }
  }
  if ( v20 >= 0x11 )
  {
    v37 = CSerializationHelper::RawDeserializeData((CSerializationHelper *)&v84, (char *)this + 640, 2u);
    inited = v37;
    if ( v37 < 0 )
    {
      v8 = 3240;
      goto LABEL_250;
    }
  }
  updated = Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v77, (CUpdate *)((char *)this + 688));
  v70 = L"installable";
  if ( *((_WORD *)this + 312) == 0xFFFF )
    v70 = L"installed";
  WUTrace(0, 0, 0x10000, v75, 0, L"Deserialized %ws update %ws, UpdateID = {%ws}", v70, *((_QWORD *)this + 47), updated);
  inited = 0;
LABEL_255:
  CSerializationHelper::~CSerializationHelper((CSerializationHelper *)&v84);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180055294  mov     [rsp-8+arg_18], rbx
0x180055299  push    rbp
0x18005529a  push    rsi
0x18005529b  push    rdi
0x18005529c  push    r12
0x18005529e  push    r13
0x1800552a0  push    r14
0x1800552a2  push    r15
0x1800552a4  lea     rbp, [rsp-150h]
0x1800552ac  sub     rsp, 250h
0x1800552b3  mov     rax, cs:__security_cookie
0x1800552ba  xor     rax, rsp
0x1800552bd  mov     [rbp+180h+var_40], rax
0x1800552c4  mov     [rsp+280h+var_228], r8d
0x1800552c9  mov     rsi, rdx
0x1800552cc  mov     r13, rcx
0x1800552cf  xor     edx, edx; Val
0x1800552d1  lea     r8d, [rdx+60h]; Size
0x1800552d5  lea     rcx, [rbp+180h+var_170]; void *
0x1800552d9  call    memset_0
0x1800552de  lea     rax, ??_7?$CSusArrayList@EV?$CSusArrayListItemOpNoop@E@@@@6B@; const CSusArrayList<uchar,CSusArrayListItemOpNoop<uchar>>::`vftable'
0x1800552e5  mov     [rbp+180h+var_170], rax
0x1800552e9  xor     ebx, ebx
0x1800552eb  mov     [rbp+180h+var_168], rbx
0x1800552ef  mov     [rbp+180h+var_160], rbx
0x1800552f3  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x1800552fb  movdqa  [rbp+180h+var_150], xmm0
0x180055300  mov     [rbp+180h+var_130], rbx
0x180055304  lea     rcx, [rbp+180h+var_170]; this
0x180055308  call    ?Clear@CSerializationHelper@@QEAAJXZ; CSerializationHelper::Clear(void)
0x18005530d  nop
0x18005530e  mov     [rbp+180h+var_198], ebx
0x180055311  mov     [rbp+180h+var_19C], bx
0x180055315  xorps   xmm0, xmm0
0x180055318  movsd   [rbp+180h+bstrString], xmm0
0x18005531d  xorps   xmm1, xmm1
0x180055320  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm1
0x180055324  mov     [rbp+180h+var_1A0], ebx
0x180055327  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x18005532b  call    cs:__imp_GetSystemTime
0x180055331  lea     r9d, [rbx+6]
0x180055335  lea     r8, [rbp+180h+SystemTime]
0x180055339  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180055340  call    SystemTimeToString
0x180055345  mov     rcx, [rbp+188h]; this
0x18005534c  lea     r12, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180055353  test    eax, eax
0x180055355  jns     short loc_180055367
0x180055357  mov     r9d, eax; char *
0x18005535a  mov     r8, r12; unsigned int
0x18005535d  mov     edx, 0BC1h; void *
0x180055362  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180055367  lea     r14, [r13+190h]
0x18005536e  mov     rdx, r14; pvtime
0x180055371  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180055375  call    cs:__imp_SystemTimeToVariantTime
0x18005537b  lea     ecx, [rax-1]
0x18005537e  neg     ecx
0x180055380  sbb     r9d, r9d
0x180055383  and     r9d, 80240FFFh; char *
0x18005538a  mov     rcx, [rbp+188h]; this
0x180055391  cmp     eax, 1
0x180055394  jz      short loc_1800553A3
0x180055396  mov     r8, r12; unsigned int
0x180055399  mov     edx, 0BC3h; void *
0x18005539e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800553a3  lea     rax, aDeserializingU; "Deserializing update from serialized BS"...
0x1800553aa  mov     [rsp+280h+var_258], rax
0x1800553af  mov     qword ptr [rsp+280h+var_260], rbx; int
0x1800553b4  xor     edx, edx
0x1800553b6  xor     ecx, ecx
0x1800553b8  lea     r9d, [rdx+5]
0x1800553bc  mov     r8d, 10000h
0x1800553c2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800553c7  lea     rcx, [rbp+180h+var_170]; this
0x1800553cb  call    ?InitDeserializeFromString@CSerializationHelper@@QEAAJXZ; CSerializationHelper::InitDeserializeFromString(void)
0x1800553d0  mov     r15d, eax
0x1800553d3  test    eax, eax
0x1800553d5  jns     short loc_1800553E1
0x1800553d7  mov     edx, 0BC7h
0x1800553dc  jmp     loc_1800558D8
0x1800553e1  mov     dword ptr [rbp+180h+lpMem], ebx
0x1800553e4  cmp     [rbp+180h+var_138], ebx
0x1800553e7  jnz     short loc_1800553F9
0x1800553e9  mov     r15d, 8000FFFFh
0x1800553ef  mov     edx, 449h
0x1800553f4  jmp     loc_1800554BC
0x1800553f9  cmp     [rbp+180h+var_158], 1
0x1800553fd  jz      short loc_18005540F
0x1800553ff  mov     r15d, 8000FFFFh
0x180055405  mov     edx, 44Ah
0x18005540a  jmp     loc_1800554BC
0x18005540f  cmp     [rbp+180h+var_118], 1
0x180055413  jz      short loc_180055425
0x180055415  mov     r15d, 8000FFFFh
0x18005541b  mov     edx, 44Bh
0x180055420  jmp     loc_1800554BC
0x180055425  mov     rcx, rsi; bstr
0x180055428  call    cs:__imp_SysStringByteLen
0x18005542e  test    eax, eax
0x180055430  jz      short loc_180055452
0x180055432  mov     r8d, eax
0x180055435  mov     rdx, rsi
0x180055438  lea     rcx, [rbp+180h+var_170]
0x18005543c  call    ?Add@?$CSusArrayList@EV?$CSusArrayListItemOpNoop@E@@@@QEAAJPEBEK@Z; CSusArrayList<uchar,CSusArrayListItemOpNoop<uchar>>::Add(uchar const *,ulong)
0x180055441  mov     r15d, eax
0x180055444  test    eax, eax
0x180055446  jns     short loc_180055452
0x180055448  mov     r9d, eax
0x18005544b  mov     edx, 451h
0x180055450  jmp     short loc_1800554BF
0x180055452  mov     r8d, 4; unsigned int
0x180055458  lea     rdx, [rbp+180h+lpMem]; void *
0x18005545c  lea     rcx, [rbp+180h+var_170]; this
0x180055460  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055465  mov     r15d, eax
0x180055468  test    eax, eax
0x18005546a  jns     short loc_180055476
0x18005546c  mov     r9d, eax
0x18005546f  mov     edx, 454h
0x180055474  jmp     short loc_1800554BF
0x180055476  mov     rdx, [rbp+180h+var_168]
0x18005547a  mov     r8d, dword ptr [rbp+180h+var_160+4]
0x18005547e  mov     r9d, dword ptr [rbp+180h+var_160]
0x180055482  mov     [rbp+180h+var_168], rbx
0x180055486  mov     [rbp+180h+var_160], rbx
0x18005548a  lea     rdi, [r8-4]
0x18005548e  mov     ebx, dword ptr [rbp+180h+lpMem]
0x180055491  mov     eax, ebx
0x180055493  sub     rax, rdi
0x180055496  neg     rax
0x180055499  sbb     eax, eax
0x18005549b  mov     r15d, 8000FFFFh
0x1800554a1  and     r15d, eax
0x1800554a4  test    rdx, rdx
0x1800554a7  jz      short loc_1800554B2
0x1800554a9  lea     rcx, [rbp+180h+var_170]
0x1800554ad  call    ?Attach@?$CSusArrayList@EV?$CSusArrayListItemOpNoop@E@@@@QEAAXPEAEKK@Z; CSusArrayList<uchar,CSusArrayListItemOpNoop<uchar>>::Attach(uchar *,ulong,ulong)
0x1800554b2  cmp     rbx, rdi
0x1800554b5  jz      short loc_1800554DC
0x1800554b7  mov     edx, 462h; void *
0x1800554bc  mov     r9d, r15d; char *
0x1800554bf  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800554c6  mov     rcx, [rbp+188h]; this
0x1800554cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800554d2  mov     edx, 0BC8h
0x1800554d7  jmp     loc_1800558D8
0x1800554dc  mov     rcx, rsi; bstr
0x1800554df  call    cs:__imp_SysStringByteLen
0x1800554e5  mov     dword ptr [rsp+280h+var_250], eax
0x1800554e9  lea     rax, aByteLengthOfTh; "Byte length of the input buffer for des"...
0x1800554f0  mov     [rsp+280h+var_258], rax
0x1800554f5  xor     edi, edi
0x1800554f7  mov     qword ptr [rsp+280h+var_260], rdi; int
0x1800554fc  mov     r9d, [rsp+280h+var_228]
0x180055501  xor     edx, edx
0x180055503  xor     ecx, ecx
0x180055505  mov     r8d, 10000h
0x18005550b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180055510  lea     ebx, [rdi+4]
0x180055513  mov     r8d, ebx; unsigned int
0x180055516  lea     rdx, [rbp+180h+var_198]; void *
0x18005551a  lea     rcx, [rbp+180h+var_170]; this
0x18005551e  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055523  mov     r15d, eax
0x180055526  test    eax, eax
0x180055528  jns     short loc_180055534
0x18005552a  mov     edx, 0BCFh
0x18005552f  jmp     loc_1800558D8
0x180055534  mov     esi, [rbp+180h+var_198]
0x180055537  mov     eax, 7
0x18005553c  cmp     esi, eax
0x18005553e  ja      short loc_180055550
0x180055540  mov     r15d, 80240058h
0x180055546  mov     edx, 0BD1h
0x18005554b  jmp     loc_1800558D8
0x180055550  lea     rdx, [r13+150h]; wchar_t **
0x180055557  lea     rcx, [rbp+180h+var_170]; this
0x18005555b  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x180055560  mov     r15d, eax
0x180055563  test    eax, eax
0x180055565  jns     short loc_180055571
0x180055567  mov     edx, 0BD2h
0x18005556c  jmp     loc_1800558D8
0x180055571  lea     rdx, [r13+158h]; wchar_t **
0x180055578  lea     rcx, [rbp+180h+var_170]; this
0x18005557c  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x180055581  mov     r15d, eax
0x180055584  test    eax, eax
0x180055586  jns     short loc_180055592
0x180055588  mov     edx, 0BD3h
0x18005558d  jmp     loc_1800558D8
0x180055592  lea     rdx, [r13+160h]; wchar_t **
0x180055599  lea     rcx, [rbp+180h+var_170]; this
0x18005559d  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x1800555a2  mov     r15d, eax
0x1800555a5  test    eax, eax
0x1800555a7  jns     short loc_1800555B3
0x1800555a9  mov     edx, 0BD4h
0x1800555ae  jmp     loc_1800558D8
0x1800555b3  lea     rdx, [r13+168h]; wchar_t **
0x1800555ba  lea     rcx, [rbp+180h+var_170]; this
0x1800555be  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x1800555c3  mov     r15d, eax
0x1800555c6  test    eax, eax
0x1800555c8  jns     short loc_1800555D4
0x1800555ca  mov     edx, 0BD5h
0x1800555cf  jmp     loc_1800558D8
0x1800555d4  lea     rdx, [r13+170h]; wchar_t **
0x1800555db  lea     rcx, [rbp+180h+var_170]; this
0x1800555df  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x1800555e4  mov     r15d, eax
0x1800555e7  test    eax, eax
0x1800555e9  jns     short loc_1800555F5
0x1800555eb  mov     edx, 0BD6h
0x1800555f0  jmp     loc_1800558D8
0x1800555f5  lea     rdx, [r13+178h]; wchar_t **
0x1800555fc  lea     rcx, [rbp+180h+var_170]; this
0x180055600  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x180055605  mov     r15d, eax
0x180055608  test    eax, eax
0x18005560a  jns     short loc_180055616
0x18005560c  mov     edx, 0BD7h
0x180055611  jmp     loc_1800558D8
0x180055616  lea     rdx, [r13+180h]; wchar_t **
0x18005561d  lea     rcx, [rbp+180h+var_170]; this
0x180055621  call    ?RawDeserializeBSTRString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeBSTRString(wchar_t * *,ulong)
0x180055626  mov     r15d, eax
0x180055629  test    eax, eax
0x18005562b  jns     short loc_180055637
0x18005562d  mov     edx, 0BD8h
0x180055632  jmp     loc_1800558D8
0x180055637  lea     rdx, [r13+188h]; void *
0x18005563e  mov     r8d, 8; unsigned int
0x180055644  lea     rcx, [rbp+180h+var_170]; this
0x180055648  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x18005564d  mov     r15d, eax
0x180055650  test    eax, eax
0x180055652  jns     short loc_18005565E
0x180055654  mov     edx, 0BD9h
0x180055659  jmp     loc_1800558D8
0x18005565e  lea     rdx, [r13+198h]; void *
0x180055665  mov     r8d, ebx; unsigned int
0x180055668  lea     rcx, [rbp+180h+var_170]; this
0x18005566c  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055671  mov     r15d, eax
0x180055674  test    eax, eax
0x180055676  jns     short loc_180055682
0x180055678  mov     edx, 0BDAh
0x18005567d  jmp     loc_1800558D8
0x180055682  lea     rdx, [r13+19Ch]; void *
0x180055689  mov     r8d, ebx; unsigned int
0x18005568c  lea     rcx, [rbp+180h+var_170]; this
0x180055690  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055695  mov     r15d, eax
0x180055698  test    eax, eax
0x18005569a  jns     short loc_1800556A6
0x18005569c  mov     edx, 0BDBh
0x1800556a1  jmp     loc_1800558D8
0x1800556a6  lea     rdx, [r13+1A0h]; void *
0x1800556ad  mov     r8d, ebx; unsigned int
0x1800556b0  lea     rcx, [rbp+180h+var_170]; this
0x1800556b4  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x1800556b9  mov     r15d, eax
0x1800556bc  test    eax, eax
0x1800556be  jns     short loc_1800556CA
0x1800556c0  mov     edx, 0BDCh
0x1800556c5  jmp     loc_1800558D8
0x1800556ca  lea     rdx, [r13+1A4h]; void *
0x1800556d1  mov     r8d, ebx; unsigned int
0x1800556d4  lea     rcx, [rbp+180h+var_170]; this
0x1800556d8  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x1800556dd  mov     r15d, eax
0x1800556e0  test    eax, eax
0x1800556e2  jns     short loc_1800556EE
0x1800556e4  mov     edx, 0BDDh
0x1800556e9  jmp     loc_1800558D8
0x1800556ee  lea     rdx, [r13+1A8h]; void *
0x1800556f5  mov     r8d, ebx; unsigned int
0x1800556f8  lea     rcx, [rbp+180h+var_170]; this
0x1800556fc  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055701  mov     r15d, eax
0x180055704  test    eax, eax
0x180055706  jns     short loc_180055712
0x180055708  mov     edx, 0BDEh
0x18005570d  jmp     loc_1800558D8
0x180055712  lea     rdx, [r13+1ACh]; void *
0x180055719  mov     r8d, ebx; unsigned int
0x18005571c  lea     rcx, [rbp+180h+var_170]; this
0x180055720  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180055725  mov     r15d, eax
0x180055728  test    eax, eax
0x18005572a  jns     short loc_180055736
0x18005572c  mov     edx, 0BDFh
0x180055731  jmp     loc_1800558D8
0x180055736  lea     rdx, [r13+1B0h]; void *
0x18005573d  mov     r8d, 8; unsigned int
0x180055743  lea     rcx, [rbp+180h+var_170]; this
0x180055747  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x18005574c  mov     r15d, eax
  ... truncated ...
```
