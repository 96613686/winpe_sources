# CBWCContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata(IDiagnosticMetadataCollection *,CDiagnosticCollection *)

- ea: `0x180009e60`
- end: `0x18000a95c`
- name: `?FindDiagnosticsBySearchMetadata@CBWCContentDiagnosticProviderImpl@@UEAAJPEAUIDiagnosticMetadataCollection@@PEAVCDiagnosticCollection@@@Z`
- size: `2812`
- prototype: `__int64 __fastcall(CBWCContentDiagnosticProviderImpl *__hidden this, struct IDiagnosticMetadataCollection *, struct CDiagnosticCollection *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180007c88`
- `0x180009b48`
- `0x180009c70`
- `0x180009e60`
- `0x18000a964`
- `0x18000ac18`
- `0x18000ad80`
- `0x18000b1f8`
- `0x18000b268`
- `0x18000b324`
- `0x18000b3f8`
- `0x18000b4f8`
- `0x18000b5fc`
- `0x18000b82c`
- `0x18000c2a0`
- `0x18000c618`
- `0x18000e7f4`
- `0x18000f0ec`
- `0x18000f654`
- `0x18000fd98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a90f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a928`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a941`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a90f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a928`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a933`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a558`
- `ntdll!WinSqmAddToStream` at `0x18000a402`
- `ntdll!WinSqmAddToStream` at `0x18000a402`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000a2cc`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000a2cc`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000a54e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000a54e`

## string_xrefs

- `0x18000a085`: `BWCContentProviderConfiguration::GetRemoteServerTimeout`

## pseudocode

```c
__int64 __fastcall CBWCContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata(
        CBWCContentDiagnosticProviderImpl *this,
        struct IDiagnosticMetadataCollection *a2,
        struct CDiagnosticCollection *a3)
{
  struct CDiagnosticCollection *v4; // r12
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // rdi
  char *v7; // r15
  unsigned int v8; // r13d
  int PreferredUILanguages; // ebx
  int v10; // edx
  int v11; // ecx
  __int64 v12; // r8
  __int64 v13; // rdx
  BWCContentProviderConfiguration *v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // r12d
  BWCContentProviderConfiguration *v19; // rcx
  int RemoteServer; // eax
  unsigned __int16 v21; // r8
  const unsigned __int16 *v22; // r9
  int v23; // eax
  int v24; // ecx
  int RequestBody; // eax
  const unsigned __int16 *v26; // rdx
  int v27; // ecx
  char v28; // al
  __int64 v29; // rdx
  void *v30; // rcx
  int v31; // r15d
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // rax
  void *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  signed int LastError; // eax
  __int64 v42; // rcx
  char v43; // al
  signed __int32 v44; // eax
  int v45; // edx
  __int64 v46; // rcx
  char v47; // al
  __int64 *v48; // rdx
  const char *v49; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v51; // rax
  HANDLE v52; // rax
  __int16 lpdwBufferLength; // [rsp+20h] [rbp-148h]
  int v55; // [rsp+F0h] [rbp-78h]
  int v56; // [rsp+F4h] [rbp-74h]
  char *v57; // [rsp+F8h] [rbp-70h] BYREF
  CBWCRequest *v58; // [rsp+100h] [rbp-68h] BYREF
  unsigned __int16 *v59; // [rsp+108h] [rbp-60h] BYREF
  unsigned __int16 *v60[2]; // [rsp+110h] [rbp-58h] BYREF
  unsigned __int16 *v61; // [rsp+120h] [rbp-48h] BYREF
  unsigned int Buffer; // [rsp+170h] [rbp+8h] BYREF
  struct IDiagnosticMetadataCollection *v63; // [rsp+178h] [rbp+10h]
  struct CDiagnosticCollection *v64; // [rsp+180h] [rbp+18h]
  DWORD dwBufferLength; // [rsp+188h] [rbp+20h] BYREF

  v64 = a3;
  v63 = a2;
  v4 = a3;
  v58 = 0;
  v5 = 0;
  v60[0] = 0;
  v6 = 0;
  v59 = 0;
  v7 = 0;
  v57 = 0;
  v8 = 0;
  dwBufferLength = 0;
  Buffer = 0;
  v61 = 0;
  v55 = 0;
  v56 = 0;
  if ( !a2 || !a3 )
  {
    PreferredUILanguages = -2147024809;
    goto LABEL_64;
  }
  PreferredUILanguages = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
  {
    PreferredUILanguages = CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages(this);
    if ( PreferredUILanguages >= 0 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 1) != 0 )
      {
        v12 = *((_QWORD *)this + 2);
        McTemplateU0ddllddlzczzttdzzzzzzzzzuuuu_EventWriteTransfer(
          v11,
          v10,
          *(_DWORD *)v12,
          *(_DWORD *)(v12 + 4),
          *(_WORD *)(v12 + 8),
          *(_WORD *)(v12 + 10),
          *(_DWORD *)(v12 + 12),
          *(_DWORD *)(v12 + 16),
          *(_WORD *)(v12 + 20),
          *(_QWORD *)(v12 + 24),
          *(_BYTE *)(v12 + 22),
          *(_QWORD *)(v12 + 40),
          *(_QWORD *)(v12 + 48),
          *(_DWORD *)(v12 + 132),
          *(_DWORD *)(v12 + 136),
          *(_DWORD *)(v12 + 36),
          *(_QWORD *)(v12 + 56),
          *(_QWORD *)(v12 + 64),
          *(_QWORD *)(v12 + 72),
          *(_QWORD *)(v12 + 80),
          *(_QWORD *)(v12 + 88),
          *(_QWORD *)(v12 + 96),
          *(_QWORD *)(v12 + 104),
          *(_QWORD *)(v12 + 112),
          *(_QWORD *)(v12 + 120),
          *(_BYTE *)(v12 + 128),
          *(_BYTE *)(v12 + 129),
          *(_BYTE *)(v12 + 130),
          *(_BYTE *)(v12 + 131));
      }
      PreferredUILanguages = CBWCRequest::CreateInstance(*((LPCWSTR **)this + 2), v63, &v58);
      if ( PreferredUILanguages >= 0 && !_InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
      {
        v14 = *(BWCContentProviderConfiguration **)v58;
        if ( !*(_QWORD *)v58 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0sq_EventWriteTransfer(0, v13, "CBWCRequest::get_Timeout", 2147947423LL);
          PreferredUILanguages = -2147019873;
          goto LABEL_63;
        }
        v15 = *((_DWORD *)v14 + 9);
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        {
          McTemplateU0s_EventWriteTransfer(
            v14,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "BWCContentProviderConfiguration::GetRemoteServerTimeout");
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(v16, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CBWCRequest::get_Timeout");
        }
        PreferredUILanguages = CBWCContentDiagnosticProviderImpl::ConfigureConnector(this, v15);
        if ( PreferredUILanguages >= 0 && !_InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
        {
          v18 = -2147019873;
          v19 = *(BWCContentProviderConfiguration **)v58;
          if ( *(_QWORD *)v58 )
          {
            RemoteServer = BWCContentProviderConfiguration::GetRemoteServer(v19, &v59);
            PreferredUILanguages = RemoteServer;
            if ( RemoteServer == -2147024809 )
            {
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                McTemplateU0sq_EventWriteTransfer(v19, v17, "CBWCRequest::get_HostName", 2147942487LL);
              v6 = v59;
              goto LABEL_63;
            }
            if ( !RemoteServer )
            {
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
                McTemplateU0s_EventWriteTransfer(v19, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CBWCRequest::get_HostName");
              v6 = v59;
              goto LABEL_28;
            }
            v6 = v59;
          }
          else
          {
            PreferredUILanguages = -2147019873;
          }
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0sq_EventWriteTransfer(v19, v17, "CBWCRequest::get_HostName", (unsigned int)PreferredUILanguages);
          if ( PreferredUILanguages < 0 )
            goto LABEL_63;
LABEL_28:
          PreferredUILanguages = CBWCRequest::get_RequestUrlPath(v58, v60);
          if ( PreferredUILanguages < 0 || _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
          {
            v5 = v60[0];
            goto LABEL_63;
          }
          v5 = v60[0];
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            McTemplateU0zz_EventWriteTransfer(0, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CONNECT_START, v6, v60[0]);
          v23 = CHttpConnector::OpenConnection(*((CHttpConnector **)this + 1), v6, v21, v22, lpdwBufferLength, v5);
          PreferredUILanguages = v23;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            McTemplateU0zzq_EventWriteTransfer(
              v24,
              (unsigned int)SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CONNECT_END,
              (_DWORD)v6,
              (_DWORD)v5,
              v23);
          if ( PreferredUILanguages < 0 )
            goto LABEL_63;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
            goto LABEL_63;
          RequestBody = CBWCRequest::get_RequestBody(v58, &v57, &dwBufferLength);
          v7 = v57;
          PreferredUILanguages = RequestBody;
          if ( RequestBody < 0 )
            goto LABEL_63;
          v28 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 1) != 0 )
          {
            McTemplateU0zzs_EventWriteTransfer(
              v27,
              (unsigned int)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_SERVER_REQUEST,
              (_DWORD)v6,
              (_DWORD)v5,
              (__int64)v57);
            v28 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          }
          if ( (v28 & 0x20) != 0 )
            McTemplateU0zzs_EventWriteTransfer(
              v27,
              (unsigned int)SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_SEND_POST_REQUEST_START,
              (_DWORD)v6,
              (_DWORD)v5,
              (__int64)v7);
          v55 = 1;
          PreferredUILanguages = CHttpConnector::Send(*((CHttpConnector **)this + 1), v26, v7, dwBufferLength);
          if ( PreferredUILanguages < 0 || _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
            goto LABEL_63;
          v30 = *(void **)(*((_QWORD *)this + 1) + 16LL);
          if ( !v30 )
          {
            v31 = -2147019873;
            goto LABEL_58;
          }
          v31 = 0;
          if ( !WinHttpReceiveResponse(v30, 0) )
          {
            PreferredUILanguages = GetLastError();
            if ( PreferredUILanguages == 12002 )
            {
              LOWORD(v8) = -1;
            }
            else
            {
              if ( PreferredUILanguages == 12030 )
              {
                v31 = -2147012866;
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) != 0 )
                  McTemplateU0q_EventWriteTransfer(
                    v30,
                    SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_CONNECTION_ERROR,
                    2147954430LL);
                goto LABEL_58;
              }
              if ( PreferredUILanguages > 0 )
                PreferredUILanguages = (unsigned __int16)PreferredUILanguages | 0x80070000;
              if ( PreferredUILanguages == -2147024809 )
              {
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                {
                  McTemplateU0sq_EventWriteTransfer(v30, v29, "CHttpConnector::WaitForResponse", 2147942487LL);
LABEL_62:
                  v7 = v57;
LABEL_63:
                  v4 = v64;
                  goto LABEL_64;
                }
                v31 = -2147024809;
LABEL_60:
                PreferredUILanguages = v31;
                if ( v31 < 0 )
                {
LABEL_61:
                  v8 = Buffer;
                  goto LABEL_62;
                }
                goto LABEL_83;
              }
              v31 = PreferredUILanguages;
              if ( PreferredUILanguages )
              {
LABEL_58:
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                  McTemplateU0sq_EventWriteTransfer(v30, v29, "CHttpConnector::WaitForResponse", (unsigned int)v31);
                goto LABEL_60;
              }
            }
          }
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(v30, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::WaitForResponse");
          PreferredUILanguages = v31;
LABEL_83:
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
            goto LABEL_126;
          if ( (_WORD)v8 == 0xFFFF )
          {
            PreferredUILanguages = -2147024638;
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 2) != 0 )
            {
              McTemplateU0zz_EventWriteTransfer(
                0,
                SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_WAIT_TIMED_OUT,
                v6,
                v5);
              goto LABEL_61;
            }
LABEL_126:
            v8 = 0;
            goto LABEL_62;
          }
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1) )
            goto LABEL_126;
          v37 = *((_QWORD *)this + 1);
          v8 = 200;
          Buffer = 0;
          dwBufferLength = 4;
          v38 = *(void **)(v37 + 16);
          if ( !v38 )
            goto LABEL_96;
          if ( !WinHttpQueryHeaders(v38, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
          {
            LastError = GetLastError();
            PreferredUILanguages = LastError;
            if ( LastError > 0 )
              PreferredUILanguages = (unsigned __int16)LastError | 0x80070000;
            if ( PreferredUILanguages < 0 )
            {
              if ( PreferredUILanguages == -2147024809 )
              {
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                {
                  McTemplateU0sq_EventWriteTransfer(v38, v29, "CHttpConnector::get_StatusCode", 2147942487LL);
                  goto LABEL_62;
                }
                v18 = -2147024809;
LABEL_101:
                PreferredUILanguages = v18;
                goto LABEL_62;
              }
              v18 = PreferredUILanguages;
            }
            else
            {
              v18 = -2147467259;
            }
LABEL_96:
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
              McTemplateU0sq_EventWriteTransfer(v38, v29, "CHttpConnector::get_StatusCode", v18);
            goto LABEL_101;
          }
          v8 = Buffer;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(v40, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::get_StatusCode");
          PreferredUILanguages = 0;
          v42 = 200;
          if ( v8 != 200 )
          {
            PreferredUILanguages = -2147467259;
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) != 0 )
              McTemplateU0zzq_EventWriteTransfer(
                200,
                (unsigned int)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_ERROR_RESPONSE,
                (_DWORD)v6,
                (_DWORD)v5,
                v8);
            goto LABEL_62;
          }
          v43 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          v56 = 1;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
          {
            McTemplateU0qq_EventWriteTransfer(200, v39, 200, 0);
            v43 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          }
          if ( (v43 & 1) != 0 )
            McTemplateU0zz_EventWriteTransfer(
              v42,
              SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_RESPONSE_RECEIVED,
              v6,
              v5);
          v44 = _InterlockedCompareExchange((volatile signed __int32 *)this + 8, 0, 1);
          v7 = v57;
          if ( v44 )
            goto LABEL_63;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            McTemplateU0zzs_EventWriteTransfer(
              0,
              (unsigned int)SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_PARSE_RESPONSE_START,
              (_DWORD)v6,
              (_DWORD)v5,
              (__int64)v57);
          v4 = v64;
          PreferredUILanguages = CBWCContentDiagnosticProviderImpl::ParseResponse(this, v64, &v61);
          v47 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
          {
            McTemplateU0zzsq_EventWriteTransfer(v46, v45, (_DWORD)v6, (_DWORD)v5, (__int64)v7, PreferredUILanguages);
            v47 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
          }
          if ( PreferredUILanguages >= 0 && (v47 & 1) != 0 )
            McTemplateU0zz_EventWriteTransfer(
              v46,
              SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_RESPONSE_VALID,
              v6,
              v5);
        }
      }
    }
  }
LABEL_64:
  CHttpConnector::Abort(*((CHttpConnector **)this + 1));
  *((_QWORD *)this + 3) = -1;
  if ( v55 && !v56 && (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
    McTemplateU0qq_EventWriteTransfer(v33, v32, v8, (unsigned int)PreferredUILanguages);
  v60[1] = (unsigned __int16 *)(unsigned int)PreferredUILanguages;
  LODWORD(v60[0]) = 1;
  WinSqmAddToStream(0, 6713, 1, v60);
  if ( PreferredUILanguages == -2147446781 )
  {
    PreferredUILanguages = -2147467259;
    if ( v6 && v5 && (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) != 0 )
      McTemplateU0zzz_EventWriteTransfer(v35, v34, (_DWORD)v6, (_DWORD)v5, (__int64)v61);
    goto LABEL_159;
  }
  if ( PreferredUILanguages != -2147024809 )
  {
    if ( PreferredUILanguages == -2147023674 )
    {
      if ( !v6 || !v5 || (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) == 0 )
        goto LABEL_159;
      v48 = SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_SERVER_NO_NETWORK_CONNECTIVITY;
    }
    else if ( PreferredUILanguages == -2147023431 )
    {
      if ( !v6 || !v5 || (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) == 0 )
        goto LABEL_159;
      v48 = SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_RESPONSE_MALFORMED;
    }
    else
    {
      if ( PreferredUILanguages != -2147012894 )
      {
        if ( PreferredUILanguages == -2147012867 || PreferredUILanguages == -2147012866 )
        {
          if ( v6 && v5 && (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 8) != 0 )
            McTemplateU0zzq_EventWriteTransfer(
              v35,
              (unsigned int)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_SERVER_CONNECT_FAILED,
              (_DWORD)v6,
              (_DWORD)v5,
              PreferredUILanguages);
        }
        else
        {
          if ( PreferredUILanguages )
          {
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
              goto LABEL_159;
            v36 = (unsigned int)PreferredUILanguages;
            goto LABEL_78;
          }
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(
              v35,
              SDIAGPRV_EVENT_DEBUG_SUCCESS,
              "CBWCContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata");
        }
        goto LABEL_159;
      }
      if ( !v6 || !v5 || (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 2) == 0 )
        goto LABEL_159;
      v48 = SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_SERVER_WINHTTP_TIMED_OUT;
    }
    McTemplateU0zz_EventWriteTransfer(v35, v48, v6, v5);
    goto LABEL_159;
  }
  if ( !v63 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_159;
    v49 = "DiagnosticMetadataCollection";
LABEL_152:
    McTemplateU0sqs_EventWriteTransfer(
      v35,
      v34,
      (unsigned int)"CBWCContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata",
      -2147024809,
      (__int64)v49);
    goto LABEL_159;
  }
  if ( !v4 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_159;
    v49 = "DiagnosticCollection";
    goto LABEL_152;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v36 = 2147942487LL;
LABEL_78:
    McTemplateU0sq_EventWriteTransfer(
      v35,
      v34,
      "CBWCContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata",
      v36);
  }
LABEL_159:
  if ( v58 )
  {
    CBWCRequest::`scalar deleting destructor'(v58, v34);
    v58 = 0;
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( v6 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v6);
  }
  if ( v7 )
  {
    v52 = GetProcessHeap();
    HeapFree(v52, 0, v7);
  }
  return (unsigned int)PreferredUILanguages;
}

```

## disassembly

```asm
0x180009e60  mov     r11, rsp
0x180009e63  mov     [r11+18h], r8
0x180009e67  mov     [r11+10h], rdx
0x180009e6b  push    rbx
0x180009e6c  push    rsi
0x180009e6d  push    rdi
0x180009e6e  push    r12
0x180009e70  push    r13
0x180009e72  push    r14
0x180009e74  push    r15
0x180009e76  sub     rsp, 130h
0x180009e7d  mov     rax, rdx
0x180009e80  mov     r14, rcx
0x180009e83  xor     edx, edx
0x180009e85  mov     r12, r8
0x180009e88  mov     [r11-68h], rdx
0x180009e8c  mov     esi, edx
0x180009e8e  mov     [r11-58h], rdx
0x180009e92  mov     edi, edx
0x180009e94  mov     [r11-60h], rdx
0x180009e98  mov     r15d, edx
0x180009e9b  mov     [r11-70h], rdx
0x180009e9f  mov     r13d, edx
0x180009ea2  mov     [r11+20h], edx
0x180009ea6  mov     ecx, 80070057h
0x180009eab  mov     [rsp+168h+Buffer], edx
0x180009eb2  mov     [r11-48h], rdx
0x180009eb6  mov     [rsp+168h+var_78], edx
0x180009ebd  mov     [rsp+168h+var_74], edx
0x180009ec4  test    rax, rax
0x180009ec7  jnz     short loc_180009ED0
0x180009ec9  mov     ebx, ecx
0x180009ecb  jmp     loc_18000A397
0x180009ed0  test    r8, r8
0x180009ed3  jz      short loc_180009EC9
0x180009ed5  mov     ebx, edx
0x180009ed7  mov     ecx, edx
0x180009ed9  mov     eax, 1
0x180009ede  lock cmpxchg [r14+20h], ecx
0x180009ee4  test    eax, eax
0x180009ee6  jnz     loc_18000A397
0x180009eec  mov     rcx, r14; this
0x180009eef  call    ?GetPreferredUILanguages@CBWCContentDiagnosticProviderImpl@@AEAAJXZ; CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages(void)
0x180009ef4  mov     ebx, eax
0x180009ef6  test    eax, eax
0x180009ef8  js      loc_18000A397
0x180009efe  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 1
0x180009f05  jz      loc_18000A02E
0x180009f0b  mov     r8, [r14+10h]
0x180009f0f  mov     al, [r8+83h]
0x180009f16  mov     [rsp+168h+var_88], al
0x180009f1d  mov     al, [r8+82h]
0x180009f24  mov     [rsp+168h+var_90], al
0x180009f2b  mov     al, [r8+81h]
0x180009f32  mov     [rsp+168h+var_98], al
0x180009f39  mov     al, [r8+80h]
0x180009f40  mov     [rsp+168h+var_A0], al
0x180009f47  mov     rax, [r8+78h]
0x180009f4b  mov     [rsp+168h+var_A8], rax
0x180009f53  mov     rax, [r8+70h]
0x180009f57  mov     [rsp+168h+var_B0], rax
0x180009f5f  mov     rax, [r8+68h]
0x180009f63  mov     [rsp+168h+var_B8], rax
0x180009f6b  mov     rax, [r8+60h]
0x180009f6f  mov     [rsp+168h+var_C0], rax
0x180009f77  mov     rax, [r8+58h]
0x180009f7b  mov     [rsp+168h+var_C8], rax
0x180009f83  mov     rax, [r8+50h]
0x180009f87  mov     r9d, [r8+4]
0x180009f8b  mov     [rsp+168h+var_D0], rax
0x180009f93  mov     rax, [r8+48h]
0x180009f97  mov     [rsp+168h+var_D8], rax
0x180009f9f  mov     rax, [r8+40h]
0x180009fa3  mov     [rsp+168h+var_E0], rax
0x180009fab  mov     rax, [r8+38h]
0x180009faf  mov     [rsp+168h+var_E8], rax
0x180009fb7  mov     eax, [r8+24h]
0x180009fbb  mov     [rsp+168h+var_F0], eax
0x180009fbf  mov     eax, [r8+88h]
0x180009fc6  mov     [rsp+168h+var_F8], eax
0x180009fca  mov     eax, [r8+84h]
0x180009fd1  mov     [rsp+168h+var_100], eax
0x180009fd5  mov     rax, [r8+30h]
0x180009fd9  mov     [rsp+168h+var_108], rax
0x180009fde  mov     rax, [r8+28h]
0x180009fe2  mov     [rsp+168h+var_110], rax
0x180009fe7  mov     al, [r8+16h]
0x180009feb  mov     [rsp+168h+var_118], al
0x180009fef  mov     rax, [r8+18h]
0x180009ff3  mov     [rsp+168h+var_120], rax
0x180009ff8  movzx   eax, word ptr [r8+14h]
0x180009ffd  mov     [rsp+168h+var_128], ax
0x18000a002  mov     eax, [r8+10h]
0x18000a006  mov     [rsp+168h+var_130], eax
0x18000a00a  mov     eax, [r8+0Ch]
0x18000a00e  mov     [rsp+168h+var_138], eax
0x18000a012  movzx   eax, word ptr [r8+0Ah]
0x18000a017  mov     word ptr [rsp+168h+lpdwIndex], ax
0x18000a01c  movzx   eax, word ptr [r8+8]
0x18000a021  mov     r8d, [r8]
0x18000a024  mov     word ptr [rsp+168h+lpdwBufferLength], ax; __int16
0x18000a029  call    McTemplateU0ddllddlzczzttdzzzzzzzzzuuuu_EventWriteTransfer
0x18000a02e  mov     rdx, [rsp+168h+arg_8]; struct IDiagnosticMetadataCollection *
0x18000a036  lea     r8, [rsp+168h+var_68]; struct CBWCRequest **
0x18000a03e  mov     rcx, [r14+10h]; struct _SYSTEM_CONFIGURATION *
0x18000a042  call    ?CreateInstance@CBWCRequest@@SAJPEAU_SYSTEM_CONFIGURATION@@PEAUIDiagnosticMetadataCollection@@PEAPEAV1@@Z; CBWCRequest::CreateInstance(_SYSTEM_CONFIGURATION *,IDiagnosticMetadataCollection *,CBWCRequest * *)
0x18000a047  mov     ebx, eax
0x18000a049  test    eax, eax
0x18000a04b  js      loc_18000A397
0x18000a051  xor     ecx, ecx
0x18000a053  lea     eax, [rcx+1]
0x18000a056  lock cmpxchg [r14+20h], ecx
0x18000a05c  test    eax, eax
0x18000a05e  jnz     loc_18000A397
0x18000a064  mov     rax, [rsp+168h+var_68]
0x18000a06c  mov     rcx, [rax]
0x18000a06f  test    rcx, rcx
0x18000a072  jz      loc_18000A742
0x18000a078  mov     ebx, [rcx+24h]
0x18000a07b  mov     al, byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1
0x18000a081  test    al, 1
0x18000a083  jz      short loc_18000A0B5
0x18000a085  lea     r8, aBwccontentprov_4; "BWCContentProviderConfiguration::GetRem"...
0x18000a08c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000a093  call    McTemplateU0s_EventWriteTransfer
0x18000a098  mov     al, byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1
0x18000a09e  test    al, 1
0x18000a0a0  jz      short loc_18000A0B5
0x18000a0a2  lea     r8, aCbwcrequestGet_1; "CBWCRequest::get_Timeout"
0x18000a0a9  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000a0b0  call    McTemplateU0s_EventWriteTransfer
0x18000a0b5  mov     edx, ebx; unsigned int
0x18000a0b7  mov     rcx, r14; this
0x18000a0ba  call    ?ConfigureConnector@CBWCContentDiagnosticProviderImpl@@AEAAJK@Z; CBWCContentDiagnosticProviderImpl::ConfigureConnector(ulong)
0x18000a0bf  mov     ebx, eax
0x18000a0c1  test    eax, eax
0x18000a0c3  js      loc_18000A397
0x18000a0c9  xor     ecx, ecx
0x18000a0cb  lea     eax, [rcx+1]
0x18000a0ce  lock cmpxchg [r14+20h], ecx
0x18000a0d4  test    eax, eax
0x18000a0d6  jnz     loc_18000A397
0x18000a0dc  mov     rax, [rsp+168h+var_68]
0x18000a0e4  mov     r12d, 8007139Fh
0x18000a0ea  mov     rcx, [rax]; this
0x18000a0ed  test    rcx, rcx
0x18000a0f0  jnz     short loc_18000A0F7
0x18000a0f2  mov     ebx, r12d
0x18000a0f5  jmp     short loc_18000A11D
0x18000a0f7  lea     rdx, [rsp+168h+var_60]; unsigned __int16 **
0x18000a0ff  call    ?GetRemoteServer@BWCContentProviderConfiguration@@QEBAJPEAPEAG@Z; BWCContentProviderConfiguration::GetRemoteServer(ushort * *)
0x18000a104  mov     ebx, eax
0x18000a106  cmp     eax, 80070057h
0x18000a10b  jz      loc_18000A71A
0x18000a111  test    eax, eax
0x18000a113  jz      short loc_18000A13F
0x18000a115  mov     rdi, [rsp+168h+var_60]
0x18000a11d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000a124  jz      short loc_18000A135
0x18000a126  mov     r9d, ebx
0x18000a129  lea     r8, aCbwcrequestGet_0; "CBWCRequest::get_HostName"
0x18000a130  call    McTemplateU0sq_EventWriteTransfer
0x18000a135  test    ebx, ebx
0x18000a137  js      loc_18000A38F
0x18000a13d  jmp     short loc_18000A163
0x18000a13f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000a146  jz      short loc_18000A15B
0x18000a148  lea     r8, aCbwcrequestGet_0; "CBWCRequest::get_HostName"
0x18000a14f  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000a156  call    McTemplateU0s_EventWriteTransfer
0x18000a15b  mov     rdi, [rsp+168h+var_60]
0x18000a163  mov     rcx, [rsp+168h+var_68]; this
0x18000a16b  lea     rdx, [rsp+168h+var_58]; unsigned __int16 **
0x18000a173  call    ?get_RequestUrlPath@CBWCRequest@@QEBAJPEAPEAG@Z; CBWCRequest::get_RequestUrlPath(ushort * *)
0x18000a178  mov     ebx, eax
0x18000a17a  test    eax, eax
0x18000a17c  js      loc_18000A70D
0x18000a182  xor     ecx, ecx
0x18000a184  lea     eax, [rcx+1]
0x18000a187  lock cmpxchg [r14+20h], ecx
0x18000a18d  test    eax, eax
0x18000a18f  jnz     loc_18000A70D
0x18000a195  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x18000a19c  mov     rsi, [rsp+168h+var_58]
0x18000a1a4  jz      short loc_18000A1B8
0x18000a1a6  mov     r9, rsi
0x18000a1a9  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CONNECT_START
0x18000a1b0  mov     r8, rdi
0x18000a1b3  call    McTemplateU0zz_EventWriteTransfer
0x18000a1b8  mov     rcx, [r14+8]; this
0x18000a1bc  mov     rdx, rdi; pswzServerName
0x18000a1bf  mov     [rsp+168h+lpdwIndex], rsi; unsigned __int16 *
0x18000a1c4  call    ?OpenConnection@CHttpConnector@@QEAAJPEBGG0F0@Z; CHttpConnector::OpenConnection(ushort const *,ushort,ushort const *,short,ushort const *)
0x18000a1c9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x18000a1d0  mov     ebx, eax
0x18000a1d2  jz      short loc_18000A1EA
0x18000a1d4  mov     r9, rsi
0x18000a1d7  mov     dword ptr [rsp+168h+lpdwBufferLength], eax
0x18000a1db  mov     r8, rdi
0x18000a1de  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CONNECT_END
0x18000a1e5  call    McTemplateU0zzq_EventWriteTransfer
0x18000a1ea  test    ebx, ebx
0x18000a1ec  js      loc_18000A38F
0x18000a1f2  xor     ecx, ecx
0x18000a1f4  lea     eax, [rcx+1]
0x18000a1f7  lock cmpxchg [r14+20h], ecx
0x18000a1fd  test    eax, eax
0x18000a1ff  jnz     loc_18000A38F
0x18000a205  mov     rcx, [rsp+168h+var_68]; this
0x18000a20d  lea     r8, [rsp+168h+dwBufferLength]; unsigned int *
0x18000a215  lea     rdx, [rsp+168h+var_70]; char **
0x18000a21d  call    ?get_RequestBody@CBWCRequest@@QEBAJPEAPEADPEAK@Z; CBWCRequest::get_RequestBody(char * *,ulong *)
0x18000a222  mov     r15, [rsp+168h+var_70]
0x18000a22a  mov     ebx, eax
0x18000a22c  test    eax, eax
0x18000a22e  js      loc_18000A38F
0x18000a234  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits
0x18000a23a  test    al, 1
0x18000a23c  jz      short loc_18000A25B
0x18000a23e  mov     r9, rsi
0x18000a241  mov     [rsp+168h+lpdwBufferLength], r15
0x18000a246  mov     r8, rdi
0x18000a249  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_SERVER_REQUEST
0x18000a250  call    McTemplateU0zzs_EventWriteTransfer
0x18000a255  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits
0x18000a25b  test    al, 20h
0x18000a25d  jz      short loc_18000A276
0x18000a25f  mov     r9, rsi
0x18000a262  mov     [rsp+168h+lpdwBufferLength], r15
0x18000a267  mov     r8, rdi
0x18000a26a  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_SEND_POST_REQUEST_START
0x18000a271  call    McTemplateU0zzs_EventWriteTransfer
0x18000a276  mov     r9d, [rsp+168h+dwBufferLength]; unsigned int
0x18000a27e  mov     r8, r15; void *
0x18000a281  mov     rcx, [r14+8]; this
0x18000a285  mov     [rsp+168h+var_78], 1
0x18000a290  call    ?Send@CHttpConnector@@QEAAJPEBGPEAXK@Z; CHttpConnector::Send(ushort const *,void *,ulong)
0x18000a295  mov     ebx, eax
0x18000a297  test    eax, eax
0x18000a299  js      loc_18000A38F
0x18000a29f  xor     ecx, ecx
0x18000a2a1  lea     eax, [rcx+1]
0x18000a2a4  lock cmpxchg [r14+20h], ecx
0x18000a2aa  test    eax, eax
0x18000a2ac  jnz     loc_18000A38F
0x18000a2b2  mov     rax, [r14+8]
0x18000a2b6  mov     rcx, [rax+10h]; hRequest
0x18000a2ba  test    rcx, rcx
0x18000a2bd  jnz     short loc_18000A2C7
0x18000a2bf  mov     r15d, r12d
0x18000a2c2  jmp     loc_18000A35B
0x18000a2c7  xor     edx, edx; lpReserved
0x18000a2c9  xor     r15d, r15d
0x18000a2cc  call    cs:__imp_WinHttpReceiveResponse
0x18000a2d2  test    eax, eax
0x18000a2d4  jnz     loc_18000A489
0x18000a2da  call    cs:__imp_GetLastError
0x18000a2e0  mov     ebx, eax
0x18000a2e2  sub     eax, 2EE2h
0x18000a2e7  jz      loc_18000A485
0x18000a2ed  cmp     eax, 1Ch
0x18000a2f0  jz      short loc_18000A33A
0x18000a2f2  test    ebx, ebx
0x18000a2f4  jle     short loc_18000A2FF
0x18000a2f6  movzx   ebx, bx
0x18000a2f9  or      ebx, 80070000h
0x18000a2ff  cmp     ebx, 80070057h
0x18000a305  jz      short loc_18000A316
0x18000a307  xor     eax, eax
0x18000a309  mov     r15d, ebx
0x18000a30c  test    ebx, ebx
0x18000a30e  jz      loc_18000A489
0x18000a314  jmp     short loc_18000A35B
0x18000a316  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000a31d  jz      short loc_18000A333
0x18000a31f  mov     r9d, 80070057h
0x18000a325  lea     r8, aChttpconnector_18; "CHttpConnector::WaitForResponse"
0x18000a32c  call    McTemplateU0sq_EventWriteTransfer
0x18000a331  jmp     short loc_18000A387
0x18000a333  xor     eax, eax
0x18000a335  mov     r15d, ebx
0x18000a338  jmp     short loc_18000A373
0x18000a33a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 8
0x18000a341  mov     r15d, 80072EFEh
0x18000a347  jz      short loc_18000A35B
0x18000a349  mov     r8d, 80072EFEh
0x18000a34f  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_CONNECTION_ERROR
0x18000a356  call    McTemplateU0q_EventWriteTransfer
0x18000a35b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000a362  jz      short loc_18000A373
0x18000a364  mov     r9d, r15d
0x18000a367  lea     r8, aChttpconnector_18; "CHttpConnector::WaitForResponse"
0x18000a36e  call    McTemplateU0sq_EventWriteTransfer
0x18000a373  mov     ebx, r15d
0x18000a376  test    r15d, r15d
0x18000a379  jns     loc_18000A4A8
0x18000a37f  mov     r13d, [rsp+168h+Buffer]
0x18000a387  mov     r15, [rsp+168h+var_70]
0x18000a38f  mov     r12, [rsp+168h+arg_10]
0x18000a397  mov     rcx, [r14+8]; this
  ... truncated ...
```
