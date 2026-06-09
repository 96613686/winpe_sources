# VpnikeRemoveTs

- ea: `0x180055be0`
- end: `0x180055f7b`
- name: `VpnikeRemoveTs`
- size: `923`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x1800077bc`
- `0x180055be0`
- `0x180056880`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e39`
- `RPCRT4!RpcRaiseException` at `0x180055f11`
- `RPCRT4!RpcRaiseException` at `0x180055f11`

## string_xrefs

- `0x180055cc6`: `VpnikeRemoveTs`
- `0x180055d99`: `Remove TrafficSelectors for TsId [%I64u]`

## pseudocode

```c
__int64 __fastcall VpnikeRemoveTs(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  PVOID *v5; // rbx
  unsigned int v6; // r14d
  char v7; // al
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rax
  ULONG_PTR SpinCount; // rdx
  __int128 *v12; // r9
  unsigned int v13; // ecx
  RPC_STATUS exception; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+7Ch] [rbp-84h]
  __int128 v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+90h] [rbp-70h] BYREF
  __int128 v25; // [rsp+94h] [rbp-6Ch]
  __int128 v26; // [rsp+A4h] [rbp-5Ch]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v29[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v3 = a3;
  v16 = a3;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3);
    v3 = v16;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  exception = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v6 = -1;
  v24 = 0;
  v27 = 0;
  v17 = 0;
  v20 = 0;
  v22 = 0;
  v7 = byte_1800AA941;
  v21 = -1;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v18 = 0;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"VpnikeRemoveTs",
      (unsigned int *)&exception,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v3 = v16;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && v3 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Tunnel ID: 0x%I64X", a2);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v28);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine + 1) + 40LL))(
           *((_QWORD *)VpnIkeProtocolEngine + 1),
           a2);
    v9 = (struct _RTL_CRITICAL_SECTION *)v8;
    if ( !v8 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v28);
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      v13 = 837;
      exception = 837;
LABEL_30:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        WPP_SF_d(v5[2], 38, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v13);
        v13 = exception;
      }
      RpcRaiseException(v13);
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      v10 = *(_QWORD *)(v8 + 112);
      if ( v10 && *(_QWORD *)(v10 + 16) )
        v6 = *(_DWORD *)(v10 + 16);
      ConvertPortNoToString(&v24, v6);
      FormatRRASErrorString(&v28, L"Remove TrafficSelectors for TsId [%I64u]", v16);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        SpinCount = v9[2].SpinCount;
        LODWORD(v12) = SpinCount + 2120;
        if ( !SpinCount )
          v12 = &v23;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v28,
          (_DWORD)v12,
          (SpinCount + 2686) & -(__int64)(v9[2].SpinCount != 0),
          (__int64)&v24);
      }
    }
    EnterCriticalSection(v9 + 4);
    exception = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64 *))v9->DebugInfo[2].ProcessLocksList.Blink)(
                  v9,
                  4,
                  &v16);
    LeaveCriticalSection(v9 + 4);
    BaseConnection::DeleteRef((BaseConnection *)v9);
    v13 = exception;
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
    v13 = 87;
    exception = 87;
  }
  if ( v13 )
    goto LABEL_30;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 39, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return 0;
}

```

## disassembly

```asm
0x180055be0  mov     [rsp-8+arg_0], rbx
0x180055be5  mov     [rsp-8+arg_18], rsi
0x180055bea  push    rbp
0x180055beb  push    rdi
0x180055bec  push    r14
0x180055bee  lea     rbp, [rsp-7D0h]
0x180055bf6  sub     rsp, 8D0h
0x180055bfd  mov     rax, cs:__security_cookie
0x180055c04  xor     rax, rsp
0x180055c07  mov     [rbp+7E0h+var_20], rax
0x180055c0e  mov     rdi, r8
0x180055c11  mov     [rsp+8E0h+var_8A8], r8
0x180055c16  mov     rsi, rdx
0x180055c19  mov     rbx, cs:WPP_GLOBAL_Control
0x180055c20  lea     rax, WPP_GLOBAL_Control
0x180055c27  cmp     rbx, rax
0x180055c2a  jz      short loc_180055C55
0x180055c2c  test    byte ptr [rbx+1Ch], 1
0x180055c30  jz      short loc_180055C55
0x180055c32  cmp     byte ptr [rbx+19h], 6
0x180055c36  jb      short loc_180055C55
0x180055c38  mov     rcx, [rbx+10h]
0x180055c3c  mov     r9, rdx
0x180055c3f  mov     [rsp+8E0h+var_8C0], r8
0x180055c44  call    WPP_SF_II
0x180055c49  mov     rdi, [rsp+8E0h+var_8A8]
0x180055c4e  mov     rbx, cs:WPP_GLOBAL_Control
0x180055c55  xor     eax, eax
0x180055c57  mov     [rsp+8E0h+exception], 0
0x180055c5f  xor     edx, edx; Val
0x180055c61  mov     [rbp+7E0h+var_820], eax
0x180055c64  mov     r8d, 7FCh; Size
0x180055c6a  lea     rcx, [rbp+7E0h+var_81C]; void *
0x180055c6e  call    memset_0
0x180055c73  xor     eax, eax
0x180055c75  xorps   xmm0, xmm0
0x180055c78  or      r14d, 0FFFFFFFFh
0x180055c7c  mov     [rbp+7E0h+var_850], eax
0x180055c7f  mov     [rbp+7E0h+var_82C], eax
0x180055c82  xorps   xmm1, xmm1
0x180055c85  mov     [rsp+8E0h+var_898], rax
0x180055c8a  mov     [rsp+8E0h+var_870], rax
0x180055c8f  mov     [rsp+8E0h+var_864], eax
0x180055c93  mov     al, cs:byte_1800AA941
0x180055c99  mov     [rsp+8E0h+var_868], r14d
0x180055c9e  movups  [rbp+7E0h+var_84C], xmm0
0x180055ca2  movups  [rbp+7E0h+var_83C], xmm0
0x180055ca6  movups  [rbp+7E0h+var_860], xmm0
0x180055caa  movdqu  [rsp+8E0h+var_890], xmm1
0x180055cb0  movdqu  [rsp+8E0h+var_880], xmm0
0x180055cb6  test    al, 8
0x180055cb8  jz      short loc_180055CE9
0x180055cba  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180055cc1  lea     r8, [rsp+8E0h+exception]; unsigned int *
0x180055cc6  lea     rdx, aVpnikeremovets; "VpnikeRemoveTs"
0x180055ccd  lea     rcx, [rsp+8E0h+var_898]; this
0x180055cd2  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180055cd7  mov     al, cs:byte_1800AA941
0x180055cdd  mov     rdi, [rsp+8E0h+var_8A8]
0x180055ce2  mov     rbx, cs:WPP_GLOBAL_Control
0x180055ce9  test    rsi, rsi
0x180055cec  jz      loc_180055EAB
0x180055cf2  test    rdi, rdi
0x180055cf5  jz      loc_180055EAB
0x180055cfb  test    al, 8
0x180055cfd  jz      short loc_180055D38
0x180055cff  xor     eax, eax
0x180055d01  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x180055d08  mov     r8, rsi
0x180055d0b  mov     word ptr [rbp+7E0h+var_820], ax
0x180055d0f  lea     rcx, [rbp+7E0h+var_820]
0x180055d13  call    FormatRRASErrorString
0x180055d18  test    cs:byte_1800AA941, 8
0x180055d1f  jz      short loc_180055D38
0x180055d21  lea     r8, [rbp+7E0h+var_820]
0x180055d25  lea     rdx, RasVpnIkeTraceInfo
0x180055d2c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055d33  call    McTemplateU0z_EventWriteTransfer
0x180055d38  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180055d3f  mov     rdx, rsi
0x180055d42  mov     rcx, [rax+8]
0x180055d46  mov     rax, [rcx]
0x180055d49  mov     rax, [rax+28h]
0x180055d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d52  mov     rdi, rax
0x180055d55  test    rax, rax
0x180055d58  jz      loc_180055E57
0x180055d5e  test    cs:byte_1800AA941, 8
0x180055d65  jz      loc_180055DFE
0x180055d6b  xor     ecx, ecx
0x180055d6d  mov     word ptr [rbp+7E0h+var_820], cx
0x180055d71  mov     word ptr [rbp+7E0h+var_850], cx
0x180055d75  mov     rax, [rax+70h]
0x180055d79  test    rax, rax
0x180055d7c  jz      short loc_180055D88
0x180055d7e  cmp     [rax+10h], rcx
0x180055d82  jz      short loc_180055D88
0x180055d84  mov     r14d, [rax+10h]
0x180055d88  mov     edx, r14d
0x180055d8b  lea     rcx, [rbp+7E0h+var_850]
0x180055d8f  call    ConvertPortNoToString
0x180055d94  mov     r8, [rsp+8E0h+var_8A8]
0x180055d99  lea     rdx, aRemoveTraffics; "Remove TrafficSelectors for TsId [%I64u"...
0x180055da0  lea     rcx, [rbp+7E0h+var_820]
0x180055da4  call    FormatRRASErrorString
0x180055da9  test    cs:byte_1800AA941, 8
0x180055db0  jz      short loc_180055DFE
0x180055db2  mov     rdx, [rdi+70h]
0x180055db6  mov     rax, rdx
0x180055db9  neg     rax
0x180055dbc  sbb     r8, r8
0x180055dbf  lea     rcx, [rdx+0A7Eh]
0x180055dc6  and     r8, rcx
0x180055dc9  lea     r9, [rdx+848h]
0x180055dd0  test    rdx, rdx
0x180055dd3  jnz     short loc_180055DD9
0x180055dd5  lea     r9, [rbp+7E0h+var_860]
0x180055dd9  lea     rax, [rbp+7E0h+var_850]
0x180055ddd  mov     [rsp+8E0h+var_8B8], rax
0x180055de2  lea     rdx, RasVpnIkeParamTraceInfo
0x180055de9  mov     [rsp+8E0h+var_8C0], r8
0x180055dee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055df5  lea     r8, [rbp+7E0h+var_820]
0x180055df9  call    McTemplateU0zjzz_EventWriteTransfer
0x180055dfe  lea     rbx, [rdi+0A0h]
0x180055e05  mov     rcx, rbx; lpCriticalSection
0x180055e08  call    cs:__imp_EnterCriticalSection
0x180055e0e  mov     rax, [rdi]
0x180055e11  lea     r8, [rsp+8E0h+var_8A8]
0x180055e16  xor     r9d, r9d
0x180055e19  mov     [rsp+8E0h+var_8C0], 0
0x180055e22  mov     rcx, rdi
0x180055e25  mov     rax, [rax+78h]
0x180055e29  lea     edx, [r9+4]
0x180055e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e32  mov     rcx, rbx; lpCriticalSection
0x180055e35  mov     [rsp+8E0h+exception], eax
0x180055e39  call    cs:__imp_LeaveCriticalSection
0x180055e3f  mov     rcx, rdi; this
0x180055e42  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180055e47  mov     ecx, [rsp+8E0h+exception]
0x180055e4b  mov     rbx, cs:WPP_GLOBAL_Control
0x180055e52  jmp     loc_180055ED9
0x180055e57  test    cs:byte_1800AA941, 4
0x180055e5e  jz      short loc_180055E99
0x180055e60  xor     eax, eax
0x180055e62  mov     r8d, esi
0x180055e65  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x180055e6c  mov     word ptr [rbp+7E0h+var_820], ax
0x180055e70  lea     rcx, [rbp+7E0h+var_820]
0x180055e74  call    FormatRRASErrorString
0x180055e79  test    cs:byte_1800AA941, 4
0x180055e80  jz      short loc_180055E99
0x180055e82  lea     r8, [rbp+7E0h+var_820]
0x180055e86  lea     rdx, RasVpnIkeTraceError
0x180055e8d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055e94  call    McTemplateU0z_EventWriteTransfer
0x180055e99  mov     rbx, cs:WPP_GLOBAL_Control
0x180055ea0  mov     ecx, 345h
0x180055ea5  mov     [rsp+8E0h+exception], ecx
0x180055ea9  jmp     short loc_180055EDD
0x180055eab  test    al, 4
0x180055ead  jz      short loc_180055ED0
0x180055eaf  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180055eb6  lea     rdx, RasVpnIkeTraceError
0x180055ebd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180055ec4  call    McTemplateU0z_EventWriteTransfer
0x180055ec9  mov     rbx, cs:WPP_GLOBAL_Control
0x180055ed0  mov     ecx, 57h ; 'W'
0x180055ed5  mov     [rsp+8E0h+exception], ecx
0x180055ed9  test    ecx, ecx
0x180055edb  jz      short loc_180055F18
0x180055edd  lea     rax, WPP_GLOBAL_Control
0x180055ee4  cmp     rbx, rax
0x180055ee7  jz      short loc_180055F11
0x180055ee9  test    byte ptr [rbx+1Ch], 1
0x180055eed  jz      short loc_180055F11
0x180055eef  cmp     byte ptr [rbx+19h], 6
0x180055ef3  jb      short loc_180055F11
0x180055ef5  mov     r9d, ecx
0x180055ef8  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055eff  mov     rcx, [rbx+10h]
0x180055f03  mov     edx, 26h ; '&'
0x180055f08  call    WPP_SF_d
0x180055f0d  mov     ecx, [rsp+8E0h+exception]; exception
0x180055f11  call    cs:__imp_RpcRaiseException
0x180055f17  int     3; Trap to Debugger
0x180055f18  lea     rax, WPP_GLOBAL_Control
0x180055f1f  cmp     rbx, rax
0x180055f22  jz      short loc_180055F48
0x180055f24  test    byte ptr [rbx+1Ch], 1
0x180055f28  jz      short loc_180055F48
0x180055f2a  cmp     byte ptr [rbx+19h], 6
0x180055f2e  jb      short loc_180055F48
0x180055f30  mov     rcx, [rbx+10h]
0x180055f34  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180055f3b  mov     edx, 27h ; '''
0x180055f40  xor     r9d, r9d
0x180055f43  call    WPP_SF_d
0x180055f48  lea     rcx, [rsp+8E0h+var_898]; this
0x180055f4d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180055f52  xor     eax, eax
0x180055f54  mov     rcx, [rbp+7E0h+var_20]
0x180055f5b  xor     rcx, rsp; StackCookie
0x180055f5e  call    __security_check_cookie
0x180055f63  lea     r11, [rsp+8E0h+var_10]
0x180055f6b  mov     rbx, [r11+20h]
0x180055f6f  mov     rsi, [r11+38h]
0x180055f73  mov     rsp, r11
0x180055f76  pop     r14
0x180055f78  pop     rdi
0x180055f79  pop     rbp
0x180055f7a  retn
```
