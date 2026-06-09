# PSAMPR_SERVER_NAME_bind

- ea: `0x1800163d0`
- end: `0x18001662d`
- name: `PSAMPR_SERVER_NAME_bind`
- size: `605`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005630`
- `0x180006620`
- `0x180015b44`
- `0x1800163d0`
- `0x18001791d`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001643b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001643b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180016541`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180016541`
- `RPCRT4!RpcBindingFree` at `0x1800165f9`
- `RPCRT4!RpcBindingFree` at `0x1800165f9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800164a8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180016573`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800164a8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180016573`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800164c4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001658b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800164c4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001658b`
- `RPCRT4!RpcStringFreeW` at `0x18001660b`
- `RPCRT4!RpcStringFreeW` at `0x18001660b`
- `RPCRT4!RpcEpResolveBinding` at `0x1800164e2`
- `RPCRT4!RpcEpResolveBinding` at `0x1800164e2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017cfe`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017cfe`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall PSAMPR_SERVER_NAME_bind(unsigned __int16 *Src)
{
  unsigned __int64 v2; // rcx
  unsigned __int8 v3; // si
  RPC_AUTH_IDENTITY_HANDLE *Value; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  RPC_AUTH_IDENTITY_HANDLE *v7; // r14
  unsigned __int16 *v8; // r9
  unsigned __int16 *v9; // r8
  unsigned __int16 *v10; // rdx
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // rdx
  unsigned __int8 v15[4]; // [rsp+40h] [rbp-58h] BYREF
  int v16; // [rsp+44h] [rbp-54h]
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-50h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp-48h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-40h] BYREF

  String = 0;
  v15[0] = 0;
  SecurityQOS = 0;
  Binding = 0;
  if ( Src )
  {
    v2 = -1;
    do
      ++v2;
    while ( Src[v2] );
    if ( (unsigned int)IsLocalServerName(v2, Src, v15) )
      return Binding;
    v3 = v15[0];
  }
  else
  {
    v3 = 1;
  }
  Value = (RPC_AUTH_IDENTITY_HANDLE *)TlsGetValue(dwTlsIndex);
  v7 = Value;
  if ( Value && *Value )
  {
    if ( v3 )
    {
      v8 = L"samss lpc";
      v9 = 0;
      v10 = L"ncalrpc";
    }
    else
    {
      v11 = wcsncmp_0(Src, L"\\\\", 2u);
      v9 = Src + 2;
      if ( v11 )
        v9 = Src;
      v8 = 0;
      v10 = L"ncacn_ip_tcp";
    }
    v12 = RpcStringBindingComposeW(0, v10, v9, v8, 0, &String);
    v16 = v12;
    if ( v12 )
      goto LABEL_27;
    v12 = RpcBindingFromStringBindingW(String, &Binding);
    v16 = v12;
    if ( v12 )
      goto LABEL_27;
    v12 = RpcEpResolveBinding(Binding, qword_18001DF60);
    v16 = v12;
    if ( v12 )
      goto LABEL_27;
    *(_QWORD *)&SecurityQOS.Version = 1;
    *(_QWORD *)&SecurityQOS.IdentityTracking = 0;
    v13 = L"samr";
    if ( v7[1] )
      v13 = (unsigned __int16 *)v7[1];
    v12 = RpcBindingSetAuthInfoExW(Binding, v13, 6u, 10 - (v7[1] != 0), *v7, 0, &SecurityQOS);
  }
  else if ( v3 )
  {
    v12 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"samss lpc", 0, &String);
    v16 = v12;
    if ( v12 )
      goto LABEL_27;
    v12 = RpcBindingFromStringBindingW(String, &Binding);
    v16 = v12;
    if ( v12 )
      goto LABEL_27;
    *(_QWORD *)&SecurityQOS.Version = 1;
    SecurityQOS.IdentityTracking = 1;
    SecurityQOS.ImpersonationType = 3;
    v12 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  }
  else
  {
    v12 = RpcpBindRpc((char *)Src, v5, v6, &Binding);
  }
  v16 = v12;
LABEL_27:
  if ( v12 && Binding )
    RpcBindingFree(&Binding);
  if ( String )
    RpcStringFreeW(&String);
  return Binding;
}

```

## disassembly

```asm
0x1800163d0  push    rbx
0x1800163d2  push    rsi
0x1800163d3  push    rdi
0x1800163d4  push    r14
0x1800163d6  sub     rsp, 78h
0x1800163da  mov     rax, cs:__security_cookie
0x1800163e1  xor     rax, rsp
0x1800163e4  mov     [rsp+98h+var_30], rax
0x1800163e9  mov     rdi, rcx
0x1800163ec  xor     ebx, ebx
0x1800163ee  mov     [rsp+98h+String], rbx
0x1800163f3  mov     [rsp+98h+var_58], bl
0x1800163f7  xorps   xmm0, xmm0
0x1800163fa  movups  xmmword ptr [rsp+98h+var_40.Version], xmm0
0x1800163ff  mov     [rsp+98h+Binding], rbx
0x180016404  test    rcx, rcx
0x180016407  jz      short loc_180016432
0x180016409  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001640d  inc     rcx; unsigned __int64
0x180016410  cmp     [rdi+rcx*2], bx
0x180016414  jnz     short loc_18001640D
0x180016416  lea     r8, [rsp+98h+var_58]; unsigned __int8 *
0x18001641b  mov     rdx, rdi; unsigned __int16 *
0x18001641e  call    ?IsLocalServerName@@YAJ_KPEAGPEAE@Z; IsLocalServerName(unsigned __int64,ushort *,uchar *)
0x180016423  test    eax, eax
0x180016425  jnz     loc_180016611
0x18001642b  mov     sil, [rsp+98h+var_58]
0x180016430  jmp     short loc_180016435
0x180016432  mov     sil, 1
0x180016435  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18001643b  call    cs:__imp_TlsGetValue
0x180016441  mov     r14, rax
0x180016444  test    rax, rax
0x180016447  jz      loc_18001654C
0x18001644d  cmp     [rax], rbx
0x180016450  jz      loc_18001654C
0x180016456  test    sil, sil
0x180016459  jz      short loc_18001646E
0x18001645b  lea     r9, Endpoint; "samss lpc"
0x180016462  xor     r8d, r8d
0x180016465  lea     rdx, aNcalrpc; "ncalrpc"
0x18001646c  jmp     short loc_180016497
0x18001646e  mov     r8d, 2; MaxCount
0x180016474  lea     rdx, String2; "\\\\"
0x18001647b  mov     rcx, rdi; String1
0x18001647e  call    wcsncmp_0
0x180016483  lea     r8, [rdi+4]
0x180016487  test    eax, eax
0x180016489  cmovnz  r8, rdi; NetworkAddr
0x18001648d  xor     r9d, r9d; Endpoint
0x180016490  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180016497  lea     rax, [rsp+98h+String]
0x18001649c  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800164a1  mov     [rsp+98h+Options], rbx; Options
0x1800164a6  xor     ecx, ecx; ObjUuid
0x1800164a8  call    cs:__imp_RpcStringBindingComposeW
0x1800164ae  mov     [rsp+98h+var_54], eax
0x1800164b2  test    eax, eax
0x1800164b4  jnz     loc_1800165E1
0x1800164ba  lea     rdx, [rsp+98h+Binding]; Binding
0x1800164bf  mov     rcx, [rsp+98h+String]; StringBinding
0x1800164c4  call    cs:__imp_RpcBindingFromStringBindingW
0x1800164ca  mov     [rsp+98h+var_54], eax
0x1800164ce  test    eax, eax
0x1800164d0  jnz     loc_1800165E1
0x1800164d6  lea     rdx, qword_18001DF60; IfSpec
0x1800164dd  mov     rcx, [rsp+98h+Binding]; Binding
0x1800164e2  call    cs:__imp_RpcEpResolveBinding
0x1800164e8  mov     [rsp+98h+var_54], eax
0x1800164ec  test    eax, eax
0x1800164ee  jnz     loc_1800165E1
0x1800164f4  mov     qword ptr [rsp+98h+var_40.Version], 1
0x1800164fd  mov     qword ptr [rsp+98h+var_40.IdentityTracking], rbx
0x180016502  mov     rcx, [r14]
0x180016505  mov     rax, [r14+8]
0x180016509  neg     rax
0x18001650c  sbb     r9d, r9d
0x18001650f  add     r9d, 0Ah; AuthnSvc
0x180016513  lea     rdx, aSamr; "samr"
0x18001651a  cmp     [r14+8], rbx
0x18001651e  cmovnz  rdx, [r14+8]; ServerPrincName
0x180016523  lea     rax, [rsp+98h+var_40]
0x180016528  mov     [rsp+98h+SecurityQOS], rax; SecurityQOS
0x18001652d  mov     dword ptr [rsp+98h+StringBinding], ebx; AuthzSvc
0x180016531  mov     [rsp+98h+Options], rcx; AuthIdentity
0x180016536  mov     r8d, 6; AuthnLevel
0x18001653c  mov     rcx, [rsp+98h+Binding]; Binding
0x180016541  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180016547  jmp     loc_1800165DD
0x18001654c  test    sil, sil
0x18001654f  jz      short loc_1800165D0
0x180016551  lea     rax, [rsp+98h+String]
0x180016556  mov     [rsp+98h+StringBinding], rax; StringBinding
0x18001655b  mov     [rsp+98h+Options], rbx; Options
0x180016560  lea     r9, Endpoint; "samss lpc"
0x180016567  xor     r8d, r8d; NetworkAddr
0x18001656a  lea     rdx, aNcalrpc; "ncalrpc"
0x180016571  xor     ecx, ecx; ObjUuid
0x180016573  call    cs:__imp_RpcStringBindingComposeW
0x180016579  mov     [rsp+98h+var_54], eax
0x18001657d  test    eax, eax
0x18001657f  jnz     short loc_1800165E1
0x180016581  lea     rdx, [rsp+98h+Binding]; Binding
0x180016586  mov     rcx, [rsp+98h+String]; StringBinding
0x18001658b  call    cs:__imp_RpcBindingFromStringBindingW
0x180016591  mov     [rsp+98h+var_54], eax
0x180016595  test    eax, eax
0x180016597  jnz     short loc_1800165E1
0x180016599  mov     qword ptr [rsp+98h+var_40.Version], 1
0x1800165a2  mov     [rsp+98h+var_40.IdentityTracking], 1
0x1800165aa  mov     [rsp+98h+var_40.ImpersonationType], 3
0x1800165b2  lea     rax, [rsp+98h+var_40]
0x1800165b7  mov     [rsp+98h+SecurityQOS], rax
0x1800165bc  mov     dword ptr [rsp+98h+StringBinding], ebx
0x1800165c0  mov     [rsp+98h+Options], rbx
0x1800165c5  xor     edx, edx
0x1800165c7  lea     r9d, [rdx+0Ah]
0x1800165cb  jmp     loc_180016536
0x1800165d0  lea     r9, [rsp+98h+Binding]
0x1800165d5  mov     rcx, rdi; Src
0x1800165d8  call    RpcpBindRpc
0x1800165dd  mov     [rsp+98h+var_54], eax
0x1800165e1  jmp     short loc_1800165E9
0x1800165e3  mov     [rsp+98h+var_54], eax
0x1800165e7  xor     ebx, ebx
0x1800165e9  test    eax, eax
0x1800165eb  jz      short loc_1800165FF
0x1800165ed  cmp     [rsp+98h+Binding], rbx
0x1800165f2  jz      short loc_1800165FF
0x1800165f4  lea     rcx, [rsp+98h+Binding]; Binding
0x1800165f9  call    cs:__imp_RpcBindingFree
0x1800165ff  cmp     [rsp+98h+String], rbx
0x180016604  jz      short loc_180016611
0x180016606  lea     rcx, [rsp+98h+String]; String
0x18001660b  call    cs:__imp_RpcStringFreeW
0x180016611  mov     rax, [rsp+98h+Binding]
0x180016616  mov     rcx, [rsp+98h+var_30]
0x18001661b  xor     rcx, rsp; StackCookie
0x18001661e  call    __security_check_cookie
0x180016623  add     rsp, 78h
0x180016627  pop     r14
0x180016629  pop     rdi
0x18001662a  pop     rsi
0x18001662b  pop     rbx
0x18001662c  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
