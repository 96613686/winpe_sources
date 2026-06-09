# HyperVStorage::ReadFromStream(ISequentialStream *,int,ushort const *)

- ea: `0x140095c14`
- end: `0x14009650c`
- name: `?ReadFromStream@HyperVStorage@@QEAAJPEAUISequentialStream@@HPEBG@Z`
- size: `2296`
- prototype: `__int64 __fastcall(HyperVStorage *__hidden this, IUnknown *pInputStream, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401d9f00`
- `0x1401da040`

## callees

- `0x1400243c0`
- `0x14002676c`
- `0x140028d38`
- `0x140029b34`
- `0x14002a218`
- `0x14002bbec`
- `0x14002e8a8`
- `0x14003b750`
- `0x14003d828`
- `0x1400419a8`
- `0x1400424a0`
- `0x140043ed8`
- `0x140049cac`
- `0x14004e848`
- `0x14004f334`
- `0x140056e90`
- `0x140057470`
- `0x1400691b4`
- `0x1400703b0`
- `0x140095344`
- `0x140095c14`
- `0x140097744`
- `0x1400af904`
- `0x1400c9538`
- `0x14011ea40`
- `0x14011fcec`
- `0x14011fd54`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400962cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400962cf`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140096218`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x140096218`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140096198`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400961d8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140096293`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140096198`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400961d8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140096293`
- `XmlLite!CreateXmlReader` at `0x140095c78`
- `XmlLite!CreateXmlReader` at `0x140095c78`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140095cc2`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x140095cc2`

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
  v8 = CreateXmlReader(&stru_1402F2078, &ppvObject, 0);
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
                  if ( dword_1403CDEC4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
                  {
                    Init_thread_header(&dword_1403CDEC4);
                    if ( dword_1403CDEC4 == -1 )
                    {
                      byte_1403B2C74 = IsDebugTraceEnabled != 0;
                      byte_1403B2C75 = v39;
                      Init_thread_footer(&dword_1403CDEC4);
                    }
                  }
                  v40 = &v71;
                  if ( v72.m128i_i64[1] > 0xFuLL )
                    v40 = (__int128 *)v71;
                  v41 = lpWideCharStr;
                  if ( *(_QWORD *)&cchWideChar[2] > 7u )
                    v41 = (LPCWCH *)lpWideCharStr[0];
                  HvsDebugTraceInternal(0x4000u, (const struct HvsDebugTraceParameters *)&off_1403B2C60, v41, v40);
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
0x140095c14  mov     [rsp+arg_10], r8d
0x140095c19  push    rbx
0x140095c1a  push    rsi
0x140095c1b  push    rdi
0x140095c1c  push    r12
0x140095c1e  push    r13
0x140095c20  push    r14
0x140095c22  push    r15
0x140095c24  sub     rsp, 170h
0x140095c2b  mov     rax, cs:__security_cookie
0x140095c32  xor     rax, rsp
0x140095c35  mov     [rsp+1A8h+var_48], rax
0x140095c3d  mov     rsi, r9
0x140095c40  mov     [rsp+1A8h+var_150], r9
0x140095c45  mov     r14d, r8d
0x140095c48  mov     rdi, rdx
0x140095c4b  mov     r15, rcx
0x140095c4e  mov     [rsp+1A8h+var_158], rcx
0x140095c53  mov     [rsp+1A8h+var_140], r9
0x140095c58  xor     ebx, ebx
0x140095c5a  mov     [rsp+1A8h+var_160], ebx
0x140095c5e  mov     [rsp+1A8h+ppvObject], rbx
0x140095c66  xor     r8d, r8d; pMalloc
0x140095c69  lea     rdx, [rsp+1A8h+ppvObject]; ppvObject
0x140095c71  lea     rcx, stru_1402F2078; riid
0x140095c78  call    cs:__imp_CreateXmlReader
0x140095c7f  nop     dword ptr [rax+rax+00h]
0x140095c84  test    eax, eax
0x140095c86  jns     short loc_140095C8F
0x140095c88  mov     ecx, eax; int
0x140095c8a  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095c8f  mov     [rsp+1A8h+var_D8], rbx
0x140095c97  lea     rax, [rsp+1A8h+var_D8]
0x140095c9f  mov     [rsp+1A8h+ppInput], rax; ppInput
0x140095ca4  lea     rax, ?CFG_XML_NAMESPACE_URI@HyperVStorage@@1QBGB; ushort const near * const HyperVStorage::CFG_XML_NAMESPACE_URI
0x140095cab  mov     [rsp+1A8h+pwszBaseUri], rax; pwszBaseUri
0x140095cb0  mov     r9d, 1; fEncodingHint
0x140095cb6  lea     r8, pwszEncodingName; "UTF-16"
0x140095cbd  xor     edx, edx; pMalloc
0x140095cbf  mov     rcx, rdi; pInputStream
0x140095cc2  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x140095cc9  nop     dword ptr [rax+rax+00h]
0x140095cce  test    eax, eax
0x140095cd0  jns     short loc_140095CD9
0x140095cd2  mov     ecx, eax; int
0x140095cd4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095cd9  mov     rcx, [rsp+1A8h+ppvObject]
0x140095ce1  mov     r9, [rcx]
0x140095ce4  mov     eax, r14d
0x140095ce7  neg     eax
0x140095ce9  sbb     r8, r8
0x140095cec  neg     r8
0x140095cef  inc     r8
0x140095cf2  mov     edx, 1
0x140095cf7  mov     rax, [r9+28h]
0x140095cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095d00  test    eax, eax
0x140095d02  jns     short loc_140095D0B
0x140095d04  mov     ecx, eax; int
0x140095d06  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095d0b  mov     rcx, [rsp+1A8h+ppvObject]
0x140095d13  mov     rax, [rcx]
0x140095d16  mov     rdx, [rsp+1A8h+var_D8]
0x140095d1e  mov     rax, [rax+18h]
0x140095d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095d27  test    eax, eax
0x140095d29  jns     short loc_140095D32
0x140095d2b  mov     ecx, eax; int
0x140095d2d  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095d32  mov     edi, 1
0x140095d37  mov     [rsp+1A8h+var_164], edi
0x140095d3b  xorps   xmm0, xmm0
0x140095d3e  movups  xmmword ptr [rsp+1A8h+String], xmm0
0x140095d46  mov     [rsp+1A8h+var_F8], rbx
0x140095d4e  mov     [rsp+1A8h+var_F0], 7
0x140095d5a  mov     word ptr [rsp+1A8h+String], bx
0x140095d62  mov     [rsp+1A8h+var_E4], ebx
0x140095d69  mov     [rsp+1A8h+var_D0], rbx
0x140095d71  mov     [rsp+1A8h+Src], rbx
0x140095d79  movsd   [rsp+1A8h+var_C8], xmm0
0x140095d82  mov     [rsp+1A8h+var_E8], ebx
0x140095d89  mov     [rsp+1A8h+var_168], ebx
0x140095d8d  movups  [rsp+1A8h+var_68], xmm0
0x140095d95  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x140095d9d  movdqu  [rsp+1A8h+var_58], xmm2
0x140095da6  mov     word ptr [rsp+1A8h+var_68], bx
0x140095dae  xorps   xmm1, xmm1
0x140095db1  movdqu  [rsp+1A8h+var_80], xmm1
0x140095dba  mov     [rsp+1A8h+var_70], rbx
0x140095dc2  movups  xmmword ptr [rsp+1A8h+lpWideCharStr], xmm0
0x140095dca  movdqu  xmmword ptr [rsp+1A8h+cchWideChar], xmm2
0x140095dd3  mov     word ptr [rsp+1A8h+lpWideCharStr], bx
0x140095ddb  movups  [rsp+1A8h+var_A0], xmm0
0x140095de3  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x140095deb  movdqu  [rsp+1A8h+var_90], xmm1
0x140095df4  mov     byte ptr [rsp+1A8h+var_A0], bl
0x140095dfb  mov     dword ptr [rsp+1A8h+var_120], edi
0x140095e02  mov     [rsp+1A8h+var_118], r15
0x140095e0a  lea     rcx, [r15+0B8h]
0x140095e11  lea     r8, [rsp+1A8h+var_120]
0x140095e19  lea     rdx, [rsp+1A8h+var_118]
0x140095e21  call    ??$emplace_back@PEAVHyperVStorage@@W4HyperVStorageOperationType@@@?$vector@VHyperVStorageOperation@@V?$allocator@VHyperVStorageOperation@@@std@@@std@@QEAAAEAVHyperVStorageOperation@@$$QEAPEAVHyperVStorage@@$$QEAW4HyperVStorageOperationType@@@Z; std::vector<HyperVStorageOperation>::emplace_back<HyperVStorage *,HyperVStorageOperationType>(HyperVStorage * &&,HyperVStorageOperationType &&)
0x140095e26  mov     r13, [r15+0C0h]
0x140095e2d  sub     r13, 58h ; 'X'
0x140095e31  mov     [rsp+1A8h+var_148], r13
0x140095e36  lea     r14, [r15+0F8h]
0x140095e3d  test    rsi, rsi
0x140095e40  jz      short loc_140095E83
0x140095e42  mov     [rsp+1A8h+var_120], rbx
0x140095e4a  mov     byte ptr [rsp+1A8h+var_178], bl
0x140095e4e  mov     [rsp+1A8h+pwszBaseUri], rbx
0x140095e53  lea     r9, [rsp+1A8h+var_120]
0x140095e5b  mov     r8, r13
0x140095e5e  mov     rdx, rsi
0x140095e61  mov     rcx, r15
0x140095e64  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x140095e69  test    eax, eax
0x140095e6b  jnz     short loc_140095E77
0x140095e6d  mov     ecx, 80004005h; int
0x140095e72  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095e77  mov     rax, [rsp+1A8h+var_120]
0x140095e7f  mov     r14, [rax+28h]
0x140095e83  mov     rcx, [rsp+1A8h+ppvObject]
0x140095e8b  mov     rax, [rcx]
0x140095e8e  lea     rdx, [rsp+1A8h+var_E4]
0x140095e96  mov     rax, [rax+30h]
0x140095e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095e9f  test    eax, eax
0x140095ea1  jnz     loc_140096437
0x140095ea7  mov     ecx, [rsp+1A8h+var_E4]
0x140095eae  sub     ecx, 1
0x140095eb1  jz      short loc_140095F25
0x140095eb3  sub     ecx, 2
0x140095eb6  jz      short loc_140095ED6
0x140095eb8  sub     ecx, 1
0x140095ebb  jz      short loc_140095ED6
0x140095ebd  sub     ecx, 9
0x140095ec0  jz      short loc_140095ECC
0x140095ec2  cmp     ecx, 2
0x140095ec5  jnz     short loc_140095E83
0x140095ec7  jmp     loc_140096041
0x140095ecc  cmp     [rsp+1A8h+var_F8], rbx
0x140095ed4  jz      short loc_140095E83
0x140095ed6  mov     [rsp+1A8h+var_120], rbx
0x140095ede  mov     rcx, [rsp+1A8h+ppvObject]
0x140095ee6  mov     rax, [rcx]
0x140095ee9  xor     r8d, r8d
0x140095eec  lea     rdx, [rsp+1A8h+var_120]
0x140095ef4  mov     rax, [rax+80h]
0x140095efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095f00  test    eax, eax
0x140095f02  jns     short loc_140095F0B
0x140095f04  mov     ecx, eax; int
0x140095f06  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095f0b  mov     rdx, [rsp+1A8h+var_120]; void *
0x140095f13  lea     rcx, [rsp+1A8h+String]; Src
0x140095f1b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140095f20  jmp     loc_140095E83
0x140095f25  mov     [rsp+1A8h+var_118], rbx
0x140095f2d  mov     rcx, [rsp+1A8h+ppvObject]
0x140095f35  mov     rax, [rcx]
0x140095f38  xor     r8d, r8d
0x140095f3b  lea     rdx, [rsp+1A8h+var_118]
0x140095f43  mov     rax, [rax+70h]
0x140095f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095f4c  test    eax, eax
0x140095f4e  jns     short loc_140095F57
0x140095f50  mov     ecx, eax; int
0x140095f52  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140095f57  mov     rdx, [rsp+1A8h+var_118]
0x140095f5f  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x140095f67  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140095f6c  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x140095f71  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140095f79  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x140095f7e  mov     rcx, [rsp+1A8h+ppvObject]
0x140095f86  mov     rax, [rcx]
0x140095f89  mov     rax, [rax+0A0h]
0x140095f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095f95  mov     edi, eax
0x140095f97  lea     r8, [rsp+1A8h+var_164]; enum HyperVStorageKeyType *
0x140095f9c  mov     rdx, [rsp+1A8h+ppvObject]; struct IXmlReader *
0x140095fa4  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x140095fa9  mov     [rsp+1A8h+var_F8], rbx
0x140095fb1  lea     rax, [rsp+1A8h+String]
0x140095fb9  cmp     [rsp+1A8h+var_F0], 7
0x140095fc2  cmova   rax, [rsp+1A8h+String]
0x140095fcb  mov     [rax], bx
0x140095fce  mov     edx, [rsp+1A8h+cchWideChar]; cchWideChar
0x140095fd5  lea     rcx, [rsp+1A8h+lpWideCharStr]
0x140095fdd  cmp     qword ptr [rsp+1A8h+cchWideChar+8], 7
0x140095fe6  cmova   rcx, [rsp+1A8h+lpWideCharStr]; lpWideCharStr
0x140095fef  lea     r9, [rsp+1A8h+var_A0]
0x140095ff7  call    ?HvsWideToMultiByte@@YA_KPEBG_KIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HvsWideToMultiByte(ushort const *,unsigned __int64,uint,std::string &)
0x140095ffc  mov     rax, [r15]
0x140095fff  mov     byte ptr [rsp+1A8h+var_178], bl
0x140096003  mov     dword ptr [rsp+1A8h+ppInput], ebx
0x140096007  mov     [rsp+1A8h+pwszBaseUri], r13
0x14009600c  lea     r9, [rsp+1A8h+var_A0]
0x140096014  mov     r8, r14
0x140096017  lea     rdx, [rsp+1A8h+var_128]
0x14009601f  mov     rcx, r15
0x140096022  mov     rax, [rax+0A8h]
0x140096029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009602e  mov     rax, [rax]
0x140096031  mov     r14, [rax+28h]
0x140096035  test    edi, edi
0x140096037  mov     edi, [rsp+1A8h+var_164]
0x14009603b  jz      loc_140095E83
0x140096041  mov     rcx, [rsp+1A8h+var_F8]
0x140096049  test    rcx, rcx
0x14009604c  jz      short loc_14009605A
0x14009604e  cmp     edi, 1
0x140096051  jnz     short loc_140096066
0x140096053  mov     edi, 6
0x140096058  jmp     short loc_140096066
0x14009605a  lea     eax, [rdi-6]
0x14009605d  cmp     eax, 1
0x140096060  ja      loc_140096321
0x140096066  cmp     edi, 6
0x140096069  jnz     short loc_140096074
0x14009606b  lea     esi, [rcx+rcx]
0x14009606e  mov     [rsp+1A8h+var_168], esi
0x140096072  jmp     short loc_1400960B3
0x140096074  cmp     edi, 7
0x140096077  jnz     short loc_1400960A6
0x140096079  test    rcx, rcx
0x14009607c  jz      short loc_14009609E
0x14009607e  lea     r9, [rsp+1A8h+var_168]
0x140096083  lea     r8, [rsp+1A8h+var_80]
0x14009608b  lea     rdx, [rsp+1A8h+String]
0x140096093  call    ?ConvertArrayDataFromString@HyperVStorage@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@AEAI@Z; HyperVStorage::ConvertArrayDataFromString(std::wstring const &,std::vector<uchar> &,uint &)
0x140096098  mov     esi, [rsp+1A8h+var_168]
0x14009609c  jmp     short loc_1400960B3
0x14009609e  mov     esi, ebx
0x1400960a0  mov     [rsp+1A8h+var_168], ebx
0x1400960a4  jmp     short loc_1400960B3
0x1400960a6  mov     ecx, edi
0x1400960a8  call    ?GetFixedTypeDataSpace@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@@Z; HyperVStorageKeyTableEntry::GetFixedTypeDataSpace(HyperVStorageKeyType)
0x1400960ad  mov     esi, eax
0x1400960af  mov     [rsp+1A8h+var_168], eax
0x1400960b3  mov     edx, ebx
0x1400960b5  cmp     esi, 800h
0x1400960bb  setnb   dl
0x1400960be  mov     r8d, esi
0x1400960c1  mov     ecx, edi
0x1400960c3  call    ?GetRequiredSpaceForData@HyperVStorageKeyTableEntry@@SAIW4HyperVStorageKeyType@@HI@Z; HyperVStorageKeyTableEntry::GetRequiredSpaceForData(HyperVStorageKeyType,int,uint)
0x1400960c8  mov     dword ptr [rsp+1A8h+var_120], eax
0x1400960cf  mov     r12, [r14+20h]
0x1400960d3  test    r12, r12
0x1400960d6  jz      loc_1400963FA
0x1400960dc  cmp     [r14+18h], ebx
0x1400960e0  jnz     loc_1400963FA
0x1400960e6  mov     rcx, r14; this
0x1400960e9  call    ?GetName@HyperVStorageKeyTableEntry@@QEBAPEBDXZ; HyperVStorageKeyTableEntry::GetName(void)
0x1400960ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400960f2  inc     r8
0x1400960f5  cmp     [rax+r8], bl
0x1400960f9  jnz     short loc_1400960F2
0x1400960fb  mov     rdx, rax
0x1400960fe  lea     rcx, [rsp+1A8h+var_A0]
0x140096106  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x14009610b  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x14009610e  mov     rcx, r12; this
0x140096111  call    ?RemoveChild@HyperVStorageKeyTableEntry@@QEAAXPEAV1@@Z; HyperVStorageKeyTableEntry::RemoveChild(HyperVStorageKeyTableEntry *)
0x140096116  mov     rdx, r14; struct HyperVStorageKeyTableEntry *
0x140096119  mov     rcx, r13; this
0x14009611c  call    ?RemoveModifiedNode@HyperVStorageOperation@@QEAAXPEAVHyperVStorageKeyTableEntry@@@Z; HyperVStorageOperation::RemoveModifiedNode(HyperVStorageKeyTableEntry *)
0x140096121  lea     rcx, [r15+8]
0x140096125  mov     rax, [rcx]
0x140096128  mov     rdx, r14
0x14009612b  mov     rax, [rax+8]
0x14009612f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096134  mov     rax, [r15]
0x140096137  mov     byte ptr [rsp+1A8h+var_178], bl
0x14009613b  mov     ecx, dword ptr [rsp+1A8h+var_120]
0x140096142  mov     dword ptr [rsp+1A8h+ppInput], ecx
0x140096146  mov     [rsp+1A8h+pwszBaseUri], r13
0x14009614b  lea     r9, [rsp+1A8h+var_A0]
0x140096153  mov     r8, r12
0x140096156  lea     rdx, [rsp+1A8h+var_138]
0x14009615b  mov     rcx, r15
0x14009615e  mov     rax, [rax+0A8h]
0x140096165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009616a  mov     rax, [rax]
0x14009616d  mov     [rsp+1A8h+var_120], rax
0x140096175  mov     r14, [rax+28h]
0x140096179  cmp     edi, 3
0x14009617c  jnz     short loc_1400961B9
0x14009617e  lea     rcx, [rsp+1A8h+String]
0x140096186  cmp     [rsp+1A8h+var_F0], 7
0x14009618f  cmova   rcx, [rsp+1A8h+String]; String
0x140096198  call    cs:__imp__wtoi64
0x14009619f  nop     dword ptr [rax+rax+00h]
0x1400961a4  mov     [rsp+1A8h+Src], rax
0x1400961ac  lea     rax, [rsp+1A8h+Src]
0x1400961b4  jmp     loc_1400962FD
0x1400961b9  cmp     edi, 4
0x1400961bc  jnz     short loc_1400961F9
0x1400961be  lea     rcx, [rsp+1A8h+String]
  ... truncated ...
```
