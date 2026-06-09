# VPNIKEClientConnection::ProcessUpdateConnection(_PROTOCOL_UPDATE &)

- ea: `0x18001ca90`
- end: `0x18001cfa3`
- name: `?ProcessUpdateConnection@VPNIKEClientConnection@@UEAAXAEAU_PROTOCOL_UPDATE@@@Z`
- size: `1299`
- prototype: `void __fastcall(VPNIKEClientConnection *__hidden this, struct _PROTOCOL_UPDATE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18001104c`
- `0x180014bec`
- `0x18001af98`
- `0x18001ca90`
- `0x18001f10c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rasman!RasSetPortUserData` at `0x18001cd68`
- `rasman!RasSetPortUserData` at `0x18001cd68`

## string_xrefs

- `0x18001cb8a`: `VPNIKEClientConnection::ProcessUpdateConnection`
- `0x18001cc56`: `ProcessUpdateConnectionParameters failed: %d.`
- `0x18001cdeb`: `VPNIKEIOCTLHelper::UpdateTunnelStart failed: %d`
- `0x18001ce51`: `SendMobikeUpdate failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VPNIKEClientConnection::ProcessUpdateConnection(
        VPNIKEClientConnection *this,
        struct _PROTOCOL_UPDATE *a2)
{
  PVOID *v4; // rbx
  __int64 v5; // r9
  unsigned int v6; // r14d
  unsigned int updated; // esi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int128 *v10; // r9
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int128 *v19; // r9
  int v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v24; // [rsp+3Ch] [rbp-C4h]
  __int128 v25; // [rsp+4Ch] [rbp-B4h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+90h] [rbp-70h]
  int v32; // [rsp+94h] [rbp-6Ch]
  __int128 v33; // [rsp+98h] [rbp-68h] BYREF
  int v34; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v35; // [rsp+ACh] [rbp-54h]
  __int128 v36; // [rsp+BCh] [rbp-44h]
  int v37; // [rsp+CCh] [rbp-34h]
  int v38; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v33 = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v6 = -1;
  v31 = -1;
  v32 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v27,
      L"VPNIKEClientConnection::ProcessUpdateConnection",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    LOBYTE(v20) = *((_BYTE *)this + 265);
    LOBYTE(v5) = *((_BYTE *)this + 264);
    WPP_SF_cc(v4[2], 43, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v5, v20);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 264) || !*((_BYTE *)this + 265) )
  {
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v34) = 0;
      v17 = *((_QWORD *)this + 14);
      if ( v17 && *(_QWORD *)(v17 + 16) )
        v6 = *(_DWORD *)(v17 + 16);
      ConvertPortNoToString(&v34, v6);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v18 = *((_QWORD *)this + 14);
        LODWORD(v19) = v18 + 2120;
        if ( !v18 )
          v19 = &v33;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Mobike is disabled either on initiator/responder. Hence this request is invalid.",
          (_DWORD)v19,
          (v18 + 2686) & -(__int64)(v18 != 0),
          (__int64)&v34);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    updated = 843;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(v4[2], 44, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, 843);
    goto LABEL_58;
  }
  updated = VPNIKEConnection::ProcessUpdateConnectionParameters(
              this,
              a2,
              (struct _PROTOCOL_ENDPOINT_RESULT *)&v23,
              &v21);
  if ( updated )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      v8 = *((_QWORD *)this + 14);
      if ( v8 && *(_QWORD *)(v8 + 16) )
        v6 = *(_DWORD *)(v8 + 16);
      ConvertPortNoToString(&v34, v6);
      FormatRRASErrorString(&v38, L"ProcessUpdateConnectionParameters failed: %d.", updated);
LABEL_19:
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v9 = *((_QWORD *)this + 14);
        LODWORD(v10) = v9 + 2120;
        if ( !v9 )
          v10 = &v33;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v38,
          (_DWORD)v10,
          (v9 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
          (__int64)&v34);
      }
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v22 = 2;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v34) = 0;
    v11 = *((_QWORD *)this + 14);
    if ( v11 && *(_QWORD *)(v11 + 16) )
      v12 = *(unsigned int *)(v11 + 16);
    else
      v12 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v34, v12);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v13 = *((_QWORD *)this + 14);
      LODWORD(v14) = v13 + 2120;
      if ( !v13 )
        v14 = &v33;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)L"Setting RASPortSubStatus to RASCSS_Reconnecting.",
        (_DWORD)v14,
        (v13 + 2686) & -(__int64)(v13 != 0),
        (__int64)&v34);
    }
  }
  RasSetPortUserData(*((_QWORD *)this + 3), 14, &v22);
  VPNIKEProtocolEngine::NotifyCaller(*((_QWORD *)this + 3), 16, 0);
  updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, int *, __int64))(**((_QWORD **)this + 30) + 16LL))(
              *((_QWORD *)this + 30),
              *((_QWORD *)this + 1),
              &v21,
              &v23,
              *((_QWORD *)this + 14) + 44LL);
  if ( updated )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      v15 = *((_QWORD *)this + 14);
      if ( v15 && *(_QWORD *)(v15 + 16) )
        v6 = *(_DWORD *)(v15 + 16);
      ConvertPortNoToString(&v34, v6);
      FormatRRASErrorString(&v38, L"VPNIKEIOCTLHelper::UpdateTunnelStart failed: %d", updated);
      goto LABEL_19;
    }
LABEL_58:
    VPNIKEClientConnection::NotifyUpdateConnectionStatus(this, updated);
    goto LABEL_59;
  }
  updated = (***((__int64 (__fastcall ****)(_QWORD, void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, unsigned int), int *))this
               + 26))(
              *((_QWORD *)this + 26),
              VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback,
              &v23);
  if ( updated )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      v16 = *((_QWORD *)this + 14);
      if ( v16 && *(_QWORD *)(v16 + 16) )
        v6 = *(_DWORD *)(v16 + 16);
      ConvertPortNoToString(&v34, v6);
      FormatRRASErrorString(&v38, L"SendMobikeUpdate failed: %d", updated);
      goto LABEL_19;
    }
    goto LABEL_58;
  }
  VPNIKEClientConnection::UpdateConnectionState(this, 0x40u);
LABEL_59:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v27);
}

```

## disassembly

```asm
0x18001ca90  mov     [rsp-8+arg_10], rbx
0x18001ca95  push    rbp
0x18001ca96  push    rsi
0x18001ca97  push    rdi
0x18001ca98  push    r14
0x18001ca9a  push    r15
0x18001ca9c  lea     rbp, [rsp-7E0h]
0x18001caa4  sub     rsp, 8E0h
0x18001caab  mov     rax, cs:__security_cookie
0x18001cab2  xor     rax, rsp
0x18001cab5  mov     [rbp+800h+var_30], rax
0x18001cabc  mov     rsi, rdx
0x18001cabf  mov     rdi, rcx
0x18001cac2  lea     rax, WPP_GLOBAL_Control
0x18001cac9  mov     rbx, cs:WPP_GLOBAL_Control
0x18001cad0  cmp     rbx, rax
0x18001cad3  jz      short loc_18001CAFD
0x18001cad5  test    byte ptr [rbx+1Ch], 1
0x18001cad9  jz      short loc_18001CAFD
0x18001cadb  cmp     byte ptr [rbx+19h], 6
0x18001cadf  jb      short loc_18001CAFD
0x18001cae1  mov     edx, 2Ah ; '*'
0x18001cae6  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001caed  mov     rcx, [rbx+10h]
0x18001caf1  call    WPP_SF_
0x18001caf6  mov     rbx, cs:WPP_GLOBAL_Control
0x18001cafd  xor     r15d, r15d
0x18001cb00  mov     [rsp+900h+var_8D0], r15d
0x18001cb05  mov     [rsp+900h+var_8C8], r15d
0x18001cb0a  xorps   xmm0, xmm0
0x18001cb0d  xor     eax, eax
0x18001cb0f  movups  [rsp+900h+var_8C4], xmm0
0x18001cb14  movups  [rsp+900h+var_8B4], xmm0
0x18001cb19  mov     [rsp+900h+var_8A4], eax
0x18001cb1d  mov     [rbp+800h+var_830], r15d
0x18001cb21  xor     edx, edx; Val
0x18001cb23  mov     r8d, 7FCh; Size
0x18001cb29  lea     rcx, [rbp+800h+var_82C]; void *
0x18001cb2d  call    memset_0
0x18001cb32  mov     [rbp+800h+var_858], r15d
0x18001cb36  xorps   xmm0, xmm0
0x18001cb39  xor     eax, eax
0x18001cb3b  movups  [rbp+800h+var_854], xmm0
0x18001cb3f  movups  [rbp+800h+var_844], xmm0
0x18001cb43  mov     [rbp+800h+var_834], eax
0x18001cb46  movups  [rbp+800h+var_868], xmm0
0x18001cb4a  xorps   xmm1, xmm1
0x18001cb4d  movdqu  [rsp+900h+var_898], xmm1
0x18001cb53  mov     [rsp+900h+var_8A0], r15
0x18001cb58  movdqu  [rsp+900h+var_888], xmm0
0x18001cb5e  mov     [rbp+800h+var_878], r15
0x18001cb62  or      r14d, 0FFFFFFFFh
0x18001cb66  mov     [rbp+800h+var_870], r14d
0x18001cb6a  mov     [rbp+800h+var_86C], r15d
0x18001cb6e  test    cs:byte_1800AA941, 8
0x18001cb75  jz      short loc_18001CBA2
0x18001cb77  mov     rax, [rdi+70h]
0x18001cb7b  mov     [rsp+900h+var_8E0], rax; void *
0x18001cb80  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001cb87  xor     r8d, r8d; unsigned int *
0x18001cb8a  lea     rdx, aVpnikeclientco_10; "VPNIKEClientConnection::ProcessUpdateCo"...
0x18001cb91  lea     rcx, [rsp+900h+var_8A0]; this
0x18001cb96  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18001cb9b  mov     rbx, cs:WPP_GLOBAL_Control
0x18001cba2  lea     rax, WPP_GLOBAL_Control
0x18001cba9  cmp     rbx, rax
0x18001cbac  jz      short loc_18001CBE7
0x18001cbae  test    byte ptr [rbx+1Ch], 1
0x18001cbb2  jz      short loc_18001CBE7
0x18001cbb4  cmp     byte ptr [rbx+19h], 5
0x18001cbb8  jb      short loc_18001CBE7
0x18001cbba  mov     edx, 2Bh ; '+'
0x18001cbbf  mov     al, [rdi+109h]
0x18001cbc5  mov     byte ptr [rsp+900h+var_8E0], al
0x18001cbc9  mov     r9b, [rdi+108h]
0x18001cbd0  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001cbd7  mov     rcx, [rbx+10h]
0x18001cbdb  call    WPP_SF_cc
0x18001cbe0  mov     rbx, cs:WPP_GLOBAL_Control
0x18001cbe7  cmp     [rdi+108h], r15b
0x18001cbee  jz      loc_18001CE6F
0x18001cbf4  cmp     [rdi+109h], r15b
0x18001cbfb  jz      loc_18001CE6F
0x18001cc01  lea     r9, [rsp+900h+var_8D0]; unsigned int *
0x18001cc06  lea     r8, [rsp+900h+var_8C8]; struct _PROTOCOL_ENDPOINT_RESULT *
0x18001cc0b  mov     rdx, rsi; struct _PROTOCOL_UPDATE *
0x18001cc0e  mov     rcx, rdi; this
0x18001cc11  call    ?ProcessUpdateConnectionParameters@VPNIKEConnection@@IEAAKAEAU_PROTOCOL_UPDATE@@AEAU_PROTOCOL_ENDPOINT_RESULT@@AEAK@Z; VPNIKEConnection::ProcessUpdateConnectionParameters(_PROTOCOL_UPDATE &,_PROTOCOL_ENDPOINT_RESULT &,ulong &)
0x18001cc16  mov     esi, eax
0x18001cc18  test    eax, eax
0x18001cc1a  jz      loc_18001CCC7
0x18001cc20  test    cs:byte_1800AA941, 4
0x18001cc27  jz      loc_18001CF34
0x18001cc2d  mov     word ptr [rbp+800h+var_830], r15w
0x18001cc32  mov     word ptr [rbp+800h+var_858], r15w
0x18001cc37  mov     rax, [rdi+70h]
0x18001cc3b  test    rax, rax
0x18001cc3e  jz      short loc_18001CC4A
0x18001cc40  cmp     [rax+10h], r15
0x18001cc44  jz      short loc_18001CC4A
0x18001cc46  mov     r14d, [rax+10h]
0x18001cc4a  mov     edx, r14d
0x18001cc4d  lea     rcx, [rbp+800h+var_858]
0x18001cc51  call    ConvertPortNoToString
0x18001cc56  lea     rdx, aProcessupdatec; "ProcessUpdateConnectionParameters faile"...
0x18001cc5d  mov     r8d, esi
0x18001cc60  lea     rcx, [rbp+800h+var_830]
0x18001cc64  call    FormatRRASErrorString
0x18001cc69  test    cs:byte_1800AA941, 4
0x18001cc70  jz      loc_18001CF34
0x18001cc76  mov     rdx, [rdi+70h]
0x18001cc7a  mov     rax, rdx
0x18001cc7d  neg     rax
0x18001cc80  lea     rcx, [rdx+0A7Eh]
0x18001cc87  sbb     r8, r8
0x18001cc8a  and     r8, rcx
0x18001cc8d  lea     r9, [rdx+848h]
0x18001cc94  test    rdx, rdx
0x18001cc97  jnz     short loc_18001CC9D
0x18001cc99  lea     r9, [rbp+800h+var_868]
0x18001cc9d  lea     rax, [rbp+800h+var_858]
0x18001cca1  mov     [rsp+900h+var_8D8], rax
0x18001cca6  mov     [rsp+900h+var_8E0], r8
0x18001ccab  lea     r8, [rbp+800h+var_830]
0x18001ccaf  lea     rdx, RasVpnIkeParamTraceError
0x18001ccb6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ccbd  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ccc2  jmp     loc_18001CF34
0x18001ccc7  mov     [rsp+900h+var_8CC], 2
0x18001cccf  test    cs:byte_1800AA941, 8
0x18001ccd6  jz      short loc_18001CD55
0x18001ccd8  mov     word ptr [rbp+800h+var_858], r15w
0x18001ccdd  mov     rax, [rdi+70h]
0x18001cce1  test    rax, rax
0x18001cce4  jz      short loc_18001CCF1
0x18001cce6  cmp     [rax+10h], r15
0x18001ccea  jz      short loc_18001CCF1
0x18001ccec  mov     edx, [rax+10h]
0x18001ccef  jmp     short loc_18001CCF4
0x18001ccf1  mov     edx, r14d
0x18001ccf4  lea     rcx, [rbp+800h+var_858]
0x18001ccf8  call    ConvertPortNoToString
0x18001ccfd  test    cs:byte_1800AA941, 8
0x18001cd04  jz      short loc_18001CD55
0x18001cd06  mov     rdx, [rdi+70h]
0x18001cd0a  mov     rax, rdx
0x18001cd0d  lea     rcx, [rdx+0A7Eh]
0x18001cd14  neg     rax
0x18001cd17  sbb     r8, r8
0x18001cd1a  and     r8, rcx
0x18001cd1d  test    rdx, rdx
0x18001cd20  lea     r9, [rdx+848h]
0x18001cd27  jnz     short loc_18001CD2D
0x18001cd29  lea     r9, [rbp+800h+var_868]
0x18001cd2d  lea     rax, [rbp+800h+var_858]
0x18001cd31  mov     [rsp+900h+var_8D8], rax
0x18001cd36  mov     [rsp+900h+var_8E0], r8
0x18001cd3b  lea     r8, aSettingRasport_1; "Setting RASPortSubStatus to RASCSS_Reco"...
0x18001cd42  lea     rdx, RasVpnIkeParamTraceInfo
0x18001cd49  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001cd50  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cd55  mov     r9d, 4
0x18001cd5b  lea     r8, [rsp+900h+var_8CC]
0x18001cd60  lea     edx, [r9+0Ah]
0x18001cd64  mov     rcx, [rdi+18h]
0x18001cd68  call    cs:__imp_RasSetPortUserData
0x18001cd6e  xor     r8d, r8d
0x18001cd71  lea     edx, [r8+10h]
0x18001cd75  mov     rcx, [rdi+18h]
0x18001cd79  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x18001cd7e  mov     r10, [rdi+0F0h]
0x18001cd85  mov     rax, [r10]
0x18001cd88  mov     rcx, [rdi+70h]
0x18001cd8c  add     rcx, 2Ch ; ','
0x18001cd90  mov     [rsp+900h+var_8E0], rcx
0x18001cd95  lea     r9, [rsp+900h+var_8C8]
0x18001cd9a  lea     r8, [rsp+900h+var_8D0]
0x18001cd9f  mov     rdx, [rdi+8]
0x18001cda3  mov     rcx, r10
0x18001cda6  mov     rax, [rax+10h]
0x18001cdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdaf  mov     esi, eax
0x18001cdb1  test    eax, eax
0x18001cdb3  jz      short loc_18001CDF7
0x18001cdb5  test    cs:byte_1800AA941, 4
0x18001cdbc  jz      loc_18001CF34
0x18001cdc2  mov     word ptr [rbp+800h+var_830], r15w
0x18001cdc7  mov     word ptr [rbp+800h+var_858], r15w
0x18001cdcc  mov     rax, [rdi+70h]
0x18001cdd0  test    rax, rax
0x18001cdd3  jz      short loc_18001CDDF
0x18001cdd5  cmp     [rax+10h], r15
0x18001cdd9  jz      short loc_18001CDDF
0x18001cddb  mov     r14d, [rax+10h]
0x18001cddf  mov     edx, r14d
0x18001cde2  lea     rcx, [rbp+800h+var_858]
0x18001cde6  call    ConvertPortNoToString
0x18001cdeb  lea     rdx, aVpnikeioctlhel_4; "VPNIKEIOCTLHelper::UpdateTunnelStart fa"...
0x18001cdf2  jmp     loc_18001CC5D
0x18001cdf7  mov     rcx, [rdi+0D0h]
0x18001cdfe  mov     rax, [rcx]
0x18001ce01  lea     r8, [rsp+900h+var_8C8]
0x18001ce06  lea     rdx, ?IkeUpdateMobikeCompleteCallback@VPNIKEClientConnection@@SAXPEAXK@Z; VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback(void *,ulong)
0x18001ce0d  mov     rax, [rax]
0x18001ce10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce15  mov     esi, eax
0x18001ce17  test    eax, eax
0x18001ce19  jz      short loc_18001CE5D
0x18001ce1b  test    cs:byte_1800AA941, 4
0x18001ce22  jz      loc_18001CF34
0x18001ce28  mov     word ptr [rbp+800h+var_830], r15w
0x18001ce2d  mov     word ptr [rbp+800h+var_858], r15w
0x18001ce32  mov     rax, [rdi+70h]
0x18001ce36  test    rax, rax
0x18001ce39  jz      short loc_18001CE45
0x18001ce3b  cmp     [rax+10h], r15
0x18001ce3f  jz      short loc_18001CE45
0x18001ce41  mov     r14d, [rax+10h]
0x18001ce45  mov     edx, r14d
0x18001ce48  lea     rcx, [rbp+800h+var_858]
0x18001ce4c  call    ConvertPortNoToString
0x18001ce51  lea     rdx, aSendmobikeupda; "SendMobikeUpdate failed: %d"
0x18001ce58  jmp     loc_18001CC5D
0x18001ce5d  mov     edx, 40h ; '@'; unsigned int
0x18001ce62  mov     rcx, rdi; this
0x18001ce65  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x18001ce6a  jmp     loc_18001CF3E
0x18001ce6f  test    cs:byte_1800AA941, 8
0x18001ce76  jz      loc_18001CEFF
0x18001ce7c  mov     word ptr [rbp+800h+var_858], r15w
0x18001ce81  mov     rax, [rdi+70h]
0x18001ce85  test    rax, rax
0x18001ce88  jz      short loc_18001CE94
0x18001ce8a  cmp     [rax+10h], r15
0x18001ce8e  jz      short loc_18001CE94
0x18001ce90  mov     r14d, [rax+10h]
0x18001ce94  mov     edx, r14d
0x18001ce97  lea     rcx, [rbp+800h+var_858]
0x18001ce9b  call    ConvertPortNoToString
0x18001cea0  test    cs:byte_1800AA941, 8
0x18001cea7  jz      short loc_18001CEF8
0x18001cea9  mov     rdx, [rdi+70h]
0x18001cead  mov     rax, rdx
0x18001ceb0  lea     rcx, [rdx+0A7Eh]
0x18001ceb7  neg     rax
0x18001ceba  sbb     r8, r8
0x18001cebd  and     r8, rcx
0x18001cec0  test    rdx, rdx
0x18001cec3  lea     r9, [rdx+848h]
0x18001ceca  jnz     short loc_18001CED0
0x18001cecc  lea     r9, [rbp+800h+var_868]
0x18001ced0  lea     rax, [rbp+800h+var_858]
0x18001ced4  mov     [rsp+900h+var_8D8], rax
0x18001ced9  mov     [rsp+900h+var_8E0], r8
0x18001cede  lea     r8, aMobikeIsDisabl; "Mobike is disabled either on initiator/"...
0x18001cee5  lea     rdx, RasVpnIkeParamTraceInfo
0x18001ceec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001cef3  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cef8  mov     rbx, cs:WPP_GLOBAL_Control
0x18001ceff  mov     esi, 34Bh
0x18001cf04  lea     rax, WPP_GLOBAL_Control
0x18001cf0b  cmp     rbx, rax
0x18001cf0e  jz      short loc_18001CF34
0x18001cf10  test    byte ptr [rbx+1Ch], 1
0x18001cf14  jz      short loc_18001CF34
0x18001cf16  cmp     byte ptr [rbx+19h], 2
0x18001cf1a  jb      short loc_18001CF34
0x18001cf1c  mov     edx, 2Ch ; ','
0x18001cf21  mov     r9d, esi
0x18001cf24  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001cf2b  mov     rcx, [rbx+10h]
0x18001cf2f  call    WPP_SF_d
0x18001cf34  mov     edx, esi; unsigned int
0x18001cf36  mov     rcx, rdi; this
0x18001cf39  call    ?NotifyUpdateConnectionStatus@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::NotifyUpdateConnectionStatus(ulong)
0x18001cf3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf45  lea     rax, WPP_GLOBAL_Control
0x18001cf4c  cmp     rcx, rax
0x18001cf4f  jz      short loc_18001CF73
0x18001cf51  test    byte ptr [rcx+1Ch], 1
0x18001cf55  jz      short loc_18001CF73
0x18001cf57  cmp     byte ptr [rcx+19h], 6
0x18001cf5b  jb      short loc_18001CF73
0x18001cf5d  mov     edx, 2Dh ; '-'
0x18001cf62  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001cf69  mov     rcx, [rcx+10h]
0x18001cf6d  call    WPP_SF_
0x18001cf72  nop
0x18001cf73  lea     rcx, [rsp+900h+var_8A0]; this
0x18001cf78  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18001cf7d  mov     rcx, [rbp+800h+var_30]
0x18001cf84  xor     rcx, rsp; StackCookie
0x18001cf87  call    __security_check_cookie
0x18001cf8c  mov     rbx, [rsp+900h+arg_10]
0x18001cf94  add     rsp, 8E0h
0x18001cf9b  pop     r15
0x18001cf9d  pop     r14
0x18001cf9f  pop     rdi
0x18001cfa0  pop     rsi
0x18001cfa1  pop     rbp
  ... truncated ...
```
