# STRING_BINDING_HANDLE_bind

- ea: `0x180006c60`
- end: `0x180006ee8`
- name: `STRING_BINDING_HANDLE_bind`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180006c60`

## import_xrefs

- `RPCRT4!RpcBindingSetOption` at `0x180006d59`
- `RPCRT4!RpcBindingSetOption` at `0x180006d59`
- `RPCRT4!RpcEpResolveBinding` at `0x180006d3e`
- `RPCRT4!RpcEpResolveBinding` at `0x180006d3e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180006d27`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180006d27`
- `RPCRT4!RpcStringBindingComposeW` at `0x180006d0f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180006d0f`
- `RPCRT4!RpcBindingFree` at `0x180006e8e`
- `RPCRT4!RpcBindingFree` at `0x180006e8e`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180006d72`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180006d72`
- `RPCRT4!RpcStringFreeW` at `0x180006dbd`
- `RPCRT4!RpcStringFreeW` at `0x180006dd4`
- `RPCRT4!RpcStringFreeW` at `0x180006dbd`
- `RPCRT4!RpcStringFreeW` at `0x180006dd4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180006da4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180006da4`
- `MobileNetworking!RaCreateWellKnownSid` at `0x180006cb5`
- `MobileNetworking!RaCreateWellKnownSid` at `0x180006cb5`
- `MobileNetworking!RaDestroySid` at `0x180006df9`
- `MobileNetworking!RaDestroySid` at `0x180006df9`

## string_xrefs

- `0x180006cea`: `Security=Impersonation Dynamic False`

## pseudocode

```c
RPC_BINDING_HANDLE STRING_BINDING_HANDLE_bind()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  union DOT11_OUI_HEADER *v2; // rcx
  RPC_BINDING_HANDLE v3; // rdx
  __int64 v5; // [rsp+40h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE v6; // [rsp+48h] [rbp-38h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-30h] BYREF
  __int128 v8; // [rsp+60h] [rbp-20h]
  __int64 v9; // [rsp+70h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+28h] BYREF
  RPC_WSTR String; // [rsp+B0h] [rbp+30h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+B8h] [rbp+38h] BYREF

  String = 0;
  v9 = 0;
  ServerPrincName = 0;
  Binding = 0;
  v5 = 0;
  SecurityQOS = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids);
  }
  v0 = RaCreateWellKnownSid(22, &v5);
  v1 = v0;
  if ( !v0 )
  {
    v9 = v5;
    SecurityQOS.Version = 3;
    *(_QWORD *)&SecurityQOS.Capabilities = 17;
    SecurityQOS.ImpersonationType = 3;
    v8 = 0;
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           0,
           (RPC_WSTR)L"Security=Impersonation Dynamic False",
           &String);
    if ( !v1 )
    {
      v1 = RpcBindingFromStringBindingW(String, &Binding);
      if ( !v1 )
      {
        v1 = RpcEpResolveBinding(Binding, qword_180063030);
        if ( !v1 )
        {
          v1 = RpcBindingSetOption(Binding, 0xBu, 1u);
          if ( !v1 )
          {
            v1 = RpcMgmtInqServerPrincNameW(Binding, 0xAu, &ServerPrincName);
            if ( !v1 )
              v1 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 0xAu, 0, 0, &SecurityQOS);
          }
        }
      }
    }
    goto LABEL_9;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids, v0);
LABEL_9:
    v2 = WPP_GLOBAL_Control;
  }
  if ( String )
  {
    RpcStringFreeW(&String);
    v2 = WPP_GLOBAL_Control;
  }
  if ( ServerPrincName )
  {
    RpcStringFreeW(&ServerPrincName);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = Binding;
  if ( v1 && Binding )
  {
    v6 = Binding;
    RpcBindingFree(&v6);
    v2 = WPP_GLOBAL_Control;
    v3 = 0;
    Binding = 0;
  }
  if ( v5 )
  {
    RaDestroySid(v5);
    v3 = Binding;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    || *((_BYTE *)v2 + 105) < 4u
    || (*((_BYTE *)v2 + 108) & 2) == 0 )
  {
    return v3;
  }
  WPP_SF_d(*((_QWORD *)v2 + 12), 12, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids, v1);
  return Binding;
}

```

## disassembly

```asm
0x180006c60  mov     [rsp-18h+arg_0], rbx
0x180006c65  push    rbp
0x180006c66  push    rsi
0x180006c67  push    rdi
0x180006c68  mov     rbp, rsp
0x180006c6b  sub     rsp, 80h
0x180006c72  xor     edi, edi
0x180006c74  xorps   xmm0, xmm0
0x180006c77  xor     eax, eax
0x180006c79  mov     [rbp+String], rdi
0x180006c7d  mov     [rbp+var_10], rax
0x180006c81  mov     [rbp+ServerPrincName], rdi
0x180006c85  mov     [rbp+Binding], rdi
0x180006c89  mov     [rbp+var_40], rdi
0x180006c8d  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180006c91  movups  [rbp+var_20], xmm0
0x180006c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c9c  lea     rsi, WPP_GLOBAL_Control
0x180006ca3  cmp     rcx, rsi
0x180006ca6  jnz     loc_180006E4F
0x180006cac  lea     rdx, [rbp+var_40]
0x180006cb0  mov     ecx, 16h
0x180006cb5  call    cs:__imp_RaCreateWellKnownSid
0x180006cbb  mov     ebx, eax
0x180006cbd  test    eax, eax
0x180006cbf  jnz     loc_180006EA7
0x180006cc5  mov     rax, [rbp+var_40]
0x180006cc9  lea     rdx, ProtSeq; "ncalrpc"
0x180006cd0  mov     [rbp+var_10], rax
0x180006cd4  xorps   xmm0, xmm0
0x180006cd7  lea     rax, [rbp+String]
0x180006cdb  mov     [rbp+var_30.Version], 3
0x180006ce2  mov     [rsp+80h+StringBinding], rax; StringBinding
0x180006ce7  xor     r9d, r9d; Endpoint
0x180006cea  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180006cf1  mov     qword ptr [rbp+var_30.Capabilities], 11h
0x180006cf9  xor     r8d, r8d; NetworkAddr
0x180006cfc  mov     [rsp+80h+Options], rax; Options
0x180006d01  xor     ecx, ecx; ObjUuid
0x180006d03  mov     [rbp+var_30.ImpersonationType], 3
0x180006d0a  movdqu  [rbp+var_20], xmm0
0x180006d0f  call    cs:__imp_RpcStringBindingComposeW
0x180006d15  mov     ebx, eax
0x180006d17  test    eax, eax
0x180006d19  jnz     loc_180006DAC
0x180006d1f  mov     rcx, [rbp+String]; StringBinding
0x180006d23  lea     rdx, [rbp+Binding]; Binding
0x180006d27  call    cs:__imp_RpcBindingFromStringBindingW
0x180006d2d  mov     ebx, eax
0x180006d2f  test    eax, eax
0x180006d31  jnz     short loc_180006DAC
0x180006d33  mov     rcx, [rbp+Binding]; Binding
0x180006d37  lea     rdx, qword_180063030; IfSpec
0x180006d3e  call    cs:__imp_RpcEpResolveBinding
0x180006d44  mov     ebx, eax
0x180006d46  test    eax, eax
0x180006d48  jnz     short loc_180006DAC
0x180006d4a  mov     rcx, [rbp+Binding]; hBinding
0x180006d4e  mov     edx, 0Bh; option
0x180006d53  mov     r8d, 1; optionValue
0x180006d59  call    cs:__imp_RpcBindingSetOption
0x180006d5f  mov     ebx, eax
0x180006d61  test    eax, eax
0x180006d63  jnz     short loc_180006DAC
0x180006d65  mov     rcx, [rbp+Binding]; Binding
0x180006d69  lea     r8, [rbp+ServerPrincName]; ServerPrincName
0x180006d6d  mov     edx, 0Ah; AuthnSvc
0x180006d72  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x180006d78  mov     ebx, eax
0x180006d7a  test    eax, eax
0x180006d7c  jnz     short loc_180006DAC
0x180006d7e  mov     rdx, [rbp+ServerPrincName]; ServerPrincName
0x180006d82  lea     rax, [rbp+var_30]
0x180006d86  mov     rcx, [rbp+Binding]; Binding
0x180006d8a  mov     r9d, 0Ah; AuthnSvc
0x180006d90  mov     [rsp+80h+SecurityQOS], rax; SecurityQOS
0x180006d95  mov     r8d, 6; AuthnLevel
0x180006d9b  mov     dword ptr [rsp+80h+StringBinding], edi; AuthzSvc
0x180006d9f  mov     [rsp+80h+Options], rdi; AuthIdentity
0x180006da4  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180006daa  mov     ebx, eax
0x180006dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180006db3  cmp     [rbp+String], rdi
0x180006db7  jz      short loc_180006DCA
0x180006db9  lea     rcx, [rbp+String]; String
0x180006dbd  call    cs:__imp_RpcStringFreeW
0x180006dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dca  cmp     [rbp+ServerPrincName], rdi
0x180006dce  jz      short loc_180006DE1
0x180006dd0  lea     rcx, [rbp+ServerPrincName]; String
0x180006dd4  call    cs:__imp_RpcStringFreeW
0x180006dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180006de1  mov     rdx, [rbp+Binding]
0x180006de5  test    ebx, ebx
0x180006de7  jnz     loc_180006E7D
0x180006ded  mov     rax, [rbp+var_40]
0x180006df1  test    rax, rax
0x180006df4  jz      short loc_180006E0A
0x180006df6  mov     rcx, rax
0x180006df9  call    cs:__imp_RaDestroySid
0x180006dff  mov     rdx, [rbp+Binding]
0x180006e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e0a  cmp     rcx, rsi
0x180006e0d  jnz     short loc_180006E25
0x180006e0f  mov     rax, rdx
0x180006e12  mov     rbx, [rsp+80h+arg_0]
0x180006e1a  add     rsp, 80h
0x180006e21  pop     rdi
0x180006e22  pop     rsi
0x180006e23  pop     rbp
0x180006e24  retn
0x180006e25  cmp     byte ptr [rcx+69h], 4
0x180006e29  jb      short loc_180006E0F
0x180006e2b  test    byte ptr [rcx+6Ch], 2
0x180006e2f  jz      short loc_180006E0F
0x180006e31  mov     rcx, [rcx+60h]
0x180006e35  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180006e3c  mov     edx, 0Ch
0x180006e41  mov     r9d, ebx
0x180006e44  call    WPP_SF_d
0x180006e49  mov     rax, [rbp+Binding]
0x180006e4d  jmp     short loc_180006E12
0x180006e4f  cmp     byte ptr [rcx+69h], 4
0x180006e53  jb      loc_180006CAC
0x180006e59  test    byte ptr [rcx+6Ch], 2
0x180006e5d  jz      loc_180006CAC
0x180006e63  mov     rcx, [rcx+60h]
0x180006e67  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180006e6e  mov     edx, 0Ah
0x180006e73  call    WPP_SF_
0x180006e78  jmp     loc_180006CAC
0x180006e7d  test    rdx, rdx
0x180006e80  jz      loc_180006DED
0x180006e86  lea     rcx, [rbp+var_38]; Binding
0x180006e8a  mov     [rbp+var_38], rdx
0x180006e8e  call    cs:__imp_RpcBindingFree
0x180006e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e9b  mov     rdx, rdi
0x180006e9e  mov     [rbp+Binding], rdx
0x180006ea2  jmp     loc_180006DED
0x180006ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eae  cmp     rcx, rsi
0x180006eb1  jz      loc_180006DB3
0x180006eb7  cmp     byte ptr [rcx+69h], 1
0x180006ebb  jb      loc_180006DB3
0x180006ec1  test    byte ptr [rcx+6Ch], 2
0x180006ec5  jz      loc_180006DB3
0x180006ecb  mov     rcx, [rcx+60h]
0x180006ecf  lea     r8, WPP_784bfa2c973138f0346cb6bab5ef92b6_Traceguids
0x180006ed6  mov     edx, 0Bh
0x180006edb  mov     r9d, eax
0x180006ede  call    WPP_SF_d
0x180006ee3  jmp     loc_180006DAC
```
