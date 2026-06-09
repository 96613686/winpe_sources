# ServiceMain(ulong,ushort * * const)

- ea: `0x1800140a0`
- end: `0x18001438c`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `748`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800011e4`
- `0x180001510`
- `0x18000166c`
- `0x180002050`
- `0x180003348`
- `0x180004018`
- `0x1800051f0`
- `0x180006844`
- `0x18000acdc`
- `0x1800140a0`
- `0x180014440`
- `0x1800144ac`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014138`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014138`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014358`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014358`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800140d7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800140d7`

## string_xrefs

- `0x1800141a7`: `Windows.Devices.Enumeration.DeviceAccessInformation`
- `0x180014310`: `TZ auto update session failed to initialize`
- `0x1800142b3`: `TZ auto update session started`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  unsigned int v3; // edx
  HANDLE EventW; // r8
  _BYTE *v5; // rdx
  bool v6; // r14
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  TzautoupdateWorker *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // r9d
  int v20; // r9d
  _BYTE v21[32]; // [rsp+0h] [rbp-88h] BYREF
  __int64 v22; // [rsp+40h] [rbp-48h] BYREF
  __int64 v23; // [rsp+48h] [rbp-40h] BYREF
  __int64 v24; // [rsp+50h] [rbp-38h] BYREF
  __m256i hstringHeader; // [rsp+58h] [rbp-30h] BYREF

  if ( a1 )
  {
    gSvcStatusHandle = RegisterServiceCtrlHandlerW(*a2, ServiceHandler);
    if ( gSvcStatusHandle )
    {
      memset(&hstringHeader, 0, 28);
      gSvcStatus.dwServiceType = 32;
      xmmword_180031364 = *(_OWORD *)((char *)hstringHeader.m256i_i64 + 4);
      qword_180031374 = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
      UpdateServiceStatus(2u, v3, 0x3E8u);
      EventW = CreateEventW(0, 1, 0, 0);
      ghSvcStopEvent = EventW;
      if ( EventW )
      {
        (*((void (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))gpServiceHostGlobalData
         + 24))(
          &ghRegisteredWait,
          *a2,
          EventW,
          ServiceStop,
          0,
          24);
        TraceLoggingRegisterEx_EventRegister_EventSetInformation();
        v24 = 0;
        hstringHeader.m256i_i64[3] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)&hstringHeader,
          L"Windows.Devices.Enumeration.DeviceAccessInformation",
          0x34u,
          0x33u);
        if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(
                    hstringHeader.m256i_i64[3],
                    &v24) < 0 )
          goto LABEL_21;
        v6 = 0;
        v22 = 0;
        v7 = v24;
        v8 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
        if ( v8(v7, 6, &v22) >= 0 )
        {
          LODWORD(v23) = 0;
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 64LL))(v22, &v23) >= 0 )
            v6 = (_DWORD)v23 == 1;
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
        if ( !v6 )
          goto LABEL_21;
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v9 = (TzautoupdateWorker *)operator new(0x1B0u);
          v22 = (__int64)v9;
          if ( v9 )
            v9 = TzautoupdateWorker::TzautoupdateWorker(v9, 0x3Cu, 0, 0);
          v22 = 0;
          std::unique_ptr<TzautoupdateWorker>::reset(v10, v9);
          std::unique_ptr<TzautoupdateWorker>::_Delete(&v22);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v5 = v21;
            if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v12) )
            {
              v22 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                v11,
                (int)&byte_180029A47,
                v12,
                v19,
                (__int64)&v22);
            }
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800142F6);
            goto LABEL_13;
          }
          if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
          {
            v5 = v21;
            if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v12) )
            {
              v22 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                v11,
                (int)&word_180029B2E,
                v12,
                v20,
                (__int64)&v22);
            }
            __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_18001428B);
          }
        }
LABEL_13:
        if ( gTzautoupdateWorker )
        {
          if ( (unsigned int)dword_180030000 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12) )
            {
              v22 = (__int64)L"TZ auto update session started";
              v23 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
                v13,
                (int)word_180029AEA,
                v14,
                v15,
                (__int64)&v23,
                (__int64)&v22);
            }
          }
          UpdateServiceStatus(4u, (unsigned int)v5, 0);
          goto LABEL_22;
        }
        if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12) )
        {
          v22 = (__int64)L"TZ auto update session failed to initialize";
          v23 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            v16,
            (int)byte_180029A79,
            v17,
            v18,
            (__int64)&v23,
            (__int64)&v22);
        }
LABEL_21:
        UpdateServiceStatus(4u, (unsigned int)v5, 0);
        SetEvent(ghSvcStopEvent);
LABEL_22:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      }
    }
  }
}

```

## disassembly

```asm
0x1800140a0  test    ecx, ecx
0x1800140a2  jz      locret_18001438B
0x1800140a8  mov     [rsp+arg_0], rbx
0x1800140ad  mov     [rsp+arg_10], rdi
0x1800140b2  push    r14
0x1800140b4  sub     rsp, 80h
0x1800140bb  mov     rax, cs:__security_cookie
0x1800140c2  xor     rax, rsp
0x1800140c5  mov     [rsp+88h+var_10], rax
0x1800140ca  mov     rbx, rdx
0x1800140cd  lea     rdx, ?ServiceHandler@@YAXK@Z; lpHandlerProc
0x1800140d4  mov     rcx, [rbx]; lpServiceName
0x1800140d7  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1800140dd  mov     cs:?gSvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * gSvcStatusHandle
0x1800140e4  test    rax, rax
0x1800140e7  jz      loc_180014369
0x1800140ed  xorps   xmm1, xmm1
0x1800140f0  movups  xmmword ptr [rsp+88h+hstringHeader.Reserved], xmm1
0x1800140f5  movups  xmmword ptr [rsp+88h+hstringHeader.Reserved+0Ch], xmm1
0x1800140fa  mov     cs:?gSvcStatus@@3U_SERVICE_STATUS@@A, 20h ; ' '; _SERVICE_STATUS gSvcStatus
0x180014104  movups  xmm0, xmmword ptr [rsp+88h+hstringHeader.Reserved+4]
0x180014109  movups  cs:xmmword_180031364, xmm0
0x180014110  unpckhpd xmm1, xmm1
0x180014114  movsd   cs:qword_180031374, xmm1
0x18001411c  mov     ecx, 2; unsigned int
0x180014121  mov     r8d, 3E8h; unsigned int
0x180014127  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18001412c  xor     r9d, r9d; lpName
0x18001412f  xor     r8d, r8d; bInitialState
0x180014132  lea     edx, [r9+1]; bManualReset
0x180014136  xor     ecx, ecx; lpEventAttributes
0x180014138  call    cs:__imp_CreateEventW
0x18001413e  mov     r8, rax
0x180014141  mov     cs:?ghSvcStopEvent@@3PEAXEA, rax; void * ghSvcStopEvent
0x180014148  test    rax, rax
0x18001414b  jz      loc_180014369
0x180014151  mov     rax, cs:?gpServiceHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * gpServiceHostGlobalData
0x180014158  mov     dword ptr [rsp+88h+var_60], 18h
0x180014160  mov     [rsp+88h+var_68], 0
0x180014169  lea     r9, ?ServiceStop@@YAXPEAXE@Z; ServiceStop(void *,uchar)
0x180014170  mov     rdx, [rbx]
0x180014173  lea     rcx, ?ghRegisteredWait@@3PEAXEA; void * ghRegisteredWait
0x18001417a  mov     rax, [rax+0C0h]
0x180014181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014186  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001418b  mov     [rsp+88h+var_38], 0
0x180014194  mov     [rsp+88h+var_18], 0
0x18001419d  mov     r9d, 33h ; '3'; unsigned int
0x1800141a3  lea     r8d, [r9+1]; unsigned int
0x1800141a7  lea     rdx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceAccessInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceAcces"...
0x1800141ae  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x1800141b3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800141b8  lea     rdx, [rsp+88h+var_38]
0x1800141bd  mov     rcx, [rsp+88h+var_18]
0x1800141c2  call    ??$GetActivationFactory@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>)
0x1800141c7  test    eax, eax
0x1800141c9  js      loc_180014345
0x1800141cf  xor     r14b, r14b
0x1800141d2  mov     [rsp+88h+var_48], 0
0x1800141db  mov     rdi, [rsp+88h+var_38]
0x1800141e0  mov     rax, [rdi]
0x1800141e3  mov     rbx, [rax+40h]
0x1800141e7  lea     rcx, [rsp+88h+var_48]
0x1800141ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800141f1  lea     r8, [rsp+88h+var_48]
0x1800141f6  mov     edx, 6
0x1800141fb  mov     rcx, rdi
0x1800141fe  mov     rax, rbx
0x180014201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014206  test    eax, eax
0x180014208  js      short loc_180014235
0x18001420a  mov     dword ptr [rsp+88h+var_40], 0
0x180014212  mov     rcx, [rsp+88h+var_48]
0x180014217  mov     rax, [rcx]
0x18001421a  lea     rdx, [rsp+88h+var_40]
0x18001421f  mov     rax, [rax+40h]
0x180014223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014228  test    eax, eax
0x18001422a  js      short loc_180014235
0x18001422c  cmp     dword ptr [rsp+88h+var_40], 1
0x180014231  setz    r14b
0x180014235  lea     rcx, [rsp+88h+var_48]
0x18001423a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001423f  test    r14b, r14b
0x180014242  jz      loc_180014345
0x180014248  mov     ecx, 1B0h; Size
0x18001424d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014252  mov     [rsp+88h+var_48], rax
0x180014257  test    rax, rax
0x18001425a  jz      short loc_18001426F
0x18001425c  xor     r9d, r9d; void *
0x18001425f  xor     r8d, r8d; bool
0x180014262  lea     edx, [r9+3Ch]; unsigned int
0x180014266  mov     rcx, rax; this
0x180014269  call    ??0TzautoupdateWorker@@QEAA@K_NPEAX@Z; TzautoupdateWorker::TzautoupdateWorker(ulong,bool,void *)
0x18001426e  nop
0x18001426f  mov     [rsp+88h+var_48], 0
0x180014278  mov     rdx, rax
0x18001427b  call    ?reset@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@QEAAXPEAVTzautoupdateWorker@@@Z; std::unique_ptr<TzautoupdateWorker>::reset(TzautoupdateWorker *)
0x180014280  lea     rcx, [rsp+88h+var_48]
0x180014285  call    ?_Delete@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@AEAAXXZ; std::unique_ptr<TzautoupdateWorker>::_Delete(void)
0x18001428a  nop
0x18001428b  cmp     cs:?gTzautoupdateWorker@@3V?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@A, 0; std::unique_ptr<TzautoupdateWorker> gTzautoupdateWorker
0x180014293  mov     eax, cs:dword_180030000
0x180014299  jz      short loc_1800142F8
0x18001429b  cmp     eax, 5
0x18001429e  jbe     short loc_1800142E8
0x1800142a0  mov     rdx, 400000000000h
0x1800142aa  call    _tlgKeywordOn
0x1800142af  test    al, al
0x1800142b1  jz      short loc_1800142E8
0x1800142b3  lea     rax, aTzAutoUpdateSe_0; "TZ auto update session started"
0x1800142ba  mov     [rsp+88h+var_48], rax
0x1800142bf  mov     [rsp+88h+var_40], 1000000h
0x1800142c8  lea     rax, [rsp+88h+var_48]
0x1800142cd  mov     [rsp+88h+var_60], rax
0x1800142d2  lea     rax, [rsp+88h+var_40]
0x1800142d7  mov     [rsp+88h+var_68], rax
0x1800142dc  lea     rdx, word_180029AEA
0x1800142e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800142e8  xor     r8d, r8d; unsigned int
0x1800142eb  lea     ecx, [r8+4]; unsigned int
0x1800142ef  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x1800142f4  jmp     short loc_18001435F
0x1800142f6  jmp     short loc_18001428B
0x1800142f8  cmp     eax, 5
0x1800142fb  jbe     short loc_180014345
0x1800142fd  mov     rdx, 400000000000h
0x180014307  call    _tlgKeywordOn
0x18001430c  test    al, al
0x18001430e  jz      short loc_180014345
0x180014310  lea     rax, aTzAutoUpdateSe; "TZ auto update session failed to initia"...
0x180014317  mov     [rsp+88h+var_48], rax
0x18001431c  mov     [rsp+88h+var_40], 1000000h
0x180014325  lea     rax, [rsp+88h+var_48]
0x18001432a  mov     [rsp+88h+var_60], rax
0x18001432f  lea     rax, [rsp+88h+var_40]
0x180014334  mov     [rsp+88h+var_68], rax
0x180014339  lea     rdx, byte_180029A79
0x180014340  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180014345  xor     r8d, r8d; unsigned int
0x180014348  lea     ecx, [r8+4]; unsigned int
0x18001434c  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180014351  mov     rcx, cs:?ghSvcStopEvent@@3PEAXEA; hEvent
0x180014358  call    cs:__imp_SetEvent
0x18001435e  nop
0x18001435f  lea     rcx, [rsp+88h+var_38]
0x180014364  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180014369  mov     rcx, [rsp+88h+var_10]
0x18001436e  xor     rcx, rsp; StackCookie
0x180014371  call    __security_check_cookie
0x180014376  lea     r11, [rsp+88h+var_8]
0x18001437e  mov     rbx, [r11+10h]
0x180014382  mov     rdi, [r11+20h]
0x180014386  mov     rsp, r11
0x180014389  pop     r14
0x18001438b  retn
```
