# SetRenderHintRpcBind(ushort *,ushort *,void * *)

- ea: `0x180031bb8`
- end: `0x180031e68`
- name: `?SetRenderHintRpcBind@@YAJPEAG0PEAPEAX@Z`
- size: `688`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031e70`

## callees

- `0x180031b10`
- `0x180031bb8`
- `0x1800323c8`
- `0x180032514`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180031df2`
- `RPCRT4!RpcBindingFree` at `0x180031df2`
- `RPCRT4!RpcStringBindingComposeW` at `0x180031c82`
- `RPCRT4!RpcStringBindingComposeW` at `0x180031c82`
- `RPCRT4!RpcStringFreeW` at `0x180031e50`
- `RPCRT4!RpcStringFreeW` at `0x180031e50`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180031cf1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180031cf1`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180031d82`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180031d82`

## pseudocode

```c
__int64 __fastcall SetRenderHintRpcBind(unsigned __int16 *a1, unsigned __int16 *a2, void **a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // r8
  __int64 v6; // rdx
  int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  bool v11; // sf
  RPC_BINDING_HANDLE v12; // rcx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // esi
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r8
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-38h] BYREF
  __int128 v21; // [rsp+50h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-18h]
  RPC_WSTR String; // [rsp+A0h] [rbp+28h] BYREF

  v22 = 0;
  String = 0;
  SecurityQOS = 0;
  v21 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 10;
LABEL_6:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v5, CurrentThreadActivityIdPrefix);
LABEL_7:
    v7 = -2147024809;
LABEL_36:
    if ( *a3 )
    {
      RpcBindingFree(a3);
      *a3 = 0;
    }
    goto LABEL_43;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 12;
    goto LABEL_6;
  }
  *a3 = 0;
  v7 = RpcStringBindingComposeW(
         (RPC_WSTR)L"10bd2718-13bd-4b84-8e7d-8b5c83770a86",
         (RPC_WSTR)L"ncalrpc",
         0,
         a2,
         0,
         &String);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 13;
LABEL_18:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v9, v8, v7);
LABEL_19:
    v11 = v7 < 0;
    if ( v7 <= 0 )
      goto LABEL_35;
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_34:
    v11 = v7 < 0;
LABEL_35:
    if ( !v11 )
      goto LABEL_43;
    goto LABEL_36;
  }
  v7 = RpcBindingFromStringBindingW(String, a3);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 14;
    goto LABEL_18;
  }
  v12 = *a3;
  *(_QWORD *)&SecurityQOS.Capabilities = 0;
  v21 = 0;
  SecurityQOS.ImpersonationType = 2;
  v22 = 0;
  SecurityQOS.Version = 3;
  v13 = RpcBindingSetAuthInfoExW(v12, (RPC_WSTR)L"NT AUTHORITY\\SYSTEM", 6u, 0xAu, 0, 0, &SecurityQOS);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    else
      v7 = v13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v16, v15, v14);
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v18, v17);
  }
  v7 = 0;
LABEL_43:
  if ( String )
    RpcStringFreeW(&String);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031bb8  mov     [rsp-20h+String], rcx
0x180031bbd  push    rbp
0x180031bbe  push    rbx
0x180031bbf  push    rsi
0x180031bc0  push    rdi
0x180031bc1  mov     rbp, rsp
0x180031bc4  sub     rsp, 78h
0x180031bc8  xor     eax, eax
0x180031bca  xorps   xmm0, xmm0
0x180031bcd  mov     [rbp+var_18], rax
0x180031bd1  mov     rdi, r8
0x180031bd4  mov     [rbp+String], rax
0x180031bd8  movups  xmmword ptr [rbp+var_38.Version], xmm0
0x180031bdc  movups  [rbp+var_28], xmm0
0x180031be0  test    rdx, rdx
0x180031be3  jnz     short loc_180031C2B
0x180031be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bec  lea     rax, WPP_GLOBAL_Control
0x180031bf3  cmp     rcx, rax
0x180031bf6  jz      short loc_180031C21
0x180031bf8  test    byte ptr [rcx+1Ch], 1
0x180031bfc  jz      short loc_180031C21
0x180031bfe  cmp     byte ptr [rcx+19h], 2
0x180031c02  jb      short loc_180031C21
0x180031c04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031c09  mov     edx, 0Ah
0x180031c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c15  mov     r9d, eax
0x180031c18  mov     rcx, [rcx+10h]
0x180031c1c  call    WPP_SF_D
0x180031c21  mov     ebx, 80070057h
0x180031c26  jmp     loc_180031DE9
0x180031c2b  test    rdi, rdi
0x180031c2e  jnz     short loc_180031C59
0x180031c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c37  lea     rax, WPP_GLOBAL_Control
0x180031c3e  cmp     rcx, rax
0x180031c41  jz      short loc_180031C21
0x180031c43  test    byte ptr [rcx+1Ch], 1
0x180031c47  jz      short loc_180031C21
0x180031c49  cmp     byte ptr [rcx+19h], 2
0x180031c4d  jb      short loc_180031C21
0x180031c4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031c54  lea     edx, [rdi+0Ch]
0x180031c57  jmp     short loc_180031C0E
0x180031c59  mov     [r8], rax
0x180031c5c  lea     rcx, a10bd271813bd4b; "10bd2718-13bd-4b84-8e7d-8b5c83770a86"
0x180031c63  lea     rax, [rbp+String]
0x180031c67  mov     r9, rdx; Endpoint
0x180031c6a  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180031c6f  lea     rdx, ProtSeq; "ncalrpc"
0x180031c76  xor     r8d, r8d; NetworkAddr
0x180031c79  mov     [rsp+78h+Options], 0; Options
0x180031c82  call    cs:__imp_RpcStringBindingComposeW
0x180031c89  nop     dword ptr [rax+rax+00h]
0x180031c8e  mov     ebx, eax
0x180031c90  test    eax, eax
0x180031c92  jz      short loc_180031CEA
0x180031c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c9b  lea     rax, WPP_GLOBAL_Control
0x180031ca2  cmp     rcx, rax
0x180031ca5  jz      short loc_180031CD4
0x180031ca7  test    byte ptr [rcx+1Ch], 1
0x180031cab  jz      short loc_180031CD4
0x180031cad  cmp     byte ptr [rcx+19h], 2
0x180031cb1  jb      short loc_180031CD4
0x180031cb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031cb8  mov     edx, 0Dh
0x180031cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cc4  mov     r9d, eax
0x180031cc7  mov     dword ptr [rsp+78h+Options], ebx
0x180031ccb  mov     rcx, [rcx+10h]
0x180031ccf  call    WPP_SF_Dd
0x180031cd4  test    ebx, ebx
0x180031cd6  jle     loc_180031DE7
0x180031cdc  movzx   ebx, bx
0x180031cdf  or      ebx, 80070000h
0x180031ce5  jmp     loc_180031DE5
0x180031cea  mov     rcx, [rbp+String]; StringBinding
0x180031cee  mov     rdx, rdi; Binding
0x180031cf1  call    cs:__imp_RpcBindingFromStringBindingW
0x180031cf8  nop     dword ptr [rax+rax+00h]
0x180031cfd  mov     ebx, eax
0x180031cff  test    eax, eax
0x180031d01  jz      short loc_180031D2E
0x180031d03  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d0a  lea     rax, WPP_GLOBAL_Control
0x180031d11  cmp     rcx, rax
0x180031d14  jz      short loc_180031CD4
0x180031d16  test    byte ptr [rcx+1Ch], 1
0x180031d1a  jz      short loc_180031CD4
0x180031d1c  cmp     byte ptr [rcx+19h], 2
0x180031d20  jb      short loc_180031CD4
0x180031d22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031d27  mov     edx, 0Eh
0x180031d2c  jmp     short loc_180031CBD
0x180031d2e  mov     rcx, [rdi]; Binding
0x180031d31  lea     rax, [rbp+var_38]
0x180031d35  mov     [rsp+78h+SecurityQOS], rax; SecurityQOS
0x180031d3a  lea     rdx, ServerPrincName; "NT AUTHORITY\\SYSTEM"
0x180031d41  mov     r9d, 0Ah; AuthnSvc
0x180031d47  mov     dword ptr [rsp+78h+StringBinding], 0; AuthzSvc
0x180031d4f  xorps   xmm0, xmm0
0x180031d52  mov     qword ptr [rbp+var_38.Capabilities], 0
0x180031d5a  movdqu  [rbp+var_28], xmm0
0x180031d5f  mov     [rbp+var_38.ImpersonationType], 2
0x180031d66  lea     r8d, [r9-4]; AuthnLevel
0x180031d6a  mov     [rbp+var_18], 0
0x180031d72  mov     [rbp+var_38.Version], 3
0x180031d79  mov     [rsp+78h+Options], 0; AuthIdentity
0x180031d82  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180031d89  nop     dword ptr [rax+rax+00h]
0x180031d8e  mov     esi, eax
0x180031d90  test    eax, eax
0x180031d92  jz      short loc_180031E07
0x180031d94  test    eax, eax
0x180031d96  jg      short loc_180031D9C
0x180031d98  mov     ebx, eax
0x180031d9a  jmp     short loc_180031DA5
0x180031d9c  movzx   ebx, si
0x180031d9f  or      ebx, 80070000h
0x180031da5  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dac  lea     rax, WPP_GLOBAL_Control
0x180031db3  cmp     rcx, rax
0x180031db6  jz      short loc_180031DE5
0x180031db8  test    byte ptr [rcx+1Ch], 1
0x180031dbc  jz      short loc_180031DE5
0x180031dbe  cmp     byte ptr [rcx+19h], 2
0x180031dc2  jb      short loc_180031DE5
0x180031dc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dd0  mov     edx, 0Fh
0x180031dd5  mov     r9d, eax
0x180031dd8  mov     dword ptr [rsp+78h+Options], esi
0x180031ddc  mov     rcx, [rcx+10h]
0x180031de0  call    WPP_SF_Dd
0x180031de5  test    ebx, ebx
0x180031de7  jns     short loc_180031E45
0x180031de9  cmp     qword ptr [rdi], 0
0x180031ded  jz      short loc_180031E45
0x180031def  mov     rcx, rdi; Binding
0x180031df2  call    cs:__imp_RpcBindingFree
0x180031df9  nop     dword ptr [rax+rax+00h]
0x180031dfe  mov     qword ptr [rdi], 0
0x180031e05  jmp     short loc_180031E45
0x180031e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e0e  lea     rax, WPP_GLOBAL_Control
0x180031e15  cmp     rcx, rax
0x180031e18  jz      short loc_180031E43
0x180031e1a  test    byte ptr [rcx+1Ch], 1
0x180031e1e  jz      short loc_180031E43
0x180031e20  cmp     byte ptr [rcx+19h], 2
0x180031e24  jb      short loc_180031E43
0x180031e26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e32  mov     edx, 10h
0x180031e37  mov     r9d, eax
0x180031e3a  mov     rcx, [rcx+10h]
0x180031e3e  call    WPP_SF_D
0x180031e43  xor     ebx, ebx
0x180031e45  cmp     [rbp+String], 0
0x180031e4a  jz      short loc_180031E5C
0x180031e4c  lea     rcx, [rbp+String]; String
0x180031e50  call    cs:__imp_RpcStringFreeW
0x180031e57  nop     dword ptr [rax+rax+00h]
0x180031e5c  mov     eax, ebx
0x180031e5e  add     rsp, 78h
0x180031e62  pop     rdi
0x180031e63  pop     rsi
0x180031e64  pop     rbx
0x180031e65  pop     rbp
0x180031e66  retn
```
