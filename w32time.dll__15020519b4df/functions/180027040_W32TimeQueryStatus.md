# W32TimeQueryStatus

- ea: `0x180027040`
- end: `0x180027393`
- name: `W32TimeQueryStatus`
- size: `851`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027040`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180027115`
- `RPCRT4!RpcStringFreeW` at `0x18002715c`
- `RPCRT4!RpcStringFreeW` at `0x18002721a`
- `RPCRT4!RpcStringFreeW` at `0x180027260`
- `RPCRT4!RpcStringFreeW` at `0x180027115`
- `RPCRT4!RpcStringFreeW` at `0x18002715c`
- `RPCRT4!RpcStringFreeW` at `0x18002721a`
- `RPCRT4!RpcStringFreeW` at `0x180027260`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800270ff`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180027204`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800270ff`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180027204`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180027331`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18002735f`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180027331`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18002735f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180027092`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800270d9`
- `RPCRT4!RpcStringBindingComposeW` at `0x180027092`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800270d9`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18002713b`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180027240`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18002713b`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x180027240`
- `RPCRT4!RpcBindingFree` at `0x1800271c3`
- `RPCRT4!RpcBindingFree` at `0x1800272d4`
- `RPCRT4!RpcBindingFree` at `0x1800271c3`
- `RPCRT4!RpcBindingFree` at `0x1800272d4`
- `RPCRT4!NdrClientCall3` at `0x180027192`
- `RPCRT4!NdrClientCall3` at `0x18002729a`
- `RPCRT4!NdrClientCall3` at `0x180027192`
- `RPCRT4!NdrClientCall3` at `0x18002729a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027382`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027382`

## pseudocode

```c
__int64 __fastcall W32TimeQueryStatus(RPC_WSTR NetworkAddr, HLOCAL *a2)
{
  unsigned int Pointer; // ebx
  RPC_BINDING_HANDLE v5; // r14
  HLOCAL v6; // rcx
  RPC_BINDING_HANDLE v8; // r15
  CLIENT_CALL_RETURN v9; // rax
  HLOCAL hMem; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR ServerPrincName[7]; // [rsp+40h] [rbp-38h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  hMem = 0;
  String = 0;
  if ( a2 )
  {
    Pointer = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME", 0, &String);
    if ( !Pointer )
    {
      Pointer = RpcBindingFromStringBindingW(String, &Binding);
      RpcStringFreeW(&String);
      v8 = Binding;
      ServerPrincName[0] = 0;
      if ( !RpcMgmtInqServerPrincNameW(Binding, 9u, ServerPrincName) )
        RpcBindingSetAuthInfoW(v8, ServerPrincName[0], 6u, 9u, 0, 0);
      if ( ServerPrincName[0] )
        RpcStringFreeW(ServerPrincName);
      if ( !Pointer )
      {
        ServerPrincName[0] = 0;
        v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, Binding, &hMem).Pointer;
        Pointer = (unsigned int)v9.Pointer;
        ServerPrincName[0] = (RPC_WSTR)v9.Pointer;
        RpcBindingFree(&Binding);
      }
    }
    if ( Pointer == 1717 || Pointer == 1722 )
    {
      Pointer = RpcStringBindingComposeW(
                  0,
                  (RPC_WSTR)L"ncacn_np",
                  NetworkAddr,
                  (RPC_WSTR)L"\\PIPE\\W32TIME_ALT",
                  0,
                  &String);
      if ( !Pointer )
      {
        Pointer = RpcBindingFromStringBindingW(String, &Binding);
        RpcStringFreeW(&String);
        v5 = Binding;
        ServerPrincName[0] = 0;
        if ( !RpcMgmtInqServerPrincNameW(Binding, 9u, ServerPrincName) )
          RpcBindingSetAuthInfoW(v5, ServerPrincName[0], 6u, 9u, 0, 0);
        if ( ServerPrincName[0] )
          RpcStringFreeW(ServerPrincName);
        if ( Pointer )
          goto LABEL_12;
        ServerPrincName[0] = 0;
        ServerPrincName[0] = (RPC_WSTR)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, Binding, &hMem).Pointer;
        Pointer = (unsigned int)ServerPrincName[0];
        RpcBindingFree(&Binding);
      }
    }
    if ( !Pointer )
    {
      if ( !hMem )
        return Pointer;
      *a2 = hMem;
      v6 = 0;
      hMem = 0;
LABEL_13:
      if ( v6 )
        LocalFree(v6);
      return Pointer;
    }
LABEL_12:
    v6 = hMem;
    goto LABEL_13;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180027040  mov     r11, rsp
0x180027043  mov     [r11+10h], rdx
0x180027047  mov     [r11+8], rcx
0x18002704b  push    rbx
0x18002704c  push    rsi
0x18002704d  push    rdi
0x18002704e  push    r14
0x180027050  push    r15
0x180027052  sub     rsp, 50h
0x180027056  mov     rsi, rdx
0x180027059  mov     r14, rcx
0x18002705c  xor     edi, edi
0x18002705e  mov     [r11+18h], rdi
0x180027062  mov     [r11-40h], rdi
0x180027066  mov     [r11+20h], rdi
0x18002706a  test    rdx, rdx
0x18002706d  jz      loc_180027370
0x180027073  lea     rax, [r11+20h]
0x180027077  mov     [r11-50h], rax
0x18002707b  mov     [r11-58h], rdi
0x18002707f  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x180027086  mov     r8, rcx; NetworkAddr
0x180027089  lea     rdx, ProtSeq; "ncacn_np"
0x180027090  xor     ecx, ecx; ObjUuid
0x180027092  call    cs:__imp_RpcStringBindingComposeW
0x180027099  nop     dword ptr [rax+rax+00h]
0x18002709e  mov     ebx, eax
0x1800270a0  test    eax, eax
0x1800270a2  jz      loc_1800271F4
0x1800270a8  cmp     ebx, 6B5h
0x1800270ae  jnz     loc_1800272E5
0x1800270b4  lea     rax, [rsp+78h+String]
0x1800270bc  mov     [rsp+78h+StringBinding], rax; StringBinding
0x1800270c1  mov     [rsp+78h+Options], rdi; Options
0x1800270c6  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x1800270cd  mov     r8, r14; NetworkAddr
0x1800270d0  lea     rdx, ProtSeq; "ncacn_np"
0x1800270d7  xor     ecx, ecx; ObjUuid
0x1800270d9  call    cs:__imp_RpcStringBindingComposeW
0x1800270e0  nop     dword ptr [rax+rax+00h]
0x1800270e5  mov     ebx, eax
0x1800270e7  test    eax, eax
0x1800270e9  jnz     loc_1800271CF
0x1800270ef  lea     rdx, [rsp+78h+Binding]; Binding
0x1800270f7  mov     rcx, [rsp+78h+String]; StringBinding
0x1800270ff  call    cs:__imp_RpcBindingFromStringBindingW
0x180027106  nop     dword ptr [rax+rax+00h]
0x18002710b  mov     ebx, eax
0x18002710d  lea     rcx, [rsp+78h+String]; String
0x180027115  call    cs:__imp_RpcStringFreeW
0x18002711c  nop     dword ptr [rax+rax+00h]
0x180027121  mov     r14, [rsp+78h+Binding]
0x180027129  mov     [rsp+78h+ServerPrincName], rdi
0x18002712e  lea     r8, [rsp+78h+ServerPrincName]; ServerPrincName
0x180027133  mov     edx, 9; AuthnSvc
0x180027138  mov     rcx, r14; Binding
0x18002713b  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x180027142  nop     dword ptr [rax+rax+00h]
0x180027147  test    eax, eax
0x180027149  jz      loc_180027314
0x18002714f  cmp     [rsp+78h+ServerPrincName], 0
0x180027155  jz      short loc_180027168
0x180027157  lea     rcx, [rsp+78h+ServerPrincName]; String
0x18002715c  call    cs:__imp_RpcStringFreeW
0x180027163  nop     dword ptr [rax+rax+00h]
0x180027168  test    ebx, ebx
0x18002716a  jnz     short loc_1800271D7
0x18002716c  mov     [rsp+78h+ServerPrincName], rdi
0x180027171  lea     rax, [rsp+78h+hMem]
0x180027176  mov     [rsp+78h+Options], rax
0x18002717b  mov     r9, [rsp+78h+Binding]
0x180027183  xor     r8d, r8d; pReturnValue
0x180027186  mov     edx, 6; nProcNum
0x18002718b  lea     rcx, pProxyInfo; pProxyInfo
0x180027192  call    cs:__imp_NdrClientCall3
0x180027199  nop     dword ptr [rax+rax+00h]
0x18002719e  mov     [rsp+78h+ServerPrincName], rax
0x1800271a3  mov     ebx, eax
0x1800271a5  mov     [rsp+78h+var_48], eax
0x1800271a9  jmp     short loc_1800271BB
0x1800271ab  mov     ebx, eax
0x1800271ad  mov     [rsp+78h+var_48], eax
0x1800271b1  xor     edi, edi
0x1800271b3  mov     rsi, [rsp+78h+arg_8]
0x1800271bb  lea     rcx, [rsp+78h+Binding]; Binding
0x1800271c3  call    cs:__imp_RpcBindingFree
0x1800271ca  nop     dword ptr [rax+rax+00h]
0x1800271cf  test    ebx, ebx
0x1800271d1  jz      loc_1800272F6
0x1800271d7  mov     rcx, [rsp+78h+hMem]; hMem
0x1800271dc  test    rcx, rcx
0x1800271df  jnz     loc_180027382
0x1800271e5  mov     eax, ebx
0x1800271e7  add     rsp, 50h
0x1800271eb  pop     r15
0x1800271ed  pop     r14
0x1800271ef  pop     rdi
0x1800271f0  pop     rsi
0x1800271f1  pop     rbx
0x1800271f2  retn
0x1800271f4  lea     rdx, [rsp+78h+Binding]; Binding
0x1800271fc  mov     rcx, [rsp+78h+String]; StringBinding
0x180027204  call    cs:__imp_RpcBindingFromStringBindingW
0x18002720b  nop     dword ptr [rax+rax+00h]
0x180027210  mov     ebx, eax
0x180027212  lea     rcx, [rsp+78h+String]; String
0x18002721a  call    cs:__imp_RpcStringFreeW
0x180027221  nop     dword ptr [rax+rax+00h]
0x180027226  mov     r15, [rsp+78h+Binding]
0x18002722e  mov     [rsp+78h+ServerPrincName], rdi
0x180027233  lea     r8, [rsp+78h+ServerPrincName]; ServerPrincName
0x180027238  mov     edx, 9; AuthnSvc
0x18002723d  mov     rcx, r15; Binding
0x180027240  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x180027247  nop     dword ptr [rax+rax+00h]
0x18002724c  test    eax, eax
0x18002724e  jz      loc_180027342
0x180027254  cmp     [rsp+78h+ServerPrincName], rdi
0x180027259  jz      short loc_18002726C
0x18002725b  lea     rcx, [rsp+78h+ServerPrincName]; String
0x180027260  call    cs:__imp_RpcStringFreeW
0x180027267  nop     dword ptr [rax+rax+00h]
0x18002726c  test    ebx, ebx
0x18002726e  jnz     loc_1800270A8
0x180027274  mov     [rsp+78h+ServerPrincName], rdi
0x180027279  lea     rax, [rsp+78h+hMem]
0x18002727e  mov     [rsp+78h+Options], rax
0x180027283  mov     r9, [rsp+78h+Binding]
0x18002728b  xor     r8d, r8d; pReturnValue
0x18002728e  mov     edx, 6; nProcNum
0x180027293  lea     rcx, pProxyInfo; pProxyInfo
0x18002729a  call    cs:__imp_NdrClientCall3
0x1800272a1  nop     dword ptr [rax+rax+00h]
0x1800272a6  mov     rbx, rax
0x1800272a9  mov     [rsp+78h+ServerPrincName], rax
0x1800272ae  mov     [rsp+78h+var_48], eax
0x1800272b2  jmp     short loc_1800272CC
0x1800272b4  mov     ebx, eax
0x1800272b6  mov     [rsp+78h+var_48], eax
0x1800272ba  xor     edi, edi
0x1800272bc  mov     rsi, [rsp+78h+arg_8]
0x1800272c4  mov     r14, [rsp+78h+arg_0]
0x1800272cc  lea     rcx, [rsp+78h+Binding]; Binding
0x1800272d4  call    cs:__imp_RpcBindingFree
0x1800272db  nop     dword ptr [rax+rax+00h]
0x1800272e0  jmp     loc_1800270A8
0x1800272e5  cmp     ebx, 6BAh
0x1800272eb  jnz     loc_1800271CF
0x1800272f1  jmp     loc_1800270B4
0x1800272f6  mov     rcx, [rsp+78h+hMem]
0x1800272fb  test    rcx, rcx
0x1800272fe  jz      loc_1800271E5
0x180027304  mov     [rsi], rcx
0x180027307  mov     rcx, rdi
0x18002730a  mov     [rsp+78h+hMem], rcx
0x18002730f  jmp     loc_1800271DC
0x180027314  mov     dword ptr [rsp+78h+StringBinding], edi; AuthzSvc
0x180027318  mov     [rsp+78h+Options], rdi; AuthIdentity
0x18002731d  mov     r9d, 9; AuthnSvc
0x180027323  mov     r8d, 6; AuthnLevel
0x180027329  mov     rdx, [rsp+78h+ServerPrincName]; ServerPrincName
0x18002732e  mov     rcx, r14; Binding
0x180027331  call    cs:__imp_RpcBindingSetAuthInfoW
0x180027338  nop     dword ptr [rax+rax+00h]
0x18002733d  jmp     loc_18002714F
0x180027342  mov     dword ptr [rsp+78h+StringBinding], edi; AuthzSvc
0x180027346  mov     [rsp+78h+Options], rdi; AuthIdentity
0x18002734b  mov     r9d, 9; AuthnSvc
0x180027351  mov     r8d, 6; AuthnLevel
0x180027357  mov     rdx, [rsp+78h+ServerPrincName]; ServerPrincName
0x18002735c  mov     rcx, r15; Binding
0x18002735f  call    cs:__imp_RpcBindingSetAuthInfoW
0x180027366  nop     dword ptr [rax+rax+00h]
0x18002736b  jmp     loc_180027254
0x180027370  mov     eax, 80070057h
0x180027375  add     rsp, 50h
0x180027379  pop     r15
0x18002737b  pop     r14
0x18002737d  pop     rdi
0x18002737e  pop     rsi
0x18002737f  pop     rbx
0x180027380  retn
0x180027382  call    cs:__imp_LocalFree
0x180027389  nop     dword ptr [rax+rax+00h]
0x18002738e  jmp     loc_1800271E5
```
