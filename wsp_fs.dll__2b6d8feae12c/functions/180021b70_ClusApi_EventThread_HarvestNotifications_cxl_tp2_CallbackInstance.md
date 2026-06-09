# ClusApi::EventThread::HarvestNotifications(cxl::tp2::CallbackInstance)

- ea: `0x180021b70`
- end: `0x180022106`
- name: `?HarvestNotifications@EventThread@ClusApi@@AEAAXVCallbackInstance@tp2@cxl@@@Z`
- size: `1430`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000c9dc`
- `0x18000ca2c`
- `0x18000d298`
- `0x18000d2bc`
- `0x18000e6f4`
- `0x1800145a0`
- `0x18001a4d0`
- `0x18001be30`
- `0x18001c424`
- `0x18001d5f8`
- `0x18001da94`
- `0x18001eb24`
- `0x18001fd48`
- `0x18002144c`
- `0x180021588`
- `0x18002173c`
- `0x18002187c`
- `0x1800219bc`
- `0x180021b70`
- `0x180022120`
- `0x1800a9010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002207f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002207f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021e7a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021e7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021c0b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021e04`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021c0b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021e04`

## string_xrefs

- `0x180021be8`: `EventThread initialization failed.`

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
    cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v4);
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
0x180021b70  push    rbx
0x180021b72  push    rsi
0x180021b73  push    r12
0x180021b75  push    r13
0x180021b77  push    r14
0x180021b79  push    r15
0x180021b7b  sub     rsp, 218h
0x180021b82  mov     rax, cs:__security_cookie
0x180021b89  xor     rax, rsp
0x180021b8c  mov     [rsp+248h+var_48], rax
0x180021b94  mov     rbx, rcx
0x180021b97  xor     r14d, r14d
0x180021b9a  mov     [rsp+248h+var_1F0], r14d
0x180021b9f  xorps   xmm0, xmm0
0x180021ba2  movdqu  xmmword ptr [rsp+248h+var_1D8], xmm0
0x180021ba8  movdqu  xmmword ptr [rsp+248h+var_1E8], xmm0
0x180021bae  mov     [rsp+248h+var_1F4], r14d
0x180021bb3  lea     rcx, [rsp+248h+var_1F8]; this
0x180021bb8  call    ??0ComThreadInit@cxl@@QEAA@K@Z; cxl::ComThreadInit::ComThreadInit(ulong)
0x180021bbd  nop
0x180021bbe  cmp     [rbx+90h], r14
0x180021bc5  jz      short loc_180021C27
0x180021bc7  lea     rcx, [rbx+58h]
0x180021bcb  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180021bd0  mov     [rsp+248h+var_1F4], eax
0x180021bd4  test    eax, eax
0x180021bd6  jns     short loc_180021C27
0x180021bd8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180021bdd  lea     rbx, [rax+28h]
0x180021be1  mov     rax, [rbx]
0x180021be4  lea     r8d, [r14+22h]
0x180021be8  lea     rdx, aEventthreadIni; "EventThread initialization failed."
0x180021bef  mov     rcx, rbx
0x180021bf2  mov     rax, [rax+18h]
0x180021bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bfb  mov     rcx, rbx
0x180021bfe  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180021c03  nop
0x180021c04  cmp     [rsp+248h+var_1F8], r14b
0x180021c09  jz      short loc_180021C12
0x180021c0b  call    cs:__imp_CoUninitialize
0x180021c11  nop
0x180021c12  mov     rcx, [rsp+248h+var_1E8+8]; this
0x180021c17  test    rcx, rcx
0x180021c1a  jz      short loc_180021C22
0x180021c1c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021c21  nop
0x180021c22  jmp     loc_180021E2A
0x180021c27  mov     r13, rbx
0x180021c2a  mov     [rsp+248h+var_1B0], rbx
0x180021c32  mov     rdx, rbx
0x180021c35  lea     rcx, [rsp+248h+var_1C8]
0x180021c3d  call    ??0_lambda_12d803a7772cc60a367ba6992f011124_@@QEAA@PEAV?$FsStorageEventContext@UIFsStorageArrivalEventSchema@smapi@@VFsStorageArrivalEventContext@2@@smapi@@@Z; _lambda_12d803a7772cc60a367ba6992f011124_::_lambda_12d803a7772cc60a367ba6992f011124_(smapi::FsStorageEventContext<smapi::IFsStorageArrivalEventSchema,smapi::FsStorageArrivalEventContext> *)
0x180021c42  mov     [rsp+248h+var_A0], 0
0x180021c4e  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_c3738b52e4bf046c47318b5b59d9fa32_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c3738b52e4bf046c47318b5b59d9fa32_,void,>::`vftable'
0x180021c55  mov     [rsp+248h+var_D8], rcx
0x180021c5d  mov     rax, [rax]
0x180021c60  mov     [rsp+248h+var_D0], rax
0x180021c68  lea     rax, [rsp+248h+var_D8]
0x180021c70  mov     [rsp+248h+var_A0], rax
0x180021c78  lea     rdx, [rsp+248h+var_D8]
0x180021c80  lea     rcx, [rsp+248h+var_98]
0x180021c88  call    ??0LambdaScopeGuard@cxl@@QEAA@AEBV?$function@$$A6AXXZ@std@@@Z; cxl::LambdaScopeGuard::LambdaScopeGuard(std::function<void (void)> const &)
0x180021c8d  nop
0x180021c8e  mov     rcx, [rsp+248h+var_A0]
0x180021c96  test    rcx, rcx
0x180021c99  jz      short loc_180021CC1
0x180021c9b  mov     rax, [rcx]
0x180021c9e  lea     rdx, [rsp+248h+var_D8]
0x180021ca6  cmp     rcx, rdx
0x180021ca9  setnz   dl
0x180021cac  mov     rax, [rax+20h]
0x180021cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cb5  mov     [rsp+248h+var_A0], 0
0x180021cc1  lea     rcx, [rbx+100h]; this
0x180021cc8  call    ?Reset@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Reset(void)
0x180021ccd  lea     rcx, [rbx+0B8h]; this
0x180021cd4  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x180021cd9  lea     rcx, [rbx+148h]; this
0x180021ce0  call    ?Reset@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Reset(void)
0x180021ce5  mov     rcx, rbx; this
0x180021ce8  call    ?ShouldShutdown@EventThread@ClusApi@@AEAA_NXZ; ClusApi::EventThread::ShouldShutdown(void)
0x180021ced  test    al, al
0x180021cef  jnz     loc_180021DEF
0x180021cf5  lea     rcx, [rsp+248h+var_1C0]
0x180021cfd  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x180021d02  nop
0x180021d03  mov     r15, [rsp+248h+var_1C0]
0x180021d0b  test    r15, r15
0x180021d0e  jz      loc_180021DDC
0x180021d14  cmp     [rsp+248h+var_1E8], 0
0x180021d1a  jnz     loc_180021E4C
0x180021d20  lea     rdx, [rsp+248h+var_1D8]
0x180021d25  mov     rcx, r15
0x180021d28  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180021d2d  mov     [rsp+248h+var_1F4], eax
0x180021d31  test    eax, eax
0x180021d33  js      loc_180021E4C
0x180021d39  mov     rcx, [rsp+248h+var_1D8]
0x180021d3e  test    rcx, rcx
0x180021d41  jz      loc_180021E4C
0x180021d47  mov     rax, [rcx]
0x180021d4a  lea     r8, [rsp+248h+var_1E8]
0x180021d4f  mov     rdx, rbx
0x180021d52  mov     rax, [rax+118h]
0x180021d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d5e  mov     [rsp+248h+var_1F4], eax
0x180021d62  test    eax, eax
0x180021d64  js      short loc_180021DC1
0x180021d66  mov     rsi, [rbx+98h]
0x180021d6d  mov     r12, [rbx+0A0h]
0x180021d74  cmp     rsi, r12
0x180021d77  jz      short loc_180021DB9
0x180021d79  mov     rcx, [rsp+248h+var_1E8]
0x180021d7e  mov     rax, [rcx]
0x180021d81  mov     rdx, rsi
0x180021d84  mov     rax, [rax+8]
0x180021d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d8d  mov     [rsp+248h+var_1F4], eax
0x180021d91  test    eax, eax
0x180021d93  js      short loc_180021D9B
0x180021d95  add     rsi, 10h
0x180021d99  jmp     short loc_180021D74
0x180021d9b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180021da0  lea     rcx, [rax+28h]
0x180021da4  lea     r8, [rsp+248h+var_1F4]
0x180021da9  lea     rdx, aFailedToRegist; "Failed to register resource type(event "...
0x180021db0  call    ??$WriteLine@DJ$$V@TextWriter@cxl@@QEAAXPEBDAEBJ@Z; cxl::TextWriter::WriteLine<char,long,>(char const *,long const &)
0x180021db5  mov     eax, [rsp+248h+var_1F4]
0x180021db9  test    eax, eax
0x180021dbb  jns     loc_180021E4C
0x180021dc1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180021dc6  lea     rcx, [rax+28h]
0x180021dca  lea     r8, [rsp+248h+var_1F4]
0x180021dcf  lea     rdx, aFailedToGetEve; "Failed to get event monitor, hr = {0}"
0x180021dd6  call    ??$WriteLine@DJ$$V@TextWriter@cxl@@QEAAXPEBDAEBJ@Z; cxl::TextWriter::WriteLine<char,long,>(char const *,long const &)
0x180021ddb  nop
0x180021ddc  mov     rcx, [rsp+248h+var_1B8]; this
0x180021de4  test    rcx, rcx
0x180021de7  jz      short loc_180021DEF
0x180021de9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021dee  nop
0x180021def  lea     rcx, [rsp+248h+var_98]; this
0x180021df7  call    ??1LambdaScopeGuard@cxl@@QEAA@XZ; cxl::LambdaScopeGuard::~LambdaScopeGuard(void)
0x180021dfc  nop
0x180021dfd  cmp     [rsp+248h+var_1F8], 0
0x180021e02  jz      short loc_180021E0B
0x180021e04  call    cs:__imp_CoUninitialize
0x180021e0a  nop
0x180021e0b  mov     rcx, [rsp+248h+var_1E8+8]; this
0x180021e10  test    rcx, rcx
0x180021e13  jz      short loc_180021E1B
0x180021e15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021e1a  nop
0x180021e1b  mov     rcx, [rsp+248h+var_1D8+8]; this
0x180021e20  test    rcx, rcx
0x180021e23  jz      short loc_180021E2A
0x180021e25  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021e2a  mov     rcx, [rsp+248h+var_48]
0x180021e32  xor     rcx, rsp; StackCookie
0x180021e35  call    __security_check_cookie
0x180021e3a  add     rsp, 218h
0x180021e41  pop     r15
0x180021e43  pop     r14
0x180021e45  pop     r13
0x180021e47  pop     r12
0x180021e49  pop     rsi
0x180021e4a  pop     rbx
0x180021e4b  retn
0x180021e4c  lea     rdx, [rsp+248h+var_1D8]
0x180021e51  mov     rcx, r15
0x180021e54  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x180021e59  mov     [rsp+248h+var_1F4], eax
0x180021e5d  test    eax, eax
0x180021e5f  jns     short loc_180021E85
0x180021e61  lea     rcx, [rsp+248h+var_1D8]
0x180021e66  call    ?reset@?$shared_ptr@VIFsStorageEventSubscriber@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(void)
0x180021e6b  lea     rcx, [rsp+248h+var_1E8]
0x180021e70  call    ?reset@?$shared_ptr@VIFsStorageEventSubscriber@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::IFsStorageEventSubscriber>::reset(void)
0x180021e75  mov     ecx, 190h; dwMilliseconds
0x180021e7a  call    cs:__imp_Sleep
0x180021e80  jmp     loc_180021FA5
0x180021e85  cmp     [rsp+248h+var_1D8], 0
0x180021e8b  jz      loc_180021FA5
0x180021e91  cmp     [rsp+248h+var_1E8], 0
0x180021e97  jz      loc_180021FA5
0x180021e9d  xorps   xmm0, xmm0
0x180021ea0  movups  [rsp+248h+var_168], xmm0
0x180021ea8  lea     rcx, [rsp+248h+var_158]
0x180021eb0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180021eb5  nop
0x180021eb6  lea     rcx, [rsp+248h+var_F8]
0x180021ebe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180021ec3  nop
0x180021ec4  lea     rcx, [rsp+248h+var_138]
0x180021ecc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180021ed1  nop
0x180021ed2  lea     rcx, [rsp+248h+var_190]
0x180021eda  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180021edf  nop
0x180021ee0  lea     rcx, [rsp+248h+var_118]
0x180021ee8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180021eed  nop
0x180021eee  mov     rcx, [rsp+248h+var_1E8]
0x180021ef3  mov     rax, [rcx]
0x180021ef6  mov     rdx, [rbx+160h]
0x180021efd  mov     [rsp+248h+var_208], rdx
0x180021f02  lea     rdx, [rsp+248h+var_118]
0x180021f0a  mov     [rsp+248h+var_210], rdx
0x180021f0f  lea     rdx, [rsp+248h+var_190]
0x180021f17  mov     [rsp+248h+var_218], rdx
0x180021f1c  lea     rdx, [rsp+248h+var_138]
0x180021f24  mov     [rsp+248h+var_220], rdx
0x180021f29  lea     rdx, [rsp+248h+var_F8]
0x180021f31  mov     [rsp+248h+var_228], rdx
0x180021f36  lea     r9, [rsp+248h+var_158]
0x180021f3e  lea     r8, [rsp+248h+var_168]
0x180021f46  mov     edx, 190h
0x180021f4b  mov     rax, [rax+18h]
0x180021f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f54  mov     [rsp+248h+var_1F4], eax
0x180021f58  cmp     eax, 80070102h
0x180021f5d  jnz     short loc_180021FC0
0x180021f5f  lea     rcx, [rsp+248h+var_118]
0x180021f67  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021f6c  nop
0x180021f6d  lea     rcx, [rsp+248h+var_190]
0x180021f75  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021f7a  nop
0x180021f7b  lea     rcx, [rsp+248h+var_138]
0x180021f83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021f88  nop
0x180021f89  lea     rcx, [rsp+248h+var_F8]
0x180021f91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021f96  nop
0x180021f97  lea     rcx, [rsp+248h+var_158]
0x180021f9f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021fa4  nop
0x180021fa5  mov     rcx, [rsp+248h+var_1B8]; this
0x180021fad  test    rcx, rcx
0x180021fb0  jz      loc_180021CE5
0x180021fb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021fbb  jmp     loc_180021CE5
0x180021fc0  test    eax, eax
0x180021fc2  js      short loc_180021F5F
0x180021fc4  mov     rcx, rbx; this
0x180021fc7  call    ?ShouldShutdown@EventThread@ClusApi@@AEAA_NXZ; ClusApi::EventThread::ShouldShutdown(void)
0x180021fcc  test    al, al
0x180021fce  jnz     loc_1800220EB
0x180021fd4  lea     rax, [rsp+248h+var_168]
0x180021fdc  mov     [rsp+248h+var_1C8], rax
0x180021fe4  mov     ecx, 0B8h; Size
0x180021fe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021fee  mov     rsi, rax
0x180021ff1  mov     [rsp+248h+var_178], rax
0x180021ff9  mov     dword ptr [rax+8], 1
0x180022000  mov     dword ptr [rax+0Ch], 1
0x180022007  lea     rax, ??_7?$_Ref_count_obj2@UNotificationPayload@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::NotificationPayload>::`vftable'
0x18002200e  mov     [rsi], rax
0x180022011  lea     r15, [rsi+10h]
0x180022015  lea     rax, [rsp+248h+var_118]
0x18002201d  mov     [rsp+248h+var_218], rax
0x180022022  lea     rax, [rsp+248h+var_190]
0x18002202a  mov     [rsp+248h+var_220], rax
0x18002202f  lea     rax, [rsp+248h+var_138]
0x180022037  mov     [rsp+248h+var_228], rax
0x18002203c  lea     r9, [rsp+248h+var_F8]
0x180022044  lea     r8, [rsp+248h+var_158]
0x18002204c  lea     rdx, [rsp+248h+var_1C8]
0x180022054  mov     rcx, r15
0x180022057  call    ??$_Construct_in_place@UNotificationPayload@ClusApi@@PEAU_NOTIFY_FILTER_AND_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAV45@AEAV?$vector@EV?$allocator@E@std@@@5@AEAV45@@std@@YAXAEAUNotificationPayload@ClusApi@@$$QEAPEAU_NOTIFY_FILTER_AND_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@22AEAV?$vector@EV?$allocator@E@std@@@0@2@Z; std::_Construct_in_place<ClusApi::NotificationPayload,_NOTIFY_FILTER_AND_TYPE *,std::wstring &,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &>(ClusApi::NotificationPayload &,_NOTIFY_FILTER_AND_TYPE * &&,std::wstring &,std::wstring &,std::wstring &,std::vector<uchar> &,std::wstring &)
0x18002205c  nop
0x18002205d  or      r14d, 1
0x180022061  mov     [rsp+248h+var_1F0], r14d
0x180022066  mov     [rsp+248h+var_1A0], r15
0x18002206e  mov     [rsp+248h+var_198], rsi
0x180022076  mov     rcx, [r13+50h]
0x18002207a  test    rcx, rcx
0x18002207d  jnz     short loc_180022085
0x18002207f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180022085  mov     rax, [rcx]
0x180022088  lea     rdx, [rsp+248h+var_1A0]
0x180022090  mov     rax, [rax+10h]
0x180022094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022099  mov     [rsp+248h+var_1F4], eax
0x18002209d  mov     rcx, [rsp+248h+var_198]; this
0x1800220a5  test    rcx, rcx
0x1800220a8  jz      short loc_1800220B3
0x1800220aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800220af  mov     eax, [rsp+248h+var_1F4]
0x1800220b3  test    eax, eax
0x1800220b5  jns     short loc_1800220EB
0x1800220b7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800220bc  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800220c0  lea     r9, [rsp+248h+var_158]
0x1800220c8  lea     rax, [rsp+248h+var_138]
0x1800220d0  cmp     [rsp+248h+var_148], 0
0x1800220d9  cmovbe  r9, rax
0x1800220dd  lea     r8, [rsp+248h+var_168]
0x1800220e5  call    ??$WriteLine@DU_NOTIFY_FILTER_AND_TYPE@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBU_NOTIFY_FILTER_AND_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,_NOTIFY_FILTER_AND_TYPE,std::wstring>(char const *,_NOTIFY_FILTER_AND_TYPE const &,std::wstring const &)
  ... truncated ...
```
