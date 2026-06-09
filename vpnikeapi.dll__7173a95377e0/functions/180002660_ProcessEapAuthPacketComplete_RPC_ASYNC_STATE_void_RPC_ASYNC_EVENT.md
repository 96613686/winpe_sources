# ProcessEapAuthPacketComplete(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180002660`
- end: `0x180002900`
- name: `?ProcessEapAuthPacketComplete@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `672`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001390`
- `0x1800022c4`
- `0x180002660`
- `0x180003120`
- `0x180004420`
- `0x1800063a0`
- `0x18000ce1c`
- `0x18000cfbe`
- `0x18000cff0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002821`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002821`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002741`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002741`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000274f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000274f`

## string_xrefs

- `0x1800026f1`: `ProcessEapAuthPacketComplete`
- `0x18000286d`: `ProcessEapAuthPacketComplete`
- `0x180002766`: `RpcAsyncCompleteCall failed: %d`

## pseudocode

```c
void __fastcall ProcessEapAuthPacketComplete(struct _RPC_ASYNC_STATE *a1, void *a2, enum _RPC_ASYNC_EVENT a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  void **p_StubInfo; // rbx
  unsigned int *StubInfo; // r8
  unsigned int Reply; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v9; // [rsp+28h] [rbp-D8h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  char v11[2044]; // [rsp+44h] [rbp-BCh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
  }
  Reply = 0;
  v10 = 0;
  v9 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Entered: %s", L"ProcessEapAuthPacketComplete");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v10);
  }
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&a1[1].UserInfo);
  v4 = RpcAsyncCompleteCall(a1, &Reply);
  v5 = v4;
  if ( v4 )
  {
    if ( (byte_1800167C1 & 0x40) != 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RpcAsyncCompleteCall failed: %d", v4);
      if ( (byte_1800167C1 & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceError, &v10);
    }
    Reply = v5;
    p_StubInfo = &a1[1].StubInfo;
    LODWORD(v9) = 0;
    a1[1].StubInfo = &v9;
  }
  else
  {
    p_StubInfo = &a1[1].StubInfo;
    StubInfo = (unsigned int *)a1[1].StubInfo;
    if ( StubInfo )
    {
      if ( byte_1800167C1 < 0 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString(&v10, L"EAP_AUTH_RESULT: State: %d, failureReason: %d", *StubInfo, Reply);
        if ( byte_1800167C1 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v10);
      }
    }
  }
  a1->UserInfo = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)&a1[1].UserInfo);
  (*(void (__fastcall **)(_QWORD, _QWORD, void *))&a1[1].Size)(*(_QWORD *)&a1[1].Lock, Reply, *p_StubInfo);
  if ( !Reply && *p_StubInfo )
  {
    FreeEapAuthPacket(*((void **)*p_StubInfo + 1));
    MIDL_user_free(*p_StubInfo);
    *p_StubInfo = 0;
  }
  if ( byte_1800167C1 < 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Leaving: %s", L"ProcessEapAuthPacketComplete");
    if ( byte_1800167C1 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeApiTraceInfo, &v10);
  }
  CleanupRpcAsyncStateObject((struct VPNIKE_ASYNC_RPC_CALL_STATE_ *)a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
  }
}

```

## disassembly

```asm
0x180002660  mov     [rsp-8+arg_8], rbx
0x180002665  mov     [rsp-8+arg_10], rsi
0x18000266a  push    rbp
0x18000266b  push    rdi
0x18000266c  push    r13
0x18000266e  lea     rbp, [rsp-750h]
0x180002676  sub     rsp, 850h
0x18000267d  mov     rax, cs:__security_cookie
0x180002684  xor     rax, rsp
0x180002687  mov     [rbp+760h+var_20], rax
0x18000268e  mov     rdi, rcx
0x180002691  mov     rcx, cs:WPP_GLOBAL_Control
0x180002698  lea     r13, WPP_GLOBAL_Control
0x18000269f  cmp     rcx, r13
0x1800026a2  jz      short loc_1800026BE
0x1800026a4  test    byte ptr [rcx+1Ch], 1
0x1800026a8  jz      short loc_1800026BE
0x1800026aa  cmp     byte ptr [rcx+19h], 6
0x1800026ae  jb      short loc_1800026BE
0x1800026b0  mov     rcx, [rcx+10h]
0x1800026b4  mov     edx, 1Ah
0x1800026b9  call    WPP_SF_
0x1800026be  xorps   xmm0, xmm0
0x1800026c1  mov     [rsp+860h+Reply], 0
0x1800026c9  xor     eax, eax
0x1800026cb  lea     rcx, [rsp+860h+var_81C]; void *
0x1800026d0  xor     edx, edx; Val
0x1800026d2  mov     [rsp+860h+var_820], eax
0x1800026d6  mov     r8d, 7FCh; Size
0x1800026dc  movups  [rsp+860h+var_838], xmm0
0x1800026e1  call    memset_0
0x1800026e6  test    cs:byte_1800167C1, 80h
0x1800026ed  jz      short loc_18000272F
0x1800026ef  xor     eax, eax
0x1800026f1  lea     r8, aProcesseapauth_0; "ProcessEapAuthPacketComplete"
0x1800026f8  lea     rdx, aEnteredS; "Entered: %s"
0x1800026ff  mov     word ptr [rsp+860h+var_820], ax
0x180002704  lea     rcx, [rsp+860h+var_820]
0x180002709  call    FormatRRASErrorString
0x18000270e  cmp     cs:byte_1800167C1, 0
0x180002715  jge     short loc_18000272F
0x180002717  lea     r8, [rsp+860h+var_820]
0x18000271c  lea     rdx, RasVpnIkeApiTraceInfo
0x180002723  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000272a  call    McTemplateU0z_EventWriteTransfer
0x18000272f  xorps   xmm0, xmm0
0x180002732  lea     rsi, [rdi+88h]
0x180002739  mov     rcx, rsi; lpCriticalSection
0x18000273c  movups  [rsp+860h+var_838], xmm0
0x180002741  call    cs:__imp_EnterCriticalSection
0x180002747  lea     rdx, [rsp+860h+Reply]; Reply
0x18000274c  mov     rcx, rdi; pAsync
0x18000274f  call    cs:__imp_RpcAsyncCompleteCall
0x180002755  mov     ebx, eax
0x180002757  test    eax, eax
0x180002759  jz      short loc_1800027BD
0x18000275b  test    cs:byte_1800167C1, 40h
0x180002762  jz      short loc_1800027A0
0x180002764  xor     ecx, ecx
0x180002766  lea     rdx, aRpcasynccomple_0; "RpcAsyncCompleteCall failed: %d"
0x18000276d  mov     word ptr [rsp+860h+var_820], cx
0x180002772  mov     r8d, eax
0x180002775  lea     rcx, [rsp+860h+var_820]
0x18000277a  call    FormatRRASErrorString
0x18000277f  test    cs:byte_1800167C1, 40h
0x180002786  jz      short loc_1800027A0
0x180002788  lea     r8, [rsp+860h+var_820]
0x18000278d  lea     rdx, RasVpnIkeApiTraceError
0x180002794  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000279b  call    McTemplateU0z_EventWriteTransfer
0x1800027a0  mov     [rsp+860h+Reply], ebx
0x1800027a4  lea     rax, [rsp+860h+var_838]
0x1800027a9  lea     rbx, [rdi+80h]
0x1800027b0  mov     dword ptr [rsp+860h+var_838], 0
0x1800027b8  mov     [rbx], rax
0x1800027bb  jmp     short loc_180002816
0x1800027bd  lea     rbx, [rdi+80h]
0x1800027c4  mov     r8, [rbx]
0x1800027c7  test    r8, r8
0x1800027ca  jz      short loc_180002816
0x1800027cc  cmp     cs:byte_1800167C1, 0
0x1800027d3  jge     short loc_180002816
0x1800027d5  mov     r9d, [rsp+860h+Reply]
0x1800027da  lea     rdx, aEapAuthResultS; "EAP_AUTH_RESULT: State: %d, failureReas"...
0x1800027e1  xor     eax, eax
0x1800027e3  lea     rcx, [rsp+860h+var_820]
0x1800027e8  mov     word ptr [rsp+860h+var_820], ax
0x1800027ed  mov     r8d, [r8]
0x1800027f0  call    FormatRRASErrorString
0x1800027f5  cmp     cs:byte_1800167C1, 0
0x1800027fc  jge     short loc_180002816
0x1800027fe  lea     r8, [rsp+860h+var_820]
0x180002803  lea     rdx, RasVpnIkeApiTraceInfo
0x18000280a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002811  call    McTemplateU0z_EventWriteTransfer
0x180002816  mov     rcx, rsi; lpCriticalSection
0x180002819  mov     qword ptr [rdi+18h], 0
0x180002821  call    cs:__imp_LeaveCriticalSection
0x180002827  mov     r8, [rbx]
0x18000282a  mov     edx, [rsp+860h+Reply]
0x18000282e  mov     rcx, [rdi+78h]
0x180002832  mov     rax, [rdi+70h]
0x180002836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283b  cmp     [rsp+860h+Reply], 0
0x180002840  jnz     short loc_180002862
0x180002842  mov     rcx, [rbx]
0x180002845  test    rcx, rcx
0x180002848  jz      short loc_180002862
0x18000284a  mov     rcx, [rcx+8]; void *
0x18000284e  call    FreeEapAuthPacket
0x180002853  mov     rcx, [rbx]; void *
0x180002856  call    MIDL_user_free
0x18000285b  mov     qword ptr [rbx], 0
0x180002862  test    cs:byte_1800167C1, 80h
0x180002869  jz      short loc_1800028AB
0x18000286b  xor     eax, eax
0x18000286d  lea     r8, aProcesseapauth_0; "ProcessEapAuthPacketComplete"
0x180002874  lea     rdx, aLeavingS; "Leaving: %s"
0x18000287b  mov     word ptr [rsp+860h+var_820], ax
0x180002880  lea     rcx, [rsp+860h+var_820]
0x180002885  call    FormatRRASErrorString
0x18000288a  cmp     cs:byte_1800167C1, 0
0x180002891  jge     short loc_1800028AB
0x180002893  lea     r8, [rsp+860h+var_820]
0x180002898  lea     rdx, RasVpnIkeApiTraceInfo
0x18000289f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800028a6  call    McTemplateU0z_EventWriteTransfer
0x1800028ab  mov     rcx, rdi; struct VPNIKE_ASYNC_RPC_CALL_STATE_ *
0x1800028ae  call    ?CleanupRpcAsyncStateObject@@YAXPEAUVPNIKE_ASYNC_RPC_CALL_STATE_@@@Z; CleanupRpcAsyncStateObject(VPNIKE_ASYNC_RPC_CALL_STATE_ *)
0x1800028b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028ba  cmp     rcx, r13
0x1800028bd  jz      short loc_1800028D9
0x1800028bf  test    byte ptr [rcx+1Ch], 1
0x1800028c3  jz      short loc_1800028D9
0x1800028c5  cmp     byte ptr [rcx+19h], 6
0x1800028c9  jb      short loc_1800028D9
0x1800028cb  mov     rcx, [rcx+10h]
0x1800028cf  mov     edx, 1Bh
0x1800028d4  call    WPP_SF_
0x1800028d9  mov     rcx, [rbp+760h+var_20]
0x1800028e0  xor     rcx, rsp; StackCookie
0x1800028e3  call    __security_check_cookie
0x1800028e8  lea     r11, [rsp+860h+var_10]
0x1800028f0  mov     rbx, [r11+28h]
0x1800028f4  mov     rsi, [r11+30h]
0x1800028f8  mov     rsp, r11
0x1800028fb  pop     r13
0x1800028fd  pop     rdi
0x1800028fe  pop     rbp
0x1800028ff  retn
```
