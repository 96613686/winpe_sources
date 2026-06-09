# VpnikeTunnelAuthDone

- ea: `0x180055f90`
- end: `0x18005653e`
- name: `VpnikeTunnelAuthDone`
- size: `1454`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x18000a3ec`
- `0x1800239c0`
- `0x180026cc4`
- `0x1800509f0`
- `0x180055f90`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800561b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800561b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800563d6`
- `RPCRT4!RpcRaiseException` at `0x1800564d4`
- `RPCRT4!RpcRaiseException` at `0x1800564d4`

## string_xrefs

- `0x18005625d`: `Ignoring AUTH_DONE notificaton during tunnel re-auth.`
- `0x1800562b8`: `Ignoring AuthDone notfication as DDM has already rejected the tunnel: 0x%I64X`

## pseudocode

```c
__int64 __fastcall VpnikeTunnelAuthDone(__int64 a1, __int64 a2, struct _IKETUNNEL_PARAMETERS_ *a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // r15d
  char v7; // al
  __int16 v8; // cx
  unsigned int v9; // ecx
  struct _RTL_CRITICAL_SECTION *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // r12
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v14; // rdx
  __int128 *v15; // r9
  ULONG_PTR v16; // rax
  ULONG_PTR v17; // rdx
  __int128 *v18; // r9
  ULONG_PTR v19; // rax
  ULONG_PTR v20; // rdx
  __int128 *v21; // r9
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h]
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+6Ch] [rbp-94h]
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+84h] [rbp-7Ch]
  __int128 v33; // [rsp+94h] [rbp-6Ch]
  int v34; // [rsp+A4h] [rbp-5Ch]
  int v35; // [rsp+B0h] [rbp-50h] BYREF
  char v36[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v6 = -1;
  v31 = 0;
  v34 = 0;
  v24 = 0;
  v27 = 0;
  v29 = 0;
  v7 = byte_1800AA941;
  v28 = -1;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v25 = 0;
  v26 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v24,
      L"VpnikeTunnelAuthDone",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 || !a3 )
  {
    if ( (v7 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Parameter");
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v9 = 87;
    goto LABEL_64;
  }
  v8 = *(_WORD *)a3;
  if ( *(_WORD *)a3 != *((_WORD *)a3 + 10) || v8 != 2 && v8 != 23 )
  {
    v9 = 13;
    exception = 13;
    if ( (v7 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Data: vpnIkeTunnelParams");
LABEL_60:
      v9 = exception;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_65;
    }
LABEL_66:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    {
      WPP_SF_d(v5[2], 62, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v9);
      v9 = exception;
    }
    RpcRaiseException(v9);
  }
  if ( (v7 & 8) != 0 )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"Tunnel ID: 0x%I64X", a2);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v35);
  }
  LogIkeTunnelParams(a3);
  if ( (byte_1800AA941 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceInfo,
      L"Checking for DdmStart notification. Waiting on sychronizing event");
  exception = WaitOnSynchronizingEvent(a2);
  v9 = exception;
  if ( !exception )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine
                                                                                        + 1)
                                                                                     + 40LL))(
                                            *((_QWORD *)VpnIkeProtocolEngine + 1),
                                            a2);
    v11 = v10;
    if ( v10 )
    {
      v12 = v10 + 4;
      EnterCriticalSection(v10 + 4);
      if ( *(_DWORD *)(v11[2].SpinCount + 40) == 2 )
      {
        if ( (a2 & 0xFF00000000LL) != 0 )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v31) = 0;
            SpinCount = v11[2].SpinCount;
            if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
              v6 = *(_DWORD *)(SpinCount + 16);
            ConvertPortNoToString(&v31, v6);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v14 = v11[2].SpinCount;
              LODWORD(v15) = v14 + 2120;
              if ( !v14 )
                v15 = &v30;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)L"Ignoring AUTH_DONE notificaton during tunnel re-auth.",
                (_DWORD)v15,
                (v14 + 2686) & -(__int64)(v11[2].SpinCount != 0),
                (__int64)&v31);
            }
          }
        }
        else if ( (unsigned int)VPNIKEServerConnection::IsStopPending(
                                  (VPNIKEServerConnection *)v11,
                                  (unsigned int *)&exception) )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v35) = 0;
            LOWORD(v31) = 0;
            v16 = v11[2].SpinCount;
            if ( v16 && *(_QWORD *)(v16 + 16) )
              v6 = *(_DWORD *)(v16 + 16);
            ConvertPortNoToString(&v31, v6);
            FormatRRASErrorString(
              &v35,
              L"Ignoring AuthDone notfication as DDM has already rejected the tunnel: 0x%I64X",
              a2);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v17 = v11[2].SpinCount;
              LODWORD(v18) = v17 + 2120;
              if ( !v17 )
                v18 = &v30;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v35,
                (_DWORD)v18,
                (v17 + 2686) & -(__int64)(v11[2].SpinCount != 0),
                (__int64)&v31);
            }
          }
          if ( !exception )
            exception = 808;
        }
        else
        {
          exception = VPNIKEServerConnection::TunnelAuthDone((VPNIKEServerConnection *)v11, a3);
        }
      }
      else if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v31) = 0;
        v19 = v11[2].SpinCount;
        if ( v19 && *(_QWORD *)(v19 + 16) )
          v6 = *(_DWORD *)(v19 + 16);
        ConvertPortNoToString(&v31, v6);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v20 = v11[2].SpinCount;
          LODWORD(v21) = v20 + 2120;
          if ( !v20 )
            v21 = &v30;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"Invalid Connection Type: Expecting Server connection",
            (_DWORD)v21,
            (v20 + 2686) & -(__int64)(v11[2].SpinCount != 0),
            (__int64)&v31);
        }
      }
      LeaveCriticalSection(v12);
      BaseConnection::DeleteRef((BaseConnection *)v11);
      goto LABEL_60;
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v35);
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 837;
    exception = 837;
    goto LABEL_66;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Wait on synchronizing event failed. ");
    v9 = exception;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( v9 == 1168 )
  {
    v9 = 808;
LABEL_64:
    exception = v9;
  }
LABEL_65:
  if ( v9 )
    goto LABEL_66;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 63, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v24);
  return 0;
}

```

## disassembly

```asm
0x180055f90  mov     [rsp-8+arg_0], rbx
0x180055f95  push    rbp
0x180055f96  push    rsi
0x180055f97  push    r12
0x180055f99  push    r14
0x180055f9b  push    r15
0x180055f9d  lea     rbp, [rsp-7C0h]
0x180055fa5  sub     rsp, 8C0h
0x180055fac  mov     rax, cs:__security_cookie
0x180055fb3  xor     rax, rsp
0x180055fb6  mov     [rbp+7E0h+var_30], rax
0x180055fbd  mov     r14, r8
0x180055fc0  mov     rsi, rdx
0x180055fc3  mov     rbx, cs:WPP_GLOBAL_Control
0x180055fca  lea     rax, WPP_GLOBAL_Control
0x180055fd1  cmp     rbx, rax
0x180055fd4  jz      short loc_180056001
0x180055fd6  test    byte ptr [rbx+1Ch], 1
0x180055fda  jz      short loc_180056001
0x180055fdc  cmp     byte ptr [rbx+19h], 6
0x180055fe0  jb      short loc_180056001
0x180055fe2  mov     rcx, [rbx+10h]
0x180055fe6  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055fed  mov     edx, 3Dh ; '='
0x180055ff2  mov     r9, rsi
0x180055ff5  call    WPP_SF_q
0x180055ffa  mov     rbx, cs:WPP_GLOBAL_Control
0x180056001  xor     eax, eax
0x180056003  mov     [rsp+8E0h+exception], 0
0x18005600b  xor     edx, edx; Val
0x18005600d  mov     [rbp+7E0h+var_830], eax
0x180056010  mov     r8d, 7FCh; Size
0x180056016  lea     rcx, [rbp+7E0h+var_82C]; void *
0x18005601a  call    memset_0
0x18005601f  xor     eax, eax
0x180056021  xorps   xmm0, xmm0
0x180056024  or      r15d, 0FFFFFFFFh
0x180056028  mov     [rbp+7E0h+var_860], eax
0x18005602b  mov     [rbp+7E0h+var_83C], eax
0x18005602e  mov     r12b, 8
0x180056031  mov     [rsp+8E0h+var_8A8], rax
0x180056036  xorps   xmm1, xmm1
0x180056039  mov     [rsp+8E0h+var_880], rax
0x18005603e  mov     [rsp+8E0h+var_874], eax
0x180056042  mov     al, cs:byte_1800AA941
0x180056048  mov     [rsp+8E0h+var_878], r15d
0x18005604d  movups  [rbp+7E0h+var_85C], xmm0
0x180056051  movups  [rbp+7E0h+var_84C], xmm0
0x180056055  movups  [rsp+8E0h+var_870], xmm0
0x18005605a  movdqu  [rsp+8E0h+var_8A0], xmm1
0x180056060  movdqu  [rsp+8E0h+var_890], xmm0
0x180056066  test    r12b, al
0x180056069  jz      short loc_180056095
0x18005606b  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180056072  lea     r8, [rsp+8E0h+exception]; unsigned int *
0x180056077  lea     rdx, aVpniketunnelau; "VpnikeTunnelAuthDone"
0x18005607e  lea     rcx, [rsp+8E0h+var_8A8]; this
0x180056083  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180056088  mov     al, cs:byte_1800AA941
0x18005608e  mov     rbx, cs:WPP_GLOBAL_Control
0x180056095  test    rsi, rsi
0x180056098  jz      loc_18005646E
0x18005609e  test    r14, r14
0x1800560a1  jz      loc_18005646E
0x1800560a7  movzx   ecx, word ptr [r14]
0x1800560ab  cmp     cx, [r14+14h]
0x1800560b0  jnz     loc_18005643A
0x1800560b6  mov     edx, 2
0x1800560bb  cmp     cx, dx
0x1800560be  jz      short loc_1800560CA
0x1800560c0  cmp     cx, 17h
0x1800560c4  jnz     loc_18005643A
0x1800560ca  test    r12b, al
0x1800560cd  jz      short loc_180056108
0x1800560cf  xor     eax, eax
0x1800560d1  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x1800560d8  mov     r8, rsi
0x1800560db  mov     word ptr [rbp+7E0h+var_830], ax
0x1800560df  lea     rcx, [rbp+7E0h+var_830]
0x1800560e3  call    FormatRRASErrorString
0x1800560e8  test    cs:byte_1800AA941, r12b
0x1800560ef  jz      short loc_180056108
0x1800560f1  lea     r8, [rbp+7E0h+var_830]
0x1800560f5  lea     rdx, RasVpnIkeTraceInfo
0x1800560fc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056103  call    McTemplateU0z_EventWriteTransfer
0x180056108  mov     rcx, r14; struct _IKETUNNEL_PARAMETERS_ *
0x18005610b  call    ?LogIkeTunnelParams@@YAXPEAU_IKETUNNEL_PARAMETERS_@@@Z; LogIkeTunnelParams(_IKETUNNEL_PARAMETERS_ *)
0x180056110  test    cs:byte_1800AA941, r12b
0x180056117  jz      short loc_180056133
0x180056119  lea     r8, aCheckingForDdm; "Checking for DdmStart notification. Wai"...
0x180056120  lea     rdx, RasVpnIkeTraceInfo
0x180056127  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005612e  call    McTemplateU0z_EventWriteTransfer
0x180056133  mov     rcx, rsi
0x180056136  call    WaitOnSynchronizingEvent
0x18005613b  mov     [rsp+8E0h+exception], eax
0x18005613f  mov     ecx, eax
0x180056141  test    eax, eax
0x180056143  jz      short loc_180056189
0x180056145  test    cs:byte_1800AA941, 4
0x18005614c  jz      short loc_18005616C
0x18005614e  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x180056155  lea     rdx, RasVpnIkeTraceError
0x18005615c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056163  call    McTemplateU0z_EventWriteTransfer
0x180056168  mov     ecx, [rsp+8E0h+exception]
0x18005616c  mov     rbx, cs:WPP_GLOBAL_Control
0x180056173  cmp     ecx, 490h
0x180056179  jnz     loc_18005649C
0x18005617f  mov     ecx, 328h
0x180056184  jmp     loc_180056498
0x180056189  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180056190  mov     rdx, rsi
0x180056193  mov     rcx, [rax+8]
0x180056197  mov     rax, [rcx]
0x18005619a  mov     rax, [rax+28h]
0x18005619e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561a3  mov     rbx, rax
0x1800561a6  test    rax, rax
0x1800561a9  jz      loc_1800563E6
0x1800561af  lea     r12, [rax+0A0h]
0x1800561b6  mov     rcx, r12; lpCriticalSection
0x1800561b9  call    cs:__imp_EnterCriticalSection
0x1800561bf  mov     rcx, [rbx+70h]
0x1800561c3  cmp     dword ptr [rcx+28h], 2
0x1800561c7  jnz     loc_18005634B
0x1800561cd  mov     rax, 0FF00000000h
0x1800561d7  test    rax, rsi
0x1800561da  jz      loc_180056269
0x1800561e0  test    cs:byte_1800AA941, 8
0x1800561e7  jz      loc_1800563D3
0x1800561ed  xor     eax, eax
0x1800561ef  mov     word ptr [rbp+7E0h+var_860], ax
0x1800561f3  mov     rax, [rbx+70h]
0x1800561f7  test    rax, rax
0x1800561fa  jz      short loc_180056207
0x1800561fc  cmp     qword ptr [rax+10h], 0
0x180056201  jz      short loc_180056207
0x180056203  mov     r15d, [rax+10h]
0x180056207  mov     edx, r15d
0x18005620a  lea     rcx, [rbp+7E0h+var_860]
0x18005620e  call    ConvertPortNoToString
0x180056213  test    cs:byte_1800AA941, 8
0x18005621a  jz      loc_1800563D3
0x180056220  mov     rdx, [rbx+70h]
0x180056224  mov     rax, rdx
0x180056227  neg     rax
0x18005622a  sbb     r8, r8
0x18005622d  lea     rcx, [rdx+0A7Eh]
0x180056234  and     r8, rcx
0x180056237  lea     r9, [rdx+848h]
0x18005623e  test    rdx, rdx
0x180056241  jnz     short loc_180056248
0x180056243  lea     r9, [rsp+8E0h+var_870]
0x180056248  lea     rax, [rbp+7E0h+var_860]
0x18005624c  mov     [rsp+8E0h+var_8B8], rax
0x180056251  lea     rdx, RasVpnIkeParamTraceInfo
0x180056258  mov     [rsp+8E0h+var_8C0], r8
0x18005625d  lea     r8, aIgnoringAuthDo; "Ignoring AUTH_DONE notificaton during t"...
0x180056264  jmp     loc_1800563C7
0x180056269  lea     rdx, [rsp+8E0h+exception]; unsigned int *
0x18005626e  mov     rcx, rbx; this
0x180056271  call    ?IsStopPending@VPNIKEServerConnection@@QEAAHPEAK@Z; VPNIKEServerConnection::IsStopPending(ulong *)
0x180056276  test    eax, eax
0x180056278  jz      loc_180056337
0x18005627e  test    cs:byte_1800AA941, 4
0x180056285  jz      loc_18005631E
0x18005628b  xor     eax, eax
0x18005628d  mov     word ptr [rbp+7E0h+var_830], ax
0x180056291  mov     word ptr [rbp+7E0h+var_860], ax
0x180056295  mov     rax, [rbx+70h]
0x180056299  test    rax, rax
0x18005629c  jz      short loc_1800562A9
0x18005629e  cmp     qword ptr [rax+10h], 0
0x1800562a3  jz      short loc_1800562A9
0x1800562a5  mov     r15d, [rax+10h]
0x1800562a9  mov     edx, r15d
0x1800562ac  lea     rcx, [rbp+7E0h+var_860]
0x1800562b0  call    ConvertPortNoToString
0x1800562b5  mov     r8, rsi
0x1800562b8  lea     rdx, aIgnoringAuthdo; "Ignoring AuthDone notfication as DDM ha"...
0x1800562bf  lea     rcx, [rbp+7E0h+var_830]
0x1800562c3  call    FormatRRASErrorString
0x1800562c8  test    cs:byte_1800AA941, 4
0x1800562cf  jz      short loc_18005631E
0x1800562d1  mov     rdx, [rbx+70h]
0x1800562d5  mov     rax, rdx
0x1800562d8  neg     rax
0x1800562db  sbb     r8, r8
0x1800562de  lea     rcx, [rdx+0A7Eh]
0x1800562e5  and     r8, rcx
0x1800562e8  lea     r9, [rdx+848h]
0x1800562ef  test    rdx, rdx
0x1800562f2  jnz     short loc_1800562F9
0x1800562f4  lea     r9, [rsp+8E0h+var_870]
0x1800562f9  lea     rax, [rbp+7E0h+var_860]
0x1800562fd  mov     [rsp+8E0h+var_8B8], rax
0x180056302  lea     rdx, RasVpnIkeParamTraceError
0x180056309  mov     [rsp+8E0h+var_8C0], r8
0x18005630e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056315  lea     r8, [rbp+7E0h+var_830]
0x180056319  call    McTemplateU0zjzz_EventWriteTransfer
0x18005631e  cmp     [rsp+8E0h+exception], 0
0x180056323  jnz     loc_1800563D3
0x180056329  mov     ecx, 328h
0x18005632e  mov     [rsp+8E0h+exception], ecx
0x180056332  jmp     loc_1800563D3
0x180056337  mov     rdx, r14; struct _IKETUNNEL_PARAMETERS_ *
0x18005633a  mov     rcx, rbx; this
0x18005633d  call    ?TunnelAuthDone@VPNIKEServerConnection@@QEAAKAEAU_IKETUNNEL_PARAMETERS_@@@Z; VPNIKEServerConnection::TunnelAuthDone(_IKETUNNEL_PARAMETERS_ &)
0x180056342  mov     [rsp+8E0h+exception], eax
0x180056346  jmp     loc_1800563D3
0x18005634b  test    cs:byte_1800AA941, 4
0x180056352  jz      short loc_1800563D3
0x180056354  xor     eax, eax
0x180056356  mov     word ptr [rbp+7E0h+var_860], ax
0x18005635a  mov     rax, [rbx+70h]
0x18005635e  test    rax, rax
0x180056361  jz      short loc_18005636E
0x180056363  cmp     qword ptr [rax+10h], 0
0x180056368  jz      short loc_18005636E
0x18005636a  mov     r15d, [rax+10h]
0x18005636e  mov     edx, r15d
0x180056371  lea     rcx, [rbp+7E0h+var_860]
0x180056375  call    ConvertPortNoToString
0x18005637a  test    cs:byte_1800AA941, 4
0x180056381  jz      short loc_1800563D3
0x180056383  mov     rdx, [rbx+70h]
0x180056387  mov     rax, rdx
0x18005638a  neg     rax
0x18005638d  sbb     r8, r8
0x180056390  lea     rcx, [rdx+0A7Eh]
0x180056397  and     r8, rcx
0x18005639a  lea     r9, [rdx+848h]
0x1800563a1  test    rdx, rdx
0x1800563a4  jnz     short loc_1800563AB
0x1800563a6  lea     r9, [rsp+8E0h+var_870]
0x1800563ab  lea     rax, [rbp+7E0h+var_860]
0x1800563af  mov     [rsp+8E0h+var_8B8], rax
0x1800563b4  lea     rdx, RasVpnIkeParamTraceError
0x1800563bb  mov     [rsp+8E0h+var_8C0], r8
0x1800563c0  lea     r8, aInvalidConnect_0; "Invalid Connection Type: Expecting Serv"...
0x1800563c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800563ce  call    McTemplateU0zjzz_EventWriteTransfer
0x1800563d3  mov     rcx, r12; lpCriticalSection
0x1800563d6  call    cs:__imp_LeaveCriticalSection
0x1800563dc  mov     rcx, rbx; this
0x1800563df  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800563e4  jmp     short loc_180056461
0x1800563e6  test    cs:byte_1800AA941, 4
0x1800563ed  jz      short loc_180056428
0x1800563ef  xor     eax, eax
0x1800563f1  mov     r8d, esi
0x1800563f4  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x1800563fb  mov     word ptr [rbp+7E0h+var_830], ax
0x1800563ff  lea     rcx, [rbp+7E0h+var_830]
0x180056403  call    FormatRRASErrorString
0x180056408  test    cs:byte_1800AA941, 4
0x18005640f  jz      short loc_180056428
0x180056411  lea     r8, [rbp+7E0h+var_830]
0x180056415  lea     rdx, RasVpnIkeTraceError
0x18005641c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056423  call    McTemplateU0z_EventWriteTransfer
0x180056428  mov     rbx, cs:WPP_GLOBAL_Control
0x18005642f  mov     ecx, 345h
0x180056434  mov     [rsp+8E0h+exception], ecx
0x180056438  jmp     short loc_1800564A0
0x18005643a  mov     ecx, 0Dh
0x18005643f  mov     [rsp+8E0h+exception], ecx
0x180056443  test    al, 4
0x180056445  jz      short loc_1800564A0
0x180056447  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x18005644e  lea     rdx, RasVpnIkeTraceError
0x180056455  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005645c  call    McTemplateU0z_EventWriteTransfer
0x180056461  mov     ecx, [rsp+8E0h+exception]
0x180056465  mov     rbx, cs:WPP_GLOBAL_Control
0x18005646c  jmp     short loc_18005649C
0x18005646e  test    al, 4
0x180056470  jz      short loc_180056493
0x180056472  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180056479  lea     rdx, RasVpnIkeTraceError
0x180056480  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056487  call    McTemplateU0z_EventWriteTransfer
0x18005648c  mov     rbx, cs:WPP_GLOBAL_Control
0x180056493  mov     ecx, 57h ; 'W'
0x180056498  mov     [rsp+8E0h+exception], ecx
0x18005649c  test    ecx, ecx
0x18005649e  jz      short loc_1800564DB
0x1800564a0  lea     rax, WPP_GLOBAL_Control
0x1800564a7  cmp     rbx, rax
0x1800564aa  jz      short loc_1800564D4
0x1800564ac  test    byte ptr [rbx+1Ch], 1
0x1800564b0  jz      short loc_1800564D4
0x1800564b2  cmp     byte ptr [rbx+19h], 6
0x1800564b6  jb      short loc_1800564D4
0x1800564b8  mov     r9d, ecx
0x1800564bb  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800564c2  mov     rcx, [rbx+10h]
  ... truncated ...
```
