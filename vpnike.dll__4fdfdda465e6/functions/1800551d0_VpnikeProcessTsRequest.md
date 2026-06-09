# VpnikeProcessTsRequest

- ea: `0x1800551d0`
- end: `0x180055893`
- name: `VpnikeProcessTsRequest`
- size: `1731`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x18000a3ec`
- `0x1800239c0`
- `0x180050e78`
- `0x1800551d0`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055375`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055375`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055728`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055728`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055763`
- `RPCRT4!RpcRaiseException` at `0x180055826`
- `RPCRT4!RpcRaiseException` at `0x180055826`

## string_xrefs

- `0x180055438`: `VPNIKE Connection object not yet created. Waiting on sychronizing event`
- `0x1800555dd`: `TS Responder: Got playload for TsId [%I64u]`
- `0x1800556b5`: `Ignoring ProcessTsRequest notfication as DDM has already rejected the tunnel: 0x%I64X`
- `0x18005577d`: `TS Responder: Respond TS payload with TsId [%I64u]`

## pseudocode

```c
__int64 __fastcall VpnikeProcessTsRequest(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        struct _VPN_TRAFFIC_SELECTORS_ *a4,
        struct _VPN_TRAFFIC_SELECTORS_ **a5)
{
  PVOID *v8; // rbx
  unsigned int v9; // r13d
  char v10; // al
  HANDLE ProcessHeap; // rax
  struct _VPN_TRAFFIC_SELECTORS_ *v12; // rax
  const wchar_t *v13; // r8
  __int64 *v14; // rdx
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v17; // rdx
  __int128 *v18; // r9
  ULONG_PTR v19; // rax
  __int64 v20; // rdx
  ULONG_PTR v21; // rdx
  __int128 *v22; // r9
  ULONG_PTR v23; // rax
  ULONG_PTR v24; // rdx
  __int128 *v25; // r9
  __int64 *v26; // rdi
  __int64 v27; // r8
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  struct _VPN_TRAFFIC_SELECTORS_ *v30; // [rsp+38h] [rbp-C8h]
  __int64 *v31; // [rsp+40h] [rbp-C0h]
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h]
  __int128 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  __int128 v38; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+90h] [rbp-70h] BYREF
  __int128 v40; // [rsp+94h] [rbp-6Ch]
  __int128 v41; // [rsp+A4h] [rbp-5Ch]
  int v42; // [rsp+B4h] [rbp-4Ch]
  int v43; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v44[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v30 = a4;
  v31 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v43 = 0;
  memset_0(v44, 0, sizeof(v44));
  v39 = 0;
  v32 = 0;
  v9 = -1;
  v42 = 0;
  v10 = byte_1800AA941;
  v35 = 0;
  v36 = -1;
  v37 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v33 = 0;
  v34 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v32,
      L"VpnikeProcessTsRequest",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v10 = byte_1800AA941;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 && a5 )
  {
    if ( (v10 & 8) != 0 )
    {
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v43, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v43);
    }
    if ( (a2 & 0xFF00000000LL) != 0 )
    {
      *a3 = 0;
      ProcessHeap = GetProcessHeap();
      v12 = (struct _VPN_TRAFFIC_SELECTORS_ *)HeapAlloc(ProcessHeap, 8u, 0x20u);
      *a5 = v12;
      if ( v12 )
      {
        *(_DWORD *)v12 = 0;
        *((_QWORD *)*a5 + 1) = 0;
        *((_DWORD *)*a5 + 4) = 0;
        *((_QWORD *)*a5 + 3) = 0;
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_20;
        v13 = L"NULL  for dummy tunnel";
        v14 = RasVpnIkeTraceInfo;
        goto LABEL_19;
      }
      exception = 8;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v43) = 0;
        FormatRRASErrorString(&v43, L"VPNIKE_MALLOC failed with error %d", 8);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v13 = (const wchar_t *)&v43;
          v14 = RasVpnIkeTraceError;
LABEL_19:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v14, v13);
        }
LABEL_20:
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_75;
      }
    }
    else
    {
      v15 = (struct _RTL_CRITICAL_SECTION *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine
                                                                                          + 1)
                                                                                       + 40LL))(
                                              *((_QWORD *)VpnIkeProtocolEngine + 1),
                                              a2);
      if ( v15 )
        goto LABEL_88;
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"VPNIKE Connection object not yet created. Waiting on sychronizing event");
      exception = WaitOnSynchronizingEvent(a2);
      if ( exception && (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"Wait on synchronizing event failed. ");
      v15 = (struct _RTL_CRITICAL_SECTION *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine
                                                                                          + 1)
                                                                                       + 40LL))(
                                              *((_QWORD *)VpnIkeProtocolEngine + 1),
                                              a2);
      if ( v15 )
      {
LABEL_88:
        if ( *(_DWORD *)(v15[2].SpinCount + 40) == 2 && (exception = WaitOnSynchronizingEvent(a2)) != 0 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v39) = 0;
            SpinCount = v15[2].SpinCount;
            if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
              v9 = *(_DWORD *)(SpinCount + 16);
            ConvertPortNoToString(&v39, v9);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v17 = v15[2].SpinCount;
              LODWORD(v18) = v17 + 2120;
              if ( !v17 )
                v18 = &v38;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)L"Wait on synchronizing event failed. ",
                (_DWORD)v18,
                (v17 + 2686) & -(__int64)(v15[2].SpinCount != 0),
                (__int64)&v39);
            }
          }
        }
        else
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v43) = 0;
            LOWORD(v39) = 0;
            v19 = v15[2].SpinCount;
            if ( v19 && *(_QWORD *)(v19 + 16) )
              v20 = *(unsigned int *)(v19 + 16);
            else
              v20 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v39, v20);
            FormatRRASErrorString(&v43, L"TS Responder: Got playload for TsId [%I64u]", *a3);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v21 = v15[2].SpinCount;
              LODWORD(v22) = v21 + 2120;
              if ( !v21 )
                v22 = &v38;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (unsigned int)&v43,
                (_DWORD)v22,
                (v21 + 2686) & -(__int64)(v15[2].SpinCount != 0),
                (__int64)&v39);
            }
          }
          LogTsPayload(v30);
          EnterCriticalSection(v15 + 4);
          if ( *(_DWORD *)(v15[2].SpinCount + 40) != 2
            || !(unsigned int)VPNIKEServerConnection::IsStopPending(
                                (VPNIKEServerConnection *)v15,
                                (unsigned int *)&exception) )
          {
            v26 = v31;
            exception = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64 *, struct _VPN_TRAFFIC_SELECTORS_ **, struct _VPN_TRAFFIC_SELECTORS_ *))v15->DebugInfo[2].ProcessLocksList.Blink)(
                          v15,
                          2,
                          v31,
                          a5,
                          v30);
            LeaveCriticalSection(v15 + 4);
            BaseConnection::DeleteRef((BaseConnection *)v15);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v27 = *v26;
              LOWORD(v43) = 0;
              FormatRRASErrorString(&v43, L"TS Responder: Respond TS payload with TsId [%I64u]", v27);
              if ( (byte_1800AA941 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v43);
            }
            LogTsPayload(*a5);
            goto LABEL_20;
          }
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v43) = 0;
            LOWORD(v39) = 0;
            v23 = v15[2].SpinCount;
            if ( v23 && *(_QWORD *)(v23 + 16) )
              v9 = *(_DWORD *)(v23 + 16);
            ConvertPortNoToString(&v39, v9);
            FormatRRASErrorString(
              &v43,
              L"Ignoring ProcessTsRequest notfication as DDM has already rejected the tunnel: 0x%I64X",
              a2);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v24 = v15[2].SpinCount;
              LODWORD(v25) = v24 + 2120;
              if ( !v24 )
                v25 = &v38;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v43,
                (_DWORD)v25,
                (v24 + 2686) & -(__int64)(v15[2].SpinCount != 0),
                (__int64)&v39);
            }
          }
          if ( !exception )
            exception = 808;
          LeaveCriticalSection(v15 + 4);
        }
        BaseConnection::DeleteRef((BaseConnection *)v15);
        goto LABEL_20;
      }
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v43) = 0;
        FormatRRASErrorString(&v43, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v43);
      }
      exception = 837;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_76:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d(v8[2], 35, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, (unsigned int)exception);
    RpcRaiseException(exception);
  }
  if ( (v10 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Invalid Parameter");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 87;
LABEL_75:
  if ( exception )
    goto LABEL_76;
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 36, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v32);
  return 0;
}

```

## disassembly

```asm
0x1800551d0  mov     [rsp-8+arg_0], rbx
0x1800551d5  push    rbp
0x1800551d6  push    rsi
0x1800551d7  push    rdi
0x1800551d8  push    r12
0x1800551da  push    r13
0x1800551dc  push    r14
0x1800551de  push    r15
0x1800551e0  lea     rbp, [rsp-7D0h]
0x1800551e8  sub     rsp, 8D0h
0x1800551ef  mov     rax, cs:__security_cookie
0x1800551f6  xor     rax, rsp
0x1800551f9  mov     [rbp+800h+var_40], rax
0x180055200  mov     r15, [rbp+800h+arg_20]
0x180055207  mov     rdi, r9
0x18005520a  mov     [rsp+900h+var_8C8], r9
0x18005520f  mov     r12, r8
0x180055212  mov     [rsp+900h+var_8C0], r8
0x180055217  mov     r14, rdx
0x18005521a  mov     rbx, cs:WPP_GLOBAL_Control
0x180055221  lea     rax, WPP_GLOBAL_Control
0x180055228  cmp     rbx, rax
0x18005522b  jz      short loc_180055258
0x18005522d  test    byte ptr [rbx+1Ch], 1
0x180055231  jz      short loc_180055258
0x180055233  cmp     byte ptr [rbx+19h], 6
0x180055237  jb      short loc_180055258
0x180055239  mov     rcx, [rbx+10h]
0x18005523d  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055244  mov     edx, 22h ; '"'
0x180055249  mov     r9, r14
0x18005524c  call    WPP_SF_q
0x180055251  mov     rbx, cs:WPP_GLOBAL_Control
0x180055258  xor     esi, esi
0x18005525a  lea     rcx, [rbp+800h+var_83C]; void *
0x18005525e  xor     edx, edx; Val
0x180055260  mov     [rsp+900h+exception], esi
0x180055264  mov     r8d, 7FCh; Size
0x18005526a  mov     [rbp+800h+var_840], esi
0x18005526d  call    memset_0
0x180055272  xorps   xmm0, xmm0
0x180055275  mov     [rbp+800h+var_870], esi
0x180055278  xor     eax, eax
0x18005527a  mov     [rsp+900h+var_8B8], rsi
0x18005527f  or      r13d, 0FFFFFFFFh
0x180055283  mov     [rbp+800h+var_84C], eax
0x180055286  mov     al, cs:byte_1800AA941
0x18005528c  xorps   xmm1, xmm1
0x18005528f  mov     [rsp+900h+var_890], rsi
0x180055294  mov     [rsp+900h+var_888], r13d
0x180055299  mov     [rsp+900h+var_884], esi
0x18005529d  movups  [rbp+800h+var_86C], xmm0
0x1800552a1  movups  [rbp+800h+var_85C], xmm0
0x1800552a5  movups  [rbp+800h+var_880], xmm0
0x1800552a9  movdqu  [rsp+900h+var_8B0], xmm1
0x1800552af  movdqu  [rsp+900h+var_8A0], xmm0
0x1800552b5  test    al, 8
0x1800552b7  jz      short loc_1800552E3
0x1800552b9  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800552c0  lea     r8, [rsp+900h+exception]; unsigned int *
0x1800552c5  lea     rdx, aVpnikeprocesst_0; "VpnikeProcessTsRequest"
0x1800552cc  lea     rcx, [rsp+900h+var_8B8]; this
0x1800552d1  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800552d6  mov     al, cs:byte_1800AA941
0x1800552dc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800552e3  test    r14, r14
0x1800552e6  jz      loc_1800557BC
0x1800552ec  test    r12, r12
0x1800552ef  jz      loc_1800557BC
0x1800552f5  test    rdi, rdi
0x1800552f8  jz      loc_1800557BC
0x1800552fe  test    r15, r15
0x180055301  jz      loc_1800557BC
0x180055307  mov     edi, 8
0x18005530c  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055313  xor     ebx, ebx
0x180055315  test    dil, al
0x180055318  jz      short loc_18005534D
0x18005531a  mov     r8, r14
0x18005531d  mov     word ptr [rbp+800h+var_840], bx
0x180055321  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x180055328  lea     rcx, [rbp+800h+var_840]
0x18005532c  call    FormatRRASErrorString
0x180055331  test    cs:byte_1800AA941, dil
0x180055338  jz      short loc_18005534D
0x18005533a  lea     r8, [rbp+800h+var_840]
0x18005533e  mov     rcx, rsi
0x180055341  lea     rdx, RasVpnIkeTraceInfo
0x180055348  call    McTemplateU0z_EventWriteTransfer
0x18005534d  mov     rax, 0FF00000000h
0x180055357  test    rax, r14
0x18005535a  jz      loc_180055406
0x180055360  mov     [r12], rbx
0x180055364  call    cs:__imp_GetProcessHeap
0x18005536a  mov     r8d, 20h ; ' '; dwBytes
0x180055370  mov     edx, edi; dwFlags
0x180055372  mov     rcx, rax; hHeap
0x180055375  call    cs:__imp_HeapAlloc
0x18005537b  mov     [r15], rax
0x18005537e  test    rax, rax
0x180055381  jnz     short loc_1800553D7
0x180055383  mov     [rsp+900h+exception], edi
0x180055387  mov     dil, 4
0x18005538a  test    cs:byte_1800AA941, dil
0x180055391  jz      loc_1800554E3
0x180055397  lea     r8d, [rax+8]
0x18005539b  mov     word ptr [rbp+800h+var_840], bx
0x18005539f  lea     rdx, aVpnikeMallocFa; "VPNIKE_MALLOC failed with error %d"
0x1800553a6  lea     rcx, [rbp+800h+var_840]
0x1800553aa  call    FormatRRASErrorString
0x1800553af  test    cs:byte_1800AA941, dil
0x1800553b6  jz      short loc_1800553CB
0x1800553b8  lea     r8, [rbp+800h+var_840]
0x1800553bc  lea     rdx, RasVpnIkeTraceError
0x1800553c3  mov     rcx, rsi
0x1800553c6  call    McTemplateU0z_EventWriteTransfer
0x1800553cb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800553d2  jmp     loc_1800557E9
0x1800553d7  mov     [rax], ebx
0x1800553d9  mov     rax, [r15]
0x1800553dc  mov     [rax+8], rbx
0x1800553e0  mov     rax, [r15]
0x1800553e3  mov     [rax+10h], ebx
0x1800553e6  mov     rax, [r15]
0x1800553e9  mov     [rax+18h], rbx
0x1800553ed  test    cs:byte_1800AA941, dil
0x1800553f4  jz      short loc_1800553CB
0x1800553f6  lea     r8, aNullForDummyTu; "NULL  for dummy tunnel"
0x1800553fd  lea     rdx, RasVpnIkeTraceInfo
0x180055404  jmp     short loc_1800553C3
0x180055406  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x18005540d  mov     rdx, r14
0x180055410  mov     rcx, [rax+8]
0x180055414  mov     rax, [rcx]
0x180055417  mov     rax, [rax+28h]
0x18005541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055420  mov     rbx, rax
0x180055423  mov     dil, 4
0x180055426  test    rax, rax
0x180055429  jnz     loc_1800554EF
0x18005542f  test    cs:byte_1800AA941, dil
0x180055436  jz      short loc_18005544E
0x180055438  lea     r8, aVpnikeConnecti; "VPNIKE Connection object not yet create"...
0x18005543f  mov     rcx, rsi
0x180055442  lea     rdx, RasVpnIkeTraceError
0x180055449  call    McTemplateU0z_EventWriteTransfer
0x18005544e  mov     rcx, r14
0x180055451  call    WaitOnSynchronizingEvent
0x180055456  mov     [rsp+900h+exception], eax
0x18005545a  test    eax, eax
0x18005545c  jz      short loc_18005547D
0x18005545e  test    cs:byte_1800AA941, dil
0x180055465  jz      short loc_18005547D
0x180055467  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x18005546e  mov     rcx, rsi
0x180055471  lea     rdx, RasVpnIkeTraceError
0x180055478  call    McTemplateU0z_EventWriteTransfer
0x18005547d  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180055484  mov     rdx, r14
0x180055487  mov     rcx, [rax+8]
0x18005548b  mov     rax, [rcx]
0x18005548e  mov     rax, [rax+28h]
0x180055492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055497  mov     rbx, rax
0x18005549a  test    rax, rax
0x18005549d  jnz     short loc_1800554EF
0x18005549f  test    cs:byte_1800AA941, dil
0x1800554a6  jz      short loc_1800554DB
0x1800554a8  mov     r8d, r14d
0x1800554ab  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x1800554b2  lea     rcx, [rbp+800h+var_840]
0x1800554b6  mov     word ptr [rbp+800h+var_840], ax
0x1800554ba  call    FormatRRASErrorString
0x1800554bf  test    cs:byte_1800AA941, dil
0x1800554c6  jz      short loc_1800554DB
0x1800554c8  lea     r8, [rbp+800h+var_840]
0x1800554cc  mov     rcx, rsi
0x1800554cf  lea     rdx, RasVpnIkeTraceError
0x1800554d6  call    McTemplateU0z_EventWriteTransfer
0x1800554db  mov     [rsp+900h+exception], 345h
0x1800554e3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800554ea  jmp     loc_1800557F0
0x1800554ef  mov     rax, [rbx+70h]
0x1800554f3  cmp     dword ptr [rax+28h], 2
0x1800554f7  jnz     loc_1800555A1
0x1800554fd  mov     rcx, r14
0x180055500  call    WaitOnSynchronizingEvent
0x180055505  mov     [rsp+900h+exception], eax
0x180055509  test    eax, eax
0x18005550b  jz      loc_1800555A1
0x180055511  test    cs:byte_1800AA941, dil
0x180055518  jz      short loc_180055594
0x18005551a  xor     eax, eax
0x18005551c  mov     word ptr [rbp+800h+var_870], ax
0x180055520  mov     rax, [rbx+70h]
0x180055524  test    rax, rax
0x180055527  jz      short loc_180055534
0x180055529  cmp     qword ptr [rax+10h], 0
0x18005552e  jz      short loc_180055534
0x180055530  mov     r13d, [rax+10h]
0x180055534  mov     edx, r13d
0x180055537  lea     rcx, [rbp+800h+var_870]
0x18005553b  call    ConvertPortNoToString
0x180055540  test    cs:byte_1800AA941, dil
0x180055547  jz      short loc_180055594
0x180055549  mov     rdx, [rbx+70h]
0x18005554d  mov     rax, rdx
0x180055550  neg     rax
0x180055553  sbb     r8, r8
0x180055556  lea     rcx, [rdx+0A7Eh]
0x18005555d  and     r8, rcx
0x180055560  lea     r9, [rdx+848h]
0x180055567  test    rdx, rdx
0x18005556a  jnz     short loc_180055570
0x18005556c  lea     r9, [rbp+800h+var_880]
0x180055570  lea     rax, [rbp+800h+var_870]
0x180055574  mov     rcx, rsi
0x180055577  mov     [rsp+900h+var_8D8], rax
0x18005557c  lea     rdx, RasVpnIkeParamTraceError
0x180055583  mov     [rsp+900h+var_8E0], r8
0x180055588  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x18005558f  call    McTemplateU0zjzz_EventWriteTransfer
0x180055594  mov     rcx, rbx; this
0x180055597  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18005559c  jmp     loc_1800553CB
0x1800555a1  test    cs:byte_1800AA941, 8
0x1800555a8  jz      loc_18005563E
0x1800555ae  xor     eax, eax
0x1800555b0  mov     word ptr [rbp+800h+var_840], ax
0x1800555b4  mov     word ptr [rbp+800h+var_870], ax
0x1800555b8  mov     rax, [rbx+70h]
0x1800555bc  test    rax, rax
0x1800555bf  jz      short loc_1800555CD
0x1800555c1  cmp     qword ptr [rax+10h], 0
0x1800555c6  jz      short loc_1800555CD
0x1800555c8  mov     edx, [rax+10h]
0x1800555cb  jmp     short loc_1800555D0
0x1800555cd  mov     edx, r13d
0x1800555d0  lea     rcx, [rbp+800h+var_870]
0x1800555d4  call    ConvertPortNoToString
0x1800555d9  mov     r8, [r12]
0x1800555dd  lea     rdx, aTsResponderGot; "TS Responder: Got playload for TsId [%I"...
0x1800555e4  lea     rcx, [rbp+800h+var_840]
0x1800555e8  call    FormatRRASErrorString
0x1800555ed  test    cs:byte_1800AA941, 8
0x1800555f4  jz      short loc_18005563E
0x1800555f6  mov     rdx, [rbx+70h]
0x1800555fa  mov     rax, rdx
0x1800555fd  neg     rax
0x180055600  sbb     r8, r8
0x180055603  lea     rcx, [rdx+0A7Eh]
0x18005560a  and     r8, rcx
0x18005560d  lea     r9, [rdx+848h]
0x180055614  test    rdx, rdx
0x180055617  jnz     short loc_18005561D
0x180055619  lea     r9, [rbp+800h+var_880]
0x18005561d  lea     rax, [rbp+800h+var_870]
0x180055621  mov     rcx, rsi
0x180055624  mov     [rsp+900h+var_8D8], rax
0x180055629  lea     rdx, RasVpnIkeParamTraceInfo
0x180055630  mov     [rsp+900h+var_8E0], r8
0x180055635  lea     r8, [rbp+800h+var_840]
0x180055639  call    McTemplateU0zjzz_EventWriteTransfer
0x18005563e  mov     rcx, [rsp+900h+var_8C8]; struct _VPN_TRAFFIC_SELECTORS_ *
0x180055643  call    ?LogTsPayload@@YAXPEAU_VPN_TRAFFIC_SELECTORS_@@@Z; LogTsPayload(_VPN_TRAFFIC_SELECTORS_ *)
0x180055648  lea     r12, [rbx+0A0h]
0x18005564f  mov     rcx, r12; lpCriticalSection
0x180055652  call    cs:__imp_EnterCriticalSection
0x180055658  mov     rax, [rbx+70h]
0x18005565c  cmp     dword ptr [rax+28h], 2
0x180055660  jnz     loc_180055733
0x180055666  lea     rdx, [rsp+900h+exception]; unsigned int *
0x18005566b  mov     rcx, rbx; this
0x18005566e  call    ?IsStopPending@VPNIKEServerConnection@@QEAAHPEAK@Z; VPNIKEServerConnection::IsStopPending(ulong *)
0x180055673  test    eax, eax
0x180055675  jz      loc_180055733
0x18005567b  test    cs:byte_1800AA941, dil
0x180055682  jz      loc_180055716
0x180055688  xor     eax, eax
0x18005568a  mov     word ptr [rbp+800h+var_840], ax
0x18005568e  mov     word ptr [rbp+800h+var_870], ax
0x180055692  mov     rax, [rbx+70h]
0x180055696  test    rax, rax
0x180055699  jz      short loc_1800556A6
0x18005569b  cmp     qword ptr [rax+10h], 0
0x1800556a0  jz      short loc_1800556A6
0x1800556a2  mov     r13d, [rax+10h]
0x1800556a6  mov     edx, r13d
0x1800556a9  lea     rcx, [rbp+800h+var_870]
0x1800556ad  call    ConvertPortNoToString
0x1800556b2  mov     r8, r14
0x1800556b5  lea     rdx, aIgnoringProces; "Ignoring ProcessTsRequest notfication a"...
0x1800556bc  lea     rcx, [rbp+800h+var_840]
0x1800556c0  call    FormatRRASErrorString
0x1800556c5  test    cs:byte_1800AA941, dil
0x1800556cc  jz      short loc_180055716
0x1800556ce  mov     rdx, [rbx+70h]
0x1800556d2  mov     rax, rdx
0x1800556d5  neg     rax
0x1800556d8  sbb     r8, r8
  ... truncated ...
```
