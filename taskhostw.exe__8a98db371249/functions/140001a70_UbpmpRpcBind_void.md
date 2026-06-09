# UbpmpRpcBind(void * *)

- ea: `0x140001a70`
- end: `0x140001bec`
- name: `?UbpmpRpcBind@@YAKPEAPEAX@Z`
- size: `380`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001a70`
- `0x14000a2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001bcd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140001ba3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140001ba3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140001b3d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140001b3d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140001b97`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140001b97`
- `RPCRT4!RpcStringFreeW` at `0x140001aff`
- `RPCRT4!RpcStringFreeW` at `0x140001aff`
- `RPCRT4!RpcBindingFree` at `0x140001be4`
- `RPCRT4!RpcBindingFree` at `0x140001be4`
- `RPCRT4!RpcStringBindingComposeW` at `0x140001adb`
- `RPCRT4!RpcStringBindingComposeW` at `0x140001adb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140001af3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140001af3`

## string_xrefs

- `0x140001ab3`: `ubpmtaskhostchannel`

## pseudocode

```c
__int64 __fastcall UbpmpRpcBind(void **a1)
{
  DWORD LastError; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-19h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-1h] BYREF
  __int128 v8; // [rsp+88h] [rbp+Fh]
  PSID v9; // [rsp+98h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  Binding = 0;
  String = 0;
  SecurityQOS = 0;
  v8 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"ubpmtaskhostchannel", 0, &String);
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    if ( !LastError )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        v9 = pSid;
        SecurityQOS.Capabilities = 1;
        SecurityQOS.IdentityTracking = 1;
        SecurityQOS.Version = 3;
        SecurityQOS.ImpersonationType = 3;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 1u, &SecurityQOS);
        FreeSid(pSid);
        if ( !LastError )
        {
          *a1 = Binding;
          return LastError;
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError;
}

```

## disassembly

```asm
0x140001a70  push    rbp
0x140001a72  push    rbx
0x140001a73  push    rsi
0x140001a74  push    rdi
0x140001a75  lea     rbp, [rsp-3Fh]
0x140001a7a  sub     rsp, 0B8h
0x140001a81  mov     rax, cs:__security_cookie
0x140001a88  xor     rax, rsp
0x140001a8b  mov     [rbp+57h+var_28], rax
0x140001a8f  xor     eax, eax
0x140001a91  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140001a97  xor     esi, esi
0x140001a99  mov     [rbp+57h+var_38], rax
0x140001a9d  xorps   xmm0, xmm0
0x140001aa0  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], eax
0x140001aa3  lea     rax, [rbp+57h+String]
0x140001aa7  mov     [rbp+57h+var_60], rsi
0x140001aab  mov     rdi, rcx
0x140001aae  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x140001ab3  lea     r9, Endpoint; "ubpmtaskhostchannel"
0x140001aba  mov     [rsp+0D0h+Options], rsi; Options
0x140001abf  xor     r8d, r8d; NetworkAddr
0x140001ac2  mov     [rbp+57h+Binding], rsi
0x140001ac6  lea     rdx, ProtSeq; "ncalrpc"
0x140001acd  mov     [rbp+57h+String], rsi
0x140001ad1  xor     ecx, ecx; ObjUuid
0x140001ad3  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x140001ad7  movups  [rbp+57h+var_48], xmm0
0x140001adb  call    cs:__imp_RpcStringBindingComposeW
0x140001ae1  mov     ebx, eax
0x140001ae3  test    eax, eax
0x140001ae5  jnz     loc_140001BAD
0x140001aeb  mov     rcx, [rbp+57h+String]; StringBinding
0x140001aef  lea     rdx, [rbp+57h+Binding]; Binding
0x140001af3  call    cs:__imp_RpcBindingFromStringBindingW
0x140001af9  lea     rcx, [rbp+57h+String]; String
0x140001afd  mov     ebx, eax
0x140001aff  call    cs:__imp_RpcStringFreeW
0x140001b05  test    ebx, ebx
0x140001b07  jnz     loc_140001BAD
0x140001b0d  lea     rax, [rbp+57h+var_60]
0x140001b11  xor     r9d, r9d; nSubAuthority1
0x140001b14  mov     [rsp+0D0h+pSid], rax; pSid
0x140001b19  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140001b1d  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x140001b21  mov     r8d, 12h; nSubAuthority0
0x140001b27  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x140001b2b  mov     dl, 1; nSubAuthorityCount
0x140001b2d  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x140001b31  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x140001b35  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x140001b39  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x140001b3d  call    cs:__imp_AllocateAndInitializeSid
0x140001b43  test    eax, eax
0x140001b45  jz      loc_140001BCD
0x140001b4b  mov     rax, [rbp+57h+var_60]
0x140001b4f  xor     edx, edx; ServerPrincName
0x140001b51  mov     rcx, [rbp+57h+Binding]; Binding
0x140001b55  mov     r9d, 0Ah; AuthnSvc
0x140001b5b  mov     [rbp+57h+var_38], rax
0x140001b5f  mov     r8d, 6; AuthnLevel
0x140001b65  lea     rax, [rbp+57h+SecurityQOS]
0x140001b69  mov     [rbp+57h+SecurityQOS.Capabilities], 1
0x140001b70  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x140001b75  mov     dword ptr [rsp+0D0h+StringBinding], 1; AuthzSvc
0x140001b7d  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x140001b82  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x140001b89  mov     [rbp+57h+SecurityQOS.Version], 3
0x140001b90  mov     [rbp+57h+SecurityQOS.ImpersonationType], 3
0x140001b97  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140001b9d  mov     rcx, [rbp+57h+var_60]; pSid
0x140001ba1  mov     ebx, eax
0x140001ba3  call    cs:__imp_FreeSid
0x140001ba9  test    ebx, ebx
0x140001bab  jz      short loc_140001BD7
0x140001bad  cmp     [rbp+57h+Binding], rsi
0x140001bb1  jnz     short loc_140001BE0
0x140001bb3  mov     eax, ebx
0x140001bb5  mov     rcx, [rbp+57h+var_28]
0x140001bb9  xor     rcx, rsp; StackCookie
0x140001bbc  call    __security_check_cookie
0x140001bc1  add     rsp, 0B8h
0x140001bc8  pop     rdi
0x140001bc9  pop     rsi
0x140001bca  pop     rbx
0x140001bcb  pop     rbp
0x140001bcc  retn
0x140001bcd  call    cs:__imp_GetLastError
0x140001bd3  mov     ebx, eax
0x140001bd5  jmp     short loc_140001BAD
0x140001bd7  mov     rax, [rbp+57h+Binding]
0x140001bdb  mov     [rdi], rax
0x140001bde  jmp     short loc_140001BB3
0x140001be0  lea     rcx, [rbp+57h+Binding]; Binding
0x140001be4  call    cs:__imp_RpcBindingFree
0x140001bea  jmp     short loc_140001BB3
```
