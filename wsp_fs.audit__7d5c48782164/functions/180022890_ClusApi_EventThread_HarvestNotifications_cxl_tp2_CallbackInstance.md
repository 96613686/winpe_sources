# ClusApi::EventThread::HarvestNotifications(cxl::tp2::CallbackInstance)

- ea: `0x180022890`
- end: `0x180022e3f`
- name: `?HarvestNotifications@EventThread@ClusApi@@AEAAXVCallbackInstance@tp2@cxl@@@Z`
- size: `1455`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000cd24`
- `0x18000cd78`
- `0x18000d600`
- `0x18000d624`
- `0x18000eb18`
- `0x180014bfc`
- `0x18001aeec`
- `0x18001c8f0`
- `0x18001cf18`
- `0x18001e18c`
- `0x18001e664`
- `0x18001f748`
- `0x1800209b0`
- `0x180022100`
- `0x180022238`
- `0x180022438`
- `0x180022580`
- `0x1800226d0`
- `0x180022890`
- `0x180022e5c`
- `0x1800ab010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180022db2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180022db2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022ba7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022ba7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002292b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022b2a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002292b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022b2a`

## string_xrefs

- `0x180022908`: `EventThread initialization failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ClusApi::EventThread::HarvestNotifications(_QWORD *a1, unsigned int a2)
{
  int v3; // r14d
  char *v4; // rbx
  _QWORD *v5; // r13
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // r15
  int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // r12
  struct cxl::TraceManager *v12; // rax
  struct cxl::TraceManager *v13; // rax
  std::_Ref_count_base *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  struct cxl::TextWriter *v17; // rcx
  struct cxl::TextWriter *v18; // rcx
  _BYTE v19[4]; // [rsp+50h] [rbp-1F8h] BYREF
  int Cluster; // [rsp+54h] [rbp-1F4h]
  int v21; // [rsp+58h] [rbp-1F0h]
  std::_Ref_count_base *v22[2]; // [rsp+60h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v23[2]; // [rsp+70h] [rbp-1D8h] BYREF
  __int128 *v24; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v25; // [rsp+88h] [rbp-1C0h] BYREF
  std::_Ref_count_base *v26; // [rsp+90h] [rbp-1B8h]
  _QWORD *v27; // [rsp+98h] [rbp-1B0h]
  _DWORD *v28; // [rsp+A8h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v29; // [rsp+B0h] [rbp-198h]
  _BYTE v30[24]; // [rsp+B8h] [rbp-190h] BYREF
  std::_Ref_count_base *v31; // [rsp+D0h] [rbp-178h]
  const cxl::Exception *v32; // [rsp+D8h] [rbp-170h] BYREF
  __int128 v33; // [rsp+E0h] [rbp-168h] BYREF
  _BYTE v34[16]; // [rsp+F0h] [rbp-158h] BYREF
  _BYTE v35[32]; // [rsp+110h] [rbp-138h] BYREF
  _BYTE v36[32]; // [rsp+130h] [rbp-118h] BYREF
  _BYTE v37[32]; // [rsp+150h] [rbp-F8h] BYREF
  _QWORD v38[7]; // [rsp+170h] [rbp-D8h] BYREF
  _QWORD *v39; // [rsp+1A8h] [rbp-A0h]
  _BYTE v40[80]; // [rsp+1B0h] [rbp-98h] BYREF

  v3 = 0;
  v21 = 0;
  *(_OWORD *)v23 = 0;
  *(_OWORD *)v22 = 0;
  Cluster = 0;
  cxl::ComThreadInit::ComThreadInit((cxl::ComThreadInit *)v19, a2);
  if ( a1[18] && (Cluster = std::_Func_class<void,>::operator()(a1 + 11), Cluster < 0) )
  {
    v4 = (char *)cxl::TraceManager::Instance() + 40;
    (*(void (__fastcall **)(char *, const wchar_t *, __int64))(*(_QWORD *)v4 + 24LL))(
      v4,
      L"EventThread initialization failed.",
      34);
    cxl::TextWriter::operator<<<cxl::ENDL>(v4);
    if ( v19[0] )
      CoUninitialize();
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
  }
  else
  {
    v5 = a1;
    v27 = a1;
    v6 = (_QWORD *)_lambda_12d803a7772cc60a367ba6992f011124_::_lambda_12d803a7772cc60a367ba6992f011124_(&v24, a1);
    v39 = 0;
    v38[0] = &std::_Func_impl_no_alloc<_lambda_c3738b52e4bf046c47318b5b59d9fa32_,void,>::`vftable';
    v38[1] = *v6;
    v39 = v38;
    cxl::LambdaScopeGuard::LambdaScopeGuard(v40, v38);
    if ( v39 )
    {
      v7 = v38;
      LOBYTE(v7) = v39 != v38;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v39 + 32LL))(v39, v7);
      v39 = 0;
    }
    cxl::ManualResetEvent::Reset((cxl::ManualResetEvent *)(a1 + 32));
    cxl::ManualResetEvent::Set((cxl::ManualResetEvent *)(a1 + 23));
    cxl::ManualResetEvent::Reset((cxl::ManualResetEvent *)(a1 + 41));
    while ( !ClusApi::EventThread::ShouldShutdown((ClusApi::EventThread *)a1) )
    {
      ClusWmi::DataStore::GetInstance(&v25);
      v8 = v25;
      if ( !v25 )
        goto LABEL_23;
      if ( !v22[0] )
      {
        Cluster = ClusWmi::DataStore::GetCluster(v25, (__int64)v23);
        if ( Cluster >= 0 )
        {
          if ( v23[0] )
          {
            v9 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *, std::_Ref_count_base **))(*(_QWORD *)v23[0] + 280LL))(
                   v23[0],
                   a1,
                   v22);
            Cluster = v9;
            if ( v9 < 0 )
              goto LABEL_22;
            v10 = a1[19];
            v11 = a1[20];
            while ( v10 != v11 )
            {
              v9 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v22[0] + 8LL))(v22[0], v10);
              Cluster = v9;
              if ( v9 < 0 )
              {
                v12 = cxl::TraceManager::Instance();
                cxl::TextWriter::WriteLine<char,long,>(
                  (struct cxl::TraceManager *)((char *)v12 + 40),
                  "Failed to register resource type(event monitor), hr = {0}");
                v9 = Cluster;
                break;
              }
              v10 += 16;
            }
            if ( v9 < 0 )
            {
LABEL_22:
              v13 = cxl::TraceManager::Instance();
              cxl::TextWriter::WriteLine<char,long,>(
                (struct cxl::TraceManager *)((char *)v13 + 40),
                "Failed to get event monitor, hr = {0}");
LABEL_23:
              if ( v26 )
                std::_Ref_count_base::_Decref(v26);
              break;
            }
          }
        }
      }
      Cluster = ClusWmi::DataStore::GetCluster(v8, (__int64)v23);
      if ( Cluster >= 0 )
      {
        if ( v23[0] && v22[0] )
        {
          v33 = 0;
          std::wstring::wstring(v34);
          std::wstring::wstring(v37);
          std::wstring::wstring(v35);
          std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(v30);
          std::wstring::wstring(v36);
          Cluster = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64, __int128 *, _BYTE *, _BYTE *, _BYTE *, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)v22[0] + 24LL))(
                      v22[0],
                      400,
                      &v33,
                      v34,
                      v37,
                      v35,
                      v30,
                      v36,
                      a1[44]);
          if ( Cluster >= 0 && !ClusApi::EventThread::ShouldShutdown((ClusApi::EventThread *)a1) )
          {
            v24 = &v33;
            try
            {
              v14 = (std::_Ref_count_base *)operator new(0xB8u);
              v31 = v14;
              *((_DWORD *)v14 + 2) = 1;
              *((_DWORD *)v14 + 3) = 1;
              *(_QWORD *)v14 = &std::_Ref_count_obj2<ClusApi::NotificationPayload>::`vftable';
              std::_Construct_in_place<ClusApi::NotificationPayload,_NOTIFY_FILTER_AND_TYPE *,std::wstring &,std::wstring &,std::wstring &,std::vector<unsigned char> &,std::wstring &>(
                (_DWORD)v14 + 16,
                (unsigned int)&v24,
                (unsigned int)v34,
                (unsigned int)v37,
                (__int64)v35,
                (__int64)v30,
                (__int64)v36);
              v3 |= 1u;
              v21 = v3;
              v28 = (_DWORD *)((char *)v14 + 16);
              v29 = v14;
              v15 = v5[10];
              if ( !v15 )
                std::_Xbad_function_call();
              v16 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v15 + 16LL))(v15, &v28);
              Cluster = v16;
              if ( v29 )
              {
                std::_Ref_count_base::_Decref(v29);
                v16 = Cluster;
              }
              if ( v16 < 0 )
              {
                v17 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
                cxl::TextWriter::WriteLine<char,_NOTIFY_FILTER_AND_TYPE,std::wstring>(v17);
              }
            }
            catch ( const cxl::Exception *v32 )
            {
              v18 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
              cxl::TextWriter::WriteLine<char,_NOTIFY_FILTER_AND_TYPE,std::wstring,cxl::Exception>(v18, (__int64)v32);
              v5 = v27;
              a1 = v27;
              v3 = v21;
            }
          }
          std::wstring::_Tidy_deallocate(v36);
          std::vector<unsigned char>::_Tidy(v30);
          std::wstring::_Tidy_deallocate(v35);
          std::wstring::_Tidy_deallocate(v37);
          std::wstring::_Tidy_deallocate(v34);
        }
      }
      else
      {
        std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(v23);
        std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(v22);
        Sleep(0x190u);
      }
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
    }
    cxl::LambdaScopeGuard::~LambdaScopeGuard((cxl::LambdaScopeGuard *)v40);
    if ( v19[0] )
      CoUninitialize();
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    if ( v23[1] )
      std::_Ref_count_base::_Decref(v23[1]);
  }
}

```

## disassembly

```asm
0x180022890  push    rbx
0x180022892  push    rsi
0x180022893  push    r12
0x180022895  push    r13
0x180022897  push    r14
0x180022899  push    r15
0x18002289b  sub     rsp, 218h
0x1800228a2  mov     rax, cs:__security_cookie
0x1800228a9  xor     rax, rsp
0x1800228ac  mov     [rsp+248h+var_48], rax
0x1800228b4  mov     rbx, rcx
0x1800228b7  xor     r14d, r14d
0x1800228ba  mov     [rsp+248h+var_1F0], r14d
0x1800228bf  xorps   xmm0, xmm0
0x1800228c2  movdqu  xmmword ptr [rsp+248h+var_1D8], xmm0
0x1800228c8  movdqu  xmmword ptr [rsp+248h+var_1E8], xmm0
0x1800228ce  mov     [rsp+248h+var_1F4], r14d
0x1800228d3  lea     rcx, [rsp+248h+var_1F8]; this
0x1800228d8  call    ??0ComThreadInit@cxl@@QEAA@K@Z; cxl::ComThreadInit::ComThreadInit(ulong)
0x1800228dd  nop
0x1800228de  cmp     [rbx+90h], r14
0x1800228e5  jz      short loc_18002294D
0x1800228e7  lea     rcx, [rbx+58h]
0x1800228eb  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800228f0  mov     [rsp+248h+var_1F4], eax
0x1800228f4  test    eax, eax
0x1800228f6  jns     short loc_18002294D
0x1800228f8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800228fd  lea     rbx, [rax+28h]
0x180022901  mov     rax, [rbx]
0x180022904  lea     r8d, [r14+22h]
0x180022908  lea     rdx, aEventthreadIni; "EventThread initialization failed."
0x18002290f  mov     rcx, rbx
0x180022912  mov     rax, [rax+18h]
0x180022916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002291b  mov     rcx, rbx
0x18002291e  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180022923  nop
0x180022924  cmp     [rsp+248h+var_1F8], r14b
0x180022929  jz      short loc_180022938
0x18002292b  call    cs:__imp_CoUninitialize
0x180022932  nop     dword ptr [rax+rax+00h]
0x180022937  nop
0x180022938  mov     rcx, [rsp+248h+var_1E8+8]; this
0x18002293d  test    rcx, rcx
0x180022940  jz      short loc_180022948
0x180022942  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022947  nop
0x180022948  jmp     loc_180022B56
0x18002294d  mov     r13, rbx
0x180022950  mov     [rsp+248h+var_1B0], rbx
0x180022958  mov     rdx, rbx
0x18002295b  lea     rcx, [rsp+248h+var_1C8]
0x180022963  call    ??0_lambda_12d803a7772cc60a367ba6992f011124_@@QEAA@PEAV?$FsStorageEventContext@UIFsStorageArrivalEventSchema@smapi@@VFsStorageArrivalEventContext@2@@smapi@@@Z; _lambda_12d803a7772cc60a367ba6992f011124_::_lambda_12d803a7772cc60a367ba6992f011124_(smapi::FsStorageEventContext<smapi::IFsStorageArrivalEventSchema,smapi::FsStorageArrivalEventContext> *)
0x180022968  mov     [rsp+248h+var_A0], 0
0x180022974  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_c3738b52e4bf046c47318b5b59d9fa32_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c3738b52e4bf046c47318b5b59d9fa32_,void,>::`vftable'
0x18002297b  mov     [rsp+248h+var_D8], rcx
0x180022983  mov     rax, [rax]
0x180022986  mov     [rsp+248h+var_D0], rax
0x18002298e  lea     rax, [rsp+248h+var_D8]
0x180022996  mov     [rsp+248h+var_A0], rax
0x18002299e  lea     rdx, [rsp+248h+var_D8]
0x1800229a6  lea     rcx, [rsp+248h+var_98]
0x1800229ae  call    ??0LambdaScopeGuard@cxl@@QEAA@AEBV?$function@$$A6AXXZ@std@@@Z; cxl::LambdaScopeGuard::LambdaScopeGuard(std::function<void (void)> const &)
0x1800229b3  nop
0x1800229b4  mov     rcx, [rsp+248h+var_A0]
0x1800229bc  test    rcx, rcx
0x1800229bf  jz      short loc_1800229E7
0x1800229c1  mov     rax, [rcx]
0x1800229c4  lea     rdx, [rsp+248h+var_D8]
0x1800229cc  cmp     rcx, rdx
0x1800229cf  setnz   dl
0x1800229d2  mov     rax, [rax+20h]
0x1800229d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229db  mov     [rsp+248h+var_A0], 0
0x1800229e7  lea     rcx, [rbx+100h]; this
0x1800229ee  call    ?Reset@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Reset(void)
0x1800229f3  lea     rcx, [rbx+0B8h]; this
0x1800229fa  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x1800229ff  lea     rcx, [rbx+148h]; this
0x180022a06  call    ?Reset@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Reset(void)
0x180022a0b  mov     rcx, rbx; this
0x180022a0e  call    ?ShouldShutdown@EventThread@ClusApi@@AEAA_NXZ; ClusApi::EventThread::ShouldShutdown(void)
0x180022a13  test    al, al
0x180022a15  jnz     loc_180022B15
0x180022a1b  lea     rcx, [rsp+248h+var_1C0]
0x180022a23  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180022a28  nop
0x180022a29  mov     r15, [rsp+248h+var_1C0]
0x180022a31  test    r15, r15
0x180022a34  jz      loc_180022B02
0x180022a3a  cmp     [rsp+248h+var_1E8], 0
0x180022a40  jnz     loc_180022B79
0x180022a46  lea     rdx, [rsp+248h+var_1D8]
0x180022a4b  mov     rcx, r15
0x180022a4e  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180022a53  mov     [rsp+248h+var_1F4], eax
0x180022a57  test    eax, eax
0x180022a59  js      loc_180022B79
0x180022a5f  mov     rcx, [rsp+248h+var_1D8]
0x180022a64  test    rcx, rcx
0x180022a67  jz      loc_180022B79
0x180022a6d  mov     rax, [rcx]
0x180022a70  lea     r8, [rsp+248h+var_1E8]
0x180022a75  mov     rdx, rbx
0x180022a78  mov     rax, [rax+118h]
0x180022a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a84  mov     [rsp+248h+var_1F4], eax
0x180022a88  test    eax, eax
0x180022a8a  js      short loc_180022AE7
0x180022a8c  mov     rsi, [rbx+98h]
0x180022a93  mov     r12, [rbx+0A0h]
0x180022a9a  cmp     rsi, r12
0x180022a9d  jz      short loc_180022ADF
0x180022a9f  mov     rcx, [rsp+248h+var_1E8]
0x180022aa4  mov     rax, [rcx]
0x180022aa7  mov     rdx, rsi
0x180022aaa  mov     rax, [rax+8]
0x180022aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ab3  mov     [rsp+248h+var_1F4], eax
0x180022ab7  test    eax, eax
0x180022ab9  js      short loc_180022AC1
0x180022abb  add     rsi, 10h
0x180022abf  jmp     short loc_180022A9A
0x180022ac1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180022ac6  lea     rcx, [rax+28h]
0x180022aca  lea     r8, [rsp+248h+var_1F4]
0x180022acf  lea     rdx, aFailedToRegist; "Failed to register resource type(event "...
0x180022ad6  call    ??$WriteLine@DJ$$V@TextWriter@cxl@@QEAAXPEBDAEBJ@Z; cxl::TextWriter::WriteLine<char,long,>(char const *,long const &)
0x180022adb  mov     eax, [rsp+248h+var_1F4]
0x180022adf  test    eax, eax
0x180022ae1  jns     loc_180022B79
0x180022ae7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180022aec  lea     rcx, [rax+28h]
0x180022af0  lea     r8, [rsp+248h+var_1F4]
0x180022af5  lea     rdx, aFailedToGetEve; "Failed to get event monitor, hr = {0}"
0x180022afc  call    ??$WriteLine@DJ$$V@TextWriter@cxl@@QEAAXPEBDAEBJ@Z; cxl::TextWriter::WriteLine<char,long,>(char const *,long const &)
0x180022b01  nop
0x180022b02  mov     rcx, [rsp+248h+var_1B8]; this
0x180022b0a  test    rcx, rcx
0x180022b0d  jz      short loc_180022B15
0x180022b0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022b14  nop
0x180022b15  lea     rcx, [rsp+248h+var_98]; this
0x180022b1d  call    ??1LambdaScopeGuard@cxl@@QEAA@XZ; cxl::LambdaScopeGuard::~LambdaScopeGuard(void)
0x180022b22  nop
0x180022b23  cmp     [rsp+248h+var_1F8], 0
0x180022b28  jz      short loc_180022B37
0x180022b2a  call    cs:__imp_CoUninitialize
0x180022b31  nop     dword ptr [rax+rax+00h]
0x180022b36  nop
0x180022b37  mov     rcx, [rsp+248h+var_1E8+8]; this
0x180022b3c  test    rcx, rcx
0x180022b3f  jz      short loc_180022B47
0x180022b41  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022b46  nop
0x180022b47  mov     rcx, [rsp+248h+var_1D8+8]; this
0x180022b4c  test    rcx, rcx
0x180022b4f  jz      short loc_180022B56
0x180022b51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022b56  mov     rcx, [rsp+248h+var_48]
0x180022b5e  xor     rcx, rsp; StackCookie
0x180022b61  call    __security_check_cookie
0x180022b66  add     rsp, 218h
0x180022b6d  pop     r15
0x180022b6f  pop     r14
0x180022b71  pop     r13
0x180022b73  pop     r12
0x180022b75  pop     rsi
0x180022b76  pop     rbx
0x180022b77  retn
0x180022b79  lea     rdx, [rsp+248h+var_1D8]
0x180022b7e  mov     rcx, r15
0x180022b81  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180022b86  mov     [rsp+248h+var_1F4], eax
0x180022b8a  test    eax, eax
0x180022b8c  jns     short loc_180022BB8
0x180022b8e  lea     rcx, [rsp+248h+var_1D8]
0x180022b93  call    ?reset@?$shared_ptr@VIFsStorageEventSubscriber@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(void)
0x180022b98  lea     rcx, [rsp+248h+var_1E8]
0x180022b9d  call    ?reset@?$shared_ptr@VIFsStorageEventSubscriber@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(void)
0x180022ba2  mov     ecx, 190h; dwMilliseconds
0x180022ba7  call    cs:__imp_Sleep
0x180022bae  nop     dword ptr [rax+rax+00h]
0x180022bb3  jmp     loc_180022CD8
0x180022bb8  cmp     [rsp+248h+var_1D8], 0
0x180022bbe  jz      loc_180022CD8
0x180022bc4  cmp     [rsp+248h+var_1E8], 0
0x180022bca  jz      loc_180022CD8
0x180022bd0  xorps   xmm0, xmm0
0x180022bd3  movups  [rsp+248h+var_168], xmm0
0x180022bdb  lea     rcx, [rsp+248h+var_158]
0x180022be3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022be8  nop
0x180022be9  lea     rcx, [rsp+248h+var_F8]
0x180022bf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022bf6  nop
0x180022bf7  lea     rcx, [rsp+248h+var_138]
0x180022bff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022c04  nop
0x180022c05  lea     rcx, [rsp+248h+var_190]
0x180022c0d  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180022c12  nop
0x180022c13  lea     rcx, [rsp+248h+var_118]
0x180022c1b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022c20  nop
0x180022c21  mov     rcx, [rsp+248h+var_1E8]
0x180022c26  mov     rax, [rcx]
0x180022c29  mov     rdx, [rbx+160h]
0x180022c30  mov     [rsp+248h+var_208], rdx
0x180022c35  lea     rdx, [rsp+248h+var_118]
0x180022c3d  mov     [rsp+248h+var_210], rdx
0x180022c42  lea     rdx, [rsp+248h+var_190]
0x180022c4a  mov     [rsp+248h+var_218], rdx
0x180022c4f  lea     rdx, [rsp+248h+var_138]
0x180022c57  mov     [rsp+248h+var_220], rdx
0x180022c5c  lea     rdx, [rsp+248h+var_F8]
0x180022c64  mov     [rsp+248h+var_228], rdx
0x180022c69  lea     r9, [rsp+248h+var_158]
0x180022c71  lea     r8, [rsp+248h+var_168]
0x180022c79  mov     edx, 190h
0x180022c7e  mov     rax, [rax+18h]
0x180022c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c87  mov     [rsp+248h+var_1F4], eax
0x180022c8b  cmp     eax, 80070102h
0x180022c90  jnz     short loc_180022CF3
0x180022c92  lea     rcx, [rsp+248h+var_118]
0x180022c9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022c9f  nop
0x180022ca0  lea     rcx, [rsp+248h+var_190]
0x180022ca8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022cad  nop
0x180022cae  lea     rcx, [rsp+248h+var_138]
0x180022cb6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022cbb  nop
0x180022cbc  lea     rcx, [rsp+248h+var_F8]
0x180022cc4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022cc9  nop
0x180022cca  lea     rcx, [rsp+248h+var_158]
0x180022cd2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022cd7  nop
0x180022cd8  mov     rcx, [rsp+248h+var_1B8]; this
0x180022ce0  test    rcx, rcx
0x180022ce3  jz      loc_180022A0B
0x180022ce9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022cee  jmp     loc_180022A0B
0x180022cf3  test    eax, eax
0x180022cf5  js      short loc_180022C92
0x180022cf7  mov     rcx, rbx; this
0x180022cfa  call    ?ShouldShutdown@EventThread@ClusApi@@AEAA_NXZ; ClusApi::EventThread::ShouldShutdown(void)
0x180022cff  test    al, al
0x180022d01  jnz     loc_180022E24
0x180022d07  lea     rax, [rsp+248h+var_168]
0x180022d0f  mov     [rsp+248h+var_1C8], rax
0x180022d17  mov     ecx, 0B8h; Size
0x180022d1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022d21  mov     rsi, rax
0x180022d24  mov     [rsp+248h+var_178], rax
0x180022d2c  mov     dword ptr [rax+8], 1
0x180022d33  mov     dword ptr [rax+0Ch], 1
0x180022d3a  lea     rax, ??_7?$_Ref_count_obj2@UNotificationPayload@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::NotificationPayload>::`vftable'
0x180022d41  mov     [rsi], rax
0x180022d44  lea     r15, [rsi+10h]
0x180022d48  lea     rax, [rsp+248h+var_118]
0x180022d50  mov     [rsp+248h+var_218], rax
0x180022d55  lea     rax, [rsp+248h+var_190]
0x180022d5d  mov     [rsp+248h+var_220], rax
0x180022d62  lea     rax, [rsp+248h+var_138]
0x180022d6a  mov     [rsp+248h+var_228], rax
0x180022d6f  lea     r9, [rsp+248h+var_F8]
0x180022d77  lea     r8, [rsp+248h+var_158]
0x180022d7f  lea     rdx, [rsp+248h+var_1C8]
0x180022d87  mov     rcx, r15
0x180022d8a  call    ??$_Construct_in_place@UNotificationPayload@ClusApi@@PEAU_NOTIFY_FILTER_AND_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAV45@AEAV?$vector@EV?$allocator@E@std@@@5@AEAV45@@std@@YAXAEAUNotificationPayload@ClusApi@@$$QEAPEAU_NOTIFY_FILTER_AND_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@22AEAV?$vector@EV?$allocator@E@std@@@0@2@Z; std::_Construct_in_place<ClusApi::NotificationPayload,_NOTIFY_FILTER_AND_TYPE *,std::wstring &,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &>(ClusApi::NotificationPayload &,_NOTIFY_FILTER_AND_TYPE * &&,std::wstring &,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &)
0x180022d8f  nop
0x180022d90  or      r14d, 1
0x180022d94  mov     [rsp+248h+var_1F0], r14d
0x180022d99  mov     [rsp+248h+var_1A0], r15
0x180022da1  mov     [rsp+248h+var_198], rsi
0x180022da9  mov     rcx, [r13+50h]
0x180022dad  test    rcx, rcx
0x180022db0  jnz     short loc_180022DBE
0x180022db2  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180022db9  nop     dword ptr [rax+rax+00h]
0x180022dbe  mov     rax, [rcx]
0x180022dc1  lea     rdx, [rsp+248h+var_1A0]
0x180022dc9  mov     rax, [rax+10h]
0x180022dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd2  mov     [rsp+248h+var_1F4], eax
0x180022dd6  mov     rcx, [rsp+248h+var_198]; this
0x180022dde  test    rcx, rcx
0x180022de1  jz      short loc_180022DEC
0x180022de3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022de8  mov     eax, [rsp+248h+var_1F4]
0x180022dec  test    eax, eax
0x180022dee  jns     short loc_180022E24
0x180022df0  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180022df5  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180022df9  lea     r9, [rsp+248h+var_158]
0x180022e01  lea     rax, [rsp+248h+var_138]
  ... truncated ...
```
