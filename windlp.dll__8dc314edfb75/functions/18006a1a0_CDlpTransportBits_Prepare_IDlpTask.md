# CDlpTransportBits::Prepare(IDlpTask *)

- ea: `0x18006a1a0`
- end: `0x18006aec6`
- name: `?Prepare@CDlpTransportBits@@UEAAJPEAVIDlpTask@@@Z`
- size: `3366`
- prototype: `__int64 __fastcall(CDlpTransportBits *__hidden this, struct IDlpTask *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180049e50`
- `0x18005a960`
- `0x180061dec`
- `0x18006a1a0`
- `0x18007da50`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006a9b0`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006a9b0`
- `RPCRT4!UuidCreate` at `0x18006a7a1`
- `RPCRT4!UuidCreate` at `0x18006a7a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a6e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a718`
- `OLEAUT32!__imp_SysFreeString` at `0x18006add4`
- `OLEAUT32!__imp_SysFreeString` at `0x18006adeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a6e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a718`
- `OLEAUT32!__imp_SysFreeString` at `0x18006add4`
- `OLEAUT32!__imp_SysFreeString` at `0x18006adeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a776`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ae06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a776`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ae06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a785`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ae14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a785`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ae14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a230`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006adbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006adbe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006a3ac`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006a3ac`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a5ac`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006abee`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a5ac`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006abee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006ae96`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006ae96`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDlpTransportBits::Prepare(CDlpTransportBits *this, struct IDlpTask *a2)
{
  CDlpTransportBits *v3; // rdi
  int v4; // ebx
  char *v5; // rsi
  __int64 v6; // rax
  int updated; // r14d
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  HRESULT v13; // eax
  unsigned int v14; // r15d
  __int64 v15; // r14
  HANDLE ProcessHeap; // rax
  RPC_STATUS v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  void *v24; // rdi
  HANDLE v25; // rax
  DWORD dwAuthnLevel[2]; // [rsp+20h] [rbp-89h]
  DWORD dwImpLevel[2]; // [rsp+28h] [rbp-81h]
  _QWORD *v29; // [rsp+40h] [rbp-69h] BYREF
  IUnknown *v30; // [rsp+48h] [rbp-61h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-51h] BYREF
  BSTR v33; // [rsp+60h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-41h] BYREF
  __int64 v35; // [rsp+70h] [rbp-39h] BYREF
  int v36; // [rsp+78h] [rbp-31h]
  struct IBackgroundCopyManager *v37; // [rsp+80h] [rbp-29h] BYREF
  CDlpTransportBits *v38; // [rsp+88h] [rbp-21h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-19h]
  void **v40; // [rsp+98h] [rbp-11h]
  char *v41; // [rsp+A0h] [rbp-9h]
  __int64 v42; // [rsp+A8h] [rbp-1h]
  __int64 v43; // [rsp+B0h] [rbp+7h]
  UUID Uuid; // [rsp+B8h] [rbp+Fh] BYREF

  v3 = this;
  v38 = this;
  v4 = 0;
  v36 = 0;
  v37 = 0;
  v30 = 0;
  pProxy = 0;
  v29 = 0;
  Uuid = 0;
  v35 = 0;
  bstrString = 0;
  v33 = 0;
  v32 = 0;
  v43 = 0;
  v41 = (char *)this + 336;
  v40 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 344);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  v42 = 1;
  v5 = (char *)v3 + 168;
  if ( (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v3 + 21) + 16LL))((__int64)v3 + 168) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
    CDlpLogT<CEmptyType>::DlpLogFormat(v6, 2u, (__int64)L"BitsTransport: Entering Prepare Method");
  }
  if ( !a2 )
  {
    updated = -2147024809;
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v9 = 0;
      if ( v8 )
      {
        v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v8,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpTransportBits::Prepare",
                1162,
                -2147024809);
        v9 = (unsigned int)v10;
        if ( v10 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    }
    goto LABEL_123;
  }
  updated = CDlpTransportBits::CheckInitialized(v3, 0);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1166;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  updated = CDlpTransportBits::UpdateState(v3, 1, 0);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1168;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  updated = 0;
  v13 = CoInitializeEx(0, 0);
  if ( v13 < 0 )
  {
    if ( v13 != -2147417850 )
    {
      updated = v13;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    }
  }
  else
  {
    v4 = 1;
    v36 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1172;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  updated = CDlpTransportBits::GetBitsCopyManager(v3, &v37);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1176;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  updated = ((__int64 (__fastcall *)(struct IBackgroundCopyManager *, const WCHAR *, _QWORD, char *, IUnknown **))v37->lpVtbl->CreateJob)(
              v37,
              L"Windows Dlp Manager",
              0,
              (char *)v3 + 636,
              &v30);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1180;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  if ( WINDLP_TRANSPORT_DO == *(_OWORD *)((char *)v3 + 616) )
  {
    updated = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v30->lpVtbl->QueryInterface)(
                v30,
                &GUID_ee2584cf_a69c_4848_b633_2649962b3ef7,
                &pProxy);
    if ( updated < 0 )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
        v12 = 0;
        if ( v11 )
        {
          dwImpLevel[0] = updated;
          dwAuthnLevel[0] = 1184;
          goto LABEL_119;
        }
        goto LABEL_121;
      }
      goto LABEL_122;
    }
    updated = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
    if ( updated < 0 )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
        v12 = 0;
        if ( v11 )
        {
          dwImpLevel[0] = updated;
          dwAuthnLevel[0] = 1192;
          goto LABEL_119;
        }
        goto LABEL_121;
      }
      goto LABEL_122;
    }
  }
  updated = (*(__int64 (__fastcall **)(struct IDlpTask *, unsigned int *))(*(_QWORD *)a2 + 184LL))(a2, &v32);
  if ( updated < 0 )
  {
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))((__int64)v3 + 168);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1198;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    goto LABEL_122;
  }
  v14 = 0;
  if ( !v32 )
  {
LABEL_69:
    if ( WINDLP_TRANSPORT_DO == *(_OWORD *)((char *)v3 + 616) )
    {
      if ( v30 )
      {
        ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
        v30 = 0;
      }
      updated = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
                  pProxy,
                  &GUID_37668d37_507e_4160_9316_26306d150b12,
                  &v30);
      if ( updated < 0 )
      {
        if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        {
          v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
          v12 = 0;
          if ( v11 )
          {
            dwImpLevel[0] = updated;
            dwAuthnLevel[0] = 1241;
            goto LABEL_119;
          }
          goto LABEL_121;
        }
        goto LABEL_122;
      }
      updated = CoSetProxyBlanket(v30, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
      if ( updated < 0 )
      {
        if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        {
          v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
          v12 = 0;
          if ( v11 )
          {
            dwImpLevel[0] = updated;
            dwAuthnLevel[0] = 1249;
            goto LABEL_119;
          }
          goto LABEL_121;
        }
        goto LABEL_122;
      }
      if ( pProxy )
      {
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        pProxy = 0;
      }
    }
    updated = CDlpTransportBits::UpdateState(v3, 2, 0);
    if ( updated < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
      {
        v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
        v12 = 0;
        if ( v11 )
        {
          dwImpLevel[0] = updated;
          dwAuthnLevel[0] = 1253;
          goto LABEL_119;
        }
        goto LABEL_121;
      }
      goto LABEL_122;
    }
    goto LABEL_129;
  }
  while ( 1 )
  {
    if ( v29 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      v29 = 0;
    }
    updated = (*(__int64 (__fastcall **)(struct IDlpTask *, _QWORD, _QWORD **))(*(_QWORD *)a2 + 168LL))(a2, v14, &v29);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1204;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v29[2] + 16LL))(v29 + 2, 1);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1206;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v29 + 48LL))(v29, &bstrString);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1209;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( v33 )
    {
      SysFreeString(v33);
      v33 = 0;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v29 + 56LL))(v29, &v33);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1212;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( WINDLP_TRANSPORT_DO == *(_OWORD *)((char *)v3 + 616) )
      break;
    v19 = ((__int64 (__fastcall *)(IUnknown *, BSTR, BSTR))v30->lpVtbl[1].AddRef)(v30, bstrString, v33);
    updated = v19;
    if ( v19 == -2147024809 )
    {
      updated = -2147024735;
LABEL_94:
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1232;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( v19 < 0 )
      goto LABEL_94;
LABEL_67:
    updated = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v29[2] + 16LL))(v29 + 2, 2);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1235;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( ++v14 >= v32 )
      goto LABEL_69;
  }
  v15 = v35;
  if ( v35 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v15 - 4));
    v3 = v38;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v35 = 0;
  }
  v17 = UuidCreate(&Uuid);
  if ( !v17 )
  {
    updated = CDlpHelpersT<CEmptyType>::GuidToSString(&Uuid, 1, &v35);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v5 + 16LL))(v5, 0) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1218;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    v18 = ((__int64 (__fastcall *)(IUnknown *, __int64, BSTR, BSTR, _DWORD, _QWORD, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
            pProxy,
            v35,
            bstrString,
            v33,
            0,
            0,
            0);
    updated = v18;
    if ( v18 == -2147024809 )
    {
      updated = -2147024735;
LABEL_77:
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
        goto LABEL_122;
      v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = 0;
      if ( v11 )
      {
        dwImpLevel[0] = updated;
        dwAuthnLevel[0] = 1226;
        goto LABEL_119;
      }
      goto LABEL_121;
    }
    if ( v18 < 0 )
      goto LABEL_77;
    goto LABEL_67;
  }
  v20 = I_RpcMapWin32Status(v17);
  updated = v20;
  if ( v20 > 0 )
    updated = (unsigned __int16)v20 | 0x80070000;
  if ( updated >= 0 )
    updated = -2147467259;
  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
    goto LABEL_122;
  v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  v12 = 0;
  if ( !v11 )
    goto LABEL_121;
  dwImpLevel[0] = updated;
  dwAuthnLevel[0] = 1217;
LABEL_119:
  v21 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v11,
          4u,
          (__int64)L"%s(%d): Result = 0x%X",
          L"CDlpTransportBits::Prepare",
          *(_QWORD *)dwAuthnLevel,
          *(_QWORD *)dwImpLevel);
  v12 = (unsigned int)v21;
  if ( v21 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
LABEL_121:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
LABEL_122:
  if ( updated < 0 )
  {
LABEL_123:
    CDlpTransportBits::UpdateState(v3, 0xFFFFFFFFLL, 0);
    if ( v30 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
      {
        v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v22,
          4u,
          (__int64)L"Cancelling BITS job due to error: 0x%X",
          (unsigned int)updated);
      }
      ((void (__fastcall *)(IUnknown *))v30->lpVtbl[2].Release)(v30);
    }
    if ( v29 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v29[2] + 16LL))(v29 + 2, 0xFFFFFFFFLL);
      (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))v29[2])(v29 + 2, (unsigned int)updated, 0);
    }
  }
LABEL_129:
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5) )
  {
    v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
    CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2u, (__int64)L"BitsTransport: Leaving Prepare Method");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( (_DWORD)v42 )
  {
    LeaveCriticalSection(lpCriticalSection);
    LODWORD(v42) = 0;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v33 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v35 )
  {
    v24 = (void *)(v35 - 4);
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( v30 )
  {
    ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
    v30 = 0;
  }
  if ( v37 )
    ((void (__fastcall *)(struct IBackgroundCopyManager *))v37->lpVtbl->Release)(v37);
  if ( v4 )
    CoUninitialize();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18006a1a0  mov     [rsp-8+arg_10], rbx
0x18006a1a5  push    rbp
0x18006a1a6  push    rsi
0x18006a1a7  push    rdi
0x18006a1a8  push    r12
0x18006a1aa  push    r13
0x18006a1ac  push    r14
0x18006a1ae  push    r15
0x18006a1b0  lea     rbp, [rsp-27h]
0x18006a1b5  sub     rsp, 0D0h
0x18006a1bc  mov     rax, cs:__security_cookie
0x18006a1c3  xor     rax, rsp
0x18006a1c6  mov     [rbp+57h+var_38], rax
0x18006a1ca  mov     r13, rdx
0x18006a1cd  mov     rdi, rcx
0x18006a1d0  mov     [rbp+57h+var_78], rcx
0x18006a1d4  xor     ebx, ebx
0x18006a1d6  mov     [rbp+57h+var_88], ebx
0x18006a1d9  mov     [rbp+57h+var_80], rbx
0x18006a1dd  mov     [rbp+57h+var_B8], rbx
0x18006a1e1  mov     [rbp+57h+pProxy], rbx
0x18006a1e5  mov     [rbp+57h+var_C0], rbx
0x18006a1e9  xorps   xmm0, xmm0
0x18006a1ec  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18006a1f0  xor     edx, edx
0x18006a1f2  mov     [rbp+57h+var_90], rdx
0x18006a1f6  mov     [rbp+57h+bstrString], rdx
0x18006a1fa  mov     [rbp+57h+var_A0], rdx
0x18006a1fe  mov     [rbp+57h+var_A8], edx
0x18006a201  mov     [rbp+57h+var_50], rdx
0x18006a205  xor     eax, eax
0x18006a207  movups  [rbp+57h+var_68], xmm0
0x18006a20b  mov     [rbp+57h+var_58], rax
0x18006a20f  lea     rax, [rcx+150h]
0x18006a216  mov     qword ptr [rbp+57h+var_68+8], rax
0x18006a21a  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18006a221  mov     qword ptr [rbp+57h+var_68], rcx
0x18006a225  add     rax, 8
0x18006a229  mov     [rbp+57h+lpCriticalSection], rax
0x18006a22d  mov     rcx, rax; lpCriticalSection
0x18006a230  call    cs:__imp_EnterCriticalSection
0x18006a236  lea     r15d, [rbx+1]
0x18006a23a  mov     dword ptr [rbp+57h+var_58], r15d
0x18006a23e  lea     rsi, [rdi+0A8h]
0x18006a245  mov     rax, [rsi]
0x18006a248  mov     rcx, rsi
0x18006a24b  mov     rax, [rax+10h]
0x18006a24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a254  test    rax, rax
0x18006a257  jz      short loc_18006A27A
0x18006a259  mov     rax, [rsi]
0x18006a25c  mov     rcx, rsi
0x18006a25f  mov     rax, [rax+10h]
0x18006a263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a268  mov     rcx, rax
0x18006a26b  lea     r8, aBitstransportE_0; "BitsTransport: Entering Prepare Method"
0x18006a272  lea     edx, [rbx+2]
0x18006a275  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006a27a  mov     r12d, 4
0x18006a280  test    r13, r13
0x18006a283  jnz     short loc_18006A2F7
0x18006a285  mov     r12d, 80070057h
0x18006a28b  mov     r14d, r12d
0x18006a28e  mov     rax, [rsi]
0x18006a291  mov     rcx, rsi
0x18006a294  mov     rax, [rax+10h]
0x18006a298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a29d  test    rax, rax
0x18006a2a0  jz      loc_18006ACDD
0x18006a2a6  mov     rax, [rsi]
0x18006a2a9  mov     rcx, rsi
0x18006a2ac  mov     rax, [rax+10h]
0x18006a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2b5  xor     ecx, ecx
0x18006a2b7  test    rax, rax
0x18006a2ba  jz      short loc_18006A2ED
0x18006a2bc  mov     [rsp+100h+dwImpLevel], r12d
0x18006a2c1  mov     [rsp+100h+dwAuthnLevel], 48Ah
0x18006a2c9  lea     r9, aCdlptransportb_23; "CDlpTransportBits::Prepare"
0x18006a2d0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006a2d7  lea     edx, [rcx+4]
0x18006a2da  mov     rcx, rax
0x18006a2dd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006a2e2  mov     ecx, eax
0x18006a2e4  test    eax, eax
0x18006a2e6  jns     short loc_18006A2ED
0x18006a2e8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006a2ed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006a2f2  jmp     loc_18006ACDD
0x18006a2f7  xor     edx, edx; enum WINDLP_STATE *
0x18006a2f9  mov     rcx, rdi; this
0x18006a2fc  call    ?CheckInitialized@CDlpTransportBits@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTransportBits::CheckInitialized(WINDLP_STATE *)
0x18006a301  mov     r14d, eax
0x18006a304  test    eax, eax
0x18006a306  jns     short loc_18006A34C
0x18006a308  mov     rcx, [rsi]
0x18006a30b  mov     rax, [rcx+10h]
0x18006a30f  mov     rcx, rsi
0x18006a312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a317  test    rax, rax
0x18006a31a  jz      loc_18006ACD4
0x18006a320  mov     rcx, [rsi]
0x18006a323  mov     rax, [rcx+10h]
0x18006a327  mov     rcx, rsi
0x18006a32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a32f  xor     ecx, ecx
0x18006a331  test    rax, rax
0x18006a334  jz      loc_18006ACCF
0x18006a33a  mov     [rsp+100h+dwImpLevel], r14d
0x18006a33f  mov     [rsp+100h+dwAuthnLevel], 48Eh
0x18006a347  jmp     loc_18006ACAB
0x18006a34c  xor     r8d, r8d
0x18006a34f  mov     edx, r15d
0x18006a352  mov     rcx, rdi
0x18006a355  call    ?UpdateState@CDlpTransportBits@@AEAAJW4WINDLP_STATE@@PEAW42@@Z; CDlpTransportBits::UpdateState(WINDLP_STATE,WINDLP_STATE *)
0x18006a35a  mov     r14d, eax
0x18006a35d  test    eax, eax
0x18006a35f  jns     short loc_18006A3A5
0x18006a361  mov     rax, [rsi]
0x18006a364  mov     rcx, rsi
0x18006a367  mov     rax, [rax+10h]
0x18006a36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a370  test    rax, rax
0x18006a373  jz      loc_18006ACD4
0x18006a379  mov     rax, [rsi]
0x18006a37c  mov     rcx, rsi
0x18006a37f  mov     rax, [rax+10h]
0x18006a383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a388  xor     ecx, ecx
0x18006a38a  test    rax, rax
0x18006a38d  jz      loc_18006ACCF
0x18006a393  mov     [rsp+100h+dwImpLevel], r14d
0x18006a398  mov     [rsp+100h+dwAuthnLevel], 490h
0x18006a3a0  jmp     loc_18006ACAB
0x18006a3a5  xor     r14d, r14d
0x18006a3a8  xor     edx, edx; dwCoInit
0x18006a3aa  xor     ecx, ecx; pvReserved
0x18006a3ac  call    cs:__imp_CoInitializeEx
0x18006a3b2  test    eax, eax
0x18006a3b4  js      short loc_18006A3BE
0x18006a3b6  mov     ebx, r15d
0x18006a3b9  mov     [rbp+57h+var_88], ebx
0x18006a3bc  jmp     short loc_18006A3CF
0x18006a3be  cmp     eax, 80010106h
0x18006a3c3  jz      short loc_18006A3CF
0x18006a3c5  mov     r14d, eax
0x18006a3c8  mov     ecx, eax
0x18006a3ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006a3cf  mov     ecx, r14d
0x18006a3d2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006a3d7  test    r14d, r14d
0x18006a3da  jns     short loc_18006A420
0x18006a3dc  mov     rax, [rsi]
0x18006a3df  mov     rcx, rsi
0x18006a3e2  mov     rax, [rax+10h]
0x18006a3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3eb  test    rax, rax
0x18006a3ee  jz      loc_18006ACD4
0x18006a3f4  mov     rax, [rsi]
0x18006a3f7  mov     rcx, rsi
0x18006a3fa  mov     rax, [rax+10h]
0x18006a3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a403  xor     ecx, ecx
0x18006a405  test    rax, rax
0x18006a408  jz      loc_18006ACCF
0x18006a40e  mov     [rsp+100h+dwImpLevel], r14d
0x18006a413  mov     [rsp+100h+dwAuthnLevel], 494h
0x18006a41b  jmp     loc_18006ACAB
0x18006a420  lea     rdx, [rbp+57h+var_80]; struct IBackgroundCopyManager **
0x18006a424  mov     rcx, rdi; this
0x18006a427  call    ?GetBitsCopyManager@CDlpTransportBits@@AEAAJPEAPEAUIBackgroundCopyManager@@@Z; CDlpTransportBits::GetBitsCopyManager(IBackgroundCopyManager * *)
0x18006a42c  mov     r14d, eax
0x18006a42f  test    eax, eax
0x18006a431  jns     short loc_18006A477
0x18006a433  mov     rax, [rsi]
0x18006a436  mov     rcx, rsi
0x18006a439  mov     rax, [rax+10h]
0x18006a43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a442  test    rax, rax
0x18006a445  jz      loc_18006ACD4
0x18006a44b  mov     rax, [rsi]
0x18006a44e  mov     rcx, rsi
0x18006a451  mov     rax, [rax+10h]
0x18006a455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a45a  xor     ecx, ecx
0x18006a45c  test    rax, rax
0x18006a45f  jz      loc_18006ACCF
0x18006a465  mov     [rsp+100h+dwImpLevel], r14d
0x18006a46a  mov     [rsp+100h+dwAuthnLevel], 498h
0x18006a472  jmp     loc_18006ACAB
0x18006a477  mov     rcx, [rbp+57h+var_80]
0x18006a47b  mov     rax, [rcx]
0x18006a47e  lea     r9, [rdi+27Ch]
0x18006a485  lea     rdx, [rbp+57h+var_B8]
0x18006a489  mov     qword ptr [rsp+100h+dwAuthnLevel], rdx
0x18006a48e  xor     r8d, r8d
0x18006a491  lea     rdx, pszAgentW; "Windows Dlp Manager"
0x18006a498  mov     rax, [rax+18h]
0x18006a49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4a1  mov     r14d, eax
0x18006a4a4  test    eax, eax
0x18006a4a6  jns     short loc_18006A4EC
0x18006a4a8  mov     rax, [rsi]
0x18006a4ab  mov     rcx, rsi
0x18006a4ae  mov     rax, [rax+10h]
0x18006a4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4b7  test    rax, rax
0x18006a4ba  jz      loc_18006ACD4
0x18006a4c0  mov     rax, [rsi]
0x18006a4c3  mov     rcx, rsi
0x18006a4c6  mov     rax, [rax+10h]
0x18006a4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4cf  xor     ecx, ecx
0x18006a4d1  test    rax, rax
0x18006a4d4  jz      loc_18006ACCF
0x18006a4da  mov     [rsp+100h+dwImpLevel], r14d
0x18006a4df  mov     [rsp+100h+dwAuthnLevel], 49Ch
0x18006a4e7  jmp     loc_18006ACAB
0x18006a4ec  mov     rax, qword ptr cs:WINDLP_TRANSPORT_DO
0x18006a4f3  or      r15d, 0FFFFFFFFh
0x18006a4f7  cmp     rax, [rdi+268h]
0x18006a4fe  jnz     loc_18006A5FD
0x18006a504  mov     rax, qword ptr cs:WINDLP_TRANSPORT_DO+8
0x18006a50b  cmp     rax, [rdi+270h]
0x18006a512  jnz     loc_18006A5FD
0x18006a518  mov     rcx, [rbp+57h+var_B8]
0x18006a51c  mov     rax, [rcx]
0x18006a51f  lea     r8, [rbp+57h+pProxy]
0x18006a523  lea     rdx, _GUID_ee2584cf_a69c_4848_b633_2649962b3ef7
0x18006a52a  mov     rax, [rax]
0x18006a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a532  mov     r14d, eax
0x18006a535  test    eax, eax
0x18006a537  jns     short loc_18006A57D
0x18006a539  mov     rax, [rsi]
0x18006a53c  mov     rcx, rsi
0x18006a53f  mov     rax, [rax+10h]
0x18006a543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a548  test    rax, rax
0x18006a54b  jz      loc_18006ACD4
0x18006a551  mov     rax, [rsi]
0x18006a554  mov     rcx, rsi
0x18006a557  mov     rax, [rax+10h]
0x18006a55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a560  xor     ecx, ecx
0x18006a562  test    rax, rax
0x18006a565  jz      loc_18006ACCF
0x18006a56b  mov     [rsp+100h+dwImpLevel], r14d
0x18006a570  mov     [rsp+100h+dwAuthnLevel], 4A0h
0x18006a578  jmp     loc_18006ACAB
0x18006a57d  mov     [rsp+100h+dwCapabilities], 0; dwCapabilities
0x18006a585  mov     [rsp+100h+pAuthInfo], 0; pAuthInfo
0x18006a58e  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x18006a596  mov     [rsp+100h+dwAuthnLevel], 5; dwAuthnLevel
0x18006a59e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18006a5a2  mov     r8d, r15d; dwAuthzSvc
0x18006a5a5  mov     edx, r15d; dwAuthnSvc
0x18006a5a8  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18006a5ac  call    cs:__imp_CoSetProxyBlanket
0x18006a5b2  mov     r14d, eax
0x18006a5b5  test    eax, eax
0x18006a5b7  jns     short loc_18006A5FD
0x18006a5b9  mov     rax, [rsi]
0x18006a5bc  mov     rcx, rsi
0x18006a5bf  mov     rax, [rax+10h]
0x18006a5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5c8  test    rax, rax
0x18006a5cb  jz      loc_18006ACD4
0x18006a5d1  mov     rax, [rsi]
0x18006a5d4  mov     rcx, rsi
0x18006a5d7  mov     rax, [rax+10h]
0x18006a5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5e0  xor     ecx, ecx
0x18006a5e2  test    rax, rax
0x18006a5e5  jz      loc_18006ACCF
0x18006a5eb  mov     [rsp+100h+dwImpLevel], r14d
0x18006a5f0  mov     [rsp+100h+dwAuthnLevel], 4A8h
0x18006a5f8  jmp     loc_18006ACAB
0x18006a5fd  mov     rax, [r13+0]
0x18006a601  lea     rdx, [rbp+57h+var_A8]
0x18006a605  mov     rcx, r13
0x18006a608  mov     rax, [rax+0B8h]
0x18006a60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a614  mov     r14d, eax
0x18006a617  test    eax, eax
0x18006a619  jns     short loc_18006A65F
0x18006a61b  mov     rax, [rsi]
0x18006a61e  mov     rcx, rsi
0x18006a621  mov     rax, [rax+10h]
0x18006a625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a62a  test    rax, rax
0x18006a62d  jz      loc_18006ACD4
0x18006a633  mov     rax, [rsi]
0x18006a636  mov     rcx, rsi
0x18006a639  mov     rax, [rax+10h]
0x18006a63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a642  xor     ecx, ecx
0x18006a644  test    rax, rax
0x18006a647  jz      loc_18006ACCF
0x18006a64d  mov     [rsp+100h+dwImpLevel], r14d
  ... truncated ...
```
