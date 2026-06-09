# VpnikeNewRasIncomingCall

- ea: `0x180053660`
- end: `0x180053d04`
- name: `VpnikeNewRasIncomingCall`
- size: `1700`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180008df8`
- `0x180009afc`
- `0x1800236f8`
- `0x1800509f0`
- `0x180053660`
- `0x18005d9ac`
- `0x18005dd70`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053836`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053836`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053861`
- `RPCRT4!RpcRaiseException` at `0x180053cfd`
- `RPCRT4!RpcRaiseException` at `0x180053cfd`

## string_xrefs

- `0x18005373f`: `VpnikeNewRasIncomingCall`
- `0x180053c35`: `ERROR_REMOTEACCESS_NOT_CONFIGURED:VPNIKE is not configured to accept connections`
- `0x180053b51`: `VPNIKEServerConnection::IncomingCall with error: %d`

## pseudocode

```c
__int64 __fastcall VpnikeNewRasIncomingCall(__int64 a1, __int64 a2, __int64 *a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // r14d
  char v7; // al
  __int16 v8; // cx
  VPNIKEProtocolEngine *v9; // rcx
  __int64 v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rax
  BaseConnection *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int128 *v16; // r9
  ULONG_PTR SpinCount; // rax
  __int64 v18; // rdx
  __int128 *v19; // r9
  const wchar_t *v20; // r8
  __int64 *v21; // rax
  __int64 v22; // rbx
  const wchar_t *v23; // r8
  __int64 v24; // rbx
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  char v27[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+48h] [rbp-B8h]
  __int128 v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+74h] [rbp-8Ch]
  __int128 v34; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+8Ch] [rbp-74h]
  __int128 v37; // [rsp+9Ch] [rbp-64h]
  int v38; // [rsp+ACh] [rbp-54h]
  int v39; // [rsp+B0h] [rbp-50h] BYREF
  char v40[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v6 = -1;
  v35 = 0;
  v38 = 0;
  v28 = 0;
  v31 = 0;
  v33 = 0;
  v7 = byte_1800AA941;
  v32 = -1;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v29 = 0;
  v30 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v28,
      L"VpnikeNewRasIncomingCall",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 && a2 )
  {
    v8 = *(_WORD *)a2;
    if ( *(_WORD *)a2 == *(_WORD *)(a2 + 20) && (v8 == 2 || v8 == 23) )
    {
      v9 = VpnIkeProtocolEngine;
      if ( VpnIkeProtocolEngine && (*((_BYTE *)VpnIkeProtocolEngine + 128) & 2) != 0 )
      {
        if ( *a3 )
        {
          if ( (v7 & 8) != 0 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(&v39, L"TunnelID: 0x%I64u means NAP Reauth");
            if ( (byte_1800AA941 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v39);
            v9 = VpnIkeProtocolEngine;
          }
          v10 = *a3;
          v11 = (struct _RTL_CRITICAL_SECTION *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v9 + 1) + 40LL))(
                                                  *((_QWORD *)v9 + 1),
                                                  *a3);
          v12 = (BaseConnection *)v11;
          if ( v11 )
          {
            if ( *(_DWORD *)(v11[2].SpinCount + 40) == 2 )
            {
              v13 = v11 + 4;
              EnterCriticalSection(v11 + 4);
              (*(void (__fastcall **)(BaseConnection *))(*(_QWORD *)v12 + 40LL))(v12);
              *a3 = *(_QWORD *)BaseConnection::GetReauthConnectionId(v12, v27);
              LeaveCriticalSection(v13);
              if ( (byte_1800AA941 & 8) != 0 )
              {
                LOWORD(v39) = 0;
                LOWORD(v35) = 0;
                v14 = *((_QWORD *)v12 + 14);
                if ( v14 && *(_QWORD *)(v14 + 16) )
                  v6 = *(_DWORD *)(v14 + 16);
                ConvertPortNoToString(&v35, v6);
                FormatRRASErrorString(&v39, L"Generated New Dummy Tunnel ID: 0x%I64X", *a3);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v15 = *((_QWORD *)v12 + 14);
                  LODWORD(v16) = v15 + 2120;
                  if ( !v15 )
                    v16 = &v34;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceInfo,
                    (unsigned int)&v39,
                    (_DWORD)v16,
                    (v15 + 2686) & -(__int64)(*((_QWORD *)v12 + 14) != 0),
                    (__int64)&v35);
                }
              }
            }
            else if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v35) = 0;
              SpinCount = v11[2].SpinCount;
              if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
                v6 = *(_DWORD *)(SpinCount + 16);
              ConvertPortNoToString(&v35, v6);
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v18 = *((_QWORD *)v12 + 14);
                LODWORD(v19) = v18 + 2120;
                if ( !v18 )
                  v19 = &v34;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceError,
                  (unsigned int)L"Invalid Connection Type: Expecting Server connection",
                  (_DWORD)v19,
                  (v18 + 2686) & -(__int64)(*((_QWORD *)v12 + 14) != 0),
                  (__int64)&v35);
              }
            }
            BaseConnection::DeleteRef(v12);
            goto LABEL_57;
          }
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_45;
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)v10);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_45;
          v20 = (const wchar_t *)&v39;
          goto LABEL_44;
        }
        *a3 = 0;
        v21 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v9 + 1) + 48LL))(
                           *((_QWORD *)v9 + 1),
                           v27);
        v22 = *v21;
        *a3 = *v21;
        if ( !v22 )
        {
          if ( (byte_1800AA941 & 4) == 0 )
          {
LABEL_45:
            v5 = (PVOID *)WPP_GLOBAL_Control;
            exception = 837;
            goto LABEL_76;
          }
          v20 = L"Failed to generate new TunnelId";
LABEL_44:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, v20);
          goto LABEL_45;
        }
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"Generated New Tunnel ID: 0x%I64X", v22);
          if ( (byte_1800AA941 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v39);
        }
        LogIkeTunnelParams((struct _IKETUNNEL_PARAMETERS_ *)a2);
        exception = CreateSynchronizingEvent(v22);
        if ( exception )
        {
          if ( (byte_1800AA941 & 4) == 0 )
          {
LABEL_57:
            if ( !exception )
            {
              v5 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_61;
            }
            v24 = *a3;
            if ( *a3 )
            {
              SignalSynchronizingEvent(*a3);
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 56LL))(
                *((_QWORD *)VpnIkeProtocolEngine + 1),
                v24);
              *a3 = 0;
            }
            goto LABEL_71;
          }
          v23 = L"Creation of synchronizing event failed";
        }
        else
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 120LL))(*((_QWORD *)VpnIkeProtocolEngine
                                                                                             + 1));
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 96LL))(
            *((_QWORD *)VpnIkeProtocolEngine + 1),
            (unsigned int)v22);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 128LL))(*((_QWORD *)VpnIkeProtocolEngine
                                                                                             + 1));
          exception = VPNIKEServerConnection::IncomingCall(v22, a2);
          if ( !exception )
            goto LABEL_57;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 120LL))(*((_QWORD *)VpnIkeProtocolEngine
                                                                                             + 1));
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 112LL))(
            *((_QWORD *)VpnIkeProtocolEngine + 1),
            (unsigned int)v22);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 128LL))(*((_QWORD *)VpnIkeProtocolEngine
                                                                                             + 1));
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_57;
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"VPNIKEServerConnection::IncomingCall with error: %d", (unsigned int)exception);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_57;
          v23 = (const wchar_t *)&v39;
        }
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, v23);
        goto LABEL_57;
      }
      if ( (v7 & 4) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"ERROR_REMOTEACCESS_NOT_CONFIGURED:VPNIKE is not configured to accept connections");
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      exception = 956;
    }
    else
    {
      exception = 13;
      if ( (v7 & 4) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"Invalid Data: vpnIkeTunnelParams");
LABEL_71:
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_75;
      }
    }
LABEL_76:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      WPP_SF_d(v5[2], 50, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, (unsigned int)exception);
    RpcRaiseException(exception);
  }
  if ( (v7 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Invalid Parameter");
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 87;
LABEL_75:
  if ( exception )
    goto LABEL_76;
LABEL_61:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 51, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v28);
  return 0;
}

```

## disassembly

```asm
0x180053660  mov     [rsp-8+arg_0], rbx
0x180053665  push    rbp
0x180053666  push    rsi
0x180053667  push    rdi
0x180053668  push    r13
0x18005366a  push    r14
0x18005366c  lea     rbp, [rsp-7C0h]
0x180053674  sub     rsp, 8C0h
0x18005367b  mov     rax, cs:__security_cookie
0x180053682  xor     rax, rsp
0x180053685  mov     [rbp+7E0h+var_30], rax
0x18005368c  mov     rsi, r8
0x18005368f  mov     rdi, rdx
0x180053692  mov     rbx, cs:WPP_GLOBAL_Control
0x180053699  lea     rax, WPP_GLOBAL_Control
0x1800536a0  cmp     rbx, rax
0x1800536a3  jz      short loc_1800536CD
0x1800536a5  test    byte ptr [rbx+1Ch], 1
0x1800536a9  jz      short loc_1800536CD
0x1800536ab  cmp     byte ptr [rbx+19h], 6
0x1800536af  jb      short loc_1800536CD
0x1800536b1  mov     rcx, [rbx+10h]
0x1800536b5  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800536bc  mov     edx, 31h ; '1'
0x1800536c1  call    WPP_SF_
0x1800536c6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800536cd  xor     eax, eax
0x1800536cf  mov     [rsp+8E0h+exception], 0
0x1800536d7  xor     edx, edx; Val
0x1800536d9  mov     [rbp+7E0h+var_830], eax
0x1800536dc  mov     r8d, 7FCh; Size
0x1800536e2  lea     rcx, [rbp+7E0h+var_82C]; void *
0x1800536e6  call    memset_0
0x1800536eb  xor     eax, eax
0x1800536ed  xorps   xmm0, xmm0
0x1800536f0  or      r14d, 0FFFFFFFFh
0x1800536f4  mov     [rbp+7E0h+var_858], eax
0x1800536f7  mov     [rbp+7E0h+var_834], eax
0x1800536fa  xorps   xmm1, xmm1
0x1800536fd  mov     [rsp+8E0h+var_8A0], rax
0x180053702  mov     [rsp+8E0h+var_878], rax
0x180053707  mov     [rsp+8E0h+var_86C], eax
0x18005370b  mov     al, cs:byte_1800AA941
0x180053711  mov     [rsp+8E0h+var_870], r14d
0x180053716  movups  [rbp+7E0h+var_854], xmm0
0x18005371a  movups  [rbp+7E0h+var_844], xmm0
0x18005371e  movups  [rsp+8E0h+var_868], xmm0
0x180053723  movdqu  [rsp+8E0h+var_898], xmm1
0x180053729  movdqu  [rsp+8E0h+var_888], xmm0
0x18005372f  test    al, 8
0x180053731  jz      short loc_18005375D
0x180053733  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005373a  lea     r8, [rsp+8E0h+exception]; unsigned int *
0x18005373f  lea     rdx, aVpnikenewrasin; "VpnikeNewRasIncomingCall"
0x180053746  lea     rcx, [rsp+8E0h+var_8A0]; this
0x18005374b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180053750  mov     al, cs:byte_1800AA941
0x180053756  mov     rbx, cs:WPP_GLOBAL_Control
0x18005375d  test    rsi, rsi
0x180053760  jz      loc_180053C8F
0x180053766  test    rdi, rdi
0x180053769  jz      loc_180053C8F
0x18005376f  movzx   ecx, word ptr [rdi]
0x180053772  cmp     cx, [rdi+14h]
0x180053776  jnz     loc_180053C60
0x18005377c  mov     r13d, 2
0x180053782  cmp     cx, r13w
0x180053786  jz      short loc_180053792
0x180053788  cmp     cx, 17h
0x18005378c  jnz     loc_180053C60
0x180053792  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053799  test    rcx, rcx
0x18005379c  jz      loc_180053C31
0x1800537a2  test    [rcx+80h], r13b
0x1800537a9  jz      loc_180053C31
0x1800537af  mov     r8, [rsi]
0x1800537b2  test    r8, r8
0x1800537b5  jz      loc_1800539C7
0x1800537bb  test    al, 8
0x1800537bd  jz      short loc_1800537FC
0x1800537bf  xor     eax, eax
0x1800537c1  lea     rdx, aTunnelid0xI64u; "TunnelID: 0x%I64u means NAP Reauth"
0x1800537c8  lea     rcx, [rbp+7E0h+var_830]
0x1800537cc  mov     word ptr [rbp+7E0h+var_830], ax
0x1800537d0  call    FormatRRASErrorString
0x1800537d5  test    cs:byte_1800AA941, 8
0x1800537dc  jz      short loc_1800537F5
0x1800537de  lea     r8, [rbp+7E0h+var_830]
0x1800537e2  lea     rdx, RasVpnIkeTraceInfo
0x1800537e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800537f0  call    McTemplateU0z_EventWriteTransfer
0x1800537f5  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800537fc  mov     rcx, [rcx+8]
0x180053800  mov     rbx, [rsi]
0x180053803  mov     rdx, rbx
0x180053806  mov     rax, [rcx]
0x180053809  mov     rax, [rax+28h]
0x18005380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053812  mov     rdi, rax
0x180053815  test    rax, rax
0x180053818  jz      loc_180053996
0x18005381e  mov     rcx, [rax+70h]
0x180053822  cmp     [rcx+28h], r13d
0x180053826  jnz     loc_180053901
0x18005382c  lea     rbx, [rax+0A0h]
0x180053833  mov     rcx, rbx; lpCriticalSection
0x180053836  call    cs:__imp_EnterCriticalSection
0x18005383c  mov     rdx, [rdi]
0x18005383f  mov     rcx, rdi
0x180053842  mov     rax, [rdx+28h]
0x180053846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005384b  lea     rdx, [rsp+8E0h+var_8A8]
0x180053850  mov     rcx, rdi
0x180053853  call    ?GetReauthConnectionId@BaseConnection@@QEAA?AT_CONNECTION_ID_@@XZ; BaseConnection::GetReauthConnectionId(void)
0x180053858  mov     rcx, rbx; lpCriticalSection
0x18005385b  mov     rdx, [rax]
0x18005385e  mov     [rsi], rdx
0x180053861  call    cs:__imp_LeaveCriticalSection
0x180053867  test    cs:byte_1800AA941, 8
0x18005386e  jz      loc_180053989
0x180053874  xor     eax, eax
0x180053876  mov     word ptr [rbp+7E0h+var_830], ax
0x18005387a  mov     word ptr [rbp+7E0h+var_858], ax
0x18005387e  mov     rax, [rdi+70h]
0x180053882  test    rax, rax
0x180053885  jz      short loc_180053892
0x180053887  cmp     qword ptr [rax+10h], 0
0x18005388c  jz      short loc_180053892
0x18005388e  mov     r14d, [rax+10h]
0x180053892  mov     edx, r14d
0x180053895  lea     rcx, [rbp+7E0h+var_858]
0x180053899  call    ConvertPortNoToString
0x18005389e  mov     r8, [rsi]
0x1800538a1  lea     rdx, aGeneratedNewDu; "Generated New Dummy Tunnel ID: 0x%I64X"
0x1800538a8  lea     rcx, [rbp+7E0h+var_830]
0x1800538ac  call    FormatRRASErrorString
0x1800538b1  test    cs:byte_1800AA941, 8
0x1800538b8  jz      loc_180053989
0x1800538be  mov     rdx, [rdi+70h]
0x1800538c2  mov     rax, rdx
0x1800538c5  neg     rax
0x1800538c8  sbb     r8, r8
0x1800538cb  lea     rcx, [rdx+0A7Eh]
0x1800538d2  and     r8, rcx
0x1800538d5  lea     r9, [rdx+848h]
0x1800538dc  test    rdx, rdx
0x1800538df  jnz     short loc_1800538E6
0x1800538e1  lea     r9, [rsp+8E0h+var_868]
0x1800538e6  lea     rax, [rbp+7E0h+var_858]
0x1800538ea  mov     [rsp+8E0h+var_8B8], rax
0x1800538ef  lea     rdx, RasVpnIkeParamTraceInfo
0x1800538f6  mov     [rsp+8E0h+var_8C0], r8
0x1800538fb  lea     r8, [rbp+7E0h+var_830]
0x1800538ff  jmp     short loc_18005397D
0x180053901  test    cs:byte_1800AA941, 4
0x180053908  jz      short loc_180053989
0x18005390a  xor     eax, eax
0x18005390c  mov     word ptr [rbp+7E0h+var_858], ax
0x180053910  mov     rax, [rdi+70h]
0x180053914  test    rax, rax
0x180053917  jz      short loc_180053924
0x180053919  cmp     qword ptr [rax+10h], 0
0x18005391e  jz      short loc_180053924
0x180053920  mov     r14d, [rax+10h]
0x180053924  mov     edx, r14d
0x180053927  lea     rcx, [rbp+7E0h+var_858]
0x18005392b  call    ConvertPortNoToString
0x180053930  test    cs:byte_1800AA941, 4
0x180053937  jz      short loc_180053989
0x180053939  mov     rdx, [rdi+70h]
0x18005393d  mov     rax, rdx
0x180053940  neg     rax
0x180053943  sbb     r8, r8
0x180053946  lea     rcx, [rdx+0A7Eh]
0x18005394d  and     r8, rcx
0x180053950  lea     r9, [rdx+848h]
0x180053957  test    rdx, rdx
0x18005395a  jnz     short loc_180053961
0x18005395c  lea     r9, [rsp+8E0h+var_868]
0x180053961  lea     rax, [rbp+7E0h+var_858]
0x180053965  mov     [rsp+8E0h+var_8B8], rax
0x18005396a  lea     rdx, RasVpnIkeParamTraceError
0x180053971  mov     [rsp+8E0h+var_8C0], r8
0x180053976  lea     r8, aInvalidConnect_0; "Invalid Connection Type: Expecting Serv"...
0x18005397d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053984  call    McTemplateU0zjzz_EventWriteTransfer
0x180053989  mov     rcx, rdi; this
0x18005398c  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180053991  jmp     loc_180053B87
0x180053996  test    cs:byte_1800AA941, 4
0x18005399d  jz      short loc_180053A11
0x18005399f  xor     eax, eax
0x1800539a1  mov     r8d, ebx
0x1800539a4  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x1800539ab  mov     word ptr [rbp+7E0h+var_830], ax
0x1800539af  lea     rcx, [rbp+7E0h+var_830]
0x1800539b3  call    FormatRRASErrorString
0x1800539b8  test    cs:byte_1800AA941, 4
0x1800539bf  jz      short loc_180053A11
0x1800539c1  lea     r8, [rbp+7E0h+var_830]
0x1800539c5  jmp     short loc_1800539FE
0x1800539c7  mov     qword ptr [rsi], 0
0x1800539ce  lea     rdx, [rsp+8E0h+var_8A8]
0x1800539d3  mov     rcx, [rcx+8]
0x1800539d7  mov     rax, [rcx]
0x1800539da  mov     rax, [rax+30h]
0x1800539de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539e3  mov     rbx, [rax]
0x1800539e6  mov     [rsi], rbx
0x1800539e9  test    rbx, rbx
0x1800539ec  jnz     short loc_180053A25
0x1800539ee  test    cs:byte_1800AA941, 4
0x1800539f5  jz      short loc_180053A11
0x1800539f7  lea     r8, aFailedToGenera; "Failed to generate new TunnelId"
0x1800539fe  lea     rdx, RasVpnIkeTraceError
0x180053a05  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053a0c  call    McTemplateU0z_EventWriteTransfer
0x180053a11  mov     rbx, cs:WPP_GLOBAL_Control
0x180053a18  mov     [rsp+8E0h+exception], 345h
0x180053a20  jmp     loc_180053CC7
0x180053a25  test    cs:byte_1800AA941, 8
0x180053a2c  jz      short loc_180053A67
0x180053a2e  xor     eax, eax
0x180053a30  lea     rdx, aGeneratedNewTu; "Generated New Tunnel ID: 0x%I64X"
0x180053a37  mov     r8, rbx
0x180053a3a  mov     word ptr [rbp+7E0h+var_830], ax
0x180053a3e  lea     rcx, [rbp+7E0h+var_830]
0x180053a42  call    FormatRRASErrorString
0x180053a47  test    cs:byte_1800AA941, 8
0x180053a4e  jz      short loc_180053A67
0x180053a50  lea     r8, [rbp+7E0h+var_830]
0x180053a54  lea     rdx, RasVpnIkeTraceInfo
0x180053a5b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053a62  call    McTemplateU0z_EventWriteTransfer
0x180053a67  mov     rcx, rdi; struct _IKETUNNEL_PARAMETERS_ *
0x180053a6a  call    ?LogIkeTunnelParams@@YAXPEAU_IKETUNNEL_PARAMETERS_@@@Z; LogIkeTunnelParams(_IKETUNNEL_PARAMETERS_ *)
0x180053a6f  mov     rcx, rbx
0x180053a72  call    CreateSynchronizingEvent
0x180053a77  mov     [rsp+8E0h+exception], eax
0x180053a7b  test    eax, eax
0x180053a7d  jz      short loc_180053A98
0x180053a7f  test    cs:byte_1800AA941, 4
0x180053a86  jz      loc_180053B87
0x180053a8c  lea     r8, aCreationOfSync_1; "Creation of synchronizing event failed"
0x180053a93  jmp     loc_180053B74
0x180053a98  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053a9f  mov     rcx, [rax+8]
0x180053aa3  mov     rax, [rcx]
0x180053aa6  mov     rax, [rax+78h]
0x180053aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aaf  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053ab6  mov     edx, ebx
0x180053ab8  mov     rcx, [rax+8]
0x180053abc  mov     rax, [rcx]
0x180053abf  mov     rax, [rax+60h]
0x180053ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ac8  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053acf  mov     rcx, [rax+8]
0x180053ad3  mov     rax, [rcx]
0x180053ad6  mov     rax, [rax+80h]
0x180053add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ae2  mov     rdx, rdi
0x180053ae5  mov     rcx, rbx
0x180053ae8  call    ?IncomingCall@VPNIKEServerConnection@@SAKT_CONNECTION_ID_@@AEAU_IKETUNNEL_PARAMETERS_@@@Z; VPNIKEServerConnection::IncomingCall(_CONNECTION_ID_,_IKETUNNEL_PARAMETERS_ &)
0x180053aed  mov     [rsp+8E0h+exception], eax
0x180053af1  test    eax, eax
0x180053af3  jz      loc_180053B87
0x180053af9  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053b00  mov     rcx, [rax+8]
0x180053b04  mov     rax, [rcx]
0x180053b07  mov     rax, [rax+78h]
0x180053b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b10  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053b17  mov     edx, ebx
0x180053b19  mov     rcx, [rax+8]
0x180053b1d  mov     rax, [rcx]
0x180053b20  mov     rax, [rax+70h]
0x180053b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b29  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180053b30  mov     rcx, [rax+8]
0x180053b34  mov     rax, [rcx]
0x180053b37  mov     rax, [rax+80h]
0x180053b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b43  test    cs:byte_1800AA941, 4
0x180053b4a  jz      short loc_180053B87
0x180053b4c  mov     r8d, [rsp+8E0h+exception]
0x180053b51  lea     rdx, aVpnikeserverco_31; "VPNIKEServerConnection::IncomingCall wi"...
0x180053b58  xor     eax, eax
0x180053b5a  lea     rcx, [rbp+7E0h+var_830]
0x180053b5e  mov     word ptr [rbp+7E0h+var_830], ax
0x180053b62  call    FormatRRASErrorString
0x180053b67  test    cs:byte_1800AA941, 4
0x180053b6e  jz      short loc_180053B87
0x180053b70  lea     r8, [rbp+7E0h+var_830]
0x180053b74  lea     rdx, RasVpnIkeTraceError
0x180053b7b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053b82  call    McTemplateU0z_EventWriteTransfer
0x180053b87  cmp     [rsp+8E0h+exception], 0
0x180053b8c  jz      short loc_180053BC8
0x180053b8e  mov     rbx, [rsi]
  ... truncated ...
```
