# HyperVStorage::ReadFromStream(ISequentialStream *,int,ushort const *)

- ea: `0x14002fa48`
- end: `0x1400303db`
- name: `?ReadFromStream@HyperVStorage@@QEAAJPEAUISequentialStream@@HPEBG@Z`
- size: `2451`
- prototype: `int(HyperVStorage *__hidden this, struct ISequentialStream *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140243e40`
- `0x140243f80`

## callees

- `0x140012364`
- `0x140017040`
- `0x140018d54`
- `0x14001bce0`
- `0x14002fa20`
- `0x14002fa48`
- `0x1400303e4`
- `0x1400304ac`
- `0x1400309a4`
- `0x1400309d0`
- `0x140030a20`
- `0x140030cd8`
- `0x140031064`
- `0x140031720`
- `0x1400336f0`
- `0x140033a7c`
- `0x1400371c8`
- `0x14003c078`
- `0x14003c574`
- `0x14003e3d8`
- `0x14005f0a4`
- `0x1400e07d0`
- `0x1400e0bf4`
- `0x1400fecc0`
- `0x140113e24`
- `0x1401332f0`
- `0x1401363ac`
- `0x140136414`
- `0x1402739cc`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003013d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003013d`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140030086`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140030086`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030006`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030046`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030101`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030006`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030046`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140030101`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x14002faf9`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x14002faf9`
- `XmlLite!CreateXmlReader` at `0x14002faac`
- `XmlLite!CreateXmlReader` at `0x14002faac`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall HyperVStorage::ReadFromStream(HyperVStorage *this, IUnknown *a2, int a3, unsigned __int16 *a4)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  __int128 v13; // xmm0
  __int64 v14; // rcx
  HyperVStorageOperation *v15; // r13
  char *v16; // r14
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HyperVStorage *v21; // rcx
  int v22; // edi
  HyperVStorage *v23; // rcx
  wchar_t **v24; // rax
  const WCHAR *v25; // rcx
  bool v26; // zf
  unsigned int FixedTypeDataSpace; // esi
  int RequiredSpaceForData; // r13d
  HyperVStorageKeyTableEntry *v29; // r12
  const char *Name; // rax
  __int64 v31; // r8
  const wchar_t *v32; // rcx
  double *v33; // rax
  const wchar_t *v34; // rcx
  const wchar_t *v35; // rcx
  const wchar_t *v36; // rcx
  wchar_t **v37; // rdx
  int IsDebugTraceEnabled; // esi
  unsigned __int64 v39; // rdx
  unsigned __int8 v40; // cl
  bool IsEnabled; // al
  char v42; // di
  __int128 *v43; // r9
  LPCWCH *v44; // r8
  wchar_t **v45; // rax
  unsigned __int16 *v46; // r12
  unsigned int v47; // edi
  LPCWSTR pwszBaseUri; // [rsp+20h] [rbp-188h]
  int ppInput; // [rsp+28h] [rbp-180h]
  int v51; // [rsp+30h] [rbp-178h]
  unsigned int v52; // [rsp+40h] [rbp-168h] BYREF
  int v53; // [rsp+44h] [rbp-164h] BYREF
  int v54; // [rsp+48h] [rbp-160h]
  HyperVStorageOperation *v55; // [rsp+50h] [rbp-158h] BYREF
  HyperVStorage *v56; // [rsp+58h] [rbp-150h]
  unsigned __int16 *v57; // [rsp+60h] [rbp-148h]
  unsigned __int16 *v58; // [rsp+68h] [rbp-140h]
  struct _GUID v59; // [rsp+70h] [rbp-138h] BYREF
  _BYTE v60[8]; // [rsp+80h] [rbp-128h] BYREF
  int v61[2]; // [rsp+88h] [rbp-120h] BYREF
  HyperVStorage *v62; // [rsp+90h] [rbp-118h] BYREF
  void *ppvObject; // [rsp+98h] [rbp-110h] BYREF
  wchar_t *String[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-F8h]
  unsigned __int64 v66; // [rsp+B8h] [rbp-F0h]
  int v67; // [rsp+C0h] [rbp-E8h] BYREF
  int v68; // [rsp+C4h] [rbp-E4h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-E0h] BYREF
  IXmlReaderInput *v70; // [rsp+D0h] [rbp-D8h] BYREF
  __int128 v71; // [rsp+D8h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-C0h]
  __int64 v73; // [rsp+F8h] [rbp-B0h] BYREF
  double v74; // [rsp+100h] [rbp-A8h] BYREF
  __int128 v75; // [rsp+108h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+118h] [rbp-90h]
  LPCWCH lpWideCharStr[2]; // [rsp+120h] [rbp-88h] BYREF
  int cchWideChar[4]; // [rsp+130h] [rbp-78h]
  _OWORD v79[2]; // [rsp+140h] [rbp-68h] BYREF

  v57 = a4;
  v56 = this;
  v58 = a4;
  v54 = 0;
  ppvObject = 0;
  v8 = CreateXmlReader(&riid, &ppvObject, 0);
  try
  {
    if ( v8 < 0 )
      HvsThrowHResultError(v8);
    v70 = 0;
    v9 = CreateXmlReaderInputWithEncodingName(a2, 0, L"UTF-16", 1, &HyperVStorage::CFG_XML_NAMESPACE_URI, &v70);
    if ( v9 < 0 )
      HvsThrowHResultError(v9);
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
            ppvObject,
            1,
            (a3 != 0) + 1LL);
    if ( v10 < 0 )
      HvsThrowHResultError(v10);
    v11 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v70);
    if ( v11 < 0 )
      HvsThrowHResultError(v11);
    v12 = 1;
    v53 = 1;
    v13 = 0;
    *(_OWORD *)String = 0;
    v65 = 0;
    v66 = 0;
    *(double *)&v13 = std::wstring::_Construct_empty(String);
    v68 = 0;
    v73 = 0;
    v69 = 0;
    v74 = *(double *)&v13;
    v67 = 0;
    v52 = 0;
    v79[0] = v13;
    v79[1] = 0;
    *(double *)&v13 = std::wstring::_Construct_empty(v79);
    v75 = v13;
    v76 = 0;
    *(double *)&v13 = std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(&v75);
    *(_OWORD *)lpWideCharStr = v13;
    *(_OWORD *)cchWideChar = 0;
    *(double *)&v13 = std::wstring::_Construct_empty(lpWideCharStr);
    v71 = v13;
    si128 = 0;
    std::string::_Construct_empty(&v71);
    LODWORD(v55) = 1;
    v62 = this;
    v14 = *((_QWORD *)this + 24);
    if ( v14 == *((_QWORD *)this + 25) )
    {
      std::vector<HyperVStorageOperation>::_Emplace_reallocate<HyperVStorage *,enum HyperVStorageOperationType>(
        (char *)this + 184,
        *((_QWORD *)this + 24),
        &v62,
        &v55);
    }
    else
    {
      HyperVStorageOperation::HyperVStorageOperation(
        v14,
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
        1);
      *((_QWORD *)this + 24) += 88LL;
    }
    v15 = (HyperVStorageOperation *)(*((_QWORD *)this + 24) - 88LL);
    v55 = v15;
    v16 = (char *)this + 248;
    if ( a4 )
    {
      *(_QWORD *)v61 = 0;
      if ( !(unsigned int)HyperVStorage::GetOrCreateNode((_DWORD)this, (_DWORD)a4, (_DWORD)v15, (unsigned int)v61, 0) )
        HvsThrowHResultError(-2147467259);
      v16 = *(char **)(*(_QWORD *)v61 + 40LL);
    }
    try
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v18 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v68);
          if ( v18 )
            goto LABEL_113;
          if ( v68 != 1 )
            break;
          v62 = 0;
          v20 = (*(__int64 (__fastcall **)(void *, HyperVStorage **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v62,
                  0);
          if ( v20 < 0 )
            HvsThrowHResultError(v20);
          std::wstring::assign(lpWideCharStr, v62);
          HyperVStorage::ReadAttributes(v21, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v53);
          v22 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
          HyperVStorage::ReadAttributes(v23, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v53);
          v65 = 0;
          v24 = String;
          if ( v66 > 7 )
            v24 = (wchar_t **)String[0];
          *(_WORD *)v24 = 0;
          v25 = (const WCHAR *)lpWideCharStr;
          if ( *(_QWORD *)&cchWideChar[2] > 7u )
            v25 = lpWideCharStr[0];
          HvsWideToMultiByte(v25, cchWideChar[0]);
          LOBYTE(v51) = 0;
          v16 = *(char **)(*(_QWORD *)(*(__int64 (__fastcall **)(HyperVStorage *, _BYTE *, char *, __int128 *, HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)this + 168LL))(
                                        this,
                                        v60,
                                        v16,
                                        &v71,
                                        v15,
                                        0,
                                        v51)
                         + 40LL);
          v26 = v22 == 0;
          v12 = v53;
          if ( !v26 )
          {
LABEL_35:
            if ( v65 )
            {
              if ( v12 == 1 )
                v12 = 6;
            }
            else if ( v12 - 6 > 1 )
            {
              goto LABEL_77;
            }
            if ( v12 == 6 )
            {
              FixedTypeDataSpace = 2 * v65;
              v52 = 2 * v65;
            }
            else if ( v12 == 7 )
            {
              if ( v65 )
              {
                HyperVStorage::ConvertArrayDataFromString(v65, String, &v75, &v52);
                FixedTypeDataSpace = v52;
              }
              else
              {
                FixedTypeDataSpace = 0;
                v52 = 0;
              }
            }
            else
            {
              FixedTypeDataSpace = HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(v12);
              v52 = FixedTypeDataSpace;
            }
            RequiredSpaceForData = HyperVStorageKeyTableEntry::GetRequiredSpaceForData(
                                     v12,
                                     FixedTypeDataSpace >= 0x800,
                                     FixedTypeDataSpace);
            v29 = (HyperVStorageKeyTableEntry *)*((_QWORD *)v16 + 4);
            if ( !v29 || *((_DWORD *)v16 + 6) )
              HvsThrowHResultError(-2147024809);
            Name = HyperVStorageKeyTableEntry::GetName((HyperVStorageKeyTableEntry *)v16);
            v31 = -1;
            do
              ++v31;
            while ( Name[v31] );
            std::string::_Assign<char>(&v71, Name);
            HyperVStorageKeyTableEntry::RemoveChild(v29, (struct HyperVStorageKeyTableEntry *)v16);
            HyperVStorageOperation::RemoveModifiedNode(v55, (struct HyperVStorageKeyTableEntry *)v16);
            (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8, v16);
            LOBYTE(v51) = 0;
            ppInput = RequiredSpaceForData;
            v15 = v55;
            *(_QWORD *)v61 = *(_QWORD *)(*(__int64 (__fastcall **)(HyperVStorage *, struct _GUID *, HyperVStorageKeyTableEntry *, __int128 *, HyperVStorageOperation *, int, int))(*(_QWORD *)this + 168LL))(
                                          this,
                                          &v59,
                                          v29,
                                          &v71,
                                          v55,
                                          ppInput,
                                          v51);
            v16 = *(char **)(*(_QWORD *)v61 + 40LL);
            switch ( v12 )
            {
              case 3u:
                v32 = (const wchar_t *)String;
                if ( v66 > 7 )
                  v32 = String[0];
                v69 = _wtoi64(v32);
                v33 = (double *)&v69;
                break;
              case 4u:
                v34 = (const wchar_t *)String;
                if ( v66 > 7 )
                  v34 = String[0];
                v73 = _wtoi64(v34);
                v33 = (double *)&v73;
                break;
              case 5u:
                v35 = (const wchar_t *)String;
                if ( v66 > 7 )
                  v35 = String[0];
                v74 = _wtof(v35);
                v33 = &v74;
                break;
              case 6u:
                v33 = (double *)String;
                if ( v66 > 7 )
                  v33 = (double *)String[0];
                break;
              case 7u:
                v33 = (double *)v75;
                break;
              case 8u:
                v36 = (const wchar_t *)String;
                if ( v66 > 7 )
                  v36 = String[0];
                v69 = _wtoi64(v36);
                v67 = 0;
                v37 = String;
                if ( v66 > 7 )
                  v37 = (wchar_t **)String[0];
                if ( !(unsigned int)_o__wcsicmp(L"true", v37) || v69 == 1 )
                  v67 = 1;
                v33 = (double *)&v67;
                break;
              default:
                IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x4000u);
                IsEnabled = HyperVStorageTrace::IsEnabled(v40, v39);
                v42 = IsEnabled;
                if ( IsDebugTraceEnabled || IsEnabled )
                {
                  if ( dword_1403DEA14 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 16LL) )
                  {
                    Init_thread_header(&dword_1403DEA14);
                    if ( dword_1403DEA14 == -1 )
                    {
                      byte_1403BC5BC = IsDebugTraceEnabled != 0;
                      byte_1403BC5BD = v42;
                      Init_thread_footer(&dword_1403DEA14);
                    }
                  }
                  v43 = &v71;
                  if ( si128.m128i_i64[1] > 0xFuLL )
                    v43 = (__int128 *)v71;
                  v44 = lpWideCharStr;
                  if ( *(_QWORD *)&cchWideChar[2] > 7u )
                    v44 = (LPCWCH *)lpWideCharStr[0];
                  HvsDebugTraceInternal(0x4000u, (const struct HvsDebugTraceParameters *)&off_1403BC5A8, v44, v43);
                }
                HvsThrowHResultError(-2147024809);
            }
            LODWORD(pwszBaseUri) = FixedTypeDataSpace;
            HyperVStorage::SetNodeValue(
              (int)this,
              (int)v29,
              (int)v61,
              v12,
              (size_t)pwszBaseUri,
              (__int64)v33,
              (__int64)v15);
LABEL_77:
            v16 = (char *)*((_QWORD *)v16 + 4);
            if ( !v16 )
              HvsThrowHResultError(-2147024809);
            v12 = 1;
            v53 = 1;
            v65 = 0;
            v45 = String;
            if ( v66 > 7 )
              v45 = (wchar_t **)String[0];
            *(_WORD *)v45 = 0;
          }
        }
        switch ( v68 )
        {
          case 3:
          case 4:
LABEL_25:
            *(_QWORD *)v61 = 0;
            v19 = (*(__int64 (__fastcall **)(void *, int *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(ppvObject, v61, 0);
            if ( v19 < 0 )
              HvsThrowHResultError(v19);
            std::wstring::append(String, *(_QWORD *)v61);
            break;
          case 13:
            if ( v65 )
              goto LABEL_25;
            break;
          case 15:
            goto LABEL_35;
        }
      }
    }
    catch ( ... )
    {
      HyperVStorageOperation::Undo(v55);
      std::vector<HyperVStorageOperation>::pop_back((char *)v56 + 184);
      throw;
    }
LABEL_113:
    if ( v18 < 0 )
      HvsThrowHResultError(v18);
    if ( si128.m128i_i64[1] > 0xFuLL )
      std::_Deallocate<16>(v71, si128.m128i_i64[1] + 1);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v71) = 0;
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpWideCharStr);
    if ( (_QWORD)v75 )
    {
      std::_Deallocate<16>(v75, v76 - v75);
      v75 = 0;
      v76 = 0;
    }
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v79);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)String);
    if ( v70 )
      ((void (__fastcall *)(IXmlReaderInput *))v70->lpVtbl->Release)(v70);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    v46 = v57;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
  v47 = v54;
  v59 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::ReadFromStream(&v59, a3 != 0, v46, v54);
  return v47;
}

```

## disassembly

```asm
0x14002fa48  mov     [rsp+arg_10], r8d
0x14002fa4d  push    rbx
0x14002fa4e  push    rsi
0x14002fa4f  push    rdi
0x14002fa50  push    r12
0x14002fa52  push    r13
0x14002fa54  push    r14
0x14002fa56  push    r15
0x14002fa58  sub     rsp, 170h
0x14002fa5f  mov     rax, cs:__security_cookie
0x14002fa66  xor     rax, rsp
0x14002fa69  mov     [rsp+1A8h+var_48], rax
0x14002fa71  mov     r12, r9
0x14002fa74  mov     [rsp+1A8h+var_148], r9
0x14002fa79  mov     esi, r8d
0x14002fa7c  mov     rdi, rdx
0x14002fa7f  mov     r15, rcx
0x14002fa82  mov     [rsp+1A8h+var_150], rcx
0x14002fa87  mov     [rsp+1A8h+var_140], r9
0x14002fa8c  xor     ebx, ebx
0x14002fa8e  mov     [rsp+1A8h+var_160], ebx
0x14002fa92  mov     [rsp+1A8h+ppvObject], rbx
0x14002fa9a  xor     r8d, r8d; pMalloc
0x14002fa9d  lea     rdx, [rsp+1A8h+ppvObject]; ppvObject
0x14002faa5  lea     rcx, riid; riid
0x14002faac  call    cs:__imp_CreateXmlReader
0x14002fab3  nop     dword ptr [rax+rax+00h]
0x14002fab8  test    eax, eax
0x14002faba  jns     short loc_14002FAC3
0x14002fabc  mov     ecx, eax; int
0x14002fabe  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fac3  mov     [rsp+1A8h+var_D8], rbx
0x14002facb  lea     rax, [rsp+1A8h+var_D8]
0x14002fad3  mov     [rsp+1A8h+ppInput], rax; ppInput
0x14002fad8  lea     rax, ?CFG_XML_NAMESPACE_URI@HyperVStorage@@1QBGB; ushort const near * const HyperVStorage::CFG_XML_NAMESPACE_URI
0x14002fadf  mov     [rsp+1A8h+pwszBaseUri], rax; pwszBaseUri
0x14002fae4  mov     r14d, 1
0x14002faea  mov     r9d, r14d; fEncodingHint
0x14002faed  lea     r8, pwszEncodingName; "UTF-16"
0x14002faf4  xor     edx, edx; pMalloc
0x14002faf6  mov     rcx, rdi; pInputStream
0x14002faf9  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x14002fb00  nop     dword ptr [rax+rax+00h]
0x14002fb05  test    eax, eax
0x14002fb07  jns     short loc_14002FB10
0x14002fb09  mov     ecx, eax; int
0x14002fb0b  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fb10  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fb18  mov     r9, [rcx]
0x14002fb1b  mov     eax, esi
0x14002fb1d  neg     eax
0x14002fb1f  sbb     r8, r8
0x14002fb22  neg     r8
0x14002fb25  add     r8, r14
0x14002fb28  mov     edx, r14d
0x14002fb2b  mov     rax, [r9+28h]
0x14002fb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fb34  test    eax, eax
0x14002fb36  jns     short loc_14002FB3F
0x14002fb38  mov     ecx, eax; int
0x14002fb3a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fb3f  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fb47  mov     rax, [rcx]
0x14002fb4a  mov     rdx, [rsp+1A8h+var_D8]
0x14002fb52  mov     rax, [rax+18h]
0x14002fb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fb5b  test    eax, eax
0x14002fb5d  jns     short loc_14002FB66
0x14002fb5f  mov     ecx, eax; int
0x14002fb61  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fb66  mov     edi, r14d
0x14002fb69  mov     [rsp+1A8h+var_164], r14d
0x14002fb6e  xorps   xmm0, xmm0
0x14002fb71  movups  xmmword ptr [rsp+1A8h+String], xmm0
0x14002fb79  mov     [rsp+1A8h+var_F8], rbx
0x14002fb81  mov     [rsp+1A8h+var_F0], rbx
0x14002fb89  lea     rcx, [rsp+1A8h+String]
0x14002fb91  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14002fb96  nop
0x14002fb97  mov     [rsp+1A8h+var_E4], ebx
0x14002fb9e  mov     [rsp+1A8h+var_B0], rbx
0x14002fba6  mov     [rsp+1A8h+var_E0], rbx
0x14002fbae  movsd   [rsp+1A8h+var_A8], xmm0
0x14002fbb7  mov     [rsp+1A8h+var_E8], ebx
0x14002fbbe  mov     [rsp+1A8h+var_168], ebx
0x14002fbc2  movups  [rsp+1A8h+var_68], xmm0
0x14002fbca  xorps   xmm1, xmm1
0x14002fbcd  movdqu  [rsp+1A8h+var_58], xmm1
0x14002fbd6  lea     rcx, [rsp+1A8h+var_68]
0x14002fbde  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14002fbe3  nop
0x14002fbe4  xor     eax, eax
0x14002fbe6  movups  [rsp+1A8h+var_A0], xmm0
0x14002fbee  mov     [rsp+1A8h+var_90], rax
0x14002fbf6  lea     rcx, [rsp+1A8h+var_A0]
0x14002fbfe  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14002fc03  nop
0x14002fc04  movups  xmmword ptr [rsp+1A8h+lpWideCharStr], xmm0
0x14002fc0c  movdqu  xmmword ptr [rsp+1A8h+cchWideChar], xmm1
0x14002fc15  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x14002fc1d  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14002fc22  nop
0x14002fc23  movups  [rsp+1A8h+var_D0], xmm0
0x14002fc2b  movdqu  [rsp+1A8h+var_C0], xmm1
0x14002fc34  lea     rcx, [rsp+1A8h+var_D0]
0x14002fc3c  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x14002fc41  nop
0x14002fc42  lea     rsi, [r15+0B8h]
0x14002fc49  mov     dword ptr [rsp+1A8h+var_158], r14d
0x14002fc4e  mov     [rsp+1A8h+var_118], r15
0x14002fc56  mov     rcx, [rsi+8]
0x14002fc5a  cmp     rcx, [rsi+10h]
0x14002fc5e  jz      short loc_14002FC7F
0x14002fc60  mov     rax, r15
0x14002fc63  lea     r8, [r15+8]
0x14002fc67  neg     rax
0x14002fc6a  sbb     rdx, rdx
0x14002fc6d  and     rdx, r8
0x14002fc70  mov     r8d, r14d
0x14002fc73  call    ??0HyperVStorageOperation@@QEAA@PEAVHyperVStorageOperationsInterface@@W4HyperVStorageOperationType@@@Z; HyperVStorageOperation::HyperVStorageOperation(HyperVStorageOperationsInterface *,HyperVStorageOperationType)
0x14002fc78  add     qword ptr [rsi+8], 58h ; 'X'
0x14002fc7d  jmp     short loc_14002FC97
0x14002fc7f  lea     r9, [rsp+1A8h+var_158]
0x14002fc84  lea     r8, [rsp+1A8h+var_118]
0x14002fc8c  mov     rdx, rcx
0x14002fc8f  mov     rcx, rsi
0x14002fc92  call    ??$_Emplace_reallocate@PEAVHyperVStorage@@W4HyperVStorageOperationType@@@?$vector@VHyperVStorageOperation@@V?$allocator@VHyperVStorageOperation@@@std@@@std@@AEAAPEAVHyperVStorageOperation@@QEAV2@$$QEAPEAVHyperVStorage@@$$QEAW4HyperVStorageOperationType@@@Z; std::vector<HyperVStorageOperation>::_Emplace_reallocate<HyperVStorage *,HyperVStorageOperationType>(HyperVStorageOperation * const,HyperVStorage * &&,HyperVStorageOperationType &&)
0x14002fc97  mov     r13, [r15+0C0h]
0x14002fc9e  sub     r13, 58h ; 'X'
0x14002fca2  mov     [rsp+1A8h+var_158], r13
0x14002fca7  lea     r14, [r15+0F8h]
0x14002fcae  test    r12, r12
0x14002fcb1  jz      short loc_14002FCF4
0x14002fcb3  mov     qword ptr [rsp+1A8h+var_120], rbx
0x14002fcbb  mov     byte ptr [rsp+1A8h+var_178], bl
0x14002fcbf  mov     [rsp+1A8h+pwszBaseUri], rbx
0x14002fcc4  lea     r9, [rsp+1A8h+var_120]
0x14002fccc  mov     r8, r13
0x14002fccf  mov     rdx, r12
0x14002fcd2  mov     rcx, r15
0x14002fcd5  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x14002fcda  test    eax, eax
0x14002fcdc  jnz     short loc_14002FCE8
0x14002fcde  mov     ecx, 80004005h; int
0x14002fce3  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fce8  mov     rax, qword ptr [rsp+1A8h+var_120]
0x14002fcf0  mov     r14, [rax+28h]
0x14002fcf4  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fcfc  mov     rax, [rcx]
0x14002fcff  lea     rdx, [rsp+1A8h+var_E4]
0x14002fd07  mov     rax, [rax+30h]
0x14002fd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fd10  test    eax, eax
0x14002fd12  jnz     loc_1400302A5
0x14002fd18  mov     ecx, [rsp+1A8h+var_E4]
0x14002fd1f  sub     ecx, 1
0x14002fd22  jz      short loc_14002FD96
0x14002fd24  sub     ecx, 2
0x14002fd27  jz      short loc_14002FD47
0x14002fd29  sub     ecx, 1
0x14002fd2c  jz      short loc_14002FD47
0x14002fd2e  sub     ecx, 9
0x14002fd31  jz      short loc_14002FD3D
0x14002fd33  cmp     ecx, 2
0x14002fd36  jnz     short loc_14002FCF4
0x14002fd38  jmp     loc_14002FEB2
0x14002fd3d  cmp     [rsp+1A8h+var_F8], rbx
0x14002fd45  jz      short loc_14002FCF4
0x14002fd47  mov     qword ptr [rsp+1A8h+var_120], rbx
0x14002fd4f  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fd57  mov     rax, [rcx]
0x14002fd5a  xor     r8d, r8d
0x14002fd5d  lea     rdx, [rsp+1A8h+var_120]
0x14002fd65  mov     rax, [rax+80h]
0x14002fd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fd71  test    eax, eax
0x14002fd73  jns     short loc_14002FD7C
0x14002fd75  mov     ecx, eax; int
0x14002fd77  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fd7c  mov     rdx, qword ptr [rsp+1A8h+var_120]
0x14002fd84  lea     rcx, [rsp+1A8h+String]
0x14002fd8c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14002fd91  jmp     loc_14002FCF4
0x14002fd96  mov     [rsp+1A8h+var_118], rbx
0x14002fd9e  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fda6  mov     rax, [rcx]
0x14002fda9  xor     r8d, r8d
0x14002fdac  lea     rdx, [rsp+1A8h+var_118]
0x14002fdb4  mov     rax, [rax+70h]
0x14002fdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fdbd  test    eax, eax
0x14002fdbf  jns     short loc_14002FDC8
0x14002fdc1  mov     ecx, eax; int
0x14002fdc3  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14002fdc8  mov     rdx, [rsp+1A8h+var_118]
0x14002fdd0  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x14002fdd8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14002fddd  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x14002fde2  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x14002fdea  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x14002fdef  mov     rcx, [rsp+1A8h+ppvObject]
0x14002fdf7  mov     rax, [rcx]
0x14002fdfa  mov     rax, [rax+0A0h]
0x14002fe01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe06  mov     edi, eax
0x14002fe08  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x14002fe0d  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x14002fe15  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x14002fe1a  mov     [rsp+1A8h+var_F8], rbx
0x14002fe22  lea     rax, [rsp+1A8h+String]
0x14002fe2a  cmp     [rsp+1A8h+var_F0], 7
0x14002fe33  cmova   rax, [rsp+1A8h+String]
0x14002fe3c  mov     [rax], bx
0x14002fe3f  mov     edx, [rsp+1A8h+cchWideChar]; cchWideChar
0x14002fe46  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x14002fe4e  cmp     qword ptr [rsp+1A8h+cchWideChar+8], 7
0x14002fe57  cmova   rcx, [rsp+1A8h+lpWideCharStr]; lpWideCharStr
0x14002fe60  lea     r9, [rsp+1A8h+var_D0]
0x14002fe68  call    ?HvsWideToMultiByte@@YA_KPEBG_KIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HvsWideToMultiByte(ushort const *,unsigned __int64,uint,std::string &)
0x14002fe6d  mov     rax, [r15]
0x14002fe70  mov     byte ptr [rsp+1A8h+var_178], bl
0x14002fe74  mov     dword ptr [rsp+1A8h+ppInput], ebx
0x14002fe78  mov     [rsp+1A8h+pwszBaseUri], r13
0x14002fe7d  lea     r9, [rsp+1A8h+var_D0]
0x14002fe85  mov     r8, r14
0x14002fe88  lea     rdx, [rsp+1A8h+var_128]
0x14002fe90  mov     rcx, r15
0x14002fe93  mov     rax, [rax+0A8h]
0x14002fe9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe9f  mov     rax, [rax]
0x14002fea2  mov     r14, [rax+28h]
0x14002fea6  test    edi, edi
0x14002fea8  mov     edi, [rsp+1A8h+var_164]
0x14002feac  jz      loc_14002FCF4
0x14002feb2  mov     rcx, [rsp+1A8h+var_F8]
0x14002feba  test    rcx, rcx
0x14002febd  jz      short loc_14002FECB
0x14002febf  cmp     edi, 1
0x14002fec2  jnz     short loc_14002FED7
0x14002fec4  mov     edi, 6
0x14002fec9  jmp     short loc_14002FED7
0x14002fecb  lea     eax, [rdi-6]
0x14002fece  cmp     eax, 1
0x14002fed1  ja      loc_14003018F
0x14002fed7  cmp     edi, 6
0x14002feda  jnz     short loc_14002FEE5
0x14002fedc  lea     esi, [rcx+rcx]
0x14002fedf  mov     [rsp+1A8h+var_168], esi
0x14002fee3  jmp     short loc_14002FF24
0x14002fee5  cmp     edi, 7
0x14002fee8  jnz     short loc_14002FF17
0x14002feea  test    rcx, rcx
0x14002feed  jz      short loc_14002FF0F
0x14002feef  lea     r9, [rsp+1A8h+var_168]
0x14002fef4  lea     r8, [rsp+1A8h+var_A0]
0x14002fefc  lea     rdx, [rsp+1A8h+String]
0x14002ff04  call    ?ConvertArrayDataFromString@HyperVStorage@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@AEAI@Z; HyperVStorage::ConvertArrayDataFromString(std::wstring const &,std::vector<uchar> &,uint &)
0x14002ff09  mov     esi, [rsp+1A8h+var_168]
0x14002ff0d  jmp     short loc_14002FF24
0x14002ff0f  mov     esi, ebx
0x14002ff11  mov     [rsp+1A8h+var_168], ebx
0x14002ff15  jmp     short loc_14002FF24
0x14002ff17  mov     ecx, edi
0x14002ff19  call    ?GetFixedTypeDataSpace@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@@Z; HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(HyperVStorageKeyType)
0x14002ff1e  mov     esi, eax
0x14002ff20  mov     [rsp+1A8h+var_168], eax
0x14002ff24  mov     edx, ebx
0x14002ff26  cmp     esi, 800h
0x14002ff2c  setnb   dl
0x14002ff2f  mov     r8d, esi
0x14002ff32  mov     ecx, edi
0x14002ff34  call    ?GetRequiredSpaceForData@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@HI@Z; HyperVStorageKeyTableEntry::GetRequiredSpaceForData(HyperVStorageKeyType,int,uint)
0x14002ff39  mov     r13d, eax
0x14002ff3c  mov     r12, [r14+20h]
0x14002ff40  test    r12, r12
0x14002ff43  jz      loc_140030268
0x14002ff49  cmp     [r14+18h], ebx
0x14002ff4d  jnz     loc_140030268
0x14002ff53  mov     rcx, r14; this
0x14002ff56  call    ?GetName@HyperVStorageKeyTableEntry@@QEBAPEBDXZ; HyperVStorageKeyTableEntry::GetName(void)
0x14002ff5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002ff5f  inc     r8
0x14002ff62  cmp     [rax+r8], bl
0x14002ff66  jnz     short loc_14002FF5F
0x14002ff68  mov     rdx, rax
0x14002ff6b  lea     rcx, [rsp+1A8h+var_D0]
0x14002ff73  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x14002ff78  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x14002ff7b  mov     rcx, r12; this
0x14002ff7e  call    ?RemoveChild@HyperVStorageKeyTableEntry@@QEAAXPEAV1@@Z; HyperVStorageKeyTableEntry::RemoveChild(HyperVStorageKeyTableEntry *)
0x14002ff83  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x14002ff86  mov     rcx, [rsp+1A8h+var_158]; this
0x14002ff8b  call    ?RemoveModifiedNode@HyperVStorageOperation@@QEAAXPEAVHyperVStorageKeyTableEntry@@@Z; HyperVStorageOperation::RemoveModifiedNode(HyperVStorageKeyTableEntry *)
0x14002ff90  lea     rcx, [r15+8]
0x14002ff94  mov     rax, [rcx]
0x14002ff97  mov     rdx, r14
0x14002ff9a  mov     rax, [rax+8]
0x14002ff9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ffa3  mov     rax, [r15]
0x14002ffa6  mov     byte ptr [rsp+1A8h+var_178], bl
  ... truncated ...
```
