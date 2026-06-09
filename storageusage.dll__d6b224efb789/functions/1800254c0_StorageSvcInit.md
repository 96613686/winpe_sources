# StorageSvcInit

- ea: `0x1800254c0`
- end: `0x18002564c`
- name: `StorageSvcInit`
- size: `396`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800078b0`
- `0x18000b350`

## callees

- `0x1800050f0`
- `0x1800254c0`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800255fc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800255fc`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180025631`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180025631`
- `RPCRT4!RpcStringFreeW` at `0x180025570`
- `RPCRT4!RpcStringFreeW` at `0x180025570`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800255e5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800255e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025542`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180025538`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180025538`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180025560`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180025560`

## pseudocode

```c
__int64 __fastcall StorageSvcInit(RPC_BINDING_HANDLE *Binding)
{
  int LastError; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  RPC_BINDING_HANDLE v6; // rcx
  RPC_WSTR String; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v10; // [rsp+90h] [rbp+7h]
  __int64 v11; // [rsp+A0h] [rbp+17h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v11 = 0;
  pSid = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  v10 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = LastError <= 0;
    goto LABEL_3;
  }
  v10 = (unsigned __int64)pSid;
  *(_QWORD *)&SecurityQOS[0].Version = 0x1100000005LL;
  SecurityQOS[0].IdentityTracking = 1;
  *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
  SecurityQOS[1].Capabilities = 0;
  *(_QWORD *)&SecurityQOS[1].IdentityTracking = 0;
  v11 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( LastError
    || (LastError = RpcBindingFromStringBindingW(String, Binding), v3 = LastError, v4 = LastError <= 0, LastError) )
  {
LABEL_3:
    if ( v4 )
      goto LABEL_5;
    goto LABEL_4;
  }
  v6 = *Binding;
  v3 = 0;
  v11 = 0;
  LastError = RpcBindingSetAuthInfoExW(v6, 0, 6u, 0xAu, 0, 0, SecurityQOS);
  if ( LastError )
  {
    if ( LastError > 0 )
    {
LABEL_4:
      v3 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_5;
    }
    v3 = LastError;
  }
LABEL_5:
  if ( pSid )
    FreeSid(pSid);
  if ( String )
    RpcStringFreeW(&String);
  return v3;
}

```

## disassembly

```asm
0x1800254c0  push    rbp
0x1800254c2  push    rbx
0x1800254c3  push    rsi
0x1800254c4  push    rdi
0x1800254c5  lea     rbp, [rsp-3Fh]
0x1800254ca  sub     rsp, 0C8h
0x1800254d1  mov     rax, cs:__security_cookie
0x1800254d8  xor     rax, rsp
0x1800254db  mov     [rbp+57h+var_30], rax
0x1800254df  xor     esi, esi
0x1800254e1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800254e7  xorps   xmm0, xmm0
0x1800254ea  mov     [rbp+57h+String], rsi
0x1800254ee  xor     eax, eax
0x1800254f0  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800254f3  mov     [rbp+57h+var_40], rax
0x1800254f7  mov     rdi, rcx
0x1800254fa  lea     rax, [rbp+57h+var_78]
0x1800254fe  mov     [rbp+57h+var_78], rsi
0x180025502  mov     [rsp+0E0h+pSid], rax; pSid
0x180025507  lea     r8d, [rsi+12h]; nSubAuthority0
0x18002550b  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x18002550f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180025513  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x180025517  xor     r9d, r9d; nSubAuthority1
0x18002551a  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x18002551e  mov     dl, 1; nSubAuthorityCount
0x180025520  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x180025524  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x180025528  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x18002552c  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x180025530  movups  [rbp+57h+var_60], xmm0
0x180025534  movups  [rbp+57h+var_50], xmm0
0x180025538  call    cs:__imp_AllocateAndInitializeSid
0x18002553e  test    eax, eax
0x180025540  jnz     short loc_180025590
0x180025542  call    cs:__imp_GetLastError
0x180025548  mov     ebx, eax
0x18002554a  test    eax, eax
0x18002554c  jle     short loc_180025557
0x18002554e  movzx   ebx, ax
0x180025551  or      ebx, 80070000h
0x180025557  mov     rcx, [rbp+57h+var_78]; pSid
0x18002555b  test    rcx, rcx
0x18002555e  jz      short loc_180025566
0x180025560  call    cs:__imp_FreeSid
0x180025566  cmp     [rbp+57h+String], rsi
0x18002556a  jz      short loc_180025576
0x18002556c  lea     rcx, [rbp+57h+String]; String
0x180025570  call    cs:__imp_RpcStringFreeW
0x180025576  mov     eax, ebx
0x180025578  mov     rcx, [rbp+57h+var_30]
0x18002557c  xor     rcx, rsp; StackCookie
0x18002557f  call    __security_check_cookie
0x180025584  add     rsp, 0C8h
0x18002558b  pop     rdi
0x18002558c  pop     rsi
0x18002558d  pop     rbx
0x18002558e  pop     rbp
0x18002558f  retn
0x180025590  mov     rcx, [rbp+57h+var_78]
0x180025594  lea     rax, [rbp+57h+String]
0x180025598  mov     qword ptr [rbp+57h+var_50], rcx
0x18002559c  lea     rdx, ProtSeq; "ncalrpc"
0x1800255a3  xor     r10d, r10d
0x1800255a6  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; StringBinding
0x1800255ab  xor     ecx, ecx; ObjUuid
0x1800255ad  mov     [rbp+57h+SecurityQOS.Version], 5
0x1800255b4  xor     r9d, r9d; Endpoint
0x1800255b7  mov     [rbp+57h+SecurityQOS.Capabilities], 11h
0x1800255be  xor     r8d, r8d; NetworkAddr
0x1800255c1  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x1800255c8  mov     qword ptr [rbp+57h+SecurityQOS.ImpersonationType], 3
0x1800255d0  mov     dword ptr [rbp+57h+var_60+4], r10d
0x1800255d4  mov     qword ptr [rbp+57h+var_60+8], rsi
0x1800255d8  mov     qword ptr [rbp+57h+var_50+8], rsi
0x1800255dc  mov     [rbp+57h+var_40], rsi
0x1800255e0  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; Options
0x1800255e5  call    cs:__imp_RpcStringBindingComposeW
0x1800255eb  mov     ebx, eax
0x1800255ed  test    eax, eax
0x1800255ef  jnz     loc_18002554C
0x1800255f5  mov     rcx, [rbp+57h+String]; StringBinding
0x1800255f9  mov     rdx, rdi; Binding
0x1800255fc  call    cs:__imp_RpcBindingFromStringBindingW
0x180025602  mov     ebx, eax
0x180025604  test    eax, eax
0x180025606  jnz     loc_18002554C
0x18002560c  mov     rcx, [rdi]; Binding
0x18002560f  lea     rax, [rbp+57h+SecurityQOS]
0x180025613  xor     edx, edx; ServerPrincName
0x180025615  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax; SecurityQOS
0x18002561a  mov     [rsp+0E0h+nSubAuthority3], esi; AuthzSvc
0x18002561e  mov     ebx, esi
0x180025620  mov     [rbp+57h+var_40], rsi
0x180025624  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; AuthIdentity
0x180025629  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18002562d  lea     r8d, [rdx+6]; AuthnLevel
0x180025631  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180025637  test    eax, eax
0x180025639  jz      loc_180025557
0x18002563f  jg      loc_18002554E
0x180025645  mov     ebx, eax
0x180025647  jmp     loc_180025557
```
