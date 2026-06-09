# CWLIDBinding::Bind(void)

- ea: `0x18000f870`
- end: `0x18000fa2c`
- name: `?Bind@CWLIDBinding@@QEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(CWLIDBinding *__hidden this)`
- caller_count: `24`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006c70`
- `0x18000ceb0`
- `0x180010cc4`
- `0x1800441f8`
- `0x180044874`
- `0x180044c08`
- `0x180045648`
- `0x180046034`
- `0x1800463a0`
- `0x18004670c`
- `0x180046d90`
- `0x180047148`
- `0x1800474f8`
- `0x18004789c`
- `0x180047c00`
- `0x180047f6c`
- `0x1800482b8`
- `0x180048c8c`
- `0x180048ff8`
- `0x180049340`
- `0x180049a00`
- `0x18004a0c4`
- `0x18004adb0`
- `0x18004b100`

## callees

- `0x18000f870`
- `0x18000fa34`
- `0x18000fa70`
- `0x18001a0d0`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000f9d1`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000f9d1`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000f985`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000f985`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000f99f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000f99f`

## string_xrefs

- `0x18000f8de`: `Security=impersonation dynamic false`

## pseudocode

```c
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
0x18000f870  push    rbp
0x18000f872  push    rbx
0x18000f873  push    rsi
0x18000f874  push    rdi
0x18000f875  lea     rbp, [rsp-28h]
0x18000f87a  sub     rsp, 128h
0x18000f881  mov     rax, cs:__security_cookie
0x18000f888  xor     rax, rsp
0x18000f88b  mov     [rbp+40h+var_30], rax
0x18000f88f  xor     esi, esi
0x18000f891  mov     [rbp+40h+var_80], 80040001h
0x18000f898  xorps   xmm0, xmm0
0x18000f89b  mov     [rsp+140h+var_E8], rsi
0x18000f8a0  lea     rax, [rbp+40h+var_98]
0x18000f8a4  mov     [rsp+140h+var_D8], rsi
0x18000f8a9  movups  [rbp+40h+var_B8], xmm0
0x18000f8ad  mov     qword ptr [rbp+40h+var_B8+8], rax
0x18000f8b1  lea     rdx, ProtSeq; "ncalrpc"
0x18000f8b8  lea     rax, [rbp+40h+var_80]
0x18000f8bc  mov     [rsp+140h+var_E0], rsi
0x18000f8c1  movups  [rbp+40h+var_A8], xmm0
0x18000f8c5  mov     qword ptr [rbp+40h+var_A8+8], rax
0x18000f8c9  mov     rdi, rcx
0x18000f8cc  lea     rax, [rsp+140h+var_E8]
0x18000f8d1  mov     [rsp+140h+Binding], rsi
0x18000f8d6  mov     [rsp+140h+StringBinding], rax; StringBinding
0x18000f8db  xor     r9d, r9d; Endpoint
0x18000f8de  lea     rax, Options; "Security=impersonation dynamic false"
0x18000f8e5  mov     [rsp+140h+var_F0], rsi
0x18000f8ea  xor     r8d, r8d; NetworkAddr
0x18000f8ed  mov     [rsp+140h+Options], rax; Options
0x18000f8f2  xor     ecx, ecx; ObjUuid
0x18000f8f4  mov     [rsp+140h+var_F8], rsi
0x18000f8f9  mov     [rbp+40h+var_7C], rsi
0x18000f8fd  mov     [rbp+40h+var_74], esi
0x18000f900  mov     [rbp+40h+var_70], 14h
0x18000f907  mov     [rbp+40h+var_6C], 300002h
0x18000f90e  mov     [rbp+40h+var_68], 1
0x18000f915  mov     [rbp+40h+var_64], 280000h
0x18000f91c  mov     [rbp+40h+var_60], 80000000h
0x18000f923  mov     [rbp+40h+var_5C], 601h
0x18000f92a  mov     [rbp+40h+var_58], 5000000h
0x18000f931  mov     [rbp+40h+var_54], 50h ; 'P'
0x18000f938  mov     [rbp+40h+var_50], 0AFFF0147h
0x18000f93f  mov     [rbp+40h+var_4C], 863F8CDDh
0x18000f946  mov     [rbp+40h+var_48], 0CB6E37BCh
0x18000f94d  mov     [rbp+40h+var_44], 0A1B3151Ah
0x18000f954  mov     [rbp+40h+var_40], 2E8CC86Bh
0x18000f95b  mov     [rbp+40h+var_98], 101h
0x18000f962  mov     [rbp+40h+var_94], 5000000h
0x18000f969  mov     [rbp+40h+var_90], 12h
0x18000f970  mov     dword ptr [rsp+140h+var_D0], 5
0x18000f978  mov     dword ptr [rsp+140h+var_D0+4], 1
0x18000f980  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x18000f985  call    cs:__imp_RpcStringBindingComposeW
0x18000f98b  mov     ebx, eax
0x18000f98d  test    eax, eax
0x18000f98f  jnz     loc_18000FA1F
0x18000f995  mov     rcx, [rsp+140h+var_E8]; StringBinding
0x18000f99a  lea     rdx, [rsp+140h+Binding]; Binding
0x18000f99f  call    cs:__imp_RpcBindingFromStringBindingW
0x18000f9a5  mov     ebx, eax
0x18000f9a7  test    eax, eax
0x18000f9a9  jnz     short loc_18000FA1F
0x18000f9ab  mov     rcx, [rsp+140h+Binding]; Binding
0x18000f9b0  lea     rax, [rsp+140h+var_D0]
0x18000f9b5  mov     [rsp+140h+SecurityQOS], rax; SecurityQOS
0x18000f9ba  xor     edx, edx; ServerPrincName
0x18000f9bc  mov     dword ptr [rsp+140h+StringBinding], esi; AuthzSvc
0x18000f9c0  mov     r9d, 0Ah; AuthnSvc
0x18000f9c6  mov     r8d, 6; AuthnLevel
0x18000f9cc  mov     [rsp+140h+Options], rsi; AuthIdentity
0x18000f9d1  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000f9d7  mov     ebx, eax
0x18000f9d9  test    eax, eax
0x18000f9db  jnz     short loc_18000FA1F
0x18000f9dd  mov     rax, [rsp+140h+Binding]
0x18000f9e2  mov     ebx, esi
0x18000f9e4  mov     [rdi], rax
0x18000f9e7  mov     [rsp+140h+Binding], rsi
0x18000f9ec  mov     [rsp+140h+var_F8], rsi
0x18000f9f1  lea     rcx, [rsp+140h+Binding]
0x18000f9f6  call    ??1?$Auto@PEAXVRpcBindingHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(void)
0x18000f9fb  lea     rcx, [rsp+140h+var_E8]
0x18000fa00  call    ??1?$Auto@PEAGVRpcWstrFunctor@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,RpcWstrFunctor,DummyContext>::~Auto<ushort *,RpcWstrFunctor,DummyContext>(void)
0x18000fa05  mov     eax, ebx
0x18000fa07  mov     rcx, [rbp+40h+var_30]
0x18000fa0b  xor     rcx, rsp; StackCookie
0x18000fa0e  call    __security_check_cookie
0x18000fa13  add     rsp, 128h
0x18000fa1a  pop     rdi
0x18000fa1b  pop     rsi
0x18000fa1c  pop     rbx
0x18000fa1d  pop     rbp
0x18000fa1e  retn
0x18000fa1f  jle     short loc_18000F9F1
0x18000fa21  movzx   ebx, ax
0x18000fa24  or      ebx, 80070000h
0x18000fa2a  jmp     short loc_18000F9F1
```
