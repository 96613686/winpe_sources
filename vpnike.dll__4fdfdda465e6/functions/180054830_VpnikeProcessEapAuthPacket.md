# VpnikeProcessEapAuthPacket

- ea: `0x180054830`
- end: `0x180054e16`
- name: `VpnikeProcessEapAuthPacket`
- size: `1510`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, __int64, __int64, struct _EAP_AUTH_PACKET_ *, unsigned int **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180007a0c`
- `0x180050774`
- `0x180054830`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054d08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054d08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054cfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054cfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a83`
- `RPCRT4!RpcRaiseException` at `0x180054d52`
- `RPCRT4!RpcRaiseException` at `0x180054d52`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180054d61`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180054d61`

## string_xrefs

- `0x180054d76`: `RpcAsyncCompleteCall failed: %d`

## pseudocode

```c
__int64 __fastcall VpnikeProcessEapAuthPacket(
        struct _RPC_ASYNC_STATE *a1,
        __int64 a2,
        __int64 a3,
        struct _EAP_AUTH_PACKET_ *a4,
        unsigned int **a5)
{
  struct _RPC_ASYNC_STATE *v7; // rdi
  PVOID *v8; // rbx
  unsigned int v9; // r13d
  char v10; // al
  __int64 v11; // rax
  BaseConnection *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int128 *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  __int128 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  __int128 *v22; // r9
  void *v23; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v25; // rbx
  HANDLE v26; // rax
  unsigned int v27; // eax
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+38h] [rbp-C8h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+48h] [rbp-B8h]
  __int128 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+74h] [rbp-8Ch]
  __int128 v37; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+88h] [rbp-78h] BYREF
  __int128 v39; // [rsp+8Ch] [rbp-74h]
  __int128 v40; // [rsp+9Ch] [rbp-64h]
  int v41; // [rsp+ACh] [rbp-54h]
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v43[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  pAsync = a1;
  v7 = a1;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v38 = 0;
  v31 = 0;
  v9 = -1;
  v41 = 0;
  v10 = byte_1800AA941;
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
      L"VpnikeProcessEapAuthPacket",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v10 = byte_1800AA941;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 && a4 && a5 )
  {
    if ( (v10 & 8) != 0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Tunnel ID: 0x%I64X", a3);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v42);
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
            *((_QWORD *)VpnIkeProtocolEngine + 1),
            a3);
    v12 = (BaseConnection *)v11;
    if ( !v11 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a3);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v42);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
      exception = 837;
LABEL_56:
      if ( *a5 )
      {
        v23 = (void *)*((_QWORD *)*a5 + 1);
        if ( v23 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v23);
          *((_QWORD *)*a5 + 1) = 0;
        }
        v25 = *a5;
        if ( *a5 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v25);
        }
        *a5 = 0;
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
        WPP_SF_d(v8[2], 44, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, (unsigned int)exception);
      RpcRaiseException(exception);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v38) = 0;
      v13 = *(_QWORD *)(v11 + 112);
      if ( v13 && *(_QWORD *)(v13 + 16) )
        v14 = *(unsigned int *)(v13 + 16);
      else
        v14 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v38, v14);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v15 = *((_QWORD *)v12 + 14);
        LODWORD(v16) = v15 + 2120;
        if ( !v15 )
          v16 = &v37;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Processing EAP packet",
          (_DWORD)v16,
          (v15 + 2686) & -(__int64)(*((_QWORD *)v12 + 14) != 0),
          (__int64)&v38);
      }
    }
    LogEAPAuthPacket(a4);
    EnterCriticalSection((LPCRITICAL_SECTION)v12 + 4);
    exception = (*(__int64 (__fastcall **)(BaseConnection *, struct _EAP_AUTH_PACKET_ *, unsigned int **))(*(_QWORD *)v12 + 128LL))(
                  v12,
                  a4,
                  a5);
    LeaveCriticalSection((LPCRITICAL_SECTION)v12 + 4);
    if ( exception || !*a5 )
    {
      if ( *(_DWORD *)(*((_QWORD *)v12 + 14) + 40LL) == 2 )
        *((_BYTE *)v12 + 360) = 1;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        v20 = *((_QWORD *)v12 + 14);
        if ( v20 && *(_QWORD *)(v20 + 16) )
          v9 = *(_DWORD *)(v20 + 16);
        ConvertPortNoToString(&v38, v9);
        FormatRRASErrorString(&v42, L"Failed to process EAP packet. %d", (unsigned int)exception);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v21 = *((_QWORD *)v12 + 14);
          LODWORD(v22) = v21 + 2120;
          if ( !v21 )
            v22 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v42,
            (_DWORD)v22,
            (v21 + 2686) & -(__int64)(*((_QWORD *)v12 + 14) != 0),
            (__int64)&v38);
        }
      }
    }
    else
    {
      if ( *(_DWORD *)(*((_QWORD *)v12 + 14) + 40LL) == 2 && !**a5 )
        *((_BYTE *)v12 + 360) = 1;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        v17 = *((_QWORD *)v12 + 14);
        if ( v17 && *(_QWORD *)(v17 + 16) )
          v9 = *(_DWORD *)(v17 + 16);
        ConvertPortNoToString(&v38, v9);
        FormatRRASErrorString(&v42, L"Processing EAP packet: State: %d", **a5);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v18 = *((_QWORD *)v12 + 14);
          LODWORD(v19) = v18 + 2120;
          if ( !v18 )
            v19 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v42,
            (_DWORD)v19,
            (v18 + 2686) & -(__int64)(*((_QWORD *)v12 + 14) != 0),
            (__int64)&v38);
        }
      }
      LogEAPAuthPacket(*((struct _EAP_AUTH_PACKET_ **)*a5 + 1));
    }
    BaseConnection::DeleteRef(v12);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v7 = pAsync;
  }
  else
  {
    if ( (v10 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"Invalid Parameter");
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    exception = 87;
  }
  if ( exception )
    goto LABEL_56;
  v27 = RpcAsyncCompleteCall(v7, &exception);
  if ( v27 )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"RpcAsyncCompleteCall failed: %d", v27);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v42);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v31);
  return 0;
}

```

## disassembly

```asm
0x180054830  mov     [rsp-8+arg_8], rbx
0x180054835  push    rbp
0x180054836  push    rsi
0x180054837  push    rdi
0x180054838  push    r12
0x18005483a  push    r13
0x18005483c  push    r14
0x18005483e  push    r15
0x180054840  lea     rbp, [rsp-7C0h]
0x180054848  sub     rsp, 8C0h
0x18005484f  mov     rax, cs:__security_cookie
0x180054856  xor     rax, rsp
0x180054859  mov     [rbp+7F0h+var_40], rax
0x180054860  mov     r15, [rbp+7F0h+arg_20]
0x180054867  mov     rsi, r9
0x18005486a  mov     r14, r8
0x18005486d  mov     [rsp+8F0h+pAsync], rcx
0x180054872  mov     rdi, rcx
0x180054875  mov     rbx, cs:WPP_GLOBAL_Control
0x18005487c  lea     rax, WPP_GLOBAL_Control
0x180054883  cmp     rbx, rax
0x180054886  jz      short loc_1800548B3
0x180054888  test    byte ptr [rbx+1Ch], 1
0x18005488c  jz      short loc_1800548B3
0x18005488e  cmp     byte ptr [rbx+19h], 6
0x180054892  jb      short loc_1800548B3
0x180054894  mov     rcx, [rbx+10h]
0x180054898  mov     r9, r8
0x18005489b  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800548a2  mov     edx, 2Bh ; '+'
0x1800548a7  call    WPP_SF_q
0x1800548ac  mov     rbx, cs:WPP_GLOBAL_Control
0x1800548b3  xor     r12d, r12d
0x1800548b6  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800548ba  xor     edx, edx; Val
0x1800548bc  mov     [rsp+8F0h+exception], r12d
0x1800548c1  mov     r8d, 7FCh; Size
0x1800548c7  mov     [rbp+7F0h+var_840], r12d
0x1800548cb  call    memset_0
0x1800548d0  xorps   xmm0, xmm0
0x1800548d3  mov     [rbp+7F0h+var_868], r12d
0x1800548d7  xor     eax, eax
0x1800548d9  mov     [rsp+8F0h+var_8B0], r12
0x1800548de  or      r13d, 0FFFFFFFFh
0x1800548e2  mov     [rbp+7F0h+var_844], eax
0x1800548e5  mov     al, cs:byte_1800AA941
0x1800548eb  xorps   xmm1, xmm1
0x1800548ee  mov     [rsp+8F0h+var_888], r12
0x1800548f3  mov     [rsp+8F0h+var_880], r13d
0x1800548f8  mov     [rsp+8F0h+var_87C], r12d
0x1800548fd  movups  [rbp+7F0h+var_864], xmm0
0x180054901  movups  [rbp+7F0h+var_854], xmm0
0x180054905  movups  [rsp+8F0h+var_878], xmm0
0x18005490a  movdqu  [rsp+8F0h+var_8A8], xmm1
0x180054910  movdqu  [rsp+8F0h+var_898], xmm0
0x180054916  test    al, 8
0x180054918  jz      short loc_180054944
0x18005491a  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180054921  lea     r8, [rsp+8F0h+exception]; unsigned int *
0x180054926  lea     rdx, aVpnikeprocesse; "VpnikeProcessEapAuthPacket"
0x18005492d  lea     rcx, [rsp+8F0h+var_8B0]; this
0x180054932  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180054937  mov     al, cs:byte_1800AA941
0x18005493d  mov     rbx, cs:WPP_GLOBAL_Control
0x180054944  test    r14, r14
0x180054947  jz      loc_180054C83
0x18005494d  test    rsi, rsi
0x180054950  jz      loc_180054C83
0x180054956  test    r15, r15
0x180054959  jz      loc_180054C83
0x18005495f  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180054966  test    al, 8
0x180054968  jz      short loc_18005499F
0x18005496a  xor     eax, eax
0x18005496c  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x180054973  mov     r8, r14
0x180054976  mov     word ptr [rbp+7F0h+var_840], ax
0x18005497a  lea     rcx, [rbp+7F0h+var_840]
0x18005497e  call    FormatRRASErrorString
0x180054983  test    cs:byte_1800AA941, 8
0x18005498a  jz      short loc_18005499F
0x18005498c  lea     r8, [rbp+7F0h+var_840]
0x180054990  mov     rcx, r12
0x180054993  lea     rdx, RasVpnIkeTraceInfo
0x18005499a  call    McTemplateU0z_EventWriteTransfer
0x18005499f  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800549a6  mov     rdx, r14
0x1800549a9  mov     rcx, [rax+8]
0x1800549ad  mov     rax, [rcx]
0x1800549b0  mov     rax, [rax+28h]
0x1800549b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549b9  mov     rdi, rax
0x1800549bc  test    rax, rax
0x1800549bf  jz      loc_180054C31
0x1800549c5  mov     r14b, 8
0x1800549c8  test    cs:byte_1800AA941, r14b
0x1800549cf  jz      short loc_180054A4C
0x1800549d1  xor     ecx, ecx
0x1800549d3  mov     word ptr [rbp+7F0h+var_868], cx
0x1800549d7  mov     rax, [rax+70h]
0x1800549db  test    rax, rax
0x1800549de  jz      short loc_1800549EB
0x1800549e0  cmp     [rax+10h], rcx
0x1800549e4  jz      short loc_1800549EB
0x1800549e6  mov     edx, [rax+10h]
0x1800549e9  jmp     short loc_1800549EE
0x1800549eb  mov     edx, r13d
0x1800549ee  lea     rcx, [rbp+7F0h+var_868]
0x1800549f2  call    ConvertPortNoToString
0x1800549f7  test    cs:byte_1800AA941, r14b
0x1800549fe  jz      short loc_180054A4C
0x180054a00  mov     rdx, [rdi+70h]
0x180054a04  mov     rax, rdx
0x180054a07  neg     rax
0x180054a0a  sbb     r8, r8
0x180054a0d  lea     rcx, [rdx+0A7Eh]
0x180054a14  and     r8, rcx
0x180054a17  lea     r9, [rdx+848h]
0x180054a1e  test    rdx, rdx
0x180054a21  jnz     short loc_180054A28
0x180054a23  lea     r9, [rsp+8F0h+var_878]
0x180054a28  lea     rax, [rbp+7F0h+var_868]
0x180054a2c  mov     rcx, r12
0x180054a2f  mov     [rsp+8F0h+var_8C8], rax
0x180054a34  lea     rdx, RasVpnIkeParamTraceInfo
0x180054a3b  mov     [rsp+8F0h+var_8D0], r8
0x180054a40  lea     r8, aProcessingEapP_0; "Processing EAP packet"
0x180054a47  call    McTemplateU0zjzz_EventWriteTransfer
0x180054a4c  mov     rcx, rsi; struct _EAP_AUTH_PACKET_ *
0x180054a4f  call    ?LogEAPAuthPacket@@YAXPEAU_EAP_AUTH_PACKET_@@@Z; LogEAPAuthPacket(_EAP_AUTH_PACKET_ *)
0x180054a54  lea     rbx, [rdi+0A0h]
0x180054a5b  mov     rcx, rbx; lpCriticalSection
0x180054a5e  call    cs:__imp_EnterCriticalSection
0x180054a64  mov     rax, [rdi]
0x180054a67  mov     r8, r15
0x180054a6a  mov     rdx, rsi
0x180054a6d  mov     rcx, rdi
0x180054a70  mov     rax, [rax+80h]
0x180054a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a7c  mov     rcx, rbx; lpCriticalSection
0x180054a7f  mov     [rsp+8F0h+exception], eax
0x180054a83  call    cs:__imp_LeaveCriticalSection
0x180054a89  cmp     [rsp+8F0h+exception], 0
0x180054a8e  mov     sil, 4
0x180054a91  jnz     loc_180054B69
0x180054a97  mov     rcx, [r15]
0x180054a9a  test    rcx, rcx
0x180054a9d  jz      loc_180054B69
0x180054aa3  mov     rax, [rdi+70h]
0x180054aa7  cmp     dword ptr [rax+28h], 2
0x180054aab  jnz     short loc_180054AB9
0x180054aad  cmp     dword ptr [rcx], 0
0x180054ab0  jnz     short loc_180054AB9
0x180054ab2  mov     byte ptr [rdi+168h], 1
0x180054ab9  test    cs:byte_1800AA941, r14b
0x180054ac0  jz      loc_180054B58
0x180054ac6  xor     eax, eax
0x180054ac8  mov     word ptr [rbp+7F0h+var_840], ax
0x180054acc  mov     word ptr [rbp+7F0h+var_868], ax
0x180054ad0  mov     rax, [rdi+70h]
0x180054ad4  test    rax, rax
0x180054ad7  jz      short loc_180054AE4
0x180054ad9  cmp     qword ptr [rax+10h], 0
0x180054ade  jz      short loc_180054AE4
0x180054ae0  mov     r13d, [rax+10h]
0x180054ae4  mov     edx, r13d
0x180054ae7  lea     rcx, [rbp+7F0h+var_868]
0x180054aeb  call    ConvertPortNoToString
0x180054af0  mov     r8, [r15]
0x180054af3  lea     rdx, aProcessingEapP; "Processing EAP packet: State: %d"
0x180054afa  lea     rcx, [rbp+7F0h+var_840]
0x180054afe  mov     r8d, [r8]
0x180054b01  call    FormatRRASErrorString
0x180054b06  test    cs:byte_1800AA941, r14b
0x180054b0d  jz      short loc_180054B58
0x180054b0f  mov     rdx, [rdi+70h]
0x180054b13  mov     rax, rdx
0x180054b16  neg     rax
0x180054b19  sbb     r8, r8
0x180054b1c  lea     rcx, [rdx+0A7Eh]
0x180054b23  and     r8, rcx
0x180054b26  lea     r9, [rdx+848h]
0x180054b2d  test    rdx, rdx
0x180054b30  jnz     short loc_180054B37
0x180054b32  lea     r9, [rsp+8F0h+var_878]
0x180054b37  lea     rax, [rbp+7F0h+var_868]
0x180054b3b  mov     rcx, r12
0x180054b3e  mov     [rsp+8F0h+var_8C8], rax
0x180054b43  lea     rdx, RasVpnIkeParamTraceInfo
0x180054b4a  mov     [rsp+8F0h+var_8D0], r8
0x180054b4f  lea     r8, [rbp+7F0h+var_840]
0x180054b53  call    McTemplateU0zjzz_EventWriteTransfer
0x180054b58  mov     rcx, [r15]
0x180054b5b  mov     rcx, [rcx+8]; struct _EAP_AUTH_PACKET_ *
0x180054b5f  call    ?LogEAPAuthPacket@@YAXPEAU_EAP_AUTH_PACKET_@@@Z; LogEAPAuthPacket(_EAP_AUTH_PACKET_ *)
0x180054b64  jmp     loc_180054C18
0x180054b69  mov     rax, [rdi+70h]
0x180054b6d  cmp     dword ptr [rax+28h], 2
0x180054b71  jnz     short loc_180054B7A
0x180054b73  mov     byte ptr [rdi+168h], 1
0x180054b7a  test    cs:byte_1800AA941, sil
0x180054b81  jz      loc_180054C18
0x180054b87  xor     eax, eax
0x180054b89  mov     word ptr [rbp+7F0h+var_840], ax
0x180054b8d  mov     word ptr [rbp+7F0h+var_868], ax
0x180054b91  mov     rax, [rdi+70h]
0x180054b95  test    rax, rax
0x180054b98  jz      short loc_180054BA5
0x180054b9a  cmp     qword ptr [rax+10h], 0
0x180054b9f  jz      short loc_180054BA5
0x180054ba1  mov     r13d, [rax+10h]
0x180054ba5  mov     edx, r13d
0x180054ba8  lea     rcx, [rbp+7F0h+var_868]
0x180054bac  call    ConvertPortNoToString
0x180054bb1  mov     r8d, [rsp+8F0h+exception]
0x180054bb6  lea     rdx, aFailedToProces; "Failed to process EAP packet. %d"
0x180054bbd  lea     rcx, [rbp+7F0h+var_840]
0x180054bc1  call    FormatRRASErrorString
0x180054bc6  test    cs:byte_1800AA941, sil
0x180054bcd  jz      short loc_180054C18
0x180054bcf  mov     rdx, [rdi+70h]
0x180054bd3  mov     rax, rdx
0x180054bd6  neg     rax
0x180054bd9  sbb     r8, r8
0x180054bdc  lea     rcx, [rdx+0A7Eh]
0x180054be3  and     r8, rcx
0x180054be6  lea     r9, [rdx+848h]
0x180054bed  test    rdx, rdx
0x180054bf0  jnz     short loc_180054BF7
0x180054bf2  lea     r9, [rsp+8F0h+var_878]
0x180054bf7  lea     rax, [rbp+7F0h+var_868]
0x180054bfb  mov     rcx, r12
0x180054bfe  mov     [rsp+8F0h+var_8C8], rax
0x180054c03  lea     rdx, RasVpnIkeParamTraceError
0x180054c0a  mov     [rsp+8F0h+var_8D0], r8
0x180054c0f  lea     r8, [rbp+7F0h+var_840]
0x180054c13  call    McTemplateU0zjzz_EventWriteTransfer
0x180054c18  mov     rcx, rdi; this
0x180054c1b  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180054c20  mov     rbx, cs:WPP_GLOBAL_Control
0x180054c27  mov     rdi, [rsp+8F0h+pAsync]
0x180054c2c  jmp     loc_180054CB7
0x180054c31  mov     sil, 4
0x180054c34  test    cs:byte_1800AA941, sil
0x180054c3b  jz      short loc_180054C72
0x180054c3d  xor     eax, eax
0x180054c3f  mov     r8d, r14d
0x180054c42  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x180054c49  mov     word ptr [rbp+7F0h+var_840], ax
0x180054c4d  lea     rcx, [rbp+7F0h+var_840]
0x180054c51  call    FormatRRASErrorString
0x180054c56  test    cs:byte_1800AA941, sil
0x180054c5d  jz      short loc_180054C72
0x180054c5f  lea     r8, [rbp+7F0h+var_840]
0x180054c63  mov     rcx, r12
0x180054c66  lea     rdx, RasVpnIkeTraceError
0x180054c6d  call    McTemplateU0z_EventWriteTransfer
0x180054c72  mov     rbx, cs:WPP_GLOBAL_Control
0x180054c79  mov     [rsp+8F0h+exception], 345h
0x180054c81  jmp     short loc_180054CC2
0x180054c83  mov     sil, 4
0x180054c86  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180054c8d  test    sil, al
0x180054c90  jz      short loc_180054CAF
0x180054c92  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180054c99  mov     rcx, r12
0x180054c9c  lea     rdx, RasVpnIkeTraceError
0x180054ca3  call    McTemplateU0z_EventWriteTransfer
0x180054ca8  mov     rbx, cs:WPP_GLOBAL_Control
0x180054caf  mov     [rsp+8F0h+exception], 57h ; 'W'
0x180054cb7  cmp     [rsp+8F0h+exception], 0
0x180054cbc  jz      loc_180054D59
0x180054cc2  mov     rax, [r15]
0x180054cc5  test    rax, rax
0x180054cc8  jz      short loc_180054D1C
0x180054cca  mov     rbx, [rax+8]
0x180054cce  test    rbx, rbx
0x180054cd1  jz      short loc_180054CF2
0x180054cd3  call    cs:__imp_GetProcessHeap
0x180054cd9  mov     r8, rbx; lpMem
0x180054cdc  xor     edx, edx; dwFlags
0x180054cde  mov     rcx, rax; hHeap
0x180054ce1  call    cs:__imp_HeapFree
0x180054ce7  mov     rax, [r15]
0x180054cea  mov     qword ptr [rax+8], 0
0x180054cf2  mov     rbx, [r15]
0x180054cf5  test    rbx, rbx
0x180054cf8  jz      short loc_180054D0E
0x180054cfa  call    cs:__imp_GetProcessHeap
0x180054d00  mov     r8, rbx; lpMem
0x180054d03  xor     edx, edx; dwFlags
0x180054d05  mov     rcx, rax; hHeap
0x180054d08  call    cs:__imp_HeapFree
0x180054d0e  mov     qword ptr [r15], 0
0x180054d15  mov     rbx, cs:WPP_GLOBAL_Control
0x180054d1c  lea     rax, WPP_GLOBAL_Control
0x180054d23  cmp     rbx, rax
0x180054d26  jz      short loc_180054D4E
0x180054d28  test    byte ptr [rbx+1Ch], 1
0x180054d2c  jz      short loc_180054D4E
  ... truncated ...
```
