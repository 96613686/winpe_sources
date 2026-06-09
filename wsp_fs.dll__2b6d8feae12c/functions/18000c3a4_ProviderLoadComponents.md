# ProviderLoadComponents

- ea: `0x18000c3a4`
- end: `0x18000c898`
- name: `ProviderLoadComponents`
- size: `1268`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18000bb60`

## callees

- `0x180001010`
- `0x1800010bc`
- `0x180001100`
- `0x180002a70`
- `0x180002a94`
- `0x18000c074`
- `0x18000c0d8`
- `0x18000c130`
- `0x18000c14c`
- `0x18000c168`
- `0x18000c284`
- `0x18000c34c`
- `0x18000c378`
- `0x18000c3a4`
- `0x18000d100`
- `0x18000d398`
- `0x18000d5b0`
- `0x18000e1b8`
- `0x18001d25c`
- `0x180025378`
- `0x180047084`
- `0x180047854`
- `0x18006e5d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c3e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c3e8`

## string_xrefs

- `0x18000c481`: `ProviderLoadComponents`
- `0x18000c4af`: `ProviderLoadComponents`
- `0x18000c834`: `ProviderLoadComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProviderLoadComponents(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  char *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  std::_Ref_count_base *v19; // rcx
  std::_Ref_count_base *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  std::_Ref_count_base *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  const char *v30; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v31; // [rsp+50h] [rbp-98h]
  const char *v32; // [rsp+58h] [rbp-90h] BYREF
  std::_Ref_count_base *v33; // [rsp+60h] [rbp-88h]
  std::_Ref_count_base *v34[2]; // [rsp+68h] [rbp-80h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+78h] [rbp-70h] BYREF
  int v36; // [rsp+88h] [rbp-60h] BYREF
  char v37; // [rsp+8Ch] [rbp-5Ch]
  GUID v38; // [rsp+90h] [rbp-58h] BYREF

  v4 = 0;
  v36 = 0;
  v37 = 0;
  if ( (unsigned int)dword_180177348 <= 5 )
    v38 = 0;
  else
    EventActivityIdControl(3u, &v38);
  v36 = 1;
  if ( (unsigned int)dword_180177348 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180177348,
      (__int64)qword_180151CC0);
  if ( (unsigned int)dword_180177348 > 5 )
  {
    v30 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)word_180151C92,
      a3,
      a4,
      &v30);
  }
  try
  {
    *(_OWORD *)v35 = 0;
    v32 = (const char *)operator new(0x90u);
    v5 = cxl::ExceptionManager::ExceptionManager(v32);
    v30 = 0;
    std::unique_ptr<cxl::ExceptionManager>::reset(v6, v5);
    std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(&v30);
    v32 = (const char *)operator new(0x140u);
    v7 = cxl::TraceManager::TraceManager(v32);
    v30 = 0;
    std::unique_ptr<cxl::TraceManager>::reset(v8, v7);
    std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(&v30);
    v9 = g_ptrTraceMgr;
    cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(&v32);
    *(_QWORD *)(v9 + 208) = ClusWmi::TraceLogRoutine;
    *(_QWORD *)(v9 + 216) = 0;
    cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(&v32);
    v10 = (char *)operator new(0x18u);
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<Wsp::MiSpace>::`vftable';
    *((_QWORD *)v10 + 2) = &Wsp::MiSpace::`vftable';
    v32 = v10 + 16;
    v33 = (std::_Ref_count_base *)v10;
    *(_OWORD *)v34 = 0;
    v11 = Wsp::MiSpaceAdapter::Create(&v30, &v32);
    std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrMiSpaceAdapter, v11);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    if ( g_ptrMiSpaceAdapter )
    {
      v14 = std::make_shared<Wsp::Facade::FileShareFactory,>(v34);
      v32 = *(const char **)v14;
      v33 = *(std::_Ref_count_base **)(v14 + 8);
      *(_QWORD *)v14 = 0;
      *(_QWORD *)(v14 + 8) = 0;
      v15 = Wsp::Singleton::Create(&v30, &v32);
      std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrSingleton, v15);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      if ( v34[1] )
        std::_Ref_count_base::_Decref(v34[1]);
      if ( g_ptrSingleton )
      {
        v18 = std::make_shared<ClusApi::ClusterApiFactory,>(v34);
        v19 = *(std::_Ref_count_base **)v18;
        v20 = *(std::_Ref_count_base **)(v18 + 8);
        *(_QWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 0;
        v35[0] = v19;
        v35[1] = v20;
        if ( v34[1] )
          std::_Ref_count_base::_Decref(v34[1]);
        v21 = smapi::LogWriter::CreateInstance(&v32);
        v22 = ClusWmi::DataStore::OpenStore(v34, v35, v21);
        std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrDataStore, v22);
        if ( v34[1] )
          std::_Ref_count_base::_Decref(v34[1]);
        v25 = v33;
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        if ( g_ptrDataStore )
        {
          if ( v35[1] )
            std::_Ref_count_base::_Decref(v35[1]);
        }
        else
        {
          v4 = 1;
          if ( (unsigned int)dword_180177348 > 2 )
          {
            v30 = "ProviderLoadComponents";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (__int64)v25,
              (__int64)&byte_180151BE7,
              v23,
              v24,
              &v30);
          }
          if ( v35[1] )
            std::_Ref_count_base::_Decref(v35[1]);
        }
      }
      else
      {
        v4 = 27;
        if ( (unsigned int)dword_180177348 > 2 )
        {
          v30 = "ProviderLoadComponents";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            27,
            (__int64)&unk_180151C20,
            v16,
            v17,
            &v30);
        }
      }
    }
    else
    {
      v4 = 27;
      if ( (unsigned int)dword_180177348 > 2 )
      {
        v30 = "ProviderLoadComponents";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          27,
          (__int64)byte_180151C59,
          v12,
          v13,
          &v30);
      }
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v36);
  }
  catch ( ... )
  {
    LODWORD(v30) = 1;
    if ( (unsigned int)dword_180177348 > 2 )
    {
      v32 = "ProviderLoadComponents";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (__int64)&word_180151BAE,
        v27,
        v28,
        &v32);
    }
    v4 = (unsigned int)v30;
  }
  if ( (unsigned int)dword_180177348 > 5 )
  {
    LODWORD(v30) = 100;
    v32 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180177348,
      (__int64)byte_180151B81,
      v27,
      v28,
      &v32);
  }
  return v4;
}

```

## disassembly

```asm
0x18000c3a4  mov     r11, rsp
0x18000c3a7  push    rbx
0x18000c3a8  push    rsi
0x18000c3a9  push    rdi
0x18000c3aa  push    r14
0x18000c3ac  push    r15
0x18000c3ae  sub     rsp, 0C0h
0x18000c3b5  mov     rax, cs:__security_cookie
0x18000c3bc  xor     rax, rsp
0x18000c3bf  mov     [rsp+0E8h+var_38], rax
0x18000c3c7  xor     r14d, r14d
0x18000c3ca  mov     esi, r14d
0x18000c3cd  mov     [r11-60h], r14d
0x18000c3d1  mov     [r11-5Ch], r14b
0x18000c3d5  mov     eax, cs:dword_180177348
0x18000c3db  cmp     eax, 5
0x18000c3de  jbe     short loc_18000C3F0
0x18000c3e0  lea     rdx, [r11-58h]; ActivityId
0x18000c3e4  lea     ecx, [r14+3]; ControlCode
0x18000c3e8  call    cs:__imp_EventActivityIdControl
0x18000c3ee  jmp     short loc_18000C3FB
0x18000c3f0  xorps   xmm0, xmm0
0x18000c3f3  movups  [rsp+0E8h+var_58], xmm0
0x18000c3fb  mov     r15d, 1
0x18000c401  mov     [rsp+0E8h+var_60], r15d
0x18000c409  mov     eax, cs:dword_180177348
0x18000c40f  cmp     eax, 5
0x18000c412  jbe     short loc_18000C46E
0x18000c414  cmp     [rsp+0E8h+var_5C], r14b
0x18000c41c  jz      short loc_18000C450
0x18000c41e  cmp     [rsp+0E8h+var_48], r14d
0x18000c426  jnz     short loc_18000C446
0x18000c428  cmp     [rsp+0E8h+var_44], r14d
0x18000c430  jnz     short loc_18000C446
0x18000c432  cmp     [rsp+0E8h+var_40], r14d
0x18000c43a  jnz     short loc_18000C446
0x18000c43c  cmp     [rsp+0E8h+var_3C], r14d
0x18000c444  jz      short loc_18000C450
0x18000c446  lea     r9, [rsp+0E8h+var_48]
0x18000c44e  jmp     short loc_18000C453
0x18000c450  mov     r9, r14
0x18000c453  lea     r8, [rsp+0E8h+var_58]
0x18000c45b  lea     rdx, qword_180151CC0
0x18000c462  lea     rcx, dword_180177348
0x18000c469  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000c46e  mov     eax, cs:dword_180177348
0x18000c474  cmp     eax, 5
0x18000c477  jbe     short loc_18000C4AF
0x18000c479  mov     [rsp+0E8h+var_A8], 33h ; '3'
0x18000c481  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c488  mov     [rsp+0E8h+var_A0], rdi
0x18000c48d  lea     rax, [rsp+0E8h+var_A8]
0x18000c492  mov     [rsp+0E8h+var_C0], rax
0x18000c497  lea     rax, [rsp+0E8h+var_A0]
0x18000c49c  mov     [rsp+0E8h+var_C8], rax
0x18000c4a1  lea     rdx, word_180151C92
0x18000c4a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c4ad  jmp     short loc_18000C4B6
0x18000c4af  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c4b6  xorps   xmm0, xmm0
0x18000c4b9  movdqu  xmmword ptr [rsp+0E8h+var_70], xmm0
0x18000c4bf  mov     ecx, 90h; Size
0x18000c4c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4c9  mov     [rsp+0E8h+var_90], rax
0x18000c4ce  mov     rcx, rax
0x18000c4d1  call    ??0ExceptionManager@cxl@@QEAA@HW4Enum@CatchUnhandledExceptions@@@Z; cxl::ExceptionManager::ExceptionManager(int,CatchUnhandledExceptions::Enum)
0x18000c4d6  nop
0x18000c4d7  mov     [rsp+0E8h+var_A0], r14
0x18000c4dc  mov     rdx, rax
0x18000c4df  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000c4e4  lea     rcx, [rsp+0E8h+var_A0]
0x18000c4e9  call    ??1?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(void)
0x18000c4ee  mov     ecx, 140h; Size
0x18000c4f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4f8  mov     [rsp+0E8h+var_90], rax
0x18000c4fd  mov     rcx, rax
0x18000c500  call    ??0TraceManager@cxl@@QEAA@HP6AXHPEB_W_KPEAX@Z2W4Enum@DoRealTracing@@@Z; cxl::TraceManager::TraceManager(int,void (*)(int,wchar_t const *,unsigned __int64,void *),void *,DoRealTracing::Enum)
0x18000c505  nop
0x18000c506  mov     [rsp+0E8h+var_A0], r14
0x18000c50b  mov     rdx, rax
0x18000c50e  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000c513  lea     rcx, [rsp+0E8h+var_A0]
0x18000c518  call    ??1?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(void)
0x18000c51d  mov     rbx, cs:?g_ptrTraceMgr@@3V?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@A; std::unique_ptr<cxl::TraceManager> g_ptrTraceMgr
0x18000c524  lea     rdx, [rbx+108h]
0x18000c52b  lea     rcx, [rsp+0E8h+var_90]
0x18000c530  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000c535  lea     rax, ?TraceLogRoutine@ClusWmi@@YAXHPEB_W_KPEAX@Z; ClusWmi::TraceLogRoutine(int,wchar_t const *,unsigned __int64,void *)
0x18000c53c  mov     [rbx+0D0h], rax
0x18000c543  mov     [rbx+0D8h], r14
0x18000c54a  lea     rcx, [rsp+0E8h+var_90]
0x18000c54f  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000c554  mov     ecx, 18h; Size
0x18000c559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c55e  mov     rcx, rax
0x18000c561  mov     [rax+8], r15d
0x18000c565  mov     [rax+0Ch], r15d
0x18000c569  lea     rax, ??_7?$_Ref_count_obj2@VMiSpace@Wsp@@@std@@6B@; const std::_Ref_count_obj2<Wsp::MiSpace>::`vftable'
0x18000c570  mov     [rcx], rax
0x18000c573  lea     rax, [rcx+10h]
0x18000c577  lea     rdx, ??_7MiSpace@Wsp@@6B@; const Wsp::MiSpace::`vftable'
0x18000c57e  mov     [rax], rdx
0x18000c581  mov     [rsp+0E8h+var_90], rax
0x18000c586  mov     [rsp+0E8h+var_88], rcx
0x18000c58b  xorps   xmm0, xmm0
0x18000c58e  movdqu  xmmword ptr [rsp+0E8h+var_80], xmm0
0x18000c594  lea     rdx, [rsp+0E8h+var_90]
0x18000c599  lea     rcx, [rsp+0E8h+var_A0]
0x18000c59e  call    ?Create@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@AEBV?$shared_ptr@UIMiSpace@Wsp@@@4@@Z; Wsp::MiSpaceAdapter::Create(std::shared_ptr<Wsp::IMiSpace> const &)
0x18000c5a3  mov     rdx, rax
0x18000c5a6  lea     rcx, ?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000c5ad  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000c5b2  mov     rcx, [rsp+0E8h+var_98]; this
0x18000c5b7  test    rcx, rcx
0x18000c5ba  jz      short loc_18000C5C2
0x18000c5bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c5c1  nop
0x18000c5c2  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c5c7  test    rcx, rcx
0x18000c5ca  jz      short loc_18000C5D2
0x18000c5cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c5d1  nop
0x18000c5d2  cmp     cs:?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000c5d9  jnz     short loc_18000C63C
0x18000c5db  mov     ecx, 1Bh
0x18000c5e0  mov     esi, ecx
0x18000c5e2  mov     eax, cs:dword_180177348
0x18000c5e8  cmp     eax, 2
0x18000c5eb  jbe     short loc_18000C629
0x18000c5ed  mov     [rsp+0E8h+var_A8], ecx
0x18000c5f1  mov     [rsp+0E8h+var_A4], 3Fh ; '?'
0x18000c5f9  mov     [rsp+0E8h+var_A0], rdi
0x18000c5fe  lea     rax, [rsp+0E8h+var_A8]
0x18000c603  mov     [rsp+0E8h+var_B8], rax
0x18000c608  lea     rax, [rsp+0E8h+var_A4]
0x18000c60d  mov     [rsp+0E8h+var_C0], rax
0x18000c612  lea     rax, [rsp+0E8h+var_A0]
0x18000c617  mov     [rsp+0E8h+var_C8], rax
0x18000c61c  lea     rdx, byte_180151C59
0x18000c623  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c628  nop
0x18000c629  lea     rcx, [rsp+0E8h+var_60]
0x18000c631  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c636  nop
0x18000c637  jmp     loc_18000C83F
0x18000c63c  lea     rcx, [rsp+0E8h+var_80]
0x18000c641  call    ??$make_shared@VFileShareFactory@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VFileShareFactory@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::FileShareFactory,>(void)
0x18000c646  mov     rcx, rax
0x18000c649  mov     rax, [rax]
0x18000c64c  mov     [rsp+0E8h+var_90], rax
0x18000c651  mov     rax, [rcx+8]
0x18000c655  mov     [rsp+0E8h+var_88], rax
0x18000c65a  mov     [rcx], r14
0x18000c65d  mov     [rcx+8], r14
0x18000c661  lea     rdx, [rsp+0E8h+var_90]
0x18000c666  lea     rcx, [rsp+0E8h+var_A0]
0x18000c66b  call    ?Create@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@AEBV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@4@@Z; Wsp::Singleton::Create(std::shared_ptr<Wsp::Facade::IFileShareFactory> const &)
0x18000c670  mov     rdx, rax
0x18000c673  lea     rcx, ?g_ptrSingleton@@3V?$shared_ptr@VSingleton@Wsp@@@std@@A; std::shared_ptr<Wsp::Singleton> g_ptrSingleton
0x18000c67a  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000c67f  mov     rcx, [rsp+0E8h+var_98]; this
0x18000c684  test    rcx, rcx
0x18000c687  jz      short loc_18000C68F
0x18000c689  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c68e  nop
0x18000c68f  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c694  test    rcx, rcx
0x18000c697  jz      short loc_18000C69F
0x18000c699  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c69e  nop
0x18000c69f  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c6a4  test    rcx, rcx
0x18000c6a7  jz      short loc_18000C6AE
0x18000c6a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c6ae  cmp     cs:?g_ptrSingleton@@3V?$shared_ptr@VSingleton@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::Singleton> g_ptrSingleton
0x18000c6b5  jnz     short loc_18000C718
0x18000c6b7  mov     ecx, 1Bh
0x18000c6bc  mov     esi, ecx
0x18000c6be  mov     eax, cs:dword_180177348
0x18000c6c4  cmp     eax, 2
0x18000c6c7  jbe     short loc_18000C705
0x18000c6c9  mov     [rsp+0E8h+var_A4], ecx
0x18000c6cd  mov     [rsp+0E8h+var_A8], 47h ; 'G'
0x18000c6d5  mov     [rsp+0E8h+var_A0], rdi
0x18000c6da  lea     rax, [rsp+0E8h+var_A4]
0x18000c6df  mov     [rsp+0E8h+var_B8], rax
0x18000c6e4  lea     rax, [rsp+0E8h+var_A8]
0x18000c6e9  mov     [rsp+0E8h+var_C0], rax
0x18000c6ee  lea     rax, [rsp+0E8h+var_A0]
0x18000c6f3  mov     [rsp+0E8h+var_C8], rax
0x18000c6f8  lea     rdx, unk_180151C20
0x18000c6ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c704  nop
0x18000c705  lea     rcx, [rsp+0E8h+var_60]
0x18000c70d  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c712  nop
0x18000c713  jmp     loc_18000C83F
0x18000c718  lea     rcx, [rsp+0E8h+var_80]
0x18000c71d  call    ??$make_shared@VClusterApiFactory@ClusApi@@$$V@std@@YA?AV?$shared_ptr@VClusterApiFactory@ClusApi@@@0@XZ; std::make_shared<ClusApi::ClusterApiFactory,>(void)
0x18000c722  mov     rdx, rax
0x18000c725  mov     rcx, [rax]
0x18000c728  mov     rax, [rax+8]
0x18000c72c  mov     [rdx], r14
0x18000c72f  mov     [rdx+8], r14
0x18000c733  mov     [rsp+0E8h+var_70], rcx
0x18000c738  mov     [rsp+0E8h+var_70+8], rax
0x18000c740  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c745  test    rcx, rcx
0x18000c748  jz      short loc_18000C74F
0x18000c74a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c74f  lea     rcx, [rsp+0E8h+var_90]
0x18000c754  call    ?CreateInstance@LogWriter@smapi@@SA?AV?$shared_ptr@UILogProvider@ClusApi@@@std@@XZ; smapi::LogWriter::CreateInstance(void)
0x18000c759  nop
0x18000c75a  mov     r8, rax
0x18000c75d  lea     rdx, [rsp+0E8h+var_70]
0x18000c762  lea     rcx, [rsp+0E8h+var_80]
0x18000c767  call    ?OpenStore@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@AEBV?$shared_ptr@UIClusterFactory@ClusApi@@@4@AEBV?$shared_ptr@UILogProvider@ClusApi@@@4@@Z; ClusWmi::DataStore::OpenStore(std::shared_ptr<ClusApi::IClusterFactory> const &,std::shared_ptr<ClusApi::ILogProvider> const &)
0x18000c76c  mov     rdx, rax
0x18000c76f  lea     rcx, ?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000c776  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000c77b  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c780  test    rcx, rcx
0x18000c783  jz      short loc_18000C78B
0x18000c785  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c78a  nop
0x18000c78b  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c790  test    rcx, rcx
0x18000c793  jz      short loc_18000C79A
0x18000c795  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c79a  cmp     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, r14; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000c7a1  jnz     short loc_18000C811
0x18000c7a3  mov     esi, r15d
0x18000c7a6  mov     eax, cs:dword_180177348
0x18000c7ac  cmp     eax, 2
0x18000c7af  jbe     short loc_18000C7EE
0x18000c7b1  mov     [rsp+0E8h+var_A4], r15d
0x18000c7b6  mov     [rsp+0E8h+var_A8], 59h ; 'Y'
0x18000c7be  mov     [rsp+0E8h+var_A0], rdi
0x18000c7c3  lea     rax, [rsp+0E8h+var_A4]
0x18000c7c8  mov     [rsp+0E8h+var_B8], rax
0x18000c7cd  lea     rax, [rsp+0E8h+var_A8]
0x18000c7d2  mov     [rsp+0E8h+var_C0], rax
0x18000c7d7  lea     rax, [rsp+0E8h+var_A0]
0x18000c7dc  mov     [rsp+0E8h+var_C8], rax
0x18000c7e1  lea     rdx, byte_180151BE7
0x18000c7e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c7ed  nop
0x18000c7ee  mov     rcx, [rsp+0E8h+var_70+8]; this
0x18000c7f6  test    rcx, rcx
0x18000c7f9  jz      short loc_18000C801
0x18000c7fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c800  nop
0x18000c801  lea     rcx, [rsp+0E8h+var_60]
0x18000c809  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c80e  nop
0x18000c80f  jmp     short loc_18000C83F
0x18000c811  mov     rcx, [rsp+0E8h+var_70+8]; this
0x18000c819  test    rcx, rcx
0x18000c81c  jz      short loc_18000C824
0x18000c81e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c823  nop
0x18000c824  lea     rcx, [rsp+0E8h+var_60]
0x18000c82c  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c831  nop
0x18000c832  jmp     short loc_18000C83F
0x18000c834  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c83b  mov     esi, dword ptr [rsp+0E8h+var_A0]
0x18000c83f  mov     ecx, cs:dword_180177348
0x18000c845  cmp     ecx, 5
0x18000c848  jbe     short loc_18000C877
0x18000c84a  mov     dword ptr [rsp+0E8h+var_A0], 64h ; 'd'
0x18000c852  mov     [rsp+0E8h+var_90], rdi
0x18000c857  lea     rax, [rsp+0E8h+var_A0]
0x18000c85c  mov     [rsp+0E8h+var_C0], rax
0x18000c861  lea     rax, [rsp+0E8h+var_90]
0x18000c866  mov     [rsp+0E8h+var_C8], rax
0x18000c86b  lea     rdx, byte_180151B81
0x18000c872  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c877  mov     eax, esi
0x18000c879  mov     rcx, [rsp+0E8h+var_38]
0x18000c881  xor     rcx, rsp; StackCookie
0x18000c884  call    __security_check_cookie
0x18000c889  add     rsp, 0C0h
0x18000c890  pop     r15
0x18000c892  pop     r14
0x18000c894  pop     rdi
0x18000c895  pop     rsi
0x18000c896  pop     rbx
0x18000c897  retn
```
