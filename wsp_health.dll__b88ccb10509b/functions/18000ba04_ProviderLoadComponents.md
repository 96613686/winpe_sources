# ProviderLoadComponents

- ea: `0x18000ba04`
- end: `0x18000be2d`
- name: `ProviderLoadComponents`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b250`

## callees

- `0x180001010`
- `0x1800010f4`
- `0x18000119c`
- `0x180002ae0`
- `0x180002f00`
- `0x18000b770`
- `0x18000b7c8`
- `0x18000b7e4`
- `0x18000b800`
- `0x18000b8e4`
- `0x18000b9ac`
- `0x18000b9d8`
- `0x18000ba04`
- `0x18000c858`
- `0x18000cb34`
- `0x18000cdc4`
- `0x18000db08`
- `0x18001a17c`
- `0x180021640`
- `0x180033ea0`
- `0x18003ae34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd9c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ba48`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ba48`

## string_xrefs

- `0x18000bae1`: `ProviderLoadComponents`
- `0x18000bb0f`: `ProviderLoadComponents`
- `0x18000bdc9`: `ProviderLoadComponents`
- `0x18000bd95`: `StorageWMI.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  std::_Ref_count_base *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  const char *v27; // [rsp+48h] [rbp-A0h] BYREF
  std::_Ref_count_base *v28; // [rsp+50h] [rbp-98h]
  const char *v29; // [rsp+58h] [rbp-90h] BYREF
  std::_Ref_count_base *v30; // [rsp+60h] [rbp-88h]
  std::_Ref_count_base *v31[2]; // [rsp+68h] [rbp-80h] BYREF
  __int128 v32; // [rsp+78h] [rbp-70h]
  int v33; // [rsp+88h] [rbp-60h] BYREF
  char v34; // [rsp+8Ch] [rbp-5Ch]
  GUID v35; // [rsp+90h] [rbp-58h] BYREF

  v4 = 0;
  v33 = 0;
  v34 = 0;
  if ( (unsigned int)dword_18014B6A8 <= 5 )
    v35 = 0;
  else
    EventActivityIdControl(3u, &v35);
  v33 = 1;
  if ( (unsigned int)dword_18014B6A8 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18014B6A8,
      (__int64)&byte_180128E77);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v27 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_180128E49,
      a3,
      a4,
      &v27);
  }
  try
  {
    *(_OWORD *)v31 = 0;
    v29 = (const char *)operator new(0x90u);
    v5 = cxl::ExceptionManager::ExceptionManager(v29);
    v27 = 0;
    std::unique_ptr<cxl::ExceptionManager>::reset(v6, v5);
    std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(&v27);
    v29 = (const char *)operator new(0x140u);
    v7 = cxl::TraceManager::TraceManager(v29);
    v27 = 0;
    std::unique_ptr<cxl::TraceManager>::reset(v8, v7);
    std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(&v27);
    v9 = g_ptrTraceMgr;
    cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(&v29, g_ptrTraceMgr + 264);
    *(_QWORD *)(v9 + 208) = ClusWmi::TraceLogRoutine;
    *(_QWORD *)(v9 + 216) = 0;
    cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(&v29);
    v10 = (char *)operator new(0x18u);
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<Wsp::MiSpace>::`vftable';
    *((_QWORD *)v10 + 2) = &Wsp::MiSpace::`vftable';
    v29 = v10 + 16;
    v30 = (std::_Ref_count_base *)v10;
    v32 = 0;
    v11 = Wsp::MiSpaceAdapter::Create(&v27, &v29);
    std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(&g_ptrMiSpaceAdapter, v11);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v14 = v30;
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    if ( g_ptrMiSpaceAdapter )
    {
      v15 = std::make_shared<ClusApi::ClusterApiFactory,>(&v29);
      v16 = *(std::_Ref_count_base **)v15;
      v17 = *(std::_Ref_count_base **)(v15 + 8);
      *(_QWORD *)v15 = 0;
      *(_QWORD *)(v15 + 8) = 0;
      v31[0] = v16;
      v31[1] = v17;
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      v18 = smapi::LogWriter::CreateInstance(&v27);
      v19 = ClusWmi::DataStore::OpenStore(&v29, v31, v18);
      std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(&g_ptrDataStore, v19);
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      v22 = v28;
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
      if ( g_ptrDataStore )
      {
        g_storageWMIResource = LoadLibraryExW(L"StorageWMI.dll", 0, 0x802u);
        if ( v31[1] )
          std::_Ref_count_base::_Decref(v31[1]);
      }
      else
      {
        v4 = 1;
        if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v27 = "ProviderLoadComponents";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)v22,
            (__int64)&byte_180128DD7,
            v20,
            v21,
            &v27);
        }
        if ( v31[1] )
          std::_Ref_count_base::_Decref(v31[1]);
      }
    }
    else
    {
      v4 = 27;
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v27 = "ProviderLoadComponents";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (__int64)v14,
          (__int64)&unk_180128E10,
          v12,
          v13,
          &v27);
      }
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v33);
  }
  catch ( ... )
  {
    LODWORD(v27) = 1;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v29 = "ProviderLoadComponents";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (__int64)&word_180128D9E,
        v24,
        v25,
        &v29);
    }
    v4 = (unsigned int)v27;
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v27) = 92;
    v29 = "ProviderLoadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_18014B6A8,
      (__int64)byte_180128D71,
      v24,
      v25,
      &v29);
  }
  return v4;
}

```

## disassembly

```asm
0x18000ba04  mov     r11, rsp
0x18000ba07  push    rbx
0x18000ba08  push    rsi
0x18000ba09  push    rdi
0x18000ba0a  push    r14
0x18000ba0c  push    r15
0x18000ba0e  sub     rsp, 0C0h
0x18000ba15  mov     rax, cs:__security_cookie
0x18000ba1c  xor     rax, rsp
0x18000ba1f  mov     [rsp+0E8h+var_38], rax
0x18000ba27  xor     r14d, r14d
0x18000ba2a  mov     esi, r14d
0x18000ba2d  mov     [r11-60h], r14d
0x18000ba31  mov     [r11-5Ch], r14b
0x18000ba35  mov     eax, cs:dword_18014B6A8
0x18000ba3b  cmp     eax, 5
0x18000ba3e  jbe     short loc_18000BA50
0x18000ba40  lea     rdx, [r11-58h]; ActivityId
0x18000ba44  lea     ecx, [r14+3]; ControlCode
0x18000ba48  call    cs:__imp_EventActivityIdControl
0x18000ba4e  jmp     short loc_18000BA5B
0x18000ba50  xorps   xmm0, xmm0
0x18000ba53  movups  [rsp+0E8h+var_58], xmm0
0x18000ba5b  mov     r15d, 1
0x18000ba61  mov     [rsp+0E8h+var_60], r15d
0x18000ba69  mov     eax, cs:dword_18014B6A8
0x18000ba6f  cmp     eax, 5
0x18000ba72  jbe     short loc_18000BACE
0x18000ba74  cmp     [rsp+0E8h+var_5C], r14b
0x18000ba7c  jz      short loc_18000BAB0
0x18000ba7e  cmp     [rsp+0E8h+var_48], r14d
0x18000ba86  jnz     short loc_18000BAA6
0x18000ba88  cmp     [rsp+0E8h+var_44], r14d
0x18000ba90  jnz     short loc_18000BAA6
0x18000ba92  cmp     [rsp+0E8h+var_40], r14d
0x18000ba9a  jnz     short loc_18000BAA6
0x18000ba9c  cmp     [rsp+0E8h+var_3C], r14d
0x18000baa4  jz      short loc_18000BAB0
0x18000baa6  lea     r9, [rsp+0E8h+var_48]
0x18000baae  jmp     short loc_18000BAB3
0x18000bab0  mov     r9, r14
0x18000bab3  lea     r8, [rsp+0E8h+var_58]
0x18000babb  lea     rdx, byte_180128E77
0x18000bac2  lea     rcx, dword_18014B6A8
0x18000bac9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000bace  mov     eax, cs:dword_18014B6A8
0x18000bad4  cmp     eax, 5
0x18000bad7  jbe     short loc_18000BB0F
0x18000bad9  mov     [rsp+0E8h+var_A8], 2Fh ; '/'
0x18000bae1  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000bae8  mov     [rsp+0E8h+var_A0], rdi
0x18000baed  lea     rax, [rsp+0E8h+var_A8]
0x18000baf2  mov     [rsp+0E8h+var_C0], rax
0x18000baf7  lea     rax, [rsp+0E8h+var_A0]
0x18000bafc  mov     [rsp+0E8h+var_C8], rax
0x18000bb01  lea     rdx, byte_180128E49
0x18000bb08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000bb0d  jmp     short loc_18000BB16
0x18000bb0f  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000bb16  xorps   xmm0, xmm0
0x18000bb19  movdqu  xmmword ptr [rsp+0E8h+var_80], xmm0
0x18000bb1f  mov     ecx, 90h; Size
0x18000bb24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb29  mov     [rsp+0E8h+var_90], rax
0x18000bb2e  mov     rcx, rax
0x18000bb31  call    ??0ExceptionManager@cxl@@QEAA@HW4Enum@CatchUnhandledExceptions@@@Z; cxl::ExceptionManager::ExceptionManager(int,CatchUnhandledExceptions::Enum)
0x18000bb36  nop
0x18000bb37  mov     [rsp+0E8h+var_A0], r14
0x18000bb3c  mov     rdx, rax
0x18000bb3f  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000bb44  lea     rcx, [rsp+0E8h+var_A0]
0x18000bb49  call    ??1?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::ExceptionManager>::~unique_ptr<cxl::ExceptionManager>(void)
0x18000bb4e  mov     ecx, 140h; Size
0x18000bb53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb58  mov     [rsp+0E8h+var_90], rax
0x18000bb5d  mov     rcx, rax
0x18000bb60  call    ??0TraceManager@cxl@@QEAA@HP6AXHPEB_W_KPEAX@Z2W4Enum@DoRealTracing@@@Z; cxl::TraceManager::TraceManager(int,void (*)(int,wchar_t const *,unsigned __int64,void *),void *,DoRealTracing::Enum)
0x18000bb65  nop
0x18000bb66  mov     [rsp+0E8h+var_A0], r14
0x18000bb6b  mov     rdx, rax
0x18000bb6e  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000bb73  lea     rcx, [rsp+0E8h+var_A0]
0x18000bb78  call    ??1?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAA@XZ; std::unique_ptr<cxl::TraceManager>::~unique_ptr<cxl::TraceManager>(void)
0x18000bb7d  mov     rbx, cs:?g_ptrTraceMgr@@3V?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@A; std::unique_ptr<cxl::TraceManager> g_ptrTraceMgr
0x18000bb84  lea     rdx, [rbx+108h]
0x18000bb8b  lea     rcx, [rsp+0E8h+var_90]
0x18000bb90  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000bb95  lea     rax, ?TraceLogRoutine@ClusWmi@@YAXHPEB_W_KPEAX@Z; ClusWmi::TraceLogRoutine(int,wchar_t const *,unsigned __int64,void *)
0x18000bb9c  mov     [rbx+0D0h], rax
0x18000bba3  mov     [rbx+0D8h], r14
0x18000bbaa  lea     rcx, [rsp+0E8h+var_90]
0x18000bbaf  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000bbb4  mov     ecx, 18h; Size
0x18000bbb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bbbe  mov     rcx, rax
0x18000bbc1  mov     [rax+8], r15d
0x18000bbc5  mov     [rax+0Ch], r15d
0x18000bbc9  lea     rax, ??_7?$_Ref_count_obj2@VMiSpace@Wsp@@@std@@6B@; const std::_Ref_count_obj2<Wsp::MiSpace>::`vftable'
0x18000bbd0  mov     [rcx], rax
0x18000bbd3  lea     rax, [rcx+10h]
0x18000bbd7  lea     rdx, ??_7MiSpace@Wsp@@6B@; const Wsp::MiSpace::`vftable'
0x18000bbde  mov     [rax], rdx
0x18000bbe1  mov     [rsp+0E8h+var_90], rax
0x18000bbe6  mov     [rsp+0E8h+var_88], rcx
0x18000bbeb  xorps   xmm0, xmm0
0x18000bbee  movdqu  [rsp+0E8h+var_70], xmm0
0x18000bbf4  lea     rdx, [rsp+0E8h+var_90]
0x18000bbf9  lea     rcx, [rsp+0E8h+var_A0]
0x18000bbfe  call    ?Create@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@AEBV?$shared_ptr@UIMiSpace@Wsp@@@4@@Z; Wsp::MiSpaceAdapter::Create(std::shared_ptr<Wsp::IMiSpace> const &)
0x18000bc03  mov     rdx, rax
0x18000bc06  lea     rcx, ?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000bc0d  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x18000bc12  mov     rcx, [rsp+0E8h+var_98]; this
0x18000bc17  test    rcx, rcx
0x18000bc1a  jz      short loc_18000BC22
0x18000bc1c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bc21  nop
0x18000bc22  mov     rcx, [rsp+0E8h+var_88]; this
0x18000bc27  test    rcx, rcx
0x18000bc2a  jz      short loc_18000BC32
0x18000bc2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bc31  nop
0x18000bc32  cmp     cs:?g_ptrMiSpaceAdapter@@3V?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@A, r14; std::shared_ptr<Wsp::MiSpaceAdapter> g_ptrMiSpaceAdapter
0x18000bc39  jnz     short loc_18000BC9A
0x18000bc3b  mov     esi, 1Bh
0x18000bc40  mov     eax, cs:dword_18014B6A8
0x18000bc46  cmp     eax, 2
0x18000bc49  jbe     short loc_18000BC87
0x18000bc4b  mov     [rsp+0E8h+var_A8], esi
0x18000bc4f  mov     [rsp+0E8h+var_A4], 3Bh ; ';'
0x18000bc57  mov     [rsp+0E8h+var_A0], rdi
0x18000bc5c  lea     rax, [rsp+0E8h+var_A8]
0x18000bc61  mov     [rsp+0E8h+var_B8], rax
0x18000bc66  lea     rax, [rsp+0E8h+var_A4]
0x18000bc6b  mov     [rsp+0E8h+var_C0], rax
0x18000bc70  lea     rax, [rsp+0E8h+var_A0]
0x18000bc75  mov     [rsp+0E8h+var_C8], rax
0x18000bc7a  lea     rdx, unk_180128E10
0x18000bc81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000bc86  nop
0x18000bc87  lea     rcx, [rsp+0E8h+var_60]
0x18000bc8f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000bc94  nop
0x18000bc95  jmp     loc_18000BDD4
0x18000bc9a  lea     rcx, [rsp+0E8h+var_90]
0x18000bc9f  call    ??$make_shared@VClusterApiFactory@ClusApi@@$$V@std@@YA?AV?$shared_ptr@VClusterApiFactory@ClusApi@@@0@XZ; std::make_shared<ClusApi::ClusterApiFactory,>(void)
0x18000bca4  mov     rdx, rax
0x18000bca7  mov     rcx, [rax]
0x18000bcaa  mov     rax, [rax+8]
0x18000bcae  mov     [rdx], r14
0x18000bcb1  mov     [rdx+8], r14
0x18000bcb5  mov     [rsp+0E8h+var_80], rcx
0x18000bcba  mov     [rsp+0E8h+var_80+8], rax
0x18000bcbf  mov     rcx, [rsp+0E8h+var_88]; this
0x18000bcc4  test    rcx, rcx
0x18000bcc7  jz      short loc_18000BCCE
0x18000bcc9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bcce  lea     rcx, [rsp+0E8h+var_A0]
0x18000bcd3  call    ?CreateInstance@LogWriter@smapi@@SA?AV?$shared_ptr@UILogProvider@ClusApi@@@std@@XZ; smapi::LogWriter::CreateInstance(void)
0x18000bcd8  nop
0x18000bcd9  mov     r8, rax
0x18000bcdc  lea     rdx, [rsp+0E8h+var_80]
0x18000bce1  lea     rcx, [rsp+0E8h+var_90]
0x18000bce6  call    ?OpenStore@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@AEBV?$shared_ptr@UIClusterFactory@ClusApi@@@4@AEBV?$shared_ptr@UILogProvider@ClusApi@@@4@@Z; ClusWmi::DataStore::OpenStore(std::shared_ptr<ClusApi::IClusterFactory> const &,std::shared_ptr<ClusApi::ILogProvider> const &)
0x18000bceb  mov     rdx, rax
0x18000bcee  lea     rcx, ?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000bcf5  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x18000bcfa  mov     rcx, [rsp+0E8h+var_88]; this
0x18000bcff  test    rcx, rcx
0x18000bd02  jz      short loc_18000BD0A
0x18000bd04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd09  nop
0x18000bd0a  mov     rcx, [rsp+0E8h+var_98]; this
0x18000bd0f  test    rcx, rcx
0x18000bd12  jz      short loc_18000BD19
0x18000bd14  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd19  cmp     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, r14; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000bd20  jnz     short loc_18000BD8D
0x18000bd22  mov     esi, r15d
0x18000bd25  mov     eax, cs:dword_18014B6A8
0x18000bd2b  cmp     eax, 2
0x18000bd2e  jbe     short loc_18000BD6D
0x18000bd30  mov     [rsp+0E8h+var_A4], r15d
0x18000bd35  mov     [rsp+0E8h+var_A8], 4Dh ; 'M'
0x18000bd3d  mov     [rsp+0E8h+var_A0], rdi
0x18000bd42  lea     rax, [rsp+0E8h+var_A4]
0x18000bd47  mov     [rsp+0E8h+var_B8], rax
0x18000bd4c  lea     rax, [rsp+0E8h+var_A8]
0x18000bd51  mov     [rsp+0E8h+var_C0], rax
0x18000bd56  lea     rax, [rsp+0E8h+var_A0]
0x18000bd5b  mov     [rsp+0E8h+var_C8], rax
0x18000bd60  lea     rdx, byte_180128DD7
0x18000bd67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000bd6c  nop
0x18000bd6d  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000bd72  test    rcx, rcx
0x18000bd75  jz      short loc_18000BD7D
0x18000bd77  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd7c  nop
0x18000bd7d  lea     rcx, [rsp+0E8h+var_60]
0x18000bd85  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000bd8a  nop
0x18000bd8b  jmp     short loc_18000BDD4
0x18000bd8d  xor     edx, edx; hFile
0x18000bd8f  mov     r8d, 802h; dwFlags
0x18000bd95  lea     rcx, LibFileName; "StorageWMI.dll"
0x18000bd9c  call    cs:__imp_LoadLibraryExW
0x18000bda2  mov     cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_storageWMIResource
0x18000bda9  mov     rcx, [rsp+0E8h+var_80+8]; this
0x18000bdae  test    rcx, rcx
0x18000bdb1  jz      short loc_18000BDB9
0x18000bdb3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bdb8  nop
0x18000bdb9  lea     rcx, [rsp+0E8h+var_60]
0x18000bdc1  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_TraceLogProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_TraceLogProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000bdc6  nop
0x18000bdc7  jmp     short loc_18000BDD4
0x18000bdc9  lea     rdi, aProviderloadco; "ProviderLoadComponents"
0x18000bdd0  mov     esi, dword ptr [rsp+0E8h+var_A0]
0x18000bdd4  mov     ecx, cs:dword_18014B6A8
0x18000bdda  cmp     ecx, 5
0x18000bddd  jbe     short loc_18000BE0C
0x18000bddf  mov     dword ptr [rsp+0E8h+var_A0], 5Ch ; '\'
0x18000bde7  mov     [rsp+0E8h+var_90], rdi
0x18000bdec  lea     rax, [rsp+0E8h+var_A0]
0x18000bdf1  mov     [rsp+0E8h+var_C0], rax
0x18000bdf6  lea     rax, [rsp+0E8h+var_90]
0x18000bdfb  mov     [rsp+0E8h+var_C8], rax
0x18000be00  lea     rdx, byte_180128D71
0x18000be07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000be0c  mov     eax, esi
0x18000be0e  mov     rcx, [rsp+0E8h+var_38]
0x18000be16  xor     rcx, rsp; StackCookie
0x18000be19  call    __security_check_cookie
0x18000be1e  add     rsp, 0C0h
0x18000be25  pop     r15
0x18000be27  pop     r14
0x18000be29  pop     rdi
0x18000be2a  pop     rsi
0x18000be2b  pop     rbx
0x18000be2c  retn
```
