# VpnikeCreateIDPayload

- ea: `0x1800516d0`
- end: `0x180051d24`
- name: `VpnikeCreateIDPayload`
- size: `1620`
- prototype: `__int64 __fastcall(__int64, __int64, struct _IKE_ID_PAYLOAD **)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x180008a7c`
- `0x1800435d0`
- `0x1800516d0`
- `0x18005ad28`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051a04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051a04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051a55`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180051a3e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180051a3e`
- `RPCRT4!RpcRaiseException` at `0x180051cbd`
- `RPCRT4!RpcRaiseException` at `0x180051cbd`

## string_xrefs

- `0x1800517cf`: `VpnikeCreateIDPayload`
- `0x180051c5b`: `VpnikeCreateIDPayload: Invalid Parameter`
- `0x18005181e`: `VpnikeCreateIDPayload: Tunnel ID: 0x%I64X`
- `0x1800518db`: `VpnikeCreateIDPayload: Got IDi playload request for ConnectionId [%d]`
- `0x180051993`: `VpnikeCreateIDPayload: Got IDi Payload for ePDG scenario for ConnectionId [%d]`
- `0x180051ad7`: `VpnikeCreateIDPayload: DID NOT Got IDi Payload for ePDG scenario for ConnectionId [%d]`
- `0x180051bdb`: `VpnikeCreateIDPayload: Invalid Connection Type: Expecting Client connection with EAP authentication type`
- `0x180051c0b`: `VpnikeCreateIDPayload: Unable to get VPNIKEConnection handle for ConnectionId: %d`

## pseudocode

```c
__int64 __fastcall VpnikeCreateIDPayload(__int64 a1, __int64 a2, struct _IKE_ID_PAYLOAD **a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // r14d
  char v7; // al
  __int64 v8; // rax
  __int64 v9; // rdi
  char v10; // cl
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int128 *v17; // r9
  __int64 v18; // rbx
  __int64 v19; // rcx
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  unsigned int v21; // ecx
  RPC_STATUS IDObject; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int128 *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdx
  __int128 *v28; // r9
  RPC_STATUS exception; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h]
  __int128 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+7Ch] [rbp-84h]
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+94h] [rbp-6Ch]
  __int128 v40; // [rsp+A4h] [rbp-5Ch]
  int v41; // [rsp+B4h] [rbp-4Ch]
  CHAR MultiByteStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  int v43; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v44[2044]; // [rsp+1D4h] [rbp+D4h] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  memset_0(MultiByteStr, 0, 0x101u);
  v43 = 0;
  memset_0(v44, 0, sizeof(v44));
  v38 = 0;
  v31 = 0;
  v6 = -1;
  v41 = 0;
  v7 = byte_1800AA941;
  v34 = 0;
  v35 = -1;
  v36 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  v32 = 0;
  v33 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v31,
      L"VpnikeCreateIDPayload",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && !*a3 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v43, L"VpnikeCreateIDPayload: Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v43);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
           *((_QWORD *)VpnIkeProtocolEngine + 1),
           a2);
    v9 = v8;
    if ( !v8 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v43) = 0;
        FormatRRASErrorString(
          &v43,
          L"VpnikeCreateIDPayload: Unable to get VPNIKEConnection handle for ConnectionId: %d",
          (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v43);
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      v21 = 837;
      exception = 837;
LABEL_68:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        WPP_SF_d(v5[2], 59, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v21);
        v21 = exception;
      }
      RpcRaiseException(v21);
    }
    if ( *(_DWORD *)(*(_QWORD *)(v8 + 112) + 40LL) != 1
      || (unsigned int)ConnectionParams::GetAuthenticationType() != 1
      || !*(_QWORD *)(v9 + 120) )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v38) = 0;
        v26 = *(_QWORD *)(v9 + 112);
        if ( v26 && *(_QWORD *)(v26 + 16) )
          v6 = *(_DWORD *)(v26 + 16);
        ConvertPortNoToString(&v38, v6);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v27 = *(_QWORD *)(v9 + 112);
          LODWORD(v28) = v27 + 2120;
          if ( !v27 )
            v28 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"VpnikeCreateIDPayload: Invalid Connection Type: Expecting Client connection with EAP authentication type",
            (_DWORD)v28,
            (v27 + 2686) & -(__int64)(*(_QWORD *)(v9 + 112) != 0),
            (__int64)&v38);
        }
      }
      exception = CreateIDObject(0, 0, 0, a3);
      goto LABEL_38;
    }
    v10 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v43) = 0;
      LOWORD(v38) = 0;
      v11 = *(_QWORD *)(v9 + 112);
      if ( v11 && *(_QWORD *)(v11 + 16) )
        v12 = *(unsigned int *)(v11 + 16);
      else
        v12 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v38, v12);
      FormatRRASErrorString(
        &v43,
        L"VpnikeCreateIDPayload: Got IDi playload request for ConnectionId [%d]",
        (unsigned int)a2);
      v10 = byte_1800AA941;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v13 = *(_QWORD *)(v9 + 112);
        LODWORD(v14) = v13 + 2120;
        if ( !v13 )
          v14 = &v37;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v43,
          (_DWORD)v14,
          (v13 + 2686) & -(__int64)(*(_QWORD *)(v9 + 112) != 0),
          (__int64)&v38);
        v10 = byte_1800AA941;
      }
    }
    if ( *(_DWORD *)(*(_QWORD *)(v9 + 112) + 4252LL) == 1 )
    {
      if ( (v10 & 8) != 0 )
      {
        LOWORD(v43) = 0;
        LOWORD(v38) = 0;
        v15 = *(_QWORD *)(v9 + 112);
        if ( v15 && *(_QWORD *)(v15 + 16) )
          v6 = *(_DWORD *)(v15 + 16);
        ConvertPortNoToString(&v38, v6);
        FormatRRASErrorString(
          &v43,
          L"VpnikeCreateIDPayload: Got IDi Payload for ePDG scenario for ConnectionId [%d]",
          (unsigned int)a2);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v16 = *(_QWORD *)(v9 + 112);
          LODWORD(v17) = v16 + 2120;
          if ( !v16 )
            v17 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v43,
            (_DWORD)v17,
            (v16 + 2686) & -(__int64)(*(_QWORD *)(v9 + 112) != 0),
            (__int64)&v38);
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 160));
      v18 = -1;
      WideCharToMultiByte(0, 0x400u, (LPCWCH)(*(_QWORD *)(v9 + 112) + 3224LL), -1, MultiByteStr, 256, 0, 0);
      exception = GetLastError();
      if ( exception )
      {
        v20 = (struct _RTL_CRITICAL_SECTION *)(v9 + 160);
LABEL_37:
        LeaveCriticalSection(v20);
LABEL_38:
        BaseConnection::DeleteRef((BaseConnection *)v9);
        v21 = exception;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_67;
      }
      do
        ++v18;
      while ( MultiByteStr[v18] );
      LOBYTE(v19) = 3;
      IDObject = CreateIDObject(v19, (unsigned int)v18, MultiByteStr, a3);
      v20 = (struct _RTL_CRITICAL_SECTION *)(v9 + 160);
    }
    else
    {
      if ( (v10 & 8) != 0 )
      {
        LOWORD(v43) = 0;
        LOWORD(v38) = 0;
        v23 = *(_QWORD *)(v9 + 112);
        if ( v23 && *(_QWORD *)(v23 + 16) )
          v6 = *(_DWORD *)(v23 + 16);
        ConvertPortNoToString(&v38, v6);
        FormatRRASErrorString(
          &v43,
          L"VpnikeCreateIDPayload: DID NOT Got IDi Payload for ePDG scenario for ConnectionId [%d]",
          (unsigned int)a2);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v24 = *(_QWORD *)(v9 + 112);
          LODWORD(v25) = v24 + 2120;
          if ( !v24 )
            v25 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v43,
            (_DWORD)v25,
            (v24 + 2686) & -(__int64)(*(_QWORD *)(v9 + 112) != 0),
            (__int64)&v38);
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 160));
      IDObject = ClientEAPAuthHandler::GetIDiPayload(*(ClientEAPAuthHandler **)(v9 + 120), a3);
      v20 = (struct _RTL_CRITICAL_SECTION *)(v9 + 160);
    }
    exception = IDObject;
    goto LABEL_37;
  }
  if ( (v7 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"VpnikeCreateIDPayload: Invalid Parameter");
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v21 = 87;
  exception = 87;
LABEL_67:
  if ( v21 )
    goto LABEL_68;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 60, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v31);
  return 0;
}

```

## disassembly

```asm
0x1800516d0  mov     [rsp-8+arg_0], rbx
0x1800516d5  mov     [rsp-8+arg_18], rsi
0x1800516da  push    rbp
0x1800516db  push    rdi
0x1800516dc  push    r12
0x1800516de  push    r14
0x1800516e0  push    r15
0x1800516e2  lea     rbp, [rsp-8E0h]
0x1800516ea  sub     rsp, 9E0h
0x1800516f1  mov     rax, cs:__security_cookie
0x1800516f8  xor     rax, rsp
0x1800516fb  mov     [rbp+900h+var_30], rax
0x180051702  mov     r15, r8
0x180051705  mov     rsi, rdx
0x180051708  mov     rbx, cs:WPP_GLOBAL_Control
0x18005170f  lea     rdi, WPP_GLOBAL_Control
0x180051716  cmp     rbx, rdi
0x180051719  jz      short loc_180051746
0x18005171b  test    byte ptr [rbx+1Ch], 1
0x18005171f  jz      short loc_180051746
0x180051721  cmp     byte ptr [rbx+19h], 6
0x180051725  jb      short loc_180051746
0x180051727  mov     rcx, [rbx+10h]
0x18005172b  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180051732  mov     edx, 3Ah ; ':'
0x180051737  mov     r9, rsi
0x18005173a  call    WPP_SF_q
0x18005173f  mov     rbx, cs:WPP_GLOBAL_Control
0x180051746  xor     r12d, r12d
0x180051749  lea     rcx, [rbp+900h+MultiByteStr]; void *
0x18005174d  xor     edx, edx; Val
0x18005174f  mov     [rsp+0A00h+exception], r12d
0x180051754  mov     r8d, 101h; Size
0x18005175a  call    memset_0
0x18005175f  xor     edx, edx; Val
0x180051761  mov     [rbp+900h+var_830], r12d
0x180051768  mov     r8d, 7FCh; Size
0x18005176e  lea     rcx, [rbp+900h+var_82C]; void *
0x180051775  call    memset_0
0x18005177a  xorps   xmm0, xmm0
0x18005177d  mov     [rbp+900h+var_970], r12d
0x180051781  xor     eax, eax
0x180051783  mov     [rsp+0A00h+var_9B8], r12
0x180051788  or      r14d, 0FFFFFFFFh
0x18005178c  mov     [rbp+900h+var_94C], eax
0x18005178f  mov     al, cs:byte_1800AA941
0x180051795  xorps   xmm1, xmm1
0x180051798  mov     [rsp+0A00h+var_990], r12
0x18005179d  mov     [rsp+0A00h+var_988], r14d
0x1800517a2  mov     [rsp+0A00h+var_984], r12d
0x1800517a7  movups  [rbp+900h+var_96C], xmm0
0x1800517ab  movups  [rbp+900h+var_95C], xmm0
0x1800517af  movups  [rbp+900h+var_980], xmm0
0x1800517b3  movdqu  [rsp+0A00h+var_9B0], xmm1
0x1800517b9  movdqu  [rsp+0A00h+var_9A0], xmm0
0x1800517bf  test    al, 8
0x1800517c1  jz      short loc_1800517ED
0x1800517c3  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800517ca  lea     r8, [rsp+0A00h+exception]; unsigned int *
0x1800517cf  lea     rdx, aVpnikecreateid; "VpnikeCreateIDPayload"
0x1800517d6  lea     rcx, [rsp+0A00h+var_9B8]; this
0x1800517db  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800517e0  mov     al, cs:byte_1800AA941
0x1800517e6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800517ed  test    rsi, rsi
0x1800517f0  jz      loc_180051C57
0x1800517f6  test    r15, r15
0x1800517f9  jz      loc_180051C57
0x1800517ff  cmp     [r15], r12
0x180051802  jnz     loc_180051C57
0x180051808  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005180f  test    al, 8
0x180051811  jz      short loc_180051850
0x180051813  mov     r8, rsi
0x180051816  mov     word ptr [rbp+900h+var_830], r12w
0x18005181e  lea     rdx, aVpnikecreateid_2; "VpnikeCreateIDPayload: Tunnel ID: 0x%I6"...
0x180051825  lea     rcx, [rbp+900h+var_830]
0x18005182c  call    FormatRRASErrorString
0x180051831  test    cs:byte_1800AA941, 8
0x180051838  jz      short loc_180051850
0x18005183a  lea     r8, [rbp+900h+var_830]
0x180051841  mov     rcx, rbx
0x180051844  lea     rdx, RasVpnIkeTraceInfo
0x18005184b  call    McTemplateU0z_EventWriteTransfer
0x180051850  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180051857  mov     rdx, rsi
0x18005185a  mov     rcx, [rax+8]
0x18005185e  mov     rax, [rcx]
0x180051861  mov     rax, [rax+28h]
0x180051865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005186a  mov     rdi, rax
0x18005186d  test    rax, rax
0x180051870  jz      loc_180051BFF
0x180051876  mov     rcx, [rax+70h]
0x18005187a  cmp     dword ptr [rcx+28h], 1
0x18005187e  jnz     loc_180051B66
0x180051884  call    ?GetAuthenticationType@ConnectionParams@@QEAA?AW4_IKEv2_AUTH_TYPE_@@XZ; ConnectionParams::GetAuthenticationType(void)
0x180051889  cmp     eax, 1
0x18005188c  jnz     loc_180051B66
0x180051892  cmp     [rdi+78h], r12
0x180051896  jz      loc_180051B66
0x18005189c  mov     cl, cs:byte_1800AA941
0x1800518a2  test    cl, 8
0x1800518a5  jz      loc_18005194A
0x1800518ab  mov     word ptr [rbp+900h+var_830], r12w
0x1800518b3  mov     word ptr [rbp+900h+var_970], r12w
0x1800518b8  mov     rax, [rdi+70h]
0x1800518bc  test    rax, rax
0x1800518bf  jz      short loc_1800518CC
0x1800518c1  cmp     [rax+10h], r12
0x1800518c5  jz      short loc_1800518CC
0x1800518c7  mov     edx, [rax+10h]
0x1800518ca  jmp     short loc_1800518CF
0x1800518cc  mov     edx, r14d
0x1800518cf  lea     rcx, [rbp+900h+var_970]
0x1800518d3  call    ConvertPortNoToString
0x1800518d8  mov     r8d, esi
0x1800518db  lea     rdx, aVpnikecreateid_6; "VpnikeCreateIDPayload: Got IDi playload"...
0x1800518e2  lea     rcx, [rbp+900h+var_830]
0x1800518e9  call    FormatRRASErrorString
0x1800518ee  mov     cl, cs:byte_1800AA941
0x1800518f4  test    cl, 8
0x1800518f7  jz      short loc_18005194A
0x1800518f9  mov     rdx, [rdi+70h]
0x1800518fd  mov     rax, rdx
0x180051900  neg     rax
0x180051903  sbb     r8, r8
0x180051906  lea     rcx, [rdx+0A7Eh]
0x18005190d  and     r8, rcx
0x180051910  lea     r9, [rdx+848h]
0x180051917  test    rdx, rdx
0x18005191a  jnz     short loc_180051920
0x18005191c  lea     r9, [rbp+900h+var_980]
0x180051920  lea     rax, [rbp+900h+var_970]
0x180051924  mov     rcx, rbx
0x180051927  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x18005192c  lea     rdx, RasVpnIkeParamTraceInfo
0x180051933  mov     [rsp+0A00h+lpMultiByteStr], r8
0x180051938  lea     r8, [rbp+900h+var_830]
0x18005193f  call    McTemplateU0zjzz_EventWriteTransfer
0x180051944  mov     cl, cs:byte_1800AA941
0x18005194a  mov     rax, [rdi+70h]
0x18005194e  cmp     dword ptr [rax+109Ch], 1
0x180051955  jnz     loc_180051A9F
0x18005195b  test    cl, 8
0x18005195e  jz      loc_1800519FA
0x180051964  mov     word ptr [rbp+900h+var_830], r12w
0x18005196c  mov     word ptr [rbp+900h+var_970], r12w
0x180051971  mov     rax, [rdi+70h]
0x180051975  test    rax, rax
0x180051978  jz      short loc_180051984
0x18005197a  cmp     [rax+10h], r12
0x18005197e  jz      short loc_180051984
0x180051980  mov     r14d, [rax+10h]
0x180051984  mov     edx, r14d
0x180051987  lea     rcx, [rbp+900h+var_970]
0x18005198b  call    ConvertPortNoToString
0x180051990  mov     r8d, esi
0x180051993  lea     rdx, aVpnikecreateid_0; "VpnikeCreateIDPayload: Got IDi Payload "...
0x18005199a  lea     rcx, [rbp+900h+var_830]
0x1800519a1  call    FormatRRASErrorString
0x1800519a6  test    cs:byte_1800AA941, 8
0x1800519ad  jz      short loc_1800519FA
0x1800519af  mov     rdx, [rdi+70h]
0x1800519b3  mov     rax, rdx
0x1800519b6  neg     rax
0x1800519b9  sbb     r8, r8
0x1800519bc  lea     rcx, [rdx+0A7Eh]
0x1800519c3  and     r8, rcx
0x1800519c6  lea     r9, [rdx+848h]
0x1800519cd  test    rdx, rdx
0x1800519d0  jnz     short loc_1800519D6
0x1800519d2  lea     r9, [rbp+900h+var_980]
0x1800519d6  lea     rax, [rbp+900h+var_970]
0x1800519da  mov     rcx, rbx
0x1800519dd  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x1800519e2  lea     rdx, RasVpnIkeParamTraceInfo
0x1800519e9  mov     [rsp+0A00h+lpMultiByteStr], r8
0x1800519ee  lea     r8, [rbp+900h+var_830]
0x1800519f5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800519fa  lea     rsi, [rdi+0A0h]
0x180051a01  mov     rcx, rsi; lpCriticalSection
0x180051a04  call    cs:__imp_EnterCriticalSection
0x180051a0a  mov     r8, [rdi+70h]
0x180051a0e  lea     rax, [rbp+900h+MultiByteStr]
0x180051a12  mov     [rsp+0A00h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180051a17  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051a1b  mov     [rsp+0A00h+lpDefaultChar], r12; lpDefaultChar
0x180051a20  add     r8, 0C98h; lpWideCharStr
0x180051a27  mov     [rsp+0A00h+cbMultiByte], 100h; cbMultiByte
0x180051a2f  mov     r9d, ebx; cchWideChar
0x180051a32  mov     edx, 400h; dwFlags
0x180051a37  mov     [rsp+0A00h+lpMultiByteStr], rax; lpMultiByteStr
0x180051a3c  xor     ecx, ecx; CodePage
0x180051a3e  call    cs:__imp_WideCharToMultiByte
0x180051a44  call    cs:__imp_GetLastError
0x180051a4a  mov     [rsp+0A00h+exception], eax
0x180051a4e  test    eax, eax
0x180051a50  jz      short loc_180051A7A
0x180051a52  mov     rcx, rsi; lpCriticalSection
0x180051a55  call    cs:__imp_LeaveCriticalSection
0x180051a5b  mov     rcx, rdi; this
0x180051a5e  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180051a63  mov     ecx, [rsp+0A00h+exception]
0x180051a67  lea     rdi, WPP_GLOBAL_Control
0x180051a6e  mov     rbx, cs:WPP_GLOBAL_Control
0x180051a75  jmp     loc_180051C85
0x180051a7a  lea     rax, [rbp+900h+MultiByteStr]
0x180051a7e  inc     rbx
0x180051a81  cmp     [rax+rbx], r12b
0x180051a85  jnz     short loc_180051A7E
0x180051a87  mov     edx, ebx
0x180051a89  lea     r8, [rbp+900h+MultiByteStr]
0x180051a8d  mov     r9, r15
0x180051a90  mov     cl, 3
0x180051a92  call    CreateIDObject
0x180051a97  mov     rcx, rsi
0x180051a9a  jmp     loc_180051B5D
0x180051a9f  test    cl, 8
0x180051aa2  jz      loc_180051B3E
0x180051aa8  mov     word ptr [rbp+900h+var_830], r12w
0x180051ab0  mov     word ptr [rbp+900h+var_970], r12w
0x180051ab5  mov     rax, [rdi+70h]
0x180051ab9  test    rax, rax
0x180051abc  jz      short loc_180051AC8
0x180051abe  cmp     [rax+10h], r12
0x180051ac2  jz      short loc_180051AC8
0x180051ac4  mov     r14d, [rax+10h]
0x180051ac8  mov     edx, r14d
0x180051acb  lea     rcx, [rbp+900h+var_970]
0x180051acf  call    ConvertPortNoToString
0x180051ad4  mov     r8d, esi
0x180051ad7  lea     rdx, aVpnikecreateid_1; "VpnikeCreateIDPayload: DID NOT Got IDi "...
0x180051ade  lea     rcx, [rbp+900h+var_830]
0x180051ae5  call    FormatRRASErrorString
0x180051aea  test    cs:byte_1800AA941, 8
0x180051af1  jz      short loc_180051B3E
0x180051af3  mov     rdx, [rdi+70h]
0x180051af7  mov     rax, rdx
0x180051afa  neg     rax
0x180051afd  sbb     r8, r8
0x180051b00  lea     rcx, [rdx+0A7Eh]
0x180051b07  and     r8, rcx
0x180051b0a  lea     r9, [rdx+848h]
0x180051b11  test    rdx, rdx
0x180051b14  jnz     short loc_180051B1A
0x180051b16  lea     r9, [rbp+900h+var_980]
0x180051b1a  lea     rax, [rbp+900h+var_970]
0x180051b1e  mov     rcx, rbx
0x180051b21  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x180051b26  lea     rdx, RasVpnIkeParamTraceInfo
0x180051b2d  mov     [rsp+0A00h+lpMultiByteStr], r8
0x180051b32  lea     r8, [rbp+900h+var_830]
0x180051b39  call    McTemplateU0zjzz_EventWriteTransfer
0x180051b3e  lea     rbx, [rdi+0A0h]
0x180051b45  mov     rcx, rbx; lpCriticalSection
0x180051b48  call    cs:__imp_EnterCriticalSection
0x180051b4e  mov     rcx, [rdi+78h]; this
0x180051b52  mov     rdx, r15; struct _IKE_ID_PAYLOAD **
0x180051b55  call    ?GetIDiPayload@ClientEAPAuthHandler@@QEAAKPEAPEAU_IKE_ID_PAYLOAD@@@Z; ClientEAPAuthHandler::GetIDiPayload(_IKE_ID_PAYLOAD * *)
0x180051b5a  mov     rcx, rbx
0x180051b5d  mov     [rsp+0A00h+exception], eax
0x180051b61  jmp     loc_180051A55
0x180051b66  test    cs:byte_1800AA941, 4
0x180051b6d  jz      short loc_180051BE7
0x180051b6f  mov     word ptr [rbp+900h+var_970], r12w
0x180051b74  mov     rax, [rdi+70h]
0x180051b78  test    rax, rax
0x180051b7b  jz      short loc_180051B87
0x180051b7d  cmp     [rax+10h], r12
0x180051b81  jz      short loc_180051B87
0x180051b83  mov     r14d, [rax+10h]
0x180051b87  mov     edx, r14d
0x180051b8a  lea     rcx, [rbp+900h+var_970]
0x180051b8e  call    ConvertPortNoToString
0x180051b93  test    cs:byte_1800AA941, 4
0x180051b9a  jz      short loc_180051BE7
0x180051b9c  mov     rdx, [rdi+70h]
0x180051ba0  mov     rax, rdx
0x180051ba3  neg     rax
0x180051ba6  sbb     r8, r8
0x180051ba9  lea     rcx, [rdx+0A7Eh]
0x180051bb0  and     r8, rcx
0x180051bb3  lea     r9, [rdx+848h]
0x180051bba  test    rdx, rdx
0x180051bbd  jnz     short loc_180051BC3
0x180051bbf  lea     r9, [rbp+900h+var_980]
0x180051bc3  lea     rax, [rbp+900h+var_970]
0x180051bc7  mov     rcx, rbx
0x180051bca  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x180051bcf  lea     rdx, RasVpnIkeParamTraceError
0x180051bd6  mov     [rsp+0A00h+lpMultiByteStr], r8
0x180051bdb  lea     r8, aVpnikecreateid_4; "VpnikeCreateIDPayload: Invalid Connecti"...
0x180051be2  call    McTemplateU0zjzz_EventWriteTransfer
0x180051be7  mov     r9, r15
0x180051bea  xor     r8d, r8d
0x180051bed  xor     edx, edx
0x180051bef  xor     ecx, ecx
0x180051bf1  call    CreateIDObject
0x180051bf6  mov     [rsp+0A00h+exception], eax
  ... truncated ...
```
