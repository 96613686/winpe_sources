# CRCMPublicRpc::Start(void)

- ea: `0x18005ca70`
- end: `0x18005cf5d`
- name: `?Start@CRCMPublicRpc@@UEAAJXZ`
- size: `1261`
- prototype: `__int64 __fastcall(CRCMPublicRpc *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x18003269c`
- `0x18004f3fc`
- `0x18005bb7c`
- `0x18005bda8`
- `0x18005ca70`
- `0x18009caac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc87`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005ce67`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005ceb1`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005ce67`
- `RPCRT4!RpcServerRegisterIf3` at `0x18005ceb1`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18005cd17`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18005cd17`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18005ccf4`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18005ccf4`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005ccaf`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18005ccaf`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cd65`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cd9d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cdd5`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005ce1d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cd65`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cd9d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005cdd5`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18005ce1d`
- `RPCRT4!RpcServerListen` at `0x18005cec7`
- `RPCRT4!RpcServerListen` at `0x18005cec7`
- `RPCRT4!RpcStringFreeW` at `0x18005cd2c`
- `RPCRT4!RpcStringFreeW` at `0x18005cd2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cf1d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005cbc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005cbc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005cc50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005cc7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005cc50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005cc7d`

## string_xrefs

- `0x18005cb69`: `RCMPublicRpc already started`
- `0x18005cb99`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`
- `0x18005cbd1`: `Error %d ConvertSidToStringSidW`
- `0x18005cc60`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainer)`
- `0x18005cc8d`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor (AllowAppContainerWithUserSignInCapability)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
                       qword_1800D03B0,
                       0,
                       0,
                       9u,
                       0x4D2u,
                       (RPC_IF_CALLBACK_FN *)CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote);
                if ( v7 )
                {
                  _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublic )", v7);
                }
                else
                {
                  v7 = RpcServerRegisterIfEx(
                         qword_1800CFF60,
                         0,
                         0,
                         9u,
                         0x4D2u,
                         (RPC_IF_CALLBACK_FN *)CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote);
                  if ( v7 )
                  {
                    _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMListener )", v7);
                  }
                  else
                  {
                    v7 = RpcServerRegisterIfEx(
                           qword_1800D1800,
                           0,
                           0,
                           9u,
                           0x4D2u,
                           (RPC_IF_CALLBACK_FN *)CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly);
                    if ( v7 )
                    {
                      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublicLocal )", v7);
                    }
                    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
                           && (v7 = RpcServerRegisterIfEx(
                                      qword_1800CFCC0,
                                      0,
                                      0,
                                      9u,
                                      0x4D2u,
                                      (RPC_IF_CALLBACK_FN *)CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly)) != 0 )
                    {
                      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( RCMPublicLocal2 )", v7);
                    }
                    else
                    {
                      v7 = RpcServerRegisterIf3(
                             qword_1800CFE30,
                             0,
                             0,
                             9,
                             1234,
                             0,
                             CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly,
                             SecurityDescriptor);
                      if ( v7
                        || (v7 = RpcServerRegisterIf3(
                                   qword_1800D0CA0,
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
0x18005ca70  push    rbp
0x18005ca72  push    rbx
0x18005ca73  push    rsi
0x18005ca74  push    r12
0x18005ca76  push    r13
0x18005ca78  push    r14
0x18005ca7a  lea     rbp, [rsp-108h]
0x18005ca82  sub     rsp, 208h
0x18005ca89  mov     rax, cs:__security_cookie
0x18005ca90  xor     rax, rsp
0x18005ca93  mov     [rbp+130h+var_40], rax
0x18005ca9a  mov     r14, rcx
0x18005ca9d  mov     [rsp+230h+PrincName], 0
0x18005caa6  mov     [rsp+230h+SecurityDescriptor], 0
0x18005caaf  xor     esi, esi
0x18005cab1  mov     [rsp+230h+Sid], rsi
0x18005cab6  mov     [rsp+230h+StringSid], rsi
0x18005cabb  mov     [rsp+230h+var_1C8], rsi
0x18005cac0  mov     [rsp+230h+hMem], rsi
0x18005cac5  lea     rax, [rsp+230h+StringSecurityDescriptor]
0x18005caca  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18005cad1  lea     edx, [rsi+2]
0x18005cad4  lea     r12d, [rdx+7Eh]
0x18005cad8  movups  xmm0, xmmword ptr [rcx]
0x18005cadb  movups  xmmword ptr [rax], xmm0
0x18005cade  movups  xmm1, xmmword ptr [rcx+10h]
0x18005cae2  movups  xmmword ptr [rax+10h], xmm1
0x18005cae6  movups  xmm0, xmmword ptr [rcx+20h]
0x18005caea  movups  xmmword ptr [rax+20h], xmm0
0x18005caee  movups  xmm1, xmmword ptr [rcx+30h]
0x18005caf2  movups  xmmword ptr [rax+30h], xmm1
0x18005caf6  movups  xmm0, xmmword ptr [rcx+40h]
0x18005cafa  movups  xmmword ptr [rax+40h], xmm0
0x18005cafe  movups  xmm1, xmmword ptr [rcx+50h]
0x18005cb02  movups  xmmword ptr [rax+50h], xmm1
0x18005cb06  movups  xmm0, xmmword ptr [rcx+60h]
0x18005cb0a  movups  xmmword ptr [rax+60h], xmm0
0x18005cb0e  movups  xmm1, xmmword ptr [rcx+70h]
0x18005cb12  movups  xmmword ptr [rax+70h], xmm1
0x18005cb16  add     rax, r12
0x18005cb19  add     rcx, r12
0x18005cb1c  sub     rdx, 1
0x18005cb20  jnz     short loc_18005CAD8
0x18005cb22  movups  xmm0, xmmword ptr [rcx]
0x18005cb25  movups  xmmword ptr [rax], xmm0
0x18005cb28  movups  xmm1, xmmword ptr [rcx+10h]
0x18005cb2c  movups  xmmword ptr [rax+10h], xmm1
0x18005cb30  movups  xmm0, xmmword ptr [rcx+20h]
0x18005cb34  movups  xmmword ptr [rax+20h], xmm0
0x18005cb38  movups  xmm1, xmmword ptr [rcx+30h]
0x18005cb3c  movups  xmmword ptr [rax+30h], xmm1
0x18005cb40  movups  xmm0, xmmword ptr [rcx+40h]
0x18005cb44  movups  xmmword ptr [rax+40h], xmm0
0x18005cb48  movups  xmm1, xmmword ptr [rcx+50h]
0x18005cb4c  movups  xmmword ptr [rax+50h], xmm1
0x18005cb50  movups  xmm0, xmmword ptr [rcx+60h]
0x18005cb54  movups  xmmword ptr [rax+60h], xmm0
0x18005cb58  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18005cb5c  movups  xmmword ptr [rax+6Ah], xmm1
0x18005cb60  cmp     [r14+638h], edx
0x18005cb67  jz      short loc_18005CB7F
0x18005cb69  lea     rdx, aRcmpublicrpcAl; "RCMPublicRpc already started"
0x18005cb70  mov     ecx, 1; int
0x18005cb75  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005cb7a  jmp     loc_18005CEF1
0x18005cb7f  lea     rcx, [rsp+230h+Sid]; void **
0x18005cb84  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x18005cb89  mov     ebx, eax
0x18005cb8b  test    eax, eax
0x18005cb8d  jns     short loc_18005CBB4
0x18005cb8f  lea     r9, aCrcmpublicrpcS; "CRCMPublicRpc::Start"
0x18005cb96  mov     r8d, eax
0x18005cb99  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x18005cba0  mov     ecx, 8; int
0x18005cba5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005cbaa  mov     rsi, [rsp+230h+Sid]
0x18005cbaf  jmp     loc_18005CEF3
0x18005cbb4  lea     rdx, [rsp+230h+StringSid]; StringSid
0x18005cbb9  mov     rsi, [rsp+230h+Sid]
0x18005cbbe  mov     rcx, rsi; Sid
0x18005cbc1  call    cs:__imp_ConvertSidToStringSidW
0x18005cbc7  test    eax, eax
0x18005cbc9  jnz     short loc_18005CC03
0x18005cbcb  call    cs:__imp_GetLastError
0x18005cbd1  lea     rdx, aErrorDConverts_1; "Error %d ConvertSidToStringSidW"
0x18005cbd8  mov     r8d, eax
0x18005cbdb  mov     ecx, 8; int
0x18005cbe0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005cbe5  call    cs:__imp_GetLastError
0x18005cbeb  mov     ebx, eax
0x18005cbed  test    eax, eax
0x18005cbef  jle     loc_18005CEF3
0x18005cbf5  movzx   ebx, ax
0x18005cbf8  or      ebx, 80070000h
0x18005cbfe  jmp     loc_18005CEF3
0x18005cc03  mov     r8, [rsp+230h+StringSid]
0x18005cc08  lea     rdx, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18005cc0f  lea     rcx, [rsp+230h+var_1C8]
0x18005cc14  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005cc19  mov     ebx, eax
0x18005cc1b  test    eax, eax
0x18005cc1d  jns     short loc_18005CC3F
0x18005cc1f  lea     r9, aCrcmpublicrpcS; "CRCMPublicRpc::Start"
0x18005cc26  mov     r8d, eax
0x18005cc29  lea     rdx, aWilStrPrintfNo; "wil::str_printf_nothrow failed: 0x%x in"...
0x18005cc30  mov     ecx, 8; int
0x18005cc35  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005cc3a  jmp     loc_18005CEF3
0x18005cc3f  xor     r9d, r9d; SecurityDescriptorSize
0x18005cc42  lea     r8, [rsp+230h+SecurityDescriptor]; SecurityDescriptor
0x18005cc47  lea     edx, [r9+1]; StringSDRevision
0x18005cc4b  lea     rcx, [rsp+230h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18005cc50  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005cc56  test    eax, eax
0x18005cc58  jnz     short loc_18005CC6C
0x18005cc5a  call    cs:__imp_GetLastError
0x18005cc60  lea     rdx, aErrorDConverts_0; "Error %d ConvertStringSecurityDescripto"...
0x18005cc67  jmp     loc_18005CBD8
0x18005cc6c  xor     r9d, r9d; SecurityDescriptorSize
0x18005cc6f  lea     r8, [rsp+230h+hMem]; SecurityDescriptor
0x18005cc74  lea     edx, [r9+1]; StringSDRevision
0x18005cc78  mov     rcx, [rsp+230h+var_1C8]; StringSecurityDescriptor
0x18005cc7d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005cc83  test    eax, eax
0x18005cc85  jnz     short loc_18005CC99
0x18005cc87  call    cs:__imp_GetLastError
0x18005cc8d  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x18005cc94  jmp     loc_18005CBD8
0x18005cc99  mov     r9, [rsp+230h+SecurityDescriptor]; SecurityDescriptor
0x18005cc9e  lea     r8, aTermsrvapi_0; "TermSrvApi"
0x18005cca5  mov     edx, r12d; MaxCalls
0x18005cca8  lea     rcx, aNcalrpc; "ncalrpc"
0x18005ccaf  call    cs:__imp_RpcServerUseProtseqEpW
0x18005ccb5  mov     ebx, eax
0x18005ccb7  test    eax, eax
0x18005ccb9  jz      short loc_18005CCE6
0x18005ccbb  cmp     eax, 6CCh
0x18005ccc0  jz      short loc_18005CCE6
0x18005ccc2  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18005ccc9  mov     r8d, ebx
0x18005cccc  mov     ecx, 8; int
0x18005ccd1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ccd6  test    ebx, ebx
0x18005ccd8  jle     loc_18005CEF3
0x18005ccde  movzx   ebx, bx
0x18005cce1  jmp     loc_18005CBF8
0x18005cce6  lea     rdx, [rsp+230h+PrincName]; PrincName
0x18005cceb  mov     r12d, 9
0x18005ccf1  mov     ecx, r12d; AuthnSvc
0x18005ccf4  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18005ccfa  mov     ebx, eax
0x18005ccfc  test    eax, eax
0x18005ccfe  jz      short loc_18005CD09
0x18005cd00  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerInqDefaultPrincName"
0x18005cd07  jmp     short loc_18005CCC9
0x18005cd09  xor     r9d, r9d; Arg
0x18005cd0c  xor     r8d, r8d; GetKeyFn
0x18005cd0f  mov     edx, r12d; AuthnSvc
0x18005cd12  mov     rcx, [rsp+230h+PrincName]; ServerPrincName
0x18005cd17  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18005cd1d  mov     ebx, eax
0x18005cd1f  cmp     [rsp+230h+PrincName], 0
0x18005cd25  jz      short loc_18005CD32
0x18005cd27  lea     rcx, [rsp+230h+PrincName]; String
0x18005cd2c  call    cs:__imp_RpcStringFreeW
0x18005cd32  test    ebx, ebx
0x18005cd34  jz      short loc_18005CD3F
0x18005cd36  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterAuthInfo"
0x18005cd3d  jmp     short loc_18005CCC9
0x18005cd3f  lea     rax, ?staticRCMPublicRpcSecurityCallbackRemote@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote(void *,void *)
0x18005cd46  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005cd4b  mov     r13d, 4D2h
0x18005cd51  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005cd56  mov     r9d, r12d; Flags
0x18005cd59  xor     r8d, r8d; MgrEpv
0x18005cd5c  xor     edx, edx; MgrTypeUuid
0x18005cd5e  lea     rcx, qword_1800D03B0; IfSpec
0x18005cd65  call    cs:__imp_RpcServerRegisterIfEx
0x18005cd6b  mov     ebx, eax
0x18005cd6d  test    eax, eax
0x18005cd6f  jz      short loc_18005CD7D
0x18005cd71  lea     rdx, aErrorDRpcserve_3; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005cd78  jmp     loc_18005CCC9
0x18005cd7d  lea     rax, ?staticRCMPublicRpcSecurityCallbackRemote@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackRemote(void *,void *)
0x18005cd84  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005cd89  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005cd8e  mov     r9d, r12d; Flags
0x18005cd91  xor     r8d, r8d; MgrEpv
0x18005cd94  xor     edx, edx; MgrTypeUuid
0x18005cd96  lea     rcx, qword_1800CFF60; IfSpec
0x18005cd9d  call    cs:__imp_RpcServerRegisterIfEx
0x18005cda3  mov     ebx, eax
0x18005cda5  test    eax, eax
0x18005cda7  jz      short loc_18005CDB5
0x18005cda9  lea     rdx, aErrorDRpcserve_6; "Error %d RpcServerRegisterIf( RCMListen"...
0x18005cdb0  jmp     loc_18005CCC9
0x18005cdb5  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005cdbc  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005cdc1  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005cdc6  mov     r9d, r12d; Flags
0x18005cdc9  xor     r8d, r8d; MgrEpv
0x18005cdcc  xor     edx, edx; MgrTypeUuid
0x18005cdce  lea     rcx, qword_1800D1800; IfSpec
0x18005cdd5  call    cs:__imp_RpcServerRegisterIfEx
0x18005cddb  mov     ebx, eax
0x18005cddd  test    eax, eax
0x18005cddf  jz      short loc_18005CDED
0x18005cde1  lea     rdx, aErrorDRpcserve_1; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005cde8  jmp     loc_18005CCC9
0x18005cded  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18005cdf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18005cdf9  test    al, al
0x18005cdfb  jz      short loc_18005CE35
0x18005cdfd  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005ce04  mov     [rsp+230h+IfCallback], rax; IfCallback
0x18005ce09  mov     [rsp+230h+MaxCalls], r13d; MaxCalls
0x18005ce0e  mov     r9d, r12d; Flags
0x18005ce11  xor     r8d, r8d; MgrEpv
0x18005ce14  xor     edx, edx; MgrTypeUuid
0x18005ce16  lea     rcx, qword_1800CFCC0; IfSpec
0x18005ce1d  call    cs:__imp_RpcServerRegisterIfEx
0x18005ce23  mov     ebx, eax
0x18005ce25  test    eax, eax
0x18005ce27  jz      short loc_18005CE35
0x18005ce29  lea     rdx, aErrorDRpcserve_8; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005ce30  jmp     loc_18005CCC9
0x18005ce35  mov     rax, [rsp+230h+SecurityDescriptor]
0x18005ce3a  mov     [rsp+230h+var_1F8], rax
0x18005ce3f  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005ce46  mov     [rsp+230h+var_200], rax
0x18005ce4b  mov     dword ptr [rsp+230h+IfCallback], 0
0x18005ce53  mov     [rsp+230h+MaxCalls], r13d
0x18005ce58  mov     r9d, r12d
0x18005ce5b  xor     r8d, r8d
0x18005ce5e  xor     edx, edx
0x18005ce60  lea     rcx, qword_1800CFE30
0x18005ce67  call    cs:__imp_RpcServerRegisterIf3
0x18005ce6d  mov     ebx, eax
0x18005ce6f  test    eax, eax
0x18005ce71  jz      short loc_18005CE7F
0x18005ce73  lea     rdx, aErrorDRpcserve_5; "Error %d RpcServerRegisterIf( RCMPublic"...
0x18005ce7a  jmp     loc_18005CCC9
0x18005ce7f  mov     rax, [rsp+230h+hMem]
0x18005ce84  mov     [rsp+230h+var_1F8], rax
0x18005ce89  lea     rax, ?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z; CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)
0x18005ce90  mov     [rsp+230h+var_200], rax
0x18005ce95  mov     dword ptr [rsp+230h+IfCallback], 0
0x18005ce9d  mov     [rsp+230h+MaxCalls], r13d
0x18005cea2  mov     r9d, r12d
0x18005cea5  xor     r8d, r8d
0x18005cea8  xor     edx, edx
0x18005ceaa  lea     rcx, qword_1800D0CA0
0x18005ceb1  call    cs:__imp_RpcServerRegisterIf3
0x18005ceb7  mov     ebx, eax
0x18005ceb9  test    eax, eax
0x18005cebb  jnz     short loc_18005CE73
0x18005cebd  lea     r8d, [rax+1]; DontWait
0x18005cec1  mov     edx, r13d; MaxCalls
0x18005cec4  mov     ecx, r8d; MinimumCallThreads
0x18005cec7  call    cs:__imp_RpcServerListen
0x18005cecd  mov     ebx, eax
0x18005cecf  test    eax, eax
0x18005ced1  jz      short loc_18005CEE6
0x18005ced3  cmp     eax, 6B1h
0x18005ced8  jz      short loc_18005CEE6
0x18005ceda  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x18005cee1  jmp     loc_18005CCC9
0x18005cee6  mov     dword ptr [r14+638h], 1
0x18005cef1  xor     ebx, ebx
0x18005cef3  mov     rcx, [rsp+230h+hMem]; hMem
0x18005cef8  test    rcx, rcx
0x18005cefb  jz      short loc_18005CF03
0x18005cefd  call    cs:__imp_LocalFree
0x18005cf03  mov     rcx, [rsp+230h+SecurityDescriptor]; hMem
0x18005cf08  test    rcx, rcx
0x18005cf0b  jz      short loc_18005CF13
0x18005cf0d  call    cs:__imp_LocalFree
0x18005cf13  mov     rcx, [rsp+230h+StringSid]; hMem
0x18005cf18  test    rcx, rcx
0x18005cf1b  jz      short loc_18005CF23
0x18005cf1d  call    cs:__imp_LocalFree
0x18005cf23  test    rsi, rsi
0x18005cf26  jz      short loc_18005CF31
0x18005cf28  mov     rcx, rsi; Block
0x18005cf2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005cf30  nop
0x18005cf31  lea     rcx, [rsp+230h+var_1C8]
0x18005cf36  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cf3b  mov     eax, ebx
0x18005cf3d  mov     rcx, [rbp+130h+var_40]
0x18005cf44  xor     rcx, rsp; StackCookie
0x18005cf47  call    __security_check_cookie
0x18005cf4c  add     rsp, 208h
0x18005cf53  pop     r14
0x18005cf55  pop     r13
0x18005cf57  pop     r12
0x18005cf59  pop     rsi
0x18005cf5a  pop     rbx
0x18005cf5b  pop     rbp
0x18005cf5c  retn
  ... truncated ...
```
