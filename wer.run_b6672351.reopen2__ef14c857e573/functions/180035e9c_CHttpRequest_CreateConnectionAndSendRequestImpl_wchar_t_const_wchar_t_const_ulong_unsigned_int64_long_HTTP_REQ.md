# CHttpRequest::CreateConnectionAndSendRequestImpl(wchar_t const *,wchar_t const *,ulong,unsigned __int64,long (*)(_HTTP_REQUEST_CALLBACK *),void *,ushort,unsigned __int64,wchar_t const *)

- ea: `0x180035e9c`
- end: `0x180036c57`
- name: `?CreateConnectionAndSendRequestImpl@CHttpRequest@@IEAAJPEB_W0K_KP6AJPEAU_HTTP_REQUEST_CALLBACK@@@ZPEAXG10@Z`
- size: `3515`
- prototype: `__int64 __usercall@<rax>(CHttpRequest *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, unsigned __int64, int (*)(struct _HTTP_REQUEST_CALLBACK *), void *, unsigned __int16, unsigned __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009edfc`

## callees

- `0x180004c64`
- `0x18000db80`
- `0x180018090`
- `0x180019ebc`
- `0x18001b148`
- `0x18001c120`
- `0x18001c368`
- `0x180020680`
- `0x18002a0c4`
- `0x18002efac`
- `0x180035e9c`
- `0x18003de9c`
- `0x180053300`
- `0x180053d3c`
- `0x18009f5ac`
- `0x18009ff10`
- `0x18009ffd8`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800365a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036ba6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800365a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003613c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003635b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800363d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003613c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003635b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800363d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369c1`
- `ntdll!wcschr` at `0x180035f9f`
- `ntdll!wcschr` at `0x180036ab3`
- `ntdll!wcschr` at `0x180035f9f`
- `ntdll!wcschr` at `0x180036ab3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036424`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036434`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036424`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036034`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003698c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036034`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003698c`
- `WINHTTP!WinHttpSetOption` at `0x180036208`
- `WINHTTP!WinHttpSetOption` at `0x180036272`
- `WINHTTP!WinHttpSetOption` at `0x1800362dc`
- `WINHTTP!WinHttpSetOption` at `0x18003634b`
- `WINHTTP!WinHttpSetOption` at `0x1800363c1`
- `WINHTTP!WinHttpSetOption` at `0x180036565`
- `WINHTTP!WinHttpSetOption` at `0x1800366b3`
- `WINHTTP!WinHttpSetOption` at `0x180036725`
- `WINHTTP!WinHttpSetOption` at `0x1800367d8`
- `WINHTTP!WinHttpSetOption` at `0x180036841`
- `WINHTTP!WinHttpSetOption` at `0x1800368b7`
- `WINHTTP!WinHttpSetOption` at `0x180036208`
- `WINHTTP!WinHttpSetOption` at `0x180036272`
- `WINHTTP!WinHttpSetOption` at `0x1800362dc`
- `WINHTTP!WinHttpSetOption` at `0x18003634b`
- `WINHTTP!WinHttpSetOption` at `0x1800363c1`
- `WINHTTP!WinHttpSetOption` at `0x180036565`
- `WINHTTP!WinHttpSetOption` at `0x1800366b3`
- `WINHTTP!WinHttpSetOption` at `0x180036725`
- `WINHTTP!WinHttpSetOption` at `0x1800367d8`
- `WINHTTP!WinHttpSetOption` at `0x180036841`
- `WINHTTP!WinHttpSetOption` at `0x1800368b7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180036926`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180036926`
- `WINHTTP!WinHttpOpen` at `0x180036079`
- `WINHTTP!WinHttpOpen` at `0x18003610b`
- `WINHTTP!WinHttpOpen` at `0x180036079`
- `WINHTTP!WinHttpOpen` at `0x18003610b`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800361af`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800361af`
- `WINHTTP!WinHttpConnect` at `0x1800364c3`
- `WINHTTP!WinHttpConnect` at `0x1800364c3`
- `WINHTTP!WinHttpOpenRequest` at `0x180036616`
- `WINHTTP!WinHttpOpenRequest` at `0x180036616`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800369b2`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800369b2`
- `WINHTTP!WinHttpCloseHandle` at `0x180036090`
- `WINHTTP!WinHttpCloseHandle` at `0x180036124`
- `WINHTTP!WinHttpCloseHandle` at `0x1800364dc`
- `WINHTTP!WinHttpCloseHandle` at `0x18003662f`
- `WINHTTP!WinHttpCloseHandle` at `0x180036090`
- `WINHTTP!WinHttpCloseHandle` at `0x180036124`
- `WINHTTP!WinHttpCloseHandle` at `0x1800364dc`
- `WINHTTP!WinHttpCloseHandle` at `0x18003662f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHttpRequest::CreateConnectionAndSendRequestImpl(
        CHttpRequest *this,
        const wchar_t *a2,
        wchar_t *a3,
        unsigned int a4,
        unsigned __int64 a5,
        int (*a6)(struct _HTTP_REQUEST_CALLBACK *),
        void *a7,
        INTERNET_PORT a8,
        unsigned __int64 a9,
        const wchar_t *a10)
{
  INTERNET_PORT v13; // si
  int ProxyInfoForUrl; // ebx
  char v15; // al
  unsigned int v16; // r15d
  wchar_t *v17; // rax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // esi
  HINTERNET v21; // rax
  void *v22; // rcx
  DWORD LastError; // eax
  HINTERNET v24; // rax
  void *v25; // rcx
  DWORD v26; // eax
  wchar_t *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  wchar_t *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  void *v38; // rcx
  HINTERNET v39; // rax
  void *v40; // rcx
  DWORD v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  const WCHAR *v45; // rsi
  HINTERNET v46; // rax
  void *v47; // rcx
  DWORD v48; // eax
  DWORD v49; // eax
  DWORD v50; // eax
  DWORD v51; // eax
  DWORD v52; // eax
  unsigned int v53; // eax
  DWORD v54; // eax
  DWORD v55; // eax
  unsigned int v56; // ebx
  WINHTTP_STATUS_CALLBACK v57; // rbx
  DWORD v58; // r14d
  wchar_t *v59; // r14
  int v60; // r12d
  wchar_t *v61; // rax
  int v62; // edx
  int v63; // r8d
  int v64; // eax
  unsigned int v65; // eax
  unsigned __int64 v67; // [rsp+30h] [rbp-D0h]
  int v68; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v69; // [rsp+44h] [rbp-BCh]
  __int64 v70; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v71; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+58h] [rbp-A8h]
  unsigned int v73; // [rsp+60h] [rbp-A0h]
  LPCWSTR pswzServerName; // [rsp+68h] [rbp-98h]
  unsigned int v75; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *Str; // [rsp+78h] [rbp-88h]
  CHttpRequest *Buffer; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpszHeaders; // [rsp+88h] [rbp-78h]
  wchar_t *v79[2]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v80[8]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v81[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v82[8]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v83[2]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v84[7]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v85; // [rsp+10Ch] [rbp+Ch]
  __int64 v86; // [rsp+114h] [rbp+14h]

  v73 = a4;
  Str = a3;
  pswzServerName = a2;
  v13 = a8;
  v69 = a8;
  lpszHeaders = a10;
  memset(v83, 0, sizeof(v83));
  v81[0] = v82;
  v81[1] = v82;
  v82[0] = 0;
  v79[0] = v80;
  v79[1] = v80;
  v80[0] = 0;
  v75 = 0;
  Buffer = this;
  v68 = 0;
  memset_0(v84, 0, 0xE8u);
  if ( *((_QWORD *)this + 2) )
  {
    ProxyInfoForUrl = -2147483638;
    goto LABEL_155;
  }
  ProxyInfoForUrl = -2147467259;
  v15 = a4;
  v16 = a4 | 1;
  if ( (v15 & 0x10) == 0 )
    v16 = v73;
  *((_DWORD *)this + 206) = -1;
  if ( (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v17 = wcschr(a3, 0x3Fu);
    if ( v17 )
    {
      v71 = a3;
      v72 = v17 - a3;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_S_utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)pswzServerName, (__int64)&v71);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
        (_DWORD)pswzServerName,
        (__int64)a3);
    }
  }
  v71 = (wchar_t *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  LOBYTE(v72) = 1;
  if ( !*(_QWORD *)this )
  {
    v20 = v73 & 0x100;
    v21 = WinHttpOpen(L"MSDW", v20 != 0 ? 4 : 1, 0, 0, 0x10000000u);
    v22 = *(void **)this;
    *(_QWORD *)this = v21;
    if ( v22 )
      WinHttpCloseHandle(v22);
    if ( !*(_QWORD *)this && v20 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, LastError);
      }
      v24 = WinHttpOpen(L"MSDW", 1u, 0, 0, 0x10000000u);
      v25 = *(void **)this;
      *(_QWORD *)this = v24;
      if ( v25 )
        WinHttpCloseHandle(v25);
    }
    if ( !*(_QWORD *)this )
    {
      v26 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v26);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 51;
LABEL_27:
      WPP_SF_d(
        *((_QWORD *)v27 + 2),
        v28,
        WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
        (unsigned int)ProxyInfoForUrl);
LABEL_28:
      utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v71);
      goto LABEL_155;
    }
    if ( !WinHttpSetTimeouts(
            *(HINTERNET *)this,
            *((_DWORD *)this + 63),
            *((_DWORD *)this + 64),
            *((_DWORD *)this + 65),
            *((_DWORD *)this + 66)) )
    {
      v29 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v29);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 52;
      goto LABEL_27;
    }
    if ( !WinHttpSetOption(*(HINTERNET *)this, 0x2Du, &Buffer, 8u) )
    {
      v30 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v30);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 53;
      goto LABEL_27;
    }
    v68 = 1;
    if ( !WinHttpSetOption(*(HINTERNET *)this, 0x58u, &v68, 4u) )
    {
      v31 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v31);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 54;
      goto LABEL_27;
    }
    v68 = 2048;
    if ( !WinHttpSetOption(*(HINTERNET *)this, 0x54u, &v68, 4u) )
    {
      v32 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v32);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 55;
      goto LABEL_27;
    }
    if ( *((_BYTE *)this + 868) )
    {
      LODWORD(v70) = 0;
      if ( !WinHttpSetOption(*(HINTERNET *)this, 0x80u, &v70, 4u) )
      {
        v33 = GetLastError();
        ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v33);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
            (unsigned int)ProxyInfoForUrl);
      }
    }
    if ( *((_DWORD *)this + 16) )
    {
      v70 = *((_QWORD *)this + 6);
      if ( !WinHttpSetOption(*(HINTERNET *)this, 0x63u, &v70, 8u) )
      {
        v34 = GetLastError();
        ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v34);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_28;
        v28 = 57;
        goto LABEL_27;
      }
    }
    v13 = v69;
  }
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v71);
  ResetEvent(*((HANDLE *)this + 4));
  ResetEvent(*((HANDLE *)this + 6));
  *((_QWORD *)this + 109) = 0;
  *((_DWORD *)this + 59) = 0;
  if ( a6
    && (LODWORD(v83[0]) = 0,
        *((_QWORD *)&v83[0] + 1) = a7,
        ProxyInfoForUrl = ((__int64 (__fastcall *)(_OWORD *))a6)(v83),
        ProxyInfoForUrl < 0) )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v36 = 58;
LABEL_61:
      v37 = (unsigned int)ProxyInfoForUrl;
LABEL_62:
      WPP_SF_d(*((_QWORD *)v35 + 2), v36, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v37);
    }
  }
  else
  {
    v38 = (void *)*((_QWORD *)this + 1);
    if ( v38 )
      goto LABEL_70;
    v39 = WinHttpConnect(*(HINTERNET *)this, pswzServerName, v13, 0);
    v40 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v39;
    if ( v40 )
      WinHttpCloseHandle(v40);
    v38 = (void *)*((_QWORD *)this + 1);
    if ( v38 )
    {
LABEL_70:
      v84[0] = 65538;
      if ( (v16 & 0x80u) != 0 )
      {
        v86 = 1;
        v85 = 4;
        v84[5] = 1;
        v84[6] = 1;
        if ( !WinHttpSetOption(v38, 0x83u, v84, 0xE8u)
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
            (unsigned int)ProxyInfoForUrl);
        }
      }
      LODWORD(v70) = GetTickCount();
      if ( (v16 & 2) != 0 )
      {
        v45 = L"GET";
      }
      else if ( (v16 & 4) != 0 )
      {
        v45 = L"PUT";
      }
      else if ( (v16 & 8) != 0 )
      {
        v45 = L"POST";
      }
      else
      {
        v45 = 0;
        MicrosoftTelemetryAssertTriggeredNoArgs(v43, v42, v44);
      }
      v46 = WinHttpOpenRequest(*((HINTERNET *)this + 1), v45, a3, 0, 0, 0, (unsigned __int8)(v16 & 1) << 23);
      v47 = (void *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = v46;
      if ( v47 )
        WinHttpCloseHandle(v47);
      if ( *((_QWORD *)this + 2) )
      {
        *((_DWORD *)this + 59) = CTimer::Stop((CTimer *)&v70);
        if ( (v16 & 0x10) == 0 || (v68 = 1, WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Du, &v68, 4u)) )
        {
          if ( (v16 & 0x100) == 0 || (v68 = 0, WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Du, &v68, 4u)) )
          {
            if ( (v16 & 1) != 0 )
            {
              if ( (v16 & 0x400) != 0 )
              {
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
              }
              else
              {
                v68 = 1;
                if ( !WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Fu, &v68, 4u) )
                {
                  v51 = GetLastError();
                  ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v51);
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v36 = 65;
                    goto LABEL_61;
                  }
                  goto LABEL_155;
                }
                LODWORD(v70) = 1;
                if ( !WinHttpSetOption(*((HINTERNET *)this + 2), 0x9Bu, &v70, 4u) )
                {
                  v52 = GetLastError();
                  v53 = ERROR_HR_FROM_WIN32(v52);
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      66,
                      WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                      v53);
                }
              }
            }
            if ( (v16 & 0x200) == 0 || (v68 = 3, WinHttpSetOption(*((HINTERNET *)this + 2), 0x76u, &v68, 4u)) )
            {
              if ( lpszHeaders
                && *lpszHeaders
                && !WinHttpAddRequestHeaders(*((HINTERNET *)this + 2), lpszHeaders, 0xFFFFFFFF, 0x20000000u) )
              {
                v55 = GetLastError();
                ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v55);
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v36 = 68;
                  goto LABEL_61;
                }
              }
              else
              {
                v56 = *((_DWORD *)this + 16) != 0 ? 0xFFFFF400 : 0;
                v71 = (wchar_t *)((char *)this + 72);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
                LOBYTE(v72) = 1;
                v57 = WinHttpSetStatusCallback(
                        *((HINTERNET *)this + 2),
                        CHttpRequest::Stub_WinHttpCompletionCallback,
                        v56 + 159321088,
                        0);
                v58 = GetLastError();
                utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v71);
                if ( v57 != (WINHTTP_STATUS_CALLBACK)-1LL )
                {
                  *((_DWORD *)this + 58) = 0;
                  v59 = Str;
                  if ( (v16 & 0x20) != 0 )
                  {
                    v60 = (int)pswzServerName;
                  }
                  else
                  {
                    v60 = (int)pswzServerName;
                    if ( (v16 & 0x100) == 0 )
                    {
                      ProxyInfoForUrl = CHttpRequest::GetProxyInfoForUrl(
                                          (_DWORD)this,
                                          (_DWORD)pswzServerName,
                                          (_DWORD)Str,
                                          v16 & 1,
                                          (__int64)v81,
                                          (__int64)v79,
                                          (__int64)&v75);
                      if ( ProxyInfoForUrl < 0 )
                      {
                        v35 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                        {
                          v36 = 70;
                          goto LABEL_61;
                        }
                        goto LABEL_155;
                      }
                    }
                  }
                  if ( (WPP_GLOBAL_Control[14] & 4) != 0 )
                  {
                    v61 = wcschr(v59, 0x3Fu);
                    if ( v61 )
                    {
                      v71 = v59;
                      v72 = v61 - v59;
                      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                        WPP_SF_S_utlwsv_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v62,
                          v63,
                          v60,
                          (__int64)&v71,
                          (__int64)v45);
                    }
                    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                    {
                      WPP_SF_SSS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        72,
                        (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                        v60,
                        (__int64)v59,
                        (__int64)v45);
                    }
                  }
                  v64 = CHttpRequest::SendRequestWithRetry(this, v81[0], v79[0], v75, a5, v16, v67);
                  ProxyInfoForUrl = v64;
                  if ( v64 >= 0 )
                  {
                    if ( (v73 & 0x40) == 0 )
                      goto LABEL_154;
                    LODWORD(v70) = GetTickCount();
                    ProxyInfoForUrl = CHttpRequest::CheckCertForMicrosoftRoot(*((void **)this + 2));
                    v65 = CTimer::Stop((CTimer *)&v70);
                    *((_DWORD *)this + 206) = v65;
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        74,
                        WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                        v65);
                      v35 = WPP_GLOBAL_Control;
                    }
                    if ( ProxyInfoForUrl >= 0 )
                    {
LABEL_154:
                      ProxyInfoForUrl = 0;
                      goto LABEL_155;
                    }
                    if ( v35 != (wchar_t *)&WPP_GLOBAL_Control && (v35[14] & 1) != 0 )
                    {
                      v36 = 75;
                      goto LABEL_61;
                    }
                  }
                  else
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                    {
                      v36 = 73;
                      v37 = (unsigned int)v64;
                      goto LABEL_62;
                    }
                  }
                  goto LABEL_155;
                }
                ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v58);
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v36 = 69;
                  goto LABEL_61;
                }
              }
            }
            else
            {
              v54 = GetLastError();
              ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v54);
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v36 = 67;
                goto LABEL_61;
              }
            }
          }
          else
          {
            v50 = GetLastError();
            ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v50);
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v36 = 63;
              goto LABEL_61;
            }
          }
        }
        else
        {
          v49 = GetLastError();
          ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v49);
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v36 = 62;
            goto LABEL_61;
          }
        }
      }
      else
      {
        v48 = GetLastError();
        ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v48);
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v36 = 61;
          goto LABEL_61;
        }
      }
    }
    else
    {
      v41 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v41);
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v36 = 59;
        goto LABEL_61;
      }
    }
  }
LABEL_155:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v79);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v81);
  return (unsigned int)ProxyInfoForUrl;
}

```

## disassembly

```asm
0x180035e9c  push    rbp
0x180035e9e  push    rbx
0x180035e9f  push    rsi
0x180035ea0  push    rdi
0x180035ea1  push    r12
0x180035ea3  push    r13
0x180035ea5  push    r14
0x180035ea7  push    r15
0x180035ea9  lea     rbp, [rsp-0F8h]
0x180035eb1  sub     rsp, 1F8h
0x180035eb8  mov     rax, cs:__security_cookie
0x180035ebf  xor     rax, rsp
0x180035ec2  mov     [rbp+130h+var_50], rax
0x180035ec9  mov     r15d, r9d
0x180035ecc  mov     [rsp+230h+var_1D0], r9d
0x180035ed1  mov     r14, r8
0x180035ed4  mov     [rsp+230h+Str], r8
0x180035ed9  mov     [rsp+230h+pswzServerName], rdx
0x180035ede  mov     rdi, rcx
0x180035ee1  mov     r12, [rbp+130h+arg_28]
0x180035ee8  mov     r13, [rbp+130h+arg_30]
0x180035eef  movzx   esi, [rbp+130h+arg_38]
0x180035ef6  mov     [rsp+230h+var_1EC], si
0x180035efb  mov     rax, [rbp+130h+arg_48]
0x180035f02  mov     [rbp+130h+lpszHeaders], rax
0x180035f06  xorps   xmm0, xmm0
0x180035f09  movups  [rbp+130h+var_160], xmm0
0x180035f0d  movups  [rbp+130h+var_150], xmm0
0x180035f11  lea     rax, [rbp+130h+var_170]
0x180035f15  mov     [rbp+130h+var_180], rax
0x180035f19  lea     rax, [rbp+130h+var_170]
0x180035f1d  mov     [rbp+130h+var_178], rax
0x180035f21  xor     ebx, ebx
0x180035f23  mov     [rbp+130h+var_170], bx
0x180035f27  lea     rax, [rbp+130h+var_190]
0x180035f2b  mov     [rbp+130h+var_1A0], rax
0x180035f2f  lea     rax, [rbp+130h+var_190]
0x180035f33  mov     [rbp+130h+var_198], rax
0x180035f37  mov     [rbp+130h+var_190], bx
0x180035f3b  mov     [rsp+230h+var_1C0], ebx
0x180035f3f  mov     [rbp+130h+Buffer], rcx
0x180035f43  mov     [rsp+230h+var_1F0], ebx
0x180035f47  xor     edx, edx; Val
0x180035f49  mov     r8d, 0E8h; Size
0x180035f4f  lea     rcx, [rbp+130h+var_140]; void *
0x180035f53  call    memset_0
0x180035f58  cmp     [rdi+10h], rbx
0x180035f5c  jz      short loc_180035F68
0x180035f5e  mov     ebx, 8000000Ah
0x180035f63  jmp     loc_180036C1E
0x180035f68  mov     ebx, 80004005h
0x180035f6d  mov     eax, r15d
0x180035f70  or      r15d, 1
0x180035f74  test    al, 10h
0x180035f76  cmovz   r15d, [rsp+230h+var_1D0]
0x180035f7c  mov     dword ptr [rdi+338h], 0FFFFFFFFh
0x180035f86  mov     rax, cs:WPP_GLOBAL_Control
0x180035f8d  test    byte ptr [rax+1Ch], 4
0x180035f91  jz      loc_18003602B
0x180035f97  mov     edx, 3Fh ; '?'; Ch
0x180035f9c  mov     rcx, r14; Str
0x180035f9f  call    cs:__imp_wcschr
0x180035fa6  nop     dword ptr [rax+rax+00h]
0x180035fab  test    rax, rax
0x180035fae  jz      short loc_180035FF3
0x180035fb0  mov     [rsp+230h+var_1E0], r14
0x180035fb5  sub     rax, r14
0x180035fb8  sar     rax, 1
0x180035fbb  mov     [rsp+230h+var_1D8], rax
0x180035fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fc7  lea     rax, WPP_GLOBAL_Control
0x180035fce  cmp     rcx, rax
0x180035fd1  jz      short loc_18003602B
0x180035fd3  test    byte ptr [rcx+1Ch], 4
0x180035fd7  jz      short loc_18003602B
0x180035fd9  lea     rax, [rsp+230h+var_1E0]
0x180035fde  mov     qword ptr [rsp+230h+dwFlags], rax
0x180035fe3  mov     r9, [rsp+230h+pswzServerName]
0x180035fe8  mov     rcx, [rcx+10h]
0x180035fec  call    WPP_SF_S_utlwsv_
0x180035ff1  jmp     short loc_18003602B
0x180035ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ffa  lea     rax, WPP_GLOBAL_Control
0x180036001  cmp     rcx, rax
0x180036004  jz      short loc_18003602B
0x180036006  test    byte ptr [rcx+1Ch], 4
0x18003600a  jz      short loc_18003602B
0x18003600c  mov     edx, 31h ; '1'
0x180036011  mov     qword ptr [rsp+230h+dwFlags], r14
0x180036016  mov     r9, [rsp+230h+pswzServerName]
0x18003601b  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180036022  mov     rcx, [rcx+10h]
0x180036026  call    WPP_SF_SS
0x18003602b  lea     rcx, [rdi+70h]; lpCriticalSection
0x18003602f  mov     [rsp+230h+var_1E0], rcx
0x180036034  call    cs:__imp_EnterCriticalSection
0x18003603b  nop     dword ptr [rax+rax+00h]
0x180036040  mov     byte ptr [rsp+230h+var_1D8], 1
0x180036045  cmp     qword ptr [rdi], 0
0x180036049  jnz     loc_180036416
0x18003604f  mov     esi, [rsp+230h+var_1D0]
0x180036053  and     esi, 100h
0x180036059  mov     eax, esi
0x18003605b  neg     eax
0x18003605d  sbb     edx, edx
0x18003605f  and     edx, 3
0x180036062  inc     edx; dwAccessType
0x180036064  mov     [rsp+230h+dwFlags], 10000000h; dwFlags
0x18003606c  xor     r9d, r9d; pszProxyBypassW
0x18003606f  xor     r8d, r8d; pszProxyW
0x180036072  lea     rcx, pszAgentW; "MSDW"
0x180036079  call    cs:__imp_WinHttpOpen
0x180036080  nop     dword ptr [rax+rax+00h]
0x180036085  mov     rcx, [rdi]; hInternet
0x180036088  mov     [rdi], rax
0x18003608b  test    rcx, rcx
0x18003608e  jz      short loc_18003609C
0x180036090  call    cs:__imp_WinHttpCloseHandle
0x180036097  nop     dword ptr [rax+rax+00h]
0x18003609c  cmp     qword ptr [rdi], 0
0x1800360a0  jnz     loc_180036132
0x1800360a6  test    esi, esi
0x1800360a8  jz      loc_180036132
0x1800360ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800360b5  lea     rcx, WPP_GLOBAL_Control
0x1800360bc  cmp     rax, rcx
0x1800360bf  jz      short loc_1800360F2
0x1800360c1  test    byte ptr [rax+1Ch], 2
0x1800360c5  jz      short loc_1800360F2
0x1800360c7  call    cs:__imp_GetLastError
0x1800360ce  nop     dword ptr [rax+rax+00h]
0x1800360d3  mov     edx, 32h ; '2'
0x1800360d8  mov     r9d, eax
0x1800360db  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x1800360e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360e9  mov     rcx, [rcx+10h]
0x1800360ed  call    WPP_SF_d
0x1800360f2  mov     [rsp+230h+dwFlags], 10000000h; dwFlags
0x1800360fa  xor     r9d, r9d; pszProxyBypassW
0x1800360fd  xor     r8d, r8d; pszProxyW
0x180036100  lea     edx, [r9+1]; dwAccessType
0x180036104  lea     rcx, pszAgentW; "MSDW"
0x18003610b  call    cs:__imp_WinHttpOpen
0x180036112  nop     dword ptr [rax+rax+00h]
0x180036117  mov     rcx, [rdi]; hInternet
0x18003611a  mov     [rdi], rax
0x18003611d  xor     esi, esi
0x18003611f  test    rcx, rcx
0x180036122  jz      short loc_180036134
0x180036124  call    cs:__imp_WinHttpCloseHandle
0x18003612b  nop     dword ptr [rax+rax+00h]
0x180036130  jmp     short loc_180036134
0x180036132  xor     esi, esi
0x180036134  mov     rcx, [rdi]; hInternet
0x180036137  test    rcx, rcx
0x18003613a  jnz     short loc_180036191
0x18003613c  call    cs:__imp_GetLastError
0x180036143  nop     dword ptr [rax+rax+00h]
0x180036148  mov     ecx, eax; unsigned int
0x18003614a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003614f  mov     ebx, eax
0x180036151  mov     rcx, cs:WPP_GLOBAL_Control
0x180036158  lea     rax, WPP_GLOBAL_Control
0x18003615f  cmp     rcx, rax
0x180036162  jz      short loc_180036182
0x180036164  test    byte ptr [rcx+1Ch], 1
0x180036168  jz      short loc_180036182
0x18003616a  mov     edx, 33h ; '3'
0x18003616f  mov     r9d, ebx
0x180036172  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180036179  mov     rcx, [rcx+10h]
0x18003617d  call    WPP_SF_d
0x180036182  lea     rcx, [rsp+230h+var_1E0]
0x180036187  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x18003618c  jmp     loc_180036C1E
0x180036191  mov     eax, [rdi+108h]
0x180036197  mov     [rsp+230h+dwFlags], eax; nReceiveTimeout
0x18003619b  mov     r9d, [rdi+104h]; nSendTimeout
0x1800361a2  mov     r8d, [rdi+100h]; nConnectTimeout
0x1800361a9  mov     edx, [rdi+0FCh]; nResolveTimeout
0x1800361af  call    cs:__imp_WinHttpSetTimeouts
0x1800361b6  nop     dword ptr [rax+rax+00h]
0x1800361bb  test    eax, eax
0x1800361bd  jnz     short loc_1800361F7
0x1800361bf  call    cs:__imp_GetLastError
0x1800361c6  nop     dword ptr [rax+rax+00h]
0x1800361cb  mov     ecx, eax; unsigned int
0x1800361cd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800361d2  mov     ebx, eax
0x1800361d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361db  lea     rax, WPP_GLOBAL_Control
0x1800361e2  cmp     rcx, rax
0x1800361e5  jz      short loc_180036182
0x1800361e7  test    byte ptr [rcx+1Ch], 1
0x1800361eb  jz      short loc_180036182
0x1800361ed  mov     edx, 34h ; '4'
0x1800361f2  jmp     loc_18003616F
0x1800361f7  mov     r9d, 8; dwBufferLength
0x1800361fd  lea     r8, [rbp+130h+Buffer]; lpBuffer
0x180036201  lea     edx, [r9+25h]; dwOption
0x180036205  mov     rcx, [rdi]; hInternet
0x180036208  call    cs:__imp_WinHttpSetOption
0x18003620f  nop     dword ptr [rax+rax+00h]
0x180036214  test    eax, eax
0x180036216  jnz     short loc_180036258
0x180036218  call    cs:__imp_GetLastError
0x18003621f  nop     dword ptr [rax+rax+00h]
0x180036224  mov     ecx, eax; unsigned int
0x180036226  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003622b  mov     ebx, eax
0x18003622d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036234  lea     rax, WPP_GLOBAL_Control
0x18003623b  cmp     rcx, rax
0x18003623e  jz      loc_180036182
0x180036244  test    byte ptr [rcx+1Ch], 1
0x180036248  jz      loc_180036182
0x18003624e  mov     edx, 35h ; '5'
0x180036253  jmp     loc_18003616F
0x180036258  mov     [rsp+230h+var_1F0], 1
0x180036260  mov     r9d, 4; dwBufferLength
0x180036266  lea     r8, [rsp+230h+var_1F0]; lpBuffer
0x18003626b  lea     edx, [r9+54h]; dwOption
0x18003626f  mov     rcx, [rdi]; hInternet
0x180036272  call    cs:__imp_WinHttpSetOption
0x180036279  nop     dword ptr [rax+rax+00h]
0x18003627e  test    eax, eax
0x180036280  jnz     short loc_1800362C2
0x180036282  call    cs:__imp_GetLastError
0x180036289  nop     dword ptr [rax+rax+00h]
0x18003628e  mov     ecx, eax; unsigned int
0x180036290  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180036295  mov     ebx, eax
0x180036297  mov     rcx, cs:WPP_GLOBAL_Control
0x18003629e  lea     rax, WPP_GLOBAL_Control
0x1800362a5  cmp     rcx, rax
0x1800362a8  jz      loc_180036182
0x1800362ae  test    byte ptr [rcx+1Ch], 1
0x1800362b2  jz      loc_180036182
0x1800362b8  mov     edx, 36h ; '6'
0x1800362bd  jmp     loc_18003616F
0x1800362c2  mov     [rsp+230h+var_1F0], 800h
0x1800362ca  mov     r9d, 4; dwBufferLength
0x1800362d0  lea     r8, [rsp+230h+var_1F0]; lpBuffer
0x1800362d5  lea     edx, [r9+50h]; dwOption
0x1800362d9  mov     rcx, [rdi]; hInternet
0x1800362dc  call    cs:__imp_WinHttpSetOption
0x1800362e3  nop     dword ptr [rax+rax+00h]
0x1800362e8  test    eax, eax
0x1800362ea  jnz     short loc_18003632C
0x1800362ec  call    cs:__imp_GetLastError
0x1800362f3  nop     dword ptr [rax+rax+00h]
0x1800362f8  mov     ecx, eax; unsigned int
0x1800362fa  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800362ff  mov     ebx, eax
0x180036301  mov     rcx, cs:WPP_GLOBAL_Control
0x180036308  lea     rax, WPP_GLOBAL_Control
0x18003630f  cmp     rcx, rax
0x180036312  jz      loc_180036182
0x180036318  test    byte ptr [rcx+1Ch], 1
0x18003631c  jz      loc_180036182
0x180036322  mov     edx, 37h ; '7'
0x180036327  jmp     loc_18003616F
0x18003632c  cmp     [rdi+364h], sil
0x180036333  jz      short loc_1800363A1
0x180036335  mov     dword ptr [rsp+230h+var_1E8], esi
0x180036339  mov     r9d, 4; dwBufferLength
0x18003633f  lea     r8, [rsp+230h+var_1E8]; lpBuffer
0x180036344  lea     edx, [r9+7Ch]; dwOption
0x180036348  mov     rcx, [rdi]; hInternet
0x18003634b  call    cs:__imp_WinHttpSetOption
0x180036352  nop     dword ptr [rax+rax+00h]
0x180036357  test    eax, eax
0x180036359  jnz     short loc_1800363A1
0x18003635b  call    cs:__imp_GetLastError
0x180036362  nop     dword ptr [rax+rax+00h]
0x180036367  mov     ecx, eax; unsigned int
0x180036369  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003636e  mov     ebx, eax
0x180036370  mov     rcx, cs:WPP_GLOBAL_Control
0x180036377  lea     rax, WPP_GLOBAL_Control
0x18003637e  cmp     rcx, rax
0x180036381  jz      short loc_1800363A1
0x180036383  test    byte ptr [rcx+1Ch], 2
0x180036387  jz      short loc_1800363A1
0x180036389  mov     edx, 38h ; '8'
0x18003638e  mov     r9d, ebx
0x180036391  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180036398  mov     rcx, [rcx+10h]
0x18003639c  call    WPP_SF_d
0x1800363a1  cmp     [rdi+40h], esi
0x1800363a4  jz      short loc_180036411
0x1800363a6  mov     rax, [rdi+30h]
0x1800363aa  mov     [rsp+230h+var_1E8], rax
0x1800363af  mov     r9d, 8; dwBufferLength
0x1800363b5  lea     r8, [rsp+230h+var_1E8]; lpBuffer
0x1800363ba  lea     edx, [r9+5Bh]; dwOption
0x1800363be  mov     rcx, [rdi]; hInternet
0x1800363c1  call    cs:__imp_WinHttpSetOption
0x1800363c8  nop     dword ptr [rax+rax+00h]
0x1800363cd  test    eax, eax
  ... truncated ...
```
