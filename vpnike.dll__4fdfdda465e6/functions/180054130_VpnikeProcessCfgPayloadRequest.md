# VpnikeProcessCfgPayloadRequest

- ea: `0x180054130`
- end: `0x180054829`
- name: `VpnikeProcessCfgPayloadRequest`
- size: `1785`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x18000a3ec`
- `0x1800239c0`
- `0x1800505a4`
- `0x180054130`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054373`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054373`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054361`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545e3`
- `RPCRT4!RpcRaiseException` at `0x1800547bc`
- `RPCRT4!RpcRaiseException` at `0x1800547bc`

## string_xrefs

- `0x18005452f`: `Ignoring CreateTunnel ProcessCfgPayloadRequest as DDM has already rejected the tunnel: 0x%I64X`

## pseudocode

```c
__int64 __fastcall VpnikeProcessCfgPayloadRequest(
        __int64 a1,
        __int64 a2,
        struct _CONFIGURATION_PAYLOAD_ *a3,
        struct _CONFIGURATION_PAYLOAD_ **a4)
{
  PVOID *v7; // rbx
  unsigned int v8; // edi
  char v9; // al
  __int64 v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  ULONG_PTR SpinCount; // rdx
  __int128 *v15; // r9
  HANDLE ProcessHeap; // rax
  struct _CONFIGURATION_PAYLOAD_ *v17; // rax
  ULONG_PTR v18; // rax
  ULONG_PTR v19; // rdx
  __int128 *v20; // r9
  ULONG_PTR v21; // rax
  ULONG_PTR v22; // rdx
  __int128 *v23; // r9
  ULONG_PTR v24; // rax
  ULONG_PTR v25; // rdx
  __int128 *v26; // r9
  unsigned int v27; // ecx
  ULONG_PTR v28; // rax
  ULONG_PTR v29; // rdx
  __int128 *v30; // r9
  ULONG_PTR v31; // rax
  ULONG_PTR v32; // rdx
  __int128 *v33; // r9
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v37; // [rsp+40h] [rbp-C0h]
  __int128 v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+6Ch] [rbp-94h]
  __int128 v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+80h] [rbp-80h] BYREF
  __int128 v44; // [rsp+84h] [rbp-7Ch]
  __int128 v45; // [rsp+94h] [rbp-6Ch]
  int v46; // [rsp+A4h] [rbp-5Ch]
  int v47; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v43 = 0;
  v36 = 0;
  v8 = -1;
  v46 = 0;
  v9 = byte_1800AA941;
  v39 = 0;
  v40 = -1;
  v41 = 0;
  v44 = 0;
  v45 = 0;
  v42 = 0;
  v37 = 0;
  v38 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v36,
      L"VpnikeProcessCfgPayloadRequest",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v9 = byte_1800AA941;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 )
  {
    if ( (v9 & 8) != 0 )
    {
      LOWORD(v47) = 0;
      FormatRRASErrorString(&v47, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v47);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
            *((_QWORD *)VpnIkeProtocolEngine + 1),
            a2);
    v11 = (struct _RTL_CRITICAL_SECTION *)v10;
    if ( !v10 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v47) = 0;
        FormatRRASErrorString(&v47, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v47);
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      v27 = 837;
      exception = 837;
LABEL_85:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        WPP_SF_d(v7[2], 26, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v27);
        v27 = exception;
      }
      RpcRaiseException(v27);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v43) = 0;
      v12 = *(_QWORD *)(v10 + 112);
      if ( v12 && *(_QWORD *)(v12 + 16) )
        v13 = *(unsigned int *)(v12 + 16);
      else
        v13 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v43, v13);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        SpinCount = v11[2].SpinCount;
        LODWORD(v15) = SpinCount + 2120;
        if ( !SpinCount )
          v15 = &v42;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Got Cfg Request from Client.....",
          (_DWORD)v15,
          (SpinCount + 2686) & -(__int64)(v11[2].SpinCount != 0),
          (__int64)&v43);
      }
    }
    LogConfigPayload(a3);
    if ( *(_DWORD *)(v11[2].SpinCount + 40) != 2 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v43) = 0;
        v31 = v11[2].SpinCount;
        if ( v31 && *(_QWORD *)(v31 + 16) )
          v8 = *(_DWORD *)(v31 + 16);
        ConvertPortNoToString(&v43, v8);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v32 = v11[2].SpinCount;
          LODWORD(v33) = v32 + 2120;
          if ( !v32 )
            v33 = &v42;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"Invalid Connection Type: Expecting Server connection",
            (_DWORD)v33,
            (v32 + 2686) & -(__int64)(v11[2].SpinCount != 0),
            (__int64)&v43);
        }
      }
      goto LABEL_57;
    }
    if ( (a2 & 0xFF00000000LL) != 0 )
    {
      ProcessHeap = GetProcessHeap();
      v17 = (struct _CONFIGURATION_PAYLOAD_ *)HeapAlloc(ProcessHeap, 8u, 0x10u);
      *a4 = v17;
      if ( !v17 )
      {
        exception = 8;
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v47) = 0;
          LOWORD(v43) = 0;
          v18 = v11[2].SpinCount;
          if ( v18 && *(_QWORD *)(v18 + 16) )
            v8 = *(_DWORD *)(v18 + 16);
          ConvertPortNoToString(&v43, v8);
          FormatRRASErrorString(&v47, L"VPNIKE_MALLOC failed with error: %d", (unsigned int)exception);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v19 = v11[2].SpinCount;
            LODWORD(v20) = v19 + 2120;
            if ( !v19 )
              v20 = &v42;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v47,
              (_DWORD)v20,
              (v19 + 2686) & -(__int64)(v11[2].SpinCount != 0),
              (__int64)&v43);
          }
        }
LABEL_57:
        BaseConnection::DeleteRef((BaseConnection *)v11);
        v27 = exception;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_84;
      }
      *(_DWORD *)v17 = 2;
      *((_QWORD *)*a4 + 1) = 0;
    }
    else
    {
      exception = WaitOnSynchronizingEvent(a2);
      if ( exception )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v43) = 0;
          v21 = v11[2].SpinCount;
          if ( v21 && *(_QWORD *)(v21 + 16) )
            v8 = *(_DWORD *)(v21 + 16);
          ConvertPortNoToString(&v43, v8);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v22 = v11[2].SpinCount;
            LODWORD(v23) = v22 + 2120;
            if ( !v22 )
              v23 = &v42;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"Wait on synchronizing event failed. ",
              (_DWORD)v23,
              (v22 + 2686) & -(__int64)(v11[2].SpinCount != 0),
              (__int64)&v43);
          }
        }
        goto LABEL_57;
      }
      EnterCriticalSection(v11 + 4);
      if ( *(_DWORD *)(v11[2].SpinCount + 40) == 2
        && (unsigned int)VPNIKEServerConnection::IsStopPending(
                           (VPNIKEServerConnection *)v11,
                           (unsigned int *)&exception) )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v47) = 0;
          LOWORD(v43) = 0;
          v24 = v11[2].SpinCount;
          if ( v24 && *(_QWORD *)(v24 + 16) )
            v8 = *(_DWORD *)(v24 + 16);
          ConvertPortNoToString(&v43, v8);
          FormatRRASErrorString(
            &v47,
            L"Ignoring CreateTunnel ProcessCfgPayloadRequest as DDM has already rejected the tunnel: 0x%I64X",
            a2);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v25 = v11[2].SpinCount;
            LODWORD(v26) = v25 + 2120;
            if ( !v25 )
              v26 = &v42;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v47,
              (_DWORD)v26,
              (v25 + 2686) & -(__int64)(v11[2].SpinCount != 0),
              (__int64)&v43);
          }
        }
        if ( !exception )
          exception = 808;
        LeaveCriticalSection(v11 + 4);
        goto LABEL_57;
      }
      exception = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, struct _CONFIGURATION_PAYLOAD_ **, struct _CONFIGURATION_PAYLOAD_ *, __int64))v11->DebugInfo[2].ProcessLocksList.Flink)(
                    v11,
                    a4,
                    a3,
                    1);
      LeaveCriticalSection(v11 + 4);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v43) = 0;
      v28 = v11[2].SpinCount;
      if ( v28 && *(_QWORD *)(v28 + 16) )
        v8 = *(_DWORD *)(v28 + 16);
      ConvertPortNoToString(&v43, v8);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v29 = v11[2].SpinCount;
        LODWORD(v30) = v29 + 2120;
        if ( !v29 )
          v30 = &v42;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Sending Cfg Response to Client.....",
          (_DWORD)v30,
          (v29 + 2686) & -(__int64)(v11[2].SpinCount != 0),
          (__int64)&v43);
      }
    }
    LogConfigPayload(*a4);
    goto LABEL_57;
  }
  if ( (v9 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Invalid Parameter");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v27 = 87;
  exception = 87;
LABEL_84:
  if ( v27 )
    goto LABEL_85;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 27, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v36);
  return 0;
}

```

## disassembly

```asm
0x180054130  mov     [rsp-8+arg_0], rbx
0x180054135  push    rbp
0x180054136  push    rsi
0x180054137  push    rdi
0x180054138  push    r12
0x18005413a  push    r13
0x18005413c  push    r14
0x18005413e  push    r15
0x180054140  lea     rbp, [rsp-7C0h]
0x180054148  sub     rsp, 8C0h
0x18005414f  mov     rax, cs:__security_cookie
0x180054156  xor     rax, rsp
0x180054159  mov     [rbp+7F0h+var_40], rax
0x180054160  mov     r12, r9
0x180054163  mov     r13, r8
0x180054166  mov     rsi, rdx
0x180054169  mov     rbx, cs:WPP_GLOBAL_Control
0x180054170  lea     rax, WPP_GLOBAL_Control
0x180054177  cmp     rbx, rax
0x18005417a  jz      short loc_1800541A7
0x18005417c  test    byte ptr [rbx+1Ch], 1
0x180054180  jz      short loc_1800541A7
0x180054182  cmp     byte ptr [rbx+19h], 6
0x180054186  jb      short loc_1800541A7
0x180054188  mov     rcx, [rbx+10h]
0x18005418c  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180054193  mov     edx, 19h
0x180054198  mov     r9, rsi
0x18005419b  call    WPP_SF_q
0x1800541a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800541a7  xor     r15d, r15d
0x1800541aa  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800541ae  xor     edx, edx; Val
0x1800541b0  mov     [rsp+8F0h+exception], r15d
0x1800541b5  mov     r8d, 7FCh; Size
0x1800541bb  mov     [rbp+7F0h+var_840], r15d
0x1800541bf  call    memset_0
0x1800541c4  xorps   xmm0, xmm0
0x1800541c7  mov     [rbp+7F0h+var_870], r15d
0x1800541cb  xor     eax, eax
0x1800541cd  mov     [rsp+8F0h+var_8B8], r15
0x1800541d2  or      edi, 0FFFFFFFFh
0x1800541d5  mov     [rbp+7F0h+var_84C], eax
0x1800541d8  mov     al, cs:byte_1800AA941
0x1800541de  xorps   xmm1, xmm1
0x1800541e1  mov     [rsp+8F0h+var_890], r15
0x1800541e6  mov     [rsp+8F0h+var_888], edi
0x1800541ea  mov     [rsp+8F0h+var_884], r15d
0x1800541ef  movups  [rbp+7F0h+var_86C], xmm0
0x1800541f3  movups  [rbp+7F0h+var_85C], xmm0
0x1800541f7  movups  [rsp+8F0h+var_880], xmm0
0x1800541fc  movdqu  [rsp+8F0h+var_8B0], xmm1
0x180054202  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180054208  test    al, 8
0x18005420a  jz      short loc_180054236
0x18005420c  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180054213  lea     r8, [rsp+8F0h+exception]; unsigned int *
0x180054218  lea     rdx, aVpnikeprocessc_0; "VpnikeProcessCfgPayloadRequest"
0x18005421f  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180054224  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180054229  mov     al, cs:byte_1800AA941
0x18005422f  mov     rbx, cs:WPP_GLOBAL_Control
0x180054236  test    rsi, rsi
0x180054239  jz      loc_180054756
0x18005423f  test    r13, r13
0x180054242  jz      loc_180054756
0x180054248  test    r12, r12
0x18005424b  jz      loc_180054756
0x180054251  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180054258  test    al, 8
0x18005425a  jz      short loc_180054290
0x18005425c  mov     r8, rsi
0x18005425f  mov     word ptr [rbp+7F0h+var_840], r15w
0x180054264  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x18005426b  lea     rcx, [rbp+7F0h+var_840]
0x18005426f  call    FormatRRASErrorString
0x180054274  test    cs:byte_1800AA941, 8
0x18005427b  jz      short loc_180054290
0x18005427d  lea     r8, [rbp+7F0h+var_840]
0x180054281  mov     rcx, r14
0x180054284  lea     rdx, RasVpnIkeTraceInfo
0x18005428b  call    McTemplateU0z_EventWriteTransfer
0x180054290  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180054297  mov     rdx, rsi
0x18005429a  mov     rcx, [rax+8]
0x18005429e  mov     rax, [rcx]
0x1800542a1  mov     rax, [rax+28h]
0x1800542a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542aa  mov     rbx, rax
0x1800542ad  test    rax, rax
0x1800542b0  jz      loc_180054707
0x1800542b6  test    cs:byte_1800AA941, 8
0x1800542bd  jz      short loc_180054338
0x1800542bf  mov     word ptr [rbp+7F0h+var_870], r15w
0x1800542c4  mov     rax, [rax+70h]
0x1800542c8  test    rax, rax
0x1800542cb  jz      short loc_1800542D8
0x1800542cd  cmp     [rax+10h], r15
0x1800542d1  jz      short loc_1800542D8
0x1800542d3  mov     edx, [rax+10h]
0x1800542d6  jmp     short loc_1800542DA
0x1800542d8  mov     edx, edi
0x1800542da  lea     rcx, [rbp+7F0h+var_870]
0x1800542de  call    ConvertPortNoToString
0x1800542e3  test    cs:byte_1800AA941, 8
0x1800542ea  jz      short loc_180054338
0x1800542ec  mov     rdx, [rbx+70h]
0x1800542f0  mov     rax, rdx
0x1800542f3  neg     rax
0x1800542f6  sbb     r8, r8
0x1800542f9  lea     rcx, [rdx+0A7Eh]
0x180054300  and     r8, rcx
0x180054303  lea     r9, [rdx+848h]
0x18005430a  test    rdx, rdx
0x18005430d  jnz     short loc_180054314
0x18005430f  lea     r9, [rsp+8F0h+var_880]
0x180054314  lea     rax, [rbp+7F0h+var_870]
0x180054318  mov     rcx, r14
0x18005431b  mov     [rsp+8F0h+var_8C8], rax
0x180054320  lea     rdx, RasVpnIkeParamTraceInfo
0x180054327  mov     [rsp+8F0h+var_8D0], r8
0x18005432c  lea     r8, aGotCfgRequestF; "Got Cfg Request from Client....."
0x180054333  call    McTemplateU0zjzz_EventWriteTransfer
0x180054338  mov     rcx, r13; struct _CONFIGURATION_PAYLOAD_ *
0x18005433b  call    ?LogConfigPayload@@YAXPEAU_CONFIGURATION_PAYLOAD_@@@Z; LogConfigPayload(_CONFIGURATION_PAYLOAD_ *)
0x180054340  mov     rax, [rbx+70h]
0x180054344  cmp     dword ptr [rax+28h], 2
0x180054348  jnz     loc_18005467A
0x18005434e  mov     rax, 0FF00000000h
0x180054358  test    rax, rsi
0x18005435b  jz      loc_180054436
0x180054361  call    cs:__imp_GetProcessHeap
0x180054367  mov     edx, 8; dwFlags
0x18005436c  mov     rcx, rax; hHeap
0x18005436f  lea     r8d, [rdx+8]; dwBytes
0x180054373  call    cs:__imp_HeapAlloc
0x180054379  mov     [r12], rax
0x18005437d  test    rax, rax
0x180054380  jnz     loc_180054423
0x180054386  test    cs:byte_1800AA941, 4
0x18005438d  mov     [rsp+8F0h+exception], 8
0x180054395  jz      loc_1800545A9
0x18005439b  mov     word ptr [rbp+7F0h+var_840], r15w
0x1800543a0  mov     word ptr [rbp+7F0h+var_870], r15w
0x1800543a5  mov     rax, [rbx+70h]
0x1800543a9  test    rax, rax
0x1800543ac  jz      short loc_1800543B7
0x1800543ae  cmp     [rax+10h], r15
0x1800543b2  jz      short loc_1800543B7
0x1800543b4  mov     edi, [rax+10h]
0x1800543b7  mov     edx, edi
0x1800543b9  lea     rcx, [rbp+7F0h+var_870]
0x1800543bd  call    ConvertPortNoToString
0x1800543c2  mov     r8d, [rsp+8F0h+exception]
0x1800543c7  lea     rdx, aVpnikeMallocFa_3; "VPNIKE_MALLOC failed with error: %d"
0x1800543ce  lea     rcx, [rbp+7F0h+var_840]
0x1800543d2  call    FormatRRASErrorString
0x1800543d7  test    cs:byte_1800AA941, 4
0x1800543de  jz      loc_1800545A9
0x1800543e4  mov     rdx, [rbx+70h]
0x1800543e8  mov     rax, rdx
0x1800543eb  neg     rax
0x1800543ee  sbb     r8, r8
0x1800543f1  lea     rcx, [rdx+0A7Eh]
0x1800543f8  and     r8, rcx
0x1800543fb  lea     r9, [rdx+848h]
0x180054402  test    rdx, rdx
0x180054405  jnz     short loc_18005440C
0x180054407  lea     r9, [rsp+8F0h+var_880]
0x18005440c  lea     rax, [rbp+7F0h+var_870]
0x180054410  mov     [rsp+8F0h+var_8C8], rax
0x180054415  mov     [rsp+8F0h+var_8D0], r8
0x18005441a  lea     r8, [rbp+7F0h+var_840]
0x18005441e  jmp     loc_1800546F3
0x180054423  mov     dword ptr [rax], 2
0x180054429  mov     rax, [r12]
0x18005442d  mov     [rax+8], r15
0x180054431  jmp     loc_1800545EC
0x180054436  mov     rcx, rsi
0x180054439  call    WaitOnSynchronizingEvent
0x18005443e  mov     [rsp+8F0h+exception], eax
0x180054442  test    eax, eax
0x180054444  jz      short loc_1800544C4
0x180054446  test    cs:byte_1800AA941, 4
0x18005444d  jz      loc_1800545A9
0x180054453  mov     word ptr [rbp+7F0h+var_870], r15w
0x180054458  mov     rax, [rbx+70h]
0x18005445c  test    rax, rax
0x18005445f  jz      short loc_18005446A
0x180054461  cmp     [rax+10h], r15
0x180054465  jz      short loc_18005446A
0x180054467  mov     edi, [rax+10h]
0x18005446a  mov     edx, edi
0x18005446c  lea     rcx, [rbp+7F0h+var_870]
0x180054470  call    ConvertPortNoToString
0x180054475  test    cs:byte_1800AA941, 4
0x18005447c  jz      loc_1800545A9
0x180054482  mov     rdx, [rbx+70h]
0x180054486  mov     rax, rdx
0x180054489  neg     rax
0x18005448c  sbb     r8, r8
0x18005448f  lea     rcx, [rdx+0A7Eh]
0x180054496  and     r8, rcx
0x180054499  lea     r9, [rdx+848h]
0x1800544a0  test    rdx, rdx
0x1800544a3  jnz     short loc_1800544AA
0x1800544a5  lea     r9, [rsp+8F0h+var_880]
0x1800544aa  lea     rax, [rbp+7F0h+var_870]
0x1800544ae  mov     [rsp+8F0h+var_8C8], rax
0x1800544b3  mov     [rsp+8F0h+var_8D0], r8
0x1800544b8  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x1800544bf  jmp     loc_1800546F3
0x1800544c4  lea     r15, [rbx+0A0h]
0x1800544cb  mov     rcx, r15; lpCriticalSection
0x1800544ce  call    cs:__imp_EnterCriticalSection
0x1800544d4  mov     rax, [rbx+70h]
0x1800544d8  cmp     dword ptr [rax+28h], 2
0x1800544dc  jnz     loc_1800545C1
0x1800544e2  lea     rdx, [rsp+8F0h+exception]; unsigned int *
0x1800544e7  mov     rcx, rbx; this
0x1800544ea  call    ?IsStopPending@VPNIKEServerConnection@@QEAAHPEAK@Z; VPNIKEServerConnection::IsStopPending(ulong *)
0x1800544ef  test    eax, eax
0x1800544f1  jz      loc_1800545C1
0x1800544f7  test    cs:byte_1800AA941, 4
0x1800544fe  jz      loc_180054591
0x180054504  xor     eax, eax
0x180054506  mov     word ptr [rbp+7F0h+var_840], ax
0x18005450a  mov     word ptr [rbp+7F0h+var_870], ax
0x18005450e  mov     rax, [rbx+70h]
0x180054512  test    rax, rax
0x180054515  jz      short loc_180054521
0x180054517  cmp     qword ptr [rax+10h], 0
0x18005451c  jz      short loc_180054521
0x18005451e  mov     edi, [rax+10h]
0x180054521  mov     edx, edi
0x180054523  lea     rcx, [rbp+7F0h+var_870]
0x180054527  call    ConvertPortNoToString
0x18005452c  mov     r8, rsi
0x18005452f  lea     rdx, aIgnoringCreate_0; "Ignoring CreateTunnel ProcessCfgPayload"...
0x180054536  lea     rcx, [rbp+7F0h+var_840]
0x18005453a  call    FormatRRASErrorString
0x18005453f  test    cs:byte_1800AA941, 4
0x180054546  jz      short loc_180054591
0x180054548  mov     rdx, [rbx+70h]
0x18005454c  mov     rax, rdx
0x18005454f  neg     rax
0x180054552  sbb     r8, r8
0x180054555  lea     rcx, [rdx+0A7Eh]
0x18005455c  and     r8, rcx
0x18005455f  lea     r9, [rdx+848h]
0x180054566  test    rdx, rdx
0x180054569  jnz     short loc_180054570
0x18005456b  lea     r9, [rsp+8F0h+var_880]
0x180054570  lea     rax, [rbp+7F0h+var_870]
0x180054574  mov     rcx, r14
0x180054577  mov     [rsp+8F0h+var_8C8], rax
0x18005457c  lea     rdx, RasVpnIkeParamTraceError
0x180054583  mov     [rsp+8F0h+var_8D0], r8
0x180054588  lea     r8, [rbp+7F0h+var_840]
0x18005458c  call    McTemplateU0zjzz_EventWriteTransfer
0x180054591  cmp     [rsp+8F0h+exception], 0
0x180054596  jnz     short loc_1800545A0
0x180054598  mov     [rsp+8F0h+exception], 328h
0x1800545a0  mov     rcx, r15; lpCriticalSection
0x1800545a3  call    cs:__imp_LeaveCriticalSection
0x1800545a9  mov     rcx, rbx; this
0x1800545ac  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800545b1  mov     ecx, [rsp+8F0h+exception]
0x1800545b5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800545bc  jmp     loc_180054784
0x1800545c1  mov     rax, [rbx]
0x1800545c4  mov     r9d, 1
0x1800545ca  mov     r8, r13
0x1800545cd  mov     rdx, r12
0x1800545d0  mov     rcx, rbx
0x1800545d3  mov     rax, [rax+70h]
0x1800545d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545dc  mov     rcx, r15; lpCriticalSection
0x1800545df  mov     [rsp+8F0h+exception], eax
0x1800545e3  call    cs:__imp_LeaveCriticalSection
0x1800545e9  xor     r15d, r15d
0x1800545ec  test    cs:byte_1800AA941, 8
0x1800545f3  jz      short loc_18005466C
0x1800545f5  mov     word ptr [rbp+7F0h+var_870], r15w
0x1800545fa  mov     rax, [rbx+70h]
0x1800545fe  test    rax, rax
0x180054601  jz      short loc_18005460C
0x180054603  cmp     [rax+10h], r15
0x180054607  jz      short loc_18005460C
0x180054609  mov     edi, [rax+10h]
0x18005460c  mov     edx, edi
0x18005460e  lea     rcx, [rbp+7F0h+var_870]
0x180054612  call    ConvertPortNoToString
0x180054617  test    cs:byte_1800AA941, 8
0x18005461e  jz      short loc_18005466C
0x180054620  mov     rdx, [rbx+70h]
0x180054624  mov     rax, rdx
0x180054627  neg     rax
0x18005462a  sbb     r8, r8
0x18005462d  lea     rcx, [rdx+0A7Eh]
  ... truncated ...
```
