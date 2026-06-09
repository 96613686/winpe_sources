# BioTrustlet::ServerBind(void)

- ea: `0x1800b5134`
- end: `0x1800b5326`
- name: `?ServerBind@BioTrustlet@@QEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(BioTrustlet *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045044`
- `0x180071de8`

## callees

- `0x18003876c`
- `0x18005388c`
- `0x180068f60`
- `0x1800b5134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b515e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b515e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b52c9`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b52c9`
- `RPCRT4!RpcEpResolveBinding` at `0x1800b5239`
- `RPCRT4!RpcEpResolveBinding` at `0x1800b5239`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b51e9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b51e9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b51a2`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b51a2`
- `RPCRT4!RpcBindingFree` at `0x1800b5273`
- `RPCRT4!RpcBindingFree` at `0x1800b5273`
- `RPCRT4!RpcStringFreeW` at `0x1800b5220`
- `RPCRT4!RpcStringFreeW` at `0x1800b52f5`
- `RPCRT4!RpcStringFreeW` at `0x1800b5220`
- `RPCRT4!RpcStringFreeW` at `0x1800b52f5`

## string_xrefs

- `0x1800b51c5`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800b5208`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800b525d`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`

## pseudocode

```c
__int64 __fastcall BioTrustlet::ServerBind(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  int Ptr; // eax
  RPC_STATUS v4; // eax
  signed int v5; // ebx
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  __int64 v8; // rdx
  RPC_STATUS v9; // eax
  int Options; // [rsp+20h] [rbp-50h]
  RPC_WSTR String; // [rsp+40h] [rbp-30h] BYREF
  RTL_SRWLOCK *v13; // [rsp+48h] [rbp-28h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = this + 6;
  AcquireSRWLockExclusive(this + 6);
  Ptr = (int)this[7].Ptr;
  v13 = v1;
  if ( Ptr )
  {
    LODWORD(this[7].Ptr) = Ptr + 1;
LABEL_27:
    v5 = 0;
    goto LABEL_28;
  }
  String = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v5 = v4;
  if ( !v4 )
  {
    v6 = RpcBindingFromStringBindingW(String, &g_bioIsoTrustletIfHandle);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36E,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
          (const char *)(unsigned int)v5,
          Options);
      goto LABEL_13;
    }
    v7 = RpcEpResolveBinding(g_bioIsoTrustletIfHandle, qword_1800D7CB0);
    v5 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_20;
      v8 = 892;
    }
    else
    {
      SecurityQOS.Version = 1;
      SecurityQOS.Capabilities = 1;
      SecurityQOS.ImpersonationType = 3;
      SecurityQOS.IdentityTracking = 1;
      v9 = RpcBindingSetAuthInfoExW(
             g_bioIsoTrustletIfHandle,
             (RPC_WSTR)L"NT Authority\\SYSTEM",
             6u,
             0xAu,
             0,
             0,
             &SecurityQOS);
      v5 = v9;
      if ( !v9 )
      {
        ++LODWORD(this[7].Ptr);
        RpcStringFreeW(&String);
        goto LABEL_27;
      }
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_20;
      v8 = 913;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
      (const char *)(unsigned int)v5,
      Options);
LABEL_20:
    RpcBindingFree(&g_bioIsoTrustletIfHandle);
LABEL_13:
    RpcStringFreeW(&String);
    goto LABEL_28;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
      (const char *)(unsigned int)v5,
      Options);
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b5134  mov     [rsp-8+arg_8], rbx
0x1800b5139  mov     [rsp-8+arg_10], rdi
0x1800b513e  push    rbp
0x1800b513f  mov     rbp, rsp
0x1800b5142  sub     rsp, 70h
0x1800b5146  mov     rax, cs:__security_cookie
0x1800b514d  xor     rax, rsp
0x1800b5150  mov     [rbp+var_10], rax
0x1800b5154  lea     rbx, [rcx+30h]
0x1800b5158  mov     rdi, rcx
0x1800b515b  mov     rcx, rbx; SRWLock
0x1800b515e  call    cs:__imp_AcquireSRWLockExclusive
0x1800b5164  mov     eax, [rdi+38h]
0x1800b5167  mov     [rbp+var_28], rbx
0x1800b516b  test    eax, eax
0x1800b516d  jz      short loc_1800B5179
0x1800b516f  inc     eax
0x1800b5171  mov     [rdi+38h], eax
0x1800b5174  jmp     loc_1800B52FB
0x1800b5179  lea     rax, [rbp+String]
0x1800b517d  mov     [rbp+String], 0
0x1800b5185  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800b518a  lea     rdx, ProtSeq; "ncalrpc"
0x1800b5191  xor     r9d, r9d; Endpoint
0x1800b5194  mov     [rsp+70h+Options], 0; int
0x1800b519d  xor     r8d, r8d; NetworkAddr
0x1800b51a0  xor     ecx, ecx; ObjUuid
0x1800b51a2  call    cs:__imp_RpcStringBindingComposeW
0x1800b51a8  mov     ebx, eax
0x1800b51aa  test    eax, eax
0x1800b51ac  jz      short loc_1800B51DE
0x1800b51ae  jle     short loc_1800B51B9
0x1800b51b0  movzx   ebx, ax
0x1800b51b3  or      ebx, 80070000h
0x1800b51b9  test    ebx, ebx
0x1800b51bb  jns     loc_1800B52FD
0x1800b51c1  mov     rcx, [rbp+8]; this
0x1800b51c5  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800b51cc  mov     r9d, ebx; char *
0x1800b51cf  mov     edx, 35Fh; void *
0x1800b51d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b51d9  jmp     loc_1800B52FD
0x1800b51de  mov     rcx, [rbp+String]; StringBinding
0x1800b51e2  lea     rdx, g_bioIsoTrustletIfHandle; Binding
0x1800b51e9  call    cs:__imp_RpcBindingFromStringBindingW
0x1800b51ef  mov     ebx, eax
0x1800b51f1  test    eax, eax
0x1800b51f3  jz      short loc_1800B522B
0x1800b51f5  jle     short loc_1800B5200
0x1800b51f7  movzx   ebx, ax
0x1800b51fa  or      ebx, 80070000h
0x1800b5200  test    ebx, ebx
0x1800b5202  jns     short loc_1800B521C
0x1800b5204  mov     rcx, [rbp+8]; this
0x1800b5208  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800b520f  mov     r9d, ebx; char *
0x1800b5212  mov     edx, 36Eh; void *
0x1800b5217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b521c  lea     rcx, [rbp+String]; String
0x1800b5220  call    cs:__imp_RpcStringFreeW
0x1800b5226  jmp     loc_1800B52FD
0x1800b522b  mov     rcx, cs:g_bioIsoTrustletIfHandle; Binding
0x1800b5232  lea     rdx, qword_1800D7CB0; IfSpec
0x1800b5239  call    cs:__imp_RpcEpResolveBinding
0x1800b523f  mov     ebx, eax
0x1800b5241  test    eax, eax
0x1800b5243  jz      short loc_1800B527B
0x1800b5245  jle     short loc_1800B5250
0x1800b5247  movzx   ebx, ax
0x1800b524a  or      ebx, 80070000h
0x1800b5250  test    ebx, ebx
0x1800b5252  jns     short loc_1800B526C
0x1800b5254  mov     edx, 37Ch; void *
0x1800b5259  mov     rcx, [rbp+8]; this
0x1800b525d  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800b5264  mov     r9d, ebx; char *
0x1800b5267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b526c  lea     rcx, g_bioIsoTrustletIfHandle; Binding
0x1800b5273  call    cs:__imp_RpcBindingFree
0x1800b5279  jmp     short loc_1800B521C
0x1800b527b  mov     rcx, cs:g_bioIsoTrustletIfHandle; Binding
0x1800b5282  lea     rax, [rbp+var_20]
0x1800b5286  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800b528b  lea     rdx, ServerPrincName; "NT Authority\\SYSTEM"
0x1800b5292  mov     r9d, 0Ah; AuthnSvc
0x1800b5298  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x1800b52a0  mov     [rbp+var_20.Version], 1
0x1800b52a7  mov     [rbp+var_20.Capabilities], 1
0x1800b52ae  mov     [rbp+var_20.ImpersonationType], 3
0x1800b52b5  lea     r8d, [r9-4]; AuthnLevel
0x1800b52b9  mov     [rbp+var_20.IdentityTracking], 1
0x1800b52c0  mov     [rsp+70h+Options], 0; AuthIdentity
0x1800b52c9  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800b52cf  mov     ebx, eax
0x1800b52d1  test    eax, eax
0x1800b52d3  jz      short loc_1800B52EE
0x1800b52d5  jle     short loc_1800B52E0
0x1800b52d7  movzx   ebx, ax
0x1800b52da  or      ebx, 80070000h
0x1800b52e0  test    ebx, ebx
0x1800b52e2  jns     short loc_1800B526C
0x1800b52e4  mov     edx, 391h
0x1800b52e9  jmp     loc_1800B5259
0x1800b52ee  inc     dword ptr [rdi+38h]
0x1800b52f1  lea     rcx, [rbp+String]; String
0x1800b52f5  call    cs:__imp_RpcStringFreeW
0x1800b52fb  xor     ebx, ebx
0x1800b52fd  lea     rcx, [rbp+var_28]
0x1800b5301  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b5306  mov     eax, ebx
0x1800b5308  mov     rcx, [rbp+var_10]
0x1800b530c  xor     rcx, rsp; StackCookie
0x1800b530f  call    __security_check_cookie
0x1800b5314  lea     r11, [rsp+70h+var_s0]
0x1800b5319  mov     rbx, [r11+18h]
0x1800b531d  mov     rdi, [r11+20h]
0x1800b5321  mov     rsp, r11
0x1800b5324  pop     rbp
0x1800b5325  retn
```
