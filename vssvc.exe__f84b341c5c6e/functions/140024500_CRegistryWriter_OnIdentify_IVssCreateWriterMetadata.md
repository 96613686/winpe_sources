# CRegistryWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x140024500`
- end: `0x140024eef`
- name: `?OnIdentify@CRegistryWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `2543`
- prototype: `bool __fastcall(CRegistryWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013b00`
- `0x140013d30`
- `0x140019990`
- `0x140019bf0`
- `0x140019e30`
- `0x140024500`
- `0x140024ef8`
- `0x140025110`
- `0x140032fcc`
- `0x1400330fc`
- `0x14003a09c`
- `0x14003a8f0`
- `0x14003fc04`
- `0x14004ee3c`
- `0x1400566d8`
- `0x140070fcc`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024abf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024abf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024d98`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140024c12`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140024c12`

## string_xrefs

- `0x14002454b`: `CRegistryWriter::OnIdentify`
- `0x140024ddf`: `CRegistryWriter::OnIdentify`
- `0x14002453d`: `base\stor\vss\modules\writers\regwriter.cxx`
- `0x140024de6`: `base\stor\vss\modules\writers\regwriter.cxx`
- `0x14002485e`: `Registry`
- `0x1400249cd`: `Registry`
- `0x1400246d9`: `Registry Writer`
- `0x140024815`: `IVssCreateWriterMetadata::SetRestoreMethod`
- `0x140024928`: `IVssCreateWriterMetadata::AddComponent`
- `0x140024cf2`: `IVssCreateWriterMetadata::AddExcludeFiles`
- `0x140024a8e`: `IVssCreateWriterMetadata::AddFilesToFileGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
bool __fastcall CRegistryWriter::OnIdentify(CRegistryWriter *this, struct IVssCreateWriterMetadata *a2)
{
  struct IVssCreateWriterMetadata *v2; // r14
  __int64 v3; // rcx
  CVssDebugInfo *v4; // rax
  __int64 v5; // r9
  signed int v6; // edi
  CVssDebugInfo *v7; // rax
  signed int v8; // edi
  CVssDebugInfo *v9; // rax
  int i; // esi
  __int64 v11; // rdi
  __int64 v12; // rax
  HLOCAL v13; // r14
  signed int v14; // edi
  CVssDebugInfo *v15; // rax
  int j; // esi
  __int64 v17; // r14
  int k; // eax
  __int64 v19; // rdi
  HLOCAL v20; // rsi
  DWORD v21; // edi
  CVssDebugInfo *v22; // rax
  bool v23; // bl
  int v25; // [rsp+28h] [rbp-2F0h]
  int v26; // [rsp+70h] [rbp-2A8h]
  void **v28; // [rsp+80h] [rbp-298h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-290h]
  void **v30; // [rsp+90h] [rbp-288h] BYREF
  HLOCAL v31; // [rsp+98h] [rbp-280h]
  const unsigned __int16 *v32; // [rsp+A0h] [rbp-278h] BYREF
  const unsigned __int16 *v33; // [rsp+A8h] [rbp-270h]
  const unsigned __int16 *v34; // [rsp+B0h] [rbp-268h]
  int v35; // [rsp+B8h] [rbp-260h]
  int v36; // [rsp+BCh] [rbp-25Ch]
  int v37; // [rsp+C0h] [rbp-258h]
  _BYTE v38[120]; // [rsp+C8h] [rbp-250h] BYREF
  int v39; // [rsp+140h] [rbp-1D8h]
  void **v40; // [rsp+148h] [rbp-1D0h] BYREF
  HLOCAL v41; // [rsp+150h] [rbp-1C8h]
  int v42; // [rsp+158h] [rbp-1C0h]
  int pExceptionObject; // [rsp+160h] [rbp-1B8h] BYREF
  int v44; // [rsp+164h] [rbp-1B4h] BYREF
  int v45; // [rsp+168h] [rbp-1B0h] BYREF
  void **v46; // [rsp+170h] [rbp-1A8h] BYREF
  __int64 v47; // [rsp+178h] [rbp-1A0h]
  int v48; // [rsp+180h] [rbp-198h] BYREF
  CRegistryWriter *v49; // [rsp+188h] [rbp-190h]
  LPVOID v50; // [rsp+1A0h] [rbp-178h] BYREF
  DWORD dwMessageId; // [rsp+1A8h] [rbp-170h]
  unsigned int v52; // [rsp+1C4h] [rbp-154h]
  _com_error *v53; // [rsp+210h] [rbp-108h] BYREF
  const std::exception *v54; // [rsp+218h] [rbp-100h] BYREF
  _BYTE v55[168]; // [rsp+220h] [rbp-F8h] BYREF
  void **v56; // [rsp+2C8h] [rbp-50h] BYREF
  __int64 v57; // [rsp+2D0h] [rbp-48h]
  __m128i si128; // [rsp+2D8h] [rbp-40h]

  v2 = a2;
  v49 = this;
  v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v33 = L"CRegistryWriter::OnIdentify";
  v34 = L"WRTREGRC";
  v35 = 155;
  v36 = 4;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v50, (__int64)&v32, 0);
  v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v33 = L"CRegistryWriter::OnIdentify";
  v34 = L"WRTREGRC";
  v35 = 159;
  v36 = 1;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  try
  {
    CVssFunctionTracer::AddOperation((__int64)&v50, (__int64)&v32, 0x1F4u);
    v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
    v33 = L"CRegistryWriter::OnIdentify";
    v34 = L"WRTREGRC";
    v35 = 160;
    v36 = 1;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    CVssResource::LoadStringW(v3, &v56, 5012);
    v4 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v55, (const struct CVssDebugInfo *)&v32);
    CVssFunctionTracer::AddContextInternal((__int64)&v50, (__int64)v4, 2, v5, L"Registry Writer");
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v56, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v56) = 0;
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v32);
    v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD))(*(_QWORD *)v2 + 48LL))(
           v2,
           6,
           0);
    dwMessageId = v6;
    v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
    v33 = L"CRegistryWriter::OnIdentify";
    v34 = L"WRTREGRC";
    v35 = 173;
    v36 = 4;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    if ( v6 < 0 )
    {
      if ( v6 == -2147418113 )
      {
        pExceptionObject = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v7 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v55, (const struct CVssDebugInfo *)&v32);
      CVssFunctionTracer::TranslateError(&v50, v7, (unsigned int)v6, L"IVssCreateWriterMetadata::SetRestoreMethod");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v32);
    v8 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, const wchar_t *, _QWORD, _DWORD, _BYTE, _BYTE, char, _BYTE, _DWORD))(*(_QWORD *)v2 + 16LL))(
           v2,
           2,
           0,
           L"Registry",
           L"Registry",
           0,
           0,
           0,
           0,
           1,
           0,
           0);
    dwMessageId = v8;
    v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
    v33 = L"CRegistryWriter::OnIdentify";
    v34 = L"WRTREGRC";
    v35 = 190;
    v36 = 4;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    if ( v8 < 0 )
    {
      if ( v8 == -2147418113 )
      {
        v44 = -2147418113;
        throw (long *)&v44;
      }
      v9 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v55, (const struct CVssDebugInfo *)&v32);
      CVssFunctionTracer::TranslateError(&v50, v9, (unsigned int)v8, L"IVssCreateWriterMetadata::AddComponent");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v32);
    for ( i = 0; ; ++i )
    {
      v11 = 4LL * i;
      if ( !(&off_14014F1C0)[v11] )
        break;
      hMem = 0;
      v28 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::ExpandEnvironmentStringsW((__int64)&v28, off_14014F1D8[v11]);
      v12 = *(_QWORD *)v2;
      LOBYTE(v25) = 0;
      v13 = hMem;
      v14 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, HLOCAL, wchar_t *, int, _QWORD, int))(v12 + 40))(
              a2,
              0,
              L"Registry",
              hMem,
              (&off_14014F1C0)[v11],
              v25,
              0,
              3855);
      dwMessageId = v14;
      v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
      v33 = L"CRegistryWriter::OnIdentify";
      v34 = L"WRTREGRC";
      v35 = 211;
      v36 = 4;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      if ( v14 < 0 )
      {
        if ( v14 == -2147418113 )
        {
          v45 = -2147418113;
          throw (long *)&v45;
        }
        v15 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v55, (const struct CVssDebugInfo *)&v32);
        CVssFunctionTracer::TranslateError(
          &v50,
          v15,
          (unsigned int)v14,
          L"IVssCreateWriterMetadata::AddFilesToFileGroup");
      }
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v32);
      if ( v13 )
        LocalFree(v13);
      hMem = 0;
      v28 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
      v2 = a2;
    }
    for ( j = 0; ; j = v26 + 1 )
    {
      v26 = j;
      v17 = 4LL * j;
      if ( !(&off_14014F1C0)[v17] )
        break;
      v41 = 0;
      v40 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      v31 = 0;
      v30 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::ExpandEnvironmentStringsW((__int64)&v40, off_14014F1D8[v17]);
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v30, v41);
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v30, L"\\");
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v30, (&off_14014F1C0)[v17]);
      for ( k = 0; ; k = v42 + 1 )
      {
        v42 = k;
        v19 = k;
        if ( !off_1400F6340[k] )
          break;
        v28 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        hMem = 0;
        v57 = 0;
        v56 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v28, v31);
        v57 = 0;
        v56 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
        CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v28, off_1400F6340[v19]);
        v20 = hMem;
        if ( GetFileAttributesW((LPCWSTR)hMem) != -1 )
        {
          v47 = 0;
          v46 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v46, (&off_14014F1C0)[v17]);
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v46, off_1400F6340[v19]);
          dwMessageId = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, HLOCAL, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
                          a2,
                          v41,
                          v47,
                          0);
          v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
          v33 = L"CRegistryWriter::OnIdentify";
          v34 = L"WRTREGRC";
          v35 = 249;
          v36 = 4;
          v37 = 255;
          v39 = 0x1000000;
          memset_0(v38, 0, sizeof(v38));
          CVssFunctionTracer::CheckForErrorInternal(&v50, &v32, L"IVssCreateWriterMetadata::AddExcludeFiles");
          CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v46);
        }
        if ( v20 )
          LocalFree(v20);
        hMem = 0;
        v28 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
      }
      if ( v31 )
        LocalFree(v31);
      v31 = 0;
      v30 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
      if ( v41 )
        LocalFree(v41);
      v41 = 0;
      v40 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    }
  }
  catch ( long v48 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v50,
      v48,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnIdentify",
      0xFEu,
      v52);
  }
  catch ( _com_error *v53 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v50,
      v53,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnIdentify",
      0xFEu,
      v52);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v50,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnIdentify",
      0xFEu,
      v52);
  }
  catch ( const std::exception *v54 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v50,
      v54,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnIdentify",
      0xFEu,
      v52);
  }
  v21 = dwMessageId;
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    v32 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
    v33 = L"CRegistryWriter::OnIdentify";
    v34 = L"WRTREGRC";
    v35 = 256;
    v36 = 4;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    v22 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v32, (CVssDebugInfo *)v55, v21);
    CVssFunctionTracer::LogError((__int64)&v50, 0x3037u, (__int64)v22, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v32);
    v21 = dwMessageId;
  }
  CRegistryWriter::TranslateWriterError(v49, v21);
  v23 = (dwMessageId & 0x80000000) == 0;
  CVssFunctionTracer::~CVssFunctionTracer(&v50);
  return v23;
}

```

## disassembly

```asm
0x140024500  mov     r11, rsp
0x140024503  mov     [r11+18h], rbx
0x140024507  mov     [r11+20h], rsi
0x14002450b  push    rdi
0x14002450c  push    r12
0x14002450e  push    r13
0x140024510  push    r14
0x140024512  push    r15
0x140024514  sub     rsp, 2F0h
0x14002451b  mov     rax, cs:__security_cookie
0x140024522  xor     rax, rsp
0x140024525  mov     [rsp+318h+var_30], rax
0x14002452d  mov     r14, rdx
0x140024530  mov     [rsp+318h+var_2A0], rdx
0x140024535  mov     [rsp+318h+var_190], rcx
0x14002453d  lea     r15, aBaseStorVssMod_31; "base\\stor\\vss\\modules\\writers\\regw"...
0x140024544  mov     [r11-278h], r15
0x14002454b  lea     r12, aCregistrywrite_5; "CRegistryWriter::OnIdentify"
0x140024552  mov     [r11-270h], r12
0x140024559  lea     r13, aWrtregrc; "WRTREGRC"
0x140024560  mov     [r11-268h], r13
0x140024567  mov     [rsp+318h+var_260], 9Bh
0x140024572  mov     [rsp+318h+var_25C], 4
0x14002457d  mov     [rsp+318h+var_258], 0FFh
0x140024588  xor     ebx, ebx
0x14002458a  mov     [rsp+318h+var_1D8], 1000000h
0x140024595  xor     edx, edx; Val
0x140024597  lea     r8d, [rbx+78h]; Size
0x14002459b  lea     rcx, [r11-250h]; void *
0x1400245a2  call    memset_0
0x1400245a7  xor     r8d, r8d
0x1400245aa  lea     rdx, [rsp+318h+var_278]
0x1400245b2  lea     rcx, [rsp+318h+var_178]
0x1400245ba  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400245bf  nop
0x1400245c0  mov     [rsp+318h+var_278], r15
0x1400245c8  mov     [rsp+318h+var_270], r12
0x1400245d0  mov     [rsp+318h+var_268], r13
0x1400245d8  mov     [rsp+318h+var_260], 9Fh
0x1400245e3  mov     [rsp+318h+var_25C], 1
0x1400245ee  mov     [rsp+318h+var_258], 0FFh
0x1400245f9  mov     [rsp+318h+var_1D8], 1000000h
0x140024604  xor     edx, edx; Val
0x140024606  lea     r8d, [rbx+78h]; Size
0x14002460a  lea     rcx, [rsp+318h+var_250]; void *
0x140024612  call    memset_0
0x140024617  mov     r8d, 1F4h
0x14002461d  lea     rdx, [rsp+318h+var_278]
0x140024625  lea     rcx, [rsp+318h+var_178]
0x14002462d  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x140024632  mov     [rsp+318h+var_278], r15
0x14002463a  mov     [rsp+318h+var_270], r12
0x140024642  mov     [rsp+318h+var_268], r13
0x14002464a  mov     [rsp+318h+var_260], 0A0h
0x140024655  mov     [rsp+318h+var_25C], 1
0x140024660  mov     [rsp+318h+var_258], 0FFh
0x14002466b  mov     [rsp+318h+var_1D8], 1000000h
0x140024676  xor     edx, edx; Val
0x140024678  lea     r8d, [rbx+78h]; Size
0x14002467c  lea     rcx, [rsp+318h+var_250]; void *
0x140024684  call    memset_0
0x140024689  lea     rax, [rsp+318h+var_278]
0x140024691  mov     [rsp+318h+var_2A8], rax
0x140024696  mov     r8d, 1394h
0x14002469c  lea     rdx, [rsp+318h+var_50]
0x1400246a4  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x1400246a9  nop
0x1400246aa  lea     r9, [rsp+318h+var_50]
0x1400246b2  cmp     [rsp+318h+var_38], 7
0x1400246bb  cmova   r9, [rsp+318h+var_50]
0x1400246c4  lea     rdx, [rsp+318h+var_278]; struct CVssDebugInfo *
0x1400246cc  lea     rcx, [rsp+318h+var_F8]; this
0x1400246d4  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1400246d9  lea     rcx, aRegistryWriter_0; "Registry Writer"
0x1400246e0  mov     [rsp+318h+var_2F8], rcx
0x1400246e5  lea     esi, [rbx+2]
0x1400246e8  mov     r8d, esi
0x1400246eb  mov     rdx, rax
0x1400246ee  lea     rcx, [rsp+318h+var_178]
0x1400246f6  call    ?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z; CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)
0x1400246fb  nop
0x1400246fc  mov     rdx, [rsp+318h+var_38]
0x140024704  cmp     rdx, 7
0x140024708  jbe     short loc_14002471F
0x14002470a  lea     rdx, ds:2[rdx*2]
0x140024712  mov     rcx, [rsp+318h+var_50]
0x14002471a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14002471f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140024727  movdqu  xmmword ptr [rsp+2D8h], xmm0
0x140024730  mov     word ptr [rsp+318h+var_50], bx
0x140024738  lea     rcx, [rsp+318h+var_278]; this
0x140024740  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140024745  mov     rax, [r14]
0x140024748  mov     byte ptr [rsp+318h+var_2F0], 1
0x14002474d  mov     dword ptr [rsp+318h+var_2F8], 1
0x140024755  xor     r9d, r9d
0x140024758  xor     r8d, r8d
0x14002475b  lea     edx, [r9+6]
0x14002475f  mov     rcx, r14
0x140024762  mov     rax, [rax+30h]
0x140024766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002476b  mov     edi, eax
0x14002476d  mov     [rsp+318h+dwMessageId], eax
0x140024774  mov     [rsp+318h+var_278], r15
0x14002477c  mov     [rsp+318h+var_270], r12
0x140024784  mov     [rsp+318h+var_268], r13
0x14002478c  mov     [rsp+318h+var_260], 0ADh
0x140024797  mov     [rsp+318h+var_25C], 4
0x1400247a2  mov     [rsp+318h+var_258], 0FFh
0x1400247ad  mov     [rsp+318h+var_1D8], 1000000h
0x1400247b8  xor     edx, edx; Val
0x1400247ba  lea     r8d, [rdx+78h]; Size
0x1400247be  lea     rcx, [rsp+318h+var_250]; void *
0x1400247c6  call    memset_0
0x1400247cb  lea     rax, [rsp+318h+var_278]
0x1400247d3  mov     [rsp+318h+var_2A8], rax
0x1400247d8  test    edi, edi
0x1400247da  jns     short loc_140024830
0x1400247dc  mov     eax, 8000FFFFh
0x1400247e1  cmp     edi, eax
0x1400247e3  jnz     short loc_140024800
0x1400247e5  mov     [rsp+318h+pExceptionObject], eax
0x1400247ec  lea     rdx, _TI1J; pThrowInfo
0x1400247f3  lea     rcx, [rsp+318h+pExceptionObject]; pExceptionObject
0x1400247fb  call    _CxxThrowException_0
0x140024800  lea     rdx, [rsp+318h+var_278]; struct CVssDebugInfo *
0x140024808  lea     rcx, [rsp+318h+var_F8]; this
0x140024810  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x140024815  lea     r9, aIvsscreatewrit_4; "IVssCreateWriterMetadata::SetRestoreMet"...
0x14002481c  mov     r8d, edi
0x14002481f  mov     rdx, rax
0x140024822  lea     rcx, [rsp+318h+var_178]
0x14002482a  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x140024830  lea     rcx, [rsp+318h+var_278]; this
0x140024838  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002483d  mov     rax, [r14]
0x140024840  mov     [rsp+318h+var_2C0], ebx
0x140024844  mov     [rsp+318h+var_2C8], bl
0x140024848  mov     [rsp+318h+var_2D0], 1
0x14002484d  mov     [rsp+318h+var_2D8], bl
0x140024851  mov     byte ptr [rsp+318h+var_2E0], bl
0x140024855  mov     dword ptr [rsp+318h+var_2E8], ebx
0x140024859  mov     [rsp+318h+var_2F0], rbx
0x14002485e  lea     rcx, aRegistry; "Registry"
0x140024865  mov     [rsp+318h+var_2F8], rcx
0x14002486a  mov     r9, rcx
0x14002486d  xor     r8d, r8d
0x140024870  mov     edx, esi
0x140024872  mov     rcx, r14
0x140024875  mov     rax, [rax+10h]
0x140024879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002487e  mov     edi, eax
0x140024880  mov     [rsp+318h+dwMessageId], eax
0x140024887  mov     [rsp+318h+var_278], r15
0x14002488f  mov     [rsp+318h+var_270], r12
0x140024897  mov     [rsp+318h+var_268], r13
0x14002489f  mov     [rsp+318h+var_260], 0BEh
0x1400248aa  mov     [rsp+318h+var_25C], 4
0x1400248b5  mov     [rsp+318h+var_258], 0FFh
0x1400248c0  mov     [rsp+318h+var_1D8], 1000000h
0x1400248cb  xor     edx, edx; Val
0x1400248cd  lea     r8d, [rdx+78h]; Size
0x1400248d1  lea     rcx, [rsp+318h+var_250]; void *
0x1400248d9  call    memset_0
0x1400248de  lea     rax, [rsp+318h+var_278]
0x1400248e6  mov     [rsp+318h+var_2A8], rax
0x1400248eb  test    edi, edi
0x1400248ed  jns     short loc_140024943
0x1400248ef  mov     eax, 8000FFFFh
0x1400248f4  cmp     edi, eax
0x1400248f6  jnz     short loc_140024913
0x1400248f8  mov     [rsp+318h+var_1B4], eax
0x1400248ff  lea     rdx, _TI1J; pThrowInfo
0x140024906  lea     rcx, [rsp+318h+var_1B4]; pExceptionObject
0x14002490e  call    _CxxThrowException_0
0x140024913  lea     rdx, [rsp+318h+var_278]; struct CVssDebugInfo *
0x14002491b  lea     rcx, [rsp+318h+var_F8]; this
0x140024923  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x140024928  lea     r9, aIvsscreatewrit_3; "IVssCreateWriterMetadata::AddComponent"
0x14002492f  mov     r8d, edi
0x140024932  mov     rdx, rax
0x140024935  lea     rcx, [rsp+318h+var_178]
0x14002493d  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x140024943  lea     rcx, [rsp+318h+var_278]; this
0x14002494b  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140024950  mov     esi, ebx
0x140024952  lea     rdx, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140024959  lea     rax, __ImageBase
0x140024960  movsxd  rdi, esi
0x140024963  shl     rdi, 5
0x140024967  cmp     [rdi+rax+14F1C0h], rbx
0x14002496f  jz      loc_140024AE8
0x140024975  mov     [rsp+318h+hMem], rbx
0x14002497d  mov     [rsp+318h+var_298], rdx
0x140024985  mov     rdx, [rdi+rax+14F1D8h]
0x14002498d  lea     rcx, [rsp+318h+var_298]
0x140024995  call    ?ExpandEnvironmentStringsW@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::ExpandEnvironmentStringsW(ushort const *)
0x14002499a  mov     rax, [r14]
0x14002499d  mov     [rsp+318h+var_2E0], 0F0Fh
0x1400249a5  mov     [rsp+318h+var_2E8], rbx
0x1400249aa  mov     byte ptr [rsp+318h+var_2F0], bl
0x1400249ae  lea     rdx, __ImageBase
0x1400249b5  mov     rcx, [rdi+rdx+14F1C0h]
0x1400249bd  mov     [rsp+318h+var_2F8], rcx
0x1400249c2  mov     r14, [rsp+318h+hMem]
0x1400249ca  mov     r9, r14
0x1400249cd  lea     r8, aRegistry; "Registry"
0x1400249d4  xor     edx, edx
0x1400249d6  mov     rcx, [rsp+318h+var_2A0]
0x1400249db  mov     rax, [rax+28h]
0x1400249df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400249e4  mov     edi, eax
0x1400249e6  mov     [rsp+318h+dwMessageId], eax
0x1400249ed  mov     [rsp+318h+var_278], r15
0x1400249f5  mov     [rsp+318h+var_270], r12
0x1400249fd  mov     [rsp+318h+var_268], r13
0x140024a05  mov     [rsp+318h+var_260], 0D3h
0x140024a10  mov     [rsp+318h+var_25C], 4
0x140024a1b  mov     [rsp+318h+var_258], 0FFh
0x140024a26  mov     [rsp+318h+var_1D8], 1000000h
0x140024a31  xor     edx, edx; Val
0x140024a33  lea     r8d, [rdx+78h]; Size
0x140024a37  lea     rcx, [rsp+318h+var_250]; void *
0x140024a3f  call    memset_0
0x140024a44  lea     rax, [rsp+318h+var_278]
0x140024a4c  mov     [rsp+318h+var_2A8], rax
0x140024a51  test    edi, edi
0x140024a53  jns     short loc_140024AA9
0x140024a55  mov     eax, 8000FFFFh
0x140024a5a  cmp     edi, eax
0x140024a5c  jnz     short loc_140024A79
0x140024a5e  mov     [rsp+318h+var_1B0], eax
0x140024a65  lea     rdx, _TI1J; pThrowInfo
0x140024a6c  lea     rcx, [rsp+318h+var_1B0]; pExceptionObject
0x140024a74  call    _CxxThrowException_0
0x140024a79  lea     rdx, [rsp+318h+var_278]; struct CVssDebugInfo *
0x140024a81  lea     rcx, [rsp+318h+var_F8]; this
0x140024a89  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x140024a8e  lea     r9, aIvsscreatewrit_0; "IVssCreateWriterMetadata::AddFilesToFil"...
0x140024a95  mov     r8d, edi
0x140024a98  mov     rdx, rax
0x140024a9b  lea     rcx, [rsp+318h+var_178]
0x140024aa3  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x140024aa9  lea     rcx, [rsp+318h+var_278]; this
0x140024ab1  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140024ab6  nop
0x140024ab7  test    r14, r14
0x140024aba  jz      short loc_140024AC5
0x140024abc  mov     rcx, r14; hMem
0x140024abf  call    cs:__imp_LocalFree
0x140024ac5  mov     [rsp+318h+hMem], rbx
0x140024acd  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140024ad4  mov     [rsp+318h+var_298], rax
0x140024adc  inc     esi
0x140024ade  mov     r14, [rsp+318h+var_2A0]
0x140024ae3  jmp     loc_140024952
0x140024ae8  mov     esi, ebx
0x140024aea  mov     dword ptr [rsp+318h+var_2A8], esi
0x140024aee  movsxd  r14, esi
0x140024af1  shl     r14, 5
0x140024af5  cmp     [r14+rax+14F1C0h], rbx
0x140024afd  jz      loc_140024DCE
0x140024b03  mov     [rsp+318h+var_1C8], rbx
0x140024b0b  mov     [rsp+318h+var_1D0], rdx
0x140024b13  mov     [rsp+318h+var_280], rbx
0x140024b1b  mov     [rsp+318h+var_288], rdx
0x140024b23  mov     rdx, [r14+rax+14F1D8h]
0x140024b2b  lea     rcx, [rsp+318h+var_1D0]
0x140024b33  call    ?ExpandEnvironmentStringsW@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::ExpandEnvironmentStringsW(ushort const *)
0x140024b38  mov     rdx, [rsp+318h+var_1C8]
0x140024b40  lea     rcx, [rsp+318h+var_288]
0x140024b48  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x140024b4d  lea     rdx, pszSrc; "\\"
0x140024b54  lea     rcx, [rsp+318h+var_288]
0x140024b5c  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x140024b61  lea     rsi, __ImageBase
0x140024b68  mov     rdx, [r14+rsi+14F1C0h]
0x140024b70  lea     rcx, [rsp+318h+var_288]
0x140024b78  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x140024b7d  mov     eax, ebx
0x140024b7f  mov     [rsp+318h+var_1C0], eax
0x140024b86  movsxd  rdi, eax
0x140024b89  cmp     ds:rva off_1400F6340[rsi+rdi*8], rbx; ".LOG" ...
0x140024b91  jz      loc_140024D57
0x140024b97  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140024b9e  mov     [rsp+318h+var_298], rax
0x140024ba6  mov     [rsp+318h+hMem], rbx
0x140024bae  mov     [rsp+318h+var_48], rbx
0x140024bb6  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140024bbd  mov     [rsp+318h+var_50], rax
0x140024bc5  mov     rdx, [rsp+318h+var_280]
0x140024bcd  lea     rcx, [rsp+318h+var_298]
0x140024bd5  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x140024bda  nop
0x140024bdb  mov     [rsp+318h+var_48], rbx
0x140024be3  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140024bea  mov     [rsp+318h+var_50], rax
0x140024bf2  mov     rdx, ds:rva off_1400F6340[rsi+rdi*8]; ".LOG" ...
0x140024bfa  lea     rcx, [rsp+318h+var_298]
0x140024c02  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
  ... truncated ...
```
