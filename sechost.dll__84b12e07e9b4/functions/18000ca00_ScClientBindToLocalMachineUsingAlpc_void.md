# ScClientBindToLocalMachineUsingAlpc(void * *)

- ea: `0x18000ca00`
- end: `0x18000cb8b`
- name: `?ScClientBindToLocalMachineUsingAlpc@@YAKPEAPEAX@Z`
- size: `395`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf10`
- `0x18003ac6c`
- `0x18003b530`

## callees

- `0x18000ca00`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb6f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ca9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ca9d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cb01`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000cb01`
- `RPCRT4!RpcStringFreeW` at `0x18000ca84`
- `RPCRT4!RpcStringFreeW` at `0x18000ca84`
- `RPCRT4!RpcBindingFree` at `0x18000cb80`
- `RPCRT4!RpcBindingFree` at `0x18000cb80`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000cb57`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000cb57`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000cac5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000cac5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ca6e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ca6e`

## pseudocode

```c
__int64 __fastcall ScClientBindToLocalMachineUsingAlpc(void **a1)
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
  *a1 = 0;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  String = 0;
  Binding = 0;
  pSid = 0;
  SecurityQOS = 0;
  v8 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"ntsvcs", 0, &String);
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    if ( !LastError )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        v9 = pSid;
        SecurityQOS.Capabilities = 1;
        SecurityQOS.IdentityTracking = 1;
        SecurityQOS.Version = 3;
        SecurityQOS.ImpersonationType = 3;
        RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 1u, &SecurityQOS);
        LastError = 0;
        *a1 = Binding;
        Binding = 0;
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( pSid )
    FreeSid(pSid);
  return LastError;
}

```

## disassembly

```asm
0x18000ca00  push    rbp
0x18000ca02  push    rbx
0x18000ca03  push    rsi
0x18000ca04  push    rdi
0x18000ca05  lea     rbp, [rsp-3Fh]
0x18000ca0a  sub     rsp, 0B8h
0x18000ca11  mov     rax, cs:__security_cookie
0x18000ca18  xor     rax, rsp
0x18000ca1b  mov     [rbp+57h+var_28], rax
0x18000ca1f  xor     esi, esi
0x18000ca21  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000ca27  xor     eax, eax
0x18000ca29  mov     [rcx], rsi
0x18000ca2c  xorps   xmm0, xmm0
0x18000ca2f  mov     [rbp+57h+var_38], rax
0x18000ca33  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], eax
0x18000ca36  lea     r9, Endpoint; "ntsvcs"
0x18000ca3d  lea     rax, [rbp+57h+String]
0x18000ca41  mov     [rbp+57h+String], rsi
0x18000ca45  mov     rdi, rcx
0x18000ca48  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x18000ca4d  xor     r8d, r8d; NetworkAddr
0x18000ca50  mov     [rsp+0D0h+Options], rsi; Options
0x18000ca55  lea     rdx, Protseq; "ncalrpc"
0x18000ca5c  mov     [rbp+57h+Binding], rsi
0x18000ca60  xor     ecx, ecx; ObjUuid
0x18000ca62  mov     [rbp+57h+pSid], rsi
0x18000ca66  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x18000ca6a  movups  [rbp+57h+var_48], xmm0
0x18000ca6e  call    cs:__imp_RpcStringBindingComposeW
0x18000ca74  mov     ebx, eax
0x18000ca76  test    eax, eax
0x18000ca78  jz      short loc_18000CABD
0x18000ca7a  cmp     [rbp+57h+String], rsi
0x18000ca7e  jz      short loc_18000CA8A
0x18000ca80  lea     rcx, [rbp+57h+String]; String
0x18000ca84  call    cs:__imp_RpcStringFreeW
0x18000ca8a  cmp     [rbp+57h+Binding], rsi
0x18000ca8e  jnz     loc_18000CB7C
0x18000ca94  mov     rcx, [rbp+57h+pSid]; pSid
0x18000ca98  test    rcx, rcx
0x18000ca9b  jz      short loc_18000CAA3
0x18000ca9d  call    cs:__imp_FreeSid
0x18000caa3  mov     eax, ebx
0x18000caa5  mov     rcx, [rbp+57h+var_28]
0x18000caa9  xor     rcx, rsp; StackCookie
0x18000caac  call    __security_check_cookie
0x18000cab1  add     rsp, 0B8h
0x18000cab8  pop     rdi
0x18000cab9  pop     rsi
0x18000caba  pop     rbx
0x18000cabb  pop     rbp
0x18000cabc  retn
0x18000cabd  mov     rcx, [rbp+57h+String]; StringBinding
0x18000cac1  lea     rdx, [rbp+57h+Binding]; Binding
0x18000cac5  call    cs:__imp_RpcBindingFromStringBindingW
0x18000cacb  mov     ebx, eax
0x18000cacd  test    eax, eax
0x18000cacf  jnz     short loc_18000CA7A
0x18000cad1  lea     rax, [rbp+57h+pSid]
0x18000cad5  xor     r9d, r9d; nSubAuthority1
0x18000cad8  mov     [rsp+0D0h+var_80], rax; pSid
0x18000cadd  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000cae1  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x18000cae5  mov     r8d, 12h; nSubAuthority0
0x18000caeb  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x18000caef  mov     dl, 1; nSubAuthorityCount
0x18000caf1  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x18000caf5  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x18000caf9  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x18000cafd  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x18000cb01  call    cs:__imp_AllocateAndInitializeSid
0x18000cb07  test    eax, eax
0x18000cb09  jz      short loc_18000CB6F
0x18000cb0b  mov     rax, [rbp+57h+pSid]
0x18000cb0f  xor     edx, edx; ServerPrincName
0x18000cb11  mov     rcx, [rbp+57h+Binding]; Binding
0x18000cb15  mov     r9d, 0Ah; AuthnSvc
0x18000cb1b  mov     [rbp+57h+var_38], rax
0x18000cb1f  mov     r8d, 6; AuthnLevel
0x18000cb25  lea     rax, [rbp+57h+SecurityQOS]
0x18000cb29  mov     [rbp+57h+SecurityQOS.Capabilities], 1
0x18000cb30  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x18000cb35  mov     dword ptr [rsp+0D0h+StringBinding], 1; AuthzSvc
0x18000cb3d  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x18000cb42  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x18000cb49  mov     [rbp+57h+SecurityQOS.Version], 3
0x18000cb50  mov     [rbp+57h+SecurityQOS.ImpersonationType], 3
0x18000cb57  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000cb5d  mov     rax, [rbp+57h+Binding]
0x18000cb61  mov     ebx, esi
0x18000cb63  mov     [rdi], rax
0x18000cb66  mov     [rbp+57h+Binding], rsi
0x18000cb6a  jmp     loc_18000CA7A
0x18000cb6f  call    cs:__imp_GetLastError
0x18000cb75  mov     ebx, eax
0x18000cb77  jmp     loc_18000CA7A
0x18000cb7c  lea     rcx, [rbp+57h+Binding]; Binding
0x18000cb80  call    cs:__imp_RpcBindingFree
0x18000cb86  jmp     loc_18000CA94
```
