# wfdClientRpcCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180003f40`
- end: `0x18000428f`
- name: `?wfdClientRpcCallback@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `847`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800021cc`
- `0x180003f40`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x180012154`
- `0x18001de28`
- `0x18001de80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fe6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000413c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000413c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180004073`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180004073`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003fb1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003fb1`
- `RPCRT4!RpcExceptionFilter` at `0x180060360`
- `RPCRT4!RpcExceptionFilter` at `0x180060360`

## pseudocode

```c
void __fastcall wfdClientRpcCallback(PRPC_ASYNC_STATE pAsync, void *a2, enum _RPC_ASYNC_EVENT a3)
{
  int v5; // r12d
  union DOT11_OUI_HEADER *v6; // rcx
  _QWORD *UserInfo; // rdi
  unsigned int v8; // esi
  _QWORD *v9; // r14
  unsigned int *v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // edx
  MIDL_STUBLESS_PROXY_INFO *v13; // rcx
  int Reply; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v15; // [rsp+88h] [rbp+20h]

  Reply = 0;
  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !pAsync )
  {
    UserInfo = 0;
LABEL_27:
    v8 = 87;
    goto LABEL_19;
  }
  UserInfo = pAsync->UserInfo;
  v15 = UserInfo;
  if ( !UserInfo )
  {
    if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v6 + 105)
      && (*((_DWORD *)v6 + 27) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 12), 11, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    goto LABEL_27;
  }
  v8 = 0;
  if ( a3 || (v8 = RpcAsyncCompleteCall(pAsync, &Reply), v6 = WPP_GLOBAL_Control, v8) || Reply )
  {
    if ( Reply )
    {
      if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)v6 + 105) >= 4u
        && (*((_DWORD *)v6 + 27) & 0x1000) != 0 )
      {
        WPP_SF_DDd(*((_QWORD *)v6 + 12), 12, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      }
    }
    else if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
           && *((_BYTE *)v6 + 105)
           && (*((_DWORD *)v6 + 27) & 0x1000) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)v6 + 12), 13, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, 0, v8);
    }
    v5 = 1;
  }
  if ( v5 )
    goto LABEL_28;
  EnterCriticalSection((LPCRITICAL_SECTION)(UserInfo + 21));
  v9 = UserInfo + 20;
  v10 = (unsigned int *)UserInfo[20];
  if ( v10 )
  {
    if ( *((_DWORD *)UserInfo + 38) )
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_DDqq(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          14,
          WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids,
          *v10,
          v10[1],
          UserInfo[1],
          UserInfo[4]);
      }
      wfdClientForwardNotificationFromServer((const struct _WFD_CLIENT_CONTEXT *)UserInfo);
    }
    v11 = *(_QWORD *)(*v9 + 32LL);
    if ( v11 )
      FreeWLMem(v11);
    FreeWLMem(*v9);
    *v9 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(UserInfo + 21));
  if ( *((_DWORD *)UserInfo + 38) )
  {
    if ( *((_DWORD *)UserInfo + 56) )
    {
      v12 = 3;
      v13 = (MIDL_STUBLESS_PROXY_INFO *)&winwlan_lowpriv_ProxyInfo;
    }
    else
    {
      v12 = 23;
      v13 = (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo;
    }
    Ndr64AsyncClientCall(v13, v12, 0, UserInfo + 5, *UserInfo, UserInfo + 20);
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v5 = 1;
    v6 = WPP_GLOBAL_Control;
  }
LABEL_19:
  if ( v5 )
  {
LABEL_28:
    SetEvent((HANDLE)UserInfo[26]);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v6 + 105) >= 4u
    && (*((_BYTE *)v6 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v6 + 12), 17, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v8);
  }
}

```

## disassembly

```asm
0x180003f40  mov     [rsp+arg_8], rsi
0x180003f45  push    rdi
0x180003f46  push    r12
0x180003f48  push    r13
0x180003f4a  push    r14
0x180003f4c  push    r15
0x180003f4e  sub     rsp, 40h
0x180003f52  mov     r13d, r8d
0x180003f55  mov     r14, rcx
0x180003f58  mov     [rsp+68h+Reply], 0
0x180003f60  xor     r12d, r12d
0x180003f63  lea     r15, WPP_GLOBAL_Control
0x180003f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f71  cmp     rcx, r15
0x180003f74  jz      short loc_180003F80
0x180003f76  cmp     byte ptr [rcx+69h], 4
0x180003f7a  jnb     loc_180004155
0x180003f80  test    r14, r14
0x180003f83  jz      loc_18000412C
0x180003f89  mov     rdi, [r14+18h]
0x180003f8d  mov     [rsp+68h+arg_18], rdi
0x180003f95  test    rdi, rdi
0x180003f98  jz      loc_180004180
0x180003f9e  xor     esi, esi
0x180003fa0  test    r13d, r13d
0x180003fa3  jnz     loc_1800041B5
0x180003fa9  lea     rdx, [rsp+68h+Reply]; Reply
0x180003fae  mov     rcx, r14; pAsync
0x180003fb1  call    cs:__imp_RpcAsyncCompleteCall
0x180003fb7  mov     esi, eax
0x180003fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fc0  test    eax, eax
0x180003fc2  jnz     loc_1800041B5
0x180003fc8  cmp     [rsp+68h+Reply], r12d
0x180003fcd  jnz     loc_1800041B5
0x180003fd3  test    r12d, r12d
0x180003fd6  jnz     loc_180004135
0x180003fdc  lea     r13, [rdi+0A8h]
0x180003fe3  mov     rcx, r13; lpCriticalSection
0x180003fe6  call    cs:__imp_EnterCriticalSection
0x180003fec  lea     r14, [rdi+0A0h]
0x180003ff3  mov     r9, [r14]
0x180003ff6  test    r9, r9
0x180003ff9  jz      short loc_180004027
0x180003ffb  cmp     [rdi+98h], r12d
0x180004002  jnz     loc_180004235
0x180004008  mov     rax, [r14]
0x18000400b  mov     rcx, [rax+20h]
0x18000400f  test    rcx, rcx
0x180004012  jnz     loc_18000414B
0x180004018  mov     rcx, [r14]
0x18000401b  call    FreeWLMem
0x180004020  mov     qword ptr [r14], 0
0x180004027  mov     rcx, r13; lpCriticalSection
0x18000402a  call    cs:__imp_LeaveCriticalSection
0x180004030  cmp     dword ptr [rdi+98h], 0
0x180004037  jz      loc_1800040F7
0x18000403d  lea     r9, [rdi+28h]
0x180004041  mov     rax, [rdi]
0x180004044  mov     [rsp+68h+var_40], r14
0x180004049  xor     r8d, r8d; pReturnValue
0x18000404c  mov     [rsp+68h+var_48], rax
0x180004051  cmp     [rdi+0E0h], r8d
0x180004058  jnz     short loc_180004067
0x18000405a  lea     edx, [r8+17h]
0x18000405e  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; _MIDL_STUBLESS_PROXY_INFO const winwlan_ProxyInfo
0x180004065  jmp     short loc_180004073
0x180004067  mov     edx, 3; nProcNum
0x18000406c  lea     rcx, ?winwlan_lowpriv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180004073  call    cs:__imp_Ndr64AsyncClientCall
0x180004079  mov     rcx, cs:WPP_GLOBAL_Control
0x180004080  jmp     short loc_1800040DA
0x180004082  mov     esi, eax
0x180004084  lea     rax, WPP_GLOBAL_Control
0x18000408b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004092  cmp     rcx, rax
0x180004095  jz      short loc_1800040C5
0x180004097  cmp     byte ptr [rcx+69h], 1
0x18000409b  jb      short loc_1800040C5
0x18000409d  test    dword ptr [rcx+6Ch], 1000h
0x1800040a4  jz      short loc_1800040C5
0x1800040a6  mov     edx, 10h
0x1800040ab  mov     r9d, esi
0x1800040ae  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800040b5  mov     rcx, [rcx+60h]
0x1800040b9  call    WPP_SF_d
0x1800040be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040c5  mov     r12d, 1
0x1800040cb  lea     r15, WPP_GLOBAL_Control
0x1800040d2  mov     rdi, [rsp+68h+arg_18]
0x1800040da  test    r12d, r12d
0x1800040dd  jnz     short loc_180004135
0x1800040df  cmp     rcx, r15
0x1800040e2  jnz     short loc_180004106
0x1800040e4  mov     rsi, [rsp+68h+arg_8]
0x1800040e9  add     rsp, 40h
0x1800040ed  pop     r15
0x1800040ef  pop     r14
0x1800040f1  pop     r13
0x1800040f3  pop     r12
0x1800040f5  pop     rdi
0x1800040f6  retn
0x1800040f7  mov     r12d, 1
0x1800040fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004104  jmp     short loc_1800040DA
0x180004106  cmp     byte ptr [rcx+69h], 4
0x18000410a  jb      short loc_1800040E4
0x18000410c  test    byte ptr [rcx+6Ch], 2
0x180004110  jz      short loc_1800040E4
0x180004112  mov     edx, 11h
0x180004117  mov     r9d, esi
0x18000411a  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180004121  mov     rcx, [rcx+60h]
0x180004125  call    WPP_SF_d
0x18000412a  jmp     short loc_1800040E4
0x18000412c  xor     edi, edi
0x18000412e  mov     esi, 57h ; 'W'
0x180004133  jmp     short loc_1800040DA
0x180004135  mov     rcx, [rdi+0D0h]; hEvent
0x18000413c  call    cs:__imp_SetEvent
0x180004142  mov     rcx, cs:WPP_GLOBAL_Control
0x180004149  jmp     short loc_1800040DF
0x18000414b  call    FreeWLMem
0x180004150  jmp     loc_180004018
0x180004155  test    byte ptr [rcx+6Ch], 2
0x180004159  jz      loc_180003F80
0x18000415f  mov     edx, 0Ah
0x180004164  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18000416b  mov     rcx, [rcx+60h]
0x18000416f  call    WPP_SF_
0x180004174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417b  jmp     loc_180003F80
0x180004180  cmp     rcx, r15
0x180004183  jz      short loc_18000412E
0x180004185  cmp     byte ptr [rcx+69h], 1
0x180004189  jb      short loc_18000412E
0x18000418b  test    dword ptr [rcx+6Ch], 1000h
0x180004192  jz      short loc_18000412E
0x180004194  mov     edx, 0Bh
0x180004199  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800041a0  mov     rcx, [rcx+60h]
0x1800041a4  call    WPP_SF_
0x1800041a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041b0  jmp     loc_18000412E
0x1800041b5  mov     r9d, [rsp+68h+Reply]
0x1800041ba  test    r9d, r9d
0x1800041bd  jz      short loc_1800041F3
0x1800041bf  cmp     rcx, r15
0x1800041c2  jz      short loc_18000422A
0x1800041c4  cmp     byte ptr [rcx+69h], 4
0x1800041c8  jb      short loc_18000422A
0x1800041ca  test    dword ptr [rcx+6Ch], 1000h
0x1800041d1  jz      short loc_18000422A
0x1800041d3  mov     edx, 0Ch
0x1800041d8  mov     dword ptr [rsp+68h+var_40], r13d
0x1800041dd  mov     dword ptr [rsp+68h+var_48], esi
0x1800041e1  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800041e8  mov     rcx, [rcx+60h]
0x1800041ec  call    WPP_SF_DDd
0x1800041f1  jmp     short loc_180004223
0x1800041f3  cmp     rcx, r15
0x1800041f6  jz      short loc_18000422A
0x1800041f8  cmp     byte ptr [rcx+69h], 1
0x1800041fc  jb      short loc_18000422A
0x1800041fe  test    dword ptr [rcx+6Ch], 1000h
0x180004205  jz      short loc_18000422A
0x180004207  mov     edx, 0Dh
0x18000420c  mov     dword ptr [rsp+68h+var_48], esi
0x180004210  xor     r9d, r9d
0x180004213  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18000421a  mov     rcx, [rcx+60h]
0x18000421e  call    WPP_SF_dd
0x180004223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000422a  mov     r12d, 1
0x180004230  jmp     loc_180003FD3
0x180004235  xor     esi, esi
0x180004237  mov     rcx, cs:WPP_GLOBAL_Control
0x18000423e  cmp     rcx, r15
0x180004241  jz      short loc_180004282
0x180004243  cmp     byte ptr [rcx+69h], 4
0x180004247  jb      short loc_180004282
0x180004249  test    dword ptr [rcx+6Ch], 1000h
0x180004250  jz      short loc_180004282
0x180004252  lea     edx, [rsi+0Eh]
0x180004255  mov     rax, [rdi+20h]
0x180004259  mov     [rsp+68h+var_38], rax
0x18000425e  mov     rax, [rdi+8]
0x180004262  mov     [rsp+68h+var_40], rax
0x180004267  mov     eax, [r9+4]
0x18000426b  mov     dword ptr [rsp+68h+var_48], eax
0x18000426f  mov     r9d, [r9]
0x180004272  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180004279  mov     rcx, [rcx+60h]
0x18000427d  call    WPP_SF_DDqq
0x180004282  mov     rcx, rdi; struct _WFD_CLIENT_CONTEXT *
0x180004285  call    ?wfdClientForwardNotificationFromServer@@YAXPEBU_WFD_CLIENT_CONTEXT@@@Z; wfdClientForwardNotificationFromServer(_WFD_CLIENT_CONTEXT const *)
0x18000428a  jmp     loc_180004008
0x180060352  push    rbp
0x180060354  sub     rsp, 40h
0x180060358  mov     rbp, rdx
0x18006035b  mov     rcx, [rcx]
0x18006035e  mov     ecx, [rcx]; ExceptionCode
0x180060360  call    cs:__imp_RpcExceptionFilter
0x180060366  nop
0x180060367  add     rsp, 40h
0x18006036b  pop     rbp
0x18006036c  retn
```
