# VpnikeGetServerEapAuthRequestPacket

- ea: `0x180052c90`
- end: `0x180053252`
- name: `VpnikeGetServerEapAuthRequestPacket`
- size: `1474`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x18000a3ec`
- `0x180050774`
- `0x180052c90`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005316f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053198`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005316f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053198`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005318a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005318a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052eec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052f10`
- `RPCRT4!RpcRaiseException` at `0x1800531e3`
- `RPCRT4!RpcRaiseException` at `0x1800531e3`

## string_xrefs

- `0x180052e1d`: `VPNIKE Connection object not yet created. Waiting on sychronizing event`

## pseudocode

```c
__int64 __fastcall VpnikeGetServerEapAuthRequestPacket(__int64 a1, __int64 a2, unsigned int **a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // r13d
  char v7; // al
  BaseConnection *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rdx
  __int128 *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int128 *v17; // r9
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v20; // rbx
  HANDLE v21; // rax
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
  _BYTE v36[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
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
      L"VpnikeGetServerEapAuthRequestPacket",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v35);
    }
    v8 = (BaseConnection *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
                             *((_QWORD *)VpnIkeProtocolEngine + 1),
                             a2);
    if ( !v8 )
    {
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
      v8 = (BaseConnection *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
                               *((_QWORD *)VpnIkeProtocolEngine + 1),
                               a2);
      if ( !v8 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v35);
        }
        v5 = (PVOID *)WPP_GLOBAL_Control;
        exception = 837;
LABEL_58:
        if ( *a3 )
        {
          v18 = (void *)*((_QWORD *)*a3 + 1);
          if ( v18 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v18);
            *((_QWORD *)*a3 + 1) = 0;
          }
          v20 = *a3;
          if ( *a3 )
          {
            v21 = GetProcessHeap();
            HeapFree(v21, 0, v20);
          }
          *a3 = 0;
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
          WPP_SF_d(v5[2], 41, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, (unsigned int)exception);
        RpcRaiseException(exception);
      }
    }
    if ( *(_DWORD *)(*((_QWORD *)v8 + 14) + 40LL) == 2 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)v8 + 4);
      exception = (*(__int64 (__fastcall **)(BaseConnection *, _QWORD, unsigned int **))(*(_QWORD *)v8 + 128LL))(
                    v8,
                    0,
                    a3);
      LeaveCriticalSection((LPCRITICAL_SECTION)v8 + 4);
      if ( exception || !*a3 )
      {
        *((_BYTE *)v8 + 360) = 1;
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v35) = 0;
          LOWORD(v31) = 0;
          v12 = *((_QWORD *)v8 + 14);
          if ( v12 && *(_QWORD *)(v12 + 16) )
            v6 = *(_DWORD *)(v12 + 16);
          ConvertPortNoToString(&v31, v6);
          FormatRRASErrorString(&v35, L"Failed to construct Eap Identity Request. %d", (unsigned int)exception);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v13 = *((_QWORD *)v8 + 14);
            LODWORD(v14) = v13 + 2120;
            if ( !v13 )
              v14 = &v30;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v35,
              (_DWORD)v14,
              (v13 + 2686) & -(__int64)(*((_QWORD *)v8 + 14) != 0),
              (__int64)&v31);
          }
        }
      }
      else
      {
        if ( !**a3 )
          *((_BYTE *)v8 + 360) = 1;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v35) = 0;
          LOWORD(v31) = 0;
          v9 = *((_QWORD *)v8 + 14);
          if ( v9 && *(_QWORD *)(v9 + 16) )
            v6 = *(_DWORD *)(v9 + 16);
          ConvertPortNoToString(&v31, v6);
          FormatRRASErrorString(&v35, L"Get EAP packet: State: %d", **a3);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v10 = *((_QWORD *)v8 + 14);
            LODWORD(v11) = v10 + 2120;
            if ( !v10 )
              v11 = &v30;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v35,
              (_DWORD)v11,
              (v10 + 2686) & -(__int64)(*((_QWORD *)v8 + 14) != 0),
              (__int64)&v31);
          }
        }
        LogEAPAuthPacket(*((struct _EAP_AUTH_PACKET_ **)*a3 + 1));
      }
    }
    else if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v31) = 0;
      v15 = *((_QWORD *)v8 + 14);
      if ( v15 && *(_QWORD *)(v15 + 16) )
        v6 = *(_DWORD *)(v15 + 16);
      ConvertPortNoToString(&v31, v6);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v16 = *((_QWORD *)v8 + 14);
        LODWORD(v17) = v16 + 2120;
        if ( !v16 )
          v17 = &v30;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid Connection Type: Expecting Server connection",
          (_DWORD)v17,
          (v16 + 2686) & -(__int64)(*((_QWORD *)v8 + 14) != 0),
          (__int64)&v31);
      }
    }
    BaseConnection::DeleteRef(v8);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( (v7 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Parameter");
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    exception = 87;
  }
  if ( exception )
    goto LABEL_58;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 42, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v24);
  return 0;
}

```

## disassembly

```asm
0x180052c90  mov     [rsp-8+arg_0], rbx
0x180052c95  mov     [rsp-8+arg_18], rdi
0x180052c9a  push    rbp
0x180052c9b  push    r12
0x180052c9d  push    r13
0x180052c9f  push    r14
0x180052ca1  push    r15
0x180052ca3  lea     rbp, [rsp-7C0h]
0x180052cab  sub     rsp, 8C0h
0x180052cb2  mov     rax, cs:__security_cookie
0x180052cb9  xor     rax, rsp
0x180052cbc  mov     [rbp+7E0h+var_30], rax
0x180052cc3  mov     r12, r8
0x180052cc6  mov     r15, rdx
0x180052cc9  mov     rbx, cs:WPP_GLOBAL_Control
0x180052cd0  lea     rax, WPP_GLOBAL_Control
0x180052cd7  cmp     rbx, rax
0x180052cda  jz      short loc_180052D07
0x180052cdc  test    byte ptr [rbx+1Ch], 1
0x180052ce0  jz      short loc_180052D07
0x180052ce2  cmp     byte ptr [rbx+19h], 6
0x180052ce6  jb      short loc_180052D07
0x180052ce8  mov     rcx, [rbx+10h]
0x180052cec  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180052cf3  mov     edx, 28h ; '('
0x180052cf8  mov     r9, r15
0x180052cfb  call    WPP_SF_q
0x180052d00  mov     rbx, cs:WPP_GLOBAL_Control
0x180052d07  xor     eax, eax
0x180052d09  mov     [rsp+8E0h+exception], 0
0x180052d11  xor     edx, edx; Val
0x180052d13  mov     [rbp+7E0h+var_830], eax
0x180052d16  mov     r8d, 7FCh; Size
0x180052d1c  lea     rcx, [rbp+7E0h+var_82C]; void *
0x180052d20  call    memset_0
0x180052d25  xor     eax, eax
0x180052d27  xorps   xmm0, xmm0
0x180052d2a  or      r13d, 0FFFFFFFFh
0x180052d2e  mov     [rbp+7E0h+var_860], eax
0x180052d31  mov     [rbp+7E0h+var_83C], eax
0x180052d34  mov     dil, 8
0x180052d37  mov     [rsp+8E0h+var_8A8], rax
0x180052d3c  xorps   xmm1, xmm1
0x180052d3f  mov     [rsp+8E0h+var_880], rax
0x180052d44  mov     [rsp+8E0h+var_874], eax
0x180052d48  mov     al, cs:byte_1800AA941
0x180052d4e  mov     [rsp+8E0h+var_878], r13d
0x180052d53  movups  [rbp+7E0h+var_85C], xmm0
0x180052d57  movups  [rbp+7E0h+var_84C], xmm0
0x180052d5b  movups  [rsp+8E0h+var_870], xmm0
0x180052d60  movdqu  [rsp+8E0h+var_8A0], xmm1
0x180052d66  movdqu  [rsp+8E0h+var_890], xmm0
0x180052d6c  test    dil, al
0x180052d6f  jz      short loc_180052D9B
0x180052d71  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180052d78  lea     r8, [rsp+8E0h+exception]; unsigned int *
0x180052d7d  lea     rdx, aVpnikegetserve; "VpnikeGetServerEapAuthRequestPacket"
0x180052d84  lea     rcx, [rsp+8E0h+var_8A8]; this
0x180052d89  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180052d8e  mov     al, cs:byte_1800AA941
0x180052d94  mov     rbx, cs:WPP_GLOBAL_Control
0x180052d9b  test    r15, r15
0x180052d9e  jz      loc_180053117
0x180052da4  test    r12, r12
0x180052da7  jz      loc_180053117
0x180052dad  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180052db4  test    dil, al
0x180052db7  jz      short loc_180052DEE
0x180052db9  xor     eax, eax
0x180052dbb  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x180052dc2  mov     r8, r15
0x180052dc5  mov     word ptr [rbp+7E0h+var_830], ax
0x180052dc9  lea     rcx, [rbp+7E0h+var_830]
0x180052dcd  call    FormatRRASErrorString
0x180052dd2  test    cs:byte_1800AA941, dil
0x180052dd9  jz      short loc_180052DEE
0x180052ddb  lea     r8, [rbp+7E0h+var_830]
0x180052ddf  mov     rcx, r14
0x180052de2  lea     rdx, RasVpnIkeTraceInfo
0x180052de9  call    McTemplateU0z_EventWriteTransfer
0x180052dee  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180052df5  mov     rdx, r15
0x180052df8  mov     rcx, [rax+8]
0x180052dfc  mov     rax, [rcx]
0x180052dff  mov     rax, [rax+28h]
0x180052e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e08  mov     rdi, rax
0x180052e0b  test    rax, rax
0x180052e0e  jnz     loc_180052ED4
0x180052e14  test    cs:byte_1800AA941, 4
0x180052e1b  jz      short loc_180052E33
0x180052e1d  lea     r8, aVpnikeConnecti; "VPNIKE Connection object not yet create"...
0x180052e24  mov     rcx, r14
0x180052e27  lea     rdx, RasVpnIkeTraceError
0x180052e2e  call    McTemplateU0z_EventWriteTransfer
0x180052e33  mov     rcx, r15
0x180052e36  call    WaitOnSynchronizingEvent
0x180052e3b  mov     [rsp+8E0h+exception], eax
0x180052e3f  test    eax, eax
0x180052e41  jz      short loc_180052E62
0x180052e43  test    cs:byte_1800AA941, 4
0x180052e4a  jz      short loc_180052E62
0x180052e4c  lea     r8, aWaitOnSynchron; "Wait on synchronizing event failed. "
0x180052e53  mov     rcx, r14
0x180052e56  lea     rdx, RasVpnIkeTraceError
0x180052e5d  call    McTemplateU0z_EventWriteTransfer
0x180052e62  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180052e69  mov     rdx, r15
0x180052e6c  mov     rcx, [rax+8]
0x180052e70  mov     rax, [rcx]
0x180052e73  mov     rax, [rax+28h]
0x180052e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e7c  mov     rdi, rax
0x180052e7f  test    rax, rax
0x180052e82  jnz     short loc_180052ED4
0x180052e84  test    cs:byte_1800AA941, 4
0x180052e8b  jz      short loc_180052EC0
0x180052e8d  mov     r8d, r15d
0x180052e90  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x180052e97  lea     rcx, [rbp+7E0h+var_830]
0x180052e9b  mov     word ptr [rbp+7E0h+var_830], ax
0x180052e9f  call    FormatRRASErrorString
0x180052ea4  test    cs:byte_1800AA941, 4
0x180052eab  jz      short loc_180052EC0
0x180052ead  lea     r8, [rbp+7E0h+var_830]
0x180052eb1  mov     rcx, r14
0x180052eb4  lea     rdx, RasVpnIkeTraceError
0x180052ebb  call    McTemplateU0z_EventWriteTransfer
0x180052ec0  mov     rbx, cs:WPP_GLOBAL_Control
0x180052ec7  mov     [rsp+8E0h+exception], 345h
0x180052ecf  jmp     loc_18005314F
0x180052ed4  mov     rax, [rdi+70h]
0x180052ed8  cmp     dword ptr [rax+28h], 2
0x180052edc  jnz     loc_180053082
0x180052ee2  lea     rbx, [rdi+0A0h]
0x180052ee9  mov     rcx, rbx; lpCriticalSection
0x180052eec  call    cs:__imp_EnterCriticalSection
0x180052ef2  mov     rax, [rdi]
0x180052ef5  mov     r8, r12
0x180052ef8  xor     edx, edx
0x180052efa  mov     rcx, rdi
0x180052efd  mov     rax, [rax+80h]
0x180052f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f09  mov     rcx, rbx; lpCriticalSection
0x180052f0c  mov     [rsp+8E0h+exception], eax
0x180052f10  call    cs:__imp_LeaveCriticalSection
0x180052f16  xor     ebx, ebx
0x180052f18  cmp     [rsp+8E0h+exception], ebx
0x180052f1c  jnz     loc_180052FE9
0x180052f22  mov     rax, [r12]
0x180052f26  test    rax, rax
0x180052f29  jz      loc_180052FE9
0x180052f2f  cmp     [rax], ebx
0x180052f31  jnz     short loc_180052F3A
0x180052f33  mov     byte ptr [rdi+168h], 1
0x180052f3a  test    cs:byte_1800AA941, 8
0x180052f41  jz      loc_180052FD7
0x180052f47  mov     word ptr [rbp+7E0h+var_830], bx
0x180052f4b  mov     word ptr [rbp+7E0h+var_860], bx
0x180052f4f  mov     rax, [rdi+70h]
0x180052f53  test    rax, rax
0x180052f56  jz      short loc_180052F62
0x180052f58  cmp     [rax+10h], rbx
0x180052f5c  jz      short loc_180052F62
0x180052f5e  mov     r13d, [rax+10h]
0x180052f62  mov     edx, r13d
0x180052f65  lea     rcx, [rbp+7E0h+var_860]
0x180052f69  call    ConvertPortNoToString
0x180052f6e  mov     r8, [r12]
0x180052f72  lea     rdx, aGetEapPacketSt; "Get EAP packet: State: %d"
0x180052f79  lea     rcx, [rbp+7E0h+var_830]
0x180052f7d  mov     r8d, [r8]
0x180052f80  call    FormatRRASErrorString
0x180052f85  test    cs:byte_1800AA941, 8
0x180052f8c  jz      short loc_180052FD7
0x180052f8e  mov     rdx, [rdi+70h]
0x180052f92  mov     rax, rdx
0x180052f95  neg     rax
0x180052f98  sbb     r8, r8
0x180052f9b  lea     rcx, [rdx+0A7Eh]
0x180052fa2  and     r8, rcx
0x180052fa5  lea     r9, [rdx+848h]
0x180052fac  test    rdx, rdx
0x180052faf  jnz     short loc_180052FB6
0x180052fb1  lea     r9, [rsp+8E0h+var_870]
0x180052fb6  lea     rax, [rbp+7E0h+var_860]
0x180052fba  mov     rcx, r14
0x180052fbd  mov     [rsp+8E0h+var_8B8], rax
0x180052fc2  lea     rdx, RasVpnIkeParamTraceInfo
0x180052fc9  mov     [rsp+8E0h+var_8C0], r8
0x180052fce  lea     r8, [rbp+7E0h+var_830]
0x180052fd2  call    McTemplateU0zjzz_EventWriteTransfer
0x180052fd7  mov     rcx, [r12]
0x180052fdb  mov     rcx, [rcx+8]; struct _EAP_AUTH_PACKET_ *
0x180052fdf  call    ?LogEAPAuthPacket@@YAXPEAU_EAP_AUTH_PACKET_@@@Z; LogEAPAuthPacket(_EAP_AUTH_PACKET_ *)
0x180052fe4  jmp     loc_180053106
0x180052fe9  mov     byte ptr [rdi+168h], 1
0x180052ff0  test    cs:byte_1800AA941, 4
0x180052ff7  jz      loc_180053106
0x180052ffd  mov     word ptr [rbp+7E0h+var_830], bx
0x180053001  mov     word ptr [rbp+7E0h+var_860], bx
0x180053005  mov     rax, [rdi+70h]
0x180053009  test    rax, rax
0x18005300c  jz      short loc_180053018
0x18005300e  cmp     [rax+10h], rbx
0x180053012  jz      short loc_180053018
0x180053014  mov     r13d, [rax+10h]
0x180053018  mov     edx, r13d
0x18005301b  lea     rcx, [rbp+7E0h+var_860]
0x18005301f  call    ConvertPortNoToString
0x180053024  mov     r8d, [rsp+8E0h+exception]
0x180053029  lea     rdx, aFailedToConstr; "Failed to construct Eap Identity Reques"...
0x180053030  lea     rcx, [rbp+7E0h+var_830]
0x180053034  call    FormatRRASErrorString
0x180053039  test    cs:byte_1800AA941, 4
0x180053040  jz      loc_180053106
0x180053046  mov     rdx, [rdi+70h]
0x18005304a  mov     rax, rdx
0x18005304d  neg     rax
0x180053050  sbb     r8, r8
0x180053053  lea     rcx, [rdx+0A7Eh]
0x18005305a  and     r8, rcx
0x18005305d  lea     r9, [rdx+848h]
0x180053064  test    rdx, rdx
0x180053067  jnz     short loc_18005306E
0x180053069  lea     r9, [rsp+8E0h+var_870]
0x18005306e  lea     rax, [rbp+7E0h+var_860]
0x180053072  mov     [rsp+8E0h+var_8B8], rax
0x180053077  mov     [rsp+8E0h+var_8C0], r8
0x18005307c  lea     r8, [rbp+7E0h+var_830]
0x180053080  jmp     short loc_1800530F7
0x180053082  test    cs:byte_1800AA941, 4
0x180053089  jz      short loc_180053106
0x18005308b  xor     eax, eax
0x18005308d  mov     word ptr [rbp+7E0h+var_860], ax
0x180053091  mov     rax, [rdi+70h]
0x180053095  test    rax, rax
0x180053098  jz      short loc_1800530A5
0x18005309a  cmp     qword ptr [rax+10h], 0
0x18005309f  jz      short loc_1800530A5
0x1800530a1  mov     r13d, [rax+10h]
0x1800530a5  mov     edx, r13d
0x1800530a8  lea     rcx, [rbp+7E0h+var_860]
0x1800530ac  call    ConvertPortNoToString
0x1800530b1  test    cs:byte_1800AA941, 4
0x1800530b8  jz      short loc_180053106
0x1800530ba  mov     rdx, [rdi+70h]
0x1800530be  mov     rax, rdx
0x1800530c1  neg     rax
0x1800530c4  sbb     r8, r8
0x1800530c7  lea     rcx, [rdx+0A7Eh]
0x1800530ce  and     r8, rcx
0x1800530d1  lea     r9, [rdx+848h]
0x1800530d8  test    rdx, rdx
0x1800530db  jnz     short loc_1800530E2
0x1800530dd  lea     r9, [rsp+8E0h+var_870]
0x1800530e2  lea     rax, [rbp+7E0h+var_860]
0x1800530e6  mov     [rsp+8E0h+var_8B8], rax
0x1800530eb  mov     [rsp+8E0h+var_8C0], r8
0x1800530f0  lea     r8, aInvalidConnect_0; "Invalid Connection Type: Expecting Serv"...
0x1800530f7  lea     rdx, RasVpnIkeParamTraceError
0x1800530fe  mov     rcx, r14
0x180053101  call    McTemplateU0zjzz_EventWriteTransfer
0x180053106  mov     rcx, rdi; this
0x180053109  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18005310e  mov     rbx, cs:WPP_GLOBAL_Control
0x180053115  jmp     short loc_180053144
0x180053117  test    al, 4
0x180053119  jz      short loc_18005313C
0x18005311b  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180053122  lea     rdx, RasVpnIkeTraceError
0x180053129  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180053130  call    McTemplateU0z_EventWriteTransfer
0x180053135  mov     rbx, cs:WPP_GLOBAL_Control
0x18005313c  mov     [rsp+8E0h+exception], 57h ; 'W'
0x180053144  cmp     [rsp+8E0h+exception], 0
0x180053149  jz      loc_1800531EA
0x18005314f  mov     rax, [r12]
0x180053153  test    rax, rax
0x180053156  jz      short loc_1800531AD
0x180053158  mov     rbx, [rax+8]
0x18005315c  test    rbx, rbx
0x18005315f  jz      short loc_180053181
0x180053161  call    cs:__imp_GetProcessHeap
0x180053167  mov     r8, rbx; lpMem
0x18005316a  xor     edx, edx; dwFlags
0x18005316c  mov     rcx, rax; hHeap
0x18005316f  call    cs:__imp_HeapFree
0x180053175  mov     rax, [r12]
0x180053179  mov     qword ptr [rax+8], 0
0x180053181  mov     rbx, [r12]
0x180053185  test    rbx, rbx
0x180053188  jz      short loc_18005319E
0x18005318a  call    cs:__imp_GetProcessHeap
0x180053190  mov     r8, rbx; lpMem
0x180053193  xor     edx, edx; dwFlags
0x180053195  mov     rcx, rax; hHeap
0x180053198  call    cs:__imp_HeapFree
0x18005319e  mov     qword ptr [r12], 0
0x1800531a6  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
