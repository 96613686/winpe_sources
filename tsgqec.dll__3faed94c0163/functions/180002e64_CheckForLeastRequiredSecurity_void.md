# CheckForLeastRequiredSecurity(void *)

- ea: `0x180002e64`
- end: `0x180003172`
- name: `?CheckForLeastRequiredSecurity@@YAJPEAX@Z`
- size: `782`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800040f0`

## callees

- `0x180002e64`
- `0x180003970`
- `0x1800053ac`
- `0x1800053ec`
- `0x180005518`
- `0x18000ae79`
- `0x18000aea0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000307a`
- `msvcrt!_wcsicmp` at `0x18000307a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002fca`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002fca`
- `RPCRT4!RpcBindingServerFromClient` at `0x180002f7a`
- `RPCRT4!RpcBindingServerFromClient` at `0x180002f7a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002ec1`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002ec1`
- `RPCRT4!RpcStringFreeW` at `0x180003138`
- `RPCRT4!RpcStringFreeW` at `0x180003149`
- `RPCRT4!RpcStringFreeW` at `0x180003138`
- `RPCRT4!RpcStringFreeW` at `0x180003149`
- `RPCRT4!RpcBindingFree` at `0x180003127`
- `RPCRT4!RpcBindingFree` at `0x180003127`
- `RPCRT4!RpcStringBindingParseW` at `0x180003031`
- `RPCRT4!RpcStringBindingParseW` at `0x180003031`

## pseudocode

```c
__int64 __fastcall CheckForLeastRequiredSecurity(RPC_BINDING_HANDLE ClientBinding)
{
  unsigned int v2; // ebx
  int v3; // r8d
  _QWORD *v4; // rcx
  int v5; // edx
  const wchar_t *v6; // r9
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // ecx
  __int64 v9; // rdx
  unsigned int v10; // eax
  RPC_BINDING_HANDLE ServerBinding; // [rsp+30h] [rbp-59h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-51h] BYREF
  RPC_WSTR Protseq[2]; // [rsp+40h] [rbp-49h] BYREF
  int RpcCallAttributes; // [rsp+50h] [rbp-39h] BYREF
  char v16[36]; // [rsp+54h] [rbp-35h] BYREF
  unsigned int v17; // [rsp+78h] [rbp-11h]
  unsigned int v18; // [rsp+7Ch] [rbp-Dh]

  ServerBinding = 0;
  StringBinding = 0;
  Protseq[0] = 0;
  memset_0(v16, 0, 0x74u);
  RpcCallAttributes = 3;
  v2 = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 55;
      v6 = L"RpcServerInqCallAttributes";
LABEL_6:
      WPP_SF_SD(v4[2], v5, v3, (_DWORD)v6, v2);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  if ( v17 < 6 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = v17;
    v9 = 56;
LABEL_39:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
      CurrentThreadActivityIdPrefix,
      v8);
LABEL_40:
    v2 = 5;
    goto LABEL_41;
  }
  if ( ((v18 - 9) & 0xFFFFFFFA) != 0 || v18 == 13 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = v18;
    v9 = 57;
    goto LABEL_39;
  }
  v2 = RpcBindingServerFromClient(ClientBinding, &ServerBinding);
  if ( !v2 )
  {
    v2 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
    if ( v2 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v5 = 59;
    }
    else
    {
      v2 = RpcStringBindingParseW(StringBinding, 0, Protseq, 0, 0, 0);
      if ( !v2 )
      {
        if ( !_wcsicmp(Protseq[0], L"ncalrpc") )
          goto LABEL_41;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, v10);
        }
        goto LABEL_40;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v5 = 60;
    }
    v6 = L"RpcBindingToStringBinding";
    goto LABEL_6;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 58;
    v6 = L"RpcBindingServerFromClient";
    goto LABEL_6;
  }
LABEL_41:
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq[0] )
    RpcStringFreeW(Protseq);
  return v2;
}

```

## disassembly

```asm
0x180002e64  mov     [rsp-8+arg_8], rbx
0x180002e69  mov     [rsp-8+arg_10], rdi
0x180002e6e  push    rbp
0x180002e6f  lea     rbp, [rsp-57h]
0x180002e74  sub     rsp, 0E0h
0x180002e7b  mov     rax, cs:__security_cookie
0x180002e82  xor     rax, rsp
0x180002e85  mov     [rbp+57h+var_10], rax
0x180002e89  xor     edx, edx; Val
0x180002e8b  mov     [rbp+57h+ServerBinding], 0
0x180002e93  mov     rdi, rcx
0x180002e96  mov     [rbp+57h+StringBinding], 0
0x180002e9e  lea     rcx, [rbp+57h+var_8C]; void *
0x180002ea2  mov     [rbp+57h+Protseq], 0
0x180002eaa  lea     r8d, [rdx+74h]; Size
0x180002eae  call    memset_0
0x180002eb3  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180002eb7  mov     [rbp+57h+RpcCallAttributes], 3
0x180002ebe  mov     rcx, rdi; ClientBinding
0x180002ec1  call    cs:__imp_RpcServerInqCallAttributesW
0x180002ec7  mov     ebx, eax
0x180002ec9  test    eax, eax
0x180002ecb  jz      short loc_180002F16
0x180002ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed4  lea     rax, WPP_GLOBAL_Control
0x180002edb  cmp     rcx, rax
0x180002ede  jz      loc_18000311C
0x180002ee4  test    byte ptr [rcx+1Ch], 8
0x180002ee8  jz      loc_18000311C
0x180002eee  cmp     byte ptr [rcx+19h], 2
0x180002ef2  jb      loc_18000311C
0x180002ef8  mov     edx, 37h ; '7'
0x180002efd  lea     r9, aRpcserverinqca; "RpcServerInqCallAttributes"
0x180002f04  mov     rcx, [rcx+10h]
0x180002f08  mov     dword ptr [rsp+0E0h+Endpoint], ebx
0x180002f0c  call    WPP_SF_SD
0x180002f11  jmp     loc_18000311C
0x180002f16  cmp     [rbp+57h+var_68], 6
0x180002f1a  jnb     short loc_180002F59
0x180002f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f23  lea     rax, WPP_GLOBAL_Control
0x180002f2a  cmp     rcx, rax
0x180002f2d  jz      loc_180003117
0x180002f33  test    byte ptr [rcx+1Ch], 1
0x180002f37  jz      loc_180003117
0x180002f3d  cmp     byte ptr [rcx+19h], 2
0x180002f41  jb      loc_180003117
0x180002f47  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180002f4c  mov     ecx, [rbp+57h+var_68]
0x180002f4f  mov     edx, 38h ; '8'
0x180002f54  jmp     loc_1800030F9
0x180002f59  mov     edx, [rbp+57h+var_64]
0x180002f5c  lea     eax, [rdx-9]
0x180002f5f  test    eax, 0FFFFFFFAh
0x180002f64  jnz     loc_1800030CD
0x180002f6a  cmp     edx, 0Dh
0x180002f6d  jz      loc_1800030CD
0x180002f73  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x180002f77  mov     rcx, rdi; ClientBinding
0x180002f7a  call    cs:__imp_RpcBindingServerFromClient
0x180002f80  mov     ebx, eax
0x180002f82  test    eax, eax
0x180002f84  jz      short loc_180002FC2
0x180002f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f8d  lea     rax, WPP_GLOBAL_Control
0x180002f94  cmp     rcx, rax
0x180002f97  jz      loc_18000311C
0x180002f9d  test    byte ptr [rcx+1Ch], 8
0x180002fa1  jz      loc_18000311C
0x180002fa7  cmp     byte ptr [rcx+19h], 2
0x180002fab  jb      loc_18000311C
0x180002fb1  mov     edx, 3Ah ; ':'
0x180002fb6  lea     r9, aRpcbindingserv; "RpcBindingServerFromClient"
0x180002fbd  jmp     loc_180002F04
0x180002fc2  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x180002fc6  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180002fca  call    cs:__imp_RpcBindingToStringBindingW
0x180002fd0  mov     ebx, eax
0x180002fd2  test    eax, eax
0x180002fd4  jz      short loc_180003012
0x180002fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fdd  lea     rax, WPP_GLOBAL_Control
0x180002fe4  cmp     rcx, rax
0x180002fe7  jz      loc_18000311C
0x180002fed  test    byte ptr [rcx+1Ch], 8
0x180002ff1  jz      loc_18000311C
0x180002ff7  cmp     byte ptr [rcx+19h], 2
0x180002ffb  jb      loc_18000311C
0x180003001  mov     edx, 3Bh ; ';'
0x180003006  lea     r9, aRpcbindingtost; "RpcBindingToStringBinding"
0x18000300d  jmp     loc_180002F04
0x180003012  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180003016  lea     r8, [rbp+57h+Protseq]; Protseq
0x18000301a  mov     [rsp+0E0h+NetworkOptions], 0; NetworkOptions
0x180003023  xor     r9d, r9d; NetworkAddr
0x180003026  xor     edx, edx; ObjUuid
0x180003028  mov     [rsp+0E0h+Endpoint], 0; Endpoint
0x180003031  call    cs:__imp_RpcStringBindingParseW
0x180003037  mov     ebx, eax
0x180003039  test    eax, eax
0x18000303b  jz      short loc_18000306F
0x18000303d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003044  lea     rax, WPP_GLOBAL_Control
0x18000304b  cmp     rcx, rax
0x18000304e  jz      loc_18000311C
0x180003054  test    byte ptr [rcx+1Ch], 8
0x180003058  jz      loc_18000311C
0x18000305e  cmp     byte ptr [rcx+19h], 2
0x180003062  jb      loc_18000311C
0x180003068  mov     edx, 3Ch ; '<'
0x18000306d  jmp     short loc_180003006
0x18000306f  mov     rcx, [rbp+57h+Protseq]; String1
0x180003073  lea     rdx, aNcalrpc; "ncalrpc"
0x18000307a  call    cs:__imp__wcsicmp
0x180003080  test    eax, eax
0x180003082  jz      loc_18000311C
0x180003088  mov     rcx, cs:WPP_GLOBAL_Control
0x18000308f  lea     rax, WPP_GLOBAL_Control
0x180003096  cmp     rcx, rax
0x180003099  jz      short loc_180003117
0x18000309b  test    byte ptr [rcx+1Ch], 1
0x18000309f  jz      short loc_180003117
0x1800030a1  cmp     byte ptr [rcx+19h], 2
0x1800030a5  jb      short loc_180003117
0x1800030a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800030ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030b3  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800030ba  mov     edx, 3Dh ; '='
0x1800030bf  mov     r9d, eax
0x1800030c2  mov     rcx, [rcx+10h]
0x1800030c6  call    WPP_SF_D
0x1800030cb  jmp     short loc_180003117
0x1800030cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030d4  lea     rax, WPP_GLOBAL_Control
0x1800030db  cmp     rcx, rax
0x1800030de  jz      short loc_180003117
0x1800030e0  test    byte ptr [rcx+1Ch], 1
0x1800030e4  jz      short loc_180003117
0x1800030e6  cmp     byte ptr [rcx+19h], 2
0x1800030ea  jb      short loc_180003117
0x1800030ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800030f1  mov     ecx, [rbp+57h+var_64]
0x1800030f4  mov     edx, 39h ; '9'
0x1800030f9  mov     dword ptr [rsp+0E0h+Endpoint], ecx
0x1800030fd  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000310b  mov     r9d, eax
0x18000310e  mov     rcx, [rcx+10h]
0x180003112  call    WPP_SF_Dd
0x180003117  mov     ebx, 5
0x18000311c  cmp     [rbp+57h+ServerBinding], 0
0x180003121  jz      short loc_18000312D
0x180003123  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x180003127  call    cs:__imp_RpcBindingFree
0x18000312d  cmp     [rbp+57h+StringBinding], 0
0x180003132  jz      short loc_18000313E
0x180003134  lea     rcx, [rbp+57h+StringBinding]; String
0x180003138  call    cs:__imp_RpcStringFreeW
0x18000313e  cmp     [rbp+57h+Protseq], 0
0x180003143  jz      short loc_18000314F
0x180003145  lea     rcx, [rbp+57h+Protseq]; String
0x180003149  call    cs:__imp_RpcStringFreeW
0x18000314f  mov     eax, ebx
0x180003151  mov     rcx, [rbp+57h+var_10]
0x180003155  xor     rcx, rsp; StackCookie
0x180003158  call    __security_check_cookie
0x18000315d  lea     r11, [rsp+0E0h+var_s0]
0x180003165  mov     rbx, [r11+18h]
0x180003169  mov     rdi, [r11+20h]
0x18000316d  mov     rsp, r11
0x180003170  pop     rbp
0x180003171  retn
```
