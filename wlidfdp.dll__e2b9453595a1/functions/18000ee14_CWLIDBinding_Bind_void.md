# CWLIDBinding::Bind(void)

- ea: `0x18000ee14`
- end: `0x18000efc8`
- name: `?Bind@CWLIDBinding@@QEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(CWLIDBinding *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000de3c`
- `0x18000e8b8`

## callees

- `0x1800027f0`
- `0x18000ed9c`
- `0x18000edd8`
- `0x18000ee14`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000ef7a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000ef7a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ef29`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ef29`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ef4c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ef4c`

## string_xrefs

- `0x18000ee82`: `Security=impersonation dynamic false`

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
0x18000ee14  push    rbp
0x18000ee16  push    rbx
0x18000ee17  push    rsi
0x18000ee18  push    rdi
0x18000ee19  lea     rbp, [rsp-28h]
0x18000ee1e  sub     rsp, 128h
0x18000ee25  mov     rax, cs:__security_cookie
0x18000ee2c  xor     rax, rsp
0x18000ee2f  mov     [rbp+40h+var_30], rax
0x18000ee33  xor     esi, esi
0x18000ee35  mov     [rbp+40h+var_80], 80040001h
0x18000ee3c  xorps   xmm0, xmm0
0x18000ee3f  mov     [rsp+140h+var_E8], rsi
0x18000ee44  lea     rax, [rbp+40h+var_98]
0x18000ee48  mov     [rsp+140h+var_D8], rsi
0x18000ee4d  movups  [rbp+40h+var_B8], xmm0
0x18000ee51  mov     qword ptr [rbp+40h+var_B8+8], rax
0x18000ee55  lea     rdx, ProtSeq; "ncalrpc"
0x18000ee5c  lea     rax, [rbp+40h+var_80]
0x18000ee60  mov     [rsp+140h+var_E0], rsi
0x18000ee65  movups  [rbp+40h+var_A8], xmm0
0x18000ee69  mov     qword ptr [rbp+40h+var_A8+8], rax
0x18000ee6d  mov     rdi, rcx
0x18000ee70  lea     rax, [rsp+140h+var_E8]
0x18000ee75  mov     [rsp+140h+Binding], rsi
0x18000ee7a  mov     [rsp+140h+StringBinding], rax; StringBinding
0x18000ee7f  xor     r9d, r9d; Endpoint
0x18000ee82  lea     rax, Options; "Security=impersonation dynamic false"
0x18000ee89  mov     [rsp+140h+var_F0], rsi
0x18000ee8e  xor     r8d, r8d; NetworkAddr
0x18000ee91  mov     [rsp+140h+Options], rax; Options
0x18000ee96  xor     ecx, ecx; ObjUuid
0x18000ee98  mov     [rsp+140h+var_F8], rsi
0x18000ee9d  mov     [rbp+40h+var_7C], rsi
0x18000eea1  mov     [rbp+40h+var_74], esi
0x18000eea4  mov     [rbp+40h+var_70], 14h
0x18000eeab  mov     [rbp+40h+var_6C], 300002h
0x18000eeb2  mov     [rbp+40h+var_68], 1
0x18000eeb9  mov     [rbp+40h+var_64], 280000h
0x18000eec0  mov     [rbp+40h+var_60], 80000000h
0x18000eec7  mov     [rbp+40h+var_5C], 601h
0x18000eece  mov     [rbp+40h+var_58], 5000000h
0x18000eed5  mov     [rbp+40h+var_54], 50h ; 'P'
0x18000eedc  mov     [rbp+40h+var_50], 0AFFF0147h
0x18000eee3  mov     [rbp+40h+var_4C], 863F8CDDh
0x18000eeea  mov     [rbp+40h+var_48], 0CB6E37BCh
0x18000eef1  mov     [rbp+40h+var_44], 0A1B3151Ah
0x18000eef8  mov     [rbp+40h+var_40], 2E8CC86Bh
0x18000eeff  mov     [rbp+40h+var_98], 101h
0x18000ef06  mov     [rbp+40h+var_94], 5000000h
0x18000ef0d  mov     [rbp+40h+var_90], 12h
0x18000ef14  mov     dword ptr [rsp+140h+var_D0], 5
0x18000ef1c  mov     dword ptr [rsp+140h+var_D0+4], 1
0x18000ef24  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x18000ef29  call    cs:__imp_RpcStringBindingComposeW
0x18000ef2f  mov     ebx, eax
0x18000ef31  test    eax, eax
0x18000ef33  jz      short loc_18000EF42
0x18000ef35  jle     short loc_18000EF9A
0x18000ef37  movzx   ebx, ax
0x18000ef3a  or      ebx, 80070000h
0x18000ef40  jmp     short loc_18000EF9A
0x18000ef42  mov     rcx, [rsp+140h+var_E8]; StringBinding
0x18000ef47  lea     rdx, [rsp+140h+Binding]; Binding
0x18000ef4c  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ef52  mov     ebx, eax
0x18000ef54  test    eax, eax
0x18000ef56  jnz     short loc_18000EF35
0x18000ef58  mov     rcx, [rsp+140h+Binding]; Binding
0x18000ef5d  lea     rax, [rsp+140h+var_D0]
0x18000ef62  mov     [rsp+140h+SecurityQOS], rax; SecurityQOS
0x18000ef67  lea     r9d, [rbx+0Ah]; AuthnSvc
0x18000ef6b  mov     dword ptr [rsp+140h+StringBinding], esi; AuthzSvc
0x18000ef6f  lea     r8d, [rbx+6]; AuthnLevel
0x18000ef73  xor     edx, edx; ServerPrincName
0x18000ef75  mov     [rsp+140h+Options], rsi; AuthIdentity
0x18000ef7a  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000ef80  mov     ebx, eax
0x18000ef82  test    eax, eax
0x18000ef84  jnz     short loc_18000EF35
0x18000ef86  mov     rcx, [rsp+140h+Binding]
0x18000ef8b  mov     ebx, esi
0x18000ef8d  mov     [rdi], rcx
0x18000ef90  mov     [rsp+140h+Binding], rsi
0x18000ef95  mov     [rsp+140h+var_F8], rsi
0x18000ef9a  lea     rcx, [rsp+140h+Binding]
0x18000ef9f  call    ??1?$Auto@PEAXVRpcBindingHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(void)
0x18000efa4  lea     rcx, [rsp+140h+var_E8]
0x18000efa9  call    ??1?$Auto@PEAGVRpcWstrFunctor@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,RpcWstrFunctor,DummyContext>::~Auto<ushort *,RpcWstrFunctor,DummyContext>(void)
0x18000efae  mov     eax, ebx
0x18000efb0  mov     rcx, [rbp+40h+var_30]
0x18000efb4  xor     rcx, rsp; StackCookie
0x18000efb7  call    __security_check_cookie
0x18000efbc  add     rsp, 128h
0x18000efc3  pop     rdi
0x18000efc4  pop     rsi
0x18000efc5  pop     rbx
0x18000efc6  pop     rbp
0x18000efc7  retn
```
