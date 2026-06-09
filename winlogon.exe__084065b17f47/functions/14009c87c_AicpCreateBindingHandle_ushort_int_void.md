# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x14009c87c`
- end: `0x14009c9d0`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `340`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14009c5b8`

## callees

- `0x140054845`
- `0x1400548fa`
- `0x140054906`
- `0x14009c87c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14009c937`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14009c937`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14009c8f6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14009c8f6`
- `RPCRT4!RpcStringFreeW` at `0x14009c902`
- `RPCRT4!RpcStringFreeW` at `0x14009c902`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14009c98a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14009c98a`
- `RPCRT4!RpcBindingFree` at `0x14009c9b8`
- `RPCRT4!RpcBindingFree` at `0x14009c9b8`
- `RPCRT4!RpcStringBindingComposeW` at `0x14009c8de`
- `RPCRT4!RpcStringBindingComposeW` at `0x14009c8de`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  DWORD LastError_0; // ebx
  HLOCAL v6; // rax
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v9; // [rsp+50h] [rbp-20h]
  void *v10; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  DWORD cbSid; // [rsp+98h] [rbp+28h] BYREF
  RPC_WSTR StringBinding; // [rsp+A8h] [rbp+38h] BYREF

  StringBinding = 0;
  v10 = 0;
  cbSid = 0;
  Binding = 0;
  v4 = 0;
  SecurityQOS = 0;
  v9 = 0;
  LastError_0 = RpcStringBindingComposeW(
                  (RPC_WSTR)L"201ef99a-7fa0-444c-9399-19ba84f12a1a",
                  (RPC_WSTR)L"ncalrpc",
                  0,
                  0,
                  0,
                  &StringBinding);
  if ( !LastError_0 )
  {
    LastError_0 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !LastError_0 )
    {
      cbSid = 68;
      v6 = LocalAlloc_0(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          v10 = v4;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          LastError_0 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastError_0 )
          {
            *a3 = Binding;
            Binding = 0;
          }
        }
        else
        {
          LastError_0 = GetLastError_0();
        }
      }
      else
      {
        LastError_0 = 8;
      }
    }
  }
  LocalFree_0(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError_0;
}

```

## disassembly

```asm
0x14009c87c  mov     r11, rsp
0x14009c87f  mov     [r11+18h], rbx
0x14009c883  mov     [rsp-18h+cbSid], edx
0x14009c887  mov     [r11+8], rcx
0x14009c88b  push    rbp
0x14009c88c  push    rsi
0x14009c88d  push    rdi
0x14009c88e  mov     rbp, rsp
0x14009c891  sub     rsp, 70h
0x14009c895  xor     eax, eax
0x14009c897  mov     [rbp+StringBinding], 0
0x14009c89f  xorps   xmm0, xmm0
0x14009c8a2  mov     [rbp+var_10], rax
0x14009c8a6  mov     [rbp+cbSid], eax
0x14009c8a9  lea     rdx, ProtSeq; "ncalrpc"
0x14009c8b0  lea     rax, [rbp+StringBinding]
0x14009c8b4  mov     [rbp+Binding], 0
0x14009c8bc  mov     rsi, r8
0x14009c8bf  mov     [r11-60h], rax
0x14009c8c3  xor     edi, edi
0x14009c8c5  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x14009c8cc  xor     r9d, r9d; Endpoint
0x14009c8cf  mov     [r11-68h], rdi
0x14009c8d3  xor     r8d, r8d; NetworkAddr
0x14009c8d6  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x14009c8da  movups  [rbp+var_20], xmm0
0x14009c8de  call    cs:__imp_RpcStringBindingComposeW
0x14009c8e4  mov     ebx, eax
0x14009c8e6  test    eax, eax
0x14009c8e8  jnz     loc_14009C9A5
0x14009c8ee  mov     rcx, [rbp+StringBinding]; StringBinding
0x14009c8f2  lea     rdx, [rbp+Binding]; Binding
0x14009c8f6  call    cs:__imp_RpcBindingFromStringBindingW
0x14009c8fc  lea     rcx, [rbp+StringBinding]; String
0x14009c900  mov     ebx, eax
0x14009c902  call    cs:__imp_RpcStringFreeW
0x14009c908  test    ebx, ebx
0x14009c90a  jnz     loc_14009C9A5
0x14009c910  lea     edx, [rdi+44h]; uBytes
0x14009c913  lea     ecx, [rdi+40h]; uFlags
0x14009c916  mov     [rbp+cbSid], edx
0x14009c919  call    LocalAlloc_0
0x14009c91e  mov     rdi, rax
0x14009c921  test    rax, rax
0x14009c924  jnz     short loc_14009C92B
0x14009c926  lea     ebx, [rax+8]
0x14009c929  jmp     short loc_14009C9A5
0x14009c92b  xor     edx, edx; DomainSid
0x14009c92d  lea     r9, [rbp+cbSid]; cbSid
0x14009c931  mov     r8, rdi; pSid
0x14009c934  lea     ecx, [rdx+16h]; WellKnownSidType
0x14009c937  call    cs:__imp_CreateWellKnownSid
0x14009c93d  test    eax, eax
0x14009c93f  jnz     short loc_14009C94A
0x14009c941  call    GetLastError_0
0x14009c946  mov     ebx, eax
0x14009c948  jmp     short loc_14009C9A5
0x14009c94a  mov     ecx, 3
0x14009c94f  mov     [rbp+var_10], rdi
0x14009c953  mov     [rbp+var_30.Version], ecx
0x14009c956  xor     edx, edx; ServerPrincName
0x14009c958  mov     [rbp+var_30.ImpersonationType], ecx
0x14009c95b  lea     eax, [rcx-2]
0x14009c95e  mov     [rbp+var_30.Capabilities], eax
0x14009c961  lea     r9d, [rcx+7]; AuthnSvc
0x14009c965  mov     [rbp+var_30.IdentityTracking], eax
0x14009c968  lea     r8d, [rcx+3]; AuthnLevel
0x14009c96c  mov     rcx, [rbp+Binding]; Binding
0x14009c970  lea     rax, [rbp+var_30]
0x14009c974  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x14009c979  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x14009c981  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x14009c98a  call    cs:__imp_RpcBindingSetAuthInfoExW
0x14009c990  mov     ebx, eax
0x14009c992  test    eax, eax
0x14009c994  jnz     short loc_14009C9A5
0x14009c996  mov     rax, [rbp+Binding]
0x14009c99a  mov     [rsi], rax
0x14009c99d  mov     [rbp+Binding], 0
0x14009c9a5  mov     rcx, rdi; hMem
0x14009c9a8  call    LocalFree_0
0x14009c9ad  cmp     [rbp+Binding], 0
0x14009c9b2  jz      short loc_14009C9BE
0x14009c9b4  lea     rcx, [rbp+Binding]; Binding
0x14009c9b8  call    cs:__imp_RpcBindingFree
0x14009c9be  mov     eax, ebx
0x14009c9c0  mov     rbx, [rsp+70h+arg_10]
0x14009c9c8  add     rsp, 70h
0x14009c9cc  pop     rdi
0x14009c9cd  pop     rsi
0x14009c9ce  pop     rbp
0x14009c9cf  retn
```
