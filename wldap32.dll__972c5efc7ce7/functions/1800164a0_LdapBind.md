# LdapBind

- ea: `0x1800164a0`
- end: `0x1800176c6`
- name: `LdapBind`
- size: `4646`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, char)`
- caller_count: `7`
- callee_count: `40`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017780`
- `0x18002e6d4`
- `0x18003b448`
- `0x18003bd34`
- `0x18003bf50`
- `0x18003c070`
- `0x18003c170`

## callees

- `0x1800018d0`
- `0x1800037a8`
- `0x180004e60`
- `0x180006510`
- `0x180008710`
- `0x18000b440`
- `0x18000cad0`
- `0x18000df44`
- `0x180010ef0`
- `0x180011c80`
- `0x180011f50`
- `0x180012ab0`
- `0x180014060`
- `0x180014600`
- `0x1800147f0`
- `0x180014b60`
- `0x180015bd8`
- `0x1800164a0`
- `0x1800176cc`
- `0x180017740`
- `0x180017854`
- `0x180018560`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001ce90`
- `0x180020970`
- `0x180023620`
- `0x180029d28`
- `0x18002a284`
- `0x18002a9f8`
- `0x18002b020`
- `0x18002b4a4`
- `0x18002b904`
- `0x180032bd8`
- `0x180034510`
- `0x18003bcbc`
- `0x180049d3c`
- `0x18004c3d8`
- `0x18004c410`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001734f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800175b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001734f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800175b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001690b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001719c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001746f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017566`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001761c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001690b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001719c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001746f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017566`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001761c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001724a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001724a`
- `ntdll!RtlInitUnicodeString` at `0x180017440`
- `ntdll!RtlInitUnicodeString` at `0x180017440`

## string_xrefs

- `0x180016972`: `ldap_bind connection 0x%x failed to initialize security.\n`
- `0x180016a47`: `New servicename for bind is '%S'\n`
- `0x180016add`: `ldap_bind connection 0x%x couldn't allocate service name.\n`
- `0x180017259`: `ldapBind thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall LdapBind(struct ldap_connection *a1, void *a2, int a3, __int64 a4, unsigned __int8 a5)
{
  int v5; // eax
  int v7; // ecx
  int v8; // r14d
  unsigned __int8 v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 result; // rax
  unsigned int ServiceNameForBind; // r15d
  int v14; // eax
  struct ldap_request *v15; // rsi
  char v16; // r13
  int v17; // edx
  int v18; // ecx
  char v19; // di
  __int64 v20; // rdx
  __int64 v21; // r8
  bool v22; // zf
  unsigned int v23; // eax
  __int64 v24; // r15
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rax
  __int64 v28; // rdx
  LONG v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  LONG v32; // ecx
  LONG v33; // eax
  unsigned __int16 *v34; // rax
  __int64 Request; // rax
  int v36; // r9d
  unsigned int v37; // eax
  __int64 v38; // rdx
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  __int64 v43; // r8
  const unsigned __int16 *v44; // rdx
  unsigned int v45; // eax
  struct CLdapBer *v46; // r8
  unsigned int v47; // eax
  int v48; // eax
  unsigned int v49; // r8d
  unsigned int v50; // eax
  DWORD CurrentThreadId; // eax
  unsigned int v52; // edx
  CryptStream *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r8
  void *v56; // rax
  _QWORD *v57; // rcx
  void *v58; // rax
  unsigned int v59; // esi
  void *v60; // rax
  struct _RTL_CRITICAL_SECTION *v61; // rcx
  size_t Size; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v63[8]; // [rsp+70h] [rbp-90h] BYREF
  struct ldap_request *v64; // [rsp+78h] [rbp-88h]
  int v65[3]; // [rsp+84h] [rbp-7Ch] BYREF
  l_timeval v66; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+98h] [rbp-68h]
  unsigned __int16 *ServiceNameFromHostName; // [rsp+A0h] [rbp-60h] BYREF
  LDAPMessage *res; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+C0h] [rbp-40h] BYREF
  int v72; // [rsp+C8h] [rbp-38h]
  __int64 v73; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+404h] [rbp+304h]
  char v77; // [rsp+418h] [rbp+318h]
  int v78; // [rsp+41Ch] [rbp+31Ch]
  int v79; // [rsp+420h] [rbp+320h]
  __int64 v80; // [rsp+430h] [rbp+330h] BYREF
  int v81; // [rsp+438h] [rbp+338h]
  __int64 v82; // [rsp+440h] [rbp+340h]
  __int64 v83; // [rsp+448h] [rbp+348h]
  int v84; // [rsp+450h] [rbp+350h]
  __int64 v85; // [rsp+774h] [rbp+674h]
  char v86; // [rsp+788h] [rbp+688h]
  int v87; // [rsp+78Ch] [rbp+68Ch]
  int v88; // [rsp+790h] [rbp+690h]

  v5 = *((_DWORD *)a1 + 115);
  *(_QWORD *)&v65[1] = a4;
  Src = a2;
  v7 = 0;
  v65[0] = 0;
  if ( v5 != 16386 )
    v7 = v5;
  v66 = 0;
  v8 = a3;
  *(_DWORD *)&v63[4] = v7;
  v63[0] = 0;
  v70 = 0;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
  {
    v9 = a5;
    LDAPClientPrint(
      0x80000,
      "ldap_bind called for connection 0x%x: DN is %S. Method is 0x%x. Synchronous is 0x%x.\n",
      (_DWORD)a1,
      (const wchar_t *)a2,
      a3,
      a5);
  }
  else
  {
    v9 = a5;
  }
  v10 = LdapConnect(a1, 0, 0);
  v11 = v10;
  if ( !v10 )
  {
    if ( !*((_BYTE *)a1 + 196) && (*((_BYTE *)a1 + 194) || *((_BYTE *)a1 + 195)) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientTraceEvent(0x10000000, "Second Bind is illegal on a signed/sealed connection\n");
      ServiceNameForBind = 53;
      SetConnectionError(a1, 53);
      return ServiceNameForBind;
    }
    v14 = *((_DWORD *)a1 + 250);
    v15 = 0;
    v16 = 0;
    v64 = 0;
    LODWORD(res) = v14;
    if ( v8 == 1158 || v8 == 16518 )
    {
      v17 = 3;
      *((_DWORD *)a1 + 250) = 3;
    }
    else
    {
      v17 = v14;
    }
    v80 = 0;
    v18 = 65001;
    v81 = 0;
    if ( v17 == 2 )
      v18 = 0;
    v82 = 0;
    v87 = v18;
    v85 = 0;
    v83 = 0;
    v86 = 0;
    v88 = 0;
    v84 = 0;
    SetConnectionError(a1, 0);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      LDAPClientPrint(
        0x2000000,
        "ldap_bind called for connection 0x%x: host is '%s'.\n",
        (_DWORD)a1,
        *((const char **)a1 + 124));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
    v19 = 1;
    if ( *((_BYTE *)a1 + 648) && v8 != 128 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "ldap_bind connection 0x%x in concurrent mode but method=0x%x\n", (_DWORD)a1, v8);
      ServiceNameForBind = 53;
      SetConnectionError(a1, 53);
      goto LABEL_231;
    }
    if ( *((_BYTE *)a1 + 552) != 1 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "ldap_bind connection 0x%x is closing.\n", (_DWORD)a1);
      ServiceNameForBind = 89;
      SetConnectionError(a1, 89);
      goto LABEL_231;
    }
    ldapFree(*((_QWORD *)a1 + 10), 1849972044);
    v22 = *((_QWORD *)a1 + 120) == -1;
    *((_QWORD *)a1 + 10) = 0;
    if ( !v22 && *((_DWORD *)a1 + 250) == 2 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "ldap_bind connection 0x%x is Connectionless.\n", (_DWORD)a1);
      if ( !Src )
        goto LABEL_56;
      v23 = strlenW(Src, v20, v21);
      v24 = v23;
      if ( !v23 )
        goto LABEL_56;
      v25 = v23 + 1;
      if ( (unsigned int)v25 >= v23 )
      {
        v26 = 2 * v25;
        if ( v26 <= 0xFFFFFFFF )
        {
          v27 = (void *)ldapMalloc(v26, 1849972044);
          *((_QWORD *)a1 + 10) = v27;
          if ( v27 )
            memcpy_0(v27, Src, 2 * v24);
LABEL_56:
          ServiceNameForBind = 0;
          v65[0] = -1;
          goto LABEL_231;
        }
      }
LABEL_52:
      ServiceNameForBind = 90;
      SetConnectionError(a1, 90);
      goto LABEL_231;
    }
    if ( *((_QWORD *)a1 + 113) == -1 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        LDAPClientPrint(0x100000, "ldap_bind connection 0x%x is Connectionless.\n", (_DWORD)a1);
      ServiceNameForBind = 2;
      SetConnectionError(a1, 2);
LABEL_231:
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
        LDAPClientPrint(0x80000, "ldap_bind returned 0x%x for connection 0x%x.\n", ServiceNameForBind, (_DWORD)a1);
      if ( v16 == 1 )
      {
        ldap_msgfree(*((LDAPMessage **)a1 + 86));
        *((_QWORD *)a1 + 86) = 0;
        *((_BYTE *)a1 + 640) = 0;
      }
      if ( v19 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
      if ( a5 )
      {
        if ( v15 )
        {
          CloseLdapRequest(v15);
          goto LABEL_248;
        }
      }
      else
      {
        if ( !ServiceNameForBind )
        {
          ServiceNameForBind = v65[0];
          goto LABEL_244;
        }
        ServiceNameForBind = -1;
        if ( v15 )
        {
          CloseLdapRequest(v15);
LABEL_244:
          if ( !v15 )
            goto LABEL_255;
LABEL_248:
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 48));
          --*((_DWORD *)v15 + 4);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", (_DWORD)v15, *((_DWORD *)v15 + 4));
          v61 = (struct _RTL_CRITICAL_SECTION *)((char *)v15 + 48);
          if ( *((_DWORD *)v15 + 4) )
          {
            LeaveCriticalSection(v61);
          }
          else
          {
            LeaveCriticalSection(v61);
            DereferenceLdapRequest2(v15, 0);
          }
        }
      }
LABEL_255:
      _InterlockedIncrement64(&qword_1800660D8);
      switch ( v8 )
      {
        case 1158:
          _InterlockedIncrement64(&qword_1800660F8);
          break;
        case 128:
          _InterlockedIncrement64(&qword_1800660E0);
          break;
        case 4230:
          _InterlockedIncrement64(&qword_1800660F0);
          break;
        case 16518:
          _InterlockedIncrement64(&qword_1800660E8);
          break;
      }
      if ( !LdapGetLastError() )
        SetConnectionError(a1, ServiceNameForBind);
      CLdapBer::~CLdapBer((CLdapBer *)&v80);
      return ServiceNameForBind;
    }
    if ( !*((_BYTE *)a1 + 648) )
    {
      if ( *((_BYTE *)a1 + 640) == 1 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
          LDAPClientPrint(0x8000000, "ldap_bind connection 0x%x has bind in progress.\n", a1);
LABEL_69:
        ServiceNameForBind = 82;
        SetConnectionError(a1, 82);
        goto LABEL_231;
      }
      *((_BYTE *)a1 + 640) = 1;
    }
    v16 = 1;
    FreeCurrentCredentials(a1);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
    v19 = 0;
    if ( v8 != 128 )
    {
      if ( v8 != 166 )
      {
        if ( !v9 )
        {
LABEL_74:
          ServiceNameForBind = 89;
          goto LABEL_231;
        }
        if ( !LdapInitSecurity() )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
            LDAPClientPrint(0x8000000, "ldap_bind connection 0x%x failed to initialize security.\n", a1);
          goto LABEL_69;
        }
        if ( v8 == 646 )
        {
          ServiceNameForBind = LdapTryAllMsnAuthentication(a1, *(__int64 *)&v65[1]);
          goto LABEL_216;
        }
        ServiceNameForBind = 7;
        if ( v8 == 1158 )
        {
          if ( !SspiPackageNegotiate && !*((_QWORD *)a1 + 83) )
            goto LABEL_231;
          v29 = 120;
          if ( *((_DWORD *)a1 + 253) )
            v29 = *((_DWORD *)a1 + 253);
          v66.tv_usec = 0;
          v66.tv_sec = v29;
          LdapDetermineServerVersion(a1, &v66, (PWCHAR *)((char *)a1 + 196));
          v30 = *((_QWORD *)a1 + 50);
          if ( v30 )
          {
            ldapFree(v30, 1987203916);
            *((_QWORD *)a1 + 50) = 0;
          }
          ServiceNameForBind = LdapGetServiceNameForBind(a1, &v66, 1158);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
            LDAPClientPrint(0x80000, "New servicename for bind is '%S'\n", *((const wchar_t **)a1 + 50));
          if ( ServiceNameForBind != 1
            && ServiceNameForBind != 81
            && ServiceNameForBind != 9
            && ServiceNameForBind != 85 )
          {
            if ( *((_BYTE *)a1 + 395)
              || (v31 = *((_QWORD *)a1 + 50), (ServiceNameFromHostName = (unsigned __int16 *)v31) == 0) )
            {
              ServiceNameFromHostName = LdapMakeServiceNameFromHostName(*((unsigned __int16 **)a1 + 54));
              v31 = (__int64)ServiceNameFromHostName;
              if ( !ServiceNameFromHostName )
                goto LABEL_100;
            }
            if ( SspiPackageDigest && !*((_QWORD *)a1 + 83) && !*((_BYTE *)a1 + 198) && *((_BYTE *)a1 + 199) )
            {
              v8 = 16518;
              *(_DWORD *)&v63[4] = *((_DWORD *)a1 + 115);
              if ( v31 != *((_QWORD *)a1 + 50) )
                ldapFree(v31, 1987203916);
              goto LABEL_116;
            }
            ServiceNameForBind = LdapSspiBind(a1, (__int64)Src, v31, *(__int64 *)&v65[1]);
            if ( ServiceNameFromHostName != *((unsigned __int16 **)a1 + 50) )
              ldapFree(ServiceNameFromHostName, 1987203916);
          }
          if ( ServiceNameForBind == 2 )
          {
            *((_DWORD *)a1 + 250) = 2;
            v8 = 4230;
          }
          else
          {
            if ( ServiceNameForBind != 7 )
            {
              if ( ((ServiceNameForBind - 81) & 0xFFFFFFFB) == 0 )
                goto LABEL_231;
              goto LABEL_216;
            }
            v8 = 4230;
            *((_DWORD *)a1 + 250) = (_DWORD)res;
          }
        }
LABEL_116:
        v32 = 120;
        v33 = *((_DWORD *)a1 + 253);
        v66.tv_usec = 0;
        if ( v33 )
          v32 = v33;
        v66.tv_sec = v32;
        LdapDetermineServerVersion(a1, &v66, (PWCHAR *)((char *)a1 + 196));
        switch ( v8 )
        {
          case 8326:
            if ( SspiPackageDpa )
              ServiceNameForBind = LdapSspiBind(a1, (__int64)L"DPA", 0, *(__int64 *)&v65[1]);
            break;
          case 2182:
            if ( SspiPackageSicily )
              ServiceNameForBind = LdapSspiBind(a1, (__int64)L"MSN", 0, *(__int64 *)&v65[1]);
            break;
          case 4230:
            if ( SspiPackageNtlm )
              ServiceNameForBind = LdapSspiBind(a1, (__int64)L"NTLM", 0, *(__int64 *)&v65[1]);
            break;
          case 16518:
            if ( SspiPackageDigest )
            {
              ldapFree(*((_QWORD *)a1 + 50), 1987203916);
              *((_QWORD *)a1 + 50) = 0;
              ServiceNameForBind = LdapGetServiceNameForBind(a1, &v66, 16518);
              if ( !*((_BYTE *)a1 + 395)
                && (v34 = (unsigned __int16 *)*((_QWORD *)a1 + 50), (ServiceNameFromHostName = v34) != 0)
                || (v34 = LdapMakeServiceNameFromHostName(*((unsigned __int16 **)a1 + 54)),
                    (ServiceNameFromHostName = v34) != 0) )
              {
                if ( !ServiceNameForBind )
                {
                  ServiceNameForBind = LdapSspiBind(a1, 0, (__int64)v34, *(__int64 *)&v65[1]);
                  v34 = ServiceNameFromHostName;
                }
                if ( v34 != *((unsigned __int16 **)a1 + 50) )
                  ldapFree(v34, 1987203916);
                break;
              }
LABEL_100:
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
                LDAPClientPrint(0x4000, "ldap_bind connection 0x%x couldn't allocate service name.\n", (_DWORD)a1);
              goto LABEL_52;
            }
            break;
          default:
            v64 = 0;
            break;
        }
LABEL_216:
        if ( !ServiceNameForBind )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
          ldapFree(*((_QWORD *)a1 + 10), 1849972044);
          *((_QWORD *)a1 + 10) = 0;
          if ( v8 == 128 || v8 == 166 )
          {
            FreeCurrentCredentials(a1);
            if ( (_DWORD)v15 )
            {
              v56 = (void *)ldapMalloc((unsigned int)v15 + (unsigned __int16)GlobalScramblingBlockSize, 1701987148);
              *((_QWORD *)a1 + 16) = v56;
              if ( v56 )
              {
                memcpy_0(v56, *(const void **)&v65[1], (unsigned int)v15);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 88));
                RtlInitUnicodeString((PUNICODE_STRING)((char *)a1 + 136), *((PCWSTR *)a1 + 16));
                RoundUnicodeStringMaxLength((char *)a1 + 136);
                EncodeUnicodeString((char *)a1 + 136);
                *((_BYTE *)a1 + 152) = 1;
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 88));
              }
            }
            v57 = (_QWORD *)((char *)a1 + 168);
            *((_DWORD *)a1 + 39) = v8;
            if ( *((_BYTE *)a1 + 557) )
              *v57 = v70;
            else
              GetCurrentLuid(v57);
          }
          v58 = Src;
          *((_BYTE *)a1 + 644) = 1;
          if ( v58 )
          {
            v59 = 2 * strlenW(v58, v54, v55);
            if ( v59 )
            {
              v60 = (void *)ldapMalloc(v59 + 2, 1849972044);
              *((_QWORD *)a1 + 10) = v60;
              if ( v60 )
                memcpy_0(v60, Src, v59);
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
        }
        goto LABEL_230;
      }
      if ( *(_QWORD *)&v65[1] || !v9 )
        goto LABEL_74;
      LODWORD(Size) = 0;
      ServiceNameForBind = LdapExchangeOpaqueToken(a1, 0, Size, 0, 0, 0, 0, (__int64)v65, 0, 1, (__int64)v63);
LABEL_210:
      if ( v63[0] )
      {
        v70 = *((_QWORD *)a1 + 21);
        CloseCredentials(a1);
        EnterCriticalSection((LPCRITICAL_SECTION)a1 + 20);
        v53 = (CryptStream *)*((_QWORD *)a1 + 88);
        if ( v53 && (*((_BYTE *)a1 + 194) || *((_BYTE *)a1 + 195)) )
        {
          CryptStream::`scalar deleting destructor'(v53, v52);
          *((_QWORD *)a1 + 88) = 0;
          *((_WORD *)a1 + 97) = 0;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 20);
      }
      goto LABEL_216;
    }
    LOBYTE(v28) = 96;
    Request = LdapCreateRequest(a1, v28);
    v64 = (struct ldap_request *)Request;
    if ( !Request )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "ldap_bind connection 0x%x couldn't allocate request.\n", (_DWORD)a1);
      ServiceNameForBind = 90;
      SetConnectionError(a1, 90);
      goto LABEL_230;
    }
    v65[0] = *(_DWORD *)(Request + 108);
    *(_BYTE *)(Request + 185) = 0;
    *(_BYTE *)(Request + 187) = v9;
    v36 = *((_DWORD *)a1 + 250);
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v76 = 0;
    v74 = 0;
    v77 = 0;
    v79 = 0;
    v75 = 0;
    if ( v36 == 2 )
    {
      v78 = 0;
    }
    else
    {
      v78 = 65001;
      if ( v36 != 3 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
          LDAPClientPrint(0x8000000, "ldap_bind connection 0x%x asked for version 0x%x.\n", (_DWORD)a1, v36);
        v38 = 2;
        ServiceNameForBind = 2;
        goto LABEL_158;
      }
    }
    v37 = CLdapBer::HrStartWriteSequence((CLdapBer *)&v80, 0x30u);
    ServiceNameForBind = v37;
    if ( v37 )
    {
      v38 = v37;
LABEL_158:
      SetConnectionError(a1, v38);
      CLdapBer::~CLdapBer((CLdapBer *)&v71);
LABEL_230:
      v15 = v64;
      goto LABEL_231;
    }
    v39 = CLdapBer::HrAddValue((CLdapBer *)&v80, v65[0], 2u);
    ServiceNameForBind = v39;
    if ( v39 )
    {
      v38 = v39;
      goto LABEL_158;
    }
    v40 = CLdapBer::HrStartWriteSequence((CLdapBer *)&v80, 0x60u);
    ServiceNameForBind = v40;
    if ( v40 )
    {
      v38 = v40;
      goto LABEL_158;
    }
    v41 = CLdapBer::HrAddValue((CLdapBer *)&v80, *((_DWORD *)a1 + 250), 2u);
    ServiceNameForBind = v41;
    if ( v41 )
    {
      v38 = v41;
      goto LABEL_158;
    }
    v42 = CLdapBer::HrAddValue((CLdapBer *)&v80, (const unsigned __int16 *)Src, 4u);
    ServiceNameForBind = v42;
    if ( v42 )
    {
      v38 = v42;
      goto LABEL_158;
    }
    *(_WORD *)&v63[4] = 0;
    if ( *(_QWORD *)&v65[1] )
    {
      LODWORD(v15) = 2 * strlenW(*(_QWORD *)&v65[1], *(_QWORD *)&v65[1], v43) + 2;
      v45 = CLdapBer::HrAddValue((CLdapBer *)&v80, v44, 0x80u);
    }
    else
    {
      v45 = CLdapBer::HrAddBinaryValue((CLdapBer *)&v80, &v63[4], 0, 0x80u);
    }
    ServiceNameForBind = v45;
    if ( v45 )
    {
      v38 = v45;
      goto LABEL_158;
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)&v80);
    CLdapBer::HrEndWriteSequence((CLdapBer *)&v80);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800) != 0 )
    {
      CLdapBer::HrStartWriteSequence((CLdapBer *)&v71, 0x30u);
      CLdapBer::HrAddValue((CLdapBer *)&v71, v65[0], 2u);
      CLdapBer::HrStartWriteSequence((CLdapBer *)&v71, 0x60u);
      CLdapBer::HrAddValue((CLdapBer *)&v71, *((_DWORD *)a1 + 250), 2u);
      CLdapBer::HrAddValue((CLdapBer *)&v71, (const unsigned __int16 *)Src, 4u);
      CLdapBer::HrEndWriteSequence((CLdapBer *)&v71);
      CLdapBer::HrEndWriteSequence((CLdapBer *)&v71);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)a1 + 14);
    AddToPendingList(v64, a1);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800) != 0 )
      v46 = (struct CLdapBer *)&v71;
    else
      v46 = 0;
    v47 = LdapSend(a1, (struct CLdapBer *)&v80, v46);
    ServiceNameForBind = v47;
    if ( v47 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        LDAPClientPrint(0x100000, "ldap_bind connection 0x%x send with error of 0x%x.\n", (_DWORD)a1, v47);
      DecrementPendingList(v64, a1);
      LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 14);
      goto LABEL_209;
    }
    v63[0] = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 14);
    if ( a5 )
    {
      v48 = *((_DWORD *)a1 + 253);
      v49 = 30000;
      res = 0;
      if ( v48 )
        v49 = 1000 * v48;
      v50 = LdapWaitForResponseFromServer(a1, v64, v49, 0, &res, 1);
      ServiceNameForBind = v50;
      if ( v50 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
          LDAPClientPrint(0x80000, "LdapBind connection 0x%x didn't get response from server, 0x%x.\n", a1, v50);
        goto LABEL_205;
      }
      if ( res )
      {
        ServiceNameForBind = res->lm_returncode;
LABEL_197:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
          LDAPClientPrint(
            0x80000,
            "LdapBind connection 0x%x gets response of 0x%x from server.\n",
            a1,
            ServiceNameForBind);
LABEL_205:
        if ( res )
        {
          ServiceNameFromHostName = 0;
          LdapParseResult(a1, res, 0, 0, &ServiceNameFromHostName, 0, 0, 0, 0);
          InsertErrorMessage(a1, ServiceNameFromHostName);
          if ( res )
            ldap_msgfree(res);
        }
        goto LABEL_209;
      }
      ServiceNameForBind = 81;
      if ( g_fTracingOn )
      {
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
        {
          CurrentThreadId = GetCurrentThreadId();
          LDAPClientPrint(128, "ldapBind thread 0x%x has connection 0x%x as down.\n", CurrentThreadId, (_DWORD)a1);
        }
        goto LABEL_197;
      }
    }
    else
    {
      ServiceNameForBind = 0;
    }
LABEL_209:
    CLdapBer::~CLdapBer((CLdapBer *)&v71);
    goto LABEL_210;
  }
  SetConnectionError(a1, v10);
  result = 0xFFFFFFFFLL;
  if ( v9 )
    return v11;
  return result;
}

```

## disassembly

```asm
0x1800164a0  push    rbp
0x1800164a2  push    rbx
0x1800164a3  push    rdi
0x1800164a4  push    r12
0x1800164a6  push    r14
0x1800164a8  push    r15
0x1800164aa  lea     rbp, [rsp-6C8h]
0x1800164b2  sub     rsp, 7C8h
0x1800164b9  mov     rax, cs:__security_cookie
0x1800164c0  xor     rax, rsp
0x1800164c3  mov     [rbp+6F0h+var_50], rax
0x1800164ca  mov     eax, [rcx+1CCh]
0x1800164d0  xor     r12d, r12d
0x1800164d3  cmp     eax, 4002h
0x1800164d8  mov     qword ptr [rbp+6F0h+var_76C+4], r9
0x1800164dc  mov     rbx, rcx
0x1800164df  mov     [rbp+6F0h+Src], rdx
0x1800164e3  mov     ecx, r12d
0x1800164e6  mov     dword ptr [rbp+6F0h+var_76C], r12d
0x1800164ea  cmovnz  ecx, eax
0x1800164ed  mov     qword ptr [rbp+6F0h+var_760.tv_sec], r12
0x1800164f1  cmp     cs:g_fTracingOn, r12d
0x1800164f8  mov     r14d, r8d
0x1800164fb  mov     dword ptr [rsp+7F0h+var_780+4], ecx
0x1800164ff  mov     [rsp+7F0h+var_780], r12b
0x180016504  mov     [rbp+6F0h+var_740], r12
0x180016508  jz      short loc_18001654B
0x18001650a  cmp     cs:g_fProviderEnabled, r12d
0x180016511  jz      short loc_18001654B
0x180016513  test    cs:g_ulTraceFlags, 80000h
0x18001651e  jz      short loc_18001654B
0x180016520  movzx   r15d, [rbp+6F0h+arg_20]
0x180016528  mov     r9, rdx
0x18001652b  mov     dword ptr [rsp+7F0h+Size], r15d
0x180016530  lea     rdx, aLdapBindCalled_0; "ldap_bind called for connection 0x%x: D"...
0x180016537  mov     dword ptr [rsp+7F0h+var_7D0], r8d
0x18001653c  mov     ecx, 80000h
0x180016541  mov     r8, rbx
0x180016544  call    LDAPClientPrint
0x180016549  jmp     short loc_180016553
0x18001654b  movzx   r15d, [rbp+6F0h+arg_20]
0x180016553  xor     r8d, r8d
0x180016556  xor     edx, edx
0x180016558  mov     rcx, rbx
0x18001655b  call    LdapConnect
0x180016560  mov     edi, eax
0x180016562  test    eax, eax
0x180016564  jz      short loc_180016580
0x180016566  mov     edx, eax
0x180016568  mov     rcx, rbx
0x18001656b  call    SetConnectionError
0x180016570  test    r15b, r15b
0x180016573  mov     eax, 0FFFFFFFFh
0x180016578  cmovnz  eax, edi
0x18001657b  jmp     loc_1800176A5
0x180016580  cmp     [rbx+0C4h], r12b
0x180016587  jnz     short loc_1800165E1
0x180016589  cmp     [rbx+0C2h], r12b
0x180016590  jnz     short loc_18001659B
0x180016592  cmp     [rbx+0C3h], r12b
0x180016599  jz      short loc_1800165E1
0x18001659b  cmp     cs:g_fTracingOn, r12d
0x1800165a2  jz      short loc_1800165CB
0x1800165a4  cmp     cs:g_fProviderEnabled, r12d
0x1800165ab  jz      short loc_1800165CB
0x1800165ad  test    cs:g_ulTraceFlags, 10000000h
0x1800165b8  jz      short loc_1800165CB
0x1800165ba  lea     rdx, aSecondBindIsIl; "Second Bind is illegal on a signed/seal"...
0x1800165c1  mov     ecx, 10000000h
0x1800165c6  call    LDAPClientTraceEvent
0x1800165cb  mov     r15d, 35h ; '5'
0x1800165d1  mov     rcx, rbx
0x1800165d4  mov     edx, r15d
0x1800165d7  call    SetConnectionError
0x1800165dc  jmp     loc_1800176A2
0x1800165e1  mov     eax, [rbx+3E8h]
0x1800165e7  mov     [rsp+7F0h+var_30], rsi
0x1800165ef  mov     rsi, r12
0x1800165f2  mov     [rsp+7F0h+var_38], r13
0x1800165fa  xor     r13b, r13b
0x1800165fd  mov     [rsp+7F0h+var_778], r12
0x180016602  mov     dword ptr [rbp+6F0h+res], eax
0x180016605  cmp     r14d, 486h
0x18001660c  jz      short loc_18001661B
0x18001660e  cmp     r14d, 4086h
0x180016615  jz      short loc_18001661B
0x180016617  mov     edx, eax
0x180016619  jmp     short loc_180016626
0x18001661b  mov     edx, 3
0x180016620  mov     [rbx+3E8h], edx
0x180016626  cmp     edx, 2
0x180016629  mov     [rbp+6F0h+var_3C0], r12
0x180016630  mov     ecx, 0FDE9h
0x180016635  mov     [rbp+6F0h+var_3B8], r12d
0x18001663c  cmovz   ecx, r12d
0x180016640  mov     [rbp+6F0h+var_3B0], r12
0x180016647  mov     [rbp+6F0h+var_64], ecx
0x18001664d  xor     edx, edx
0x18001664f  mov     rcx, rbx
0x180016652  mov     [rbp+6F0h+var_7C], r12
0x180016659  mov     [rbp+6F0h+var_3A8], r12
0x180016660  mov     [rbp+6F0h+var_68], sil
0x180016667  mov     [rbp+6F0h+var_60], r12d
0x18001666e  mov     [rbp+6F0h+var_3A0], r12d
0x180016675  call    SetConnectionError
0x18001667a  cmp     cs:g_fTracingOn, esi
0x180016680  jz      short loc_1800166B2
0x180016682  cmp     cs:g_fProviderEnabled, esi
0x180016688  jz      short loc_1800166B2
0x18001668a  test    cs:g_ulTraceFlags, 2000000h
0x180016695  jz      short loc_1800166B2
0x180016697  mov     r9, [rbx+3E0h]
0x18001669e  lea     rdx, aLdapBindCalled; "ldap_bind called for connection 0x%x: h"...
0x1800166a5  mov     r8, rbx
0x1800166a8  mov     ecx, 2000000h
0x1800166ad  call    LDAPClientPrint
0x1800166b2  lea     rcx, [rbx+200h]; lpCriticalSection
0x1800166b9  call    cs:__imp_EnterCriticalSection
0x1800166c0  nop     dword ptr [rax+rax+00h]
0x1800166c5  mov     dil, 1
0x1800166c8  cmp     [rbx+288h], sil
0x1800166cf  jz      short loc_180016724
0x1800166d1  cmp     r14d, 80h
0x1800166d8  jz      short loc_180016724
0x1800166da  cmp     cs:g_fTracingOn, esi
0x1800166e0  jz      short loc_18001670E
0x1800166e2  cmp     cs:g_fProviderEnabled, esi
0x1800166e8  jz      short loc_18001670E
0x1800166ea  test    cs:g_ulTraceFlags, 2000000h
0x1800166f5  jz      short loc_18001670E
0x1800166f7  mov     r9d, r14d
0x1800166fa  lea     rdx, aLdapBindConnec_7; "ldap_bind connection 0x%x in concurrent"...
0x180016701  mov     r8, rbx
0x180016704  mov     ecx, 2000000h
0x180016709  call    LDAPClientPrint
0x18001670e  mov     r15d, 35h ; '5'
0x180016714  mov     rcx, rbx
0x180016717  mov     edx, r15d
0x18001671a  call    SetConnectionError
0x18001671f  jmp     loc_1800174FC
0x180016724  cmp     [rbx+228h], dil
0x18001672b  jz      short loc_180016774
0x18001672d  cmp     cs:g_fTracingOn, esi
0x180016733  jz      short loc_18001675E
0x180016735  cmp     cs:g_fProviderEnabled, esi
0x18001673b  jz      short loc_18001675E
0x18001673d  test    cs:g_ulTraceFlags, 2000000h
0x180016748  jz      short loc_18001675E
0x18001674a  mov     r8, rbx
0x18001674d  lea     rdx, aLdapBindConnec_5; "ldap_bind connection 0x%x is closing.\n"
0x180016754  mov     ecx, 2000000h
0x180016759  call    LDAPClientPrint
0x18001675e  mov     r15d, 59h ; 'Y'
0x180016764  mov     rcx, rbx
0x180016767  mov     edx, r15d
0x18001676a  call    SetConnectionError
0x18001676f  jmp     loc_1800174FC
0x180016774  mov     rcx, [rbx+50h]
0x180016778  mov     edx, 6E44554Ch
0x18001677d  call    ldapFree
0x180016782  cmp     qword ptr [rbx+3C0h], 0FFFFFFFFFFFFFFFFh
0x18001678a  mov     [rbx+50h], rsi
0x18001678e  jz      loc_180016849
0x180016794  cmp     dword ptr [rbx+3E8h], 2
0x18001679b  jnz     loc_180016849
0x1800167a1  cmp     cs:g_fTracingOn, esi
0x1800167a7  jz      short loc_1800167D2
0x1800167a9  cmp     cs:g_fProviderEnabled, esi
0x1800167af  jz      short loc_1800167D2
0x1800167b1  test    cs:g_ulTraceFlags, 2000000h
0x1800167bc  jz      short loc_1800167D2
0x1800167be  mov     r8, rbx
0x1800167c1  lea     rdx, aLdapBindConnec_6; "ldap_bind connection 0x%x is Connection"...
0x1800167c8  mov     ecx, 2000000h
0x1800167cd  call    LDAPClientPrint
0x1800167d2  mov     rax, [rbp+6F0h+Src]
0x1800167d6  test    rax, rax
0x1800167d9  jz      short loc_18001683A
0x1800167db  mov     rcx, rax
0x1800167de  call    strlenW
0x1800167e3  mov     r15d, eax
0x1800167e6  test    eax, eax
0x1800167e8  jz      short loc_18001683A
0x1800167ea  lea     ecx, [r15+1]
0x1800167ee  cmp     ecx, r15d
0x1800167f1  jnb     short loc_180016808
0x1800167f3  mov     edx, 5Ah ; 'Z'
0x1800167f8  mov     rcx, rbx
0x1800167fb  mov     r15d, edx
0x1800167fe  call    SetConnectionError
0x180016803  jmp     loc_1800174FC
0x180016808  add     rcx, rcx
0x18001680b  mov     eax, 0FFFFFFFFh
0x180016810  cmp     rcx, rax
0x180016813  ja      short loc_1800167F3
0x180016815  mov     edx, 6E44554Ch
0x18001681a  call    ldapMalloc
0x18001681f  mov     [rbx+50h], rax
0x180016823  test    rax, rax
0x180016826  jz      short loc_18001683A
0x180016828  mov     rdx, [rbp+6F0h+Src]; Src
0x18001682c  mov     r8, r15
0x18001682f  add     r8, r8; Size
0x180016832  mov     rcx, rax; void *
0x180016835  call    memcpy_0
0x18001683a  xor     r15d, r15d
0x18001683d  mov     dword ptr [rbp+6F0h+var_76C], 0FFFFFFFFh
0x180016844  jmp     loc_1800174FC
0x180016849  cmp     qword ptr [rbx+388h], 0FFFFFFFFFFFFFFFFh
0x180016851  jnz     short loc_180016899
0x180016853  cmp     cs:g_fTracingOn, esi
0x180016859  jz      short loc_180016884
0x18001685b  cmp     cs:g_fProviderEnabled, esi
0x180016861  jz      short loc_180016884
0x180016863  test    cs:g_ulTraceFlags, 100000h
0x18001686e  jz      short loc_180016884
0x180016870  mov     r8, rbx
0x180016873  lea     rdx, aLdapBindConnec_6; "ldap_bind connection 0x%x is Connection"...
0x18001687a  mov     ecx, 100000h
0x18001687f  call    LDAPClientPrint
0x180016884  mov     edx, 2
0x180016889  mov     rcx, rbx
0x18001688c  mov     r15d, edx
0x18001688f  call    SetConnectionError
0x180016894  jmp     loc_1800174FC
0x180016899  cmp     [rbx+288h], sil
0x1800168a0  jnz     short loc_1800168F8
0x1800168a2  cmp     [rbx+280h], dil
0x1800168a9  jnz     short loc_1800168F1
0x1800168ab  cmp     cs:g_fTracingOn, esi
0x1800168b1  jz      short loc_1800168DC
0x1800168b3  cmp     cs:g_fProviderEnabled, esi
0x1800168b9  jz      short loc_1800168DC
0x1800168bb  test    cs:g_ulTraceFlags, 8000000h
0x1800168c6  jz      short loc_1800168DC
0x1800168c8  lea     rdx, aLdapBindConnec; "ldap_bind connection 0x%x has bind in p"...
0x1800168cf  mov     r8, rbx
0x1800168d2  mov     ecx, 8000000h
0x1800168d7  call    LDAPClientPrint
0x1800168dc  mov     edx, 52h ; 'R'
0x1800168e1  mov     rcx, rbx
0x1800168e4  mov     r15d, edx
0x1800168e7  call    SetConnectionError
0x1800168ec  jmp     loc_1800174FC
0x1800168f1  mov     [rbx+280h], dil
0x1800168f8  mov     rcx, rbx
0x1800168fb  movzx   r13d, dil
0x1800168ff  call    FreeCurrentCredentials
0x180016904  lea     rcx, [rbx+200h]; lpCriticalSection
0x18001690b  call    cs:__imp_LeaveCriticalSection
0x180016912  nop     dword ptr [rax+rax+00h]
0x180016917  xor     dil, dil
0x18001691a  cmp     r14d, 80h
0x180016921  jz      loc_180016E57
0x180016927  cmp     r14d, 0A6h
0x18001692e  jz      loc_180016DE8
0x180016934  test    r15b, r15b
0x180016937  jnz     short loc_180016944
0x180016939  mov     r15d, 59h ; 'Y'
0x18001693f  jmp     loc_1800174FC
0x180016944  call    LdapInitSecurity
0x180016949  test    al, al
0x18001694b  jnz     short loc_18001697E
0x18001694d  cmp     cs:g_fTracingOn, esi
0x180016953  jz      short loc_1800168DC
0x180016955  cmp     cs:g_fProviderEnabled, esi
0x18001695b  jz      loc_1800168DC
0x180016961  test    cs:g_ulTraceFlags, 8000000h
0x18001696c  jz      loc_1800168DC
0x180016972  lea     rdx, aLdapBindConnec_3; "ldap_bind connection 0x%x failed to ini"...
0x180016979  jmp     loc_1800168CF
0x18001697e  cmp     r14d, 286h
0x180016985  jnz     short loc_18001699B
0x180016987  mov     rdx, qword ptr [rbp+6F0h+var_76C+4]; __int64
0x18001698b  mov     rcx, rbx; struct ldap_connection *
0x18001698e  call    LdapTryAllMsnAuthentication
0x180016993  mov     r15d, eax
0x180016996  jmp     loc_1800173A0
0x18001699b  mov     r15d, 7
0x1800169a1  cmp     r14d, 486h
0x1800169a8  jnz     loc_180016BCC
0x1800169ae  cmp     cs:SspiPackageNegotiate, rsi
0x1800169b5  jnz     short loc_1800169C4
0x1800169b7  cmp     [rbx+298h], rsi
0x1800169be  jz      loc_1800174FC
0x1800169c4  mov     ecx, [rbx+3F4h]
0x1800169ca  lea     r8, [rbx+0C4h]
0x1800169d1  test    ecx, ecx
0x1800169d3  lea     rdx, [rbp+6F0h+var_760]
0x1800169d7  mov     eax, 78h ; 'x'
0x1800169dc  cmovnz  eax, ecx
0x1800169df  xor     r15d, r15d
0x1800169e2  mov     rcx, rbx; struct ldap_connection *
0x1800169e5  mov     [rbp+6F0h+var_760.tv_usec], r15d
0x1800169e9  mov     [rbp+6F0h+var_760.tv_sec], eax
0x1800169ec  call    LdapDetermineServerVersion
0x1800169f1  mov     rcx, [rbx+190h]
0x1800169f8  test    rcx, rcx
0x1800169fb  jz      short loc_180016A0E
0x1800169fd  mov     edx, 7672534Ch
  ... truncated ...
```
