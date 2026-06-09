# CRegistryWriter::OnPrepareBackup(IVssWriterComponents *)

- ea: `0x14003bac0`
- end: `0x14003c158`
- name: `?OnPrepareBackup@CRegistryWriter@@UEAA_NPEAVIVssWriterComponents@@@Z`
- size: `1688`
- prototype: `bool __fastcall(CRegistryWriter *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140006020`
- `0x1400088fc`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140013d30`
- `0x140019990`
- `0x140019bf0`
- `0x140019e30`
- `0x14003bac0`
- `0x14003c160`
- `0x14004ee3c`
- `0x1400566d8`
- `0x140070fcc`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003bfe3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003bfe3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003c06a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003c082`
- `OLEAUT32!__imp_SysFreeString` at `0x14003c06a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003c082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003beb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bfc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003beb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bfc0`

## string_xrefs

- `0x14003baf1`: `base\stor\vss\modules\writers\regwriter.cxx`
- `0x14003bafd`: `CRegistryWriter::OnPrepareBackup`
- `0x14003bdee`: `CRegistryWriter::OnPrepareBackup`
- `0x14003bef7`: `CRegistryWriter::OnPrepareBackup`
- `0x14003bff6`: `CRegistryWriter::OnPrepareBackup`
- `0x14003bfdc`: `Registry`
- `0x14003bc4a`: `Registry Writer`
- `0x14003bd8e`: `IVssWriterComponents::GetComponentCount`
- `0x14003bf8c`: `IVssComponent::GetComponentName`
- `0x14003be83`: `IVssWriterComponents::GetComponent`
- `0x14003c0df`: `No Registry writer components selected`
- `0x14003c044`: `Registry writer 'Registry' component selected, writer will copy registry hives`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall CRegistryWriter::OnPrepareBackup(CRegistryWriter *this, struct IVssWriterComponents *a2)
{
  __int64 v3; // rcx
  CVssDebugInfo *v4; // rax
  __int64 v5; // r9
  CRegistryWriter *v6; // r14
  __int64 v7; // rcx
  int v8; // edi
  CVssDebugInfo *v9; // rax
  unsigned int i; // esi
  int v11; // edi
  CVssDebugInfo *v12; // rax
  __int64 j; // rdi
  void *v14; // rcx
  int v15; // edi
  CVssDebugInfo *v16; // rax
  __int64 k; // rdi
  void *v18; // rcx
  bool v19; // bl
  const unsigned __int16 **v21; // [rsp+40h] [rbp-268h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-260h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-258h] BYREF
  const unsigned __int16 *v24; // [rsp+58h] [rbp-250h] BYREF
  const unsigned __int16 *v25; // [rsp+60h] [rbp-248h]
  const unsigned __int16 *v26; // [rsp+68h] [rbp-240h]
  int v27; // [rsp+70h] [rbp-238h]
  int v28; // [rsp+74h] [rbp-234h]
  int v29; // [rsp+78h] [rbp-230h]
  LPVOID pv[15]; // [rsp+80h] [rbp-228h] BYREF
  int v31; // [rsp+F8h] [rbp-1B0h]
  const unsigned __int16 **v32; // [rsp+100h] [rbp-1A8h]
  int pExceptionObject; // [rsp+108h] [rbp-1A0h] BYREF
  int v34; // [rsp+10Ch] [rbp-19Ch] BYREF
  int v35; // [rsp+110h] [rbp-198h] BYREF
  CRegistryWriter *v36; // [rsp+118h] [rbp-190h]
  const unsigned __int16 **v37; // [rsp+120h] [rbp-188h]
  int v38; // [rsp+128h] [rbp-180h] BYREF
  LPVOID v39; // [rsp+130h] [rbp-178h] BYREF
  int v40; // [rsp+138h] [rbp-170h]
  unsigned int v41; // [rsp+154h] [rbp-154h]
  _com_error *v42; // [rsp+1A0h] [rbp-108h] BYREF
  const std::exception *v43; // [rsp+1A8h] [rbp-100h] BYREF
  _BYTE v44[168]; // [rsp+1B0h] [rbp-F8h] BYREF
  __int64 v45; // [rsp+258h] [rbp-50h] BYREF
  __m128i si128; // [rsp+268h] [rbp-40h]

  v36 = this;
  v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v25 = L"CRegistryWriter::OnPrepareBackup";
  v26 = L"WRTREGRC";
  v27 = 268;
  v28 = 4;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v39, (__int64)&v24, 0);
  v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v25 = L"CRegistryWriter::OnPrepareBackup";
  v26 = L"WRTREGRC";
  v27 = 272;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  try
  {
    CVssFunctionTracer::AddOperation((__int64)&v39, (__int64)&v24, 0xD1u);
    v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
    v25 = L"CRegistryWriter::OnPrepareBackup";
    v26 = L"WRTREGRC";
    v27 = 273;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v21 = &v24;
    CVssResource::LoadStringW(v3, &v45, 5012);
    v4 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v24);
    CVssFunctionTracer::AddContextInternal((__int64)&v39, (__int64)v4, 2, v5, L"Registry Writer");
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v45, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v45) = 0;
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v24);
    v6 = v36;
    v7 = *((_QWORD *)v36 + 1);
    if ( v7 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 120LL))(v7) )
    {
      v23 = 0;
      *((_DWORD *)v6 + 9) = 0;
      v8 = (**(__int64 (__fastcall ***)(struct IVssWriterComponents *, unsigned int *))a2)(a2, &v23);
      v40 = v8;
      v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
      v25 = L"CRegistryWriter::OnPrepareBackup";
      v26 = L"WRTREGRC";
      v27 = 286;
      v28 = 4;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      v21 = &v24;
      if ( v8 < 0 )
      {
        if ( v8 == -2147418113 )
        {
          pExceptionObject = -2147418113;
          throw (long *)&pExceptionObject;
        }
        v9 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v24);
        CVssFunctionTracer::TranslateError(&v39, v9, (unsigned int)v8, L"IVssWriterComponents::GetComponentCount");
      }
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v24);
      for ( i = 0; i < v23; ++i )
      {
        ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v21);
        v11 = (*(__int64 (__fastcall **)(struct IVssWriterComponents *, _QWORD, const unsigned __int16 ***))(*(_QWORD *)a2 + 16LL))(
                a2,
                i,
                &v21);
        v40 = v11;
        v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
        v25 = L"CRegistryWriter::OnPrepareBackup";
        v26 = L"WRTREGRC";
        v27 = 293;
        v28 = 4;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        v37 = &v24;
        if ( v11 < 0 )
        {
          if ( v11 == -2147418113 )
          {
            v34 = -2147418113;
            throw (long *)&v34;
          }
          v12 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v24);
          CVssFunctionTracer::TranslateError(&v39, v12, (unsigned int)v11, L"IVssWriterComponents::GetComponent");
        }
        if ( HIBYTE(v31) )
        {
          for ( j = 0; j != 15; ++j )
          {
            v14 = pv[j];
            if ( v14 )
            {
              CoTaskMemFree(v14);
              pv[j] = 0;
            }
          }
        }
        bstrString = 0;
        v15 = (*((__int64 (__fastcall **)(const unsigned __int16 **, BSTR *))*v21 + 5))(v21, &bstrString);
        v40 = v15;
        v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
        v25 = L"CRegistryWriter::OnPrepareBackup";
        v26 = L"WRTREGRC";
        v27 = 297;
        v28 = 4;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        v32 = &v24;
        if ( v15 < 0 )
        {
          if ( v15 == -2147418113 )
          {
            v35 = -2147418113;
            throw (long *)&v35;
          }
          v16 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v24);
          CVssFunctionTracer::TranslateError(&v39, v16, (unsigned int)v15, L"IVssComponent::GetComponentName");
        }
        if ( HIBYTE(v31) )
        {
          for ( k = 0; k != 15; ++k )
          {
            v18 = pv[k];
            if ( v18 )
            {
              CoTaskMemFree(v18);
              pv[k] = 0;
            }
          }
        }
        if ( !(unsigned int)_o__wcsicmp(L"Registry", bstrString) )
        {
          v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
          v25 = L"CRegistryWriter::OnPrepareBackup";
          v26 = L"WRTREGRC";
          v27 = 302;
          v28 = 4;
          v29 = 255;
          v31 = 0x1000000;
          memset_0(pv, 0, sizeof(pv));
          CVssFunctionTracer::Trace(
            &v39,
            &v24,
            L"Registry writer 'Registry' component selected, writer will copy registry hives");
          *((_DWORD *)v6 + 9) = 1;
          SysFreeString(bstrString);
          ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v21);
          goto LABEL_42;
        }
        SysFreeString(bstrString);
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v21);
      }
    }
    else
    {
      v24 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
      v25 = L"CRegistryWriter::OnPrepareBackup";
      v26 = L"WRTREGRC";
      v27 = 310;
      v28 = 4;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Trace(&v39, &v24, L"No Registry writer components selected");
    }
  }
  catch ( long v38 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v39,
      v38,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnPrepareBackup",
      0x139u,
      v41);
  }
  catch ( _com_error *v42 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v39,
      v42,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnPrepareBackup",
      0x139u,
      v41);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v39,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnPrepareBackup",
      0x139u,
      v41);
  }
  catch ( const std::exception *v43 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v39,
      v43,
      L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
      L"WRTREGRC",
      L"CRegistryWriter::OnPrepareBackup",
      0x139u,
      v41);
  }
LABEL_42:
  CRegistryWriter::TranslateWriterError(v36, v40);
  v19 = v40 >= 0;
  CVssFunctionTracer::~CVssFunctionTracer(&v39);
  return v19;
}

```

## disassembly

```asm
0x14003bac0  mov     [rsp+arg_10], rbx
0x14003bac5  push    rsi
0x14003bac6  push    rdi
0x14003bac7  push    r13
0x14003bac9  push    r14
0x14003bacb  push    r15
0x14003bacd  sub     rsp, 280h
0x14003bad4  mov     rax, cs:__security_cookie
0x14003badb  xor     rax, rsp
0x14003bade  mov     [rsp+2A8h+var_30], rax
0x14003bae6  mov     r15, rdx
0x14003bae9  mov     [rsp+2A8h+var_190], rcx
0x14003baf1  lea     r13, aBaseStorVssMod_31; "base\\stor\\vss\\modules\\writers\\regw"...
0x14003baf8  mov     [rsp+2A8h+var_250], r13
0x14003bafd  lea     rsi, aCregistrywrite_6; "CRegistryWriter::OnPrepareBackup"
0x14003bb04  mov     [rsp+2A8h+var_248], rsi
0x14003bb09  lea     rdi, aWrtregrc; "WRTREGRC"
0x14003bb10  mov     [rsp+2A8h+var_240], rdi
0x14003bb15  mov     [rsp+2A8h+var_238], 10Ch
0x14003bb1d  mov     [rsp+2A8h+var_234], 4
0x14003bb25  mov     r14d, 0FFh
0x14003bb2b  mov     [rsp+2A8h+var_230], r14d
0x14003bb30  xor     ebx, ebx
0x14003bb32  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003bb3d  xor     edx, edx; Val
0x14003bb3f  lea     r8d, [rbx+78h]; Size
0x14003bb43  lea     rcx, [rsp+2A8h+pv]; void *
0x14003bb4b  call    memset_0
0x14003bb50  xor     r8d, r8d
0x14003bb53  lea     rdx, [rsp+2A8h+var_250]
0x14003bb58  lea     rcx, [rsp+2A8h+var_178]
0x14003bb60  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14003bb65  nop
0x14003bb66  mov     [rsp+2A8h+var_250], r13
0x14003bb6b  mov     [rsp+2A8h+var_248], rsi
0x14003bb70  mov     [rsp+2A8h+var_240], rdi
0x14003bb75  mov     [rsp+2A8h+var_238], 110h
0x14003bb7d  mov     [rsp+2A8h+var_234], 1
0x14003bb85  mov     [rsp+2A8h+var_230], r14d
0x14003bb8a  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003bb95  xor     edx, edx; Val
0x14003bb97  lea     r8d, [rbx+78h]; Size
0x14003bb9b  lea     rcx, [rsp+2A8h+pv]; void *
0x14003bba3  call    memset_0
0x14003bba8  lea     r8d, [r14-2Eh]
0x14003bbac  lea     rdx, [rsp+2A8h+var_250]
0x14003bbb1  lea     rcx, [rsp+2A8h+var_178]
0x14003bbb9  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x14003bbbe  mov     [rsp+2A8h+var_250], r13
0x14003bbc3  mov     [rsp+2A8h+var_248], rsi
0x14003bbc8  mov     [rsp+2A8h+var_240], rdi
0x14003bbcd  mov     [rsp+2A8h+var_238], 111h
0x14003bbd5  mov     [rsp+2A8h+var_234], 1
0x14003bbdd  mov     [rsp+2A8h+var_230], r14d
0x14003bbe2  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003bbed  xor     edx, edx; Val
0x14003bbef  lea     r8d, [rbx+78h]; Size
0x14003bbf3  lea     rcx, [rsp+2A8h+pv]; void *
0x14003bbfb  call    memset_0
0x14003bc00  lea     rax, [rsp+2A8h+var_250]
0x14003bc05  mov     [rsp+2A8h+var_268], rax
0x14003bc0a  mov     r8d, 1394h
0x14003bc10  lea     rdx, [rsp+2A8h+var_50]
0x14003bc18  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x14003bc1d  nop
0x14003bc1e  lea     r9, [rsp+2A8h+var_50]
0x14003bc26  cmp     [rsp+2A8h+var_38], 7
0x14003bc2f  cmova   r9, [rsp+2A8h+var_50]
0x14003bc38  lea     rdx, [rsp+2A8h+var_250]; struct CVssDebugInfo *
0x14003bc3d  lea     rcx, [rsp+2A8h+var_F8]; this
0x14003bc45  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003bc4a  lea     rcx, aRegistryWriter_0; "Registry Writer"
0x14003bc51  mov     [rsp+2A8h+var_288], rcx
0x14003bc56  lea     r8d, [rbx+2]
0x14003bc5a  mov     rdx, rax
0x14003bc5d  lea     rcx, [rsp+2A8h+var_178]
0x14003bc65  call    ?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z; CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)
0x14003bc6a  nop
0x14003bc6b  mov     rdx, [rsp+2A8h+var_38]
0x14003bc73  cmp     rdx, 7
0x14003bc77  jbe     short loc_14003BC8E
0x14003bc79  lea     rdx, ds:2[rdx*2]
0x14003bc81  mov     rcx, [rsp+2A8h+var_50]
0x14003bc89  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14003bc8e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003bc96  movdqu  xmmword ptr [rsp+268h], xmm0
0x14003bc9f  mov     word ptr [rsp+2A8h+var_50], bx
0x14003bca7  lea     rcx, [rsp+2A8h+var_250]; this
0x14003bcac  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003bcb1  mov     r14, [rsp+2A8h+var_190]
0x14003bcb9  mov     rcx, [r14+8]
0x14003bcbd  test    rcx, rcx
0x14003bcc0  jz      loc_14003C09A
0x14003bcc6  mov     rax, [rcx]
0x14003bcc9  mov     rax, [rax+78h]
0x14003bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bcd2  test    al, al
0x14003bcd4  jz      loc_14003C09A
0x14003bcda  mov     [rsp+2A8h+var_258], ebx
0x14003bcde  mov     [r14+24h], ebx
0x14003bce2  mov     rax, [r15]
0x14003bce5  lea     rdx, [rsp+2A8h+var_258]
0x14003bcea  mov     rcx, r15
0x14003bced  mov     rax, [rax]
0x14003bcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bcf5  mov     edi, eax
0x14003bcf7  mov     [rsp+2A8h+var_170], eax
0x14003bcfe  mov     [rsp+2A8h+var_250], r13
0x14003bd03  mov     [rsp+2A8h+var_248], rsi
0x14003bd08  lea     rax, aWrtregrc; "WRTREGRC"
0x14003bd0f  mov     [rsp+2A8h+var_240], rax
0x14003bd14  mov     [rsp+2A8h+var_238], 11Eh
0x14003bd1c  mov     [rsp+2A8h+var_234], 4
0x14003bd24  mov     [rsp+2A8h+var_230], 0FFh
0x14003bd2c  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003bd37  xor     edx, edx; Val
0x14003bd39  lea     r8d, [rdx+78h]; Size
0x14003bd3d  lea     rcx, [rsp+2A8h+pv]; void *
0x14003bd45  call    memset_0
0x14003bd4a  lea     rax, [rsp+2A8h+var_250]
0x14003bd4f  mov     [rsp+2A8h+var_268], rax
0x14003bd54  test    edi, edi
0x14003bd56  jns     short loc_14003BDA9
0x14003bd58  mov     eax, 8000FFFFh
0x14003bd5d  cmp     edi, eax
0x14003bd5f  jnz     short loc_14003BD7C
0x14003bd61  mov     [rsp+2A8h+pExceptionObject], eax
0x14003bd68  lea     rdx, _TI1J; pThrowInfo
0x14003bd6f  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x14003bd77  call    _CxxThrowException_0
0x14003bd7c  lea     rdx, [rsp+2A8h+var_250]; struct CVssDebugInfo *
0x14003bd81  lea     rcx, [rsp+2A8h+var_F8]; this
0x14003bd89  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003bd8e  lea     r9, aIvsswritercomp_0; "IVssWriterComponents::GetComponentCount"
0x14003bd95  mov     r8d, edi
0x14003bd98  mov     rdx, rax
0x14003bd9b  lea     rcx, [rsp+2A8h+var_178]
0x14003bda3  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003bda9  lea     rcx, [rsp+2A8h+var_250]; this
0x14003bdae  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003bdb3  mov     esi, ebx
0x14003bdb5  cmp     esi, [rsp+2A8h+var_258]
0x14003bdb9  jnb     loc_14003C0F9
0x14003bdbf  lea     rcx, [rsp+2A8h+var_268]
0x14003bdc4  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14003bdc9  nop
0x14003bdca  mov     rax, [r15]
0x14003bdcd  lea     r8, [rsp+2A8h+var_268]
0x14003bdd2  mov     edx, esi
0x14003bdd4  mov     rcx, r15
0x14003bdd7  mov     rax, [rax+10h]
0x14003bddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bde0  mov     edi, eax
0x14003bde2  mov     [rsp+2A8h+var_170], eax
0x14003bde9  mov     [rsp+2A8h+var_250], r13
0x14003bdee  lea     rax, aCregistrywrite_6; "CRegistryWriter::OnPrepareBackup"
0x14003bdf5  mov     [rsp+2A8h+var_248], rax
0x14003bdfa  lea     rax, aWrtregrc; "WRTREGRC"
0x14003be01  mov     [rsp+2A8h+var_240], rax
0x14003be06  mov     [rsp+2A8h+var_238], 125h
0x14003be0e  mov     [rsp+2A8h+var_234], 4
0x14003be16  mov     [rsp+2A8h+var_230], 0FFh
0x14003be1e  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003be29  xor     edx, edx; Val
0x14003be2b  lea     r8d, [rdx+78h]; Size
0x14003be2f  lea     rcx, [rsp+2A8h+pv]; void *
0x14003be37  call    memset_0
0x14003be3c  lea     rax, [rsp+2A8h+var_250]
0x14003be41  mov     [rsp+2A8h+var_188], rax
0x14003be49  test    edi, edi
0x14003be4b  jns     short loc_14003BE9E
0x14003be4d  mov     eax, 8000FFFFh
0x14003be52  cmp     edi, eax
0x14003be54  jnz     short loc_14003BE71
0x14003be56  mov     [rsp+2A8h+var_19C], eax
0x14003be5d  lea     rdx, _TI1J; pThrowInfo
0x14003be64  lea     rcx, [rsp+2A8h+var_19C]; pExceptionObject
0x14003be6c  call    _CxxThrowException_0
0x14003be71  lea     rdx, [rsp+2A8h+var_250]; struct CVssDebugInfo *
0x14003be76  lea     rcx, [rsp+2A8h+var_F8]; this
0x14003be7e  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003be83  lea     r9, aIvsswritercomp_1; "IVssWriterComponents::GetComponent"
0x14003be8a  mov     r8d, edi
0x14003be8d  mov     rdx, rax
0x14003be90  lea     rcx, [rsp+2A8h+var_178]
0x14003be98  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003be9e  cmp     byte ptr [rsp+2A8h+var_1B0+3], bl
0x14003bea5  jz      short loc_14003BECE
0x14003bea7  mov     rdi, rbx
0x14003beaa  mov     rcx, [rsp+rdi*8+2A8h+pv]; pv
0x14003beb2  test    rcx, rcx
0x14003beb5  jz      short loc_14003BEC5
0x14003beb7  call    cs:__imp_CoTaskMemFree
0x14003bebd  mov     [rsp+rdi*8+2A8h+pv], rbx
0x14003bec5  inc     rdi
0x14003bec8  cmp     rdi, 0Fh
0x14003becc  jnz     short loc_14003BEAA
0x14003bece  mov     [rsp+2A8h+bstrString], rbx
0x14003bed3  mov     rcx, [rsp+2A8h+var_268]
0x14003bed8  mov     rax, [rcx]
0x14003bedb  lea     rdx, [rsp+2A8h+bstrString]
0x14003bee0  mov     rax, [rax+28h]
0x14003bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bee9  mov     edi, eax
0x14003beeb  mov     [rsp+2A8h+var_170], eax
0x14003bef2  mov     [rsp+2A8h+var_250], r13
0x14003bef7  lea     rax, aCregistrywrite_6; "CRegistryWriter::OnPrepareBackup"
0x14003befe  mov     [rsp+2A8h+var_248], rax
0x14003bf03  lea     rax, aWrtregrc; "WRTREGRC"
0x14003bf0a  mov     [rsp+2A8h+var_240], rax
0x14003bf0f  mov     [rsp+2A8h+var_238], 129h
0x14003bf17  mov     [rsp+2A8h+var_234], 4
0x14003bf1f  mov     [rsp+2A8h+var_230], 0FFh
0x14003bf27  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003bf32  xor     edx, edx; Val
0x14003bf34  lea     r8d, [rdx+78h]; Size
0x14003bf38  lea     rcx, [rsp+2A8h+pv]; void *
0x14003bf40  call    memset_0
0x14003bf45  lea     rax, [rsp+2A8h+var_250]
0x14003bf4a  mov     [rsp+2A8h+var_1A8], rax
0x14003bf52  test    edi, edi
0x14003bf54  jns     short loc_14003BFA7
0x14003bf56  mov     eax, 8000FFFFh
0x14003bf5b  cmp     edi, eax
0x14003bf5d  jnz     short loc_14003BF7A
0x14003bf5f  mov     [rsp+2A8h+var_198], eax
0x14003bf66  lea     rdx, _TI1J; pThrowInfo
0x14003bf6d  lea     rcx, [rsp+2A8h+var_198]; pExceptionObject
0x14003bf75  call    _CxxThrowException_0
0x14003bf7a  lea     rdx, [rsp+2A8h+var_250]; struct CVssDebugInfo *
0x14003bf7f  lea     rcx, [rsp+2A8h+var_F8]; this
0x14003bf87  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003bf8c  lea     r9, aIvsscomponentG_0; "IVssComponent::GetComponentName"
0x14003bf93  mov     r8d, edi
0x14003bf96  mov     rdx, rax
0x14003bf99  lea     rcx, [rsp+2A8h+var_178]
0x14003bfa1  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003bfa7  cmp     byte ptr [rsp+2A8h+var_1B0+3], bl
0x14003bfae  jz      short loc_14003BFD7
0x14003bfb0  mov     rdi, rbx
0x14003bfb3  mov     rcx, [rsp+rdi*8+2A8h+pv]; pv
0x14003bfbb  test    rcx, rcx
0x14003bfbe  jz      short loc_14003BFCE
0x14003bfc0  call    cs:__imp_CoTaskMemFree
0x14003bfc6  mov     [rsp+rdi*8+2A8h+pv], rbx
0x14003bfce  inc     rdi
0x14003bfd1  cmp     rdi, 0Fh
0x14003bfd5  jnz     short loc_14003BFB3
0x14003bfd7  mov     rdx, [rsp+2A8h+bstrString]
0x14003bfdc  lea     rcx, aRegistry; "Registry"
0x14003bfe3  call    cs:__imp__o__wcsicmp
0x14003bfe9  test    eax, eax
0x14003bfeb  jnz     loc_14003C07D
0x14003bff1  mov     [rsp+2A8h+var_250], r13
0x14003bff6  lea     rax, aCregistrywrite_6; "CRegistryWriter::OnPrepareBackup"
0x14003bffd  mov     [rsp+2A8h+var_248], rax
0x14003c002  lea     rax, aWrtregrc; "WRTREGRC"
0x14003c009  mov     [rsp+2A8h+var_240], rax
0x14003c00e  mov     [rsp+2A8h+var_238], 12Eh
0x14003c016  mov     [rsp+2A8h+var_234], 4
0x14003c01e  mov     [rsp+2A8h+var_230], 0FFh
0x14003c026  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003c031  xor     edx, edx; Val
0x14003c033  lea     r8d, [rdx+78h]; Size
0x14003c037  lea     rcx, [rsp+2A8h+pv]; void *
0x14003c03f  call    memset_0
0x14003c044  lea     r8, aRegistryWriter; "Registry writer 'Registry' component se"...
0x14003c04b  lea     rdx, [rsp+2A8h+var_250]
0x14003c050  lea     rcx, [rsp+2A8h+var_178]
0x14003c058  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003c05d  mov     dword ptr [r14+24h], 1
0x14003c065  mov     rcx, [rsp+2A8h+bstrString]; bstrString
0x14003c06a  call    cs:__imp_SysFreeString
0x14003c070  nop
0x14003c071  lea     rcx, [rsp+2A8h+var_268]
0x14003c076  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x14003c07b  jmp     short loc_14003C0F9
0x14003c07d  mov     rcx, [rsp+2A8h+bstrString]; bstrString
0x14003c082  call    cs:__imp_SysFreeString
0x14003c088  nop
0x14003c089  lea     rcx, [rsp+2A8h+var_268]
0x14003c08e  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x14003c093  inc     esi
0x14003c095  jmp     loc_14003BDB5
0x14003c09a  mov     [rsp+2A8h+var_250], r13
0x14003c09f  mov     [rsp+2A8h+var_248], rsi
0x14003c0a4  mov     [rsp+2A8h+var_240], rdi
0x14003c0a9  mov     [rsp+2A8h+var_238], 136h
0x14003c0b1  mov     [rsp+2A8h+var_234], 4
0x14003c0b9  mov     [rsp+2A8h+var_230], 0FFh
0x14003c0c1  mov     [rsp+2A8h+var_1B0], 1000000h
0x14003c0cc  xor     edx, edx; Val
0x14003c0ce  lea     r8d, [rdx+78h]; Size
0x14003c0d2  lea     rcx, [rsp+2A8h+pv]; void *
0x14003c0da  call    memset_0
0x14003c0df  lea     r8, aNoRegistryWrit; "No Registry writer components selected"
0x14003c0e6  lea     rdx, [rsp+2A8h+var_250]
0x14003c0eb  lea     rcx, [rsp+2A8h+var_178]
0x14003c0f3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003c0f8  nop
  ... truncated ...
```
