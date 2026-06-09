# SessionComposingStatusHandler::_OnRemoteContactComposing(ushort const *,_GUID const &,int,ushort const *,int,_FILETIME)

- ea: `0x1800f6534`
- end: `0x1800f6893`
- name: `?_OnRemoteContactComposing@SessionComposingStatusHandler@@IEAAJPEBGAEBU_GUID@@H0HU_FILETIME@@@Z`
- size: `863`
- prototype: `int(SessionComposingStatusHandler *__hidden this, const unsigned __int16 *, const struct _GUID *, int, const unsigned __int16 *, int, struct _FILETIME)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f5930`

## callees

- `0x180004ce4`
- `0x180008ee8`
- `0x18006db44`
- `0x18006f0a8`
- `0x180072ccc`
- `0x1800977ac`
- `0x1800a8658`
- `0x1800f53e0`
- `0x1800f5990`
- `0x1800f59d0`
- `0x1800f6534`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PhoneUtil!GetDialStringFromTelUri` at `0x1800f6651`
- `PhoneUtil!GetDialStringFromTelUri` at `0x1800f6651`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x1800f677a`
- `MessagingDataModel2!Messaging_SmEntryIdToUdmObjectId` at `0x1800f677a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f65c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f65c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f6599`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f6599`
- `UserDataTypeHelperUtil!DupString` at `0x1800f67c5`
- `UserDataTypeHelperUtil!DupString` at `0x1800f67c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6698`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6698`

## pseudocode

```c
__int64 __fastcall SessionComposingStatusHandler::_OnRemoteContactComposing(
        SessionComposingStatusHandler *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        int a4,
        const unsigned __int16 *a5,
        int a6)
{
  RcsServiceManager *v10; // rbx
  int ProviderIdForImsClientId; // eax
  __int64 v12; // r8
  unsigned int v13; // ebx
  unsigned int v14; // r14d
  int DialStringFromTelUri; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  HRESULT Instance; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r8
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // r8
  ServiceDataSession *v30; // rcx
  WINBOOL fPending[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  struct ISmEntryId *v34; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID Context; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  void *v42; // [rsp+88h] [rbp-78h]
  unsigned int v43; // [rsp+90h] [rbp-70h]
  int v44; // [rsp+94h] [rbp-6Ch]
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  int v46; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v47[64]; // [rsp+D0h] [rbp-30h] BYREF

  v33 = -1;
  fPending[0] = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015DCD8, 0, fPending, &Context);
  v10 = (RcsServiceManager *)Context;
  if ( !Context )
  {
    v10 = (RcsServiceManager *)qword_18015DCE0;
    RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
    v38[0] = 0;
    InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v38);
  }
  ProviderIdForImsClientId = RcsServiceManager::GetProviderIdForImsClientId(v10, a3, &v33);
  v13 = ProviderIdForImsClientId;
  if ( ProviderIdForImsClientId >= 0 )
  {
    v36 = 0;
    v14 = v33;
    if ( a4 )
    {
      DialStringFromTelUri = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)this + 14) + 64LL))(
                               *((_QWORD *)this + 14),
                               a2,
                               &v36);
      v13 = DialStringFromTelUri;
      if ( DialStringFromTelUri < 0 )
      {
        v17 = 320;
LABEL_10:
        Log_HREvent_62((unsigned int)DialStringFromTelUri, 1, v16, v17);
        goto LABEL_30;
      }
LABEL_19:
      v34 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, struct ISmEntryId **))(*(_QWORD *)v36 + 88LL))(v36, &v34);
      v13 = v21;
      if ( v21 >= 0 )
      {
        v45 = 0;
        v46 = 0;
        Messaging_SmEntryIdToUdmObjectId(v34, (struct UdmObjectId *)&v45);
        v23 = (_QWORD *)utl::find<utl::_ArrayIt<UdmObjectId>,UdmObjectId>(
                          v38,
                          *((_QWORD *)this + 16),
                          *((_QWORD *)this + 17),
                          &v45);
        if ( v26 == *v23 )
          Log_AssertionEvent_31(v25, v24, 356);
        Block = 0;
        v27 = tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&Block);
        v28 = DupString(v27, a5);
        v13 = v28;
        if ( v28 >= 0 )
        {
          memset_0(&v39, 0, 0x48u);
          v30 = (ServiceDataSession *)*((_QWORD *)this + 8);
          v41 = v46;
          v42 = Block;
          v44 = a6;
          v39 = 46;
          v40 = v45;
          v43 = v14;
          ServiceDataSession::PushNotify(v30, (const struct UdmNotifyStructure *)&v39);
          if ( Block )
            operator delete(Block);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
          v13 = 0;
          goto LABEL_30;
        }
        Log_HREvent_62((unsigned int)v28, 1, v29, 360);
        if ( Block )
          operator delete(Block);
      }
      else
      {
        Log_HREvent_62((unsigned int)v21, 1, v22, 348);
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
LABEL_30:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
      return v13;
    }
    DialStringFromTelUri = GetDialStringFromTelUri(a2, v47, 0x40u);
    v13 = DialStringFromTelUri;
    if ( DialStringFromTelUri < 0 )
    {
      v17 = 330;
      goto LABEL_10;
    }
    *(_QWORD *)fPending = 0;
    Instance = CoCreateInstance(
                 &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
                 0,
                 0x17u,
                 &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
                 (LPVOID *)fPending);
    v13 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64, _QWORD, _DWORD))(**(_QWORD **)fPending
                                                                                                + 24LL))(
                   *(_QWORD *)fPending,
                   v47,
                   1,
                   v14,
                   0);
      v13 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 14) + 48LL))(
                     *((_QWORD *)this + 14),
                     *(_QWORD *)fPending,
                     &v36);
        v13 = Instance;
        if ( Instance >= 0 )
        {
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(fPending);
          goto LABEL_19;
        }
        v20 = 343;
      }
      else
      {
        v20 = 339;
      }
    }
    else
    {
      v20 = 333;
    }
    Log_HREvent_62((unsigned int)Instance, 1, v19, v20);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(fPending);
    goto LABEL_30;
  }
  Log_HREvent_62((unsigned int)ProviderIdForImsClientId, 1, v12, 312);
  return v13;
}

```

## disassembly

```asm
0x1800f6534  mov     [rsp-8+arg_18], rbx
0x1800f6539  push    rbp
0x1800f653a  push    rsi
0x1800f653b  push    rdi
0x1800f653c  push    r12
0x1800f653e  push    r13
0x1800f6540  push    r14
0x1800f6542  push    r15
0x1800f6544  lea     rbp, [rsp-60h]
0x1800f6549  sub     rsp, 160h
0x1800f6550  mov     rax, cs:__security_cookie
0x1800f6557  xor     rax, rsp
0x1800f655a  mov     [rbp+90h+var_40], rax
0x1800f655e  mov     r13, [rbp+90h+arg_20]
0x1800f6565  mov     r12d, r9d
0x1800f6568  mov     rdi, r8
0x1800f656b  mov     [rsp+190h+var_158], 0FFFFFFFFh
0x1800f6573  mov     r15, rdx
0x1800f6576  lea     r9, [rsp+190h+Context]; lpContext
0x1800f657b  mov     rsi, rcx
0x1800f657e  lea     r8, [rsp+190h+fPending]; fPending
0x1800f6583  xor     r14d, r14d
0x1800f6586  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800f658d  xor     edx, edx; dwFlags
0x1800f658f  mov     [rsp+190h+fPending], r14d
0x1800f6594  mov     [rsp+190h+Context], r14
0x1800f6599  call    cs:__imp_InitOnceBeginInitialize
0x1800f659f  mov     rbx, [rsp+190h+Context]
0x1800f65a4  test    rbx, rbx
0x1800f65a7  jnz     short loc_1800F65D9
0x1800f65a9  lea     rbx, qword_18015DCE0
0x1800f65b0  mov     rcx, rbx; this
0x1800f65b3  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800f65b8  mov     r8, rbx; lpContext
0x1800f65bb  mov     [rsp+190h+var_130], r14
0x1800f65c0  xor     edx, edx; dwFlags
0x1800f65c2  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800f65c9  call    cs:__imp_InitOnceComplete
0x1800f65cf  lea     rcx, [rsp+190h+var_130]
0x1800f65d4  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800f65d9  lea     r8, [rsp+190h+var_158]; unsigned int *
0x1800f65de  mov     rdx, rdi; struct _GUID *
0x1800f65e1  mov     rcx, rbx; this
0x1800f65e4  call    ?GetProviderIdForImsClientId@RcsServiceManager@@QEAAJAEBU_GUID@@AEAK@Z; RcsServiceManager::GetProviderIdForImsClientId(_GUID const &,ulong &)
0x1800f65e9  mov     ebx, eax
0x1800f65eb  test    eax, eax
0x1800f65ed  jns     short loc_1800F6606
0x1800f65ef  mov     edx, 1
0x1800f65f4  mov     r9d, 138h
0x1800f65fa  mov     ecx, eax
0x1800f65fc  call    Log_HREvent_62
0x1800f6601  jmp     loc_1800F686A
0x1800f6606  mov     [rsp+190h+var_140], r14
0x1800f660b  mov     edi, 1
0x1800f6610  mov     r14d, [rsp+190h+var_158]
0x1800f6615  test    r12d, r12d
0x1800f6618  jz      short loc_1800F6644
0x1800f661a  mov     rcx, [rsi+70h]
0x1800f661e  lea     r8, [rsp+190h+var_140]
0x1800f6623  mov     rdx, r15
0x1800f6626  mov     rax, [rcx]
0x1800f6629  mov     rax, [rax+40h]
0x1800f662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6632  mov     ebx, eax
0x1800f6634  test    eax, eax
0x1800f6636  jns     loc_1800F6725
0x1800f663c  mov     r9d, 140h
0x1800f6642  jmp     short loc_1800F6663
0x1800f6644  mov     r8d, 40h ; '@'
0x1800f664a  lea     rdx, [rbp+90h+var_C0]
0x1800f664e  mov     rcx, r15
0x1800f6651  call    cs:__imp_?GetDialStringFromTelUri@@YAJPEBGPEAGI@Z; GetDialStringFromTelUri(ushort const *,ushort *,uint)
0x1800f6657  mov     ebx, eax
0x1800f6659  test    eax, eax
0x1800f665b  jns     short loc_1800F6671
0x1800f665d  mov     r9d, 14Ah
0x1800f6663  mov     edx, edi
0x1800f6665  mov     ecx, eax
0x1800f6667  call    Log_HREvent_62
0x1800f666c  jmp     loc_1800F6860
0x1800f6671  xor     edx, edx; pUnkOuter
0x1800f6673  mov     qword ptr [rsp+190h+fPending], 0
0x1800f667c  lea     rax, [rsp+190h+fPending]
0x1800f6681  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x1800f6688  mov     [rsp+190h+ppv], rax; ppv
0x1800f668d  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x1800f6694  lea     r8d, [rdx+17h]; dwClsContext
0x1800f6698  call    cs:__imp_CoCreateInstance
0x1800f669e  mov     ebx, eax
0x1800f66a0  test    eax, eax
0x1800f66a2  jns     short loc_1800F66C2
0x1800f66a4  mov     r9d, 14Dh
0x1800f66aa  mov     edx, edi
0x1800f66ac  mov     ecx, eax
0x1800f66ae  call    Log_HREvent_62
0x1800f66b3  lea     rcx, [rsp+190h+fPending]
0x1800f66b8  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800f66bd  jmp     loc_1800F6860
0x1800f66c2  mov     rcx, qword ptr [rsp+190h+fPending]
0x1800f66c7  lea     rdx, [rbp+90h+var_C0]
0x1800f66cb  mov     r9d, r14d
0x1800f66ce  mov     dword ptr [rsp+190h+ppv], 0
0x1800f66d6  mov     r8d, edi
0x1800f66d9  mov     rax, [rcx]
0x1800f66dc  mov     rax, [rax+18h]
0x1800f66e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f66e5  mov     ebx, eax
0x1800f66e7  test    eax, eax
0x1800f66e9  jns     short loc_1800F66F3
0x1800f66eb  mov     r9d, 153h
0x1800f66f1  jmp     short loc_1800F66AA
0x1800f66f3  mov     rcx, [rsi+70h]
0x1800f66f7  lea     r8, [rsp+190h+var_140]
0x1800f66fc  mov     rdx, qword ptr [rsp+190h+fPending]
0x1800f6701  mov     rax, [rcx]
0x1800f6704  mov     rax, [rax+30h]
0x1800f6708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f670d  mov     ebx, eax
0x1800f670f  test    eax, eax
0x1800f6711  jns     short loc_1800F671B
0x1800f6713  mov     r9d, 157h
0x1800f6719  jmp     short loc_1800F66AA
0x1800f671b  lea     rcx, [rsp+190h+fPending]
0x1800f6720  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800f6725  mov     rcx, [rsp+190h+var_140]
0x1800f672a  lea     rdx, [rsp+190h+var_150]
0x1800f672f  mov     [rsp+190h+var_150], 0
0x1800f6738  mov     rax, [rcx]
0x1800f673b  mov     rax, [rax+58h]
0x1800f673f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6744  mov     ebx, eax
0x1800f6746  test    eax, eax
0x1800f6748  jns     short loc_1800F6768
0x1800f674a  mov     r9d, 15Ch
0x1800f6750  mov     edx, edi
0x1800f6752  mov     ecx, eax
0x1800f6754  call    Log_HREvent_62
0x1800f6759  lea     rcx, [rsp+190h+var_150]
0x1800f675e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800f6763  jmp     loc_1800F6860
0x1800f6768  mov     rcx, [rsp+190h+var_150]
0x1800f676d  lea     rdx, [rbp+90h+var_D0]
0x1800f6771  xor     eax, eax
0x1800f6773  mov     [rbp+90h+var_D0], rax
0x1800f6777  mov     [rbp+90h+var_C8], eax
0x1800f677a  call    cs:__imp_?Messaging_SmEntryIdToUdmObjectId@@YAJPEAUISmEntryId@@PEAUUdmObjectId@@@Z; Messaging_SmEntryIdToUdmObjectId(ISmEntryId *,UdmObjectId *)
0x1800f6780  mov     r8, [rsi+88h]
0x1800f6787  lea     r9, [rbp+90h+var_D0]
0x1800f678b  mov     rdx, [rsi+80h]
0x1800f6792  lea     rcx, [rsp+190h+var_130]
0x1800f6797  call    ??$find@V?$_ArrayIt@UUdmObjectId@@@utl@@UUdmObjectId@@@utl@@YA?AV?$_ArrayIt@UUdmObjectId@@@0@V10@0AEBUUdmObjectId@@@Z; utl::find<utl::_ArrayIt<UdmObjectId>,UdmObjectId>(utl::_ArrayIt<UdmObjectId>,utl::_ArrayIt<UdmObjectId>,UdmObjectId const &)
0x1800f679c  cmp     r8, [rax]
0x1800f679f  jnz     short loc_1800F67AC
0x1800f67a1  mov     r8d, 164h
0x1800f67a7  call    Log_AssertionEvent_31
0x1800f67ac  lea     rcx, [rsp+190h+Block]
0x1800f67b1  mov     [rsp+190h+Block], 0
0x1800f67ba  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x1800f67bf  mov     rcx, rax
0x1800f67c2  mov     rdx, r13
0x1800f67c5  call    cs:__imp_DupString
0x1800f67cb  mov     ebx, eax
0x1800f67cd  test    eax, eax
0x1800f67cf  jns     short loc_1800F67F8
0x1800f67d1  mov     r9d, 168h
0x1800f67d7  mov     edx, edi
0x1800f67d9  mov     ecx, eax
0x1800f67db  call    Log_HREvent_62
0x1800f67e0  mov     rcx, [rsp+190h+Block]; Block
0x1800f67e5  test    rcx, rcx
0x1800f67e8  jz      loc_1800F6759
0x1800f67ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f67f3  jmp     loc_1800F6759
0x1800f67f8  xor     edx, edx; Val
0x1800f67fa  lea     rcx, [rsp+190h+var_120]; void *
0x1800f67ff  lea     r8d, [rdx+48h]; Size
0x1800f6803  call    memset_0
0x1800f6808  mov     eax, [rbp+90h+var_C8]
0x1800f680b  lea     rdx, [rsp+190h+var_120]; struct UdmNotifyStructure *
0x1800f6810  movsd   xmm0, [rbp+90h+var_D0]
0x1800f6815  mov     rcx, [rsi+40h]; this
0x1800f6819  mov     [rbp+90h+var_110], eax
0x1800f681c  mov     rax, [rsp+190h+Block]
0x1800f6821  mov     [rbp+90h+var_108], rax
0x1800f6825  mov     eax, [rbp+90h+arg_28]
0x1800f682b  mov     [rbp+90h+var_FC], eax
0x1800f682e  mov     [rsp+190h+var_120], 2Eh ; '.'
0x1800f6836  movsd   [rsp+190h+var_118], xmm0
0x1800f683c  mov     [rbp+90h+var_100], r14d
0x1800f6840  call    ?PushNotify@ServiceDataSession@@QEAAXAEBUUdmNotifyStructure@@@Z; ServiceDataSession::PushNotify(UdmNotifyStructure const &)
0x1800f6845  mov     rcx, [rsp+190h+Block]; Block
0x1800f684a  test    rcx, rcx
0x1800f684d  jz      short loc_1800F6854
0x1800f684f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f6854  lea     rcx, [rsp+190h+var_150]
0x1800f6859  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800f685e  xor     ebx, ebx
0x1800f6860  lea     rcx, [rsp+190h+var_140]
0x1800f6865  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800f686a  mov     eax, ebx
0x1800f686c  mov     rcx, [rbp+90h+var_40]
0x1800f6870  xor     rcx, rsp; StackCookie
0x1800f6873  call    __security_check_cookie
0x1800f6878  mov     rbx, [rsp+190h+arg_18]
0x1800f6880  add     rsp, 160h
0x1800f6887  pop     r15
0x1800f6889  pop     r14
0x1800f688b  pop     r13
0x1800f688d  pop     r12
0x1800f688f  pop     rdi
0x1800f6890  pop     rsi
0x1800f6891  pop     rbp
0x1800f6892  retn
```
