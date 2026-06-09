# Common::GetFileInUseProcessInformation(ulong,void *,Common::FileInUseProcessInformation &)

- ea: `0x1800ad028`
- end: `0x1800ad7d5`
- name: `?GetFileInUseProcessInformation@Common@@YAJKPEAXAEAUFileInUseProcessInformation@1@@Z`
- size: `1965`
- prototype: `int(Common *__hidden this, unsigned int, void *, struct Common::FileInUseProcessInformation *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180263264`

## callees

- `0x18000e8fc`
- `0x18001d350`
- `0x18006a6c4`
- `0x180078ca0`
- `0x1800ad028`
- `0x1800ad7dc`
- `0x1800bf144`
- `0x180190050`
- `0x180190196`
- `0x18027a9d8`
- `0x18027aa5c`
- `0x18027b98c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ad5a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ad5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad659`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad076`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad076`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800ad795`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800ad795`
- `ntdll!NtQueryInformationProcess` at `0x1800ad457`
- `ntdll!NtQueryInformationProcess` at `0x1800ad4fa`
- `ntdll!NtQueryInformationProcess` at `0x1800ad457`
- `ntdll!NtQueryInformationProcess` at `0x1800ad4fa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad526`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad526`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad319`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad3bd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad319`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad3bd`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800ad1c9`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800ad1c9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ad64b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ad769`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ad64b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ad769`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800ad147`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800ad147`

## string_xrefs

- `0x1800ad0af`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad0e3`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad122`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad170`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad1a4`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad1f2`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad226`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad273`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad2da`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad39f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad408`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad4d0`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad552`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad5da`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad6de`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ad090`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ad0c4`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ad0ff`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ad257`: `<Error 0x%X getting the user's SID from the process' token>`
- `0x1800ad187`: `<Error 0x%X in GetApplicationUserModelIdFromToken>`
- `0x1800ad5be`: `<Error 0x%X moving command line>`
- `0x1800ad2be`: `<Error 0x%X converting the user's SID to a string>`
- `0x1800ad6bb`: `<No commandline present>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Common::GetFileInUseProcessInformation(
        Common *this,
        void *a2,
        char *a3,
        struct Common::FileInUseProcessInformation *a4)
{
  PSID v6; // rbx
  __int64 LastError; // r15
  int v8; // eax
  int v9; // eax
  char *v10; // rsi
  int v11; // eax
  unsigned int ApplicationUserModelIdFromToken; // eax
  int v13; // eax
  int v14; // eax
  unsigned int PackageFullNameFromToken; // eax
  int v16; // eax
  int v17; // eax
  int UserSidFromToken; // eax
  int v19; // eax
  _DWORD *v20; // rsi
  int v21; // eax
  int v22; // eax
  DWORD v23; // esi
  unsigned __int64 v24; // rdx
  WCHAR *v25; // r14
  int v26; // eax
  unsigned __int64 v27; // rdx
  int v28; // eax
  char *v29; // rax
  ULONG v30; // r12d
  NTSTATUS v31; // eax
  int InformationProcess; // r14d
  unsigned __int64 v33; // rdx
  void *v34; // r14
  unsigned __int16 *v35; // rsi
  int v36; // eax
  unsigned __int64 v37; // rdx
  ULONG v38; // eax
  int v39; // eax
  unsigned __int16 *v40; // r14
  const void *v41; // rdx
  unsigned __int64 v42; // rsi
  int v43; // eax
  PSID v44; // r12
  unsigned __int64 v45; // rdx
  void *v46; // rsi
  void **v47; // r14
  int v48; // eax
  unsigned __int64 v49; // rdx
  WCHAR *v50; // rsi
  _QWORD *v51; // r15
  void *v52; // rdx
  unsigned __int64 v53; // rdx
  int ReturnLength; // [rsp+20h] [rbp-50h]
  int ReturnLengtha; // [rsp+20h] [rbp-50h]
  ULONG ProcessInformationLength; // [rsp+40h] [rbp-30h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-28h] BYREF
  PSID Sid; // [rsp+50h] [rbp-20h] BYREF
  PSID peUse; // [rsp+58h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD dwProcessId; // [rsp+B0h] [rbp+40h]
  DWORD dwSize; // [rsp+C8h] [rbp+58h] BYREF

  dwProcessId = (unsigned int)this;
  Common::FileInUseProcessInformation::Reset((Common::FileInUseProcessInformation *)a3);
  v6 = 0;
  peUse = 0;
  Sid = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(a2, 8u, &TokenHandle) )
  {
    applicationUserModelIdLength = 130;
    ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                        TokenHandle,
                                        &applicationUserModelIdLength,
                                        (PWSTR)a3 + 128);
    if ( ApplicationUserModelIdFromToken == 15703 )
    {
      v13 = StringCchCopyW((unsigned __int16 *)a3 + 128, 0x82u, L"<None>");
      if ( v13 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v13,
          ReturnLength);
    }
    else if ( ApplicationUserModelIdFromToken )
    {
      v14 = StringCchPrintfW(
              (unsigned __int16 *)a3 + 128,
              0x82u,
              L"<Error 0x%X in GetApplicationUserModelIdFromToken>",
              ApplicationUserModelIdFromToken);
      if ( v14 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v14,
          ReturnLength);
    }
    applicationUserModelIdLength = 128;
    PackageFullNameFromToken = GetPackageFullNameFromToken(TokenHandle, &applicationUserModelIdLength, (PWSTR)a3);
    if ( PackageFullNameFromToken == 15700 )
    {
      v16 = StringCchCopyW((unsigned __int16 *)a3, 0x80u, L"<None>");
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v16,
          ReturnLength);
    }
    else if ( PackageFullNameFromToken )
    {
      v17 = StringCchPrintfW(
              (unsigned __int16 *)a3,
              0x80u,
              L"<Error 0x%X in GetPackageFullName>",
              PackageFullNameFromToken);
      if ( v17 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v17,
          ReturnLength);
    }
    UserSidFromToken = Common::SidHelper::GetUserSidFromToken(TokenHandle, &peUse);
    v6 = peUse;
    if ( UserSidFromToken >= 0 )
    {
      Sid = peUse;
      v20 = a3 + 520;
      v21 = Common::SidHelper::ConvertSidToString(peUse, (struct Common::StringBuffer *)(a3 + 520));
      if ( v21 < 0 )
      {
        v22 = StringCchPrintfW(
                (unsigned __int16 *)a3 + 276,
                0x64u,
                L"<Error 0x%X converting the user's SID to a string>",
                (unsigned int)v21);
        if ( v22 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v22,
            ReturnLength);
      }
    }
    else
    {
      v19 = StringCchPrintfW(
              (unsigned __int16 *)a3 + 276,
              0x64u,
              L"<Error 0x%X getting the user's SID from the process' token>",
              (unsigned int)UserSidFromToken);
      if ( v19 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v19,
          ReturnLength);
      v20 = a3 + 520;
    }
    if ( *v20 )
      v10 = (char *)*((_QWORD *)a3 + 66);
    else
      v10 = a3 + 552;
  }
  else
  {
    LastError = GetLastError();
    v8 = StringCchPrintfW((unsigned __int16 *)a3 + 128, 0x82u, L"<Error 0x%X in OpenProcessToken>", LastError);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
    v9 = StringCchPrintfW((unsigned __int16 *)a3, 0x80u, L"<Error 0x%X in OpenProcessToken>", (unsigned int)LastError);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v9,
        ReturnLength);
    v10 = a3 + 552;
    v11 = StringCchPrintfW(
            (unsigned __int16 *)a3 + 276,
            0x64u,
            L"<Error 0x%X in OpenProcessToken>",
            (unsigned int)LastError);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v11,
        ReturnLength);
  }
  *((_QWORD *)a3 + 68) = v10;
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(a2, 0, (LPWSTR)a3 + 384, &dwSize) )
  {
    v23 = GetLastError();
    if ( v23 == 122 )
    {
      v25 = (WCHAR *)operator new[](saturated_mul(++dwSize, 2u));
      if ( *((WCHAR **)a3 + 95) == v25 )
      {
        v25 = (WCHAR *)*((_QWORD *)a3 + 95);
      }
      else
      {
        operator delete(*((void **)a3 + 95), v24);
        *((_QWORD *)a3 + 95) = v25;
      }
      if ( !v25 )
      {
        v26 = StringCchCopyW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error allocating memory>");
        if ( v26 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v26,
            ReturnLength);
        goto LABEL_43;
      }
      if ( QueryFullProcessImageNameW(a2, 0, v25, &dwSize) )
        goto LABEL_41;
      v23 = GetLastError();
      operator delete(*((void **)a3 + 95), v27);
      *((_QWORD *)a3 + 95) = 0;
    }
    if ( !v23 )
      goto LABEL_43;
LABEL_41:
    v28 = StringCchPrintfW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error 0x%X in QueryFullProcessImageNameW>", v23);
    if ( v28 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v28,
        ReturnLength);
  }
LABEL_43:
  v29 = (char *)*((_QWORD *)a3 + 95);
  if ( !v29 )
    v29 = a3 + 768;
  *((_QWORD *)a3 + 94) = v29;
  ProcessInformationLength = 0;
  v30 = 520;
  v31 = NtQueryInformationProcess(
          a2,
          ProcessImageFileMapping|ProcessUserModeIOPL,
          a3 + 1344,
          0x208u,
          &ProcessInformationLength);
  InformationProcess = v31;
  if ( v31 >= 0 )
  {
    v35 = (unsigned __int16 *)(a3 + 1344);
  }
  else
  {
    if ( v31 != -1073741820 )
    {
      v35 = (unsigned __int16 *)(a3 + 1344);
LABEL_56:
      v38 = RtlNtStatusToDosErrorNoTeb(InformationProcess);
      v39 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X in NtQueryInformationProcess>", v38);
      if ( v39 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v39,
          ReturnLengtha);
      goto LABEL_68;
    }
    v34 = operator new[](ProcessInformationLength);
    if ( *((void **)a3 + 167) == v34 )
    {
      v35 = (unsigned __int16 *)(a3 + 1344);
      v34 = (void *)*((_QWORD *)a3 + 167);
    }
    else
    {
      operator delete(*((void **)a3 + 167), v33);
      *((_QWORD *)a3 + 167) = v34;
      v35 = (unsigned __int16 *)(a3 + 1344);
    }
    if ( !v34 )
    {
      v36 = StringCchCopyW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error allocating memory>");
      if ( v36 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v36,
          ReturnLengtha);
LABEL_68:
      v40 = v35;
      goto LABEL_69;
    }
    InformationProcess = NtQueryInformationProcess(
                           a2,
                           ProcessImageFileMapping|ProcessUserModeIOPL,
                           v34,
                           ProcessInformationLength,
                           0);
    if ( InformationProcess < 0 )
    {
      operator delete(*((void **)a3 + 167), v37);
      *((_QWORD *)a3 + 167) = 0;
      goto LABEL_56;
    }
  }
  v40 = (unsigned __int16 *)*((_QWORD *)a3 + 167);
  if ( v40 )
    v30 = ProcessInformationLength;
  else
    v40 = v35;
  v41 = (const void *)*((_QWORD *)v40 + 1);
  if ( !v41 )
  {
    v48 = StringCchCopyW(v35, 0x104u, L"<No commandline present>");
    if ( v48 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v48,
        ReturnLengtha);
    goto LABEL_68;
  }
  v42 = *v40;
  if ( *v40 )
  {
    if ( v30 < v42 )
    {
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
      v43 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X moving command line>", 34);
      if ( v43 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v43,
          ReturnLengtha);
      v35 = (unsigned __int16 *)(a3 + 1344);
      goto LABEL_68;
    }
    memmove_0(v40, v41, *v40);
  }
  v40[v42 >> 1] = 0;
LABEL_69:
  *((_QWORD *)a3 + 166) = v40;
  v44 = Sid;
  if ( Sid )
  {
    LODWORD(Sid) = 0;
    cchReferencedDomainName = 0;
    LODWORD(peUse) = 0;
    if ( !LookupAccountSidW(0, v44, 0, (LPDWORD)&Sid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&peUse)
      && GetLastError() == 122 )
    {
      v46 = operator new[](saturated_mul(cchReferencedDomainName, 2u));
      v47 = (void **)(a3 + 1288);
      if ( *((void **)a3 + 161) == v46 )
      {
        v46 = *v47;
      }
      else
      {
        operator delete(*v47, v45);
        *v47 = v46;
      }
      if ( v46 )
      {
        v50 = (WCHAR *)operator new[](saturated_mul((unsigned int)Sid, 2u));
        if ( *((WCHAR **)a3 + 162) == v50 )
        {
          v51 = a3 + 1288;
          v50 = (WCHAR *)*((_QWORD *)a3 + 162);
        }
        else
        {
          operator delete(*((void **)a3 + 162), v49);
          *((_QWORD *)a3 + 162) = v50;
          v51 = a3 + 1288;
        }
        if ( v50
          && LookupAccountSidW(
               0,
               v44,
               v50,
               (LPDWORD)&Sid,
               (LPWSTR)*v47,
               &cchReferencedDomainName,
               (PSID_NAME_USE)&peUse) )
        {
          *((_QWORD *)a3 + 163) = *v51;
          *((_QWORD *)a3 + 164) = *((_QWORD *)a3 + 162);
        }
      }
    }
  }
  if ( !ProcessIdToSessionId(dwProcessId, (DWORD *)a3 + 330) )
    *((_DWORD *)a3 + 330) = -1;
  Common::CloseHandleHelper((Common *)TokenHandle, v52);
  operator delete(v6, v53);
  return 0;
}

```

## disassembly

```asm
0x1800ad028  mov     [rsp-38h+arg_8], rbx
0x1800ad02d  mov     [rsp-38h+dwProcessId], ecx
0x1800ad031  push    rbp
0x1800ad032  push    rsi
0x1800ad033  push    rdi
0x1800ad034  push    r12
0x1800ad036  push    r13
0x1800ad038  push    r14
0x1800ad03a  push    r15
0x1800ad03c  mov     rbp, rsp
0x1800ad03f  sub     rsp, 70h
0x1800ad043  mov     rdi, r8
0x1800ad046  mov     r13, rdx
0x1800ad049  mov     rcx, r8; this
0x1800ad04c  call    ?Reset@FileInUseProcessInformation@Common@@QEAAXXZ; Common::FileInUseProcessInformation::Reset(void)
0x1800ad051  xor     r12d, r12d
0x1800ad054  mov     ebx, r12d
0x1800ad057  mov     [rbp+var_18], rbx
0x1800ad05b  mov     [rbp+Sid], r12
0x1800ad05f  mov     [rbp+TokenHandle], r12
0x1800ad063  lea     r14, [rdi+100h]
0x1800ad06a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ad06e  lea     edx, [r12+8]; DesiredAccess
0x1800ad073  mov     rcx, r13; ProcessHandle
0x1800ad076  call    cs:__imp_OpenProcessToken
0x1800ad07c  test    eax, eax
0x1800ad07e  jnz     loc_1800AD134
0x1800ad084  call    cs:__imp_GetLastError
0x1800ad08a  mov     r15d, eax
0x1800ad08d  mov     r9d, eax
0x1800ad090  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ad097  mov     edx, 82h; unsigned __int64
0x1800ad09c  mov     rcx, r14; unsigned __int16 *
0x1800ad09f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad0a4  mov     rcx, [rbp+38h]; this
0x1800ad0a8  test    eax, eax
0x1800ad0aa  jns     short loc_1800AD0C1
0x1800ad0ac  mov     r9d, eax; char *
0x1800ad0af  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad0b6  mov     edx, 0C1h; void *
0x1800ad0bb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad0c1  mov     r9d, r15d
0x1800ad0c4  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ad0cb  mov     edx, 80h; unsigned __int64
0x1800ad0d0  mov     rcx, rdi; unsigned __int16 *
0x1800ad0d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad0d8  mov     rcx, [rbp+38h]; this
0x1800ad0dc  test    eax, eax
0x1800ad0de  jns     short loc_1800AD0F5
0x1800ad0e0  mov     r9d, eax; char *
0x1800ad0e3  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad0ea  mov     edx, 0C3h; void *
0x1800ad0ef  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad0f5  lea     rsi, [rdi+228h]
0x1800ad0fc  mov     r9d, r15d
0x1800ad0ff  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ad106  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ad10b  mov     rcx, rsi; unsigned __int16 *
0x1800ad10e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad113  mov     rcx, [rbp+38h]; this
0x1800ad117  test    eax, eax
0x1800ad119  jns     loc_1800AD2F3
0x1800ad11f  mov     r9d, eax; char *
0x1800ad122  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad129  mov     edx, 0C5h; void *
0x1800ad12e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad134  mov     esi, 82h
0x1800ad139  mov     [rbp+applicationUserModelIdLength], esi
0x1800ad13c  mov     r8, r14; applicationUserModelId
0x1800ad13f  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800ad143  mov     rcx, [rbp+TokenHandle]; token
0x1800ad147  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800ad14d  cmp     eax, 3D57h
0x1800ad152  jnz     short loc_1800AD180
0x1800ad154  lea     r8, aNone; "<None>"
0x1800ad15b  mov     edx, esi; unsigned __int64
0x1800ad15d  mov     rcx, r14; unsigned __int16 *
0x1800ad160  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad165  mov     rcx, [rbp+38h]; this
0x1800ad169  test    eax, eax
0x1800ad16b  jns     short loc_1800AD1B6
0x1800ad16d  mov     r9d, eax; char *
0x1800ad170  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad177  lea     edx, [rsi+4Dh]; void *
0x1800ad17a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad180  test    eax, eax
0x1800ad182  jz      short loc_1800AD1B6
0x1800ad184  mov     r9d, eax
0x1800ad187  lea     r8, aError0xXInGeta; "<Error 0x%X in GetApplicationUserModelI"...
0x1800ad18e  mov     rdx, rsi; unsigned __int64
0x1800ad191  mov     rcx, r14; unsigned __int16 *
0x1800ad194  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad199  mov     rcx, [rbp+38h]; this
0x1800ad19d  test    eax, eax
0x1800ad19f  jns     short loc_1800AD1B6
0x1800ad1a1  mov     r9d, eax; char *
0x1800ad1a4  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad1ab  mov     edx, 0D4h; void *
0x1800ad1b0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad1b6  mov     esi, 80h
0x1800ad1bb  mov     [rbp+applicationUserModelIdLength], esi
0x1800ad1be  mov     r8, rdi; packageFullName
0x1800ad1c1  lea     rdx, [rbp+applicationUserModelIdLength]; packageFullNameLength
0x1800ad1c5  mov     rcx, [rbp+TokenHandle]; token
0x1800ad1c9  call    cs:__imp_GetPackageFullNameFromToken
0x1800ad1cf  cmp     eax, 3D54h
0x1800ad1d4  jnz     short loc_1800AD202
0x1800ad1d6  lea     r8, aNone; "<None>"
0x1800ad1dd  mov     edx, esi; unsigned __int64
0x1800ad1df  mov     rcx, rdi; unsigned __int16 *
0x1800ad1e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad1e7  mov     rcx, [rbp+38h]; this
0x1800ad1eb  test    eax, eax
0x1800ad1ed  jns     short loc_1800AD238
0x1800ad1ef  mov     r9d, eax; char *
0x1800ad1f2  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad1f9  lea     edx, [rsi+5Ch]; void *
0x1800ad1fc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad202  test    eax, eax
0x1800ad204  jz      short loc_1800AD238
0x1800ad206  mov     r9d, eax
0x1800ad209  lea     r8, aError0xXInGetp; "<Error 0x%X in GetPackageFullName>"
0x1800ad210  mov     rdx, rsi; unsigned __int64
0x1800ad213  mov     rcx, rdi; unsigned __int16 *
0x1800ad216  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad21b  mov     rcx, [rbp+38h]; this
0x1800ad21f  test    eax, eax
0x1800ad221  jns     short loc_1800AD238
0x1800ad223  mov     r9d, eax; char *
0x1800ad226  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad22d  mov     edx, 0E1h; void *
0x1800ad232  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad238  lea     rdx, [rbp+var_18]; void **
0x1800ad23c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ad240  call    ?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z; Common::SidHelper::GetUserSidFromToken(void *,void * *)
0x1800ad245  mov     rbx, [rbp+var_18]
0x1800ad249  test    eax, eax
0x1800ad24b  jns     short loc_1800AD29A
0x1800ad24d  lea     rcx, [rdi+228h]; unsigned __int16 *
0x1800ad254  mov     r9d, eax
0x1800ad257  lea     r8, aError0xXGettin; "<Error 0x%X getting the user's SID from"...
0x1800ad25e  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ad263  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad268  mov     rcx, [rbp+38h]; this
0x1800ad26c  test    eax, eax
0x1800ad26e  jns     short loc_1800AD285
0x1800ad270  mov     r9d, eax; char *
0x1800ad273  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad27a  mov     edx, 0E9h; void *
0x1800ad27f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad285  lea     rsi, [rdi+208h]
0x1800ad28c  cmp     [rsi], r12d
0x1800ad28f  jbe     short loc_1800AD2EC
0x1800ad291  mov     rsi, [rdi+210h]
0x1800ad298  jmp     short loc_1800AD2F3
0x1800ad29a  mov     [rbp+Sid], rbx
0x1800ad29e  lea     rsi, [rdi+208h]
0x1800ad2a5  mov     rdx, rsi; this
0x1800ad2a8  mov     rcx, rbx; Sid
0x1800ad2ab  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800ad2b0  test    eax, eax
0x1800ad2b2  jns     short loc_1800AD28C
0x1800ad2b4  lea     rcx, [rdi+228h]; unsigned __int16 *
0x1800ad2bb  mov     r9d, eax
0x1800ad2be  lea     r8, aError0xXConver; "<Error 0x%X converting the user's SID t"...
0x1800ad2c5  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ad2ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad2cf  mov     rcx, [rbp+38h]; this
0x1800ad2d3  test    eax, eax
0x1800ad2d5  jns     short loc_1800AD28C
0x1800ad2d7  mov     r9d, eax; char *
0x1800ad2da  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad2e1  mov     edx, 0F2h; void *
0x1800ad2e6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad2ec  lea     rsi, [rdi+228h]
0x1800ad2f3  mov     eax, 220h
0x1800ad2f8  mov     rcx, rdi
0x1800ad2fb  mov     [rcx+rax], rsi
0x1800ad2ff  mov     [rbp+dwSize], 104h
0x1800ad306  lea     r15, [rdi+300h]
0x1800ad30d  lea     r9, [rbp+dwSize]; lpdwSize
0x1800ad311  mov     r8, r15; lpExeName
0x1800ad314  xor     edx, edx; dwFlags
0x1800ad316  mov     rcx, r13; hProcess
0x1800ad319  call    cs:__imp_QueryFullProcessImageNameW
0x1800ad31f  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ad323  test    eax, eax
0x1800ad325  jnz     loc_1800AD41A
0x1800ad32b  call    cs:__imp_GetLastError
0x1800ad331  mov     esi, eax
0x1800ad333  cmp     eax, 7Ah ; 'z'
0x1800ad336  jnz     loc_1800AD3E2
0x1800ad33c  mov     ecx, [rbp+dwSize]
0x1800ad33f  inc     ecx
0x1800ad341  mov     [rbp+dwSize], ecx
0x1800ad344  mov     edx, ecx
0x1800ad346  lea     eax, [rsi-78h]
0x1800ad349  mul     rdx
0x1800ad34c  cmovb   rax, r14
0x1800ad350  mov     rcx, rax; unsigned __int64
0x1800ad353  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ad358  mov     r14, rax
0x1800ad35b  mov     rax, [rdi+2F8h]
0x1800ad362  cmp     rax, r14
0x1800ad365  jz      short loc_1800AD378
0x1800ad367  mov     rcx, rax; void *
0x1800ad36a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ad36f  mov     [rdi+2F8h], r14
0x1800ad376  jmp     short loc_1800AD37B
0x1800ad378  mov     r14, rax
0x1800ad37b  test    r14, r14
0x1800ad37e  jnz     short loc_1800AD3B1
0x1800ad380  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800ad387  mov     edx, 104h; unsigned __int64
0x1800ad38c  mov     rcx, r15; unsigned __int16 *
0x1800ad38f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad394  mov     rcx, [rbp+38h]; this
0x1800ad398  test    eax, eax
0x1800ad39a  jns     short loc_1800AD41A
0x1800ad39c  mov     r9d, eax; char *
0x1800ad39f  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad3a6  mov     edx, 103h; void *
0x1800ad3ab  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad3b1  lea     r9, [rbp+dwSize]; lpdwSize
0x1800ad3b5  mov     r8, r14; lpExeName
0x1800ad3b8  xor     edx, edx; dwFlags
0x1800ad3ba  mov     rcx, r13; hProcess
0x1800ad3bd  call    cs:__imp_QueryFullProcessImageNameW
0x1800ad3c3  test    eax, eax
0x1800ad3c5  jnz     short loc_1800AD3E6
0x1800ad3c7  call    cs:__imp_GetLastError
0x1800ad3cd  mov     esi, eax
0x1800ad3cf  mov     rcx, [rdi+2F8h]; void *
0x1800ad3d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ad3db  mov     [rdi+2F8h], r12
0x1800ad3e2  test    esi, esi
0x1800ad3e4  jz      short loc_1800AD41A
0x1800ad3e6  mov     r9d, esi
0x1800ad3e9  lea     r8, aError0xXInQuer; "<Error 0x%X in QueryFullProcessImageNam"...
0x1800ad3f0  mov     edx, 104h; unsigned __int64
0x1800ad3f5  mov     rcx, r15; unsigned __int16 *
0x1800ad3f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad3fd  mov     rcx, [rbp+38h]; this
0x1800ad401  test    eax, eax
0x1800ad403  jns     short loc_1800AD41A
0x1800ad405  mov     r9d, eax; char *
0x1800ad408  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad40f  mov     edx, 10Fh; void *
0x1800ad414  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad41a  mov     rax, [rdi+2F8h]
0x1800ad421  test    rax, rax
0x1800ad424  cmovz   rax, r15
0x1800ad428  mov     [rdi+2F0h], rax
0x1800ad42f  mov     [rbp+ProcessInformationLength], r12d
0x1800ad433  lea     r15, [rdi+540h]
0x1800ad43a  lea     rax, [rbp+ProcessInformationLength]
0x1800ad43e  mov     [rsp+70h+ReturnLength], rax; int
0x1800ad443  mov     r12d, 208h
0x1800ad449  mov     r9d, r12d; ProcessInformationLength
0x1800ad44c  mov     r8, r15; ProcessInformation
0x1800ad44f  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1800ad454  mov     rcx, r13; ProcessHandle
0x1800ad457  call    cs:__imp_NtQueryInformationProcess
0x1800ad45d  mov     r14d, eax
0x1800ad460  test    eax, eax
0x1800ad462  jns     loc_1800AD564
0x1800ad468  cmp     eax, 0C0000004h
0x1800ad46d  jnz     loc_1800AD520
0x1800ad473  mov     ecx, [rbp+ProcessInformationLength]; unsigned __int64
0x1800ad476  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ad47b  mov     r14, rax
0x1800ad47e  mov     rax, [rdi+538h]
0x1800ad485  cmp     rax, r14
0x1800ad488  jz      short loc_1800AD4A2
0x1800ad48a  mov     rcx, rax; void *
0x1800ad48d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ad492  mov     [rdi+538h], r14
0x1800ad499  lea     rsi, [rdi+540h]
0x1800ad4a0  jmp     short loc_1800AD4A8
0x1800ad4a2  mov     rsi, r15
0x1800ad4a5  mov     r14, rax
0x1800ad4a8  test    r14, r14
0x1800ad4ab  jnz     short loc_1800AD4E2
0x1800ad4ad  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800ad4b4  mov     edx, 104h; unsigned __int64
0x1800ad4b9  mov     rcx, r15; unsigned __int16 *
0x1800ad4bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad4c1  mov     rcx, [rbp+38h]; this
0x1800ad4c5  test    eax, eax
0x1800ad4c7  jns     loc_1800AD5F3
0x1800ad4cd  mov     r9d, eax; char *
0x1800ad4d0  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ad4d7  mov     edx, 120h; void *
0x1800ad4dc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad4e2  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1800ad4eb  mov     r9d, [rbp+ProcessInformationLength]; ProcessInformationLength
0x1800ad4ef  mov     r8, r14; ProcessInformation
0x1800ad4f2  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1800ad4f7  mov     rcx, r13; ProcessHandle
0x1800ad4fa  call    cs:__imp_NtQueryInformationProcess
  ... truncated ...
```
