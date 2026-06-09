# UnistoreService::OnStarting(void)

- ea: `0x180023700`
- end: `0x180023a8d`
- name: `?OnStarting@UnistoreService@@UEAAJXZ`
- size: `909`
- prototype: `__int64 __fastcall(UnistoreService *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800068f0`
- `0x180023700`
- `0x180023a94`
- `0x180066794`
- `0x180073930`
- `0x18007436c`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqW` at `0x180023799`
- `RPCRT4!RpcServerUseProtseqW` at `0x180023799`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800238ff`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800238ff`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002391c`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002391c`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800237ee`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800237ee`
- `RPCRT4!RpcBindingVectorFree` at `0x180023a6f`
- `RPCRT4!RpcBindingVectorFree` at `0x180023a82`
- `RPCRT4!RpcBindingVectorFree` at `0x180023a6f`
- `RPCRT4!RpcBindingVectorFree` at `0x180023a82`
- `RPCRT4!RpcServerInqBindings` at `0x18002380e`
- `RPCRT4!RpcServerInqBindings` at `0x18002380e`
- `RPCRT4!RpcEpRegisterW` at `0x18002382f`
- `RPCRT4!RpcEpRegisterW` at `0x18002382f`
- `RPCRT4!RpcStringFreeW` at `0x18002393b`
- `RPCRT4!RpcStringFreeW` at `0x18002393b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023860`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002386f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800238c9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800238d8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023982`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023995`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023860`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002386f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800238c9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800238d8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023982`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180023995`
- `UserDataPlatformHelperUtil!GetCombinedTransientObjectSecurityDescriptor` at `0x18002375c`
- `UserDataPlatformHelperUtil!GetCombinedTransientObjectSecurityDescriptor` at `0x18002375c`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800237a9`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800237a9`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18002372e`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18002372e`

## string_xrefs

- `0x18002387f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x1800238b1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x180023957`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x1800239a6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x1800239ca`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x180023a2d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x180023a51`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\servicemain.cpp`
- `0x180023755`: `UnistoreServiceOneCore\Interface`
- `0x18002374e`: `UnistoreServiceMobile\Interface`

## pseudocode

```c
__int64 __fastcall UnistoreService::OnStarting(UnistoreService *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int CombinedTransientObjectSecurityDescriptor; // eax
  int DefaultRpcSecurityDescriptor; // eax
  void *v5; // rbx
  RPC_STATUS v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  __int64 v12; // r9
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  __int64 v15; // r9
  RPC_BINDING_VECTOR *p_SecurityDescriptor; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+48h] [rbp-8h]
  void *SecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+88h] [rbp+38h] BYREF

  g_serviceShuttingDown = 0;
  g_fInProc = 1;
  g_fDoProtectionCheck = 1;
  v1 = UseEdgeBrowserComponentsForProcess();
  v2 = v1;
  if ( v1 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v1,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      105);
    return v2;
  }
  v19 = 0;
  CombinedTransientObjectSecurityDescriptor = GetCombinedTransientObjectSecurityDescriptor(
                                                L"UnistoreServiceOneCore\\Interface",
                                                L"UnistoreServiceMobile\\Interface",
                                                9,
                                                &v19);
  v2 = CombinedTransientObjectSecurityDescriptor;
  if ( CombinedTransientObjectSecurityDescriptor < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)CombinedTransientObjectSecurityDescriptor,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      117);
LABEL_36:
    if ( v19 )
      ((void (*)(void))FreeTransientObjectSecurityDescriptor)();
    return v2;
  }
  SecurityDescriptor = 0;
  DefaultRpcSecurityDescriptor = GetDefaultRpcSecurityDescriptor(&SecurityDescriptor);
  v2 = DefaultRpcSecurityDescriptor;
  if ( DefaultRpcSecurityDescriptor < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)DefaultRpcSecurityDescriptor,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      124);
    if ( SecurityDescriptor )
      ((void (*)(void))FreeTransientObjectSecurityDescriptor)();
    goto LABEL_36;
  }
  v5 = SecurityDescriptor;
  v6 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v12 = 132;
    goto LABEL_21;
  }
  if ( !(unsigned int)IsCommsSystemService() )
  {
    SecurityDescriptor = 0;
    p_SecurityDescriptor = (RPC_BINDING_VECTOR *)&SecurityDescriptor;
    LOBYTE(v17) = 1;
    v13 = RpcServerInqDefaultPrincNameW(0xAu, (RPC_WSTR *)&SecurityDescriptor);
    v7 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      v15 = 145;
    }
    else
    {
      v14 = RpcServerRegisterAuthInfoW((RPC_WSTR)SecurityDescriptor, 0xAu, 0, 0);
      v7 = v14;
      if ( !v14 )
      {
        if ( SecurityDescriptor )
          RpcStringFreeW((RPC_WSTR *)&SecurityDescriptor);
        goto LABEL_6;
      }
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v15 = 147;
    }
    Log_UnistoreHREvent_0(
      v7,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      v15);
    tlx::_UndoSolo__lambda_1d87ecedbc2b07177442c4d72e272f38___::__UndoSolo__lambda_1d87ecedbc2b07177442c4d72e272f38___(&p_SecurityDescriptor);
    goto LABEL_22;
  }
LABEL_6:
  v8 = RpcServerRegisterIf3(
         qword_1800C7720,
         0,
         0,
         33,
         1234,
         0,
         UniStoreSvcRpcSecurityCallback,
         v19,
         p_SecurityDescriptor,
         v17);
  v7 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    v12 = 158;
LABEL_21:
    Log_UnistoreHREvent_0(
      v7,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      v12);
    goto LABEL_22;
  }
  BYTE1(SecurityDescriptor) = 1;
  BindingVector = 0;
  v9 = RpcServerInqBindings(&BindingVector);
  v7 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    Log_UnistoreHREvent_0(
      v7,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      166);
    tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(&BindingVector);
  }
  else
  {
    v10 = RpcEpRegisterW(qword_1800C7720, BindingVector, 0, 0);
    v7 = v10;
    if ( !v10 )
    {
      BYTE1(SecurityDescriptor) = 0;
      if ( BindingVector )
      {
        p_SecurityDescriptor = BindingVector;
        RpcBindingVectorFree(&p_SecurityDescriptor);
      }
      tlx::_UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___::__UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___(&SecurityDescriptor);
      if ( v5 )
        FreeTransientObjectSecurityDescriptor(v5);
      if ( v19 )
        FreeTransientObjectSecurityDescriptor(v19);
      return 0;
    }
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    Log_UnistoreHREvent_0(
      v7,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\servicemain.cpp",
      168);
    if ( BindingVector )
    {
      p_SecurityDescriptor = BindingVector;
      RpcBindingVectorFree(&p_SecurityDescriptor);
    }
  }
  tlx::_UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___::__UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___(&SecurityDescriptor);
LABEL_22:
  if ( v5 )
    FreeTransientObjectSecurityDescriptor(v5);
  if ( v19 )
    FreeTransientObjectSecurityDescriptor(v19);
  return v7;
}

```

## disassembly

```asm
0x180023700  mov     [rsp-18h+arg_0], rbx
0x180023705  push    rbp
0x180023706  push    rdi
0x180023707  push    r14
0x180023709  mov     rbp, rsp
0x18002370c  sub     rsp, 50h
0x180023710  mov     r14d, 1
0x180023716  mov     cs:?g_serviceShuttingDown@@3HA, 0; int g_serviceShuttingDown
0x180023720  mov     cs:?g_fInProc@@3HA, r14d; int g_fInProc
0x180023727  mov     cs:?g_fDoProtectionCheck@@3HA, r14d; int g_fDoProtectionCheck
0x18002372e  call    cs:__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x180023734  mov     ebx, eax
0x180023736  test    eax, eax
0x180023738  js      loc_180023879
0x18002373e  lea     r9, [rbp+arg_10]
0x180023742  mov     [rbp+arg_10], 0
0x18002374a  lea     r8d, [r14+8]
0x18002374e  lea     rdx, aUnistoreservic; "UnistoreServiceMobile\\Interface"
0x180023755  lea     rcx, aUnistoreservic_0; "UnistoreServiceOneCore\\Interface"
0x18002375c  call    cs:__imp_GetCombinedTransientObjectSecurityDescriptor
0x180023762  mov     ebx, eax
0x180023764  test    eax, eax
0x180023766  js      loc_180023A4B
0x18002376c  lea     rcx, [rbp+SecurityDescriptor]; void **
0x180023770  mov     [rbp+SecurityDescriptor], 0
0x180023778  call    ?GetDefaultRpcSecurityDescriptor@@YAJPEAPEAX@Z; GetDefaultRpcSecurityDescriptor(void * *)
0x18002377d  mov     ebx, eax
0x18002377f  test    eax, eax
0x180023781  js      loc_1800239C4
0x180023787  mov     rbx, [rbp+SecurityDescriptor]
0x18002378b  lea     edx, [r14+9]; MaxCalls
0x18002378f  mov     r8, rbx; SecurityDescriptor
0x180023792  lea     rcx, ProtSeq; "ncalrpc"
0x180023799  call    cs:__imp_RpcServerUseProtseqW
0x18002379f  mov     edi, eax
0x1800237a1  test    eax, eax
0x1800237a3  jnz     loc_1800239E6
0x1800237a9  call    cs:__imp_IsCommsSystemService
0x1800237af  test    eax, eax
0x1800237b1  jz      loc_1800238E2
0x1800237b7  mov     rax, [rbp+arg_10]
0x1800237bb  lea     rcx, qword_1800C7720
0x1800237c2  mov     [rsp+50h+var_18], rax
0x1800237c7  mov     r9d, 21h ; '!'
0x1800237cd  lea     rax, ?UniStoreSvcRpcSecurityCallback@@YAJPEAPEAXPEAX@Z; UniStoreSvcRpcSecurityCallback(void * *,void *)
0x1800237d4  xor     r8d, r8d
0x1800237d7  mov     [rsp+50h+var_20], rax
0x1800237dc  xor     edx, edx
0x1800237de  mov     [rsp+50h+var_28], 0
0x1800237e6  mov     [rsp+50h+var_30], 4D2h
0x1800237ee  call    cs:__imp_RpcServerRegisterIf3
0x1800237f4  mov     edi, eax
0x1800237f6  test    eax, eax
0x1800237f8  jnz     loc_1800238A0
0x1800237fe  lea     rcx, [rbp+BindingVector]; BindingVector
0x180023802  mov     byte ptr [rbp+SecurityDescriptor+1], r14b
0x180023806  mov     [rbp+BindingVector], 0
0x18002380e  call    cs:__imp_RpcServerInqBindings
0x180023814  mov     edi, eax
0x180023816  test    eax, eax
0x180023818  jnz     loc_180023A1C
0x18002381e  mov     rdx, [rbp+BindingVector]; BindingVector
0x180023822  lea     rcx, qword_1800C7720; IfSpec
0x180023829  xor     r9d, r9d; Annotation
0x18002382c  xor     r8d, r8d; UuidVector
0x18002382f  call    cs:__imp_RpcEpRegisterW
0x180023835  mov     edi, eax
0x180023837  test    eax, eax
0x180023839  jnz     loc_180023946
0x18002383f  mov     byte ptr [rbp+SecurityDescriptor+1], al
0x180023842  mov     rax, [rbp+BindingVector]
0x180023846  test    rax, rax
0x180023849  jnz     loc_180023A7A
0x18002384f  lea     rcx, [rbp+SecurityDescriptor]
0x180023853  call    tlx___UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376_______UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___
0x180023858  test    rbx, rbx
0x18002385b  jz      short loc_180023866
0x18002385d  mov     rcx, rbx
0x180023860  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180023866  mov     rcx, [rbp+arg_10]
0x18002386a  test    rcx, rcx
0x18002386d  jz      short loc_180023875
0x18002386f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180023875  xor     eax, eax
0x180023877  jmp     short loc_180023892
0x180023879  mov     r9d, 69h ; 'i'
0x18002387f  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023886  mov     edx, r14d
0x180023889  mov     ecx, ebx
0x18002388b  call    Log_UnistoreHREvent_0
0x180023890  mov     eax, ebx
0x180023892  mov     rbx, [rsp+50h+arg_0]
0x180023897  add     rsp, 50h
0x18002389b  pop     r14
0x18002389d  pop     rdi
0x18002389e  pop     rbp
0x18002389f  retn
0x1800238a0  jle     short loc_1800238AB
0x1800238a2  movzx   edi, ax
0x1800238a5  or      edi, 80070000h
0x1800238ab  mov     r9d, 9Eh
0x1800238b1  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800238b8  xor     edx, edx
0x1800238ba  mov     ecx, edi
0x1800238bc  call    Log_UnistoreHREvent_0
0x1800238c1  test    rbx, rbx
0x1800238c4  jz      short loc_1800238CF
0x1800238c6  mov     rcx, rbx
0x1800238c9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800238cf  mov     rcx, [rbp+arg_10]
0x1800238d3  test    rcx, rcx
0x1800238d6  jz      short loc_1800238DE
0x1800238d8  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800238de  mov     eax, edi
0x1800238e0  jmp     short loc_180023892
0x1800238e2  lea     rax, [rbp+SecurityDescriptor]
0x1800238e6  mov     [rbp+SecurityDescriptor], 0
0x1800238ee  lea     rdx, [rbp+SecurityDescriptor]; PrincName
0x1800238f2  mov     [rbp+var_10], rax
0x1800238f6  mov     ecx, 0Ah; AuthnSvc
0x1800238fb  mov     byte ptr [rbp+var_8], r14b
0x1800238ff  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x180023905  mov     edi, eax
0x180023907  test    eax, eax
0x180023909  jnz     loc_1800239FC
0x18002390f  mov     rcx, [rbp+SecurityDescriptor]; ServerPrincName
0x180023913  lea     edx, [rax+0Ah]; AuthnSvc
0x180023916  xor     r9d, r9d; Arg
0x180023919  xor     r8d, r8d; GetKeyFn
0x18002391c  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180023922  mov     edi, eax
0x180023924  test    eax, eax
0x180023926  jnz     loc_180023A0F
0x18002392c  cmp     [rbp+SecurityDescriptor], 0
0x180023931  jz      loc_1800237B7
0x180023937  lea     rcx, [rbp+SecurityDescriptor]; String
0x18002393b  call    cs:__imp_RpcStringFreeW
0x180023941  jmp     loc_1800237B7
0x180023946  jle     short loc_180023951
0x180023948  movzx   edi, ax
0x18002394b  or      edi, 80070000h
0x180023951  mov     r9d, 0A8h
0x180023957  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002395e  xor     edx, edx
0x180023960  mov     ecx, edi
0x180023962  call    Log_UnistoreHREvent_0
0x180023967  mov     rax, [rbp+BindingVector]
0x18002396b  test    rax, rax
0x18002396e  jnz     loc_180023A67
0x180023974  lea     rcx, [rbp+SecurityDescriptor]
0x180023978  call    tlx___UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376_______UndoSolo__lambda_b489dbe7b3bf9e560a663f2948dbe376___
0x18002397d  jmp     loc_1800238C1
0x180023982  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180023988  mov     rcx, [rbp+arg_10]
0x18002398c  test    rcx, rcx
0x18002398f  jz      loc_180023890
0x180023995  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002399b  jmp     loc_180023890
0x1800239a0  mov     r9d, 93h
0x1800239a6  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800239ad  xor     edx, edx
0x1800239af  mov     ecx, edi
0x1800239b1  call    Log_UnistoreHREvent_0
0x1800239b6  lea     rcx, [rbp+var_10]
0x1800239ba  call    tlx___UndoSolo__lambda_1d87ecedbc2b07177442c4d72e272f38_______UndoSolo__lambda_1d87ecedbc2b07177442c4d72e272f38___
0x1800239bf  jmp     loc_1800238C1
0x1800239c4  mov     r9d, 7Ch ; '|'
0x1800239ca  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800239d1  mov     edx, r14d
0x1800239d4  mov     ecx, ebx
0x1800239d6  call    Log_UnistoreHREvent_0
0x1800239db  mov     rcx, [rbp+SecurityDescriptor]
0x1800239df  test    rcx, rcx
0x1800239e2  jz      short loc_180023988
0x1800239e4  jmp     short loc_180023982
0x1800239e6  jle     short loc_1800239F1
0x1800239e8  movzx   edi, ax
0x1800239eb  or      edi, 80070000h
0x1800239f1  mov     r9d, 84h
0x1800239f7  jmp     loc_1800238B1
0x1800239fc  jle     short loc_180023A07
0x1800239fe  movzx   edi, ax
0x180023a01  or      edi, 80070000h
0x180023a07  mov     r9d, 91h
0x180023a0d  jmp     short loc_1800239A6
0x180023a0f  jle     short loc_1800239A0
0x180023a11  movzx   edi, ax
0x180023a14  or      edi, 80070000h
0x180023a1a  jmp     short loc_1800239A0
0x180023a1c  jle     short loc_180023A27
0x180023a1e  movzx   edi, ax
0x180023a21  or      edi, 80070000h
0x180023a27  mov     r9d, 0A6h
0x180023a2d  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023a34  xor     edx, edx
0x180023a36  mov     ecx, edi
0x180023a38  call    Log_UnistoreHREvent_0
0x180023a3d  lea     rcx, [rbp+BindingVector]
0x180023a41  call    ?_Delete@?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(void)
0x180023a46  jmp     loc_180023974
0x180023a4b  mov     r9d, 75h ; 'u'
0x180023a51  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023a58  mov     edx, r14d
0x180023a5b  mov     ecx, ebx
0x180023a5d  call    Log_UnistoreHREvent_0
0x180023a62  jmp     loc_180023988
0x180023a67  lea     rcx, [rbp+var_10]; BindingVector
0x180023a6b  mov     [rbp+var_10], rax
0x180023a6f  call    cs:__imp_RpcBindingVectorFree
0x180023a75  jmp     loc_180023974
0x180023a7a  lea     rcx, [rbp+var_10]; BindingVector
0x180023a7e  mov     [rbp+var_10], rax
0x180023a82  call    cs:__imp_RpcBindingVectorFree
0x180023a88  jmp     loc_18002384F
```
