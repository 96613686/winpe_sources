# ProviderLoadComponents

- ea: `0x18000c6e4`
- end: `0x18000cbdf`
- name: `ProviderLoadComponents`
- size: `1275`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18000bea0`

## callees

- `0x180001010`
- `0x1800010bc`
- `0x180001100`
- `0x180002ad0`
- `0x180002af4`
- `0x18000c3b0`
- `0x18000c414`
- `0x18000c46c`
- `0x18000c48c`
- `0x18000c4ac`
- `0x18000c5c4`
- `0x18000c68c`
- `0x18000c6b8`
- `0x18000c6e4`
- `0x18000d460`
- `0x18000d700`
- `0x18000d92c`
- `0x18000e59c`
- `0x18001ddc0`
- `0x18002606c`
- `0x180048224`
- `0x180048a14`
- `0x18006fe54`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c728`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c728`

## string_xrefs

- `0x18000c7c7`: `ProviderLoadComponents`
- `0x18000c7f5`: `ProviderLoadComponents`
- `0x18000cb7a`: `ProviderLoadComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  std::_Ref_count_base *v19; // rcx
  std::_Ref_count_base *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v30; // [rsp+40h] [rbp-A8h] BYREF
  int v31; // [rsp+44h] [rbp-A4h] BYREF
  const char *v32; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v33; // [rsp+50h] [rbp-98h]
  const char *v34; // [rsp+58h] [rbp-90h] BYREF
  std::_Ref_count_base *v35; // [rsp+60h] [rbp-88h]
  std::_Ref_count_base *v36[2]; // [rsp+68h] [rbp-80h] BYREF
  std::_Ref_count_base *v37[2]; // [rsp+78h] [rbp-70h] BYREF
  int v38; // [rsp+88h] [rbp-60h] BYREF
  char v39; // [rsp+8Ch] [rbp-5Ch]
  GUID v40; // [rsp+90h] [rbp-58h] BYREF

  v4 = 0;
  v38 = 0;
  v39 = 0;
  if ( (unsigned int)dword_180179348 <= 5 )
    v40 = 0;
  else
    EventActivityIdControl(3u, &v40);
  v38 = 1;
  if ( (unsigned int)dword_180179348 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180179348,
      qword_180153CC8,
      &v40,
      0);
  if ( (unsigned int)dword_180179348 > 5 )
  {
    v30 = 51;
    v32 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)word_180153C9A,
      a3,
      a4,
      (__int64)&v32,
      (__int64)&v30);
  }
  try
  {
    *(_OWORD *)v37 = 0;
    v34 = (const char *)operator new(0x90u);
    v5 = cxl::ExceptionManager::ExceptionManager(v34);
    v32 = 0;
    std::unique_ptr<cxl::ExceptionManager>::reset(v6, v5);
    std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(&v32);
    v34 = (const char *)operator new(0x140u);
    v7 = cxl::TraceManager::TraceManager(v34);
    v32 = 0;
    std::unique_ptr<cxl::TraceManager>::reset(v8, v7);
    std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(&v32);
    v9 = g_ptrTraceMgr;
    cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(&v34);
    *(_QWORD *)(v9 + 208) = ClusWmi::TraceLogRoutine;
    *(_QWORD *)(v9 + 216) = 0;
    cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(&v34);
    v10 = (char *)operator new(0x18u);
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<Wsp::MiSpace>::`vftable';
    *((_QWORD *)v10 + 2) = &Wsp::MiSpace::`vftable';
    v34 = v10 + 16;
    v35 = (std::_Ref_count_base *)v10;
    *(_OWORD *)v36 = 0;
    v11 = Wsp::MiSpaceAdapter::Create(&v32, &v34);
    std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrMiSpaceAdapter, v11);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    if ( v35 )
      std::_Ref_count_base::_Decref(v35);
    if ( g_ptrMiSpaceAdapter )
    {
      v14 = std::make_shared<Wsp::Facade::FileShareFactory,>(v36);
      v34 = *(const char **)v14;
      v35 = *(std::_Ref_count_base **)(v14 + 8);
      *(_QWORD *)v14 = 0;
      *(_QWORD *)(v14 + 8) = 0;
      v15 = Wsp::Singleton::Create(&v32, &v34);
      std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrSingleton, v15);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      if ( v35 )
        std::_Ref_count_base::_Decref(v35);
      if ( v36[1] )
        std::_Ref_count_base::_Decref(v36[1]);
      if ( g_ptrSingleton )
      {
        v18 = std::make_shared<ClusApi::ClusterApiFactory,>(v36);
        v19 = *(std::_Ref_count_base **)v18;
        v20 = *(std::_Ref_count_base **)(v18 + 8);
        *(_QWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 0;
        v37[0] = v19;
        v37[1] = v20;
        if ( v36[1] )
          std::_Ref_count_base::_Decref(v36[1]);
        v21 = smapi::LogWriter::CreateInstance(&v34);
        v22 = ClusWmi::DataStore::OpenStore(v36, v37, v21);
        std::shared_ptr<ClusWmi::DataStore>::operator=(&g_ptrDataStore, v22);
        if ( v36[1] )
          std::_Ref_count_base::_Decref(v36[1]);
        v25 = (int)v35;
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
        if ( g_ptrDataStore )
        {
          if ( v37[1] )
            std::_Ref_count_base::_Decref(v37[1]);
        }
        else
        {
          v4 = 1;
          if ( (unsigned int)dword_180179348 > 2 )
          {
            v31 = 1;
            v30 = 89;
            v32 = "ProviderLoadComponents";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v25,
              (unsigned int)&byte_180153BEF,
              v23,
              v24,
              (__int64)&v32,
              (__int64)&v30,
              (__int64)&v31);
          }
          if ( v37[1] )
            std::_Ref_count_base::_Decref(v37[1]);
        }
      }
      else
      {
        v4 = 27;
        if ( (unsigned int)dword_180179348 > 2 )
        {
          v31 = 27;
          v30 = 71;
          v32 = "ProviderLoadComponents";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            27,
            (unsigned int)&unk_180153C28,
            v16,
            v17,
            (__int64)&v32,
            (__int64)&v30,
            (__int64)&v31);
        }
      }
    }
    else
    {
      v4 = 27;
      if ( (unsigned int)dword_180179348 > 2 )
      {
        v30 = 27;
        v31 = 63;
        v32 = "ProviderLoadComponents";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          27,
          (unsigned int)byte_180153C61,
          v12,
          v13,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30);
      }
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v38);
  }
  catch ( ... )
  {
    LODWORD(v32) = 1;
    if ( (unsigned int)dword_180179348 > 2 )
    {
      v31 = 1;
      v30 = 96;
      v34 = "ProviderLoadComponents";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)&word_180153BB6,
        v27,
        v28,
        (__int64)&v34,
        (__int64)&v30,
        (__int64)&v31);
    }
    v4 = (unsigned int)v32;
  }
  if ( (unsigned int)dword_180179348 > 5 )
  {
    LODWORD(v32) = 100;
    v34 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_180179348,
      (unsigned int)byte_180153B89,
      v27,
      v28,
      (__int64)&v34,
      (__int64)&v32);
  }
  return v4;
}

```

## disassembly

```asm
0x18000c6e4  mov     r11, rsp
0x18000c6e7  push    rbx
0x18000c6e8  push    rsi
0x18000c6e9  push    rdi
0x18000c6ea  push    r14
0x18000c6ec  push    r15
0x18000c6ee  sub     rsp, 0C0h
0x18000c6f5  mov     rax, cs:__security_cookie
0x18000c6fc  xor     rax, rsp
0x18000c6ff  mov     [rsp+0E8h+var_38], rax
0x18000c707  xor     r14d, r14d
0x18000c70a  mov     esi, r14d
0x18000c70d  mov     [r11-60h], r14d
0x18000c711  mov     [r11-5Ch], r14b
0x18000c715  mov     eax, cs:dword_180179348
0x18000c71b  cmp     eax, 5
0x18000c71e  jbe     short loc_18000C736
0x18000c720  lea     rdx, [r11-58h]; ActivityId
0x18000c724  lea     ecx, [r14+3]; ControlCode
0x18000c728  call    cs:__imp_EventActivityIdControl
0x18000c72f  nop     dword ptr [rax+rax+00h]
0x18000c734  jmp     short loc_18000C741
0x18000c736  xorps   xmm0, xmm0
0x18000c739  movups  [rsp+0E8h+var_58], xmm0
0x18000c741  mov     r15d, 1
0x18000c747  mov     [rsp+0E8h+var_60], r15d
0x18000c74f  mov     eax, cs:dword_180179348
0x18000c755  cmp     eax, 5
0x18000c758  jbe     short loc_18000C7B4
0x18000c75a  cmp     [rsp+0E8h+var_5C], r14b
0x18000c762  jz      short loc_18000C796
0x18000c764  cmp     [rsp+0E8h+var_48], r14d
0x18000c76c  jnz     short loc_18000C78C
0x18000c76e  cmp     [rsp+0E8h+var_44], r14d
0x18000c776  jnz     short loc_18000C78C
0x18000c778  cmp     [rsp+0E8h+var_40], r14d
0x18000c780  jnz     short loc_18000C78C
0x18000c782  cmp     [rsp+0E8h+var_3C], r14d
0x18000c78a  jz      short loc_18000C796
0x18000c78c  lea     r9, [rsp+0E8h+var_48]
0x18000c794  jmp     short loc_18000C799
0x18000c796  mov     r9, r14
0x18000c799  lea     r8, [rsp+0E8h+var_58]
0x18000c7a1  lea     rdx, qword_180153CC8
0x18000c7a8  lea     rcx, dword_180179348
0x18000c7af  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000c7b4  mov     eax, cs:dword_180179348
0x18000c7ba  cmp     eax, 5
0x18000c7bd  jbe     short loc_18000C7F5
0x18000c7bf  mov     [rsp+0E8h+var_A8], 33h ; '3'
0x18000c7c7  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c7ce  mov     [rsp+0E8h+var_A0], rdi
0x18000c7d3  lea     rax, [rsp+0E8h+var_A8]
0x18000c7d8  mov     [rsp+0E8h+var_C0], rax
0x18000c7dd  lea     rax, [rsp+0E8h+var_A0]
0x18000c7e2  mov     [rsp+0E8h+var_C8], rax
0x18000c7e7  lea     rdx, word_180153C9A
0x18000c7ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c7f3  jmp     short loc_18000C7FC
0x18000c7f5  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000c7fc  xorps   xmm0, xmm0
0x18000c7ff  movdqu  xmmword ptr [rsp+0E8h+var_70], xmm0
0x18000c805  mov     ecx, 90h; Size
0x18000c80a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c80f  mov     [rsp+0E8h+var_90], rax
0x18000c814  mov     rcx, rax
0x18000c817  call    ??0ExceptionManager@cxl@@QEAA@HW4Enum@CatchUnhandledExceptions@@@Z; cxl::ExceptionManager::ExceptionManager(int,CatchUnhandledExceptions::Enum)
0x18000c81c  nop
0x18000c81d  mov     [rsp+0E8h+var_A0], r14
0x18000c822  mov     rdx, rax
0x18000c825  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000c82a  lea     rcx, [rsp+0E8h+var_A0]
0x18000c82f  call    ??1?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(void)
0x18000c834  mov     ecx, 140h; Size
0x18000c839  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c83e  mov     [rsp+0E8h+var_90], rax
0x18000c843  mov     rcx, rax
0x18000c846  call    ??0TraceManager@cxl@@QEAA@HP6AXHPEB_W_KPEAX@Z2W4Enum@DoRealTracing@@@Z; cxl::TraceManager::TraceManager(int,void (*)(int,wchar_t const *,unsigned __int64,void *),void *,DoRealTracing::Enum)
0x18000c84b  nop
0x18000c84c  mov     [rsp+0E8h+var_A0], r14
0x18000c851  mov     rdx, rax
0x18000c854  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000c859  lea     rcx, [rsp+0E8h+var_A0]
0x18000c85e  call    ??1?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(void)
0x18000c863  mov     rbx, cs:?g_ptrTraceMgr@@3V?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@A; std::unique_ptr<cxl::TraceManager> g_ptrTraceMgr
0x18000c86a  lea     rdx, [rbx+108h]
0x18000c871  lea     rcx, [rsp+0E8h+var_90]
0x18000c876  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000c87b  lea     rax, ?TraceLogRoutine@ClusWmi@@YAXHPEB_W_KPEAX@Z; ClusWmi::TraceLogRoutine(int,wchar_t const *,unsigned __int64,void *)
0x18000c882  mov     [rbx+0D0h], rax
0x18000c889  mov     [rbx+0D8h], r14
0x18000c890  lea     rcx, [rsp+0E8h+var_90]
0x18000c895  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000c89a  mov     ecx, 18h; Size
0x18000c89f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c8a4  mov     rcx, rax
0x18000c8a7  mov     [rax+8], r15d
0x18000c8ab  mov     [rax+0Ch], r15d
0x18000c8af  lea     rax, ??_7?$_Ref_count_obj2@VMiSpace@Wsp@@@std@@6B@; const std::_Ref_count_obj2<Wsp::MiSpace>::`vftable'
0x18000c8b6  mov     [rcx], rax
0x18000c8b9  lea     rax, [rcx+10h]
0x18000c8bd  lea     rdx, ??_7MiSpace@Wsp@@6B@; const Wsp::MiSpace::`vftable'
0x18000c8c4  mov     [rax], rdx
0x18000c8c7  mov     [rsp+0E8h+var_90], rax
0x18000c8cc  mov     [rsp+0E8h+var_88], rcx
0x18000c8d1  xorps   xmm0, xmm0
0x18000c8d4  movdqu  xmmword ptr [rsp+0E8h+var_80], xmm0
0x18000c8da  lea     rdx, [rsp+0E8h+var_90]
0x18000c8df  lea     rcx, [rsp+0E8h+var_A0]
0x18000c8e4  call    ?Create@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@AEBV?$shared_ptr@UIMiSpace@Wsp@@@4@@Z; Wsp::MiSpaceAdapter::Create(std::shared_ptr<Wsp::IMiSpace> const &)
0x18000c8e9  mov     rdx, rax
0x18000c8ec  lea     rcx, ?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000c8f3  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000c8f8  mov     rcx, [rsp+0E8h+var_98]; this
0x18000c8fd  test    rcx, rcx
0x18000c900  jz      short loc_18000C908
0x18000c902  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c907  nop
0x18000c908  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c90d  test    rcx, rcx
0x18000c910  jz      short loc_18000C918
0x18000c912  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c917  nop
0x18000c918  cmp     cs:?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000c91f  jnz     short loc_18000C982
0x18000c921  mov     ecx, 1Bh
0x18000c926  mov     esi, ecx
0x18000c928  mov     eax, cs:dword_180179348
0x18000c92e  cmp     eax, 2
0x18000c931  jbe     short loc_18000C96F
0x18000c933  mov     [rsp+0E8h+var_A8], ecx
0x18000c937  mov     [rsp+0E8h+var_A4], 3Fh ; '?'
0x18000c93f  mov     [rsp+0E8h+var_A0], rdi
0x18000c944  lea     rax, [rsp+0E8h+var_A8]
0x18000c949  mov     [rsp+0E8h+var_B8], rax
0x18000c94e  lea     rax, [rsp+0E8h+var_A4]
0x18000c953  mov     [rsp+0E8h+var_C0], rax
0x18000c958  lea     rax, [rsp+0E8h+var_A0]
0x18000c95d  mov     [rsp+0E8h+var_C8], rax
0x18000c962  lea     rdx, byte_180153C61
0x18000c969  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c96e  nop
0x18000c96f  lea     rcx, [rsp+0E8h+var_60]
0x18000c977  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000c97c  nop
0x18000c97d  jmp     loc_18000CB85
0x18000c982  lea     rcx, [rsp+0E8h+var_80]
0x18000c987  call    ??$make_shared@VFileShareFactory@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VFileShareFactory@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::FileShareFactory,>(void)
0x18000c98c  mov     rcx, rax
0x18000c98f  mov     rax, [rax]
0x18000c992  mov     [rsp+0E8h+var_90], rax
0x18000c997  mov     rax, [rcx+8]
0x18000c99b  mov     [rsp+0E8h+var_88], rax
0x18000c9a0  mov     [rcx], r14
0x18000c9a3  mov     [rcx+8], r14
0x18000c9a7  lea     rdx, [rsp+0E8h+var_90]
0x18000c9ac  lea     rcx, [rsp+0E8h+var_A0]
0x18000c9b1  call    ?Create@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@AEBV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@4@@Z; Wsp::Singleton::Create(std::shared_ptr<Wsp::Facade::IFileShareFactory> const &)
0x18000c9b6  mov     rdx, rax
0x18000c9b9  lea     rcx, ?g_ptrSingleton@@3V?$shared_ptr@VSingleton@Wsp@@@std@@A; std::shared_ptr<Wsp::Singleton> g_ptrSingleton
0x18000c9c0  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000c9c5  mov     rcx, [rsp+0E8h+var_98]; this
0x18000c9ca  test    rcx, rcx
0x18000c9cd  jz      short loc_18000C9D5
0x18000c9cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c9d4  nop
0x18000c9d5  mov     rcx, [rsp+0E8h+var_88]; this
0x18000c9da  test    rcx, rcx
0x18000c9dd  jz      short loc_18000C9E5
0x18000c9df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c9e4  nop
0x18000c9e5  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000c9ea  test    rcx, rcx
0x18000c9ed  jz      short loc_18000C9F4
0x18000c9ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c9f4  cmp     cs:?g_ptrSingleton@@3V?$shared_ptr@VSingleton@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::Singleton> g_ptrSingleton
0x18000c9fb  jnz     short loc_18000CA5E
0x18000c9fd  mov     ecx, 1Bh
0x18000ca02  mov     esi, ecx
0x18000ca04  mov     eax, cs:dword_180179348
0x18000ca0a  cmp     eax, 2
0x18000ca0d  jbe     short loc_18000CA4B
0x18000ca0f  mov     [rsp+0E8h+var_A4], ecx
0x18000ca13  mov     [rsp+0E8h+var_A8], 47h ; 'G'
0x18000ca1b  mov     [rsp+0E8h+var_A0], rdi
0x18000ca20  lea     rax, [rsp+0E8h+var_A4]
0x18000ca25  mov     [rsp+0E8h+var_B8], rax
0x18000ca2a  lea     rax, [rsp+0E8h+var_A8]
0x18000ca2f  mov     [rsp+0E8h+var_C0], rax
0x18000ca34  lea     rax, [rsp+0E8h+var_A0]
0x18000ca39  mov     [rsp+0E8h+var_C8], rax
0x18000ca3e  lea     rdx, unk_180153C28
0x18000ca45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ca4a  nop
0x18000ca4b  lea     rcx, [rsp+0E8h+var_60]
0x18000ca53  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000ca58  nop
0x18000ca59  jmp     loc_18000CB85
0x18000ca5e  lea     rcx, [rsp+0E8h+var_80]
0x18000ca63  call    ??$make_shared@VClusterApiFactory@ClusApi@@$$V@std@@YA?AV?$shared_ptr@VClusterApiFactory@ClusApi@@@0@XZ; std::make_shared<ClusApi::ClusterApiFactory,>(void)
0x18000ca68  mov     rdx, rax
0x18000ca6b  mov     rcx, [rax]
0x18000ca6e  mov     rax, [rax+8]
0x18000ca72  mov     [rdx], r14
0x18000ca75  mov     [rdx+8], r14
0x18000ca79  mov     [rsp+0E8h+var_70], rcx
0x18000ca7e  mov     [rsp+0E8h+var_70+8], rax
0x18000ca86  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000ca8b  test    rcx, rcx
0x18000ca8e  jz      short loc_18000CA95
0x18000ca90  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ca95  lea     rcx, [rsp+0E8h+var_90]
0x18000ca9a  call    ?CreateInstance@LogWriter@smapi@@SA?AV?$shared_ptr@UILogProvider@ClusApi@@@std@@XZ; smapi::LogWriter::CreateInstance(void)
0x18000ca9f  nop
0x18000caa0  mov     r8, rax
0x18000caa3  lea     rdx, [rsp+0E8h+var_70]
0x18000caa8  lea     rcx, [rsp+0E8h+var_80]
0x18000caad  call    ?OpenStore@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@AEBV?$shared_ptr@UIClusterFactory@ClusApi@@@4@AEBV?$shared_ptr@UILogProvider@ClusApi@@@4@@Z; ClusWmi::DataStore::OpenStore(std::shared_ptr<ClusApi::IClusterFactory> const &,std::shared_ptr<ClusApi::ILogProvider> const &)
0x18000cab2  mov     rdx, rax
0x18000cab5  lea     rcx, ?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000cabc  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18000cac1  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000cac6  test    rcx, rcx
0x18000cac9  jz      short loc_18000CAD1
0x18000cacb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cad0  nop
0x18000cad1  mov     rcx, [rsp+0E8h+var_88]; this
0x18000cad6  test    rcx, rcx
0x18000cad9  jz      short loc_18000CAE0
0x18000cadb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cae0  cmp     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, r14; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000cae7  jnz     short loc_18000CB57
0x18000cae9  mov     esi, r15d
0x18000caec  mov     eax, cs:dword_180179348
0x18000caf2  cmp     eax, 2
0x18000caf5  jbe     short loc_18000CB34
0x18000caf7  mov     [rsp+0E8h+var_A4], r15d
0x18000cafc  mov     [rsp+0E8h+var_A8], 59h ; 'Y'
0x18000cb04  mov     [rsp+0E8h+var_A0], rdi
0x18000cb09  lea     rax, [rsp+0E8h+var_A4]
0x18000cb0e  mov     [rsp+0E8h+var_B8], rax
0x18000cb13  lea     rax, [rsp+0E8h+var_A8]
0x18000cb18  mov     [rsp+0E8h+var_C0], rax
0x18000cb1d  lea     rax, [rsp+0E8h+var_A0]
0x18000cb22  mov     [rsp+0E8h+var_C8], rax
0x18000cb27  lea     rdx, byte_180153BEF
0x18000cb2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cb33  nop
0x18000cb34  mov     rcx, [rsp+0E8h+var_70+8]; this
0x18000cb3c  test    rcx, rcx
0x18000cb3f  jz      short loc_18000CB47
0x18000cb41  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cb46  nop
0x18000cb47  lea     rcx, [rsp+0E8h+var_60]
0x18000cb4f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000cb54  nop
0x18000cb55  jmp     short loc_18000CB85
0x18000cb57  mov     rcx, [rsp+0E8h+var_70+8]; this
0x18000cb5f  test    rcx, rcx
0x18000cb62  jz      short loc_18000CB6A
0x18000cb64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cb69  nop
0x18000cb6a  lea     rcx, [rsp+0E8h+var_60]
0x18000cb72  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000cb77  nop
0x18000cb78  jmp     short loc_18000CB85
0x18000cb7a  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000cb81  mov     esi, dword ptr [rsp+0E8h+var_A0]
0x18000cb85  mov     ecx, cs:dword_180179348
0x18000cb8b  cmp     ecx, 5
0x18000cb8e  jbe     short loc_18000CBBD
0x18000cb90  mov     dword ptr [rsp+0E8h+var_A0], 64h ; 'd'
0x18000cb98  mov     [rsp+0E8h+var_90], rdi
0x18000cb9d  lea     rax, [rsp+0E8h+var_A0]
0x18000cba2  mov     [rsp+0E8h+var_C0], rax
0x18000cba7  lea     rax, [rsp+0E8h+var_90]
0x18000cbac  mov     [rsp+0E8h+var_C8], rax
0x18000cbb1  lea     rdx, byte_180153B89
0x18000cbb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000cbbd  mov     eax, esi
0x18000cbbf  mov     rcx, [rsp+0E8h+var_38]
0x18000cbc7  xor     rcx, rsp; StackCookie
0x18000cbca  call    __security_check_cookie
0x18000cbcf  add     rsp, 0C0h
0x18000cbd6  pop     r15
0x18000cbd8  pop     r14
0x18000cbda  pop     rdi
0x18000cbdb  pop     rsi
0x18000cbdc  pop     rbx
0x18000cbdd  retn
```
