# VpnikeGetTsRequest

- ea: `0x180053260`
- end: `0x180053656`
- name: `VpnikeGetTsRequest`
- size: `1014`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x180050e78`
- `0x180053260`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005349e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005349e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800534ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800534ce`
- `RPCRT4!RpcRaiseException` at `0x1800535f1`
- `RPCRT4!RpcRaiseException` at `0x1800535f1`

## string_xrefs

- `0x18005342e`: `TS Initiator: Requested TS for TsId [%I64u]`
- `0x1800534e9`: `TS Initiator: Send TS payload for TsId [%I64u]`

## pseudocode

```c
__int64 __fastcall VpnikeGetTsRequest(__int64 a1, __int64 a2, __int64 *a3, struct _VPN_TRAFFIC_SELECTORS_ **a4)
{
  PVOID *v7; // rbx
  unsigned int v8; // r13d
  char v9; // al
  __int64 v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // r14
  __int64 v12; // rcx
  ULONG_PTR SpinCount; // rdx
  __int128 *v14; // r9
  __int64 v15; // r8
  unsigned int v16; // ecx
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+80h] [rbp-80h] BYREF
  __int128 v27; // [rsp+84h] [rbp-7Ch]
  __int128 v28; // [rsp+94h] [rbp-6Ch]
  int v29; // [rsp+A4h] [rbp-5Ch]
  int v30; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v8 = -1;
  v26 = 0;
  v29 = 0;
  v19 = 0;
  v22 = 0;
  v24 = 0;
  v9 = byte_1800AA941;
  v23 = -1;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  v20 = 0;
  v21 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"VpnikeGetTsRequest",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v9 = byte_1800AA941;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 && !*a4 )
  {
    if ( (v9 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v30);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
            *((_QWORD *)VpnIkeProtocolEngine + 1),
            a2);
    v11 = (struct _RTL_CRITICAL_SECTION *)v10;
    if ( !v10 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v30, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v30);
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      v16 = 837;
      exception = 837;
LABEL_35:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        WPP_SF_d(v7[2], 29, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v16);
        v16 = exception;
      }
      RpcRaiseException(v16);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      v12 = *(_QWORD *)(v10 + 112);
      if ( v12 && *(_QWORD *)(v12 + 16) )
        v8 = *(_DWORD *)(v12 + 16);
      ConvertPortNoToString(&v26, v8);
      FormatRRASErrorString(&v30, L"TS Initiator: Requested TS for TsId [%I64u]", *a3);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        SpinCount = v11[2].SpinCount;
        LODWORD(v14) = SpinCount + 2120;
        if ( !SpinCount )
          v14 = &v25;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v30,
          (_DWORD)v14,
          (SpinCount + 2686) & -(__int64)(v11[2].SpinCount != 0),
          (__int64)&v26);
      }
    }
    EnterCriticalSection(v11 + 4);
    exception = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64 *, struct _VPN_TRAFFIC_SELECTORS_ **, _QWORD))v11->DebugInfo[2].ProcessLocksList.Blink)(
                  v11,
                  1,
                  a3,
                  a4,
                  0);
    LeaveCriticalSection(v11 + 4);
    BaseConnection::DeleteRef((BaseConnection *)v11);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v15 = *a3;
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"TS Initiator: Send TS payload for TsId [%I64u]", v15);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v30);
    }
    LogTsPayload(*a4);
    v16 = exception;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( (v9 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Parameter");
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v16 = 87;
    exception = 87;
  }
  if ( v16 )
    goto LABEL_35;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 30, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return 0;
}

```

## disassembly

```asm
0x180053260  push    rbp
0x180053262  push    rbx
0x180053263  push    rsi
0x180053264  push    r12
0x180053266  push    r13
0x180053268  push    r14
0x18005326a  push    r15
0x18005326c  lea     rbp, [rsp-7C0h]
0x180053274  sub     rsp, 8C0h
0x18005327b  mov     rax, cs:__security_cookie
0x180053282  xor     rax, rsp
0x180053285  mov     [rbp+7F0h+var_40], rax
0x18005328c  mov     r15, r9
0x18005328f  mov     r12, r8
0x180053292  mov     rsi, rdx
0x180053295  mov     rbx, cs:WPP_GLOBAL_Control
0x18005329c  lea     rax, WPP_GLOBAL_Control
0x1800532a3  cmp     rbx, rax
0x1800532a6  jz      short loc_1800532D3
0x1800532a8  test    byte ptr [rbx+1Ch], 1
0x1800532ac  jz      short loc_1800532D3
0x1800532ae  cmp     byte ptr [rbx+19h], 6
0x1800532b2  jb      short loc_1800532D3
0x1800532b4  mov     rcx, [rbx+10h]
0x1800532b8  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800532bf  mov     edx, 1Ch
0x1800532c4  mov     r9, rsi
0x1800532c7  call    WPP_SF_q
0x1800532cc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800532d3  xor     eax, eax
0x1800532d5  mov     [rsp+8F0h+exception], 0
0x1800532dd  xor     edx, edx; Val
0x1800532df  mov     [rbp+7F0h+var_840], eax
0x1800532e2  mov     r8d, 7FCh; Size
0x1800532e8  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800532ec  call    memset_0
0x1800532f1  xor     eax, eax
0x1800532f3  xorps   xmm0, xmm0
0x1800532f6  or      r13d, 0FFFFFFFFh
0x1800532fa  mov     [rbp+7F0h+var_870], eax
0x1800532fd  mov     [rbp+7F0h+var_84C], eax
0x180053300  mov     r14b, 8
0x180053303  mov     [rsp+8F0h+var_8B8], rax
0x180053308  xorps   xmm1, xmm1
0x18005330b  mov     [rsp+8F0h+var_890], rax
0x180053310  mov     [rsp+8F0h+var_884], eax
0x180053314  mov     al, cs:byte_1800AA941
0x18005331a  mov     [rsp+8F0h+var_888], r13d
0x18005331f  movups  [rbp+7F0h+var_86C], xmm0
0x180053323  movups  [rbp+7F0h+var_85C], xmm0
0x180053327  movups  [rsp+8F0h+var_880], xmm0
0x18005332c  movdqu  [rsp+8F0h+var_8B0], xmm1
0x180053332  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180053338  test    r14b, al
0x18005333b  jz      short loc_180053367
0x18005333d  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180053344  lea     r8, [rsp+8F0h+exception]; unsigned int *
0x180053349  lea     rdx, aVpnikegettsreq; "VpnikeGetTsRequest"
0x180053350  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180053355  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005335a  mov     al, cs:byte_1800AA941
0x180053360  mov     rbx, cs:WPP_GLOBAL_Control
0x180053367  test    rsi, rsi
0x18005336a  jz      loc_18005358B
0x180053370  test    r12, r12
0x180053373  jz      loc_18005358B
0x180053379  test    r15, r15
0x18005337c  jz      loc_18005358B
0x180053382  cmp     qword ptr [r15], 0
0x180053386  jnz     loc_18005358B
0x18005338c  test    r14b, al
0x18005338f  jz      short loc_1800533CA
0x180053391  xor     eax, eax
0x180053393  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x18005339a  mov     r8, rsi
0x18005339d  mov     word ptr [rbp+7F0h+var_840], ax
0x1800533a1  lea     rcx, [rbp+7F0h+var_840]
0x1800533a5  call    FormatRRASErrorString
0x1800533aa  test    cs:byte_1800AA941, r14b
0x1800533b1  jz      short loc_1800533CA
0x1800533b3  lea     r8, [rbp+7F0h+var_840]
0x1800533b7  lea     rdx, RasVpnIkeTraceInfo
0x1800533be  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800533c5  call    McTemplateU0z_EventWriteTransfer
0x1800533ca  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800533d1  mov     rdx, rsi
0x1800533d4  mov     rcx, [rax+8]
0x1800533d8  mov     rax, [rcx]
0x1800533db  mov     rax, [rax+28h]
0x1800533df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533e4  mov     r14, rax
0x1800533e7  test    rax, rax
0x1800533ea  jz      loc_180053537
0x1800533f0  mov     sil, 8
0x1800533f3  test    cs:byte_1800AA941, sil
0x1800533fa  jz      loc_180053494
0x180053400  xor     ecx, ecx
0x180053402  mov     word ptr [rbp+7F0h+var_840], cx
0x180053406  mov     word ptr [rbp+7F0h+var_870], cx
0x18005340a  mov     rcx, [rax+70h]
0x18005340e  test    rcx, rcx
0x180053411  jz      short loc_18005341E
0x180053413  cmp     qword ptr [rcx+10h], 0
0x180053418  jz      short loc_18005341E
0x18005341a  mov     r13d, [rcx+10h]
0x18005341e  mov     edx, r13d
0x180053421  lea     rcx, [rbp+7F0h+var_870]
0x180053425  call    ConvertPortNoToString
0x18005342a  mov     r8, [r12]
0x18005342e  lea     rdx, aTsInitiatorReq; "TS Initiator: Requested TS for TsId [%I"...
0x180053435  lea     rcx, [rbp+7F0h+var_840]
0x180053439  call    FormatRRASErrorString
0x18005343e  test    cs:byte_1800AA941, sil
0x180053445  jz      short loc_180053494
0x180053447  mov     rdx, [r14+70h]
0x18005344b  mov     rax, rdx
0x18005344e  neg     rax
0x180053451  sbb     r8, r8
0x180053454  lea     rcx, [rdx+0A7Eh]
0x18005345b  and     r8, rcx
0x18005345e  lea     r9, [rdx+848h]
0x180053465  test    rdx, rdx
0x180053468  jnz     short loc_18005346F
0x18005346a  lea     r9, [rsp+8F0h+var_880]
0x18005346f  lea     rax, [rbp+7F0h+var_870]
0x180053473  mov     [rsp+8F0h+var_8C8], rax
0x180053478  lea     rdx, RasVpnIkeParamTraceInfo
0x18005347f  mov     [rsp+8F0h+var_8D0], r8
0x180053484  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005348b  lea     r8, [rbp+7F0h+var_840]
0x18005348f  call    McTemplateU0zjzz_EventWriteTransfer
0x180053494  lea     rbx, [r14+0A0h]
0x18005349b  mov     rcx, rbx; lpCriticalSection
0x18005349e  call    cs:__imp_EnterCriticalSection
0x1800534a4  mov     rax, [r14]
0x1800534a7  mov     r9, r15
0x1800534aa  mov     r8, r12
0x1800534ad  mov     [rsp+8F0h+var_8D0], 0
0x1800534b6  mov     edx, 1
0x1800534bb  mov     rcx, r14
0x1800534be  mov     rax, [rax+78h]
0x1800534c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534c7  mov     rcx, rbx; lpCriticalSection
0x1800534ca  mov     [rsp+8F0h+exception], eax
0x1800534ce  call    cs:__imp_LeaveCriticalSection
0x1800534d4  mov     rcx, r14; this
0x1800534d7  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800534dc  test    cs:byte_1800AA941, sil
0x1800534e3  jz      short loc_18005351F
0x1800534e5  mov     r8, [r12]
0x1800534e9  lea     rdx, aTsInitiatorSen; "TS Initiator: Send TS payload for TsId "...
0x1800534f0  xor     eax, eax
0x1800534f2  lea     rcx, [rbp+7F0h+var_840]
0x1800534f6  mov     word ptr [rbp+7F0h+var_840], ax
0x1800534fa  call    FormatRRASErrorString
0x1800534ff  test    cs:byte_1800AA941, sil
0x180053506  jz      short loc_18005351F
0x180053508  lea     r8, [rbp+7F0h+var_840]
0x18005350c  lea     rdx, RasVpnIkeTraceInfo
0x180053513  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005351a  call    McTemplateU0z_EventWriteTransfer
0x18005351f  mov     rcx, [r15]; struct _VPN_TRAFFIC_SELECTORS_ *
0x180053522  call    ?LogTsPayload@@YAXPEAU_VPN_TRAFFIC_SELECTORS_@@@Z; LogTsPayload(_VPN_TRAFFIC_SELECTORS_ *)
0x180053527  mov     ecx, [rsp+8F0h+exception]
0x18005352b  mov     rbx, cs:WPP_GLOBAL_Control
0x180053532  jmp     loc_1800535B9
0x180053537  test    cs:byte_1800AA941, 4
0x18005353e  jz      short loc_180053579
0x180053540  xor     eax, eax
0x180053542  mov     r8d, esi
0x180053545  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x18005354c  mov     word ptr [rbp+7F0h+var_840], ax
0x180053550  lea     rcx, [rbp+7F0h+var_840]
0x180053554  call    FormatRRASErrorString
0x180053559  test    cs:byte_1800AA941, 4
0x180053560  jz      short loc_180053579
0x180053562  lea     r8, [rbp+7F0h+var_840]
0x180053566  lea     rdx, RasVpnIkeTraceError
0x18005356d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053574  call    McTemplateU0z_EventWriteTransfer
0x180053579  mov     rbx, cs:WPP_GLOBAL_Control
0x180053580  mov     ecx, 345h
0x180053585  mov     [rsp+8F0h+exception], ecx
0x180053589  jmp     short loc_1800535BD
0x18005358b  test    al, 4
0x18005358d  jz      short loc_1800535B0
0x18005358f  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180053596  lea     rdx, RasVpnIkeTraceError
0x18005359d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800535a4  call    McTemplateU0z_EventWriteTransfer
0x1800535a9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800535b0  mov     ecx, 57h ; 'W'
0x1800535b5  mov     [rsp+8F0h+exception], ecx
0x1800535b9  test    ecx, ecx
0x1800535bb  jz      short loc_1800535F8
0x1800535bd  lea     rax, WPP_GLOBAL_Control
0x1800535c4  cmp     rbx, rax
0x1800535c7  jz      short loc_1800535F1
0x1800535c9  test    byte ptr [rbx+1Ch], 1
0x1800535cd  jz      short loc_1800535F1
0x1800535cf  cmp     byte ptr [rbx+19h], 6
0x1800535d3  jb      short loc_1800535F1
0x1800535d5  mov     r9d, ecx
0x1800535d8  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800535df  mov     rcx, [rbx+10h]
0x1800535e3  mov     edx, 1Dh
0x1800535e8  call    WPP_SF_d
0x1800535ed  mov     ecx, [rsp+8F0h+exception]; exception
0x1800535f1  call    cs:__imp_RpcRaiseException
0x1800535f7  int     3; Trap to Debugger
0x1800535f8  lea     rax, WPP_GLOBAL_Control
0x1800535ff  cmp     rbx, rax
0x180053602  jz      short loc_180053628
0x180053604  test    byte ptr [rbx+1Ch], 1
0x180053608  jz      short loc_180053628
0x18005360a  cmp     byte ptr [rbx+19h], 6
0x18005360e  jb      short loc_180053628
0x180053610  mov     rcx, [rbx+10h]
0x180053614  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x18005361b  mov     edx, 1Eh
0x180053620  xor     r9d, r9d
0x180053623  call    WPP_SF_d
0x180053628  lea     rcx, [rsp+8F0h+var_8B8]; this
0x18005362d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180053632  xor     eax, eax
0x180053634  mov     rcx, [rbp+7F0h+var_40]
0x18005363b  xor     rcx, rsp; StackCookie
0x18005363e  call    __security_check_cookie
0x180053643  add     rsp, 8C0h
0x18005364a  pop     r15
0x18005364c  pop     r14
0x18005364e  pop     r13
0x180053650  pop     r12
0x180053652  pop     rsi
0x180053653  pop     rbx
0x180053654  pop     rbp
0x180053655  retn
```
