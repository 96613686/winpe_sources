# UpdateRegistryPostRestore(ushort *,uchar,uchar,ulong,_GUID *,CBlbBackupStatUpdater *)

- ea: `0x1401302e8`
- end: `0x140130837`
- name: `?UpdateRegistryPostRestore@@YAJPEAGEEKPEAU_GUID@@PEAVCBlbBackupStatUpdater@@@Z`
- size: `1359`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int8@<dl>, unsigned __int8@<r8b>, unsigned int@<r9d>, struct _GUID *, struct CBlbBackupStatUpdater *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14007d630`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14008863c`
- `0x140094cb8`
- `0x140094f38`
- `0x14012eacc`
- `0x14012fa10`
- `0x1401302e8`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1401305bb`
- `ADVAPI32!RegDeleteValueW` at `0x14013069f`
- `ADVAPI32!RegDeleteValueW` at `0x1401305bb`
- `ADVAPI32!RegDeleteValueW` at `0x14013069f`
- `ADVAPI32!RegOpenKeyExW` at `0x14013053c`
- `ADVAPI32!RegOpenKeyExW` at `0x140130579`
- `ADVAPI32!RegOpenKeyExW` at `0x14013053c`
- `ADVAPI32!RegOpenKeyExW` at `0x140130579`
- `ADVAPI32!RegSetValueExW` at `0x140130798`
- `ADVAPI32!RegSetValueExW` at `0x140130798`
- `ADVAPI32!RegCreateKeyExW` at `0x140130637`
- `ADVAPI32!RegCreateKeyExW` at `0x140130637`
- `ADVAPI32!RegCloseKey` at `0x140130424`
- `ADVAPI32!RegCloseKey` at `0x14013042e`
- `ADVAPI32!RegCloseKey` at `0x140130438`
- `ADVAPI32!RegCloseKey` at `0x140130424`
- `ADVAPI32!RegCloseKey` at `0x14013042e`
- `ADVAPI32!RegCloseKey` at `0x140130438`
- `ADVAPI32!RegLoadKeyW` at `0x1401303fc`
- `ADVAPI32!RegLoadKeyW` at `0x1401303fc`
- `ADVAPI32!RegUnLoadKeyW` at `0x140130451`
- `ADVAPI32!RegUnLoadKeyW` at `0x140130451`
- `KERNEL32!RaiseException` at `0x140130475`
- `KERNEL32!RaiseException` at `0x140130499`
- `KERNEL32!RaiseException` at `0x140130475`
- `KERNEL32!RaiseException` at `0x140130499`
- `ole32!CoTaskMemFree` at `0x1401304b9`
- `ole32!CoTaskMemFree` at `0x1401304b9`
- `RPCRT4!UuidToStringW` at `0x140130759`
- `RPCRT4!UuidToStringW` at `0x140130759`
- `RPCRT4!UuidCreate` at `0x14013073d`
- `RPCRT4!UuidCreate` at `0x14013073d`
- `RPCRT4!RpcStringFreeW` at `0x1401304a3`
- `RPCRT4!RpcStringFreeW` at `0x1401304a3`

## string_xrefs

- `0x14013038f`: `SeBackupPrivilege`
- `0x1401303bf`: `SeRestorePrivilege`
- `0x140130361`: `pBlbBackupStatUpdater != NULL`
- `0x1401303d8`: `\Windows\System32\config\Software`

## pseudocode

```c
__int64 __fastcall UpdateRegistryPostRestore(
        unsigned __int16 *a1,
        char a2,
        unsigned __int8 a3,
        unsigned int a4,
        struct _GUID *a5,
        BYTE *lpData)
{
  char v10; // dl
  signed int appended; // ebx
  LSTATUS KeyW; // eax
  bool v13; // cc
  signed int v14; // eax
  signed int v15; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  LSTATUS v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  LSTATUS v22; // eax
  __int64 v23; // rax
  LSTATUS v24; // eax
  int v25; // [rsp+50h] [rbp-59h]
  HKEY hKey; // [rsp+58h] [rbp-51h] BYREF
  HKEY v27; // [rsp+60h] [rbp-49h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-41h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-31h] BYREF
  LPCWSTR lpFile; // [rsp+80h] [rbp-29h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+88h] [rbp-21h] BYREF
  struct _TOKEN_PRIVILEGES v33; // [rsp+98h] [rbp-11h] BYREF
  UUID Uuid; // [rsp+A8h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids);
  }
  if ( !lpData )
    BlbAssert("base\\stor\\blb\\bmr\\asrrestore.cpp", 0x2A4u, "pBlbBackupStatUpdater != NULL");
  lpFile = 0;
  hKey = 0;
  v27 = 0;
  phkResult = 0;
  Uuid = 0;
  dwDisposition = 0;
  NewState = 0;
  v25 = 0;
  v33 = 0;
  String = 0;
  appended = BlbutilSetPrivilege(L"SeBackupPrivilege", a2, &NewState);
  if ( appended < 0 )
    goto LABEL_13;
  appended = BlbutilSetPrivilege(L"SeRestorePrivilege", v10, &v33);
  if ( appended < 0 )
    goto LABEL_13;
  appended = BlbutilAppendString(a1, L"\\Windows\\System32\\config\\Software", (unsigned __int16 **)&lpFile);
  if ( appended < 0 )
    goto LABEL_13;
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"OfflineSoftwareHive", lpFile);
  appended = KeyW;
  v13 = KeyW <= 0;
  if ( KeyW
    || (v25 = 1,
        KeyW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"OfflineSoftwareHive", 0, 0xF003Fu, &hKey),
        appended = KeyW,
        v13 = KeyW <= 0,
        KeyW) )
  {
    if ( !v13 )
      appended = (unsigned __int16)KeyW | 0x80070000;
    goto LABEL_13;
  }
  if ( !a2 )
  {
    if ( RegOpenKeyExW(hKey, L"Microsoft\\Windows\\CurrentVersion\\Reliability", 0, 0xF003Fu, &phkResult) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v18 = 46;
LABEL_40:
        WPP_SF_d(v17[2], v18, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids);
      }
    }
    else if ( RegDeleteValueW(phkResult, L"LastAliveStamp") )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v18 = 47;
        goto LABEL_40;
      }
    }
  }
  v19 = RegCreateKeyExW(
          hKey,
          L"MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &v27,
          &dwDisposition);
  appended = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      appended = (unsigned __int16)v19 | 0x80070000;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 48;
LABEL_48:
      WPP_SF_d(v20[2], v21, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids);
    }
  }
  else
  {
    v22 = RegDeleteValueW(v27, L"LastInstance");
    appended = v22;
    if ( (v22 & 0xFFFFFFFD) != 0 )
    {
      if ( v22 > 0 )
        appended = (unsigned __int16)v22 | 0x80070000;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 49;
        goto LABEL_48;
      }
    }
    else
    {
      appended = SetRestoredVolumesString(a3, a4, a5, v27);
      if ( appended >= 0 )
      {
        if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &String) )
        {
          appended = -2147467259;
        }
        else
        {
          v23 = -1;
          do
            ++v23;
          while ( String[v23] );
          v24 = RegSetValueExW(v27, L"LastInstance", 0, 1u, (const BYTE *)String, 2 * v23 + 2);
          appended = v24;
          if ( v24 )
          {
            if ( v24 > 0 )
              appended = (unsigned __int16)v24 | 0x80070000;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v21 = 51;
              goto LABEL_48;
            }
          }
          else
          {
            appended = CBlbBackupStatUpdater::SaveStatsToRegistry(lpData, hKey, 1);
            if ( appended < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids);
              }
              appended = 0;
            }
          }
        }
      }
      else
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 50;
          goto LABEL_48;
        }
      }
    }
  }
LABEL_13:
  RegCloseKey(hKey);
  RegCloseKey(v27);
  RegCloseKey(phkResult);
  if ( v25 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"OfflineSoftwareHive");
  if ( NewState.PrivilegeCount )
  {
    v14 = BlbutilRevertPrivilege(&NewState);
    if ( v14 < 0 )
      RaiseException(v14, 1u, 0, 0);
  }
  if ( v33.PrivilegeCount )
  {
    v15 = BlbutilRevertPrivilege(&v33);
    if ( v15 < 0 )
      RaiseException(v15, 1u, 0, 0);
  }
  RpcStringFreeW(&String);
  String = 0;
  if ( lpFile )
    CoTaskMemFree((LPVOID)lpFile);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1401302e8  mov     [rsp-8+arg_8], rbx
0x1401302ed  push    rbp
0x1401302ee  push    rsi
0x1401302ef  push    rdi
0x1401302f0  push    r12
0x1401302f2  push    r13
0x1401302f4  push    r14
0x1401302f6  push    r15
0x1401302f8  lea     rbp, [rsp-17h]
0x1401302fd  sub     rsp, 0C0h
0x140130304  mov     rax, cs:__security_cookie
0x14013030b  xor     rax, rsp
0x14013030e  mov     [rbp+47h+var_38], rax
0x140130312  mov     r13, [rbp+47h+arg_20]
0x140130316  mov     r12d, r9d
0x140130319  mov     r14, [rbp+47h+lpData]
0x14013031d  mov     r15b, r8b
0x140130320  mov     sil, dl
0x140130323  mov     rdi, rcx
0x140130326  mov     rcx, cs:WPP_GLOBAL_Control
0x14013032d  lea     rax, WPP_GLOBAL_Control
0x140130334  cmp     rcx, rax
0x140130337  jz      short loc_14013035A
0x140130339  test    byte ptr [rcx+1Ch], 20h
0x14013033d  jz      short loc_14013035A
0x14013033f  cmp     byte ptr [rcx+19h], 4
0x140130343  jb      short loc_14013035A
0x140130345  mov     rcx, [rcx+10h]
0x140130349  lea     r8, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids
0x140130350  mov     edx, 2Dh ; '-'
0x140130355  call    WPP_SF_
0x14013035a  xor     ebx, ebx
0x14013035c  test    r14, r14
0x14013035f  jnz     short loc_140130379
0x140130361  lea     r8, aPblbbackupstat; "pBlbBackupStatUpdater != NULL"
0x140130368  mov     edx, 2A4h; unsigned int
0x14013036d  lea     rcx, aBaseStorBlbBmr; "base\\stor\\blb\\bmr\\asrrestore.cpp"
0x140130374  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140130379  xorps   xmm0, xmm0
0x14013037c  mov     [rbp+47h+lpFile], rbx
0x140130380  xorps   xmm1, xmm1
0x140130383  mov     [rbp+47h+hKey], rbx
0x140130387  lea     r8, [rbp+47h+NewState]; struct _TOKEN_PRIVILEGES *
0x14013038b  mov     [rbp+47h+var_90], rbx
0x14013038f  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x140130396  mov     [rbp+47h+var_78], rbx
0x14013039a  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x14013039e  mov     [rbp+47h+dwDisposition], ebx
0x1401303a1  movups  xmmword ptr [rbp+47h+NewState.PrivilegeCount], xmm1
0x1401303a5  mov     [rbp+47h+var_A0], ebx
0x1401303a8  movups  xmmword ptr [rbp+47h+var_58.PrivilegeCount], xmm0
0x1401303ac  mov     [rbp+47h+String], rbx
0x1401303b0  call    ?BlbutilSetPrivilege@@YAJPEBGHPEAU_TOKEN_PRIVILEGES@@@Z; BlbutilSetPrivilege(ushort const *,int,_TOKEN_PRIVILEGES *)
0x1401303b5  mov     ebx, eax
0x1401303b7  test    eax, eax
0x1401303b9  js      short loc_140130417
0x1401303bb  lea     r8, [rbp+47h+var_58]; struct _TOKEN_PRIVILEGES *
0x1401303bf  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1401303c6  call    ?BlbutilSetPrivilege@@YAJPEBGHPEAU_TOKEN_PRIVILEGES@@@Z; BlbutilSetPrivilege(ushort const *,int,_TOKEN_PRIVILEGES *)
0x1401303cb  mov     ebx, eax
0x1401303cd  test    eax, eax
0x1401303cf  js      short loc_140130417
0x1401303d1  lea     r8, [rbp+47h+lpFile]; unsigned __int16 **
0x1401303d5  mov     rcx, rdi; unsigned __int16 *
0x1401303d8  lea     rdx, aWindowsSystem3; "\\Windows\\System32\\config\\Software"
0x1401303df  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1401303e4  mov     ebx, eax
0x1401303e6  test    eax, eax
0x1401303e8  js      short loc_140130417
0x1401303ea  mov     r8, [rbp+47h+lpFile]; lpFile
0x1401303ee  lea     rdx, aOfflinesoftwar; "OfflineSoftwareHive"
0x1401303f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1401303fc  call    cs:__imp_RegLoadKeyW
0x140130402  mov     ebx, eax
0x140130404  test    eax, eax
0x140130406  jz      loc_140130515
0x14013040c  jle     short loc_140130417
0x14013040e  movzx   ebx, ax
0x140130411  or      ebx, 80070000h
0x140130417  xor     esi, esi
0x140130419  lea     rdi, WPP_GLOBAL_Control
0x140130420  mov     rcx, [rbp+47h+hKey]; hKey
0x140130424  call    cs:__imp_RegCloseKey
0x14013042a  mov     rcx, [rbp+47h+var_90]; hKey
0x14013042e  call    cs:__imp_RegCloseKey
0x140130434  mov     rcx, [rbp+47h+var_78]; hKey
0x140130438  call    cs:__imp_RegCloseKey
0x14013043e  cmp     [rbp+47h+var_A0], esi
0x140130441  jz      short loc_140130457
0x140130443  lea     rdx, aOfflinesoftwar; "OfflineSoftwareHive"
0x14013044a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140130451  call    cs:__imp_RegUnLoadKeyW
0x140130457  cmp     [rbp+47h+NewState.PrivilegeCount], esi
0x14013045a  jz      short loc_14013047B
0x14013045c  lea     rcx, [rbp+47h+NewState]; NewState
0x140130460  call    ?BlbutilRevertPrivilege@@YAJPEAU_TOKEN_PRIVILEGES@@@Z; BlbutilRevertPrivilege(_TOKEN_PRIVILEGES *)
0x140130465  test    eax, eax
0x140130467  jns     short loc_14013047B
0x140130469  xor     r9d, r9d; lpArguments
0x14013046c  xor     r8d, r8d; nNumberOfArguments
0x14013046f  mov     ecx, eax; dwExceptionCode
0x140130471  lea     edx, [r9+1]; dwExceptionFlags
0x140130475  call    cs:__imp_RaiseException
0x14013047b  cmp     [rbp+47h+var_58.PrivilegeCount], esi
0x14013047e  jz      short loc_14013049F
0x140130480  lea     rcx, [rbp+47h+var_58]; NewState
0x140130484  call    ?BlbutilRevertPrivilege@@YAJPEAU_TOKEN_PRIVILEGES@@@Z; BlbutilRevertPrivilege(_TOKEN_PRIVILEGES *)
0x140130489  test    eax, eax
0x14013048b  jns     short loc_14013049F
0x14013048d  xor     r9d, r9d; lpArguments
0x140130490  xor     r8d, r8d; nNumberOfArguments
0x140130493  mov     ecx, eax; dwExceptionCode
0x140130495  lea     edx, [r9+1]; dwExceptionFlags
0x140130499  call    cs:__imp_RaiseException
0x14013049f  lea     rcx, [rbp+47h+String]; String
0x1401304a3  call    cs:__imp_RpcStringFreeW
0x1401304a9  mov     rax, [rbp+47h+lpFile]
0x1401304ad  mov     [rbp+47h+String], rsi
0x1401304b1  test    rax, rax
0x1401304b4  jz      short loc_1401304BF
0x1401304b6  mov     rcx, rax; pv
0x1401304b9  call    cs:__imp_CoTaskMemFree
0x1401304bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1401304c6  cmp     rcx, rdi
0x1401304c9  jz      short loc_1401304EC
0x1401304cb  test    byte ptr [rcx+1Ch], 20h
0x1401304cf  jz      short loc_1401304EC
0x1401304d1  cmp     byte ptr [rcx+19h], 4
0x1401304d5  jb      short loc_1401304EC
0x1401304d7  mov     rcx, [rcx+10h]
0x1401304db  lea     r8, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids
0x1401304e2  mov     edx, 35h ; '5'
0x1401304e7  call    WPP_SF_
0x1401304ec  mov     eax, ebx
0x1401304ee  mov     rcx, [rbp+47h+var_38]
0x1401304f2  xor     rcx, rsp; StackCookie
0x1401304f5  call    __security_check_cookie
0x1401304fa  mov     rbx, [rsp+0F0h+arg_8]
0x140130502  add     rsp, 0C0h
0x140130509  pop     r15
0x14013050b  pop     r14
0x14013050d  pop     r13
0x14013050f  pop     r12
0x140130511  pop     rdi
0x140130512  pop     rsi
0x140130513  pop     rbp
0x140130514  retn
0x140130515  lea     rax, [rbp+47h+hKey]
0x140130519  mov     [rbp+47h+var_A0], 1
0x140130520  mov     r9d, 0F003Fh; samDesired
0x140130526  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14013052b  xor     r8d, r8d; ulOptions
0x14013052e  lea     rdx, aOfflinesoftwar; "OfflineSoftwareHive"
0x140130535  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14013053c  call    cs:__imp_RegOpenKeyExW
0x140130542  mov     ebx, eax
0x140130544  test    eax, eax
0x140130546  jnz     loc_14013040C
0x14013054c  xor     ebx, ebx
0x14013054e  mov     edi, 80070000h
0x140130553  test    sil, sil
0x140130556  jnz     loc_140130603
0x14013055c  mov     rcx, [rbp+47h+hKey]; hKey
0x140130560  lea     rax, [rbp+47h+var_78]
0x140130564  mov     r9d, 0F003Fh; samDesired
0x14013056a  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14013056f  xor     r8d, r8d; ulOptions
0x140130572  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\CurrentVersion\\Rel"...
0x140130579  call    cs:__imp_RegOpenKeyExW
0x14013057f  test    eax, eax
0x140130581  jz      short loc_1401305B0
0x140130583  jle     short loc_14013058A
0x140130585  movzx   eax, ax
0x140130588  or      eax, edi
0x14013058a  mov     rcx, cs:WPP_GLOBAL_Control
0x140130591  lea     rdx, WPP_GLOBAL_Control
0x140130598  cmp     rcx, rdx
0x14013059b  jz      short loc_140130603
0x14013059d  test    byte ptr [rcx+1Ch], 20h
0x1401305a1  jz      short loc_140130603
0x1401305a3  cmp     byte ptr [rcx+19h], 3
0x1401305a7  jb      short loc_140130603
0x1401305a9  mov     edx, 2Eh ; '.'
0x1401305ae  jmp     short loc_1401305F0
0x1401305b0  mov     rcx, [rbp+47h+var_78]; hKey
0x1401305b4  lea     rdx, aLastalivestamp; "LastAliveStamp"
0x1401305bb  call    cs:__imp_RegDeleteValueW
0x1401305c1  test    eax, eax
0x1401305c3  jz      short loc_140130603
0x1401305c5  jle     short loc_1401305CC
0x1401305c7  movzx   eax, ax
0x1401305ca  or      eax, edi
0x1401305cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401305d3  lea     rdx, WPP_GLOBAL_Control
0x1401305da  cmp     rcx, rdx
0x1401305dd  jz      short loc_140130603
0x1401305df  test    byte ptr [rcx+1Ch], 20h
0x1401305e3  jz      short loc_140130603
0x1401305e5  cmp     byte ptr [rcx+19h], 3
0x1401305e9  jb      short loc_140130603
0x1401305eb  mov     edx, 2Fh ; '/'
0x1401305f0  mov     rcx, [rcx+10h]
0x1401305f4  lea     r8, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids
0x1401305fb  mov     r9d, eax
0x1401305fe  call    WPP_SF_d
0x140130603  mov     rcx, [rbp+47h+hKey]; hKey
0x140130607  lea     rax, [rbp+47h+dwDisposition]
0x14013060b  mov     [rsp+0F0h+lpdwDisposition], rax; lpdwDisposition
0x140130610  lea     rdx, aMicrosoftWindo_3; "MICROSOFT\\WINDOWS NT\\CurrentVersion\\"...
0x140130617  lea     rax, [rbp+47h+var_90]
0x14013061b  xor     r9d, r9d; lpClass
0x14013061e  mov     [rsp+0F0h+var_B8], rax; phkResult
0x140130623  xor     r8d, r8d; Reserved
0x140130626  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x14013062b  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x140130633  mov     dword ptr [rsp+0F0h+phkResult], ebx; dwOptions
0x140130637  call    cs:__imp_RegCreateKeyExW
0x14013063d  xor     esi, esi
0x14013063f  mov     ebx, eax
0x140130641  test    eax, eax
0x140130643  jz      short loc_140130694
0x140130645  jle     short loc_14013064C
0x140130647  movzx   ebx, ax
0x14013064a  or      ebx, edi
0x14013064c  mov     rcx, cs:WPP_GLOBAL_Control
0x140130653  lea     rdi, WPP_GLOBAL_Control
0x14013065a  cmp     rcx, rdi
0x14013065d  jz      loc_140130420
0x140130663  test    byte ptr [rcx+1Ch], 20h
0x140130667  jz      loc_140130420
0x14013066d  cmp     byte ptr [rcx+19h], 2
0x140130671  jb      loc_140130420
0x140130677  mov     edx, 30h ; '0'
0x14013067c  mov     r9d, ebx
0x14013067f  mov     rcx, [rcx+10h]
0x140130683  lea     r8, WPP_75fd459b8877341b2b53e1be0e0d91a0_Traceguids
0x14013068a  call    WPP_SF_d
0x14013068f  jmp     loc_140130420
0x140130694  mov     rcx, [rbp+47h+var_90]; hKey
0x140130698  lea     rdx, aLastinstance; "LastInstance"
0x14013069f  call    cs:__imp_RegDeleteValueW
0x1401306a5  mov     ebx, eax
0x1401306a7  test    eax, 0FFFFFFFDh
0x1401306ac  jz      short loc_1401306E9
0x1401306ae  test    eax, eax
0x1401306b0  jle     short loc_1401306B7
0x1401306b2  movzx   ebx, ax
0x1401306b5  or      ebx, edi
0x1401306b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1401306be  lea     rdi, WPP_GLOBAL_Control
0x1401306c5  cmp     rcx, rdi
0x1401306c8  jz      loc_140130420
0x1401306ce  test    byte ptr [rcx+1Ch], 20h
0x1401306d2  jz      loc_140130420
0x1401306d8  cmp     byte ptr [rcx+19h], 2
0x1401306dc  jb      loc_140130420
0x1401306e2  mov     edx, 31h ; '1'
0x1401306e7  jmp     short loc_14013067C
0x1401306e9  mov     r9, [rbp+47h+var_90]; HKEY
0x1401306ed  mov     r8, r13; struct _GUID *
0x1401306f0  mov     edx, r12d; unsigned int
0x1401306f3  mov     cl, r15b; unsigned __int8
0x1401306f6  call    ?SetRestoredVolumesString@@YAJEKPEAU_GUID@@PEAUHKEY__@@@Z; SetRestoredVolumesString(uchar,ulong,_GUID *,HKEY__ *)
0x1401306fb  mov     ebx, eax
0x1401306fd  test    eax, eax
0x1401306ff  jns     short loc_140130739
0x140130701  mov     rcx, cs:WPP_GLOBAL_Control
0x140130708  lea     rdi, WPP_GLOBAL_Control
0x14013070f  cmp     rcx, rdi
0x140130712  jz      loc_140130420
0x140130718  test    byte ptr [rcx+1Ch], 20h
0x14013071c  jz      loc_140130420
0x140130722  cmp     byte ptr [rcx+19h], 2
0x140130726  jb      loc_140130420
0x14013072c  mov     edx, 32h ; '2'
0x140130731  mov     r9d, eax
0x140130734  jmp     loc_14013067F
0x140130739  lea     rcx, [rbp+47h+Uuid]; Uuid
0x14013073d  call    cs:__imp_UuidCreate
0x140130743  test    eax, eax
0x140130745  jz      short loc_140130751
0x140130747  mov     ebx, 80004005h
0x14013074c  jmp     loc_140130419
0x140130751  lea     rdx, [rbp+47h+String]; StringUuid
0x140130755  lea     rcx, [rbp+47h+Uuid]; Uuid
0x140130759  call    cs:__imp_UuidToStringW
0x14013075f  test    eax, eax
0x140130761  jnz     short loc_140130747
0x140130763  mov     rcx, [rbp+47h+String]
0x140130767  or      rax, 0FFFFFFFFFFFFFFFFh
0x14013076b  inc     rax
0x14013076e  cmp     [rcx+rax*2], si
0x140130772  jnz     short loc_14013076B
0x140130774  lea     eax, ds:2[rax*2]
0x14013077b  mov     r9d, 1; dwType
0x140130781  mov     [rsp+0F0h+samDesired], eax; cbData
0x140130785  lea     rdx, aLastinstance; "LastInstance"
0x14013078c  mov     [rsp+0F0h+phkResult], rcx; lpData
0x140130791  xor     r8d, r8d; Reserved
0x140130794  mov     rcx, [rbp+47h+var_90]; hKey
  ... truncated ...
```
