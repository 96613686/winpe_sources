# CThumbnailCache::_PerformFullExtractionCore(IShellItem *,uint,uint,WTS_FLAGS,WTS_PRIV_FLAGS,IBitmapResult * *,int *,WTS_ALPHATYPE *,ulong *)

- ea: `0x180011c10`
- end: `0x180012120`
- name: `?_PerformFullExtractionCore@CThumbnailCache@@AEAAJPEAUIShellItem@@IIW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAPEAUIBitmapResult@@PEAHPEAW4WTS_ALPHATYPE@@PEAK@Z`
- size: `1296`
- prototype: ``
- caller_count: `4`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ffcc`
- `0x18001195c`
- `0x18002d090`
- `0x1800429b4`

## callees

- `0x1800021d8`
- `0x180002344`
- `0x18000333c`
- `0x180003510`
- `0x180003624`
- `0x180004614`
- `0x180008480`
- `0x180011c10`
- `0x180012260`
- `0x18001c134`
- `0x18001d264`
- `0x18001f090`
- `0x18001f98c`
- `0x180020094`
- `0x180020154`
- `0x180020244`
- `0x180028358`
- `0x1800283f0`
- `0x180029c04`
- `0x18002a900`
- `0x18002aa78`
- `0x18002afc8`
- `0x18002b11c`
- `0x18002b628`
- `0x18002d630`
- `0x180030984`
- `0x180031e04`
- `0x180035830`
- `0x180035c48`
- `0x180035dbc`
- `0x180035e24`
- `0x18004097c`
- `0x1800409dc`
- `0x180040c50`
- `0x180046758`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120ee`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800120e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800120e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011d2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011fc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011d2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011fc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CThumbnailCache::_PerformFullExtractionCore(
        CThumbnailCache *a1,
        struct IShellItem *a2,
        int a3,
        LONG a4,
        enum WTS_FLAGS a5,
        unsigned int a6,
        struct _GUID *a7,
        int *a8,
        enum WTS_ALPHATYPE *a9,
        unsigned int *a10)
{
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  signed __int32 v17; // ebx
  __int64 v18; // rcx
  char v19; // r14
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // eax
  ULONGLONG v25; // rdi
  ULONGLONG v26; // r15
  struct ThumbnailTelemetryAggregator *GlobalTelemetryAggregator; // rbx
  struct ISharedBitmap *v28; // rdx
  void **v29; // r9
  ULONGLONG v30; // rsi
  struct ThumbnailTelemetryAggregator *v31; // rdi
  unsigned int v32; // ebx
  void *v34; // rdx
  HANDLE Semaphore; // rbx
  unsigned int v36; // r8d
  const char *v37; // r9
  ULONGLONG TickCount64; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  CThumbnailCache *v40; // [rsp+68h] [rbp-98h]
  _BYTE v41[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v42; // [rsp+90h] [rbp-70h]
  int *v43; // [rsp+98h] [rbp-68h]
  char v44; // [rsp+A0h] [rbp-60h]
  int Surrogate; // [rsp+A8h] [rbp-58h] BYREF
  Windows::Internal::Thumbnails *v46; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v47; // [rsp+B8h] [rbp-48h] BYREF
  struct tagSIZE v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  IUnknown *punk; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v51[24]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v52[42]; // [rsp+F0h] [rbp-10h] BYREF
  HBITMAP ho[2]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  LODWORD(v46) = a3;
  v40 = a1;
  *(_QWORD *)&a7->Data1 = 0;
  if ( a10 )
    *a10 = 0;
  Surrogate = 0;
  if ( (*((_BYTE *)a1 + 768) & 4) != 0 )
  {
    v46 = 0;
    v48.cx = a4;
    v48.cy = a4;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    v13 = FullExtract(a2, v48, &v46);
    Surrogate = v13;
    if ( v13 < 0 )
    {
      if ( (byte_180062901 & 2) != 0 )
      {
        McTemplateU0d_EventWriteTransfer(v15, v14, (unsigned int)v13);
        v13 = Surrogate;
      }
      if ( _IsUnrecoverableError(v13) )
        Surrogate = -2147175936;
    }
    else
    {
      v47 = 0;
      Surrogate = (*(__int64 (__fastcall **)(Windows::Internal::Thumbnails *, unsigned int *))(*(_QWORD *)v46 + 88LL))(
                    v46,
                    &v47);
      if ( Surrogate >= 0 )
      {
        Surrogate = Microsoft::WRL::ComPtr<IBitmapResult>::CopyTo(&v46, v16, a7);
        if ( Surrogate >= 0 )
          *a9 = (v47 != 0) + 1;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  }
  else
  {
    TickCount64 = GetTickCount64();
    if ( dword_180062C98 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180062C98);
      if ( dword_180062C98 == -1 )
      {
        Semaphore = CreateSemaphoreExW(0, 10, 10, 0, 0, 0x1F0003u);
        if ( !Semaphore )
          wil::details::in1diag3::FailFast_GetLastError(retaddr, v34, v36, v37);
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          &hHandle,
          Semaphore);
        atexit(CThumbnailCache::_PerformFullExtractionCore_::_21_::_dynamic_atexit_destructor_for__s_semaphoreMaxSimultaneousExtractions__);
        Init_thread_footer(&dword_180062C98);
      }
    }
    v17 = _InterlockedExchangeAdd(&dword_180062A70, 1u);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v52,
      "PerformFullExtractionCore");
    v52[0] = &ThumbnailCacheTelemetry::PerformFullExtractionCore::`vftable';
    ThumbnailCacheTelemetry::PerformFullExtractionCore::StartActivity(
      (ThumbnailCacheTelemetry::PerformFullExtractionCore *)v52,
      a2,
      0,
      v17 + 1);
    v42 = v52;
    v43 = &Surrogate;
    v44 = 1;
    _acquire___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_failfast_policy_3__wil__QEAA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      v18,
      &v39);
    if ( v39 )
    {
      Surrogate = 0;
      v48 = 0;
      Surrogate = CThumbnailCache::_GetSurrogate(a1, a5, (LPVOID *)&v48);
      if ( Surrogate >= 0 )
      {
        CThumbnailCache::TryGetFileExtension(&v49, a2);
        v19 = 0;
        CRPCTimeout::CRPCTimeout((CRPCTimeout *)v51);
        if ( (a5 & 0x400) == 0 )
          CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v51);
        punk = 0;
        v47 = 0;
        v20 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD))InitExtractor)(
                v48,
                (unsigned int)a5,
                a6,
                a2,
                a4,
                (_DWORD)v46,
                &v47,
                a8,
                &punk);
        v23 = (unsigned int)v20;
        Surrogate = v20;
        if ( v20 < 0
          || (ho[0] = 0,
              v24 = RunExtractor(punk, v47, a5, ho, a9, a8, a10),
              v23 = (unsigned int)v24,
              Surrogate = v24,
              v24 < 0) )
        {
          v26 = TickCount64;
        }
        else
        {
          v25 = GetTickCount64();
          v19 = 1;
          if ( v49 )
          {
            GlobalTelemetryAggregator = ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator();
            std::wstring::wstring(v41, v49);
            v26 = TickCount64;
            ThumbnailTelemetryAggregator::AddSuccessSample(GlobalTelemetryAggregator, v41, v25 - TickCount64);
            std::wstring::~wstring(v41);
          }
          else
          {
            v26 = TickCount64;
          }
          v46 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          Surrogate = CSharedBitmap::CreateInstance(
                        ho[0],
                        *a9,
                        0,
                        &GUID_091162a4_bc96_411f_aae8_c5122cd03363,
                        (void **)&v46);
          if ( Surrogate >= 0 )
            Surrogate = Windows::Internal::Thumbnails::CreateBitmapResult(v46, v28, a7, v29);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          v23 = (unsigned int)Surrogate;
        }
        if ( (int)v23 < 0 )
        {
          if ( v51[4] )
          {
            if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(v23, &Thumbnails_ExtractionTimeout_Info, v22, 1, ho);
            v23 = 2147791361LL;
            Surrogate = -2147175935;
          }
          if ( (byte_180062901 & 2) != 0 )
          {
            McTemplateU0d_EventWriteTransfer(v23, v21, (unsigned int)v23);
            LODWORD(v23) = Surrogate;
          }
          if ( _IsUnrecoverableError(v23) )
          {
            LODWORD(v23) = -2147175936;
            Surrogate = -2147175936;
          }
          if ( !v19 )
          {
            v30 = GetTickCount64();
            if ( v49 )
            {
              v31 = ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator();
              v32 = Surrogate;
              std::wstring::wstring(v41, v49);
              ThumbnailTelemetryAggregator::AddFailureSample(v31, v41, v30 - v26, v32);
              std::wstring::~wstring(v41);
            }
            LODWORD(v23) = Surrogate;
          }
        }
        CThumbnailCache::_ResetSurrogate(v40, v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&punk);
        CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v51);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    }
    else
    {
      Surrogate = -2147175935;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v39);
    ThumbnailCacheTelemetry::PerformFullExtractionCore::Stop(
      (ThumbnailCacheTelemetry::PerformFullExtractionCore *)v52,
      Surrogate,
      _InterlockedDecrement(&dword_180062A70));
    ThumbnailCacheTelemetry::PerformFullExtractionCore::~PerformFullExtractionCore((ThumbnailCacheTelemetry::PerformFullExtractionCore *)v52);
  }
  return (unsigned int)Surrogate;
}

```

## disassembly

```asm
0x180011c10  push    rbp
0x180011c12  push    rbx
0x180011c13  push    rsi
0x180011c14  push    rdi
0x180011c15  push    r12
0x180011c17  push    r13
0x180011c19  push    r14
0x180011c1b  push    r15
0x180011c1d  lea     rbp, [rsp-168h]
0x180011c25  sub     rsp, 268h
0x180011c2c  mov     rax, cs:__security_cookie
0x180011c33  xor     rax, rsp
0x180011c36  mov     [rbp+1A0h+var_50], rax
0x180011c3d  mov     esi, r9d
0x180011c40  mov     dword ptr [rbp+1A0h+var_1F0], r8d
0x180011c44  mov     rdi, rdx
0x180011c47  mov     r14, rcx
0x180011c4a  mov     [rsp+2A0h+var_238], rcx
0x180011c4f  mov     r13, [rbp+1A0h+arg_30]
0x180011c56  mov     rax, [rbp+1A0h+arg_38]
0x180011c5d  mov     [rsp+2A0h+var_248], rax
0x180011c62  mov     r12, [rbp+1A0h+arg_40]
0x180011c69  mov     r15, [rbp+1A0h+arg_48]
0x180011c70  xor     ebx, ebx
0x180011c72  mov     [r13+0], rbx
0x180011c76  test    r15, r15
0x180011c79  jz      short loc_180011C7E
0x180011c7b  mov     [r15], ebx
0x180011c7e  mov     [rbp+1A0h+var_1F8], ebx
0x180011c81  test    byte ptr [rcx+300h], 4
0x180011c88  jz      loc_180011D2F
0x180011c8e  mov     [rbp+1A0h+var_1F0], rbx
0x180011c92  mov     [rbp+1A0h+var_1E0.cx], esi
0x180011c95  mov     [rbp+1A0h+var_1E0.cy], esi
0x180011c98  lea     rcx, [rbp+1A0h+var_1F0]
0x180011c9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ca1  lea     r8, [rbp+1A0h+var_1F0]; struct IBitmapResult **
0x180011ca5  mov     rdx, qword ptr [rbp+1A0h+var_1E0.cx]; struct tagSIZE
0x180011ca9  mov     rcx, rdi; struct IShellItem *
0x180011cac  call    ?FullExtract@@YAJPEAUIShellItem@@UtagSIZE@@PEAPEAUIBitmapResult@@@Z; FullExtract(IShellItem *,tagSIZE,IBitmapResult * *)
0x180011cb1  mov     [rbp+1A0h+var_1F8], eax
0x180011cb4  test    eax, eax
0x180011cb6  js      short loc_180011CFA
0x180011cb8  mov     [rbp+1A0h+var_1E8], ebx
0x180011cbb  mov     rcx, [rbp+1A0h+var_1F0]
0x180011cbf  mov     rax, [rcx]
0x180011cc2  lea     rdx, [rbp+1A0h+var_1E8]
0x180011cc6  mov     rax, [rax+58h]
0x180011cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ccf  mov     [rbp+1A0h+var_1F8], eax
0x180011cd2  test    eax, eax
0x180011cd4  js      short loc_180011D21
0x180011cd6  mov     r8, r13
0x180011cd9  lea     rcx, [rbp+1A0h+var_1F0]
0x180011cdd  call    ?CopyTo@?$ComPtr@UIBitmapResult@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IBitmapResult>::CopyTo(_GUID const &,void * *)
0x180011ce2  mov     [rbp+1A0h+var_1F8], eax
0x180011ce5  test    eax, eax
0x180011ce7  js      short loc_180011D21
0x180011ce9  mov     eax, [rbp+1A0h+var_1E8]
0x180011cec  neg     eax
0x180011cee  sbb     ecx, ecx
0x180011cf0  neg     ecx
0x180011cf2  inc     ecx
0x180011cf4  mov     [r12], ecx
0x180011cf8  jmp     short loc_180011D21
0x180011cfa  test    cs:byte_180062901, 2
0x180011d01  jz      short loc_180011D0E
0x180011d03  mov     r8d, eax
0x180011d06  call    McTemplateU0d_EventWriteTransfer
0x180011d0b  mov     eax, [rbp+1A0h+var_1F8]
0x180011d0e  mov     ecx, eax; int
0x180011d10  call    ?_IsUnrecoverableError@@YA_NJ@Z; _IsUnrecoverableError(long)
0x180011d15  test    al, al
0x180011d17  jz      short loc_180011D21
0x180011d19  mov     ecx, 8004B200h
0x180011d1e  mov     [rbp+1A0h+var_1F8], ecx
0x180011d21  lea     rcx, [rbp+1A0h+var_1F0]
0x180011d25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d2a  jmp     loc_18001207C
0x180011d2f  call    cs:__imp_GetTickCount64
0x180011d35  mov     [rsp+2A0h+var_250], rax
0x180011d3a  mov     edx, cs:_tls_index
0x180011d40  mov     rcx, gs:58h
0x180011d49  mov     eax, 4
0x180011d4e  mov     rcx, [rcx+rdx*8]
0x180011d52  mov     ecx, [rax+rcx]
0x180011d55  cmp     cs:dword_180062C98, ecx
0x180011d5b  jg      loc_1800120AF
0x180011d61  mov     ebx, 1
0x180011d66  lock xadd cs:dword_180062A70, ebx
0x180011d6e  lea     rdx, aPerformfullext; "PerformFullExtractionCore"
0x180011d75  lea     rcx, [rbp+1A0h+var_1B0]
0x180011d79  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011d7e  lea     rax, ??_7PerformFullExtractionCore@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::PerformFullExtractionCore::`vftable'
0x180011d85  mov     [rbp+1A0h+var_1B0], rax
0x180011d89  lea     r9d, [rbx+1]; int
0x180011d8d  xor     r8d, r8d; bool
0x180011d90  mov     rdx, rdi; void *
0x180011d93  lea     rcx, [rbp+1A0h+var_1B0]; this
0x180011d97  call    ?StartActivity@PerformFullExtractionCore@ThumbnailCacheTelemetry@@QEAAXPEAX_NJ@Z; ThumbnailCacheTelemetry::PerformFullExtractionCore::StartActivity(void *,bool,long)
0x180011d9c  nop
0x180011d9d  lea     rax, [rbp+1A0h+var_1B0]
0x180011da1  mov     [rbp+1A0h+var_210], rax
0x180011da5  lea     rax, [rbp+1A0h+var_1F8]
0x180011da9  mov     [rbp+1A0h+var_208], rax
0x180011dad  mov     [rbp+1A0h+var_200], 1
0x180011db1  lea     rdx, [rsp+2A0h+var_240]
0x180011db6  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_failfast_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011dbb  nop
0x180011dbc  xor     eax, eax
0x180011dbe  cmp     [rsp+2A0h+var_240], rax
0x180011dc3  jz      loc_180012043
0x180011dc9  mov     [rbp+1A0h+var_1F8], eax
0x180011dcc  mov     qword ptr [rbp+1A0h+var_1E0.cx], rax
0x180011dd0  lea     r8, [rbp+1A0h+var_1E0]; struct ICreateObject **
0x180011dd4  mov     ebx, [rbp+1A0h+arg_20]
0x180011dda  mov     edx, ebx; enum WTS_FLAGS
0x180011ddc  mov     rcx, r14; this
0x180011ddf  call    ?_GetSurrogate@CThumbnailCache@@AEAAJW4WTS_FLAGS@@PEAPEAUICreateObject@@@Z; CThumbnailCache::_GetSurrogate(WTS_FLAGS,ICreateObject * *)
0x180011de4  mov     [rbp+1A0h+var_1F8], eax
0x180011de7  test    eax, eax
0x180011de9  js      loc_180012038
0x180011def  mov     rdx, rdi
0x180011df2  lea     rcx, [rbp+1A0h+var_1D8]
0x180011df6  call    ?TryGetFileExtension@CThumbnailCache@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@@Z; CThumbnailCache::TryGetFileExtension(IShellItem *)
0x180011dfb  nop
0x180011dfc  xor     r14b, r14b
0x180011dff  lea     rcx, [rbp+1A0h+var_1C8]; this
0x180011e03  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180011e08  nop
0x180011e09  bt      ebx, 0Ah
0x180011e0d  jb      short loc_180011E18
0x180011e0f  lea     rcx, [rbp+1A0h+var_1C8]; this
0x180011e13  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180011e18  mov     [rbp+1A0h+punk], 0
0x180011e20  mov     [rbp+1A0h+var_1E8], 0
0x180011e27  lea     rax, [rbp+1A0h+punk]
0x180011e2b  mov     [rsp+2A0h+var_260], rax
0x180011e30  mov     rax, [rsp+2A0h+var_248]
0x180011e35  mov     [rsp+2A0h+var_268], rax
0x180011e3a  lea     rax, [rbp+1A0h+var_1E8]
0x180011e3e  mov     [rsp+2A0h+var_270], rax
0x180011e43  mov     eax, dword ptr [rbp+1A0h+var_1F0]
0x180011e46  mov     [rsp+2A0h+dwDesiredAccess], eax
0x180011e4a  mov     [rsp+2A0h+dwFlags], esi
0x180011e4e  mov     r9, rdi
0x180011e51  mov     r8d, [rbp+1A0h+arg_28]
0x180011e58  mov     edx, ebx
0x180011e5a  mov     rcx, qword ptr [rbp+1A0h+var_1E0.cx]
0x180011e5e  call    ?InitExtractor@@YAJPEAUICreateObject@@W4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAUIShellItem@@IIPEAIPEAHPEAPEAUIUnknown@@@Z; InitExtractor(ICreateObject *,WTS_FLAGS,WTS_PRIV_FLAGS,IShellItem *,uint,uint,uint *,int *,IUnknown * *)
0x180011e63  mov     ecx, eax
0x180011e65  mov     [rbp+1A0h+var_1F8], eax
0x180011e68  xor     esi, esi
0x180011e6a  test    eax, eax
0x180011e6c  js      loc_180011F55
0x180011e72  mov     [rbp+1A0h+ho], rsi
0x180011e79  mov     [rsp+2A0h+var_270], r15; unsigned int *
0x180011e7e  mov     rax, [rsp+2A0h+var_248]
0x180011e83  mov     qword ptr [rsp+2A0h+dwDesiredAccess], rax; int *
0x180011e88  mov     qword ptr [rsp+2A0h+dwFlags], r12; enum WTS_ALPHATYPE *
0x180011e8d  lea     r9, [rbp+1A0h+ho]; HBITMAP *
0x180011e94  mov     r8d, ebx; enum WTS_FLAGS
0x180011e97  mov     edx, [rbp+1A0h+var_1E8]; unsigned int
0x180011e9a  mov     rcx, [rbp+1A0h+punk]; punk
0x180011e9e  call    ?RunExtractor@@YAJPEAUIUnknown@@IW4WTS_FLAGS@@PEAPEAUHBITMAP__@@PEAW4WTS_ALPHATYPE@@PEAHPEAK@Z; RunExtractor(IUnknown *,uint,WTS_FLAGS,HBITMAP__ * *,WTS_ALPHATYPE *,int *,ulong *)
0x180011ea3  mov     ecx, eax
0x180011ea5  mov     [rbp+1A0h+var_1F8], eax
0x180011ea8  test    eax, eax
0x180011eaa  js      loc_180011F55
0x180011eb0  call    cs:__imp_GetTickCount64
0x180011eb6  mov     rdi, rax
0x180011eb9  mov     r14b, 1
0x180011ebc  cmp     [rbp+1A0h+var_1D8], rsi
0x180011ec0  jnz     short loc_180011EC9
0x180011ec2  mov     r15, [rsp+2A0h+var_250]
0x180011ec7  jmp     short loc_180011F01
0x180011ec9  call    ?GetGlobalTelemetryAggregator@ThumbnailTelemetryAggregator@@SAAEAV1@XZ; ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator(void)
0x180011ece  mov     rbx, rax
0x180011ed1  mov     rdx, [rbp+1A0h+var_1D8]
0x180011ed5  lea     rcx, [rsp+2A0h+var_230]
0x180011eda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011edf  mov     r15, [rsp+2A0h+var_250]
0x180011ee4  sub     rdi, r15
0x180011ee7  mov     r8, rdi
0x180011eea  lea     rdx, [rsp+2A0h+var_230]
0x180011eef  mov     rcx, rbx
0x180011ef2  call    ?AddSuccessSample@ThumbnailTelemetryAggregator@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; ThumbnailTelemetryAggregator::AddSuccessSample(std::wstring const &,unsigned __int64)
0x180011ef7  lea     rcx, [rsp+2A0h+var_230]
0x180011efc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f01  mov     [rbp+1A0h+var_1F0], rsi
0x180011f05  lea     rcx, [rbp+1A0h+var_1F0]
0x180011f09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f0e  lea     rax, [rbp+1A0h+var_1F0]
0x180011f12  mov     qword ptr [rsp+2A0h+dwFlags], rax; void **
0x180011f17  lea     r9, _GUID_091162a4_bc96_411f_aae8_c5122cd03363; struct _GUID *
0x180011f1e  xor     r8d, r8d; struct CGlobalRefCount *
0x180011f21  mov     edx, [r12]; enum WTS_ALPHATYPE
0x180011f25  mov     rcx, [rbp+1A0h+ho]; ho
0x180011f2c  call    ?CreateInstance@CSharedBitmap@@SAJPEAUHBITMAP__@@W4WTS_ALPHATYPE@@PEAVCGlobalRefCount@@AEBU_GUID@@PEAPEAX@Z; CSharedBitmap::CreateInstance(HBITMAP__ *,WTS_ALPHATYPE,CGlobalRefCount *,_GUID const &,void * *)
0x180011f31  mov     [rbp+1A0h+var_1F8], eax
0x180011f34  test    eax, eax
0x180011f36  js      short loc_180011F47
0x180011f38  mov     r8, r13; struct _GUID *
0x180011f3b  mov     rcx, [rbp+1A0h+var_1F0]; this
0x180011f3f  call    ?CreateBitmapResult@Thumbnails@Internal@Windows@@YAJPEAUISharedBitmap@@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::Thumbnails::CreateBitmapResult(ISharedBitmap *,_GUID const &,void * *)
0x180011f44  mov     [rbp+1A0h+var_1F8], eax
0x180011f47  lea     rcx, [rbp+1A0h+var_1F0]
0x180011f4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f50  mov     ecx, [rbp+1A0h+var_1F8]
0x180011f53  jmp     short loc_180011F5A
0x180011f55  mov     r15, [rsp+2A0h+var_250]
0x180011f5a  test    ecx, ecx
0x180011f5c  jns     loc_18001200D
0x180011f62  cmp     [rbp+1A0h+var_1C4], sil
0x180011f66  jz      short loc_180011F97
0x180011f68  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180011f6f  jz      short loc_180011F8F
0x180011f71  lea     rax, [rbp+1A0h+ho]
0x180011f78  mov     qword ptr [rsp+2A0h+dwFlags], rax
0x180011f7d  mov     r9d, 1
0x180011f83  lea     rdx, Thumbnails_ExtractionTimeout_Info
0x180011f8a  call    McGenEventWrite_EventWriteTransfer
0x180011f8f  mov     ecx, 8004B201h
0x180011f94  mov     [rbp+1A0h+var_1F8], ecx
0x180011f97  test    cs:byte_180062901, 2
0x180011f9e  jz      short loc_180011FAB
0x180011fa0  mov     r8d, ecx
0x180011fa3  call    McTemplateU0d_EventWriteTransfer
0x180011fa8  mov     ecx, [rbp+1A0h+var_1F8]; int
0x180011fab  call    ?_IsUnrecoverableError@@YA_NJ@Z; _IsUnrecoverableError(long)
0x180011fb0  test    al, al
0x180011fb2  jz      short loc_180011FBC
0x180011fb4  mov     ecx, 8004B200h
0x180011fb9  mov     [rbp+1A0h+var_1F8], ecx
0x180011fbc  test    r14b, r14b
0x180011fbf  jnz     short loc_18001200D
0x180011fc1  call    cs:__imp_GetTickCount64
0x180011fc7  mov     rsi, rax
0x180011fca  cmp     [rbp+1A0h+var_1D8], 0
0x180011fcf  jz      short loc_18001200A
0x180011fd1  call    ?GetGlobalTelemetryAggregator@ThumbnailTelemetryAggregator@@SAAEAV1@XZ; ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator(void)
0x180011fd6  mov     rdi, rax
0x180011fd9  mov     ebx, [rbp+1A0h+var_1F8]
0x180011fdc  mov     rdx, [rbp+1A0h+var_1D8]
0x180011fe0  lea     rcx, [rsp+2A0h+var_230]
0x180011fe5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011fea  sub     rsi, r15
0x180011fed  mov     r9d, ebx
0x180011ff0  mov     r8, rsi
0x180011ff3  lea     rdx, [rsp+2A0h+var_230]
0x180011ff8  mov     rcx, rdi
0x180011ffb  call    ?AddFailureSample@ThumbnailTelemetryAggregator@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KJ@Z; ThumbnailTelemetryAggregator::AddFailureSample(std::wstring const &,unsigned __int64,long)
0x180012000  lea     rcx, [rsp+2A0h+var_230]
0x180012005  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001200a  mov     ecx, [rbp+1A0h+var_1F8]
0x18001200d  mov     edx, ecx; int
0x18001200f  mov     rcx, [rsp+2A0h+var_238]; this
0x180012014  call    ?_ResetSurrogate@CThumbnailCache@@AEAAJJ@Z; CThumbnailCache::_ResetSurrogate(long)
0x180012019  nop
0x18001201a  lea     rcx, [rbp+1A0h+punk]
0x18001201e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012023  nop
0x180012024  lea     rcx, [rbp+1A0h+var_1C8]; this
0x180012028  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18001202d  nop
0x18001202e  lea     rcx, [rbp+1A0h+var_1D8]
0x180012032  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012037  nop
0x180012038  lea     rcx, [rbp+1A0h+var_1E0]
0x18001203c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012041  jmp     short loc_18001204B
0x180012043  mov     ecx, 8004B201h
0x180012048  mov     [rbp+1A0h+var_1F8], ecx
0x18001204b  lea     rcx, [rsp+2A0h+var_240]
0x180012050  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012055  nop
0x180012056  or      r8d, 0FFFFFFFFh
0x18001205a  lock xadd cs:dword_180062A70, r8d
0x180012063  dec     r8d; unsigned int
0x180012066  mov     edx, [rbp+1A0h+var_1F8]; int
0x180012069  lea     rcx, [rbp+1A0h+var_1B0]; this
0x18001206d  call    ?Stop@PerformFullExtractionCore@ThumbnailCacheTelemetry@@QEAAXJI@Z; ThumbnailCacheTelemetry::PerformFullExtractionCore::Stop(long,uint)
0x180012072  nop
0x180012073  lea     rcx, [rbp+1A0h+var_1B0]; this
0x180012077  call    ??1PerformFullExtractionCore@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::PerformFullExtractionCore::~PerformFullExtractionCore(void)
0x18001207c  mov     eax, [rbp+1A0h+var_1F8]
0x18001207f  mov     rcx, [rbp+1A0h+var_50]
0x180012086  xor     rcx, rsp; StackCookie
0x180012089  call    __security_check_cookie
0x18001208e  add     rsp, 268h
0x180012095  pop     r15
0x180012097  pop     r14
0x180012099  pop     r13
0x18001209b  pop     r12
0x18001209d  pop     rdi
0x18001209e  pop     rsi
0x18001209f  pop     rbx
0x1800120a0  pop     rbp
0x1800120a1  retn
0x1800120a2  mov     rcx, [rbp+1A8h]; this
  ... truncated ...
```
