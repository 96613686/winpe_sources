# WcmOpenOnDemandRequestHandleByWwanProfileName

- ea: `0x180012b10`
- end: `0x180012ed6`
- name: `WcmOpenOnDemandRequestHandleByWwanProfileName`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x180001518`
- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180008a90`
- `0x18000c7c0`
- `0x18000c8e0`
- `0x18000d264`
- `0x18000e7c8`
- `0x1800111dc`
- `0x180012b10`
- `0x18001473c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180012bd9`
- `RPCRT4!NdrClientCall3` at `0x180012bd9`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180012d97`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180012d97`
- `RPCRT4!RpcExceptionFilter` at `0x18001d2c1`
- `RPCRT4!RpcExceptionFilter` at `0x18001d2e3`
- `RPCRT4!RpcExceptionFilter` at `0x18001d2c1`
- `RPCRT4!RpcExceptionFilter` at `0x18001d2e3`
- `MobileNetworking!HtNewHandle` at `0x180012d26`
- `MobileNetworking!HtNewHandle` at `0x180012d26`

## string_xrefs

- `0x180012b8f`: `WcmOpenOnDemandRequestHandleByWwanProfileName`
- `0x180012e94`: `WcmOpenOnDemandRequestHandleByWwanProfileName`

## pseudocode

```c
__int64 __fastcall WcmOpenOnDemandRequestHandleByWwanProfileName(
        _OWORD *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CLIENT_CALL_RETURN v6; // rax
  unsigned int Pointer; // ebx
  int v8; // ebx
  unsigned int v9; // eax
  WcmPolicyManager *v10; // rcx
  __int64 v11; // rdx
  struct WCM_ONDEMAND_HANDLE_CONTEXT *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // r8d
  struct WCM_ONDEMAND_HANDLE_CONTEXT *v17; // [rsp+48h] [rbp-4B0h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-4A8h]
  WCHAR *Simple; // [rsp+58h] [rbp-4A0h]
  unsigned __int16 *v20; // [rsp+60h] [rbp-498h]
  _OWORD *v21; // [rsp+68h] [rbp-490h]
  __int64 v22; // [rsp+70h] [rbp-488h] BYREF
  __int128 v23; // [rsp+78h] [rbp-480h]
  void *ContextHandle; // [rsp+88h] [rbp-470h] BYREF
  __int64 v25; // [rsp+90h] [rbp-468h] BYREF
  __int16 v26; // [rsp+98h] [rbp-460h] BYREF
  unsigned __int16 v27[264]; // [rsp+A0h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+2B0h] [rbp-248h] BYREF

  v21 = a1;
  v18 = a2;
  v20 = a3;
  ContextHandle = 0;
  v25 = 0;
  v17 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmOpenOnDemandRequestHandleByWwanProfileName");
  }
  v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001F060, 0xCu, 0, &v26, a1, a2, &ContextHandle).Pointer;
  Pointer = (unsigned int)v6.Pointer;
  Simple = (WCHAR *)v6.Simple;
  if ( LODWORD(v6.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
        LODWORD(v6.Pointer));
    }
    v8 = ServiceStatus(Pointer);
    goto LABEL_23;
  }
  v9 = ClientCreateOnDemandContext(&v17);
  v8 = v9;
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 25)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v11 = 100;
LABEL_16:
    WPP_SF_D(*((_QWORD *)v10 + 2), v11, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, v9);
    goto LABEL_23;
  }
  v12 = v17;
  *(_QWORD *)v17 = ContextHandle;
  v9 = HtNewHandle(g_hHandleTable, v12, 1129074260, ClientDestroyOnDemandContext, 1, &v25);
  v8 = v9;
  if ( !v9 )
  {
    v13 = v25;
    *(_QWORD *)a3 = v25;
    *((_QWORD *)v17 + 1) = v13;
    goto LABEL_23;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 101;
    goto LABEL_16;
  }
LABEL_23:
  if ( v8 )
  {
    if ( ContextHandle )
      RpcCloseOnDemandRequestHandle(&ContextHandle);
    if ( v17 )
      ClientDestroyOnDemandContext((char *)v17);
  }
  GetContextInfo(Filename, v27);
  if ( (unsigned int)dword_18002A000 > 5 )
  {
    v20 = v27;
    Simple = Filename;
    LODWORD(v17) = v8;
    v18 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v14,
      byte_180024B65);
  }
  if ( v8 > 0 )
    v15 = (unsigned __int16)v8 | 0x80070000;
  else
    v15 = v8;
  v22 = 4;
  v23 = *a1;
  NetworkingTriageScenario::OnDemand::OnDemandRequestByWwanProfileAction(
    (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)&v22,
    a2,
    v15);
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmOpenOnDemandRequestHandleByWwanProfileName",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012b10  mov     [rsp+arg_18], rbx
0x180012b15  push    rsi
0x180012b16  push    rdi
0x180012b17  push    r12
0x180012b19  push    r14
0x180012b1b  push    r15
0x180012b1d  sub     rsp, 4D0h
0x180012b24  mov     rax, cs:__security_cookie
0x180012b2b  xor     rax, rsp
0x180012b2e  mov     [rsp+4F8h+var_38], rax
0x180012b36  mov     r14, r8
0x180012b39  mov     r15, rdx
0x180012b3c  mov     r12, rcx
0x180012b3f  mov     [rsp+4F8h+var_490], rcx
0x180012b44  mov     [rsp+4F8h+var_4A8], rdx
0x180012b49  mov     [rsp+4F8h+var_498], r8
0x180012b4e  xor     edi, edi
0x180012b50  mov     [rsp+4F8h+ContextHandle], rdi
0x180012b58  mov     [rsp+4F8h+var_468], rdi
0x180012b60  mov     [rsp+4F8h+var_4B0], rdi
0x180012b65  mov     [rsp+4F8h+var_460], di
0x180012b6d  lea     rsi, WPP_GLOBAL_Control
0x180012b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b7b  cmp     rcx, rsi
0x180012b7e  jz      short loc_180012BA7
0x180012b80  cmp     byte ptr [rcx+19h], 5
0x180012b84  jb      short loc_180012BA7
0x180012b86  test    byte ptr [rcx+1Ch], 1
0x180012b8a  jz      short loc_180012BA7
0x180012b8c  lea     edx, [rdi+61h]
0x180012b8f  lea     r9, aWcmopenondeman_1; "WcmOpenOnDemandRequestHandleByWwanProfi"...
0x180012b96  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012b9d  mov     rcx, [rcx+10h]
0x180012ba1  call    WPP_SF_s
0x180012ba6  nop
0x180012ba7  mov     [rsp+4F8h+var_4A0], rdi
0x180012bac  lea     rax, [rsp+4F8h+ContextHandle]
0x180012bb4  mov     [rsp+4F8h+var_4C8], rax
0x180012bb9  mov     [rsp+4F8h+var_4D0], r15
0x180012bbe  mov     [rsp+4F8h+var_4D8], r12
0x180012bc3  lea     r9, [rsp+4F8h+var_460]
0x180012bcb  xor     r8d, r8d; pReturnValue
0x180012bce  lea     edx, [r8+0Ch]; nProcNum
0x180012bd2  lea     rcx, stru_18001F060; pProxyInfo
0x180012bd9  call    cs:__imp_NdrClientCall3
0x180012be0  nop     dword ptr [rax+rax+00h]
0x180012be5  mov     rbx, rax
0x180012be8  mov     [rsp+4F8h+var_4A0], rax
0x180012bed  mov     [rsp+4F8h+var_4B8], eax
0x180012bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bf8  jmp     short loc_180012C56
0x180012bfa  mov     ebx, eax
0x180012bfc  mov     [rsp+4F8h+var_4B8], eax
0x180012c00  lea     rdx, WPP_GLOBAL_Control
0x180012c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c0e  cmp     rcx, rdx
0x180012c11  jz      short loc_180012C3E
0x180012c13  cmp     byte ptr [rcx+19h], 1
0x180012c17  jb      short loc_180012C3E
0x180012c19  test    byte ptr [rcx+1Ch], 1
0x180012c1d  jz      short loc_180012C3E
0x180012c1f  mov     edx, 62h ; 'b'
0x180012c24  mov     r9d, eax
0x180012c27  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012c2e  mov     rcx, [rcx+10h]
0x180012c32  call    WPP_SF_D
0x180012c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c3e  xor     edi, edi
0x180012c40  lea     rsi, WPP_GLOBAL_Control
0x180012c47  mov     r14, [rsp+4F8h+var_498]
0x180012c4c  mov     r12, [rsp+4F8h+var_490]
0x180012c51  mov     r15, [rsp+4F8h+var_4A8]
0x180012c56  test    ebx, ebx
0x180012c58  jz      short loc_180012C95
0x180012c5a  cmp     rcx, rsi
0x180012c5d  jz      short loc_180012C83
0x180012c5f  cmp     byte ptr [rcx+19h], 1
0x180012c63  jb      short loc_180012C83
0x180012c65  test    byte ptr [rcx+1Ch], 1
0x180012c69  jz      short loc_180012C83
0x180012c6b  mov     edx, 63h ; 'c'
0x180012c70  mov     r9d, ebx
0x180012c73  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012c7a  mov     rcx, [rcx+10h]
0x180012c7e  call    WPP_SF_D
0x180012c83  mov     ecx, ebx; unsigned int
0x180012c85  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180012c8a  mov     ebx, eax
0x180012c8c  mov     [rsp+4F8h+var_4B8], eax
0x180012c90  jmp     loc_180012D72
0x180012c95  lea     rcx, [rsp+4F8h+var_4B0]; struct WCM_ONDEMAND_HANDLE_CONTEXT **
0x180012c9a  call    ?ClientCreateOnDemandContext@@YAKPEAPEAUWCM_ONDEMAND_HANDLE_CONTEXT@@@Z; ClientCreateOnDemandContext(WCM_ONDEMAND_HANDLE_CONTEXT * *)
0x180012c9f  mov     ebx, eax
0x180012ca1  mov     [rsp+4F8h+var_4B8], eax
0x180012ca5  test    eax, eax
0x180012ca7  jz      short loc_180012CEA
0x180012ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cb0  cmp     rcx, rsi
0x180012cb3  jz      loc_180012D72
0x180012cb9  cmp     byte ptr [rcx+19h], 1
0x180012cbd  jb      loc_180012D72
0x180012cc3  test    byte ptr [rcx+1Ch], 1
0x180012cc7  jz      loc_180012D72
0x180012ccd  mov     edx, 64h ; 'd'
0x180012cd2  mov     r9d, eax
0x180012cd5  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012cdc  mov     rcx, [rcx+10h]
0x180012ce0  call    WPP_SF_D
0x180012ce5  jmp     loc_180012D72
0x180012cea  mov     rax, [rsp+4F8h+ContextHandle]
0x180012cf2  mov     rcx, [rsp+4F8h+var_4B0]
0x180012cf7  mov     [rcx], rax
0x180012cfa  lea     rax, [rsp+4F8h+var_468]
0x180012d02  mov     [rsp+4F8h+var_4D0], rax
0x180012d07  mov     dword ptr [rsp+4F8h+var_4D8], 1
0x180012d0f  lea     r9, ?ClientDestroyOnDemandContext@@YAXPEAX@Z; ClientDestroyOnDemandContext(void *)
0x180012d16  mov     r8d, 434C4E54h
0x180012d1c  mov     rdx, rcx
0x180012d1f  mov     rcx, cs:g_hHandleTable
0x180012d26  call    cs:__imp_HtNewHandle
0x180012d2d  nop     dword ptr [rax+rax+00h]
0x180012d32  mov     ebx, eax
0x180012d34  mov     [rsp+4F8h+var_4B8], eax
0x180012d38  test    eax, eax
0x180012d3a  jz      short loc_180012D5E
0x180012d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d43  cmp     rcx, rsi
0x180012d46  jz      short loc_180012D72
0x180012d48  cmp     byte ptr [rcx+19h], 1
0x180012d4c  jb      short loc_180012D72
0x180012d4e  test    byte ptr [rcx+1Ch], 1
0x180012d52  jz      short loc_180012D72
0x180012d54  mov     edx, 65h ; 'e'
0x180012d59  jmp     loc_180012CD2
0x180012d5e  mov     rcx, [rsp+4F8h+var_468]
0x180012d66  mov     [r14], rcx
0x180012d69  mov     rax, [rsp+4F8h+var_4B0]
0x180012d6e  mov     [rax+8], rcx
0x180012d72  test    ebx, ebx
0x180012d74  jz      short loc_180012DC7
0x180012d76  cmp     [rsp+4F8h+ContextHandle], rdi
0x180012d7e  jz      short loc_180012DB8
0x180012d80  lea     rcx, [rsp+4F8h+ContextHandle]
0x180012d88  call    RpcCloseOnDemandRequestHandle
0x180012d8d  jmp     short loc_180012DB8
0x180012d8f  lea     rcx, [rsp+4F8h+ContextHandle]; ContextHandle
0x180012d97  call    cs:__imp_RpcSsDestroyClientContext
0x180012d9e  nop     dword ptr [rax+rax+00h]
0x180012da3  lea     rsi, WPP_GLOBAL_Control
0x180012daa  mov     ebx, [rsp+4F8h+var_4B8]
0x180012dae  mov     r12, [rsp+4F8h+var_490]
0x180012db3  mov     r15, [rsp+4F8h+var_4A8]
0x180012db8  mov     rcx, [rsp+4F8h+var_4B0]; lpMem
0x180012dbd  test    rcx, rcx
0x180012dc0  jz      short loc_180012DC7
0x180012dc2  call    ?ClientDestroyOnDemandContext@@YAXPEAX@Z; ClientDestroyOnDemandContext(void *)
0x180012dc7  lea     rdx, [rsp+4F8h+var_458]; unsigned __int16 *
0x180012dcf  lea     rcx, [rsp+4F8h+Filename]; lpFilename
0x180012dd7  call    ?GetContextInfo@@YAXPEAG0@Z; GetContextInfo(ushort *,ushort *)
0x180012ddc  mov     eax, cs:dword_18002A000
0x180012de2  cmp     eax, 5
0x180012de5  jbe     short loc_180012E3E
0x180012de7  lea     rax, [rsp+4F8h+var_458]
0x180012def  mov     [rsp+4F8h+var_498], rax
0x180012df4  lea     rax, [rsp+4F8h+Filename]
0x180012dfc  mov     [rsp+4F8h+var_4A0], rax
0x180012e01  mov     dword ptr [rsp+4F8h+var_4B0], ebx
0x180012e05  mov     [rsp+4F8h+var_4A8], r15
0x180012e0a  lea     rax, [rsp+4F8h+var_498]
0x180012e0f  mov     [rsp+4F8h+var_4C0], rax
0x180012e14  lea     rax, [rsp+4F8h+var_4A0]
0x180012e19  mov     [rsp+4F8h+var_4C8], rax
0x180012e1e  lea     rax, [rsp+4F8h+var_4B0]
0x180012e23  mov     [rsp+4F8h+var_4D0], rax
0x180012e28  lea     rax, [rsp+4F8h+var_4A8]
0x180012e2d  mov     [rsp+4F8h+var_4D8], rax
0x180012e32  lea     rdx, byte_180024B65
0x180012e39  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180012e3e  test    ebx, ebx
0x180012e40  jg      short loc_180012E47
0x180012e42  mov     r8d, ebx
0x180012e45  jmp     short loc_180012E52
0x180012e47  movzx   r8d, bx
0x180012e4b  or      r8d, 80070000h; int
0x180012e52  mov     [rsp+4F8h+var_488], 4
0x180012e5b  movups  xmm0, xmmword ptr [r12]
0x180012e60  movdqu  [rsp+4F8h+var_480], xmm0
0x180012e66  mov     rdx, r15; unsigned __int16 *
0x180012e69  lea     rcx, [rsp+4F8h+var_488]; struct NetworkingTriageScenario::OnDemand::RequiredFields *
0x180012e6e  call    ?OnDemandRequestByWwanProfileAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBGJ@Z; NetworkingTriageScenario::OnDemand::OnDemandRequestByWwanProfileAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,ushort const *,long)
0x180012e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e7a  cmp     rcx, rsi
0x180012e7d  jz      short loc_180012EAB
0x180012e7f  cmp     byte ptr [rcx+19h], 5
0x180012e83  jb      short loc_180012EAB
0x180012e85  test    byte ptr [rcx+1Ch], 1
0x180012e89  jz      short loc_180012EAB
0x180012e8b  mov     edx, 66h ; 'f'
0x180012e90  mov     dword ptr [rsp+4F8h+var_4D8], ebx
0x180012e94  lea     r9, aWcmopenondeman_1; "WcmOpenOnDemandRequestHandleByWwanProfi"...
0x180012e9b  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012ea2  mov     rcx, [rcx+10h]
0x180012ea6  call    WPP_SF_sL
0x180012eab  mov     eax, ebx
0x180012ead  mov     rcx, [rsp+4F8h+var_38]
0x180012eb5  xor     rcx, rsp; StackCookie
0x180012eb8  call    __security_check_cookie
0x180012ebd  mov     rbx, [rsp+4F8h+arg_18]
0x180012ec5  add     rsp, 4D0h
0x180012ecc  pop     r15
0x180012ece  pop     r14
0x180012ed0  pop     r12
0x180012ed2  pop     rdi
0x180012ed3  pop     rsi
0x180012ed4  retn
0x18001d2b3  push    rbp
0x18001d2b5  sub     rsp, 40h
0x18001d2b9  mov     rbp, rdx
0x18001d2bc  mov     rcx, [rcx]
0x18001d2bf  mov     ecx, [rcx]; ExceptionCode
0x18001d2c1  call    cs:__imp_RpcExceptionFilter
0x18001d2c8  nop     dword ptr [rax+rax+00h]
0x18001d2cd  nop
0x18001d2ce  add     rsp, 40h
0x18001d2d2  pop     rbp
0x18001d2d3  retn
0x18001d2d5  push    rbp
0x18001d2d7  sub     rsp, 40h
0x18001d2db  mov     rbp, rdx
0x18001d2de  mov     rcx, [rcx]
0x18001d2e1  mov     ecx, [rcx]; ExceptionCode
0x18001d2e3  call    cs:__imp_RpcExceptionFilter
0x18001d2ea  nop     dword ptr [rax+rax+00h]
0x18001d2ef  nop
0x18001d2f0  add     rsp, 40h
0x18001d2f4  pop     rbp
0x18001d2f5  retn
```
