# CAgentProtocolTalker::PopulateAuthCookies(CAgentProtocolTalkerContext const *,CSusArrayList<SusWsStructs::SusAuthorizationCookie,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusAuthorizationCookie>> &)

- ea: `0x18006fc3c`
- end: `0x180070401`
- name: `?PopulateAuthCookies@CAgentProtocolTalker@@AEAAJPEBVCAgentProtocolTalkerContext@@AEAV?$CSusArrayList@USusAuthorizationCookie@SusWsStructs@@V?$CSusArrayListItemOpSusServiceStruct@USusAuthorizationCookie@SusWsStructs@@@@@@@Z`
- size: `1989`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180070408`

## callees

- `0x18000def4`
- `0x180014964`
- `0x18003b350`
- `0x180060988`
- `0x180062ab0`
- `0x180065acc`
- `0x180065c94`
- `0x18006fc3c`
- `0x180070b68`
- `0x180070c10`
- `0x180070ca8`
- `0x180070ebc`
- `0x180079e5c`
- `0x180109994`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x18012d944`
- `0x1801c0108`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006fce7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006fe5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006fce7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006fe5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006fd1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ff1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006fd1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ff1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006fdc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006fe32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070078`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006fdc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006fe32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070078`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ff12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ff12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fed3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fed3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800700c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800700c9`

## string_xrefs

- `0x18007027d`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800702b9`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800702db`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800702f4`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x180070320`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x180070365`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800703ab`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x1800703e2`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x18006fec5`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAgentProtocolTalker::PopulateAuthCookies(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v5; // rdi
  int v6; // esi
  __int64 v7; // rdx
  int v8; // r14d
  __int64 v9; // r12
  __int64 v10; // r13
  const WCHAR *v11; // r8
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdi
  int v15; // r14d
  unsigned int v16; // eax
  int EndpointUrlAndToken; // eax
  char v18; // al
  int v19; // eax
  CSusClientId *v20; // rcx
  int SusClientId; // eax
  CAuthorizationCookieWrapper *v22; // rcx
  wchar_t *v23; // rdi
  int Utf8BufSize; // eax
  unsigned __int64 v25; // rsi
  char *v26; // rax
  CAuthorizationCookieWrapper *v27; // rcx
  int v28; // eax
  char v29; // al
  __int64 v31; // r9
  __int64 v32; // rdx
  HKEY v33; // rcx
  __int64 v34; // rdx
  int lpString2; // [rsp+28h] [rbp-E0h]
  int v36; // [rsp+68h] [rbp-A0h]
  HKEY phkResult; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-50h] BYREF
  char v41; // [rsp+C0h] [rbp-48h] BYREF
  char v42; // [rsp+C1h] [rbp-47h]
  int v43; // [rsp+C4h] [rbp-44h] BYREF
  unsigned int v44[2]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v45; // [rsp+D0h] [rbp-38h]
  __int128 v46; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v47[24]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v48; // [rsp+100h] [rbp-8h] BYREF
  __int64 v49; // [rsp+110h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  v3 = a3;
  v46 = 0;
  *(_QWORD *)&v46 = *(_QWORD *)(a1 + 64);
  BYTE8(v46) = 0;
  memset(v47, 0, sizeof(v47));
  v43 = 0;
  v40 = 0;
  v42 = 1;
  CSusArrayList<SusWsStructs::SusAuthorizationCookie,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusAuthorizationCookie>>::RemoveArraySection(a3);
  v5 = *(_QWORD *)(a2 + 96);
  v40 = 0;
  v43 = 0;
  AcquireSRWLockShared((PSRWLOCK)(v5 + 40));
  v6 = CSusService::ValidateServerConfigState((CSusService *)v5);
  if ( v6 >= 0 )
    v6 = CopySusStructArray<SusWsStructs::SusAuthPlugInInfo>(
           &v43,
           &v40,
           *(unsigned int *)(v5 + 344),
           *(_QWORD *)(v5 + 336));
  ReleaseSRWLockShared((PSRWLOCK)(v5 + 40));
  if ( v6 >= 0 )
  {
    v8 = 0;
    v36 = 0;
    if ( v43 <= 0 )
    {
LABEL_51:
      v29 = 0;
      v42 = 0;
      v6 = 0;
      goto LABEL_52;
    }
    v9 = 0;
    while ( 1 )
    {
      v10 = v40;
      if ( (***(unsigned int (__fastcall ****)(_QWORD))a2)(*(_QWORD *)a2) )
      {
        v6 = -2145124341;
        wil::details::in1diag3::Return_HrSuppressTelemetry(
          retaddr,
          (void *)0x12ED,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
          (const char *)0x8024000BLL,
          lpString2);
        goto LABEL_80;
      }
      v11 = *(const WCHAR **)(v9 + v10);
      if ( !v11 )
        break;
      if ( CompareStringW(0x7Fu, 1u, v11, -1, L"Anonymous", -1) == 2 )
      {
        if ( *(_QWORD *)&c_idSrvWU.Data1 == *(_QWORD *)(a2 + 8) && *(_QWORD *)c_idSrvWU.Data4 == *(_QWORD *)(a2 + 16) )
        {
          WUTrace(0, 0, 8, 3, 0, L"PTWarn: Anonymous plug-in skipped for WU");
          goto LABEL_49;
        }
        v12 = CAuthorizationCookieWrapper::InitializeAnonymousCookie((CAuthorizationCookieWrapper *)&v46);
        v6 = v12;
        if ( v12 < 0 )
        {
          v13 = (unsigned int)v12;
          v7 = 4859;
          goto LABEL_61;
        }
      }
      else if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v9 + v10), -1, L"SimpleTargeting", -1) == 2 )
      {
        v14 = *(_QWORD *)(a2 + 96);
        phkResult = 0;
        v44[0] = 0;
        v15 = 1;
        AcquireSRWLockShared((PSRWLOCK)(v14 + 40));
        v6 = CSusService::ValidateServerConfigState((CSusService *)v14);
        if ( v6 >= 0 && *(double *)(v14 + 384) < 4.0 )
        {
          v15 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
          if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14)
            && (unsigned int)AreTestKeysAllowed(1)
            && !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                  0,
                  0x20019u,
                  &phkResult) )
          {
            if ( phkResult && RegQueryDwordValue(phkResult, L"AllowSimpleTargettingForNonManaged", v44) >= 0 )
            {
              v16 = v44[0];
            }
            else
            {
              v16 = 0;
              v44[0] = 0;
            }
            v15 = v16 == 1;
            RegCloseKey(phkResult);
          }
        }
        ReleaseSRWLockShared((PSRWLOCK)(v14 + 40));
        if ( v6 < 0 )
        {
          v7 = 4871;
          goto LABEL_60;
        }
        if ( !v15 )
        {
          WUTrace(0, 0, 8, 3, 0, L"Skipping SimpleTargeting plug-in because it is no longer allowed.");
          goto LABEL_30;
        }
        v45 = 0;
        lpString2 = 0;
        EndpointUrlAndToken = CSusService::GetEndpointUrlAndToken(
                                *(_QWORD *)(a2 + 96),
                                3,
                                *(_QWORD *)(a1 + 128),
                                *(_QWORD *)(a2 + 40));
        v6 = EndpointUrlAndToken;
        if ( EndpointUrlAndToken < 0 )
        {
          if ( EndpointUrlAndToken != -2145123265 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x131D,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
              (const char *)(unsigned int)EndpointUrlAndToken,
              0);
            goto LABEL_80;
          }
LABEL_30:
          v8 = v36;
LABEL_49:
          v3 = a3;
          goto LABEL_50;
        }
        v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 96) + 24LL))(*(_QWORD *)(a2 + 96));
        v19 = CAuthorizationCookieWrapper::InitializeSimpleTargetingCookie(
                (CAuthorizationCookieWrapper *)&v46,
                *(const struct CCallerIdentity **)(a2 + 40),
                *(struct CSusSettingCache **)(a1 + 40),
                0,
                *(const wchar_t **)(v9 + v10 + 8),
                v45,
                v18,
                *(const char **)(a2 + 392),
                (*(_DWORD *)(a2 + 48) & 0x100000) != 0,
                *(_DWORD *)(a2 + 48) & 0x10000);
        v6 = v19;
        if ( v19 < 0 )
        {
          v13 = (unsigned int)v19;
          v7 = 4908;
          goto LABEL_61;
        }
        v8 = v36;
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v9 + v10), -1, L"PidValidator", -1) != 2 )
        {
          WUTrace(0, 0, 8, 3, 0, L"PTWarn: Unknown auth plug-in %ws is skipped");
          goto LABEL_49;
        }
        phkResult = 0;
        *(_QWORD *)v44 = 0;
        v41 = 1;
        v49 = 1;
        *(_QWORD *)&v48 = &v41;
        *((_QWORD *)&v48 + 1) = &v46;
        if ( BYTE8(v46) )
        {
          v6 = -2145107950;
          v34 = 5275;
LABEL_76:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
            (const char *)(unsigned int)v6,
            lpString2);
          if ( v41 )
            SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)v47);
          goto LABEL_78;
        }
        *(_QWORD *)v47 = SysAllocString(L"PidValidator");
        if ( !*(_QWORD *)v47 )
        {
          v6 = -2147024882;
          v34 = 5278;
          goto LABEL_76;
        }
        SusClientId = CSusClientId::GetSusClientId(v20, (wchar_t **)&phkResult);
        v6 = SusClientId;
        if ( SusClientId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A1,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
            (const char *)(unsigned int)SusClientId,
            lpString2);
          if ( v41 )
            SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)v47);
          v33 = phkResult;
          if ( phkResult )
LABEL_68:
            SusFree(v33);
LABEL_78:
          v7 = 4913;
          goto LABEL_60;
        }
        v23 = (wchar_t *)phkResult;
        Utf8BufSize = CAuthorizationCookieWrapper::GetUtf8BufSize(
                        v22,
                        (const wchar_t *)phkResult,
                        (unsigned __int64 *)v44);
        v6 = Utf8BufSize;
        if ( Utf8BufSize < 0 )
        {
          v31 = (unsigned int)Utf8BufSize;
          v32 = 5285;
LABEL_64:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v32,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
            (const char *)v31,
            lpString2);
          if ( v41 )
            SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)v47);
          if ( v23 )
          {
            v33 = (HKEY)v23;
            goto LABEL_68;
          }
          goto LABEL_78;
        }
        v25 = *(_QWORD *)v44;
        v26 = (char *)SafeSusAllocArray(*(unsigned __int64 *)v44, 1u);
        *(_QWORD *)&v47[16] = v26;
        if ( !v26 )
        {
          v6 = -2147024882;
          v31 = 2147942414LL;
          v32 = 5288;
          goto LABEL_64;
        }
        *(_DWORD *)&v47[8] = v25;
        v28 = CAuthorizationCookieWrapper::WriteUnicodeToUtf8(v27, v26, v25, v23);
        v6 = v28;
        if ( v28 < 0 )
        {
          v31 = (unsigned int)v28;
          v32 = 5292;
          goto LABEL_64;
        }
        BYTE8(v46) = 1;
        v41 = 0;
        if ( v23 )
          SusFree(v23);
      }
      v48 = 0;
      v49 = 0;
      if ( !BYTE8(v46) )
      {
        v6 = -2145124348;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1547,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
          (const char *)0x80240004LL,
          lpString2);
        v7 = 4927;
        goto LABEL_60;
      }
      SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)&v48);
      v48 = *(_OWORD *)v47;
      v49 = *(_QWORD *)&v47[16];
      memset(v47, 0, sizeof(v47));
      BYTE8(v46) = 0;
      v3 = a3;
      v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)a3 + 8LL))(a3, &v48, 0);
      if ( v6 < 0 )
      {
        SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)&v48);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1349,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
          (const char *)(unsigned int)v6,
          lpString2);
        goto LABEL_81;
      }
LABEL_50:
      v36 = ++v8;
      v9 += 24;
      if ( v8 >= v43 )
        goto LABEL_51;
    }
    WUTrace(0, 0, 8, 3, 0, L"PTWarn: Auth plug-in name is invalid. Ignoring plug-in");
    goto LABEL_49;
  }
  v7 = 4839;
LABEL_60:
  v13 = (unsigned int)v6;
LABEL_61:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
    (const char *)v13,
    lpString2);
LABEL_80:
  v3 = a3;
LABEL_81:
  v29 = v42;
LABEL_52:
  if ( v29 )
    CSusArrayList<SusWsStructs::SusAuthorizationCookie,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusAuthorizationCookie>>::RemoveArraySection(v3);
  SafeSusStructArrayFree<SusWsStructs::SusAuthPlugInInfo>((unsigned int)v43, v40);
  SusWsStructs::SusAuthorizationCookie::Clear((SusWsStructs::SusAuthorizationCookie *)v47);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006fc3c  mov     rax, rsp
0x18006fc3f  mov     [rax+20h], rbx
0x18006fc43  push    rbp
0x18006fc44  push    rsi
0x18006fc45  push    rdi
0x18006fc46  push    r12
0x18006fc48  push    r13
0x18006fc4a  push    r14
0x18006fc4c  push    r15
0x18006fc4e  lea     rbp, [rax-68h]
0x18006fc52  sub     rsp, 130h
0x18006fc59  movaps  xmmword ptr [rax-48h], xmm6
0x18006fc5d  mov     rax, cs:__security_cookie
0x18006fc64  xor     rax, rsp
0x18006fc67  mov     [rbp+60h+var_50], rax
0x18006fc6b  mov     r13, r8
0x18006fc6e  mov     [rsp+160h+var_F8], r8
0x18006fc73  mov     r15, rdx
0x18006fc76  mov     [rsp+160h+var_E8], rcx
0x18006fc7b  xorps   xmm0, xmm0
0x18006fc7e  movups  [rbp+60h+var_90], xmm0
0x18006fc82  mov     rax, [rcx+40h]
0x18006fc86  mov     qword ptr [rbp+60h+var_90], rax
0x18006fc8a  xor     r12d, r12d
0x18006fc8d  mov     byte ptr [rbp+60h+var_90+8], r12b
0x18006fc91  xor     eax, eax
0x18006fc93  movups  [rbp+60h+var_80], xmm0
0x18006fc97  mov     [rbp+60h+var_70], rax
0x18006fc9b  mov     ebx, r12d
0x18006fc9e  mov     [rsp+160h+var_F0], rbx
0x18006fca3  mov     [rbp+60h+var_A4], r12d
0x18006fca7  mov     [rbp+60h+var_B0], r12
0x18006fcab  mov     [rbp+60h+var_A7], 1
0x18006fcaf  lea     rax, [rbp+60h+var_A7]
0x18006fcb3  mov     [rbp+60h+var_E0], rax
0x18006fcb7  mov     [rbp+60h+var_D8], r8
0x18006fcbb  lea     rax, [rbp+60h+var_A4]
0x18006fcbf  mov     [rbp+60h+var_D0], rax
0x18006fcc3  lea     rax, [rbp+60h+var_B0]
0x18006fcc7  mov     [rbp+60h+var_C8], rax
0x18006fccb  mov     [rbp+60h+var_C0], 1
0x18006fccf  mov     rcx, r8
0x18006fcd2  call    ?RemoveArraySection@?$CSusArrayList@USusAuthorizationCookie@SusWsStructs@@V?$CSusArrayListItemOpSusServiceStruct@USusAuthorizationCookie@SusWsStructs@@@@@@IEAAXKKH@Z; CSusArrayList<SusWsStructs::SusAuthorizationCookie,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusAuthorizationCookie>>::RemoveArraySection(ulong,ulong,int)
0x18006fcd7  mov     rdi, [r15+60h]
0x18006fcdb  mov     [rbp+60h+var_B0], r12
0x18006fcdf  mov     [rbp+60h+var_A4], r12d
0x18006fce3  lea     rcx, [rdi+28h]; SRWLock
0x18006fce7  call    cs:__imp_AcquireSRWLockShared
0x18006fced  mov     rcx, rdi; this
0x18006fcf0  call    ?ValidateServerConfigState@CSusService@@AEAAJXZ; CSusService::ValidateServerConfigState(void)
0x18006fcf5  mov     esi, eax
0x18006fcf7  test    eax, eax
0x18006fcf9  js      short loc_18006FD18
0x18006fcfb  mov     r9, [rdi+150h]
0x18006fd02  mov     r8d, [rdi+158h]
0x18006fd09  lea     rdx, [rbp+60h+var_B0]
0x18006fd0d  lea     rcx, [rbp+60h+var_A4]
0x18006fd11  call    ??$CopySusStructArray@USusAuthPlugInInfo@SusWsStructs@@@@YAJPEAHPEAPEAUSusAuthPlugInInfo@SusWsStructs@@HPEBU01@@Z; CopySusStructArray<SusWsStructs::SusAuthPlugInInfo>(int *,SusWsStructs::SusAuthPlugInInfo * *,int,SusWsStructs::SusAuthPlugInInfo const *)
0x18006fd16  mov     esi, eax
0x18006fd18  lea     rcx, [rdi+28h]; SRWLock
0x18006fd1c  call    cs:__imp_ReleaseSRWLockShared
0x18006fd22  test    esi, esi
0x18006fd24  jns     short loc_18006FD30
0x18006fd26  mov     edx, 12E7h
0x18006fd2b  jmp     loc_1800702F1
0x18006fd30  xor     r14d, r14d
0x18006fd33  mov     dword ptr [rsp+160h+var_100], r14d
0x18006fd38  cmp     [rbp+60h+var_A4], r14d
0x18006fd3c  jle     loc_180070211
0x18006fd42  xor     r12d, r12d
0x18006fd45  lea     rdi, ?c_szAuthPlugInPID@@3QB_WB; "PidValidator"
0x18006fd4c  movsd   xmm6, cs:__real@4010000000000000
0x18006fd54  mov     r13, [rbp+60h+var_B0]
0x18006fd58  mov     rcx, [r15]
0x18006fd5b  mov     rax, [rcx]
0x18006fd5e  mov     rax, [rax]
0x18006fd61  call    _guard_dispatch_icall
0x18006fd66  test    eax, eax
0x18006fd68  jnz     loc_1800703D6
0x18006fd6e  mov     r8, [r12+r13]; lpString1
0x18006fd72  test    r8, r8
0x18006fd75  jnz     short loc_18006FDA2
0x18006fd77  lea     rax, aPtwarnAuthPlug; "PTWarn: Auth plug-in name is invalid. I"...
0x18006fd7e  mov     qword ptr [rsp+160h+cchCount2], rax
0x18006fd83  mov     [rsp+160h+lpString2], 0
0x18006fd8c  xor     edx, edx
0x18006fd8e  xor     ecx, ecx
0x18006fd90  lea     r9d, [rdx+3]
0x18006fd94  lea     r8d, [rdx+8]
0x18006fd98  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18006fd9d  jmp     loc_1800701F6
0x18006fda2  mov     [rsp+160h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006fdaa  lea     rax, ?c_szAuthPlugInAnonymous@@3QB_WB; "Anonymous"
0x18006fdb1  mov     [rsp+160h+lpString2], rax; lpString2
0x18006fdb6  or      r9d, 0FFFFFFFFh; cchCount1
0x18006fdba  lea     edx, [r9+2]; dwCmpFlags
0x18006fdbe  lea     ecx, [rdx+7Eh]; Locale
0x18006fdc1  call    cs:__imp_CompareStringW
0x18006fdc7  cmp     eax, 2
0x18006fdca  jnz     short loc_18006FE0F
0x18006fdcc  mov     rax, qword ptr cs:c_idSrvWU.Data1
0x18006fdd3  cmp     rax, [r15+8]
0x18006fdd7  jnz     short loc_18006FDEF
0x18006fdd9  mov     rax, qword ptr cs:c_idSrvWU.Data4
0x18006fde0  cmp     rax, [r15+10h]
0x18006fde4  jnz     short loc_18006FDEF
0x18006fde6  lea     rax, aPtwarnAnonymou; "PTWarn: Anonymous plug-in skipped for W"...
0x18006fded  jmp     short loc_18006FD7E
0x18006fdef  lea     rcx, [rbp+60h+var_90]; this
0x18006fdf3  call    ?InitializeAnonymousCookie@CAuthorizationCookieWrapper@@QEAAJXZ; CAuthorizationCookieWrapper::InitializeAnonymousCookie(void)
0x18006fdf8  mov     esi, eax
0x18006fdfa  test    eax, eax
0x18006fdfc  jns     loc_180070159
0x18006fe02  mov     r9d, eax
0x18006fe05  mov     edx, 12FBh
0x18006fe0a  jmp     loc_1800702F4
0x18006fe0f  mov     [rsp+160h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006fe17  lea     rax, ?c_szAuthPlugInSimpleTargeting@@3QB_WB; "SimpleTargeting"
0x18006fe1e  mov     [rsp+160h+lpString2], rax; lpString2
0x18006fe23  or      r9d, 0FFFFFFFFh; cchCount1
0x18006fe27  mov     r8, [r12+r13]; lpString1
0x18006fe2b  lea     edx, [r9+2]; dwCmpFlags
0x18006fe2f  lea     ecx, [rdx+7Eh]; Locale
0x18006fe32  call    cs:__imp_CompareStringW
0x18006fe38  cmp     eax, 2
0x18006fe3b  jnz     loc_18007005C
0x18006fe41  mov     rdi, [r15+60h]
0x18006fe45  mov     [rbp+60h+phkResult], 0
0x18006fe4d  mov     [rbp+60h+var_A0], 0
0x18006fe54  lea     r14d, [rax-1]
0x18006fe58  lea     rcx, [rdi+28h]; SRWLock
0x18006fe5c  call    cs:__imp_AcquireSRWLockShared
0x18006fe62  mov     rcx, rdi; this
0x18006fe65  call    ?ValidateServerConfigState@CSusService@@AEAAJXZ; CSusService::ValidateServerConfigState(void)
0x18006fe6a  mov     esi, eax
0x18006fe6c  test    eax, eax
0x18006fe6e  js      loc_18006FF18
0x18006fe74  comisd  xmm6, qword ptr [rdi+180h]
0x18006fe7c  jbe     loc_18006FF18
0x18006fe82  mov     rax, [rdi]
0x18006fe85  mov     rcx, rdi
0x18006fe88  mov     rax, [rax+18h]
0x18006fe8c  call    _guard_dispatch_icall
0x18006fe91  movzx   r14d, al
0x18006fe95  mov     rax, [rdi]
0x18006fe98  mov     rcx, rdi
0x18006fe9b  mov     rax, [rax+18h]
0x18006fe9f  call    _guard_dispatch_icall
0x18006fea4  test    al, al
0x18006fea6  jnz     short loc_18006FF18
0x18006fea8  mov     cl, 1; bool
0x18006feaa  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18006feaf  test    eax, eax
0x18006feb1  jz      short loc_18006FF18
0x18006feb3  lea     rax, [rbp+60h+phkResult]
0x18006feb7  mov     [rsp+160h+lpString2], rax; phkResult
0x18006febc  mov     r9d, 20019h; samDesired
0x18006fec2  xor     r8d, r8d; ulOptions
0x18006fec5  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006fecc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fed3  call    cs:__imp_RegOpenKeyExW
0x18006fed9  test    eax, eax
0x18006fedb  jnz     short loc_18006FF18
0x18006fedd  mov     rcx, [rbp+60h+phkResult]; HKEY
0x18006fee1  test    rcx, rcx
0x18006fee4  jz      short loc_18006FEFF
0x18006fee6  lea     r8, [rbp+60h+var_A0]; unsigned int *
0x18006feea  lea     rdx, aAllowsimpletar; "AllowSimpleTargettingForNonManaged"
0x18006fef1  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18006fef6  test    eax, eax
0x18006fef8  js      short loc_18006FEFF
0x18006fefa  mov     eax, [rbp+60h+var_A0]
0x18006fefd  jmp     short loc_18006FF04
0x18006feff  xor     eax, eax
0x18006ff01  mov     [rbp+60h+var_A0], eax
0x18006ff04  xor     r14d, r14d
0x18006ff07  cmp     eax, 1
0x18006ff0a  setz    r14b
0x18006ff0e  mov     rcx, [rbp+60h+phkResult]; hKey
0x18006ff12  call    cs:__imp_RegCloseKey
0x18006ff18  lea     rcx, [rdi+28h]; SRWLock
0x18006ff1c  call    cs:__imp_ReleaseSRWLockShared
0x18006ff22  test    esi, esi
0x18006ff24  js      loc_1800702A2
0x18006ff2a  test    r14d, r14d
0x18006ff2d  jnz     short loc_18006FF66
0x18006ff2f  lea     rax, aSkippingSimple; "Skipping SimpleTargeting plug-in becaus"...
0x18006ff36  mov     qword ptr [rsp+160h+cchCount2], rax
0x18006ff3b  mov     [rsp+160h+lpString2], 0
0x18006ff44  xor     edx, edx
0x18006ff46  xor     ecx, ecx
0x18006ff48  lea     r9d, [r14+3]
0x18006ff4c  lea     r8d, [r14+8]
0x18006ff50  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18006ff55  mov     r14d, dword ptr [rsp+160h+var_100]
0x18006ff5a  lea     rdi, ?c_szAuthPlugInPID@@3QB_WB; "PidValidator"
0x18006ff61  jmp     loc_1800701F6
0x18006ff66  mov     [rbp+60h+var_98], 0
0x18006ff6d  mov     rdi, [r15+60h]
0x18006ff71  mov     rsi, [r15+68h]
0x18006ff75  xor     r14d, r14d
0x18006ff78  test    rbx, rbx
0x18006ff7b  jz      short loc_18006FF8A
0x18006ff7d  mov     rcx, rbx; lpMem
0x18006ff80  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006ff85  mov     [rsp+160h+var_F0], r14
0x18006ff8a  mov     [rsp+160h+var_110], rsi
0x18006ff8f  lea     rax, [rbp+60h+var_98]
0x18006ff93  mov     qword ptr [rsp+160h+var_118], rax
0x18006ff98  mov     qword ptr [rsp+160h+var_120], r14
0x18006ff9d  lea     rax, [rsp+160h+var_F0]
0x18006ffa2  mov     [rsp+160h+var_128], rax
0x18006ffa7  mov     dword ptr [rsp+160h+lpString2], r14d; int
0x18006ffac  mov     r9, [r15+28h]
0x18006ffb0  mov     r14, [rsp+160h+var_E8]
0x18006ffb5  mov     r8, [r14+80h]
0x18006ffbc  mov     edx, 3
0x18006ffc1  mov     rcx, rdi
0x18006ffc4  call    ?GetEndpointUrlAndToken@CSusService@@QEAAJW4tagEndpointType@@PEAXPEBVCCallerIdentity@@HIPEBU_GUID@@PEAPEA_WPEAPEAVCWsSecurityToken@@PEAKPEAVISupportSusServiceExtendedResult@@@Z; CSusService::GetEndpointUrlAndToken(tagEndpointType,void *,CCallerIdentity const *,int,uint,_GUID const *,wchar_t * *,CWsSecurityToken * *,ulong *,ISupportSusServiceExtendedResult *)
0x18006ffc9  mov     esi, eax
0x18006ffcb  test    eax, eax
0x18006ffcd  jns     short loc_18006FFE4
0x18006ffcf  cmp     eax, 8024043Fh
0x18006ffd4  jnz     loc_180070276
0x18006ffda  mov     rbx, [rsp+160h+var_F0]
0x18006ffdf  jmp     loc_18006FF55
0x18006ffe4  mov     rcx, [r15+60h]
0x18006ffe8  mov     rax, [rcx]
0x18006ffeb  mov     rax, [rax+18h]
0x18006ffef  call    _guard_dispatch_icall
0x18006fff4  mov     edx, [r15+30h]
0x18006fff8  mov     edi, [rbp+60h+var_98]
0x18006fffb  mov     ecx, edx
0x18006fffd  shr     ecx, 10h
0x180070000  and     cl, 1
0x180070003  shr     edx, 14h
0x180070006  and     dl, 1
0x180070009  mov     [rsp+160h+var_118], cl; bool
0x18007000d  mov     [rsp+160h+var_120], dl; bool
0x180070011  mov     rcx, [r15+188h]
0x180070018  mov     [rsp+160h+var_128], rcx; char *
0x18007001d  mov     [rsp+160h+var_130], al; bool
0x180070021  mov     [rsp+160h+cchCount2], edi; unsigned int
0x180070025  mov     rax, [r12+r13+8]
0x18007002a  mov     [rsp+160h+lpString2], rax; wchar_t *
0x18007002f  mov     rbx, [rsp+160h+var_F0]
0x180070034  mov     r9, rbx; wchar_t *
0x180070037  mov     r8, [r14+28h]; struct CSusSettingCache *
0x18007003b  mov     rdx, [r15+28h]; struct CCallerIdentity *
0x18007003f  lea     rcx, [rbp+60h+var_90]; this
0x180070043  call    ?InitializeSimpleTargetingCookie@CAuthorizationCookieWrapper@@QEAAJPEBVCCallerIdentity@@PEAVCSusSettingCache@@PEB_W2K_NPEBD33@Z; CAuthorizationCookieWrapper::InitializeSimpleTargetingCookie(CCallerIdentity const *,CSusSettingCache *,wchar_t const *,wchar_t const *,ulong,bool,char const *,bool,bool)
0x180070048  mov     esi, eax
0x18007004a  test    eax, eax
0x18007004c  js      loc_180070298
0x180070052  mov     r14d, dword ptr [rsp+160h+var_100]
0x180070057  jmp     loc_180070159
0x18007005c  mov     [rsp+160h+cchCount2], 0FFFFFFFFh; cchCount2
0x180070064  mov     [rsp+160h+lpString2], rdi; int
0x180070069  or      r9d, 0FFFFFFFFh; cchCount1
0x18007006d  mov     r8, [r12+r13]; lpString1
0x180070071  lea     edx, [r9+2]; dwCmpFlags
0x180070075  lea     ecx, [rdx+7Eh]; Locale
0x180070078  call    cs:__imp_CompareStringW
0x18007007e  cmp     eax, 2
0x180070081  jnz     loc_1800701C7
0x180070087  mov     [rbp+60h+phkResult], 0
0x18007008f  mov     qword ptr [rbp+60h+var_A0], 0
0x180070097  mov     [rbp+60h+var_A8], 1
0x18007009b  xorps   xmm0, xmm0
0x18007009e  xor     eax, eax
0x1800700a0  movups  [rbp+60h+var_68], xmm0
0x1800700a4  mov     [rbp+60h+var_58], rax
0x1800700a8  lea     rax, [rbp+60h+var_A8]
0x1800700ac  mov     qword ptr [rbp+60h+var_68], rax
0x1800700b0  lea     rax, [rbp+60h+var_90]
0x1800700b4  mov     qword ptr [rbp+60h+var_68+8], rax
0x1800700b8  mov     byte ptr [rbp+60h+var_58], 1
0x1800700bc  cmp     byte ptr [rbp+60h+var_90+8], 0
0x1800700c0  jnz     loc_18007039E
0x1800700c6  mov     rcx, rdi; psz
0x1800700c9  call    cs:__imp_SysAllocString
0x1800700cf  mov     qword ptr [rbp+60h+var_80], rax
0x1800700d3  test    rax, rax
0x1800700d6  jz      loc_180070392
0x1800700dc  lea     rdx, [rbp+60h+phkResult]; wchar_t **
0x1800700e0  call    ?GetSusClientId@CSusClientId@@QEAAJPEAPEA_W@Z; CSusClientId::GetSusClientId(wchar_t * *)
0x1800700e5  mov     esi, eax
0x1800700e7  test    eax, eax
0x1800700e9  js      loc_18007035E
0x1800700ef  lea     r8, [rbp+60h+var_A0]; unsigned __int64 *
0x1800700f3  mov     rdi, [rbp+60h+phkResult]
0x1800700f7  mov     rdx, rdi; wchar_t *
0x1800700fa  call    ?GetUtf8BufSize@CAuthorizationCookieWrapper@@AEAAJPEB_WPEA_K@Z; CAuthorizationCookieWrapper::GetUtf8BufSize(wchar_t const *,unsigned __int64 *)
0x1800700ff  mov     esi, eax
0x180070101  xor     r13d, r13d
0x180070104  test    eax, eax
0x180070106  js      loc_180070354
0x18007010c  lea     edx, [r13+1]; unsigned __int64
0x180070110  mov     rsi, qword ptr [rbp+60h+var_A0]
0x180070114  mov     rcx, rsi; unsigned __int64
  ... truncated ...
```
