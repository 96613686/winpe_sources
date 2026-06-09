# RDSHTelemetryLogging::InitOnceCallbackFn(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800926c8`
- end: `0x180092ab5`
- name: `?InitOnceCallbackFn@RDSHTelemetryLogging@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `1005`
- prototype: `__int64 __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092fd8`
- `0x1800938f0`

## callees

- `0x1800016a8`
- `0x180034500`
- `0x1800924ac`
- `0x1800926c8`
- `0x1800ca374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092793`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180092883`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800929ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180092883`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800929ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092781`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800927d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800927d8`

## string_xrefs

- `0x180092818`: `RegOpenKeyEx REG_CONTROL_SESSDIR_TELEMETRY_KEY failed`

## pseudocode

```c
_BOOL8 __fastcall RDSHTelemetryLogging::InitOnceCallbackFn(union _RTL_RUN_ONCE *a1, void *a2, void **a3)
{
  int SessDirActive; // ebx
  int v4; // r8d
  int v5; // r9d
  int v6; // ecx
  __int16 *v7; // rdx
  const char **v8; // rax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  unsigned __int64 v12; // rcx
  LSTATUS v13; // eax
  unsigned __int64 v14; // rcx
  const char **v15; // [rsp+38h] [rbp-30h]
  const char *v16; // [rsp+40h] [rbp-28h] BYREF
  const char *v17; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+28h] BYREF
  int v20; // [rsp+94h] [rbp+2Ch]
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  int v22; // [rsp+9Ch] [rbp+34h]
  DWORD cbData; // [rsp+A0h] [rbp+38h] BYREF
  int v24; // [rsp+A4h] [rbp+3Ch]
  HKEY hKey; // [rsp+A8h] [rbp+40h] BYREF

  v24 = HIDWORD(a3);
  v22 = HIDWORD(a2);
  v20 = HIDWORD(a1);
  hKey = 0;
  Type = 0;
  cbData = 0;
  v19 = 0;
  SessDirActive = RDSHTelemetryLogging::GetSessDirActive(&v19);
  if ( SessDirActive < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v6 = dword_18012E170;
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_5;
    v16 = "InitOnceCallbackFn";
    v7 = &word_18011714E;
    v17 = "REG_TS_SESSDIRACTIVE not REG_DWORD";
    v18[0] = "Warning HResult failed";
    v15 = &v16;
    v8 = (const char **)v18;
    goto LABEL_4;
  }
  if ( !v19 )
    goto LABEL_5;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM",
          0,
          0x20019u,
          &hKey);
  SessDirActive = v10;
  if ( v10 > 0 )
    SessDirActive = (unsigned __int16)v10 | 0x80070000;
  if ( SessDirActive >= 0 )
  {
    cbData = 512;
    v11 = RegQueryValueExW(hKey, L"TelemetryDeploymentId", 0, &Type, &RDSHTelemetryLogging::m_DeploymentId, &cbData);
    SessDirActive = v11;
    if ( v11 > 0 )
      SessDirActive = (unsigned __int16)v11 | 0x80070000;
    if ( SessDirActive >= 0 )
    {
      if ( Type != 1 )
      {
        SessDirActive = -2147024809;
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v19 = -2147024809;
          v18[0] = "InitOnceCallbackFn";
          v17 = "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not REG_SZ";
          v16 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            -2147024809,
            (unsigned int)word_180117082,
            v4,
            v5,
            (__int64)&v16,
            (__int64)&v17,
            (__int64)&v19,
            (__int64)v18);
        }
        goto LABEL_5;
      }
      v12 = cbData & 0xFFFFFFFE;
      if ( v12 < 0x202 )
      {
        cbData = 512;
        *(_WORD *)(&RDSHTelemetryLogging::m_DeploymentId + v12) = 0;
        v13 = RegQueryValueExW(hKey, L"TelemetryFarmId", 0, &Type, &RDSHTelemetryLogging::m_FarmId, &cbData);
        SessDirActive = v13;
        if ( v13 > 0 )
          SessDirActive = (unsigned __int16)v13 | 0x80070000;
        if ( SessDirActive < 0 )
        {
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v18[0] = "InitOnceCallbackFn";
            v7 = &word_18011703E;
            v17 = "RegQueryValueEx REG_SESSDIR_TELEMETRY_FARM_ID failed";
            v16 = "Warning HResult failed";
            v15 = (const char **)v18;
            v8 = &v16;
            goto LABEL_4;
          }
          goto LABEL_5;
        }
        if ( Type != 1 )
        {
          SessDirActive = -2147024809;
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v19 = -2147024809;
            v18[0] = "InitOnceCallbackFn";
            v17 = "REG_SESSDIR_TELEMETRY_FARM_ID not REG_SZ";
            v16 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              -2147024809,
              (unsigned int)word_180116FFA,
              v4,
              v5,
              (__int64)&v16,
              (__int64)&v17,
              (__int64)&v19,
              (__int64)v18);
          }
          goto LABEL_5;
        }
        v14 = cbData & 0xFFFFFFFE;
        if ( v14 < 0x202 )
        {
          *(_WORD *)(&RDSHTelemetryLogging::m_FarmId + v14) = 0;
          goto LABEL_5;
        }
      }
      _report_rangecheckfailure();
    }
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v18[0] = "InitOnceCallbackFn";
      v7 = &word_1801170C6;
      v17 = "RegQueryValueEx REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID failed";
      v16 = "Warning HResult failed";
      v15 = (const char **)v18;
      v8 = &v16;
      goto LABEL_4;
    }
  }
  else if ( (unsigned int)dword_18012E170 > 3 )
  {
    v18[0] = "InitOnceCallbackFn";
    v7 = word_18011710A;
    v17 = "RegOpenKeyEx REG_CONTROL_SESSDIR_TELEMETRY_KEY failed";
    v16 = "Warning HResult failed";
    v15 = (const char **)v18;
    v8 = &v16;
LABEL_4:
    v19 = SessDirActive;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v6,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)v8,
      (__int64)&v17,
      (__int64)&v19,
      (__int64)v15);
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( SessDirActive < 0 )
    SetLastError(SessDirActive);
  return SessDirActive >= 0;
}

```

## disassembly

```asm
0x1800926c8  mov     qword ptr [rsp-20h+cbData], r8
0x1800926cd  mov     qword ptr [rsp-20h+Type], rdx
0x1800926d2  mov     qword ptr [rsp-20h+arg_0], rcx
0x1800926d7  push    rbp
0x1800926d8  push    rbx
0x1800926d9  push    r12
0x1800926db  push    r15
0x1800926dd  mov     rbp, rsp
0x1800926e0  sub     rsp, 68h
0x1800926e4  lea     rcx, [rbp+arg_0]; unsigned int *
0x1800926e8  mov     [rbp+hKey], 0
0x1800926f0  mov     [rbp+Type], 0
0x1800926f7  mov     [rbp+cbData], 0
0x1800926fe  mov     [rbp+arg_0], 0
0x180092705  call    ?GetSessDirActive@RDSHTelemetryLogging@@CAJPEAK@Z; RDSHTelemetryLogging::GetSessDirActive(ulong *)
0x18009270a  mov     ebx, eax
0x18009270c  test    eax, eax
0x18009270e  jns     loc_1800927B2
0x180092714  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180092719  mov     ecx, cs:dword_18012E170
0x18009271f  cmp     ecx, 3
0x180092722  jbe     short loc_180092778
0x180092724  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18009272b  mov     [rbp+var_28], rax
0x18009272f  lea     rdx, word_18011714E
0x180092736  lea     rax, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD"
0x18009273d  mov     [rbp+var_20], rax
0x180092741  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092748  mov     [rbp+var_18], rax
0x18009274c  lea     rax, [rbp+var_28]
0x180092750  mov     [rsp+68h+var_30], rax
0x180092755  lea     rax, [rbp+arg_0]
0x180092759  mov     [rsp+68h+var_38], rax
0x18009275e  lea     rax, [rbp+var_20]
0x180092762  mov     [rsp+68h+lpcbData], rax
0x180092767  lea     rax, [rbp+var_18]
0x18009276b  mov     [rbp+arg_0], ebx
0x18009276e  mov     [rsp+68h+phkResult], rax
0x180092773  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180092778  mov     rcx, [rbp+hKey]; hKey
0x18009277c  test    rcx, rcx
0x18009277f  jz      short loc_18009278D
0x180092781  call    cs:__imp_RegCloseKey
0x180092788  nop     dword ptr [rax+rax+00h]
0x18009278d  test    ebx, ebx
0x18009278f  jns     short loc_18009279F
0x180092791  mov     ecx, ebx; dwErrCode
0x180092793  call    cs:__imp_SetLastError
0x18009279a  nop     dword ptr [rax+rax+00h]
0x18009279f  not     ebx
0x1800927a1  shr     ebx, 1Fh
0x1800927a4  mov     eax, ebx
0x1800927a6  add     rsp, 68h
0x1800927aa  pop     r15
0x1800927ac  pop     r12
0x1800927ae  pop     rbx
0x1800927af  pop     rbp
0x1800927b0  retn
0x1800927b2  cmp     [rbp+arg_0], 0
0x1800927b6  jz      short loc_180092778
0x1800927b8  lea     rax, [rbp+hKey]
0x1800927bc  mov     r9d, 20019h; samDesired
0x1800927c2  xor     r8d, r8d; ulOptions
0x1800927c5  mov     [rsp+68h+phkResult], rax; phkResult
0x1800927ca  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Ter"...
0x1800927d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800927d8  call    cs:__imp_RegOpenKeyExW
0x1800927df  nop     dword ptr [rax+rax+00h]
0x1800927e4  mov     ebx, eax
0x1800927e6  test    eax, eax
0x1800927e8  jle     short loc_1800927F3
0x1800927ea  movzx   ebx, ax
0x1800927ed  or      ebx, 80070000h
0x1800927f3  test    ebx, ebx
0x1800927f5  jns     short loc_180092852
0x1800927f7  mov     eax, cs:dword_18012E170
0x1800927fd  cmp     eax, 3
0x180092800  jbe     loc_180092778
0x180092806  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18009280d  mov     [rbp+var_18], rax
0x180092811  lea     rdx, word_18011710A
0x180092818  lea     rax, aRegopenkeyexRe; "RegOpenKeyEx REG_CONTROL_SESSDIR_TELEME"...
0x18009281f  mov     [rbp+var_20], rax
0x180092823  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009282a  mov     [rbp+var_28], rax
0x18009282e  lea     rax, [rbp+var_18]
0x180092832  mov     [rsp+68h+var_30], rax
0x180092837  lea     rax, [rbp+arg_0]
0x18009283b  mov     [rsp+68h+var_38], rax
0x180092840  lea     rax, [rbp+var_20]
0x180092844  mov     [rsp+68h+lpcbData], rax
0x180092849  lea     rax, [rbp+var_28]
0x18009284d  jmp     loc_18009276B
0x180092852  mov     rcx, [rbp+hKey]; hKey
0x180092856  lea     rax, [rbp+cbData]
0x18009285a  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18009285f  lea     r12, ?m_DeploymentId@RDSHTelemetryLogging@@0PAGA; ushort near * RDSHTelemetryLogging::m_DeploymentId
0x180092866  mov     r15d, 200h
0x18009286c  mov     [rsp+68h+phkResult], r12; lpData
0x180092871  lea     r9, [rbp+Type]; lpType
0x180092875  mov     [rbp+cbData], r15d
0x180092879  xor     r8d, r8d; lpReserved
0x18009287c  lea     rdx, aTelemetrydeplo; "TelemetryDeploymentId"
0x180092883  call    cs:__imp_RegQueryValueExW
0x18009288a  nop     dword ptr [rax+rax+00h]
0x18009288f  mov     ebx, eax
0x180092891  test    eax, eax
0x180092893  jle     short loc_18009289E
0x180092895  movzx   ebx, ax
0x180092898  or      ebx, 80070000h
0x18009289e  test    ebx, ebx
0x1800928a0  jns     short loc_1800928FD
0x1800928a2  mov     eax, cs:dword_18012E170
0x1800928a8  cmp     eax, 3
0x1800928ab  jbe     loc_180092778
0x1800928b1  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x1800928b8  mov     [rbp+var_18], rax
0x1800928bc  lea     rdx, word_1801170C6
0x1800928c3  lea     rax, aRegqueryvaluee; "RegQueryValueEx REG_SESSDIR_TELEMETRY_D"...
0x1800928ca  mov     [rbp+var_20], rax
0x1800928ce  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800928d5  mov     [rbp+var_28], rax
0x1800928d9  lea     rax, [rbp+var_18]
0x1800928dd  mov     [rsp+68h+var_30], rax
0x1800928e2  lea     rax, [rbp+arg_0]
0x1800928e6  mov     [rsp+68h+var_38], rax
0x1800928eb  lea     rax, [rbp+var_20]
0x1800928ef  mov     [rsp+68h+lpcbData], rax
0x1800928f4  lea     rax, [rbp+var_28]
0x1800928f8  jmp     loc_18009276B
0x1800928fd  cmp     [rbp+Type], 1
0x180092901  jz      short loc_180092968
0x180092903  mov     eax, cs:dword_18012E170
0x180092909  mov     ecx, 80070057h
0x18009290e  mov     ebx, ecx
0x180092910  cmp     eax, 3
0x180092913  jbe     loc_180092778
0x180092919  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x180092920  mov     [rbp+arg_0], ecx
0x180092923  mov     [rbp+var_18], rax
0x180092927  lea     rdx, word_180117082
0x18009292e  lea     rax, aRegSessdirTele_0; "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not"...
0x180092935  mov     [rbp+var_20], rax
0x180092939  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092940  mov     [rbp+var_28], rax
0x180092944  lea     rax, [rbp+var_18]
0x180092948  mov     [rsp+68h+var_30], rax
0x18009294d  lea     rax, [rbp+arg_0]
0x180092951  mov     [rsp+68h+var_38], rax
0x180092956  lea     rax, [rbp+var_20]
0x18009295a  mov     [rsp+68h+lpcbData], rax
0x18009295f  lea     rax, [rbp+var_28]
0x180092963  jmp     loc_18009276E
0x180092968  mov     ecx, [rbp+cbData]
0x18009296b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18009296f  cmp     rcx, 202h
0x180092976  jnb     loc_180092AAF
0x18009297c  xor     eax, eax
0x18009297e  mov     [rbp+cbData], r15d
0x180092982  mov     [rcx+r12], ax
0x180092987  lea     r15, ?m_FarmId@RDSHTelemetryLogging@@0PAGA; ushort near * RDSHTelemetryLogging::m_FarmId
0x18009298e  mov     rcx, [rbp+hKey]; hKey
0x180092992  lea     rax, [rbp+cbData]
0x180092996  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18009299b  lea     r9, [rbp+Type]; lpType
0x18009299f  xor     r8d, r8d; lpReserved
0x1800929a2  mov     [rsp+68h+phkResult], r15; lpData
0x1800929a7  lea     rdx, aTelemetryfarmi; "TelemetryFarmId"
0x1800929ae  call    cs:__imp_RegQueryValueExW
0x1800929b5  nop     dword ptr [rax+rax+00h]
0x1800929ba  mov     ebx, eax
0x1800929bc  test    eax, eax
0x1800929be  jle     short loc_1800929C9
0x1800929c0  movzx   ebx, ax
0x1800929c3  or      ebx, 80070000h
0x1800929c9  test    ebx, ebx
0x1800929cb  jns     short loc_180092A28
0x1800929cd  mov     eax, cs:dword_18012E170
0x1800929d3  cmp     eax, 3
0x1800929d6  jbe     loc_180092778
0x1800929dc  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x1800929e3  mov     [rbp+var_18], rax
0x1800929e7  lea     rdx, word_18011703E
0x1800929ee  lea     rax, aRegqueryvaluee_0; "RegQueryValueEx REG_SESSDIR_TELEMETRY_F"...
0x1800929f5  mov     [rbp+var_20], rax
0x1800929f9  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092a00  mov     [rbp+var_28], rax
0x180092a04  lea     rax, [rbp+var_18]
0x180092a08  mov     [rsp+68h+var_30], rax
0x180092a0d  lea     rax, [rbp+arg_0]
0x180092a11  mov     [rsp+68h+var_38], rax
0x180092a16  lea     rax, [rbp+var_20]
0x180092a1a  mov     [rsp+68h+lpcbData], rax
0x180092a1f  lea     rax, [rbp+var_28]
0x180092a23  jmp     loc_18009276B
0x180092a28  cmp     [rbp+Type], 1
0x180092a2c  jz      short loc_180092A93
0x180092a2e  mov     eax, cs:dword_18012E170
0x180092a34  mov     ecx, 80070057h
0x180092a39  mov     ebx, ecx
0x180092a3b  cmp     eax, 3
0x180092a3e  jbe     loc_180092778
0x180092a44  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x180092a4b  mov     [rbp+arg_0], ecx
0x180092a4e  mov     [rbp+var_18], rax
0x180092a52  lea     rdx, word_180116FFA
0x180092a59  lea     rax, aRegSessdirTele; "REG_SESSDIR_TELEMETRY_FARM_ID not REG_S"...
0x180092a60  mov     [rbp+var_20], rax
0x180092a64  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092a6b  mov     [rbp+var_28], rax
0x180092a6f  lea     rax, [rbp+var_18]
0x180092a73  mov     [rsp+68h+var_30], rax
0x180092a78  lea     rax, [rbp+arg_0]
0x180092a7c  mov     [rsp+68h+var_38], rax
0x180092a81  lea     rax, [rbp+var_20]
0x180092a85  mov     [rsp+68h+lpcbData], rax
0x180092a8a  lea     rax, [rbp+var_28]
0x180092a8e  jmp     loc_18009276E
0x180092a93  mov     ecx, [rbp+cbData]
0x180092a96  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180092a9a  cmp     rcx, 202h
0x180092aa1  jnb     short loc_180092AAF
0x180092aa3  xor     eax, eax
0x180092aa5  mov     [rcx+r15], ax
0x180092aaa  jmp     loc_180092778
0x180092aaf  call    __report_rangecheckfailure
```
