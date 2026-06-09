# RestrictMsaRootRegistryKeyAccess(IServiceExecutionContext *)

- ea: `0x18006ae38`
- end: `0x18006b22c`
- name: `?RestrictMsaRootRegistryKeyAccess@@YAXPEAVIServiceExecutionContext@@@Z`
- size: `1012`
- prototype: `void __fastcall(struct IServiceExecutionContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180078a50`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180038a80`
- `0x180054fb4`
- `0x18006ae38`
- `0x1800793b4`
- `0x1800841b0`
- `0x1800a6724`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b10a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b10a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006b02a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006b02a`
- `ext-ms-win-msa-user-l1-1-1!MsaUser_GetUserRegistrySecurityDescriptor` at `0x18006afe7`
- `ext-ms-win-msa-user-l1-1-1!MsaUser_GetUserRegistrySecurityDescriptor` at `0x18006afe7`

## string_xrefs

- `0x18006ae6b`: `RestrictMsaRootRegistryKeyAccess`
- `0x18006ae90`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\setregistrypermission.cpp`
- `0x18006af98`: `hr = pExecutionContext->GetCRegKeyWrapper()->Create(&key, HKEY_USERS, SYSTEM_USER_KEYPATH, nullptr, 0, KEY_ALL_ACCESS, nullptr, nullptr)`
- `0x18006aed9`: `Already done, skip.`
- `0x18006b195`: `hr = HRESULT_FROM_WIN32( pExecutionContextLite->GetWinApiFunctions()->SetNamedSecurityInfoW( L"USERS\\" SYSTEM_USER_KEYPATH, SE_REGISTRY_KEY, DACL_SECURITY_INFORMATION | PROTECTED_DACL_SECURITY_INFORMATION | LABEL_SECURITY_INFORMATION, nullptr, nullptr, dacl, sacl))`
- `0x18006aea9`: `SetRegistryPermissionDone`
- `0x18006b1da`: `SetRegistryPermissionDone`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RestrictMsaRootRegistryKeyAccess(struct IServiceExecutionContext *a1)
{
  __int64 v2; // rdi
  int ValueFrom; // eax
  __int64 v4; // rax
  signed int LastError; // eax
  const char *v6; // rcx
  unsigned int v7; // r8d
  int UserRegistrySecurityDescriptor; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  char *v12; // [rsp+20h] [rbp-89h]
  int v13; // [rsp+20h] [rbp-89h]
  PSECURITY_DESCRIPTOR SecurityDescriptor[3]; // [rsp+50h] [rbp-59h] BYREF
  int v15; // [rsp+68h] [rbp-41h] BYREF
  int v16; // [rsp+6Ch] [rbp-3Dh] BYREF
  int v17; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v18[3]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v19; // [rsp+90h] [rbp-19h] BYREF
  __int64 v20; // [rsp+98h] [rbp-11h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD v22[11]; // [rsp+A8h] [rbp-1h] BYREF
  int v23; // [rsp+110h] [rbp+67h] BYREF
  int v24; // [rsp+118h] [rbp+6Fh] BYREF
  ULONG SecurityDescriptorSize; // [rsp+120h] [rbp+77h] BYREF
  int v26; // [rsp+128h] [rbp+7Fh] BYREF

  v23 = 0;
  v2 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 40LL))(a1);
  v21 = v2;
  v24 = 0;
  v22[0] = "RestrictMsaRootRegistryKeyAccess";
  v22[1] = &v23;
  v22[2] = 0;
  v22[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
    "RestrictMsaRootRegistryKeyAccess",
    (const char *)0x22,
    0,
    (const unsigned __int16 *)v12);
  ValueFrom = RegistryHelper::ReadValueFromRegistry<unsigned long>(
                (unsigned int)&v21,
                -2147483645,
                (unsigned int)L".default\\Software\\Microsoft\\IdentityCRL",
                (unsigned int)aSetregistryper,
                v13,
                (__int64)&v24);
  v23 = ValueFrom;
  if ( ValueFrom == -2147024894 )
  {
    v23 = 0;
  }
  else if ( ValueFrom < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
      "RestrictMsaRootRegistryKeyAccess",
      0x2Du,
      ValueFrom,
      "hr");
    goto LABEL_38;
  }
  if ( !v24 )
  {
    memset(v18, 0, sizeof(v18));
    memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
    SecurityDescriptorSize = 0;
    v20 = 0;
    v15 = 0;
    v26 = 0;
    v19 = 0;
    v17 = 0;
    v16 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 24LL))(a1);
    LastError = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, const unsigned __int16 *, _QWORD, _DWORD, int, _QWORD, _QWORD))(*(_QWORD *)v4 + 64LL))(
                  v4,
                  v18,
                  -2147483645,
                  L".default\\Software\\Microsoft\\IdentityCRL",
                  0,
                  0,
                  983103,
                  0,
                  0);
    v23 = LastError;
    if ( LastError < 0 )
    {
      v6 = "hr = pExecutionContext->GetCRegKeyWrapper()->Create(&key, HKEY_USERS, SYSTEM_USER_KEYPATH, nullptr, 0, KEY_AL"
           "L_ACCESS, nullptr, nullptr)";
      v7 = 76;
LABEL_9:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
        "RestrictMsaRootRegistryKeyAccess",
        v7,
        LastError,
        v6);
LABEL_10:
      Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(SecurityDescriptor);
      ATL::CRegKey::Close((ATL::CRegKey *)v18);
      goto LABEL_38;
    }
    if ( (unsigned __int8)IsMsaUser_GetDeviceTelemetryInformationPresent() )
    {
      UserRegistrySecurityDescriptor = MsaUser_GetUserRegistrySecurityDescriptor(
                                         SecurityDescriptor,
                                         &SecurityDescriptorSize);
      v23 = UserRegistrySecurityDescriptor;
      if ( UserRegistrySecurityDescriptor != -2147467263 )
      {
        if ( UserRegistrySecurityDescriptor < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
            "RestrictMsaRootRegistryKeyAccess",
            0x54u,
            UserRegistrySecurityDescriptor,
            "hr");
          goto LABEL_10;
        }
        goto LABEL_22;
      }
    }
    else
    {
      v23 = -2147467263;
    }
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            aDPaiACiioidKaC,
            1u,
            SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v23 = LastError;
      if ( LastError < 0 )
      {
        v6 = "hr = HRESULT_FROM_WIN32(GetLastError())";
        v7 = 99;
        goto LABEL_9;
      }
    }
    v23 = 0;
LABEL_22:
    if ( SecurityDescriptorSize )
    {
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
      if ( !(*(unsigned int (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, int *, __int64 *, int *))(*(_QWORD *)v9 + 336LL))(
              v9,
              SecurityDescriptor[0],
              &v15,
              &v20,
              &v26) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v23 = LastError;
        if ( LastError < 0 )
        {
          v6 = "hr = HRESULT_FROM_WIN32(GetLastError())";
          v7 = 111;
          goto LABEL_9;
        }
      }
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
      if ( !(*(unsigned int (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, int *, __int64 *, int *))(*(_QWORD *)v10 + 344LL))(
              v10,
              SecurityDescriptor[0],
              &v17,
              &v19,
              &v16) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v23 = LastError;
        if ( LastError < 0 )
        {
          v6 = "hr = HRESULT_FROM_WIN32(GetLastError())";
          v7 = 118;
          goto LABEL_9;
        }
      }
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
      LastError = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v11 + 352LL))(
                    v11,
                    L"USERS\\.default\\Software\\Microsoft\\IdentityCRL",
                    4,
                    2147483668LL,
                    0,
                    0,
                    v20,
                    v19);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v23 = LastError;
      if ( LastError < 0 )
      {
        v6 = "hr = HRESULT_FROM_WIN32( pExecutionContextLite->GetWinApiFunctions()->SetNamedSecurityInfoW( L\"USERS\\\\\""
             " SYSTEM_USER_KEYPATH, SE_REGISTRY_KEY, DACL_SECURITY_INFORMATION | PROTECTED_DACL_SECURITY_INFORMATION | LA"
             "BEL_SECURITY_INFORMATION, nullptr, nullptr, dacl, sacl))";
        v7 = 128;
        goto LABEL_9;
      }
    }
    Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(SecurityDescriptor);
    ATL::CRegKey::Close((ATL::CRegKey *)v18);
    v24 = 1;
    RegistryHelper::WriteBufferToRegistry(
      (RegistryHelper *)&v21,
      HKEY_USERS,
      L".default\\Software\\Microsoft\\IdentityCRL",
      aSetregistryper,
      4u,
      (unsigned __int8 *)&v24,
      4u);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
      0x89u,
      L"Set permission done.");
    goto LABEL_38;
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\setregistrypermission.cpp",
    0x31u,
    L"Already done, skip.");
LABEL_38:
  CTraceFuncW<long>::~CTraceFuncW<long>(v22);
}

```

## disassembly

```asm
0x18006ae38  push    rbp
0x18006ae3a  push    rbx
0x18006ae3b  push    rsi
0x18006ae3c  push    rdi
0x18006ae3d  push    r14
0x18006ae3f  push    r15
0x18006ae41  lea     rbp, [rsp-2Fh]
0x18006ae46  sub     rsp, 0D8h
0x18006ae4d  mov     rbx, rcx
0x18006ae50  xor     esi, esi
0x18006ae52  mov     [rbp+57h+arg_0], esi
0x18006ae55  mov     rax, [rcx]
0x18006ae58  mov     rax, [rax+28h]
0x18006ae5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae61  mov     rdi, rax
0x18006ae64  mov     [rbp+57h+var_60], rax
0x18006ae68  mov     [rbp+57h+arg_8], esi
0x18006ae6b  lea     r15, aRestrictmsaroo; "RestrictMsaRootRegistryKeyAccess"
0x18006ae72  mov     [rbp+57h+var_58], r15
0x18006ae76  lea     rax, [rbp+57h+arg_0]
0x18006ae7a  mov     [rbp+57h+var_50], rax
0x18006ae7e  mov     [rbp+57h+var_48], rsi
0x18006ae82  mov     [rbp+57h+var_40], rsi
0x18006ae86  xor     r9d, r9d; unsigned int
0x18006ae89  lea     r8d, [rsi+22h]; char *
0x18006ae8d  mov     rdx, r15; char *
0x18006ae90  lea     r14, aOnecoreuapDsEx_109; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006ae97  mov     rcx, r14; this
0x18006ae9a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006ae9f  nop
0x18006aea0  lea     rax, [rbp+57h+arg_8]
0x18006aea4  mov     [rsp+100h+var_D8], rax
0x18006aea9  lea     r9, aSetregistryper; "SetRegistryPermissionDone"
0x18006aeb0  lea     r8, aDefaultSoftwar; ".default\\Software\\Microsoft\\Identity"...
0x18006aeb7  mov     rdx, 0FFFFFFFF80000003h
0x18006aebe  lea     rcx, [rbp+57h+var_60]
0x18006aec2  call    ??$ReadValueFromRegistry@K@RegistryHelper@@AEAAJPEAUHKEY__@@PEBG1KPEAK@Z; RegistryHelper::ReadValueFromRegistry<ulong>(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x18006aec7  mov     [rbp+57h+arg_0], eax
0x18006aeca  cmp     eax, 80070002h
0x18006aecf  jnz     short loc_18006AEEB
0x18006aed1  mov     [rbp+57h+arg_0], esi
0x18006aed4  cmp     [rbp+57h+arg_8], esi
0x18006aed7  jz      short loc_18006AF14
0x18006aed9  lea     r9, aAlreadyDoneSki; "Already done, skip."
0x18006aee0  mov     r8d, 31h ; '1'
0x18006aee6  jmp     loc_18006B205
0x18006aeeb  test    eax, eax
0x18006aeed  jns     short loc_18006AED4
0x18006aeef  lea     r8, aHr; "hr"
0x18006aef6  mov     [rsp+100h+var_E0], r8; char *
0x18006aefb  mov     r9d, eax; int
0x18006aefe  mov     r8d, 2Dh ; '-'; unsigned int
0x18006af04  mov     rdx, r15; char *
0x18006af07  mov     rcx, r14; char *
0x18006af0a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006af0f  jmp     loc_18006B213
0x18006af14  mov     [rbp+57h+var_88], rsi
0x18006af18  mov     [rbp+57h+var_80], rsi
0x18006af1c  mov     [rbp+57h+var_78], rsi
0x18006af20  mov     [rbp+57h+SecurityDescriptor], rsi
0x18006af24  mov     [rbp+57h+var_A0], rsi
0x18006af28  mov     [rbp+57h+var_A8], rsi
0x18006af2c  mov     [rbp+57h+SecurityDescriptorSize], esi
0x18006af2f  mov     [rbp+57h+var_68], rsi
0x18006af33  mov     [rbp+57h+var_98], esi
0x18006af36  mov     [rbp+57h+arg_18], esi
0x18006af39  mov     [rbp+57h+var_70], rsi
0x18006af3d  mov     [rbp+57h+var_90], esi
0x18006af40  mov     [rbp+57h+var_94], esi
0x18006af43  mov     rax, [rbx]
0x18006af46  mov     rcx, rbx
0x18006af49  mov     rax, [rax+18h]
0x18006af4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af52  mov     r10, rax
0x18006af55  mov     rcx, [rax]
0x18006af58  mov     rax, [rcx+40h]
0x18006af5c  mov     [rsp+100h+var_C0], rsi
0x18006af61  mov     [rsp+100h+var_C8], rsi
0x18006af66  mov     [rsp+100h+var_D0], 0F003Fh
0x18006af6e  mov     dword ptr [rsp+100h+var_D8], esi
0x18006af72  mov     [rsp+100h+var_E0], rsi
0x18006af77  lea     r9, aDefaultSoftwar; ".default\\Software\\Microsoft\\Identity"...
0x18006af7e  mov     r8, 0FFFFFFFF80000003h
0x18006af85  lea     rdx, [rbp+57h+var_88]
0x18006af89  mov     rcx, r10
0x18006af8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af91  mov     [rbp+57h+arg_0], eax
0x18006af94  test    eax, eax
0x18006af96  jns     short loc_18006AFD1
0x18006af98  lea     rcx, aHrPexecutionco_2; "hr = pExecutionContext->GetCRegKeyWrapp"...
0x18006af9f  mov     r8d, 4Ch ; 'L'; unsigned int
0x18006afa5  mov     [rsp+100h+var_E0], rcx; char *
0x18006afaa  mov     r9d, eax; int
0x18006afad  mov     rdx, r15; char *
0x18006afb0  mov     rcx, r14; char *
0x18006afb3  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006afb8  nop
0x18006afb9  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006afbd  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x18006afc2  nop
0x18006afc3  lea     rcx, [rbp+57h+var_88]; this
0x18006afc7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006afcc  jmp     loc_18006B213
0x18006afd1  call    IsMsaUser_GetDeviceTelemetryInformationPresent
0x18006afd6  mov     ebx, 80070000h
0x18006afdb  test    al, al
0x18006afdd  jz      short loc_18006B00F
0x18006afdf  lea     rdx, [rbp+57h+SecurityDescriptorSize]
0x18006afe3  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006afe7  call    cs:__imp_MsaUser_GetUserRegistrySecurityDescriptor
0x18006afed  mov     [rbp+57h+arg_0], eax
0x18006aff0  cmp     eax, 80004001h
0x18006aff5  jz      short loc_18006B016
0x18006aff7  test    eax, eax
0x18006aff9  jns     short loc_18006B05F
0x18006affb  lea     r8, aHr; "hr"
0x18006b002  mov     [rsp+100h+var_E0], r8
0x18006b007  mov     r8d, 54h ; 'T'
0x18006b00d  jmp     short loc_18006AFAA
0x18006b00f  mov     [rbp+57h+arg_0], 80004001h
0x18006b016  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18006b01a  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006b01e  mov     edx, 1; StringSDRevision
0x18006b023  lea     rcx, aDPaiACiioidKaC; "D:PAI(A;CIIOID;KA;;;CO)(A;CIID;KA;;;SY)"...
0x18006b02a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006b030  test    eax, eax
0x18006b032  jnz     short loc_18006B05C
0x18006b034  call    cs:__imp_GetLastError
0x18006b03a  test    eax, eax
0x18006b03c  jle     short loc_18006B043
0x18006b03e  movzx   eax, ax
0x18006b041  or      eax, ebx
0x18006b043  mov     [rbp+57h+arg_0], eax
0x18006b046  test    eax, eax
0x18006b048  jns     short loc_18006B05C
0x18006b04a  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006b051  mov     r8d, 63h ; 'c'
0x18006b057  jmp     loc_18006AFA5
0x18006b05c  mov     [rbp+57h+arg_0], esi
0x18006b05f  cmp     [rbp+57h+SecurityDescriptorSize], esi
0x18006b062  jbe     loc_18006B1A7
0x18006b068  mov     rax, [rdi]
0x18006b06b  mov     rcx, rdi
0x18006b06e  mov     rax, [rax+18h]
0x18006b072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b077  mov     r10, rax
0x18006b07a  mov     rcx, [rax]
0x18006b07d  mov     rax, [rcx+150h]
0x18006b084  lea     rcx, [rbp+57h+arg_18]
0x18006b088  mov     [rsp+100h+var_E0], rcx
0x18006b08d  lea     r9, [rbp+57h+var_68]
0x18006b091  lea     r8, [rbp+57h+var_98]
0x18006b095  mov     rdx, [rbp+57h+SecurityDescriptor]
0x18006b099  mov     rcx, r10
0x18006b09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0a1  test    eax, eax
0x18006b0a3  jnz     short loc_18006B0CD
0x18006b0a5  call    cs:__imp_GetLastError
0x18006b0ab  test    eax, eax
0x18006b0ad  jle     short loc_18006B0B4
0x18006b0af  movzx   eax, ax
0x18006b0b2  or      eax, ebx
0x18006b0b4  mov     [rbp+57h+arg_0], eax
0x18006b0b7  test    eax, eax
0x18006b0b9  jns     short loc_18006B0CD
0x18006b0bb  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006b0c2  mov     r8d, 6Fh ; 'o'
0x18006b0c8  jmp     loc_18006AFA5
0x18006b0cd  mov     rax, [rdi]
0x18006b0d0  mov     rcx, rdi
0x18006b0d3  mov     rax, [rax+18h]
0x18006b0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0dc  mov     r10, rax
0x18006b0df  mov     rcx, [rax]
0x18006b0e2  mov     rax, [rcx+158h]
0x18006b0e9  lea     rcx, [rbp+57h+var_94]
0x18006b0ed  mov     [rsp+100h+var_E0], rcx
0x18006b0f2  lea     r9, [rbp+57h+var_70]
0x18006b0f6  lea     r8, [rbp+57h+var_90]
0x18006b0fa  mov     rdx, [rbp+57h+SecurityDescriptor]
0x18006b0fe  mov     rcx, r10
0x18006b101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b106  test    eax, eax
0x18006b108  jnz     short loc_18006B132
0x18006b10a  call    cs:__imp_GetLastError
0x18006b110  test    eax, eax
0x18006b112  jle     short loc_18006B119
0x18006b114  movzx   eax, ax
0x18006b117  or      eax, ebx
0x18006b119  mov     [rbp+57h+arg_0], eax
0x18006b11c  test    eax, eax
0x18006b11e  jns     short loc_18006B132
0x18006b120  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006b127  mov     r8d, 76h ; 'v'
0x18006b12d  jmp     loc_18006AFA5
0x18006b132  mov     rax, [rdi]
0x18006b135  mov     rcx, rdi
0x18006b138  mov     rax, [rax+18h]
0x18006b13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b141  mov     r10, rax
0x18006b144  mov     rdx, [rbp+57h+var_70]
0x18006b148  mov     r8, [rbp+57h+var_68]
0x18006b14c  mov     rcx, [rax]
0x18006b14f  mov     rax, [rcx+160h]
0x18006b156  mov     [rsp+100h+var_C8], rdx
0x18006b15b  mov     qword ptr [rsp+100h+var_D0], r8
0x18006b160  mov     [rsp+100h+var_D8], rsi
0x18006b165  mov     [rsp+100h+var_E0], rsi
0x18006b16a  mov     r9d, 80000014h
0x18006b170  mov     r8d, 4
0x18006b176  lea     rdx, aUsersDefaultSo; "USERS\\.default\\Software\\Microsoft\\I"...
0x18006b17d  mov     rcx, r10
0x18006b180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b185  test    eax, eax
0x18006b187  jle     short loc_18006B18E
0x18006b189  movzx   eax, ax
0x18006b18c  or      eax, ebx
0x18006b18e  mov     [rbp+57h+arg_0], eax
0x18006b191  test    eax, eax
0x18006b193  jns     short loc_18006B1A7
0x18006b195  lea     rcx, aHrHresultFromW_5; "hr = HRESULT_FROM_WIN32( pExecutionCont"...
0x18006b19c  mov     r8d, 80h
0x18006b1a2  jmp     loc_18006AFA5
0x18006b1a7  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006b1ab  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x18006b1b0  nop
0x18006b1b1  lea     rcx, [rbp+57h+var_88]; this
0x18006b1b5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006b1ba  mov     [rbp+57h+arg_8], 1
0x18006b1c1  mov     [rsp+100h+var_D0], 4; unsigned int
0x18006b1c9  lea     rax, [rbp+57h+arg_8]
0x18006b1cd  mov     [rsp+100h+var_D8], rax; unsigned __int8 *
0x18006b1d2  mov     dword ptr [rsp+100h+var_E0], 4; unsigned int
0x18006b1da  lea     r9, aSetregistryper; "SetRegistryPermissionDone"
0x18006b1e1  lea     r8, aDefaultSoftwar; ".default\\Software\\Microsoft\\Identity"...
0x18006b1e8  mov     rdx, 0FFFFFFFF80000003h; HKEY
0x18006b1ef  lea     rcx, [rbp+57h+var_60]; this
0x18006b1f3  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x18006b1f8  lea     r9, aSetPermissionD; "Set permission done."
0x18006b1ff  mov     r8d, 89h; unsigned int
0x18006b205  mov     rdx, r14; char *
0x18006b208  mov     ecx, 5; unsigned __int8
0x18006b20d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006b212  nop
0x18006b213  lea     rcx, [rbp+57h+var_58]
0x18006b217  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006b21c  add     rsp, 0D8h
0x18006b223  pop     r15
0x18006b225  pop     r14
0x18006b227  pop     rdi
0x18006b228  pop     rsi
0x18006b229  pop     rbx
0x18006b22a  pop     rbp
0x18006b22b  retn
```
