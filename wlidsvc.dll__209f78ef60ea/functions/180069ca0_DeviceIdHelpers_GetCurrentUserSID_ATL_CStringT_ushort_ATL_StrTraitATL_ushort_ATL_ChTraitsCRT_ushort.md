# DeviceIdHelpers::GetCurrentUserSID(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180069ca0`
- end: `0x180069f48`
- name: `?GetCurrentUserSID@DeviceIdHelpers@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `680`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800121a0`
- `0x1800124f0`
- `0x180072374`
- `0x1800ea4fc`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x180015860`
- `0x180018f80`
- `0x1800191c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180022f38`
- `0x180039d94`
- `0x180069ca0`
- `0x1800f3b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ec0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069dbd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069e4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069dbd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069e4b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180069e8d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180069e8d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069eb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069eb6`

## string_xrefs

- `0x180069ce6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers.cpp`
- `0x180069cbf`: `DeviceIdHelpers::GetCurrentUserSID`
- `0x180069d8d`: `hr = WlidsvcUtil::GetCurrentUserToken(TOKEN_QUERY, hToken)`
- `0x180069d52`: `!wstrSid.IsEmpty()`
- `0x180069dfa`: `GetTokenInformation failed with hr = 0x%x`
- `0x180069dcd`: `!GetTokenInformation(hToken, TokenUser, nullptr, 0, &cbti)`
- `0x180069e9d`: `IsValidSid(ptiUser->User.Sid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceIdHelpers::GetCurrentUserSID(_QWORD *a1)
{
  __int64 v2; // rdx
  int v3; // r9d
  const char *v4; // rax
  unsigned int v5; // r8d
  int CurrentUserToken; // eax
  signed int LastError; // eax
  PSID *v8; // rdi
  signed int v9; // eax
  signed int v10; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-60h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-60h]
  LPWSTR StringSid[3]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+48h] [rbp-38h] BYREF
  LPVOID TokenInformation; // [rsp+50h] [rbp-30h]
  int v18; // [rsp+58h] [rbp-28h]
  _QWORD v19[4]; // [rsp+60h] [rbp-20h] BYREF
  int v20; // [rsp+C8h] [rbp+48h] BYREF
  DWORD TokenInformationLength; // [rsp+D0h] [rbp+50h] BYREF
  HANDLE TokenHandle; // [rsp+D8h] [rbp+58h] BYREF

  v20 = 0;
  v19[0] = "DeviceIdHelpers::GetCurrentUserSID";
  v19[1] = &v20;
  v19[2] = 0;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
    "DeviceIdHelpers::GetCurrentUserSID",
    (const char *)0x2EF,
    0,
    ReturnLength);
  TokenHandle = 0;
  TokenInformationLength = 0;
  TokenInformation = 0;
  v16 = 0;
  v18 = 0;
  memset(StringSid, 0, sizeof(StringSid));
  v2 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
  if ( v2 )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=(a1, v2);
    if ( !*(_DWORD *)(*a1 - 16LL) )
    {
      v3 = -2147024809;
      v4 = "!wstrSid.IsEmpty()";
      v5 = 766;
LABEL_4:
      v20 = v3;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
        "DeviceIdHelpers::GetCurrentUserSID",
        v5,
        v3,
        v4);
    }
  }
  else
  {
    CurrentUserToken = WlidsvcUtil::GetCurrentUserToken(8u, &TokenHandle);
    v20 = CurrentUserToken;
    if ( CurrentUserToken >= 0 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      {
        v3 = -2147418113;
        v4 = "!GetTokenInformation(hToken, TokenUser, nullptr, 0, &cbti)";
        v5 = 775;
        goto LABEL_4;
      }
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        CBytePtr::SetLength((CBytePtr *)&v16, TokenInformationLength, 1);
        v8 = (PSID *)TokenInformation;
        if ( TokenInformation )
        {
          if ( !GetTokenInformation(
                  TokenHandle,
                  TokenUser,
                  TokenInformation,
                  TokenInformationLength,
                  &TokenInformationLength) )
          {
            v9 = GetLastError();
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
            v20 = v9;
            if ( v9 < 0 )
            {
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
                "DeviceIdHelpers::GetCurrentUserSID",
                0x317u,
                v9,
                "hr = HRESULT_FROM_WIN32(GetLastError())");
              goto LABEL_30;
            }
          }
          if ( !IsValidSid(*v8) )
          {
            v3 = -2147418113;
            v4 = "IsValidSid(ptiUser->User.Sid)";
            v5 = 793;
            goto LABEL_4;
          }
          if ( !ConvertSidToStringSidW(*v8, StringSid) )
          {
            v10 = GetLastError();
            if ( v10 > 0 )
              v10 = (unsigned __int16)v10 | 0x80070000;
            v20 = v10;
            if ( v10 < 0 )
            {
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
                "DeviceIdHelpers::GetCurrentUserSID",
                0x31Bu,
                v10,
                "hr = HRESULT_FROM_WIN32(GetLastError())");
              goto LABEL_30;
            }
          }
          if ( StringSid[0] )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1, StringSid[0]);
            goto LABEL_30;
          }
        }
        v20 = -2147024882;
        goto LABEL_30;
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v20 = LastError;
      LODWORD(ReturnLengtha) = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
        0x30Eu,
        L"GetTokenInformation failed with hr = 0x%x",
        ReturnLengtha);
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers.cpp",
        "DeviceIdHelpers::GetCurrentUserSID",
        0x304u,
        CurrentUserToken,
        "hr = WlidsvcUtil::GetCurrentUserToken(TOKEN_QUERY, hToken)");
    }
  }
LABEL_30:
  v11 = v20;
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)StringSid);
  CBytePtr::Empty((CBytePtr *)&v16);
  ATL::CHandle::~CHandle((ATL::CHandle *)&TokenHandle);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return v11;
}

```

## disassembly

```asm
0x180069ca0  push    rbp
0x180069ca2  push    rbx
0x180069ca3  push    rsi
0x180069ca4  push    rdi
0x180069ca5  push    r12
0x180069ca7  push    r14
0x180069ca9  push    r15
0x180069cab  mov     rbp, rsp
0x180069cae  sub     rsp, 80h
0x180069cb5  mov     rsi, rcx
0x180069cb8  xor     r14d, r14d
0x180069cbb  mov     [rbp+arg_8], r14d
0x180069cbf  lea     r12, aDeviceidhelper_41; "DeviceIdHelpers::GetCurrentUserSID"
0x180069cc6  mov     [rbp+var_20], r12
0x180069cca  lea     rax, [rbp+arg_8]
0x180069cce  mov     [rbp+var_18], rax
0x180069cd2  mov     [rbp+var_10], r14
0x180069cd6  mov     [rbp+var_8], r14
0x180069cda  xor     r9d, r9d; unsigned int
0x180069cdd  mov     r8d, 2EFh; char *
0x180069ce3  mov     rdx, r12; char *
0x180069ce6  lea     r15, aOnecoreuapDsEx_70; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180069ced  mov     rcx, r15; this
0x180069cf0  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180069cf5  nop
0x180069cf6  mov     [rbp+TokenHandle], r14
0x180069cfa  mov     [rbp+TokenInformationLength], r14d
0x180069cfe  mov     [rbp+TokenInformation], r14
0x180069d02  mov     [rbp+var_38], r14d
0x180069d06  mov     [rbp+var_28], r14d
0x180069d0a  mov     [rbp+StringSid], r14
0x180069d0e  mov     [rbp+var_40], r14
0x180069d12  mov     [rbp+var_48], r14
0x180069d16  mov     ecx, cs:_tls_index
0x180069d1c  mov     rax, gs:58h
0x180069d25  mov     edx, 10h
0x180069d2a  mov     rax, [rax+rcx*8]
0x180069d2e  mov     rdx, [rdx+rax]
0x180069d32  test    rdx, rdx
0x180069d35  jz      short loc_180069D78
0x180069d37  mov     rcx, rsi
0x180069d3a  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180069d3f  mov     rax, [rsi]
0x180069d42  cmp     [rax-10h], r14d
0x180069d46  jnz     loc_180069F0A
0x180069d4c  mov     r9d, 80070057h; int
0x180069d52  lea     rax, aWstrsidIsempty; "!wstrSid.IsEmpty()"
0x180069d59  mov     r8d, 2FEh; unsigned int
0x180069d5f  mov     [rbp+arg_8], r9d
0x180069d63  mov     [rsp+80h+ReturnLength], rax; char *
0x180069d68  mov     rdx, r12; char *
0x180069d6b  mov     rcx, r15; char *
0x180069d6e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180069d73  jmp     loc_180069F0A
0x180069d78  lea     rdx, [rbp+TokenHandle]; TokenHandle
0x180069d7c  mov     ecx, 8; DesiredAccess
0x180069d81  call    ?GetCurrentUserToken@WlidsvcUtil@@SAJKAEAVCHandle@ATL@@@Z; WlidsvcUtil::GetCurrentUserToken(ulong,ATL::CHandle &)
0x180069d86  mov     [rbp+arg_8], eax
0x180069d89  test    eax, eax
0x180069d8b  jns     short loc_180069DA4
0x180069d8d  lea     rcx, aHrWlidsvcutilG_1; "hr = WlidsvcUtil::GetCurrentUserToken(T"...
0x180069d94  mov     [rsp+80h+ReturnLength], rcx
0x180069d99  mov     r9d, eax
0x180069d9c  mov     r8d, 304h
0x180069da2  jmp     short loc_180069D68
0x180069da4  lea     rax, [rbp+TokenInformationLength]
0x180069da8  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180069dad  xor     r9d, r9d; TokenInformationLength
0x180069db0  xor     r8d, r8d; TokenInformation
0x180069db3  lea     ebx, [r9+1]
0x180069db7  mov     edx, ebx; TokenInformationClass
0x180069db9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180069dbd  call    cs:__imp_GetTokenInformation
0x180069dc3  test    eax, eax
0x180069dc5  jz      short loc_180069DDC
0x180069dc7  mov     r9d, 8000FFFFh
0x180069dcd  lea     rax, aGettokeninform; "!GetTokenInformation(hToken, TokenUser,"...
0x180069dd4  mov     r8d, 307h
0x180069dda  jmp     short loc_180069D5F
0x180069ddc  call    cs:__imp_GetLastError
0x180069de2  cmp     eax, 7Ah ; 'z'
0x180069de5  jz      short loc_180069E19
0x180069de7  test    eax, eax
0x180069de9  jle     short loc_180069DF3
0x180069deb  movzx   eax, ax
0x180069dee  or      eax, 80070000h
0x180069df3  mov     [rbp+arg_8], eax
0x180069df6  mov     dword ptr [rsp+80h+ReturnLength], eax
0x180069dfa  lea     r9, aGettokeninform_0; "GetTokenInformation failed with hr = 0x"...
0x180069e01  mov     r8d, 30Eh; unsigned int
0x180069e07  mov     rdx, r15; char *
0x180069e0a  mov     ecx, 2; unsigned __int8
0x180069e0f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180069e14  jmp     loc_180069F0A
0x180069e19  mov     r8b, bl; bool
0x180069e1c  mov     edx, [rbp+TokenInformationLength]; unsigned int
0x180069e1f  lea     rcx, [rbp+var_38]; this
0x180069e23  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x180069e28  mov     rdi, [rbp+TokenInformation]
0x180069e2c  test    rdi, rdi
0x180069e2f  jz      loc_180069F03
0x180069e35  lea     rax, [rbp+TokenInformationLength]
0x180069e39  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180069e3e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180069e42  mov     r8, rdi; TokenInformation
0x180069e45  mov     edx, ebx; TokenInformationClass
0x180069e47  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180069e4b  call    cs:__imp_GetTokenInformation
0x180069e51  mov     ebx, 80070000h
0x180069e56  test    eax, eax
0x180069e58  jnz     short loc_180069E8A
0x180069e5a  call    cs:__imp_GetLastError
0x180069e60  test    eax, eax
0x180069e62  jle     short loc_180069E69
0x180069e64  movzx   eax, ax
0x180069e67  or      eax, ebx
0x180069e69  mov     [rbp+arg_8], eax
0x180069e6c  test    eax, eax
0x180069e6e  jns     short loc_180069E8A
0x180069e70  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180069e77  mov     [rsp+80h+ReturnLength], rcx
0x180069e7c  mov     r9d, eax
0x180069e7f  mov     r8d, 317h
0x180069e85  jmp     loc_180069D68
0x180069e8a  mov     rcx, [rdi]; pSid
0x180069e8d  call    cs:__imp_IsValidSid
0x180069e93  test    eax, eax
0x180069e95  jnz     short loc_180069EAF
0x180069e97  mov     r9d, 8000FFFFh
0x180069e9d  lea     rax, aIsvalidsidPtiu; "IsValidSid(ptiUser->User.Sid)"
0x180069ea4  mov     r8d, 319h
0x180069eaa  jmp     loc_180069D5F
0x180069eaf  lea     rdx, [rbp+StringSid]; StringSid
0x180069eb3  mov     rcx, [rdi]; Sid
0x180069eb6  call    cs:__imp_ConvertSidToStringSidW
0x180069ebc  test    eax, eax
0x180069ebe  jnz     short loc_180069EF0
0x180069ec0  call    cs:__imp_GetLastError
0x180069ec6  test    eax, eax
0x180069ec8  jle     short loc_180069ECF
0x180069eca  movzx   eax, ax
0x180069ecd  or      eax, ebx
0x180069ecf  mov     [rbp+arg_8], eax
0x180069ed2  test    eax, eax
0x180069ed4  jns     short loc_180069EF0
0x180069ed6  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180069edd  mov     [rsp+80h+ReturnLength], rcx
0x180069ee2  mov     r9d, eax
0x180069ee5  mov     r8d, 31Bh
0x180069eeb  jmp     loc_180069D68
0x180069ef0  mov     rdx, [rbp+StringSid]
0x180069ef4  test    rdx, rdx
0x180069ef7  jz      short loc_180069F03
0x180069ef9  mov     rcx, rsi
0x180069efc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180069f01  jmp     short loc_180069F0A
0x180069f03  mov     [rbp+arg_8], 8007000Eh
0x180069f0a  mov     ebx, [rbp+arg_8]
0x180069f0d  lea     rcx, [rbp+StringSid]
0x180069f11  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180069f16  nop
0x180069f17  lea     rcx, [rbp+var_38]; this
0x180069f1b  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180069f20  nop
0x180069f21  lea     rcx, [rbp+TokenHandle]; this
0x180069f25  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180069f2a  nop
0x180069f2b  lea     rcx, [rbp+var_20]
0x180069f2f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180069f34  mov     eax, ebx
0x180069f36  add     rsp, 80h
0x180069f3d  pop     r15
0x180069f3f  pop     r14
0x180069f41  pop     r12
0x180069f43  pop     rdi
0x180069f44  pop     rsi
0x180069f45  pop     rbx
0x180069f46  pop     rbp
0x180069f47  retn
```
