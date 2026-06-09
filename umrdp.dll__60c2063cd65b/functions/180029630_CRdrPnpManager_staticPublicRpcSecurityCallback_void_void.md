# CRdrPnpManager::staticPublicRpcSecurityCallback(void *,void *)

- ea: `0x180029630`
- end: `0x1800299c4`
- name: `?staticPublicRpcSecurityCallback@CRdrPnpManager@@CAJPEAX0@Z`
- size: `916`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b8f8`
- `0x18000c2e1`
- `0x18000f75c`
- `0x18000f79c`
- `0x180029630`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029900`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029900`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002967e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002967e`
- `RPCRT4!RpcImpersonateClient` at `0x1800298a6`
- `RPCRT4!RpcImpersonateClient` at `0x1800298a6`
- `RPCRT4!RpcRevertToSelf` at `0x180029910`
- `RPCRT4!RpcRevertToSelf` at `0x18002994b`
- `RPCRT4!RpcRevertToSelf` at `0x180029910`
- `RPCRT4!RpcRevertToSelf` at `0x18002994b`
- `RPCRT4!RpcStringFreeW` at `0x18002973a`
- `RPCRT4!RpcStringFreeW` at `0x180029749`
- `RPCRT4!RpcStringFreeW` at `0x180029765`
- `RPCRT4!RpcStringFreeW` at `0x18002973a`
- `RPCRT4!RpcStringFreeW` at `0x180029749`
- `RPCRT4!RpcStringFreeW` at `0x180029765`
- `RPCRT4!RpcStringBindingParseW` at `0x1800296e3`
- `RPCRT4!RpcStringBindingParseW` at `0x1800296e3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800297c7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800297c7`

## pseudocode

```c
__int64 __fastcall CRdrPnpManager::staticPublicRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  RPC_STATUS v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  RPC_STATUS v6; // ebx
  unsigned int v7; // eax
  int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  WINBOOL IsMember; // [rsp+30h] [rbp-59h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-51h] BYREF
  RPC_WSTR Protseq[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 RpcCallAttributes; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-31h] BYREF
  int v17; // [rsp+78h] [rbp-11h]
  int v18; // [rsp+80h] [rbp-9h]

  StringBinding = 0;
  Protseq[0] = 0;
  memset_0(&RpcCallAttributes, 0, 0x78u);
  v3 = RpcBindingToStringBindingW(Context, &StringBinding);
  if ( v3 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 18;
    goto LABEL_51;
  }
  v6 = RpcStringBindingParseW(StringBinding, 0, Protseq, 0, 0, 0);
  if ( v6 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        19,
        WPP_70aee318d17e395770d165b9e187b7ad_Traceguids,
        v7,
        v6);
    }
    RpcStringFreeW(&StringBinding);
    return 5;
  }
  RpcStringFreeW(&StringBinding);
  v8 = wcsicmp_0(Protseq[0], L"ncalrpc");
  RpcStringFreeW(Protseq);
  if ( v8 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 20;
    goto LABEL_32;
  }
  memset_0(v16, 0, 0x70u);
  RpcCallAttributes = 3;
  v3 = RpcServerInqCallAttributesW(Context, &RpcCallAttributes);
  if ( v3 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 21;
    goto LABEL_51;
  }
  if ( v17 != 6 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 22;
    goto LABEL_32;
  }
  if ( v18 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 23;
LABEL_32:
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v10,
      WPP_70aee318d17e395770d165b9e187b7ad_Traceguids,
      v9);
    return 5;
  }
  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 24;
    goto LABEL_51;
  }
  IsMember = 0;
  if ( !CheckTokenMembership(0, CRdrPnpManager::static_pLocalServiceSid, &IsMember) || !IsMember )
  {
    v3 = RpcRevertToSelf();
    if ( !v3
      || *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      return 5;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 25;
    goto LABEL_51;
  }
  v3 = RpcRevertToSelf();
  if ( !v3 )
    return 0;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 26;
LABEL_51:
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v5,
      WPP_70aee318d17e395770d165b9e187b7ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      v3);
  }
  return 5;
}

```

## disassembly

```asm
0x180029630  mov     [rsp-8+arg_0], rbx
0x180029635  mov     [rsp-8+arg_10], rdi
0x18002963a  push    rbp
0x18002963b  lea     rbp, [rsp-57h]
0x180029640  sub     rsp, 0E0h
0x180029647  mov     rax, cs:__security_cookie
0x18002964e  xor     rax, rsp
0x180029651  mov     [rbp+57h+var_10], rax
0x180029655  mov     rdi, rdx
0x180029658  mov     [rbp+57h+StringBinding], 0
0x180029660  xor     edx, edx; Val
0x180029662  mov     [rbp+57h+Protseq], 0
0x18002966a  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18002966e  lea     r8d, [rdx+78h]; Size
0x180029672  call    memset_0
0x180029677  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18002967b  mov     rcx, rdi; Binding
0x18002967e  call    cs:__imp_RpcBindingToStringBindingW
0x180029684  mov     ebx, eax
0x180029686  test    eax, eax
0x180029688  jz      short loc_1800296C4
0x18002968a  mov     rdx, cs:WPP_GLOBAL_Control
0x180029691  lea     rcx, WPP_GLOBAL_Control
0x180029698  cmp     rdx, rcx
0x18002969b  jz      loc_18002999E
0x1800296a1  test    byte ptr [rdx+1Ch], 1
0x1800296a5  jz      loc_18002999E
0x1800296ab  cmp     byte ptr [rdx+19h], 2
0x1800296af  jb      loc_18002999E
0x1800296b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800296ba  mov     edx, 12h
0x1800296bf  jmp     loc_180029980
0x1800296c4  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x1800296c8  lea     r8, [rbp+57h+Protseq]; Protseq
0x1800296cc  mov     [rsp+0E0h+NetworkOptions], 0; NetworkOptions
0x1800296d5  xor     r9d, r9d; NetworkAddr
0x1800296d8  xor     edx, edx; ObjUuid
0x1800296da  mov     [rsp+0E0h+Endpoint], 0; Endpoint
0x1800296e3  call    cs:__imp_RpcStringBindingParseW
0x1800296e9  mov     ebx, eax
0x1800296eb  test    eax, eax
0x1800296ed  jz      short loc_180029745
0x1800296ef  mov     rdx, cs:WPP_GLOBAL_Control
0x1800296f6  lea     rcx, WPP_GLOBAL_Control
0x1800296fd  cmp     rdx, rcx
0x180029700  jz      short loc_180029736
0x180029702  test    byte ptr [rdx+1Ch], 1
0x180029706  jz      short loc_180029736
0x180029708  cmp     byte ptr [rdx+19h], 2
0x18002970c  jb      short loc_180029736
0x18002970e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029713  mov     rcx, cs:WPP_GLOBAL_Control
0x18002971a  lea     r8, WPP_70aee318d17e395770d165b9e187b7ad_Traceguids
0x180029721  mov     edx, 13h
0x180029726  mov     dword ptr [rsp+0E0h+Endpoint], ebx
0x18002972a  mov     r9d, eax
0x18002972d  mov     rcx, [rcx+10h]
0x180029731  call    WPP_SF_Dd
0x180029736  lea     rcx, [rbp+57h+StringBinding]; String
0x18002973a  call    cs:__imp_RpcStringFreeW
0x180029740  jmp     loc_18002999E
0x180029745  lea     rcx, [rbp+57h+StringBinding]; String
0x180029749  call    cs:__imp_RpcStringFreeW
0x18002974f  mov     rcx, [rbp+57h+Protseq]; String1
0x180029753  lea     rdx, aNcalrpc; "ncalrpc"
0x18002975a  call    _wcsicmp_0
0x18002975f  lea     rcx, [rbp+57h+Protseq]; String
0x180029763  mov     ebx, eax
0x180029765  call    cs:__imp_RpcStringFreeW
0x18002976b  test    ebx, ebx
0x18002976d  jz      short loc_1800297A9
0x18002976f  mov     rax, cs:WPP_GLOBAL_Control
0x180029776  lea     rcx, WPP_GLOBAL_Control
0x18002977d  cmp     rax, rcx
0x180029780  jz      loc_18002999E
0x180029786  test    byte ptr [rax+1Ch], 1
0x18002978a  jz      loc_18002999E
0x180029790  cmp     byte ptr [rax+19h], 2
0x180029794  jb      loc_18002999E
0x18002979a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002979f  mov     edx, 14h
0x1800297a4  jmp     loc_180029885
0x1800297a9  xor     edx, edx; Val
0x1800297ab  lea     rcx, [rbp+57h+var_88]; void *
0x1800297af  lea     r8d, [rdx+70h]; Size
0x1800297b3  call    memset_0
0x1800297b8  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800297bc  mov     [rbp+57h+RpcCallAttributes], 3
0x1800297c4  mov     rcx, rdi; ClientBinding
0x1800297c7  call    cs:__imp_RpcServerInqCallAttributesW
0x1800297cd  mov     ebx, eax
0x1800297cf  test    eax, eax
0x1800297d1  jz      short loc_18002980D
0x1800297d3  mov     rdx, cs:WPP_GLOBAL_Control
0x1800297da  lea     rcx, WPP_GLOBAL_Control
0x1800297e1  cmp     rdx, rcx
0x1800297e4  jz      loc_18002999E
0x1800297ea  test    byte ptr [rdx+1Ch], 1
0x1800297ee  jz      loc_18002999E
0x1800297f4  cmp     byte ptr [rdx+19h], 2
0x1800297f8  jb      loc_18002999E
0x1800297fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029803  mov     edx, 15h
0x180029808  jmp     loc_180029980
0x18002980d  cmp     [rbp+57h+var_68], 6
0x180029811  jz      short loc_18002984A
0x180029813  mov     rax, cs:WPP_GLOBAL_Control
0x18002981a  lea     rcx, WPP_GLOBAL_Control
0x180029821  cmp     rax, rcx
0x180029824  jz      loc_18002999E
0x18002982a  test    byte ptr [rax+1Ch], 1
0x18002982e  jz      loc_18002999E
0x180029834  cmp     byte ptr [rax+19h], 2
0x180029838  jb      loc_18002999E
0x18002983e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029843  mov     edx, 16h
0x180029848  jmp     short loc_180029885
0x18002984a  cmp     [rbp+57h+var_60], 0
0x18002984e  jz      short loc_1800298A4
0x180029850  mov     rax, cs:WPP_GLOBAL_Control
0x180029857  lea     rcx, WPP_GLOBAL_Control
0x18002985e  cmp     rax, rcx
0x180029861  jz      loc_18002999E
0x180029867  test    byte ptr [rax+1Ch], 1
0x18002986b  jz      loc_18002999E
0x180029871  cmp     byte ptr [rax+19h], 2
0x180029875  jb      loc_18002999E
0x18002987b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029880  mov     edx, 17h
0x180029885  mov     rcx, cs:WPP_GLOBAL_Control
0x18002988c  lea     r8, WPP_70aee318d17e395770d165b9e187b7ad_Traceguids
0x180029893  mov     r9d, eax
0x180029896  mov     rcx, [rcx+10h]
0x18002989a  call    WPP_SF_D
0x18002989f  jmp     loc_18002999E
0x1800298a4  xor     ecx, ecx; BindingHandle
0x1800298a6  call    cs:__imp_RpcImpersonateClient
0x1800298ac  mov     ebx, eax
0x1800298ae  test    eax, eax
0x1800298b0  jz      short loc_1800298EC
0x1800298b2  mov     rdx, cs:WPP_GLOBAL_Control
0x1800298b9  lea     rcx, WPP_GLOBAL_Control
0x1800298c0  cmp     rdx, rcx
0x1800298c3  jz      loc_18002999E
0x1800298c9  test    byte ptr [rdx+1Ch], 1
0x1800298cd  jz      loc_18002999E
0x1800298d3  cmp     byte ptr [rdx+19h], 2
0x1800298d7  jb      loc_18002999E
0x1800298dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800298e2  mov     edx, 18h
0x1800298e7  jmp     loc_180029980
0x1800298ec  mov     rdx, cs:?static_pLocalServiceSid@CRdrPnpManager@@0PEAXEA; SidToCheck
0x1800298f3  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800298f7  xor     ecx, ecx; TokenHandle
0x1800298f9  mov     [rbp+57h+IsMember], 0
0x180029900  call    cs:__imp_CheckTokenMembership
0x180029906  test    eax, eax
0x180029908  jz      short loc_18002994B
0x18002990a  cmp     [rbp+57h+IsMember], 0
0x18002990e  jz      short loc_18002994B
0x180029910  call    cs:__imp_RpcRevertToSelf
0x180029916  mov     ebx, eax
0x180029918  test    eax, eax
0x18002991a  jz      short loc_180029947
0x18002991c  mov     rdx, cs:WPP_GLOBAL_Control
0x180029923  lea     rcx, WPP_GLOBAL_Control
0x18002992a  cmp     rdx, rcx
0x18002992d  jz      short loc_18002999E
0x18002992f  test    byte ptr [rdx+1Ch], 1
0x180029933  jz      short loc_18002999E
0x180029935  cmp     byte ptr [rdx+19h], 2
0x180029939  jb      short loc_18002999E
0x18002993b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029940  mov     edx, 1Ah
0x180029945  jmp     short loc_180029980
0x180029947  xor     eax, eax
0x180029949  jmp     short loc_1800299A3
0x18002994b  call    cs:__imp_RpcRevertToSelf
0x180029951  mov     ebx, eax
0x180029953  test    eax, eax
0x180029955  jz      short loc_18002999E
0x180029957  mov     rdx, cs:WPP_GLOBAL_Control
0x18002995e  lea     rcx, WPP_GLOBAL_Control
0x180029965  cmp     rdx, rcx
0x180029968  jz      short loc_18002999E
0x18002996a  test    byte ptr [rdx+1Ch], 1
0x18002996e  jz      short loc_18002999E
0x180029970  cmp     byte ptr [rdx+19h], 2
0x180029974  jb      short loc_18002999E
0x180029976  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002997b  mov     edx, 19h
0x180029980  mov     rcx, cs:WPP_GLOBAL_Control
0x180029987  lea     r8, WPP_70aee318d17e395770d165b9e187b7ad_Traceguids
0x18002998e  mov     r9d, eax
0x180029991  mov     dword ptr [rsp+0E0h+Endpoint], ebx
0x180029995  mov     rcx, [rcx+10h]
0x180029999  call    WPP_SF_Dd
0x18002999e  mov     eax, 5
0x1800299a3  mov     rcx, [rbp+57h+var_10]
0x1800299a7  xor     rcx, rsp; StackCookie
0x1800299aa  call    __security_check_cookie
0x1800299af  lea     r11, [rsp+0E0h+var_s0]
0x1800299b7  mov     rbx, [r11+10h]
0x1800299bb  mov     rdi, [r11+20h]
0x1800299bf  mov     rsp, r11
0x1800299c2  pop     rbp
0x1800299c3  retn
```
