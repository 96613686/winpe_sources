# InitializeProtocolEngine

- ea: `0x1800082d0`
- end: `0x180008512`
- name: `InitializeProtocolEngine`
- size: `578`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003d9c`
- `0x180007590`
- `0x1800082d0`
- `0x180008800`
- `0x1800639d0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rasman!RasInitializeNoWait` at `0x1800084a9`
- `rasman!RasInitializeNoWait` at `0x1800084a9`

## string_xrefs

- `0x180008371`: `InitializeProtocolEngine`
- `0x180008396`: `VpnIkeProtocolEngine already loaded`
- `0x18000847c`: `VpnIkeProtocolEngine failed to load`
- `0x180008506`: `VpnIkeProtocolEngine->Initialize failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializeProtocolEngine(__int64 a1, unsigned int a2, unsigned int a3)
{
  char v6; // al
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  VPNIKEProtocolEngine *v10; // rcx
  unsigned int v11; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v13; // [rsp+30h] [rbp-D0h]
  __int128 v14; // [rsp+40h] [rbp-C0h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v11 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v6 = byte_1800AA941;
  v12 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  v13 = 0;
  v14 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"InitializeProtocolEngine",
      &v11,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v6 = byte_1800AA941;
  }
  if ( !VpnIkeProtocolEngine )
  {
    v11 = InitializeVpnIkeRpcServer();
    v7 = v11;
    if ( v11 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_13;
      v8 = L"InitializeVpnIkeRpcServer failed: %d";
    }
    else
    {
      g_RasRpcInitialized = 1;
      VpnIkeProtocolEngine = VPNIKEProtocolEngine::GetInstance();
      v10 = VpnIkeProtocolEngine;
      if ( !VpnIkeProtocolEngine )
      {
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasVpnIkeTraceInfo,
            L"VpnIkeProtocolEngine failed to load");
        v11 = 14;
        goto LABEL_14;
      }
      if ( (a3 & 1) != 0 )
      {
        v11 = RasInitializeNoWait(VpnIkeProtocolEngine);
        v7 = v11;
        if ( v11 )
        {
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_13;
          v8 = L"RasInitializeNoWait failed: %d";
          goto LABEL_10;
        }
        v10 = VpnIkeProtocolEngine;
      }
      v11 = (*(__int64 (__fastcall **)(VPNIKEProtocolEngine *, __int64, _QWORD))(*(_QWORD *)v10 + 8LL))(v10, a1, a2);
      v7 = v11;
      if ( !v11 || (byte_1800AA941 & 4) == 0 )
        goto LABEL_13;
      v8 = L"VpnIkeProtocolEngine->Initialize failed: %d";
    }
LABEL_10:
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, v8, v7);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v18);
    v7 = v11;
LABEL_13:
    if ( !v7 )
      goto LABEL_15;
LABEL_14:
    UninitializeProtocolEngine(a3);
    v7 = v11;
    goto LABEL_15;
  }
  if ( (v6 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceInfo,
      L"VpnIkeProtocolEngine already loaded");
  v7 = 4317;
LABEL_15:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v7;
}

```

## disassembly

```asm
0x1800082d0  mov     [rsp-8+arg_10], rbx
0x1800082d5  mov     [rsp-8+arg_18], rsi
0x1800082da  push    rbp
0x1800082db  push    rdi
0x1800082dc  push    r14
0x1800082de  lea     rbp, [rsp-770h]
0x1800082e6  sub     rsp, 870h
0x1800082ed  mov     rax, cs:__security_cookie
0x1800082f4  xor     rax, rsp
0x1800082f7  mov     [rbp+780h+var_20], rax
0x1800082fe  mov     edi, r8d
0x180008301  mov     [rsp+880h+var_860], 0
0x180008309  mov     r14d, edx
0x18000830c  mov     rsi, rcx
0x18000830f  xor     eax, eax
0x180008311  lea     rcx, [rsp+880h+var_81C]; void *
0x180008316  xor     edx, edx; Val
0x180008318  mov     [rsp+880h+var_820], eax
0x18000831c  mov     r8d, 7FCh; Size
0x180008322  call    memset_0
0x180008327  mov     al, cs:byte_1800AA941
0x18000832d  xorps   xmm0, xmm0
0x180008330  mov     [rsp+880h+var_858], 0
0x180008339  xorps   xmm1, xmm1
0x18000833c  mov     [rsp+880h+var_830], 0
0x180008345  mov     [rsp+880h+var_828], 0FFFFFFFFh
0x18000834d  mov     [rsp+880h+var_824], 0
0x180008355  movdqu  [rsp+880h+var_850], xmm0
0x18000835b  movdqu  [rsp+880h+var_840], xmm1
0x180008361  test    al, 8
0x180008363  jz      short loc_180008388
0x180008365  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000836c  lea     r8, [rsp+880h+var_860]; unsigned int *
0x180008371  lea     rdx, aInitializeprot_0; "InitializeProtocolEngine"
0x180008378  lea     rcx, [rsp+880h+var_858]; this
0x18000837d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180008382  mov     al, cs:byte_1800AA941
0x180008388  cmp     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, 0; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180008390  jz      short loc_1800083B7
0x180008392  test    al, 8
0x180008394  jz      short loc_1800083B0
0x180008396  lea     r8, aVpnikeprotocol_10; "VpnIkeProtocolEngine already loaded"
0x18000839d  lea     rdx, RasVpnIkeTraceInfo
0x1800083a4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800083ab  call    McTemplateU0z_EventWriteTransfer
0x1800083b0  mov     ebx, 10DDh
0x1800083b5  jmp     short loc_180008422
0x1800083b7  call    InitializeVpnIkeRpcServer
0x1800083bc  mov     [rsp+880h+var_860], eax
0x1800083c0  mov     ebx, eax
0x1800083c2  test    eax, eax
0x1800083c4  jz      loc_180008455
0x1800083ca  test    cs:byte_1800AA941, 4
0x1800083d1  jz      short loc_180008413
0x1800083d3  lea     rdx, aInitializevpni; "InitializeVpnIkeRpcServer failed: %d"
0x1800083da  xor     eax, eax
0x1800083dc  lea     rcx, [rsp+880h+var_820]
0x1800083e1  mov     r8d, ebx
0x1800083e4  mov     word ptr [rsp+880h+var_820], ax
0x1800083e9  call    FormatRRASErrorString
0x1800083ee  test    cs:byte_1800AA941, 4
0x1800083f5  jz      short loc_18000840F
0x1800083f7  lea     r8, [rsp+880h+var_820]
0x1800083fc  lea     rdx, RasVpnIkeTraceError
0x180008403  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000840a  call    McTemplateU0z_EventWriteTransfer
0x18000840f  mov     ebx, [rsp+880h+var_860]
0x180008413  test    ebx, ebx
0x180008415  jz      short loc_180008422
0x180008417  mov     ecx, edi
0x180008419  call    UninitializeProtocolEngine
0x18000841e  mov     ebx, [rsp+880h+var_860]
0x180008422  lea     rcx, [rsp+880h+var_858]; this
0x180008427  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000842c  mov     eax, ebx
0x18000842e  mov     rcx, [rbp+780h+var_20]
0x180008435  xor     rcx, rsp; StackCookie
0x180008438  call    __security_check_cookie
0x18000843d  lea     r11, [rsp+880h+var_10]
0x180008445  mov     rbx, [r11+30h]
0x180008449  mov     rsi, [r11+38h]
0x18000844d  mov     rsp, r11
0x180008450  pop     r14
0x180008452  pop     rdi
0x180008453  pop     rbp
0x180008454  retn
0x180008455  mov     cs:?g_RasRpcInitialized@@3HA, 1; int g_RasRpcInitialized
0x18000845f  call    ?GetInstance@VPNIKEProtocolEngine@@SAPEAV1@XZ; VPNIKEProtocolEngine::GetInstance(void)
0x180008464  mov     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, rax; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x18000846b  mov     rcx, rax
0x18000846e  test    rax, rax
0x180008471  jnz     short loc_1800084A3
0x180008473  test    cs:byte_1800AA941, 8
0x18000847a  jz      short loc_180008496
0x18000847c  lea     r8, aVpnikeprotocol_11; "VpnIkeProtocolEngine failed to load"
0x180008483  lea     rdx, RasVpnIkeTraceInfo
0x18000848a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008491  call    McTemplateU0z_EventWriteTransfer
0x180008496  mov     [rsp+880h+var_860], 0Eh
0x18000849e  jmp     loc_180008417
0x1800084a3  test    dil, 1
0x1800084a7  jz      short loc_1800084D9
0x1800084a9  call    cs:__imp_RasInitializeNoWait
0x1800084af  mov     [rsp+880h+var_860], eax
0x1800084b3  mov     ebx, eax
0x1800084b5  test    eax, eax
0x1800084b7  jz      short loc_1800084D2
0x1800084b9  test    cs:byte_1800AA941, 4
0x1800084c0  jz      loc_180008413
0x1800084c6  lea     rdx, aRasinitializen; "RasInitializeNoWait failed: %d"
0x1800084cd  jmp     loc_1800083DA
0x1800084d2  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800084d9  mov     rax, [rcx]
0x1800084dc  mov     r8d, r14d
0x1800084df  mov     rdx, rsi
0x1800084e2  mov     rax, [rax+8]
0x1800084e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084eb  mov     [rsp+880h+var_860], eax
0x1800084ef  mov     ebx, eax
0x1800084f1  test    eax, eax
0x1800084f3  jz      loc_180008413
0x1800084f9  test    cs:byte_1800AA941, 4
0x180008500  jz      loc_180008413
0x180008506  lea     rdx, aVpnikeprotocol_5; "VpnIkeProtocolEngine->Initialize failed"...
0x18000850d  jmp     loc_1800083DA
```
