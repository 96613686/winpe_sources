# GetBindingHandle(void * *)

- ea: `0x180075a3c`
- end: `0x180075c77`
- name: `?GetBindingHandle@@YAJPEAPEAX@Z`
- size: `571`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800390c0`

## callees

- `0x1800068f0`
- `0x1800678b4`
- `0x180075a3c`
- `0x180075c80`
- `0x180078a34`
- `0x18007c318`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180075aad`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180075aad`
- `RPCRT4!RpcStringBindingComposeW` at `0x180075a87`
- `RPCRT4!RpcStringBindingComposeW` at `0x180075a87`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180075bf6`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180075bf6`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075b34`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075c39`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075c59`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075b34`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075c39`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180075c59`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180075aff`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180075aff`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x180075b5a`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x180075b5a`

## string_xrefs

- `0x180075aca`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180075b15`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180075b79`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180075c13`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180075af3`: `UnistoreServiceOneCore\Server`

## pseudocode

```c
__int64 __fastcall GetBindingHandle(RPC_BINDING_HANDLE *Binding)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  RPC_STATUS v5; // eax
  _QWORD *v6; // rax
  int TransientObjectSecurityDescriptor; // eax
  void *v8; // rbx
  __int64 v9; // rdx
  int token_information; // eax
  RPC_BINDING_HANDLE v11; // rcx
  RPC_STATUS v12; // eax
  unsigned int v13; // edi
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h]
  __int128 v17; // [rsp+60h] [rbp-20h]
  __int64 v18; // [rsp+70h] [rbp-10h]
  __int64 v19; // [rsp+A8h] [rbp+28h] BYREF
  RPC_WSTR StringBinding; // [rsp+B0h] [rbp+30h] BYREF
  void *Block; // [rsp+B8h] [rbp+38h] BYREF

  StringBinding = 0;
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void _CloseBindString(unsigned short *),0>::_Delete(&StringBinding);
  StringBinding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = 44;
LABEL_9:
    Log_UnistoreHREvent_0(
      v3,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      v4);
    goto LABEL_33;
  }
  v5 = RpcBindingFromStringBindingW(StringBinding, Binding);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v4 = 46;
    goto LABEL_9;
  }
  v19 = 0;
  v6 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&v19);
  TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(9, L"UnistoreServiceOneCore\\Server", v6);
  v3 = TransientObjectSecurityDescriptor | 0x10000000;
  if ( TransientObjectSecurityDescriptor < 0 )
  {
    Log_UnistoreHREvent_0(
      v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      55);
LABEL_12:
    if ( v19 )
      FreeTransientObjectSecurityDescriptor(v19);
    goto LABEL_33;
  }
  v8 = 0;
  v18 = 0;
  SecurityQOS = 0;
  Block = 0;
  v16 = 0;
  v17 = 0;
  if ( (unsigned int)IsCommsSystemService() )
  {
    SecurityQOS.Capabilities = 0;
  }
  else
  {
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v9);
    v3 = token_information;
    if ( token_information < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)token_information,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        62);
      if ( Block )
        operator delete(Block);
      goto LABEL_12;
    }
    v8 = Block;
    SecurityQOS.Capabilities = 17;
    *(_QWORD *)&v17 = *(_QWORD *)Block;
  }
  v11 = *Binding;
  v18 = v19;
  SecurityQOS.Version = 5;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 3;
  v12 = RpcBindingSetAuthInfoExW(v11, 0, 6u, 0x14u, 0, 0, &SecurityQOS);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    Log_UnistoreHREvent_0(
      v13,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      83);
    if ( v8 )
      operator delete(v8);
    if ( v19 )
      FreeTransientObjectSecurityDescriptor(v19);
    v3 = v13;
  }
  else
  {
    if ( v8 )
      operator delete(v8);
    if ( v19 )
      FreeTransientObjectSecurityDescriptor(v19);
    v3 = 0;
  }
LABEL_33:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void _CloseBindString(unsigned short *),0>::_Delete(&StringBinding);
  return v3;
}

```

## disassembly

```asm
0x180075a3c  push    rbp
0x180075a3e  push    rbx
0x180075a3f  push    rdi
0x180075a40  mov     rbp, rsp
0x180075a43  sub     rsp, 80h
0x180075a4a  mov     rdi, rcx
0x180075a4d  mov     [rbp+arg_10], 0
0x180075a55  lea     rcx, [rbp+arg_10]
0x180075a59  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?_CloseBindString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&_CloseBindString(ushort *),0>::_Delete(void)
0x180075a5e  lea     rax, [rbp+arg_10]
0x180075a62  mov     [rbp+arg_10], 0
0x180075a6a  mov     [rsp+80h+StringBinding], rax; StringBinding
0x180075a6f  lea     rdx, ProtSeq; "ncalrpc"
0x180075a76  xor     r9d, r9d; Endpoint
0x180075a79  mov     [rsp+80h+Options], 0; Options
0x180075a82  xor     r8d, r8d; NetworkAddr
0x180075a85  xor     ecx, ecx; ObjUuid
0x180075a87  call    cs:__imp_RpcStringBindingComposeW
0x180075a8d  mov     ebx, eax
0x180075a8f  test    eax, eax
0x180075a91  jz      short loc_180075AA6
0x180075a93  jle     short loc_180075A9E
0x180075a95  movzx   ebx, ax
0x180075a98  or      ebx, 80070000h
0x180075a9e  mov     r9d, 2Ch ; ','
0x180075aa4  jmp     short loc_180075ACA
0x180075aa6  mov     rcx, [rbp+arg_10]; StringBinding
0x180075aaa  mov     rdx, rdi; Binding
0x180075aad  call    cs:__imp_RpcBindingFromStringBindingW
0x180075ab3  mov     ebx, eax
0x180075ab5  test    eax, eax
0x180075ab7  jz      short loc_180075ADF
0x180075ab9  jle     short loc_180075AC4
0x180075abb  movzx   ebx, ax
0x180075abe  or      ebx, 80070000h
0x180075ac4  mov     r9d, 2Eh ; '.'
0x180075aca  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075ad1  xor     edx, edx
0x180075ad3  mov     ecx, ebx
0x180075ad5  call    Log_UnistoreHREvent_0
0x180075ada  jmp     loc_180075C61
0x180075adf  lea     rcx, [rbp+arg_8]
0x180075ae3  mov     [rbp+arg_8], 0
0x180075aeb  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180075af0  mov     r8, rax
0x180075af3  lea     rdx, aUnistoreservic_1; "UnistoreServiceOneCore\\Server"
0x180075afa  mov     ecx, 9
0x180075aff  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180075b05  mov     ebx, eax
0x180075b07  or      ebx, 10000000h
0x180075b0d  jge     short loc_180075B3F
0x180075b0f  mov     r9d, 37h ; '7'
0x180075b15  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075b1c  mov     ecx, ebx
0x180075b1e  lea     edx, [r9-36h]
0x180075b22  call    Log_UnistoreHREvent_0
0x180075b27  mov     rcx, [rbp+arg_8]
0x180075b2b  test    rcx, rcx
0x180075b2e  jz      loc_180075C61
0x180075b34  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180075b3a  jmp     loc_180075C61
0x180075b3f  xorps   xmm0, xmm0
0x180075b42  xor     eax, eax
0x180075b44  xor     ebx, ebx
0x180075b46  mov     [rbp+var_10], rax
0x180075b4a  movups  xmmword ptr [rbp+var_40.Version], xmm0
0x180075b4e  mov     [rbp+Block], rbx
0x180075b52  movups  [rbp+var_30], xmm0
0x180075b56  movups  [rbp+var_20], xmm0
0x180075b5a  call    cs:__imp_IsCommsSystemService
0x180075b60  test    eax, eax
0x180075b62  jnz     short loc_180075BAF
0x180075b64  lea     rcx, [rbp+Block]
0x180075b68  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180075b6d  mov     ebx, eax
0x180075b6f  test    eax, eax
0x180075b71  jns     short loc_180075B9B
0x180075b73  mov     r9d, 3Eh ; '>'
0x180075b79  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075b80  mov     ecx, eax
0x180075b82  lea     edx, [r9-3Dh]
0x180075b86  call    Log_UnistoreHREvent_0
0x180075b8b  mov     rcx, [rbp+Block]; Block
0x180075b8f  test    rcx, rcx
0x180075b92  jz      short loc_180075B27
0x180075b94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075b99  jmp     short loc_180075B27
0x180075b9b  mov     rbx, [rbp+Block]
0x180075b9f  mov     [rbp+var_40.Capabilities], 11h
0x180075ba6  mov     rax, [rbx]
0x180075ba9  mov     qword ptr [rbp+var_20], rax
0x180075bad  jmp     short loc_180075BB2
0x180075baf  mov     [rbp+var_40.Capabilities], ebx
0x180075bb2  mov     rax, [rbp+arg_8]
0x180075bb6  xor     edx, edx; ServerPrincName
0x180075bb8  mov     rcx, [rdi]; Binding
0x180075bbb  mov     [rbp+var_10], rax
0x180075bbf  lea     rax, [rbp+var_40]
0x180075bc3  mov     [rsp+80h+SecurityQOS], rax; SecurityQOS
0x180075bc8  mov     dword ptr [rsp+80h+StringBinding], 0; AuthzSvc
0x180075bd0  lea     r9d, [rdx+14h]; AuthnSvc
0x180075bd4  lea     r8d, [rdx+6]; AuthnLevel
0x180075bd8  mov     [rsp+80h+Options], 0; AuthIdentity
0x180075be1  mov     [rbp+var_40.Version], 5
0x180075be8  mov     [rbp+var_40.IdentityTracking], 1
0x180075bef  mov     [rbp+var_40.ImpersonationType], 3
0x180075bf6  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180075bfc  mov     edi, eax
0x180075bfe  test    eax, eax
0x180075c00  jz      short loc_180075C43
0x180075c02  jle     short loc_180075C0D
0x180075c04  movzx   edi, ax
0x180075c07  or      edi, 80070000h
0x180075c0d  mov     r9d, 53h ; 'S'
0x180075c13  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180075c1a  xor     edx, edx
0x180075c1c  mov     ecx, edi
0x180075c1e  call    Log_UnistoreHREvent_0
0x180075c23  test    rbx, rbx
0x180075c26  jz      short loc_180075C30
0x180075c28  mov     rcx, rbx; Block
0x180075c2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075c30  mov     rcx, [rbp+arg_8]
0x180075c34  test    rcx, rcx
0x180075c37  jz      short loc_180075C3F
0x180075c39  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180075c3f  mov     ebx, edi
0x180075c41  jmp     short loc_180075C61
0x180075c43  test    rbx, rbx
0x180075c46  jz      short loc_180075C50
0x180075c48  mov     rcx, rbx; Block
0x180075c4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075c50  mov     rcx, [rbp+arg_8]
0x180075c54  test    rcx, rcx
0x180075c57  jz      short loc_180075C5F
0x180075c59  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180075c5f  xor     ebx, ebx
0x180075c61  lea     rcx, [rbp+arg_10]
0x180075c65  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?_CloseBindString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&_CloseBindString(ushort *),0>::_Delete(void)
0x180075c6a  mov     eax, ebx
0x180075c6c  add     rsp, 80h
0x180075c73  pop     rdi
0x180075c74  pop     rbx
0x180075c75  pop     rbp
0x180075c76  retn
```
