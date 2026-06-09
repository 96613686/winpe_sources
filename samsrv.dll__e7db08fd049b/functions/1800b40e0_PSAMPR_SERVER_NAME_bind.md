# PSAMPR_SERVER_NAME_bind

- ea: `0x1800b40e0`
- end: `0x1800b433d`
- name: `PSAMPR_SERVER_NAME_bind`
- size: `605`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002cd80`
- `0x1800b3ac0`
- `0x1800b40e0`
- `0x1800b9eb8`
- `0x1800bb770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b414b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b414b`
- `RPCRT4!RpcEpResolveBinding` at `0x1800b41f2`
- `RPCRT4!RpcEpResolveBinding` at `0x1800b41f2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b41d4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b429b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b41d4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b429b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b41b8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b4283`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b41b8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b4283`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bba18`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bba18`
- `RPCRT4!RpcBindingFree` at `0x1800b4309`
- `RPCRT4!RpcBindingFree` at `0x1800b4309`
- `RPCRT4!RpcStringFreeW` at `0x1800b431b`
- `RPCRT4!RpcStringFreeW` at `0x1800b431b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b4251`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b4251`

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
    v12 = RpcEpResolveBinding(Binding, qword_1800C86C0);
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
0x1800b40e0  push    rbx
0x1800b40e2  push    rsi
0x1800b40e3  push    rdi
0x1800b40e4  push    r14
0x1800b40e6  sub     rsp, 78h
0x1800b40ea  mov     rax, cs:__security_cookie
0x1800b40f1  xor     rax, rsp
0x1800b40f4  mov     [rsp+98h+var_30], rax
0x1800b40f9  mov     rdi, rcx
0x1800b40fc  xor     ebx, ebx
0x1800b40fe  mov     [rsp+98h+String], rbx
0x1800b4103  mov     [rsp+98h+var_58], bl
0x1800b4107  xorps   xmm0, xmm0
0x1800b410a  movups  xmmword ptr [rsp+98h+var_40.Version], xmm0
0x1800b410f  mov     [rsp+98h+Binding], rbx
0x1800b4114  test    rcx, rcx
0x1800b4117  jz      short loc_1800B4142
0x1800b4119  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b411d  inc     rcx; unsigned __int64
0x1800b4120  cmp     [rdi+rcx*2], bx
0x1800b4124  jnz     short loc_1800B411D
0x1800b4126  lea     r8, [rsp+98h+var_58]; unsigned __int8 *
0x1800b412b  mov     rdx, rdi; unsigned __int16 *
0x1800b412e  call    ?IsLocalServerName@@YAJ_KPEAGPEAE@Z; IsLocalServerName(unsigned __int64,ushort *,uchar *)
0x1800b4133  test    eax, eax
0x1800b4135  jnz     loc_1800B4321
0x1800b413b  mov     sil, [rsp+98h+var_58]
0x1800b4140  jmp     short loc_1800B4145
0x1800b4142  mov     sil, 1
0x1800b4145  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800b414b  call    cs:__imp_TlsGetValue
0x1800b4151  mov     r14, rax
0x1800b4154  test    rax, rax
0x1800b4157  jz      loc_1800B425C
0x1800b415d  cmp     [rax], rbx
0x1800b4160  jz      loc_1800B425C
0x1800b4166  test    sil, sil
0x1800b4169  jz      short loc_1800B417E
0x1800b416b  lea     r9, Endpoint; "samss lpc"
0x1800b4172  xor     r8d, r8d
0x1800b4175  lea     rdx, aNcalrpc; "ncalrpc"
0x1800b417c  jmp     short loc_1800B41A7
0x1800b417e  mov     r8d, 2; MaxCount
0x1800b4184  lea     rdx, asc_1800D5A3C; "\\\\"
0x1800b418b  mov     rcx, rdi; String1
0x1800b418e  call    wcsncmp_0
0x1800b4193  lea     r8, [rdi+4]
0x1800b4197  test    eax, eax
0x1800b4199  cmovnz  r8, rdi; NetworkAddr
0x1800b419d  xor     r9d, r9d; Endpoint
0x1800b41a0  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1800b41a7  lea     rax, [rsp+98h+String]
0x1800b41ac  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800b41b1  mov     [rsp+98h+Options], rbx; Options
0x1800b41b6  xor     ecx, ecx; ObjUuid
0x1800b41b8  call    cs:__imp_RpcStringBindingComposeW
0x1800b41be  mov     [rsp+98h+var_54], eax
0x1800b41c2  test    eax, eax
0x1800b41c4  jnz     loc_1800B42F1
0x1800b41ca  lea     rdx, [rsp+98h+Binding]; Binding
0x1800b41cf  mov     rcx, [rsp+98h+String]; StringBinding
0x1800b41d4  call    cs:__imp_RpcBindingFromStringBindingW
0x1800b41da  mov     [rsp+98h+var_54], eax
0x1800b41de  test    eax, eax
0x1800b41e0  jnz     loc_1800B42F1
0x1800b41e6  lea     rdx, qword_1800C86C0; IfSpec
0x1800b41ed  mov     rcx, [rsp+98h+Binding]; Binding
0x1800b41f2  call    cs:__imp_RpcEpResolveBinding
0x1800b41f8  mov     [rsp+98h+var_54], eax
0x1800b41fc  test    eax, eax
0x1800b41fe  jnz     loc_1800B42F1
0x1800b4204  mov     qword ptr [rsp+98h+var_40.Version], 1
0x1800b420d  mov     qword ptr [rsp+98h+var_40.IdentityTracking], rbx
0x1800b4212  mov     rcx, [r14]
0x1800b4215  mov     rax, [r14+8]
0x1800b4219  neg     rax
0x1800b421c  sbb     r9d, r9d
0x1800b421f  add     r9d, 0Ah; AuthnSvc
0x1800b4223  lea     rdx, aSamr; "samr"
0x1800b422a  cmp     [r14+8], rbx
0x1800b422e  cmovnz  rdx, [r14+8]; ServerPrincName
0x1800b4233  lea     rax, [rsp+98h+var_40]
0x1800b4238  mov     [rsp+98h+SecurityQOS], rax; SecurityQOS
0x1800b423d  mov     dword ptr [rsp+98h+StringBinding], ebx; AuthzSvc
0x1800b4241  mov     [rsp+98h+Options], rcx; AuthIdentity
0x1800b4246  mov     r8d, 6; AuthnLevel
0x1800b424c  mov     rcx, [rsp+98h+Binding]; Binding
0x1800b4251  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800b4257  jmp     loc_1800B42ED
0x1800b425c  test    sil, sil
0x1800b425f  jz      short loc_1800B42E0
0x1800b4261  lea     rax, [rsp+98h+String]
0x1800b4266  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800b426b  mov     [rsp+98h+Options], rbx; Options
0x1800b4270  lea     r9, Endpoint; "samss lpc"
0x1800b4277  xor     r8d, r8d; NetworkAddr
0x1800b427a  lea     rdx, aNcalrpc; "ncalrpc"
0x1800b4281  xor     ecx, ecx; ObjUuid
0x1800b4283  call    cs:__imp_RpcStringBindingComposeW
0x1800b4289  mov     [rsp+98h+var_54], eax
0x1800b428d  test    eax, eax
0x1800b428f  jnz     short loc_1800B42F1
0x1800b4291  lea     rdx, [rsp+98h+Binding]; Binding
0x1800b4296  mov     rcx, [rsp+98h+String]; StringBinding
0x1800b429b  call    cs:__imp_RpcBindingFromStringBindingW
0x1800b42a1  mov     [rsp+98h+var_54], eax
0x1800b42a5  test    eax, eax
0x1800b42a7  jnz     short loc_1800B42F1
0x1800b42a9  mov     qword ptr [rsp+98h+var_40.Version], 1
0x1800b42b2  mov     [rsp+98h+var_40.IdentityTracking], 1
0x1800b42ba  mov     [rsp+98h+var_40.ImpersonationType], 3
0x1800b42c2  lea     rax, [rsp+98h+var_40]
0x1800b42c7  mov     [rsp+98h+SecurityQOS], rax
0x1800b42cc  mov     dword ptr [rsp+98h+StringBinding], ebx
0x1800b42d0  mov     [rsp+98h+Options], rbx
0x1800b42d5  xor     edx, edx
0x1800b42d7  lea     r9d, [rdx+0Ah]
0x1800b42db  jmp     loc_1800B4246
0x1800b42e0  lea     r9, [rsp+98h+Binding]
0x1800b42e5  mov     rcx, rdi; Src
0x1800b42e8  call    RpcpBindRpc
0x1800b42ed  mov     [rsp+98h+var_54], eax
0x1800b42f1  jmp     short loc_1800B42F9
0x1800b42f3  mov     [rsp+98h+var_54], eax
0x1800b42f7  xor     ebx, ebx
0x1800b42f9  test    eax, eax
0x1800b42fb  jz      short loc_1800B430F
0x1800b42fd  cmp     [rsp+98h+Binding], rbx
0x1800b4302  jz      short loc_1800B430F
0x1800b4304  lea     rcx, [rsp+98h+Binding]; Binding
0x1800b4309  call    cs:__imp_RpcBindingFree
0x1800b430f  cmp     [rsp+98h+String], rbx
0x1800b4314  jz      short loc_1800B4321
0x1800b4316  lea     rcx, [rsp+98h+String]; String
0x1800b431b  call    cs:__imp_RpcStringFreeW
0x1800b4321  mov     rax, [rsp+98h+Binding]
0x1800b4326  mov     rcx, [rsp+98h+var_30]
0x1800b432b  xor     rcx, rsp; StackCookie
0x1800b432e  call    __security_check_cookie
0x1800b4333  add     rsp, 78h
0x1800b4337  pop     r14
0x1800b4339  pop     rdi
0x1800b433a  pop     rsi
0x1800b433b  pop     rbx
0x1800b433c  retn
0x1800bba0a  push    rbp
0x1800bba0c  sub     rsp, 40h
0x1800bba10  mov     rbp, rdx
0x1800bba13  mov     rcx, [rcx]
0x1800bba16  mov     ecx, [rcx]; ExceptionCode
0x1800bba18  call    cs:__imp_I_RpcExceptionFilter
0x1800bba1e  nop
0x1800bba1f  add     rsp, 40h
0x1800bba23  pop     rbp
0x1800bba24  retn
```
