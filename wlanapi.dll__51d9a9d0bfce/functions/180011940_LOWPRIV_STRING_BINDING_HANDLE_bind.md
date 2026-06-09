# LOWPRIV_STRING_BINDING_HANDLE_bind

- ea: `0x180011940`
- end: `0x180011bef`
- name: `LOWPRIV_STRING_BINDING_HANDLE_bind`
- size: `687`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x1800105e0`
- `0x180011940`

## import_xrefs

- `RPCRT4!RpcBindingSetOption` at `0x180011a91`
- `RPCRT4!RpcBindingSetOption` at `0x180011a91`
- `RPCRT4!RpcEpResolveBinding` at `0x180011a7a`
- `RPCRT4!RpcEpResolveBinding` at `0x180011a7a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011a63`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011a63`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800119ff`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800119ff`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180011aac`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180011aac`
- `RPCRT4!RpcStringFreeW` at `0x180011b58`
- `RPCRT4!RpcStringFreeW` at `0x180011b6e`
- `RPCRT4!RpcStringFreeW` at `0x180011b58`
- `RPCRT4!RpcStringFreeW` at `0x180011b6e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180011ae2`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180011ae2`
- `MobileNetworking!RaCreateWellKnownSid` at `0x1800119aa`
- `MobileNetworking!RaCreateWellKnownSid` at `0x1800119aa`
- `MobileNetworking!RaDestroySid` at `0x180011bac`
- `MobileNetworking!RaDestroySid` at `0x180011bac`

## string_xrefs

- `0x1800119ee`: `Security=Impersonation Dynamic False`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall LOWPRIV_STRING_BINDING_HANDLE_bind(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  union DOT11_OUI_HEADER *v4; // rcx
  __int64 v6; // [rsp+40h] [rbp-30h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+48h] [rbp-28h] BYREF
  __int128 v8; // [rsp+58h] [rbp-18h]
  __int64 v9; // [rsp+68h] [rbp-8h]
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+28h] BYREF
  RPC_WSTR String; // [rsp+A0h] [rbp+30h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+A8h] [rbp+38h] BYREF

  String = 0;
  ServerPrincName = 0;
  SecurityQOS = 0;
  v9 = 0;
  v8 = 0;
  Binding = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids);
  }
  v2 = RaCreateWellKnownSid(22, &v6);
  v3 = v2;
  if ( !v2 )
  {
    *(_QWORD *)&SecurityQOS.Capabilities = 17;
    SecurityQOS.Version = 3;
    SecurityQOS.ImpersonationType = 3;
    v9 = v6;
    v8 = 0;
    v3 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           0,
           (RPC_WSTR)L"Security=Impersonation Dynamic False",
           &String);
    if ( !v3 )
    {
      v3 = RpcBindingFromStringBindingW(String, &Binding);
      if ( !v3 )
      {
        v3 = RpcEpResolveBinding(Binding, qword_180063150);
        if ( !v3 )
        {
          v3 = RpcBindingSetOption(Binding, 0xBu, 1u);
          if ( !v3 )
          {
            v3 = RpcMgmtInqServerPrincNameW(Binding, 0xAu, &ServerPrincName);
            if ( !v3 )
              v3 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 0xAu, 0, 0, &SecurityQOS);
          }
        }
      }
    }
    goto LABEL_5;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids, v2);
LABEL_5:
    v4 = WPP_GLOBAL_Control;
  }
  if ( String )
  {
    RpcStringFreeW(&String);
    v4 = WPP_GLOBAL_Control;
  }
  if ( ServerPrincName )
  {
    RpcStringFreeW(&ServerPrincName);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v3 && Binding )
  {
    LOWPRIV_STRING_BINDING_HANDLE_unbind(a1);
    v4 = WPP_GLOBAL_Control;
    Binding = 0;
  }
  if ( v6 )
  {
    RaDestroySid(v6);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v4 + 105) >= 4u
    && (*((_BYTE *)v4 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 12), 18, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids, v3);
  }
  return Binding;
}

```

## disassembly

```asm
0x180011940  mov     [rsp-18h+arg_0], rbx
0x180011945  push    rbp
0x180011946  push    rdi
0x180011947  push    r12
0x180011949  mov     rbp, rsp
0x18001194c  sub     rsp, 70h
0x180011950  xorps   xmm0, xmm0
0x180011953  mov     [rbp+String], 0
0x18001195b  xor     eax, eax
0x18001195d  mov     [rbp+ServerPrincName], 0
0x180011965  movups  xmmword ptr [rbp+var_28.Version], xmm0
0x180011969  mov     [rbp+var_8], rax
0x18001196d  mov     rdi, rcx
0x180011970  movups  [rbp+var_18], xmm0
0x180011974  mov     [rbp+Binding], 0
0x18001197c  mov     [rbp+var_30], 0
0x180011984  mov     rcx, cs:WPP_GLOBAL_Control
0x18001198b  lea     r12, WPP_GLOBAL_Control
0x180011992  cmp     rcx, r12
0x180011995  jz      short loc_1800119A1
0x180011997  cmp     byte ptr [rcx+69h], 4
0x18001199b  jnb     loc_180011AEF
0x1800119a1  lea     rdx, [rbp+var_30]
0x1800119a5  mov     ecx, 16h
0x1800119aa  call    cs:__imp_RaCreateWellKnownSid
0x1800119b0  mov     ebx, eax
0x1800119b2  test    eax, eax
0x1800119b4  jnz     loc_180011B13
0x1800119ba  lea     eax, [rbx+3]
0x1800119bd  mov     qword ptr [rbp+var_28.Capabilities], 11h
0x1800119c5  mov     [rbp+var_28.Version], eax
0x1800119c8  lea     rdx, ProtSeq; "ncalrpc"
0x1800119cf  mov     [rbp+var_28.ImpersonationType], eax
0x1800119d2  xorps   xmm0, xmm0
0x1800119d5  mov     rax, [rbp+var_30]
0x1800119d9  xor     r9d, r9d; Endpoint
0x1800119dc  mov     [rbp+var_8], rax
0x1800119e0  xor     r8d, r8d; NetworkAddr
0x1800119e3  lea     rax, [rbp+String]
0x1800119e7  xor     ecx, ecx; ObjUuid
0x1800119e9  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800119ee  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800119f5  mov     [rsp+70h+Options], rax; Options
0x1800119fa  movdqu  [rbp+var_18], xmm0
0x1800119ff  call    cs:__imp_RpcStringBindingComposeW
0x180011a05  mov     ebx, eax
0x180011a07  test    eax, eax
0x180011a09  jz      short loc_180011A5B
0x180011a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a12  cmp     [rbp+String], 0
0x180011a17  jnz     loc_180011B54
0x180011a1d  cmp     [rbp+ServerPrincName], 0
0x180011a22  jnz     loc_180011B6A
0x180011a28  test    ebx, ebx
0x180011a2a  jnz     loc_180011B80
0x180011a30  mov     rax, [rbp+var_30]
0x180011a34  test    rax, rax
0x180011a37  jnz     loc_180011BA9
0x180011a3d  cmp     rcx, r12
0x180011a40  jnz     loc_180011BBE
0x180011a46  mov     rax, [rbp+Binding]
0x180011a4a  mov     rbx, [rsp+70h+arg_0]
0x180011a52  add     rsp, 70h
0x180011a56  pop     r12
0x180011a58  pop     rdi
0x180011a59  pop     rbp
0x180011a5a  retn
0x180011a5b  mov     rcx, [rbp+String]; StringBinding
0x180011a5f  lea     rdx, [rbp+Binding]; Binding
0x180011a63  call    cs:__imp_RpcBindingFromStringBindingW
0x180011a69  mov     ebx, eax
0x180011a6b  test    eax, eax
0x180011a6d  jnz     short loc_180011A0B
0x180011a6f  mov     rcx, [rbp+Binding]; Binding
0x180011a73  lea     rdx, qword_180063150; IfSpec
0x180011a7a  call    cs:__imp_RpcEpResolveBinding
0x180011a80  mov     ebx, eax
0x180011a82  test    eax, eax
0x180011a84  jnz     short loc_180011A0B
0x180011a86  mov     rcx, [rbp+Binding]; hBinding
0x180011a8a  lea     edx, [rax+0Bh]; option
0x180011a8d  lea     r8d, [rax+1]; optionValue
0x180011a91  call    cs:__imp_RpcBindingSetOption
0x180011a97  mov     ebx, eax
0x180011a99  test    eax, eax
0x180011a9b  jnz     loc_180011A0B
0x180011aa1  mov     rcx, [rbp+Binding]; Binding
0x180011aa5  lea     r8, [rbp+ServerPrincName]; ServerPrincName
0x180011aa9  lea     edx, [rax+0Ah]; AuthnSvc
0x180011aac  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x180011ab2  mov     ebx, eax
0x180011ab4  test    eax, eax
0x180011ab6  jnz     loc_180011A0B
0x180011abc  mov     rdx, [rbp+ServerPrincName]; ServerPrincName
0x180011ac0  lea     rax, [rbp+var_28]
0x180011ac4  mov     rcx, [rbp+Binding]; Binding
0x180011ac8  lea     r9d, [rbx+0Ah]; AuthnSvc
0x180011acc  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180011ad1  lea     r8d, [rbx+6]; AuthnLevel
0x180011ad5  mov     dword ptr [rsp+70h+StringBinding], ebx; AuthzSvc
0x180011ad9  mov     [rsp+70h+Options], 0; AuthIdentity
0x180011ae2  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180011ae8  mov     ebx, eax
0x180011aea  jmp     loc_180011A0B
0x180011aef  test    byte ptr [rcx+6Ch], 2
0x180011af3  jz      loc_1800119A1
0x180011af9  mov     rcx, [rcx+60h]
0x180011afd  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180011b04  mov     edx, 10h
0x180011b09  call    WPP_SF_
0x180011b0e  jmp     loc_1800119A1
0x180011b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b1a  cmp     rcx, r12
0x180011b1d  jz      loc_180011A12
0x180011b23  cmp     byte ptr [rcx+69h], 1
0x180011b27  jb      loc_180011A12
0x180011b2d  test    byte ptr [rcx+6Ch], 2
0x180011b31  jz      loc_180011A12
0x180011b37  mov     rcx, [rcx+60h]
0x180011b3b  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180011b42  mov     edx, 11h
0x180011b47  mov     r9d, eax
0x180011b4a  call    WPP_SF_d
0x180011b4f  jmp     loc_180011A0B
0x180011b54  lea     rcx, [rbp+String]; String
0x180011b58  call    cs:__imp_RpcStringFreeW
0x180011b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b65  jmp     loc_180011A1D
0x180011b6a  lea     rcx, [rbp+ServerPrincName]; String
0x180011b6e  call    cs:__imp_RpcStringFreeW
0x180011b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b7b  jmp     loc_180011A28
0x180011b80  mov     rdx, [rbp+Binding]
0x180011b84  test    rdx, rdx
0x180011b87  jz      loc_180011A30
0x180011b8d  mov     rcx, rdi
0x180011b90  call    LOWPRIV_STRING_BINDING_HANDLE_unbind
0x180011b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b9c  mov     [rbp+Binding], 0
0x180011ba4  jmp     loc_180011A30
0x180011ba9  mov     rcx, rax
0x180011bac  call    cs:__imp_RaDestroySid
0x180011bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bb9  jmp     loc_180011A3D
0x180011bbe  cmp     byte ptr [rcx+69h], 4
0x180011bc2  jb      loc_180011A46
0x180011bc8  test    byte ptr [rcx+6Ch], 2
0x180011bcc  jz      loc_180011A46
0x180011bd2  mov     rcx, [rcx+60h]
0x180011bd6  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180011bdd  mov     edx, 12h
0x180011be2  mov     r9d, ebx
0x180011be5  call    WPP_SF_d
0x180011bea  jmp     loc_180011A46
```
