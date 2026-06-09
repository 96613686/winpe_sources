# CWLIDBinding::Bind(void)

- ea: `0x180050c84`
- end: `0x180050e38`
- name: `?Bind@CWLIDBinding@@QEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(CWLIDBinding *__hidden this)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800473e0`
- `0x180047a84`
- `0x180048158`
- `0x180048b44`
- `0x180048ecc`
- `0x180049c6c`
- `0x180049fd8`
- `0x18004a344`
- `0x18004a6b0`
- `0x18004aa84`
- `0x18004ae78`
- `0x18004c300`
- `0x18004c66c`
- `0x18004c9b8`
- `0x18004cd60`
- `0x18004d0cc`
- `0x18004d78c`
- `0x18004daf8`
- `0x18004e198`
- `0x18004e838`
- `0x18004eba0`
- `0x18004f8d4`
- `0x18004fc38`
- `0x180050304`
- `0x180050724`

## callees

- `0x180002da0`
- `0x180050c0c`
- `0x180050c48`
- `0x180050c84`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180050dea`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180050dea`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050d99`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050d99`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050dbc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050dbc`

## string_xrefs

- `0x180050cf2`: `Security=impersonation dynamic false`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWLIDBinding::Bind(CWLIDBinding *this)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v7; // [rsp+48h] [rbp-B8h]
  __int64 v8; // [rsp+50h] [rbp-B0h]
  RPC_WSTR StringBinding[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE SecurityQOS[24]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v11; // [rsp+88h] [rbp-78h]
  _DWORD *v12; // [rsp+90h] [rbp-70h]
  __int64 v13; // [rsp+98h] [rbp-68h]
  int *v14; // [rsp+A0h] [rbp-60h]
  _DWORD v15[6]; // [rsp+A8h] [rbp-58h] BYREF
  int v16; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v17; // [rsp+C4h] [rbp-3Ch]
  int v18; // [rsp+CCh] [rbp-34h]
  int v19; // [rsp+D0h] [rbp-30h]
  int v20; // [rsp+D4h] [rbp-2Ch]
  int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+DCh] [rbp-24h]
  unsigned int v23; // [rsp+E0h] [rbp-20h]
  int v24; // [rsp+E4h] [rbp-1Ch]
  int v25; // [rsp+E8h] [rbp-18h]
  int v26; // [rsp+ECh] [rbp-14h]
  int v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+F4h] [rbp-Ch]
  int v29; // [rsp+F8h] [rbp-8h]
  int v30; // [rsp+FCh] [rbp-4h]
  int v31; // [rsp+100h] [rbp+0h]

  v16 = -2147221503;
  memset(StringBinding, 0, sizeof(StringBinding));
  v11 = 0;
  v12 = v15;
  v13 = 0;
  v14 = &v16;
  Binding = 0;
  v8 = 0;
  v7 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 20;
  v20 = 3145730;
  v21 = 1;
  v22 = 2621440;
  v23 = 0x80000000;
  v24 = 1537;
  v25 = 83886080;
  v26 = 80;
  v27 = -1342242489;
  v28 = -2042655523;
  v29 = -881969220;
  v30 = -1582099174;
  v31 = 780978283;
  v15[0] = 257;
  v15[1] = 83886080;
  v15[2] = 18;
  *(_DWORD *)SecurityQOS = 5;
  *(_DWORD *)&SecurityQOS[4] = 1;
  *(_OWORD *)&SecurityQOS[8] = 0;
  v2 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         0,
         (RPC_WSTR)L"Security=impersonation dynamic false",
         StringBinding);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2
    || (v2 = RpcBindingFromStringBindingW(StringBinding[0], &Binding), v3 = v2, v4 = v2 <= 0, v2)
    || (v2 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, (RPC_SECURITY_QOS *)SecurityQOS),
        v3 = v2,
        v4 = v2 <= 0,
        v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v3 = 0;
    *(_QWORD *)this = Binding;
    Binding = 0;
    v7 = 0;
  }
  Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(&Binding);
  Auto<unsigned short *,RpcWstrFunctor,DummyContext>::~Auto<unsigned short *,RpcWstrFunctor,DummyContext>(StringBinding);
  return v3;
}

```

## disassembly

```asm
0x180050c84  push    rbp
0x180050c86  push    rbx
0x180050c87  push    rsi
0x180050c88  push    rdi
0x180050c89  lea     rbp, [rsp-28h]
0x180050c8e  sub     rsp, 128h
0x180050c95  mov     rax, cs:__security_cookie
0x180050c9c  xor     rax, rsp
0x180050c9f  mov     [rbp+40h+var_30], rax
0x180050ca3  xor     esi, esi
0x180050ca5  mov     [rbp+40h+var_80], 80040001h
0x180050cac  xorps   xmm0, xmm0
0x180050caf  mov     [rsp+140h+var_E8], rsi
0x180050cb4  lea     rax, [rbp+40h+var_98]
0x180050cb8  mov     [rsp+140h+var_D8], rsi
0x180050cbd  movups  [rbp+40h+var_B8], xmm0
0x180050cc1  mov     qword ptr [rbp+40h+var_B8+8], rax
0x180050cc5  lea     rdx, ProtSeq; "ncalrpc"
0x180050ccc  lea     rax, [rbp+40h+var_80]
0x180050cd0  mov     [rsp+140h+var_E0], rsi
0x180050cd5  movups  [rbp+40h+var_A8], xmm0
0x180050cd9  mov     qword ptr [rbp+40h+var_A8+8], rax
0x180050cdd  mov     rdi, rcx
0x180050ce0  lea     rax, [rsp+140h+var_E8]
0x180050ce5  mov     [rsp+140h+Binding], rsi
0x180050cea  mov     [rsp+140h+StringBinding], rax; StringBinding
0x180050cef  xor     r9d, r9d; Endpoint
0x180050cf2  lea     rax, Options; "Security=impersonation dynamic false"
0x180050cf9  mov     [rsp+140h+var_F0], rsi
0x180050cfe  xor     r8d, r8d; NetworkAddr
0x180050d01  mov     [rsp+140h+Options], rax; Options
0x180050d06  xor     ecx, ecx; ObjUuid
0x180050d08  mov     [rsp+140h+var_F8], rsi
0x180050d0d  mov     [rbp+40h+var_7C], rsi
0x180050d11  mov     [rbp+40h+var_74], esi
0x180050d14  mov     [rbp+40h+var_70], 14h
0x180050d1b  mov     [rbp+40h+var_6C], 300002h
0x180050d22  mov     [rbp+40h+var_68], 1
0x180050d29  mov     [rbp+40h+var_64], 280000h
0x180050d30  mov     [rbp+40h+var_60], 80000000h
0x180050d37  mov     [rbp+40h+var_5C], 601h
0x180050d3e  mov     [rbp+40h+var_58], 5000000h
0x180050d45  mov     [rbp+40h+var_54], 50h ; 'P'
0x180050d4c  mov     [rbp+40h+var_50], 0AFFF0147h
0x180050d53  mov     [rbp+40h+var_4C], 863F8CDDh
0x180050d5a  mov     [rbp+40h+var_48], 0CB6E37BCh
0x180050d61  mov     [rbp+40h+var_44], 0A1B3151Ah
0x180050d68  mov     [rbp+40h+var_40], 2E8CC86Bh
0x180050d6f  mov     [rbp+40h+var_98], 101h
0x180050d76  mov     [rbp+40h+var_94], 5000000h
0x180050d7d  mov     [rbp+40h+var_90], 12h
0x180050d84  mov     dword ptr [rsp+140h+var_D0], 5
0x180050d8c  mov     dword ptr [rsp+140h+var_D0+4], 1
0x180050d94  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x180050d99  call    cs:__imp_RpcStringBindingComposeW
0x180050d9f  mov     ebx, eax
0x180050da1  test    eax, eax
0x180050da3  jz      short loc_180050DB2
0x180050da5  jle     short loc_180050E0A
0x180050da7  movzx   ebx, ax
0x180050daa  or      ebx, 80070000h
0x180050db0  jmp     short loc_180050E0A
0x180050db2  mov     rcx, [rsp+140h+var_E8]; StringBinding
0x180050db7  lea     rdx, [rsp+140h+Binding]; Binding
0x180050dbc  call    cs:__imp_RpcBindingFromStringBindingW
0x180050dc2  mov     ebx, eax
0x180050dc4  test    eax, eax
0x180050dc6  jnz     short loc_180050DA5
0x180050dc8  mov     rcx, [rsp+140h+Binding]; Binding
0x180050dcd  lea     rax, [rsp+140h+var_D0]
0x180050dd2  mov     [rsp+140h+SecurityQOS], rax; SecurityQOS
0x180050dd7  lea     r9d, [rbx+0Ah]; AuthnSvc
0x180050ddb  mov     dword ptr [rsp+140h+StringBinding], esi; AuthzSvc
0x180050ddf  lea     r8d, [rbx+6]; AuthnLevel
0x180050de3  xor     edx, edx; ServerPrincName
0x180050de5  mov     [rsp+140h+Options], rsi; AuthIdentity
0x180050dea  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180050df0  mov     ebx, eax
0x180050df2  test    eax, eax
0x180050df4  jnz     short loc_180050DA5
0x180050df6  mov     rcx, [rsp+140h+Binding]
0x180050dfb  mov     ebx, esi
0x180050dfd  mov     [rdi], rcx
0x180050e00  mov     [rsp+140h+Binding], rsi
0x180050e05  mov     [rsp+140h+var_F8], rsi
0x180050e0a  lea     rcx, [rsp+140h+Binding]
0x180050e0f  call    ??1?$Auto@PEAXVRpcBindingHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(void)
0x180050e14  lea     rcx, [rsp+140h+var_E8]
0x180050e19  call    ??1?$Auto@PEAGVRpcWstrFunctor@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,RpcWstrFunctor,DummyContext>::~Auto<ushort *,RpcWstrFunctor,DummyContext>(void)
0x180050e1e  mov     eax, ebx
0x180050e20  mov     rcx, [rbp+40h+var_30]
0x180050e24  xor     rcx, rsp; StackCookie
0x180050e27  call    __security_check_cookie
0x180050e2c  add     rsp, 128h
0x180050e33  pop     rdi
0x180050e34  pop     rsi
0x180050e35  pop     rbx
0x180050e36  pop     rbp
0x180050e37  retn
```
