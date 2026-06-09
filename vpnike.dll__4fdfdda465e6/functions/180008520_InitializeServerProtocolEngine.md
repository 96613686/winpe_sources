# InitializeServerProtocolEngine

- ea: `0x180008520`
- end: `0x1800087c2`
- name: `InitializeServerProtocolEngine`
- size: `674`
- prototype: `__int64 __fastcall(void (*)(struct _PROTOCOL_RESULT *), unsigned int, unsigned int, unsigned int, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007590`
- `0x180007fbc`
- `0x180008520`
- `0x1800088d0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x1800085d6`: `InitializeServerProtocolEngine`
- `0x1800085fb`: `VpnIkeProtocolEngine not loaded by rasman already. ERROR_INVALID_OPERATION`
- `0x18000867a`: `Cannot load VPNIKE with this auth configuration`
- `0x180008722`: `VpnIkeProtocolEngine->InitializeServer failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializeServerProtocolEngine(
        void (*a1)(struct _PROTOCOL_RESULT *),
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  char v12; // al
  unsigned int v13; // ebx
  __int64 v15; // rax
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int128 v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  int v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+94h] [rbp-6Ch]
  int v24; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v17 = a8;
  v16 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v12 = byte_1800AA941;
  v18 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  v19 = 0;
  v20 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"InitializeServerProtocolEngine",
      &v16,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v12 = byte_1800AA941;
  }
  if ( !VpnIkeProtocolEngine )
  {
    if ( (v12 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceAdminError,
        L"VpnIkeProtocolEngine not loaded by rasman already. ERROR_INVALID_OPERATION");
    v13 = 4317;
LABEL_15:
    EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
    return v13;
  }
  if ( (v12 & 8) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Init Server Options: 0x%08x", a2);
    v12 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v24);
      v12 = byte_1800AA941;
    }
  }
  if ( (a2 & 0x14008000) == 0 )
  {
    if ( !IsPSKAuthConfigured() )
    {
      if ( (byte_1800AA941 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceAdminError,
          L"Cannot load VPNIKE with this auth configuration");
      v13 = 50;
      goto LABEL_15;
    }
    v12 = byte_1800AA941;
  }
  if ( a1 && a6 && a7 )
  {
    v15 = *(_QWORD *)VpnIkeProtocolEngine;
    g_fnSendProtocolMsgToDDM = a1;
    v16 = (*(__int64 (__fastcall **)(VPNIKEProtocolEngine *, _QWORD, _QWORD, _QWORD, int, __int64, __int64, __int64))(v15 + 16))(
            VpnIkeProtocolEngine,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            v17);
    v13 = v16;
    if ( v16 && (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"VpnIkeProtocolEngine->InitializeServer failed: %d", v16);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v24);
      v13 = v16;
    }
    if ( v13 )
    {
      UninitializeServerProtocolEngine();
      v13 = v16;
    }
    goto LABEL_15;
  }
  if ( (v12 & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Failed as ERROR_INVALID_PARAMETER");
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return 87;
}

```

## disassembly

```asm
0x180008520  push    rbp
0x180008522  push    rbx
0x180008523  push    rsi
0x180008524  push    r12
0x180008526  push    r13
0x180008528  push    r14
0x18000852a  push    r15
0x18000852c  lea     rbp, [rsp-7B0h]
0x180008534  sub     rsp, 8B0h
0x18000853b  mov     rax, cs:__security_cookie
0x180008542  xor     rax, rsp
0x180008545  mov     [rbp+7E0h+var_40], rax
0x18000854c  mov     rax, [rbp+7E0h+arg_38]
0x180008553  mov     r12d, r8d
0x180008556  mov     r14, [rbp+7E0h+arg_28]
0x18000855d  mov     ebx, edx
0x18000855f  mov     r15, [rbp+7E0h+arg_30]
0x180008566  mov     rsi, rcx
0x180008569  mov     [rsp+8E0h+var_888], rax
0x18000856e  lea     rcx, [rbp+7E0h+var_83C]; void *
0x180008572  xor     eax, eax
0x180008574  mov     [rsp+8E0h+var_890], 0
0x18000857c  xor     edx, edx; Val
0x18000857e  mov     [rbp+7E0h+var_840], eax
0x180008581  mov     r8d, 7FCh; Size
0x180008587  mov     r13d, r9d
0x18000858a  call    memset_0
0x18000858f  mov     al, cs:byte_1800AA941
0x180008595  xorps   xmm0, xmm0
0x180008598  mov     [rsp+8E0h+var_880], 0
0x1800085a1  xorps   xmm1, xmm1
0x1800085a4  mov     [rbp+7E0h+var_858], 0
0x1800085ac  mov     [rbp+7E0h+var_850], 0FFFFFFFFh
0x1800085b3  mov     [rbp+7E0h+var_84C], 0
0x1800085ba  movdqu  [rsp+8E0h+var_878], xmm0
0x1800085c0  movdqu  [rsp+8E0h+var_868], xmm1
0x1800085c6  test    al, 8
0x1800085c8  jz      short loc_1800085ED
0x1800085ca  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800085d1  lea     r8, [rsp+8E0h+var_890]; unsigned int *
0x1800085d6  lea     rdx, aInitializeserv_0; "InitializeServerProtocolEngine"
0x1800085dd  lea     rcx, [rsp+8E0h+var_880]; this
0x1800085e2  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800085e7  mov     al, cs:byte_1800AA941
0x1800085ed  cmp     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, 0; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800085f5  jnz     short loc_18000861C
0x1800085f7  test    al, 1
0x1800085f9  jz      short loc_180008615
0x1800085fb  lea     r8, aVpnikeprotocol_1; "VpnIkeProtocolEngine not loaded by rasm"...
0x180008602  lea     rdx, RasVpnIkeTraceAdminError
0x180008609  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008610  call    McTemplateU0z_EventWriteTransfer
0x180008615  mov     ebx, 10DDh
0x18000861a  jmp     short loc_180008699
0x18000861c  test    al, 8
0x18000861e  jz      short loc_180008660
0x180008620  xor     eax, eax
0x180008622  lea     rdx, aInitServerOpti; "Init Server Options: 0x%08x"
0x180008629  mov     r8d, ebx
0x18000862c  mov     word ptr [rbp+7E0h+var_840], ax
0x180008630  lea     rcx, [rbp+7E0h+var_840]
0x180008634  call    FormatRRASErrorString
0x180008639  mov     al, cs:byte_1800AA941
0x18000863f  test    al, 8
0x180008641  jz      short loc_180008660
0x180008643  lea     r8, [rbp+7E0h+var_840]
0x180008647  lea     rdx, RasVpnIkeTraceInfo
0x18000864e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008655  call    McTemplateU0z_EventWriteTransfer
0x18000865a  mov     al, cs:byte_1800AA941
0x180008660  test    ebx, 14008000h
0x180008666  jnz     short loc_1800086B0
0x180008668  call    ?IsPSKAuthConfigured@@YAEXZ; IsPSKAuthConfigured(void)
0x18000866d  test    al, al
0x18000866f  jnz     short loc_1800086AA
0x180008671  test    cs:byte_1800AA941, 1
0x180008678  jz      short loc_180008694
0x18000867a  lea     r8, aCannotLoadVpni; "Cannot load VPNIKE with this auth confi"...
0x180008681  lea     rdx, RasVpnIkeTraceAdminError
0x180008688  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000868f  call    McTemplateU0z_EventWriteTransfer
0x180008694  mov     ebx, 32h ; '2'
0x180008699  lea     rcx, [rsp+8E0h+var_880]; this
0x18000869e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800086a3  mov     eax, ebx
0x1800086a5  jmp     loc_1800087A0
0x1800086aa  mov     al, cs:byte_1800AA941
0x1800086b0  test    rsi, rsi
0x1800086b3  jz      loc_180008773
0x1800086b9  test    r14, r14
0x1800086bc  jz      loc_180008773
0x1800086c2  test    r15, r15
0x1800086c5  jz      loc_180008773
0x1800086cb  mov     rdx, [rsp+8E0h+var_888]
0x1800086d0  mov     r9d, r13d
0x1800086d3  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800086da  mov     r8d, r12d
0x1800086dd  mov     r10d, [rbp+7E0h+arg_20]
0x1800086e4  mov     [rsp+8E0h+var_8A8], rdx
0x1800086e9  mov     edx, ebx
0x1800086eb  mov     [rsp+8E0h+var_8B0], r15
0x1800086f0  mov     rax, [rcx]
0x1800086f3  mov     [rsp+8E0h+var_8B8], r14
0x1800086f8  mov     cs:?g_fnSendProtocolMsgToDDM@@3P6AXPEAU_PROTOCOL_RESULT@@@ZEA, rsi; void (*g_fnSendProtocolMsgToDDM)(_PROTOCOL_RESULT *)
0x1800086ff  mov     [rsp+8E0h+var_8C0], r10d
0x180008704  mov     rax, [rax+10h]
0x180008708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870d  mov     [rsp+8E0h+var_890], eax
0x180008711  mov     ebx, eax
0x180008713  test    eax, eax
0x180008715  jz      short loc_18000875D
0x180008717  test    cs:byte_1800AA941, 4
0x18000871e  jz      short loc_18000875D
0x180008720  xor     eax, eax
0x180008722  lea     rdx, aVpnikeprotocol_7; "VpnIkeProtocolEngine->InitializeServer "...
0x180008729  mov     r8d, ebx
0x18000872c  mov     word ptr [rbp+7E0h+var_840], ax
0x180008730  lea     rcx, [rbp+7E0h+var_840]
0x180008734  call    FormatRRASErrorString
0x180008739  test    cs:byte_1800AA941, 4
0x180008740  jz      short loc_180008759
0x180008742  lea     r8, [rbp+7E0h+var_840]
0x180008746  lea     rdx, RasVpnIkeTraceError
0x18000874d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008754  call    McTemplateU0z_EventWriteTransfer
0x180008759  mov     ebx, [rsp+8E0h+var_890]
0x18000875d  test    ebx, ebx
0x18000875f  jz      loc_180008699
0x180008765  call    UninitializeServerProtocolEngine
0x18000876a  mov     ebx, [rsp+8E0h+var_890]
0x18000876e  jmp     loc_180008699
0x180008773  test    al, 4
0x180008775  jz      short loc_180008791
0x180008777  lea     r8, aFailedAsErrorI; "Failed as ERROR_INVALID_PARAMETER"
0x18000877e  lea     rdx, RasVpnIkeTraceError
0x180008785  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000878c  call    McTemplateU0z_EventWriteTransfer
0x180008791  lea     rcx, [rsp+8E0h+var_880]; this
0x180008796  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000879b  mov     eax, 57h ; 'W'
0x1800087a0  mov     rcx, [rbp+7E0h+var_40]
0x1800087a7  xor     rcx, rsp; StackCookie
0x1800087aa  call    __security_check_cookie
0x1800087af  add     rsp, 8B0h
0x1800087b6  pop     r15
0x1800087b8  pop     r14
0x1800087ba  pop     r13
0x1800087bc  pop     r12
0x1800087be  pop     rsi
0x1800087bf  pop     rbx
0x1800087c0  pop     rbp
0x1800087c1  retn
```
