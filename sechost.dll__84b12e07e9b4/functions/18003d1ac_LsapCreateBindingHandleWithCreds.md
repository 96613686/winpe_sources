# LsapCreateBindingHandleWithCreds

- ea: `0x18003d1ac`
- end: `0x18003d2a2`
- name: `LsapCreateBindingHandleWithCreds`
- size: `246`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr, RPC_WSTR ServerPrincName, unsigned int AuthnLevel, unsigned int AuthnSvc, RPC_AUTH_IDENTITY_HANDLE AuthIdentity, unsigned int AuthzSvc, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800181f0`
- `0x18003cc70`
- `0x18003ce68`

## callees

- `0x18003d1ac`
- `0x18004f932`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18003d27b`
- `RPCRT4!RpcStringFreeW` at `0x18003d27b`
- `RPCRT4!RpcBindingFree` at `0x18003d267`
- `RPCRT4!RpcBindingFree` at `0x18003d267`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003d224`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003d224`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18003d256`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18003d256`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003d20e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003d20e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003d293`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003d293`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleWithCreds(
        const wchar_t *NetworkAddr,
        RPC_WSTR ServerPrincName,
        unsigned int AuthnLevel,
        unsigned int AuthnSvc,
        RPC_AUTH_IDENTITY_HANDLE AuthIdentity,
        unsigned int AuthzSvc,
        RPC_BINDING_HANDLE *a7)
{
  int v11; // eax
  unsigned __int16 *v12; // r8
  RPC_STATUS v13; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-38h] BYREF
  RPC_WSTR String[6]; // [rsp+38h] [rbp-30h] BYREF

  String[0] = 0;
  Binding = 0;
  v11 = wcsncmp_0(NetworkAddr, L"\\\\", 2u);
  v12 = (unsigned __int16 *)(NetworkAddr + 2);
  if ( v11 )
    v12 = (unsigned __int16 *)NetworkAddr;
  v13 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", v12, 0, 0, String);
  if ( !v13 )
  {
    v13 = RpcBindingFromStringBindingW(String[0], &Binding);
    if ( !v13 )
    {
      v13 = RpcBindingSetAuthInfoW(Binding, ServerPrincName, AuthnLevel, AuthnSvc, AuthIdentity, AuthzSvc);
      if ( v13 )
      {
        RpcBindingFree(&Binding);
        Binding = 0;
      }
    }
    RpcStringFreeW(String);
  }
  *a7 = Binding;
  return I_RpcMapWin32Status(v13);
}

```

## disassembly

```asm
0x18003d1ac  push    rbx
0x18003d1ae  push    rbp
0x18003d1af  push    rsi
0x18003d1b0  push    rdi
0x18003d1b1  sub     rsp, 48h
0x18003d1b5  mov     esi, r8d
0x18003d1b8  mov     [rsp+68h+String], 0
0x18003d1c1  mov     rbp, rdx
0x18003d1c4  mov     [rsp+68h+Binding], 0
0x18003d1cd  mov     r8d, 2; MaxCount
0x18003d1d3  lea     rdx, asc_180064784; "\\\\"
0x18003d1da  mov     edi, r9d
0x18003d1dd  mov     rbx, rcx
0x18003d1e0  call    wcsncmp_0
0x18003d1e5  test    eax, eax
0x18003d1e7  lea     r8, [rbx+4]
0x18003d1eb  lea     rax, [rsp+68h+String]
0x18003d1f0  cmovnz  r8, rbx; NetworkAddr
0x18003d1f4  mov     [rsp+68h+StringBinding], rax; StringBinding
0x18003d1f9  xor     r9d, r9d; Endpoint
0x18003d1fc  mov     [rsp+68h+Options], 0; Options
0x18003d205  xor     ecx, ecx; ObjUuid
0x18003d207  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18003d20e  call    cs:__imp_RpcStringBindingComposeW
0x18003d214  mov     ebx, eax
0x18003d216  test    eax, eax
0x18003d218  jnz     short loc_18003D281
0x18003d21a  mov     rcx, [rsp+68h+String]; StringBinding
0x18003d21f  lea     rdx, [rsp+68h+Binding]; Binding
0x18003d224  call    cs:__imp_RpcBindingFromStringBindingW
0x18003d22a  mov     ebx, eax
0x18003d22c  test    eax, eax
0x18003d22e  jnz     short loc_18003D276
0x18003d230  mov     eax, [rsp+68h+AuthzSvc]
0x18003d237  mov     r9d, edi; AuthnSvc
0x18003d23a  mov     rcx, [rsp+68h+Binding]; Binding
0x18003d23f  mov     r8d, esi; AuthnLevel
0x18003d242  mov     dword ptr [rsp+68h+StringBinding], eax; AuthzSvc
0x18003d246  mov     rdx, rbp; ServerPrincName
0x18003d249  mov     rax, [rsp+68h+AuthIdentity]
0x18003d251  mov     [rsp+68h+Options], rax; AuthIdentity
0x18003d256  call    cs:__imp_RpcBindingSetAuthInfoW
0x18003d25c  mov     ebx, eax
0x18003d25e  test    eax, eax
0x18003d260  jz      short loc_18003D276
0x18003d262  lea     rcx, [rsp+68h+Binding]; Binding
0x18003d267  call    cs:__imp_RpcBindingFree
0x18003d26d  mov     [rsp+68h+Binding], 0
0x18003d276  lea     rcx, [rsp+68h+String]; String
0x18003d27b  call    cs:__imp_RpcStringFreeW
0x18003d281  mov     rcx, [rsp+68h+arg_30]
0x18003d289  mov     rax, [rsp+68h+Binding]
0x18003d28e  mov     [rcx], rax
0x18003d291  mov     ecx, ebx; Status
0x18003d293  call    cs:__imp_I_RpcMapWin32Status
0x18003d299  add     rsp, 48h
0x18003d29d  pop     rdi
0x18003d29e  pop     rsi
0x18003d29f  pop     rbp
0x18003d2a0  pop     rbx
0x18003d2a1  retn
```
