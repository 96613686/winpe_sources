# XactSrvRpcSecurityCallback

- ea: `0x18002fce0`
- end: `0x180030036`
- name: `XactSrvRpcSecurityCallback`
- size: `854`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001deb0`
- `0x18001e80c`
- `0x180020dc0`
- `0x180020de8`
- `0x18002fce0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ff69`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ff69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff73`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ff06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ff06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002fef0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002fef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ffe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ffe2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002fdfd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002fdfd`
- `RPCRT4!RpcStringBindingParseW` at `0x18002fda8`
- `RPCRT4!RpcStringBindingParseW` at `0x18002fda8`
- `RPCRT4!RpcStringFreeW` at `0x18002ffc1`
- `RPCRT4!RpcStringFreeW` at `0x18002ffd3`
- `RPCRT4!RpcStringFreeW` at `0x18002ffc1`
- `RPCRT4!RpcStringFreeW` at `0x18002ffd3`
- `RPCRT4!RpcImpersonateClient` at `0x18002feb6`
- `RPCRT4!RpcImpersonateClient` at `0x18002feb6`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002fd6f`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002fd6f`
- `RPCRT4!RpcBindingFree` at `0x18002ffaf`
- `RPCRT4!RpcBindingFree` at `0x18002ffaf`
- `RPCRT4!RpcRevertToSelf` at `0x18002ff0e`
- `RPCRT4!RpcRevertToSelf` at `0x18002ff0e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002fe60`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002fe60`
- `RPCRT4!RpcBindingServerFromClient` at `0x18002fd53`
- `RPCRT4!RpcBindingServerFromClient` at `0x18002fd53`

## pseudocode

```c
__int64 __fastcall XactSrvRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  DWORD LastError; // ebx
  DWORD v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  BOOL v9; // edi
  WINBOOL IsMember; // [rsp+30h] [rbp-99h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-91h] BYREF
  RPC_WSTR Protseq; // [rsp+40h] [rbp-89h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+48h] [rbp-81h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-79h] BYREF
  _DWORD SidToCheck[6]; // [rsp+58h] [rbp-71h] BYREF
  int RpcCallAttributes; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v17[84]; // [rsp+74h] [rbp-55h] BYREF
  __int16 v18; // [rsp+C8h] [rbp-1h]

  IsMember = 1;
  ServerBinding = 0;
  StringBinding = 0;
  Protseq = 0;
  TokenHandle = 0;
  memset_0(&RpcCallAttributes, 0, 0x70u);
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( RpcBindingServerFromClient(Context, &ServerBinding) )
    return 5;
  if ( !RpcBindingToStringBindingW(ServerBinding, &StringBinding) )
  {
    v5 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    LastError = v5;
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_41;
      }
      v7 = 10;
      goto LABEL_10;
    }
    if ( lstrcmpW(Protseq, L"ncalrpc") )
    {
      LastError = 5;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids);
      }
      goto LABEL_41;
    }
    memset_0(v17, 0, 0x6Cu);
    RpcCallAttributes = 2;
    v5 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    LastError = v5;
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_41;
      }
      v7 = 12;
      goto LABEL_10;
    }
    if ( v18 != 2 && v18 != 5 )
    {
      v5 = RpcImpersonateClient(0);
      LastError = v5;
      if ( v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_41;
        }
        v7 = 13;
        goto LABEL_10;
      }
      CurrentThread = GetCurrentThread();
      v9 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
      v5 = RpcRevertToSelf();
      LastError = v5;
      if ( v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_41;
        }
        v7 = 14;
LABEL_10:
        WPP_SF_d(v6[2], v7, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, v5);
        goto LABEL_41;
      }
      if ( !v9 )
      {
        LastError = GetLastError();
        goto LABEL_41;
      }
    }
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      LastError = IsMember != 1 ? 5 : 0;
      goto LABEL_41;
    }
    v5 = GetLastError();
    LastError = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_41;
    }
    v7 = 15;
    goto LABEL_10;
  }
  LastError = 5;
LABEL_41:
  RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002fce0  push    rbp
0x18002fce2  push    rbx
0x18002fce3  push    rsi
0x18002fce4  push    rdi
0x18002fce5  push    r13
0x18002fce7  push    r15
0x18002fce9  lea     rbp, [rsp-2Fh]
0x18002fcee  sub     rsp, 0F8h
0x18002fcf5  mov     rax, cs:__security_cookie
0x18002fcfc  xor     rax, rsp
0x18002fcff  mov     [rbp+57h+var_40], rax
0x18002fd03  xor     esi, esi
0x18002fd05  mov     [rsp+120h+IsMember], 1
0x18002fd0d  mov     rbx, rdx
0x18002fd10  mov     [rsp+120h+ServerBinding], rsi
0x18002fd15  xor     edx, edx; Val
0x18002fd17  mov     [rsp+120h+StringBinding], rsi
0x18002fd1c  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18002fd20  mov     [rsp+120h+Protseq], rsi
0x18002fd25  lea     r8d, [rsi+70h]; Size
0x18002fd29  mov     [rbp+57h+TokenHandle], rsi
0x18002fd2d  call    memset_0
0x18002fd32  lea     rdx, [rsp+120h+ServerBinding]; ServerBinding
0x18002fd37  mov     [rbp+57h+SidToCheck], 101h
0x18002fd3e  mov     rcx, rbx; ClientBinding
0x18002fd41  mov     [rbp+57h+var_C4], 5000000h
0x18002fd48  lea     r15d, [rsi+5]
0x18002fd4c  mov     [rbp+57h+var_C0], 12h
0x18002fd53  call    cs:__imp_RpcBindingServerFromClient
0x18002fd59  test    eax, eax
0x18002fd5b  jz      short loc_18002FD65
0x18002fd5d  mov     eax, r15d
0x18002fd60  jmp     loc_18003001A
0x18002fd65  mov     rcx, [rsp+120h+ServerBinding]; Binding
0x18002fd6a  lea     rdx, [rsp+120h+StringBinding]; StringBinding
0x18002fd6f  call    cs:__imp_RpcBindingToStringBindingW
0x18002fd75  lea     r13, WPP_GLOBAL_Control
0x18002fd7c  lea     rdi, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18002fd83  test    eax, eax
0x18002fd85  jz      short loc_18002FD8F
0x18002fd87  mov     ebx, r15d
0x18002fd8a  jmp     loc_18002FFAA
0x18002fd8f  mov     rcx, [rsp+120h+StringBinding]; StringBinding
0x18002fd94  lea     r8, [rsp+120h+Protseq]; Protseq
0x18002fd99  mov     [rsp+120h+NetworkOptions], rsi; NetworkOptions
0x18002fd9e  xor     r9d, r9d; NetworkAddr
0x18002fda1  xor     edx, edx; ObjUuid
0x18002fda3  mov     [rsp+120h+Endpoint], rsi; Endpoint
0x18002fda8  call    cs:__imp_RpcStringBindingParseW
0x18002fdae  mov     ebx, eax
0x18002fdb0  test    eax, eax
0x18002fdb2  jz      short loc_18002FDF1
0x18002fdb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdbb  cmp     rcx, r13
0x18002fdbe  jz      loc_18002FFAA
0x18002fdc4  test    byte ptr [rcx+1Ch], 10h
0x18002fdc8  jz      loc_18002FFAA
0x18002fdce  cmp     byte ptr [rcx+19h], 1
0x18002fdd2  jb      loc_18002FFAA
0x18002fdd8  mov     edx, 0Ah
0x18002fddd  mov     r8, rdi
0x18002fde0  mov     rcx, [rcx+10h]
0x18002fde4  mov     r9d, eax
0x18002fde7  call    WPP_SF_d
0x18002fdec  jmp     loc_18002FFAA
0x18002fdf1  mov     rcx, [rsp+120h+Protseq]; lpString1
0x18002fdf6  lea     rdx, String2; "ncalrpc"
0x18002fdfd  call    cs:__imp_lstrcmpW
0x18002fe03  test    eax, eax
0x18002fe05  jz      short loc_18002FE44
0x18002fe07  mov     ebx, r15d
0x18002fe0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe11  cmp     rcx, r13
0x18002fe14  jz      loc_18002FFAA
0x18002fe1a  test    byte ptr [rcx+1Ch], 10h
0x18002fe1e  jz      loc_18002FFAA
0x18002fe24  cmp     byte ptr [rcx+19h], 1
0x18002fe28  jb      loc_18002FFAA
0x18002fe2e  mov     rcx, [rcx+10h]
0x18002fe32  mov     edx, 0Bh
0x18002fe37  mov     r8, rdi
0x18002fe3a  call    WPP_SF_
0x18002fe3f  jmp     loc_18002FFAA
0x18002fe44  xor     edx, edx; Val
0x18002fe46  lea     rcx, [rbp+57h+var_AC]; void *
0x18002fe4a  lea     r8d, [rdx+6Ch]; Size
0x18002fe4e  call    memset_0
0x18002fe53  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18002fe57  mov     [rbp+57h+RpcCallAttributes], 2
0x18002fe5e  xor     ecx, ecx; ClientBinding
0x18002fe60  call    cs:__imp_RpcServerInqCallAttributesW
0x18002fe66  mov     ebx, eax
0x18002fe68  test    eax, eax
0x18002fe6a  jz      short loc_18002FE9A
0x18002fe6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe73  cmp     rcx, r13
0x18002fe76  jz      loc_18002FFAA
0x18002fe7c  test    byte ptr [rcx+1Ch], 10h
0x18002fe80  jz      loc_18002FFAA
0x18002fe86  cmp     byte ptr [rcx+19h], 1
0x18002fe8a  jb      loc_18002FFAA
0x18002fe90  mov     edx, 0Ch
0x18002fe95  jmp     loc_18002FDDD
0x18002fe9a  mov     eax, 2
0x18002fe9f  cmp     [rbp+57h+var_58], ax
0x18002fea3  jz      loc_18002FF5C
0x18002fea9  cmp     [rbp+57h+var_58], r15w
0x18002feae  jz      loc_18002FF5C
0x18002feb4  xor     ecx, ecx; BindingHandle
0x18002feb6  call    cs:__imp_RpcImpersonateClient
0x18002febc  mov     ebx, eax
0x18002febe  test    eax, eax
0x18002fec0  jz      short loc_18002FEF0
0x18002fec2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fec9  cmp     rcx, r13
0x18002fecc  jz      loc_18002FFAA
0x18002fed2  test    byte ptr [rcx+1Ch], 10h
0x18002fed6  jz      loc_18002FFAA
0x18002fedc  cmp     byte ptr [rcx+19h], 1
0x18002fee0  jb      loc_18002FFAA
0x18002fee6  mov     edx, 0Dh
0x18002feeb  jmp     loc_18002FDDD
0x18002fef0  call    cs:__imp_GetCurrentThread
0x18002fef6  mov     edx, 8; DesiredAccess
0x18002fefb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002feff  mov     rcx, rax; ThreadHandle
0x18002ff02  lea     r8d, [rdx-7]; OpenAsSelf
0x18002ff06  call    cs:__imp_OpenThreadToken
0x18002ff0c  mov     edi, eax
0x18002ff0e  call    cs:__imp_RpcRevertToSelf
0x18002ff14  mov     ebx, eax
0x18002ff16  test    eax, eax
0x18002ff18  jz      short loc_18002FF47
0x18002ff1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff21  cmp     rcx, r13
0x18002ff24  jz      loc_18002FFAA
0x18002ff2a  test    byte ptr [rcx+1Ch], 10h
0x18002ff2e  jz      short loc_18002FFAA
0x18002ff30  cmp     byte ptr [rcx+19h], 1
0x18002ff34  jb      short loc_18002FFAA
0x18002ff36  mov     edx, 0Eh
0x18002ff3b  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18002ff42  jmp     loc_18002FDE0
0x18002ff47  test    edi, edi
0x18002ff49  jnz     short loc_18002FF55
0x18002ff4b  call    cs:__imp_GetLastError
0x18002ff51  mov     ebx, eax
0x18002ff53  jmp     short loc_18002FFAA
0x18002ff55  lea     rdi, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18002ff5c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002ff60  lea     r8, [rsp+120h+IsMember]; IsMember
0x18002ff65  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002ff69  call    cs:__imp_CheckTokenMembership
0x18002ff6f  test    eax, eax
0x18002ff71  jnz     short loc_18002FF9D
0x18002ff73  call    cs:__imp_GetLastError
0x18002ff79  mov     ebx, eax
0x18002ff7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff82  cmp     rcx, r13
0x18002ff85  jz      short loc_18002FFAA
0x18002ff87  test    byte ptr [rcx+1Ch], 10h
0x18002ff8b  jz      short loc_18002FFAA
0x18002ff8d  cmp     byte ptr [rcx+19h], 1
0x18002ff91  jb      short loc_18002FFAA
0x18002ff93  mov     edx, 0Fh
0x18002ff98  jmp     loc_18002FDDD
0x18002ff9d  mov     eax, [rsp+120h+IsMember]
0x18002ffa1  dec     eax
0x18002ffa3  neg     eax
0x18002ffa5  sbb     ebx, ebx
0x18002ffa7  and     ebx, r15d
0x18002ffaa  lea     rcx, [rsp+120h+ServerBinding]; Binding
0x18002ffaf  call    cs:__imp_RpcBindingFree
0x18002ffb5  cmp     [rsp+120h+StringBinding], rsi
0x18002ffba  jz      short loc_18002FFC7
0x18002ffbc  lea     rcx, [rsp+120h+StringBinding]; String
0x18002ffc1  call    cs:__imp_RpcStringFreeW
0x18002ffc7  cmp     [rsp+120h+Protseq], rsi
0x18002ffcc  jz      short loc_18002FFD9
0x18002ffce  lea     rcx, [rsp+120h+Protseq]; String
0x18002ffd3  call    cs:__imp_RpcStringFreeW
0x18002ffd9  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002ffdd  test    rcx, rcx
0x18002ffe0  jz      short loc_18002FFE8
0x18002ffe2  call    cs:__imp_CloseHandle
0x18002ffe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffef  cmp     rcx, r13
0x18002fff2  jz      short loc_180030018
0x18002fff4  test    byte ptr [rcx+1Ch], 10h
0x18002fff8  jz      short loc_180030018
0x18002fffa  cmp     byte ptr [rcx+19h], 2
0x18002fffe  jb      short loc_180030018
0x180030000  mov     rcx, [rcx+10h]
0x180030004  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18003000b  mov     edx, 10h
0x180030010  mov     r9d, ebx
0x180030013  call    WPP_SF_d
0x180030018  mov     eax, ebx
0x18003001a  mov     rcx, [rbp+57h+var_40]
0x18003001e  xor     rcx, rsp; StackCookie
0x180030021  call    __security_check_cookie
0x180030026  add     rsp, 0F8h
0x18003002d  pop     r15
0x18003002f  pop     r13
0x180030031  pop     rdi
0x180030032  pop     rsi
0x180030033  pop     rbx
0x180030034  pop     rbp
0x180030035  retn
```
