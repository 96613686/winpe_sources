# CRCMPublicRpc::Start(void)

- ea: `0x18005f8a0`
- end: `0x18005fe0f`
- name: `?Start@CRCMPublicRpc@@UEAAJXZ`
- size: `1391`
- prototype: `__int64 __fastcall(CRCMPublicRpc *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009940`
- `0x180033f60`
- `0x18003440c`
- `0x180051aa4`
- `0x18005e92c`
- `0x18005eb60`
- `0x18005f8a0`
- `0x1800a0dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fadb`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005fcf4`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005fd44`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005fcf4`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005fd44`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18005fb7d`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18005fb7d`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18005fb54`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18005fb54`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005fb09`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005fb09`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fbda`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fc18`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fc56`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fca4`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fbda`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fc18`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fc56`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005fca4`
- `RPCRT4!RpcServerListen` at `0x18005fd60`
- `RPCRT4!RpcServerListen` at `0x18005fd60`
- `RPCRT4!RpcStringFreeW` at `0x18005fb98`
- `RPCRT4!RpcStringFreeW` at `0x18005fb98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fd9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fdb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fdc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fd9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fdb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fdc8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f9f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f9f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005fa92`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005facb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005fa92`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005facb`

## string_xrefs

- `0x18005f999`: `RCMPublicRpc already started`
- `0x18005f9c9`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`
- `0x18005fa0d`: `Error %d ConvertSidToStringSidW`
- `0x18005faae`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainer)`
- `0x18005fae7`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainerWithUserSignInCapability)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRCMPublicRpc::Start(CRCMPublicRpc *this)
{
  PSID v2; // rsi
  WCHAR *v3; // rax
  const wchar_t *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  DWORD v8; // eax
  signed int v9; // eax
  int v10; // eax
  DWORD v11; // eax
  DWORD LastError; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  RPC_WSTR PrincName; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v21; // [rsp+68h] [rbp-98h] BYREF
  WCHAR StringSecurityDescriptor[192]; // [rsp+70h] [rbp-90h] BYREF

  PrincName = 0;
  SecurityDescriptor = 0;
  v2 = 0;
  Sid = 0;
  StringSid = 0;
  v21 = 0;
  hMem = 0;
  v3 = StringSecurityDescriptor;
  v4 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGWGX;;;AC)(A;;GRGWGX;;;S-1-15-3-1024-1864111754-7"
        "76273317-3666925027-2523908081-3792458206-3582472437-4114419977-1582884857)";
  v5 = 2;
  do
  {
    *(_OWORD *)v3 = *(_OWORD *)v4;
    *((_OWORD *)v3 + 1) = *((_OWORD *)v4 + 1);
    *((_OWORD *)v3 + 2) = *((_OWORD *)v4 + 2);
    *((_OWORD *)v3 + 3) = *((_OWORD *)v4 + 3);
    *((_OWORD *)v3 + 4) = *((_OWORD *)v4 + 4);
    *((_OWORD *)v3 + 5) = *((_OWORD *)v4 + 5);
    *((_OWORD *)v3 + 6) = *((_OWORD *)v4 + 6);
    *((_OWORD *)v3 + 7) = *((_OWORD *)v4 + 7);
    v3 += 64;
    v4 += 64;
    --v5;
  }
  while ( v5 );
  *(_OWORD *)v3 = *(_OWORD *)v4;
  *((_OWORD *)v3 + 1) = *((_OWORD *)v4 + 1);
  *((_OWORD *)v3 + 2) = *((_OWORD *)v4 + 2);
  *((_OWORD *)v3 + 3) = *((_OWORD *)v4 + 3);
  *((_OWORD *)v3 + 4) = *((_OWORD *)v4 + 4);
  *((_OWORD *)v3 + 5) = *((_OWORD *)v4 + 5);
  *((_OWORD *)v3 + 6) = *((_OWORD *)v4 + 6);
  *(_OWORD *)(v3 + 53) = *(_OWORD *)(v4 + 53);
  if ( !*((_DWORD *)this + 398) )
  {
    v6 = CUtils::CreateUserSignInCapabilitySID(&Sid);
    v7 = v6;
    if ( v6 < 0 )
    {
      _DbgPrintMessage(8, "CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s", v6, "CRCMPublicRpc::Start");
      v2 = Sid;
      goto LABEL_46;
    }
    v2 = Sid;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v21,
              L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGWGX;;;%s)",
              StringSid);
      v7 = v10;
      if ( v10 < 0 )
      {
        _DbgPrintMessage(8, "wil::str_printf_nothrow failed: 0x%x in %s", v10, "CRCMPublicRpc::Start");
        goto LABEL_46;
      }
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      {
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v21, 1u, &hMem, 0) )
        {
          v13 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x80u, (RPC_WSTR)L"TermSrvApi", SecurityDescriptor);
          v7 = v13;
          if ( !v13 || v13 == 1740 )
          {
            v7 = RpcServerInqDefaultPrincNameW(9u, &PrincName);
            if ( v7 )
            {
              _DbgPrintMessage(8, "Error %d RpcServerInqDefaultPrincName", v7);
            }
            else
            {
              v7 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0);
              if ( PrincName )
                RpcStringFreeW(&PrincName);
              if ( v7 )
              {
                _DbgPrintMessage(8, "Error %d RpcServerRegisterAuthInfo", v7);
              }
              else
              {
                v7 = RpcServerRegisterIfEx(
                       qword_1800D6490,
                       0,
                       0,
                       9u,
                       0x4D2u,
                       CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote);
                if ( v7 )
                {
                  _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublic )", v7);
                }
                else
                {
                  v7 = RpcServerRegisterIfEx(
                         qword_1800D5F50,
                         0,
                         0,
                         9u,
                         0x4D2u,
                         CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote);
                  if ( v7 )
                  {
                    _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMListener )", v7);
                  }
                  else
                  {
                    v7 = RpcServerRegisterIfEx(
                           qword_1800D78A0,
                           0,
                           0,
                           9u,
                           0x4D2u,
                           CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly);
                    if ( v7 )
                    {
                      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublicLocal )", v7);
                    }
                    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
                           && (v7 = RpcServerRegisterIfEx(
                                      qword_1800D5D00,
                                      0,
                                      0,
                                      9u,
                                      0x4D2u,
                                      CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly)) != 0 )
                    {
                      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublicLocal2 )", v7);
                    }
                    else
                    {
                      v7 = RpcServerRegisterIf3(
                             qword_1800D5E70,
                             0,
                             0,
                             9,
                             1234,
                             0,
                             CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly,
                             SecurityDescriptor);
                      if ( v7
                        || (v7 = RpcServerRegisterIf3(
                                   qword_1800D6CE0,
                                   0,
                                   0,
                                   9,
                                   1234,
                                   0,
                                   CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly,
                                   hMem)) != 0 )
                      {
                        _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublicLocalAppContainer )", v7);
                      }
                      else
                      {
                        v14 = RpcServerListen(1u, 0x4D2u, 1u);
                        v7 = v14;
                        if ( !v14 || v14 == 1713 )
                        {
                          *((_DWORD *)this + 398) = 1;
                          goto LABEL_45;
                        }
                        _DbgPrintMessage(8, "Error %d RpcServerListen", v14);
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            _DbgPrintMessage(8, "Error %d RpcUseProtseqEp on ncalrpc", v13);
          }
          if ( (int)v7 <= 0 )
            goto LABEL_46;
          v7 = (unsigned __int16)v7;
LABEL_11:
          v7 |= 0x80070000;
          goto LABEL_46;
        }
        LastError = GetLastError();
        _DbgPrintMessage(
          8,
          "Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainerWithUserSignInCapability)",
          LastError);
      }
      else
      {
        v11 = GetLastError();
        _DbgPrintMessage(8, "Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainer)", v11);
      }
    }
    else
    {
      v8 = GetLastError();
      _DbgPrintMessage(8, "Error %d ConvertSidToStringSidW", v8);
    }
    v9 = GetLastError();
    v7 = v9;
    if ( v9 <= 0 )
      goto LABEL_46;
    v7 = (unsigned __int16)v9;
    goto LABEL_11;
  }
  _DbgPrintMessage(1, "RCMPublicRpc already started");
LABEL_45:
  v7 = 0;
LABEL_46:
  if ( hMem )
    LocalFree(hMem);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v2 )
    operator delete(v2);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  return v7;
}

```

## disassembly

```asm
0x18005f8a0  push    rbp
0x18005f8a2  push    rbx
0x18005f8a3  push    rsi
0x18005f8a4  push    r12
0x18005f8a6  push    r13
0x18005f8a8  push    r14
0x18005f8aa  lea     rbp, [rsp-108h]
0x18005f8b2  sub     rsp, 208h
0x18005f8b9  mov     rax, cs:__security_cookie
0x18005f8c0  xor     rax, rsp
0x18005f8c3  mov     [rbp+130h+var_40], rax
0x18005f8ca  mov     r14, rcx
0x18005f8cd  mov     [rsp+230h+PrincName], 0
0x18005f8d6  mov     [rsp+230h+SecurityDescriptor], 0
0x18005f8df  xor     esi, esi
0x18005f8e1  mov     [rsp+230h+Sid], rsi
0x18005f8e6  mov     [rsp+230h+StringSid], rsi
0x18005f8eb  mov     [rsp+230h+var_1C8], rsi
0x18005f8f0  mov     [rsp+230h+hMem], rsi
0x18005f8f5  lea     rax, [rsp+230h+StringSecurityDescriptor]
0x18005f8fa  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18005f901  lea     edx, [rsi+2]
0x18005f904  lea     r12d, [rdx+7Eh]
0x18005f908  movups  xmm0, xmmword ptr [rcx]
0x18005f90b  movups  xmmword ptr [rax], xmm0
0x18005f90e  movups  xmm1, xmmword ptr [rcx+10h]
0x18005f912  movups  xmmword ptr [rax+10h], xmm1
0x18005f916  movups  xmm0, xmmword ptr [rcx+20h]
0x18005f91a  movups  xmmword ptr [rax+20h], xmm0
0x18005f91e  movups  xmm1, xmmword ptr [rcx+30h]
0x18005f922  movups  xmmword ptr [rax+30h], xmm1
0x18005f926  movups  xmm0, xmmword ptr [rcx+40h]
0x18005f92a  movups  xmmword ptr [rax+40h], xmm0
0x18005f92e  movups  xmm1, xmmword ptr [rcx+50h]
0x18005f932  movups  xmmword ptr [rax+50h], xmm1
0x18005f936  movups  xmm0, xmmword ptr [rcx+60h]
0x18005f93a  movups  xmmword ptr [rax+60h], xmm0
0x18005f93e  movups  xmm1, xmmword ptr [rcx+70h]
0x18005f942  movups  xmmword ptr [rax+70h], xmm1
0x18005f946  add     rax, r12
0x18005f949  add     rcx, r12
0x18005f94c  sub     rdx, 1
0x18005f950  jnz     short loc_18005F908
0x18005f952  movups  xmm0, xmmword ptr [rcx]
0x18005f955  movups  xmmword ptr [rax], xmm0
0x18005f958  movups  xmm1, xmmword ptr [rcx+10h]
0x18005f95c  movups  xmmword ptr [rax+10h], xmm1
0x18005f960  movups  xmm0, xmmword ptr [rcx+20h]
0x18005f964  movups  xmmword ptr [rax+20h], xmm0
0x18005f968  movups  xmm1, xmmword ptr [rcx+30h]
0x18005f96c  movups  xmmword ptr [rax+30h], xmm1
0x18005f970  movups  xmm0, xmmword ptr [rcx+40h]
0x18005f974  movups  xmmword ptr [rax+40h], xmm0
0x18005f978  movups  xmm1, xmmword ptr [rcx+50h]
0x18005f97c  movups  xmmword ptr [rax+50h], xmm1
0x18005f980  movups  xmm0, xmmword ptr [rcx+60h]
0x18005f984  movups  xmmword ptr [rax+60h], xmm0
0x18005f988  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18005f98c  movups  xmmword ptr [rax+6Ah], xmm1
0x18005f990  cmp     [r14+638h], edx
0x18005f997  jz      short loc_18005F9AF
0x18005f999  lea     rdx, aRcmpublicrpcAl; "RCMPublicRpc already started"
0x18005f9a0  mov     ecx, 1; int
0x18005f9a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005f9aa  jmp     loc_18005FD90
0x18005f9af  lea     rcx, [rsp+230h+Sid]; void **
0x18005f9b4  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x18005f9b9  mov     ebx, eax
0x18005f9bb  test    eax, eax
0x18005f9bd  jns     short loc_18005F9E4
0x18005f9bf  lea     r9, aCrcmpublicrpcS; "CRCMPublicRpc::Start"
0x18005f9c6  mov     r8d, eax
0x18005f9c9  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x18005f9d0  mov     ecx, 8; int
0x18005f9d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005f9da  mov     rsi, [rsp+230h+Sid]
0x18005f9df  jmp     loc_18005FD92
0x18005f9e4  lea     rdx, [rsp+230h+StringSid]; StringSid
0x18005f9e9  mov     rsi, [rsp+230h+Sid]
0x18005f9ee  mov     rcx, rsi; Sid
0x18005f9f1  call    cs:__imp_ConvertSidToStringSidW
0x18005f9f8  nop     dword ptr [rax+rax+00h]
0x18005f9fd  test    eax, eax
0x18005f9ff  jnz     short loc_18005FA45
0x18005fa01  call    cs:__imp_GetLastError
0x18005fa08  nop     dword ptr [rax+rax+00h]
0x18005fa0d  lea     rdx, aErrorDConverts_1; "Error %d ConvertSidToStringSidW"
0x18005fa14  mov     r8d, eax
0x18005fa17  mov     ecx, 8; int
0x18005fa1c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fa21  call    cs:__imp_GetLastError
0x18005fa28  nop     dword ptr [rax+rax+00h]
0x18005fa2d  mov     ebx, eax
0x18005fa2f  test    eax, eax
0x18005fa31  jle     loc_18005FD92
0x18005fa37  movzx   ebx, ax
0x18005fa3a  or      ebx, 80070000h
0x18005fa40  jmp     loc_18005FD92
0x18005fa45  mov     r8, [rsp+230h+StringSid]
0x18005fa4a  lea     rdx, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18005fa51  lea     rcx, [rsp+230h+var_1C8]
0x18005fa56  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005fa5b  mov     ebx, eax
0x18005fa5d  test    eax, eax
0x18005fa5f  jns     short loc_18005FA81
0x18005fa61  lea     r9, aCrcmpublicrpcS; "CRCMPublicRpc::Start"
0x18005fa68  mov     r8d, eax
0x18005fa6b  lea     rdx, aWilStrPrintfNo; "wil::str_printf_nothrow failed: 0x%x in"...
0x18005fa72  mov     ecx, 8; int
0x18005fa77  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fa7c  jmp     loc_18005FD92
0x18005fa81  xor     r9d, r9d; SecurityDescriptorSize
0x18005fa84  lea     r8, [rsp+230h+SecurityDescriptor]; SecurityDescriptor
0x18005fa89  lea     edx, [r9+1]; StringSDRevision
0x18005fa8d  lea     rcx, [rsp+230h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18005fa92  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005fa99  nop     dword ptr [rax+rax+00h]
0x18005fa9e  test    eax, eax
0x18005faa0  jnz     short loc_18005FABA
0x18005faa2  call    cs:__imp_GetLastError
0x18005faa9  nop     dword ptr [rax+rax+00h]
0x18005faae  lea     rdx, aErrorDConverts_0; "Error %d ConvertStringSecurityDescripto"...
0x18005fab5  jmp     loc_18005FA14
0x18005faba  xor     r9d, r9d; SecurityDescriptorSize
0x18005fabd  lea     r8, [rsp+230h+hMem]; SecurityDescriptor
0x18005fac2  lea     edx, [r9+1]; StringSDRevision
0x18005fac6  mov     rcx, [rsp+230h+var_1C8]; StringSecurityDescriptor
0x18005facb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005fad2  nop     dword ptr [rax+rax+00h]
0x18005fad7  test    eax, eax
0x18005fad9  jnz     short loc_18005FAF3
0x18005fadb  call    cs:__imp_GetLastError
0x18005fae2  nop     dword ptr [rax+rax+00h]
0x18005fae7  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x18005faee  jmp     loc_18005FA14
0x18005faf3  mov     r9, [rsp+230h+SecurityDescriptor]; SecurityDescriptor
0x18005faf8  lea     r8, aTermsrvapi_0; "TermSrvApi"
0x18005faff  mov     edx, r12d; MaxCalls
0x18005fb02  lea     rcx, aNcalrpc; "ncalrpc"
0x18005fb09  call    cs:__imp_RpcServerUseProtseqEpW
0x18005fb10  nop     dword ptr [rax+rax+00h]
0x18005fb15  mov     ebx, eax
0x18005fb17  test    eax, eax
0x18005fb19  jz      short loc_18005FB46
0x18005fb1b  cmp     eax, 6CCh
0x18005fb20  jz      short loc_18005FB46
0x18005fb22  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18005fb29  mov     r8d, ebx
0x18005fb2c  mov     ecx, 8; int
0x18005fb31  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fb36  test    ebx, ebx
0x18005fb38  jle     loc_18005FD92
0x18005fb3e  movzx   ebx, bx
0x18005fb41  jmp     loc_18005FA3A
0x18005fb46  lea     rdx, [rsp+230h+PrincName]; PrincName
0x18005fb4b  mov     r12d, 9
0x18005fb51  mov     ecx, r12d; AuthnSvc
0x18005fb54  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18005fb5b  nop     dword ptr [rax+rax+00h]
0x18005fb60  mov     ebx, eax
0x18005fb62  test    eax, eax
0x18005fb64  jz      short loc_18005FB6F
0x18005fb66  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerInqDefaultPrincName"
0x18005fb6d  jmp     short loc_18005FB29
0x18005fb6f  xor     r9d, r9d; Arg
0x18005fb72  xor     r8d, r8d; GetKeyFn
0x18005fb75  mov     edx, r12d; AuthnSvc
0x18005fb78  mov     rcx, [rsp+230h+PrincName]; ServerPrincName
0x18005fb7d  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18005fb84  nop     dword ptr [rax+rax+00h]
0x18005fb89  mov     ebx, eax
0x18005fb8b  cmp     [rsp+230h+PrincName], 0
0x18005fb91  jz      short loc_18005FBA4
0x18005fb93  lea     rcx, [rsp+230h+PrincName]; String
0x18005fb98  call    cs:__imp_RpcStringFreeW
0x18005fb9f  nop     dword ptr [rax+rax+00h]
0x18005fba4  test    ebx, ebx
0x18005fba6  jz      short loc_18005FBB4
0x18005fba8  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterAuthInfo"
0x18005fbaf  jmp     loc_18005FB29
0x18005fbb4  lea     rax, ?staticRCMPublicRpcSecurityCallbackRemote@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote(void *,void *)
0x18005fbbb  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005fbc0  mov     r13d, 4D2h
0x18005fbc6  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005fbcb  mov     r9d, r12d; Flags
0x18005fbce  xor     r8d, r8d; MgrEpv
0x18005fbd1  xor     edx, edx; MgrTypeUuid
0x18005fbd3  lea     rcx, qword_1800D6490; IfSpec
0x18005fbda  call    cs:__imp_RpcServerRegisterIfEx
0x18005fbe1  nop     dword ptr [rax+rax+00h]
0x18005fbe6  mov     ebx, eax
0x18005fbe8  test    eax, eax
0x18005fbea  jz      short loc_18005FBF8
0x18005fbec  lea     rdx, aErrorDRpcserve_3; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005fbf3  jmp     loc_18005FB29
0x18005fbf8  lea     rax, ?staticRCMPublicRpcSecurityCallbackRemote@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote(void *,void *)
0x18005fbff  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005fc04  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005fc09  mov     r9d, r12d; Flags
0x18005fc0c  xor     r8d, r8d; MgrEpv
0x18005fc0f  xor     edx, edx; MgrTypeUuid
0x18005fc11  lea     rcx, qword_1800D5F50; IfSpec
0x18005fc18  call    cs:__imp_RpcServerRegisterIfEx
0x18005fc1f  nop     dword ptr [rax+rax+00h]
0x18005fc24  mov     ebx, eax
0x18005fc26  test    eax, eax
0x18005fc28  jz      short loc_18005FC36
0x18005fc2a  lea     rdx, aErrorDRpcserve_6; "Error %d RpcServerRegisterIf( RCMListen"...
0x18005fc31  jmp     loc_18005FB29
0x18005fc36  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005fc3d  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005fc42  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005fc47  mov     r9d, r12d; Flags
0x18005fc4a  xor     r8d, r8d; MgrEpv
0x18005fc4d  xor     edx, edx; MgrTypeUuid
0x18005fc4f  lea     rcx, qword_1800D78A0; IfSpec
0x18005fc56  call    cs:__imp_RpcServerRegisterIfEx
0x18005fc5d  nop     dword ptr [rax+rax+00h]
0x18005fc62  mov     ebx, eax
0x18005fc64  test    eax, eax
0x18005fc66  jz      short loc_18005FC74
0x18005fc68  lea     rdx, aErrorDRpcserve_1; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005fc6f  jmp     loc_18005FB29
0x18005fc74  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18005fc7b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18005fc80  test    al, al
0x18005fc82  jz      short loc_18005FCC2
0x18005fc84  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005fc8b  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005fc90  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005fc95  mov     r9d, r12d; Flags
0x18005fc98  xor     r8d, r8d; MgrEpv
0x18005fc9b  xor     edx, edx; MgrTypeUuid
0x18005fc9d  lea     rcx, qword_1800D5D00; IfSpec
0x18005fca4  call    cs:__imp_RpcServerRegisterIfEx
0x18005fcab  nop     dword ptr [rax+rax+00h]
0x18005fcb0  mov     ebx, eax
0x18005fcb2  test    eax, eax
0x18005fcb4  jz      short loc_18005FCC2
0x18005fcb6  lea     rdx, aErrorDRpcserve_8; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005fcbd  jmp     loc_18005FB29
0x18005fcc2  mov     rax, [rsp+230h+SecurityDescriptor]
0x18005fcc7  mov     [rsp+230h+var_1F8], rax
0x18005fccc  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005fcd3  mov     [rsp+230h+var_200], rax
0x18005fcd8  mov     dword ptr [rsp+230h+IfCallback], 0
0x18005fce0  mov     [rsp+230h+MaxCalls], r13d
0x18005fce5  mov     r9d, r12d
0x18005fce8  xor     r8d, r8d
0x18005fceb  xor     edx, edx
0x18005fced  lea     rcx, qword_1800D5E70
0x18005fcf4  call    cs:__imp_RpcServerRegisterIf3
0x18005fcfb  nop     dword ptr [rax+rax+00h]
0x18005fd00  mov     ebx, eax
0x18005fd02  test    eax, eax
0x18005fd04  jz      short loc_18005FD12
0x18005fd06  lea     rdx, aErrorDRpcserve_5; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005fd0d  jmp     loc_18005FB29
0x18005fd12  mov     rax, [rsp+230h+hMem]
0x18005fd17  mov     [rsp+230h+var_1F8], rax
0x18005fd1c  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005fd23  mov     [rsp+230h+var_200], rax
0x18005fd28  mov     dword ptr [rsp+230h+IfCallback], 0
0x18005fd30  mov     [rsp+230h+MaxCalls], r13d
0x18005fd35  mov     r9d, r12d
0x18005fd38  xor     r8d, r8d
0x18005fd3b  xor     edx, edx
0x18005fd3d  lea     rcx, qword_1800D6CE0
0x18005fd44  call    cs:__imp_RpcServerRegisterIf3
0x18005fd4b  nop     dword ptr [rax+rax+00h]
0x18005fd50  mov     ebx, eax
0x18005fd52  test    eax, eax
0x18005fd54  jnz     short loc_18005FD06
0x18005fd56  lea     r8d, [rax+1]; DontWait
0x18005fd5a  mov     edx, r13d; MaxCalls
0x18005fd5d  mov     ecx, r8d; MinimumCallThreads
0x18005fd60  call    cs:__imp_RpcServerListen
0x18005fd67  nop     dword ptr [rax+rax+00h]
0x18005fd6c  mov     ebx, eax
0x18005fd6e  test    eax, eax
0x18005fd70  jz      short loc_18005FD85
0x18005fd72  cmp     eax, 6B1h
0x18005fd77  jz      short loc_18005FD85
0x18005fd79  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x18005fd80  jmp     loc_18005FB29
0x18005fd85  mov     dword ptr [r14+638h], 1
0x18005fd90  xor     ebx, ebx
0x18005fd92  mov     rcx, [rsp+230h+hMem]; hMem
0x18005fd97  test    rcx, rcx
0x18005fd9a  jz      short loc_18005FDA8
0x18005fd9c  call    cs:__imp_LocalFree
0x18005fda3  nop     dword ptr [rax+rax+00h]
0x18005fda8  mov     rcx, [rsp+230h+SecurityDescriptor]; hMem
0x18005fdad  test    rcx, rcx
0x18005fdb0  jz      short loc_18005FDBE
0x18005fdb2  call    cs:__imp_LocalFree
0x18005fdb9  nop     dword ptr [rax+rax+00h]
0x18005fdbe  mov     rcx, [rsp+230h+StringSid]; hMem
0x18005fdc3  test    rcx, rcx
0x18005fdc6  jz      short loc_18005FDD4
  ... truncated ...
```
