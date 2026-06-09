# CRecoMaster::~CRecoMaster(void)

- ea: `0x18004693c`
- end: `0x180046b06`
- name: `??1CRecoMaster@@QEAA@XZ`
- size: `458`
- prototype: `void __fastcall(CRecoMaster *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180082e24`
- `0x180083f64`

## callees

- `0x18000a590`
- `0x18000bea0`
- `0x18000bec4`
- `0x180026c10`
- `0x18002895c`
- `0x18004693c`
- `0x180046b0c`
- `0x180046b34`
- `0x180046b64`
- `0x180046bd8`
- `0x180046c4c`
- `0x180046c7c`
- `0x180046cf0`
- `0x180046d20`
- `0x180046e0c`
- `0x180046e44`
- `0x180046e6c`
- `0x180093084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046964`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800469af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046ae4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046964`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800469af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004697e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004697e`

## pseudocode

```c
void __fastcall CRecoMaster::~CRecoMaster(CRecoMaster *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  struct _TP_TIMER *v6; // rcx

  FileCaptureBase::~FileCaptureBase((CRecoMaster *)((char *)this + 1896));
  FileCaptureBase::~FileCaptureBase((CRecoMaster *)((char *)this + 1832));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1768));
  CoTaskMemFree(*((LPVOID *)this + 212));
  CoTaskMemFree(*((LPVOID *)this + 208));
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1640);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1632);
  CPhoneCallHandler::~CPhoneCallHandler((CRecoMaster *)((char *)this + 1608));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 39);
  RecognizerServerTelemetry::RecoMasterLifetime::~RecoMasterLifetime((CRecoMaster *)((char *)this + 1064));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 132);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1040);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1008);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 115);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 112);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  SysVadAudioControl::~SysVadAudioControl((CRecoMaster *)((char *)this + 872));
  SPPIPEINFO::~SPPIPEINFO((CRecoMaster *)((char *)this + 840));
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 808);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 100);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 784);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 776);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 768);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 760);
  CSpBasicQueue<CSRTask,1,0>::~CSpBasicQueue<CSRTask,1,0>((char *)this + 736);
  CSpProducerConsumerQueue<CSRTask,1>::~CSpProducerConsumerQueue<CSRTask,1>((char *)this + 656);
  CSpProducerConsumerIOCompletionQueue<CSRTask,1>::~CSpProducerConsumerIOCompletionQueue<CSRTask,1>((char *)this + 560);
  CSpProducerConsumerIOCompletionQueue<CSREvent,1>::~CSpProducerConsumerIOCompletionQueue<CSREvent,1>((char *)this + 464);
  CSpHandleTable<CRecoInstCategory,void *,1>::~CSpHandleTable<CRecoInstCategory,void *,1>((char *)this + 424);
  CSpHandleTable<CRecoInstGrammar,SPGRAMMARHANDLE__ *,1>::~CSpHandleTable<CRecoInstGrammar,SPGRAMMARHANDLE__ *,1>((char *)this + 400);
  CSpHandleTable<CRecoInstCtxt,SPRECOCONTEXTHANDLE__ *,1>::~CSpHandleTable<CRecoInstCtxt,SPRECOCONTEXTHANDLE__ *,1>((char *)this + 376);
  SysVadAudioControl::~SysVadAudioControl((CRecoMaster *)((char *)this + 352));
  SysVadAudioControl::~SysVadAudioControl((CRecoMaster *)((char *)this + 336));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 14);
  if ( v6 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v6);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 48);
}

```

## disassembly

```asm
0x18004693c  push    rbx
0x18004693e  sub     rsp, 20h
0x180046942  mov     rbx, rcx
0x180046945  add     rcx, 768h; this
0x18004694c  call    ??1FileCaptureBase@@UEAA@XZ; FileCaptureBase::~FileCaptureBase(void)
0x180046951  lea     rcx, [rbx+728h]; this
0x180046958  call    ??1FileCaptureBase@@UEAA@XZ; FileCaptureBase::~FileCaptureBase(void)
0x18004695d  lea     rcx, [rbx+6E8h]; lpCriticalSection
0x180046964  call    cs:__imp_DeleteCriticalSection
0x18004696a  mov     rcx, [rbx+6A0h]; pv
0x180046971  call    cs:__imp_CoTaskMemFree
0x180046977  mov     rcx, [rbx+680h]; pv
0x18004697e  call    cs:__imp_CoTaskMemFree
0x180046984  lea     rcx, [rbx+668h]
0x18004698b  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046990  lea     rcx, [rbx+660h]
0x180046997  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x18004699c  lea     rcx, [rbx+648h]; this
0x1800469a3  call    ??1CPhoneCallHandler@@UEAA@XZ; CPhoneCallHandler::~CPhoneCallHandler(void)
0x1800469a8  lea     rcx, [rbx+618h]; lpCriticalSection
0x1800469af  call    cs:__imp_DeleteCriticalSection
0x1800469b5  lea     rcx, [rbx+428h]; this
0x1800469bc  call    ??1RecoMasterLifetime@RecognizerServerTelemetry@@UEAA@XZ; RecognizerServerTelemetry::RecoMasterLifetime::~RecoMasterLifetime(void)
0x1800469c1  mov     rcx, [rbx+420h]; this
0x1800469c8  test    rcx, rcx
0x1800469cb  jz      short loc_1800469D2
0x1800469cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800469d2  lea     rcx, [rbx+410h]
0x1800469d9  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800469de  lea     rcx, [rbx+3F0h]
0x1800469e5  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800469ea  mov     rcx, [rbx+398h]; this
0x1800469f1  test    rcx, rcx
0x1800469f4  jz      short loc_1800469FB
0x1800469f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800469fb  mov     rcx, [rbx+380h]; this
0x180046a02  test    rcx, rcx
0x180046a05  jz      short loc_180046A0C
0x180046a07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046a0c  lea     rcx, [rbx+368h]; this
0x180046a13  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x180046a18  lea     rcx, [rbx+348h]; this
0x180046a1f  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180046a24  lea     rcx, [rbx+328h]
0x180046a2b  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046a30  mov     rcx, [rbx+320h]; this
0x180046a37  test    rcx, rcx
0x180046a3a  jz      short loc_180046A41
0x180046a3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046a41  lea     rcx, [rbx+310h]
0x180046a48  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046a4d  lea     rcx, [rbx+308h]
0x180046a54  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046a59  lea     rcx, [rbx+300h]
0x180046a60  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046a65  lea     rcx, [rbx+2F8h]
0x180046a6c  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180046a71  lea     rcx, [rbx+2E0h]
0x180046a78  call    ??1?$CSpBasicQueue@VCSRTask@@$00$0A@@@QEAA@XZ; CSpBasicQueue<CSRTask,1,0>::~CSpBasicQueue<CSRTask,1,0>(void)
0x180046a7d  lea     rcx, [rbx+290h]
0x180046a84  call    ??1?$CSpProducerConsumerQueue@VCSRTask@@$00@@QEAA@XZ; CSpProducerConsumerQueue<CSRTask,1>::~CSpProducerConsumerQueue<CSRTask,1>(void)
0x180046a89  lea     rcx, [rbx+230h]
0x180046a90  call    ??1?$CSpProducerConsumerIOCompletionQueue@VCSRTask@@$00@@QEAA@XZ; CSpProducerConsumerIOCompletionQueue<CSRTask,1>::~CSpProducerConsumerIOCompletionQueue<CSRTask,1>(void)
0x180046a95  lea     rcx, [rbx+1D0h]
0x180046a9c  call    ??1?$CSpProducerConsumerIOCompletionQueue@VCSREvent@@$00@@QEAA@XZ; CSpProducerConsumerIOCompletionQueue<CSREvent,1>::~CSpProducerConsumerIOCompletionQueue<CSREvent,1>(void)
0x180046aa1  lea     rcx, [rbx+1A8h]
0x180046aa8  call    ??1?$CSpHandleTable@VCRecoInstCategory@@PEAX$00@@QEAA@XZ; CSpHandleTable<CRecoInstCategory,void *,1>::~CSpHandleTable<CRecoInstCategory,void *,1>(void)
0x180046aad  lea     rcx, [rbx+190h]
0x180046ab4  call    ??1?$CSpHandleTable@VCRecoInstGrammar@@PEAUSPGRAMMARHANDLE__@@$00@@QEAA@XZ; CSpHandleTable<CRecoInstGrammar,SPGRAMMARHANDLE__ *,1>::~CSpHandleTable<CRecoInstGrammar,SPGRAMMARHANDLE__ *,1>(void)
0x180046ab9  lea     rcx, [rbx+178h]
0x180046ac0  call    ??1?$CSpHandleTable@VCRecoInstCtxt@@PEAUSPRECOCONTEXTHANDLE__@@$00@@QEAA@XZ; CSpHandleTable<CRecoInstCtxt,SPRECOCONTEXTHANDLE__ *,1>::~CSpHandleTable<CRecoInstCtxt,SPRECOCONTEXTHANDLE__ *,1>(void)
0x180046ac5  lea     rcx, [rbx+160h]; this
0x180046acc  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x180046ad1  lea     rcx, [rbx+150h]; this
0x180046ad8  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x180046add  lea     rcx, [rbx+80h]; lpCriticalSection
0x180046ae4  call    cs:__imp_DeleteCriticalSection
0x180046aea  mov     rcx, [rbx+70h]; pti
0x180046aee  test    rcx, rcx
0x180046af1  jz      short loc_180046AF8
0x180046af3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180046af8  lea     rcx, [rbx+30h]
0x180046afc  add     rsp, 20h
0x180046b00  pop     rbx
0x180046b01  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
