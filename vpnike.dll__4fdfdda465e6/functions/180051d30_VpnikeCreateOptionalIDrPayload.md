# VpnikeCreateOptionalIDrPayload

- ea: `0x180051d30`
- end: `0x180052297`
- name: `VpnikeCreateOptionalIDrPayload`
- size: `1383`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x180008a7c`
- `0x180051d30`
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

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051fc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052019`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052019`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180052002`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180052002`
- `RPCRT4!RpcRaiseException` at `0x18005222e`
- `RPCRT4!RpcRaiseException` at `0x18005222e`

## string_xrefs

- `0x180051e28`: `VpnikeCreateOptionalIDrPayload`
- `0x1800521cc`: `VpnikeCreateOptionalIDrPayload: Invalid Parameter`
- `0x180051e6f`: `VpnikeCreateOptionalIDrPayload: Tunnel ID: 0x%I64X`
- `0x180051f36`: `VpnikeCreateOptionalIDrPayload: Got Optional IDr playload request for ConnectionId [%d]`
- `0x1800520cb`: `VpnikeCreateOptionalIDrPayload: Unsupported scenario.`
- `0x180052141`: `VpnikeCreateOptionalIDrPayload: Invalid Connection Type: Expecting Client connection with EAP authentication type`
- `0x18005217d`: `VpnikeCreateOptionalIDrPayload: Unable to get VPNIKEConnection handle for ConnectionId: %d`

## pseudocode

```c
__int64 __fastcall VpnikeCreateOptionalIDrPayload(__int64 a1, __int64 a2, _QWORD *a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // r14d
  char v7; // al
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int64 v10; // rcx
  char v11; // cl
  ULONG_PTR SpinCount; // rax
  __int64 v13; // rdx
  ULONG_PTR v14; // rdx
  __int128 *v15; // r9
  __int64 v16; // rdi
  unsigned int v17; // ecx
  ULONG_PTR v18; // rax
  ULONG_PTR v19; // rdx
  __int128 *v20; // r9
  ULONG_PTR v21; // rax
  ULONG_PTR v22; // rdx
  __int128 *v23; // r9
  RPC_STATUS exception; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+7Ch] [rbp-84h]
  __int128 v32; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+90h] [rbp-70h] BYREF
  __int128 v34; // [rsp+94h] [rbp-6Ch]
  __int128 v35; // [rsp+A4h] [rbp-5Ch]
  int v36; // [rsp+B4h] [rbp-4Ch]
  CHAR MultiByteStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v39[2044]; // [rsp+1D4h] [rbp+D4h] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  memset_0(MultiByteStr, 0, 0x101u);
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v6 = -1;
  v33 = 0;
  v36 = 0;
  v26 = 0;
  v29 = 0;
  v31 = 0;
  v7 = byte_1800AA941;
  v30 = -1;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v27 = 0;
  v28 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v26,
      L"VpnikeCreateOptionalIDrPayload",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && !*a3 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, L"VpnikeCreateOptionalIDrPayload: Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v38);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
           *((_QWORD *)VpnIkeProtocolEngine + 1),
           a2);
    v9 = (struct _RTL_CRITICAL_SECTION *)v8;
    if ( !v8 || (v10 = *(_QWORD *)(v8 + 112)) == 0 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(
          &v38,
          L"VpnikeCreateOptionalIDrPayload: Unable to get VPNIKEConnection handle for ConnectionId: %d",
          (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v38);
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      v17 = 837;
      exception = 837;
LABEL_57:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        WPP_SF_d(v5[2], 56, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v17);
        v17 = exception;
      }
      RpcRaiseException(v17);
    }
    if ( *(_DWORD *)(v10 + 40) == 1 && (unsigned int)ConnectionParams::GetAuthenticationType(v10) == 1 )
    {
      v11 = byte_1800AA941;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v38) = 0;
        LOWORD(v33) = 0;
        SpinCount = v9[2].SpinCount;
        if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
          v13 = *(unsigned int *)(SpinCount + 16);
        else
          v13 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v33, v13);
        FormatRRASErrorString(
          &v38,
          L"VpnikeCreateOptionalIDrPayload: Got Optional IDr playload request for ConnectionId [%d]",
          (unsigned int)a2);
        v11 = byte_1800AA941;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v14 = v9[2].SpinCount;
          LODWORD(v15) = v14 + 2120;
          if ( !v14 )
            v15 = &v32;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v38,
            (_DWORD)v15,
            (v14 + 2686) & -(__int64)(v9[2].SpinCount != 0),
            (__int64)&v33);
          v11 = byte_1800AA941;
        }
      }
      if ( *(_DWORD *)(v9[2].SpinCount + 4252) == 1 )
      {
        EnterCriticalSection(v9 + 4);
        v16 = -1;
        WideCharToMultiByte(0, 0x400u, (LPCWCH)(v9[2].SpinCount + 3738), -1, MultiByteStr, 256, 0, 0);
        exception = GetLastError();
        if ( !exception )
        {
          do
            ++v16;
          while ( MultiByteStr[v16] );
          exception = CreateIDObject(2u, v16, MultiByteStr, (__int64)a3);
        }
        LeaveCriticalSection(v9 + 4);
        goto LABEL_29;
      }
      if ( (v11 & 4) != 0 )
      {
        LOWORD(v33) = 0;
        v18 = v9[2].SpinCount;
        if ( v18 && *(_QWORD *)(v18 + 16) )
          v6 = *(_DWORD *)(v18 + 16);
        ConvertPortNoToString(&v33, v6);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v19 = v9[2].SpinCount;
          LODWORD(v20) = v19 + 2120;
          if ( !v19 )
            v20 = &v32;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"VpnikeCreateOptionalIDrPayload: Unsupported scenario.",
            (_DWORD)v20,
            (v19 + 2686) & -(__int64)(v9[2].SpinCount != 0),
            (__int64)&v33);
        }
      }
    }
    else if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v33) = 0;
      v21 = v9[2].SpinCount;
      if ( v21 && *(_QWORD *)(v21 + 16) )
        v6 = *(_DWORD *)(v21 + 16);
      ConvertPortNoToString(&v33, v6);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v22 = v9[2].SpinCount;
        LODWORD(v23) = v22 + 2120;
        if ( !v22 )
          v23 = &v32;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"VpnikeCreateOptionalIDrPayload: Invalid Connection Type: Expecting Client connection with EAP au"
                         "thentication type",
          (_DWORD)v23,
          (v22 + 2686) & -(__int64)(v9[2].SpinCount != 0),
          (__int64)&v33);
      }
    }
    exception = CreateIDObject(0, 0, 0, (__int64)a3);
LABEL_29:
    BaseConnection::DeleteRef((BaseConnection *)v9);
    v17 = exception;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  if ( (v7 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"VpnikeCreateOptionalIDrPayload: Invalid Parameter");
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = 87;
  exception = 87;
LABEL_56:
  if ( v17 )
    goto LABEL_57;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 57, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v26);
  return 0;
}

```

## disassembly

```asm
0x180051d30  mov     [rsp-8+arg_0], rbx
0x180051d35  push    rbp
0x180051d36  push    rsi
0x180051d37  push    rdi
0x180051d38  push    r14
0x180051d3a  push    r15
0x180051d3c  lea     rbp, [rsp-8E0h]
0x180051d44  sub     rsp, 9E0h
0x180051d4b  mov     rax, cs:__security_cookie
0x180051d52  xor     rax, rsp
0x180051d55  mov     [rbp+900h+var_30], rax
0x180051d5c  mov     r15, r8
0x180051d5f  mov     rsi, rdx
0x180051d62  mov     rbx, cs:WPP_GLOBAL_Control
0x180051d69  lea     rax, WPP_GLOBAL_Control
0x180051d70  cmp     rbx, rax
0x180051d73  jz      short loc_180051DA0
0x180051d75  test    byte ptr [rbx+1Ch], 1
0x180051d79  jz      short loc_180051DA0
0x180051d7b  cmp     byte ptr [rbx+19h], 6
0x180051d7f  jb      short loc_180051DA0
0x180051d81  mov     rcx, [rbx+10h]
0x180051d85  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180051d8c  mov     edx, 37h ; '7'
0x180051d91  mov     r9, rsi
0x180051d94  call    WPP_SF_q
0x180051d99  mov     rbx, cs:WPP_GLOBAL_Control
0x180051da0  xor     edx, edx; Val
0x180051da2  mov     [rsp+0A00h+exception], 0
0x180051daa  mov     r8d, 101h; Size
0x180051db0  lea     rcx, [rbp+900h+MultiByteStr]; void *
0x180051db4  call    memset_0
0x180051db9  xor     eax, eax
0x180051dbb  lea     rcx, [rbp+900h+var_82C]; void *
0x180051dc2  xor     edx, edx; Val
0x180051dc4  mov     [rbp+900h+var_830], eax
0x180051dca  mov     r8d, 7FCh; Size
0x180051dd0  call    memset_0
0x180051dd5  xor     eax, eax
0x180051dd7  xorps   xmm0, xmm0
0x180051dda  or      r14d, 0FFFFFFFFh
0x180051dde  mov     [rbp+900h+var_970], eax
0x180051de1  mov     [rbp+900h+var_94C], eax
0x180051de4  xorps   xmm1, xmm1
0x180051de7  mov     [rsp+0A00h+var_9B8], rax
0x180051dec  mov     [rsp+0A00h+var_990], rax
0x180051df1  mov     [rsp+0A00h+var_984], eax
0x180051df5  mov     al, cs:byte_1800AA941
0x180051dfb  mov     [rsp+0A00h+var_988], r14d
0x180051e00  movups  [rbp+900h+var_96C], xmm0
0x180051e04  movups  [rbp+900h+var_95C], xmm0
0x180051e08  movups  [rbp+900h+var_980], xmm0
0x180051e0c  movdqu  [rsp+0A00h+var_9B0], xmm1
0x180051e12  movdqu  [rsp+0A00h+var_9A0], xmm0
0x180051e18  test    al, 8
0x180051e1a  jz      short loc_180051E46
0x180051e1c  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180051e23  lea     r8, [rsp+0A00h+exception]; unsigned int *
0x180051e28  lea     rdx, aVpnikecreateop_3; "VpnikeCreateOptionalIDrPayload"
0x180051e2f  lea     rcx, [rsp+0A00h+var_9B8]; this
0x180051e34  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180051e39  mov     al, cs:byte_1800AA941
0x180051e3f  mov     rbx, cs:WPP_GLOBAL_Control
0x180051e46  test    rsi, rsi
0x180051e49  jz      loc_1800521C8
0x180051e4f  test    r15, r15
0x180051e52  jz      loc_1800521C8
0x180051e58  cmp     qword ptr [r15], 0
0x180051e5c  jnz     loc_1800521C8
0x180051e62  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180051e69  test    al, 8
0x180051e6b  jz      short loc_180051EAB
0x180051e6d  xor     eax, eax
0x180051e6f  lea     rdx, aVpnikecreateop_4; "VpnikeCreateOptionalIDrPayload: Tunnel "...
0x180051e76  mov     r8, rsi
0x180051e79  mov     word ptr [rbp+900h+var_830], ax
0x180051e80  lea     rcx, [rbp+900h+var_830]
0x180051e87  call    FormatRRASErrorString
0x180051e8c  test    cs:byte_1800AA941, 8
0x180051e93  jz      short loc_180051EAB
0x180051e95  lea     r8, [rbp+900h+var_830]
0x180051e9c  mov     rcx, rdi
0x180051e9f  lea     rdx, RasVpnIkeTraceInfo
0x180051ea6  call    McTemplateU0z_EventWriteTransfer
0x180051eab  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180051eb2  mov     rdx, rsi
0x180051eb5  mov     rcx, [rax+8]
0x180051eb9  mov     rax, [rcx]
0x180051ebc  mov     rax, [rax+28h]
0x180051ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ec5  mov     rbx, rax
0x180051ec8  test    rax, rax
0x180051ecb  jz      loc_18005216F
0x180051ed1  mov     rcx, [rax+70h]
0x180051ed5  test    rcx, rcx
0x180051ed8  jz      loc_18005216F
0x180051ede  cmp     dword ptr [rcx+28h], 1
0x180051ee2  jnz     loc_1800520D4
0x180051ee8  call    ?GetAuthenticationType@ConnectionParams@@QEAA?AW4_IKEv2_AUTH_TYPE_@@XZ; ConnectionParams::GetAuthenticationType(void)
0x180051eed  cmp     eax, 1
0x180051ef0  jnz     loc_1800520D4
0x180051ef6  mov     cl, cs:byte_1800AA941
0x180051efc  test    cl, 8
0x180051eff  jz      loc_180051FA5
0x180051f05  xor     eax, eax
0x180051f07  mov     word ptr [rbp+900h+var_830], ax
0x180051f0e  mov     word ptr [rbp+900h+var_970], ax
0x180051f12  mov     rax, [rbx+70h]
0x180051f16  test    rax, rax
0x180051f19  jz      short loc_180051F27
0x180051f1b  cmp     qword ptr [rax+10h], 0
0x180051f20  jz      short loc_180051F27
0x180051f22  mov     edx, [rax+10h]
0x180051f25  jmp     short loc_180051F2A
0x180051f27  mov     edx, r14d
0x180051f2a  lea     rcx, [rbp+900h+var_970]
0x180051f2e  call    ConvertPortNoToString
0x180051f33  mov     r8d, esi
0x180051f36  lea     rdx, aVpnikecreateop_1; "VpnikeCreateOptionalIDrPayload: Got Opt"...
0x180051f3d  lea     rcx, [rbp+900h+var_830]
0x180051f44  call    FormatRRASErrorString
0x180051f49  mov     cl, cs:byte_1800AA941
0x180051f4f  test    cl, 8
0x180051f52  jz      short loc_180051FA5
0x180051f54  mov     rdx, [rbx+70h]
0x180051f58  mov     rax, rdx
0x180051f5b  neg     rax
0x180051f5e  sbb     r8, r8
0x180051f61  lea     rcx, [rdx+0A7Eh]
0x180051f68  and     r8, rcx
0x180051f6b  lea     r9, [rdx+848h]
0x180051f72  test    rdx, rdx
0x180051f75  jnz     short loc_180051F7B
0x180051f77  lea     r9, [rbp+900h+var_980]
0x180051f7b  lea     rax, [rbp+900h+var_970]
0x180051f7f  mov     rcx, rdi
0x180051f82  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x180051f87  lea     rdx, RasVpnIkeParamTraceInfo
0x180051f8e  mov     [rsp+0A00h+lpMultiByteStr], r8
0x180051f93  lea     r8, [rbp+900h+var_830]
0x180051f9a  call    McTemplateU0zjzz_EventWriteTransfer
0x180051f9f  mov     cl, cs:byte_1800AA941
0x180051fa5  mov     rax, [rbx+70h]
0x180051fa9  cmp     dword ptr [rax+109Ch], 1
0x180051fb0  jnz     loc_18005205A
0x180051fb6  lea     rsi, [rbx+0A0h]
0x180051fbd  mov     rcx, rsi; lpCriticalSection
0x180051fc0  call    cs:__imp_EnterCriticalSection
0x180051fc6  mov     r8, [rbx+70h]
0x180051fca  lea     rax, [rbp+900h+MultiByteStr]
0x180051fce  mov     [rsp+0A00h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180051fd7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180051fdb  mov     [rsp+0A00h+lpDefaultChar], 0; lpDefaultChar
0x180051fe4  add     r8, 0E9Ah; lpWideCharStr
0x180051feb  mov     [rsp+0A00h+cbMultiByte], 100h; cbMultiByte
0x180051ff3  mov     r9d, edi; cchWideChar
0x180051ff6  mov     edx, 400h; dwFlags
0x180051ffb  mov     [rsp+0A00h+lpMultiByteStr], rax; lpMultiByteStr
0x180052000  xor     ecx, ecx; CodePage
0x180052002  call    cs:__imp_WideCharToMultiByte
0x180052008  call    cs:__imp_GetLastError
0x18005200e  mov     [rsp+0A00h+exception], eax
0x180052012  test    eax, eax
0x180052014  jz      short loc_180052037
0x180052016  mov     rcx, rsi; lpCriticalSection
0x180052019  call    cs:__imp_LeaveCriticalSection
0x18005201f  mov     rcx, rbx; this
0x180052022  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180052027  mov     ecx, [rsp+0A00h+exception]
0x18005202b  mov     rbx, cs:WPP_GLOBAL_Control
0x180052032  jmp     loc_1800521F6
0x180052037  lea     rax, [rbp+900h+MultiByteStr]
0x18005203b  inc     rdi
0x18005203e  cmp     byte ptr [rax+rdi], 0
0x180052042  jnz     short loc_18005203B
0x180052044  mov     edx, edi
0x180052046  lea     r8, [rbp+900h+MultiByteStr]
0x18005204a  mov     r9, r15
0x18005204d  mov     cl, 2
0x18005204f  call    CreateIDObject
0x180052054  mov     [rsp+0A00h+exception], eax
0x180052058  jmp     short loc_180052016
0x18005205a  test    cl, 4
0x18005205d  jz      loc_180052157
0x180052063  xor     eax, eax
0x180052065  mov     word ptr [rbp+900h+var_970], ax
0x180052069  mov     rax, [rbx+70h]
0x18005206d  test    rax, rax
0x180052070  jz      short loc_18005207D
0x180052072  cmp     qword ptr [rax+10h], 0
0x180052077  jz      short loc_18005207D
0x180052079  mov     r14d, [rax+10h]
0x18005207d  mov     edx, r14d
0x180052080  lea     rcx, [rbp+900h+var_970]
0x180052084  call    ConvertPortNoToString
0x180052089  test    cs:byte_1800AA941, 4
0x180052090  jz      loc_180052157
0x180052096  mov     rdx, [rbx+70h]
0x18005209a  mov     rax, rdx
0x18005209d  neg     rax
0x1800520a0  sbb     r8, r8
0x1800520a3  lea     rcx, [rdx+0A7Eh]
0x1800520aa  and     r8, rcx
0x1800520ad  lea     r9, [rdx+848h]
0x1800520b4  test    rdx, rdx
0x1800520b7  jnz     short loc_1800520BD
0x1800520b9  lea     r9, [rbp+900h+var_980]
0x1800520bd  lea     rax, [rbp+900h+var_970]
0x1800520c1  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x1800520c6  mov     [rsp+0A00h+lpMultiByteStr], r8
0x1800520cb  lea     r8, aVpnikecreateop_5; "VpnikeCreateOptionalIDrPayload: Unsuppo"...
0x1800520d2  jmp     short loc_180052148
0x1800520d4  test    cs:byte_1800AA941, 4
0x1800520db  jz      short loc_180052157
0x1800520dd  xor     eax, eax
0x1800520df  mov     word ptr [rbp+900h+var_970], ax
0x1800520e3  mov     rax, [rbx+70h]
0x1800520e7  test    rax, rax
0x1800520ea  jz      short loc_1800520F7
0x1800520ec  cmp     qword ptr [rax+10h], 0
0x1800520f1  jz      short loc_1800520F7
0x1800520f3  mov     r14d, [rax+10h]
0x1800520f7  mov     edx, r14d
0x1800520fa  lea     rcx, [rbp+900h+var_970]
0x1800520fe  call    ConvertPortNoToString
0x180052103  test    cs:byte_1800AA941, 4
0x18005210a  jz      short loc_180052157
0x18005210c  mov     rdx, [rbx+70h]
0x180052110  mov     rax, rdx
0x180052113  neg     rax
0x180052116  sbb     r8, r8
0x180052119  lea     rcx, [rdx+0A7Eh]
0x180052120  and     r8, rcx
0x180052123  lea     r9, [rdx+848h]
0x18005212a  test    rdx, rdx
0x18005212d  jnz     short loc_180052133
0x18005212f  lea     r9, [rbp+900h+var_980]
0x180052133  lea     rax, [rbp+900h+var_970]
0x180052137  mov     qword ptr [rsp+0A00h+cbMultiByte], rax
0x18005213c  mov     [rsp+0A00h+lpMultiByteStr], r8
0x180052141  lea     r8, aVpnikecreateop_0; "VpnikeCreateOptionalIDrPayload: Invalid"...
0x180052148  lea     rdx, RasVpnIkeParamTraceError
0x18005214f  mov     rcx, rdi
0x180052152  call    McTemplateU0zjzz_EventWriteTransfer
0x180052157  mov     r9, r15
0x18005215a  xor     r8d, r8d
0x18005215d  xor     edx, edx
0x18005215f  xor     ecx, ecx
0x180052161  call    CreateIDObject
0x180052166  mov     [rsp+0A00h+exception], eax
0x18005216a  jmp     loc_18005201F
0x18005216f  test    cs:byte_1800AA941, 4
0x180052176  jz      short loc_1800521B6
0x180052178  xor     eax, eax
0x18005217a  mov     r8d, esi
0x18005217d  lea     rdx, aVpnikecreateop_2; "VpnikeCreateOptionalIDrPayload: Unable "...
0x180052184  mov     word ptr [rbp+900h+var_830], ax
0x18005218b  lea     rcx, [rbp+900h+var_830]
0x180052192  call    FormatRRASErrorString
0x180052197  test    cs:byte_1800AA941, 4
0x18005219e  jz      short loc_1800521B6
0x1800521a0  lea     r8, [rbp+900h+var_830]
0x1800521a7  mov     rcx, rdi
0x1800521aa  lea     rdx, RasVpnIkeTraceError
0x1800521b1  call    McTemplateU0z_EventWriteTransfer
0x1800521b6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800521bd  mov     ecx, 345h
0x1800521c2  mov     [rsp+0A00h+exception], ecx
0x1800521c6  jmp     short loc_1800521FA
0x1800521c8  test    al, 4
0x1800521ca  jz      short loc_1800521ED
0x1800521cc  lea     r8, aVpnikecreateop; "VpnikeCreateOptionalIDrPayload: Invalid"...
0x1800521d3  lea     rdx, RasVpnIkeTraceError
0x1800521da  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800521e1  call    McTemplateU0z_EventWriteTransfer
0x1800521e6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800521ed  mov     ecx, 57h ; 'W'
0x1800521f2  mov     [rsp+0A00h+exception], ecx
0x1800521f6  test    ecx, ecx
0x1800521f8  jz      short loc_180052235
0x1800521fa  lea     rax, WPP_GLOBAL_Control
0x180052201  cmp     rbx, rax
0x180052204  jz      short loc_18005222E
0x180052206  test    byte ptr [rbx+1Ch], 1
0x18005220a  jz      short loc_18005222E
0x18005220c  cmp     byte ptr [rbx+19h], 6
0x180052210  jb      short loc_18005222E
0x180052212  mov     r9d, ecx
0x180052215  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x18005221c  mov     rcx, [rbx+10h]
0x180052220  mov     edx, 38h ; '8'
0x180052225  call    WPP_SF_d
0x18005222a  mov     ecx, [rsp+0A00h+exception]; exception
0x18005222e  call    cs:__imp_RpcRaiseException
0x180052234  int     3; Trap to Debugger
0x180052235  lea     rax, WPP_GLOBAL_Control
0x18005223c  cmp     rbx, rax
0x18005223f  jz      short loc_180052265
0x180052241  test    byte ptr [rbx+1Ch], 1
0x180052245  jz      short loc_180052265
  ... truncated ...
```
