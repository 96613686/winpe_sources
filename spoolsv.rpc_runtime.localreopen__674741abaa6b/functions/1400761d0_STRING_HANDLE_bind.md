# STRING_HANDLE_bind

- ea: `0x1400761d0`
- end: `0x1400763e3`
- name: `STRING_HANDLE_bind`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b4b0`
- `0x14000bca0`
- `0x14002d0a0`
- `0x14002d8d0`
- `0x14005c9cc`
- `0x14005dfb4`
- `0x14005e1dc`
- `0x14005e558`
- `0x14005e650`
- `0x14005ea88`
- `0x1400761d0`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140076381`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140076381`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400762cc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400762cc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400762f4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400762f4`
- `RPCRT4!RpcStringFreeW` at `0x14007639c`
- `RPCRT4!RpcStringFreeW` at `0x14007639c`

## string_xrefs

- `0x1400762a7`: `Security=Impersonation Static True`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind(unsigned __int64 a1)
{
  const unsigned __int16 *v1; // r8
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rbx
  unsigned __int16 *Options; // rbx
  unsigned __int16 *v5; // rsi
  unsigned __int16 *RpcOverTcpPortString; // rax
  unsigned __int16 *v7; // rdi
  RPC_STATUS v8; // ebx
  RPC_STATUS v9; // ebx
  int v10; // ebx
  unsigned __int16 *ServerPrincipalName; // rdi
  RPC_WSTR String; // [rsp+40h] [rbp-C0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-B8h] BYREF
  RPC_SECURITY_QOS SecurityQOS[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 NetworkAddr[264]; // [rsp+80h] [rbp-80h] BYREF

  String = 0;
  Binding = 0;
  if ( !a1 || *(_WORD *)a1 != 92 || *(_WORD *)(a1 + 2) != 92 )
    return 0;
  v1 = (const unsigned __int16 *)(a1 + 4);
  LODWORD(a1) = 0;
  if ( *v1 )
  {
    do
    {
      if ( v1[(unsigned int)a1] == 92 )
        break;
      a1 = (unsigned int)(a1 + 1);
    }
    while ( v1[a1] );
    if ( (unsigned int)a1 >= 0x106 )
      return 0;
  }
  v2 = (unsigned int)a1;
  StringCchCopyNW(NetworkAddr, 0x106u, v1, (unsigned int)a1);
  v3 = v2;
  if ( v3 >= 262 )
    _report_rangecheckfailure();
  NetworkAddr[v3] = 0;
  if ( (unsigned int)UseNamedPipeProtocol() )
  {
    v5 = L"ncacn_np";
    RpcOverTcpPortString = (unsigned __int16 *)AllocSplStr(L"\\pipe\\spoolss");
    Options = L"Security=Impersonation Static True";
  }
  else
  {
    Options = 0;
    v5 = L"ncacn_ip_tcp";
    RpcOverTcpPortString = GetRpcOverTcpPortString();
  }
  v7 = RpcOverTcpPortString;
  v8 = RpcStringBindingComposeW(0, v5, NetworkAddr, RpcOverTcpPortString, Options, &String);
  DllFreeSplStr(v7);
  if ( v8 )
    return 0;
  v9 = RpcBindingFromStringBindingW(String, &Binding);
  if ( !v9 )
  {
    if ( (unsigned int)IsAuthenticationRequiredForRpc() )
    {
      SecurityQOS[0].Version = 3;
      memset(&SecurityQOS[1].Capabilities, 0, 20);
      *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
      *(_QWORD *)&SecurityQOS[0].Capabilities = 1;
      v10 = ForceKerberosAuthentication();
      ServerPrincipalName = GetServerPrincipalName(NetworkAddr);
      v9 = RpcBindingSetAuthInfoExW(Binding, ServerPrincipalName, 6u, v10 != 0 ? 16 : 9, 0, -(v10 != 0), SecurityQOS);
      DllFreeSplStr(ServerPrincipalName);
    }
  }
  RpcStringFreeW(&String);
  if ( v9 )
    return 0;
  else
    return Binding;
}

```

## disassembly

```asm
0x1400761d0  mov     [rsp-8+arg_8], rbx
0x1400761d5  mov     [rsp-8+arg_10], rsi
0x1400761da  push    rbp
0x1400761db  push    rdi
0x1400761dc  push    r14
0x1400761de  lea     rbp, [rsp-1A0h]
0x1400761e6  sub     rsp, 2A0h
0x1400761ed  mov     rax, cs:__security_cookie
0x1400761f4  xor     rax, rsp
0x1400761f7  mov     [rbp+1B0h+var_20], rax
0x1400761fe  xor     r14d, r14d
0x140076201  mov     [rsp+2B0h+String], r14
0x140076206  mov     [rsp+2B0h+Binding], r14
0x14007620b  test    rcx, rcx
0x14007620e  jz      loc_1400763B9
0x140076214  cmp     word ptr [rcx], 5Ch ; '\'
0x140076218  jnz     loc_1400763B9
0x14007621e  cmp     word ptr [rcx+2], 5Ch ; '\'
0x140076223  jnz     loc_1400763B9
0x140076229  lea     r8, [rcx+4]; unsigned __int16 *
0x14007622d  mov     edx, 106h; unsigned __int64
0x140076232  mov     ecx, r14d
0x140076235  cmp     [r8], r14w
0x140076239  jz      short loc_140076256
0x14007623b  mov     eax, ecx
0x14007623d  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140076243  jz      short loc_14007624E
0x140076245  inc     ecx
0x140076247  cmp     [r8+rcx*2], r14w
0x14007624c  jnz     short loc_14007623B
0x14007624e  cmp     ecx, edx
0x140076250  jnb     loc_1400763B9
0x140076256  mov     ebx, ecx
0x140076258  mov     r9d, ecx; unsigned __int64
0x14007625b  lea     rcx, [rbp+1B0h+NetworkAddr]; unsigned __int16 *
0x14007625f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140076264  add     rbx, rbx
0x140076267  cmp     rbx, 20Ch
0x14007626e  jnb     loc_1400763B3
0x140076274  mov     [rbp+rbx+1B0h+NetworkAddr], r14w
0x14007627a  call    ?UseNamedPipeProtocol@@YAHXZ; UseNamedPipeProtocol(void)
0x14007627f  test    eax, eax
0x140076281  jnz     short loc_140076294
0x140076283  mov     rbx, r14
0x140076286  lea     rsi, ProtSeq; "ncacn_ip_tcp"
0x14007628d  call    ?GetRpcOverTcpPortString@@YAPEAGXZ; GetRpcOverTcpPortString(void)
0x140076292  jmp     short loc_1400762AE
0x140076294  lea     rcx, aPipeSpoolss; "\\pipe\\spoolss"
0x14007629b  lea     rsi, aNcacnNp; "ncacn_np"
0x1400762a2  call    AllocSplStr
0x1400762a7  lea     rbx, aSecurityImpers; "Security=Impersonation Static True"
0x1400762ae  mov     rdi, rax
0x1400762b1  lea     r8, [rbp+1B0h+NetworkAddr]; NetworkAddr
0x1400762b5  lea     rax, [rsp+2B0h+String]
0x1400762ba  mov     r9, rdi; Endpoint
0x1400762bd  mov     [rsp+2B0h+StringBinding], rax; StringBinding
0x1400762c2  mov     rdx, rsi; ProtSeq
0x1400762c5  xor     ecx, ecx; ObjUuid
0x1400762c7  mov     [rsp+2B0h+Options], rbx; Options
0x1400762cc  call    cs:__imp_RpcStringBindingComposeW
0x1400762d3  nop     dword ptr [rax+rax+00h]
0x1400762d8  mov     rcx, rdi
0x1400762db  mov     ebx, eax
0x1400762dd  call    DllFreeSplStr
0x1400762e2  test    ebx, ebx
0x1400762e4  jnz     loc_1400763B9
0x1400762ea  mov     rcx, [rsp+2B0h+String]; StringBinding
0x1400762ef  lea     rdx, [rsp+2B0h+Binding]; Binding
0x1400762f4  call    cs:__imp_RpcBindingFromStringBindingW
0x1400762fb  nop     dword ptr [rax+rax+00h]
0x140076300  mov     ebx, eax
0x140076302  test    eax, eax
0x140076304  jnz     loc_140076397
0x14007630a  call    ?IsAuthenticationRequiredForRpc@@YAHXZ; IsAuthenticationRequiredForRpc(void)
0x14007630f  test    eax, eax
0x140076311  jz      loc_140076397
0x140076317  lea     eax, [rbx+3]
0x14007631a  mov     [rsp+2B0h+var_23C], r14d
0x14007631f  xorps   xmm0, xmm0
0x140076322  mov     dword ptr [rsp+2B0h+var_260], eax
0x140076326  movdqu  [rsp+2B0h+var_24C], xmm0
0x14007632c  mov     qword ptr [rsp+2B0h+var_260+0Ch], rax
0x140076331  mov     qword ptr [rsp+2B0h+var_260+4], 1
0x14007633a  call    ?ForceKerberosAuthentication@@YAHXZ; ForceKerberosAuthentication(void)
0x14007633f  lea     rcx, [rbp+1B0h+NetworkAddr]; unsigned __int16 *
0x140076343  mov     ebx, eax
0x140076345  call    ?GetServerPrincipalName@@YAPEAGPEAG@Z; GetServerPrincipalName(ushort *)
0x14007634a  mov     ecx, ebx
0x14007634c  mov     rdi, rax
0x14007634f  neg     ecx
0x140076351  lea     rax, [rsp+2B0h+var_260]
0x140076356  mov     rcx, [rsp+2B0h+Binding]; Binding
0x14007635b  mov     r8d, 6; AuthnLevel
0x140076361  sbb     edx, edx
0x140076363  mov     [rsp+2B0h+SecurityQOS], rax; SecurityQOS
0x140076368  mov     dword ptr [rsp+2B0h+StringBinding], edx; AuthzSvc
0x14007636c  neg     ebx
0x14007636e  mov     rdx, rdi; ServerPrincName
0x140076371  mov     [rsp+2B0h+Options], r14; AuthIdentity
0x140076376  sbb     r9d, r9d
0x140076379  and     r9d, 7
0x14007637d  add     r9d, 9; AuthnSvc
0x140076381  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140076388  nop     dword ptr [rax+rax+00h]
0x14007638d  mov     rcx, rdi
0x140076390  mov     ebx, eax
0x140076392  call    DllFreeSplStr
0x140076397  lea     rcx, [rsp+2B0h+String]; String
0x14007639c  call    cs:__imp_RpcStringFreeW
0x1400763a3  nop     dword ptr [rax+rax+00h]
0x1400763a8  test    ebx, ebx
0x1400763aa  jnz     short loc_1400763B9
0x1400763ac  mov     rax, [rsp+2B0h+Binding]
0x1400763b1  jmp     short loc_1400763BB
0x1400763b3  call    __report_rangecheckfailure
0x1400763b9  xor     eax, eax
0x1400763bb  mov     rcx, [rbp+1B0h+var_20]
0x1400763c2  xor     rcx, rsp; StackCookie
0x1400763c5  call    __security_check_cookie
0x1400763ca  lea     r11, [rsp+2B0h+var_10]
0x1400763d2  mov     rbx, [r11+28h]
0x1400763d6  mov     rsi, [r11+30h]
0x1400763da  mov     rsp, r11
0x1400763dd  pop     r14
0x1400763df  pop     rdi
0x1400763e0  pop     rbp
0x1400763e1  retn
```
