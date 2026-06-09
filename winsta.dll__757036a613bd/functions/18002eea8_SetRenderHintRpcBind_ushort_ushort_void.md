# SetRenderHintRpcBind(ushort *,ushort *,void * *)

- ea: `0x18002eea8`
- end: `0x18002f139`
- name: `?SetRenderHintRpcBind@@YAJPEAG0PEAPEAX@Z`
- size: `657`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f140`

## callees

- `0x18002ee14`
- `0x18002eea8`
- `0x18002f65c`
- `0x18002f794`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18002f0d0`
- `RPCRT4!RpcBindingFree` at `0x18002f0d0`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002ef72`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002ef72`
- `RPCRT4!RpcStringFreeW` at `0x18002f128`
- `RPCRT4!RpcStringFreeW` at `0x18002f128`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002efdb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002efdb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002f066`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002f066`

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
0x18002eea8  mov     [rsp-20h+String], rcx
0x18002eead  push    rbp
0x18002eeae  push    rbx
0x18002eeaf  push    rsi
0x18002eeb0  push    rdi
0x18002eeb1  mov     rbp, rsp
0x18002eeb4  sub     rsp, 78h
0x18002eeb8  xor     eax, eax
0x18002eeba  xorps   xmm0, xmm0
0x18002eebd  mov     [rbp+var_18], rax
0x18002eec1  mov     rdi, r8
0x18002eec4  mov     [rbp+String], rax
0x18002eec8  movups  xmmword ptr [rbp+var_38.Version], xmm0
0x18002eecc  movups  [rbp+var_28], xmm0
0x18002eed0  test    rdx, rdx
0x18002eed3  jnz     short loc_18002EF1B
0x18002eed5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eedc  lea     rax, WPP_GLOBAL_Control
0x18002eee3  cmp     rcx, rax
0x18002eee6  jz      short loc_18002EF11
0x18002eee8  test    byte ptr [rcx+1Ch], 1
0x18002eeec  jz      short loc_18002EF11
0x18002eeee  cmp     byte ptr [rcx+19h], 2
0x18002eef2  jb      short loc_18002EF11
0x18002eef4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002eef9  mov     edx, 0Ah
0x18002eefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef05  mov     r9d, eax
0x18002ef08  mov     rcx, [rcx+10h]
0x18002ef0c  call    WPP_SF_D
0x18002ef11  mov     ebx, 80070057h
0x18002ef16  jmp     loc_18002F0C7
0x18002ef1b  test    rdi, rdi
0x18002ef1e  jnz     short loc_18002EF49
0x18002ef20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef27  lea     rax, WPP_GLOBAL_Control
0x18002ef2e  cmp     rcx, rax
0x18002ef31  jz      short loc_18002EF11
0x18002ef33  test    byte ptr [rcx+1Ch], 1
0x18002ef37  jz      short loc_18002EF11
0x18002ef39  cmp     byte ptr [rcx+19h], 2
0x18002ef3d  jb      short loc_18002EF11
0x18002ef3f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ef44  lea     edx, [rdi+0Ch]
0x18002ef47  jmp     short loc_18002EEFE
0x18002ef49  mov     [r8], rax
0x18002ef4c  lea     rcx, a10bd271813bd4b; "10bd2718-13bd-4b84-8e7d-8b5c83770a86"
0x18002ef53  lea     rax, [rbp+String]
0x18002ef57  mov     r9, rdx; Endpoint
0x18002ef5a  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18002ef5f  lea     rdx, ProtSeq; "ncalrpc"
0x18002ef66  xor     r8d, r8d; NetworkAddr
0x18002ef69  mov     [rsp+78h+Options], 0; Options
0x18002ef72  call    cs:__imp_RpcStringBindingComposeW
0x18002ef78  mov     ebx, eax
0x18002ef7a  test    eax, eax
0x18002ef7c  jz      short loc_18002EFD4
0x18002ef7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef85  lea     rax, WPP_GLOBAL_Control
0x18002ef8c  cmp     rcx, rax
0x18002ef8f  jz      short loc_18002EFBE
0x18002ef91  test    byte ptr [rcx+1Ch], 1
0x18002ef95  jz      short loc_18002EFBE
0x18002ef97  cmp     byte ptr [rcx+19h], 2
0x18002ef9b  jb      short loc_18002EFBE
0x18002ef9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002efa2  mov     edx, 0Dh
0x18002efa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efae  mov     r9d, eax
0x18002efb1  mov     dword ptr [rsp+78h+Options], ebx
0x18002efb5  mov     rcx, [rcx+10h]
0x18002efb9  call    WPP_SF_Dd
0x18002efbe  test    ebx, ebx
0x18002efc0  jle     loc_18002F0C5
0x18002efc6  movzx   ebx, bx
0x18002efc9  or      ebx, 80070000h
0x18002efcf  jmp     loc_18002F0C3
0x18002efd4  mov     rcx, [rbp+String]; StringBinding
0x18002efd8  mov     rdx, rdi; Binding
0x18002efdb  call    cs:__imp_RpcBindingFromStringBindingW
0x18002efe1  mov     ebx, eax
0x18002efe3  test    eax, eax
0x18002efe5  jz      short loc_18002F012
0x18002efe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efee  lea     rax, WPP_GLOBAL_Control
0x18002eff5  cmp     rcx, rax
0x18002eff8  jz      short loc_18002EFBE
0x18002effa  test    byte ptr [rcx+1Ch], 1
0x18002effe  jz      short loc_18002EFBE
0x18002f000  cmp     byte ptr [rcx+19h], 2
0x18002f004  jb      short loc_18002EFBE
0x18002f006  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f00b  mov     edx, 0Eh
0x18002f010  jmp     short loc_18002EFA7
0x18002f012  mov     rcx, [rdi]; Binding
0x18002f015  lea     rax, [rbp+var_38]
0x18002f019  mov     [rsp+78h+SecurityQOS], rax; SecurityQOS
0x18002f01e  lea     rdx, ServerPrincName; "NT AUTHORITY\\SYSTEM"
0x18002f025  mov     r9d, 0Ah; AuthnSvc
0x18002f02b  mov     dword ptr [rsp+78h+StringBinding], 0; AuthzSvc
0x18002f033  xorps   xmm0, xmm0
0x18002f036  mov     qword ptr [rbp+var_38.Capabilities], 0
0x18002f03e  movdqu  [rbp+var_28], xmm0
0x18002f043  mov     [rbp+var_38.ImpersonationType], 2
0x18002f04a  lea     r8d, [r9-4]; AuthnLevel
0x18002f04e  mov     [rbp+var_18], 0
0x18002f056  mov     [rbp+var_38.Version], 3
0x18002f05d  mov     [rsp+78h+Options], 0; AuthIdentity
0x18002f066  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18002f06c  mov     esi, eax
0x18002f06e  test    eax, eax
0x18002f070  jz      short loc_18002F0DF
0x18002f072  test    eax, eax
0x18002f074  jg      short loc_18002F07A
0x18002f076  mov     ebx, eax
0x18002f078  jmp     short loc_18002F083
0x18002f07a  movzx   ebx, si
0x18002f07d  or      ebx, 80070000h
0x18002f083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f08a  lea     rax, WPP_GLOBAL_Control
0x18002f091  cmp     rcx, rax
0x18002f094  jz      short loc_18002F0C3
0x18002f096  test    byte ptr [rcx+1Ch], 1
0x18002f09a  jz      short loc_18002F0C3
0x18002f09c  cmp     byte ptr [rcx+19h], 2
0x18002f0a0  jb      short loc_18002F0C3
0x18002f0a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0ae  mov     edx, 0Fh
0x18002f0b3  mov     r9d, eax
0x18002f0b6  mov     dword ptr [rsp+78h+Options], esi
0x18002f0ba  mov     rcx, [rcx+10h]
0x18002f0be  call    WPP_SF_Dd
0x18002f0c3  test    ebx, ebx
0x18002f0c5  jns     short loc_18002F11D
0x18002f0c7  cmp     qword ptr [rdi], 0
0x18002f0cb  jz      short loc_18002F11D
0x18002f0cd  mov     rcx, rdi; Binding
0x18002f0d0  call    cs:__imp_RpcBindingFree
0x18002f0d6  mov     qword ptr [rdi], 0
0x18002f0dd  jmp     short loc_18002F11D
0x18002f0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0e6  lea     rax, WPP_GLOBAL_Control
0x18002f0ed  cmp     rcx, rax
0x18002f0f0  jz      short loc_18002F11B
0x18002f0f2  test    byte ptr [rcx+1Ch], 1
0x18002f0f6  jz      short loc_18002F11B
0x18002f0f8  cmp     byte ptr [rcx+19h], 2
0x18002f0fc  jb      short loc_18002F11B
0x18002f0fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f103  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f10a  mov     edx, 10h
0x18002f10f  mov     r9d, eax
0x18002f112  mov     rcx, [rcx+10h]
0x18002f116  call    WPP_SF_D
0x18002f11b  xor     ebx, ebx
0x18002f11d  cmp     [rbp+String], 0
0x18002f122  jz      short loc_18002F12E
0x18002f124  lea     rcx, [rbp+String]; String
0x18002f128  call    cs:__imp_RpcStringFreeW
0x18002f12e  mov     eax, ebx
0x18002f130  add     rsp, 78h
0x18002f134  pop     rdi
0x18002f135  pop     rsi
0x18002f136  pop     rbx
0x18002f137  pop     rbp
0x18002f138  retn
```
