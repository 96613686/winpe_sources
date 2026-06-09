# RegisterEndpoint

- ea: `0x18002d704`
- end: `0x18002daac`
- name: `RegisterEndpoint`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007e9c8`

## callees

- `0x180008f0c`
- `0x18002d6dc`
- `0x18002d704`
- `0x18002dab4`
- `0x18007be90`
- `0x180084314`
- `0x18009d0e0`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18002d935`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18002d935`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002d9ad`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002d9ad`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002d7c8`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002d7c8`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18002d963`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18002d963`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002d85e`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002d85e`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002d8d2`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002d8d2`
- `RPCRT4!RpcBindingVectorFree` at `0x18002da62`
- `RPCRT4!RpcBindingVectorFree` at `0x18002da62`
- `RPCRT4!RpcEpRegisterW` at `0x18002da2f`
- `RPCRT4!RpcEpRegisterW` at `0x18002da2f`
- `RPCRT4!RpcServerInqBindings` at `0x18002d9e3`
- `RPCRT4!RpcServerInqBindings` at `0x18002d9e3`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18002d758`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18002d758`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d788`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d832`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d90e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d928`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002da70`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002da80`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d788`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d832`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d90e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002d928`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002da70`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002da80`

## string_xrefs

- `0x18002d751`: `UserDataServiceOneCore\Interface`
- `0x18002d76e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`
- `0x18002d815`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`
- `0x18002d8f6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`
- `0x18002d980`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`
- `0x18002da00`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\dll\datamodelserviceendpoint.cpp`
- `0x18002d866`: `UserDataModelService`

## pseudocode

```c
__int64 __fastcall RegisterEndpoint(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  int DefaultRpcSecurityDescriptor; // ebx
  __int64 v6; // r9
  int v8; // eax
  __int64 v9; // r9
  void *v10; // rbx
  RPC_STATUS v11; // eax
  unsigned int v12; // edi
  RPC_STATUS v13; // eax
  __int64 v14; // r9
  RPC_STATUS v15; // eax
  RPC_STATUS v16; // eax
  __int64 v17; // r9
  RPC_STATUS v18; // eax
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  void *SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp-B0h] BYREF
  RPC_IF_HANDLE *p_IfSpec; // [rsp+58h] [rbp-A8h] BYREF
  char v23; // [rsp+60h] [rbp-A0h]
  RPC_IF_HANDLE IfSpec; // [rsp+70h] [rbp-90h] BYREF
  void **p_SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+88h] [rbp-78h]
  unsigned __int16 Endpoint[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[26]; // [rsp+A0h] [rbp-60h]
  _BYTE v29[486]; // [rsp+BAh] [rbp-46h] BYREF

  v19 = 0;
  IfSpec = qword_18012FD60;
  v4 = QueryTransientObjectSecurityDescriptor(9, L"UserDataServiceOneCore\\Interface", &v19);
  if ( v4 < 0 )
  {
    DefaultRpcSecurityDescriptor = v4 | 0x10000000;
    v6 = 19;
LABEL_3:
    Log_HREvent(
      (unsigned int)DefaultRpcSecurityDescriptor,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
      v6);
LABEL_4:
    if ( v19 )
      FreeTransientObjectSecurityDescriptor(v19);
    return (unsigned int)DefaultRpcSecurityDescriptor;
  }
  v8 = RpcServerRegisterIf3(IfSpec, 0, 0, 41, 1234, 0, 0, v19);
  DefaultRpcSecurityDescriptor = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      DefaultRpcSecurityDescriptor = (unsigned __int16)v8 | 0x80070000;
    v6 = 32;
    goto LABEL_3;
  }
  v23 = 1;
  p_IfSpec = &IfSpec;
  SecurityDescriptor = 0;
  DefaultRpcSecurityDescriptor = GetDefaultRpcSecurityDescriptor(&SecurityDescriptor);
  if ( DefaultRpcSecurityDescriptor < 0 )
  {
    v9 = 43;
LABEL_13:
    Log_HREvent(
      (unsigned int)DefaultRpcSecurityDescriptor,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
      v9);
    if ( SecurityDescriptor )
      FreeTransientObjectSecurityDescriptor(SecurityDescriptor);
    tlx::_UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___::__UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___(&p_IfSpec);
    goto LABEL_4;
  }
  if ( a3 )
  {
    *(_OWORD *)Endpoint = *(_OWORD *)L"UserDataModelService";
    *(_OWORD *)v28 = *(_OWORD *)L"ModelService";
    *(_OWORD *)&v28[10] = *(_OWORD *)L"Service";
    memset_0(v29, 0, 0x1DEu);
    DefaultRpcSecurityDescriptor = StringCchCopyW(Endpoint, 0x104u, a3);
    if ( DefaultRpcSecurityDescriptor < 0 )
    {
      v9 = 58;
      goto LABEL_13;
    }
    v10 = SecurityDescriptor;
    v11 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, Endpoint, SecurityDescriptor);
  }
  else
  {
    v10 = SecurityDescriptor;
    v11 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  }
  v12 = v11;
  if ( v11 != 1740 && v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    Log_HREvent(
      v12,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
      69);
    goto LABEL_26;
  }
  if ( !(unsigned int)IsCommsSystemService() )
  {
    SecurityDescriptor = 0;
    p_SecurityDescriptor = &SecurityDescriptor;
    v26 = 1;
    v13 = RpcServerInqDefaultPrincNameW(0xAu, (RPC_WSTR *)&SecurityDescriptor);
    v12 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      v14 = 83;
LABEL_36:
      Log_HREvent(
        v12,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
        v14);
      tlx::_UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___::__UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___(&p_SecurityDescriptor);
LABEL_26:
      if ( v10 )
        FreeTransientObjectSecurityDescriptor(v10);
      tlx::_UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___::__UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___(&p_IfSpec);
      if ( v19 )
        FreeTransientObjectSecurityDescriptor(v19);
      return v12;
    }
    v15 = RpcServerRegisterAuthInfoW((RPC_WSTR)SecurityDescriptor, 0xAu, 0, 0);
    v12 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v12 = (unsigned __int16)v15 | 0x80070000;
      v14 = 85;
      goto LABEL_36;
    }
    tlx::_UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___::__UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___(&p_SecurityDescriptor);
  }
  BindingVector = 0;
  v16 = RpcServerInqBindings(&BindingVector);
  v12 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    v17 = 90;
LABEL_46:
    Log_HREvent(
      v12,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\dll\\datamodelserviceendpoint.cpp",
      v17);
    tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(&BindingVector);
    goto LABEL_26;
  }
  v18 = RpcEpRegisterW(IfSpec, BindingVector, 0, 0);
  v12 = v18;
  if ( v18 )
  {
    if ( v18 > 0 )
      v12 = (unsigned __int16)v18 | 0x80070000;
    v17 = 91;
    goto LABEL_46;
  }
  if ( BindingVector )
  {
    SecurityDescriptor = BindingVector;
    RpcBindingVectorFree((RPC_BINDING_VECTOR **)&SecurityDescriptor);
  }
  if ( v10 )
    FreeTransientObjectSecurityDescriptor(v10);
  if ( v19 )
    FreeTransientObjectSecurityDescriptor(v19);
  return 0;
}

```

## disassembly

```asm
0x18002d704  mov     [rsp-8+arg_0], rbx
0x18002d709  mov     [rsp-8+arg_8], rdi
0x18002d70e  push    rbp
0x18002d70f  lea     rbp, [rsp-1B0h]
0x18002d717  sub     rsp, 2B0h
0x18002d71e  mov     rax, cs:__security_cookie
0x18002d725  xor     rax, rsp
0x18002d728  mov     [rbp+1B0h+var_10], rax
0x18002d72f  mov     rdi, r8
0x18002d732  mov     [rsp+2B0h+var_270], 0
0x18002d73b  lea     rax, qword_18012FD60
0x18002d742  mov     ecx, 9
0x18002d747  lea     r8, [rsp+2B0h+var_270]
0x18002d74c  mov     [rsp+2B0h+IfSpec], rax
0x18002d751  lea     rdx, aUserdataservic_0; "UserDataServiceOneCore\\Interface"
0x18002d758  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18002d75e  mov     ebx, eax
0x18002d760  test    eax, eax
0x18002d762  jns     short loc_18002D795
0x18002d764  bts     ebx, 1Ch
0x18002d768  mov     r9d, 13h
0x18002d76e  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d775  xor     edx, edx
0x18002d777  mov     ecx, ebx
0x18002d779  call    Log_HREvent
0x18002d77e  mov     rcx, [rsp+2B0h+var_270]
0x18002d783  test    rcx, rcx
0x18002d786  jz      short loc_18002D78E
0x18002d788  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002d78e  mov     eax, ebx
0x18002d790  jmp     loc_18002DA88
0x18002d795  mov     rax, [rsp+2B0h+var_270]
0x18002d79a  mov     r9d, 29h ; ')'
0x18002d7a0  mov     rcx, [rsp+2B0h+IfSpec]
0x18002d7a5  xor     r8d, r8d
0x18002d7a8  mov     [rsp+2B0h+var_278], rax
0x18002d7ad  xor     edx, edx
0x18002d7af  mov     [rsp+2B0h+var_280], 0
0x18002d7b8  mov     [rsp+2B0h+var_288], 0
0x18002d7c0  mov     [rsp+2B0h+var_290], 4D2h
0x18002d7c8  call    cs:__imp_RpcServerRegisterIf3
0x18002d7ce  mov     ebx, eax
0x18002d7d0  test    eax, eax
0x18002d7d2  jz      short loc_18002D7E7
0x18002d7d4  jle     short loc_18002D7DF
0x18002d7d6  movzx   ebx, ax
0x18002d7d9  or      ebx, 80070000h
0x18002d7df  mov     r9d, 20h ; ' '
0x18002d7e5  jmp     short loc_18002D76E
0x18002d7e7  lea     rax, [rsp+2B0h+IfSpec]
0x18002d7ec  mov     [rsp+2B0h+var_250], 1
0x18002d7f1  lea     rcx, [rsp+2B0h+SecurityDescriptor]; void **
0x18002d7f6  mov     [rsp+2B0h+var_258], rax
0x18002d7fb  mov     [rsp+2B0h+SecurityDescriptor], 0
0x18002d804  call    ?GetDefaultRpcSecurityDescriptor@@YAJPEAPEAX@Z; GetDefaultRpcSecurityDescriptor(void * *)
0x18002d809  mov     ebx, eax
0x18002d80b  test    eax, eax
0x18002d80d  jns     short loc_18002D847
0x18002d80f  mov     r9d, 2Bh ; '+'
0x18002d815  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d81c  mov     edx, 1
0x18002d821  mov     ecx, ebx
0x18002d823  call    Log_HREvent
0x18002d828  mov     rcx, [rsp+2B0h+SecurityDescriptor]
0x18002d82d  test    rcx, rcx
0x18002d830  jz      short loc_18002D838
0x18002d832  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002d838  lea     rcx, [rsp+2B0h+var_258]
0x18002d83d  call    tlx___UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7_______UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___
0x18002d842  jmp     loc_18002D77E
0x18002d847  test    rdi, rdi
0x18002d84a  jnz     short loc_18002D866
0x18002d84c  mov     rbx, [rsp+2B0h+SecurityDescriptor]
0x18002d851  lea     edx, [rdi+0Ah]; MaxCalls
0x18002d854  mov     r8, rbx; SecurityDescriptor
0x18002d857  lea     rcx, Protseq; "ncalrpc"
0x18002d85e  call    cs:__imp_RpcServerUseProtseqW
0x18002d864  jmp     short loc_18002D8D8
0x18002d866  movups  xmm0, xmmword ptr cs:aUserdatamodels; "UserDataModelService"
0x18002d86d  xor     edx, edx; Val
0x18002d86f  mov     r8d, 1DEh; Size
0x18002d875  movups  xmm1, xmmword ptr cs:aUserdatamodels+10h; "ModelService"
0x18002d87c  lea     rcx, [rbp+1B0h+var_1F6]; void *
0x18002d880  movaps  xmmword ptr [rbp+1B0h+Endpoint], xmm0
0x18002d884  movups  xmm0, xmmword ptr cs:aUserdatamodels+1Ah; "Service"
0x18002d88b  movaps  xmmword ptr [rbp+1B0h+var_210], xmm1
0x18002d88f  movups  xmmword ptr [rbp+1B0h+var_210+0Ah], xmm0
0x18002d893  call    memset_0
0x18002d898  mov     r8, rdi; unsigned __int16 *
0x18002d89b  lea     rcx, [rbp+1B0h+Endpoint]; unsigned __int16 *
0x18002d89f  mov     edx, 104h; unsigned __int64
0x18002d8a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d8a9  mov     ebx, eax
0x18002d8ab  test    eax, eax
0x18002d8ad  jns     short loc_18002D8BA
0x18002d8af  mov     r9d, 3Ah ; ':'
0x18002d8b5  jmp     loc_18002D815
0x18002d8ba  mov     rbx, [rsp+2B0h+SecurityDescriptor]
0x18002d8bf  lea     r8, [rbp+1B0h+Endpoint]; Endpoint
0x18002d8c3  mov     r9, rbx; SecurityDescriptor
0x18002d8c6  lea     rcx, Protseq; "ncalrpc"
0x18002d8cd  mov     edx, 0Ah; MaxCalls
0x18002d8d2  call    cs:__imp_RpcServerUseProtseqEpW
0x18002d8d8  mov     edi, eax
0x18002d8da  cmp     eax, 6CCh
0x18002d8df  jz      short loc_18002D935
0x18002d8e1  test    eax, eax
0x18002d8e3  jz      short loc_18002D935
0x18002d8e5  jle     short loc_18002D8F0
0x18002d8e7  movzx   edi, di
0x18002d8ea  or      edi, 80070000h
0x18002d8f0  mov     r9d, 45h ; 'E'
0x18002d8f6  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d8fd  xor     edx, edx
0x18002d8ff  mov     ecx, edi
0x18002d901  call    Log_HREvent
0x18002d906  test    rbx, rbx
0x18002d909  jz      short loc_18002D914
0x18002d90b  mov     rcx, rbx
0x18002d90e  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002d914  lea     rcx, [rsp+2B0h+var_258]
0x18002d919  call    tlx___UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7_______UndoSolo__lambda_0f8a791acc9cbd73333e7d015d7531b7___
0x18002d91e  mov     rcx, [rsp+2B0h+var_270]
0x18002d923  test    rcx, rcx
0x18002d926  jz      short loc_18002D92E
0x18002d928  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002d92e  mov     eax, edi
0x18002d930  jmp     loc_18002DA88
0x18002d935  call    cs:__imp_IsCommsSystemService
0x18002d93b  test    eax, eax
0x18002d93d  jnz     loc_18002D9D5
0x18002d943  lea     rax, [rsp+2B0h+SecurityDescriptor]
0x18002d948  mov     [rsp+2B0h+SecurityDescriptor], 0
0x18002d951  lea     rdx, [rsp+2B0h+SecurityDescriptor]; PrincName
0x18002d956  mov     [rbp+1B0h+var_230], rax
0x18002d95a  mov     ecx, 0Ah; AuthnSvc
0x18002d95f  mov     [rbp+1B0h+var_228], 1
0x18002d963  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18002d969  mov     edi, eax
0x18002d96b  test    eax, eax
0x18002d96d  jz      short loc_18002D99E
0x18002d96f  jle     short loc_18002D97A
0x18002d971  movzx   edi, ax
0x18002d974  or      edi, 80070000h
0x18002d97a  mov     r9d, 53h ; 'S'
0x18002d980  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d987  xor     edx, edx
0x18002d989  mov     ecx, edi
0x18002d98b  call    Log_HREvent
0x18002d990  lea     rcx, [rbp+1B0h+var_230]
0x18002d994  call    tlx___UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32_______UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___
0x18002d999  jmp     loc_18002D906
0x18002d99e  mov     rcx, [rsp+2B0h+SecurityDescriptor]; ServerPrincName
0x18002d9a3  xor     r9d, r9d; Arg
0x18002d9a6  xor     r8d, r8d; GetKeyFn
0x18002d9a9  lea     edx, [r9+0Ah]; AuthnSvc
0x18002d9ad  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18002d9b3  mov     edi, eax
0x18002d9b5  test    eax, eax
0x18002d9b7  jz      short loc_18002D9CC
0x18002d9b9  jle     short loc_18002D9C4
0x18002d9bb  movzx   edi, ax
0x18002d9be  or      edi, 80070000h
0x18002d9c4  mov     r9d, 55h ; 'U'
0x18002d9ca  jmp     short loc_18002D980
0x18002d9cc  lea     rcx, [rbp+1B0h+var_230]
0x18002d9d0  call    tlx___UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32_______UndoSolo__lambda_0a0e32e6e2eafada895adcb128aa4a32___
0x18002d9d5  lea     rcx, [rsp+2B0h+BindingVector]; BindingVector
0x18002d9da  mov     [rsp+2B0h+BindingVector], 0
0x18002d9e3  call    cs:__imp_RpcServerInqBindings
0x18002d9e9  mov     edi, eax
0x18002d9eb  test    eax, eax
0x18002d9ed  jz      short loc_18002DA1F
0x18002d9ef  jle     short loc_18002D9FA
0x18002d9f1  movzx   edi, ax
0x18002d9f4  or      edi, 80070000h
0x18002d9fa  mov     r9d, 5Ah ; 'Z'
0x18002da00  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002da07  xor     edx, edx
0x18002da09  mov     ecx, edi
0x18002da0b  call    Log_HREvent
0x18002da10  lea     rcx, [rsp+2B0h+BindingVector]
0x18002da15  call    ?_Delete@?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(void)
0x18002da1a  jmp     loc_18002D906
0x18002da1f  mov     rdx, [rsp+2B0h+BindingVector]; BindingVector
0x18002da24  xor     r9d, r9d; Annotation
0x18002da27  mov     rcx, [rsp+2B0h+IfSpec]; IfSpec
0x18002da2c  xor     r8d, r8d; UuidVector
0x18002da2f  call    cs:__imp_RpcEpRegisterW
0x18002da35  mov     edi, eax
0x18002da37  test    eax, eax
0x18002da39  jz      short loc_18002DA4E
0x18002da3b  jle     short loc_18002DA46
0x18002da3d  movzx   edi, ax
0x18002da40  or      edi, 80070000h
0x18002da46  mov     r9d, 5Bh ; '['
0x18002da4c  jmp     short loc_18002DA00
0x18002da4e  mov     rax, [rsp+2B0h+BindingVector]
0x18002da53  test    rax, rax
0x18002da56  jz      short loc_18002DA68
0x18002da58  lea     rcx, [rsp+2B0h+SecurityDescriptor]; BindingVector
0x18002da5d  mov     [rsp+2B0h+SecurityDescriptor], rax
0x18002da62  call    cs:__imp_RpcBindingVectorFree
0x18002da68  test    rbx, rbx
0x18002da6b  jz      short loc_18002DA76
0x18002da6d  mov     rcx, rbx
0x18002da70  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002da76  mov     rcx, [rsp+2B0h+var_270]
0x18002da7b  test    rcx, rcx
0x18002da7e  jz      short loc_18002DA86
0x18002da80  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002da86  xor     eax, eax
0x18002da88  mov     rcx, [rbp+1B0h+var_10]
0x18002da8f  xor     rcx, rsp; StackCookie
0x18002da92  call    __security_check_cookie
0x18002da97  lea     r11, [rsp+2B0h+var_s0]
0x18002da9f  mov     rbx, [r11+10h]
0x18002daa3  mov     rdi, [r11+18h]
0x18002daa7  mov     rsp, r11
0x18002daaa  pop     rbp
0x18002daab  retn
```
