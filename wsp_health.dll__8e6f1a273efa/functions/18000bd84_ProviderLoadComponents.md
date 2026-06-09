# ProviderLoadComponents

- ea: `0x18000bd84`
- end: `0x18000c1ba`
- name: `ProviderLoadComponents`
- size: `1078`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b5d0`

## callees

- `0x180001010`
- `0x1800010f8`
- `0x1800011a0`
- `0x180002b50`
- `0x180002f70`
- `0x18000baec`
- `0x18000bb44`
- `0x18000bb64`
- `0x18000bb84`
- `0x18000bc64`
- `0x18000bd2c`
- `0x18000bd58`
- `0x18000bd84`
- `0x18000cbfc`
- `0x18000cee0`
- `0x18000d184`
- `0x18000df3c`
- `0x18001abe0`
- `0x180022230`
- `0x180034fd0`
- `0x18003c294`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c122`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c122`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bdc8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bdc8`

## string_xrefs

- `0x18000be67`: `ProviderLoadComponents`
- `0x18000be95`: `ProviderLoadComponents`
- `0x18000c155`: `ProviderLoadComponents`
- `0x18000c11b`: `StorageWMI.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ProviderLoadComponents(int a1, __int64 a2, int a3, int a4)
{
  unsigned int v4; // esi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  char *v10; // rcx
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v27; // [rsp+40h] [rbp-A8h] BYREF
  int v28; // [rsp+44h] [rbp-A4h] BYREF
  const char *v29; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v30; // [rsp+50h] [rbp-98h]
  const char *v31; // [rsp+58h] [rbp-90h] BYREF
  std::_Ref_count_base *v32; // [rsp+60h] [rbp-88h]
  std::_Ref_count_base *v33[2]; // [rsp+68h] [rbp-80h] BYREF
  __int128 v34; // [rsp+78h] [rbp-70h]
  int v35; // [rsp+88h] [rbp-60h] BYREF
  char v36; // [rsp+8Ch] [rbp-5Ch]
  GUID v37; // [rsp+90h] [rbp-58h] BYREF

  v4 = 0;
  v35 = 0;
  v36 = 0;
  if ( (unsigned int)dword_18014D6A8 <= 5 )
    v37 = 0;
  else
    EventActivityIdControl(3u, &v37);
  v35 = 1;
  if ( (unsigned int)dword_18014D6A8 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18014D6A8,
      &byte_18012AE7F,
      &v37,
      0);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v27 = 47;
    v29 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18012AE51,
      a3,
      a4,
      (__int64)&v29,
      (__int64)&v27);
  }
  try
  {
    *(_OWORD *)v33 = 0;
    v31 = (const char *)operator new(0x90u);
    v5 = cxl::ExceptionManager::ExceptionManager(v31);
    v29 = 0;
    std::unique_ptr<cxl::ExceptionManager>::reset(v6, v5);
    std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(&v29);
    v31 = (const char *)operator new(0x140u);
    v7 = cxl::TraceManager::TraceManager(v31);
    v29 = 0;
    std::unique_ptr<cxl::TraceManager>::reset(v8, v7);
    std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(&v29);
    v9 = g_ptrTraceMgr;
    cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(&v31, g_ptrTraceMgr + 264);
    *(_QWORD *)(v9 + 208) = ClusWmi::TraceLogRoutine;
    *(_QWORD *)(v9 + 216) = 0;
    cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(&v31);
    v10 = (char *)operator new(0x18u);
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<Wsp::MiSpace>::`vftable';
    *((_QWORD *)v10 + 2) = &Wsp::MiSpace::`vftable';
    v31 = v10 + 16;
    v32 = (std::_Ref_count_base *)v10;
    v34 = 0;
    v11 = Wsp::MiSpaceAdapter::Create(&v29, &v31);
    std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(&g_ptrMiSpaceAdapter, v11);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    v14 = (int)v32;
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    if ( g_ptrMiSpaceAdapter )
    {
      v15 = std::make_shared<ClusApi::ClusterApiFactory,>(&v31);
      v16 = *(std::_Ref_count_base **)v15;
      v17 = *(std::_Ref_count_base **)(v15 + 8);
      *(_QWORD *)v15 = 0;
      *(_QWORD *)(v15 + 8) = 0;
      v33[0] = v16;
      v33[1] = v17;
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
      v18 = smapi::LogWriter::CreateInstance(&v29);
      v19 = ClusWmi::DataStore::OpenStore(&v31, v33, v18);
      std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(&g_ptrDataStore, v19);
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
      v22 = (int)v30;
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      if ( g_ptrDataStore )
      {
        g_storageWMIResource = LoadLibraryExW(L"StorageWMI.dll", 0, 0x802u);
        if ( v33[1] )
          std::_Ref_count_base::_Decref(v33[1]);
      }
      else
      {
        v4 = 1;
        if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v28 = 1;
          v27 = 77;
          v29 = "ProviderLoadComponents";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&byte_18012ADDF,
            v20,
            v21,
            (__int64)&v29,
            (__int64)&v27,
            (__int64)&v28);
        }
        if ( v33[1] )
          std::_Ref_count_base::_Decref(v33[1]);
      }
    }
    else
    {
      v4 = 27;
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v27 = 27;
        v28 = 59;
        v29 = "ProviderLoadComponents";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&unk_18012AE18,
          v12,
          v13,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27);
      }
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v35);
  }
  catch ( ... )
  {
    LODWORD(v29) = 1;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v28 = 1;
      v27 = 88;
      v31 = "ProviderLoadComponents";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&word_18012ADA6,
        v24,
        v25,
        (__int64)&v31,
        (__int64)&v27,
        (__int64)&v28);
    }
    v4 = (unsigned int)v29;
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v29) = 92;
    v31 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18014D6A8,
      (unsigned int)byte_18012AD79,
      v24,
      v25,
      (__int64)&v31,
      (__int64)&v29);
  }
  return v4;
}

```

## disassembly

```asm
0x18000bd84  mov     r11, rsp
0x18000bd87  push    rbx
0x18000bd88  push    rsi
0x18000bd89  push    rdi
0x18000bd8a  push    r14
0x18000bd8c  push    r15
0x18000bd8e  sub     rsp, 0C0h
0x18000bd95  mov     rax, cs:__security_cookie
0x18000bd9c  xor     rax, rsp
0x18000bd9f  mov     [rsp+0E8h+var_38], rax
0x18000bda7  xor     r14d, r14d
0x18000bdaa  mov     esi, r14d
0x18000bdad  mov     [r11-60h], r14d
0x18000bdb1  mov     [r11-5Ch], r14b
0x18000bdb5  mov     eax, cs:dword_18014D6A8
0x18000bdbb  cmp     eax, 5
0x18000bdbe  jbe     short loc_18000BDD6
0x18000bdc0  lea     rdx, [r11-58h]; ActivityId
0x18000bdc4  lea     ecx, [r14+3]; ControlCode
0x18000bdc8  call    cs:__imp_EventActivityIdControl
0x18000bdcf  nop     dword ptr [rax+rax+00h]
0x18000bdd4  jmp     short loc_18000BDE1
0x18000bdd6  xorps   xmm0, xmm0
0x18000bdd9  movups  [rsp+0E8h+var_58], xmm0
0x18000bde1  mov     r15d, 1
0x18000bde7  mov     [rsp+0E8h+var_60], r15d
0x18000bdef  mov     eax, cs:dword_18014D6A8
0x18000bdf5  cmp     eax, 5
0x18000bdf8  jbe     short loc_18000BE54
0x18000bdfa  cmp     [rsp+0E8h+var_5C], r14b
0x18000be02  jz      short loc_18000BE36
0x18000be04  cmp     [rsp+0E8h+var_48], r14d
0x18000be0c  jnz     short loc_18000BE2C
0x18000be0e  cmp     [rsp+0E8h+var_44], r14d
0x18000be16  jnz     short loc_18000BE2C
0x18000be18  cmp     [rsp+0E8h+var_40], r14d
0x18000be20  jnz     short loc_18000BE2C
0x18000be22  cmp     [rsp+0E8h+var_3C], r14d
0x18000be2a  jz      short loc_18000BE36
0x18000be2c  lea     r9, [rsp+0E8h+var_48]
0x18000be34  jmp     short loc_18000BE39
0x18000be36  mov     r9, r14
0x18000be39  lea     r8, [rsp+0E8h+var_58]
0x18000be41  lea     rdx, byte_18012AE7F
0x18000be48  lea     rcx, dword_18014D6A8
0x18000be4f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000be54  mov     eax, cs:dword_18014D6A8
0x18000be5a  cmp     eax, 5
0x18000be5d  jbe     short loc_18000BE95
0x18000be5f  mov     [rsp+0E8h+var_A8], 2Fh ; '/'
0x18000be67  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000be6e  mov     [rsp+0E8h+var_A0], rdi
0x18000be73  lea     rax, [rsp+0E8h+var_A8]
0x18000be78  mov     [rsp+0E8h+var_C0], rax
0x18000be7d  lea     rax, [rsp+0E8h+var_A0]
0x18000be82  mov     [rsp+0E8h+var_C8], rax
0x18000be87  lea     rdx, byte_18012AE51
0x18000be8e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000be93  jmp     short loc_18000BE9C
0x18000be95  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000be9c  xorps   xmm0, xmm0
0x18000be9f  movdqu  xmmword ptr [rsp+0E8h+var_80], xmm0
0x18000bea5  mov     ecx, 90h; Size
0x18000beaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000beaf  mov     [rsp+0E8h+var_90], rax
0x18000beb4  mov     rcx, rax
0x18000beb7  call    ??0ExceptionManager@cxl@@QEAA@HW4Enum@CatchUnhandledExceptions@@@Z; cxl::ExceptionManager::ExceptionManager(int,CatchUnhandledExceptions::Enum)
0x18000bebc  nop
0x18000bebd  mov     [rsp+0E8h+var_A0], r14
0x18000bec2  mov     rdx, rax
0x18000bec5  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000beca  lea     rcx, [rsp+0E8h+var_A0]
0x18000becf  call    ??1?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(void)
0x18000bed4  mov     ecx, 140h; Size
0x18000bed9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bede  mov     [rsp+0E8h+var_90], rax
0x18000bee3  mov     rcx, rax
0x18000bee6  call    ??0TraceManager@cxl@@QEAA@HP6AXHPEB_W_KPEAX@Z2W4Enum@DoRealTracing@@@Z; cxl::TraceManager::TraceManager(int,void (*)(int,wchar_t const *,unsigned __int64,void *),void *,DoRealTracing::Enum)
0x18000beeb  nop
0x18000beec  mov     [rsp+0E8h+var_A0], r14
0x18000bef1  mov     rdx, rax
0x18000bef4  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000bef9  lea     rcx, [rsp+0E8h+var_A0]
0x18000befe  call    ??1?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(void)
0x18000bf03  mov     rbx, cs:?g_ptrTraceMgr@@3V?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@A; std::unique_ptr<cxl::TraceManager> g_ptrTraceMgr
0x18000bf0a  lea     rdx, [rbx+108h]
0x18000bf11  lea     rcx, [rsp+0E8h+var_90]
0x18000bf16  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000bf1b  lea     rax, ?TraceLogRoutine@ClusWmi@@YAXHPEB_W_KPEAX@Z; ClusWmi::TraceLogRoutine(int,wchar_t const *,unsigned __int64,void *)
0x18000bf22  mov     [rbx+0D0h], rax
0x18000bf29  mov     [rbx+0D8h], r14
0x18000bf30  lea     rcx, [rsp+0E8h+var_90]
0x18000bf35  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000bf3a  mov     ecx, 18h; Size
0x18000bf3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf44  mov     rcx, rax
0x18000bf47  mov     [rax+8], r15d
0x18000bf4b  mov     [rax+0Ch], r15d
0x18000bf4f  lea     rax, ??_7?$_Ref_count_obj2@VMiSpace@Wsp@@@std@@6B@; const std::_Ref_count_obj2<Wsp::MiSpace>::`vftable'
0x18000bf56  mov     [rcx], rax
0x18000bf59  lea     rax, [rcx+10h]
0x18000bf5d  lea     rdx, ??_7MiSpace@Wsp@@6B@; const Wsp::MiSpace::`vftable'
0x18000bf64  mov     [rax], rdx
0x18000bf67  mov     [rsp+0E8h+var_90], rax
0x18000bf6c  mov     [rsp+0E8h+var_88], rcx
0x18000bf71  xorps   xmm0, xmm0
0x18000bf74  movdqu  [rsp+0E8h+var_70], xmm0
0x18000bf7a  lea     rdx, [rsp+0E8h+var_90]
0x18000bf7f  lea     rcx, [rsp+0E8h+var_A0]
0x18000bf84  call    ?Create@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@AEBV?$shared_ptr@UIMiSpace@Wsp@@@4@@Z; Wsp::MiSpaceAdapter::Create(std::shared_ptr<Wsp::IMiSpace> const &)
0x18000bf89  mov     rdx, rax
0x18000bf8c  lea     rcx, ?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000bf93  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x18000bf98  mov     rcx, [rsp+0E8h+var_98]; this
0x18000bf9d  test    rcx, rcx
0x18000bfa0  jz      short loc_18000BFA8
0x18000bfa2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bfa7  nop
0x18000bfa8  mov     rcx, [rsp+0E8h+var_88]; this
0x18000bfad  test    rcx, rcx
0x18000bfb0  jz      short loc_18000BFB8
0x18000bfb2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bfb7  nop
0x18000bfb8  cmp     cs:?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000bfbf  jnz     short loc_18000C020
0x18000bfc1  mov     esi, 1Bh
0x18000bfc6  mov     eax, cs:dword_18014D6A8
0x18000bfcc  cmp     eax, 2
0x18000bfcf  jbe     short loc_18000C00D
0x18000bfd1  mov     [rsp+0E8h+var_A8], esi
0x18000bfd5  mov     [rsp+0E8h+var_A4], 3Bh ; ';'
0x18000bfdd  mov     [rsp+0E8h+var_A0], rdi
0x18000bfe2  lea     rax, [rsp+0E8h+var_A8]
0x18000bfe7  mov     [rsp+0E8h+var_B8], rax
0x18000bfec  lea     rax, [rsp+0E8h+var_A4]
0x18000bff1  mov     [rsp+0E8h+var_C0], rax
0x18000bff6  lea     rax, [rsp+0E8h+var_A0]
0x18000bffb  mov     [rsp+0E8h+var_C8], rax
0x18000c000  lea     rdx, unk_18012AE18
0x18000c007  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c00c  nop
0x18000c00d  lea     rcx, [rsp+0E8h+var_60]
0x18000c015  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c01a  nop
0x18000c01b  jmp     loc_18000C160
0x18000c020  lea     rcx, [rsp+0E8h+var_90]
0x18000c025  call    ??$make_shared@VClusterApiFactory@ClusApi@@$$V@std@@YA?AV?$shared_ptr@VClusterApiFactory@ClusApi@@@0@XZ; std::make_shared<ClusApi::ClusterApiFactory,>(void)
0x18000c02a  mov     rdx, rax
0x18000c02d  mov     rcx, [rax]
0x18000c030  mov     rax, [rax+8]
0x18000c034  mov     [rdx], r14
0x18000c037  mov     [rdx+8], r14
0x18000c03b  mov     [rsp+0E8h+var_80], rcx
0x18000c040  mov     [rsp+0E8h+var_80+8], rax
0x18000c045  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c04a  test    rcx, rcx
0x18000c04d  jz      short loc_18000C054
0x18000c04f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c054  lea     rcx, [rsp+0E8h+var_A0]
0x18000c059  call    ?CreateInstance@LogWriter@smapi@@SA?AV?$shared_ptr@UILogProvider@ClusApi@@@std@@XZ; smapi::LogWriter::CreateInstance(void)
0x18000c05e  nop
0x18000c05f  mov     r8, rax
0x18000c062  lea     rdx, [rsp+0E8h+var_80]
0x18000c067  lea     rcx, [rsp+0E8h+var_90]
0x18000c06c  call    ?OpenStore@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@AEBV?$shared_ptr@UIClusterFactory@ClusApi@@@4@AEBV?$shared_ptr@UILogProvider@ClusApi@@@4@@Z; ClusWmi::DataStore::OpenStore(std::shared_ptr<ClusApi::IClusterFactory> const &,std::shared_ptr<ClusApi::ILogProvider> const &)
0x18000c071  mov     rdx, rax
0x18000c074  lea     rcx, ?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000c07b  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x18000c080  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c085  test    rcx, rcx
0x18000c088  jz      short loc_18000C090
0x18000c08a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c08f  nop
0x18000c090  mov     rcx, [rsp+0E8h+var_98]; this
0x18000c095  test    rcx, rcx
0x18000c098  jz      short loc_18000C09F
0x18000c09a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c09f  cmp     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, r14; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000c0a6  jnz     short loc_18000C113
0x18000c0a8  mov     esi, r15d
0x18000c0ab  mov     eax, cs:dword_18014D6A8
0x18000c0b1  cmp     eax, 2
0x18000c0b4  jbe     short loc_18000C0F3
0x18000c0b6  mov     [rsp+0E8h+var_A4], r15d
0x18000c0bb  mov     [rsp+0E8h+var_A8], 4Dh ; 'M'
0x18000c0c3  mov     [rsp+0E8h+var_A0], rdi
0x18000c0c8  lea     rax, [rsp+0E8h+var_A4]
0x18000c0cd  mov     [rsp+0E8h+var_B8], rax
0x18000c0d2  lea     rax, [rsp+0E8h+var_A8]
0x18000c0d7  mov     [rsp+0E8h+var_C0], rax
0x18000c0dc  lea     rax, [rsp+0E8h+var_A0]
0x18000c0e1  mov     [rsp+0E8h+var_C8], rax
0x18000c0e6  lea     rdx, byte_18012ADDF
0x18000c0ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c0f2  nop
0x18000c0f3  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c0f8  test    rcx, rcx
0x18000c0fb  jz      short loc_18000C103
0x18000c0fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c102  nop
0x18000c103  lea     rcx, [rsp+0E8h+var_60]
0x18000c10b  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c110  nop
0x18000c111  jmp     short loc_18000C160
0x18000c113  xor     edx, edx; hFile
0x18000c115  mov     r8d, 802h; dwFlags
0x18000c11b  lea     rcx, LibFileName; "StorageWMI.dll"
0x18000c122  call    cs:__imp_LoadLibraryExW
0x18000c129  nop     dword ptr [rax+rax+00h]
0x18000c12e  mov     cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_storageWMIResource
0x18000c135  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c13a  test    rcx, rcx
0x18000c13d  jz      short loc_18000C145
0x18000c13f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c144  nop
0x18000c145  lea     rcx, [rsp+0E8h+var_60]
0x18000c14d  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c152  nop
0x18000c153  jmp     short loc_18000C160
0x18000c155  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c15c  mov     esi, dword ptr [rsp+0E8h+var_A0]
0x18000c160  mov     ecx, cs:dword_18014D6A8
0x18000c166  cmp     ecx, 5
0x18000c169  jbe     short loc_18000C198
0x18000c16b  mov     dword ptr [rsp+0E8h+var_A0], 5Ch ; '\'
0x18000c173  mov     [rsp+0E8h+var_90], rdi
0x18000c178  lea     rax, [rsp+0E8h+var_A0]
0x18000c17d  mov     [rsp+0E8h+var_C0], rax
0x18000c182  lea     rax, [rsp+0E8h+var_90]
0x18000c187  mov     [rsp+0E8h+var_C8], rax
0x18000c18c  lea     rdx, byte_18012AD79
0x18000c193  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c198  mov     eax, esi
0x18000c19a  mov     rcx, [rsp+0E8h+var_38]
0x18000c1a2  xor     rcx, rsp; StackCookie
0x18000c1a5  call    __security_check_cookie
0x18000c1aa  add     rsp, 0C0h
0x18000c1b1  pop     r15
0x18000c1b3  pop     r14
0x18000c1b5  pop     rdi
0x18000c1b6  pop     rsi
0x18000c1b7  pop     rbx
0x18000c1b8  retn
```
