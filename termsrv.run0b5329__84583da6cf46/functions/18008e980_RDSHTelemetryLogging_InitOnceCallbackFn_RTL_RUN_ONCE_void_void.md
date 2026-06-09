# RDSHTelemetryLogging::InitOnceCallbackFn(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18008e980`
- end: `0x18008ed4a`
- name: `?InitOnceCallbackFn@RDSHTelemetryLogging@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `970`
- prototype: `__int64 __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f264`
- `0x18008fb70`

## callees

- `0x180001688`
- `0x180032790`
- `0x18008e778`
- `0x18008e980`
- `0x1800c4290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008ea45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008ea45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008eb24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ec49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008eb24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ec49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ea39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ea39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ea83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ea83`

## string_xrefs

- `0x18008eab9`: `RegOpenKeyEx REG_CONTROL_SESSDIR_TELEMETRY_KEY failed`

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
    v6 = dword_180128170;
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_5;
    v16 = "InitOnceCallbackFn";
    v7 = &word_1801110CE;
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
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v19 = -2147024809;
          v18[0] = "InitOnceCallbackFn";
          v17 = "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not REG_SZ";
          v16 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            -2147024809,
            (unsigned int)word_180111002,
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
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v18[0] = "InitOnceCallbackFn";
            v7 = &word_180110FBE;
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
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v19 = -2147024809;
            v18[0] = "InitOnceCallbackFn";
            v17 = "REG_SESSDIR_TELEMETRY_FARM_ID not REG_SZ";
            v16 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              -2147024809,
              (unsigned int)word_180110F7A,
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
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v18[0] = "InitOnceCallbackFn";
      v7 = &word_180111046;
      v17 = "RegQueryValueEx REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID failed";
      v16 = "Warning HResult failed";
      v15 = (const char **)v18;
      v8 = &v16;
      goto LABEL_4;
    }
  }
  else if ( (unsigned int)dword_180128170 > 3 )
  {
    v18[0] = "InitOnceCallbackFn";
    v7 = word_18011108A;
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
0x18008e980  mov     qword ptr [rsp-20h+cbData], r8
0x18008e985  mov     qword ptr [rsp-20h+Type], rdx
0x18008e98a  mov     qword ptr [rsp-20h+arg_0], rcx
0x18008e98f  push    rbp
0x18008e990  push    rbx
0x18008e991  push    r12
0x18008e993  push    r15
0x18008e995  mov     rbp, rsp
0x18008e998  sub     rsp, 68h
0x18008e99c  lea     rcx, [rbp+arg_0]; unsigned int *
0x18008e9a0  mov     [rbp+hKey], 0
0x18008e9a8  mov     [rbp+Type], 0
0x18008e9af  mov     [rbp+cbData], 0
0x18008e9b6  mov     [rbp+arg_0], 0
0x18008e9bd  call    ?GetSessDirActive@RDSHTelemetryLogging@@CAJPEAK@Z; RDSHTelemetryLogging::GetSessDirActive(ulong *)
0x18008e9c2  mov     ebx, eax
0x18008e9c4  test    eax, eax
0x18008e9c6  jns     loc_18008EA5D
0x18008e9cc  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr) == true")
0x18008e9d1  mov     ecx, cs:dword_180128170
0x18008e9d7  cmp     ecx, 3
0x18008e9da  jbe     short loc_18008EA30
0x18008e9dc  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008e9e3  mov     [rbp+var_28], rax
0x18008e9e7  lea     rdx, word_1801110CE
0x18008e9ee  lea     rax, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD"
0x18008e9f5  mov     [rbp+var_20], rax
0x18008e9f9  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008ea00  mov     [rbp+var_18], rax
0x18008ea04  lea     rax, [rbp+var_28]
0x18008ea08  mov     [rsp+68h+var_30], rax
0x18008ea0d  lea     rax, [rbp+arg_0]
0x18008ea11  mov     [rsp+68h+var_38], rax
0x18008ea16  lea     rax, [rbp+var_20]
0x18008ea1a  mov     [rsp+68h+lpcbData], rax
0x18008ea1f  lea     rax, [rbp+var_18]
0x18008ea23  mov     [rbp+arg_0], ebx
0x18008ea26  mov     [rsp+68h+phkResult], rax
0x18008ea2b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008ea30  mov     rcx, [rbp+hKey]; hKey
0x18008ea34  test    rcx, rcx
0x18008ea37  jz      short loc_18008EA3F
0x18008ea39  call    cs:__imp_RegCloseKey
0x18008ea3f  test    ebx, ebx
0x18008ea41  jns     short loc_18008EA4B
0x18008ea43  mov     ecx, ebx; dwErrCode
0x18008ea45  call    cs:__imp_SetLastError
0x18008ea4b  not     ebx
0x18008ea4d  shr     ebx, 1Fh
0x18008ea50  mov     eax, ebx
0x18008ea52  add     rsp, 68h
0x18008ea56  pop     r15
0x18008ea58  pop     r12
0x18008ea5a  pop     rbx
0x18008ea5b  pop     rbp
0x18008ea5c  retn
0x18008ea5d  cmp     [rbp+arg_0], 0
0x18008ea61  jz      short loc_18008EA30
0x18008ea63  lea     rax, [rbp+hKey]
0x18008ea67  mov     r9d, 20019h; samDesired
0x18008ea6d  xor     r8d, r8d; ulOptions
0x18008ea70  mov     [rsp+68h+phkResult], rax; phkResult
0x18008ea75  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Ter"...
0x18008ea7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008ea83  call    cs:__imp_RegOpenKeyExW
0x18008ea89  mov     ebx, eax
0x18008ea8b  test    eax, eax
0x18008ea8d  jle     short loc_18008EA98
0x18008ea8f  movzx   ebx, ax
0x18008ea92  or      ebx, 80070000h
0x18008ea98  test    ebx, ebx
0x18008ea9a  jns     short loc_18008EAF3
0x18008ea9c  mov     eax, cs:dword_180128170
0x18008eaa2  cmp     eax, 3
0x18008eaa5  jbe     short loc_18008EA30
0x18008eaa7  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008eaae  mov     [rbp+var_18], rax
0x18008eab2  lea     rdx, word_18011108A
0x18008eab9  lea     rax, aRegopenkeyexRe; "RegOpenKeyEx REG_CONTROL_SESSDIR_TELEME"...
0x18008eac0  mov     [rbp+var_20], rax
0x18008eac4  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008eacb  mov     [rbp+var_28], rax
0x18008eacf  lea     rax, [rbp+var_18]
0x18008ead3  mov     [rsp+68h+var_30], rax
0x18008ead8  lea     rax, [rbp+arg_0]
0x18008eadc  mov     [rsp+68h+var_38], rax
0x18008eae1  lea     rax, [rbp+var_20]
0x18008eae5  mov     [rsp+68h+lpcbData], rax
0x18008eaea  lea     rax, [rbp+var_28]
0x18008eaee  jmp     loc_18008EA23
0x18008eaf3  mov     rcx, [rbp+hKey]; hKey
0x18008eaf7  lea     rax, [rbp+cbData]
0x18008eafb  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18008eb00  lea     r12, ?m_DeploymentId@RDSHTelemetryLogging@@0PAGA; ushort near * RDSHTelemetryLogging::m_DeploymentId
0x18008eb07  mov     r15d, 200h
0x18008eb0d  mov     [rsp+68h+phkResult], r12; lpData
0x18008eb12  lea     r9, [rbp+Type]; lpType
0x18008eb16  mov     [rbp+cbData], r15d
0x18008eb1a  xor     r8d, r8d; lpReserved
0x18008eb1d  lea     rdx, aTelemetrydeplo; "TelemetryDeploymentId"
0x18008eb24  call    cs:__imp_RegQueryValueExW
0x18008eb2a  mov     ebx, eax
0x18008eb2c  test    eax, eax
0x18008eb2e  jle     short loc_18008EB39
0x18008eb30  movzx   ebx, ax
0x18008eb33  or      ebx, 80070000h
0x18008eb39  test    ebx, ebx
0x18008eb3b  jns     short loc_18008EB98
0x18008eb3d  mov     eax, cs:dword_180128170
0x18008eb43  cmp     eax, 3
0x18008eb46  jbe     loc_18008EA30
0x18008eb4c  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008eb53  mov     [rbp+var_18], rax
0x18008eb57  lea     rdx, word_180111046
0x18008eb5e  lea     rax, aRegqueryvaluee; "RegQueryValueEx REG_SESSDIR_TELEMETRY_D"...
0x18008eb65  mov     [rbp+var_20], rax
0x18008eb69  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008eb70  mov     [rbp+var_28], rax
0x18008eb74  lea     rax, [rbp+var_18]
0x18008eb78  mov     [rsp+68h+var_30], rax
0x18008eb7d  lea     rax, [rbp+arg_0]
0x18008eb81  mov     [rsp+68h+var_38], rax
0x18008eb86  lea     rax, [rbp+var_20]
0x18008eb8a  mov     [rsp+68h+lpcbData], rax
0x18008eb8f  lea     rax, [rbp+var_28]
0x18008eb93  jmp     loc_18008EA23
0x18008eb98  cmp     [rbp+Type], 1
0x18008eb9c  jz      short loc_18008EC03
0x18008eb9e  mov     eax, cs:dword_180128170
0x18008eba4  mov     ecx, 80070057h
0x18008eba9  mov     ebx, ecx
0x18008ebab  cmp     eax, 3
0x18008ebae  jbe     loc_18008EA30
0x18008ebb4  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008ebbb  mov     [rbp+arg_0], ecx
0x18008ebbe  mov     [rbp+var_18], rax
0x18008ebc2  lea     rdx, word_180111002
0x18008ebc9  lea     rax, aRegSessdirTele_0; "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not"...
0x18008ebd0  mov     [rbp+var_20], rax
0x18008ebd4  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008ebdb  mov     [rbp+var_28], rax
0x18008ebdf  lea     rax, [rbp+var_18]
0x18008ebe3  mov     [rsp+68h+var_30], rax
0x18008ebe8  lea     rax, [rbp+arg_0]
0x18008ebec  mov     [rsp+68h+var_38], rax
0x18008ebf1  lea     rax, [rbp+var_20]
0x18008ebf5  mov     [rsp+68h+lpcbData], rax
0x18008ebfa  lea     rax, [rbp+var_28]
0x18008ebfe  jmp     loc_18008EA26
0x18008ec03  mov     ecx, [rbp+cbData]
0x18008ec06  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18008ec0a  cmp     rcx, 202h
0x18008ec11  jnb     loc_18008ED44
0x18008ec17  xor     eax, eax
0x18008ec19  mov     [rbp+cbData], r15d
0x18008ec1d  mov     [rcx+r12], ax
0x18008ec22  lea     r15, ?m_FarmId@RDSHTelemetryLogging@@0PAGA; ushort near * RDSHTelemetryLogging::m_FarmId
0x18008ec29  mov     rcx, [rbp+hKey]; hKey
0x18008ec2d  lea     rax, [rbp+cbData]
0x18008ec31  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18008ec36  lea     r9, [rbp+Type]; lpType
0x18008ec3a  xor     r8d, r8d; lpReserved
0x18008ec3d  mov     [rsp+68h+phkResult], r15; lpData
0x18008ec42  lea     rdx, aTelemetryfarmi; "TelemetryFarmId"
0x18008ec49  call    cs:__imp_RegQueryValueExW
0x18008ec4f  mov     ebx, eax
0x18008ec51  test    eax, eax
0x18008ec53  jle     short loc_18008EC5E
0x18008ec55  movzx   ebx, ax
0x18008ec58  or      ebx, 80070000h
0x18008ec5e  test    ebx, ebx
0x18008ec60  jns     short loc_18008ECBD
0x18008ec62  mov     eax, cs:dword_180128170
0x18008ec68  cmp     eax, 3
0x18008ec6b  jbe     loc_18008EA30
0x18008ec71  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008ec78  mov     [rbp+var_18], rax
0x18008ec7c  lea     rdx, word_180110FBE
0x18008ec83  lea     rax, aRegqueryvaluee_0; "RegQueryValueEx REG_SESSDIR_TELEMETRY_F"...
0x18008ec8a  mov     [rbp+var_20], rax
0x18008ec8e  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008ec95  mov     [rbp+var_28], rax
0x18008ec99  lea     rax, [rbp+var_18]
0x18008ec9d  mov     [rsp+68h+var_30], rax
0x18008eca2  lea     rax, [rbp+arg_0]
0x18008eca6  mov     [rsp+68h+var_38], rax
0x18008ecab  lea     rax, [rbp+var_20]
0x18008ecaf  mov     [rsp+68h+lpcbData], rax
0x18008ecb4  lea     rax, [rbp+var_28]
0x18008ecb8  jmp     loc_18008EA23
0x18008ecbd  cmp     [rbp+Type], 1
0x18008ecc1  jz      short loc_18008ED28
0x18008ecc3  mov     eax, cs:dword_180128170
0x18008ecc9  mov     ecx, 80070057h
0x18008ecce  mov     ebx, ecx
0x18008ecd0  cmp     eax, 3
0x18008ecd3  jbe     loc_18008EA30
0x18008ecd9  lea     rax, aInitoncecallba; "InitOnceCallbackFn"
0x18008ece0  mov     [rbp+arg_0], ecx
0x18008ece3  mov     [rbp+var_18], rax
0x18008ece7  lea     rdx, word_180110F7A
0x18008ecee  lea     rax, aRegSessdirTele; "REG_SESSDIR_TELEMETRY_FARM_ID not REG_S"...
0x18008ecf5  mov     [rbp+var_20], rax
0x18008ecf9  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008ed00  mov     [rbp+var_28], rax
0x18008ed04  lea     rax, [rbp+var_18]
0x18008ed08  mov     [rsp+68h+var_30], rax
0x18008ed0d  lea     rax, [rbp+arg_0]
0x18008ed11  mov     [rsp+68h+var_38], rax
0x18008ed16  lea     rax, [rbp+var_20]
0x18008ed1a  mov     [rsp+68h+lpcbData], rax
0x18008ed1f  lea     rax, [rbp+var_28]
0x18008ed23  jmp     loc_18008EA26
0x18008ed28  mov     ecx, [rbp+cbData]
0x18008ed2b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18008ed2f  cmp     rcx, 202h
0x18008ed36  jnb     short loc_18008ED44
0x18008ed38  xor     eax, eax
0x18008ed3a  mov     [rcx+r15], ax
0x18008ed3f  jmp     loc_18008EA30
0x18008ed44  call    __report_rangecheckfailure
```
