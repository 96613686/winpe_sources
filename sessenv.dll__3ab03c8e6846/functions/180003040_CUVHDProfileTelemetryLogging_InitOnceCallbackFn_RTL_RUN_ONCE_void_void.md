# CUVHDProfileTelemetryLogging::InitOnceCallbackFn(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180003040`
- end: `0x1800033d0`
- name: `?InitOnceCallbackFn@CUVHDProfileTelemetryLogging@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `912`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004620`
- `0x1800337b0`

## callees

- `0x180003040`
- `0x180003f30`
- `0x18001a870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000322a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000322a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000308a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003264`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000308a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003264`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003129`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003357`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003129`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000321e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000321e`

## string_xrefs

- `0x1800030ad`: `RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s`
- `0x180003122`: `TSAppCompat`
- `0x1800030e7`: `SessionDirectoryActive`
- `0x18000314c`: `RegQueryValueEx REG_TERMSRV_APPCOMPAT failed failed: 0x%x in %s`
- `0x1800031d1`: `REG_TERMSRV_APPCOMPAT not REG_DWORD failed: 0x%x in %s`
- `0x180003287`: `RegOpenKeyEx REG_CONTROL_SESSDIR_TELEMETRY_KEY failed failed: 0x%x in %s`

## pseudocode

```c
_BOOL8 __fastcall CUVHDProfileTelemetryLogging::InitOnceCallbackFn(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  int v3; // edi
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  unsigned __int64 v11; // rcx
  LSTATUS v12; // eax
  unsigned __int64 v13; // rcx
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+34h] [rbp-34h] BYREF
  DWORD v16; // [rsp+38h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-2Ch] BYREF
  BYTE v18[8]; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  DWORD lpcbData; // [rsp+A8h] [rbp+40h] BYREF

  phkResult = 0;
  v16 = 0;
  lpcbData = 0;
  hKey = 0;
  v3 = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v18 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s",
      v5,
      "CUVHDProfileTelemetryLogging::GetRoleStatus");
    goto LABEL_20;
  }
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"SessionDirectoryActive", 0, &Type, Data, &cbData);
  v5 = v6;
  if ( v6 == 2 )
  {
    *(_DWORD *)Data = 0;
  }
  else
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegQueryValueEx REG_TS_SESSDIRACTIVE failed failed: 0x%x in %s",
        v5,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
      goto LABEL_20;
    }
    if ( Type != 4 )
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_TS_SESSDIRACTIVE not REG_DWORD failed: 0x%x in %s",
        -2147024809,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
      goto LABEL_20;
    }
  }
  cbData = 4;
  v7 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, v18, &cbData);
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( Type == 4 )
    {
      v3 = *(_DWORD *)Data;
    }
    else
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_TERMSRV_APPCOMPAT not REG_DWORD failed: 0x%x in %s",
        -2147024809,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "RegQueryValueEx REG_TERMSRV_APPCOMPAT failed failed: 0x%x in %s",
      v5,
      "CUVHDProfileTelemetryLogging::GetRoleStatus");
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "REG_TS_SESSDIRACTIVE not REG_DWORD failed: 0x%x in %s",
      (unsigned int)v5,
      "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
    goto LABEL_24;
  }
  if ( v3 )
  {
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM",
           0,
           0x20019u,
           &phkResult);
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegOpenKeyEx REG_CONTROL_SESSDIR_TELEMETRY_KEY failed failed: 0x%x in %s",
        (unsigned int)v5,
        "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
      goto LABEL_24;
    }
    lpcbData = 512;
    v10 = RegQueryValueExW(
            phkResult,
            L"TelemetryDeploymentId",
            0,
            &v16,
            &CUVHDProfileTelemetryLogging::m_DeploymentId,
            &lpcbData);
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegQueryValueEx REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID failed failed: 0x%x in %s",
        (unsigned int)v5,
        "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
      goto LABEL_24;
    }
    if ( v16 != 1 )
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not REG_SZ failed: 0x%x in %s",
        2147942487LL,
        "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
      goto LABEL_24;
    }
    v11 = lpcbData & 0xFFFFFFFE;
    if ( v11 >= 0x202 )
      goto LABEL_49;
    *(_WORD *)(&CUVHDProfileTelemetryLogging::m_DeploymentId + v11) = 0;
    lpcbData = 512;
    v12 = RegQueryValueExW(phkResult, L"TelemetryFarmId", 0, &v16, &CUVHDProfileTelemetryLogging::m_FarmId, &lpcbData);
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegQueryValueEx REG_SESSDIR_TELEMETRY_FARM_ID failed failed: 0x%x in %s",
        (unsigned int)v5,
        "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
      goto LABEL_24;
    }
    if ( v16 != 1 )
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_SESSDIR_TELEMETRY_FARM_ID not REG_SZ failed: 0x%x in %s",
        2147942487LL,
        "CUVHDProfileTelemetryLogging::InitOnceCallbackFn");
      goto LABEL_24;
    }
    v13 = lpcbData & 0xFFFFFFFE;
    if ( v13 >= 0x202 )
LABEL_49:
      _report_rangecheckfailure();
    *(_WORD *)(&CUVHDProfileTelemetryLogging::m_FarmId + v13) = 0;
    CUVHDProfileTelemetryLogging::m_TelemetryEnabled = 1;
  }
LABEL_24:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 < 0 )
    SetLastError(v5);
  return v5 >= 0;
}

```

## disassembly

```asm
0x180003040  push    rbp
0x180003042  push    rbx
0x180003043  push    rsi
0x180003044  push    rdi
0x180003045  mov     rbp, rsp
0x180003048  sub     rsp, 68h
0x18000304c  xor     esi, esi
0x18000304e  lea     rax, [rbp+hKey]
0x180003052  mov     r9d, 20019h; samDesired
0x180003058  mov     [rbp+var_18], rsi
0x18000305c  xor     r8d, r8d; ulOptions
0x18000305f  mov     [rbp+var_30], esi
0x180003062  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180003069  mov     [rbp+arg_18], esi
0x18000306c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003073  mov     [rbp+hKey], rsi
0x180003077  mov     edi, esi
0x180003079  mov     [rbp+Type], esi
0x18000307c  mov     [rbp+cbData], esi
0x18000307f  mov     dword ptr [rbp+Data], esi
0x180003082  mov     dword ptr [rbp+var_28], esi
0x180003085  mov     [rsp+68h+phkResult], rax; phkResult
0x18000308a  call    cs:__imp_RegOpenKeyExW
0x180003090  mov     ebx, eax
0x180003092  test    eax, eax
0x180003094  jle     short loc_18000309F
0x180003096  movzx   ebx, ax
0x180003099  or      ebx, 80070000h
0x18000309f  test    ebx, ebx
0x1800030a1  jns     short loc_1800030C3
0x1800030a3  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x1800030aa  mov     r8d, ebx
0x1800030ad  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"...
0x1800030b4  mov     ecx, 8; int
0x1800030b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800030be  jmp     loc_1800031E7
0x1800030c3  mov     rcx, [rbp+hKey]; hKey
0x1800030c7  lea     rax, [rbp+cbData]
0x1800030cb  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800030d0  lea     r9, [rbp+Type]; lpType
0x1800030d4  lea     rax, [rbp+Data]
0x1800030d8  mov     [rbp+cbData], 4
0x1800030df  xor     r8d, r8d; lpReserved
0x1800030e2  mov     [rsp+68h+phkResult], rax; lpData
0x1800030e7  lea     rdx, aSessiondirecto; "SessionDirectoryActive"
0x1800030ee  call    cs:__imp_RegQueryValueExW
0x1800030f4  mov     ebx, eax
0x1800030f6  cmp     eax, 2
0x1800030f9  jnz     short loc_180003162
0x1800030fb  mov     dword ptr [rbp+Data], esi
0x1800030fe  mov     rcx, [rbp+hKey]; hKey
0x180003102  lea     rax, [rbp+cbData]
0x180003106  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000310b  lea     r9, [rbp+Type]; lpType
0x18000310f  lea     rax, [rbp+var_28]
0x180003113  mov     [rbp+cbData], 4
0x18000311a  xor     r8d, r8d; lpReserved
0x18000311d  mov     [rsp+68h+phkResult], rax; lpData
0x180003122  lea     rdx, aTsappcompat; "TSAppCompat"
0x180003129  call    cs:__imp_RegQueryValueExW
0x18000312f  mov     ebx, eax
0x180003131  test    eax, eax
0x180003133  jle     short loc_18000313E
0x180003135  movzx   ebx, ax
0x180003138  or      ebx, 80070000h
0x18000313e  test    ebx, ebx
0x180003140  jns     short loc_1800031BC
0x180003142  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180003149  mov     r8d, ebx
0x18000314c  lea     rdx, aRegqueryvaluee_1; "RegQueryValueEx REG_TERMSRV_APPCOMPAT f"...
0x180003153  mov     ecx, 8; int
0x180003158  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000315d  jmp     loc_1800031E7
0x180003162  test    eax, eax
0x180003164  jle     short loc_18000316F
0x180003166  movzx   ebx, ax
0x180003169  or      ebx, 80070000h
0x18000316f  test    ebx, ebx
0x180003171  jns     short loc_180003190
0x180003173  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x18000317a  mov     r8d, ebx
0x18000317d  lea     rdx, aRegqueryvaluee_10; "RegQueryValueEx REG_TS_SESSDIRACTIVE fa"...
0x180003184  mov     ecx, 8; int
0x180003189  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000318e  jmp     short loc_1800031E7
0x180003190  cmp     [rbp+Type], 4
0x180003194  jz      loc_1800030FE
0x18000319a  mov     ebx, 80070057h
0x18000319f  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x1800031a6  mov     r8d, ebx
0x1800031a9  lea     rdx, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD fail"...
0x1800031b0  mov     ecx, 8; int
0x1800031b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800031ba  jmp     short loc_1800031E7
0x1800031bc  cmp     [rbp+Type], 4
0x1800031c0  jz      short loc_1800031E4
0x1800031c2  mov     ebx, 80070057h
0x1800031c7  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x1800031ce  mov     r8d, ebx
0x1800031d1  lea     rdx, aRegTermsrvAppc; "REG_TERMSRV_APPCOMPAT not REG_DWORD fai"...
0x1800031d8  mov     ecx, 8; int
0x1800031dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800031e2  jmp     short loc_1800031E7
0x1800031e4  mov     edi, dword ptr [rbp+Data]
0x1800031e7  mov     rcx, [rbp+hKey]; hKey
0x1800031eb  test    rcx, rcx
0x1800031ee  jz      short loc_1800031F6
0x1800031f0  call    cs:__imp_RegCloseKey
0x1800031f6  test    ebx, ebx
0x1800031f8  jns     short loc_180003240
0x1800031fa  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x180003201  mov     r8d, ebx
0x180003204  lea     rdx, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD fail"...
0x18000320b  mov     ecx, 8; int
0x180003210  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003215  mov     rcx, [rbp+var_18]; hKey
0x180003219  test    rcx, rcx
0x18000321c  jz      short loc_180003224
0x18000321e  call    cs:__imp_RegCloseKey
0x180003224  test    ebx, ebx
0x180003226  jns     short loc_180003230
0x180003228  mov     ecx, ebx; dwErrCode
0x18000322a  call    cs:__imp_SetLastError
0x180003230  not     ebx
0x180003232  shr     ebx, 1Fh
0x180003235  mov     eax, ebx
0x180003237  add     rsp, 68h
0x18000323b  pop     rdi
0x18000323c  pop     rsi
0x18000323d  pop     rbx
0x18000323e  pop     rbp
0x18000323f  retn
0x180003240  test    edi, edi
0x180003242  jz      short loc_180003215
0x180003244  lea     rax, [rbp+var_18]
0x180003248  mov     r9d, 20019h; samDesired
0x18000324e  xor     r8d, r8d; ulOptions
0x180003251  mov     [rsp+68h+phkResult], rax; phkResult
0x180003256  lea     rdx, aSystemCurrentc_11; "System\\CurrentControlSet\\Control\\Ter"...
0x18000325d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003264  call    cs:__imp_RegOpenKeyExW
0x18000326a  mov     ebx, eax
0x18000326c  test    eax, eax
0x18000326e  jle     short loc_180003279
0x180003270  movzx   ebx, ax
0x180003273  or      ebx, 80070000h
0x180003279  test    ebx, ebx
0x18000327b  jns     short loc_180003293
0x18000327d  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x180003284  mov     r8d, ebx
0x180003287  lea     rdx, aRegopenkeyexRe; "RegOpenKeyEx REG_CONTROL_SESSDIR_TELEME"...
0x18000328e  jmp     loc_18000320B
0x180003293  mov     rcx, [rbp+var_18]; hKey
0x180003297  lea     rax, [rbp+arg_18]
0x18000329b  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800032a0  lea     rdi, ?m_DeploymentId@CUVHDProfileTelemetryLogging@@0PAGA; ushort near * CUVHDProfileTelemetryLogging::m_DeploymentId
0x1800032a7  lea     r9, [rbp+var_30]; lpType
0x1800032ab  mov     [rsp+68h+phkResult], rdi; lpData
0x1800032b0  xor     r8d, r8d; lpReserved
0x1800032b3  mov     [rbp+arg_18], 200h
0x1800032ba  lea     rdx, aTelemetrydeplo; "TelemetryDeploymentId"
0x1800032c1  call    cs:__imp_RegQueryValueExW
0x1800032c7  mov     ebx, eax
0x1800032c9  test    eax, eax
0x1800032cb  jle     short loc_1800032D6
0x1800032cd  movzx   ebx, ax
0x1800032d0  or      ebx, 80070000h
0x1800032d6  test    ebx, ebx
0x1800032d8  jns     short loc_1800032F0
0x1800032da  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x1800032e1  mov     r8d, ebx
0x1800032e4  lea     rdx, aRegqueryvaluee_7; "RegQueryValueEx REG_SESSDIR_TELEMETRY_D"...
0x1800032eb  jmp     loc_18000320B
0x1800032f0  cmp     [rbp+var_30], 1
0x1800032f4  jz      short loc_180003311
0x1800032f6  mov     ebx, 80070057h
0x1800032fb  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x180003302  mov     r8d, ebx
0x180003305  lea     rdx, aRegSessdirTele; "REG_SESSDIR_TELEMETRY_DEPLOYMENT_ID not"...
0x18000330c  jmp     loc_18000320B
0x180003311  mov     ecx, [rbp+arg_18]
0x180003314  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180003318  cmp     rcx, 202h
0x18000331f  jnb     loc_1800033CA
0x180003325  mov     [rcx+rdi], si
0x180003329  lea     rax, [rbp+arg_18]
0x18000332d  mov     rcx, [rbp+var_18]; hKey
0x180003331  lea     rdi, ?m_FarmId@CUVHDProfileTelemetryLogging@@0PAGA; ushort near * CUVHDProfileTelemetryLogging::m_FarmId
0x180003338  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000333d  lea     r9, [rbp+var_30]; lpType
0x180003341  xor     r8d, r8d; lpReserved
0x180003344  mov     [rsp+68h+phkResult], rdi; lpData
0x180003349  lea     rdx, aTelemetryfarmi; "TelemetryFarmId"
0x180003350  mov     [rbp+arg_18], 200h
0x180003357  call    cs:__imp_RegQueryValueExW
0x18000335d  mov     ebx, eax
0x18000335f  test    eax, eax
0x180003361  jle     short loc_18000336C
0x180003363  movzx   ebx, ax
0x180003366  or      ebx, 80070000h
0x18000336c  test    ebx, ebx
0x18000336e  jns     short loc_180003386
0x180003370  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x180003377  mov     r8d, ebx
0x18000337a  lea     rdx, aRegqueryvaluee_9; "RegQueryValueEx REG_SESSDIR_TELEMETRY_F"...
0x180003381  jmp     loc_18000320B
0x180003386  cmp     [rbp+var_30], 1
0x18000338a  jz      short loc_1800033A7
0x18000338c  mov     ebx, 80070057h
0x180003391  lea     r9, aCuvhdprofilete_6; "CUVHDProfileTelemetryLogging::InitOnceC"...
0x180003398  mov     r8d, ebx
0x18000339b  lea     rdx, aRegSessdirTele_0; "REG_SESSDIR_TELEMETRY_FARM_ID not REG_S"...
0x1800033a2  jmp     loc_18000320B
0x1800033a7  mov     ecx, [rbp+arg_18]
0x1800033aa  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800033ae  cmp     rcx, 202h
0x1800033b5  jnb     short loc_1800033CA
0x1800033b7  mov     [rcx+rdi], si
0x1800033bb  mov     cs:?m_TelemetryEnabled@CUVHDProfileTelemetryLogging@@0HA, 1; int CUVHDProfileTelemetryLogging::m_TelemetryEnabled
0x1800033c5  jmp     loc_180003215
0x1800033ca  call    __report_rangecheckfailure
```
