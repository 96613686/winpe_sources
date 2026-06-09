# InterruptNotifications::SetCacheState(IServiceExecutionContext *,long,int,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180008ac8`
- end: `0x180009268`
- name: `?SetCacheState@InterruptNotifications@@KAJPEAVIServiceExecutionContext@@JHPEBG111@Z`
- size: `1952`
- prototype: `__int64 __usercall@<rax>(struct IServiceExecutionContext *@<rcx>, int@<edx>, int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006b240`

## callees

- `0x180006ac0`
- `0x180007da0`
- `0x180008ac8`
- `0x18000a354`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180097894`
- `0x1800a4784`
- `0x1800f3854`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008d2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008f0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008ff7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800090b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800091a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000924c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008d2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008f0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008ff7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800090b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800091a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000924c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009209`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009209`

## string_xrefs

- `0x180008b28`: `InterruptNotifications::SetCacheState`
- `0x180008baf`: `InterruptNotifications::SetCacheState`
- `0x180008c44`: `InterruptNotifications::SetCacheState`
- `0x180008c99`: `InterruptNotifications::SetCacheState`
- `0x180008daa`: `InterruptNotifications::SetCacheState`
- `0x180008e05`: `InterruptNotifications::SetCacheState`
- `0x180008ee1`: `InterruptNotifications::SetCacheState`
- `0x180008fc9`: `InterruptNotifications::SetCacheState`
- `0x180009089`: `InterruptNotifications::SetCacheState`
- `0x180008b4c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008bb6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008c4b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008ca0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008db1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008e0c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008ee8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008fd0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180009090`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\interruptnotifications.cpp`
- `0x180008c84`: `hr = pExecutionContext->CreateRegKey(&pRegKey.m_p)`
- `0x180008b9a`: `hr = pSvcWrapper->Impersonate(&client)`
- `0x180008d07`: `hr = HRESULT_FROM_WIN32(pRegKey->Create(hkcu, PPCRL_REG_ACTIONCENTER_KEYPATH, REG_NONE, REG_OPTION_NON_VOLATILE, KEY_READ | KEY_WRITE, nullptr, &disposition))`
- `0x180008d95`: `hr = SetCachePermissions(pServiceExecutionContext)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall InterruptNotifications::SetCacheState(
        struct IServiceExecutionContext *a1,
        unsigned int a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  HKEY v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // rbx
  int v14; // eax
  HKEY *CurrentUserKey; // rax
  HKEY v16; // rcx
  signed int v17; // eax
  const char *v18; // rcx
  unsigned int v19; // r8d
  signed int LastError; // eax
  unsigned int v21; // ebx
  int v22; // eax
  signed int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  signed int v26; // eax
  __int64 v27; // rdx
  signed int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  unsigned int v33; // ebx
  signed int v34; // eax
  signed int v35; // eax
  unsigned int v36; // ebx
  signed int v37; // eax
  signed int v38; // eax
  signed int v39; // eax
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  char *v43; // [rsp+20h] [rbp-D1h]
  unsigned int pExceptionObject; // [rsp+50h] [rbp-A1h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-99h] BYREF
  HANDLE Token; // [rsp+60h] [rbp-91h]
  __int64 v47; // [rsp+70h] [rbp-81h] BYREF
  int v48; // [rsp+78h] [rbp-79h] BYREF
  __int64 v49; // [rsp+80h] [rbp-71h] BYREF
  _QWORD v50[3]; // [rsp+88h] [rbp-69h] BYREF
  _QWORD v51[3]; // [rsp+A0h] [rbp-51h] BYREF
  HKEY v52; // [rsp+B8h] [rbp-39h]
  __int64 v53; // [rsp+C0h] [rbp-31h]
  __int64 v54; // [rsp+C8h] [rbp-29h]
  _QWORD v55[12]; // [rsp+D0h] [rbp-21h] BYREF
  int v56; // [rsp+140h] [rbp+4Fh] BYREF

  v49 = 0;
  v47 = 0;
  memset(v51, 0, sizeof(v51));
  memset(v50, 0, sizeof(v50));
  v11 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v48 = 1;
  v56 = 0;
  v55[0] = "InterruptNotifications::SetCacheState";
  v55[1] = &v56;
  v55[2] = 0;
  v55[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
    "InterruptNotifications::SetCacheState",
    (const char *)0x28C,
    0,
    (const unsigned __int16 *)v43);
  v12 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v13 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, &v49, 0);
  v56 = v14;
  if ( v14 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x299u,
      v14,
      "hr = pSvcWrapper->Impersonate(&client)");
    goto LABEL_91;
  }
  CurrentUserKey = (HKEY *)GetCurrentUserKey(&hKey);
  v16 = *CurrentUserKey;
  if ( *CurrentUserKey )
  {
    *CurrentUserKey = 0;
    v11 = v16;
    v52 = v16;
  }
  if ( hKey )
    RegCloseKey(hKey);
  LODWORD(hKey) = 0;
  Token = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, HKEY *, __int64))(*(_QWORD *)v13 + 96LL))(v13, &hKey, 1) )
  {
    v56 = -2147188475;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x2A1u,
      -2147188475,
      "pSvcWrapper->Revert(&revert)");
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&hKey);
    goto LABEL_91;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 8LL))(v12, &v47);
  v56 = v17;
  if ( v17 < 0 )
  {
    v18 = "hr = pExecutionContext->CreateRegKey(&pRegKey.m_p)";
    v19 = 675;
LABEL_11:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      v19,
      v17,
      v18);
LABEL_12:
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&hKey);
    goto LABEL_91;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, HKEY, const wchar_t *, _QWORD, _DWORD, int, _QWORD, int *))(*(_QWORD *)v47 + 8LL))(
          v47,
          v11,
          L"Software\\Microsoft\\IdentityCRL\\InterruptState",
          0,
          0,
          131103,
          0,
          &v48);
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  v56 = v17;
  if ( v17 < 0 )
  {
    v18 = "hr = HRESULT_FROM_WIN32(pRegKey->Create(hkcu, PPCRL_REG_ACTIONCENTER_KEYPATH, REG_NONE, REG_OPTION_NON_VOLATIL"
          "E, KEY_READ | KEY_WRITE, nullptr, &disposition))";
    v19 = 679;
    goto LABEL_11;
  }
  if ( (_DWORD)hKey )
  {
    if ( !Token )
      goto LABEL_27;
    if ( !SetThreadToken(0, Token) )
    {
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      if ( Token )
        CloseHandle(Token);
      pExceptionObject = v21;
      throw (long *)&pExceptionObject;
    }
  }
  if ( Token )
    CloseHandle(Token);
LABEL_27:
  if ( v48 == 1 )
  {
    v22 = InterruptNotifications::SetCachePermissions(a1);
    v56 = v22;
    if ( v22 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
        "InterruptNotifications::SetCacheState",
        0x2AEu,
        v22,
        "hr = SetCachePermissions(pServiceExecutionContext)");
      goto LABEL_91;
    }
  }
  LODWORD(hKey) = 0;
  Token = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, HKEY *, __int64))(*(_QWORD *)v13 + 96LL))(v13, &hKey, 1) )
  {
    v56 = -2147188475;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x2B4u,
      -2147188475,
      "pSvcWrapper->Revert(&revert)");
    goto LABEL_12;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64))(*(_QWORD *)v47 + 56LL))(
          v47,
          L"AccountSettingsUrl",
          a4,
          1);
  if ( v23 > 0 )
    v23 = (unsigned __int16)v23 | 0x80070000;
  v56 = v23;
  if ( v23 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x2B7u,
      v23,
      "hr = HRESULT_FROM_WIN32(pRegKey->SetStringValue(PPCRL_REG_ACCOUNT_SETTINGS_URL, pAccountSettingUrl))");
    goto LABEL_12;
  }
  v25 = WlidsvcUtil::DelimiterSeperatedToMultiSzString(a5, v24, v51);
  v56 = v25;
  if ( v25 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x2BAu,
      v25,
      "hr = WlidsvcUtil::DelimiterSeperatedToMultiSzString(pTargets, PPCRL_LINEBREAK_DELIMITER, targetMultiSzString)");
    goto LABEL_12;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v47 + 88LL))(
          v47,
          L"NotificationTargets",
          v51[0]);
  if ( v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x80070000;
  v56 = v26;
  if ( v26 >= 0 )
  {
    v30 = WlidsvcUtil::DelimiterSeperatedToMultiSzString(a6, v27, v50);
    v56 = v30;
    if ( v30 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
        "InterruptNotifications::SetCacheState",
        0x2BEu,
        v30,
        "hr = WlidsvcUtil::DelimiterSeperatedToMultiSzString(pPolicies, PPCRL_LINEBREAK_DELIMITER, policyMultiSzString)");
      goto LABEL_12;
    }
    v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v47 + 88LL))(
            v47,
            L"NotificationPolicies",
            v50[0]);
    if ( v31 > 0 )
      v31 = (unsigned __int16)v31 | 0x80070000;
    v56 = v31;
    if ( v31 >= 0 )
    {
      v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64))(*(_QWORD *)v47 + 56LL))(
              v47,
              L"AppId",
              a7,
              1);
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      v56 = v34;
      if ( v34 >= 0 )
      {
        v37 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v47 + 40LL))(
                v47,
                L"InterruptCode",
                a2);
        if ( v37 > 0 )
          v37 = (unsigned __int16)v37 | 0x80070000;
        v56 = v37;
        if ( v37 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
            "InterruptNotifications::SetCacheState",
            0x2C5u,
            v37,
            "hr = HRESULT_FROM_WIN32(pRegKey->SetDWORDValue(PPCRL_REG_ACTIONCENTER_CODE, static_cast<DWORD>(interruptCode)))");
          goto LABEL_12;
        }
        v38 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, bool))(*(_QWORD *)v47 + 40LL))(
                v47,
                L"RootLevelInterrupt",
                a3 != 0);
        if ( v38 > 0 )
          v38 = (unsigned __int16)v38 | 0x80070000;
        v56 = v38;
        if ( v38 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
            "InterruptNotifications::SetCacheState",
            0x2C8u,
            v38,
            "hr = HRESULT_FROM_WIN32(pRegKey->SetDWORDValue(PPCRL_REG_ACTIONCENTER_ROOT_LEVEL_INTERRUPT, (isRootLevelInte"
            "rrupt ? 1 : 0)))");
          goto LABEL_12;
        }
        if ( (_DWORD)hKey )
        {
          if ( !Token )
            goto LABEL_91;
          if ( !SetThreadToken(0, Token) )
          {
            v39 = GetLastError();
            v40 = v39;
            if ( v39 > 0 )
              v40 = (unsigned __int16)v39 | 0x80070000;
            if ( Token )
              CloseHandle(Token);
            pExceptionObject = v40;
            throw (long *)&pExceptionObject;
          }
        }
      }
      else
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
          "InterruptNotifications::SetCacheState",
          0x2C2u,
          v34,
          "hr = HRESULT_FROM_WIN32(pRegKey->SetStringValue(PPCRL_REG_ACTIONCENTER_APPID, pAppId))");
        if ( (_DWORD)hKey )
        {
          if ( !Token )
            goto LABEL_91;
          if ( !SetThreadToken(0, Token) )
          {
            v35 = GetLastError();
            v36 = v35;
            if ( v35 > 0 )
              v36 = (unsigned __int16)v35 | 0x80070000;
            if ( Token )
              CloseHandle(Token);
            pExceptionObject = v36;
            throw (long *)&pExceptionObject;
          }
        }
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
        "InterruptNotifications::SetCacheState",
        0x2BFu,
        v31,
        "hr = HRESULT_FROM_WIN32(pRegKey->SetMultiStringValue(PPCRL_REG_ACTIONCENTER_POLICIES, policyMultiSzString))");
      if ( (_DWORD)hKey )
      {
        if ( !Token )
          goto LABEL_91;
        if ( !SetThreadToken(0, Token) )
        {
          v32 = GetLastError();
          v33 = v32;
          if ( v32 > 0 )
            v33 = (unsigned __int16)v32 | 0x80070000;
          if ( Token )
            CloseHandle(Token);
          pExceptionObject = v33;
          throw (long *)&pExceptionObject;
        }
      }
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\interruptnotifications.cpp",
      "InterruptNotifications::SetCacheState",
      0x2BBu,
      v26,
      "hr = HRESULT_FROM_WIN32(pRegKey->SetMultiStringValue(PPCRL_REG_ACTIONCENTER_TARGETS, targetMultiSzString))");
    if ( (_DWORD)hKey )
    {
      if ( !Token )
        goto LABEL_91;
      if ( !SetThreadToken(0, Token) )
      {
        v28 = GetLastError();
        v29 = v28;
        if ( v28 > 0 )
          v29 = (unsigned __int16)v28 | 0x80070000;
        if ( Token )
          CloseHandle(Token);
        pExceptionObject = v29;
        throw (long *)&pExceptionObject;
      }
    }
  }
  if ( Token )
    CloseHandle(Token);
LABEL_91:
  v41 = v56;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v55);
  if ( v11 )
    RegCloseKey(v11);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v50);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v51);
  if ( v47 )
    (**(void (__fastcall ***)(__int64, __int64))v47)(v47, 1);
  v47 = 0;
  if ( (_DWORD)v49 )
    SetThreadToken(0, 0);
  return v41;
}

```

## disassembly

```asm
0x180008ac8  push    rbp
0x180008aca  push    rbx
0x180008acb  push    rsi
0x180008acc  push    rdi
0x180008acd  push    r12
0x180008acf  push    r13
0x180008ad1  push    r14
0x180008ad3  push    r15
0x180008ad5  lea     rbp, [rsp-7]
0x180008ada  sub     rsp, 0F8h
0x180008ae1  mov     r15, r9
0x180008ae4  mov     r13d, r8d
0x180008ae7  mov     r12d, edx
0x180008aea  mov     r14, rcx
0x180008aed  xor     ecx, ecx
0x180008aef  mov     [rbp+3Fh+var_B0], rcx
0x180008af3  mov     [rsp+130h+var_C0], rcx
0x180008af8  mov     [rbp+3Fh+var_90], rcx
0x180008afc  mov     [rbp+3Fh+var_80], rcx
0x180008b00  mov     [rbp+3Fh+var_88], rcx
0x180008b04  mov     [rbp+3Fh+var_A8], rcx
0x180008b08  mov     [rbp+3Fh+var_98], rcx
0x180008b0c  mov     [rbp+3Fh+var_A0], rcx
0x180008b10  mov     edi, ecx
0x180008b12  mov     [rbp+3Fh+var_78], rcx
0x180008b16  mov     [rbp+3Fh+var_70], rcx
0x180008b1a  mov     [rbp+3Fh+var_68], rcx
0x180008b1e  mov     [rbp+3Fh+var_B8], 1
0x180008b25  mov     [rbp+3Fh+arg_0], ecx
0x180008b28  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008b2f  mov     [rbp+3Fh+var_60], rdx
0x180008b33  lea     rax, [rbp+3Fh+arg_0]
0x180008b37  mov     [rbp+3Fh+var_58], rax
0x180008b3b  mov     [rbp+3Fh+var_50], rcx
0x180008b3f  mov     [rbp+3Fh+var_48], rcx
0x180008b43  xor     r9d, r9d; unsigned int
0x180008b46  mov     r8d, 28Ch; char *
0x180008b4c  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008b53  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180008b58  nop
0x180008b59  mov     rax, [r14]
0x180008b5c  mov     rcx, r14
0x180008b5f  mov     rax, [rax+20h]
0x180008b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b68  mov     rsi, rax
0x180008b6b  mov     rcx, [r14]
0x180008b6e  mov     rax, [rcx+50h]
0x180008b72  mov     rcx, r14
0x180008b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7a  mov     rbx, rax
0x180008b7d  mov     rcx, [rax]
0x180008b80  mov     rax, [rcx+20h]
0x180008b84  xor     r8d, r8d
0x180008b87  lea     rdx, [rbp+3Fh+var_B0]
0x180008b8b  mov     rcx, rbx
0x180008b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b93  mov     [rbp+3Fh+arg_0], eax
0x180008b96  test    eax, eax
0x180008b98  jns     short loc_180008BC9
0x180008b9a  lea     r8, aHrPsvcwrapperI; "hr = pSvcWrapper->Impersonate(&client)"
0x180008ba1  mov     [rsp+130h+var_110], r8; char *
0x180008ba6  mov     r9d, eax; int
0x180008ba9  mov     r8d, 299h; unsigned int
0x180008baf  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008bb6  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008bbd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008bc2  xor     esi, esi
0x180008bc4  jmp     loc_1800091F4
0x180008bc9  lea     rcx, [rsp+130h+hKey]
0x180008bce  call    ?GetCurrentUserKey@@YA?AVCRegKey@ATL@@XZ; GetCurrentUserKey(void)
0x180008bd3  mov     rcx, [rax]
0x180008bd6  test    rcx, rcx
0x180008bd9  jz      short loc_180008BE9
0x180008bdb  mov     qword ptr [rax], 0
0x180008be2  mov     rdi, rcx
0x180008be5  mov     [rbp+3Fh+var_78], rcx
0x180008be9  mov     rcx, [rsp+130h+hKey]; hKey
0x180008bee  test    rcx, rcx
0x180008bf1  jz      short loc_180008BF9
0x180008bf3  call    cs:__imp_RegCloseKey
0x180008bf9  mov     dword ptr [rsp+130h+hKey], 0
0x180008c01  mov     [rsp+130h+Token], 0
0x180008c0a  mov     rax, [rbx]
0x180008c0d  mov     r8d, 1
0x180008c13  lea     rdx, [rsp+130h+hKey]
0x180008c18  mov     rcx, rbx
0x180008c1b  mov     rax, [rax+60h]
0x180008c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c24  test    eax, eax
0x180008c26  jnz     short loc_180008C67
0x180008c28  mov     r9d, 80048105h; int
0x180008c2e  mov     [rbp+3Fh+arg_0], r9d
0x180008c32  lea     rax, aPsvcwrapperRev; "pSvcWrapper->Revert(&revert)"
0x180008c39  mov     [rsp+130h+var_110], rax; char *
0x180008c3e  mov     r8d, 2A1h; unsigned int
0x180008c44  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008c4b  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008c52  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008c57  nop
0x180008c58  lea     rcx, [rsp+130h+hKey]; this
0x180008c5d  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x180008c62  jmp     loc_180008BC2
0x180008c67  mov     rax, [rsi]
0x180008c6a  lea     rdx, [rsp+130h+var_C0]
0x180008c6f  mov     rcx, rsi
0x180008c72  mov     rax, [rax+8]
0x180008c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7b  mov     [rbp+3Fh+arg_0], eax
0x180008c7e  xor     esi, esi
0x180008c80  test    eax, eax
0x180008c82  jns     short loc_180008CBC
0x180008c84  lea     rcx, aHrPexecutionco_0; "hr = pExecutionContext->CreateRegKey(&p"...
0x180008c8b  mov     r8d, 2A3h; unsigned int
0x180008c91  mov     r9d, eax; int
0x180008c94  mov     [rsp+130h+var_110], rcx; char *
0x180008c99  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008ca0  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008ca7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008cac  nop
0x180008cad  lea     rcx, [rsp+130h+hKey]; this
0x180008cb2  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x180008cb7  jmp     loc_1800091F4
0x180008cbc  mov     rcx, [rsp+130h+var_C0]
0x180008cc1  mov     rax, [rcx]
0x180008cc4  lea     rdx, [rbp+3Fh+var_B8]
0x180008cc8  mov     [rsp+130h+var_F8], rdx
0x180008ccd  mov     [rsp+130h+var_100], rsi
0x180008cd2  mov     [rsp+130h+var_108], 2001Fh
0x180008cda  mov     dword ptr [rsp+130h+var_110], esi
0x180008cde  xor     r9d, r9d
0x180008ce1  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\IdentityCRL\\Inter"...
0x180008ce8  mov     rdx, rdi
0x180008ceb  mov     rax, [rax+8]
0x180008cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf4  test    eax, eax
0x180008cf6  jle     short loc_180008D00
0x180008cf8  movzx   eax, ax
0x180008cfb  or      eax, 80070000h
0x180008d00  mov     [rbp+3Fh+arg_0], eax
0x180008d03  test    eax, eax
0x180008d05  jns     short loc_180008D19
0x180008d07  lea     rcx, aHrHresultFromW_35; "hr = HRESULT_FROM_WIN32(pRegKey->Create"...
0x180008d0e  mov     r8d, 2A7h
0x180008d14  jmp     loc_180008C91
0x180008d19  cmp     dword ptr [rsp+130h+hKey], esi
0x180008d1d  jz      short loc_180008D70
0x180008d1f  mov     rdx, [rsp+130h+Token]; Token
0x180008d24  test    rdx, rdx
0x180008d27  jz      short loc_180008D80
0x180008d29  xor     ecx, ecx; Thread
0x180008d2b  call    cs:__imp_SetThreadToken
0x180008d31  test    eax, eax
0x180008d33  jnz     short loc_180008D70
0x180008d35  call    cs:__imp_GetLastError
0x180008d3b  mov     ebx, eax
0x180008d3d  test    eax, eax
0x180008d3f  jle     short loc_180008D4A
0x180008d41  movzx   ebx, ax
0x180008d44  or      ebx, 80070000h
0x180008d4a  mov     rcx, [rsp+130h+Token]; hObject
0x180008d4f  test    rcx, rcx
0x180008d52  jz      short loc_180008D5A
0x180008d54  call    cs:__imp_CloseHandle
0x180008d5a  mov     [rsp+130h+pExceptionObject], ebx
0x180008d5e  lea     rdx, _TI1J; pThrowInfo
0x180008d65  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180008d6a  call    _CxxThrowException_0
0x180008d70  mov     rcx, [rsp+130h+Token]; hObject
0x180008d75  test    rcx, rcx
0x180008d78  jz      short loc_180008D80
0x180008d7a  call    cs:__imp_CloseHandle
0x180008d80  cmp     [rbp+3Fh+var_B8], 1
0x180008d84  jnz     short loc_180008DC2
0x180008d86  mov     rcx, r14; struct IServiceExecutionContext *
0x180008d89  call    ?SetCachePermissions@InterruptNotifications@@KAJPEAVIServiceExecutionContext@@@Z; InterruptNotifications::SetCachePermissions(IServiceExecutionContext *)
0x180008d8e  mov     [rbp+3Fh+arg_0], eax
0x180008d91  test    eax, eax
0x180008d93  jns     short loc_180008DC2
0x180008d95  lea     rcx, aHrSetcacheperm; "hr = SetCachePermissions(pServiceExecut"...
0x180008d9c  mov     [rsp+130h+var_110], rcx; char *
0x180008da1  mov     r9d, eax; int
0x180008da4  mov     r8d, 2AEh; unsigned int
0x180008daa  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008db1  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008db8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008dbd  jmp     loc_1800091F4
0x180008dc2  mov     dword ptr [rsp+130h+hKey], esi
0x180008dc6  mov     [rsp+130h+Token], rsi
0x180008dcb  mov     rax, [rbx]
0x180008dce  mov     r8d, 1
0x180008dd4  lea     rdx, [rsp+130h+hKey]
0x180008dd9  mov     rcx, rbx
0x180008ddc  mov     rax, [rax+60h]
0x180008de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de5  test    eax, eax
0x180008de7  jnz     short loc_180008E1E
0x180008de9  mov     r9d, 80048105h; int
0x180008def  mov     [rbp+3Fh+arg_0], r9d
0x180008df3  lea     rax, aPsvcwrapperRev; "pSvcWrapper->Revert(&revert)"
0x180008dfa  mov     [rsp+130h+var_110], rax; char *
0x180008dff  mov     r8d, 2B4h; unsigned int
0x180008e05  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008e0c  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008e13  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008e18  nop
0x180008e19  jmp     loc_180008CAD
0x180008e1e  mov     rcx, [rsp+130h+var_C0]
0x180008e23  mov     rax, [rcx]
0x180008e26  mov     r9d, 1
0x180008e2c  mov     r8, r15
0x180008e2f  lea     rdx, aAccountsetting; "AccountSettingsUrl"
0x180008e36  mov     rax, [rax+38h]
0x180008e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e3f  mov     r14d, 80070000h
0x180008e45  test    eax, eax
0x180008e47  jle     short loc_180008E4F
0x180008e49  movzx   eax, ax
0x180008e4c  or      eax, r14d
0x180008e4f  mov     [rbp+3Fh+arg_0], eax
0x180008e52  test    eax, eax
0x180008e54  jns     short loc_180008E6D
0x180008e56  lea     rcx, aHrHresultFromW_30; "hr = HRESULT_FROM_WIN32(pRegKey->SetStr"...
0x180008e5d  mov     [rsp+130h+var_110], rcx
0x180008e62  mov     r9d, eax
0x180008e65  mov     r8d, 2B7h
0x180008e6b  jmp     short loc_180008E05
0x180008e6d  lea     r8, [rbp+3Fh+var_90]
0x180008e71  mov     rcx, [rbp+3Fh+arg_20]
0x180008e75  call    ?DelimiterSeperatedToMultiSzString@WlidsvcUtil@@SAJPEBG0AEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@@Z; WlidsvcUtil::DelimiterSeperatedToMultiSzString(ushort const *,ushort const *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &)
0x180008e7a  mov     [rbp+3Fh+arg_0], eax
0x180008e7d  test    eax, eax
0x180008e7f  jns     short loc_180008E9B
0x180008e81  lea     rcx, aHrWlidsvcutilD_0; "hr = WlidsvcUtil::DelimiterSeperatedToM"...
0x180008e88  mov     [rsp+130h+var_110], rcx
0x180008e8d  mov     r9d, eax
0x180008e90  mov     r8d, 2BAh
0x180008e96  jmp     loc_180008E05
0x180008e9b  mov     rcx, [rsp+130h+var_C0]
0x180008ea0  mov     rax, [rcx]
0x180008ea3  mov     r8, [rbp+3Fh+var_90]
0x180008ea7  lea     rdx, aNotificationta; "NotificationTargets"
0x180008eae  mov     rax, [rax+58h]
0x180008eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb7  test    eax, eax
0x180008eb9  jle     short loc_180008EC1
0x180008ebb  movzx   eax, ax
0x180008ebe  or      eax, r14d
0x180008ec1  mov     [rbp+3Fh+arg_0], eax
0x180008ec4  test    eax, eax
0x180008ec6  jns     loc_180008F55
0x180008ecc  lea     rcx, aHrHresultFromW_31; "hr = HRESULT_FROM_WIN32(pRegKey->SetMul"...
0x180008ed3  mov     [rsp+130h+var_110], rcx; char *
0x180008ed8  mov     r9d, eax; int
0x180008edb  mov     r8d, 2BBh; unsigned int
0x180008ee1  lea     rdx, aInterruptnotif_8; "InterruptNotifications::SetCacheState"
0x180008ee8  lea     rcx, aOnecoreuapDsEx_90; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180008eef  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180008ef4  nop
0x180008ef5  cmp     dword ptr [rsp+130h+hKey], esi
0x180008ef9  jz      loc_1800091E4
0x180008eff  mov     rdx, [rsp+130h+Token]; Token
0x180008f04  test    rdx, rdx
0x180008f07  jz      loc_1800091F4
0x180008f0d  xor     ecx, ecx; Thread
0x180008f0f  call    cs:__imp_SetThreadToken
0x180008f15  test    eax, eax
0x180008f17  jnz     loc_1800091E4
0x180008f1d  call    cs:__imp_GetLastError
0x180008f23  mov     ebx, eax
0x180008f25  test    eax, eax
0x180008f27  jle     short loc_180008F2F
0x180008f29  movzx   ebx, ax
0x180008f2c  or      ebx, r14d
0x180008f2f  mov     rcx, [rsp+130h+Token]; hObject
0x180008f34  test    rcx, rcx
0x180008f37  jz      short loc_180008F3F
0x180008f39  call    cs:__imp_CloseHandle
0x180008f3f  mov     [rsp+130h+pExceptionObject], ebx
0x180008f43  lea     rdx, _TI1J; pThrowInfo
0x180008f4a  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180008f4f  call    _CxxThrowException_0
0x180008f55  lea     r8, [rbp+3Fh+var_A8]
0x180008f59  mov     rcx, [rbp+3Fh+arg_28]
0x180008f5d  call    ?DelimiterSeperatedToMultiSzString@WlidsvcUtil@@SAJPEBG0AEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@@Z; WlidsvcUtil::DelimiterSeperatedToMultiSzString(ushort const *,ushort const *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &)
0x180008f62  mov     [rbp+3Fh+arg_0], eax
0x180008f65  test    eax, eax
0x180008f67  jns     short loc_180008F83
0x180008f69  lea     rcx, aHrWlidsvcutilD; "hr = WlidsvcUtil::DelimiterSeperatedToM"...
0x180008f70  mov     [rsp+130h+var_110], rcx
0x180008f75  mov     r9d, eax
0x180008f78  mov     r8d, 2BEh
0x180008f7e  jmp     loc_180008E05
0x180008f83  mov     rcx, [rsp+130h+var_C0]
0x180008f88  mov     rax, [rcx]
0x180008f8b  mov     r8, [rbp+3Fh+var_A8]
0x180008f8f  lea     rdx, aNotificationpo; "NotificationPolicies"
0x180008f96  mov     rax, [rax+58h]
0x180008f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9f  test    eax, eax
0x180008fa1  jle     short loc_180008FA9
  ... truncated ...
```
