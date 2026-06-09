# CCertManager::staticCertUpdateThread(void *)

- ea: `0x1800033e0`
- end: `0x180003850`
- name: `?staticCertUpdateThread@CCertManager@@CAKPEAX@Z`
- size: `1136`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800033e0`
- `0x180003860`
- `0x180003f30`
- `0x1800125f0`
- `0x18001346c`
- `0x18001a280`
- `0x18001a8d0`
- `0x180029094`
- `0x18002b64c`
- `0x18002b830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003789`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003597`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003597`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180003776`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180003776`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800034b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000356a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800034b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000356a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000374c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000374c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000342f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000342f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003828`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003828`

## string_xrefs

- `0x1800036cd`: `Reg.OpenKey failed: 0x%x in %s`
- `0x18000343b`: `CCertManager::staticCertUpdateThread`
- `0x180003817`: `CCertManager::staticCertUpdateThread`
- `0x1800035b2`: `UpdateDefaultCertificate failed: 0x%x`
- `0x1800035f4`: `UpdateDefaultCertificate failed: 0x%x`
- `0x1800035d4`: `UpdateSelfSignedCertificate failed: 0x%x`
- `0x180003616`: `UpdateCustomCertificates failed: 0x%x`
- `0x18000370e`: `Reg.ReadRegDWord failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::staticCertUpdateThread(HANDLE *Parameter)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HANDLE v5; // rcx
  void *v6; // rax
  unsigned int v7; // edi
  DWORD v8; // eax
  signed int LastError; // eax
  DWORD v10; // eax
  DWORD v11; // r15d
  int v12; // esi
  HANDLE v13; // rax
  DWORD v14; // eax
  int v15; // eax
  int updated; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  DWORD v20; // edi
  int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  bool v24; // sf
  unsigned int v25; // eax
  signed int v26; // eax
  unsigned int v27; // esi
  int v28; // edi
  unsigned int v29; // [rsp+30h] [rbp-39h] BYREF
  void **v30; // [rsp+38h] [rbp-31h] BYREF
  void *Block; // [rsp+40h] [rbp-29h]
  int v32; // [rsp+48h] [rbp-21h]
  HKEY hKey[2]; // [rsp+50h] [rbp-19h] BYREF
  HANDLE hHandle[2]; // [rsp+60h] [rbp-9h] BYREF
  HANDLE v35; // [rsp+70h] [rbp+7h]

  *(_OWORD *)hHandle = 0;
  v35 = 0;
  if ( !Parameter )
    return 2147942487LL;
  v3 = CoInitializeEx(0, 2u);
  v4 = v3;
  if ( v3 < 0 )
  {
    _DbgPrintMessage(8, "CoInitializeEx failed: 0x%x in %s", v3, "CCertManager::staticCertUpdateThread");
    return v4;
  }
  v5 = Parameter[199];
  hHandle[0] = v5;
  hHandle[1] = Parameter[203];
  v35 = Parameter[200];
  v6 = 0;
  if ( v5 != (HANDLE)-1LL )
    v6 = v5;
  if ( !v6 )
  {
    _DbgPrintMessage(
      8,
      "Missing paramter %s in %s",
      "hEventToCheck == INVALID_HANDLE_VALUE ? NULL : hEventToCheck",
      "CCertManager::CheckEventSet");
    v7 = -2147024809;
LABEL_17:
    v4 = v7;
    _DbgPrintMessage(8, "CheckEventSet() before loop failed: 0x%x in %s", v7, "CCertManager::staticCertUpdateThread");
    goto LABEL_71;
  }
  v8 = WaitForSingleObject(v5, 0);
  if ( v8 == -1 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
    {
      _DbgPrintMessage(8, "WaitForSingleObject() failed: 0x%x in %s", v7, "CCertManager::CheckEventSet");
      goto LABEL_17;
    }
LABEL_16:
    v7 = -2147467259;
    _DbgPrintMessage(
      8,
      "Unexpected result from WaitForSingleObject() failed: 0x%x in %s",
      2147500037LL,
      "CCertManager::CheckEventSet");
    goto LABEL_17;
  }
  if ( v8 && v8 != 258 )
    goto LABEL_16;
  v4 = 0;
  if ( !v8 )
    goto LABEL_71;
  v10 = 258;
  v11 = 3;
  v12 = 0;
  if ( !v35 )
    v11 = 2;
  while ( 1 )
  {
    if ( v10 != 1 )
    {
      updated = CCertManager::UpdateSelfSignedCertificate((unsigned __int16 **)Parameter);
      if ( updated < 0 )
        _DbgPrintMessage(8, "UpdateSelfSignedCertificate failed: 0x%x", updated);
      v17 = CCertManager::UpdateDefaultCertificate((const unsigned __int16 **)Parameter);
      if ( v17 < 0 )
        _DbgPrintMessage(8, "UpdateDefaultCertificate failed: 0x%x", v17);
      v18 = CCertManager::UpdateCustomCertificates((CCertManager *)Parameter);
      v4 = v18;
      if ( v18 < 0 )
        _DbgPrintMessage(8, "UpdateCustomCertificates failed: 0x%x", v18);
      if ( *((_DWORD *)Parameter + 428) != 2 )
        CCertManager::DoneFixingCertificatePermissions((CCertManager *)Parameter);
      goto LABEL_39;
    }
    v13 = 0;
    if ( hHandle[0] != (HANDLE)-1LL )
      v13 = hHandle[0];
    if ( !v13 )
      break;
    v14 = WaitForSingleObject(hHandle[0], 0x4E20u);
    if ( v14 == -1 )
    {
      v26 = GetLastError();
      v4 = v26;
      if ( v26 > 0 )
        v4 = (unsigned __int16)v26 | 0x80070000;
      if ( (v4 & 0x80000000) != 0 )
      {
        v27 = v4;
        _DbgPrintMessage(8, "WaitForSingleObject() failed: 0x%x in %s", v4, "CCertManager::CheckEventSet");
        goto LABEL_70;
      }
LABEL_67:
      v28 = -2147467259;
      v27 = -2147467259;
      _DbgPrintMessage(
        8,
        "Unexpected result from WaitForSingleObject() failed: 0x%x in %s",
        -2147467259,
        "CCertManager::CheckEventSet");
      goto LABEL_69;
    }
    if ( v14 && v14 != 258 )
      goto LABEL_67;
    v4 = 0;
    if ( !v14 )
      goto LABEL_71;
    ResetEvent(hHandle[1]);
    v15 = CCertManager::UpdateDefaultCertificate((const unsigned __int16 **)Parameter);
    v4 = v15;
    if ( v15 < 0 )
      _DbgPrintMessage(8, "UpdateDefaultCertificate failed: 0x%x", v15);
LABEL_39:
    if ( !v12 )
    {
      v19 = CCertManager::RegisterTermsrvSPN((CCertManager *)Parameter);
      v4 = v19;
      if ( v19 >= 0 )
        v12 = 1;
      else
        _DbgPrintMessage(8, "SessionEnv failed to register TERMSRV SPN 0x%X", v19);
    }
    v20 = 43200000;
    v29 = 0;
    v30 = &CRegistry::`vftable';
    Block = 0;
    v32 = 0;
    hKey[0] = 0;
    hKey[1] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v21 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20019u,
            hKey);
    v22 = v21 < 0;
    if ( v21 )
    {
      hKey[0] = 0;
      if ( v21 > 0 )
      {
        v21 = (unsigned __int16)v21 | 0x80070000;
        v22 = v21 < 0;
      }
    }
    if ( v22 )
    {
      _DbgPrintMessage(8, "Reg.OpenKey failed: 0x%x in %s", v21, "CCertManager::GetCertRefreshInterval");
    }
    else
    {
      v23 = CRegistry::ReadRegDWord((CRegistry *)&v30, L"CertRefreshInterval", &v29);
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 )
      {
        _DbgPrintMessage(8, "Reg.ReadRegDWord failed: 0x%x in %s", v23, "CCertManager::GetCertRefreshInterval");
      }
      else
      {
        v25 = v29;
        if ( v29 )
        {
          if ( v29 > 0xA8C0 )
            v25 = 43200;
          v20 = 60000 * v25;
        }
        else
        {
          v20 = -1;
        }
      }
    }
    v30 = &CRegistry::`vftable';
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    if ( Block )
      operator delete(Block);
    v10 = WaitForMultipleObjectsEx(v11, hHandle, 0, v20, 0);
    if ( !v10 )
      goto LABEL_71;
  }
  _DbgPrintMessage(
    8,
    "Missing paramter %s in %s",
    "hEventToCheck == INVALID_HANDLE_VALUE ? NULL : hEventToCheck",
    "CCertManager::CheckEventSet");
  v28 = -2147024809;
  v27 = -2147024809;
LABEL_69:
  v4 = v28;
LABEL_70:
  _DbgPrintMessage(8, "CheckEventSet(EVT_StopEventId) failed: 0x%x in %s", v27, "CCertManager::staticCertUpdateThread");
LABEL_71:
  CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x1800033e0  push    rbp
0x1800033e2  push    rbx
0x1800033e3  push    rsi
0x1800033e4  push    rdi
0x1800033e5  push    r12
0x1800033e7  push    r13
0x1800033e9  push    r14
0x1800033eb  push    r15
0x1800033ed  lea     rbp, [rsp-1Fh]
0x1800033f2  sub     rsp, 88h
0x1800033f9  mov     rax, cs:__security_cookie
0x180003400  xor     rax, rsp
0x180003403  mov     [rbp+57h+var_48], rax
0x180003407  mov     r14, rcx
0x18000340a  xorps   xmm0, xmm0
0x18000340d  xor     eax, eax
0x18000340f  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x180003413  mov     [rbp+57h+var_50], rax
0x180003417  test    rcx, rcx
0x18000341a  jnz     short loc_180003426
0x18000341c  mov     eax, 80070057h
0x180003421  jmp     loc_180003830
0x180003426  mov     edi, 2
0x18000342b  mov     edx, edi; dwCoInit
0x18000342d  xor     ecx, ecx; pvReserved
0x18000342f  call    cs:__imp_CoInitializeEx
0x180003435  mov     ebx, eax
0x180003437  test    eax, eax
0x180003439  jns     short loc_18000345B
0x18000343b  lea     r9, aCcertmanagerSt; "CCertManager::staticCertUpdateThread"
0x180003442  mov     r8d, eax
0x180003445  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed: 0x%x in %s"
0x18000344c  mov     ecx, 8; int
0x180003451  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003456  jmp     loc_18000382E
0x18000345b  mov     rcx, [r14+638h]; hHandle
0x180003462  mov     [rbp+57h+hHandle], rcx
0x180003466  mov     rax, [r14+658h]
0x18000346d  mov     [rbp+57h+hHandle+8], rax
0x180003471  mov     rax, [r14+640h]
0x180003478  mov     [rbp+57h+var_50], rax
0x18000347c  xor     r12d, r12d
0x18000347f  mov     eax, r12d
0x180003482  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003486  cmovnz  rax, rcx
0x18000348a  test    rax, rax
0x18000348d  jnz     short loc_1800034B5
0x18000348f  lea     r9, aCcertmanagerCh_3; "CCertManager::CheckEventSet"
0x180003496  lea     r8, aHeventtocheckI; "hEventToCheck == INVALID_HANDLE_VALUE ?"...
0x18000349d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800034a4  mov     ecx, 8; int
0x1800034a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800034ae  mov     edi, 80070057h
0x1800034b3  jmp     short loc_18000350F
0x1800034b5  xor     edx, edx; dwMilliseconds
0x1800034b7  call    cs:__imp_WaitForSingleObject
0x1800034bd  cmp     eax, 0FFFFFFFFh
0x1800034c0  jnz     short loc_1800034E4
0x1800034c2  call    cs:__imp_GetLastError
0x1800034c8  mov     edi, eax
0x1800034ca  test    eax, eax
0x1800034cc  jle     short loc_1800034D7
0x1800034ce  movzx   edi, ax
0x1800034d1  or      edi, 80070000h
0x1800034d7  test    edi, edi
0x1800034d9  jns     short loc_1800034EF
0x1800034db  lea     rdx, aWaitforsingleo_0; "WaitForSingleObject() failed: 0x%x in %"...
0x1800034e2  jmp     short loc_1800034FB
0x1800034e4  test    eax, eax
0x1800034e6  jz      short loc_180003520
0x1800034e8  cmp     eax, 102h
0x1800034ed  jz      short loc_180003520
0x1800034ef  mov     edi, 80004005h
0x1800034f4  lea     rdx, aUnexpectedResu; "Unexpected result from WaitForSingleObj"...
0x1800034fb  lea     r9, aCcertmanagerCh_3; "CCertManager::CheckEventSet"
0x180003502  mov     r8d, edi
0x180003505  mov     ecx, 8; int
0x18000350a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000350f  mov     ebx, edi
0x180003511  mov     r8d, edi
0x180003514  lea     rdx, aCheckeventsetB_0; "CheckEventSet() before loop failed: 0x%"...
0x18000351b  jmp     loc_180003817
0x180003520  mov     ebx, r12d
0x180003523  test    eax, eax
0x180003525  jz      loc_180003828
0x18000352b  mov     eax, 102h
0x180003530  mov     r15d, 3
0x180003536  mov     esi, r12d
0x180003539  cmp     [rbp+57h+var_50], rbx
0x18000353d  cmovz   r15d, edi
0x180003541  lea     r13, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180003548  cmp     eax, 1
0x18000354b  jnz     short loc_1800035C5
0x18000354d  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180003551  mov     rax, r12
0x180003554  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003558  cmovnz  rax, rcx
0x18000355c  test    rax, rax
0x18000355f  jz      loc_1800037E5
0x180003565  mov     edx, 4E20h; dwMilliseconds
0x18000356a  call    cs:__imp_WaitForSingleObject
0x180003570  cmp     eax, 0FFFFFFFFh
0x180003573  jz      loc_180003789
0x180003579  test    eax, eax
0x18000357b  jz      short loc_180003588
0x18000357d  cmp     eax, 102h
0x180003582  jnz     loc_1800037C1
0x180003588  mov     ebx, r12d
0x18000358b  test    eax, eax
0x18000358d  jz      loc_180003828
0x180003593  mov     rcx, [rbp+57h+hHandle+8]; hEvent
0x180003597  call    cs:__imp_ResetEvent
0x18000359d  mov     rcx, r14; this
0x1800035a0  call    ?UpdateDefaultCertificate@CCertManager@@AEAAJXZ; CCertManager::UpdateDefaultCertificate(void)
0x1800035a5  mov     ebx, eax
0x1800035a7  test    eax, eax
0x1800035a9  jns     loc_180003639
0x1800035af  mov     r8d, eax
0x1800035b2  lea     rdx, aUpdatedefaultc; "UpdateDefaultCertificate failed: 0x%x"
0x1800035b9  mov     ecx, 8; int
0x1800035be  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800035c3  jmp     short loc_180003639
0x1800035c5  mov     rcx, r14; this
0x1800035c8  call    ?UpdateSelfSignedCertificate@CCertManager@@AEAAJXZ; CCertManager::UpdateSelfSignedCertificate(void)
0x1800035cd  test    eax, eax
0x1800035cf  jns     short loc_1800035E5
0x1800035d1  mov     r8d, eax
0x1800035d4  lea     rdx, aUpdateselfsign; "UpdateSelfSignedCertificate failed: 0x%"...
0x1800035db  mov     ecx, 8; int
0x1800035e0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800035e5  mov     rcx, r14; this
0x1800035e8  call    ?UpdateDefaultCertificate@CCertManager@@AEAAJXZ; CCertManager::UpdateDefaultCertificate(void)
0x1800035ed  test    eax, eax
0x1800035ef  jns     short loc_180003605
0x1800035f1  mov     r8d, eax
0x1800035f4  lea     rdx, aUpdatedefaultc; "UpdateDefaultCertificate failed: 0x%x"
0x1800035fb  mov     ecx, 8; int
0x180003600  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003605  mov     rcx, r14; this
0x180003608  call    ?UpdateCustomCertificates@CCertManager@@AEAAJXZ; CCertManager::UpdateCustomCertificates(void)
0x18000360d  mov     ebx, eax
0x18000360f  test    eax, eax
0x180003611  jns     short loc_180003627
0x180003613  mov     r8d, eax
0x180003616  lea     rdx, aUpdatecustomce; "UpdateCustomCertificates failed: 0x%x"
0x18000361d  mov     ecx, 8; int
0x180003622  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003627  cmp     dword ptr [r14+6B0h], 2
0x18000362f  jz      short loc_180003639
0x180003631  mov     rcx, r14; this
0x180003634  call    ?DoneFixingCertificatePermissions@CCertManager@@AEAAJXZ; CCertManager::DoneFixingCertificatePermissions(void)
0x180003639  test    esi, esi
0x18000363b  jnz     short loc_180003666
0x18000363d  mov     rcx, r14; this
0x180003640  call    ?RegisterTermsrvSPN@CCertManager@@AEAAJXZ; CCertManager::RegisterTermsrvSPN(void)
0x180003645  mov     ebx, eax
0x180003647  test    eax, eax
0x180003649  jns     short loc_180003661
0x18000364b  mov     r8d, eax
0x18000364e  lea     rdx, aSessionenvFail; "SessionEnv failed to register TERMSRV S"...
0x180003655  mov     ecx, 8; int
0x18000365a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000365f  jmp     short loc_180003666
0x180003661  mov     esi, 1
0x180003666  mov     edi, 2932E00h
0x18000366b  mov     [rbp+57h+var_90], r12d
0x18000366f  mov     [rbp+57h+var_88], r13
0x180003673  mov     [rbp+57h+Block], r12
0x180003677  mov     [rbp+57h+var_78], r12d
0x18000367b  mov     [rbp+57h+hKey], r12
0x18000367f  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x180003687  lea     rax, [rbp+57h+hKey]
0x18000368b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180003690  mov     r9d, 20019h; samDesired
0x180003696  xor     r8d, r8d; ulOptions
0x180003699  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x1800036a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800036a7  call    cs:__imp_RegOpenKeyExW
0x1800036ad  test    eax, eax
0x1800036af  jz      short loc_1800036C1
0x1800036b1  mov     [rbp+57h+hKey], r12
0x1800036b5  jle     short loc_1800036C1
0x1800036b7  movzx   eax, ax
0x1800036ba  or      eax, 80070000h
0x1800036bf  test    eax, eax
0x1800036c1  jns     short loc_1800036E0
0x1800036c3  lea     r9, aCcertmanagerGe_5; "CCertManager::GetCertRefreshInterval"
0x1800036ca  mov     r8d, eax
0x1800036cd  lea     rdx, aRegOpenkeyFail; "Reg.OpenKey failed: 0x%x in %s"
0x1800036d4  mov     ecx, 8; int
0x1800036d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800036de  jmp     short loc_18000373F
0x1800036e0  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1800036e4  lea     rdx, aCertrefreshint; "CertRefreshInterval"
0x1800036eb  lea     rcx, [rbp+57h+var_88]; this
0x1800036ef  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x1800036f4  test    eax, eax
0x1800036f6  jle     short loc_180003702
0x1800036f8  movzx   eax, ax
0x1800036fb  or      eax, 80070000h
0x180003700  test    eax, eax
0x180003702  jns     short loc_180003721
0x180003704  lea     r9, aCcertmanagerGe_5; "CCertManager::GetCertRefreshInterval"
0x18000370b  mov     r8d, eax
0x18000370e  lea     rdx, aRegReadregdwor; "Reg.ReadRegDWord failed: 0x%x in %s"
0x180003715  mov     ecx, 8; int
0x18000371a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000371f  jmp     short loc_18000373F
0x180003721  mov     eax, [rbp+57h+var_90]
0x180003724  test    eax, eax
0x180003726  jz      short loc_18000373A
0x180003728  mov     ecx, 0A8C0h
0x18000372d  cmp     eax, ecx
0x18000372f  cmova   eax, ecx
0x180003732  imul    edi, eax, 0EA60h
0x180003738  jmp     short loc_18000373F
0x18000373a  mov     edi, 0FFFFFFFFh
0x18000373f  mov     [rbp+57h+var_88], r13
0x180003743  mov     rcx, [rbp+57h+hKey]; hKey
0x180003747  test    rcx, rcx
0x18000374a  jz      short loc_180003756
0x18000374c  call    cs:__imp_RegCloseKey
0x180003752  mov     [rbp+57h+hKey], r12
0x180003756  mov     rcx, [rbp+57h+Block]; Block
0x18000375a  test    rcx, rcx
0x18000375d  jz      short loc_180003764
0x18000375f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003764  mov     dword ptr [rsp+0C0h+phkResult], r12d; bAlertable
0x180003769  mov     r9d, edi; dwMilliseconds
0x18000376c  xor     r8d, r8d; bWaitAll
0x18000376f  lea     rdx, [rbp+57h+hHandle]; lpHandles
0x180003773  mov     ecx, r15d; nCount
0x180003776  call    cs:__imp_WaitForMultipleObjectsEx
0x18000377c  test    eax, eax
0x18000377e  jnz     loc_180003548
0x180003784  jmp     loc_180003828
0x180003789  call    cs:__imp_GetLastError
0x18000378f  mov     ebx, eax
0x180003791  test    eax, eax
0x180003793  jle     short loc_18000379E
0x180003795  movzx   ebx, ax
0x180003798  or      ebx, 80070000h
0x18000379e  test    ebx, ebx
0x1800037a0  jns     short loc_1800037C1
0x1800037a2  mov     esi, ebx
0x1800037a4  lea     r9, aCcertmanagerCh_3; "CCertManager::CheckEventSet"
0x1800037ab  mov     r8d, ebx
0x1800037ae  lea     rdx, aWaitforsingleo_0; "WaitForSingleObject() failed: 0x%x in %"...
0x1800037b5  mov     ecx, 8; int
0x1800037ba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800037bf  jmp     short loc_18000380D
0x1800037c1  mov     edi, 80004005h
0x1800037c6  mov     esi, edi
0x1800037c8  lea     r9, aCcertmanagerCh_3; "CCertManager::CheckEventSet"
0x1800037cf  mov     r8d, edi
0x1800037d2  lea     rdx, aUnexpectedResu; "Unexpected result from WaitForSingleObj"...
0x1800037d9  mov     ecx, 8; int
0x1800037de  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800037e3  jmp     short loc_18000380B
0x1800037e5  lea     r9, aCcertmanagerCh_3; "CCertManager::CheckEventSet"
0x1800037ec  lea     r8, aHeventtocheckI; "hEventToCheck == INVALID_HANDLE_VALUE ?"...
0x1800037f3  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800037fa  mov     ecx, 8; int
0x1800037ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003804  mov     edi, 80070057h
0x180003809  mov     esi, edi
0x18000380b  mov     ebx, edi
0x18000380d  mov     r8d, esi
0x180003810  lea     rdx, aCheckeventsetE; "CheckEventSet(EVT_StopEventId) failed: "...
0x180003817  lea     r9, aCcertmanagerSt; "CCertManager::staticCertUpdateThread"
0x18000381e  mov     ecx, 8; int
0x180003823  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003828  call    cs:__imp_CoUninitialize
0x18000382e  mov     eax, ebx
0x180003830  mov     rcx, [rbp+57h+var_48]
0x180003834  xor     rcx, rsp; StackCookie
0x180003837  call    __security_check_cookie
0x18000383c  add     rsp, 88h
0x180003843  pop     r15
0x180003845  pop     r14
0x180003847  pop     r13
0x180003849  pop     r12
0x18000384b  pop     rdi
0x18000384c  pop     rsi
0x18000384d  pop     rbx
0x18000384e  pop     rbp
0x18000384f  retn
```
