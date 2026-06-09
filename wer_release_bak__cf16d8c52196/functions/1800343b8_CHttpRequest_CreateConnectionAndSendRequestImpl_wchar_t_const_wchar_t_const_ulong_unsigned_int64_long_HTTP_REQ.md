# CHttpRequest::CreateConnectionAndSendRequestImpl(wchar_t const *,wchar_t const *,ulong,unsigned __int64,long (*)(_HTTP_REQUEST_CALLBACK *),void *,ushort,unsigned __int64,wchar_t const *)

- ea: `0x1800343b8`
- end: `0x18003504d`
- name: `?CreateConnectionAndSendRequestImpl@CHttpRequest@@IEAAJPEB_W0K_KP6AJPEAU_HTTP_REQUEST_CALLBACK@@@ZPEAXG10@Z`
- size: `3221`
- prototype: `__int64 __usercall@<rax>(CHttpRequest *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, unsigned __int64, int (*)(struct _HTTP_REQUEST_CALLBACK *), void *, unsigned __int16, unsigned __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009a644`

## callees

- `0x180004bb4`
- `0x180006f54`
- `0x18000716c`
- `0x18000dad0`
- `0x180015520`
- `0x180016468`
- `0x180019904`
- `0x18001fe24`
- `0x180029380`
- `0x18002d338`
- `0x1800343b8`
- `0x18003bf14`
- `0x180050db0`
- `0x1800517cc`
- `0x18009ad98`
- `0x18009b68c`
- `0x18009b750`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034a1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034fa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034a1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003469d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003469d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dca`
- `ntdll!wcschr` at `0x1800344bb`
- `ntdll!wcschr` at `0x180034eb6`
- `ntdll!wcschr` at `0x1800344bb`
- `ntdll!wcschr` at `0x180034eb6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800348bd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800348c7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800348bd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800348c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003454a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034da1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003454a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034da1`
- `WINHTTP!WinHttpSetOption` at `0x1800346dd`
- `WINHTTP!WinHttpSetOption` at `0x18003473b`
- `WINHTTP!WinHttpSetOption` at `0x180034799`
- `WINHTTP!WinHttpSetOption` at `0x1800347fc`
- `WINHTTP!WinHttpSetOption` at `0x180034866`
- `WINHTTP!WinHttpSetOption` at `0x1800349e0`
- `WINHTTP!WinHttpSetOption` at `0x180034b10`
- `WINHTTP!WinHttpSetOption` at `0x180034b76`
- `WINHTTP!WinHttpSetOption` at `0x180034c1d`
- `WINHTTP!WinHttpSetOption` at `0x180034c7a`
- `WINHTTP!WinHttpSetOption` at `0x180034ce4`
- `WINHTTP!WinHttpSetOption` at `0x1800346dd`
- `WINHTTP!WinHttpSetOption` at `0x18003473b`
- `WINHTTP!WinHttpSetOption` at `0x180034799`
- `WINHTTP!WinHttpSetOption` at `0x1800347fc`
- `WINHTTP!WinHttpSetOption` at `0x180034866`
- `WINHTTP!WinHttpSetOption` at `0x1800349e0`
- `WINHTTP!WinHttpSetOption` at `0x180034b10`
- `WINHTTP!WinHttpSetOption` at `0x180034b76`
- `WINHTTP!WinHttpSetOption` at `0x180034c1d`
- `WINHTTP!WinHttpSetOption` at `0x180034c7a`
- `WINHTTP!WinHttpSetOption` at `0x180034ce4`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180034d47`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180034d47`
- `WINHTTP!WinHttpOpen` at `0x180034589`
- `WINHTTP!WinHttpOpen` at `0x180034601`
- `WINHTTP!WinHttpOpen` at `0x180034589`
- `WINHTTP!WinHttpOpen` at `0x180034601`
- `WINHTTP!WinHttpSetTimeouts` at `0x180034693`
- `WINHTTP!WinHttpSetTimeouts` at `0x180034693`
- `WINHTTP!WinHttpConnect` at `0x180034950`
- `WINHTTP!WinHttpConnect` at `0x180034950`
- `WINHTTP!WinHttpOpenRequest` at `0x180034a85`
- `WINHTTP!WinHttpOpenRequest` at `0x180034a85`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180034dc1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180034dc1`
- `WINHTTP!WinHttpCloseHandle` at `0x18003459a`
- `WINHTTP!WinHttpCloseHandle` at `0x180034614`
- `WINHTTP!WinHttpCloseHandle` at `0x180034963`
- `WINHTTP!WinHttpCloseHandle` at `0x180034a98`
- `WINHTTP!WinHttpCloseHandle` at `0x18003459a`
- `WINHTTP!WinHttpCloseHandle` at `0x180034614`
- `WINHTTP!WinHttpCloseHandle` at `0x180034963`
- `WINHTTP!WinHttpCloseHandle` at `0x180034a98`

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
  const WCHAR *v42; // rsi
  HINTERNET v43; // rax
  void *v44; // rcx
  DWORD v45; // eax
  DWORD v46; // eax
  DWORD v47; // eax
  DWORD v48; // eax
  DWORD v49; // eax
  unsigned int v50; // eax
  DWORD v51; // eax
  DWORD v52; // eax
  unsigned int v53; // ebx
  WINHTTP_STATUS_CALLBACK v54; // rbx
  DWORD v55; // r14d
  wchar_t *v56; // r14
  int v57; // r12d
  wchar_t *v58; // rax
  int v59; // edx
  int v60; // r8d
  int v61; // eax
  unsigned int v62; // eax
  unsigned __int64 v64; // [rsp+30h] [rbp-D0h]
  int v65; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v66; // [rsp+44h] [rbp-BCh]
  __int64 v67; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v68; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h]
  unsigned int v70; // [rsp+60h] [rbp-A0h]
  LPCWSTR pswzServerName; // [rsp+68h] [rbp-98h]
  unsigned int v72; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *Str; // [rsp+78h] [rbp-88h]
  CHttpRequest *Buffer; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpszHeaders; // [rsp+88h] [rbp-78h]
  wchar_t *v76[2]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v77[8]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v78[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v79[8]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v80[2]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v81[7]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+114h] [rbp+14h]

  v70 = a4;
  Str = a3;
  pswzServerName = a2;
  v13 = a8;
  v66 = a8;
  lpszHeaders = a10;
  memset(v80, 0, sizeof(v80));
  v78[0] = v79;
  v78[1] = v79;
  v79[0] = 0;
  v76[0] = v77;
  v76[1] = v77;
  v77[0] = 0;
  v72 = 0;
  Buffer = this;
  v65 = 0;
  memset_0(v81, 0, 0xE8u);
  if ( *((_QWORD *)this + 2) )
  {
    ProxyInfoForUrl = -2147483638;
    goto LABEL_155;
  }
  ProxyInfoForUrl = -2147467259;
  v15 = a4;
  v16 = a4 | 1;
  if ( (v15 & 0x10) == 0 )
    v16 = v70;
  *((_DWORD *)this + 206) = -1;
  if ( (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v17 = wcschr(a3, 0x3Fu);
    if ( v17 )
    {
      v68 = a3;
      v69 = v17 - a3;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_S_utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)pswzServerName, (__int64)&v68);
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
  v68 = (wchar_t *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  LOBYTE(v69) = 1;
  if ( !*(_QWORD *)this )
  {
    v20 = v70 & 0x100;
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
      utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v68);
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
    v65 = 1;
    if ( !WinHttpSetOption(*(HINTERNET *)this, 0x58u, &v65, 4u) )
    {
      v31 = GetLastError();
      ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v31);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v28 = 54;
      goto LABEL_27;
    }
    v65 = 2048;
    if ( !WinHttpSetOption(*(HINTERNET *)this, 0x54u, &v65, 4u) )
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
      LODWORD(v67) = 0;
      if ( !WinHttpSetOption(*(HINTERNET *)this, 0x80u, &v67, 4u) )
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
      v67 = *((_QWORD *)this + 6);
      if ( !WinHttpSetOption(*(HINTERNET *)this, 0x63u, &v67, 8u) )
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
    v13 = v66;
  }
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v68);
  ResetEvent(*((HANDLE *)this + 4));
  ResetEvent(*((HANDLE *)this + 6));
  *((_QWORD *)this + 109) = 0;
  *((_DWORD *)this + 59) = 0;
  if ( a6
    && (LODWORD(v80[0]) = 0,
        *((_QWORD *)&v80[0] + 1) = a7,
        ProxyInfoForUrl = ((__int64 (__fastcall *)(_OWORD *))a6)(v80),
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
      v81[0] = 65538;
      if ( (v16 & 0x80u) != 0 )
      {
        v83 = 1;
        v82 = 4;
        v81[5] = 1;
        v81[6] = 1;
        if ( !WinHttpSetOption(v38, 0x83u, v81, 0xE8u)
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
      LODWORD(v67) = GetTickCount();
      if ( (v16 & 2) != 0 )
      {
        v42 = L"GET";
      }
      else if ( (v16 & 4) != 0 )
      {
        v42 = L"PUT";
      }
      else if ( (v16 & 8) != 0 )
      {
        v42 = L"POST";
      }
      else
      {
        v42 = 0;
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v43 = WinHttpOpenRequest(*((HINTERNET *)this + 1), v42, a3, 0, 0, 0, (unsigned __int8)(v16 & 1) << 23);
      v44 = (void *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = v43;
      if ( v44 )
        WinHttpCloseHandle(v44);
      if ( *((_QWORD *)this + 2) )
      {
        *((_DWORD *)this + 59) = CTimer::Stop((CTimer *)&v67);
        if ( (v16 & 0x10) == 0 || (v65 = 1, WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Du, &v65, 4u)) )
        {
          if ( (v16 & 0x100) == 0 || (v65 = 0, WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Du, &v65, 4u)) )
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
                v65 = 1;
                if ( !WinHttpSetOption(*((HINTERNET *)this + 2), 0x4Fu, &v65, 4u) )
                {
                  v48 = GetLastError();
                  ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v48);
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v36 = 65;
                    goto LABEL_61;
                  }
                  goto LABEL_155;
                }
                LODWORD(v67) = 1;
                if ( !WinHttpSetOption(*((HINTERNET *)this + 2), 0x9Bu, &v67, 4u) )
                {
                  v49 = GetLastError();
                  v50 = ERROR_HR_FROM_WIN32(v49);
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      66,
                      WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                      v50);
                }
              }
            }
            if ( (v16 & 0x200) == 0 || (v65 = 3, WinHttpSetOption(*((HINTERNET *)this + 2), 0x76u, &v65, 4u)) )
            {
              if ( lpszHeaders
                && *lpszHeaders
                && !WinHttpAddRequestHeaders(*((HINTERNET *)this + 2), lpszHeaders, 0xFFFFFFFF, 0x20000000u) )
              {
                v52 = GetLastError();
                ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v52);
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v36 = 68;
                  goto LABEL_61;
                }
              }
              else
              {
                v53 = *((_DWORD *)this + 16) != 0 ? 0xFFFFF400 : 0;
                v68 = (wchar_t *)((char *)this + 72);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
                LOBYTE(v69) = 1;
                v54 = WinHttpSetStatusCallback(
                        *((HINTERNET *)this + 2),
                        CHttpRequest::Stub_WinHttpCompletionCallback,
                        v53 + 159321088,
                        0);
                v55 = GetLastError();
                utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v68);
                if ( v54 != (WINHTTP_STATUS_CALLBACK)-1LL )
                {
                  *((_DWORD *)this + 58) = 0;
                  v56 = Str;
                  if ( (v16 & 0x20) != 0 )
                  {
                    v57 = (int)pswzServerName;
                  }
                  else
                  {
                    v57 = (int)pswzServerName;
                    if ( (v16 & 0x100) == 0 )
                    {
                      ProxyInfoForUrl = CHttpRequest::GetProxyInfoForUrl(
                                          (_DWORD)this,
                                          (_DWORD)pswzServerName,
                                          (_DWORD)Str,
                                          v16 & 1,
                                          (__int64)v78,
                                          (__int64)v76,
                                          (__int64)&v72);
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
                    v58 = wcschr(v56, 0x3Fu);
                    if ( v58 )
                    {
                      v68 = v56;
                      v69 = v58 - v56;
                      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                        WPP_SF_S_utlwsv_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v59,
                          v60,
                          v57,
                          (__int64)&v68,
                          (__int64)v42);
                    }
                    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                    {
                      WPP_SF_SSS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        72,
                        (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                        v57,
                        (__int64)v56,
                        (__int64)v42);
                    }
                  }
                  v61 = CHttpRequest::SendRequestWithRetry(this, v78[0], v76[0], v72, a5, v16, v64);
                  ProxyInfoForUrl = v61;
                  if ( v61 >= 0 )
                  {
                    if ( (v70 & 0x40) == 0 )
                      goto LABEL_154;
                    LODWORD(v67) = GetTickCount();
                    ProxyInfoForUrl = CHttpRequest::CheckCertForMicrosoftRoot(*((void **)this + 2));
                    v62 = CTimer::Stop((CTimer *)&v67);
                    *((_DWORD *)this + 206) = v62;
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        74,
                        WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
                        v62);
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
                      v37 = (unsigned int)v61;
                      goto LABEL_62;
                    }
                  }
                  goto LABEL_155;
                }
                ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v55);
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
              v51 = GetLastError();
              ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v51);
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
            v47 = GetLastError();
            ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v47);
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
          v46 = GetLastError();
          ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v46);
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
        v45 = GetLastError();
        ProxyInfoForUrl = ERROR_HR_FROM_WIN32(v45);
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
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v76);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v78);
  return (unsigned int)ProxyInfoForUrl;
}

```

## disassembly

```asm
0x1800343b8  push    rbp
0x1800343ba  push    rbx
0x1800343bb  push    rsi
0x1800343bc  push    rdi
0x1800343bd  push    r12
0x1800343bf  push    r13
0x1800343c1  push    r14
0x1800343c3  push    r15
0x1800343c5  lea     rbp, [rsp-0F8h]
0x1800343cd  sub     rsp, 1F8h
0x1800343d4  mov     rax, cs:__security_cookie
0x1800343db  xor     rax, rsp
0x1800343de  mov     [rbp+130h+var_50], rax
0x1800343e5  mov     r15d, r9d
0x1800343e8  mov     [rsp+230h+var_1D0], r9d
0x1800343ed  mov     r14, r8
0x1800343f0  mov     [rsp+230h+Str], r8
0x1800343f5  mov     [rsp+230h+pswzServerName], rdx
0x1800343fa  mov     rdi, rcx
0x1800343fd  mov     r12, [rbp+130h+arg_28]
0x180034404  mov     r13, [rbp+130h+arg_30]
0x18003440b  movzx   esi, [rbp+130h+arg_38]
0x180034412  mov     [rsp+230h+var_1EC], si
0x180034417  mov     rax, [rbp+130h+arg_48]
0x18003441e  mov     [rbp+130h+lpszHeaders], rax
0x180034422  xorps   xmm0, xmm0
0x180034425  movups  [rbp+130h+var_160], xmm0
0x180034429  movups  [rbp+130h+var_150], xmm0
0x18003442d  lea     rax, [rbp+130h+var_170]
0x180034431  mov     [rbp+130h+var_180], rax
0x180034435  lea     rax, [rbp+130h+var_170]
0x180034439  mov     [rbp+130h+var_178], rax
0x18003443d  xor     ebx, ebx
0x18003443f  mov     [rbp+130h+var_170], bx
0x180034443  lea     rax, [rbp+130h+var_190]
0x180034447  mov     [rbp+130h+var_1A0], rax
0x18003444b  lea     rax, [rbp+130h+var_190]
0x18003444f  mov     [rbp+130h+var_198], rax
0x180034453  mov     [rbp+130h+var_190], bx
0x180034457  mov     [rsp+230h+var_1C0], ebx
0x18003445b  mov     [rbp+130h+Buffer], rcx
0x18003445f  mov     [rsp+230h+var_1F0], ebx
0x180034463  xor     edx, edx; Val
0x180034465  mov     r8d, 0E8h; Size
0x18003446b  lea     rcx, [rbp+130h+var_140]; void *
0x18003446f  call    memset_0
0x180034474  cmp     [rdi+10h], rbx
0x180034478  jz      short loc_180034484
0x18003447a  mov     ebx, 8000000Ah
0x18003447f  jmp     loc_180035015
0x180034484  mov     ebx, 80004005h
0x180034489  mov     eax, r15d
0x18003448c  or      r15d, 1
0x180034490  test    al, 10h
0x180034492  cmovz   r15d, [rsp+230h+var_1D0]
0x180034498  mov     dword ptr [rdi+338h], 0FFFFFFFFh
0x1800344a2  mov     rax, cs:WPP_GLOBAL_Control
0x1800344a9  test    byte ptr [rax+1Ch], 4
0x1800344ad  jz      loc_180034541
0x1800344b3  mov     edx, 3Fh ; '?'; Ch
0x1800344b8  mov     rcx, r14; Str
0x1800344bb  call    cs:__imp_wcschr
0x1800344c1  test    rax, rax
0x1800344c4  jz      short loc_180034509
0x1800344c6  mov     [rsp+230h+var_1E0], r14
0x1800344cb  sub     rax, r14
0x1800344ce  sar     rax, 1
0x1800344d1  mov     [rsp+230h+var_1D8], rax
0x1800344d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344dd  lea     rax, WPP_GLOBAL_Control
0x1800344e4  cmp     rcx, rax
0x1800344e7  jz      short loc_180034541
0x1800344e9  test    byte ptr [rcx+1Ch], 4
0x1800344ed  jz      short loc_180034541
0x1800344ef  lea     rax, [rsp+230h+var_1E0]
0x1800344f4  mov     qword ptr [rsp+230h+dwFlags], rax
0x1800344f9  mov     r9, [rsp+230h+pswzServerName]
0x1800344fe  mov     rcx, [rcx+10h]
0x180034502  call    WPP_SF_S_utlwsv_
0x180034507  jmp     short loc_180034541
0x180034509  mov     rcx, cs:WPP_GLOBAL_Control
0x180034510  lea     rax, WPP_GLOBAL_Control
0x180034517  cmp     rcx, rax
0x18003451a  jz      short loc_180034541
0x18003451c  test    byte ptr [rcx+1Ch], 4
0x180034520  jz      short loc_180034541
0x180034522  mov     edx, 31h ; '1'
0x180034527  mov     qword ptr [rsp+230h+dwFlags], r14
0x18003452c  mov     r9, [rsp+230h+pswzServerName]
0x180034531  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180034538  mov     rcx, [rcx+10h]
0x18003453c  call    WPP_SF_SS
0x180034541  lea     rcx, [rdi+70h]; lpCriticalSection
0x180034545  mov     [rsp+230h+var_1E0], rcx
0x18003454a  call    cs:__imp_EnterCriticalSection
0x180034550  mov     byte ptr [rsp+230h+var_1D8], 1
0x180034555  cmp     qword ptr [rdi], 0
0x180034559  jnz     loc_1800348AF
0x18003455f  mov     esi, [rsp+230h+var_1D0]
0x180034563  and     esi, 100h
0x180034569  mov     eax, esi
0x18003456b  neg     eax
0x18003456d  sbb     edx, edx
0x18003456f  and     edx, 3
0x180034572  inc     edx; dwAccessType
0x180034574  mov     [rsp+230h+dwFlags], 10000000h; dwFlags
0x18003457c  xor     r9d, r9d; pszProxyBypassW
0x18003457f  xor     r8d, r8d; pszProxyW
0x180034582  lea     rcx, pszAgentW; "MSDW"
0x180034589  call    cs:__imp_WinHttpOpen
0x18003458f  mov     rcx, [rdi]; hInternet
0x180034592  mov     [rdi], rax
0x180034595  test    rcx, rcx
0x180034598  jz      short loc_1800345A0
0x18003459a  call    cs:__imp_WinHttpCloseHandle
0x1800345a0  cmp     qword ptr [rdi], 0
0x1800345a4  jnz     short loc_18003461C
0x1800345a6  test    esi, esi
0x1800345a8  jz      short loc_18003461C
0x1800345aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800345b1  lea     rcx, WPP_GLOBAL_Control
0x1800345b8  cmp     rax, rcx
0x1800345bb  jz      short loc_1800345E8
0x1800345bd  test    byte ptr [rax+1Ch], 2
0x1800345c1  jz      short loc_1800345E8
0x1800345c3  call    cs:__imp_GetLastError
0x1800345c9  mov     edx, 32h ; '2'
0x1800345ce  mov     r9d, eax
0x1800345d1  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x1800345d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345df  mov     rcx, [rcx+10h]
0x1800345e3  call    WPP_SF_d
0x1800345e8  mov     [rsp+230h+dwFlags], 10000000h; dwFlags
0x1800345f0  xor     r9d, r9d; pszProxyBypassW
0x1800345f3  xor     r8d, r8d; pszProxyW
0x1800345f6  lea     edx, [r9+1]; dwAccessType
0x1800345fa  lea     rcx, pszAgentW; "MSDW"
0x180034601  call    cs:__imp_WinHttpOpen
0x180034607  mov     rcx, [rdi]; hInternet
0x18003460a  mov     [rdi], rax
0x18003460d  xor     esi, esi
0x18003460f  test    rcx, rcx
0x180034612  jz      short loc_18003461E
0x180034614  call    cs:__imp_WinHttpCloseHandle
0x18003461a  jmp     short loc_18003461E
0x18003461c  xor     esi, esi
0x18003461e  mov     rcx, [rdi]; hInternet
0x180034621  test    rcx, rcx
0x180034624  jnz     short loc_180034675
0x180034626  call    cs:__imp_GetLastError
0x18003462c  mov     ecx, eax; unsigned int
0x18003462e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180034633  mov     ebx, eax
0x180034635  mov     rcx, cs:WPP_GLOBAL_Control
0x18003463c  lea     rax, WPP_GLOBAL_Control
0x180034643  cmp     rcx, rax
0x180034646  jz      short loc_180034666
0x180034648  test    byte ptr [rcx+1Ch], 1
0x18003464c  jz      short loc_180034666
0x18003464e  mov     edx, 33h ; '3'
0x180034653  mov     r9d, ebx
0x180034656  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18003465d  mov     rcx, [rcx+10h]
0x180034661  call    WPP_SF_d
0x180034666  lea     rcx, [rsp+230h+var_1E0]
0x18003466b  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180034670  jmp     loc_180035015
0x180034675  mov     eax, [rdi+108h]
0x18003467b  mov     [rsp+230h+dwFlags], eax; nReceiveTimeout
0x18003467f  mov     r9d, [rdi+104h]; nSendTimeout
0x180034686  mov     r8d, [rdi+100h]; nConnectTimeout
0x18003468d  mov     edx, [rdi+0FCh]; nResolveTimeout
0x180034693  call    cs:__imp_WinHttpSetTimeouts
0x180034699  test    eax, eax
0x18003469b  jnz     short loc_1800346CC
0x18003469d  call    cs:__imp_GetLastError
0x1800346a3  mov     ecx, eax; unsigned int
0x1800346a5  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800346aa  mov     ebx, eax
0x1800346ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800346b3  lea     rax, WPP_GLOBAL_Control
0x1800346ba  cmp     rcx, rax
0x1800346bd  jz      short loc_180034666
0x1800346bf  test    byte ptr [rcx+1Ch], 1
0x1800346c3  jz      short loc_180034666
0x1800346c5  mov     edx, 34h ; '4'
0x1800346ca  jmp     short loc_180034653
0x1800346cc  mov     r9d, 8; dwBufferLength
0x1800346d2  lea     r8, [rbp+130h+Buffer]; lpBuffer
0x1800346d6  lea     edx, [r9+25h]; dwOption
0x1800346da  mov     rcx, [rdi]; hInternet
0x1800346dd  call    cs:__imp_WinHttpSetOption
0x1800346e3  test    eax, eax
0x1800346e5  jnz     short loc_180034721
0x1800346e7  call    cs:__imp_GetLastError
0x1800346ed  mov     ecx, eax; unsigned int
0x1800346ef  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800346f4  mov     ebx, eax
0x1800346f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800346fd  lea     rax, WPP_GLOBAL_Control
0x180034704  cmp     rcx, rax
0x180034707  jz      loc_180034666
0x18003470d  test    byte ptr [rcx+1Ch], 1
0x180034711  jz      loc_180034666
0x180034717  mov     edx, 35h ; '5'
0x18003471c  jmp     loc_180034653
0x180034721  mov     [rsp+230h+var_1F0], 1
0x180034729  mov     r9d, 4; dwBufferLength
0x18003472f  lea     r8, [rsp+230h+var_1F0]; lpBuffer
0x180034734  lea     edx, [r9+54h]; dwOption
0x180034738  mov     rcx, [rdi]; hInternet
0x18003473b  call    cs:__imp_WinHttpSetOption
0x180034741  test    eax, eax
0x180034743  jnz     short loc_18003477F
0x180034745  call    cs:__imp_GetLastError
0x18003474b  mov     ecx, eax; unsigned int
0x18003474d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180034752  mov     ebx, eax
0x180034754  mov     rcx, cs:WPP_GLOBAL_Control
0x18003475b  lea     rax, WPP_GLOBAL_Control
0x180034762  cmp     rcx, rax
0x180034765  jz      loc_180034666
0x18003476b  test    byte ptr [rcx+1Ch], 1
0x18003476f  jz      loc_180034666
0x180034775  mov     edx, 36h ; '6'
0x18003477a  jmp     loc_180034653
0x18003477f  mov     [rsp+230h+var_1F0], 800h
0x180034787  mov     r9d, 4; dwBufferLength
0x18003478d  lea     r8, [rsp+230h+var_1F0]; lpBuffer
0x180034792  lea     edx, [r9+50h]; dwOption
0x180034796  mov     rcx, [rdi]; hInternet
0x180034799  call    cs:__imp_WinHttpSetOption
0x18003479f  test    eax, eax
0x1800347a1  jnz     short loc_1800347DD
0x1800347a3  call    cs:__imp_GetLastError
0x1800347a9  mov     ecx, eax; unsigned int
0x1800347ab  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800347b0  mov     ebx, eax
0x1800347b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347b9  lea     rax, WPP_GLOBAL_Control
0x1800347c0  cmp     rcx, rax
0x1800347c3  jz      loc_180034666
0x1800347c9  test    byte ptr [rcx+1Ch], 1
0x1800347cd  jz      loc_180034666
0x1800347d3  mov     edx, 37h ; '7'
0x1800347d8  jmp     loc_180034653
0x1800347dd  cmp     [rdi+364h], sil
0x1800347e4  jz      short loc_180034846
0x1800347e6  mov     dword ptr [rsp+230h+var_1E8], esi
0x1800347ea  mov     r9d, 4; dwBufferLength
0x1800347f0  lea     r8, [rsp+230h+var_1E8]; lpBuffer
0x1800347f5  lea     edx, [r9+7Ch]; dwOption
0x1800347f9  mov     rcx, [rdi]; hInternet
0x1800347fc  call    cs:__imp_WinHttpSetOption
0x180034802  test    eax, eax
0x180034804  jnz     short loc_180034846
0x180034806  call    cs:__imp_GetLastError
0x18003480c  mov     ecx, eax; unsigned int
0x18003480e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180034813  mov     ebx, eax
0x180034815  mov     rcx, cs:WPP_GLOBAL_Control
0x18003481c  lea     rax, WPP_GLOBAL_Control
0x180034823  cmp     rcx, rax
0x180034826  jz      short loc_180034846
0x180034828  test    byte ptr [rcx+1Ch], 2
0x18003482c  jz      short loc_180034846
0x18003482e  mov     edx, 38h ; '8'
0x180034833  mov     r9d, ebx
0x180034836  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18003483d  mov     rcx, [rcx+10h]
0x180034841  call    WPP_SF_d
0x180034846  cmp     [rdi+40h], esi
0x180034849  jz      short loc_1800348AA
0x18003484b  mov     rax, [rdi+30h]
0x18003484f  mov     [rsp+230h+var_1E8], rax
0x180034854  mov     r9d, 8; dwBufferLength
0x18003485a  lea     r8, [rsp+230h+var_1E8]; lpBuffer
0x18003485f  lea     edx, [r9+5Bh]; dwOption
0x180034863  mov     rcx, [rdi]; hInternet
0x180034866  call    cs:__imp_WinHttpSetOption
0x18003486c  test    eax, eax
0x18003486e  jnz     short loc_1800348AA
0x180034870  call    cs:__imp_GetLastError
0x180034876  mov     ecx, eax; unsigned int
0x180034878  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003487d  mov     ebx, eax
0x18003487f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034886  lea     rax, WPP_GLOBAL_Control
0x18003488d  cmp     rcx, rax
0x180034890  jz      loc_180034666
0x180034896  test    byte ptr [rcx+1Ch], 1
0x18003489a  jz      loc_180034666
0x1800348a0  mov     edx, 39h ; '9'
0x1800348a5  jmp     loc_180034653
0x1800348aa  movzx   esi, [rsp+230h+var_1EC]
0x1800348af  lea     rcx, [rsp+230h+var_1E0]
0x1800348b4  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x1800348b9  mov     rcx, [rdi+20h]; hEvent
0x1800348bd  call    cs:__imp_ResetEvent
0x1800348c3  mov     rcx, [rdi+30h]; hEvent
  ... truncated ...
```
