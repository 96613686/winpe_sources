# VpnikeProcessTsReply

- ea: `0x180054e20`
- end: `0x1800551c5`
- name: `VpnikeProcessTsReply`
- size: `933`
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
- `0x180054e20`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055057`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055084`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055084`
- `RPCRT4!RpcRaiseException` at `0x180055163`
- `RPCRT4!RpcRaiseException` at `0x180055163`

## string_xrefs

- `0x180054fe0`: `TS Initiator: Got reponse for TsId [%I64u]`

## pseudocode

```c
__int64 __fastcall VpnikeProcessTsReply(__int64 a1, __int64 a2, __int64 a3, struct _VPN_TRAFFIC_SELECTORS_ *a4)
{
  PVOID *v6; // rbx
  unsigned int v7; // r14d
  char v8; // al
  __int64 v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  __int64 v11; // rax
  ULONG_PTR SpinCount; // rdx
  __int128 *v13; // r9
  unsigned int v14; // ecx
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  __int128 v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch]
  __int128 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+B4h] [rbp-4Ch]
  int v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v17 = a3;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v7 = -1;
  v25 = 0;
  v28 = 0;
  v18 = 0;
  v21 = 0;
  v23 = 0;
  v8 = byte_1800AA941;
  v22 = -1;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  v19 = 0;
  v20 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"VpnikeProcessTsReply",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v8 = byte_1800AA941;
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && v17 && a4 )
  {
    if ( (v8 & 8) != 0 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v29);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
           *((_QWORD *)VpnIkeProtocolEngine + 1),
           a2);
    v10 = (struct _RTL_CRITICAL_SECTION *)v9;
    if ( !v9 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v29);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v14 = 837;
      exception = 837;
LABEL_31:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        WPP_SF_d(v6[2], 32, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v14);
        v14 = exception;
      }
      RpcRaiseException(v14);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v11 = *(_QWORD *)(v9 + 112);
      if ( v11 && *(_QWORD *)(v11 + 16) )
        v7 = *(_DWORD *)(v11 + 16);
      ConvertPortNoToString(&v25, v7);
      FormatRRASErrorString(&v29, L"TS Initiator: Got reponse for TsId [%I64u]", v17);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        SpinCount = v10[2].SpinCount;
        LODWORD(v13) = SpinCount + 2120;
        if ( !SpinCount )
          v13 = &v24;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v29,
          (_DWORD)v13,
          (SpinCount + 2686) & -(__int64)(v10[2].SpinCount != 0),
          (__int64)&v25);
      }
    }
    LogTsPayload(a4);
    EnterCriticalSection(v10 + 4);
    exception = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64 *))v10->DebugInfo[2].ProcessLocksList.Blink)(
                  v10,
                  3,
                  &v17);
    LeaveCriticalSection(v10 + 4);
    BaseConnection::DeleteRef((BaseConnection *)v10);
    v14 = exception;
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( (v8 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Parameter");
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v14 = 87;
    exception = 87;
  }
  if ( v14 )
    goto LABEL_31;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 33, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return 0;
}

```

## disassembly

```asm
0x180054e20  mov     [rsp-8+arg_0], rbx
0x180054e25  push    rbp
0x180054e26  push    rsi
0x180054e27  push    rdi
0x180054e28  push    r14
0x180054e2a  push    r15
0x180054e2c  lea     rbp, [rsp-7D0h]
0x180054e34  sub     rsp, 8D0h
0x180054e3b  mov     rax, cs:__security_cookie
0x180054e42  xor     rax, rsp
0x180054e45  mov     [rbp+7F0h+var_30], rax
0x180054e4c  mov     r15, r9
0x180054e4f  mov     [rsp+8F0h+var_8B8], r8
0x180054e54  mov     rdi, rdx
0x180054e57  mov     rbx, cs:WPP_GLOBAL_Control
0x180054e5e  lea     rsi, WPP_GLOBAL_Control
0x180054e65  cmp     rbx, rsi
0x180054e68  jz      short loc_180054E95
0x180054e6a  test    byte ptr [rbx+1Ch], 1
0x180054e6e  jz      short loc_180054E95
0x180054e70  cmp     byte ptr [rbx+19h], 6
0x180054e74  jb      short loc_180054E95
0x180054e76  mov     rcx, [rbx+10h]
0x180054e7a  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180054e81  mov     edx, 1Fh
0x180054e86  mov     r9, rdi
0x180054e89  call    WPP_SF_q
0x180054e8e  mov     rbx, cs:WPP_GLOBAL_Control
0x180054e95  xor     eax, eax
0x180054e97  mov     [rsp+8F0h+exception], 0
0x180054e9f  xor     edx, edx; Val
0x180054ea1  mov     [rbp+7F0h+var_830], eax
0x180054ea4  mov     r8d, 7FCh; Size
0x180054eaa  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180054eae  call    memset_0
0x180054eb3  xor     eax, eax
0x180054eb5  xorps   xmm0, xmm0
0x180054eb8  or      r14d, 0FFFFFFFFh
0x180054ebc  mov     [rbp+7F0h+var_860], eax
0x180054ebf  mov     [rbp+7F0h+var_83C], eax
0x180054ec2  xorps   xmm1, xmm1
0x180054ec5  mov     [rsp+8F0h+var_8A8], rax
0x180054eca  mov     [rsp+8F0h+var_880], rax
0x180054ecf  mov     [rsp+8F0h+var_874], eax
0x180054ed3  mov     al, cs:byte_1800AA941
0x180054ed9  mov     [rsp+8F0h+var_878], r14d
0x180054ede  movups  [rbp+7F0h+var_85C], xmm0
0x180054ee2  movups  [rbp+7F0h+var_84C], xmm0
0x180054ee6  movups  [rbp+7F0h+var_870], xmm0
0x180054eea  movdqu  [rsp+8F0h+var_8A0], xmm1
0x180054ef0  movdqu  [rsp+8F0h+var_890], xmm0
0x180054ef6  test    al, 8
0x180054ef8  jz      short loc_180054F24
0x180054efa  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180054f01  lea     r8, [rsp+8F0h+exception]; unsigned int *
0x180054f06  lea     rdx, aVpnikeprocesst; "VpnikeProcessTsReply"
0x180054f0d  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180054f12  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180054f17  mov     al, cs:byte_1800AA941
0x180054f1d  mov     rbx, cs:WPP_GLOBAL_Control
0x180054f24  test    rdi, rdi
0x180054f27  jz      loc_1800550FD
0x180054f2d  cmp     [rsp+8F0h+var_8B8], 0
0x180054f33  jz      loc_1800550FD
0x180054f39  test    r15, r15
0x180054f3c  jz      loc_1800550FD
0x180054f42  test    al, 8
0x180054f44  jz      short loc_180054F7F
0x180054f46  xor     eax, eax
0x180054f48  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x180054f4f  mov     r8, rdi
0x180054f52  mov     word ptr [rbp+7F0h+var_830], ax
0x180054f56  lea     rcx, [rbp+7F0h+var_830]
0x180054f5a  call    FormatRRASErrorString
0x180054f5f  test    cs:byte_1800AA941, 8
0x180054f66  jz      short loc_180054F7F
0x180054f68  lea     r8, [rbp+7F0h+var_830]
0x180054f6c  lea     rdx, RasVpnIkeTraceInfo
0x180054f73  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180054f7a  call    McTemplateU0z_EventWriteTransfer
0x180054f7f  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180054f86  mov     rdx, rdi
0x180054f89  mov     rcx, [rax+8]
0x180054f8d  mov     rax, [rcx]
0x180054f90  mov     rax, [rax+28h]
0x180054f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f99  mov     rsi, rax
0x180054f9c  test    rax, rax
0x180054f9f  jz      loc_1800550A9
0x180054fa5  test    cs:byte_1800AA941, 8
0x180054fac  jz      loc_180055045
0x180054fb2  xor     ecx, ecx
0x180054fb4  mov     word ptr [rbp+7F0h+var_830], cx
0x180054fb8  mov     word ptr [rbp+7F0h+var_860], cx
0x180054fbc  mov     rax, [rax+70h]
0x180054fc0  test    rax, rax
0x180054fc3  jz      short loc_180054FCF
0x180054fc5  cmp     [rax+10h], rcx
0x180054fc9  jz      short loc_180054FCF
0x180054fcb  mov     r14d, [rax+10h]
0x180054fcf  mov     edx, r14d
0x180054fd2  lea     rcx, [rbp+7F0h+var_860]
0x180054fd6  call    ConvertPortNoToString
0x180054fdb  mov     r8, [rsp+8F0h+var_8B8]
0x180054fe0  lea     rdx, aTsInitiatorGot; "TS Initiator: Got reponse for TsId [%I6"...
0x180054fe7  lea     rcx, [rbp+7F0h+var_830]
0x180054feb  call    FormatRRASErrorString
0x180054ff0  test    cs:byte_1800AA941, 8
0x180054ff7  jz      short loc_180055045
0x180054ff9  mov     rdx, [rsi+70h]
0x180054ffd  mov     rax, rdx
0x180055000  neg     rax
0x180055003  sbb     r8, r8
0x180055006  lea     rcx, [rdx+0A7Eh]
0x18005500d  and     r8, rcx
0x180055010  lea     r9, [rdx+848h]
0x180055017  test    rdx, rdx
0x18005501a  jnz     short loc_180055020
0x18005501c  lea     r9, [rbp+7F0h+var_870]
0x180055020  lea     rax, [rbp+7F0h+var_860]
0x180055024  mov     [rsp+8F0h+var_8C8], rax
0x180055029  lea     rdx, RasVpnIkeParamTraceInfo
0x180055030  mov     [rsp+8F0h+var_8D0], r8
0x180055035  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005503c  lea     r8, [rbp+7F0h+var_830]
0x180055040  call    McTemplateU0zjzz_EventWriteTransfer
0x180055045  mov     rcx, r15; struct _VPN_TRAFFIC_SELECTORS_ *
0x180055048  call    ?LogTsPayload@@YAXPEAU_VPN_TRAFFIC_SELECTORS_@@@Z; LogTsPayload(_VPN_TRAFFIC_SELECTORS_ *)
0x18005504d  lea     rbx, [rsi+0A0h]
0x180055054  mov     rcx, rbx; lpCriticalSection
0x180055057  call    cs:__imp_EnterCriticalSection
0x18005505d  mov     rax, [rsi]
0x180055060  lea     r8, [rsp+8F0h+var_8B8]
0x180055065  xor     r9d, r9d
0x180055068  mov     [rsp+8F0h+var_8D0], r15
0x18005506d  mov     rcx, rsi
0x180055070  mov     rax, [rax+78h]
0x180055074  lea     edx, [r9+3]
0x180055078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005507d  mov     rcx, rbx; lpCriticalSection
0x180055080  mov     [rsp+8F0h+exception], eax
0x180055084  call    cs:__imp_LeaveCriticalSection
0x18005508a  mov     rcx, rsi; this
0x18005508d  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180055092  mov     ecx, [rsp+8F0h+exception]
0x180055096  lea     rsi, WPP_GLOBAL_Control
0x18005509d  mov     rbx, cs:WPP_GLOBAL_Control
0x1800550a4  jmp     loc_18005512B
0x1800550a9  test    cs:byte_1800AA941, 4
0x1800550b0  jz      short loc_1800550EB
0x1800550b2  xor     eax, eax
0x1800550b4  mov     r8d, edi
0x1800550b7  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x1800550be  mov     word ptr [rbp+7F0h+var_830], ax
0x1800550c2  lea     rcx, [rbp+7F0h+var_830]
0x1800550c6  call    FormatRRASErrorString
0x1800550cb  test    cs:byte_1800AA941, 4
0x1800550d2  jz      short loc_1800550EB
0x1800550d4  lea     r8, [rbp+7F0h+var_830]
0x1800550d8  lea     rdx, RasVpnIkeTraceError
0x1800550df  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800550e6  call    McTemplateU0z_EventWriteTransfer
0x1800550eb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800550f2  mov     ecx, 345h
0x1800550f7  mov     [rsp+8F0h+exception], ecx
0x1800550fb  jmp     short loc_18005512F
0x1800550fd  test    al, 4
0x1800550ff  jz      short loc_180055122
0x180055101  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180055108  lea     rdx, RasVpnIkeTraceError
0x18005510f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055116  call    McTemplateU0z_EventWriteTransfer
0x18005511b  mov     rbx, cs:WPP_GLOBAL_Control
0x180055122  mov     ecx, 57h ; 'W'
0x180055127  mov     [rsp+8F0h+exception], ecx
0x18005512b  test    ecx, ecx
0x18005512d  jz      short loc_18005516A
0x18005512f  lea     rax, WPP_GLOBAL_Control
0x180055136  cmp     rbx, rax
0x180055139  jz      short loc_180055163
0x18005513b  test    byte ptr [rbx+1Ch], 1
0x18005513f  jz      short loc_180055163
0x180055141  cmp     byte ptr [rbx+19h], 6
0x180055145  jb      short loc_180055163
0x180055147  mov     r9d, ecx
0x18005514a  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055151  mov     rcx, [rbx+10h]
0x180055155  mov     edx, 20h ; ' '
0x18005515a  call    WPP_SF_d
0x18005515f  mov     ecx, [rsp+8F0h+exception]; exception
0x180055163  call    cs:__imp_RpcRaiseException
0x180055169  int     3; Trap to Debugger
0x18005516a  cmp     rbx, rsi
0x18005516d  jz      short loc_180055193
0x18005516f  test    byte ptr [rbx+1Ch], 1
0x180055173  jz      short loc_180055193
0x180055175  cmp     byte ptr [rbx+19h], 6
0x180055179  jb      short loc_180055193
0x18005517b  mov     rcx, [rbx+10h]
0x18005517f  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055186  mov     edx, 21h ; '!'
0x18005518b  xor     r9d, r9d
0x18005518e  call    WPP_SF_d
0x180055193  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180055198  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005519d  xor     eax, eax
0x18005519f  mov     rcx, [rbp+7F0h+var_30]
0x1800551a6  xor     rcx, rsp; StackCookie
0x1800551a9  call    __security_check_cookie
0x1800551ae  mov     rbx, [rsp+8F0h+arg_0]
0x1800551b6  add     rsp, 8D0h
0x1800551bd  pop     r15
0x1800551bf  pop     r14
0x1800551c1  pop     rdi
0x1800551c2  pop     rsi
0x1800551c3  pop     rbp
0x1800551c4  retn
```
