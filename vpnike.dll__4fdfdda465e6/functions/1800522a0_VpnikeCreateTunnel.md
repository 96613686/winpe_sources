# VpnikeCreateTunnel

- ea: `0x1800522a0`
- end: `0x18005276e`
- name: `VpnikeCreateTunnel`
- size: `1230`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x18000a3ec`
- `0x1800239c0`
- `0x1800509f0`
- `0x1800522a0`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052503`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800525de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800525de`
- `RPCRT4!RpcRaiseException` at `0x18005270a`
- `RPCRT4!RpcRaiseException` at `0x18005270a`

## string_xrefs

- `0x180052384`: `VpnikeCreateTunnel`
- `0x180052566`: `Ignoring CreateTunnel notfication as DDM has already rejected the tunnel: 0x%I64X`

## pseudocode

```c
__int64 __fastcall VpnikeCreateTunnel(__int64 a1, __int64 a2, struct _IKETUNNEL_PARAMETERS_ *a3, __int64 a4)
{
  PVOID *v7; // rbx
  unsigned int v8; // r15d
  char v9; // al
  __int16 v10; // cx
  __int64 v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v14; // rdx
  __int128 *v15; // r9
  ULONG_PTR v16; // rax
  ULONG_PTR v17; // rdx
  __int128 *v18; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  RPC_STATUS v20; // eax
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h]
  __int128 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+6Ch] [rbp-94h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+84h] [rbp-7Ch]
  __int128 v32; // [rsp+94h] [rbp-6Ch]
  int v33; // [rsp+A4h] [rbp-5Ch]
  int v34; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v35[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v8 = -1;
  v30 = 0;
  v33 = 0;
  v23 = 0;
  v26 = 0;
  v28 = 0;
  v9 = byte_1800AA941;
  v27 = -1;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v24 = 0;
  v25 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v23,
      L"VpnikeCreateTunnel",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v9 = byte_1800AA941;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    v10 = *(_WORD *)a3;
    if ( *(_WORD *)a3 == *((_WORD *)a3 + 10) && (v10 == 2 || v10 == 23) )
    {
      if ( (v9 & 8) != 0 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"Tunnel ID: 0x%I64X", a2);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v34);
      }
      LogIkeTunnelParams(a3);
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
              *((_QWORD *)VpnIkeProtocolEngine + 1),
              a2);
      v12 = (struct _RTL_CRITICAL_SECTION *)v11;
      if ( v11 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v11 + 112) + 40LL) == 2 && (exception = WaitOnSynchronizingEvent(a2)) != 0 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v30) = 0;
            SpinCount = v12[2].SpinCount;
            if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
              v8 = *(_DWORD *)(SpinCount + 16);
            ConvertPortNoToString(&v30, v8);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v14 = v12[2].SpinCount;
              LODWORD(v15) = v14 + 2120;
              if ( !v14 )
                v15 = &v29;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)L"Wait on synchronizing event failed. ",
                (_DWORD)v15,
                (v14 + 2686) & -(__int64)(v12[2].SpinCount != 0),
                (__int64)&v30);
            }
          }
        }
        else
        {
          EnterCriticalSection(v12 + 4);
          if ( *(_DWORD *)(v12[2].SpinCount + 40) == 2
            && (unsigned int)VPNIKEServerConnection::IsStopPending(
                               (VPNIKEServerConnection *)v12,
                               (unsigned int *)&exception) )
          {
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v34) = 0;
              LOWORD(v30) = 0;
              v16 = v12[2].SpinCount;
              if ( v16 && *(_QWORD *)(v16 + 16) )
                v8 = *(_DWORD *)(v16 + 16);
              ConvertPortNoToString(&v30, v8);
              FormatRRASErrorString(
                &v34,
                L"Ignoring CreateTunnel notfication as DDM has already rejected the tunnel: 0x%I64X",
                a2);
              if ( (byte_1800AA941 & 4) != 0 )
              {
                v17 = v12[2].SpinCount;
                LODWORD(v18) = v17 + 2120;
                if ( !v17 )
                  v18 = &v29;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceError,
                  (unsigned int)&v34,
                  (_DWORD)v18,
                  (v17 + 2686) & -(__int64)(v12[2].SpinCount != 0),
                  (__int64)&v30);
              }
            }
            if ( !exception )
              exception = 808;
          }
          else
          {
            DebugInfo = v12->DebugInfo;
            if ( (a2 & 0xFF00000000LL) != 0 )
              v20 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))DebugInfo[2].CriticalSection)(v12);
            else
              v20 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, struct _IKETUNNEL_PARAMETERS_ *, __int64))&DebugInfo[1].EntryCount)(
                      v12,
                      a3,
                      a4);
            exception = v20;
          }
          LeaveCriticalSection(v12 + 4);
        }
        BaseConnection::DeleteRef((BaseConnection *)v12);
        goto LABEL_50;
      }
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v34);
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      exception = 837;
    }
    else
    {
      exception = 13;
      if ( (v9 & 4) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"Invalid Data: vpnIkeTunnelParams");
LABEL_50:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_54;
      }
    }
LABEL_55:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      WPP_SF_d(v7[2], 11, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, (unsigned int)exception);
    RpcRaiseException(exception);
  }
  if ( (v9 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Invalid Parameter");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 87;
LABEL_54:
  if ( exception )
    goto LABEL_55;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 12, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v23);
  return 0;
}

```

## disassembly

```asm
0x1800522a0  push    rbp
0x1800522a2  push    rbx
0x1800522a3  push    rsi
0x1800522a4  push    rdi
0x1800522a5  push    r12
0x1800522a7  push    r14
0x1800522a9  push    r15
0x1800522ab  lea     rbp, [rsp-7C0h]
0x1800522b3  sub     rsp, 8C0h
0x1800522ba  mov     rax, cs:__security_cookie
0x1800522c1  xor     rax, rsp
0x1800522c4  mov     [rbp+7F0h+var_40], rax
0x1800522cb  mov     r12, r9
0x1800522ce  mov     rsi, r8
0x1800522d1  mov     rdi, rdx
0x1800522d4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800522db  lea     rax, WPP_GLOBAL_Control
0x1800522e2  cmp     rbx, rax
0x1800522e5  jz      short loc_180052312
0x1800522e7  test    byte ptr [rbx+1Ch], 1
0x1800522eb  jz      short loc_180052312
0x1800522ed  cmp     byte ptr [rbx+19h], 6
0x1800522f1  jb      short loc_180052312
0x1800522f3  mov     rcx, [rbx+10h]
0x1800522f7  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800522fe  mov     edx, 0Ah
0x180052303  mov     r9, rdi
0x180052306  call    WPP_SF_q
0x18005230b  mov     rbx, cs:WPP_GLOBAL_Control
0x180052312  xor     eax, eax
0x180052314  mov     [rsp+8F0h+exception], 0
0x18005231c  xor     edx, edx; Val
0x18005231e  mov     [rbp+7F0h+var_840], eax
0x180052321  mov     r8d, 7FCh; Size
0x180052327  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18005232b  call    memset_0
0x180052330  xor     eax, eax
0x180052332  xorps   xmm0, xmm0
0x180052335  or      r15d, 0FFFFFFFFh
0x180052339  mov     [rbp+7F0h+var_870], eax
0x18005233c  mov     [rbp+7F0h+var_84C], eax
0x18005233f  xorps   xmm1, xmm1
0x180052342  mov     [rsp+8F0h+var_8B8], rax
0x180052347  mov     [rsp+8F0h+var_890], rax
0x18005234c  mov     [rsp+8F0h+var_884], eax
0x180052350  mov     al, cs:byte_1800AA941
0x180052356  mov     [rsp+8F0h+var_888], r15d
0x18005235b  movups  [rbp+7F0h+var_86C], xmm0
0x18005235f  movups  [rbp+7F0h+var_85C], xmm0
0x180052363  movups  [rsp+8F0h+var_880], xmm0
0x180052368  movdqu  [rsp+8F0h+var_8B0], xmm1
0x18005236e  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180052374  test    al, 8
0x180052376  jz      short loc_1800523A2
0x180052378  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005237f  lea     r8, [rsp+8F0h+exception]; unsigned int *
0x180052384  lea     rdx, aVpnikecreatetu; "VpnikeCreateTunnel"
0x18005238b  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180052390  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180052395  mov     al, cs:byte_1800AA941
0x18005239b  mov     rbx, cs:WPP_GLOBAL_Control
0x1800523a2  test    rdi, rdi
0x1800523a5  jz      loc_1800526A0
0x1800523ab  test    rsi, rsi
0x1800523ae  jz      loc_1800526A0
0x1800523b4  movzx   ecx, word ptr [rsi]
0x1800523b7  cmp     cx, [rsi+14h]
0x1800523bb  jnz     loc_180052671
0x1800523c1  mov     r14d, 2
0x1800523c7  cmp     cx, r14w
0x1800523cb  jz      short loc_1800523D7
0x1800523cd  cmp     cx, 17h
0x1800523d1  jnz     loc_180052671
0x1800523d7  test    al, 8
0x1800523d9  jz      short loc_180052414
0x1800523db  xor     eax, eax
0x1800523dd  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x1800523e4  mov     r8, rdi
0x1800523e7  mov     word ptr [rbp+7F0h+var_840], ax
0x1800523eb  lea     rcx, [rbp+7F0h+var_840]
0x1800523ef  call    FormatRRASErrorString
0x1800523f4  test    cs:byte_1800AA941, 8
0x1800523fb  jz      short loc_180052414
0x1800523fd  lea     r8, [rbp+7F0h+var_840]
0x180052401  lea     rdx, RasVpnIkeTraceInfo
0x180052408  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005240f  call    McTemplateU0z_EventWriteTransfer
0x180052414  mov     rcx, rsi; struct _IKETUNNEL_PARAMETERS_ *
0x180052417  call    ?LogIkeTunnelParams@@YAXPEAU_IKETUNNEL_PARAMETERS_@@@Z; LogIkeTunnelParams(_IKETUNNEL_PARAMETERS_ *)
0x18005241c  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180052423  mov     rdx, rdi
0x180052426  mov     rcx, [rax+8]
0x18005242a  mov     rax, [rcx]
0x18005242d  mov     rax, [rax+28h]
0x180052431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052436  mov     rbx, rax
0x180052439  test    rax, rax
0x18005243c  jz      loc_18005261E
0x180052442  mov     rcx, [rax+70h]
0x180052446  cmp     [rcx+28h], r14d
0x18005244a  jnz     loc_1800524F9
0x180052450  mov     rcx, rdi
0x180052453  call    WaitOnSynchronizingEvent
0x180052458  mov     [rsp+8F0h+exception], eax
0x18005245c  test    eax, eax
0x18005245e  jz      loc_1800524F9
0x180052464  test    cs:byte_1800AA941, 4
0x18005246b  jz      short loc_1800524EC
0x18005246d  xor     eax, eax
0x18005246f  mov     word ptr [rbp+7F0h+var_870], ax
0x180052473  mov     rax, [rbx+70h]
0x180052477  test    rax, rax
0x18005247a  jz      short loc_180052487
0x18005247c  cmp     qword ptr [rax+10h], 0
0x180052481  jz      short loc_180052487
0x180052483  mov     r15d, [rax+10h]
0x180052487  mov     edx, r15d
0x18005248a  lea     rcx, [rbp+7F0h+var_870]
0x18005248e  call    ConvertPortNoToString
0x180052493  test    cs:byte_1800AA941, 4
0x18005249a  jz      short loc_1800524EC
0x18005249c  mov     rdx, [rbx+70h]
0x1800524a0  mov     rax, rdx
0x1800524a3  neg     rax
0x1800524a6  sbb     r8, r8
0x1800524a9  lea     rcx, [rdx+0A7Eh]
0x1800524b0  and     r8, rcx
0x1800524b3  lea     r9, [rdx+848h]
0x1800524ba  test    rdx, rdx
0x1800524bd  jnz     short loc_1800524C4
0x1800524bf  lea     r9, [rsp+8F0h+var_880]
0x1800524c4  lea     rax, [rbp+7F0h+var_870]
0x1800524c8  mov     [rsp+8F0h+var_8C8], rax
0x1800524cd  lea     rdx, RasVpnIkeParamTraceError
0x1800524d4  mov     [rsp+8F0h+var_8D0], r8
0x1800524d9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800524e0  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x1800524e7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800524ec  mov     rcx, rbx; this
0x1800524ef  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800524f4  jmp     loc_180052697
0x1800524f9  lea     r14, [rbx+0A0h]
0x180052500  mov     rcx, r14; lpCriticalSection
0x180052503  call    cs:__imp_EnterCriticalSection
0x180052509  mov     rax, [rbx+70h]
0x18005250d  cmp     dword ptr [rax+28h], 2
0x180052511  jnz     loc_1800525E9
0x180052517  lea     rdx, [rsp+8F0h+exception]; unsigned int *
0x18005251c  mov     rcx, rbx; this
0x18005251f  call    ?IsStopPending@VPNIKEServerConnection@@QEAAHPEAK@Z; VPNIKEServerConnection::IsStopPending(ulong *)
0x180052524  test    eax, eax
0x180052526  jz      loc_1800525E9
0x18005252c  test    cs:byte_1800AA941, 4
0x180052533  jz      loc_1800525CC
0x180052539  xor     eax, eax
0x18005253b  mov     word ptr [rbp+7F0h+var_840], ax
0x18005253f  mov     word ptr [rbp+7F0h+var_870], ax
0x180052543  mov     rax, [rbx+70h]
0x180052547  test    rax, rax
0x18005254a  jz      short loc_180052557
0x18005254c  cmp     qword ptr [rax+10h], 0
0x180052551  jz      short loc_180052557
0x180052553  mov     r15d, [rax+10h]
0x180052557  mov     edx, r15d
0x18005255a  lea     rcx, [rbp+7F0h+var_870]
0x18005255e  call    ConvertPortNoToString
0x180052563  mov     r8, rdi
0x180052566  lea     rdx, aIgnoringCreate; "Ignoring CreateTunnel notfication as DD"...
0x18005256d  lea     rcx, [rbp+7F0h+var_840]
0x180052571  call    FormatRRASErrorString
0x180052576  test    cs:byte_1800AA941, 4
0x18005257d  jz      short loc_1800525CC
0x18005257f  mov     rdx, [rbx+70h]
0x180052583  mov     rax, rdx
0x180052586  neg     rax
0x180052589  sbb     r8, r8
0x18005258c  lea     rcx, [rdx+0A7Eh]
0x180052593  and     r8, rcx
0x180052596  lea     r9, [rdx+848h]
0x18005259d  test    rdx, rdx
0x1800525a0  jnz     short loc_1800525A7
0x1800525a2  lea     r9, [rsp+8F0h+var_880]
0x1800525a7  lea     rax, [rbp+7F0h+var_870]
0x1800525ab  mov     [rsp+8F0h+var_8C8], rax
0x1800525b0  lea     rdx, RasVpnIkeParamTraceError
0x1800525b7  mov     [rsp+8F0h+var_8D0], r8
0x1800525bc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800525c3  lea     r8, [rbp+7F0h+var_840]
0x1800525c7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800525cc  cmp     [rsp+8F0h+exception], 0
0x1800525d1  jnz     short loc_1800525DB
0x1800525d3  mov     [rsp+8F0h+exception], 328h
0x1800525db  mov     rcx, r14; lpCriticalSection
0x1800525de  call    cs:__imp_LeaveCriticalSection
0x1800525e4  jmp     loc_1800524EC
0x1800525e9  mov     rax, [rbx]
0x1800525ec  mov     rcx, 0FF00000000h
0x1800525f6  test    rcx, rdi
0x1800525f9  mov     rcx, rbx
0x1800525fc  jz      short loc_180052609
0x1800525fe  mov     rax, [rax+68h]
0x180052602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052607  jmp     short loc_180052618
0x180052609  mov     rax, [rax+50h]
0x18005260d  mov     r8, r12
0x180052610  mov     rdx, rsi
0x180052613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052618  mov     [rsp+8F0h+exception], eax
0x18005261c  jmp     short loc_1800525DB
0x18005261e  test    cs:byte_1800AA941, 4
0x180052625  jz      short loc_180052660
0x180052627  xor     eax, eax
0x180052629  mov     r8d, edi
0x18005262c  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x180052633  mov     word ptr [rbp+7F0h+var_840], ax
0x180052637  lea     rcx, [rbp+7F0h+var_840]
0x18005263b  call    FormatRRASErrorString
0x180052640  test    cs:byte_1800AA941, 4
0x180052647  jz      short loc_180052660
0x180052649  lea     r8, [rbp+7F0h+var_840]
0x18005264d  lea     rdx, RasVpnIkeTraceError
0x180052654  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005265b  call    McTemplateU0z_EventWriteTransfer
0x180052660  mov     rbx, cs:WPP_GLOBAL_Control
0x180052667  mov     [rsp+8F0h+exception], 345h
0x18005266f  jmp     short loc_1800526D4
0x180052671  mov     [rsp+8F0h+exception], 0Dh
0x180052679  test    al, 4
0x18005267b  jz      short loc_1800526D4
0x18005267d  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x180052684  lea     rdx, RasVpnIkeTraceError
0x18005268b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180052692  call    McTemplateU0z_EventWriteTransfer
0x180052697  mov     rbx, cs:WPP_GLOBAL_Control
0x18005269e  jmp     short loc_1800526CD
0x1800526a0  test    al, 4
0x1800526a2  jz      short loc_1800526C5
0x1800526a4  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x1800526ab  lea     rdx, RasVpnIkeTraceError
0x1800526b2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800526b9  call    McTemplateU0z_EventWriteTransfer
0x1800526be  mov     rbx, cs:WPP_GLOBAL_Control
0x1800526c5  mov     [rsp+8F0h+exception], 57h ; 'W'
0x1800526cd  cmp     [rsp+8F0h+exception], 0
0x1800526d2  jz      short loc_180052711
0x1800526d4  lea     rax, WPP_GLOBAL_Control
0x1800526db  cmp     rbx, rax
0x1800526de  jz      short loc_180052706
0x1800526e0  test    byte ptr [rbx+1Ch], 1
0x1800526e4  jz      short loc_180052706
0x1800526e6  cmp     byte ptr [rbx+19h], 6
0x1800526ea  jb      short loc_180052706
0x1800526ec  mov     r9d, [rsp+8F0h+exception]
0x1800526f1  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800526f8  mov     rcx, [rbx+10h]
0x1800526fc  mov     edx, 0Bh
0x180052701  call    WPP_SF_d
0x180052706  mov     ecx, [rsp+8F0h+exception]; exception
0x18005270a  call    cs:__imp_RpcRaiseException
0x180052710  int     3; Trap to Debugger
0x180052711  lea     rax, WPP_GLOBAL_Control
0x180052718  cmp     rbx, rax
0x18005271b  jz      short loc_180052741
0x18005271d  test    byte ptr [rbx+1Ch], 1
0x180052721  jz      short loc_180052741
0x180052723  cmp     byte ptr [rbx+19h], 6
0x180052727  jb      short loc_180052741
0x180052729  mov     rcx, [rbx+10h]
0x18005272d  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180052734  mov     edx, 0Ch
0x180052739  xor     r9d, r9d
0x18005273c  call    WPP_SF_d
0x180052741  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180052746  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005274b  xor     eax, eax
0x18005274d  mov     rcx, [rbp+7F0h+var_40]
0x180052754  xor     rcx, rsp; StackCookie
0x180052757  call    __security_check_cookie
0x18005275c  add     rsp, 8C0h
0x180052763  pop     r15
0x180052765  pop     r14
0x180052767  pop     r12
0x180052769  pop     rdi
0x18005276a  pop     rsi
0x18005276b  pop     rbx
0x18005276c  pop     rbp
0x18005276d  retn
```
