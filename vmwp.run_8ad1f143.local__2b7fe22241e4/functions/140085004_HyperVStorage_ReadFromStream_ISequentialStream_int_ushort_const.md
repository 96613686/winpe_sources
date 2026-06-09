# HyperVStorage::ReadFromStream(ISequentialStream *,int,ushort const *)

- ea: `0x140085004`
- end: `0x1400858fc`
- name: `?ReadFromStream@HyperVStorage@@QEAAJPEAUISequentialStream@@HPEBG@Z`
- size: `2296`
- prototype: `__int64 __fastcall(HyperVStorage *__hidden this, IUnknown *pInputStream, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401ea510`
- `0x1401ea650`

## callees

- `0x140023e50`
- `0x1400261fc`
- `0x1400287c8`
- `0x14002ed20`
- `0x140031ca8`
- `0x140036db4`
- `0x140037498`
- `0x140038e6c`
- `0x14003bb28`
- `0x140044074`
- `0x140044b60`
- `0x140046548`
- `0x14004b0cc`
- `0x1400505c8`
- `0x1400510b4`
- `0x140056520`
- `0x140056b00`
- `0x140059940`
- `0x14005e804`
- `0x140084734`
- `0x140085004`
- `0x1400b9bc4`
- `0x1400da3b0`
- `0x1400db268`
- `0x140132960`
- `0x140133c0c`
- `0x140133c74`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400856bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400856bf`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140085608`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140085608`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085588`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400855c8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085683`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085588`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400855c8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140085683`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1400850b2`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1400850b2`
- `XmlLite!CreateXmlReader` at `0x140085068`
- `XmlLite!CreateXmlReader` at `0x140085068`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall HyperVStorage::ReadFromStream(
        HyperVStorage *this,
        IUnknown *pInputStream,
        int a3,
        unsigned __int16 *a4)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  HyperVStorageOperation *v13; // r13
  char *v14; // r14
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HyperVStorage *v19; // rcx
  int v20; // edi
  HyperVStorage *v21; // rcx
  wchar_t **v22; // rax
  const WCHAR *v23; // rcx
  bool v24; // zf
  unsigned int FixedTypeDataSpace; // esi
  HyperVStorageKeyTableEntry *v26; // r12
  const char *Name; // rax
  __int64 v28; // r8
  const wchar_t *v29; // rcx
  __int64 *p_Src; // rax
  const wchar_t *v31; // rcx
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rcx
  wchar_t **v34; // rdx
  int IsDebugTraceEnabled; // esi
  unsigned __int64 v36; // rdx
  unsigned __int8 v37; // cl
  bool IsEnabled; // al
  char v39; // di
  __int128 *v40; // r9
  LPCWCH *v41; // r8
  wchar_t **v42; // rax
  unsigned __int16 *v43; // rsi
  unsigned int v44; // r12d
  LPCWSTR pwszBaseUri; // [rsp+20h] [rbp-188h]
  int v47; // [rsp+30h] [rbp-178h]
  unsigned int v48; // [rsp+40h] [rbp-168h] BYREF
  int v49; // [rsp+44h] [rbp-164h] BYREF
  int v50; // [rsp+48h] [rbp-160h]
  HyperVStorage *v51; // [rsp+50h] [rbp-158h]
  unsigned __int16 *v52; // [rsp+58h] [rbp-150h]
  HyperVStorageOperation *v53; // [rsp+60h] [rbp-148h]
  unsigned __int16 *v54; // [rsp+68h] [rbp-140h]
  struct _GUID v55; // [rsp+70h] [rbp-138h] BYREF
  _BYTE v56[8]; // [rsp+80h] [rbp-128h] BYREF
  void *v57; // [rsp+88h] [rbp-120h] BYREF
  HyperVStorage *v58; // [rsp+90h] [rbp-118h] BYREF
  void *ppvObject; // [rsp+98h] [rbp-110h] BYREF
  wchar_t *String[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-F8h]
  unsigned __int64 v62; // [rsp+B8h] [rbp-F0h]
  int v63; // [rsp+C0h] [rbp-E8h] BYREF
  int v64; // [rsp+C4h] [rbp-E4h] BYREF
  __int64 Src; // [rsp+C8h] [rbp-E0h] BYREF
  IXmlReaderInput *ppInput; // [rsp+D0h] [rbp-D8h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-D0h] BYREF
  double v68; // [rsp+E0h] [rbp-C8h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+E8h] [rbp-C0h] BYREF
  int cchWideChar[4]; // [rsp+F8h] [rbp-B0h]
  __int128 v71; // [rsp+108h] [rbp-A0h] BYREF
  __m128i v72; // [rsp+118h] [rbp-90h]
  __int128 v73; // [rsp+128h] [rbp-80h] BYREF
  __int64 v74; // [rsp+138h] [rbp-70h]
  __int128 v75; // [rsp+140h] [rbp-68h] BYREF
  __m128i si128; // [rsp+150h] [rbp-58h]

  v52 = a4;
  v51 = this;
  v54 = a4;
  v50 = 0;
  ppvObject = 0;
  v8 = CreateXmlReader(&stru_1402E8610, &ppvObject, 0);
  try
  {
    if ( v8 < 0 )
      HvsThrowHResultError(v8);
    ppInput = 0;
    v9 = CreateXmlReaderInputWithEncodingName(
           pInputStream,
           0,
           L"UTF-16",
           1,
           &HyperVStorage::CFG_XML_NAMESPACE_URI,
           &ppInput);
    if ( v9 < 0 )
      HvsThrowHResultError(v9);
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
            ppvObject,
            1,
            (a3 != 0) + 1LL);
    if ( v10 < 0 )
      HvsThrowHResultError(v10);
    v11 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
    if ( v11 < 0 )
      HvsThrowHResultError(v11);
    v12 = 1;
    v49 = 1;
    *(_OWORD *)String = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(String[0]) = 0;
    v64 = 0;
    v67 = 0;
    Src = 0;
    v68 = 0.0;
    v63 = 0;
    v48 = 0;
    v75 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v75) = 0;
    v73 = 0;
    v74 = 0;
    *(_OWORD *)lpWideCharStr = 0;
    *(__m128i *)cchWideChar = si128;
    LOWORD(lpWideCharStr[0]) = 0;
    v71 = 0;
    v72 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v71) = 0;
    LODWORD(v57) = 1;
    v58 = this;
    std::vector<HyperVStorageOperation>::emplace_back<HyperVStorage *,enum HyperVStorageOperationType>(
      (char *)this + 184,
      &v58,
      &v57);
    v13 = (HyperVStorageOperation *)(*((_QWORD *)this + 24) - 88LL);
    v53 = v13;
    v14 = (char *)this + 248;
    if ( a4 )
    {
      v57 = 0;
      if ( !(unsigned int)HyperVStorage::GetOrCreateNode(this, a4, v13, &v57, 0) )
        HvsThrowHResultError(-2147467259);
      v14 = (char *)*((_QWORD *)v57 + 5);
    }
    try
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v16 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v64);
          if ( v16 )
            goto LABEL_102;
          if ( v64 != 1 )
            break;
          v58 = 0;
          v18 = (*(__int64 (__fastcall **)(void *, HyperVStorage **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v58,
                  0);
          if ( v18 < 0 )
            HvsThrowHResultError(v18);
          std::wstring::assign(lpWideCharStr, v58);
          HyperVStorage::ReadAttributes(v19, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v49);
          v20 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
          HyperVStorage::ReadAttributes(v21, (struct IXmlReader *)ppvObject, (enum HyperVStorageKeyType *)&v49);
          v61 = 0;
          v22 = String;
          if ( v62 > 7 )
            v22 = (wchar_t **)String[0];
          *(_WORD *)v22 = 0;
          v23 = (const WCHAR *)lpWideCharStr;
          if ( *(_QWORD *)&cchWideChar[2] > 7u )
            v23 = lpWideCharStr[0];
          HvsWideToMultiByte(v23, cchWideChar[0]);
          LOBYTE(v47) = 0;
          v14 = *(char **)(*(_QWORD *)(*(__int64 (__fastcall **)(HyperVStorage *, _BYTE *, char *, __int128 *, HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)this + 168LL))(
                                        this,
                                        v56,
                                        v14,
                                        &v71,
                                        v13,
                                        0,
                                        v47)
                         + 40LL);
          v24 = v20 == 0;
          v12 = v49;
          if ( !v24 )
          {
LABEL_32:
            if ( v61 )
            {
              if ( v12 == 1 )
                v12 = 6;
            }
            else if ( v12 - 6 > 1 )
            {
              goto LABEL_74;
            }
            if ( v12 == 6 )
            {
              FixedTypeDataSpace = 2 * v61;
              v48 = 2 * v61;
            }
            else if ( v12 == 7 )
            {
              if ( v61 )
              {
                HyperVStorage::ConvertArrayDataFromString(v61, String, &v73, &v48);
                FixedTypeDataSpace = v48;
              }
              else
              {
                FixedTypeDataSpace = 0;
                v48 = 0;
              }
            }
            else
            {
              FixedTypeDataSpace = HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(v12);
              v48 = FixedTypeDataSpace;
            }
            LODWORD(v57) = HyperVStorageKeyTableEntry::GetRequiredSpaceForData(
                             v12,
                             FixedTypeDataSpace >= 0x800,
                             FixedTypeDataSpace);
            v26 = (HyperVStorageKeyTableEntry *)*((_QWORD *)v14 + 4);
            if ( !v26 || *((_DWORD *)v14 + 6) )
              HvsThrowHResultError(-2147024809);
            Name = HyperVStorageKeyTableEntry::GetName((HyperVStorageKeyTableEntry *)v14);
            v28 = -1;
            do
              ++v28;
            while ( Name[v28] );
            std::string::_Assign<char>(&v71, Name);
            HyperVStorageKeyTableEntry::RemoveChild(v26, (struct HyperVStorageKeyTableEntry *)v14);
            HyperVStorageOperation::RemoveModifiedNode(v13, (struct HyperVStorageKeyTableEntry *)v14);
            (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8, v14);
            LOBYTE(v47) = 0;
            v57 = *(void **)(*(__int64 (__fastcall **)(HyperVStorage *, struct _GUID *, HyperVStorageKeyTableEntry *, __int128 *, HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)this + 168LL))(
                              this,
                              &v55,
                              v26,
                              &v71,
                              v13,
                              (_DWORD)v57,
                              v47);
            v14 = (char *)*((_QWORD *)v57 + 5);
            switch ( v12 )
            {
              case 3u:
                v29 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v29 = String[0];
                Src = _wtoi64(v29);
                p_Src = &Src;
                break;
              case 4u:
                v31 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v31 = String[0];
                v67 = _wtoi64(v31);
                p_Src = &v67;
                break;
              case 5u:
                v32 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v32 = String[0];
                v68 = _wtof(v32);
                p_Src = (__int64 *)&v68;
                break;
              case 6u:
                p_Src = (__int64 *)String;
                if ( v62 > 7 )
                  p_Src = (__int64 *)String[0];
                break;
              case 7u:
                p_Src = (__int64 *)v73;
                break;
              case 8u:
                v33 = (const wchar_t *)String;
                if ( v62 > 7 )
                  v33 = String[0];
                Src = _wtoi64(v33);
                v63 = 0;
                v34 = String;
                if ( v62 > 7 )
                  v34 = (wchar_t **)String[0];
                if ( !(unsigned int)_o__wcsicmp(L"true", v34) || Src == 1 )
                  v63 = 1;
                p_Src = (__int64 *)&v63;
                break;
              default:
                IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x4000u);
                IsEnabled = HyperVStorageTrace::IsEnabled(v37, v36);
                v39 = IsEnabled;
                if ( IsDebugTraceEnabled || IsEnabled )
                {
                  if ( dword_1403C1934 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
                  {
                    Init_thread_header(&dword_1403C1934);
                    if ( dword_1403C1934 == -1 )
                    {
                      byte_1403A6B7C = IsDebugTraceEnabled != 0;
                      byte_1403A6B7D = v39;
                      Init_thread_footer(&dword_1403C1934);
                    }
                  }
                  v40 = &v71;
                  if ( v72.m128i_i64[1] > 0xFuLL )
                    v40 = (__int128 *)v71;
                  v41 = lpWideCharStr;
                  if ( *(_QWORD *)&cchWideChar[2] > 7u )
                    v41 = (LPCWCH *)lpWideCharStr[0];
                  HvsDebugTraceInternal(0x4000u, (const struct HvsDebugTraceParameters *)&off_1403A6B68, v41, v40);
                }
                HvsThrowHResultError(-2147024809);
            }
            LODWORD(pwszBaseUri) = FixedTypeDataSpace;
            HyperVStorage::SetNodeValue((int)this, (int)v26, (int)&v57, v12, (size_t)pwszBaseUri, p_Src, (__int64)v13);
LABEL_74:
            v14 = (char *)*((_QWORD *)v14 + 4);
            if ( !v14 )
              HvsThrowHResultError(-2147024809);
            v12 = 1;
            v49 = 1;
            v61 = 0;
            v42 = String;
            if ( v62 > 7 )
              v42 = (wchar_t **)String[0];
            *(_WORD *)v42 = 0;
          }
        }
        switch ( v64 )
        {
          case 3:
          case 4:
LABEL_22:
            v57 = 0;
            v17 = (*(__int64 (__fastcall **)(void *, void **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                    ppvObject,
                    &v57,
                    0);
            if ( v17 < 0 )
              HvsThrowHResultError(v17);
            std::wstring::append(String, v57);
            break;
          case 13:
            if ( v61 )
              goto LABEL_22;
            break;
          case 15:
            goto LABEL_32;
        }
      }
    }
    catch ( ... )
    {
      HyperVStorageOperation::Undo(v53);
      std::vector<HyperVStorageOperation>::pop_back((char *)v51 + 184);
      throw;
    }
LABEL_102:
    if ( v16 < 0 )
      HvsThrowHResultError(v16);
    std::string::~string(&v71);
    std::wstring::_Tidy_deallocate(lpWideCharStr);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v73);
    std::wstring::_Tidy_deallocate(&v75);
    std::wstring::_Tidy_deallocate(String);
    HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&ppInput);
    HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&ppvObject);
    v43 = v52;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
  v44 = v50;
  v55 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::ReadFromStream(&v55, a3 != 0, v43, v50);
  return v44;
}

```

## disassembly

```asm
0x140085004  mov     [rsp+arg_10], r8d
0x140085009  push    rbx
0x14008500a  push    rsi
0x14008500b  push    rdi
0x14008500c  push    r12
0x14008500e  push    r13
0x140085010  push    r14
0x140085012  push    r15
0x140085014  sub     rsp, 170h
0x14008501b  mov     rax, cs:__security_cookie
0x140085022  xor     rax, rsp
0x140085025  mov     [rsp+1A8h+var_48], rax
0x14008502d  mov     rsi, r9
0x140085030  mov     [rsp+1A8h+var_150], r9
0x140085035  mov     r14d, r8d
0x140085038  mov     rdi, rdx
0x14008503b  mov     r15, rcx
0x14008503e  mov     [rsp+1A8h+var_158], rcx
0x140085043  mov     [rsp+1A8h+var_140], r9
0x140085048  xor     ebx, ebx
0x14008504a  mov     [rsp+1A8h+var_160], ebx
0x14008504e  mov     [rsp+1A8h+ppvObject], rbx
0x140085056  xor     r8d, r8d; pMalloc
0x140085059  lea     rdx, [rsp+1A8h+ppvObject]; ppvObject
0x140085061  lea     rcx, stru_1402E8610; riid
0x140085068  call    cs:__imp_CreateXmlReader
0x14008506f  nop     dword ptr [rax+rax+00h]
0x140085074  test    eax, eax
0x140085076  jns     short loc_14008507F
0x140085078  mov     ecx, eax; int
0x14008507a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x14008507f  mov     [rsp+1A8h+var_D8], rbx
0x140085087  lea     rax, [rsp+1A8h+var_D8]
0x14008508f  mov     [rsp+1A8h+ppInput], rax; ppInput
0x140085094  lea     rax, ?CFG_XML_NAMESPACE_URI@HyperVStorage@@1QBGB; ushort const near * const HyperVStorage::CFG_XML_NAMESPACE_URI
0x14008509b  mov     [rsp+1A8h+pwszBaseUri], rax; pwszBaseUri
0x1400850a0  mov     r9d, 1; fEncodingHint
0x1400850a6  lea     r8, pwszEncodingName; "UTF-16"
0x1400850ad  xor     edx, edx; pMalloc
0x1400850af  mov     rcx, rdi; pInputStream
0x1400850b2  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1400850b9  nop     dword ptr [rax+rax+00h]
0x1400850be  test    eax, eax
0x1400850c0  jns     short loc_1400850C9
0x1400850c2  mov     ecx, eax; int
0x1400850c4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400850c9  mov     rcx, [rsp+1A8h+ppvObject]
0x1400850d1  mov     r9, [rcx]
0x1400850d4  mov     eax, r14d
0x1400850d7  neg     eax
0x1400850d9  sbb     r8, r8
0x1400850dc  neg     r8
0x1400850df  inc     r8
0x1400850e2  mov     edx, 1
0x1400850e7  mov     rax, [r9+28h]
0x1400850eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400850f0  test    eax, eax
0x1400850f2  jns     short loc_1400850FB
0x1400850f4  mov     ecx, eax; int
0x1400850f6  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400850fb  mov     rcx, [rsp+1A8h+ppvObject]
0x140085103  mov     rax, [rcx]
0x140085106  mov     rdx, [rsp+1A8h+var_D8]
0x14008510e  mov     rax, [rax+18h]
0x140085112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085117  test    eax, eax
0x140085119  jns     short loc_140085122
0x14008511b  mov     ecx, eax; int
0x14008511d  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085122  mov     edi, 1
0x140085127  mov     [rsp+1A8h+var_164], edi
0x14008512b  xorps   xmm0, xmm0
0x14008512e  movups  xmmword ptr [rsp+1A8h+String], xmm0
0x140085136  mov     [rsp+1A8h+var_F8], rbx
0x14008513e  mov     [rsp+1A8h+var_F0], 7
0x14008514a  mov     word ptr [rsp+1A8h+String], bx
0x140085152  mov     [rsp+1A8h+var_E4], ebx
0x140085159  mov     [rsp+1A8h+var_D0], rbx
0x140085161  mov     [rsp+1A8h+Src], rbx
0x140085169  movsd   [rsp+1A8h+var_C8], xmm0
0x140085172  mov     [rsp+1A8h+var_E8], ebx
0x140085179  mov     [rsp+1A8h+var_168], ebx
0x14008517d  movups  [rsp+1A8h+var_68], xmm0
0x140085185  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x14008518d  movdqu  [rsp+1A8h+var_58], xmm2
0x140085196  mov     word ptr [rsp+1A8h+var_68], bx
0x14008519e  xorps   xmm1, xmm1
0x1400851a1  movdqu  [rsp+1A8h+var_80], xmm1
0x1400851aa  mov     [rsp+1A8h+var_70], rbx
0x1400851b2  movups  xmmword ptr [rsp+1A8h+lpWideCharStr], xmm0
0x1400851ba  movdqu  xmmword ptr [rsp+1A8h+cchWideChar], xmm2
0x1400851c3  mov     word ptr [rsp+1A8h+lpWideCharStr], bx
0x1400851cb  movups  [rsp+1A8h+var_A0], xmm0
0x1400851d3  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1400851db  movdqu  [rsp+1A8h+var_90], xmm1
0x1400851e4  mov     byte ptr [rsp+1A8h+var_A0], bl
0x1400851eb  mov     dword ptr [rsp+1A8h+var_120], edi
0x1400851f2  mov     [rsp+1A8h+var_118], r15
0x1400851fa  lea     rcx, [r15+0B8h]
0x140085201  lea     r8, [rsp+1A8h+var_120]
0x140085209  lea     rdx, [rsp+1A8h+var_118]
0x140085211  call    ??$emplace_back@PEAVHyperVStorage@@W4HyperVStorageOperationType@@@?$vector@VHyperVStorageOperation@@V?$allocator@VHyperVStorageOperation@@@std@@@std@@QEAAAEAVHyperVStorageOperation@@$$QEAPEAVHyperVStorage@@$$QEAW4HyperVStorageOperationType@@@Z; std::vector<HyperVStorageOperation>::emplace_back<HyperVStorage *,HyperVStorageOperationType>(HyperVStorage * &&,HyperVStorageOperationType &&)
0x140085216  mov     r13, [r15+0C0h]
0x14008521d  sub     r13, 58h ; 'X'
0x140085221  mov     [rsp+1A8h+var_148], r13
0x140085226  lea     r14, [r15+0F8h]
0x14008522d  test    rsi, rsi
0x140085230  jz      short loc_140085273
0x140085232  mov     [rsp+1A8h+var_120], rbx
0x14008523a  mov     byte ptr [rsp+1A8h+var_178], bl
0x14008523e  mov     [rsp+1A8h+pwszBaseUri], rbx
0x140085243  lea     r9, [rsp+1A8h+var_120]
0x14008524b  mov     r8, r13
0x14008524e  mov     rdx, rsi
0x140085251  mov     rcx, r15
0x140085254  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x140085259  test    eax, eax
0x14008525b  jnz     short loc_140085267
0x14008525d  mov     ecx, 80004005h; int
0x140085262  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085267  mov     rax, [rsp+1A8h+var_120]
0x14008526f  mov     r14, [rax+28h]
0x140085273  mov     rcx, [rsp+1A8h+ppvObject]
0x14008527b  mov     rax, [rcx]
0x14008527e  lea     rdx, [rsp+1A8h+var_E4]
0x140085286  mov     rax, [rax+30h]
0x14008528a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008528f  test    eax, eax
0x140085291  jnz     loc_140085827
0x140085297  mov     ecx, [rsp+1A8h+var_E4]
0x14008529e  sub     ecx, 1
0x1400852a1  jz      short loc_140085315
0x1400852a3  sub     ecx, 2
0x1400852a6  jz      short loc_1400852C6
0x1400852a8  sub     ecx, 1
0x1400852ab  jz      short loc_1400852C6
0x1400852ad  sub     ecx, 9
0x1400852b0  jz      short loc_1400852BC
0x1400852b2  cmp     ecx, 2
0x1400852b5  jnz     short loc_140085273
0x1400852b7  jmp     loc_140085431
0x1400852bc  cmp     [rsp+1A8h+var_F8], rbx
0x1400852c4  jz      short loc_140085273
0x1400852c6  mov     [rsp+1A8h+var_120], rbx
0x1400852ce  mov     rcx, [rsp+1A8h+ppvObject]
0x1400852d6  mov     rax, [rcx]
0x1400852d9  xor     r8d, r8d
0x1400852dc  lea     rdx, [rsp+1A8h+var_120]
0x1400852e4  mov     rax, [rax+80h]
0x1400852eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400852f0  test    eax, eax
0x1400852f2  jns     short loc_1400852FB
0x1400852f4  mov     ecx, eax; int
0x1400852f6  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1400852fb  mov     rdx, [rsp+1A8h+var_120]; void *
0x140085303  lea     rcx, [rsp+1A8h+String]; Src
0x14008530b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140085310  jmp     loc_140085273
0x140085315  mov     [rsp+1A8h+var_118], rbx
0x14008531d  mov     rcx, [rsp+1A8h+ppvObject]
0x140085325  mov     rax, [rcx]
0x140085328  xor     r8d, r8d
0x14008532b  lea     rdx, [rsp+1A8h+var_118]
0x140085333  mov     rax, [rax+70h]
0x140085337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008533c  test    eax, eax
0x14008533e  jns     short loc_140085347
0x140085340  mov     ecx, eax; int
0x140085342  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140085347  mov     rdx, [rsp+1A8h+var_118]
0x14008534f  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x140085357  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14008535c  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x140085361  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140085369  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x14008536e  mov     rcx, [rsp+1A8h+ppvObject]
0x140085376  mov     rax, [rcx]
0x140085379  mov     rax, [rax+0A0h]
0x140085380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085385  mov     edi, eax
0x140085387  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x14008538c  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140085394  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x140085399  mov     [rsp+1A8h+var_F8], rbx
0x1400853a1  lea     rax, [rsp+1A8h+String]
0x1400853a9  cmp     [rsp+1A8h+var_F0], 7
0x1400853b2  cmova   rax, [rsp+1A8h+String]
0x1400853bb  mov     [rax], bx
0x1400853be  mov     edx, [rsp+1A8h+cchWideChar]; cchWideChar
0x1400853c5  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x1400853cd  cmp     qword ptr [rsp+1A8h+cchWideChar+8], 7
0x1400853d6  cmova   rcx, [rsp+1A8h+lpWideCharStr]; lpWideCharStr
0x1400853df  lea     r9, [rsp+1A8h+var_A0]
0x1400853e7  call    ?HvsWideToMultiByte@@YA_KPEBG_KIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HvsWideToMultiByte(ushort const *,unsigned __int64,uint,std::string &)
0x1400853ec  mov     rax, [r15]
0x1400853ef  mov     byte ptr [rsp+1A8h+var_178], bl
0x1400853f3  mov     dword ptr [rsp+1A8h+ppInput], ebx
0x1400853f7  mov     [rsp+1A8h+pwszBaseUri], r13
0x1400853fc  lea     r9, [rsp+1A8h+var_A0]
0x140085404  mov     r8, r14
0x140085407  lea     rdx, [rsp+1A8h+var_128]
0x14008540f  mov     rcx, r15
0x140085412  mov     rax, [rax+0A8h]
0x140085419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008541e  mov     rax, [rax]
0x140085421  mov     r14, [rax+28h]
0x140085425  test    edi, edi
0x140085427  mov     edi, [rsp+1A8h+var_164]
0x14008542b  jz      loc_140085273
0x140085431  mov     rcx, [rsp+1A8h+var_F8]
0x140085439  test    rcx, rcx
0x14008543c  jz      short loc_14008544A
0x14008543e  cmp     edi, 1
0x140085441  jnz     short loc_140085456
0x140085443  mov     edi, 6
0x140085448  jmp     short loc_140085456
0x14008544a  lea     eax, [rdi-6]
0x14008544d  cmp     eax, 1
0x140085450  ja      loc_140085711
0x140085456  cmp     edi, 6
0x140085459  jnz     short loc_140085464
0x14008545b  lea     esi, [rcx+rcx]
0x14008545e  mov     [rsp+1A8h+var_168], esi
0x140085462  jmp     short loc_1400854A3
0x140085464  cmp     edi, 7
0x140085467  jnz     short loc_140085496
0x140085469  test    rcx, rcx
0x14008546c  jz      short loc_14008548E
0x14008546e  lea     r9, [rsp+1A8h+var_168]
0x140085473  lea     r8, [rsp+1A8h+var_80]
0x14008547b  lea     rdx, [rsp+1A8h+String]
0x140085483  call    ?ConvertArrayDataFromString@HyperVStorage@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@AEAI@Z; HyperVStorage::ConvertArrayDataFromString(std::wstring const &,std::vector<uchar> &,uint &)
0x140085488  mov     esi, [rsp+1A8h+var_168]
0x14008548c  jmp     short loc_1400854A3
0x14008548e  mov     esi, ebx
0x140085490  mov     [rsp+1A8h+var_168], ebx
0x140085494  jmp     short loc_1400854A3
0x140085496  mov     ecx, edi
0x140085498  call    ?GetFixedTypeDataSpace@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@@Z; HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(HyperVStorageKeyType)
0x14008549d  mov     esi, eax
0x14008549f  mov     [rsp+1A8h+var_168], eax
0x1400854a3  mov     edx, ebx
0x1400854a5  cmp     esi, 800h
0x1400854ab  setnb   dl
0x1400854ae  mov     r8d, esi
0x1400854b1  mov     ecx, edi
0x1400854b3  call    ?GetRequiredSpaceForData@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@HI@Z; HyperVStorageKeyTableEntry::GetRequiredSpaceForData(HyperVStorageKeyType,int,uint)
0x1400854b8  mov     dword ptr [rsp+1A8h+var_120], eax
0x1400854bf  mov     r12, [r14+20h]
0x1400854c3  test    r12, r12
0x1400854c6  jz      loc_1400857EA
0x1400854cc  cmp     [r14+18h], ebx
0x1400854d0  jnz     loc_1400857EA
0x1400854d6  mov     rcx, r14; this
0x1400854d9  call    ?GetName@HyperVStorageKeyTableEntry@@QEBAPEBDXZ; HyperVStorageKeyTableEntry::GetName(void)
0x1400854de  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400854e2  inc     r8
0x1400854e5  cmp     [rax+r8], bl
0x1400854e9  jnz     short loc_1400854E2
0x1400854eb  mov     rdx, rax
0x1400854ee  lea     rcx, [rsp+1A8h+var_A0]
0x1400854f6  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1400854fb  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x1400854fe  mov     rcx, r12; this
0x140085501  call    ?RemoveChild@HyperVStorageKeyTableEntry@@QEAAXPEAV1@@Z; HyperVStorageKeyTableEntry::RemoveChild(HyperVStorageKeyTableEntry *)
0x140085506  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x140085509  mov     rcx, r13; this
0x14008550c  call    ?RemoveModifiedNode@HyperVStorageOperation@@QEAAXPEAVHyperVStorageKeyTableEntry@@@Z; HyperVStorageOperation::RemoveModifiedNode(HyperVStorageKeyTableEntry *)
0x140085511  lea     rcx, [r15+8]
0x140085515  mov     rax, [rcx]
0x140085518  mov     rdx, r14
0x14008551b  mov     rax, [rax+8]
0x14008551f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085524  mov     rax, [r15]
0x140085527  mov     byte ptr [rsp+1A8h+var_178], bl
0x14008552b  mov     ecx, dword ptr [rsp+1A8h+var_120]
0x140085532  mov     dword ptr [rsp+1A8h+ppInput], ecx
0x140085536  mov     [rsp+1A8h+pwszBaseUri], r13
0x14008553b  lea     r9, [rsp+1A8h+var_A0]
0x140085543  mov     r8, r12
0x140085546  lea     rdx, [rsp+1A8h+var_138]
0x14008554b  mov     rcx, r15
0x14008554e  mov     rax, [rax+0A8h]
0x140085555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008555a  mov     rax, [rax]
0x14008555d  mov     [rsp+1A8h+var_120], rax
0x140085565  mov     r14, [rax+28h]
0x140085569  cmp     edi, 3
0x14008556c  jnz     short loc_1400855A9
0x14008556e  lea     rcx, [rsp+1A8h+String]
0x140085576  cmp     [rsp+1A8h+var_F0], 7
0x14008557f  cmova   rcx, [rsp+1A8h+String]; String
0x140085588  call    cs:__imp__wtoi64
0x14008558f  nop     dword ptr [rax+rax+00h]
0x140085594  mov     [rsp+1A8h+Src], rax
0x14008559c  lea     rax, [rsp+1A8h+Src]
0x1400855a4  jmp     loc_1400856ED
0x1400855a9  cmp     edi, 4
0x1400855ac  jnz     short loc_1400855E9
0x1400855ae  lea     rcx, [rsp+1A8h+String]
  ... truncated ...
```
