# CDlpTransportBits::TransferFileWorker(IDlpFile *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x180079890`
- end: `0x18007b5f9`
- name: `?TransferFileWorker@CDlpTransportBits@@AEAAJPEAVIDlpFile@@PEAT_ULARGE_INTEGER@@1@Z`
- size: `7529`
- prototype: `__int64 __fastcall(CDlpTransportBits *__hidden this, struct IDlpFile *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180077c64`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18004d020`
- `0x180053b74`
- `0x18005a960`
- `0x180061dec`
- `0x1800668b0`
- `0x180079890`
- `0x18007da50`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18007a00b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18007a00b`
- `RPCRT4!UuidCreate` at `0x180079de2`
- `RPCRT4!UuidCreate` at `0x180079de2`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b4c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b4d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b4c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b4d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b4ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a527`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a527`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079a29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a4cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a537`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a5cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b2c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b335`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079a29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a4cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a537`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a5cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b2c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b335`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a50e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a5f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b2eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b46e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b5cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a50e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a5f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b2eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b46e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b5cd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007a3aa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007a3aa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180079b6c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180079b6c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180079d63`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180079f91`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007a716`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180079d63`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180079f91`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007a716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b50f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007b5b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007b5b8`

## string_xrefs

- `0x18007ad45`: `BitsTransferFile: Completing BITS job.`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CDlpTransportBits::TransferFileWorker(
        CDlpTransportBits *this,
        struct IDlpFile *a2,
        union _ULARGE_INTEGER *a3,
        union _ULARGE_INTEGER *a4)
{
  int v8; // ebx
  CBitsNotifyInterface *v9; // r12
  char *v10; // rdi
  __int64 v11; // rax
  int BitsCopyManager; // esi
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // esi
  __int64 v17; // rax
  __int64 v18; // rcx
  HRESULT v19; // eax
  RPC_STATUS v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  CBitsNotifyInterface *v24; // r15
  signed int LastError; // eax
  DWORD v26; // r14d
  int v27; // esi
  int v28; // eax
  __int128 v29; // kr00_16
  __int64 (__fastcall *v30)(char *); // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  struct IDlpFile *v37; // r14
  int v38; // eax
  IUnknown *v39; // rcx
  int v40; // r15d
  unsigned int v41; // eax
  struct IDlpFile *v42; // r15
  __int64 v43; // rax
  __int64 v44; // rax
  void *v45; // rdi
  HANDLE ProcessHeap; // rax
  DWORD dwAuthnLevel[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwImpLevel[2]; // [rsp+28h] [rbp-D8h]
  CBitsNotifyInterface *v50; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-A8h] BYREF
  struct IBackgroundCopyManager *v54; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+68h] [rbp-98h] BYREF
  int v56; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v57[4]; // [rsp+74h] [rbp-8Ch] BYREF
  int v58; // [rsp+78h] [rbp-88h]
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  BSTR v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  struct IDlpFile *v62; // [rsp+98h] [rbp-68h]
  LPVOID pv[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v64; // [rsp+B8h] [rbp-48h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h] BYREF
  int v67; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v68[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v69; // [rsp+F0h] [rbp-10h]
  __int64 v70; // [rsp+F8h] [rbp-8h]
  __int64 v71; // [rsp+100h] [rbp+0h]
  __int128 v72; // [rsp+108h] [rbp+8h] BYREF
  UUID Uuid; // [rsp+118h] [rbp+18h] BYREF
  __int128 v74; // [rsp+128h] [rbp+28h] BYREF
  __int64 v75; // [rsp+138h] [rbp+38h]
  __int128 v76; // [rsp+140h] [rbp+40h] BYREF

  v62 = a2;
  v69 = 0;
  v68[1] = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v68[2] = (char *)this + 336;
  v8 = 0;
  v65 = 0;
  v54 = 0;
  v51 = 0;
  v55 = 0;
  pProxy = 0;
  v70 = 0;
  v9 = 0;
  v50 = 0;
  v61 = 0;
  v71 = 0;
  pv[0] = 0;
  v76 = 0;
  Uuid = 0;
  v68[0] = 0;
  v60 = 0;
  bstrString = 0;
  v72 = 0;
  v74 = 0;
  v75 = 0;
  v52 = 0;
  v56 = 0;
  v66 = 0;
  v67 = 0;
  v10 = (char *)this + 168;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
  {
    v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    CDlpLogT<CEmptyType>::DlpLogFormat(v11, 2u, (__int64)L"BitsTransport: Entering TransferFile Method");
  }
  v58 = 0;
  if ( !a2 )
  {
    BitsCopyManager = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
      goto LABEL_300;
    v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    v14 = 0;
    if ( !v13 )
      goto LABEL_9;
    dwImpLevel[0] = -2147024809;
    dwAuthnLevel[0] = 2419;
LABEL_7:
    v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v13,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportBits::TransferFileWorker",
            *(_QWORD *)dwAuthnLevel,
            *(_QWORD *)dwImpLevel);
    v14 = (unsigned int)v15;
    if ( v15 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
LABEL_9:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
    goto LABEL_300;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  LODWORD(v69) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v64 = 1;
  v16 = *((_DWORD *)this + 54);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v64 = 0;
  if ( v16 == 1 )
  {
    v58 = 1;
    BitsCopyManager = (*(__int64 (__fastcall **)(struct IDlpFile *, BSTR *))(*(_QWORD *)v62 + 48LL))(v62, &v60);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2433;
      goto LABEL_296;
    }
    BitsCopyManager = (*(__int64 (__fastcall **)(struct IDlpFile *, BSTR *))(*(_QWORD *)v62 + 56LL))(v62, &bstrString);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2434;
      goto LABEL_296;
    }
    BitsCopyManager = 0;
    v19 = CoInitializeEx(0, 0);
    if ( v19 < 0 )
    {
      if ( v19 != -2147417850 )
      {
        BitsCopyManager = v19;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      }
    }
    else
    {
      v8 = 1;
      v65 = 1;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2438;
      goto LABEL_296;
    }
    BitsCopyManager = CDlpTransportBits::GetBitsCopyManager(this, &v54);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2442;
      goto LABEL_296;
    }
    BitsCopyManager = ((__int64 (__fastcall *)(struct IBackgroundCopyManager *, const WCHAR *, _QWORD, __int128 *, IUnknown **))v54->lpVtbl->CreateJob)(
                        v54,
                        L"Windows Dlp Manager",
                        0,
                        &v76,
                        &v51);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2446;
      goto LABEL_296;
    }
    if ( WINDLP_TRANSPORT_DO == *(_OWORD *)((char *)this + 616) )
    {
      BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v51->lpVtbl->QueryInterface)(
                          v51,
                          &GUID_ee2584cf_a69c_4848_b633_2649962b3ef7,
                          &pProxy);
      if ( BitsCopyManager < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2450;
        goto LABEL_296;
      }
      BitsCopyManager = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
      if ( BitsCopyManager < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2458;
        goto LABEL_296;
      }
      if ( a3 )
        *(union _ULARGE_INTEGER *)&v72 = *a3;
      else
        *(_QWORD *)&v72 = 0;
      if ( a4 )
        *((union _ULARGE_INTEGER *)&v72 + 1) = *a4;
      else
        *((_QWORD *)&v72 + 1) = -1;
      v20 = UuidCreate(&Uuid);
      if ( v20 )
      {
        v22 = I_RpcMapWin32Status(v20);
        BitsCopyManager = v22;
        if ( v22 > 0 )
          BitsCopyManager = (unsigned __int16)v22 | 0x80070000;
        if ( BitsCopyManager >= 0 )
          BitsCopyManager = -2147467259;
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2464;
        goto LABEL_296;
      }
      BitsCopyManager = CDlpHelpersT<CEmptyType>::GuidToSString(&Uuid, 1, v68);
      if ( BitsCopyManager < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2465;
        goto LABEL_296;
      }
      v21 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, BSTR, BSTR, int, __int128 *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
              pProxy,
              v68[0],
              v60,
              bstrString,
              1,
              &v72,
              0);
      if ( v21 == -2147024809 )
      {
        BitsCopyManager = -2147024735;
LABEL_62:
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2473;
        goto LABEL_296;
      }
      if ( v21 < 0 )
      {
        BitsCopyManager = v21;
        goto LABEL_62;
      }
      if ( v51 )
      {
        ((void (__fastcall *)(IUnknown *))v51->lpVtbl->Release)(v51);
        v51 = 0;
      }
      BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
                          pProxy,
                          &GUID_37668d37_507e_4160_9316_26306d150b12,
                          &v51);
      if ( BitsCopyManager < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2476;
        goto LABEL_296;
      }
      BitsCopyManager = CoSetProxyBlanket(v51, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
      if ( BitsCopyManager < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2484;
        goto LABEL_296;
      }
      if ( pProxy )
      {
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        pProxy = 0;
      }
LABEL_103:
      if ( WINDLP_TRANSPORT_DO == *(_OWORD *)((char *)this + 616)
        || (BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, _QWORD))v51->lpVtbl[9].Release)(v51, 0),
            BitsCopyManager >= 0) )
      {
        BitsCopyManager = CBitsNotifyInterface::CreateInstance(this, &v50);
        if ( BitsCopyManager >= 0 )
        {
          v24 = v50;
          BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, CBitsNotifyInterface *))v51->lpVtbl[8].AddRef)(
                              v51,
                              v50);
          if ( BitsCopyManager >= 0 )
          {
            BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, __int64))v51->lpVtbl[7].Release)(v51, 11);
            if ( BitsCopyManager >= 0 )
            {
              BitsCopyManager = CDlpTransportBits::UpdateState(this, 2, 0);
              if ( BitsCopyManager >= 0 )
              {
                if ( !ResetEvent(*((HANDLE *)this + 73)) )
                {
                  LastError = GetLastError();
                  BitsCopyManager = LastError;
                  if ( LastError )
                  {
                    if ( LastError > 0 )
                      BitsCopyManager = (unsigned __int16)LastError | 0x80070000;
                  }
                  else
                  {
                    BitsCopyManager = -2147467259;
                  }
                  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                    goto LABEL_299;
                  v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                  v18 = 0;
                  if ( BitsCopyManager >= 0 || !v17 )
                    goto LABEL_298;
                  dwImpLevel[0] = BitsCopyManager;
                  dwAuthnLevel[0] = 2521;
                  goto LABEL_296;
                }
                BitsCopyManager = CDlpTransportBits::InternalResumeJob(this, (struct IBackgroundCopyJob *)v51);
                if ( BitsCopyManager >= 0 )
                {
                  BitsCopyManager = CDlpTransportBits::UpdateState(this, 3, 0);
                  if ( BitsCopyManager >= 0 )
                  {
                    EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
                    v64 = 1;
                    *((_DWORD *)this + 24) = 0;
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                    if ( v64 )
                    {
                      LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
                      v64 = 0;
                    }
                    while ( 1 )
                    {
                      if ( (_DWORD)v69 )
                      {
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
                        LODWORD(v69) = 0;
                      }
                      v26 = WaitForSingleObject(*((HANDLE *)this + 73), 0x3A98u);
                      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
                      LODWORD(v69) = 1;
                      if ( v26 )
                      {
                        if ( v26 != 258 )
                        {
                          BitsCopyManager = -2147467259;
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = -2147467259;
                            dwAuthnLevel[0] = 2552;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                      }
                      else
                      {
                        BitsCopyManager = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 2) + 8LL))(
                                            (char *)this + 16,
                                            &v56);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2559;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        BitsCopyManager = v56;
                        if ( v56 < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2560;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                      }
                      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
                      v64 = 1;
                      v27 = *((_DWORD *)this + 54);
                      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                      if ( v64 )
                      {
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
                        v64 = 0;
                      }
                      if ( v27 == -1073741824 )
                      {
                        BitsCopyManager = -2147023661;
                        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          goto LABEL_299;
                        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v18 = 0;
                        if ( v17 )
                        {
                          dwImpLevel[0] = -2147023661;
                          dwAuthnLevel[0] = 2566;
                          goto LABEL_296;
                        }
                        goto LABEL_298;
                      }
                      v28 = ((__int64 (__fastcall *)(IUnknown *, int *))v51->lpVtbl[4].Release)(v51, &v52);
                      BitsCopyManager = v28;
                      if ( v28 == -2147023174 || v28 == -2147417848 )
                      {
                        if ( v24 )
                        {
                          (*(void (__fastcall **)(CBitsNotifyInterface *))(*(_QWORD *)v24 + 16LL))(v24);
                          v50 = 0;
                        }
                        if ( v51 )
                        {
                          ((void (__fastcall *)(IUnknown *))v51->lpVtbl->Release)(v51);
                          v51 = 0;
                        }
                        if ( v54 )
                        {
                          ((void (__fastcall *)(struct IBackgroundCopyManager *))v54->lpVtbl->Release)(v54);
                          v54 = 0;
                        }
                        BitsCopyManager = CDlpTransportBits::GetBitsCopyManager(this, &v54);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2581;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        BitsCopyManager = ((__int64 (__fastcall *)(struct IBackgroundCopyManager *, char *, IUnknown **))v54->lpVtbl->GetJobA)(
                                            v54,
                                            (char *)this + 636,
                                            &v51);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2582;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        v29 = WINDLP_TRANSPORT_DO;
                        if ( (_QWORD)WINDLP_TRANSPORT_DO != *((_QWORD *)this + 77) )
                          goto LABEL_354;
                        if ( *((_QWORD *)&WINDLP_TRANSPORT_DO + 1) == *((_QWORD *)this + 78) )
                        {
                          BitsCopyManager = CoSetProxyBlanket(
                                              v51,
                                              0xFFFFFFFF,
                                              0xFFFFFFFF,
                                              (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                                              5u,
                                              3u,
                                              0,
                                              0);
                          if ( BitsCopyManager < 0 )
                          {
                            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = BitsCopyManager;
                              dwAuthnLevel[0] = 2593;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                          v29 = WINDLP_TRANSPORT_DO;
                        }
                        if ( v29 != *(_OWORD *)((char *)this + 616) )
                        {
LABEL_354:
                          BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, _QWORD))v51->lpVtbl[9].Release)(v51, 0);
                          if ( BitsCopyManager < 0 )
                          {
                            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = BitsCopyManager;
                              dwAuthnLevel[0] = 2600;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                        }
                        BitsCopyManager = CBitsNotifyInterface::CreateInstance(this, &v50);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2603;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        v24 = v50;
                        BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, CBitsNotifyInterface *))v51->lpVtbl[8].AddRef)(
                                            v51,
                                            v50);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2607;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, __int64))v51->lpVtbl[7].Release)(v51, 11);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2610;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                        BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, int *))v51->lpVtbl[4].Release)(v51, &v52);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2614;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                      }
                      if ( BitsCopyManager < 0 )
                      {
                        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          goto LABEL_299;
                        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v18 = 0;
                        if ( v17 )
                        {
                          dwImpLevel[0] = BitsCopyManager;
                          dwAuthnLevel[0] = 2616;
                          goto LABEL_296;
                        }
                        goto LABEL_298;
                      }
                      if ( v52 == 6 )
                        break;
                      if ( v26 != 258 )
                      {
                        if ( *((_DWORD *)this + 165) || *((_DWORD *)this + 167) )
                        {
                          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          {
                            v32 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            CDlpLogT<CEmptyType>::DlpLogFormat(
                              v32,
                              2u,
                              (__int64)L"BitsTransferFile: Suspending BITS job at user request.");
                          }
                          BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *))v51->lpVtbl[2].QueryInterface)(v51);
                          if ( BitsCopyManager < 0 )
                          {
                            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = BitsCopyManager;
                              dwAuthnLevel[0] = 2642;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                          if ( *((_DWORD *)this + 165) )
                          {
                            BitsCopyManager = CDlpTransportBits::UpdateState(this, 5, v57);
                            if ( BitsCopyManager < 0 )
                            {
                              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                                goto LABEL_299;
                              v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                              v18 = 0;
                              if ( v17 )
                              {
                                dwImpLevel[0] = BitsCopyManager;
                                dwAuthnLevel[0] = 2648;
                                goto LABEL_296;
                              }
                              goto LABEL_298;
                            }
                          }
                          else
                          {
                            BitsCopyManager = CDlpTransportBits::UpdateState(this, 4, v57);
                            if ( BitsCopyManager < 0 )
                            {
                              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                                goto LABEL_299;
                              v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                              v18 = 0;
                              if ( v17 )
                              {
                                dwImpLevel[0] = BitsCopyManager;
                                dwAuthnLevel[0] = 2652;
                                goto LABEL_296;
                              }
                              goto LABEL_298;
                            }
                          }
                          if ( *((_DWORD *)this + 167) )
                          {
                            if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            {
                              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                              CDlpLogT<CEmptyType>::DlpLogFormat(
                                v33,
                                2u,
                                (__int64)L"BitsTransferFile: Suspending execution at user request.");
                            }
                            break;
                          }
                        }
                        else
                        {
                          v30 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL);
                          if ( !*((_DWORD *)this + 166) )
                          {
                            BitsCopyManager = -2147418113;
                            if ( !v30(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = -2147418113;
                              dwAuthnLevel[0] = 2684;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                          if ( v30(v10) )
                          {
                            v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            CDlpLogT<CEmptyType>::DlpLogFormat(
                              v31,
                              2u,
                              (__int64)L"BitsTransferFile: Resuming BITS job at user request.");
                          }
                          BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *))v51->lpVtbl[2].AddRef)(v51);
                          if ( BitsCopyManager < 0 )
                          {
                            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = BitsCopyManager;
                              dwAuthnLevel[0] = 2670;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                          *((_DWORD *)this + 166) = 0;
                          BitsCopyManager = CDlpTransportBits::UpdateState(this, 3, v57);
                          if ( BitsCopyManager < 0 )
                          {
                            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                              goto LABEL_299;
                            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                            v18 = 0;
                            if ( v17 )
                            {
                              dwImpLevel[0] = BitsCopyManager;
                              dwAuthnLevel[0] = 2678;
                              goto LABEL_296;
                            }
                            goto LABEL_298;
                          }
                        }
                      }
                    }
                    BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, __int128 *))v51->lpVtbl[4].QueryInterface)(
                                        v51,
                                        &v74);
                    if ( BitsCopyManager < 0 )
                    {
                      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                        goto LABEL_299;
                      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                      v18 = 0;
                      if ( v17 )
                      {
                        dwImpLevel[0] = BitsCopyManager;
                        dwAuthnLevel[0] = 2690;
                        goto LABEL_296;
                      }
                      goto LABEL_298;
                    }
                    BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, int *))v51->lpVtbl[4].Release)(v51, &v52);
                    if ( BitsCopyManager < 0 )
                    {
                      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                        goto LABEL_299;
                      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                      v18 = 0;
                      if ( v17 )
                      {
                        dwImpLevel[0] = BitsCopyManager;
                        dwAuthnLevel[0] = 2694;
                        goto LABEL_296;
                      }
                      goto LABEL_298;
                    }
                    if ( v52 == 6 )
                    {
                      v9 = v50;
                      if ( v50 )
                      {
                        BitsCopyManager = CBitsNotifyInterface::Disable(v50);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_300;
                          v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v14 = 0;
                          if ( v13 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2706;
                            goto LABEL_7;
                          }
                          goto LABEL_9;
                        }
                      }
                      BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, __int64))v51->lpVtbl[7].Release)(v51, 4);
                      if ( BitsCopyManager < 0 )
                      {
                        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          goto LABEL_300;
                        v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v14 = 0;
                        if ( v13 )
                        {
                          dwImpLevel[0] = BitsCopyManager;
                          dwAuthnLevel[0] = 2708;
                          goto LABEL_7;
                        }
                        goto LABEL_9;
                      }
                      BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, _QWORD))v51->lpVtbl[8].AddRef)(v51, 0);
                      v34 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                      if ( BitsCopyManager < 0 )
                      {
                        if ( !v34 )
                          goto LABEL_300;
                        v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v14 = 0;
                        if ( v13 )
                        {
                          dwImpLevel[0] = BitsCopyManager;
                          dwAuthnLevel[0] = 2709;
                          goto LABEL_7;
                        }
                        goto LABEL_9;
                      }
                      if ( v34 )
                      {
                        v35 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        CDlpLogT<CEmptyType>::DlpLogFormat(v35, 2u, (__int64)L"BitsTransferFile: Completing BITS job.");
                      }
                      BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *))v51->lpVtbl[3].QueryInterface)(v51);
                      if ( BitsCopyManager < 0 )
                      {
                        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          goto LABEL_300;
                        v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v14 = 0;
                        if ( v13 )
                        {
                          dwImpLevel[0] = BitsCopyManager;
                          dwAuthnLevel[0] = 2712;
                          goto LABEL_7;
                        }
                        goto LABEL_9;
                      }
                      BitsCopyManager = CDlpTransportBits::UpdateState(this, 6, 0);
                      if ( BitsCopyManager < 0 )
                      {
                        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                          goto LABEL_300;
                        v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                        v14 = 0;
                        if ( v13 )
                        {
                          dwImpLevel[0] = BitsCopyManager;
                          dwAuthnLevel[0] = 2713;
                          goto LABEL_7;
                        }
                        goto LABEL_9;
                      }
                    }
                    else
                    {
                      if ( v52 == 3 )
                      {
                        if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                        {
                          v36 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          CDlpLogT<CEmptyType>::DlpLogFormat(
                            v36,
                            2u,
                            (__int64)L"BitsTransferFile: Leaving BITS job suspended.");
                        }
                        BitsCopyManager = CDlpTransportBits::UpdateState(this, 4, 0);
                        if ( BitsCopyManager < 0 )
                        {
                          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                            goto LABEL_299;
                          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                          v18 = 0;
                          if ( v17 )
                          {
                            dwImpLevel[0] = BitsCopyManager;
                            dwAuthnLevel[0] = 2718;
                            goto LABEL_296;
                          }
                          goto LABEL_298;
                        }
                      }
                      v9 = v50;
                    }
                    v37 = v62;
                    BitsCopyManager = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*((_QWORD *)v62 + 2) + 8LL))(
                                        (__int64)v62 + 16,
                                        *((_QWORD *)&v74 + 1),
                                        *((_QWORD *)&v74 + 1));
                    if ( BitsCopyManager < 0 )
                    {
                      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                        goto LABEL_300;
                      v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                      v14 = 0;
                      if ( v13 )
                      {
                        dwImpLevel[0] = BitsCopyManager;
                        dwAuthnLevel[0] = 2722;
                        goto LABEL_7;
                      }
                      goto LABEL_9;
                    }
                    BitsCopyManager = (**((__int64 (__fastcall ***)(__int64, _QWORD, _QWORD))v37 + 2))(
                                        (__int64)v37 + 16,
                                        0,
                                        0);
                    if ( BitsCopyManager >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                      goto LABEL_300;
                    v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                    v14 = 0;
                    if ( !v13 )
                      goto LABEL_9;
                    dwImpLevel[0] = BitsCopyManager;
                    dwAuthnLevel[0] = 2723;
                    goto LABEL_7;
                  }
                  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                    goto LABEL_299;
                  v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                  v18 = 0;
                  if ( !v17 )
                    goto LABEL_298;
                  dwImpLevel[0] = BitsCopyManager;
                  dwAuthnLevel[0] = 2527;
                }
                else
                {
                  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                    goto LABEL_299;
                  v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                  v18 = 0;
                  if ( !v17 )
                    goto LABEL_298;
                  dwImpLevel[0] = BitsCopyManager;
                  dwAuthnLevel[0] = 2525;
                }
              }
              else
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                  goto LABEL_299;
                v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
                v18 = 0;
                if ( !v17 )
                  goto LABEL_298;
                dwImpLevel[0] = BitsCopyManager;
                dwAuthnLevel[0] = 2519;
              }
            }
            else
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
                goto LABEL_299;
              v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
              v18 = 0;
              if ( !v17 )
                goto LABEL_298;
              dwImpLevel[0] = BitsCopyManager;
              dwAuthnLevel[0] = 2517;
            }
          }
          else
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
              goto LABEL_299;
            v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
            v18 = 0;
            if ( !v17 )
              goto LABEL_298;
            dwImpLevel[0] = BitsCopyManager;
            dwAuthnLevel[0] = 2514;
          }
        }
        else
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
            goto LABEL_299;
          v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
          v18 = 0;
          if ( !v17 )
            goto LABEL_298;
          dwImpLevel[0] = BitsCopyManager;
          dwAuthnLevel[0] = 2510;
        }
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
          goto LABEL_299;
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = 0;
        if ( !v17 )
          goto LABEL_298;
        dwImpLevel[0] = BitsCopyManager;
        dwAuthnLevel[0] = 2507;
      }
LABEL_296:
      v38 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v17,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpTransportBits::TransferFileWorker",
              *(_QWORD *)dwAuthnLevel,
              *(_QWORD *)dwImpLevel);
      v18 = (unsigned int)v38;
      if ( v38 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v38);
      goto LABEL_298;
    }
    BitsCopyManager = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v51->lpVtbl->QueryInterface)(
                        v51,
                        &GUID_443c8934_90ff_48ed_bcde_26f5c7450042,
                        &v55);
    if ( BitsCopyManager < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
        goto LABEL_299;
      v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      v18 = 0;
      if ( !v17 )
        goto LABEL_298;
      dwImpLevel[0] = BitsCopyManager;
      dwAuthnLevel[0] = 2489;
      goto LABEL_296;
    }
    if ( a3 )
      *(union _ULARGE_INTEGER *)&v72 = *a3;
    else
      *(_QWORD *)&v72 = 0;
    if ( a4 )
      *((union _ULARGE_INTEGER *)&v72 + 1) = *a4;
    else
      *((_QWORD *)&v72 + 1) = -1;
    v23 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, __int64, __int128 *))(*(_QWORD *)v55 + 352LL))(
            v55,
            v60,
            bstrString,
            1,
            &v72);
    if ( v23 == -2147024809 )
    {
      BitsCopyManager = -2147024735;
    }
    else
    {
      if ( v23 >= 0 )
      {
        if ( v55 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          v55 = 0;
        }
        goto LABEL_103;
      }
      BitsCopyManager = v23;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
      goto LABEL_299;
    v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    v18 = 0;
    if ( !v17 )
      goto LABEL_298;
    dwImpLevel[0] = BitsCopyManager;
    dwAuthnLevel[0] = 2499;
    goto LABEL_296;
  }
  BitsCopyManager = -2147019873;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
  {
    v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    v18 = 0;
    if ( v17 )
    {
      dwImpLevel[0] = -2147019873;
      dwAuthnLevel[0] = 2428;
      goto LABEL_296;
    }
LABEL_298:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
  }
LABEL_299:
  v9 = v50;
LABEL_300:
  v39 = v51;
  if ( v51 )
  {
    if ( v9 )
    {
      CBitsNotifyInterface::Disable(v9);
      v39 = v51;
    }
    ((void (__fastcall *)(IUnknown *, __int64))v39->lpVtbl[7].Release)(v39, 4);
    ((void (__fastcall *)(IUnknown *, _QWORD))v51->lpVtbl[8].AddRef)(v51, 0);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v64 = 1;
  v40 = *((_DWORD *)this + 54);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v64 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    v64 = 0;
  }
  if ( v40 == -1073741824 )
  {
    if ( BitsCopyManager >= 0 )
      BitsCopyManager = -2147023661;
    v41 = -858993460;
  }
  else
  {
    if ( BitsCopyManager >= 0 )
      goto LABEL_322;
    v41 = -1;
  }
  CDlpTransportBits::UpdateState(this, v41, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v64 = 1;
  *((_DWORD *)this + 24) = BitsCopyManager;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v64 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
    v64 = 0;
  }
  if ( v51 )
  {
    v42 = v62;
    if ( v62 )
    {
      ((void (__fastcall *)(IUnknown *, __int64 *))v51->lpVtbl[5].QueryInterface)(v51, &v61);
      if ( v61 )
      {
        (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v61 + 24LL))(v61, &v67, &v66);
        (*(void (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v61 + 40LL))(v61, 1024, pv);
      }
      (**((void (__fastcall ***)(__int64, _QWORD, LPVOID))v42 + 2))(
        (__int64)v42 + 16,
        (unsigned int)BitsCopyManager,
        pv[0]);
    }
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
    {
      v43 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v43,
        4u,
        (__int64)L"BitsTransferFile: Cancelling BITS job due to error: 0x%X",
        (unsigned int)BitsCopyManager);
    }
    ((void (__fastcall *)(IUnknown *))v51->lpVtbl[2].Release)(v51);
  }
LABEL_322:
  if ( v58 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    v64 = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_DWORD *)this + 55) = -21037378;
    *((_DWORD *)this + 54) = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v64 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      v64 = 0;
    }
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10) )
  {
    v44 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    CDlpLogT<CEmptyType>::DlpLogFormat(v44, 2u, (__int64)L"BitsTransport: Leaving TransferFile Method");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v60 )
  {
    SysFreeString(v60);
    v60 = 0;
  }
  if ( v68[0] )
  {
    v45 = (void *)(v68[0] - 4LL);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v45);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(CBitsNotifyInterface *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v51 )
  {
    ((void (__fastcall *)(IUnknown *))v51->lpVtbl->Release)(v51);
    v51 = 0;
  }
  if ( v54 )
    ((void (__fastcall *)(struct IBackgroundCopyManager *))v54->lpVtbl->Release)(v54);
  if ( v8 )
    CoUninitialize();
  if ( (_DWORD)v69 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
    LODWORD(v69) = 0;
  }
  return (unsigned int)BitsCopyManager;
}

```

## disassembly

```asm
0x180079890  push    rbp
0x180079892  push    rbx
0x180079893  push    rsi
0x180079894  push    rdi
0x180079895  push    r12
0x180079897  push    r13
0x180079899  push    r14
0x18007989b  push    r15
0x18007989d  lea     rbp, [rsp-68h]
0x1800798a2  sub     rsp, 168h
0x1800798a9  mov     rax, cs:__security_cookie
0x1800798b0  xor     rax, rsp
0x1800798b3  mov     [rbp+0A0h+var_50], rax
0x1800798b7  mov     r15, r9
0x1800798ba  mov     r14, r8
0x1800798bd  mov     rsi, rdx
0x1800798c0  mov     [rbp+0A0h+var_108], rdx
0x1800798c4  mov     r13, rcx
0x1800798c7  xorps   xmm0, xmm0
0x1800798ca  xor     eax, eax
0x1800798cc  movups  [rbp+0A0h+var_C0], xmm0
0x1800798d0  mov     [rbp+0A0h+var_B0], rax
0x1800798d4  lea     rax, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x1800798db  mov     qword ptr [rbp+0A0h+var_C0], rax
0x1800798df  lea     rax, [rcx+150h]
0x1800798e6  mov     qword ptr [rbp+0A0h+var_C0+8], rax
0x1800798ea  xor     ecx, ecx
0x1800798ec  mov     ebx, ecx
0x1800798ee  mov     [rbp+0A0h+var_D8], ecx
0x1800798f1  mov     [rsp+1A0h+var_140], rcx
0x1800798f6  mov     [rsp+1A0h+var_158], rcx
0x1800798fb  mov     [rsp+1A0h+var_138], rcx
0x180079900  mov     [rsp+1A0h+pProxy], rcx
0x180079905  mov     [rbp+0A0h+var_A8], rcx
0x180079909  mov     r12d, ecx
0x18007990c  mov     [rsp+1A0h+var_160], rcx
0x180079911  mov     [rbp+0A0h+var_110], rcx
0x180079915  mov     [rbp+0A0h+var_A0], rcx
0x180079919  mov     [rbp+0A0h+pv], rcx
0x18007991d  movups  [rbp+0A0h+var_60], xmm0
0x180079921  xorps   xmm1, xmm1
0x180079924  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm1
0x180079928  mov     [rbp+0A0h+var_C8], rcx
0x18007992c  mov     [rbp+0A0h+var_118], rcx
0x180079930  mov     [rbp+0A0h+bstrString], rcx
0x180079934  movups  [rbp+0A0h+var_98], xmm0
0x180079938  xor     eax, eax
0x18007993a  movups  [rbp+0A0h+var_78], xmm1
0x18007993e  mov     [rbp+0A0h+var_68], rax
0x180079942  mov     [rsp+1A0h+var_150], ecx
0x180079946  mov     [rsp+1A0h+var_130], ecx
0x18007994a  mov     [rbp+0A0h+var_D4], ecx
0x18007994d  mov     [rbp+0A0h+var_D0], ecx
0x180079950  lea     rdi, [r13+0A8h]
0x180079957  mov     rax, [rdi]
0x18007995a  mov     rcx, rdi
0x18007995d  mov     rax, [rax+10h]
0x180079961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079966  test    rax, rax
0x180079969  jz      short loc_18007998E
0x18007996b  mov     rax, [rdi]
0x18007996e  mov     rcx, rdi
0x180079971  mov     rax, [rax+10h]
0x180079975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007997a  mov     rcx, rax
0x18007997d  lea     r8, aBitstransportE; "BitsTransport: Entering TransferFile Me"...
0x180079984  lea     edx, [r12+2]
0x180079989  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18007998e  mov     [rsp+1A0h+var_128], 0
0x180079996  test    rsi, rsi
0x180079999  jnz     short loc_180079A0A
0x18007999b  mov     esi, 80070057h
0x1800799a0  mov     rax, [rdi]
0x1800799a3  mov     rcx, rdi
0x1800799a6  mov     rax, [rax+10h]
0x1800799aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799af  test    rax, rax
0x1800799b2  jz      loc_18007B276
0x1800799b8  mov     rax, [rdi]
0x1800799bb  mov     rcx, rdi
0x1800799be  mov     rax, [rax+10h]
0x1800799c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799c7  xor     ecx, ecx
0x1800799c9  test    rax, rax
0x1800799cc  jz      short loc_180079A00
0x1800799ce  mov     [rsp+1A0h+dwImpLevel], esi
0x1800799d2  mov     [rsp+1A0h+dwAuthnLevel], 973h
0x1800799da  lea     r9, aCdlptransportb_33; "CDlpTransportBits::TransferFileWorker"
0x1800799e1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800799e8  mov     edx, 4
0x1800799ed  mov     rcx, rax
0x1800799f0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800799f5  test    eax, eax
0x1800799f7  mov     ecx, eax
0x1800799f9  jns     short loc_180079A00
0x1800799fb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180079a00  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180079a05  jmp     loc_18007B276
0x180079a0a  lea     rcx, [r13+158h]; lpCriticalSection
0x180079a11  call    cs:__imp_EnterCriticalSection
0x180079a17  mov     esi, 1
0x180079a1c  mov     dword ptr [rbp+0A0h+var_B0], esi
0x180079a1f  lea     r12, [r13+0E8h]
0x180079a26  mov     rcx, r12; lpCriticalSection
0x180079a29  call    cs:__imp_EnterCriticalSection
0x180079a2f  mov     [rbp+0A0h+var_E8], esi
0x180079a32  mov     esi, [r13+0D8h]
0x180079a39  xor     ecx, ecx
0x180079a3b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180079a40  mov     eax, [rbp+0A0h+var_E8]
0x180079a43  test    eax, eax
0x180079a45  jz      short loc_180079A57
0x180079a47  mov     rcx, r12; lpCriticalSection
0x180079a4a  call    cs:__imp_LeaveCriticalSection
0x180079a50  mov     [rbp+0A0h+var_E8], 0
0x180079a57  cmp     esi, 1
0x180079a5a  jz      short loc_180079AA4
0x180079a5c  mov     esi, 8007139Fh
0x180079a61  mov     rax, [rdi]
0x180079a64  mov     rcx, rdi
0x180079a67  mov     rax, [rax+10h]
0x180079a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a70  test    rax, rax
0x180079a73  jz      loc_18007B271
0x180079a79  mov     rax, [rdi]
0x180079a7c  mov     rcx, rdi
0x180079a7f  mov     rax, [rax+10h]
0x180079a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a88  xor     ecx, ecx
0x180079a8a  test    rax, rax
0x180079a8d  jz      loc_18007B26C
0x180079a93  mov     [rsp+1A0h+dwImpLevel], esi
0x180079a97  mov     [rsp+1A0h+dwAuthnLevel], 97Ch
0x180079a9f  jmp     loc_18007B246
0x180079aa4  mov     [rsp+1A0h+var_128], 1
0x180079aac  mov     rcx, [rbp+0A0h+var_108]
0x180079ab0  mov     rax, [rcx]
0x180079ab3  lea     rdx, [rbp+0A0h+var_118]
0x180079ab7  mov     rax, [rax+30h]
0x180079abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ac0  mov     esi, eax
0x180079ac2  test    eax, eax
0x180079ac4  jns     short loc_180079B09
0x180079ac6  mov     rcx, [rdi]
0x180079ac9  mov     rax, [rcx+10h]
0x180079acd  mov     rcx, rdi
0x180079ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ad5  test    rax, rax
0x180079ad8  jz      loc_18007B271
0x180079ade  mov     rcx, [rdi]
0x180079ae1  mov     rax, [rcx+10h]
0x180079ae5  mov     rcx, rdi
0x180079ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079aed  xor     ecx, ecx
0x180079aef  test    rax, rax
0x180079af2  jz      loc_18007B26C
0x180079af8  mov     [rsp+1A0h+dwImpLevel], esi
0x180079afc  mov     [rsp+1A0h+dwAuthnLevel], 981h
0x180079b04  jmp     loc_18007B246
0x180079b09  mov     rcx, [rbp+0A0h+var_108]
0x180079b0d  mov     rax, [rcx]
0x180079b10  lea     rdx, [rbp+0A0h+bstrString]
0x180079b14  mov     rax, [rax+38h]
0x180079b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b1d  mov     esi, eax
0x180079b1f  test    eax, eax
0x180079b21  jns     short loc_180079B66
0x180079b23  mov     rax, [rdi]
0x180079b26  mov     rcx, rdi
0x180079b29  mov     rax, [rax+10h]
0x180079b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b32  test    rax, rax
0x180079b35  jz      loc_18007B271
0x180079b3b  mov     rax, [rdi]
0x180079b3e  mov     rcx, rdi
0x180079b41  mov     rax, [rax+10h]
0x180079b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b4a  xor     ecx, ecx
0x180079b4c  test    rax, rax
0x180079b4f  jz      loc_18007B26C
0x180079b55  mov     [rsp+1A0h+dwImpLevel], esi
0x180079b59  mov     [rsp+1A0h+dwAuthnLevel], 982h
0x180079b61  jmp     loc_18007B246
0x180079b66  xor     esi, esi
0x180079b68  xor     edx, edx; dwCoInit
0x180079b6a  xor     ecx, ecx; pvReserved
0x180079b6c  call    cs:__imp_CoInitializeEx
0x180079b72  test    eax, eax
0x180079b74  js      short loc_180079B7E
0x180079b76  lea     ebx, [rsi+1]
0x180079b79  mov     [rbp+0A0h+var_D8], ebx
0x180079b7c  jmp     short loc_180079B8E
0x180079b7e  cmp     eax, 80010106h
0x180079b83  jz      short loc_180079B8E
0x180079b85  mov     esi, eax
0x180079b87  mov     ecx, eax
0x180079b89  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180079b8e  mov     ecx, esi
0x180079b90  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180079b95  test    esi, esi
0x180079b97  jns     short loc_180079BDC
0x180079b99  mov     rax, [rdi]
0x180079b9c  mov     rcx, rdi
0x180079b9f  mov     rax, [rax+10h]
0x180079ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ba8  test    rax, rax
0x180079bab  jz      loc_18007B271
0x180079bb1  mov     rax, [rdi]
0x180079bb4  mov     rcx, rdi
0x180079bb7  mov     rax, [rax+10h]
0x180079bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079bc0  xor     ecx, ecx
0x180079bc2  test    rax, rax
0x180079bc5  jz      loc_18007B26C
0x180079bcb  mov     [rsp+1A0h+dwImpLevel], esi
0x180079bcf  mov     [rsp+1A0h+dwAuthnLevel], 986h
0x180079bd7  jmp     loc_18007B246
0x180079bdc  lea     rdx, [rsp+1A0h+var_140]; struct IBackgroundCopyManager **
0x180079be1  mov     rcx, r13; this
0x180079be4  call    ?GetBitsCopyManager@CDlpTransportBits@@AEAAJPEAPEAUIBackgroundCopyManager@@@Z; CDlpTransportBits::GetBitsCopyManager(IBackgroundCopyManager * *)
0x180079be9  mov     esi, eax
0x180079beb  test    eax, eax
0x180079bed  jns     short loc_180079C32
0x180079bef  mov     rax, [rdi]
0x180079bf2  mov     rcx, rdi
0x180079bf5  mov     rax, [rax+10h]
0x180079bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079bfe  test    rax, rax
0x180079c01  jz      loc_18007B271
0x180079c07  mov     rax, [rdi]
0x180079c0a  mov     rcx, rdi
0x180079c0d  mov     rax, [rax+10h]
0x180079c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c16  xor     ecx, ecx
0x180079c18  test    rax, rax
0x180079c1b  jz      loc_18007B26C
0x180079c21  mov     [rsp+1A0h+dwImpLevel], esi
0x180079c25  mov     [rsp+1A0h+dwAuthnLevel], 98Ah
0x180079c2d  jmp     loc_18007B246
0x180079c32  mov     rcx, [rsp+1A0h+var_140]
0x180079c37  mov     rax, [rcx]
0x180079c3a  lea     rdx, [rsp+1A0h+var_158]
0x180079c3f  mov     qword ptr [rsp+1A0h+dwAuthnLevel], rdx
0x180079c44  lea     r9, [rbp+0A0h+var_60]
0x180079c48  xor     r8d, r8d
0x180079c4b  lea     rdx, pszAgentW; "Windows Dlp Manager"
0x180079c52  mov     rax, [rax+18h]
0x180079c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c5b  mov     esi, eax
0x180079c5d  test    eax, eax
0x180079c5f  jns     short loc_180079CA4
0x180079c61  mov     rax, [rdi]
0x180079c64  mov     rcx, rdi
0x180079c67  mov     rax, [rax+10h]
0x180079c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c70  test    rax, rax
0x180079c73  jz      loc_18007B271
0x180079c79  mov     rax, [rdi]
0x180079c7c  mov     rcx, rdi
0x180079c7f  mov     rax, [rax+10h]
0x180079c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c88  xor     ecx, ecx
0x180079c8a  test    rax, rax
0x180079c8d  jz      loc_18007B26C
0x180079c93  mov     [rsp+1A0h+dwImpLevel], esi
0x180079c97  mov     [rsp+1A0h+dwAuthnLevel], 98Eh
0x180079c9f  jmp     loc_18007B246
0x180079ca4  mov     rax, qword ptr cs:WINDLP_TRANSPORT_DO
0x180079cab  cmp     rax, [r13+268h]
0x180079cb2  jnz     loc_18007A077
0x180079cb8  mov     rax, qword ptr cs:WINDLP_TRANSPORT_DO+8
0x180079cbf  cmp     rax, [r13+270h]
0x180079cc6  jnz     loc_18007A077
0x180079ccc  mov     rcx, [rsp+1A0h+var_158]
0x180079cd1  mov     rax, [rcx]
0x180079cd4  lea     r8, [rsp+1A0h+pProxy]
0x180079cd9  lea     rdx, _GUID_ee2584cf_a69c_4848_b633_2649962b3ef7
0x180079ce0  mov     rax, [rax]
0x180079ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ce8  mov     esi, eax
0x180079cea  test    eax, eax
0x180079cec  jns     short loc_180079D31
0x180079cee  mov     rax, [rdi]
0x180079cf1  mov     rcx, rdi
0x180079cf4  mov     rax, [rax+10h]
0x180079cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cfd  test    rax, rax
0x180079d00  jz      loc_18007B271
0x180079d06  mov     rax, [rdi]
0x180079d09  mov     rcx, rdi
0x180079d0c  mov     rax, [rax+10h]
0x180079d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d15  xor     ecx, ecx
0x180079d17  test    rax, rax
0x180079d1a  jz      loc_18007B26C
0x180079d20  mov     [rsp+1A0h+dwImpLevel], esi
0x180079d24  mov     [rsp+1A0h+dwAuthnLevel], 992h
0x180079d2c  jmp     loc_18007B246
0x180079d31  mov     [rsp+1A0h+dwCapabilities], 0; dwCapabilities
0x180079d39  mov     [rsp+1A0h+pAuthInfo], 0; pAuthInfo
  ... truncated ...
```
