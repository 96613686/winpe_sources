# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x18001a13c`
- end: `0x18001a28f`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `339`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001a038`

## callees

- `0x18001a13c`
- `0x180022b7f`
- `0x180022b9d`
- `0x180022bdf`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a1f7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a1f7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001a249`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001a249`
- `RPCRT4!RpcStringFreeW` at `0x18001a1c2`
- `RPCRT4!RpcStringFreeW` at `0x18001a1c2`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001a19e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001a19e`
- `RPCRT4!RpcBindingFree` at `0x18001a277`
- `RPCRT4!RpcBindingFree` at `0x18001a277`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001a1b6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001a1b6`

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
                  (RPC_WSTR)L"0f738e20-73c0-4ca8-aa6a-8dfef545fea8",
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
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          *(_QWORD *)&SecurityQOS.Capabilities = 1;
          v10 = v4;
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
0x18001a13c  mov     r11, rsp
0x18001a13f  mov     [r11+18h], rbx
0x18001a143  mov     [rsp-18h+cbSid], edx
0x18001a147  mov     [r11+8], rcx
0x18001a14b  push    rbp
0x18001a14c  push    rsi
0x18001a14d  push    rdi
0x18001a14e  mov     rbp, rsp
0x18001a151  sub     rsp, 70h
0x18001a155  xor     eax, eax
0x18001a157  mov     [rbp+StringBinding], 0
0x18001a15f  xorps   xmm0, xmm0
0x18001a162  mov     [rbp+var_10], rax
0x18001a166  mov     [rbp+cbSid], eax
0x18001a169  lea     rdx, ProtSeq; "ncalrpc"
0x18001a170  lea     rax, [rbp+StringBinding]
0x18001a174  mov     [rbp+Binding], 0
0x18001a17c  mov     rsi, r8
0x18001a17f  mov     [r11-60h], rax
0x18001a183  xor     edi, edi
0x18001a185  lea     rcx, ObjUuid; "0f738e20-73c0-4ca8-aa6a-8dfef545fea8"
0x18001a18c  xor     r9d, r9d; Endpoint
0x18001a18f  mov     [r11-68h], rdi
0x18001a193  xor     r8d, r8d; NetworkAddr
0x18001a196  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x18001a19a  movups  [rbp+var_20], xmm0
0x18001a19e  call    cs:__imp_RpcStringBindingComposeW
0x18001a1a4  mov     ebx, eax
0x18001a1a6  test    eax, eax
0x18001a1a8  jnz     loc_18001A264
0x18001a1ae  mov     rcx, [rbp+StringBinding]; StringBinding
0x18001a1b2  lea     rdx, [rbp+Binding]; Binding
0x18001a1b6  call    cs:__imp_RpcBindingFromStringBindingW
0x18001a1bc  lea     rcx, [rbp+StringBinding]; String
0x18001a1c0  mov     ebx, eax
0x18001a1c2  call    cs:__imp_RpcStringFreeW
0x18001a1c8  test    ebx, ebx
0x18001a1ca  jnz     loc_18001A264
0x18001a1d0  lea     edx, [rdi+44h]; uBytes
0x18001a1d3  lea     ecx, [rdi+40h]; uFlags
0x18001a1d6  mov     [rbp+cbSid], edx
0x18001a1d9  call    LocalAlloc_0
0x18001a1de  mov     rdi, rax
0x18001a1e1  test    rax, rax
0x18001a1e4  jnz     short loc_18001A1EB
0x18001a1e6  lea     ebx, [rax+8]
0x18001a1e9  jmp     short loc_18001A264
0x18001a1eb  xor     edx, edx; DomainSid
0x18001a1ed  lea     r9, [rbp+cbSid]; cbSid
0x18001a1f1  mov     r8, rdi; pSid
0x18001a1f4  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001a1f7  call    cs:__imp_CreateWellKnownSid
0x18001a1fd  test    eax, eax
0x18001a1ff  jnz     short loc_18001A20A
0x18001a201  call    GetLastError_0
0x18001a206  mov     ebx, eax
0x18001a208  jmp     short loc_18001A264
0x18001a20a  mov     rcx, [rbp+Binding]; Binding
0x18001a20e  mov     eax, 3
0x18001a213  xor     edx, edx; ServerPrincName
0x18001a215  mov     [rbp+var_30.Version], eax
0x18001a218  mov     [rbp+var_30.ImpersonationType], eax
0x18001a21b  lea     rax, [rbp+var_30]
0x18001a21f  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18001a224  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x18001a22c  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18001a230  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x18001a239  lea     r8d, [rdx+6]; AuthnLevel
0x18001a23d  mov     qword ptr [rbp+var_30.Capabilities], 1
0x18001a245  mov     [rbp+var_10], rdi
0x18001a249  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18001a24f  mov     ebx, eax
0x18001a251  test    eax, eax
0x18001a253  jnz     short loc_18001A264
0x18001a255  mov     rax, [rbp+Binding]
0x18001a259  mov     [rsi], rax
0x18001a25c  mov     [rbp+Binding], 0
0x18001a264  mov     rcx, rdi; hMem
0x18001a267  call    LocalFree_0
0x18001a26c  cmp     [rbp+Binding], 0
0x18001a271  jz      short loc_18001A27D
0x18001a273  lea     rcx, [rbp+Binding]; Binding
0x18001a277  call    cs:__imp_RpcBindingFree
0x18001a27d  mov     eax, ebx
0x18001a27f  mov     rbx, [rsp+70h+arg_10]
0x18001a287  add     rsp, 70h
0x18001a28b  pop     rdi
0x18001a28c  pop     rsi
0x18001a28d  pop     rbp
0x18001a28e  retn
```
